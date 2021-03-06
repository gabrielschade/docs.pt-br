---
title: Codificação e globalização de formulários do Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], lack of Unicode support
- DateTimePicker control [Windows Forms], lack of Unicode support
- TrackBar control [Windows Forms], lack of Unicode support
- ImageList component [Windows Forms], lack of Unicode support
- Unicode [Windows Forms]
- ToolBar control [Windows Forms], lack of Unicode support
- international applications [Windows Forms], character display
- StatusBar control [Windows Forms], lack of Unicode support
- MonthCalendar control [Windows Forms], lack of Unicode support
- international characters
- TabControl control [Windows Forms], lack of Unicode support
- Windows Forms, encoding
- TreeView control [Windows Forms], lack of Unicode support
- ProgressBar control [Windows Forms], Unicode-enabled forms
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: 22e8965d-a712-42b3-8167-3ee346bd70f9
ms.openlocfilehash: 9257a6b725839d8f433988ab76c4ce9ae349d950
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208540"
---
# <a name="encoding-and-windows-forms-globalization"></a>Codificação e globalização de formulários do Windows Forms
Aplicativos dos Windows Forms são totalmente habilitados para Unicode, o que significa que cada caractere é representado por um número exclusivo, independente da plataforma, programa ou linguagem. Para obter mais informações sobre Unicode, consulte o [site da Unicode Consortium](http://www.unicode.org).  
  
## <a name="benefits-of-unicode"></a>Benefícios do Unicode  
 Os benefícios de formulários habilitados para Unicode incluem a capacidade de trabalhar com scripts voltados apenas para Unicode, como Hindi. Além disso, é possível usar vários idiomas em um único formulário. Em Unicode, todos os caracteres têm dois bytes, portanto nenhum esforço especial é necessário para representar caracteres de byte duplo. Também é possível escrever um único conjunto de códigos que funcionará em todas as plataformas. Essa é uma alteração de versões anteriores do Visual Basic, você precisava escrever código diferente para diferentes plataformas, como Windows NT e [!INCLUDE[win98](../../../../includes/win98-md.md)].  
  
 No entanto, certos controles não dão suporte a Unicode no [!INCLUDE[win98](../../../../includes/win98-md.md)] e Windows Millennium Edition. Esses controles, todos com herança do controle comum, processarão dados com as páginas de código do Windows, como [!INCLUDE[vcpransi](../../../../includes/vcpransi-md.md)]. Esses controles estão: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar>, e <xref:System.Windows.Forms.StatusBar>. Como resultado, não é possível exibir dados Unicode nesses controles nas plataformas listadas. Por exemplo, não é possível exibir caracteres em japonês em um em sistema operacional [!INCLUDE[win98](../../../../includes/win98-md.md)] em inglês.  
  
 Para alternativas cientes do Unicode para a <xref:System.Windows.Forms.ToolBar> e <xref:System.Windows.Forms.StatusBar> controles, use o <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.StatusStrip> controles, que substituem estes controles mais antigos. Para manter uma aparência semelhante entre elementos visuais em seu aplicativo, use o <xref:System.Windows.Forms.MenuStrip> controle menus de renderização, em vez de <xref:System.Windows.Forms.MainMenu>. Como <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.StatusStrip>, <xref:System.Windows.Forms.MenuStrip> também pode processar e exibir os caracteres Unicode.  
  
## <a name="see-also"></a>Consulte também

[Globalizando aplicativos do Windows Forms](globalizing-windows-forms.md)
