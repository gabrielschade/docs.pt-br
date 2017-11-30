---
title: "Transações locais"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8ae3712f-ef5e-41a1-9ea9-b3d0399439f1
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f9b1280f3a05a42a2f713adf993bb439245c95a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="local-transactions"></a><span data-ttu-id="e37f5-102">Transações locais</span><span class="sxs-lookup"><span data-stu-id="e37f5-102">Local Transactions</span></span>
<span data-ttu-id="e37f5-103">As transações no [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] são usadas quando o usuário deseja associar várias tarefas para que possam ser executadas como uma unidade de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e37f5-103">Transactions in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] are used when you want to bind multiple tasks together so that they execute as a single unit of work.</span></span> <span data-ttu-id="e37f5-104">Por exemplo, imagine que um aplicativo executa duas tarefas.</span><span class="sxs-lookup"><span data-stu-id="e37f5-104">For example, imagine that an application performs two tasks.</span></span> <span data-ttu-id="e37f5-105">Primeiro, ele atualiza uma tabela com informações sobre pedidos.</span><span class="sxs-lookup"><span data-stu-id="e37f5-105">First, it updates a table with order information.</span></span> <span data-ttu-id="e37f5-106">Em seguida, ele atualiza uma tabela que contém informações de inventário, debitando os itens pedidos.</span><span class="sxs-lookup"><span data-stu-id="e37f5-106">Second, it updates a table that contains inventory information, debiting the items ordered.</span></span> <span data-ttu-id="e37f5-107">Se a tarefa falhar, em seguida, ambas as atualizações serão revertidas.</span><span class="sxs-lookup"><span data-stu-id="e37f5-107">If either task fails, then both updates are rolled back.</span></span>  
  
## <a name="determining-the-transaction-type"></a><span data-ttu-id="e37f5-108">Determinando o tipo de transação</span><span class="sxs-lookup"><span data-stu-id="e37f5-108">Determining the Transaction Type</span></span>  
 <span data-ttu-id="e37f5-109">Uma transação é considerada uma transação local quando ele é uma transação de fase única e é tratado pelo banco de dados diretamente.</span><span class="sxs-lookup"><span data-stu-id="e37f5-109">A transaction is considered to be a local transaction when it is a single-phase transaction and is handled by the database directly.</span></span> <span data-ttu-id="e37f5-110">Uma transação é considerada uma transação distribuída quando ele é coordenado pelo monitor de uma transação e usa mecanismos à prova de falhas (como a confirmação de duas fases) para resolução de transações.</span><span class="sxs-lookup"><span data-stu-id="e37f5-110">A transaction is considered to be a distributed transaction when it is coordinated by a transaction monitor and uses fail-safe mechanisms (such as two-phase commit) for transaction resolution.</span></span>  
  
 <span data-ttu-id="e37f5-111">Cada provedor de dados do [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] tem seu próprio objeto `Transaction` para executar transações locais.</span><span class="sxs-lookup"><span data-stu-id="e37f5-111">Each of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers has its own `Transaction` object for performing local transactions.</span></span> <span data-ttu-id="e37f5-112">Se você precisar executar uma transação em um banco de dados do SQL Server, selecione uma transação <xref:System.Data.SqlClient>.</span><span class="sxs-lookup"><span data-stu-id="e37f5-112">If you require a transaction to be performed in a SQL Server database, select a <xref:System.Data.SqlClient> transaction.</span></span> <span data-ttu-id="e37f5-113">Para uma transação Oracle, use o provedor <xref:System.Data.OracleClient>.</span><span class="sxs-lookup"><span data-stu-id="e37f5-113">For an Oracle transaction, use the <xref:System.Data.OracleClient> provider.</span></span> <span data-ttu-id="e37f5-114">Além disso, há uma nova classe <xref:System.Data.Common.DbTransaction> que está disponível para a criação de código independente de provedor que requer transações.</span><span class="sxs-lookup"><span data-stu-id="e37f5-114">In addition, there is a new <xref:System.Data.Common.DbTransaction> class that is available for writing provider-independent code that requires transactions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e37f5-115">As transações são mais eficientes quando executadas no servidor.</span><span class="sxs-lookup"><span data-stu-id="e37f5-115">Transactions are most efficient when it is performed on the server.</span></span> <span data-ttu-id="e37f5-116">Se você estiver trabalhando com um banco de dados do SQL Server que faz uso extensivo de transações explícitas, considere criá-las como procedimentos armazenados usando a instrução Transact-SQL BEGIN TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="e37f5-116">If you are working with a SQL Server database that makes extensive use of explicit transactions, consider writing them as stored procedures using the Transact-SQL BEGIN TRANSACTION statement.</span></span> <span data-ttu-id="e37f5-117">Para obter mais informações sobre como executar transações no servidor, consulte Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e37f5-117">For more information about performing server-side transactions, see SQL Server Books Online.</span></span>  
  
