---
title: Design de enum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b7e1686dca2b96e339917b6dd4861f0f43d20d66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="enum-design"></a><span data-ttu-id="595e4-102">Design de enum</span><span class="sxs-lookup"><span data-stu-id="595e4-102">Enum Design</span></span>
<span data-ttu-id="595e4-103">Enumerações são um tipo especial de tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="595e4-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="595e4-104">Há dois tipos de enums: enums enums e o sinalizador simples.</span><span class="sxs-lookup"><span data-stu-id="595e4-104">There are two kinds of enums: simple enums and flag enums.</span></span>  
  
 <span data-ttu-id="595e4-105">Enums simples representam pequenos conjuntos fechados de opções.</span><span class="sxs-lookup"><span data-stu-id="595e4-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="595e4-106">Um exemplo comum de enum simple é um conjunto de cores.</span><span class="sxs-lookup"><span data-stu-id="595e4-106">A common example of the simple enum is a set of colors.</span></span>  
  
 <span data-ttu-id="595e4-107">Enumerações de sinalizador são projetadas para dar suporte a operações bit a bit com os valores de enum.</span><span class="sxs-lookup"><span data-stu-id="595e4-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="595e4-108">Um exemplo comum de enum de sinalizadores é uma lista de opções.</span><span class="sxs-lookup"><span data-stu-id="595e4-108">A common example of the flags enum is a list of options.</span></span>  
  
 <span data-ttu-id="595e4-109">**FAZER ✓** usar uma enumeração para fortemente tipados parâmetros, propriedades e retornam valores que representam os conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="595e4-109">**✓ DO** use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>  
  
 <span data-ttu-id="595e4-110">**FAZER ✓** favorecer usando um enum em vez de constantes estáticas.</span><span class="sxs-lookup"><span data-stu-id="595e4-110">**✓ DO** favor using an enum instead of static constants.</span></span>  
  
 <span data-ttu-id="595e4-111">**X não** usar uma enumeração para abrir conjuntos (como a versão do sistema operacional, os nomes dos seus amigos, etc.).</span><span class="sxs-lookup"><span data-stu-id="595e4-111">**X DO NOT** use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>  
  
 <span data-ttu-id="595e4-112">**X não** fornecer valores de enum reservado que se destinam para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="595e4-112">**X DO NOT** provide reserved enum values that are intended for future use.</span></span>  
  
 <span data-ttu-id="595e4-113">Você sempre simplesmente pode adicionar valores para a enum existente em um estágio posterior.</span><span class="sxs-lookup"><span data-stu-id="595e4-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="595e4-114">Consulte [adicionar valores para enumerações](#add_value) para obter mais detalhes sobre como adicionar valores para enums.</span><span class="sxs-lookup"><span data-stu-id="595e4-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="595e4-115">Valores reservados apenas poluir o conjunto de valores reais e tendem a causar erros de usuário.</span><span class="sxs-lookup"><span data-stu-id="595e4-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>  
  
 <span data-ttu-id="595e4-116">**X Evite** publicamente expondo enums com apenas um valor.</span><span class="sxs-lookup"><span data-stu-id="595e4-116">**X AVOID** publicly exposing enums with only one value.</span></span>  
  
 <span data-ttu-id="595e4-117">É uma prática comum para garantir a extensibilidade futura de APIs de C adicionar parâmetros reservados para assinaturas de método.</span><span class="sxs-lookup"><span data-stu-id="595e4-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="595e4-118">Esses parâmetros reservados podem ser expressados como enums com um valor único padrão.</span><span class="sxs-lookup"><span data-stu-id="595e4-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="595e4-119">Isso não deve ser feito de APIs gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="595e4-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="595e4-120">Sobrecarga de método permite a adição de parâmetros em versões futuras.</span><span class="sxs-lookup"><span data-stu-id="595e4-120">Method overloading allows adding parameters in future releases.</span></span>  
  
 <span data-ttu-id="595e4-121">**X não** incluir valores de sentinela em enums.</span><span class="sxs-lookup"><span data-stu-id="595e4-121">**X DO NOT** include sentinel values in enums.</span></span>  
  
 <span data-ttu-id="595e4-122">Embora, às vezes, elas são úteis para os desenvolvedores do framework, os valores de sentinela são confusos para os usuários do framework.</span><span class="sxs-lookup"><span data-stu-id="595e4-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="595e4-123">Eles são usados para controlar o estado de enum em vez de ser um dos valores do conjunto de representado por enum.</span><span class="sxs-lookup"><span data-stu-id="595e4-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>  
  
 <span data-ttu-id="595e4-124">**FAZER ✓** fornecer um valor de zero em enumerações simples.</span><span class="sxs-lookup"><span data-stu-id="595e4-124">**✓ DO** provide a value of zero on simple enums.</span></span>  
  
 <span data-ttu-id="595e4-125">Considere a possibilidade de chamar o valor algo como "None".</span><span class="sxs-lookup"><span data-stu-id="595e4-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="595e4-126">Se esse valor não é apropriado para essa enumeração específica, o valor padrão mais comum para a enum deve ser atribuído o valor subjacente do zero.</span><span class="sxs-lookup"><span data-stu-id="595e4-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>  
  
 <span data-ttu-id="595e4-127">**✓ CONSIDERE** usando <xref:System.Int32> (o padrão na maioria das linguagens de programação) como o tipo subjacente de enum, a menos que qualquer um dos seguintes for verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="595e4-127">**✓ CONSIDER** using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>  
  
