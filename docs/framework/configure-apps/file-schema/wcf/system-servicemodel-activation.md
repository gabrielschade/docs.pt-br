---
title: '&lt;system.serviceModel.activation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0cae85f-56cb-4030-8807-6f96edff8d2d
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 18376f3553bc0a39b82cb0f223081c09a674e062
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="ltsystemservicemodelactivationgt"></a><span data-ttu-id="e1f11-102">&lt;system.serviceModel.activation&gt;</span><span class="sxs-lookup"><span data-stu-id="e1f11-102">&lt;system.serviceModel.activation&gt;</span></span>
<span data-ttu-id="e1f11-103">Esta seção de configuração representa as definições de configuração para a ferramenta SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="e1f11-103">This configuration section represents the configuration settings for the SMSvcHost.exe tool.</span></span> <span data-ttu-id="e1f11-104">Os elementos de configuração podem ser configurados no arquivo de SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="e1f11-104">The configuration elements can be configured in the SMSvcHost.exe.config file.</span></span> <span data-ttu-id="e1f11-105">Especificamente, ele inclui todas as configurações de máquina que devem ser configuradas.</span><span class="sxs-lookup"><span data-stu-id="e1f11-105">Specifically, it includes all machine-wide settings that must be configured.</span></span>  
  
## <a name="sample-configuration-file"></a><span data-ttu-id="e1f11-106">Arquivo de configuração de exemplo</span><span class="sxs-lookup"><span data-stu-id="e1f11-106">Sample Configuration File</span></span>  
 <span data-ttu-id="e1f11-107">Este é um arquivo de configuração de exemplo (SMSvcHost.exe), que é usado pelo processo de ouvinte SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="e1f11-107">The following is a sample configuration file (SMSvcHost.exe.config), which is used by the listener process SMSvcHost.exe.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false" />  
   </runtime>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="10"  
          maxPendingAccepts="2"  
          maxPendingConnections="100"  
          receiveTimeout="00:00:10"  
          teredoEnabled="false">  
          <allowAccounts>  
             <!-- LocalSystem account -->  
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->  
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Network Service account -->  
            <add securityIdentifier="S-1-5-20"/>   
             <!-- Administrators account -->  
            <add securityIdentifier="S-1-5-32-544" />   
             <!-- IIS_IUSRS account (Vista only) -->  
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
       <net.pipe maxConnectionsPendingDispatch="100"  
          maxPendingAccepts="2"  
          receiveTimeout="00:00:10">  
          <allowAccounts>  
             <!-- LocalSystem account -->  
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->  
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Network Service account -->  
            <add securityIdentifier="S-1-5-20"/>   
             <!-- Administrators account -->  
            <add securityIdentifier="S-1-5-32-544" />   
             <!-- IIS_IUSRS account (Vista only) -->  
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.pipe>  
       <diagnostics performanceCountersEnabled="true" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1f11-108">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e1f11-108">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration>