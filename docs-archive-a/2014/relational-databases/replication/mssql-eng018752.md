---
title: MSSQL_ENG018752 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG018752 error
ms.assetid: 405b2655-acb4-4e15-bcc6-b8f86bb22b37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fe62d540ea8e988cd4249112f196f75493a8f623
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685059"
---
# <a name="mssql_eng018752"></a><span data-ttu-id="e78bd-102">MSSQL_ENG018752</span><span class="sxs-lookup"><span data-stu-id="e78bd-102">MSSQL_ENG018752</span></span>
    
## <a name="message-details"></a><span data-ttu-id="e78bd-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="e78bd-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e78bd-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="e78bd-104">Product Name</span></span>|<span data-ttu-id="e78bd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e78bd-105">SQL Server</span></span>|  
|<span data-ttu-id="e78bd-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="e78bd-106">Event ID</span></span>|<span data-ttu-id="e78bd-107">18752</span><span class="sxs-lookup"><span data-stu-id="e78bd-107">18752</span></span>|  
|<span data-ttu-id="e78bd-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="e78bd-108">Event Source</span></span>|<span data-ttu-id="e78bd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e78bd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e78bd-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e78bd-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="e78bd-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="e78bd-111">Symbolic Name</span></span>||  
|<span data-ttu-id="e78bd-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="e78bd-112">Message Text</span></span>|<span data-ttu-id="e78bd-113">Somente um Agente de Leitor de Log ou um procedimento relacionado ao log (sp_repldone, sp_replcmds e sp_replshowcmds) pode se conectar ao banco de dados de cada vez.</span><span class="sxs-lookup"><span data-stu-id="e78bd-113">Only one Log Reader Agent or log-related procedure (sp_repldone, sp_replcmds, and sp_replshowcmds) can connect to a database at a time.</span></span> <span data-ttu-id="e78bd-114">Se você tiver executado um procedimento relacionado ao log, descarte a conexão através da qual o procedimento foi executado ou execute sp_replflush por essa conexão antes de iniciar o Agente de Leitor de Log ou de executar outro procedimento relacionado ao log.</span><span class="sxs-lookup"><span data-stu-id="e78bd-114">If you executed a log-related procedure, drop the connection over which the procedure was executed or execute sp_replflush over that connection before starting the Log Reader Agent or executing another log-related procedure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e78bd-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="e78bd-115">Explanation</span></span>  
 <span data-ttu-id="e78bd-116">Mais de uma conexão atual está tentando executar um dos seguintes: **sp_repldone**, **sp_replcmds**ou **sp_replshowcmds**.</span><span class="sxs-lookup"><span data-stu-id="e78bd-116">More than one current connection is trying to execute any of the following: **sp_repldone**, **sp_replcmds**, or **sp_replshowcmds**.</span></span> <span data-ttu-id="e78bd-117">Os procedimentos armazenados [sp_repldone &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-repldone-transact-sql) e [sp_replcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replcmds-transact-sql) são usados pelo Agente de Leitor de Log para localizar e atualizar informações sobre as transações replicadas em um banco de dados publicado.</span><span class="sxs-lookup"><span data-stu-id="e78bd-117">The stored procedures [sp_repldone &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-repldone-transact-sql) and [sp_replcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replcmds-transact-sql) are stored procedures used by the Log Reader Agent to locate and update information about replicated transactions in a published database.</span></span> <span data-ttu-id="e78bd-118">O procedimento armazenado [sp_replshowcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replshowcmds-transact-sql) é usado para solucionar alguns tipos de problemas com a replicação transacional.</span><span class="sxs-lookup"><span data-stu-id="e78bd-118">The stored procedure [sp_replshowcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replshowcmds-transact-sql) is used to troubleshoot certain types of issues with transactional replication.</span></span>  
  
 <span data-ttu-id="e78bd-119">Esse erro é gerado nas seguintes circunstâncias:</span><span class="sxs-lookup"><span data-stu-id="e78bd-119">This error is raised in the following circumstances:</span></span>  
  
-   <span data-ttu-id="e78bd-120">Se o Log Reader Agent de um banco de dados publicado estiver sendo executado e um segundo Log Reader Agent tentar ser executado no mesmo banco de dados, o erro será gerado para o segundo agente e será exibido no histórico do agente.</span><span class="sxs-lookup"><span data-stu-id="e78bd-120">If the Log Reader Agent for a published database is running and a second Log Reader Agent attempts to run against the same database, the error is raised for the second agent and appears in the agent history.</span></span>  
  
     <span data-ttu-id="e78bd-121">Em uma situação na qual há vários agentes, é possível que mais de um agente seja resultado de um processo órfão.</span><span class="sxs-lookup"><span data-stu-id="e78bd-121">In a situation where it appears there are multiple agents, it is possible that one of them is the result of an orphaned process.</span></span>  
  
-   <span data-ttu-id="e78bd-122">Se o Agente de Leitor de Log de um banco de dados publicado for iniciado e um usuário executar **sp_repldone**, **sp_replcmds**ou **sp_replshowcmds** no mesmo banco de dados, o erro será gerado no aplicativo em que o procedimento armazenado foi executado (como **sqlcmd**).</span><span class="sxs-lookup"><span data-stu-id="e78bd-122">If the Log Reader Agent for a published database is started and a user executes **sp_repldone**, **sp_replcmds**, or **sp_replshowcmds** against the same database, the error is raised in the application where the stored procedure was executed (such as **sqlcmd**).</span></span>  
  
