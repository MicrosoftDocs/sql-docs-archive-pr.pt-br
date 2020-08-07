---
title: Gerenciamento de logons e trabalhos para os bancos de dados de um grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], failover
- failover [SQL Server], AlwaysOn Availability Groups
ms.assetid: d7da14d3-848c-44d4-8e49-d536a1158a61
author: rothja
ms.author: jroth
ms.openlocfilehash: 457f3ef946b5cfaf86a4a19774af63c5d7635882
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583771"
---
# <a name="management-of-logins-and-jobs-for-the-databases-of-an-availability-group-sql-server"></a><span data-ttu-id="d0fbe-102">Gerenciamento de logons e trabalhos para os bancos de dados de um grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d0fbe-102">Management of Logins and Jobs for the Databases of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="d0fbe-103">Você deve manter o mesmo conjunto de logons de usuários e trabalhos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent rotineiramente em todo banco de dados primário de um grupo de disponibilidade AlwaysOn e nos bancos de dados secundários correspondentes.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-103">You should routinely maintain the same set of user logins and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs on every primary database of an AlwaysOn availability group and the corresponding secondary databases.</span></span> <span data-ttu-id="d0fbe-104">Os logons e trabalhos devem ser reproduzidos em toda instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que hospede uma réplica de disponibilidade para o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-104">The logins and jobs must be reproduced on every instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that hosts an availability replica for the availability group.</span></span>  
  
