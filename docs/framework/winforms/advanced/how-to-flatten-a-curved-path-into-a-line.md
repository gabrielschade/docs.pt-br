---
title: Como nivelar um demarcador curvo em uma linha
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 62dedc987c2b622dc3f3aa81dac3cdea6dd75740
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="29ea7-102">Como nivelar um demarcador curvo em uma linha</span><span class="sxs-lookup"><span data-stu-id="29ea7-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="29ea7-103">Um <xref:System.Drawing.Drawing2D.GraphicsPath> objeto armazena uma sequência de splines de Bézier e linhas.</span><span class="sxs-lookup"><span data-stu-id="29ea7-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="29ea7-104">Você pode adicionar vários tipos de curvas (elipses, arcos, splines cardinais) em um caminho, mas cada curva é convertida em um spline de Bézier antes de ser armazenado no caminho.</span><span class="sxs-lookup"><span data-stu-id="29ea7-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="29ea7-105">Mesclar um caminho consiste em converter cada spline de Bézier no caminho em uma sequência de linhas retas.</span><span class="sxs-lookup"><span data-stu-id="29ea7-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="29ea7-106">A ilustração a seguir mostra um caminho antes e após mesclar.</span><span class="sxs-lookup"><span data-stu-id="29ea7-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="29ea7-107">![Linhas retas e curvas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="29ea7-107">![Straight Lines and Curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="29ea7-108">Para mesclar um caminho</span><span class="sxs-lookup"><span data-stu-id="29ea7-108">To Flatten a Path</span></span>  
  
-   <span data-ttu-id="29ea7-109">chamar o <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> método de um <xref:System.Drawing.Drawing2D.GraphicsPath> objeto.</span><span class="sxs-lookup"><span data-stu-id="29ea7-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="29ea7-110">O <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> método recebe um argumento de achatamento que especifica a distância máxima entre o caminho mesclado e o caminho original.</span><span class="sxs-lookup"><span data-stu-id="29ea7-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29ea7-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="29ea7-111">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 [<span data-ttu-id="29ea7-112">Linhas, Curvas e Formas</span><span class="sxs-lookup"><span data-stu-id="29ea7-112">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="29ea7-113">Construindo e Desenhando Caminhos</span><span class="sxs-lookup"><span data-stu-id="29ea7-113">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)