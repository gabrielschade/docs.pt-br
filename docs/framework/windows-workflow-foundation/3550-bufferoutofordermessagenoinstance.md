---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ce8b2cd52523d8a2efc94214479ca3c41d2dec4b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="4fb47-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="4fb47-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="4fb47-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="4fb47-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4fb47-104">ID</span><span class="sxs-lookup"><span data-stu-id="4fb47-104">ID</span></span>|<span data-ttu-id="4fb47-105">3550</span><span class="sxs-lookup"><span data-stu-id="4fb47-105">3550</span></span>|  
|<span data-ttu-id="4fb47-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4fb47-106">Keywords</span></span>|<span data-ttu-id="4fb47-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="4fb47-107">WFServices</span></span>|  
|<span data-ttu-id="4fb47-108">Nível</span><span class="sxs-lookup"><span data-stu-id="4fb47-108">Level</span></span>|<span data-ttu-id="4fb47-109">Informações</span><span class="sxs-lookup"><span data-stu-id="4fb47-109">Information</span></span>|  
|<span data-ttu-id="4fb47-110">Canal</span><span class="sxs-lookup"><span data-stu-id="4fb47-110">Channel</span></span>|<span data-ttu-id="4fb47-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="4fb47-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4fb47-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="4fb47-112">Description</span></span>  
 <span data-ttu-id="4fb47-113">Indica que um armazenados em buffer recebe falhou.</span><span class="sxs-lookup"><span data-stu-id="4fb47-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="4fb47-114">A operação será tentada novamente quando a instância do serviço está pronta para processar esta operação específico.</span><span class="sxs-lookup"><span data-stu-id="4fb47-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4fb47-115">Mensagem</span><span class="sxs-lookup"><span data-stu-id="4fb47-115">Message</span></span>  
 <span data-ttu-id="4fb47-116">A operação “%1 " não pode ser executada no momento.</span><span class="sxs-lookup"><span data-stu-id="4fb47-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="4fb47-117">Outra tentativa será feita quando a instância de serviço estiver pronta para processar esse operação específica.</span><span class="sxs-lookup"><span data-stu-id="4fb47-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4fb47-118">Detalhes</span><span class="sxs-lookup"><span data-stu-id="4fb47-118">Details</span></span>  
  
|<span data-ttu-id="4fb47-119">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="4fb47-119">Data Item Name</span></span>|<span data-ttu-id="4fb47-120">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="4fb47-120">Data Item Type</span></span>|<span data-ttu-id="4fb47-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="4fb47-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4fb47-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="4fb47-122">OperationName</span></span>|<span data-ttu-id="4fb47-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="4fb47-123">xs:string</span></span>|<span data-ttu-id="4fb47-124">O nome da operação.</span><span class="sxs-lookup"><span data-stu-id="4fb47-124">The name of the operation.</span></span>|  
|<span data-ttu-id="4fb47-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4fb47-125">AppDomain</span></span>|<span data-ttu-id="4fb47-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="4fb47-126">xs:string</span></span>|<span data-ttu-id="4fb47-127">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4fb47-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|