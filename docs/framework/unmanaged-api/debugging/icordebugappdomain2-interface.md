---
title: Interface1 ICorDebugAppDomain2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain2
helpviewer_keywords: ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ebd1e504cbf2f74ad82e7fea6b6c3f355a1bda34
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain2-interface1"></a><span data-ttu-id="2b62f-102">Interface1 ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="2b62f-102">ICorDebugAppDomain2 Interface1</span></span>
<span data-ttu-id="2b62f-103">Fornece métodos para trabalhar com matrizes, ponteiros, ponteiros de função e tipos de referência.</span><span class="sxs-lookup"><span data-stu-id="2b62f-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="2b62f-104">Essa interface é uma extensão da interface ICorDebugAppDomain.</span><span class="sxs-lookup"><span data-stu-id="2b62f-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2b62f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2b62f-105">Methods</span></span>  
  
|<span data-ttu-id="2b62f-106">Método</span><span class="sxs-lookup"><span data-stu-id="2b62f-106">Method</span></span>|<span data-ttu-id="2b62f-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="2b62f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2b62f-108">Método GetArrayOrPointerType</span><span class="sxs-lookup"><span data-stu-id="2b62f-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="2b62f-109">Obtém uma matriz do tipo especificado, ou um ponteiro ou referência ao tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="2b62f-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="2b62f-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="2b62f-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="2b62f-111">Obtém um ponteiro para uma função que tem uma assinatura fornecida.</span><span class="sxs-lookup"><span data-stu-id="2b62f-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b62f-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="2b62f-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b62f-113">Esta interface não dá suporte a que está sendo chamado remotamente, entre computadores ou entre processos.</span><span class="sxs-lookup"><span data-stu-id="2b62f-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b62f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b62f-114">Requirements</span></span>  
 <span data-ttu-id="2b62f-115">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b62f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b62f-116">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b62f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b62f-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b62f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b62f-118">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b62f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b62f-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2b62f-119">See Also</span></span>  
 [<span data-ttu-id="2b62f-120">Interfaces de depuração</span><span class="sxs-lookup"><span data-stu-id="2b62f-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)