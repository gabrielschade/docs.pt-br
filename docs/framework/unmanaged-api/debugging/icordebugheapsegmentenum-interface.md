---
title: Interface ICorDebugHeapSegmentEnum
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cac4ddc33bcaf07d615fd186a63d96b1f4f6464c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417726"
---
# <a name="icordebugheapsegmentenum-interface"></a>Interface ICorDebugHeapSegmentEnum
Fornece um enumerador para regiões de memória do heap gerenciado. Esta interface é uma subclasse da interface ICorDebugEnum.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descrição|  
|------------|-----------------|  
|[Método Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|Obtém o número especificado de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instâncias que contêm informações sobre as regiões do heap gerenciado.|  
  
## <a name="remarks"></a>Comentários  
 O `ICorDebugHeapSegmentEnum` interface implementa a interface ICorDebugEnum.  
  
 Um `ICorDebugHeapSegmentEnum` instância é populada com [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instâncias chamando o [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) método. O [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objetos na coleção podem ser enumerados chamando o [Icordebugheapsegmentenum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) método.  
  
 Um `ICorDebugHeapSegmentEnum` objeto da coleção enumera todas as regiões de memória que podem conter objetos gerenciados, mas não garante que os objetos gerenciados, na verdade, residam nessas regiões. Ele pode incluir informações sobre regiões de memória reservada ou vazio.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 [Depurando interfaces](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
