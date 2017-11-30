---
title: "Propriedade e separação do esquema do usuário no SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 242830c1-31b5-4427-828c-cc22ff339f30
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 168eaf9bc0bbac80cbd1e2bb0538aab89d262a49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ownership-and-user-schema-separation-in-sql-server"></a><span data-ttu-id="3485e-102">Propriedade e separação do esquema do usuário no SQL Server</span><span class="sxs-lookup"><span data-stu-id="3485e-102">Ownership and User-Schema Separation in SQL Server</span></span>
<span data-ttu-id="3485e-103">Um conceito central de segurança do SQL Server é que os proprietários de objetos têm permissões irrevogáveis administrá-los.</span><span class="sxs-lookup"><span data-stu-id="3485e-103">A core concept of SQL Server security is that owners of objects have irrevocable permissions to administer them.</span></span> <span data-ttu-id="3485e-104">Você não pode remover os privilégios de um proprietário de objeto e não pode eliminar usuários de um banco de dados se eles possuírem objetos nele.</span><span class="sxs-lookup"><span data-stu-id="3485e-104">You cannot remove privileges from an object owner, and you cannot drop users from a database if they own objects in it.</span></span>  
  
## <a name="user-schema-separation"></a><span data-ttu-id="3485e-105">Separação do esquema do usuário</span><span class="sxs-lookup"><span data-stu-id="3485e-105">User-Schema Separation</span></span>  
 <span data-ttu-id="3485e-106">A separação do esquema do usuário permite maior flexibilidade em gerenciar permissões do objeto de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3485e-106">User-schema separation allows for more flexibility in managing database object permissions.</span></span> <span data-ttu-id="3485e-107">Um *esquema* é um contêiner nomeado para objetos de banco de dados, que permite aos objetos de grupo em namespaces separados.</span><span class="sxs-lookup"><span data-stu-id="3485e-107">A *schema* is a named container for database objects, which allows you to group objects into separate namespaces.</span></span> <span data-ttu-id="3485e-108">Por exemplo, o banco de dados de exemplo AdventureWorks contém esquemas para Production, Sales e HumanResources.</span><span class="sxs-lookup"><span data-stu-id="3485e-108">For example, the AdventureWorks sample database contains schemas for Production, Sales, and HumanResources.</span></span>  
  
 <span data-ttu-id="3485e-109">A sintaxe de nomeação de quatro partes para referir-se a objetos especifica o nome do esquema.</span><span class="sxs-lookup"><span data-stu-id="3485e-109">The four-part naming syntax for referring to objects specifies the schema name.</span></span>  
  
```  
Server.Database.DatabaseSchema.DatabaseObject  
```  
  
### <a name="schema-owners-and-permissions"></a><span data-ttu-id="3485e-110">Proprietários e permissões do esquema</span><span class="sxs-lookup"><span data-stu-id="3485e-110">Schema Owners and Permissions</span></span>  
 <span data-ttu-id="3485e-111">Os esquemas podem ser de propriedade de qualquer entidade de banco de dados, e uma única entidade pode possuir vários esquemas.</span><span class="sxs-lookup"><span data-stu-id="3485e-111">Schemas can be owned by any database principal, and a single principal can own multiple schemas.</span></span> <span data-ttu-id="3485e-112">Você pode aplicar regras de segurança a um esquema, que são herdadas por todos os objetos no esquema.</span><span class="sxs-lookup"><span data-stu-id="3485e-112">You can apply security rules to a schema, which are inherited by all objects in the schema.</span></span> <span data-ttu-id="3485e-113">Depois que você configurar permissões de acesso para um esquema, essas permissões serão aplicadas automaticamente à medida que novos objetos forem adicionados ao esquema.</span><span class="sxs-lookup"><span data-stu-id="3485e-113">Once you set up access permissions for a schema, those permissions are automatically applied as new objects are added to the schema.</span></span> <span data-ttu-id="3485e-114">Os usuários podem ser atribuídos a um esquema padrão, e vários usuários do banco de dados podem compartilhar o mesmo esquema.</span><span class="sxs-lookup"><span data-stu-id="3485e-114">Users can be assigned a default schema, and multiple database users can share the same schema.</span></span>  
  
 <span data-ttu-id="3485e-115">Por padrão, quando os desenvolvedores criam objetos em um esquema, os objetos são possuídos pela entidade de segurança que possui o esquema, não pelo desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="3485e-115">By default, when developers create objects in a schema, the objects are owned by the security principal that owns the schema, not the developer.</span></span> <span data-ttu-id="3485e-116">A propriedade do objeto pode ser transferida com a instrução ALTER AUTHORIZATION do Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="3485e-116">Object ownership can be transferred with ALTER AUTHORIZATION Transact-SQL statement.</span></span> <span data-ttu-id="3485e-117">Um esquema também pode conter objetos que são possuídos por diferentes usuários e ter as permissões mais granulares que as atribuídas ao esquema, embora isso não seja recomendado porque adiciona complexidade a permissões de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="3485e-117">A schema can also contain objects that are owned by different users and have more granular permissions than those assigned to the schema, although this is not recommended because it adds complexity to managing permissions.</span></span> <span data-ttu-id="3485e-118">Os objetos podem ser movidos entre esquemas e a propriedade do esquema pode ser transferida entre entidades de segurança.</span><span class="sxs-lookup"><span data-stu-id="3485e-118">Objects can be moved between schemas, and schema ownership can be transferred between principals.</span></span> <span data-ttu-id="3485e-119">Os usuários do banco de dados podem ser removidos sem afetar esquemas.</span><span class="sxs-lookup"><span data-stu-id="3485e-119">Database users can be dropped without affecting schemas.</span></span>  
  
