---
title: "Tipos definido pelo usuário CLR"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e81cf54ed9dc516d88b8c7a97c8a5b33b8943d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="a3516-102">Tipos definido pelo usuário CLR</span><span class="sxs-lookup"><span data-stu-id="a3516-102">CLR User-Defined Types</span></span>
<span data-ttu-id="a3516-103">O Microsoft SQL Server oferece suporte a tipos definidos pelo usuário (UDTs) implementados com o CLR do Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a3516-103">Microsoft SQL Server provides support for user-defined types (UDTs) implemented with the Microsoft .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="a3516-104">O CLR é integrado no SQL Server e esse mecanismo permite estender o sistema de tipos do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a3516-104">The CLR is integrated into SQL Server, and this mechanism enables you to extend the type system of the database.</span></span> <span data-ttu-id="a3516-105">Os UDTs oferecem extensibilidade do usuário do sistema de tipo de dados do SQL Server, além da capacidade de definir tipos estruturados complexos.</span><span class="sxs-lookup"><span data-stu-id="a3516-105">UDTs provide user extensibility of the SQL Server data type system, and also the ability to define complex structured types.</span></span>  
  
 <span data-ttu-id="a3516-106">Os UDTs podem fornecer dois principais benefícios de uma perspectiva da arquitetura de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="a3516-106">UDTs can provide two key benefits from an application architecture perspective:</span></span>  
  
-   <span data-ttu-id="a3516-107">Encapsulamento forte (no cliente e no servidor) entre o estado interno e os comportamentos externos.</span><span class="sxs-lookup"><span data-stu-id="a3516-107">Strong encapsulation (both in the client and the server) between the internal state and the external behaviors.</span></span>  
  
-   <span data-ttu-id="a3516-108">Integração profunda com outros recursos relacionados ao servidor.</span><span class="sxs-lookup"><span data-stu-id="a3516-108">Deep integration with other related server features.</span></span> <span data-ttu-id="a3516-109">Depois de definir seu próprio UDT, você poderá usá-lo em todos os contextos em que você pode usar um tipo de sistema no SQL Server, inclusive definições de coluna, e como variáveis, parâmetros, resultados de função, cursores, gatilhos e replicação.</span><span class="sxs-lookup"><span data-stu-id="a3516-109">Once you define your own UDT, you can use it in all contexts where you can use a system type in SQL Server, including column definitions, and as variables, parameters, function results, cursors, triggers, and replication.</span></span>  
  
 <span data-ttu-id="a3516-110">Para obter informações detalhadas, consulte a versão dos Manuais Online do SQL Server da versão do SQL Server que você está usando.</span><span class="sxs-lookup"><span data-stu-id="a3516-110">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="a3516-111">**SQL Server Books Online** (Guias online do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a3516-111">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="a3516-112">Tipos CLR definidos pelo usuário</span><span class="sxs-lookup"><span data-stu-id="a3516-112">CLR User-Defined Types</span></span>](http://go.microsoft.com/fwlink/?LinkId=98366)  
  
## <a name="see-also"></a><span data-ttu-id="a3516-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a3516-113">See Also</span></span>  
 [<span data-ttu-id="a3516-114">Criando objetos do SQL Server 2005 em código gerenciado</span><span class="sxs-lookup"><span data-stu-id="a3516-114">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 <span data-ttu-id="a3516-115">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="a3516-115">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)</span></span>