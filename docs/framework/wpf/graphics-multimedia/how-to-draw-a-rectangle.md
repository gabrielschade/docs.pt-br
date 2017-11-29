---
title: "Como desenhar um retângulo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c163897af27c9b34c8cd87a3b197047f86d21ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-rectangle"></a><span data-ttu-id="4080b-102">Como desenhar um retângulo</span><span class="sxs-lookup"><span data-stu-id="4080b-102">How to: Draw a Rectangle</span></span>
<span data-ttu-id="4080b-103">Este exemplo mostra como desenhar um retângulo, usando o <xref:System.Windows.Shapes.Rectangle> elemento.</span><span class="sxs-lookup"><span data-stu-id="4080b-103">This example shows how to draw a rectangle by using the <xref:System.Windows.Shapes.Rectangle> element.</span></span>  
  
 <span data-ttu-id="4080b-104">Para desenhar um retângulo, crie um <xref:System.Windows.Shapes.Rectangle> elemento e especifique seu <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="4080b-104">To draw a rectangle, create a <xref:System.Windows.Shapes.Rectangle> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="4080b-105">Para pintar o interior de um retângulo, defina seu <xref:System.Windows.Shapes.Shape.Fill%2A>.</span><span class="sxs-lookup"><span data-stu-id="4080b-105">To paint the inside of the rectangle, set its <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="4080b-106">Para fornecer uma estrutura de tópicos de retângulo, use seu <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> propriedades.</span><span class="sxs-lookup"><span data-stu-id="4080b-106">To give the rectangle an outline, use its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties.</span></span>  
  
 <span data-ttu-id="4080b-107">Para dar o retângulo arredondado cantos, especifique o valor opcional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> e <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> propriedades.</span><span class="sxs-lookup"><span data-stu-id="4080b-107">To give the rectangle rounded corners, specify the optional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="4080b-108">O <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> e <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> propriedades definem o raios eixos x e y da elipse que é usada para arredondar os cantos do retângulo.</span><span class="sxs-lookup"><span data-stu-id="4080b-108">The <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties set the x-axis and y-axis radii of the ellipse that is used to round the corners of the rectangle.</span></span>  
  
 <span data-ttu-id="4080b-109">No exemplo a seguir, dois <xref:System.Windows.Shapes.Rectangle> elementos são desenhados em um <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="4080b-109">In the following example, two <xref:System.Windows.Shapes.Rectangle> elements are drawn in a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="4080b-110">O primeiro retângulo tem um <xref:System.Windows.Media.Brushes.Blue%2A> interiores.</span><span class="sxs-lookup"><span data-stu-id="4080b-110">The first rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior.</span></span> <span data-ttu-id="4080b-111">O segundo retângulo tem um <xref:System.Windows.Media.Brushes.Blue%2A> interiores, uma <xref:System.Windows.Media.Brushes.Black%2A> contorno e cantos arredondados.</span><span class="sxs-lookup"><span data-stu-id="4080b-111">The second rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior, a <xref:System.Windows.Media.Brushes.Black%2A> outline, and rounded corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4080b-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4080b-112">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 <span data-ttu-id="4080b-113">Embora este exemplo usa um <xref:System.Windows.Controls.Canvas> para conter os retângulos, você pode usar elementos de retângulo (e todos os outros elementos de forma) com qualquer <xref:System.Windows.Controls.Panel> ou <xref:System.Windows.Controls.Control> que dá suporte a conteúdo não texto.</span><span class="sxs-lookup"><span data-stu-id="4080b-113">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the rectangles, you can use rectangle elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span> <span data-ttu-id="4080b-114">Na verdade, retângulos são particularmente útil para exibir planos de fundo para as partes <xref:System.Windows.Controls.Grid> painéis.</span><span class="sxs-lookup"><span data-stu-id="4080b-114">In fact, rectangles are particularly useful for providing backgrounds for portions of <xref:System.Windows.Controls.Grid> panels.</span></span> <span data-ttu-id="4080b-115">Para ver um exemplo, consulte a [Visão geral da tabela](../../../../docs/framework/wpf/advanced/table-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4080b-115">For an example, see the [Table Overview](../../../../docs/framework/wpf/advanced/table-overview.md).</span></span>  
  
 <span data-ttu-id="4080b-116">Este exemplo faz parte de um exemplo maior; para ver o exemplo completo, consulte o [Exemplo de elementos de forma](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="4080b-116">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4080b-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4080b-117">See Also</span></span>  
 <xref:System.Windows.Shapes.Rectangle>  
 [<span data-ttu-id="4080b-118">Exemplo de elementos de forma</span><span class="sxs-lookup"><span data-stu-id="4080b-118">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [<span data-ttu-id="4080b-119">Visão geral de formas e desenho básico no WPF</span><span class="sxs-lookup"><span data-stu-id="4080b-119">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [<span data-ttu-id="4080b-120">Visão geral da tabela</span><span class="sxs-lookup"><span data-stu-id="4080b-120">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)