## <a name="performing-a-transaction-using-a-single-connection"></a><span data-ttu-id="e37f5-118">Executando uma transação com uma única conexão</span><span class="sxs-lookup"><span data-stu-id="e37f5-118">Performing a Transaction Using a Single Connection</span></span>  
 <span data-ttu-id="e37f5-119">No [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], você controla transações com o objeto `Connection`.</span><span class="sxs-lookup"><span data-stu-id="e37f5-119">In [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], you control transactions with the `Connection` object.</span></span> <span data-ttu-id="e37f5-120">É possível iniciar uma transação local com o método `BeginTransaction`.</span><span class="sxs-lookup"><span data-stu-id="e37f5-120">You can initiate a local transaction with the `BeginTransaction` method.</span></span> <span data-ttu-id="e37f5-121">Depois de iniciar uma transação, você pode inscrever um comando nessa transação com a propriedade `Transaction` de um objeto `Command`.</span><span class="sxs-lookup"><span data-stu-id="e37f5-121">Once you have begun a transaction, you can enlist a command in that transaction with the `Transaction` property of a `Command` object.</span></span> <span data-ttu-id="e37f5-122">Em seguida, você poderá confirmar ou reverter todas as modificações feitas na fonte de dados com base no êxito ou na falha dos componentes de transação.</span><span class="sxs-lookup"><span data-stu-id="e37f5-122">You can then commit or roll back modifications made at the data source based on the success or failure of the components of the transaction.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e37f5-123">O método `EnlistDistributedTransaction` não deve ser usado para uma transação local.</span><span class="sxs-lookup"><span data-stu-id="e37f5-123">The `EnlistDistributedTransaction` method should not be used for a local transaction.</span></span>  
  
 <span data-ttu-id="e37f5-124">O escopo da transação é limitado à conexão.</span><span class="sxs-lookup"><span data-stu-id="e37f5-124">The scope of the transaction is limited to the connection.</span></span> <span data-ttu-id="e37f5-125">O exemplo a seguir executa uma transação explícita que consiste em dois comandos separados no bloco `try`.</span><span class="sxs-lookup"><span data-stu-id="e37f5-125">The following example performs an explicit transaction that consists of two separate commands in the `try` block.</span></span> <span data-ttu-id="e37f5-126">Os comandos executam as instruções INSERT na tabela Production.ScrapReason do banco de dados de exemplo AdventureWorks do [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], as quais são confirmadas se nenhuma exceção for gerada.</span><span class="sxs-lookup"><span data-stu-id="e37f5-126">The commands execute INSERT statements against the Production.ScrapReason table in the AdventureWorks [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] sample database, which are committed if no exceptions are thrown.</span></span> <span data-ttu-id="e37f5-127">O código no bloco `catch` reverte a transação se uma exceção é gerada.</span><span class="sxs-lookup"><span data-stu-id="e37f5-127">The code in the `catch` block rolls back the transaction if an exception is thrown.</span></span> <span data-ttu-id="e37f5-128">Se a transação for anulada ou a conexão for fechada antes de a transação ser concluída, a transação será automaticamente revertida.</span><span class="sxs-lookup"><span data-stu-id="e37f5-128">If the transaction is aborted or the connection is closed before the transaction has completed, it is automatically rolled back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e37f5-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e37f5-129">Example</span></span>  
 <span data-ttu-id="e37f5-130">Siga estas etapas para executar uma transação.</span><span class="sxs-lookup"><span data-stu-id="e37f5-130">Follow these steps to perform a transaction.</span></span>  
  