-   <span data-ttu-id="e78bd-123">Se nenhum Log Reader Agent estiver sendo executado para um banco de dados publicado, um usuário executar **sp_repldone**, **sp_replcmds**ou **sp_replshowcmds** e a conexão na qual o procedimento foi executado não for encerrada, o erro será gerado quando o Log Reader Agent tentar se conectar ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e78bd-123">If no Log Reader Agent is running for a published database and a user executes **sp_repldone**, **sp_replcmds**, or **sp_replshowcmds** and then does not close the connection over which the procedure was executed, the error is raised when the Log Reader Agent attempts to connect to the database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e78bd-124">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="e78bd-124">User Action</span></span>  
 <span data-ttu-id="e78bd-125">As etapas a seguir podem ajudar a solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="e78bd-125">The following steps can help you to troubleshoot the problem.</span></span> <span data-ttu-id="e78bd-126">Se qualquer etapa permitir que o Log Reader Agent seja iniciado sem erros, não será necessário concluir as etapas restantes.</span><span class="sxs-lookup"><span data-stu-id="e78bd-126">If any step allows the Log Reader Agent to start without errors, there is no need to complete the remaining steps.</span></span>  
  
-   <span data-ttu-id="e78bd-127">Verifique o histórico do Log Reader Agent em relação a qualquer outro erro que poderia estar contribuindo com esse erro.</span><span class="sxs-lookup"><span data-stu-id="e78bd-127">Check the history of the Log Reader agent for any other errors that could be contributing to this error.</span></span> <span data-ttu-id="e78bd-128">Para obter informações sobre exibir detalhes de status e de erro do agente no Replication Monitor, confira [Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="e78bd-128">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="e78bd-129">Verifique o resultado de [sp_who &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-who-transact-sql) para obter os SPIDs (números de identificação do processo específico) conectados ao banco de dados publicado.</span><span class="sxs-lookup"><span data-stu-id="e78bd-129">Check the output of [sp_who &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-who-transact-sql) for specific process identification numbers (SPIDs) that are connected to the published database.</span></span> <span data-ttu-id="e78bd-130">Feche qualquer conexão que poderia haver executado **sp_repldone**, **sp_replcmds**ou **sp_replshowcmds**.</span><span class="sxs-lookup"><span data-stu-id="e78bd-130">Close any connections that might have run **sp_repldone**, **sp_replcmds**, or **sp_replshowcmds**.</span></span>  
  
-   <span data-ttu-id="e78bd-131">Reinicie o Agente de Leitor de Log.</span><span class="sxs-lookup"><span data-stu-id="e78bd-131">Restart the Log Reader Agent.</span></span> <span data-ttu-id="e78bd-132">Para obter mais informações, consulte [Iniciar e interromper um agente de replicação &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="e78bd-132">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
-   <span data-ttu-id="e78bd-133">Reinicie o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (offline ou online em um cluster) no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="e78bd-133">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service (bring it offline or online in a cluster) on the Distributor.</span></span> <span data-ttu-id="e78bd-134">Se houver a possibilidade de um trabalho agendado ter executado **sp_repldone**, **sp_replcmds**ou **sp_replshowcmds** de qualquer outra instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , também será necessário reiniciar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para essas instâncias.</span><span class="sxs-lookup"><span data-stu-id="e78bd-134">If there is possibility that a scheduled job could have executed **sp_repldone**, **sp_replcmds**, or **sp_replshowcmds** from any other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent for those instances as well.</span></span> <span data-ttu-id="e78bd-135">Para obter mais informações, consulte [Iniciar, parar ou pausar o serviço SQL Server Agent](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md).</span><span class="sxs-lookup"><span data-stu-id="e78bd-135">For more information, see [Start, Stop, or Pause the SQL Server Agent Service](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md).</span></span>  
  
-   <span data-ttu-id="e78bd-136">Execute [sp_replflush &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replflush-transact-sql) no Publicador do banco de dados de publicação e reinicie o Agente de Leitor de Log.</span><span class="sxs-lookup"><span data-stu-id="e78bd-136">Execute [sp_replflush &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replflush-transact-sql) at the Publisher on the publication database, and then restart the Log Reader Agent.</span></span>  
  
-   <span data-ttu-id="e78bd-137">Se o erro continuar ocorrendo, aumente o log do agente e especifique um arquivo de saída para o log.</span><span class="sxs-lookup"><span data-stu-id="e78bd-137">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="e78bd-138">Dependendo do contexto do erro, isso poderá fornecer as etapas que levaram ao erro e/ou as mensagens de erros adicionais.</span><span class="sxs-lookup"><span data-stu-id="e78bd-138">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e78bd-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e78bd-139">See Also</span></span>  
 <span data-ttu-id="e78bd-140">[Referência de erros e eventos &#40;Replicação&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="e78bd-140">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="e78bd-141">Agente do Leitor de Log de Replicação</span><span class="sxs-lookup"><span data-stu-id="e78bd-141">Replication Log Reader Agent</span></span>](agents/replication-log-reader-agent.md)  
  
  