-   <span data-ttu-id="d0fbe-105">**[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]Trabalhos do Agent**</span><span class="sxs-lookup"><span data-stu-id="d0fbe-105">**[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs**</span></span>  
  
     <span data-ttu-id="d0fbe-106">Você precisa copiar manualmente trabalhos relevantes da instância de servidor que hospeda a réplica primária original nas instâncias de servidor que hospedam as réplicas secundárias originais.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-106">You need to manually copy relevant jobs from the server instance that hosts the original primary replica to the server instances that host the original secondary replicas.</span></span> <span data-ttu-id="d0fbe-107">Para todos os bancos de dados, você precisa adicionar lógica no início de cada trabalho relevante para que o trabalho seja executado somente no banco de dados primário, ou seja, apenas quando a réplica local for a réplica primária do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-107">For all databases, you need to add logic at the beginning of each relevant job to make the job execute only on the primary database, that is, only when the local replica is the primary replica for the database.</span></span>  
  
     <span data-ttu-id="d0fbe-108">As instâncias de servidor que hospedam as réplicas de disponibilidade de um grupo de disponibilidade podem ser configuradas de maneira diferente, com diferentes letras de unidade de fita ou algo assim.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-108">The server instances that host the availability replicas of an availability group might be configured differently, with different tape drive letters or such.</span></span> <span data-ttu-id="d0fbe-109">Os trabalhos de cada réplica de disponibilidade devem permitir essas diferenças.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-109">The jobs for each availability replica must allow for any such differences.</span></span>  
  
     <span data-ttu-id="d0fbe-110">Observe que os trabalhos de backup podem usar a função [sys.fn_hadr_is_preferred_backup_replica](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql) para identificar se a réplica local é a preferencial para backups, de acordo com as preferências de backup do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-110">Notice that backup jobs can use the [sys.fn_hadr_is_preferred_backup_replica](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql) function to identify whether the local replica is the preferred one for backups, according to the availability group backup preferences.</span></span> <span data-ttu-id="d0fbe-111">Os trabalhos de backup criados usando o [Assistente de Plano de Manutenção](../relational-databases/maintenance-plans/use-the-maintenance-plan-wizard.md) nativamente usam essa função.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-111">Backup jobs created using the [Maintenance Plan Wizard](../relational-databases/maintenance-plans/use-the-maintenance-plan-wizard.md) natively use this function.</span></span> <span data-ttu-id="d0fbe-112">Para outros trabalhos de backup, recomendamos o uso dessa função como condição em seus trabalhos de backup, de forma que eles sejam executados apenas na réplica preferencial.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-112">For other backup jobs, we recommend that you use this function as a condition in your backup jobs, so they execute only on the preferred replica.</span></span> <span data-ttu-id="d0fbe-113">Para obter mais informações, consulte secundários [ativos: backup em réplicas secundárias (grupos de disponibilidade AlwaysOn)](availability-groups/windows/active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="d0fbe-113">For more information, see [Active Secondaries: Backup on Secondary Replicas (AlwaysOn Availability Groups)](availability-groups/windows/active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
-   <span data-ttu-id="d0fbe-114">**Logons**</span><span class="sxs-lookup"><span data-stu-id="d0fbe-114">**Logins**</span></span>  
  
     <span data-ttu-id="d0fbe-115">Se você estiver usando bancos de dados independentes, poderá configurar usuários independentes nos bancos de dados e, para esses usuários, não precisará criar logons nas instâncias do servidor que hospedam uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-115">If you are using contained databases, you can configure contained users in the databases, and for these users, you do not need to create logins on the server instances that host a secondary replica.</span></span> <span data-ttu-id="d0fbe-116">Para um banco de dados de disponibilidade dependente, você precisará criar usuários para os logons nas instâncias do servidor que hospedam as réplicas de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-116">For a non-contained availability database, you will need to create users for the logins on the server instances that host the availability replicas.</span></span> <span data-ttu-id="d0fbe-117">Para obter mais informações, consulte [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d0fbe-117">For more information, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
     <span data-ttu-id="d0fbe-118">Se qualquer um dos seus aplicativos usam [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Autenticação ou um logon local do Windows, consulte [Os logons dos aplicativos que usam a autenticação do SQL Server ou Logon local do Windows](../../2014/database-engine/logins-and-jobs-for-availability-group-databases.md#SSauthentication), mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-118">If any of your applications use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication or a local Windows login, see [Logins Of Applications That Use SQL Server Authentication or a Local Windows Login](../../2014/database-engine/logins-and-jobs-for-availability-group-databases.md#SSauthentication), later in this topic.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d0fbe-119">Um usuário de banco de dados para o qual o logon do SQL Server não está definido ou está definido incorretamente em uma instância do servidor não pode fazer logon na instância.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-119">A database user for which the SQL Server login is undefined or is incorrectly defined on a server instance cannot log in to the instance.</span></span> <span data-ttu-id="d0fbe-120">Esse usuário é um *usuário órfão* do banco de dados nessa instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-120">Such a user is said to be an *orphaned user* of the database on that server instance.</span></span> <span data-ttu-id="d0fbe-121">Se um usuário se tornar órfão em uma determinada instância de servidor, você poderá configurar os logons de usuários a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-121">If a user is orphaned on a given server instance, you can set up the user logins at any time.</span></span> <span data-ttu-id="d0fbe-122">Para obter mais informações, consulte [Solução de problemas de usuários órfãos &#40;SQL Server&#41;](../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d0fbe-122">For more information, see [Troubleshoot Orphaned Users &#40;SQL Server&#41;](../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md).</span></span>  
  
-   <span data-ttu-id="d0fbe-123">**Metadados adicionais**</span><span class="sxs-lookup"><span data-stu-id="d0fbe-123">**Additional metadata**</span></span>  
  
     <span data-ttu-id="d0fbe-124">Os logons e os trabalhos não são as únicas informações que precisam ser recriadas em cada instância de servidor que hospeda uma réplica secundária para determinado grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-124">Logins and jobs are not the only information that need to be recreated on each of the server instances that hosts an secondary replica for a given availability group.</span></span> <span data-ttu-id="d0fbe-125">Por exemplo, talvez você precise recriar parâmetros de configuração de servidor, credenciais, dados criptografados, permissões, configurações de replicação, aplicativos do service broker, gatilhos (em nível de servidor) e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-125">For example, you might need to recreate server configuration settings, credentials, encrypted data, permissions, replication settings, service broker applications, triggers (at server level), and so forth.</span></span> <span data-ttu-id="d0fbe-126">Para obter mais informações, consulte [Gerenciar metadados ao disponibilizar um banco de dados em outra instância do servidor &#40;SQL Server&#41;](../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="d0fbe-126">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
##  <a name="logins-of-applications-that-use-sql-server-authentication-or-a-local-windows-login"></a><a name="SSauthentication"></a> <span data-ttu-id="d0fbe-127">Os logons dos aplicativos que usam a autenticação do SQL Server ou Logon local do Windows</span><span class="sxs-lookup"><span data-stu-id="d0fbe-127">Logins Of Applications That Use SQL Server Authentication or a Local Windows Login</span></span>  
 <span data-ttu-id="d0fbe-128">Se um aplicativo usar a autenticação do SQL Server ou um logon local do Windows, as SIDs incompatíveis poderão impedir que o logon do aplicativo seja resolvido em uma instância remota do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0fbe-128">If an application uses SQL Server Authentication or a local Windows login, mismatched SIDs can prevent the application's login from resolving on a remote instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d0fbe-129">As SIDs incompatíveis fazem o logon se tornar um usuário órfão na instância do servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-129">The mismatched SIDs cause the login to become an orphaned user on the remote server instance.</span></span> <span data-ttu-id="d0fbe-130">Esse problema pode ocorrer quando um aplicativo se conectar a um banco de dados espelhado ou de envio de logs depois de um failover ou a um banco de dados de assinante de replicação que foi inicializado de um backup.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-130">This issue can occur when an application connects to a mirrored or log shipping database after a failover or to a replication subscriber database that was initialized from a backup.</span></span>  
  
 <span data-ttu-id="d0fbe-131">Para evitar esse problema, recomendamos que você tome medidas preventivas quando configurar esse aplicativo para usar um banco de dados que seja hospedado por uma instância remota do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0fbe-131">To prevent this issue, we recommend that you take preventative measures when you set up such an application to use a database that is hosted by a remote instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d0fbe-132">A prevenção envolve transferir os logons e as senhas da instância local do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para a instância remota do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0fbe-132">Prevention involves transferring the logins and the passwords from the local instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to the remote instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d0fbe-133">Para obter mais informações sobre como evitar esse problema, consulte o artigo da base de dados 918992-[como transferir os logons e as senhas entre instâncias do SQL Server](https://support.microsoft.com/kb/918992/)).</span><span class="sxs-lookup"><span data-stu-id="d0fbe-133">For more information about how to prevent this issue, see KB article 918992-[How to transfer the logins and the passwords between instances of SQL Server](https://support.microsoft.com/kb/918992/)).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d0fbe-134">Esse problema afeta contas locais do windows em computadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-134">This problem affects Windows local accounts on different computers.</span></span> <span data-ttu-id="d0fbe-135">No entanto, esse problema não ocorre para contas de domínio porque o SID será o mesmo em cada computador.</span><span class="sxs-lookup"><span data-stu-id="d0fbe-135">However, this problem does not occur for domain accounts because the SID is the same on each of the computers.</span></span>  
  
 <span data-ttu-id="d0fbe-136">Para obter mais informações, consulte [Usuários órfãos com espelhamento de banco de dados e envio de logs](https://blogs.msdn.com/b/sqlserverfaq/archive/2009/04/13/orphaned-users-with-database-mirroring-and-log-shipping.aspx) (um blog do mecanismo de banco de dados).</span><span class="sxs-lookup"><span data-stu-id="d0fbe-136">For more information, see [Orphaned Users with Database Mirroring and Log Shipping](https://blogs.msdn.com/b/sqlserverfaq/archive/2009/04/13/orphaned-users-with-database-mirroring-and-log-shipping.aspx) (a Database Engine blog).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d0fbe-137">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="d0fbe-137">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d0fbe-138">Criar um logon</span><span class="sxs-lookup"><span data-stu-id="d0fbe-138">Create a Login</span></span>](../relational-databases/security/authentication-access/create-a-login.md)  
  
-   <span data-ttu-id="d0fbe-139">[Crie um usuário de banco de dados](../relational-databases/security/authentication-access/create-a-database-user.md).</span><span class="sxs-lookup"><span data-stu-id="d0fbe-139">[Create a Database User](../relational-databases/security/authentication-access/create-a-database-user.md).</span></span>  
  
-   [<span data-ttu-id="d0fbe-140">Criar um trabalho</span><span class="sxs-lookup"><span data-stu-id="d0fbe-140">Create a Job</span></span>](../ssms/agent/create-a-job.md)  
  
-   [<span data-ttu-id="d0fbe-141">Gerenciar metadados ao disponibilizar um banco de dados em outra instância do servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d0fbe-141">Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;</span></span>](../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="d0fbe-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d0fbe-142">See Also</span></span>  
 <span data-ttu-id="d0fbe-143">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d0fbe-143">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="d0fbe-144">[Bancos de dados independentes](../relational-databases/databases/contained-databases.md) </span><span class="sxs-lookup"><span data-stu-id="d0fbe-144">[Contained Databases](../relational-databases/databases/contained-databases.md) </span></span>  
 [<span data-ttu-id="d0fbe-145">Criar trabalhos</span><span class="sxs-lookup"><span data-stu-id="d0fbe-145">Create Jobs</span></span>](../ssms/agent/create-jobs.md)  
  
  