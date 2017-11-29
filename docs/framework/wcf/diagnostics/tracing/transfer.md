---
title: Transferir
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfcfa36c-d3bb-44b4-aa15-1c922c6f73e6
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 40cd80b2b4e2f949b92f4c89cde6b271a502d047
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="transfer"></a><span data-ttu-id="085b3-102">Transferir</span><span class="sxs-lookup"><span data-stu-id="085b3-102">Transfer</span></span>
<span data-ttu-id="085b3-103">Este tópico descreve a transferência de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] modelo de rastreamento de atividade.</span><span class="sxs-lookup"><span data-stu-id="085b3-103">This topic describes transfer in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] activity tracing model.</span></span>  
  
## <a name="transfer-definition"></a><span data-ttu-id="085b3-104">Definição de transferência</span><span class="sxs-lookup"><span data-stu-id="085b3-104">Transfer Definition</span></span>  
 <span data-ttu-id="085b3-105">As transferências entre atividades representam causais relações entre eventos em que as atividades relacionadas em pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="085b3-105">Transfers between activities represent causal relationships between events in the related activities within endpoints.</span></span> <span data-ttu-id="085b3-106">Duas atividades estão relacionadas com transferências quando fluxos de controle entre essas atividades, por exemplo, uma chamada de método Cruzando os limites de atividade.</span><span class="sxs-lookup"><span data-stu-id="085b3-106">Two activities are related with transfers when control flows between these activities, for example, a method call crossing activity boundaries.</span></span> <span data-ttu-id="085b3-107">Em [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], quando os bytes são recebidos do serviço, a escuta na atividade é transferida para a atividade receber Bytes em que o objeto de mensagem é criado.</span><span class="sxs-lookup"><span data-stu-id="085b3-107">In [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], when bytes are incoming on the service, the Listen At activity is transferred to the Receive Bytes activity where the message object is created.</span></span> <span data-ttu-id="085b3-108">Para obter uma lista de cenários de rastreamento ponta a ponta e sua respectiva atividade e design de rastreamento, consulte [cenários de rastreamento ponta a ponta](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="085b3-108">For a list of end-to-end tracing scenarios, and their respective activity and tracing design, see [End-To-End Tracing Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md).</span></span>  
  
 <span data-ttu-id="085b3-109">Para emitir rastreamentos de transferência, use o `ActivityTracing` configuração da origem de rastreamento, conforme demonstrado pelo código de configuração a seguir.</span><span class="sxs-lookup"><span data-stu-id="085b3-109">To emit transfer traces, use the `ActivityTracing` setting on the trace source as demonstrated by the following configuration code.</span></span>  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing">  
```  
  
## <a name="using-transfer-to-correlate-activities-within-endpoints"></a><span data-ttu-id="085b3-110">Usar a transferência para correlacionar atividades dentro de pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="085b3-110">Using Transfer to Correlate Activities Within Endpoints</span></span>  
 <span data-ttu-id="085b3-111">Atividades e transferências de permitem que o usuário com probabilidade localizar a causa do erro.</span><span class="sxs-lookup"><span data-stu-id="085b3-111">Activities and transfers permit the user to probabilistically locate the root cause of an error.</span></span> <span data-ttu-id="085b3-112">Por exemplo, se é transferir e voltar entre as atividades M e N respectivamente de componentes M e N, e uma falha ocorre no direito de N após a transferência M, podemos pode desenhar final que é provavelmente devido a dados de transmissão do N para M.</span><span class="sxs-lookup"><span data-stu-id="085b3-112">For example, if we transfer back and forth between activities M and N respectively in components M and N, and a crash happens in N right after the transfer back to M, we can draw the conclusion that it is likely due to N’s passing data back to M.</span></span>  
  
 <span data-ttu-id="085b3-113">Um rastreamento de transferência é emitido de atividade M a atividade de N quando há um fluxo de controle entre M e N. Por exemplo, N executa algum trabalho para M devido a uma chamada de método Cruzando os limites das atividades.</span><span class="sxs-lookup"><span data-stu-id="085b3-113">A transfer trace is emitted from activity M to activity N when there is a flow of control between M and N. For example, N performs some work for M because of a method call crossing the activities’ boundaries.</span></span> <span data-ttu-id="085b3-114">N pode já existir ou tiver sido criada.</span><span class="sxs-lookup"><span data-stu-id="085b3-114">N may already exist or has been created.</span></span> <span data-ttu-id="085b3-115">N é gerado pelo M quando N é uma nova atividade que executa um trabalho para M.</span><span class="sxs-lookup"><span data-stu-id="085b3-115">N is spawned by M when N is a new activity that performs some work for M.</span></span>  
  
 <span data-ttu-id="085b3-116">Uma transferência de M a N não pode ser seguida por uma transferência de N a M. Isso ocorre porque o M pode gerar algum trabalho N e não rastrear quando N de que o trabalho for concluído.</span><span class="sxs-lookup"><span data-stu-id="085b3-116">A transfer from M to N may not be followed by a transfer back from N to M. This is because M can spawn some work in N and do not track when N completes that work.</span></span> <span data-ttu-id="085b3-117">Na verdade, M pode terminar antes N concluir sua tarefa.</span><span class="sxs-lookup"><span data-stu-id="085b3-117">In fact, M can terminate before N completes its task.</span></span> <span data-ttu-id="085b3-118">Isso ocorre na atividade "Abrir ServiceHost" (M) que gera a atividades de ouvinte (N) e, em seguida, termina.</span><span class="sxs-lookup"><span data-stu-id="085b3-118">This happens in the "Open ServiceHost" activity (M) that spawns Listener activities (N) and then terminates.</span></span> <span data-ttu-id="085b3-119">Uma transferência de N a M significa que N concluído o trabalho relacionado a M.</span><span class="sxs-lookup"><span data-stu-id="085b3-119">A transfer back from N to M means that N completed the work related to M.</span></span>  
  
 <span data-ttu-id="085b3-120">N pode continuar a executar outro processamento não relacionado a M, por exemplo, uma atividade de autenticador existente (N) que mantém receber solicitações de logon (M) de atividades de logon diferente.</span><span class="sxs-lookup"><span data-stu-id="085b3-120">N can continue performing other processing unrelated to M, for example, an existing authenticator activity (N) that keeps receiving login requests (M) from different login activities.</span></span>  
  
 <span data-ttu-id="085b3-121">Uma relação de aninhamento não necessariamente existe entre atividades M e N. Isso pode acontecer devido a duas razões.</span><span class="sxs-lookup"><span data-stu-id="085b3-121">A nesting relationship does not necessarily exist between activities M and N. This can happen due to two reasons.</span></span> <span data-ttu-id="085b3-122">Primeiro, quando a atividade M não monitora o processamento real realizadas em N embora iniciada M s. Segundo, quando N já existe.</span><span class="sxs-lookup"><span data-stu-id="085b3-122">First, when activity M does not monitor the actual processing performed in N although M initiated N. Second, when N already exists.</span></span>  
  
## <a name="example-of-transfers"></a><span data-ttu-id="085b3-123">Exemplo de transferências</span><span class="sxs-lookup"><span data-stu-id="085b3-123">Example of Transfers</span></span>  
 <span data-ttu-id="085b3-124">Listas de dois exemplos a seguir transferência.</span><span class="sxs-lookup"><span data-stu-id="085b3-124">The following lists two transfer examples.</span></span>  
  
-   <span data-ttu-id="085b3-125">Quando você cria um host de serviço, o construtor de assumir o controle do código de chamada ou o código de chamada é transferida para o construtor.</span><span class="sxs-lookup"><span data-stu-id="085b3-125">When you create a service host, the constructor gains control from the calling code, or the calling code transfers to the constructor.</span></span> <span data-ttu-id="085b3-126">Quando o construtor concluiu a execução, ele retorna o controle para o código de chamada ou o construtor de transferências de volta para o código de chamada.</span><span class="sxs-lookup"><span data-stu-id="085b3-126">When the constructor has finished executing, it returns control to the calling code, or the constructor transfers back to the calling code.</span></span> <span data-ttu-id="085b3-127">Esse é o caso de uma relação aninhada.</span><span class="sxs-lookup"><span data-stu-id="085b3-127">This is the case of a nested relationship.</span></span>  
  
-   <span data-ttu-id="085b3-128">Quando um ouvinte de processamento de dados de transporte é iniciado, ele cria um novo thread e passa para a atividade receber Bytes o contexto apropriado para processamento, passando o controle e dados.</span><span class="sxs-lookup"><span data-stu-id="085b3-128">When a listener starts processing transport data, it creates a new thread and hands to the Receive Bytes activity the appropriate context for processing, passing control and data.</span></span> <span data-ttu-id="085b3-129">Quando esse thread terminou de processar a solicitação, a atividade receber Bytes passa nada de volta para o ouvinte.</span><span class="sxs-lookup"><span data-stu-id="085b3-129">When that thread has finished processing the request, the Receive Bytes activity passes nothing back to the listener.</span></span> <span data-ttu-id="085b3-130">Nesse caso, temos uma transferência em mas nenhuma transferência de nova atividade de thread.</span><span class="sxs-lookup"><span data-stu-id="085b3-130">In this case, we have a transfer in but no transfer out of the new thread activity.</span></span> <span data-ttu-id="085b3-131">As duas atividades estão relacionadas, mas não aninhadas.</span><span class="sxs-lookup"><span data-stu-id="085b3-131">The two activities are related but not nested.</span></span>  
  
## <a name="activity-transfer-sequence"></a><span data-ttu-id="085b3-132">Sequência de transferência de atividade</span><span class="sxs-lookup"><span data-stu-id="085b3-132">Activity Transfer Sequence</span></span>  
 <span data-ttu-id="085b3-133">Uma sequência de transferência de atividade válido inclui as seguintes etapas.</span><span class="sxs-lookup"><span data-stu-id="085b3-133">A well-formed activity transfer sequence includes the following steps.</span></span>  
  
1.  <span data-ttu-id="085b3-134">Iniciar uma nova atividade, que consiste em selecionar um novo gAId.</span><span class="sxs-lookup"><span data-stu-id="085b3-134">Begin a new activity, which consists of selecting a new gAId.</span></span>  
  
2.  <span data-ttu-id="085b3-135">Emissão de um rastreamento de transferência para esse novo gAId da ID da atividade atual</span><span class="sxs-lookup"><span data-stu-id="085b3-135">Emit a transfer trace to that new gAId from the current activity ID</span></span>  
  
3.  <span data-ttu-id="085b3-136">Definir a nova ID de TLS</span><span class="sxs-lookup"><span data-stu-id="085b3-136">Set the new ID in TLS</span></span>  
  
4.  <span data-ttu-id="085b3-137">Emita um rastreamento de início para indicar o início da nova atividade por.</span><span class="sxs-lookup"><span data-stu-id="085b3-137">Emit a start trace to indicate the beginning of the new activity by.</span></span>  
  
5.  <span data-ttu-id="085b3-138">Voltar para a atividade original consiste no seguinte:</span><span class="sxs-lookup"><span data-stu-id="085b3-138">Return to the original activity consists of the following:</span></span>  
  
6.  <span data-ttu-id="085b3-139">Emissão de um rastreamento de transferência para o gAId original</span><span class="sxs-lookup"><span data-stu-id="085b3-139">Emit a transfer trace to the original gAId</span></span>  
  
7.  <span data-ttu-id="085b3-140">Emissão de um rastreamento de parada para indicar o fim da nova atividade</span><span class="sxs-lookup"><span data-stu-id="085b3-140">Emit a Stop trace to indicate the end of the new activity</span></span>  
  
8.  <span data-ttu-id="085b3-141">Defina o TLS para o antigo gAId.</span><span class="sxs-lookup"><span data-stu-id="085b3-141">Set TLS to the old gAId.</span></span>  
  
 <span data-ttu-id="085b3-142">O exemplo de código a seguir demonstra como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="085b3-142">The following code example demonstrates how to do this.</span></span> <span data-ttu-id="085b3-143">Este exemplo supõe que uma chamada de bloqueio é feita ao transferir para a nova atividade e inclui os rastreamentos de suspender/retomar.</span><span class="sxs-lookup"><span data-stu-id="085b3-143">This sample assumes a blocking call is made when transferring to the new activity, and includes suspend/resume traces.</span></span>  
  
```  
// 0. Create a trace source  
TraceSource ts = new TraceSource("myTS");  
// 1. remember existing ("ambient") activity for clean up  
Guid oldGuid = Trace.CorrelationManager.ActivityId;  
// this will be our new activity  
Guid newGuid = Guid.NewGuid();   
// 2. call transfer, indicating that we are switching to the new AID  
ts.TraceTransfer(667, "Transferring.", newGuid);  
// 3. Suspend the current activity.  
ts.TraceEvent(TraceEventType.Suspend, 667, "Suspend: Activity " + i-1);  
// 4. set the new AID in TLS  
Trace.CorrelationManager.ActivityId = newGuid;  
// 5. Emit the start trace  
ts.TraceEvent(TraceEventType.Start, 667, "Boundary: Activity " + i);  
// trace something  
ts.TraceEvent(TraceEventType.Information, 667, "Hello from activity " + i);  
// Perform Work  
// some work.  
// Return  
ts.TraceEvent(TraceEventType.Information, 667, "Work complete on activity " + i);   
// 6. Emit the transfer returning to the original activity  
ts.TraceTransfer(667, "Transferring Back.", oldGuid);  
// 7. Emit the End trace  
ts.TraceEvent(TraceEventType.Stop, 667, "Boundary: Activity " + i);  
// 8. Change the tls variable to the original AID  
Trace.CorrelationManager.ActivityId = oldGuid;    
// 9. Resume the old activity  
ts.TraceEvent(TraceEventType.Resume, 667, "Resume: Activity " + i-1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="085b3-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="085b3-144">See Also</span></span>  
 [<span data-ttu-id="085b3-145">Configurando o rastreamento</span><span class="sxs-lookup"><span data-stu-id="085b3-145">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
 [<span data-ttu-id="085b3-146">Usando o Visualizador de Rastreamento de Serviço para exibir rastreamentos correlacionados e solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="085b3-146">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [<span data-ttu-id="085b3-147">Cenários de rastreamento ponta a ponta</span><span class="sxs-lookup"><span data-stu-id="085b3-147">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 <span data-ttu-id="085b3-148">[Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) (Ferramenta Visualizador de rastreamento de serviço (SvcTraceViewer.exe))</span><span class="sxs-lookup"><span data-stu-id="085b3-148">[Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)</span></span>