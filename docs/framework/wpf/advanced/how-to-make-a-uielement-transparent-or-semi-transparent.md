---
title: Como deixar um UIElement transparente ou semitransparente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec35ae2e064acf78d1165f64ce8c9e34b153299d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a><span data-ttu-id="4947d-102">Como deixar um UIElement transparente ou semitransparente</span><span class="sxs-lookup"><span data-stu-id="4947d-102">How to: Make a UIElement Transparent or Semi-Transparent</span></span>
<span data-ttu-id="4947d-103">Este exemplo mostra como fazer um <xref:System.Windows.UIElement> transparente ou semi-transparente.</span><span class="sxs-lookup"><span data-stu-id="4947d-103">This example shows how to make a <xref:System.Windows.UIElement> transparent or semi-transparent.</span></span> <span data-ttu-id="4947d-104">Para tornar um elemento transparente ou semi-transparente, você deve definir seu <xref:System.Windows.UIElement.Opacity%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="4947d-104">To make an element transparent or semi-transparent, you set its <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="4947d-105">Um valor de `0.0` torna o elemento completamente transparente, enquanto um valor de `1.0` torna o elemento completamente opaco.</span><span class="sxs-lookup"><span data-stu-id="4947d-105">A value of `0.0` makes the element completely transparent, while a value of `1.0` makes the element completely opaque.</span></span> <span data-ttu-id="4947d-106">Um valor de `0.5` torna o elemento 50% opaco e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="4947d-106">A value of `0.5` makes the element 50% opaque, and so on.</span></span> <span data-ttu-id="4947d-107">Um elemento <xref:System.Windows.UIElement.Opacity%2A> é definido como `1.0` por padrão.</span><span class="sxs-lookup"><span data-stu-id="4947d-107">An element's <xref:System.Windows.UIElement.Opacity%2A> is set to `1.0` by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4947d-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4947d-108">Example</span></span>  
 <span data-ttu-id="4947d-109">O exemplo a seguir define o <xref:System.Windows.UIElement.Opacity%2A> de um botão para `0.25`, fazendo e seu conteúdo (neste caso, o texto do botão) 25% opaco.</span><span class="sxs-lookup"><span data-stu-id="4947d-109">The following example sets the <xref:System.Windows.UIElement.Opacity%2A> of a button to `0.25`, making it and its contents (in this case, the button's text) 25% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 <span data-ttu-id="4947d-110">Se o conteúdo de um elemento têm seus próprios <xref:System.Windows.UIElement.Opacity%2A> configurações, esses valores são multiplicadas contendo elementos <xref:System.Windows.UIElement.Opacity%2A>.</span><span class="sxs-lookup"><span data-stu-id="4947d-110">If an element's contents have their own <xref:System.Windows.UIElement.Opacity%2A> settings, those values are multiplied against the containing elements <xref:System.Windows.UIElement.Opacity%2A>.</span></span>  
  
 <span data-ttu-id="4947d-111">O exemplo a seguir define um botão <xref:System.Windows.UIElement.Opacity%2A> para `0.25`e o <xref:System.Windows.UIElement.Opacity%2A> de um <xref:System.Windows.Controls.Image> controle contido no botão para `0.5`.</span><span class="sxs-lookup"><span data-stu-id="4947d-111">The following example sets a button's <xref:System.Windows.UIElement.Opacity%2A> to `0.25`, and the <xref:System.Windows.UIElement.Opacity%2A> of an <xref:System.Windows.Controls.Image> control contained with in the button to `0.5`.</span></span> <span data-ttu-id="4947d-112">Como resultado, a imagem aparece 12,5% opaca: 0,25 * 0,5 = 0,125.</span><span class="sxs-lookup"><span data-stu-id="4947d-112">As a result, the image appears 12.5% opaque: 0.25 * 0.5 = 0.125.</span></span>  
  
 [!code-xaml[brushsamples_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 <span data-ttu-id="4947d-113">Outra maneira de controlar a opacidade de um elemento é definir a opacidade do <xref:System.Windows.Media.Brush> que pinta o elemento.</span><span class="sxs-lookup"><span data-stu-id="4947d-113">Another way to control the opacity of an element is to set the opacity of the <xref:System.Windows.Media.Brush> that paints the element.</span></span> <span data-ttu-id="4947d-114">Essa abordagem permite que você altere seletivamente a opacidade de partes de um elemento e fornece os benefícios de desempenho com o uso do elemento <xref:System.Windows.UIElement.Opacity%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="4947d-114">This approach enables you to selectively alter the opacity of portions of an element, and provides performance benefits over using the element's <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="4947d-115">O exemplo a seguir define o <xref:System.Windows.Media.Brush.Opacity%2A> de um <xref:System.Windows.Media.SolidColorBrush> usado para pintar o botão <xref:System.Windows.Controls.Control.Background%2A> é definido como `0.25`.</span><span class="sxs-lookup"><span data-stu-id="4947d-115">The following example sets the <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush> used to paint the button's <xref:System.Windows.Controls.Control.Background%2A> is set to `0.25`.</span></span> <span data-ttu-id="4947d-116">Como resultado, a tela de fundo do pincel é 25% opaca, mas seu conteúdo (o texto do botão) permanece 100% opaco.</span><span class="sxs-lookup"><span data-stu-id="4947d-116">As a result, the brush's background is 25% opaque, but its contents (the button's text) remain 100% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 <span data-ttu-id="4947d-117">Também é possível controlar a opacidade de cores individuais em um pincel.</span><span class="sxs-lookup"><span data-stu-id="4947d-117">You may also control the opacity of individual colors within a brush.</span></span> <span data-ttu-id="4947d-118">Para obter mais informações sobre cores e pincéis, consulte [Visão geral de pintura com cores sólidas e gradientes](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4947d-118">For more information about colors and brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span> <span data-ttu-id="4947d-119">Para ver um exemplo que mostra como animar a opacidade de um elemento, consulte [Animar a opacidade de um elemento ou pincel](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).</span><span class="sxs-lookup"><span data-stu-id="4947d-119">For an example showing how to animate an element's opacity, see [Animate the Opacity of an Element or Brush](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).</span></span>