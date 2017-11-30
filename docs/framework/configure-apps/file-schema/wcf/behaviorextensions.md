---
title: '&lt;behaviorExtensions&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59f2791a-c78f-40d7-aa80-0d9cd10135d9
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ed7c75fb7070b43b850a8f5b812abf0a52c3c16f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltbehaviorextensionsgt"></a><span data-ttu-id="cbe54-102">&lt;behaviorExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="cbe54-102">&lt;behaviorExtensions&gt;</span></span>
<span data-ttu-id="cbe54-103">Extensões de comportamento permitem ao usuário criar elementos de comportamento definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="cbe54-103">Behavior extensions enable the user to create user-defined behavior elements.</span></span> <span data-ttu-id="cbe54-104">Esses elementos podem ser usados junto com os elementos de comportamento padrão do Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="cbe54-104">These elements can be used alongside the standard Windows Communication Foundation (WCF) behavior elements.</span></span> <span data-ttu-id="cbe54-105">O `behaviorExtensions` seção define o elemento de modo que ele pode ser usado na configuração.</span><span class="sxs-lookup"><span data-stu-id="cbe54-105">The `behaviorExtensions` section defines the element such that it can be used in configuration.</span></span> <span data-ttu-id="cbe54-106">Aqui está um exemplo de uma extensão de comportamento típico.</span><span class="sxs-lookup"><span data-stu-id="cbe54-106">Here is an example of a typical behavior extension.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="myBehavior" type="Microsoft.ServiceModel.Samples.MyBehaviorSection, MyBehavior,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
       </behaviorExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="cbe54-107">Para adicionar recursos de configuração para o elemento, você precisa escrever e registrar um elemento de configuração.</span><span class="sxs-lookup"><span data-stu-id="cbe54-107">To add configuration abilities to the element, you need to write and register a configuration element.</span></span> <span data-ttu-id="cbe54-108">Para obter mais informações sobre isso, consulte o <xref:System.Configuration> documentação.</span><span class="sxs-lookup"><span data-stu-id="cbe54-108">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="cbe54-109">Depois que o elemento e seu tipo de configuração são definidos, a extensão pode ser usada, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="cbe54-109">After the element and its configuration type are defined, the extension can be used, as shown in the following example.</span></span>  
  
```xml  
<behaviors>  
    <behavior configurationName="testChannelBehavior">  
        <myBehavior />  
        <channelSecurity cacheCookies="false" detectReplays="false" maxCachedNonces="9"  
            maxClockSkew="00:00:03" maxCookieCachingTime="00:07:24" replayWindow="00:07:22.2190000" />  
    </behavior>  
</behaviors>  
```  
  
## <a name="security"></a><span data-ttu-id="cbe54-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="cbe54-110">Security</span></span>  
 <span data-ttu-id="cbe54-111">É altamente recomendável que você use nomes de assembly totalmente qualificado ao registrar tipos no `machine.config` e `app.config` arquivos.</span><span class="sxs-lookup"><span data-stu-id="cbe54-111">It is strongly recommended that you use fully qualified assembly names when registering types in the `machine.config` and `app.config` files.</span></span> <span data-ttu-id="cbe54-112">Se o tipo não é exclusivamente definido, o carregador de tipo CLR pesquisa nos seguintes locais na ordem especificada:</span><span class="sxs-lookup"><span data-stu-id="cbe54-112">If the type is not uniquely defined, the CLR type loader searches for it in the following locations in the specified order:</span></span>  
  
 <span data-ttu-id="cbe54-113">Se o assembly do tipo for conhecido, o carregador de pesquisa locais de redirecionamento do arquivo de configuração, GAC, o assembly atual usando as informações de configuração e o diretório base do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cbe54-113">If the assembly of the type is known, the loader searches the configuration file's redirect locations, GAC, the current assembly using configuration information, and the application base directory.</span></span> <span data-ttu-id="cbe54-114">Se o assembly for desconhecido, o carregador de pesquisa do assembly atual, mscorlib e o local retornado pelo `TypeResolve` manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="cbe54-114">If the assembly is unknown, the loader searches the current assembly, mscorlib, and the location returned by the `TypeResolve` event handler.</span></span> <span data-ttu-id="cbe54-115">Essa ordem de pesquisa do CLR pode ser modificada com ganchos de como o mecanismo de encaminhamento de tipo e o evento AppDomain.TypeResolve.</span><span class="sxs-lookup"><span data-stu-id="cbe54-115">This CLR search order can be modified with hooks such as the Type Forwarding mechanism and the AppDomain.TypeResolve event.</span></span>  
  
 <span data-ttu-id="cbe54-116">Um invasor pode explorar a ordem de pesquisa CLR e executar código não autorizado.</span><span class="sxs-lookup"><span data-stu-id="cbe54-116">An attacker can exploit the CLR search order and execute unauthorized code.</span></span> <span data-ttu-id="cbe54-117">Usando os nomes totalmente qualificados (fortes) exclusivamente identifica um tipo e aumenta ainda mais a segurança do sistema.</span><span class="sxs-lookup"><span data-stu-id="cbe54-117">Using fully qualified (strong) names uniquely identifies a type and further increases security of your system.</span></span>  
  
 <span data-ttu-id="cbe54-118">Para obter mais informações, consulte [como o tempo de execução Localiza Assemblies](http://go.microsoft.com/fwlink/?LinkId=95336) e <xref:System.AppDomain.TypeResolve>.</span><span class="sxs-lookup"><span data-stu-id="cbe54-118">For more information, see [How the Runtime Locates Assemblies](http://go.microsoft.com/fwlink/?LinkId=95336) and <xref:System.AppDomain.TypeResolve>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe54-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cbe54-119">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>  
 [<span data-ttu-id="cbe54-120">Configurando e estendendo o tempo de execução com comportamentos</span><span class="sxs-lookup"><span data-stu-id="cbe54-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)