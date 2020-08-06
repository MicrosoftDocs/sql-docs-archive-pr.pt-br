---
title: Classe de evento Audit Login Failed | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Audit Login Failed event class
ms.assetid: 6b83963b-b685-429d-92ba-5173f6f0000d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 72734a0d8fa24cc69fd0f29b34fba4f6b2f61b6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682247"
---
# <a name="audit-login-failed-event-class"></a><span data-ttu-id="c9c88-102">Classe de evento Audit Login Failed</span><span class="sxs-lookup"><span data-stu-id="c9c88-102">Audit Login Failed Event Class</span></span>
  <span data-ttu-id="c9c88-103">A classe de evento **Audit Login Failed** indica que um usuário tentou fazer logon no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e não conseguiu.</span><span class="sxs-lookup"><span data-stu-id="c9c88-103">The **Audit Login Failed** event class indicates that a user tried to log in to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and failed.</span></span> <span data-ttu-id="c9c88-104">Os eventos nesta classe são disparados por novas conexões ou por conexões reutilizadas de um pool de conexões.</span><span class="sxs-lookup"><span data-stu-id="c9c88-104">Events in this class are fired by new connections or by connections that are reused from a connection pool.</span></span>  
  
## <a name="audit-login-failed-event-class-data-columns"></a><span data-ttu-id="c9c88-105">Colunas de dados da classe de evento Audit Login Failed</span><span class="sxs-lookup"><span data-stu-id="c9c88-105">Audit Login Failed Event Class Data Columns</span></span>  
  
