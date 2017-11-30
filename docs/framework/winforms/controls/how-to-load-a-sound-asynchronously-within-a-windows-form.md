---
title: "Como carregar um som de forma assíncrona dentro de um Windows Form"
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
- SoundPlayer class [Windows Forms], loading sounds asynchronously
- sounds [Windows Forms], loading on separate threads
- threading [Windows Forms], sounds
ms.assetid: 3b6a9296-1d5e-4d52-a4ba-94366d6fe302
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d4ff6670c8e4d8ab735323fe13549e34c6cfd55f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-a-sound-asynchronously-within-a-windows-form"></a><span data-ttu-id="2bbcc-102">Como carregar um som de forma assíncrona dentro de um Windows Form</span><span class="sxs-lookup"><span data-stu-id="2bbcc-102">How to: Load a Sound Asynchronously within a Windows Form</span></span>
<span data-ttu-id="2bbcc-103">O exemplo de código a seguir carrega assincronamente um som de uma URL e é reproduzido em um novo thread.</span><span class="sxs-lookup"><span data-stu-id="2bbcc-103">The following code example asynchronously loads a sound from an URL and then plays it on a new thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bbcc-104">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2bbcc-104">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2bbcc-105">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="2bbcc-105">Compiling the Code</span></span>  
 <span data-ttu-id="2bbcc-106">Este exemplo requer:</span><span class="sxs-lookup"><span data-stu-id="2bbcc-106">This example requires:</span></span>  
  
-   <span data-ttu-id="2bbcc-107">Referências aos assemblies Sistema e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="2bbcc-107">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="2bbcc-108">Se você substituir o nome de arquivo `"http://www.tailspintoys.com/sounds/stop.wav"` com um nome de arquivo válido.</span><span class="sxs-lookup"><span data-stu-id="2bbcc-108">That you replace the file name `"http://www.tailspintoys.com/sounds/stop.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="2bbcc-109">Para obter informações sobre como criar este exemplo da linha de comando para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] ou [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) (Compilação da linha de comando) ou [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) (Compilação da linha de comando com csc.exe).</span><span class="sxs-lookup"><span data-stu-id="2bbcc-109">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="2bbcc-110">Também é possível compilar este exemplo em [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] colando o código em um novo projeto.</span><span class="sxs-lookup"><span data-stu-id="2bbcc-110">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="2bbcc-111">Consulte também [Como compilar e executar um exemplo completo de código do Windows Forms usando o Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="2bbcc-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="2bbcc-112">Programação robusta</span><span class="sxs-lookup"><span data-stu-id="2bbcc-112">Robust Programming</span></span>  
 <span data-ttu-id="2bbcc-113">Operações de arquivo devem ser incluídas dentro de blocos de tratamento de exceção apropriados.</span><span class="sxs-lookup"><span data-stu-id="2bbcc-113">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="2bbcc-114">As seguintes condições podem causar uma exceção:</span><span class="sxs-lookup"><span data-stu-id="2bbcc-114">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="2bbcc-115">O nome do caminho está malformado.</span><span class="sxs-lookup"><span data-stu-id="2bbcc-115">The path name is malformed.</span></span> <span data-ttu-id="2bbcc-116">Por exemplo, ele contém caracteres que não são válidos ou apenas espaços em branco (<xref:System.ArgumentException> classe).</span><span class="sxs-lookup"><span data-stu-id="2bbcc-116">For example, it contains characters that are not valid or is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="2bbcc-117">O caminho é somente leitura (<xref:System.IO.IOException> classe).</span><span class="sxs-lookup"><span data-stu-id="2bbcc-117">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="2bbcc-118">O nome do caminho é `Nothing` (<xref:System.ArgumentNullException> classe).</span><span class="sxs-lookup"><span data-stu-id="2bbcc-118">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="2bbcc-119">O nome do caminho é muito longo (<xref:System.IO.PathTooLongException> classe).</span><span class="sxs-lookup"><span data-stu-id="2bbcc-119">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="2bbcc-120">O caminho não é válido (<xref:System.IO.DirectoryNotFoundException> classe).</span><span class="sxs-lookup"><span data-stu-id="2bbcc-120">The path is not valid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="2bbcc-121">O caminho é apenas um dois-pontos ":" (<xref:System.NotSupportedException> classe).</span><span class="sxs-lookup"><span data-stu-id="2bbcc-121">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2bbcc-122">Segurança do .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2bbcc-122">.NET Framework Security</span></span>  
 <span data-ttu-id="2bbcc-123">Não tome decisões sobre o conteúdo do arquivo com base no nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="2bbcc-123">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="2bbcc-124">Por exemplo, o arquivo `Form1.vb` não pode ser um arquivo de origem do Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2bbcc-124">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="2bbcc-125">Verifique todas as entradas antes de usar os dados no seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2bbcc-125">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bbcc-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2bbcc-126">See Also</span></span>  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <xref:System.Media.SoundPlayer.LoadCompleted>  
 <xref:System.Media.SoundPlayer.Play%2A>  
 [<span data-ttu-id="2bbcc-127">Como reproduzir um som de um Windows Form</span><span class="sxs-lookup"><span data-stu-id="2bbcc-127">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)