---
title: "Serviço de roteamento"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca7c216a-5141-4132-8193-102c181d2eba
caps.latest.revision: "13"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: a4f58c5124e229f1692dabbb0abded0e21a346f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="routing-service"></a><span data-ttu-id="a11dd-102">Serviço de roteamento</span><span class="sxs-lookup"><span data-stu-id="a11dd-102">Routing Service</span></span>
<span data-ttu-id="a11dd-103">O serviço de roteamento é um intermediário SOAP genérico que atua como um roteador de mensagem.</span><span class="sxs-lookup"><span data-stu-id="a11dd-103">The Routing Service is a generic SOAP intermediary that acts as a message router.</span></span> <span data-ttu-id="a11dd-104">A funcionalidade básica do serviço de roteamento é a capacidade para rotear mensagens com base no conteúdo da mensagem, que permite que uma mensagem a serem encaminhados para um ponto de extremidade do cliente com base em um valor dentro da mensagem, no cabeçalho ou no corpo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="a11dd-104">The core functionality of the Routing Service is the ability to route messages based on message content, which allows a message to be forwarded to a client endpoint based on a value within the message itself, in either the header or the message body.</span></span>  
  
 <span data-ttu-id="a11dd-105">O <xref:System.ServiceModel.Routing.RoutingService> é implementado como um [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] serviço o <xref:System.ServiceModel.Routing> namespace.</span><span class="sxs-lookup"><span data-stu-id="a11dd-105">The <xref:System.ServiceModel.Routing.RoutingService> is implemented as a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service in the <xref:System.ServiceModel.Routing> namespace.</span></span> <span data-ttu-id="a11dd-106">O serviço de roteamento expõe um ou mais pontos de extremidade que recebem mensagens e, em seguida, rotas de cada mensagem para um ou mais pontos de extremidade de cliente com base no conteúdo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="a11dd-106">The Routing Service exposes one or more service endpoints that receive messages and then routes each message to one or more client endpoints based on the message content.</span></span> <span data-ttu-id="a11dd-107">O serviço fornece os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="a11dd-107">The service provides the following features:</span></span>  
  
-   <span data-ttu-id="a11dd-108">Roteamento baseado em conteúdo</span><span class="sxs-lookup"><span data-stu-id="a11dd-108">Content-based routing</span></span>  
  
    -   <span data-ttu-id="a11dd-109">Agregação de serviço</span><span class="sxs-lookup"><span data-stu-id="a11dd-109">Service aggregation</span></span>  
  
    -   <span data-ttu-id="a11dd-110">Controle de versão de serviço</span><span class="sxs-lookup"><span data-stu-id="a11dd-110">Service versioning</span></span>  
  
    -   <span data-ttu-id="a11dd-111">Roteamento de prioridade</span><span class="sxs-lookup"><span data-stu-id="a11dd-111">Priority routing</span></span>  
  
    -   <span data-ttu-id="a11dd-112">Configuração dinâmica</span><span class="sxs-lookup"><span data-stu-id="a11dd-112">Dynamic configuration</span></span>  
  
-   <span data-ttu-id="a11dd-113">Ponte de protocolo</span><span class="sxs-lookup"><span data-stu-id="a11dd-113">Protocol bridging</span></span>  
  
-   <span data-ttu-id="a11dd-114">Processamento de SOAP</span><span class="sxs-lookup"><span data-stu-id="a11dd-114">SOAP processing</span></span>  
  
-   <span data-ttu-id="a11dd-115">Tratamento avançado de erros</span><span class="sxs-lookup"><span data-stu-id="a11dd-115">Advanced error handling</span></span>  
  
