---
title: 209 - MessageInspectorBeforeSendInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8de4338fd9d1d18ab1f689df39b2247a29d2dcf5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="3e292-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="3e292-102">209 - MessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="3e292-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="3e292-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3e292-104">ID</span><span class="sxs-lookup"><span data-stu-id="3e292-104">ID</span></span>|<span data-ttu-id="3e292-105">209</span><span class="sxs-lookup"><span data-stu-id="3e292-105">209</span></span>|  
|<span data-ttu-id="3e292-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3e292-106">Keywords</span></span>|<span data-ttu-id="3e292-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3e292-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="3e292-108">Nível</span><span class="sxs-lookup"><span data-stu-id="3e292-108">Level</span></span>|<span data-ttu-id="3e292-109">Informações</span><span class="sxs-lookup"><span data-stu-id="3e292-109">Information</span></span>|  
|<span data-ttu-id="3e292-110">Canal</span><span class="sxs-lookup"><span data-stu-id="3e292-110">Channel</span></span>|<span data-ttu-id="3e292-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="3e292-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3e292-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="3e292-112">Description</span></span>  
 <span data-ttu-id="3e292-113">Esse evento é emitido após o modelo de serviço foi invocado o `BeforeSend` método em um Inspetor de mensagem.</span><span class="sxs-lookup"><span data-stu-id="3e292-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3e292-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="3e292-114">Message</span></span>  
 <span data-ttu-id="3e292-115">O Dispatcher invocou 'BeforeSendRequest' em um MessageInspector do tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="3e292-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3e292-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="3e292-116">Details</span></span>  
  
|<span data-ttu-id="3e292-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="3e292-117">Data Item Name</span></span>|<span data-ttu-id="3e292-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="3e292-118">Data Item Type</span></span>|<span data-ttu-id="3e292-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="3e292-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3e292-120">NomeDoTipo</span><span class="sxs-lookup"><span data-stu-id="3e292-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="3e292-121">O FullName do CLR do tipo de chamada `MessageInspector`.</span><span class="sxs-lookup"><span data-stu-id="3e292-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="3e292-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="3e292-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="3e292-123">Para serviços hospedados na Web, este campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="3e292-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="3e292-124">O formato é definido como ' caminho Virtual do aplicativo de nome de Site da Web &#124; Caminho Virtual do serviço &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="3e292-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="3e292-125">Exemplo: ' Default Web Site/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="3e292-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="3e292-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3e292-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="3e292-127">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3e292-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|