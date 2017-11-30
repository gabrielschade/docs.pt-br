---
title: LINQ to Entities
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 641f9b68-9046-47a1-abb0-1c8eaeda0e2d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 685651f4291a11b857da82a63068e4bd2333275c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="linq-to-entities"></a><span data-ttu-id="ff02f-102">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ff02f-102">LINQ to Entities</span></span>
<span data-ttu-id="ff02f-103">O LINQ to Entities fornece suporte a LINQ (Consulta Integrada à Linguagem) que permite aos desenvolvedores escreverem consultas no modelo conceitual do Entity Framework usando Visual Basic ou Visual C#.</span><span class="sxs-lookup"><span data-stu-id="ff02f-103">LINQ to Entities provides Language-Integrated Query (LINQ) support that enables developers to write queries against the Entity Framework conceptual model using Visual Basic or Visual C#.</span></span> <span data-ttu-id="ff02f-104">As consultas no Entity Framework são representadas por consultas de árvore de comando, que são executadas no contexto de objeto.</span><span class="sxs-lookup"><span data-stu-id="ff02f-104">Queries against the Entity Framework are represented by command tree queries, which execute against the object context.</span></span> <span data-ttu-id="ff02f-105">O LINQ to Entities converte consultas do LINQ (Consulta Integrada à Linguagem) para consultas de árvore de comando, executa as consultas no Entity Framework e retorna os objetos que podem ser usados pelo Entity Framework e pelo LINQ.</span><span class="sxs-lookup"><span data-stu-id="ff02f-105">LINQ to Entities converts Language-Integrated Queries (LINQ) queries to command tree queries, executes the queries against the Entity Framework, and returns objects that can be used by both the Entity Framework and LINQ.</span></span> <span data-ttu-id="ff02f-106">Veja a seguir o processo para criar e executar uma consulta LINQ to Entities:</span><span class="sxs-lookup"><span data-stu-id="ff02f-106">The following is the process for creating and executing a LINQ to Entities query:</span></span>  
  
1.  <span data-ttu-id="ff02f-107">Construa uma instância <xref:System.Data.Objects.ObjectQuery%601> do <xref:System.Data.Objects.ObjectContext>.</span><span class="sxs-lookup"><span data-stu-id="ff02f-107">Construct an <xref:System.Data.Objects.ObjectQuery%601> instance from <xref:System.Data.Objects.ObjectContext>.</span></span>  
  
2.  <span data-ttu-id="ff02f-108">Componha uma consulta LINQ to Entities no C# ou Visual Basic usando a instância <xref:System.Data.Objects.ObjectQuery%601>.</span><span class="sxs-lookup"><span data-stu-id="ff02f-108">Compose a LINQ to Entities query in C# or Visual Basic by using the <xref:System.Data.Objects.ObjectQuery%601> instance.</span></span>  
  
3.  <span data-ttu-id="ff02f-109">Converta operadores e expressões padrão de consulta LINQ para árvores de comando.</span><span class="sxs-lookup"><span data-stu-id="ff02f-109">Convert LINQ standard query operators and expressions to command trees.</span></span>  
  
4.  <span data-ttu-id="ff02f-110">Execute a consulta, na representação da árvore de comando, na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ff02f-110">Execute the query, in command tree representation, against the data source.</span></span> <span data-ttu-id="ff02f-111">Todas as exceções geradas na fonte de dados durante a execução são passadas diretamente até o cliente.</span><span class="sxs-lookup"><span data-stu-id="ff02f-111">Any exceptions thrown on the data source during execution are passed directly up to the client.</span></span>  
  
5.  <span data-ttu-id="ff02f-112">Retorne os resultados da consulta de volta para o cliente.</span><span class="sxs-lookup"><span data-stu-id="ff02f-112">Return query results back to the client.</span></span>  
  