-   <span data-ttu-id="a11dd-116">Pontos de extremidade de backup</span><span class="sxs-lookup"><span data-stu-id="a11dd-116">Backup endpoints</span></span>  
  
 <span data-ttu-id="a11dd-117">Embora seja possível criar um serviço intermediário que realiza um ou mais dessas metas, geralmente essa implementação estiver associada a um cenário específico ou uma solução e não pode ser aplicada prontamente para novos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="a11dd-117">While it is possible to create an intermediary service that accomplishes one or more of these goals, often such an implementation is tied to a specific scenario or solution and cannot be readily applied to new applications.</span></span>  
  
 <span data-ttu-id="a11dd-118">O serviço de roteamento fornece um intermediário SOAP genérico, podem ser configurado dinamicamente, conectável que é compatível com o [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] serviço e canal de modelos e permite que você execute roteamento baseado em conteúdo de mensagens de baseado em SOAP.</span><span class="sxs-lookup"><span data-stu-id="a11dd-118">The Routing Service provides a generic, dynamically configurable, pluggable SOAP intermediary that is compatible with the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Service and Channel models and allows you to perform content-based routing of SOAP-based messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a11dd-119">O serviço de roteamento não atualmente suporte a roteamento de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] serviços REST.</span><span class="sxs-lookup"><span data-stu-id="a11dd-119">The Routing Service does not currently support routing of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST services.</span></span>  <span data-ttu-id="a11dd-120">Para encaminhar chamadas REST, considere o uso de <xref:System.Web.Routing> ou [Application Request Routing](http://go.microsoft.com/fwlink/?LinkId=164589) (http://go.microsoft.com/fwlink/?LinkId=164589).</span><span class="sxs-lookup"><span data-stu-id="a11dd-120">To route REST calls, consider using <xref:System.Web.Routing> or [Application Request Routing](http://go.microsoft.com/fwlink/?LinkId=164589) (http://go.microsoft.com/fwlink/?LinkId=164589).</span></span>  
  
## <a name="content-based-routing"></a><span data-ttu-id="a11dd-121">Roteamento baseado em conteúdo</span><span class="sxs-lookup"><span data-stu-id="a11dd-121">Content-Based Routing</span></span>  
 <span data-ttu-id="a11dd-122">Roteamento baseado em conteúdo é a capacidade de encaminhar uma mensagem com base em um ou mais valores contidos na mensagem.</span><span class="sxs-lookup"><span data-stu-id="a11dd-122">Content-based routing is the ability to route a message based on one or more values contained within the message.</span></span> <span data-ttu-id="a11dd-123">O serviço de roteamento verifica se cada mensagem e a roteia para o ponto de extremidade de destino com base no conteúdo da mensagem e a lógica de roteamento que você criar.</span><span class="sxs-lookup"><span data-stu-id="a11dd-123">The Routing Service inspects each message and routes it to the destination endpoint based on the message contents and the routing logic you create.</span></span> <span data-ttu-id="a11dd-124">Roteamento baseado em conteúdo fornece a base para agregação de serviço, controle de versão de serviço e roteamento de prioridade.</span><span class="sxs-lookup"><span data-stu-id="a11dd-124">Content-based routing provides the basis for service aggregation, service versioning, and priority routing.</span></span>  
  
 <span data-ttu-id="a11dd-125">Para implementar roteamento baseado em conteúdo, o serviço de roteamento depende <xref:System.ServiceModel.Dispatcher.MessageFilter> implementações que são usadas para corresponder valores específicos nas mensagens deve ser roteada.</span><span class="sxs-lookup"><span data-stu-id="a11dd-125">To implement content-based routing, the Routing Service relies on <xref:System.ServiceModel.Dispatcher.MessageFilter> implementations that are used to match specific values within the messages to be routed.</span></span> <span data-ttu-id="a11dd-126">Se um **MessageFilter** corresponde uma mensagem, a mensagem é roteada para o ponto de extremidade de destino associado a **MessageFilter**.</span><span class="sxs-lookup"><span data-stu-id="a11dd-126">If a **MessageFilter** matches a message, the message is routed to the destination endpoint associated with the **MessageFilter**.</span></span>  <span data-ttu-id="a11dd-127">Filtros de mensagem são agrupados em tabelas de filtro (<xref:System.ServiceModel.Routing.Configuration.FilterTableCollection>) para construir a lógica complexa de roteamento.</span><span class="sxs-lookup"><span data-stu-id="a11dd-127">Message filters are grouped together into filter tables (<xref:System.ServiceModel.Routing.Configuration.FilterTableCollection>) to construct complex routing logic.</span></span> <span data-ttu-id="a11dd-128">Por exemplo, uma tabela de filtro pode conter cinco filtros de mensagem mutuamente exclusivos que fazer com que as mensagens sejam roteadas para apenas um dos pontos de extremidade de cinco destino.</span><span class="sxs-lookup"><span data-stu-id="a11dd-128">For example, a filter table might contain five mutually exclusive message filters that cause messages to be routed to only one of the five destination endpoints.</span></span>  
  
 <span data-ttu-id="a11dd-129">O serviço de roteamento permite configurar a lógica que é usada para executar o roteamento baseado em conteúdo, bem como atualizar dinamicamente a lógica de roteamento em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="a11dd-129">The Routing Service allows you to configure the logic that is used to perform content-based routing, as well as dynamically update the routing logic at run time.</span></span>  
  
 <span data-ttu-id="a11dd-130">Por meio do agrupamento de filtros de mensagem em tabelas de filtro, lógica de roteamento pode ser construída que permite que você manipule vários cenários de roteamentos, como:</span><span class="sxs-lookup"><span data-stu-id="a11dd-130">Through the grouping of message filters into filter tables, routing logic can be constructed that allows you to handle multiple routing scenarios such as:</span></span>  
  