### <a name="built-in-schemas"></a><span data-ttu-id="3485e-120">Esquemas internos</span><span class="sxs-lookup"><span data-stu-id="3485e-120">Built-In Schemas</span></span>  
 <span data-ttu-id="3485e-121">O SQL Server vem com dez esquemas predefinidos que têm os mesmos nomes que os usuários e as funções internas do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3485e-121">SQL Server ships with ten pre-defined schemas that have the same names as the built-in database users and roles.</span></span> <span data-ttu-id="3485e-122">Eles existem principalmente para compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="3485e-122">These exist mainly for backward compatibility.</span></span> <span data-ttu-id="3485e-123">Você pode remover os esquemas que têm os mesmos nomes que as funções de banco de dados fixas se não precisar deles.</span><span class="sxs-lookup"><span data-stu-id="3485e-123">You can drop the schemas that have the same names as the fixed database roles if you do not need them.</span></span> <span data-ttu-id="3485e-124">Você não pode remover os esquemas a seguir:</span><span class="sxs-lookup"><span data-stu-id="3485e-124">You cannot drop the following schemas:</span></span>  
  
-   `dbo`  
  
-   `guest`  
  
-   `sys`  
  
-   `INFORMATION_SCHEMA`  
  
 <span data-ttu-id="3485e-125">Se você removê-los do banco de dados modelo, eles não aparecerão em novos bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="3485e-125">If you drop them from the model database, they will not appear in new databases.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3485e-126">Os esquemas `sys` e `INFORMATION_SCHEMA` são reservados para objetos do sistema.</span><span class="sxs-lookup"><span data-stu-id="3485e-126">The `sys` and `INFORMATION_SCHEMA` schemas are reserved for system objects.</span></span> <span data-ttu-id="3485e-127">Você não pode criar objetos nesses esquemas e não pode removê-los.</span><span class="sxs-lookup"><span data-stu-id="3485e-127">You cannot create objects in these schemas and you cannot drop them.</span></span>  
  
