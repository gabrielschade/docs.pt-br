---
title: "Adicionando restrições existentes para um conjunto de dados"
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
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e457113eff471c620ccdbf78337d2013d7a62bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="adding-existing-constraints-to-a-dataset"></a><span data-ttu-id="f452e-102">Adicionando restrições existentes para um conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="f452e-102">Adding Existing Constraints to a DataSet</span></span>
<span data-ttu-id="f452e-103">O **preencher** método o **DataAdapter** preenche uma <xref:System.Data.DataSet> apenas com colunas de tabelas e linhas de uma fonte de dados; no entanto restrições mais frequentemente definidas pela fonte de dados, o **preencher** método não adicionar essas informações de esquema para o **DataSet** por padrão.</span><span class="sxs-lookup"><span data-stu-id="f452e-103">The **Fill** method of the **DataAdapter** fills a <xref:System.Data.DataSet> only with table columns and rows from a data source; though constraints are commonly set by the data source, the **Fill** method does not add this schema information to the **DataSet** by default.</span></span> <span data-ttu-id="f452e-104">Para popular um **DataSet** com informações de restrição de chave primária existente de uma fonte de dados, você pode chamar o **FillSchema** método do **DataAdapter**, ou defina o **MissingSchemaAction** propriedade o **DataAdapter** para **AddWithKey** antes de chamar **preencher**.</span><span class="sxs-lookup"><span data-stu-id="f452e-104">To populate a **DataSet** with existing primary key constraint information from a data source, you can either call the **FillSchema** method of the **DataAdapter**, or set the **MissingSchemaAction** property of the **DataAdapter** to **AddWithKey** before calling **Fill**.</span></span> <span data-ttu-id="f452e-105">Isso garantirá que a chave primária restrições no **DataSet** refletem aqueles na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f452e-105">This will ensure that primary key constraints in the **DataSet** reflect those at the data source.</span></span> <span data-ttu-id="f452e-106">Informações de restrição de chave estrangeira não está incluídas e devem ser criadas explicitamente, conforme mostrado no [restrições de DataTable](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="f452e-106">Foreign key constraint information is not included and must be created explicitly, as shown in [DataTable Constraints](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="f452e-107">Adicionando informações de esquema para um **DataSet** para preenchê-lo com dados garante que as restrições de chave primária são incluídas com o <xref:System.Data.DataTable> objetos no **conjunto de dados**.</span><span class="sxs-lookup"><span data-stu-id="f452e-107">Adding schema information to a **DataSet** before filling it with data ensures that primary key constraints are included with the <xref:System.Data.DataTable> objects in the **DataSet**.</span></span> <span data-ttu-id="f452e-108">Como resultado, quando adicionais chamadas para preencher o **DataSet** são feitas, o principal informações de coluna de chave são usadas para corresponder a novas linhas da fonte de dados com linhas atuais em cada **DataTable**e os dados atuais as tabelas é substituído por dados da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f452e-108">As a result, when additional calls to fill the **DataSet** are made, the primary key column information is used to match new rows from the data source with current rows in each **DataTable**, and current data in the tables is overwritten with data from the data source.</span></span> <span data-ttu-id="f452e-109">Sem as informações de esquema, as novas linhas da fonte de dados são anexadas ao **conjunto de dados**, resultando em linhas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="f452e-109">Without the schema information, the new rows from the data source are appended to the **DataSet**, resulting in duplicate rows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f452e-110">Se uma coluna em uma fonte de dados for identificada como incremento automático, o **FillSchema** método, ou o **preencher** método com um **MissingSchemaAction** de  **AddWithKey**, cria um **DataColumn** com um **AutoIncrement** propriedade definida como `true`.</span><span class="sxs-lookup"><span data-stu-id="f452e-110">If a column in a data source is identified as auto-incrementing, the **FillSchema** method, or the **Fill** method with a **MissingSchemaAction** of **AddWithKey**, creates a **DataColumn** with an **AutoIncrement** property set to `true`.</span></span> <span data-ttu-id="f452e-111">No entanto, você precisará definir o **AutoIncrementStep** e **AutoIncrementSeed** valores por conta própria.</span><span class="sxs-lookup"><span data-stu-id="f452e-111">However, you will need to set the **AutoIncrementStep** and **AutoIncrementSeed** values yourself.</span></span> <span data-ttu-id="f452e-112">Para obter mais informações sobre colunas de incremento automático, consulte [criar colunas de incremento automático](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span><span class="sxs-lookup"><span data-stu-id="f452e-112">For more information about auto-incrementing columns, see [Creating AutoIncrement Columns](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span></span>  
  
 <span data-ttu-id="f452e-113">Usando **FillSchema** ou configuração de **MissingSchemaAction** para **AddWithKey** requer processamento extra na fonte de dados para determinar as informações de coluna de chave primária.</span><span class="sxs-lookup"><span data-stu-id="f452e-113">Using **FillSchema** or setting the **MissingSchemaAction** to **AddWithKey** requires extra processing at the data source to determine primary key column information.</span></span> <span data-ttu-id="f452e-114">Esse processamento adicional pode prejudicar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="f452e-114">This additional processing can hinder performance.</span></span> <span data-ttu-id="f452e-115">Se você souber que as informações de chave primárias em tempo de design, é recomendável que você especificar explicitamente a coluna de chave primária ou colunas para alcançar um desempenho ideal.</span><span class="sxs-lookup"><span data-stu-id="f452e-115">If you know the primary key information at design time, we recommend that you explicitly specify the primary key column or columns in order to achieve optimal performance.</span></span> <span data-ttu-id="f452e-116">Para obter informações sobre como definir explicitamente as informações de chave primária para uma tabela, consulte [definindo chaves primárias](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="f452e-116">For information about explicitly setting primary key information for a table, see [Defining Primary Keys](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
 <span data-ttu-id="f452e-117">O exemplo de código a seguir mostra como adicionar informações de esquema para um **DataSet** usando **FillSchema**.</span><span class="sxs-lookup"><span data-stu-id="f452e-117">The following code example shows how to add schema information to a **DataSet** using **FillSchema**.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 <span data-ttu-id="f452e-118">O exemplo de código a seguir mostra como adicionar informações de esquema para um **DataSet** usando o **MissingSchemaAction.AddWithKey** propriedade o **preencher** método.</span><span class="sxs-lookup"><span data-stu-id="f452e-118">The following code example shows how to add schema information to a **DataSet** using the **MissingSchemaAction.AddWithKey** property of the **Fill** method.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="f452e-119">Manipulando vários conjuntos de resultados</span><span class="sxs-lookup"><span data-stu-id="f452e-119">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="f452e-120">Se o **DataAdapter** encontra vários conjuntos de resultados retornados do **SelectCommand**, ele criará várias tabelas no **conjunto de dados**.</span><span class="sxs-lookup"><span data-stu-id="f452e-120">If the **DataAdapter** encounters multiple result sets returned from the **SelectCommand**, it will create multiple tables in the **DataSet**.</span></span> <span data-ttu-id="f452e-121">As tabelas terá um nome de base zero padrão incremental **tabela** *N*, começando com **tabela** em vez de "Table0".</span><span class="sxs-lookup"><span data-stu-id="f452e-121">The tables will be given a zero-based incremental default name of **Table** *N*, starting with **Table** instead of "Table0".</span></span> <span data-ttu-id="f452e-122">Se um nome de tabela é passado como um argumento para o **FillSchema** método, as tabelas terá um nome incremental com base em zero do **TableName** *N*, começando com **TableName** em vez de "TableName0".</span><span class="sxs-lookup"><span data-stu-id="f452e-122">If a table name is passed as an argument to the **FillSchema** method, the tables will be given a zero-based incremental name of **TableName** *N*, starting with **TableName** instead of "TableName0".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f452e-123">Se o **FillSchema** método o **OleDbDataAdapter** objeto é chamado para um comando que retorna vários conjuntos de resultados, somente as informações de esquema do primeiro conjunto de resultados serão retornadas.</span><span class="sxs-lookup"><span data-stu-id="f452e-123">If the **FillSchema** method of the **OleDbDataAdapter** object is called for a command that returns multiple result sets, only the schema information from the first result set is returned.</span></span> <span data-ttu-id="f452e-124">Quando retornando informações de esquema de resultados múltiplos conjuntos usando o **OleDbDataAdapter**, é recomendável que você especifique um **MissingSchemaAction** de **AddWithKey** e obter as informações de esquema ao chamar o **preencher** método.</span><span class="sxs-lookup"><span data-stu-id="f452e-124">When returning schema information for multiple result sets using the **OleDbDataAdapter**, it is recommended that you specify a **MissingSchemaAction** of **AddWithKey** and obtain the schema information when calling the **Fill** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f452e-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f452e-125">See Also</span></span>  
 [<span data-ttu-id="f452e-126">DataAdapters e DataReaders</span><span class="sxs-lookup"><span data-stu-id="f452e-126">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 <span data-ttu-id="f452e-127">[DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md) (DataSets, DataTables e DataViews)</span><span class="sxs-lookup"><span data-stu-id="f452e-127">[DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)</span></span>  
 <span data-ttu-id="f452e-128">[Retrieving and Modifying Data in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md) (Recuperando e modificando dados no ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="f452e-128">[Retrieving and Modifying Data in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)</span></span>  
 <span data-ttu-id="f452e-129">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="f452e-129">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)</span></span>