## <a name="constructing-an-objectquery-instance"></a><span data-ttu-id="ff02f-113">Construindo uma instância de ObjectQuery</span><span class="sxs-lookup"><span data-stu-id="ff02f-113">Constructing an ObjectQuery Instance</span></span>  
 <span data-ttu-id="ff02f-114">A classe genérica <xref:System.Data.Objects.ObjectQuery%601> representa uma consulta que retorna uma coleção de zero ou mais entidades tipadas.</span><span class="sxs-lookup"><span data-stu-id="ff02f-114">The <xref:System.Data.Objects.ObjectQuery%601> generic class represents a query that returns a collection of zero or more typed entities.</span></span> <span data-ttu-id="ff02f-115">Uma consulta de objeto é construída normalmente de um contexto de objeto existente, em vez de ser construído manualmente, e sempre pertence ao contexto de objeto.</span><span class="sxs-lookup"><span data-stu-id="ff02f-115">An object query is typically constructed from an existing object context, instead of being manually constructed, and always belongs to that object context.</span></span> <span data-ttu-id="ff02f-116">Esse contexto fornece a conexão e as informações de metadados necessárias para compor e executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="ff02f-116">This context provides the connection and metadata information that is required to compose and execute the query.</span></span> <span data-ttu-id="ff02f-117">A classe genérica <xref:System.Data.Objects.ObjectQuery%601> implementa a interface genérica <xref:System.Linq.IQueryable%601>, cujos métodos de construtor habilitam as consultas LINQ para serem criadas incrementalmente.</span><span class="sxs-lookup"><span data-stu-id="ff02f-117">The <xref:System.Data.Objects.ObjectQuery%601> generic class implements the <xref:System.Linq.IQueryable%601> generic interface, whose builder methods enable LINQ queries to be incrementally built.</span></span> <span data-ttu-id="ff02f-118">Você também pode permitir que o compilador infira o tipo de entidade usando a palavra-chave `var` do C# (`Dim` no Visual Basic, com inferência de tipo de local habilitada).</span><span class="sxs-lookup"><span data-stu-id="ff02f-118">You can also let the compiler infer the type of entities by using the C# `var` keyword (`Dim` in Visual Basic, with local type inference enabled).</span></span>  
  
