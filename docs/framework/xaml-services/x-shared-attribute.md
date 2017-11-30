---
title: Atributo x:Shared
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
caps.latest.revision: "16"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: d6a9333b2267e82fc25b2a0ec4bf5dd14f644078
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="xshared-attribute"></a><span data-ttu-id="49801-102">Atributo x:Shared</span><span class="sxs-lookup"><span data-stu-id="49801-102">x:Shared Attribute</span></span>
<span data-ttu-id="49801-103">Quando definido como `false`, modifica o comportamento de recuperação de recursos do WPF para que as solicitações para o recurso atribuído criam uma nova instância para cada solicitação, em vez de compartilhar a mesma instância para todas as solicitações.</span><span class="sxs-lookup"><span data-stu-id="49801-103">When set to `false`, modifies WPF resource-retrieval behavior so that requests for the attributed resource create a new instance for each request instead of sharing the same instance for all requests.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="49801-104">Uso do Atributo XAML</span><span class="sxs-lookup"><span data-stu-id="49801-104">XAML Attribute Usage</span></span>  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a><span data-ttu-id="49801-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="49801-105">Remarks</span></span>  
 <span data-ttu-id="49801-106">`x:Shared`é mapeado para o namespace XAML de linguagem XAML e é reconhecido como um elemento de linguagem XAML válido por serviços XAML do .NET Framework e seus leitores XAML.</span><span class="sxs-lookup"><span data-stu-id="49801-106">`x:Shared` is mapped to the XAML language XAML namespace and is recognized as a valid XAML language element by .NET Framework XAML Services and its XAML readers.</span></span> <span data-ttu-id="49801-107">No entanto, os recursos declarados de `x:Shared` só são relevantes para aplicativos do WPF e para o analisador de WPF XAML.</span><span class="sxs-lookup"><span data-stu-id="49801-107">However, the stated capabilities of `x:Shared` are only relevant for WPF applications and for the WPF XAML parser.</span></span> <span data-ttu-id="49801-108">No WPF, `x:Shared` só é útil como um atributo quando ele é aplicado a um objeto que existe dentro de um WPF <xref:System.Windows.ResourceDictionary>.</span><span class="sxs-lookup"><span data-stu-id="49801-108">In WPF, `x:Shared` is only useful as an attribute when it is applied to an object that exists within a WPF <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="49801-109">Outros usos não emitem exceções de análise ou outros erros, mas eles não têm nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="49801-109">Other usages do not throw parse exceptions or other errors, but they have no effect.</span></span>  
  
 <span data-ttu-id="49801-110">O significado de `x:Shared` não for especificado na especificação de linguagem XAML.</span><span class="sxs-lookup"><span data-stu-id="49801-110">The meaning of `x:Shared` is not specified in the XAML language specification.</span></span> <span data-ttu-id="49801-111">Outras implementações de XAML, como aqueles com base nos serviços de XAML do .NET Framework, não necessariamente oferecem suporte de compartilhamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="49801-111">Other XAML implementations, such as those that build on .NET Framework XAML Services, do not necessarily provide resource-sharing support.</span></span> <span data-ttu-id="49801-112">Tais implementações de XAML podem fornecer um comportamento semelhante na estrutura de suporte que também usado `x:Shared` valores.</span><span class="sxs-lookup"><span data-stu-id="49801-112">Such XAML implementations could provide similar behavior in the supporting framework that also used `x:Shared` values.</span></span>  
  
 <span data-ttu-id="49801-113">No WPF, o padrão `x:Shared` condição de recursos é `true`.</span><span class="sxs-lookup"><span data-stu-id="49801-113">In WPF, the default `x:Shared` condition for resources is `true`.</span></span> <span data-ttu-id="49801-114">Esta condição significa que qualquer solicitação de determinado recurso sempre retorna a mesma instância.</span><span class="sxs-lookup"><span data-stu-id="49801-114">This condition means that any given resource request always returns the same instance.</span></span>  
  
 <span data-ttu-id="49801-115">Modificando um objeto que é retornado por meio de um recurso de API, como <xref:System.Windows.FrameworkElement.FindResource%2A>, ou modificando um objeto diretamente em um <xref:System.Windows.ResourceDictionary>, modifica o recurso original.</span><span class="sxs-lookup"><span data-stu-id="49801-115">Modifying an object that is returned through a resource API, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, or modifying an object directly within a <xref:System.Windows.ResourceDictionary>, changes the original resource.</span></span> <span data-ttu-id="49801-116">Se as referências a esse recurso referências a recursos dinâmicos, os consumidores do recurso ter alterado do recurso.</span><span class="sxs-lookup"><span data-stu-id="49801-116">If references to that resource were dynamic resource references, the consumers of that resource get the changed resource.</span></span>  
  
 <span data-ttu-id="49801-117">Se a referência ao recurso fosse estática, mudanças no recurso após [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] tempo de processamento são irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="49801-117">If references to the resource were static resource references, changes to the resource after [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing time are irrelevant.</span></span> <span data-ttu-id="49801-118">Para obter mais informações sobre estática em vez de referências a recursos dinâmicos, consulte [recursos XAML](../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="49801-118">For more information about static versus dynamic resource references, see [XAML Resources](../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 <span data-ttu-id="49801-119">Especificando explicitamente `x:Shared="true"` raramente é feita, pois já é o padrão.</span><span class="sxs-lookup"><span data-stu-id="49801-119">Explicitly specifying `x:Shared="true"` is rarely done, because that is already the default.</span></span> <span data-ttu-id="49801-120">Não há nenhum código direto equivalente para `x:Shared` modelo de objeto no WPF; ele só pode ser especificado no uso de XAML e deve ser processado pelo comportamento padrão do WPF ou em um fluxo do nó XAML intermediário no caminho de carga se processado usando o .NET Framework XAML Se rvices e seus leitores XAML.</span><span class="sxs-lookup"><span data-stu-id="49801-120">There is no direct code equivalent for `x:Shared` in the WPF object model; it can only be specified in a XAML usage and must be processed either by the default WPF behavior or in an intermediate XAML node stream on the load path if processed using .NET Framework XAML Services and its XAML readers.</span></span>  
  
 <span data-ttu-id="49801-121">Um cenário para `x:Shared="false"` é se você definir um <xref:System.Windows.FrameworkElement> ou <xref:System.Windows.FrameworkContentElement> derivado da classe como um recurso e, em seguida, você introduzir o recurso de elemento em um modelo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="49801-121">A scenario for `x:Shared="false"` is if you define a <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> derived class as a resource and then you introduce the element resource into a content model.</span></span> <span data-ttu-id="49801-122">`x:Shared="false"`permite que um recurso de elemento ser introduzido várias vezes na mesma coleção (como um <xref:System.Windows.Controls.UIElementCollection>).</span><span class="sxs-lookup"><span data-stu-id="49801-122">`x:Shared="false"` enables an element resource to be introduced multiple times in the same collection (such as a <xref:System.Windows.Controls.UIElementCollection>).</span></span> <span data-ttu-id="49801-123">Sem `x:Shared="false"` isso é inválido porque a coleção impõe a exclusividade de seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="49801-123">Without `x:Shared="false"` this is invalid because the collection enforces uniqueness of its contents.</span></span> <span data-ttu-id="49801-124">No entanto, o `x:Shared="false"` comportamento cria outra instância idêntica do recurso em vez de retornar a mesma instância.</span><span class="sxs-lookup"><span data-stu-id="49801-124">However, the `x:Shared="false"` behavior creates another identical instance of the resource instead of returning the same instance.</span></span>  
  
 <span data-ttu-id="49801-125">Outro cenário para `x:Shared="false"` é se você usar um <xref:System.Windows.Freezable> recursos para valores de animação, mas você deseja modificar o recurso em uma base por animação.</span><span class="sxs-lookup"><span data-stu-id="49801-125">Another scenario for `x:Shared="false"` is if you use a <xref:System.Windows.Freezable> resource for animation values but want to modify the resource on a per animation basis.</span></span>  
  
 <span data-ttu-id="49801-126">A manipulação de cadeia de caracteres de `false` não diferencia maiusculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="49801-126">The string handling of `false` is not case sensitive.</span></span>  
  
 <span data-ttu-id="49801-127">No WPF, `x:Shared` só é válida nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="49801-127">In WPF, `x:Shared` is only valid under the following conditions:</span></span>  
  
-   <span data-ttu-id="49801-128">O <xref:System.Windows.ResourceDictionary> que contém os itens com `x:Shared` devem ser compiladas.</span><span class="sxs-lookup"><span data-stu-id="49801-128">The <xref:System.Windows.ResourceDictionary> that contains the items with `x:Shared` must be compiled.</span></span> <span data-ttu-id="49801-129">O <xref:System.Windows.ResourceDictionary> não pode estar em XAML flexível ou usado para temas.</span><span class="sxs-lookup"><span data-stu-id="49801-129">The <xref:System.Windows.ResourceDictionary> cannot be within loose XAML or used for themes.</span></span>  
  
-   <span data-ttu-id="49801-130">O <xref:System.Windows.ResourceDictionary> que contém os itens não podem ser aninhados dentro de outra <xref:System.Windows.ResourceDictionary>.</span><span class="sxs-lookup"><span data-stu-id="49801-130">The <xref:System.Windows.ResourceDictionary> that contains the items must not be nested within another <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="49801-131">Por exemplo, você não pode usar `x:Shared` para itens em uma <xref:System.Windows.ResourceDictionary> que está dentro um <xref:System.Windows.Style> que já é um <xref:System.Windows.ResourceDictionary> item.</span><span class="sxs-lookup"><span data-stu-id="49801-131">For example, you cannot use `x:Shared` for items in a <xref:System.Windows.ResourceDictionary> that is within a <xref:System.Windows.Style> that is already a <xref:System.Windows.ResourceDictionary> item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49801-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="49801-132">See Also</span></span>  
 <xref:System.Windows.ResourceDictionary>  
 [<span data-ttu-id="49801-133">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="49801-133">XAML Resources</span></span>](../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="49801-134">Elementos base</span><span class="sxs-lookup"><span data-stu-id="49801-134">Base Elements</span></span>](../../../docs/framework/wpf/advanced/base-elements.md)