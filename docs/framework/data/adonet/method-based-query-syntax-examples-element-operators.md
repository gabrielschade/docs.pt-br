---
title: 'Exemplos de sintaxe da consulta com base em método: Operadores de elemento (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eedf2fbd-f407-4f62-bb1a-c00eb001b1dd
ms.openlocfilehash: 8c01709f062048db34680ef8ba987f6e08bf15f2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764145"
---
# <a name="method-based-query-syntax-examples-element-operators-linq-to-dataset"></a>Exemplos de sintaxe da consulta com base em método: Operadores de elemento (LINQ to DataSet)
Os exemplos neste tópico demonstram como usar os métodos de <xref:System.Linq.Enumerable.First%2A> e de <xref:System.Linq.Enumerable.ElementAt%2A> para obter os elementos de <xref:System.Data.DataRow> de <xref:System.Data.DataSet> usando a sintaxe da expressão de consulta.  
  
 O `FillDataSet` método usado nesses exemplos é especificado em [carregar dados em um conjunto de dados](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 Os exemplos neste tópico usam as tabelas Contact, Address, Product, SalesOrderHeader e SalesOrderDetail no banco de dados de exemplo AdventureWorks.  
  
 Os exemplos neste tópico usam o seguinte `using` / `Imports` instruções:  
  
[!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]   
[!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]     

 Para obter mais informações, consulte [como: criar um LINQ to DataSet de projeto no Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## <a name="elementat"></a>ElementAt  
  
### <a name="example"></a>Exemplo  
 Este exemplo usa o método de <xref:System.Linq.Enumerable.ElementAt%2A> para recuperar o quinto endereço onde o == “M4B 1V7” de `PostalCode` .  
  
[!code-csharp[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#elementat)]   
[!code-vb[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#elementat)]     
  
## <a name="first"></a>Primeiro  
  
### <a name="example"></a>Exemplo  
 Este exemplo usa o método de <xref:System.Linq.Enumerable.First%2A> para retornar o primeiro contato cujo nome é “Brooke”.  
  
[!code-csharp[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#firstsimple)]   
[!code-vb[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#firstsimple)] 
  
## <a name="see-also"></a>Consulte também  
 [Carregar dados para um conjunto de dados](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [Exemplos de LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [Visão Geral de Operadores de Consulta Padrão](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
