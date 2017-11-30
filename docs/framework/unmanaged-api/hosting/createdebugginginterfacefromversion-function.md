---
title: "Função CreateDebuggingInterfaceFromVersion"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CreateDebuggingInterfaceFromVersion
helpviewer_keywords: CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cc352603ef1c3610edf99f7bdd877c6bb0e5d9fb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="d165b-102">Função CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="d165b-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="d165b-103">Cria um [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) objeto com base nas informações de versão especificada.</span><span class="sxs-lookup"><span data-stu-id="d165b-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="d165b-104">Essa função é obsoleta no [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d165b-104">This function is obsolete in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="d165b-105">Em vez disso, para obter uma interface para o common language runtime (CLR) 2.0, use o [Iclrruntimeinfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) método e especifique o identificador de classe CLSID_CLRDebuggingLegacy e o identificador de interface IID_ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="d165b-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="d165b-106">Para obter uma interface CLR 4 ou posterior, chame o [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) de função e especifique o identificador de classe CLSID_CLRDebugging e o identificador de interface IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="d165b-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d165b-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d165b-107">Syntax</span></span>  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d165b-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d165b-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="d165b-109">[in] A versão do `ICorDebug` que é esperado pelo depurador.</span><span class="sxs-lookup"><span data-stu-id="d165b-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="d165b-110">Consulte o [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeração para os valores válidos.</span><span class="sxs-lookup"><span data-stu-id="d165b-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="d165b-111">[in] A versão de tempo de execução language comuns associada ao aplicativo ou processo a ser depurado.</span><span class="sxs-lookup"><span data-stu-id="d165b-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="d165b-112">Consulte o [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) ou [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) método para obter informações sobre como recuperar esse valor.</span><span class="sxs-lookup"><span data-stu-id="d165b-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="d165b-113">[out] O local que recebe um ponteiro para o `ICorDebug` objeto.</span><span class="sxs-lookup"><span data-stu-id="d165b-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d165b-114">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="d165b-114">Return Value</span></span>  
 <span data-ttu-id="d165b-115">Esse método retorna códigos de erro padrão COM conforme definido no arquivo de Winerror. H, além dos valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="d165b-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="d165b-116">Código de retorno</span><span class="sxs-lookup"><span data-stu-id="d165b-116">Return code</span></span>|<span data-ttu-id="d165b-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="d165b-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d165b-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="d165b-118">S_OK</span></span>|<span data-ttu-id="d165b-119">O método foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="d165b-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="d165b-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d165b-120">E_INVALIDARG</span></span>|<span data-ttu-id="d165b-121">`szDebuggeeVersion`ou `ppCordb` é nulo ou a versão de cadeia de caracteres está incorreta.</span><span class="sxs-lookup"><span data-stu-id="d165b-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d165b-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="d165b-122">Remarks</span></span>  
 <span data-ttu-id="d165b-123">O `szDebuggeeVersion` parâmetro mapeado para a versão correspondente do MSCorDbi.dll.</span><span class="sxs-lookup"><span data-stu-id="d165b-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d165b-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d165b-124">Requirements</span></span>  
 <span data-ttu-id="d165b-125">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d165b-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d165b-126">**Cabeçalho:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d165b-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d165b-127">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d165b-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d165b-128">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d165b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d165b-129">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d165b-129">See Also</span></span>  
 [<span data-ttu-id="d165b-130">Funções de hospedagem CLR reprovadas</span><span class="sxs-lookup"><span data-stu-id="d165b-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)