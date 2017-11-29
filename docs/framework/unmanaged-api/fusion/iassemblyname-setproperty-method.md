---
title: "Método IAssemblyName::SetProperty"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.SetProperty
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2b99b9c01d014f7b6c02eedde157fa6fdd4e142a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="8e46a-102">Método IAssemblyName::SetProperty</span><span class="sxs-lookup"><span data-stu-id="8e46a-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="8e46a-103">Define o valor da propriedade referenciada pelo identificador de propriedade especificado.</span><span class="sxs-lookup"><span data-stu-id="8e46a-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e46a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8e46a-104">Syntax</span></span>  
  
```  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e46a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8e46a-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="8e46a-106">[in] O identificador exclusivo da propriedade cujo valor será definido.</span><span class="sxs-lookup"><span data-stu-id="8e46a-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="8e46a-107">[in] O valor para o qual definir a propriedade referenciada por `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="8e46a-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="8e46a-108">[in] O tamanho, em bytes, de `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="8e46a-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e46a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e46a-109">Requirements</span></span>  
 <span data-ttu-id="8e46a-110">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e46a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e46a-111">**Cabeçalho:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="8e46a-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8e46a-112">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e46a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e46a-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8e46a-113">See Also</span></span>  
 [<span data-ttu-id="8e46a-114">Interface IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="8e46a-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)