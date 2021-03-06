---
title: Método ICorDebugController::Continue
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 529a65285203ac831e1bcab9dc1bea69ac28a282
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412559"
---
# <a name="icordebugcontrollercontinue-method"></a>Método ICorDebugController::Continue
Retoma a execução de threads gerenciados após uma chamada para [método Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `fIsOutOfBand`  
 [in] Definido como `true` se continuar a partir de um evento fora de banda; caso contrário, defina como `false`.  
  
## <a name="remarks"></a>Comentários  
 `Continue` continua o processo após uma chamada para o `ICorDebugController::Stop` método.  
  
 Ao fazer a depuração de modo misto, não chame `Continue` em Win32 do thread eventos, a menos que você está continuando a partir de um evento fora de banda.  
  
 Um *em banda evento* é um evento gerenciado ou um evento normal de não gerenciado durante o qual o depurador oferece suporte à interação com o estado do processo gerenciado. Nesse caso, o depurador recebe o [Icordebugunmanagedcallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) retorno de chamada com seu `fOutOfBand` parâmetro definido como `false`.  
  
 Um *eventos fora de banda* é um evento não gerenciado durante o qual a interação com o estado do processo gerenciado é impossível enquanto o processo foi interrompido devido ao evento. Nesse caso, o depurador recebe o `ICorDebugUnmanagedCallback::DebugEvent` retorno de chamada com seu `fOutOfBand` parâmetro definido como `true`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 