## <a name="composing-the-queries"></a><span data-ttu-id="ff02f-119">Compondo as consultas</span><span class="sxs-lookup"><span data-stu-id="ff02f-119">Composing the Queries</span></span>  
 <span data-ttu-id="ff02f-120">As instâncias da classe genérica <xref:System.Data.Objects.ObjectQuery%601>, que implementa a interface de <xref:System.Linq.IQueryable%601>, funcionam como a fonte de dados para consultas LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="ff02f-120">Instances of the <xref:System.Data.Objects.ObjectQuery%601> generic class, which implements the generic <xref:System.Linq.IQueryable%601> interface, serve as the data source for LINQ to Entities queries.</span></span> <span data-ttu-id="ff02f-121">Em uma consulta, você especifica exatamente as informações que deseja recuperar da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ff02f-121">In a query, you specify exactly the information that you want to retrieve from the data source.</span></span> <span data-ttu-id="ff02f-122">Uma consulta também pode especificar como essas informações devem ser classificadas, agrupadas e moldadas antes de serem retornadas.</span><span class="sxs-lookup"><span data-stu-id="ff02f-122">A query can also specify how that information should be sorted, grouped, and shaped before it is returned.</span></span> <span data-ttu-id="ff02f-123">No LINQ, uma consulta é armazenada em uma variável.</span><span class="sxs-lookup"><span data-stu-id="ff02f-123">In LINQ, a query is stored in a variable.</span></span> <span data-ttu-id="ff02f-124">Essa variável de consulta não toma nenhuma ação e não retorna nenhum dado, ela apenas armazena as informações da consulta.</span><span class="sxs-lookup"><span data-stu-id="ff02f-124">This query variable takes no action and returns no data; it only stores the query information.</span></span> <span data-ttu-id="ff02f-125">Depois de criar uma consulta, você deve executá-la para recuperar todos os dados.</span><span class="sxs-lookup"><span data-stu-id="ff02f-125">After you create a query you must execute that query to retrieve any data.</span></span>  
  
 <span data-ttu-id="ff02f-126">As consultas LINQ to Entities podem ser compostas de duas sintaxes diferentes: sintaxe de expressão de consulta e sintaxe de consulta baseada em método.</span><span class="sxs-lookup"><span data-stu-id="ff02f-126">LINQ to Entities queries can be composed in two different syntaxes: query expression syntax and method-based query syntax.</span></span> <span data-ttu-id="ff02f-127">A sintaxe da expressão de consulta e a sintaxe da consulta com base em método são novidades no C# 3.0 e no Visual Basic 9.0.</span><span class="sxs-lookup"><span data-stu-id="ff02f-127">Query expression syntax and method-based query syntax are new in C# 3.0 and Visual Basic 9.0.</span></span>  
  
 <span data-ttu-id="ff02f-128">Para obter mais informações, consulte [consultas no LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="ff02f-128">For more information, see [Queries in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md).</span></span>  
  
## <a name="query-conversion"></a><span data-ttu-id="ff02f-129">Conversão de consulta</span><span class="sxs-lookup"><span data-stu-id="ff02f-129">Query Conversion</span></span>  
 <span data-ttu-id="ff02f-130">Para executar uma consulta LINQ to Entities no Entity Framework, a consulta LINQ deve ser convertida em uma representação de árvore de comando que pode ser executada no Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="ff02f-130">To execute a LINQ to Entities query against the Entity Framework, the LINQ query must be converted to a command tree representation that can be executed against the Entity Framework.</span></span>  
  
 <span data-ttu-id="ff02f-131">As consultas LINQ to Entities são compostas de operadores padrão de consulta LINQ (como <xref:System.Linq.Queryable.Select%2A>, <xref:System.Linq.Queryable.Where%2A> e <xref:System.Linq.Queryable.GroupBy%2A>) e expressões (x > 10, Contact.LastName, e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="ff02f-131">LINQ to Entities queries are comprised of LINQ standard query operators (such as <xref:System.Linq.Queryable.Select%2A>, <xref:System.Linq.Queryable.Where%2A>, and <xref:System.Linq.Queryable.GroupBy%2A>) and expressions (x > 10, Contact.LastName, and so on).</span></span> <span data-ttu-id="ff02f-132">Os operadores LINQ não são definidos por uma classe, mas são métodos em uma classe.</span><span class="sxs-lookup"><span data-stu-id="ff02f-132">LINQ operators are not defined by a class, but rather are methods on a class.</span></span> <span data-ttu-id="ff02f-133">No LINQ, as expressões podem conter tudo o que é permitido por tipos dentro do namespace <xref:System.Linq.Expressions> e, por extensão, tudo o que pode ser representado em uma função lambda.</span><span class="sxs-lookup"><span data-stu-id="ff02f-133">In LINQ, expressions can contain anything allowed by types within the <xref:System.Linq.Expressions> namespace and, by extension, anything that can be represented in a lambda function.</span></span> <span data-ttu-id="ff02f-134">Este é um superconjunto de expressões que são permitidas pelo Entity Framework, que são restritas por definição para as operações permitidas no banco de dados, e têm suporte pelo <xref:System.Data.Objects.ObjectQuery%601>.</span><span class="sxs-lookup"><span data-stu-id="ff02f-134">This is a superset of the expressions that are allowed by the Entity Framework, which are by definition restricted to operations allowed on the database, and supported by <xref:System.Data.Objects.ObjectQuery%601>.</span></span>  
  
 <span data-ttu-id="ff02f-135">No Entity Framework, os operadores e as expressões são representados por uma única hierarquia de tipo, que são colocadas em uma árvore de comando.</span><span class="sxs-lookup"><span data-stu-id="ff02f-135">In the Entity Framework, both operators and expressions are represented by a single type hierarchy, which are then placed in a command tree.</span></span> <span data-ttu-id="ff02f-136">A árvore de comando é usada pelo Entity Framework para executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="ff02f-136">The command tree is used by the Entity Framework to execute the query.</span></span> <span data-ttu-id="ff02f-137">Se a consulta LINQ não puder ser expressada como uma árvore de comando, uma exceção será gerada quando a consulta estiver sendo convertida.</span><span class="sxs-lookup"><span data-stu-id="ff02f-137">If the LINQ query cannot be expressed as a command tree, an exception will be thrown when the query is being converted.</span></span> <span data-ttu-id="ff02f-138">A conversão de consultas LINQ to Entities envolve duas subconversões: a conversão dos operadores de consulta padrão e a conversão das expressões.</span><span class="sxs-lookup"><span data-stu-id="ff02f-138">The conversion of LINQ to Entities queries involves two sub-conversions: the conversion of the standard query operators, and the conversion of the expressions.</span></span>  
  
 <span data-ttu-id="ff02f-139">Há um número de operadores padrão de consulta LINQ que não têm uma tradução válida no LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="ff02f-139">There are a number of LINQ standard query operators that do not have a valid translation in LINQ to Entities.</span></span> <span data-ttu-id="ff02f-140">As tentativas de usar esses operadores resultarão em uma exceção em tempo de tradução de consulta.</span><span class="sxs-lookup"><span data-stu-id="ff02f-140">Attempts to use these operators will result in an exception at query translation time.</span></span> <span data-ttu-id="ff02f-141">Para obter uma lista de LINQ com suporte a operadores de entidades, consulte [com suporte e não há suporte para métodos de LINQ (LINQ to Entities)](../../../../../../docs/framework/data/adonet/ef/language-reference/supported-and-unsupported-linq-methods-linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="ff02f-141">For a list of supported LINQ to Entities operators, see [Supported and Unsupported LINQ Methods (LINQ to Entities)](../../../../../../docs/framework/data/adonet/ef/language-reference/supported-and-unsupported-linq-methods-linq-to-entities.md).</span></span>  
  
 <span data-ttu-id="ff02f-142">Para obter mais informações sobre como usar os operadores de consulta padrão em LINQ to Entities, consulte [operadores de consulta padrão em consultas LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/standard-query-operators-in-linq-to-entities-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ff02f-142">For more information about using the standard query operators in LINQ to Entities, see [Standard Query Operators in LINQ to Entities Queries](../../../../../../docs/framework/data/adonet/ef/language-reference/standard-query-operators-in-linq-to-entities-queries.md).</span></span>  
  
 <span data-ttu-id="ff02f-143">Em geral, as expressões no LINQ to Entities são avaliadas no servidor. Portanto, não se deve esperar que o comportamento da expressão siga a semântica de CLR.</span><span class="sxs-lookup"><span data-stu-id="ff02f-143">In general, expressions in LINQ to Entities are evaluated on the server, so the behavior of the expression should not be expected to follow CLR semantics.</span></span> <span data-ttu-id="ff02f-144">Para obter mais informações, consulte [expressões em consultas LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ff02f-144">For more information, see [Expressions in LINQ to Entities Queries](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md).</span></span>  
  
 <span data-ttu-id="ff02f-145">Para obter informações sobre como as chamadas de método CLR são mapeadas para funções canônicas na fonte de dados, consulte [método CLR ao mapeamento canônico de função](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="ff02f-145">For information about how CLR method calls are mapped to canonical functions in the data source, see [CLR Method to Canonical Function Mapping](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md).</span></span>  
  
 <span data-ttu-id="ff02f-146">Para obter informações sobre como chamar canônico, banco de dados e funções personalizadas no [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] consultas, consulte [chamando funções em consultas LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ff02f-146">For information about how to call canonical, database, and custom functions from within [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries, see [Calling Functions in LINQ to Entities Queries](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md).</span></span>  
  
## <a name="query-execution"></a><span data-ttu-id="ff02f-147">Execução da Consulta</span><span class="sxs-lookup"><span data-stu-id="ff02f-147">Query Execution</span></span>  
 <span data-ttu-id="ff02f-148">Depois que a consulta LINQ é criada pelo usuário, ela é convertida para uma representação que está compatível com o Entity Framework (na forma de árvores de comando), que é, em seguida, executado na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ff02f-148">After the LINQ query is created by the user, it is converted to a representation that is compatible with the Entity Framework (in the form of command trees), which is then executed against the data source.</span></span> <span data-ttu-id="ff02f-149">No tempo de execução de consulta, todas as expressões de consulta (ou componentes da consulta) são avaliados no cliente ou no servidor.</span><span class="sxs-lookup"><span data-stu-id="ff02f-149">At query execution time, all query expressions (or components of the query) are evaluated on the client or on the server.</span></span> <span data-ttu-id="ff02f-150">Isso inclui as expressões que são usadas na materialização de resultados ou projeções de entidade.</span><span class="sxs-lookup"><span data-stu-id="ff02f-150">This includes expressions that are used in result materialization or entity projections.</span></span> <span data-ttu-id="ff02f-151">Para obter mais informações, consulte [a execução da consulta](../../../../../../docs/framework/data/adonet/ef/language-reference/query-execution.md).</span><span class="sxs-lookup"><span data-stu-id="ff02f-151">For more information, see [Query Execution](../../../../../../docs/framework/data/adonet/ef/language-reference/query-execution.md).</span></span> <span data-ttu-id="ff02f-152">Para obter informações sobre como melhorar o desempenho ao compilar uma consulta uma vez e, em seguida, executá-la várias vezes com parâmetros diferentes, consulte [consultas compiladas (LINQ to Entities)](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="ff02f-152">For information on how to improve performance by compiling a query once and then executing it several times with different parameters, see [Compiled Queries  (LINQ to Entities)](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span></span>  
  
## <a name="materialization"></a><span data-ttu-id="ff02f-153">Materialização</span><span class="sxs-lookup"><span data-stu-id="ff02f-153">Materialization</span></span>  
 <span data-ttu-id="ff02f-154">A materialização é o processo de retornar resultados de consulta de volta para o cliente como tipos CLR.</span><span class="sxs-lookup"><span data-stu-id="ff02f-154">Materialization is the process of returning query results back to the client as CLR types.</span></span> <span data-ttu-id="ff02f-155">No LINQ to Entities, os registros de dados dos resultados da consulta nunca são retornados; há sempre um tipo CLR de suporte, definido pelo usuário ou pelo Entity Framework, ou gerado pelo compilador (tipos anônimos).</span><span class="sxs-lookup"><span data-stu-id="ff02f-155">In LINQ to Entities, query results data records are never returned; there is always a backing CLR type, defined by the user or by the Entity Framework, or generated by the compiler (anonymous types).</span></span> <span data-ttu-id="ff02f-156">Qualquer materialização de objeto é executada pelo Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="ff02f-156">All object materialization is performed by the Entity Framework.</span></span> <span data-ttu-id="ff02f-157">Todos os erros que resultarem de uma incapacidade de mapear entre o Entity Framework e o CLR gerarão exceções durante a materialização do objeto.</span><span class="sxs-lookup"><span data-stu-id="ff02f-157">Any errors that result from an inability to map between the Entity Framework and the CLR will cause exceptions to be thrown during object materialization.</span></span>  
  
 <span data-ttu-id="ff02f-158">Os resultados da consulta são geralmente retornados como um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="ff02f-158">Query results are usually returned as one of the following:</span></span>  
  
-   <span data-ttu-id="ff02f-159">Uma coleção de zero ou mais objetos de entidade tipados ou uma projeção de tipos complexos definidos no modelo conceitual.</span><span class="sxs-lookup"><span data-stu-id="ff02f-159">A collection of zero or more typed entity objects or a projection of complex types defined in the conceptual model.</span></span>  
  
-   <span data-ttu-id="ff02f-160">Tipos CLR que têm suporte pelo [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff02f-160">CLR types that are supported by the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  
  
-   <span data-ttu-id="ff02f-161">Coleções internas.</span><span class="sxs-lookup"><span data-stu-id="ff02f-161">Inline collections.</span></span>  
  
-   <span data-ttu-id="ff02f-162">Tipos anônimos.</span><span class="sxs-lookup"><span data-stu-id="ff02f-162">Anonymous types.</span></span>  
  
 <span data-ttu-id="ff02f-163">Para obter mais informações, consulte [resultados da consulta](../../../../../../docs/framework/data/adonet/ef/language-reference/query-results.md).</span><span class="sxs-lookup"><span data-stu-id="ff02f-163">For more information, see [Query Results](../../../../../../docs/framework/data/adonet/ef/language-reference/query-results.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff02f-164">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ff02f-164">In This Section</span></span>  
 [<span data-ttu-id="ff02f-165">Consultas no LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ff02f-165">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
  
 [<span data-ttu-id="ff02f-166">Expressões em consultas LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ff02f-166">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)  
  
 [<span data-ttu-id="ff02f-167">Chamando funções em consultas LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ff02f-167">Calling Functions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
  
 [<span data-ttu-id="ff02f-168">Consultas compiladas (LINQ to Entities)</span><span class="sxs-lookup"><span data-stu-id="ff02f-168">Compiled Queries  (LINQ to Entities)</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md)  
  
 [<span data-ttu-id="ff02f-169">Execução de consulta</span><span class="sxs-lookup"><span data-stu-id="ff02f-169">Query Execution</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-execution.md)  
  
 [<span data-ttu-id="ff02f-170">Resultados da Consulta</span><span class="sxs-lookup"><span data-stu-id="ff02f-170">Query Results</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-results.md)  
  
 [<span data-ttu-id="ff02f-171">Operadores de consulta padrão em consultas LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ff02f-171">Standard Query Operators in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/standard-query-operators-in-linq-to-entities-queries.md)  
  
 [<span data-ttu-id="ff02f-172">Método CLR ao mapeamento canônico de função</span><span class="sxs-lookup"><span data-stu-id="ff02f-172">CLR Method to Canonical Function Mapping</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md)  
  
 [<span data-ttu-id="ff02f-173">Métodos com suporte e sem suporte LINQ (LINQ to Entities)</span><span class="sxs-lookup"><span data-stu-id="ff02f-173">Supported and Unsupported LINQ Methods (LINQ to Entities)</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/supported-and-unsupported-linq-methods-linq-to-entities.md)  
  
 [<span data-ttu-id="ff02f-174">Problemas conhecidos e considerações no LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ff02f-174">Known Issues and Considerations in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/known-issues-and-considerations-in-linq-to-entities.md)  
  
## <a name="see-also"></a><span data-ttu-id="ff02f-175">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ff02f-175">See Also</span></span>  
 [<span data-ttu-id="ff02f-176">Problemas conhecidos e considerações no LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ff02f-176">Known Issues and Considerations in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/known-issues-and-considerations-in-linq-to-entities.md)  
 [<span data-ttu-id="ff02f-177">LINQ (Consulta Integrada à Linguagem)</span><span class="sxs-lookup"><span data-stu-id="ff02f-177">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [<span data-ttu-id="ff02f-178">LINQ e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ff02f-178">LINQ and ADO.NET</span></span>](../../../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 [<span data-ttu-id="ff02f-179">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="ff02f-179">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)