#### <a name="the-dbo-schema"></a><span data-ttu-id="3485e-128">O esquema dbo</span><span class="sxs-lookup"><span data-stu-id="3485e-128">The dbo Schema</span></span>  
 <span data-ttu-id="3485e-129">O esquema `dbo` é o esquema padrão para um banco de dados recém-criado.</span><span class="sxs-lookup"><span data-stu-id="3485e-129">The `dbo` schema is the default schema for a newly created database.</span></span> <span data-ttu-id="3485e-130">O esquema `dbo` é de propriedade da conta de usuário do `dbo`.</span><span class="sxs-lookup"><span data-stu-id="3485e-130">The `dbo` schema is owned by the `dbo` user account.</span></span> <span data-ttu-id="3485e-131">Por padrão, os usuários criados com o comando CREATE USER do Transact-SQL têm `dbo` como o esquema padrão.</span><span class="sxs-lookup"><span data-stu-id="3485e-131">By default, users created with the CREATE USER Transact-SQL command have `dbo` as their default schema.</span></span>  
  
 <span data-ttu-id="3485e-132">Os usuários que são atribuídos ao esquema `dbo` não herdam as permissões da conta de usuário do `dbo`.</span><span class="sxs-lookup"><span data-stu-id="3485e-132">Users who are assigned the `dbo` schema do not inherit the permissions of the `dbo` user account.</span></span> <span data-ttu-id="3485e-133">Nenhuma permissão é herdada de um esquema por usuários; as permissões de esquema são herdadas pelos objetos de banco de dados contidos no esquema.</span><span class="sxs-lookup"><span data-stu-id="3485e-133">No permissions are inherited from a schema by users; schema permissions are inherited by the database objects contained in the schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3485e-134">Quando os objetos de banco de dados são referenciados usando um nome de uma parte, o SQL Server primeiro procura no esquema padrão do usuário.</span><span class="sxs-lookup"><span data-stu-id="3485e-134">When database objects are referenced by using a one-part name, SQL Server first looks in the user's default schema.</span></span> <span data-ttu-id="3485e-135">Se o objeto não for encontrado lá, o SQL Server procurará em seguida no esquema `dbo`.</span><span class="sxs-lookup"><span data-stu-id="3485e-135">If the object is not found there, SQL Server looks next in the `dbo` schema.</span></span> <span data-ttu-id="3485e-136">Se o objeto não estiver no esquema `dbo`, um erro será retornado.</span><span class="sxs-lookup"><span data-stu-id="3485e-136">If the object is not in the `dbo` schema, an error is returned.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="3485e-137">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="3485e-137">External Resources</span></span>  
 <span data-ttu-id="3485e-138">Para obter mais informações sobre a propriedade e os esquemas do objeto, consulte os recursos a seguir.</span><span class="sxs-lookup"><span data-stu-id="3485e-138">For more information on object ownership and schemas, see the following resources.</span></span>  
  
|<span data-ttu-id="3485e-139">Recurso</span><span class="sxs-lookup"><span data-stu-id="3485e-139">Resource</span></span>|<span data-ttu-id="3485e-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="3485e-140">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="3485e-141">[Separação do esquema de usuário](http://msdn.microsoft.com/library/ms190387.aspx) nos Manuais Online do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3485e-141">[User-Schema Separation](http://msdn.microsoft.com/library/ms190387.aspx) in SQL Server Books Online</span></span>|<span data-ttu-id="3485e-142">Descreve as alterações introduzidas pela separação do esquema do usuário.</span><span class="sxs-lookup"><span data-stu-id="3485e-142">Describes the changes introduced by user-schema separation.</span></span> <span data-ttu-id="3485e-143">Inclui o novo comportamento, o seu impacto na propriedade, as exibições do catálogo e as permissões.</span><span class="sxs-lookup"><span data-stu-id="3485e-143">Includes new behavior, its impact on ownership, catalog views, and permissions.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3485e-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3485e-144">See Also</span></span>  
 <span data-ttu-id="3485e-145">[Securing ADO.NET Applications](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md) (Protegendo aplicativos ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="3485e-145">[Securing ADO.NET Applications](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)</span></span>  
 [<span data-ttu-id="3485e-146">Cenários de segurança do aplicativo no SQL Server</span><span class="sxs-lookup"><span data-stu-id="3485e-146">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="3485e-147">Autenticação no SQL Server</span><span class="sxs-lookup"><span data-stu-id="3485e-147">Authentication in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 [<span data-ttu-id="3485e-148">Servidor e funções de banco de dados no SQL Server</span><span class="sxs-lookup"><span data-stu-id="3485e-148">Server and Database Roles in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)  
 [<span data-ttu-id="3485e-149">Autorização e permissões no SQL Server</span><span class="sxs-lookup"><span data-stu-id="3485e-149">Authorization and Permissions in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)  
 <span data-ttu-id="3485e-150">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="3485e-150">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)</span></span>