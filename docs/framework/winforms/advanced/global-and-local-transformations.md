---
title: "Transformações globais e locais"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 432402fefc6c958fbab0b1450a429d9b130b8239
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="global-and-local-transformations"></a><span data-ttu-id="5debe-102">Transformações globais e locais</span><span class="sxs-lookup"><span data-stu-id="5debe-102">Global and Local Transformations</span></span>
<span data-ttu-id="5debe-103">Uma transformação global é uma transformação que se aplica a cada item desenhada por um determinado <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="5debe-103">A global transformation is a transformation that applies to every item drawn by a given <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="5debe-104">Em contraste, uma transformação local é uma transformação que se aplica a um item específico a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="5debe-104">In contrast, a local transformation is a transformation that applies to a specific item to be drawn.</span></span>  
  
## <a name="global-transformations"></a><span data-ttu-id="5debe-105">Transformações globais</span><span class="sxs-lookup"><span data-stu-id="5debe-105">Global Transformations</span></span>  
 <span data-ttu-id="5debe-106">Para criar uma transformação global, construir um <xref:System.Drawing.Graphics> de objeto e, em seguida, manipular seu <xref:System.Drawing.Graphics.Transform%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="5debe-106">To create a global transformation, construct a <xref:System.Drawing.Graphics> object, and then manipulate its <xref:System.Drawing.Graphics.Transform%2A> property.</span></span> <span data-ttu-id="5debe-107">O <xref:System.Drawing.Graphics.Transform%2A> propriedade é um <xref:System.Drawing.Drawing2D.Matrix> do objeto, portanto ele pode conter qualquer sequência de transformações afins.</span><span class="sxs-lookup"><span data-stu-id="5debe-107">The <xref:System.Drawing.Graphics.Transform%2A> property is a <xref:System.Drawing.Drawing2D.Matrix> object, so it can hold any sequence of affine transformations.</span></span> <span data-ttu-id="5debe-108">A transformação armazenados no <xref:System.Drawing.Graphics.Transform%2A> propriedade é chamada de transformações de mundo.</span><span class="sxs-lookup"><span data-stu-id="5debe-108">The transformation stored in the <xref:System.Drawing.Graphics.Transform%2A> property is called the world transformation.</span></span> <span data-ttu-id="5debe-109">O <xref:System.Drawing.Graphics> classe fornece vários métodos para a criação de uma transformação world composto: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>, e <xref:System.Drawing.Graphics.TranslateTransform%2A>.</span><span class="sxs-lookup"><span data-stu-id="5debe-109">The <xref:System.Drawing.Graphics> class provides several methods for building up a composite world transformation: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>, and <xref:System.Drawing.Graphics.TranslateTransform%2A>.</span></span> <span data-ttu-id="5debe-110">O exemplo a seguir desenha uma elipse duas vezes: uma vez antes de criar uma transformação global e outra vez depois.</span><span class="sxs-lookup"><span data-stu-id="5debe-110">The following example draws an ellipse twice: once before creating a world transformation and once after.</span></span> <span data-ttu-id="5debe-111">A transformação primeiro é dimensionada por um fator de 0,5 na direção y e, em seguida, move 50 unidades na direção x e gira 30 graus.</span><span class="sxs-lookup"><span data-stu-id="5debe-111">The transformation first scales by a factor of 0.5 in the y direction, then translates 50 units in the x direction, and then rotates 30 degrees.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 <span data-ttu-id="5debe-112">A ilustração a seguir mostra as matrizes envolvidas na transformação.</span><span class="sxs-lookup"><span data-stu-id="5debe-112">The following illustration shows the matrices involved in the transformation.</span></span>  
  
 <span data-ttu-id="5debe-113">![Transformações](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.gif "AboutGdip05_art14")</span><span class="sxs-lookup"><span data-stu-id="5debe-113">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.gif "AboutGdip05_art14")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5debe-114">No exemplo anterior, a elipse é girada sobre a origem do sistema de coordenadas, que está localizado no canto superior esquerdo da área de cliente.</span><span class="sxs-lookup"><span data-stu-id="5debe-114">In the preceding example, the ellipse is rotated about the origin of the coordinate system, which is at the upper-left corner of the client area.</span></span> <span data-ttu-id="5debe-115">Isso produz um resultado diferente de girar a elipse sobre seu próprio centro.</span><span class="sxs-lookup"><span data-stu-id="5debe-115">This produces a different result than rotating the ellipse about its own center.</span></span>  
  
