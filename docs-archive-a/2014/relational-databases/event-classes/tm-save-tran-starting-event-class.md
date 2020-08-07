---
title: 'Classe de evento TM: Save Tran Starting | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- 'TM: Save Tran Starting event class'
ms.assetid: 6f19fe7c-a452-4323-b957-7e17d13bf8fd
author: stevestein
ms.author: sstein
ms.openlocfilehash: bc2bf8c781df287bf499f4a6d10bdd572c4129ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583592"
---
# <a name="tm-save-tran-starting-event-class"></a><span data-ttu-id="6ba78-102">classe de evento TM: Save Tran Starting</span><span class="sxs-lookup"><span data-stu-id="6ba78-102">TM: Save Tran Starting Event Class</span></span>
  <span data-ttu-id="6ba78-103">A classe de evento TM: SaveTran Starting indica que uma solicitação SAVE TRANSACTION está sendo iniciada.</span><span class="sxs-lookup"><span data-stu-id="6ba78-103">The TM: Save Tran Starting event class indicates that a SAVE TRANSACTION request is starting.</span></span> <span data-ttu-id="6ba78-104">A solicitação é enviada do cliente pela interface de gerenciamento de transações.</span><span class="sxs-lookup"><span data-stu-id="6ba78-104">The request is sent from the client through a transaction management interface.</span></span>  
  
## <a name="tm-save-tran-starting-event-class-data-columns"></a><span data-ttu-id="6ba78-105">Colunas de dados da classe de evento TM: Save Tran Starting</span><span class="sxs-lookup"><span data-stu-id="6ba78-105">TM: Save Tran Starting Event Class Data Columns</span></span>  
  
