---
title: Usando a atividade de InvokeMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6643550-d043-4ac7-8069-9c55ebbb4233
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5dd488a01e00af0661ee7ee110c79d2c56a0b777
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-invokemethod-activity"></a><span data-ttu-id="2fb67-102">Usando a atividade de InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="2fb67-102">Using the InvokeMethod Activity</span></span>
<span data-ttu-id="2fb67-103">Este exemplo demonstra como usar o <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) atividade invocar métodos públicos em classes públicas.</span><span class="sxs-lookup"><span data-stu-id="2fb67-103">This sample demonstrates how to use the <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity to invoke public methods in public classes.</span></span> <span data-ttu-id="2fb67-104">O <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) atividade permite que um fluxo de trabalho chamar métodos em objetos, passar parâmetros, obter o valor de retorno, especificar tipos de métodos genéricos e especificar se o método é síncrono ou assíncrono.</span><span class="sxs-lookup"><span data-stu-id="2fb67-104">The <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity allows a workflow to call methods against objects, pass in parameters, get the return value, specify types for generic methods, and specify whether the method is synchronous or asynchronous.</span></span> 
  
 <span data-ttu-id="2fb67-105">Há uma versão não genérica do <xref:System.Activities.Statements.InvokeMethod> atividade em que o valor de retorno é definido como o <xref:System.Activities.Statements.InvokeMethod.Result%2A> propriedade e uma versão genérica do <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) em que o valor de retorno é retornado de atividade por meio de <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> --> [ <code>System.Activities.Statements.InvokeMethod\`1.Result</code> ](https://msdn.microsoft.com/library/dd987724.aspx) propriedade do tipo `TResult`.</span><span class="sxs-lookup"><span data-stu-id="2fb67-105">There is a non-generic version of the <xref:System.Activities.Statements.InvokeMethod> activity where the return value is set to the <xref:System.Activities.Statements.InvokeMethod.Result%2A> property and a generic version of the <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity where the return value is returned through the <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> -->[<code>System.Activities.Statements.InvokeMethod\`1.Result</code>](https://msdn.microsoft.com/library/dd987724.aspx) property of type `TResult`.</span></span>  
  
 <span data-ttu-id="2fb67-106">Este exemplo demonstra como chamar vários tipos de método.</span><span class="sxs-lookup"><span data-stu-id="2fb67-106">This sample demonstrates how to call various method types.</span></span> <span data-ttu-id="2fb67-107">A lista a seguir detalha os tipos de método demonstrado no exemplo:</span><span class="sxs-lookup"><span data-stu-id="2fb67-107">The following list details the method types demonstrated in this sample:</span></span>  
  
-   <span data-ttu-id="2fb67-108">Chamar um método de instância sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="2fb67-108">Invoke an instance method without parameters.</span></span>  
  
-   <span data-ttu-id="2fb67-109">Chamar um método de instância com dois parâmetros (System.String e System.Int32).</span><span class="sxs-lookup"><span data-stu-id="2fb67-109">Invoke an instance method with two parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="2fb67-110">Chamar um método de instância com dois parâmetros (System.String e System.Int32) e uma matriz de parâmetros de tipo System.String [].</span><span class="sxs-lookup"><span data-stu-id="2fb67-110">Invoke an instance method with two parameters (System.String and System.Int32) and a parameter array of type System.String[].</span></span>  
  
-   <span data-ttu-id="2fb67-111">Chamar um método de instância com dois parâmetros (dois números System.Int32) e resultado do tipo System.Int32.</span><span class="sxs-lookup"><span data-stu-id="2fb67-111">Invoke an instance method with two parameters (two System.Int32 numbers) and a result of type System.Int32.</span></span>  
  
     <span data-ttu-id="2fb67-112">O valor de retorno é associado a uma variável e impresso no console usando a atividade de <xref:System.Activities.Statements.WriteLine> .</span><span class="sxs-lookup"><span data-stu-id="2fb67-112">The return value is bound to a variable and printed to the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
-   <span data-ttu-id="2fb67-113">Chamar um método estático com dois parâmetros (System.String e System.Int32).</span><span class="sxs-lookup"><span data-stu-id="2fb67-113">Invoke a static method with two parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="2fb67-114">Chamar um método de instância com um parâmetro genérico (System.String).</span><span class="sxs-lookup"><span data-stu-id="2fb67-114">Invoke an instance method with one generic parameter (System.String).</span></span>  
  
-   <span data-ttu-id="2fb67-115">Chamar um método estático com dois parâmetros genéricos (System.String e System.Int32).</span><span class="sxs-lookup"><span data-stu-id="2fb67-115">Invoke a static method with two generic parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="2fb67-116">Chamar um método de instância que tem um parâmetro passado por referência (System.String).</span><span class="sxs-lookup"><span data-stu-id="2fb67-116">Invoke an instance method that has one parameter passed by reference (System.String).</span></span>  
  
     <span data-ttu-id="2fb67-117">O parâmetro referenciado é associado a uma variável e impresso no console usando a atividade de <xref:System.Activities.Statements.WriteLine> .</span><span class="sxs-lookup"><span data-stu-id="2fb67-117">The referenced parameter is bound to a variable and printed to the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
-   <span data-ttu-id="2fb67-118">Chamar um método de instância assíncrono.</span><span class="sxs-lookup"><span data-stu-id="2fb67-118">Invoke an asynchronous instance method.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="2fb67-119">Para usar este exemplo</span><span class="sxs-lookup"><span data-stu-id="2fb67-119">To use this sample</span></span>  
  
1.  <span data-ttu-id="2fb67-120">Usando [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra o arquivo de solução de InvokeMethodUsage.sln.</span><span class="sxs-lookup"><span data-stu-id="2fb67-120">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file.</span></span>  
  
2.  <span data-ttu-id="2fb67-121">Para criar a solução, pressione CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="2fb67-121">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="2fb67-122">Para executar a solução, pressione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="2fb67-122">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2fb67-123">Os exemplos podem já estar instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="2fb67-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2fb67-124">Verifique o seguinte diretório (padrão) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="2fb67-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2fb67-125">Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos.</span><span class="sxs-lookup"><span data-stu-id="2fb67-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2fb67-126">Este exemplo está localizado no seguinte diretório.</span><span class="sxs-lookup"><span data-stu-id="2fb67-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`  
  
## <a name="see-also"></a><span data-ttu-id="2fb67-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2fb67-127">See Also</span></span>