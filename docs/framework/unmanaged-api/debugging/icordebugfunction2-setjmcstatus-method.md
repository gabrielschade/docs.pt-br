---
title: Método ICorDebugFunction2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15b102be5a792f982edeb320199576bdddbd859a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412354"
---
# <a name="icordebugfunction2setjmcstatus-method"></a>Método ICorDebugFunction2::SetJMCStatus
Marca a função representada por esse ICorDebugFunction2 para apenas meu código passo a passo.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `bIsJustMyCode`  
 [in] Definido como `true` para marcar a função como código de usuário; caso contrário, é definido como `false`.  
  
## <a name="return-values"></a>Valores de Retorno  
  
|HRESULT|Descrição|  
|-------------|-----------------|  
|`S_OK`|A função foi marcada com êxito.|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|A função não pode ser marcada como código de usuário porque ele não pode ser depurado.|  
  
## <a name="remarks"></a>Comentários  
 Um seletor de apenas meu código vai ignorar o código de não usuário. Código do usuário deve ser um subconjunto de código depurável.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
