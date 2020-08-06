---
title: 'Classe de evento TM: Rollback Tran Starting | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- 'TM: Rollback Tran Starting event class'
ms.assetid: 3b4d0d56-c51f-4f07-a116-5d4bd6ec1a3c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0492c7df719b9c6177c947d9848c95fc151ac093
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678763"
---
# <a name="tm-rollback-tran-starting-event-class"></a><span data-ttu-id="d632f-102">classe de evento TM: Rollback Tran Starting</span><span class="sxs-lookup"><span data-stu-id="d632f-102">TM: Rollback Tran Starting Event Class</span></span>
  <span data-ttu-id="d632f-103">A classe de evento TM: Rollback Tran Startingindica que uma solicitação de ROLLBACK TRANSACTION está iniciando.</span><span class="sxs-lookup"><span data-stu-id="d632f-103">The TM: Rollback Tran Starting event class indicates that a ROLLBACK TRANSACTION request is starting.</span></span> <span data-ttu-id="d632f-104">O cliente envia a solicitação pela interface de administração de transações.</span><span class="sxs-lookup"><span data-stu-id="d632f-104">The client sends the request through the transaction management interface.</span></span> <span data-ttu-id="d632f-105">A coluna EventSubClass indica se uma transação nova será iniciada depois que a transação atual for revertida.</span><span class="sxs-lookup"><span data-stu-id="d632f-105">The EventSubClass column indicates if a new transaction will be started after the current transaction is rolled back.</span></span>  
  
## <a name="tm-rollback-tran-starting-event-class-data-columns"></a><span data-ttu-id="d632f-106">Colunas de dados da classe de evento TM: Rollback Tran Starting</span><span class="sxs-lookup"><span data-stu-id="d632f-106">TM: Rollback Tran Starting Event Class Data Columns</span></span>  
  
