---
title: 'Como: Representa colunas como permitir valores nulos'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: efa6f9d453940151dfe01d27827760521359ab67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="9489e-102">Como: Representa colunas como permitir valores nulos</span><span class="sxs-lookup"><span data-stu-id="9489e-102">How to: Represent Columns as Allowing Null Values</span></span>
<span data-ttu-id="9489e-103">Use o [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> propriedade o <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para especificar que a coluna de banco de dados associado pode conter valores nulos.</span><span class="sxs-lookup"><span data-stu-id="9489e-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="9489e-104">Para exemplos de código, consulte <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="9489e-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="9489e-105">Para designar uma coluna como permitir valores nulos</span><span class="sxs-lookup"><span data-stu-id="9489e-105">To designate a column as allowing null values</span></span>  
  
1.  <span data-ttu-id="9489e-106">Adicione a propriedade de <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> ao atributo de <xref:System.Data.Linq.Mapping.ColumnAttribute> .</span><span class="sxs-lookup"><span data-stu-id="9489e-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="9489e-107">Definir o valor da propriedade de <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> a `true`.</span><span class="sxs-lookup"><span data-stu-id="9489e-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9489e-108">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9489e-108">See Also</span></span>  
 [<span data-ttu-id="9489e-109">O LINQ no modelo de objeto do SQL</span><span class="sxs-lookup"><span data-stu-id="9489e-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="9489e-110">Como: Personalizar Classes de entidade usando o Editor de código</span><span class="sxs-lookup"><span data-stu-id="9489e-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)