-   <span data-ttu-id="a11dd-131">Agregação de serviço</span><span class="sxs-lookup"><span data-stu-id="a11dd-131">Service aggregation</span></span>  
  
-   <span data-ttu-id="a11dd-132">Controle de versão de serviço</span><span class="sxs-lookup"><span data-stu-id="a11dd-132">Service versioning</span></span>  
  
-   <span data-ttu-id="a11dd-133">Roteamento de prioridade</span><span class="sxs-lookup"><span data-stu-id="a11dd-133">Priority routing</span></span>  
  
-   <span data-ttu-id="a11dd-134">Configuração dinâmica</span><span class="sxs-lookup"><span data-stu-id="a11dd-134">Dynamic configuration</span></span>  
  
 <span data-ttu-id="a11dd-135">Para obter mais informações sobre filtros de mensagem e tabelas de filtro, consulte [roteamento Introdução](../../../../docs/framework/wcf/feature-details/routing-introduction.md) e [filtros de mensagem](../../../../docs/framework/wcf/feature-details/message-filters.md).</span><span class="sxs-lookup"><span data-stu-id="a11dd-135">For more information about message filters and filter tables, see [Routing Introduction](../../../../docs/framework/wcf/feature-details/routing-introduction.md) and [Message Filters](../../../../docs/framework/wcf/feature-details/message-filters.md).</span></span>  
  
### <a name="service-aggregation"></a><span data-ttu-id="a11dd-136">Agregação de serviço</span><span class="sxs-lookup"><span data-stu-id="a11dd-136">Service Aggregation</span></span>  
 <span data-ttu-id="a11dd-137">Usando o roteamento baseado em conteúdo, você pode expor um ponto de extremidade que recebe mensagens do aplicativo cliente externo e, em seguida, encaminha cada mensagem para o ponto de extremidade interno apropriado com base em um valor dentro da mensagem.</span><span class="sxs-lookup"><span data-stu-id="a11dd-137">By using content-based routing, you can expose one endpoint that receives messages from external client applications and then routes each message to the appropriate internal endpoint based on a value within the message.</span></span> <span data-ttu-id="a11dd-138">Isso é útil para oferecer um ponto de extremidade específico para uma variedade de aplicativos back-end e também para apresentar um ponto de extremidade do aplicativo para os clientes durante o cálculo de seu aplicativo em uma variedade de serviços.</span><span class="sxs-lookup"><span data-stu-id="a11dd-138">This is useful to offer one specific endpoint for a variety of back-end applications, and also to present one application endpoint to customers while factoring your application into a variety of services.</span></span>  
  
