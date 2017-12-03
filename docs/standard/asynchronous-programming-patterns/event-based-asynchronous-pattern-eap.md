---
title: "Padrão assíncrono baseado em evento (EAP)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b5f242b9586c4ea3b045daf8f10b84127b81085
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="event-based-asynchronous-pattern-eap"></a><span data-ttu-id="4bfd3-102">Padrão assíncrono baseado em evento (EAP)</span><span class="sxs-lookup"><span data-stu-id="4bfd3-102">Event-based Asynchronous Pattern (EAP)</span></span>
<span data-ttu-id="4bfd3-103">Há várias maneiras de expor recursos assíncronos para o código cliente.</span><span class="sxs-lookup"><span data-stu-id="4bfd3-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="4bfd3-104">O Padrão Assíncrono baseado em evento prescreve uma maneira de as classes apresentarem comportamento assíncrono.</span><span class="sxs-lookup"><span data-stu-id="4bfd3-104">The Event-based Asynchronous Pattern prescribes one way for classes to present asynchronous behavior.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4bfd3-105">Começando com o [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], a biblioteca paralela de tarefas fornece um novo modelo de programação assíncrona e paralela.</span><span class="sxs-lookup"><span data-stu-id="4bfd3-105">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the Task Parallel Library provides a new model for asynchronous and parallel programming.</span></span> <span data-ttu-id="4bfd3-106">Para obter mais informações, consulte [Programação paralela](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="4bfd3-106">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4bfd3-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="4bfd3-107">In This Section</span></span>  
 [<span data-ttu-id="4bfd3-108">Visão Geral do Padrão Assíncrono Baseado em Evento</span><span class="sxs-lookup"><span data-stu-id="4bfd3-108">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="4bfd3-109">Descreve como o Padrão Assíncrono Baseado em Evento disponibiliza as vantagens de aplicativos de vários threads enquanto oculta muitos problemas complexos inerentes ao design com vários threads.</span><span class="sxs-lookup"><span data-stu-id="4bfd3-109">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="4bfd3-110">Implementando o Padrão Assíncrono baseado em Evento</span><span class="sxs-lookup"><span data-stu-id="4bfd3-110">Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="4bfd3-111">Descreve a maneira padronizada de empacotar uma classe com recursos assíncronos.</span><span class="sxs-lookup"><span data-stu-id="4bfd3-111">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="4bfd3-112">Práticas recomendadas para a implementação do Padrão Assíncrono baseado em Evento</span><span class="sxs-lookup"><span data-stu-id="4bfd3-112">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="4bfd3-113">Descreve as exigências para expor recursos assíncronos de acordo com o Padrão Assíncrono Baseado em Evento.</span><span class="sxs-lookup"><span data-stu-id="4bfd3-113">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="4bfd3-114">Decidindo quando implementar o Padrão Assíncrono baseado em Evento</span><span class="sxs-lookup"><span data-stu-id="4bfd3-114">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="4bfd3-115">Descreve como determinar quando você deve escolher implementar o Padrão Assíncrono Baseado em Evento, em vez do padrão <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="4bfd3-115">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern.</span></span>  
  
 [<span data-ttu-id="4bfd3-116">Instruções passo a passo: implementando um componente compatível com o Padrão Assíncrono baseado em Evento</span><span class="sxs-lookup"><span data-stu-id="4bfd3-116">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="4bfd3-117">Ilustra como criar um componente que implemente o Padrão Assíncrono Baseado em Evento.</span><span class="sxs-lookup"><span data-stu-id="4bfd3-117">Illustrates how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="4bfd3-118">É implementado usando classes do auxiliar do namespace <xref:System.ComponentModel?displayProperty=nameWithType>, o que garante que o componente funcione corretamente em qualquer modelo de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4bfd3-118">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  
  
 [<span data-ttu-id="4bfd3-119">Como usar componentes compatíveis com o Padrão Assíncrono baseado em Evento</span><span class="sxs-lookup"><span data-stu-id="4bfd3-119">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="4bfd3-120">Descreve como usar um componente com suporte ao Padrão Assíncrono Baseado em Evento.</span><span class="sxs-lookup"><span data-stu-id="4bfd3-120">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4bfd3-121">Referência</span><span class="sxs-lookup"><span data-stu-id="4bfd3-121">Reference</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="4bfd3-122">Descreve a classe <xref:System.ComponentModel.AsyncOperation> e tem links a todos os seus membros.</span><span class="sxs-lookup"><span data-stu-id="4bfd3-122">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="4bfd3-123">Descreve a classe <xref:System.ComponentModel.AsyncOperationManager> e tem links a todos os seus membros.</span><span class="sxs-lookup"><span data-stu-id="4bfd3-123">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="4bfd3-124">Descreve o componente <xref:System.ComponentModel.BackgroundWorker> e tem links a todos os seus membros.</span><span class="sxs-lookup"><span data-stu-id="4bfd3-124">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4bfd3-125">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="4bfd3-125">Related Sections</span></span>  
 [<span data-ttu-id="4bfd3-126">TPL (Biblioteca de Paralelismo de Tarefas)</span><span class="sxs-lookup"><span data-stu-id="4bfd3-126">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="4bfd3-127">Descreve um modelo de programação para operações paralelas e assíncronas.</span><span class="sxs-lookup"><span data-stu-id="4bfd3-127">Describes a programming model for asynchronous and parallel operations.</span></span>  
  
 [<span data-ttu-id="4bfd3-128">Threading</span><span class="sxs-lookup"><span data-stu-id="4bfd3-128">Threading</span></span>](../../../docs/standard/threading/index.md)  
 <span data-ttu-id="4bfd3-129">Descreve recursos de multithreading no .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4bfd3-129">Describes multithreading features in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="4bfd3-130">Threading</span><span class="sxs-lookup"><span data-stu-id="4bfd3-130">Threading</span></span>](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)  
 <span data-ttu-id="4bfd3-131">Descreve recursos de multithreading nas linguagens C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4bfd3-131">Describes multithreading features in the C# and Visual Basic languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bfd3-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4bfd3-132">See Also</span></span>  
 [<span data-ttu-id="4bfd3-133">Práticas recomendadas de threading gerenciado</span><span class="sxs-lookup"><span data-stu-id="4bfd3-133">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [<span data-ttu-id="4bfd3-134">Eventos</span><span class="sxs-lookup"><span data-stu-id="4bfd3-134">Events</span></span>](../../../docs/standard/events/index.md)  
 [<span data-ttu-id="4bfd3-135">Multithreading em componentes</span><span class="sxs-lookup"><span data-stu-id="4bfd3-135">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [<span data-ttu-id="4bfd3-136">Padrões de Design de programação assíncrona</span><span class="sxs-lookup"><span data-stu-id="4bfd3-136">Asynchronous Programming Design Patterns</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)