## <a name="local-transformations"></a><span data-ttu-id="5debe-116">Transformações locais</span><span class="sxs-lookup"><span data-stu-id="5debe-116">Local Transformations</span></span>  
 <span data-ttu-id="5debe-117">Uma transformação local aplica-se a um item específico a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="5debe-117">A local transformation applies to a specific item to be drawn.</span></span> <span data-ttu-id="5debe-118">Por exemplo, um <xref:System.Drawing.Drawing2D.GraphicsPath> objeto tem um <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> método que permite transformar os pontos de dados desse caminho.</span><span class="sxs-lookup"><span data-stu-id="5debe-118">For example, a <xref:System.Drawing.Drawing2D.GraphicsPath> object has a <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> method that allows you to transform the data points of that path.</span></span> <span data-ttu-id="5debe-119">O exemplo a seguir desenha um retângulo sem transformação e um caminho com uma transformação de rotação.</span><span class="sxs-lookup"><span data-stu-id="5debe-119">The following example draws a rectangle with no transformation and a path with a rotation transformation.</span></span> <span data-ttu-id="5debe-120">(Suponha que não haja nenhuma transformação global.)</span><span class="sxs-lookup"><span data-stu-id="5debe-120">(Assume that there is no world transformation.)</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 <span data-ttu-id="5debe-121">Você pode combinar a transformação global com transformações locais para obter uma variedade de resultados.</span><span class="sxs-lookup"><span data-stu-id="5debe-121">You can combine the world transformation with local transformations to achieve a variety of results.</span></span> <span data-ttu-id="5debe-122">Por exemplo, você pode usar a transformação global para revisar o sistema de coordenadas e usar transformações locais para girar e dimensionar objetos desenhados no novo sistema de coordenadas.</span><span class="sxs-lookup"><span data-stu-id="5debe-122">For example, you can use the world transformation to revise the coordinate system and use local transformations to rotate and scale objects drawn on the new coordinate system.</span></span>  
  
 <span data-ttu-id="5debe-123">Suponha que você deseje obter um sistema de coordenadas que tenha sua origem 200 pixels da borda esquerda da área de cliente e 150 pixels da parte superior da área de cliente.</span><span class="sxs-lookup"><span data-stu-id="5debe-123">Suppose you want a coordinate system that has its origin 200 pixels from the left edge of the client area and 150 pixels from the top of the client area.</span></span> <span data-ttu-id="5debe-124">Além disso, suponha que você deseje que a unidade de medida seja o pixel, com o eixo x apontando para a direita e o eixo y apontando para cima.</span><span class="sxs-lookup"><span data-stu-id="5debe-124">Furthermore, assume that you want the unit of measure to be the pixel, with the x-axis pointing to the right and the y-axis pointing up.</span></span> <span data-ttu-id="5debe-125">O sistema de coordenadas padrão tem o eixo y apontando para baixo, assim, você precisa executar uma reflexão no eixo horizontal.</span><span class="sxs-lookup"><span data-stu-id="5debe-125">The default coordinate system has the y-axis pointing down, so you need to perform a reflection across the horizontal axis.</span></span> <span data-ttu-id="5debe-126">A ilustração a seguir mostra a matriz de uma reflexão assim.</span><span class="sxs-lookup"><span data-stu-id="5debe-126">The following illustration shows the matrix of such a reflection.</span></span>  
  
 <span data-ttu-id="5debe-127">![Transformações](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.gif "AboutGdip05_art15")</span><span class="sxs-lookup"><span data-stu-id="5debe-127">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.gif "AboutGdip05_art15")</span></span>  
  
 <span data-ttu-id="5debe-128">Em seguida, suponha que você precisa executar uma translação de 200 unidades para a direita e 150 unidades para baixo.</span><span class="sxs-lookup"><span data-stu-id="5debe-128">Next, assume you need to perform a translation 200 units to the right and 150 units down.</span></span>  
  
 <span data-ttu-id="5debe-129">O exemplo a seguir estabelece o sistema de coordenadas que acabamos de descrever, definindo a transformação global de um <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="5debe-129">The following example establishes the coordinate system just described by setting the world transformation of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 <span data-ttu-id="5debe-130">O código a seguir (colocado no final do exemplo anterior) cria um caminho que consiste em um único retângulo com seu canto inferior esquerdo na origem do novo sistema de coordenadas.</span><span class="sxs-lookup"><span data-stu-id="5debe-130">The following code (placed at the end of the preceding example) creates a path that consists of a single rectangle with its lower-left corner at the origin of the new coordinate system.</span></span> <span data-ttu-id="5debe-131">O retângulo é preenchido uma vez sem transformação local e uma vez com transformação local.</span><span class="sxs-lookup"><span data-stu-id="5debe-131">The rectangle is filled once with no local transformation and once with a local transformation.</span></span> <span data-ttu-id="5debe-132">A transformação local consiste em uma colocação em escala horizontal por um fator de 2 seguida por uma rotação de 30 graus.</span><span class="sxs-lookup"><span data-stu-id="5debe-132">The local transformation consists of a horizontal scaling by a factor of 2 followed by a 30-degree rotation.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 <span data-ttu-id="5debe-133">A ilustração a seguir mostra o novo sistema de coordenadas e os dois retângulos.</span><span class="sxs-lookup"><span data-stu-id="5debe-133">The following illustration shows the new coordinate system and the two rectangles.</span></span>  
  
 <span data-ttu-id="5debe-134">![Transformações](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.gif "AboutGdip05_art16")</span><span class="sxs-lookup"><span data-stu-id="5debe-134">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.gif "AboutGdip05_art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5debe-135">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5debe-135">See Also</span></span>  
 [<span data-ttu-id="5debe-136">Sistemas de Coordenadas e Transformações</span><span class="sxs-lookup"><span data-stu-id="5debe-136">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [<span data-ttu-id="5debe-137">Usando Transformações no GDI+ Gerenciado</span><span class="sxs-lookup"><span data-stu-id="5debe-137">Using Transformations in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)