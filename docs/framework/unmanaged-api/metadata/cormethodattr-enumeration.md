---
title: "Enumeração CorMethodAttr"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorMethodAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorMethodAttr
helpviewer_keywords: CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 91afbc9894826b1f44d84f23b550a81d610e3de9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="cormethodattr-enumeration"></a><span data-ttu-id="34e84-102">Enumeração CorMethodAttr</span><span class="sxs-lookup"><span data-stu-id="34e84-102">CorMethodAttr Enumeration</span></span>
<span data-ttu-id="34e84-103">Contém valores que descrevem os recursos de um método.</span><span class="sxs-lookup"><span data-stu-id="34e84-103">Contains values that describe the features of a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34e84-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="34e84-104">Syntax</span></span>  
  
```  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="34e84-105">Membros</span><span class="sxs-lookup"><span data-stu-id="34e84-105">Members</span></span>  
  
|<span data-ttu-id="34e84-106">Membro</span><span class="sxs-lookup"><span data-stu-id="34e84-106">Member</span></span>|<span data-ttu-id="34e84-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="34e84-107">Description</span></span>|  
|------------|-----------------|  
|`mdMemberAccessMask`|<span data-ttu-id="34e84-108">Especifica o acesso de membro.</span><span class="sxs-lookup"><span data-stu-id="34e84-108">Specifies member access.</span></span>|  
|`mdPrivateScope`|<span data-ttu-id="34e84-109">Especifica que o membro não pode ser referenciado.</span><span class="sxs-lookup"><span data-stu-id="34e84-109">Specifies that the member cannot be referenced.</span></span>|  
|`mdPrivate`|<span data-ttu-id="34e84-110">Especifica que o membro é acessível somente pelo tipo de pai.</span><span class="sxs-lookup"><span data-stu-id="34e84-110">Specifies that the member is accessible only by the parent type.</span></span>|  
|`mdFamANDAssem`|<span data-ttu-id="34e84-111">Especifica que o membro é acessível por subtipos somente neste assembly.</span><span class="sxs-lookup"><span data-stu-id="34e84-111">Specifies that the member is accessible by subtypes only in this assembly.</span></span>|  
|`mdAssem`|<span data-ttu-id="34e84-112">Especifica que o membro é acessível por qualquer pessoa no assembly.</span><span class="sxs-lookup"><span data-stu-id="34e84-112">Specifies that the member is accessibly by anyone in the assembly.</span></span>|  
|`mdFamily`|<span data-ttu-id="34e84-113">Especifica que o membro é acessível somente por tipo e subtipos.</span><span class="sxs-lookup"><span data-stu-id="34e84-113">Specifies that the member is accessible only by type and subtypes.</span></span>|  
|`mdFamORAssem`|<span data-ttu-id="34e84-114">Especifica que o membro é acessível por classes derivadas e por outros tipos em seu assembly.</span><span class="sxs-lookup"><span data-stu-id="34e84-114">Specifies that the member is accessible by derived classes and by other types in its assembly.</span></span>|  
|`mdPublic`|<span data-ttu-id="34e84-115">Especifica que o membro é acessado por todos os tipos com acesso ao escopo.</span><span class="sxs-lookup"><span data-stu-id="34e84-115">Specifies that the member is accessible by all types with access to the scope.</span></span>|  
|`mdStatic`|<span data-ttu-id="34e84-116">Especifica que o membro é definido como parte do tipo em vez de um membro de uma instância.</span><span class="sxs-lookup"><span data-stu-id="34e84-116">Specifies that the member is defined as part of the type rather than as a member of an instance.</span></span>|  
|`mdFinal`|<span data-ttu-id="34e84-117">Especifica que o método não pode ser substituído.</span><span class="sxs-lookup"><span data-stu-id="34e84-117">Specifies that the method cannot be overridden.</span></span>|  
|`mdVirtual`|<span data-ttu-id="34e84-118">Especifica que o método pode ser substituído.</span><span class="sxs-lookup"><span data-stu-id="34e84-118">Specifies that the method can be overridden.</span></span>|  
|`mdHideBySig`|<span data-ttu-id="34e84-119">Especifica que o método oculta por nome e assinatura, em vez de apenas por nome.</span><span class="sxs-lookup"><span data-stu-id="34e84-119">Specifies that the method hides by name and signature, rather than just by name.</span></span>|  
|`mdVtableLayoutMask`|<span data-ttu-id="34e84-120">Especifica o layout da tabela virtual.</span><span class="sxs-lookup"><span data-stu-id="34e84-120">Specifies virtual table layout.</span></span>|  
|`mdReuseSlot`|<span data-ttu-id="34e84-121">Especifica que o slot usado para este método na tabela virtual seja reutilizado.</span><span class="sxs-lookup"><span data-stu-id="34e84-121">Specifies that the slot used for this method in the virtual table be reused.</span></span> <span data-ttu-id="34e84-122">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="34e84-122">This is the default.</span></span>|  
|`mdNewSlot`|<span data-ttu-id="34e84-123">Especifica que o método sempre obtém um novo slot na tabela virtual.</span><span class="sxs-lookup"><span data-stu-id="34e84-123">Specifies that the method always gets a new slot in the virtual table.</span></span>|  
|`mdCheckAccessOnOverride`|<span data-ttu-id="34e84-124">Especifica que o método pode ser substituído pelos mesmos tipos aos quais ela é visível.</span><span class="sxs-lookup"><span data-stu-id="34e84-124">Specifies that the method can be overridden by the same types to which it is visible.</span></span>|  
|`mdAbstract`|<span data-ttu-id="34e84-125">Especifica que o método não está implementado.</span><span class="sxs-lookup"><span data-stu-id="34e84-125">Specifies that the method is not implemented.</span></span>|  
|`mdSpecialName`|<span data-ttu-id="34e84-126">Especifica que o método é especial, e que descreve seu nome como.</span><span class="sxs-lookup"><span data-stu-id="34e84-126">Specifies that the method is special, and that its name describes how.</span></span>|  
|`mdPinvokeImpl`|<span data-ttu-id="34e84-127">Especifica que a implementação do método é encaminhada usando PInvoke.</span><span class="sxs-lookup"><span data-stu-id="34e84-127">Specifies that the method implementation is forwarded using PInvoke.</span></span>|  
|`mdUnmanagedExport`|<span data-ttu-id="34e84-128">Especifica que o método é um método gerenciado exportado para o código não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="34e84-128">Specifies that the method is a managed method exported to unmanaged code.</span></span>|  
|`mdReservedMask`|<span data-ttu-id="34e84-129">Reservado para uso interno pelo common language runtime.</span><span class="sxs-lookup"><span data-stu-id="34e84-129">Reserved for internal use by the common language runtime.</span></span>|  
|`mdRTSpecialName`|<span data-ttu-id="34e84-130">Especifica que o common language runtime deve verificar a codificação do nome do método.</span><span class="sxs-lookup"><span data-stu-id="34e84-130">Specifies that the common language runtime should check the encoding of the method name.</span></span>|  
|`mdHasSecurity`|<span data-ttu-id="34e84-131">Especifica que o método tem segurança associada a ele.</span><span class="sxs-lookup"><span data-stu-id="34e84-131">Specifies that the method has security associated with it.</span></span>|  
|`mdRequireSecObject`|<span data-ttu-id="34e84-132">Especifica que o método chama outro método que contém o código de segurança.</span><span class="sxs-lookup"><span data-stu-id="34e84-132">Specifies that the method calls another method containing security code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="34e84-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34e84-133">Requirements</span></span>  
 <span data-ttu-id="34e84-134">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34e84-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34e84-135">**Cabeçalho:** Corhdr</span><span class="sxs-lookup"><span data-stu-id="34e84-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="34e84-136">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34e84-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34e84-137">Consulte também</span><span class="sxs-lookup"><span data-stu-id="34e84-137">See Also</span></span>  
 [<span data-ttu-id="34e84-138">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="34e84-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)