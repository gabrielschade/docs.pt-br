---
title: "Gravando o conteúdo do DataSet como dados XML"
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
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d43fd8ec006f92131056d389ed2153263f7b7f1c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="writing-dataset-contents-as-xml-data"></a><span data-ttu-id="002b1-102">Gravando o conteúdo do DataSet como dados XML</span><span class="sxs-lookup"><span data-stu-id="002b1-102">Writing DataSet Contents as XML Data</span></span>
<span data-ttu-id="002b1-103">No ADO.NET, você pode gravar a representação XML de um <xref:System.Data.DataSet>, com ou sem seu esquema.</span><span class="sxs-lookup"><span data-stu-id="002b1-103">In ADO.NET you can write an XML representation of a <xref:System.Data.DataSet>, with or without its schema.</span></span> <span data-ttu-id="002b1-104">Se as informações de esquema forem embutidas no XML embutido, elas serão gravadas através da linguagem de definição de esquema XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="002b1-104">If schema information is included inline with the XML, it is written using the XML Schema definition language (XSD).</span></span> <span data-ttu-id="002b1-105">O esquema contém as definições de tabela do <xref:System.Data.DataSet>, bem como as definições de relação e de restrição.</span><span class="sxs-lookup"><span data-stu-id="002b1-105">The schema contains the table definitions of the <xref:System.Data.DataSet> as well as the relation and constraint definitions.</span></span>  
  
 <span data-ttu-id="002b1-106">Quando um <xref:System.Data.DataSet> é gravado como dados XML, as linhas do <xref:System.Data.DataSet> são gravadas nas suas versões atuais.</span><span class="sxs-lookup"><span data-stu-id="002b1-106">When a <xref:System.Data.DataSet> is written as XML data, the rows in the <xref:System.Data.DataSet> are written in their current versions.</span></span> <span data-ttu-id="002b1-107">No entanto, o <xref:System.Data.DataSet> também pode ser gravado como um DiffGram de modo que os valores atuais e originais das linhas sejam incluídos.</span><span class="sxs-lookup"><span data-stu-id="002b1-107">However, the <xref:System.Data.DataSet> can also be written as a DiffGram so that both the current and the original values of the rows will be included.</span></span>  
  
 <span data-ttu-id="002b1-108">A representação XML do <xref:System.Data.DataSet> podem ser gravados em um arquivo, um fluxo, uma **XmlWriter**, ou uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="002b1-108">The XML representation of the <xref:System.Data.DataSet> can be written to a file, a stream, an **XmlWriter**, or a string.</span></span> <span data-ttu-id="002b1-109">Essas opções proporcionam excelente flexibilidade para o transporte da representação XML do <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="002b1-109">These choices provide great flexibility for how you transport the XML representation of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="002b1-110">Para obter a representação XML do <xref:System.Data.DataSet> como uma cadeia de caracteres, use o **GetXml** método conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="002b1-110">To obtain the XML representation of the <xref:System.Data.DataSet> as a string, use the **GetXml** method as shown in the following example.</span></span>  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 <span data-ttu-id="002b1-111">**GetXml** retorna a representação XML do <xref:System.Data.DataSet> sem informações de esquema.</span><span class="sxs-lookup"><span data-stu-id="002b1-111">**GetXml** returns the XML representation of the <xref:System.Data.DataSet> without schema information.</span></span> <span data-ttu-id="002b1-112">Para gravar as informações de esquema de <xref:System.Data.DataSet> (como um esquema XML) em uma cadeia de caracteres, use **GetXmlSchema**.</span><span class="sxs-lookup"><span data-stu-id="002b1-112">To write the schema information from the <xref:System.Data.DataSet> (as XML Schema) to a string, use **GetXmlSchema**.</span></span>  
  
 <span data-ttu-id="002b1-113">Para gravar um <xref:System.Data.DataSet> para um arquivo, fluxo, ou **XmlWriter**, use o **WriteXml** método.</span><span class="sxs-lookup"><span data-stu-id="002b1-113">To write a <xref:System.Data.DataSet> to a file, stream, or **XmlWriter**, use the **WriteXml** method.</span></span> <span data-ttu-id="002b1-114">O primeiro parâmetro transmitido **WriteXml** é o destino da saída XML.</span><span class="sxs-lookup"><span data-stu-id="002b1-114">The first parameter you pass to **WriteXml** is the destination of the XML output.</span></span> <span data-ttu-id="002b1-115">Por exemplo, passar uma cadeia de caracteres que contém um nome de arquivo, uma **TextWriter** objeto e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="002b1-115">For example, pass a string containing a file name, a **System.IO.TextWriter** object, and so on.</span></span> <span data-ttu-id="002b1-116">Você pode passar um segundo parâmetro opcional de um **XmlWriteMode** para especificar como a saída XML a ser gravado.</span><span class="sxs-lookup"><span data-stu-id="002b1-116">You can pass an optional second parameter of an **XmlWriteMode** to specify how the XML output is to be written.</span></span>  
  
 <span data-ttu-id="002b1-117">A tabela a seguir mostra as opções para **XmlWriteMode**.</span><span class="sxs-lookup"><span data-stu-id="002b1-117">The following table shows the options for **XmlWriteMode**.</span></span>  
  
