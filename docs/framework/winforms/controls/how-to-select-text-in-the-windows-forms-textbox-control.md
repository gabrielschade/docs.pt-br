---
title: Como selecionar texto no controle TextBox dos Windows Forms
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
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 08ad19f3daca43fb33e845b632ac7d92b00f544c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a><span data-ttu-id="1f1cd-102">Como selecionar texto no controle TextBox dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1f1cd-102">How to: Select Text in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="1f1cd-103">Você pode selecionar texto programaticamente no Windows Forms <xref:System.Windows.Forms.TextBox> controle.</span><span class="sxs-lookup"><span data-stu-id="1f1cd-103">You can select text programmatically in the Windows Forms <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="1f1cd-104">Por exemplo, se você criar uma função que pesquisa de texto de uma determinada cadeia de caracteres, poderá selecionar o texto para alertar visualmente o leitor da posição da cadeia de caracteres encontrada.</span><span class="sxs-lookup"><span data-stu-id="1f1cd-104">For example, if you create a function that searches text for a particular string, you can select the text to visually alert the reader of the found string's position.</span></span>  
  
### <a name="to-select-text-programmatically"></a><span data-ttu-id="1f1cd-105">Selecionar texto com programação</span><span class="sxs-lookup"><span data-stu-id="1f1cd-105">To select text programmatically</span></span>  
  
1.  <span data-ttu-id="1f1cd-106">Definir o <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> propriedade para o início do texto que você deseja selecionar.</span><span class="sxs-lookup"><span data-stu-id="1f1cd-106">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to the beginning of the text you want to select.</span></span>  
  
     <span data-ttu-id="1f1cd-107">O <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> é um número que indica o ponto de inserção na cadeia de caracteres de texto, com 0, sendo a posição mais à esquerda.</span><span class="sxs-lookup"><span data-stu-id="1f1cd-107">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is a number that indicates the insertion point within the string of text, with 0 being the left-most position.</span></span> <span data-ttu-id="1f1cd-108">Se o <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> propriedade é definida como um valor igual ou maior que o número de caracteres na caixa de texto, o ponto de inserção é posicionado após o último caractere.</span><span class="sxs-lookup"><span data-stu-id="1f1cd-108">If the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is set to a value equal to or greater than the number of characters in the text box, the insertion point is placed after the last character.</span></span>  
  
2.  <span data-ttu-id="1f1cd-109">Definir o <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> propriedade para o comprimento do texto que você deseja selecionar.</span><span class="sxs-lookup"><span data-stu-id="1f1cd-109">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="1f1cd-110">O <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> propriedade é um valor numérico que define a largura do ponto de inserção.</span><span class="sxs-lookup"><span data-stu-id="1f1cd-110">The <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property is a numeric value that sets the width of the insertion point.</span></span> <span data-ttu-id="1f1cd-111">Definindo o <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> para um número maior que 0 faz com que esse número de caracteres a ser selecionado, partindo do ponto de inserção atual.</span><span class="sxs-lookup"><span data-stu-id="1f1cd-111">Setting the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> to a number greater than 0 causes that number of characters to be selected, starting from the current insertion point.</span></span>  
  
3.  <span data-ttu-id="1f1cd-112">(Opcional) O texto selecionado por meio de acesso a <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="1f1cd-112">(Optional) Access the selected text through the <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> property.</span></span>  
  
     <span data-ttu-id="1f1cd-113">O código a seguir seleciona o conteúdo de um texto da caixa quando o controle <xref:System.Windows.Forms.Control.Enter> evento ocorre.</span><span class="sxs-lookup"><span data-stu-id="1f1cd-113">The code below selects the contents of a text box when the control's <xref:System.Windows.Forms.Control.Enter> event occurs.</span></span> <span data-ttu-id="1f1cd-114">Este exemplo verifica se a caixa de texto tem um valor para o <xref:System.Windows.Forms.TextBox.Text%2A> propriedade que não é `null` ou uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="1f1cd-114">This example checks if the text box has a value for the <xref:System.Windows.Forms.TextBox.Text%2A> property that is not `null` or an empty string.</span></span> <span data-ttu-id="1f1cd-115">Quando a caixa de texto recebe o foco, o texto presente nela é selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f1cd-115">When the text box receives the focus, the current text in the text box is selected.</span></span> <span data-ttu-id="1f1cd-116">O manipulador de eventos `TextBox1_Enter` deve ser associado ao controle; para obter mais informações, consulte [Como criar manipuladores de eventos no tempo de execução para Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="1f1cd-116">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="1f1cd-117">Para testar esse exemplo, pressione a tecla Tab até que a caixa de texto receber o foco.</span><span class="sxs-lookup"><span data-stu-id="1f1cd-117">To test this example, press the Tab key until the text box has the focus.</span></span> <span data-ttu-id="1f1cd-118">Se você clicar na caixa de texto, a seleção dele será cancelada.</span><span class="sxs-lookup"><span data-stu-id="1f1cd-118">If you click in the text box, the text is unselected.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1f1cd-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1f1cd-119">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="1f1cd-120">Visão geral do controle TextBox</span><span class="sxs-lookup"><span data-stu-id="1f1cd-120">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="1f1cd-121">Como controlar o ponto de inserção em um controle TextBox dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1f1cd-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="1f1cd-122">Como criar uma caixa de texto de senha com o controle TextBox dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1f1cd-122">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="1f1cd-123">Como criar uma caixa de texto somente leitura</span><span class="sxs-lookup"><span data-stu-id="1f1cd-123">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="1f1cd-124">Como inserir aspas em uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="1f1cd-124">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="1f1cd-125">Como exibir várias linhas no controle TextBox dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1f1cd-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="1f1cd-126">Controle TextBox</span><span class="sxs-lookup"><span data-stu-id="1f1cd-126">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)