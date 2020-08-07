---
title: Classe de evento SP:CacheRemove | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SP:CacheRemove event class
ms.assetid: aaa3c5c4-2d3a-4832-a473-ce9bd4fb1c17
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4d0d1a88c7a40bfd10b206e971d22c57ac6cd035
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575129"
---
# <a name="spcacheremove-event-class"></a><span data-ttu-id="c3ae2-102">Classe de evento SP:CacheRemove</span><span class="sxs-lookup"><span data-stu-id="c3ae2-102">SP:CacheRemove Event Class</span></span>
  <span data-ttu-id="c3ae2-103">A classe de evento SP:CacheRemove indica que o procedimento armazenado foi removido do cache do plano.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-103">The SP:CacheRemove event class indicates that the stored procedure has been removed from the plan cache.</span></span>  
  
## <a name="spcacheremove-event-class-data-columns"></a><span data-ttu-id="c3ae2-104">Colunas de dados da classe de evento SP:CacheRemove</span><span class="sxs-lookup"><span data-stu-id="c3ae2-104">SP:CacheRemove Event Class Data Columns</span></span>  
  
|<span data-ttu-id="c3ae2-105">Nome da coluna de dados</span><span class="sxs-lookup"><span data-stu-id="c3ae2-105">Data column name</span></span>|`Data type`|<span data-ttu-id="c3ae2-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="c3ae2-106">Description</span></span>|<span data-ttu-id="c3ae2-107">ID da coluna</span><span class="sxs-lookup"><span data-stu-id="c3ae2-107">Column ID</span></span>|<span data-ttu-id="c3ae2-108">Filtrável</span><span class="sxs-lookup"><span data-stu-id="c3ae2-108">Filterable</span></span>|  
|----------------------|-------------------|-----------------|---------------|----------------|  
|<span data-ttu-id="c3ae2-109">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="c3ae2-109">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="c3ae2-110">Nome do aplicativo cliente que criou a conexão com uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3ae2-110">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c3ae2-111">Essa coluna é populada com os valores passados pelo aplicativo e não com o nome exibido do programa.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-111">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="c3ae2-112">10</span><span class="sxs-lookup"><span data-stu-id="c3ae2-112">10</span></span>|<span data-ttu-id="c3ae2-113">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-113">Yes</span></span>|  
|<span data-ttu-id="c3ae2-114">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="c3ae2-114">ClientProcessID</span></span>|`int`|<span data-ttu-id="c3ae2-115">ID atribuída pelo computador host ao processo em que o aplicativo cliente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-115">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="c3ae2-116">Essa coluna de dados será populada se o cliente fornecer a ID de processo do cliente.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-116">This data column is populated if the client provides the client process ID.</span></span>|<span data-ttu-id="c3ae2-117">9</span><span class="sxs-lookup"><span data-stu-id="c3ae2-117">9</span></span>|<span data-ttu-id="c3ae2-118">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-118">Yes</span></span>|  
|<span data-ttu-id="c3ae2-119">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="c3ae2-119">DatabaseID</span></span>|`int`|<span data-ttu-id="c3ae2-120">ID do banco de dados em que o procedimento armazenado está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-120">ID of the database in which the stored procedure is running.</span></span> <span data-ttu-id="c3ae2-121">Determine o valor para um banco de dados usando a função DB_ID.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-121">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="c3ae2-122">3</span><span class="sxs-lookup"><span data-stu-id="c3ae2-122">3</span></span>|<span data-ttu-id="c3ae2-123">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-123">Yes</span></span>|  
|<span data-ttu-id="c3ae2-124">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="c3ae2-124">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="c3ae2-125">Nome do banco de dados no qual o procedimento armazenado está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-125">Name of the database in which the stored procedure is running.</span></span>|<span data-ttu-id="c3ae2-126">35</span><span class="sxs-lookup"><span data-stu-id="c3ae2-126">35</span></span>|<span data-ttu-id="c3ae2-127">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-127">Yes</span></span>|  
|<span data-ttu-id="c3ae2-128">EventClass</span><span class="sxs-lookup"><span data-stu-id="c3ae2-128">EventClass</span></span>|`int`|<span data-ttu-id="c3ae2-129">Tipo de evento = 36.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-129">Type of event = 36.</span></span>|<span data-ttu-id="c3ae2-130">27</span><span class="sxs-lookup"><span data-stu-id="c3ae2-130">27</span></span>|<span data-ttu-id="c3ae2-131">Não</span><span class="sxs-lookup"><span data-stu-id="c3ae2-131">No</span></span>|  
|<span data-ttu-id="c3ae2-132">EventSequence</span><span class="sxs-lookup"><span data-stu-id="c3ae2-132">EventSequence</span></span>|`int`|<span data-ttu-id="c3ae2-133">Sequência de um determinado evento na solicitação.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-133">Sequence of a given event within the request.</span></span>|<span data-ttu-id="c3ae2-134">51</span><span class="sxs-lookup"><span data-stu-id="c3ae2-134">51</span></span>|<span data-ttu-id="c3ae2-135">Não</span><span class="sxs-lookup"><span data-stu-id="c3ae2-135">No</span></span>|  
|<span data-ttu-id="c3ae2-136">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="c3ae2-136">EventSubClass</span></span>|`int`|<span data-ttu-id="c3ae2-137">Tipo de subclasse de eventos:</span><span class="sxs-lookup"><span data-stu-id="c3ae2-137">Type of event subclass:</span></span><br /><br /> <span data-ttu-id="c3ae2-138">1 = Compplan remover.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-138">1=Compplan Remove.</span></span> <span data-ttu-id="c3ae2-139">Um plano de consulta compilado foi removido do cache.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-139">A compiled query plan has been removed from the cache.</span></span><br /><br /> <span data-ttu-id="c3ae2-140">2 = processamento de liberação de cache.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-140">2=Proc Cache Flush.</span></span> <span data-ttu-id="c3ae2-141">Todas as entradas foram removidas do cache de procedimentos.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-141">All entries have been removed from the procedure cache.</span></span>|<span data-ttu-id="c3ae2-142">21</span><span class="sxs-lookup"><span data-stu-id="c3ae2-142">21</span></span>|<span data-ttu-id="c3ae2-143">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-143">Yes</span></span>|  
|<span data-ttu-id="c3ae2-144">GroupID</span><span class="sxs-lookup"><span data-stu-id="c3ae2-144">GroupID</span></span>|`int`|<span data-ttu-id="c3ae2-145">ID do grupo de carga de trabalho no qual o evento de Rastreamento do SQL dispara.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-145">ID of the workload group where the SQL Trace event fires.</span></span>|<span data-ttu-id="c3ae2-146">66</span><span class="sxs-lookup"><span data-stu-id="c3ae2-146">66</span></span>|<span data-ttu-id="c3ae2-147">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-147">Yes</span></span>|  
|<span data-ttu-id="c3ae2-148">HostName</span><span class="sxs-lookup"><span data-stu-id="c3ae2-148">HostName</span></span>|`nvarchar`|<span data-ttu-id="c3ae2-149">Nome do computador no qual o cliente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-149">Name of the computer on which the client is running.</span></span> <span data-ttu-id="c3ae2-150">Essa coluna de dados será populada se o cliente fornecer o nome do host.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-150">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="c3ae2-151">Para determinar o nome do host, use a função HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-151">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="c3ae2-152">8</span><span class="sxs-lookup"><span data-stu-id="c3ae2-152">8</span></span>|<span data-ttu-id="c3ae2-153">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-153">Yes</span></span>|  
|<span data-ttu-id="c3ae2-154">IsSystem</span><span class="sxs-lookup"><span data-stu-id="c3ae2-154">IsSystem</span></span>|`int`|<span data-ttu-id="c3ae2-155">Indica se o evento ocorreu em um processo do sistema ou do usuário.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-155">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="c3ae2-156">1 = sistema, 0 = usuário.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-156">1 = system, 0 = user.</span></span>|<span data-ttu-id="c3ae2-157">60</span><span class="sxs-lookup"><span data-stu-id="c3ae2-157">60</span></span>|<span data-ttu-id="c3ae2-158">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-158">Yes</span></span>|  
|<span data-ttu-id="c3ae2-159">LoginName</span><span class="sxs-lookup"><span data-stu-id="c3ae2-159">LoginName</span></span>|`nvarchar`|<span data-ttu-id="c3ae2-160">Nome de logon do usuário (logon de segurança do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou as credenciais de logon do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows no formato DOMÍNIO/nomedousuário).</span><span class="sxs-lookup"><span data-stu-id="c3ae2-160">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="c3ae2-161">11</span><span class="sxs-lookup"><span data-stu-id="c3ae2-161">11</span></span>|<span data-ttu-id="c3ae2-162">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-162">Yes</span></span>|  
|<span data-ttu-id="c3ae2-163">LoginSid</span><span class="sxs-lookup"><span data-stu-id="c3ae2-163">LoginSid</span></span>|`image`|<span data-ttu-id="c3ae2-164">Número SID (identificação de segurança) do usuário que fez logon.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-164">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="c3ae2-165">Você pode encontrar essas informações na exibição de catálogo sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-165">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="c3ae2-166">Cada SID é exclusivo para cada logon no servidor.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-166">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="c3ae2-167">41</span><span class="sxs-lookup"><span data-stu-id="c3ae2-167">41</span></span>|<span data-ttu-id="c3ae2-168">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-168">Yes</span></span>|  
|<span data-ttu-id="c3ae2-169">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="c3ae2-169">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="c3ae2-170">O domínio do Windows ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-170">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="c3ae2-171">7</span><span class="sxs-lookup"><span data-stu-id="c3ae2-171">7</span></span>|<span data-ttu-id="c3ae2-172">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-172">Yes</span></span>|  
|<span data-ttu-id="c3ae2-173">NTUserName</span><span class="sxs-lookup"><span data-stu-id="c3ae2-173">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="c3ae2-174">Nome do usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-174">Windows user name.</span></span>|<span data-ttu-id="c3ae2-175">6</span><span class="sxs-lookup"><span data-stu-id="c3ae2-175">6</span></span>|<span data-ttu-id="c3ae2-176">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-176">Yes</span></span>|  
|<span data-ttu-id="c3ae2-177">ObjectID</span><span class="sxs-lookup"><span data-stu-id="c3ae2-177">ObjectID</span></span>|`int`|<span data-ttu-id="c3ae2-178">ID do procedimento armazenado, atribuído pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-178">System-assigned ID of the stored procedure.</span></span>|<span data-ttu-id="c3ae2-179">22</span><span class="sxs-lookup"><span data-stu-id="c3ae2-179">22</span></span>|<span data-ttu-id="c3ae2-180">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-180">Yes</span></span>|  
|<span data-ttu-id="c3ae2-181">ObjectType</span><span class="sxs-lookup"><span data-stu-id="c3ae2-181">ObjectType</span></span>|`int`|<span data-ttu-id="c3ae2-182">Valor que representa o tipo do objeto envolvido no evento.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-182">Value representing the type of the object involved in the event.</span></span> <span data-ttu-id="c3ae2-183">Esse valor corresponde à coluna do tipo na exibição do catálogo sys.objects.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-183">This value corresponds to the type column in the sys.objects catalog view.</span></span> <span data-ttu-id="c3ae2-184">Para obter valores, consulte [Coluna de evento de rastreamento ObjectType](objecttype-trace-event-column.md).</span><span class="sxs-lookup"><span data-stu-id="c3ae2-184">For values, see [ObjectType Trace Event Column](objecttype-trace-event-column.md).</span></span>|<span data-ttu-id="c3ae2-185">28</span><span class="sxs-lookup"><span data-stu-id="c3ae2-185">28</span></span>|<span data-ttu-id="c3ae2-186">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-186">Yes</span></span>|  
|<span data-ttu-id="c3ae2-187">RequestID</span><span class="sxs-lookup"><span data-stu-id="c3ae2-187">RequestID</span></span>|`int`|<span data-ttu-id="c3ae2-188">ID da solicitação que contém a instrução.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-188">ID of the request containing the statement.</span></span>|<span data-ttu-id="c3ae2-189">49</span><span class="sxs-lookup"><span data-stu-id="c3ae2-189">49</span></span>|<span data-ttu-id="c3ae2-190">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-190">Yes</span></span>|  
|<span data-ttu-id="c3ae2-191">ServerName</span><span class="sxs-lookup"><span data-stu-id="c3ae2-191">ServerName</span></span>|`nvarchar`|<span data-ttu-id="c3ae2-192">Nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo rastreada.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-192">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="c3ae2-193">26</span><span class="sxs-lookup"><span data-stu-id="c3ae2-193">26</span></span>|<span data-ttu-id="c3ae2-194">Não</span><span class="sxs-lookup"><span data-stu-id="c3ae2-194">No</span></span>|  
|<span data-ttu-id="c3ae2-195">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="c3ae2-195">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="c3ae2-196">Nome de logon do usuário que originou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-196">Login name of the user who originated the session.</span></span> <span data-ttu-id="c3ae2-197">Por exemplo, ao se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o Logon1 e executar uma instrução como Logon2, SessionLoginName mostrará o Logon1 e LoginName mostrará o Logon2.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-197">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, SessionLoginName shows Login1 and LoginName shows Login2.</span></span> <span data-ttu-id="c3ae2-198">Essa coluna exibe logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do Windows.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-198">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="c3ae2-199">64</span><span class="sxs-lookup"><span data-stu-id="c3ae2-199">64</span></span>|<span data-ttu-id="c3ae2-200">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-200">Yes</span></span>|  
|<span data-ttu-id="c3ae2-201">SPID</span><span class="sxs-lookup"><span data-stu-id="c3ae2-201">SPID</span></span>|`int`|<span data-ttu-id="c3ae2-202">Identificação da sessão em que ocorreu o evento.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-202">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="c3ae2-203">12</span><span class="sxs-lookup"><span data-stu-id="c3ae2-203">12</span></span>|<span data-ttu-id="c3ae2-204">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-204">Yes</span></span>|  
|<span data-ttu-id="c3ae2-205">StartTime</span><span class="sxs-lookup"><span data-stu-id="c3ae2-205">StartTime</span></span>|`datetime`|<span data-ttu-id="c3ae2-206">Hora de início do evento, se disponível.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-206">Time at which the event started, if available.</span></span>|<span data-ttu-id="c3ae2-207">14</span><span class="sxs-lookup"><span data-stu-id="c3ae2-207">14</span></span>|<span data-ttu-id="c3ae2-208">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-208">Yes</span></span>|  
|<span data-ttu-id="c3ae2-209">TextData</span><span class="sxs-lookup"><span data-stu-id="c3ae2-209">TextData</span></span>|`ntext`|<span data-ttu-id="c3ae2-210">Texto do SQL que está sendo removido do cache.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-210">Text of the SQL being removed from the cache.</span></span>|<span data-ttu-id="c3ae2-211">1</span><span class="sxs-lookup"><span data-stu-id="c3ae2-211">1</span></span>|<span data-ttu-id="c3ae2-212">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-212">Yes</span></span>|  
|<span data-ttu-id="c3ae2-213">TransactionID</span><span class="sxs-lookup"><span data-stu-id="c3ae2-213">TransactionID</span></span>|`bigint`|<span data-ttu-id="c3ae2-214">ID da transação atribuída pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-214">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="c3ae2-215">4</span><span class="sxs-lookup"><span data-stu-id="c3ae2-215">4</span></span>|<span data-ttu-id="c3ae2-216">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-216">Yes</span></span>|  
|<span data-ttu-id="c3ae2-217">XactSequence</span><span class="sxs-lookup"><span data-stu-id="c3ae2-217">XactSequence</span></span>|`bigint`|<span data-ttu-id="c3ae2-218">Token que descreve a transação atual.</span><span class="sxs-lookup"><span data-stu-id="c3ae2-218">Token that describes the current transaction.</span></span>|<span data-ttu-id="c3ae2-219">50</span><span class="sxs-lookup"><span data-stu-id="c3ae2-219">50</span></span>|<span data-ttu-id="c3ae2-220">Sim</span><span class="sxs-lookup"><span data-stu-id="c3ae2-220">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c3ae2-221">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c3ae2-221">See Also</span></span>  
 <span data-ttu-id="c3ae2-222">[Eventos estendidos](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="c3ae2-222">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="c3ae2-223">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ae2-223">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  