|<span data-ttu-id="002b1-118">Opção de XmlWriteMode</span><span class="sxs-lookup"><span data-stu-id="002b1-118">XmlWriteMode option</span></span>|<span data-ttu-id="002b1-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="002b1-119">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="002b1-120">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="002b1-120">**IgnoreSchema**</span></span>|<span data-ttu-id="002b1-121">Grava o conteúdo atual do <xref:System.Data.DataSet> como dados XML, sem um esquema XML.</span><span class="sxs-lookup"><span data-stu-id="002b1-121">Writes the current contents of the <xref:System.Data.DataSet> as XML data, without an XML Schema.</span></span> <span data-ttu-id="002b1-122">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="002b1-122">This is the default.</span></span>|  
|<span data-ttu-id="002b1-123">**WriteSchema**</span><span class="sxs-lookup"><span data-stu-id="002b1-123">**WriteSchema**</span></span>|<span data-ttu-id="002b1-124">Grava o conteúdo atual do <xref:System.Data.DataSet> como dados XML com a estrutura relacional como um esquema XML embutido.</span><span class="sxs-lookup"><span data-stu-id="002b1-124">Writes the current contents of the <xref:System.Data.DataSet> as XML data with the relational structure as inline XML Schema.</span></span>|  
|<span data-ttu-id="002b1-125">**DiffGram**</span><span class="sxs-lookup"><span data-stu-id="002b1-125">**DiffGram**</span></span>|<span data-ttu-id="002b1-126">Grava todo o <xref:System.Data.DataSet> como um DiffGram, incluindo valores originais e atuais.</span><span class="sxs-lookup"><span data-stu-id="002b1-126">Writes the entire <xref:System.Data.DataSet> as a DiffGram, including original and current values.</span></span> <span data-ttu-id="002b1-127">Para obter mais informações, consulte [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span><span class="sxs-lookup"><span data-stu-id="002b1-127">For more information, see [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span></span>|  
  
 <span data-ttu-id="002b1-128">Ao escrever uma representação XML de um <xref:System.Data.DataSet> que contém **DataRelation** objetos, provavelmente você desejará que o XML resultante para que as linhas filho de cada relação aninhada dentro de seus elementos pai relacionado.</span><span class="sxs-lookup"><span data-stu-id="002b1-128">When writing an XML representation of a <xref:System.Data.DataSet> that contains **DataRelation** objects, you will most likely want the resulting XML to have the child rows of each relation nested within their related parent elements.</span></span> <span data-ttu-id="002b1-129">Para fazer isso, defina o **aninhadas** propriedade o **DataRelation** para **true** quando você adiciona o **DataRelation** para o <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="002b1-129">To accomplish this, set the **Nested** property of the **DataRelation** to **true** when you add the **DataRelation** to the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="002b1-130">Para obter mais informações, consulte [aninhamento DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span><span class="sxs-lookup"><span data-stu-id="002b1-130">For more information, see [Nesting DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span></span>  
  
 <span data-ttu-id="002b1-131">A seguir, há dois exemplos de como gravar a representação XML de um <xref:System.Data.DataSet> em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="002b1-131">Following are two examples of how to write the XML representation of a <xref:System.Data.DataSet> to a file.</span></span> <span data-ttu-id="002b1-132">O primeiro exemplo passa o nome de arquivo para o XML resultante como uma cadeia de caracteres **WriteXml**.</span><span class="sxs-lookup"><span data-stu-id="002b1-132">The first example passes the file name for the resulting XML as a string to **WriteXml**.</span></span> <span data-ttu-id="002b1-133">O segundo exemplo passa um **System.IO.StreamWriter** objeto.</span><span class="sxs-lookup"><span data-stu-id="002b1-133">The second example passes a **System.IO.StreamWriter** object.</span></span>  
  
```vb  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema)  
```  
  
```csharp  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema);  
```  
  
```vb  
Dim xmlSW As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xml")  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema)  
xmlSW.Close()  
```  
  
```csharp  
System.IO.StreamWriter xmlSW = new System.IO.StreamWriter("Customers.xml");  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema);  
xmlSW.Close();  
```  
  
## <a name="mapping-columns-to-xml-elements-attributes-and-text"></a><span data-ttu-id="002b1-134">Mapeando colunas para elementos XML, atributos e texto</span><span class="sxs-lookup"><span data-stu-id="002b1-134">Mapping Columns to XML Elements, Attributes, and Text</span></span>  
 <span data-ttu-id="002b1-135">Você pode especificar como uma coluna de uma tabela é representada em XML usando o **ColumnMapping** propriedade o **DataColumn** objeto.</span><span class="sxs-lookup"><span data-stu-id="002b1-135">You can specify how a column of a table is represented in XML using the **ColumnMapping** property of the **DataColumn** object.</span></span> <span data-ttu-id="002b1-136">A tabela a seguir mostra os diferentes **MappingType** valores para o **ColumnMapping** propriedade de uma coluna de tabela e o XML resultante.</span><span class="sxs-lookup"><span data-stu-id="002b1-136">The following table shows the different **MappingType** values for the **ColumnMapping** property of a table column, and the resulting XML.</span></span>  
  
|<span data-ttu-id="002b1-137">Valor de MappingType</span><span class="sxs-lookup"><span data-stu-id="002b1-137">MappingType value</span></span>|<span data-ttu-id="002b1-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="002b1-138">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="002b1-139">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="002b1-139">**Element**</span></span>|<span data-ttu-id="002b1-140">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="002b1-140">This is the default.</span></span> <span data-ttu-id="002b1-141">A coluna é gravada como um elemento XML, em que ColumnName é o nome do elemento e o conteúdo da coluna é gravado como texto do elemento.</span><span class="sxs-lookup"><span data-stu-id="002b1-141">The column is written as an XML element where the ColumnName is the name of the element and the contents of the column are written as the text of the element.</span></span> <span data-ttu-id="002b1-142">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="002b1-142">For example:</span></span><br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|<span data-ttu-id="002b1-143">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="002b1-143">**Attribute**</span></span>|<span data-ttu-id="002b1-144">A coluna é gravada como um atributo XML do elemento XML da linha atual, em que ColumnName é o nome do atributo e o conteúdo da coluna é gravado como valor do atributo.</span><span class="sxs-lookup"><span data-stu-id="002b1-144">The column is written as an XML attribute of the XML element for the current row where the ColumnName is the name of the attribute and the contents of the column are written as the value of the attribute.</span></span> <span data-ttu-id="002b1-145">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="002b1-145">For example:</span></span><br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|<span data-ttu-id="002b1-146">**SimpleContent**</span><span class="sxs-lookup"><span data-stu-id="002b1-146">**SimpleContent**</span></span>|<span data-ttu-id="002b1-147">O conteúdo de coluna é gravado como texto no elemento XML da linha atual.</span><span class="sxs-lookup"><span data-stu-id="002b1-147">The contents of the column are written as text in the XML element for the current row.</span></span> <span data-ttu-id="002b1-148">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="002b1-148">For example:</span></span><br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> <span data-ttu-id="002b1-149">Observe que **SimpleContent** não pode ser definida para uma coluna de uma tabela que tem **elemento** colunas ou relações aninhadas.</span><span class="sxs-lookup"><span data-stu-id="002b1-149">Note that **SimpleContent** cannot be set for a column of a table that has **Element** columns or nested relations.</span></span>|  
|<span data-ttu-id="002b1-150">**Oculto**</span><span class="sxs-lookup"><span data-stu-id="002b1-150">**Hidden**</span></span>|<span data-ttu-id="002b1-151">A coluna não é gravada na saída XML.</span><span class="sxs-lookup"><span data-stu-id="002b1-151">The column is not written in the XML output.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="002b1-152">Consulte também</span><span class="sxs-lookup"><span data-stu-id="002b1-152">See Also</span></span>  
 <span data-ttu-id="002b1-153">[Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md) (Usando XML em um DataSet)</span><span class="sxs-lookup"><span data-stu-id="002b1-153">[Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)</span></span>  
 [<span data-ttu-id="002b1-154">DiffGrams</span><span class="sxs-lookup"><span data-stu-id="002b1-154">DiffGrams</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 [<span data-ttu-id="002b1-155">Aninhamento DataRelations</span><span class="sxs-lookup"><span data-stu-id="002b1-155">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [<span data-ttu-id="002b1-156">Gravando informações de esquema de conjunto de dados como XSD</span><span class="sxs-lookup"><span data-stu-id="002b1-156">Writing DataSet Schema Information as XSD</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)  
 <span data-ttu-id="002b1-157">[DataSets, DataTables, and DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md) (DataSets, DataTables e DataViews)</span><span class="sxs-lookup"><span data-stu-id="002b1-157">[DataSets, DataTables, and DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)</span></span>  
 <span data-ttu-id="002b1-158">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="002b1-158">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)</span></span>