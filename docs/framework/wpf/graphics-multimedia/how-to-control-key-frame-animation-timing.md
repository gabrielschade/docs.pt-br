---
title: "Como controlar o tempo de animação do quadro-chave"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-fram animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3bc3566cf25282749a09c5f2372cd1c81e3ce881
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="40996-102">Como controlar o tempo de animação do quadro-chave</span><span class="sxs-lookup"><span data-stu-id="40996-102">How to: Control Key-Frame Animation Timing</span></span>
<span data-ttu-id="40996-103">Este exemplo mostra como controlar o intervalo de quadros chave em uma animação de quadro chave.</span><span class="sxs-lookup"><span data-stu-id="40996-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="40996-104">Assim como outras animações, animações de quadro-chave têm um <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="40996-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="40996-105">Além de especificar a duração de uma animação, é necessário especificar qual parte da duração é atribuída a cada um de seus quadros chave.</span><span class="sxs-lookup"><span data-stu-id="40996-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="40996-106">Ínterim, você deve especificar um <xref:System.Windows.Media.Animation.KeyTime> para cada quadro chave na animação.</span><span class="sxs-lookup"><span data-stu-id="40996-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>  
  
 <span data-ttu-id="40996-107">O <xref:System.Windows.Media.Animation.KeyTime> para cada quadro chave especifica quando um quadro chave termina (ele não especifica o período de tempo que um quadro chave toca).</span><span class="sxs-lookup"><span data-stu-id="40996-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="40996-108">Você pode especificar um <xref:System.Windows.Media.Animation.KeyTime> como um <xref:System.TimeSpan> valor, como uma porcentagem ou como o <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> ou <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> valor especial.</span><span class="sxs-lookup"><span data-stu-id="40996-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40996-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="40996-109">Example</span></span>  
 <span data-ttu-id="40996-110">O exemplo a seguir usa um <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> para animar um retângulo pela tela.</span><span class="sxs-lookup"><span data-stu-id="40996-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="40996-111">Tempos de quadro chave chave são definidos com <xref:System.TimeSpan> valores.</span><span class="sxs-lookup"><span data-stu-id="40996-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
 [!code-vb[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
 [!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]  
  
 <span data-ttu-id="40996-112">A ilustração a seguir mostra quando o valor de cada quadro chave é alcançado.</span><span class="sxs-lookup"><span data-stu-id="40996-112">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="40996-113">![Valores de chave são alcançados em 3, 4 e 10 segundos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="40996-113">![Key values are reached at 3, 4, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>  
  
 <span data-ttu-id="40996-114">O exemplo a seguir mostra uma animação que é idêntica, exceto que os tempos da chave os quadros chave são especificados com valores de percentual.</span><span class="sxs-lookup"><span data-stu-id="40996-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
 [!code-vb[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
 [!code-xaml[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]  
  
 <span data-ttu-id="40996-115">A ilustração a seguir mostra quando o valor de cada quadro chave é alcançado.</span><span class="sxs-lookup"><span data-stu-id="40996-115">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="40996-116">![Valores de chave são alcançados em 3, 4 e 10 segundos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="40996-116">![Key values are reached at 3, 4, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>  
  
 <span data-ttu-id="40996-117">O exemplo a seguir usa <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> valores de tempo de chave.</span><span class="sxs-lookup"><span data-stu-id="40996-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
 [!code-vb[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
 [!code-xaml[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]  
  
 <span data-ttu-id="40996-118">A ilustração a seguir mostra quando o valor de cada quadro chave é alcançado.</span><span class="sxs-lookup"><span data-stu-id="40996-118">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="40996-119">![Valores de chave são alcançados em 3,3, 6,6 e 9,9 segundos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="40996-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>  
  
 <span data-ttu-id="40996-120">O exemplo final usa <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> valores de tempo de chave.</span><span class="sxs-lookup"><span data-stu-id="40996-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
 [!code-vb[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
 [!code-xaml[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]  
  
 <span data-ttu-id="40996-121">A ilustração a seguir mostra quando o valor de cada quadro chave é alcançado.</span><span class="sxs-lookup"><span data-stu-id="40996-121">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="40996-122">![Valores de chave são alcançados em 0, 5 e 10 segundos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="40996-122">![Key values are reached at 0, 5, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>  
  
 <span data-ttu-id="40996-123">Para simplificar, as versões de código neste exemplo usam animações locais, não storyboards, porque uma única animação está sendo aplicada a uma única propriedade, mas os exemplos podem ser modificados para utilizar storyboards.</span><span class="sxs-lookup"><span data-stu-id="40996-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="40996-124">Para ver um exemplo que mostra como declarar um storyboard no código, consulte [Animar uma propriedade usando um Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="40996-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span></span>  
  
 <span data-ttu-id="40996-125">Para ver o exemplo completo, consulte [Exemplo de animação de quadro-chave](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="40996-125">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span> <span data-ttu-id="40996-126">Para obter mais informações sobre animações de quadro chave, consulte a [Visão geral de animações de quadro chave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="40996-126">For more information about key frame animations, see the [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40996-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="40996-127">See Also</span></span>  
 [<span data-ttu-id="40996-128">Visão geral das animações de quadro-chave</span><span class="sxs-lookup"><span data-stu-id="40996-128">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="40996-129">Visão geral da animação</span><span class="sxs-lookup"><span data-stu-id="40996-129">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="40996-130">Tópicos explicativos</span><span class="sxs-lookup"><span data-stu-id="40996-130">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)