### <a name="service-versioning"></a><span data-ttu-id="a11dd-139">Controle de versão de serviço</span><span class="sxs-lookup"><span data-stu-id="a11dd-139">Service Versioning</span></span>  
 <span data-ttu-id="a11dd-140">Ao migrar para uma nova versão de sua solução, você pode ter que manter a versão antiga em paralelo para atender a clientes existentes.</span><span class="sxs-lookup"><span data-stu-id="a11dd-140">When migrating to a new version of your solution, you may have to maintain the old version in parallel to serve existing customers.</span></span> <span data-ttu-id="a11dd-141">Geralmente, isso requer que clientes conectando-se para a versão mais recente devem usar um endereço diferente ao se comunicar com a solução.</span><span class="sxs-lookup"><span data-stu-id="a11dd-141">Often this requires that clients connecting to the newer version must use a different address when communicating with the solution.</span></span> <span data-ttu-id="a11dd-142">O serviço de roteamento permite expor um ponto de extremidade de serviço que serve a ambas as versões de sua solução pelo roteamento de mensagens para a solução apropriada com base nas informações específicas de versão contidas na mensagem.</span><span class="sxs-lookup"><span data-stu-id="a11dd-142">The Routing Service allows you to expose one service endpoint that serves both versions of your solution by routing messages to the appropriate solution based on version-specific information contained in the message.</span></span> <span data-ttu-id="a11dd-143">Para obter um exemplo de tal implementação consulte [como: controle de versão do serviço](../../../../docs/framework/wcf/feature-details/how-to-service-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="a11dd-143">For an example of such an implementation see [How To: Service Versioning](../../../../docs/framework/wcf/feature-details/how-to-service-versioning.md).</span></span>  
  
### <a name="priority-routing"></a><span data-ttu-id="a11dd-144">Roteamento de prioridade</span><span class="sxs-lookup"><span data-stu-id="a11dd-144">Priority Routing</span></span>  
 <span data-ttu-id="a11dd-145">Ao fornecer um serviço para vários clientes, você pode ter um contrato de nível de serviço (SLA) com alguns parceiros que requer que todos os dados desses parceiros para ser processada separadamente a partir de outros clientes.</span><span class="sxs-lookup"><span data-stu-id="a11dd-145">When providing a service for multiple clients, you may have a service level agreement (SLA) with some partners that requires all data from these partners to be processed separately from that of other clients.</span></span> <span data-ttu-id="a11dd-146">Usando um filtro que procura informações específicas do cliente contidas na mensagem, você pode facilmente rotear mensagens de parceiros específicos para um ponto de extremidade que foi criada para atender aos requisitos de SLA.</span><span class="sxs-lookup"><span data-stu-id="a11dd-146">By using a filter that looks for customer-specific information contained in the message, you can easily route messages from specific partners to an endpoint that has been created to meet their SLA requirements.</span></span>  
  
## <a name="dynamic-configuration"></a><span data-ttu-id="a11dd-147">Configuração dinâmica</span><span class="sxs-lookup"><span data-stu-id="a11dd-147">Dynamic Configuration</span></span>  
 <span data-ttu-id="a11dd-148">Para dar suporte a sistemas de missão crítica, onde as mensagens devem ser processadas sem qualquer interrupção no serviço, é essencial que você poderá modificar a configuração dos componentes dentro do sistema em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="a11dd-148">To support mission-critical systems, where messages must be processed without any service interruptions, it is vital that you be able to modify the configuration of components within the system at run time.</span></span> <span data-ttu-id="a11dd-149">Para dar suporte a essa necessidade, o serviço de roteamento fornece um <xref:System.ServiceModel.IExtension%601> implementação, o <xref:System.ServiceModel.Routing.RoutingExtension>, que permite que a atualização dinâmica da configuração do serviço de roteamento em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="a11dd-149">To support this need, the Routing Service provides an <xref:System.ServiceModel.IExtension%601> implementation, the <xref:System.ServiceModel.Routing.RoutingExtension>, which allows dynamic updating of the Routing Service configuration at run time.</span></span>  
  
 <span data-ttu-id="a11dd-150">Para obter mais informações sobre a configuração dinâmica do serviço de roteamento, consulte [roteamento Introdução](../../../../docs/framework/wcf/feature-details/routing-introduction.md).</span><span class="sxs-lookup"><span data-stu-id="a11dd-150">For more information about dynamic configuration of the Routing Service, see [Routing Introduction](../../../../docs/framework/wcf/feature-details/routing-introduction.md).</span></span>  
  
## <a name="protocol-bridging"></a><span data-ttu-id="a11dd-151">Ponte de protocolo</span><span class="sxs-lookup"><span data-stu-id="a11dd-151">Protocol Bridging</span></span>  
 <span data-ttu-id="a11dd-152">Um dos desafios em cenários intermediários é que os pontos de extremidade internos podem ter diferente transporte ou requisitos de versão do SOAP que o ponto de extremidade que as mensagens são recebidas em.</span><span class="sxs-lookup"><span data-stu-id="a11dd-152">One of the challenges in intermediary scenarios is that the internal endpoints may have different transport or SOAP version requirements than the endpoint that messages are received on.</span></span> <span data-ttu-id="a11dd-153">Para dar suporte a esse cenário, o serviço de roteamento pode ligar protocolos, incluindo o processamento da mensagem SOAP para o <xref:System.ServiceModel.Channels.MessageVersion> exigido pela extremidade de destino.</span><span class="sxs-lookup"><span data-stu-id="a11dd-153">To support this scenario, the Routing Service can bridge protocols, including processing the SOAP message to the <xref:System.ServiceModel.Channels.MessageVersion> required by the destination endpoint(s).</span></span> <span data-ttu-id="a11dd-154">Dessa forma, um protocolo pode ser usado para comunicação interna, enquanto outra pode ser usada para comunicações externas.</span><span class="sxs-lookup"><span data-stu-id="a11dd-154">In this way, one protocol can be used for internal communication, while another can be used for external communication.</span></span>  
  
 <span data-ttu-id="a11dd-155">Para dar suporte a roteamento de mensagens entre pontos de extremidade com transportes diferentes, o serviço de roteamento usa associações fornecidas pelo sistema que permitem que o serviço acabar com protocolos diferentes.</span><span class="sxs-lookup"><span data-stu-id="a11dd-155">To support the routing of messages between endpoints with different transports, the Routing Service uses system-provided bindings that enable the service to bridge dissimilar protocols.</span></span> <span data-ttu-id="a11dd-156">Isso ocorre automaticamente quando o ponto de extremidade do serviço exposto pelo serviço de roteamento usa um protocolo diferente que os pontos de extremidade do cliente que as mensagens são roteadas.</span><span class="sxs-lookup"><span data-stu-id="a11dd-156">This occurs automatically when the service endpoint exposed by the Routing Service uses a different protocol than the client endpoints that messages are routed to.</span></span>  
  
## <a name="soap-processing"></a><span data-ttu-id="a11dd-157">Processamento de SOAP</span><span class="sxs-lookup"><span data-stu-id="a11dd-157">SOAP Processing</span></span>  
 <span data-ttu-id="a11dd-158">Um requisito comum de roteamento é a capacidade para rotear mensagens entre pontos de extremidade com diferentes requisitos de SOAP.</span><span class="sxs-lookup"><span data-stu-id="a11dd-158">A common routing requirement is the ability to route messages between endpoints with differing SOAP requirements.</span></span> <span data-ttu-id="a11dd-159">Para dar suporte a esse requisito, o serviço de roteamento fornece um <xref:System.ServiceModel.Routing.SoapProcessingBehavior> que cria automaticamente um novo **MessageVersion** que atenda aos requisitos do ponto de extremidade de destino antes da mensagem é roteada para ele.</span><span class="sxs-lookup"><span data-stu-id="a11dd-159">To support this requirement, the Routing Service provides a <xref:System.ServiceModel.Routing.SoapProcessingBehavior> that automatically creates a new **MessageVersion** that meets the requirements of the destination endpoint before the message is routed to it.</span></span> <span data-ttu-id="a11dd-160">Esse comportamento também cria um novo **MessageVersion** qualquer mensagem de resposta antes de retorná-lo ao aplicativo cliente solicitante, para garantir que o **MessageVersion** da resposta é igual do a solicitação original.</span><span class="sxs-lookup"><span data-stu-id="a11dd-160">This behavior also creates a new **MessageVersion** for any response message before returning it to the requesting client application, to ensure that the **MessageVersion** of the response matches that of the original request.</span></span>  
  
 <span data-ttu-id="a11dd-161">Para obter mais informações sobre o processamento de SOAP, consulte [roteamento Introdução](../../../../docs/framework/wcf/feature-details/routing-introduction.md).</span><span class="sxs-lookup"><span data-stu-id="a11dd-161">For more information about SOAP processing, see [Routing Introduction](../../../../docs/framework/wcf/feature-details/routing-introduction.md).</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="a11dd-162">Tratamento de erros</span><span class="sxs-lookup"><span data-stu-id="a11dd-162">Error Handling</span></span>  
 <span data-ttu-id="a11dd-163">Em um sistema composto de serviços distribuídos que dependem de comunicações de rede, é importante garantir que as comunicações no sistema são resistente a falhas de rede temporárias.</span><span class="sxs-lookup"><span data-stu-id="a11dd-163">In a system composed of distributed services that rely on network communications, it is important to ensure that communications within your system are resistant to transient network failures.</span></span>  <span data-ttu-id="a11dd-164">O serviço de roteamento implementa tratamento de erros que permite que você manipule vários cenários de falha de comunicação que, caso contrário, podem resultar em uma interrupção de serviço.</span><span class="sxs-lookup"><span data-stu-id="a11dd-164">The Routing Service implements error handling that allows you to handle many communication failure scenarios that might otherwise result in a service outage.</span></span>  
  
 <span data-ttu-id="a11dd-165">Se o serviço de roteamento encontrar um <xref:System.ServiceModel.CommunicationException> ao tentar enviar uma mensagem, tratamento de erro ocorrerá.</span><span class="sxs-lookup"><span data-stu-id="a11dd-165">If the Routing Service encounters a <xref:System.ServiceModel.CommunicationException> while attempting to send a message, error handling will take place.</span></span>  <span data-ttu-id="a11dd-166">Essas exceções geralmente indicam que ocorreu um problema ao tentar se comunicar com o ponto de extremidade do cliente definido como um <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException>, ou <xref:System.ServiceModel.CommunicationObjectFaultedException>.</span><span class="sxs-lookup"><span data-stu-id="a11dd-166">These exceptions typically indicate that a problem was encountered while attempting to communicate with the defined client endpoint, such as an <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException>, or <xref:System.ServiceModel.CommunicationObjectFaultedException>.</span></span>  <span data-ttu-id="a11dd-167">O código de tratamento de erros também catch e tentar reenviar quando um **TimeoutException** ocorre, que é outra exceção comum que não é derivada de **CommunicationException**.</span><span class="sxs-lookup"><span data-stu-id="a11dd-167">The error-handling code will also catch and attempt to retry sending when a **TimeoutException** occurs, which is another common exception that is not derived from **CommunicationException**.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a11dd-168">tratamento de erros, consulte [roteamento Introdução](../../../../docs/framework/wcf/feature-details/routing-introduction.md).</span><span class="sxs-lookup"><span data-stu-id="a11dd-168"> error handling, see [Routing Introduction](../../../../docs/framework/wcf/feature-details/routing-introduction.md).</span></span>  
  
## <a name="backup-endpoints"></a><span data-ttu-id="a11dd-169">Pontos de extremidade de backup</span><span class="sxs-lookup"><span data-stu-id="a11dd-169">Backup Endpoints</span></span>  
 <span data-ttu-id="a11dd-170">Além de destino os pontos de extremidade associados a cada definição de filtro na tabela de filtro, você também pode criar uma lista de pontos de extremidade de backup que a mensagem será roteada para em caso de falha de transmissão.</span><span class="sxs-lookup"><span data-stu-id="a11dd-170">In addition to the destination client endpoints associated with each filter definition in the filter table, you can also create a list of backup endpoints that the message will be routed to in the event of a transmission failure.</span></span> <span data-ttu-id="a11dd-171">Se ocorrer um erro e uma lista de backup é definida para a entrada de filtro, o serviço de roteamento tentará enviar a mensagem para o primeiro ponto de extremidade definido na lista.</span><span class="sxs-lookup"><span data-stu-id="a11dd-171">If an error occurs and a backup list is defined for the filter entry, the Routing Service will attempt to send the message to the first endpoint defined in the list.</span></span> <span data-ttu-id="a11dd-172">Se essa falha de tentativa de transmissão, o serviço tente o próximo ponto de extremidade e continuar este processo até que a tentativa de transmissão for bem-sucedido, retornará que um erro de transmissão não relacionado, ou todos os pontos de extremidade na lista de backup tiveram retornado um erro de transmissão.</span><span class="sxs-lookup"><span data-stu-id="a11dd-172">If this transmission attempt fails, the service will try the next endpoint, and continue this process until the transmission attempt succeeds, returns a non-transmission related error, or all endpoints in the backup list have returned a transmission error.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a11dd-173">pontos de extremidade de backup, consulte [roteamento Introdução](../../../../docs/framework/wcf/feature-details/routing-introduction.md) e [filtros de mensagem](../../../../docs/framework/wcf/feature-details/message-filters.md).</span><span class="sxs-lookup"><span data-stu-id="a11dd-173"> backup endpoints, see [Routing Introduction](../../../../docs/framework/wcf/feature-details/routing-introduction.md) and [Message Filters](../../../../docs/framework/wcf/feature-details/message-filters.md).</span></span>  
  
## <a name="streaming"></a><span data-ttu-id="a11dd-174">Streaming</span><span class="sxs-lookup"><span data-stu-id="a11dd-174">Streaming</span></span>  
 <span data-ttu-id="a11dd-175">O serviço de roteamento com êxito pode transmitir mensagens, se você definir a associação para dar suporte a streaming.</span><span class="sxs-lookup"><span data-stu-id="a11dd-175">The routing service can successfully stream messages if you set the binding to support streaming.</span></span>  <span data-ttu-id="a11dd-176">No entanto, há algumas condições sob as quais mensagens talvez precise em buffer:</span><span class="sxs-lookup"><span data-stu-id="a11dd-176">However, there are some conditions under which messages may need to buffered:</span></span>  
  
-   <span data-ttu-id="a11dd-177">Multicast (buffer para criar cópias adicionais)</span><span class="sxs-lookup"><span data-stu-id="a11dd-177">Multicast (buffer to create additional message copies)</span></span>  
  
-   <span data-ttu-id="a11dd-178">Failover (buffer caso que a mensagem precisa ser enviada a um backup)</span><span class="sxs-lookup"><span data-stu-id="a11dd-178">Failover (buffer in case the message needs to be sent to a backup)</span></span>  
  
-   <span data-ttu-id="a11dd-179">System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly for false (buffer para apresentar a MessageFilterTable com MessageBuffer para que os filtros podem inspecionar o corpo)</span><span class="sxs-lookup"><span data-stu-id="a11dd-179">System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly is false (buffer to present the MessageFilterTable with a MessageBuffer so that filters can inspect the body)</span></span>  
  
-   <span data-ttu-id="a11dd-180">Configuração dinâmica</span><span class="sxs-lookup"><span data-stu-id="a11dd-180">Dynamic configuration</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a11dd-181">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a11dd-181">See Also</span></span>  
 [<span data-ttu-id="a11dd-182">Introdução ao roteamento</span><span class="sxs-lookup"><span data-stu-id="a11dd-182">Routing Introduction</span></span>](../../../../docs/framework/wcf/feature-details/routing-introduction.md)  
 [<span data-ttu-id="a11dd-183">Contratos de roteamento</span><span class="sxs-lookup"><span data-stu-id="a11dd-183">Routing Contracts</span></span>](../../../../docs/framework/wcf/feature-details/routing-contracts.md)  
 [<span data-ttu-id="a11dd-184">Filtros de mensagem</span><span class="sxs-lookup"><span data-stu-id="a11dd-184">Message Filters</span></span>](../../../../docs/framework/wcf/feature-details/message-filters.md)