|<span data-ttu-id="c9c88-106">Nome da coluna de dados</span><span class="sxs-lookup"><span data-stu-id="c9c88-106">Data column name</span></span>|<span data-ttu-id="c9c88-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="c9c88-107">Data type</span></span>|<span data-ttu-id="c9c88-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="c9c88-108">Description</span></span>|<span data-ttu-id="c9c88-109">ID da coluna</span><span class="sxs-lookup"><span data-stu-id="c9c88-109">Column ID</span></span>|<span data-ttu-id="c9c88-110">Filtrável</span><span class="sxs-lookup"><span data-stu-id="c9c88-110">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="c9c88-111">**ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="c9c88-111">**ApplicationName**</span></span>|<span data-ttu-id="c9c88-112">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="c9c88-112">**nvarchar**</span></span>|<span data-ttu-id="c9c88-113">Nome do aplicativo cliente que criou a conexão com uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9c88-113">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c9c88-114">Essa coluna é populada com os valores passados pelo aplicativo e não com o nome exibido do programa.</span><span class="sxs-lookup"><span data-stu-id="c9c88-114">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="c9c88-115">10</span><span class="sxs-lookup"><span data-stu-id="c9c88-115">10</span></span>|<span data-ttu-id="c9c88-116">Sim</span><span class="sxs-lookup"><span data-stu-id="c9c88-116">Yes</span></span>|  
|<span data-ttu-id="c9c88-117">**ClientProcessID**</span><span class="sxs-lookup"><span data-stu-id="c9c88-117">**ClientProcessID**</span></span>|<span data-ttu-id="c9c88-118">**int**</span><span class="sxs-lookup"><span data-stu-id="c9c88-118">**int**</span></span>|<span data-ttu-id="c9c88-119">ID atribuída pelo computador host ao processo em que o aplicativo cliente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="c9c88-119">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="c9c88-120">Essa coluna de dados será populada se a ID do processo do cliente for fornecida pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="c9c88-120">This data column is populated if the client process ID is provided by the client.</span></span>|<span data-ttu-id="c9c88-121">9</span><span class="sxs-lookup"><span data-stu-id="c9c88-121">9</span></span>|<span data-ttu-id="c9c88-122">Sim</span><span class="sxs-lookup"><span data-stu-id="c9c88-122">Yes</span></span>|  
|<span data-ttu-id="c9c88-123">**DatabaseID**</span><span class="sxs-lookup"><span data-stu-id="c9c88-123">**DatabaseID**</span></span>|<span data-ttu-id="c9c88-124">**int**</span><span class="sxs-lookup"><span data-stu-id="c9c88-124">**int**</span></span>|<span data-ttu-id="c9c88-125">ID do banco de dados especificado pela instrução USE de *database* ou o banco de dados padrão se nenhuma instrução USE de *database* tiver sido emitida para uma determinada instância.</span><span class="sxs-lookup"><span data-stu-id="c9c88-125">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="c9c88-126">exibirá o nome do banco de dados se a coluna de dados **ServerName** for capturada no rastreamento e o servidor estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="c9c88-126">displays the name of the database if the **ServerName** data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="c9c88-127">Determine o valor para um banco de dados usando a função DB_ID.</span><span class="sxs-lookup"><span data-stu-id="c9c88-127">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="c9c88-128">3</span><span class="sxs-lookup"><span data-stu-id="c9c88-128">3</span></span>|<span data-ttu-id="c9c88-129">Sim</span><span class="sxs-lookup"><span data-stu-id="c9c88-129">Yes</span></span>|  
|<span data-ttu-id="c9c88-130">**DatabaseName**</span><span class="sxs-lookup"><span data-stu-id="c9c88-130">**DatabaseName**</span></span>|<span data-ttu-id="c9c88-131">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="c9c88-131">**nvarchar**</span></span>|<span data-ttu-id="c9c88-132">Nome do banco de dados no qual a instrução do usuário está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="c9c88-132">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="c9c88-133">35</span><span class="sxs-lookup"><span data-stu-id="c9c88-133">35</span></span>|<span data-ttu-id="c9c88-134">Sim</span><span class="sxs-lookup"><span data-stu-id="c9c88-134">Yes</span></span>|  
|<span data-ttu-id="c9c88-135">**Erro**</span><span class="sxs-lookup"><span data-stu-id="c9c88-135">**Error**</span></span>|<span data-ttu-id="c9c88-136">**int**</span><span class="sxs-lookup"><span data-stu-id="c9c88-136">**int**</span></span>|<span data-ttu-id="c9c88-137">Número de erro de um determinado evento.</span><span class="sxs-lookup"><span data-stu-id="c9c88-137">Error number of a given event.</span></span> <span data-ttu-id="c9c88-138">Geralmente é o número do erro armazenado na exibição de catálogo **sys.messages** .</span><span class="sxs-lookup"><span data-stu-id="c9c88-138">Often this is the error number stored in the **sys.messages** catalog view.</span></span>|<span data-ttu-id="c9c88-139">31</span><span class="sxs-lookup"><span data-stu-id="c9c88-139">31</span></span>|<span data-ttu-id="c9c88-140">Sim</span><span class="sxs-lookup"><span data-stu-id="c9c88-140">Yes</span></span>|  
|<span data-ttu-id="c9c88-141">**EventClass**</span><span class="sxs-lookup"><span data-stu-id="c9c88-141">**EventClass**</span></span>|<span data-ttu-id="c9c88-142">**int**</span><span class="sxs-lookup"><span data-stu-id="c9c88-142">**int**</span></span>|<span data-ttu-id="c9c88-143">Tipo de evento = 20.</span><span class="sxs-lookup"><span data-stu-id="c9c88-143">Type of event = 20.</span></span>|<span data-ttu-id="c9c88-144">27</span><span class="sxs-lookup"><span data-stu-id="c9c88-144">27</span></span>|<span data-ttu-id="c9c88-145">Não</span><span class="sxs-lookup"><span data-stu-id="c9c88-145">No</span></span>|  
|<span data-ttu-id="c9c88-146">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="c9c88-146">**EventSequence**</span></span>|<span data-ttu-id="c9c88-147">**int**</span><span class="sxs-lookup"><span data-stu-id="c9c88-147">**int**</span></span>|<span data-ttu-id="c9c88-148">A sequência de determinado evento dentro da solicitação.</span><span class="sxs-lookup"><span data-stu-id="c9c88-148">The sequence of a given event within the request.</span></span>|<span data-ttu-id="c9c88-149">51</span><span class="sxs-lookup"><span data-stu-id="c9c88-149">51</span></span>|<span data-ttu-id="c9c88-150">Não</span><span class="sxs-lookup"><span data-stu-id="c9c88-150">No</span></span>|  
|<span data-ttu-id="c9c88-151">**HostName**</span><span class="sxs-lookup"><span data-stu-id="c9c88-151">**HostName**</span></span>|<span data-ttu-id="c9c88-152">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="c9c88-152">**nvarchar**</span></span>|<span data-ttu-id="c9c88-153">Nome do computador no qual o cliente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="c9c88-153">Name of the computer on which the client is running.</span></span> <span data-ttu-id="c9c88-154">Essa coluna de dados será populada se o nome do host for fornecido pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="c9c88-154">This data column is populated if the host name is provided by the client.</span></span> <span data-ttu-id="c9c88-155">Para determinar o nome do host, use a função HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="c9c88-155">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="c9c88-156">8</span><span class="sxs-lookup"><span data-stu-id="c9c88-156">8</span></span>|<span data-ttu-id="c9c88-157">Sim</span><span class="sxs-lookup"><span data-stu-id="c9c88-157">Yes</span></span>|  
|<span data-ttu-id="c9c88-158">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="c9c88-158">**IsSystem**</span></span>|<span data-ttu-id="c9c88-159">**int**</span><span class="sxs-lookup"><span data-stu-id="c9c88-159">**int**</span></span>|<span data-ttu-id="c9c88-160">Indica se o evento ocorreu em um processo do sistema ou do usuário.</span><span class="sxs-lookup"><span data-stu-id="c9c88-160">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="c9c88-161">1 = sistema, 0 = usuário.</span><span class="sxs-lookup"><span data-stu-id="c9c88-161">1 = system, 0 = user.</span></span>|<span data-ttu-id="c9c88-162">60</span><span class="sxs-lookup"><span data-stu-id="c9c88-162">60</span></span>|<span data-ttu-id="c9c88-163">Sim</span><span class="sxs-lookup"><span data-stu-id="c9c88-163">Yes</span></span>|  
|<span data-ttu-id="c9c88-164">**LoginName**</span><span class="sxs-lookup"><span data-stu-id="c9c88-164">**LoginName**</span></span>|<span data-ttu-id="c9c88-165">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="c9c88-165">**nvarchar**</span></span>|<span data-ttu-id="c9c88-166">Nome de logon do usuário (logon de segurança do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou as credenciais de logon do Windows na forma de DOMAIN\nome_do_usuário).</span><span class="sxs-lookup"><span data-stu-id="c9c88-166">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="c9c88-167">11</span><span class="sxs-lookup"><span data-stu-id="c9c88-167">11</span></span>|<span data-ttu-id="c9c88-168">Sim</span><span class="sxs-lookup"><span data-stu-id="c9c88-168">Yes</span></span>|  
|<span data-ttu-id="c9c88-169">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="c9c88-169">**NTDomainName**</span></span>|<span data-ttu-id="c9c88-170">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="c9c88-170">**nvarchar**</span></span>|<span data-ttu-id="c9c88-171">O domínio do Windows ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="c9c88-171">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="c9c88-172">7</span><span class="sxs-lookup"><span data-stu-id="c9c88-172">7</span></span>|<span data-ttu-id="c9c88-173">Sim</span><span class="sxs-lookup"><span data-stu-id="c9c88-173">Yes</span></span>|  
|<span data-ttu-id="c9c88-174">**NTUserName**</span><span class="sxs-lookup"><span data-stu-id="c9c88-174">**NTUserName**</span></span>|<span data-ttu-id="c9c88-175">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="c9c88-175">**nvarchar**</span></span>|<span data-ttu-id="c9c88-176">Nome do usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="c9c88-176">Windows user name.</span></span>|<span data-ttu-id="c9c88-177">6</span><span class="sxs-lookup"><span data-stu-id="c9c88-177">6</span></span>|<span data-ttu-id="c9c88-178">Sim</span><span class="sxs-lookup"><span data-stu-id="c9c88-178">Yes</span></span>|  
|<span data-ttu-id="c9c88-179">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="c9c88-179">**RequestID**</span></span>|<span data-ttu-id="c9c88-180">**int**</span><span class="sxs-lookup"><span data-stu-id="c9c88-180">**int**</span></span>|<span data-ttu-id="c9c88-181">O ID da solicitação que contém a instrução.</span><span class="sxs-lookup"><span data-stu-id="c9c88-181">The ID of the request containing the statement.</span></span>|<span data-ttu-id="c9c88-182">49</span><span class="sxs-lookup"><span data-stu-id="c9c88-182">49</span></span>|<span data-ttu-id="c9c88-183">Sim</span><span class="sxs-lookup"><span data-stu-id="c9c88-183">Yes</span></span>|  
|<span data-ttu-id="c9c88-184">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="c9c88-184">**ServerName**</span></span>|<span data-ttu-id="c9c88-185">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="c9c88-185">**nvarchar**</span></span>|<span data-ttu-id="c9c88-186">Nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo rastreada.</span><span class="sxs-lookup"><span data-stu-id="c9c88-186">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="c9c88-187">26</span><span class="sxs-lookup"><span data-stu-id="c9c88-187">26</span></span>|<span data-ttu-id="c9c88-188">Não</span><span class="sxs-lookup"><span data-stu-id="c9c88-188">No</span></span>|  
|<span data-ttu-id="c9c88-189">**SessionLoginName**</span><span class="sxs-lookup"><span data-stu-id="c9c88-189">**SessionLoginName**</span></span>|<span data-ttu-id="c9c88-190">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="c9c88-190">**nvarchar**</span></span>|<span data-ttu-id="c9c88-191">Nome de logon do usuário que originou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c9c88-191">Login name of the user who originated the session.</span></span> <span data-ttu-id="c9c88-192">Por exemplo, para se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o Logon1 e executar uma instrução como Logon2, o **SessionLoginName** mostrará o Logon1 e o **LoginName** mostrará o Logon2.</span><span class="sxs-lookup"><span data-stu-id="c9c88-192">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, **SessionLoginName** shows Login1 and **LoginName** shows Login2.</span></span> <span data-ttu-id="c9c88-193">Essa coluna exibe logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do Windows.</span><span class="sxs-lookup"><span data-stu-id="c9c88-193">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="c9c88-194">64</span><span class="sxs-lookup"><span data-stu-id="c9c88-194">64</span></span>|<span data-ttu-id="c9c88-195">Sim</span><span class="sxs-lookup"><span data-stu-id="c9c88-195">Yes</span></span>|  
|<span data-ttu-id="c9c88-196">**SPID**</span><span class="sxs-lookup"><span data-stu-id="c9c88-196">**SPID**</span></span>|<span data-ttu-id="c9c88-197">**int**</span><span class="sxs-lookup"><span data-stu-id="c9c88-197">**int**</span></span>|<span data-ttu-id="c9c88-198">Identificação da sessão em que ocorreu o evento.</span><span class="sxs-lookup"><span data-stu-id="c9c88-198">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="c9c88-199">12</span><span class="sxs-lookup"><span data-stu-id="c9c88-199">12</span></span>|<span data-ttu-id="c9c88-200">Sim</span><span class="sxs-lookup"><span data-stu-id="c9c88-200">Yes</span></span>|  
|<span data-ttu-id="c9c88-201">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="c9c88-201">**StartTime**</span></span>|<span data-ttu-id="c9c88-202">**datetime**</span><span class="sxs-lookup"><span data-stu-id="c9c88-202">**datetime**</span></span>|<span data-ttu-id="c9c88-203">Hora de início do evento, se disponível.</span><span class="sxs-lookup"><span data-stu-id="c9c88-203">Time at which the event started, if available.</span></span>|<span data-ttu-id="c9c88-204">14</span><span class="sxs-lookup"><span data-stu-id="c9c88-204">14</span></span>|<span data-ttu-id="c9c88-205">Sim</span><span class="sxs-lookup"><span data-stu-id="c9c88-205">Yes</span></span>|  
|<span data-ttu-id="c9c88-206">**Êxito**</span><span class="sxs-lookup"><span data-stu-id="c9c88-206">**Success**</span></span>|<span data-ttu-id="c9c88-207">**int**</span><span class="sxs-lookup"><span data-stu-id="c9c88-207">**int**</span></span>|<span data-ttu-id="c9c88-208">1 = êxito.</span><span class="sxs-lookup"><span data-stu-id="c9c88-208">1 = success.</span></span> <span data-ttu-id="c9c88-209">0 = falha.</span><span class="sxs-lookup"><span data-stu-id="c9c88-209">0 = failure.</span></span> <span data-ttu-id="c9c88-210">Esse evento sempre mostrará falha.</span><span class="sxs-lookup"><span data-stu-id="c9c88-210">This event will always show failure.</span></span>|<span data-ttu-id="c9c88-211">23</span><span class="sxs-lookup"><span data-stu-id="c9c88-211">23</span></span>|<span data-ttu-id="c9c88-212">Sim</span><span class="sxs-lookup"><span data-stu-id="c9c88-212">Yes</span></span>|  
|<span data-ttu-id="c9c88-213">**TextData**</span><span class="sxs-lookup"><span data-stu-id="c9c88-213">**TextData**</span></span>|<span data-ttu-id="c9c88-214">**ntext**</span><span class="sxs-lookup"><span data-stu-id="c9c88-214">**ntext**</span></span>|<span data-ttu-id="c9c88-215">Valor do texto dependente da classe de evento capturada no rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c9c88-215">Text value dependent on the event class captured in the trace.</span></span>|<span data-ttu-id="c9c88-216">1</span><span class="sxs-lookup"><span data-stu-id="c9c88-216">1</span></span>|<span data-ttu-id="c9c88-217">Sim</span><span class="sxs-lookup"><span data-stu-id="c9c88-217">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9c88-218">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c9c88-218">See Also</span></span>  
 <span data-ttu-id="c9c88-219">[Eventos estendidos](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="c9c88-219">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="c9c88-220">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c9c88-220">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  