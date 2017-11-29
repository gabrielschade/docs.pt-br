---
title: Como criar uma cena 3D
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
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dd84a95bf793b3da9970b605b2f02509e3938ab0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-a-3-d-scene"></a><span data-ttu-id="fc817-102">Como criar uma cena 3D</span><span class="sxs-lookup"><span data-stu-id="fc817-102">How to: Create a 3-D Scene</span></span>
<span data-ttu-id="fc817-103">Este exemplo mostra como criar um objeto 3D parecido com uma folha de papel que foi girada.</span><span class="sxs-lookup"><span data-stu-id="fc817-103">This example shows how to create a 3-D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="fc817-104">Um <xref:System.Windows.Controls.Viewport3D> juntamente com os seguintes componentes são usados para criar esta cena 3D simples:</span><span class="sxs-lookup"><span data-stu-id="fc817-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3-D scene:</span></span>  
  
-   <span data-ttu-id="fc817-105">Uma câmera é criada usando um <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span><span class="sxs-lookup"><span data-stu-id="fc817-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="fc817-106">A câmera especifica qual parte da cena 3D é visível.</span><span class="sxs-lookup"><span data-stu-id="fc817-106">The camera specifies what part of the 3-D scene is viewable.</span></span>  
  
-   <span data-ttu-id="fc817-107">Uma malha é criada para especificar a forma do objeto 3D (folha de papel) usando o <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> propriedade <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="fc817-107">A mesh is created to specify the shape of 3-D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="fc817-108">Um material é especificado para ser exibido na superfície do objeto (gradiente linear neste exemplo) usando o <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> propriedade <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="fc817-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="fc817-109">A luz é criada para ser exibido no objeto usando <xref:System.Windows.Media.Media3D.DirectionalLight>.</span><span class="sxs-lookup"><span data-stu-id="fc817-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc817-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="fc817-110">Example</span></span>  
 <span data-ttu-id="fc817-111">O código a seguir mostra como criar uma cena 3D em XAML.</span><span class="sxs-lookup"><span data-stu-id="fc817-111">The code below shows how to create a 3-D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="fc817-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="fc817-112">Example</span></span>  
 <span data-ttu-id="fc817-113">O código a seguir mostra como criar a mesma cena 3D em código procedural.</span><span class="sxs-lookup"><span data-stu-id="fc817-113">The code below shows how to create the same 3-D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="fc817-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fc817-114">See Also</span></span>  
 [<span data-ttu-id="fc817-115">Visão geral de elementos gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="fc817-115">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)