-   <span data-ttu-id="595e4-128">A enumeração é um enum de sinalizadores e você tem mais de 32 sinalizadores ou espera ter mais no futuro.</span><span class="sxs-lookup"><span data-stu-id="595e4-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>  
  
-   <span data-ttu-id="595e4-129">O tipo subjacente deve ser diferente de <xref:System.Int32> mais fácil interoperabilidade com código não gerenciado esperando enums de tamanho diferente.</span><span class="sxs-lookup"><span data-stu-id="595e4-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>  
  
-   <span data-ttu-id="595e4-130">Um tipo subjacente menores pode resultar em uma economia substancial no espaço.</span><span class="sxs-lookup"><span data-stu-id="595e4-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="595e4-131">Se você espera que o enum a ser usada principalmente como um argumento para o fluxo de controle, o tamanho faz pouca diferença.</span><span class="sxs-lookup"><span data-stu-id="595e4-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="595e4-132">A economia de tamanho pode ser significativa se:</span><span class="sxs-lookup"><span data-stu-id="595e4-132">The size savings might be significant if:</span></span>  
  
    -   <span data-ttu-id="595e4-133">Você espera que o enum a ser usado como um campo em uma classe ou estrutura instanciada com muita frequência.</span><span class="sxs-lookup"><span data-stu-id="595e4-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>  
  
    -   <span data-ttu-id="595e4-134">Você espera que os usuários criem matrizes grandes ou coleções de enumerar instâncias.</span><span class="sxs-lookup"><span data-stu-id="595e4-134">You expect users to create large arrays or collections of the enum instances.</span></span>  
  
    -   <span data-ttu-id="595e4-135">Você espera que um grande número de instâncias do enum a ser serializado.</span><span class="sxs-lookup"><span data-stu-id="595e4-135">You expect a large number of instances of the enum to be serialized.</span></span>  
  
 <span data-ttu-id="595e4-136">Para uso na memória, esteja ciente de que os objetos gerenciados são sempre `DWORD`-alinhado, portanto, você precisa efetivamente várias enums ou outras estruturas pequenas em uma instância para um enum menor do pacote para fazer a diferença, porque o tamanho de instância total é sempre vai ser arredondado para cima até um `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="595e4-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>  
  
 <span data-ttu-id="595e4-137">**FAZER ✓** nome do sinalizador enums com substantivos plurais ou frases nominais e simples enums com substantivos singulares ou frases nominais.</span><span class="sxs-lookup"><span data-stu-id="595e4-137">**✓ DO** name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="595e4-138">**X não** estender <xref:System.Enum?displayProperty=nameWithType> diretamente.</span><span class="sxs-lookup"><span data-stu-id="595e4-138">**X DO NOT** extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>  
  
 <span data-ttu-id="595e4-139"><xref:System.Enum?displayProperty=nameWithType>é um tipo especial usado pelo CLR para criar enumerações definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="595e4-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="595e4-140">A maioria das linguagens de programação fornecem um elemento de programação que fornece acesso a essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="595e4-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="595e4-141">Por exemplo, no c# o `enum` palavra-chave é usada para definir uma enumeração.</span><span class="sxs-lookup"><span data-stu-id="595e4-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a><span data-ttu-id="595e4-142">Projetando Enums de sinalizador</span><span class="sxs-lookup"><span data-stu-id="595e4-142">Designing Flag Enums</span></span>  
 <span data-ttu-id="595e4-143">**FAZER ✓** se aplicam a <xref:System.FlagsAttribute?displayProperty=nameWithType> para enums de sinalizador.</span><span class="sxs-lookup"><span data-stu-id="595e4-143">**✓ DO** apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="595e4-144">Não aplica esse atributo para enums simples.</span><span class="sxs-lookup"><span data-stu-id="595e4-144">Do not apply this attribute to simple enums.</span></span>  
  
 <span data-ttu-id="595e4-145">**FAZER ✓** usar potências de dois para os valores de enumeração de sinalizador, portanto, eles podem ser livremente combinados usando a operação OR bit a bit.</span><span class="sxs-lookup"><span data-stu-id="595e4-145">**✓ DO** use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>  
  
 <span data-ttu-id="595e4-146">**✓ CONSIDERE** fornecer valores de enum especial para comumente usadas combinações de sinalizadores.</span><span class="sxs-lookup"><span data-stu-id="595e4-146">**✓ CONSIDER** providing special enum values for commonly used combinations of flags.</span></span>  
  
 <span data-ttu-id="595e4-147">Operações bit a bit são um conceito avançado e não será necessárias para tarefas simples.</span><span class="sxs-lookup"><span data-stu-id="595e4-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="595e4-148"><xref:System.IO.FileAccess.ReadWrite>é um exemplo de tal um valor especial.</span><span class="sxs-lookup"><span data-stu-id="595e4-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>  
  
 <span data-ttu-id="595e4-149">**X Evite** criando enums sinalizador onde algumas combinações de valores são inválidas.</span><span class="sxs-lookup"><span data-stu-id="595e4-149">**X AVOID** creating flag enums where certain combinations of values are invalid.</span></span>  
  
 <span data-ttu-id="595e4-150">**X Evite** usando o sinalizador valores de enumeração de zero, a menos que o valor representa a "todos os sinalizadores são desmarcados" e é denominado adequadamente, conforme descrito pela seguinte diretriz.</span><span class="sxs-lookup"><span data-stu-id="595e4-150">**X AVOID** using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>  
  
 <span data-ttu-id="595e4-151">**FAZER ✓** o nome do valor zero de sinalizador enums `None`.</span><span class="sxs-lookup"><span data-stu-id="595e4-151">**✓ DO** name the zero value of flag enums `None`.</span></span> <span data-ttu-id="595e4-152">Para um enum de sinalizador, o valor sempre deve significa "todos os sinalizadores são desmarcados."</span><span class="sxs-lookup"><span data-stu-id="595e4-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a><span data-ttu-id="595e4-153">Adicionando o valor para Enums</span><span class="sxs-lookup"><span data-stu-id="595e4-153">Adding Value to Enums</span></span>  
 <span data-ttu-id="595e4-154">É muito comum para descobrir o que você precisa adicionar valores a um enum depois que você já o tenha enviado.</span><span class="sxs-lookup"><span data-stu-id="595e4-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="595e4-155">Há um possível problema de compatibilidade do aplicativo quando o valor recém-adicionado é retornado de uma API existente, como aplicativos mal escritos não podem tratar o novo valor corretamente.</span><span class="sxs-lookup"><span data-stu-id="595e4-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>  
  
 <span data-ttu-id="595e4-156">**✓ CONSIDERE** adicionando valores a enums, apesar de um risco de compatibilidade pequeno.</span><span class="sxs-lookup"><span data-stu-id="595e4-156">**✓ CONSIDER** adding values to enums, despite a small compatibility risk.</span></span>  
  
 <span data-ttu-id="595e4-157">Se você tiver dados reais sobre incompatibilidades entre aplicativos causados por adições para um enum, considere adicionar uma nova API que retorna os valores novos e antigos e substituir a antiga API, o que deve continuar a retornar apenas os valores antigos.</span><span class="sxs-lookup"><span data-stu-id="595e4-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="595e4-158">Isso irá garantir que seus aplicativos existentes permanecem compatíveis.</span><span class="sxs-lookup"><span data-stu-id="595e4-158">This will ensure that your existing applications remain compatible.</span></span>  
  
 <span data-ttu-id="595e4-159">*Partes © 2005, 2009 Microsoft Corporation. Todos os direitos reservados.*</span><span class="sxs-lookup"><span data-stu-id="595e4-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="595e4-160">*Reimpressas pela permissão de Pearson educação, Inc. de [diretrizes de Design do Framework: convenções, linguagens e padrões para bibliotecas do .NET reutilizável, 2ª edição](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) por Krzysztof Cwalina e Brad Abrams, publicados 22 de outubro de 2008, Addison-Wesley Professional como parte da série de desenvolvimento do Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="595e4-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="595e4-161">Consulte também</span><span class="sxs-lookup"><span data-stu-id="595e4-161">See Also</span></span>  
 [<span data-ttu-id="595e4-162">Diretrizes de Design de tipo</span><span class="sxs-lookup"><span data-stu-id="595e4-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="595e4-163">Diretrizes de design do Framework</span><span class="sxs-lookup"><span data-stu-id="595e4-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)