1.  <span data-ttu-id="e37f5-131">Chame o método <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> do objeto <xref:System.Data.SqlClient.SqlConnection> para marcar o início da transação.</span><span class="sxs-lookup"><span data-stu-id="e37f5-131">Call the <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object to mark the start of the transaction.</span></span> <span data-ttu-id="e37f5-132">O método <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> retorna uma referência à transação.</span><span class="sxs-lookup"><span data-stu-id="e37f5-132">The <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> method returns a reference to the transaction.</span></span> <span data-ttu-id="e37f5-133">Essa referência é atribuída aos objetos <xref:System.Data.SqlClient.SqlCommand> inscritos na transação.</span><span class="sxs-lookup"><span data-stu-id="e37f5-133">This reference is assigned to the <xref:System.Data.SqlClient.SqlCommand> objects that are enlisted in the transaction.</span></span>  
  
2.  <span data-ttu-id="e37f5-134">Atribua o objeto `Transaction` à propriedade <xref:System.Data.SqlClient.SqlCommand.Transaction%2A> de <xref:System.Data.SqlClient.SqlCommand> a ser executado.</span><span class="sxs-lookup"><span data-stu-id="e37f5-134">Assign the `Transaction` object to the <xref:System.Data.SqlClient.SqlCommand.Transaction%2A> property of the <xref:System.Data.SqlClient.SqlCommand> to be executed.</span></span> <span data-ttu-id="e37f5-135">Se um comando for executado em uma conexão com uma transação ativa, e o objeto `Transaction` não tiver sido atribuído à propriedade `Transaction` do objeto `Command`, uma exceção será gerada.</span><span class="sxs-lookup"><span data-stu-id="e37f5-135">If a command is executed on a connection with an active transaction, and the `Transaction` object has not been assigned to the `Transaction` property of the `Command` object, an exception is thrown.</span></span>  
  
3.  <span data-ttu-id="e37f5-136">Execute os comandos necessários.</span><span class="sxs-lookup"><span data-stu-id="e37f5-136">Execute the required commands.</span></span>  
  
4.  <span data-ttu-id="e37f5-137">Chame o método <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> do objeto <xref:System.Data.SqlClient.SqlTransaction> para concluir a transação, ou chame o método <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A> para finalizar a transação.</span><span class="sxs-lookup"><span data-stu-id="e37f5-137">Call the <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> method of the <xref:System.Data.SqlClient.SqlTransaction> object to complete the transaction, or call the <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A> method to end the transaction.</span></span> <span data-ttu-id="e37f5-138">Se a conexão for fechada ou descartada antes do método <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> ou <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A> ser executado, a transação será revertida.</span><span class="sxs-lookup"><span data-stu-id="e37f5-138">If the connection is closed or disposed before either the <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> or <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A> methods have been executed, the transaction is rolled back.</span></span>  
  
 <span data-ttu-id="e37f5-139">O exemplo de código a seguir demonstra a lógica transacional usando o [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] com o Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e37f5-139">The following code example demonstrates transactional logic using [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] with Microsoft SQL Server.</span></span>  
  
 [!code-csharp[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e37f5-140">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e37f5-140">See Also</span></span>  
 [<span data-ttu-id="e37f5-141">Transações e simultaneidade</span><span class="sxs-lookup"><span data-stu-id="e37f5-141">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="e37f5-142">Transações distribuídas</span><span class="sxs-lookup"><span data-stu-id="e37f5-142">Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 [<span data-ttu-id="e37f5-143">Integração de System. Transactions com o SQL Server</span><span class="sxs-lookup"><span data-stu-id="e37f5-143">System.Transactions Integration with SQL Server</span></span>](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 <span data-ttu-id="e37f5-144">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="e37f5-144">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)</span></span>