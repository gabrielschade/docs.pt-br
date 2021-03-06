---
title: Adicionando elementos, atributos e nós em uma árvore XML (Visual Basic)
ms.date: 07/20/2015
ms.assetid: e243e694-c987-43aa-8b22-1e33dace582c
ms.openlocfilehash: 86d28f5974e30a9b7f1a1e830cd40c3cd916e8ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643007"
---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-visual-basic"></a>Adicionando elementos, atributos e nós em uma árvore XML (Visual Basic)
Você pode adicionar conteúdo (elementos, atributos, comentários, instruções de processamento, texto e CDATA) a uma árvore XML existente.  
  
## <a name="methods-for-adding-content"></a>Métodos para adicionar conteúdo  
 Os seguintes métodos adicionam conteúdo filho a um <xref:System.Xml.Linq.XElement> ou a um <xref:System.Xml.Linq.XDocument>:  
  
|Método|Descrição|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|Adiciona conteúdo ao final do conteúdo filho de <xref:System.Xml.Linq.XContainer>.|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|Adiciona conteúdo ao início do conteúdo filho de <xref:System.Xml.Linq.XContainer>.|  
  
 Os seguintes métodos adicionam o conteúdo como nós irmãos de um <xref:System.Xml.Linq.XNode>. O nó mais comum ao qual você adiciona conteúdo irmão é <xref:System.Xml.Linq.XElement>, embora você possa adicionar conteúdo irmão válido a outros tipos de nós como <xref:System.Xml.Linq.XText> ou <xref:System.Xml.Linq.XComment>.  
  
|Método|Descrição|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|Adiciona conteúdo depois de <xref:System.Xml.Linq.XNode>.|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|Adiciona conteúdo antes de <xref:System.Xml.Linq.XNode>.|  
  
## <a name="example"></a>Exemplo  
  
### <a name="description"></a>Descrição  
 O exemplo a seguir cria duas árvores XML e, em seguida, modifica uma das árvores.  
  
### <a name="code"></a>Código  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element1>1</Element1>  
        <Element2>2</Element2>  
        <Element3>3</Element3>  
        <Element4>4</Element4>  
        <Element5>5</Element5>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child2>2</Child2>  
        <Child3>3</Child3>  
        <Child4>4</Child4>  
        <Child5>5</Child5>  
    </Root>  
  
xmlTree.Add(<NewChild>new content</NewChild>)  
xmlTree.Add( _  
    From el In srcTree.Elements() _  
    Where CInt(el) > 3 _  
    Select el)  
  
' Even though Child9 does not exist in srcTree, the following statement  
' will not throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"))  
Console.WriteLine(xmlTree)  
```  
  
### <a name="comments"></a>Comentários  
 Esse código gera a seguinte saída:  
  
```xml  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
  <Child4>4</Child4>  
  <Child5>5</Child5>  
  <NewChild>new content</NewChild>  
  <Element4>4</Element4>  
  <Element5>5</Element5>  
</Root>  
```  
  
## <a name="see-also"></a>Consulte também  
 [Modificando árvores XML (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