|<span data-ttu-id="d632f-107">Nome da coluna de dados</span><span class="sxs-lookup"><span data-stu-id="d632f-107">Data column name</span></span>|<span data-ttu-id="d632f-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="d632f-108">Data type</span></span>|<span data-ttu-id="d632f-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="d632f-109">Description</span></span>|<span data-ttu-id="d632f-110">ID da coluna</span><span class="sxs-lookup"><span data-stu-id="d632f-110">Column ID</span></span>|<span data-ttu-id="d632f-111">Filtrável</span><span class="sxs-lookup"><span data-stu-id="d632f-111">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="d632f-112">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="d632f-112">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="d632f-113">Nome do aplicativo cliente que criou a conexão com uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d632f-113">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d632f-114">Essa coluna é populada com os valores passados pelo aplicativo e não com o nome exibido do programa.</span><span class="sxs-lookup"><span data-stu-id="d632f-114">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="d632f-115">10</span><span class="sxs-lookup"><span data-stu-id="d632f-115">10</span></span>|<span data-ttu-id="d632f-116">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-116">Yes</span></span>|  
|<span data-ttu-id="d632f-117">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="d632f-117">ClientProcessID</span></span>|`int`|<span data-ttu-id="d632f-118">ID atribuída pelo computador host ao processo em que o aplicativo cliente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="d632f-118">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="d632f-119">Essa coluna de dados será populada se a ID do processo do cliente for fornecida pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="d632f-119">This data column is populated if the client process ID is provided by the client.</span></span>|<span data-ttu-id="d632f-120">9</span><span class="sxs-lookup"><span data-stu-id="d632f-120">9</span></span>|<span data-ttu-id="d632f-121">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-121">Yes</span></span>|  
|<span data-ttu-id="d632f-122">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="d632f-122">DatabaseID</span></span>|`int`|<span data-ttu-id="d632f-123">ID do banco de dados especificado pela instrução USE de *database* ou o banco de dados padrão se nenhuma instrução USE de *database* tiver sido emitida para uma determinada instância.</span><span class="sxs-lookup"><span data-stu-id="d632f-123">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="d632f-124">exibirá o nome do banco de dados se a coluna de dados ServerName for capturada no rastreamento e o servidor estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="d632f-124">displays the name of the database if the ServerName data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="d632f-125">Determine o valor para um banco de dados usando a função DB_ID.</span><span class="sxs-lookup"><span data-stu-id="d632f-125">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="d632f-126">3</span><span class="sxs-lookup"><span data-stu-id="d632f-126">3</span></span>|<span data-ttu-id="d632f-127">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-127">Yes</span></span>|  
|<span data-ttu-id="d632f-128">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="d632f-128">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="d632f-129">Nome do banco de dados no qual a instrução do usuário está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="d632f-129">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="d632f-130">35</span><span class="sxs-lookup"><span data-stu-id="d632f-130">35</span></span>|<span data-ttu-id="d632f-131">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-131">Yes</span></span>|  
|<span data-ttu-id="d632f-132">EventClass</span><span class="sxs-lookup"><span data-stu-id="d632f-132">EventClass</span></span>|`int`|<span data-ttu-id="d632f-133">Tipo de evento = 187.</span><span class="sxs-lookup"><span data-stu-id="d632f-133">Type of event = 187.</span></span>|<span data-ttu-id="d632f-134">27</span><span class="sxs-lookup"><span data-stu-id="d632f-134">27</span></span>|<span data-ttu-id="d632f-135">Não</span><span class="sxs-lookup"><span data-stu-id="d632f-135">No</span></span>|  
|<span data-ttu-id="d632f-136">EventSequence</span><span class="sxs-lookup"><span data-stu-id="d632f-136">EventSequence</span></span>|`int`|<span data-ttu-id="d632f-137">A sequência de determinado evento dentro da solicitação.</span><span class="sxs-lookup"><span data-stu-id="d632f-137">The sequence of a given event within the request.</span></span>|<span data-ttu-id="d632f-138">51</span><span class="sxs-lookup"><span data-stu-id="d632f-138">51</span></span>|<span data-ttu-id="d632f-139">Não</span><span class="sxs-lookup"><span data-stu-id="d632f-139">No</span></span>|  
|<span data-ttu-id="d632f-140">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="d632f-140">EventSubClass</span></span>|`int`|<span data-ttu-id="d632f-141">Tipo de subclasse de evento.</span><span class="sxs-lookup"><span data-stu-id="d632f-141">Type of event subclass.</span></span><br /><br /> <span data-ttu-id="d632f-142">1=Rollback</span><span class="sxs-lookup"><span data-stu-id="d632f-142">1=Rollback</span></span><br /><br /> <span data-ttu-id="d632f-143">2=Rollback and Begin</span><span class="sxs-lookup"><span data-stu-id="d632f-143">2=Rollback and Begin</span></span>|<span data-ttu-id="d632f-144">21</span><span class="sxs-lookup"><span data-stu-id="d632f-144">21</span></span>|<span data-ttu-id="d632f-145">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-145">Yes</span></span>|  
|<span data-ttu-id="d632f-146">GroupID</span><span class="sxs-lookup"><span data-stu-id="d632f-146">GroupID</span></span>|`int`|<span data-ttu-id="d632f-147">ID do grupo de carga de trabalho no qual o evento de Rastreamento do SQL dispara.</span><span class="sxs-lookup"><span data-stu-id="d632f-147">ID of the workload group where the SQL Trace event fires.</span></span>|<span data-ttu-id="d632f-148">66</span><span class="sxs-lookup"><span data-stu-id="d632f-148">66</span></span>|<span data-ttu-id="d632f-149">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-149">Yes</span></span>|  
|<span data-ttu-id="d632f-150">HostName</span><span class="sxs-lookup"><span data-stu-id="d632f-150">HostName</span></span>|`nvarchar`|<span data-ttu-id="d632f-151">Nome do computador no qual o cliente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="d632f-151">Name of the computer on which the client is running.</span></span> <span data-ttu-id="d632f-152">Essa coluna de dados será populada se o cliente fornecer o nome do host.</span><span class="sxs-lookup"><span data-stu-id="d632f-152">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="d632f-153">Para determinar o nome do host, use a função HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="d632f-153">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="d632f-154">8</span><span class="sxs-lookup"><span data-stu-id="d632f-154">8</span></span>|<span data-ttu-id="d632f-155">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-155">Yes</span></span>|  
|<span data-ttu-id="d632f-156">IsSystem</span><span class="sxs-lookup"><span data-stu-id="d632f-156">IsSystem</span></span>|`int`|<span data-ttu-id="d632f-157">Indica se o evento ocorreu em um processo do sistema ou do usuário.</span><span class="sxs-lookup"><span data-stu-id="d632f-157">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="d632f-158">1 = sistema, 0 = usuário.</span><span class="sxs-lookup"><span data-stu-id="d632f-158">1 = system, 0 = user.</span></span>|<span data-ttu-id="d632f-159">60</span><span class="sxs-lookup"><span data-stu-id="d632f-159">60</span></span>|<span data-ttu-id="d632f-160">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-160">Yes</span></span>|  
|<span data-ttu-id="d632f-161">LoginName</span><span class="sxs-lookup"><span data-stu-id="d632f-161">LoginName</span></span>|`nvarchar`|<span data-ttu-id="d632f-162">Nome de logon do usuário (logon de segurança do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou as credenciais de logon do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows no formato DOMÍNIO/nomedousuário).</span><span class="sxs-lookup"><span data-stu-id="d632f-162">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="d632f-163">11</span><span class="sxs-lookup"><span data-stu-id="d632f-163">11</span></span>|<span data-ttu-id="d632f-164">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-164">Yes</span></span>|  
|<span data-ttu-id="d632f-165">LoginSid</span><span class="sxs-lookup"><span data-stu-id="d632f-165">LoginSid</span></span>|`image`|<span data-ttu-id="d632f-166">SID (identificador de segurança) do usuário que fez logon.</span><span class="sxs-lookup"><span data-stu-id="d632f-166">Security identifier (SID) of the logged-in user.</span></span> <span data-ttu-id="d632f-167">Você pode encontrar essas informações na exibição de catálogo sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="d632f-167">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="d632f-168">Cada SID é exclusivo para cada logon no servidor.</span><span class="sxs-lookup"><span data-stu-id="d632f-168">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="d632f-169">41</span><span class="sxs-lookup"><span data-stu-id="d632f-169">41</span></span>|<span data-ttu-id="d632f-170">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-170">Yes</span></span>|  
|<span data-ttu-id="d632f-171">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="d632f-171">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="d632f-172">O domínio do Windows ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="d632f-172">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="d632f-173">7</span><span class="sxs-lookup"><span data-stu-id="d632f-173">7</span></span>|<span data-ttu-id="d632f-174">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-174">Yes</span></span>|  
|<span data-ttu-id="d632f-175">NTUserName</span><span class="sxs-lookup"><span data-stu-id="d632f-175">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="d632f-176">Nome do usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="d632f-176">Windows user name.</span></span>|<span data-ttu-id="d632f-177">6</span><span class="sxs-lookup"><span data-stu-id="d632f-177">6</span></span>|<span data-ttu-id="d632f-178">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-178">Yes</span></span>|  
|<span data-ttu-id="d632f-179">RequestID</span><span class="sxs-lookup"><span data-stu-id="d632f-179">RequestID</span></span>|`int`|<span data-ttu-id="d632f-180">ID da solicitação que contém a instrução.</span><span class="sxs-lookup"><span data-stu-id="d632f-180">ID of the request containing the statement.</span></span>|<span data-ttu-id="d632f-181">49</span><span class="sxs-lookup"><span data-stu-id="d632f-181">49</span></span>|<span data-ttu-id="d632f-182">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-182">Yes</span></span>|  
|<span data-ttu-id="d632f-183">ServerName</span><span class="sxs-lookup"><span data-stu-id="d632f-183">ServerName</span></span>|`nvarchar`|<span data-ttu-id="d632f-184">Nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo rastreada.</span><span class="sxs-lookup"><span data-stu-id="d632f-184">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="d632f-185">26</span><span class="sxs-lookup"><span data-stu-id="d632f-185">26</span></span>|<span data-ttu-id="d632f-186">Não</span><span class="sxs-lookup"><span data-stu-id="d632f-186">No</span></span>|  
|<span data-ttu-id="d632f-187">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="d632f-187">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="d632f-188">Nome de logon do usuário que originou a sessão.</span><span class="sxs-lookup"><span data-stu-id="d632f-188">Login name of the user who originated the session.</span></span> <span data-ttu-id="d632f-189">Por exemplo, ao se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o Logon1 e executar uma instrução como Logon2, SessionLoginName mostrará o Logon1 e LoginName mostrará o Logon2.</span><span class="sxs-lookup"><span data-stu-id="d632f-189">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, SessionLoginName shows Login1 and LoginName shows Login2.</span></span> <span data-ttu-id="d632f-190">Essa coluna exibe logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do Windows.</span><span class="sxs-lookup"><span data-stu-id="d632f-190">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="d632f-191">64</span><span class="sxs-lookup"><span data-stu-id="d632f-191">64</span></span>|<span data-ttu-id="d632f-192">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-192">Yes</span></span>|  
|<span data-ttu-id="d632f-193">SPID</span><span class="sxs-lookup"><span data-stu-id="d632f-193">SPID</span></span>|`int`|<span data-ttu-id="d632f-194">Identificação da sessão em que ocorreu o evento.</span><span class="sxs-lookup"><span data-stu-id="d632f-194">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="d632f-195">12</span><span class="sxs-lookup"><span data-stu-id="d632f-195">12</span></span>|<span data-ttu-id="d632f-196">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-196">Yes</span></span>|  
|<span data-ttu-id="d632f-197">StartTime</span><span class="sxs-lookup"><span data-stu-id="d632f-197">StartTime</span></span>|`datetime`|<span data-ttu-id="d632f-198">Hora de início do evento, se disponível.</span><span class="sxs-lookup"><span data-stu-id="d632f-198">Time at which the event started, if available.</span></span>|<span data-ttu-id="d632f-199">14</span><span class="sxs-lookup"><span data-stu-id="d632f-199">14</span></span>|<span data-ttu-id="d632f-200">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-200">Yes</span></span>|  
|<span data-ttu-id="d632f-201">TextData</span><span class="sxs-lookup"><span data-stu-id="d632f-201">TextData</span></span>|`ntext`|<span data-ttu-id="d632f-202">Valor do texto dependente da classe de evento capturada no rastreamento.</span><span class="sxs-lookup"><span data-stu-id="d632f-202">Text value dependent on the event class captured in the trace.</span></span>|<span data-ttu-id="d632f-203">1</span><span class="sxs-lookup"><span data-stu-id="d632f-203">1</span></span>|<span data-ttu-id="d632f-204">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-204">Yes</span></span>|  
|<span data-ttu-id="d632f-205">TransactionID</span><span class="sxs-lookup"><span data-stu-id="d632f-205">TransactionID</span></span>|`bigint`|<span data-ttu-id="d632f-206">ID da transação atribuída pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="d632f-206">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="d632f-207">4</span><span class="sxs-lookup"><span data-stu-id="d632f-207">4</span></span>|<span data-ttu-id="d632f-208">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-208">Yes</span></span>|  
|<span data-ttu-id="d632f-209">XactSequence</span><span class="sxs-lookup"><span data-stu-id="d632f-209">XactSequence</span></span>|`bigint`|<span data-ttu-id="d632f-210">Token que descreve a transação atual.</span><span class="sxs-lookup"><span data-stu-id="d632f-210">Token that describes the current transaction.</span></span>|<span data-ttu-id="d632f-211">50</span><span class="sxs-lookup"><span data-stu-id="d632f-211">50</span></span>|<span data-ttu-id="d632f-212">Sim</span><span class="sxs-lookup"><span data-stu-id="d632f-212">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d632f-213">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d632f-213">See Also</span></span>  
 <span data-ttu-id="d632f-214">[Reverter transação &#40;&#41;Transact-SQL](/sql/t-sql/language-elements/rollback-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d632f-214">[ROLLBACK TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/rollback-transaction-transact-sql) </span></span>  
 [<span data-ttu-id="d632f-215">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d632f-215">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  