---
title: Segurança do Agente &lt;AgentName&gt; | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.agentnameagentsecurity.f1
ms.assetid: d34c7ef8-cf77-4ffd-887f-3c4214dfd71e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fc72d4380b4d1980da30b8445596e1919a859e31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583544"
---
# <a name="ltagentnamegt-agent-security"></a><span data-ttu-id="c746b-102">Segurança do Agente &lt;AgentName&gt;</span><span class="sxs-lookup"><span data-stu-id="c746b-102">&lt;AgentName&gt; Agent Security</span></span>
  <span data-ttu-id="c746b-103">A página **Segurança do agente \<AgentName>** permite especificar as contas nas quais o Agente de Distribuição (para replicação transacional ou de instantâneo) ou o Agente de Mesclagem (para replicação de mesclagem) é executado e faz conexões com os computadores em uma topologia de replicação.</span><span class="sxs-lookup"><span data-stu-id="c746b-103">The **\<AgentName> Agent Security** page allows you to specify the accounts under which the Distribution Agent (for transactional and snapshot replication) or Merge Agent (for merge replication) run and make connections to the computers in a replication topology.</span></span> <span data-ttu-id="c746b-104">Para obter informações sobre as permissões necessárias para os agentes e as melhores práticas de segurança da replicação, consulte [Modelo de segurança do agente de replicação](security/replication-agent-security-model.md) e [Melhores práticas de segurança da replicação](security/replication-security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="c746b-104">For information on permissions required by agents and best practices for replication security, see [Replication Agent Security Model](security/replication-agent-security-model.md) and [Replication Security Best Practices](security/replication-security-best-practices.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c746b-105">Opções</span><span class="sxs-lookup"><span data-stu-id="c746b-105">Options</span></span>  
 <span data-ttu-id="c746b-106">Clique no botão de propriedades ( **...** ) na linha de cada Assinante para acessar a caixa de diálogo **Segurança do Distribution Agent** ou **Segurança do Merge Agent** .</span><span class="sxs-lookup"><span data-stu-id="c746b-106">Click the properties button (**...**) in the row for each Subscriber to access the **Distribution Agent Security** or **Merge Agent Security** dialog box.</span></span> <span data-ttu-id="c746b-107">Clique em **Ajuda** na caixa de diálogo que é iniciada para obter mais informações sobre as permissões requeridas para contas usadas pelos agentes.</span><span class="sxs-lookup"><span data-stu-id="c746b-107">Click **Help** on the dialog box that is launched for more information on the permissions required for accounts used by the agents.</span></span>  
  
 <span data-ttu-id="c746b-108">Depois que as configurações forem inseridas em uma das caixas de diálogo, as informações de conexão para o Assinante serão exibidas na grade.</span><span class="sxs-lookup"><span data-stu-id="c746b-108">After settings have been entered in one of the dialog boxes, connection information for the Subscriber is displayed in the grid.</span></span>  
  
 <span data-ttu-id="c746b-109">**Agente para Assinante**</span><span class="sxs-lookup"><span data-stu-id="c746b-109">**Agent for Subscriber**</span></span>  
 <span data-ttu-id="c746b-110">O nome de cada Assinante.</span><span class="sxs-lookup"><span data-stu-id="c746b-110">The name of each Subscriber.</span></span>  
  
 <span data-ttu-id="c746b-111">**Conexão com o Distribuidor**</span><span class="sxs-lookup"><span data-stu-id="c746b-111">**Connection to Distributor**</span></span>  
 <span data-ttu-id="c746b-112">Exibido para replicação de instantâneo e transacional.</span><span class="sxs-lookup"><span data-stu-id="c746b-112">Displayed for transactional and snapshot replication.</span></span> <span data-ttu-id="c746b-113">O contexto no qual a conexão com o Distribuidor é feita.</span><span class="sxs-lookup"><span data-stu-id="c746b-113">The context under which the connection to the Distributor is made.</span></span> <span data-ttu-id="c746b-114">Conexões locais sempre são feitas usando o contexto de conta do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows no qual o agente executa:</span><span class="sxs-lookup"><span data-stu-id="c746b-114">Local connections are always made using the context of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the agent runs:</span></span>  
  
-   <span data-ttu-id="c746b-115">Para assinaturas push, a conexão local é a conexão com o Distribuidor, portanto, esse campo sempre exibirá: **Representar '\<Domain>\\<Logon\>'** ou **Representar '\<Computer>\\<Logon\>'** para assinaturas push.</span><span class="sxs-lookup"><span data-stu-id="c746b-115">For push subscriptions, the local connection is the connection to the Distributor, so this field will always display: **Impersonate '\<Domain>\\<Login\>'** or **Impersonate '\<Computer>\\<Login\>'** for push subscriptions.</span></span>  
  
-   <span data-ttu-id="c746b-116">Para assinaturas pull, a conexão pode ser feita também no contexto de um logon [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c746b-116">For pull subscriptions, the connection can also be made under the context of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="c746b-117">O campo exibe uma das opções a seguir: **Usar o logon '\<Login>'** , **Representar '\<Domain>\\<Logon\>'** ou **Representar '\<Computer>\\<Logon\>'** .</span><span class="sxs-lookup"><span data-stu-id="c746b-117">The field displays one of the following: **Use login '\<Login>'**, **Impersonate '\<Domain>\\<Login\>'** or **Impersonate '\<Computer>\\<Login\>'**.</span></span> <span data-ttu-id="c746b-118">A[!INCLUDE[msCoName](../../includes/msconame-md.md)] recomenda que todas as conexões sejam feitas com o uso do contexto da conta do Windows.</span><span class="sxs-lookup"><span data-stu-id="c746b-118">[!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that all connections be made using the context of the Windows account.</span></span>  
  
 <span data-ttu-id="c746b-119">**Conexão com o Publicador e Distribuidor**</span><span class="sxs-lookup"><span data-stu-id="c746b-119">**Connection to Publisher & Distributor**</span></span>  
 <span data-ttu-id="c746b-120">Exibido para replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="c746b-120">Displayed for merge replication.</span></span> <span data-ttu-id="c746b-121">O contexto no qual as conexões com o Publicador e o Distribuidor são feitas.</span><span class="sxs-lookup"><span data-stu-id="c746b-121">The context under which the connections to the Publisher and Distributor are made.</span></span> <span data-ttu-id="c746b-122">Conexões locais sempre são feitas usando o contexto da conta do Windows na qual o agente é executado:</span><span class="sxs-lookup"><span data-stu-id="c746b-122">Local connections are always made using the context of the Windows account under which the agent runs:</span></span>  
  
-   <span data-ttu-id="c746b-123">Para assinaturas push, a conexão local é a conexão com o Editor e o Distribuidor, portanto, esse campo sempre exibirá: **Representar '\<Domain>\\<Logon\>'** ou **Representar '\<Computer>\\<Logon\>'** para assinaturas push.</span><span class="sxs-lookup"><span data-stu-id="c746b-123">For push subscriptions, the local connection is the connection to the Publisher and Distributor, so this field will always display: **Impersonate '\<Domain>\\<Login\>'** or **Impersonate '\<Computer>\\<Login\>'** for push subscriptions.</span></span>  
  
-   <span data-ttu-id="c746b-124">Para assinaturas pull, a conexão pode ser feita também no contexto de um logon [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c746b-124">For pull subscriptions, the connection can also be made under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="c746b-125">O campo exibe uma das opções a seguir: **Usar o logon '\<Login>'** , **Representar '\<Domain>\\<Logon\>'** ou **Representar '\<Computer>\\<Logon\>'** .</span><span class="sxs-lookup"><span data-stu-id="c746b-125">The field displays one of the following: **Use login '\<Login>'**, **Impersonate '\<Domain>\\<Login\>'** or **Impersonate '\<Computer>\\<Login\>'**.</span></span> <span data-ttu-id="c746b-126">A[!INCLUDE[msCoName](../../includes/msconame-md.md)] recomenda que todas as conexões sejam feitas com o uso do contexto da conta do Windows.</span><span class="sxs-lookup"><span data-stu-id="c746b-126">[!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that all connections be made using the context of the Windows account.</span></span>  
  
 <span data-ttu-id="c746b-127">**Conexão com o Assinante**</span><span class="sxs-lookup"><span data-stu-id="c746b-127">**Connection to Subscriber**</span></span>  
 <span data-ttu-id="c746b-128">O contexto no qual a conexão com o Assinante é feita.</span><span class="sxs-lookup"><span data-stu-id="c746b-128">The context under which the connection to the Subscriber is made.</span></span> <span data-ttu-id="c746b-129">Conexões locais sempre são feitas usando o contexto da conta do Windows na qual o agente é executado:</span><span class="sxs-lookup"><span data-stu-id="c746b-129">Local connections are always made using the context of the Windows account under which the agent runs:</span></span>  
  
-   <span data-ttu-id="c746b-130">Para assinaturas pull, a conexão local é a conexão com o Assinante, portanto, esse campo sempre exibirá: **Representar '\<Domain>\\<Logon\>'** ou **Representar '\<Computer>\\<Logon\>'** para assinaturas push.</span><span class="sxs-lookup"><span data-stu-id="c746b-130">For pull subscriptions, the local connection is the connection to the Subscriber, so this field will always display: **Impersonate '\<Domain>\\<Login\>'** or **Impersonate '\<Computer>\\<Login\>'** for push subscriptions.</span></span>  
  
-   <span data-ttu-id="c746b-131">Para assinaturas push, a conexão pode ser feita também no contexto de um logon [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c746b-131">For push subscriptions, the connection can also be made under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="c746b-132">O campo exibe uma das opções a seguir: **Usar o logon '\<Login>'** , **Representar '\<Domain>\\<Logon\>'** ou **Representar '\<Computer>\\<Logon\>'** .</span><span class="sxs-lookup"><span data-stu-id="c746b-132">The field displays one of the following: **Use login '\<Login>'**, **Impersonate '\<Domain>\\<Login\>'** or **Impersonate '\<Computer>\\<Login\>'**.</span></span> <span data-ttu-id="c746b-133">A[!INCLUDE[msCoName](../../includes/msconame-md.md)] recomenda que todas as conexões sejam feitas com o uso do contexto da conta do Windows.</span><span class="sxs-lookup"><span data-stu-id="c746b-133">[!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that all connections be made using the context of the Windows account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c746b-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c746b-134">See Also</span></span>  
 <span data-ttu-id="c746b-135">[Exibir e modificar propriedades de assinatura pull](view-and-modify-pull-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="c746b-135">[View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md) </span></span>  
 <span data-ttu-id="c746b-136">[Exibir e modificar propriedades de assinatura push](view-and-modify-push-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="c746b-136">[View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) </span></span>  
 <span data-ttu-id="c746b-137">[Gerenciar logons e senhas na replicação](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="c746b-137">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="c746b-138">[Modelo de segurança do agente de replicação](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="c746b-138">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 [<span data-ttu-id="c746b-139">Segurança de Replicação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="c746b-139">SQL Server Replication Security</span></span>](security/view-and-modify-replication-security-settings.md)  
  
  