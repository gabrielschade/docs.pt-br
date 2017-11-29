---
title: "Como desabilitar páginas de guia"
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
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 20674a93459f42a793ddf5f7ee5dffb1fa122d0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="d5f39-102">Como desabilitar páginas de guia</span><span class="sxs-lookup"><span data-stu-id="d5f39-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="d5f39-103">Em algumas ocasiões, pode ser útil restringir o acesso aos dados que estão disponíveis no seu Aplicativo do Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d5f39-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="d5f39-104">Um exemplo disso seria quando você tem dados exibidos nas páginas da guia de um controle guia. Os administradores poderiam ter informações em uma página da guia que você gostaria de proibir para convidados ou usuários de nível inferior.</span><span class="sxs-lookup"><span data-stu-id="d5f39-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="d5f39-105">Desabilitar páginas de guia com programação</span><span class="sxs-lookup"><span data-stu-id="d5f39-105">To disable tab pages programmatically</span></span>  
  
1.  <span data-ttu-id="d5f39-106">Escrever código para manipular o controle de guia <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> eventos.</span><span class="sxs-lookup"><span data-stu-id="d5f39-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="d5f39-107">Esse é o evento que é gerado quando o usuário alterna de uma guia para a próxima.</span><span class="sxs-lookup"><span data-stu-id="d5f39-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2.  <span data-ttu-id="d5f39-108">Verifique as credenciais.</span><span class="sxs-lookup"><span data-stu-id="d5f39-108">Check credentials.</span></span> <span data-ttu-id="d5f39-109">Dependendo das informações apresentadas, pode ser útil verificar o nome de usuário com que o usuário fez logon ou alguma outra credencial antes de permitir que o usuário exiba a guia.</span><span class="sxs-lookup"><span data-stu-id="d5f39-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3.  <span data-ttu-id="d5f39-110">Se o usuário tiver as credenciais apropriadas, exiba a guia que foi clicada.</span><span class="sxs-lookup"><span data-stu-id="d5f39-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="d5f39-111">Se o usuário não tiver as credenciais apropriadas, exibirá uma caixa de mensagem ou alguma outra interface do usuário indicando que eles não têm acesso e retorne à guia inicial.</span><span class="sxs-lookup"><span data-stu-id="d5f39-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5f39-112">Quando você implementa essa funcionalidade em seus aplicativos de produção, você pode executar essa verificação de credencial durante o formulário <xref:System.Windows.Forms.Form.Load> eventos.</span><span class="sxs-lookup"><span data-stu-id="d5f39-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="d5f39-113">Isso permitirá que você oculte a guia antes de exibir qualquer interface do usuário, que é uma abordagem muito mais simples do que programação.</span><span class="sxs-lookup"><span data-stu-id="d5f39-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="d5f39-114">A metodologia usada abaixo (verificar as credenciais e desabilitando a guia durante o <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento) é para fins ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="d5f39-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4.  <span data-ttu-id="d5f39-115">Opcionalmente, se você tiver mais de duas páginas da guia, exiba uma página da guia diferente da original.</span><span class="sxs-lookup"><span data-stu-id="d5f39-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="d5f39-116">No exemplo a seguir, um <xref:System.Windows.Forms.CheckBox> controle é usado em vez de verificar as credenciais, como os critérios para o acesso à guia variam de acordo com o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d5f39-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="d5f39-117">Quando o <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento é gerado se a verificação de credencial for true (ou seja, a caixa de seleção estiver marcada) e a guia selecionada é `TabPage2` (guia com as informações confidenciais, neste exemplo), em seguida, `TabPage2` é exibido.</span><span class="sxs-lookup"><span data-stu-id="d5f39-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="d5f39-118">Caso contrário, `TabPage3` será exibido e uma caixa de mensagem será exibida para o usuário, indicando que ele não tem os privilégios de acesso apropriados.</span><span class="sxs-lookup"><span data-stu-id="d5f39-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="d5f39-119">O código a seguir supõe que um formulário com um <xref:System.Windows.Forms.CheckBox> controle (`CredentialCheck`) e um <xref:System.Windows.Forms.TabControl> controle com três guias.</span><span class="sxs-lookup"><span data-stu-id="d5f39-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
    ```vb  
    Private Sub TabControl1_SelectedIndexChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles TabControl1.SelectedIndexChanged  
       ' Check Credentials Here  
  
       If CredentialCheck.Checked = True And _   
       TabControl1.SelectedTab Is TabPage2 Then  
          TabControl1.SelectedTab = TabPage2  
       ElseIf CredentialCheck.Checked = False _   
       And TabControl1.SelectedTab Is TabPage2 Then  
          MessageBox.Show _   
         ("Unable to load tab. You have insufficient access privileges.")  
          TabControl1.SelectedTab = TabPage3  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void tabControl1_SelectedIndexChanged(object sender, System.EventArgs e)  
    {  
        // Check Credentials Here  
  
        if ((CredentialCheck.Checked == true) && (tabControl1.SelectedTab == tabPage2))   
        {  
            tabControl1.SelectedTab = tabPage2;  
        }  
        else if ((CredentialCheck.Checked == false) && (tabControl1.SelectedTab == tabPage2))  
        {  
            MessageBox.Show("Unable to load tab. You have insufficient access privileges.");  
            tabControl1.SelectedTab = tabPage3;  
        }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void tabControl1_SelectedIndexChanged(  
          System::Object ^ sender,  
          System::EventArgs ^  e)  
       {  
          // Check Credentials Here  
          if ((CredentialCheck->Checked == true) &&  
              (tabControl1->SelectedTab == tabPage2))  
          {  
             tabControl1->SelectedTab = tabPage2;  
          }  
          else if ((CredentialCheck->Checked == false) &&  
                   (tabControl1->SelectedTab == tabPage2))  
          {  
             MessageBox::Show(String::Concat("Unable to load tab. ",  
                "You have insufficient access privileges."));  
             tabControl1->SelectedTab = tabPage3;  
          }  
       }  
    ```  
  
     <span data-ttu-id="d5f39-120">(Visual C#, Visual C++) Coloque o seguinte código no construtor do formulário para registrar o manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="d5f39-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d5f39-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d5f39-121">See Also</span></span>  
 [<span data-ttu-id="d5f39-122">Visão geral do controle TabControl</span><span class="sxs-lookup"><span data-stu-id="d5f39-122">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="d5f39-123">Como adicionar um controle a uma página da guia</span><span class="sxs-lookup"><span data-stu-id="d5f39-123">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="d5f39-124">Como adicionar e remover guias com o TabControl dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5f39-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="d5f39-125">Como alterar a aparência do TabControl dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5f39-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)