|<span data-ttu-id="6ba78-106">Nome da coluna de dados</span><span class="sxs-lookup"><span data-stu-id="6ba78-106">Data column name</span></span>|<span data-ttu-id="6ba78-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="6ba78-107">Data type</span></span>|<span data-ttu-id="6ba78-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="6ba78-108">Description</span></span>|<span data-ttu-id="6ba78-109">ID da coluna</span><span class="sxs-lookup"><span data-stu-id="6ba78-109">Column ID</span></span>|<span data-ttu-id="6ba78-110">Filtrável</span><span class="sxs-lookup"><span data-stu-id="6ba78-110">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="6ba78-111">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="6ba78-111">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="6ba78-112">Nome do aplicativo cliente que criou a conexão com uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6ba78-112">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6ba78-113">Essa coluna é populada com os valores passados pelo aplicativo e não com o nome exibido do programa.</span><span class="sxs-lookup"><span data-stu-id="6ba78-113">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="6ba78-114">10</span><span class="sxs-lookup"><span data-stu-id="6ba78-114">10</span></span>|<span data-ttu-id="6ba78-115">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-115">Yes</span></span>|  
|<span data-ttu-id="6ba78-116">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="6ba78-116">ClientProcessID</span></span>|`int`|<span data-ttu-id="6ba78-117">ID atribuída pelo computador host ao processo em que o aplicativo cliente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="6ba78-117">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="6ba78-118">Essa coluna de dados será populada se a ID do processo do cliente for fornecida pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="6ba78-118">This data column is populated if the client process ID is provided by the client.</span></span>|<span data-ttu-id="6ba78-119">9</span><span class="sxs-lookup"><span data-stu-id="6ba78-119">9</span></span>|<span data-ttu-id="6ba78-120">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-120">Yes</span></span>|  
|<span data-ttu-id="6ba78-121">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="6ba78-121">DatabaseID</span></span>|`int`|<span data-ttu-id="6ba78-122">ID do banco de dados especificado pela instrução USE de *database* ou o banco de dados padrão se nenhuma instrução USE de *database* tiver sido emitida para uma determinada instância.</span><span class="sxs-lookup"><span data-stu-id="6ba78-122">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="6ba78-123">exibirá o nome do banco de dados se a coluna de dados ServerName for capturada no rastreamento e o servidor estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="6ba78-123">displays the name of the database if the ServerName data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="6ba78-124">Determine o valor para um banco de dados usando a função DB_ID.</span><span class="sxs-lookup"><span data-stu-id="6ba78-124">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="6ba78-125">3</span><span class="sxs-lookup"><span data-stu-id="6ba78-125">3</span></span>|<span data-ttu-id="6ba78-126">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-126">Yes</span></span>|  
|<span data-ttu-id="6ba78-127">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="6ba78-127">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="6ba78-128">Nome do banco de dados no qual a instrução do usuário está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="6ba78-128">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="6ba78-129">35</span><span class="sxs-lookup"><span data-stu-id="6ba78-129">35</span></span>|<span data-ttu-id="6ba78-130">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-130">Yes</span></span>|  
|<span data-ttu-id="6ba78-131">EventClass</span><span class="sxs-lookup"><span data-stu-id="6ba78-131">EventClass</span></span>|`int`|<span data-ttu-id="6ba78-132">Tipo de evento = 191.</span><span class="sxs-lookup"><span data-stu-id="6ba78-132">Type of event = 191.</span></span>|<span data-ttu-id="6ba78-133">27</span><span class="sxs-lookup"><span data-stu-id="6ba78-133">27</span></span>|<span data-ttu-id="6ba78-134">Não</span><span class="sxs-lookup"><span data-stu-id="6ba78-134">No</span></span>|  
|<span data-ttu-id="6ba78-135">EventSequence</span><span class="sxs-lookup"><span data-stu-id="6ba78-135">EventSequence</span></span>|`int`|<span data-ttu-id="6ba78-136">A sequência de determinado evento dentro da solicitação.</span><span class="sxs-lookup"><span data-stu-id="6ba78-136">The sequence of a given event within the request.</span></span>|<span data-ttu-id="6ba78-137">51</span><span class="sxs-lookup"><span data-stu-id="6ba78-137">51</span></span>|<span data-ttu-id="6ba78-138">Não</span><span class="sxs-lookup"><span data-stu-id="6ba78-138">No</span></span>|  
|<span data-ttu-id="6ba78-139">GroupID</span><span class="sxs-lookup"><span data-stu-id="6ba78-139">GroupID</span></span>|`int`|<span data-ttu-id="6ba78-140">ID do grupo de carga de trabalho no qual o evento de Rastreamento do SQL dispara.</span><span class="sxs-lookup"><span data-stu-id="6ba78-140">ID of the workload group where the SQL Trace event fires.</span></span>|<span data-ttu-id="6ba78-141">66</span><span class="sxs-lookup"><span data-stu-id="6ba78-141">66</span></span>|<span data-ttu-id="6ba78-142">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-142">Yes</span></span>|  
|<span data-ttu-id="6ba78-143">HostName</span><span class="sxs-lookup"><span data-stu-id="6ba78-143">HostName</span></span>|`nvarchar`|<span data-ttu-id="6ba78-144">Nome do computador no qual o cliente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="6ba78-144">Name of the computer on which the client is running.</span></span> <span data-ttu-id="6ba78-145">Essa coluna de dados será populada se o cliente fornecer o nome do host.</span><span class="sxs-lookup"><span data-stu-id="6ba78-145">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="6ba78-146">Para determinar o nome do host, use a função HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="6ba78-146">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="6ba78-147">8</span><span class="sxs-lookup"><span data-stu-id="6ba78-147">8</span></span>|<span data-ttu-id="6ba78-148">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-148">Yes</span></span>|  
|<span data-ttu-id="6ba78-149">IsSystem</span><span class="sxs-lookup"><span data-stu-id="6ba78-149">IsSystem</span></span>|`int`|<span data-ttu-id="6ba78-150">Indica se o evento ocorreu em um processo do sistema ou do usuário.</span><span class="sxs-lookup"><span data-stu-id="6ba78-150">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="6ba78-151">1 = sistema, 0 = usuário.</span><span class="sxs-lookup"><span data-stu-id="6ba78-151">1 = system, 0 = user.</span></span>|<span data-ttu-id="6ba78-152">60</span><span class="sxs-lookup"><span data-stu-id="6ba78-152">60</span></span>|<span data-ttu-id="6ba78-153">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-153">Yes</span></span>|  
|<span data-ttu-id="6ba78-154">LoginName</span><span class="sxs-lookup"><span data-stu-id="6ba78-154">LoginName</span></span>|`nvarchar`|<span data-ttu-id="6ba78-155">Nome de logon do usuário (logon de segurança do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou as credenciais de logon do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows no formato DOMÍNIO/nomedousuário).</span><span class="sxs-lookup"><span data-stu-id="6ba78-155">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="6ba78-156">11</span><span class="sxs-lookup"><span data-stu-id="6ba78-156">11</span></span>|<span data-ttu-id="6ba78-157">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-157">Yes</span></span>|  
|<span data-ttu-id="6ba78-158">LoginSid</span><span class="sxs-lookup"><span data-stu-id="6ba78-158">LoginSid</span></span>|`image`|<span data-ttu-id="6ba78-159">SID (identificador de segurança) do usuário que fez logon.</span><span class="sxs-lookup"><span data-stu-id="6ba78-159">Security identifier (SID) of the logged-in user.</span></span> <span data-ttu-id="6ba78-160">Você pode encontrar essas informações na exibição de catálogo sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="6ba78-160">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="6ba78-161">Cada SID é exclusivo para cada logon no servidor.</span><span class="sxs-lookup"><span data-stu-id="6ba78-161">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="6ba78-162">41</span><span class="sxs-lookup"><span data-stu-id="6ba78-162">41</span></span>|<span data-ttu-id="6ba78-163">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-163">Yes</span></span>|  
|<span data-ttu-id="6ba78-164">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="6ba78-164">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="6ba78-165">O domínio do Windows ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="6ba78-165">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="6ba78-166">7</span><span class="sxs-lookup"><span data-stu-id="6ba78-166">7</span></span>|<span data-ttu-id="6ba78-167">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-167">Yes</span></span>|  
|<span data-ttu-id="6ba78-168">NTUserName</span><span class="sxs-lookup"><span data-stu-id="6ba78-168">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="6ba78-169">Nome do usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="6ba78-169">Windows user name.</span></span>|<span data-ttu-id="6ba78-170">6</span><span class="sxs-lookup"><span data-stu-id="6ba78-170">6</span></span>|<span data-ttu-id="6ba78-171">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-171">Yes</span></span>|  
|<span data-ttu-id="6ba78-172">RequestID</span><span class="sxs-lookup"><span data-stu-id="6ba78-172">RequestID</span></span>|`int`|<span data-ttu-id="6ba78-173">O ID da solicitação que contém a instrução.</span><span class="sxs-lookup"><span data-stu-id="6ba78-173">The ID of the request containing the statement.</span></span>|<span data-ttu-id="6ba78-174">49</span><span class="sxs-lookup"><span data-stu-id="6ba78-174">49</span></span>|<span data-ttu-id="6ba78-175">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-175">Yes</span></span>|  
|<span data-ttu-id="6ba78-176">ServerName</span><span class="sxs-lookup"><span data-stu-id="6ba78-176">ServerName</span></span>|`nvarchar`|<span data-ttu-id="6ba78-177">Nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo rastreada.</span><span class="sxs-lookup"><span data-stu-id="6ba78-177">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="6ba78-178">26</span><span class="sxs-lookup"><span data-stu-id="6ba78-178">26</span></span>|<span data-ttu-id="6ba78-179">Não</span><span class="sxs-lookup"><span data-stu-id="6ba78-179">No</span></span>|  
|<span data-ttu-id="6ba78-180">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="6ba78-180">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="6ba78-181">O nome de logon do usuário que originou a sessão.</span><span class="sxs-lookup"><span data-stu-id="6ba78-181">The login name of the user who originated the session.</span></span> <span data-ttu-id="6ba78-182">Por exemplo, ao se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o Logon1 e executar uma instrução como Logon2, SessionLoginName mostrará o Logon1 e LoginName mostrará o Logon2.</span><span class="sxs-lookup"><span data-stu-id="6ba78-182">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, SessionLoginName shows Login1 and LoginName shows Login2.</span></span> <span data-ttu-id="6ba78-183">Essa coluna exibe logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do Windows.</span><span class="sxs-lookup"><span data-stu-id="6ba78-183">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="6ba78-184">64</span><span class="sxs-lookup"><span data-stu-id="6ba78-184">64</span></span>|<span data-ttu-id="6ba78-185">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-185">Yes</span></span>|  
|<span data-ttu-id="6ba78-186">SPID</span><span class="sxs-lookup"><span data-stu-id="6ba78-186">SPID</span></span>|`int`|<span data-ttu-id="6ba78-187">Identificação da sessão em que ocorreu o evento.</span><span class="sxs-lookup"><span data-stu-id="6ba78-187">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="6ba78-188">12</span><span class="sxs-lookup"><span data-stu-id="6ba78-188">12</span></span>|<span data-ttu-id="6ba78-189">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-189">Yes</span></span>|  
|<span data-ttu-id="6ba78-190">StartTime</span><span class="sxs-lookup"><span data-stu-id="6ba78-190">StartTime</span></span>|`datetime`|<span data-ttu-id="6ba78-191">Horário de início do evento, quando disponível.</span><span class="sxs-lookup"><span data-stu-id="6ba78-191">Time at which the event started, when available.</span></span>|<span data-ttu-id="6ba78-192">14</span><span class="sxs-lookup"><span data-stu-id="6ba78-192">14</span></span>|<span data-ttu-id="6ba78-193">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-193">Yes</span></span>|  
|<span data-ttu-id="6ba78-194">TextData</span><span class="sxs-lookup"><span data-stu-id="6ba78-194">TextData</span></span>|`ntext`|<span data-ttu-id="6ba78-195">Valor do texto dependente da classe de evento capturada no rastreamento.</span><span class="sxs-lookup"><span data-stu-id="6ba78-195">Text value dependent on the event class captured in the trace.</span></span>|<span data-ttu-id="6ba78-196">1</span><span class="sxs-lookup"><span data-stu-id="6ba78-196">1</span></span>|<span data-ttu-id="6ba78-197">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-197">Yes</span></span>|  
|<span data-ttu-id="6ba78-198">TransactionID</span><span class="sxs-lookup"><span data-stu-id="6ba78-198">TransactionID</span></span>|`bigint`|<span data-ttu-id="6ba78-199">ID da transação atribuída pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="6ba78-199">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="6ba78-200">4</span><span class="sxs-lookup"><span data-stu-id="6ba78-200">4</span></span>|<span data-ttu-id="6ba78-201">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-201">Yes</span></span>|  
|<span data-ttu-id="6ba78-202">XactSequence</span><span class="sxs-lookup"><span data-stu-id="6ba78-202">XactSequence</span></span>|`bigint`|<span data-ttu-id="6ba78-203">Token que descreve a transação atual.</span><span class="sxs-lookup"><span data-stu-id="6ba78-203">Token that describes the current transaction.</span></span>|<span data-ttu-id="6ba78-204">50</span><span class="sxs-lookup"><span data-stu-id="6ba78-204">50</span></span>|<span data-ttu-id="6ba78-205">Sim</span><span class="sxs-lookup"><span data-stu-id="6ba78-205">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ba78-206">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6ba78-206">See Also</span></span>  
 <span data-ttu-id="6ba78-207">[Eventos estendidos](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="6ba78-207">[Extended Events](../extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="6ba78-208">[SALVAR transação &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/save-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6ba78-208">[SAVE TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/save-transaction-transact-sql) </span></span>  
 [<span data-ttu-id="6ba78-209">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6ba78-209">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  