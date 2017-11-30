---
title: "Informações de erro de linha"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8b1f9070-d032-48c7-b030-bd8fbb2ca59a
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 95cbac7f5bf2c28a3db206faca443edacc5b7be1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="row-error-information"></a><span data-ttu-id="24f8a-102">Informações de erro de linha</span><span class="sxs-lookup"><span data-stu-id="24f8a-102">Row Error Information</span></span>
<span data-ttu-id="24f8a-103">Para evitar a responder a erros de linha durante a edição de valores em um <xref:System.Data.DataTable>, você pode adicionar as informações de erro para a linha para uso posterior.</span><span class="sxs-lookup"><span data-stu-id="24f8a-103">To avoid having to respond to row errors while editing values in a <xref:System.Data.DataTable>, you can add the error information to the row for later use.</span></span> <span data-ttu-id="24f8a-104">O <xref:System.Data.DataRow> objeto fornece um <xref:System.Data.DataRow.RowError%2A> propriedade em cada linha para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="24f8a-104">The <xref:System.Data.DataRow> object provides a <xref:System.Data.DataRow.RowError%2A> property on each row for this purpose.</span></span> <span data-ttu-id="24f8a-105">Adicionando dados a **RowError** propriedade de um **DataRow** define o <xref:System.Data.DataRow.HasErrors%2A> propriedade do **DataRow** para **true**.</span><span class="sxs-lookup"><span data-stu-id="24f8a-105">Adding data to the **RowError** property of a **DataRow** sets the <xref:System.Data.DataRow.HasErrors%2A> property of the **DataRow** to **true**.</span></span> <span data-ttu-id="24f8a-106">Se o **DataRow** faz parte de um **DataTable**, e **DataRow.HasErrors** é **true**, o **DataTable.HasErrors** propriedade também é **true**.</span><span class="sxs-lookup"><span data-stu-id="24f8a-106">If the **DataRow** is part of a **DataTable**, and **DataRow.HasErrors** is **true**, the **DataTable.HasErrors** property is also **true**.</span></span> <span data-ttu-id="24f8a-107">Isso se aplica, bem como o **DataSet** ao qual o **DataTable** pertence.</span><span class="sxs-lookup"><span data-stu-id="24f8a-107">This applies as well to the **DataSet** to which the **DataTable** belongs.</span></span> <span data-ttu-id="24f8a-108">Quando os testes de erros, você pode verificar o **HasErrors** propriedade para determinar se as informações de erro foi adicionadas para todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="24f8a-108">When testing for errors, you can check the **HasErrors** property to determine if error information has been added to any rows.</span></span> <span data-ttu-id="24f8a-109">Se **HasErrors** é **true**, você pode usar o <xref:System.Data.DataTable.GetErrors%2A> método o **DataTable** para retornar e examinar somente as linhas com erros, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="24f8a-109">If **HasErrors** is **true**, you can use the <xref:System.Data.DataTable.GetErrors%2A> method of the **DataTable** to return and examine only the rows with errors, as shown in the following example.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
workTable.Columns.Add("CustID", Type.GetType("System.Int32"))  
workTable.Columns.Add("Total", Type.GetType("System.Double"))  
  
AddHandler workTable.RowChanged, New DataRowChangeEventHandler(AddressOf OnRowChanged)  
  
Dim i  As Int32  
  
For i  = 0 To 10  
  workTable.Rows.Add(New Object() {i , i *100})  
Next  
  
If workTable.HasErrors Then  
  Console.WriteLine("Errors in Table " & workTable.TableName)  
  
  Dim myRow As DataRow  
  
  For Each myRow In workTable.GetErrors()  
    Console.WriteLine("CustID = " & myRow("CustID").ToString())  
    Console.WriteLine(" Error = " & myRow.RowError & vbCrLf)  
  Next  
End If  
  
Private Shared Sub OnRowChanged( _  
    sender As Object, args As DataRowChangeEventArgs)  
  ' Check for zero values.  
  If CDbl(args.Row("Total")) = 0 Then args.Row.RowError = _  
      "Total cannot be 0."  
End Sub  
```  
  
```csharp  
DataTable  workTable = new DataTable("Customers");  
workTable.Columns.Add("CustID", typeof(Int32));  
workTable.Columns.Add("Total", typeof(Double));  
  
workTable.RowChanged += new DataRowChangeEventHandler(OnRowChanged);  
  
for (int i = 0; i < 10; i++)  
  workTable.Rows.Add(new Object[] {i, i*100});  
  
if (workTable.HasErrors)  
{  
  Console.WriteLine("Errors in Table " + workTable.TableName);  
  
  foreach (DataRow myRow in workTable.GetErrors())  
  {  
    Console.WriteLine("CustID = " + myRow["CustID"]);  
    Console.WriteLine(" Error = " + myRow.RowError + "\n");  
  }  
}  
  
protected static void OnRowChanged(  
    Object sender, DataRowChangeEventArgs args)  
{  
  // Check for zero values.  
  if (args.Row["Total"].Equals(0D))  
    args.Row.RowError = "Total cannot be 0.";  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="24f8a-110">Consulte também</span><span class="sxs-lookup"><span data-stu-id="24f8a-110">See Also</span></span>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="24f8a-111">Manipulação de dados em uma DataTable</span><span class="sxs-lookup"><span data-stu-id="24f8a-111">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 <span data-ttu-id="24f8a-112">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="24f8a-112">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)</span></span>