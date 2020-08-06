---
title: Expiração e desativação de assinatura | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Distributors [SQL Server replication], distribution retention period
- subscriptions [SQL Server replication], expiration
- publications [SQL Server replication], publication retention periods
- expiration [SQL Server replication]
- retention periods [SQL Server replication]
- publication retention periods
- distribution retention period
- subscriptions [SQL Server replication], deactivation
- deactivating subscriptions
ms.assetid: 4d03f5ab-e721-4f56-aebc-60f6a56c1e07
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6d81e8b5c02fcfe5399be9e63c8160036a999547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685042"
---
# <a name="subscription-expiration-and-deactivation"></a><span data-ttu-id="6aff0-102">Validade e desativação de assinatura</span><span class="sxs-lookup"><span data-stu-id="6aff0-102">Subscription Expiration and Deactivation</span></span>
  <span data-ttu-id="6aff0-103">As assinaturas podem ser desativadas ou podem expirar se não forem sincronizadas dentro de um *período de retenção*especificado.</span><span class="sxs-lookup"><span data-stu-id="6aff0-103">Subscriptions can be deactivated or can expire if they are not synchronized within a specified *retention period*.</span></span> <span data-ttu-id="6aff0-104">A ação que ocorre depende do tipo de replicação e do período de retenção excedido.</span><span class="sxs-lookup"><span data-stu-id="6aff0-104">The action that occurs depends on the type of replication and the retention period that is exceeded.</span></span>  
  
 <span data-ttu-id="6aff0-105">Para definir os períodos de retenção, consulte [Definir o período de validade para assinaturas](publish/set-the-expiration-period-for-subscriptions.md), [Definir o período de retenção de distribuição para publicações transacionais &#40;SQL Server Management Studio&#41;](set-distribution-retention-period-for-transactional-publications.md) e [Configurar publicação e distribuição](configure-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="6aff0-105">To set retention periods, see [Set the Expiration Period for Subscriptions](publish/set-the-expiration-period-for-subscriptions.md), [Set the Distribution Retention Period for Transactional Publications &#40;SQL Server Management Studio&#41;](set-distribution-retention-period-for-transactional-publications.md), and [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span></span>  
  
## <a name="transactional-replication"></a><span data-ttu-id="6aff0-106">Replicação transacional</span><span class="sxs-lookup"><span data-stu-id="6aff0-106">Transactional Replication</span></span>  
 <span data-ttu-id="6aff0-107">A replicação transacional usa o período máximo de retenção de distribuição (o **@max_distretention** parâmetro de [sp_adddistributiondb &#40;&#41;TRANSACT-SQL ](/sql/relational-databases/system-stored-procedures/sp-adddistributiondb-transact-sql)) e o período de retenção da publicação (o **@retention** parâmetro de [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql)):</span><span class="sxs-lookup"><span data-stu-id="6aff0-107">Transactional replication uses the maximum distribution retention period (the **@max_distretention** parameter of [sp_adddistributiondb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistributiondb-transact-sql)) and the publication retention period (the **@retention** parameter of [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql)):</span></span>  
  
-   <span data-ttu-id="6aff0-108">Se a assinatura não for sincronizada dentro do período de retenção máximo da distribuição (padrão de 72 horas) e houver mudanças no banco de dados de distribuição que não foram entregues ao Assinante, a assinatura será marcada como desativada pelo trabalho de **Limpeza da distribuição** sendo executado no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="6aff0-108">If a subscription is not synchronized within the maximum distribution retention period (default of 72 hours) and there are changes in the distribution database that have not been delivered to the Subscriber, the subscription will be marked deactivated by the **Distribution clean up** job that runs on the Distributor.</span></span> <span data-ttu-id="6aff0-109">A assinatura deverá ser reinicializada.</span><span class="sxs-lookup"><span data-stu-id="6aff0-109">The subscription must be reinitialized.</span></span>  
  
-   <span data-ttu-id="6aff0-110">Se a assinatura não for sincronizada no período de retenção máximo da publicação (padrão de 336 horas), a assinatura expirará e será descartada pelo trabalho de **Limpeza de assinaturas expiradas** executado no Publicador.</span><span class="sxs-lookup"><span data-stu-id="6aff0-110">If a subscription is not synchronized within the publication retention period (default of 336 hours), the subscription will expire and be dropped by the **Expired subscription clean up** job that runs on the Publisher.</span></span> <span data-ttu-id="6aff0-111">A assinatura deverá ser criada novamente e ser sincronizada.</span><span class="sxs-lookup"><span data-stu-id="6aff0-111">The subscription must be recreated and synchronized.</span></span>  
  
     <span data-ttu-id="6aff0-112">Se uma assinatura push expirar, ela é completamente removida, mas não as assinaturas pull.</span><span class="sxs-lookup"><span data-stu-id="6aff0-112">If a push subscription expires, it is completely removed, but pull subscriptions are not.</span></span> <span data-ttu-id="6aff0-113">Você deve limpar as assinaturas pull no Assinante.</span><span class="sxs-lookup"><span data-stu-id="6aff0-113">You must clean up pull subscriptions at the Subscriber.</span></span> <span data-ttu-id="6aff0-114">Para obter mais informações, consulte [Delete a Pull Subscription](delete-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="6aff0-114">For more information, see [Delete a Pull Subscription](delete-a-pull-subscription.md).</span></span>  
  
## <a name="merge-replication"></a><span data-ttu-id="6aff0-115">Replicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="6aff0-115">Merge Replication</span></span>  
 <span data-ttu-id="6aff0-116">A replicação de mesclagem usa o período de retenção da publicação (os **@retention** **@retention_period_unit** parâmetros e de [Sp_addmergepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql)).</span><span class="sxs-lookup"><span data-stu-id="6aff0-116">Merge replication uses the publication retention period (the **@retention** and **@retention_period_unit** parameters of [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql)).</span></span> <span data-ttu-id="6aff0-117">Quando uma assinatura expira, ela deverá ser reiniciada, pois os metadados da assinatura serão removidos.</span><span class="sxs-lookup"><span data-stu-id="6aff0-117">When a subscription expires, it must be reinitialized, because metadata for the subscription is removed.</span></span> <span data-ttu-id="6aff0-118">As assinaturas que não forem reinicializadas serão descartadas pelo trabalho de **Limpeza de assinaturas expiradas** executado no Publicador.</span><span class="sxs-lookup"><span data-stu-id="6aff0-118">Subscriptions that are not reinitialized are dropped by the **Expired subscription clean up** job that runs on the Publisher.</span></span> <span data-ttu-id="6aff0-119">Por padrão, este trabalho é executado diariamente, ele remove todas as assinaturas push que não sincronizaram por um período duas vezes maior do período de retenção da publicação.</span><span class="sxs-lookup"><span data-stu-id="6aff0-119">By default, this job runs daily; it removes all push subscriptions that have not synchronized for double the length of the publication retention period.</span></span> <span data-ttu-id="6aff0-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6aff0-120">For example:</span></span>  
  
-   <span data-ttu-id="6aff0-121">Se a publicação tiver um período de retenção de 14 dias, uma assinatura poderá expirar se não sincronizar dentro de 14 dias.</span><span class="sxs-lookup"><span data-stu-id="6aff0-121">If a publication has a retention period of 14 days, a subscription can expire if it has not synchronized within 14 days.</span></span>  
  
     <span data-ttu-id="6aff0-122">Se o Publicador estiver executando o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou uma versão posterior e o agente para a assinatura pertencer ao [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou versão posterior, uma assinatura só expirará se ocorrerem mudanças nos dados naquela partição da assinatura.</span><span class="sxs-lookup"><span data-stu-id="6aff0-122">If the Publisher is running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or a later version and the agent for the subscription is from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or a later version, a subscription only expires if there have been changes to the data in that subscription's partition.</span></span> <span data-ttu-id="6aff0-123">Por exemplo, se um Assinante receber dados de cliente apenas de clientes na Alemanha.</span><span class="sxs-lookup"><span data-stu-id="6aff0-123">For example, suppose a Subscriber receives customer data only for customers in Germany.</span></span> <span data-ttu-id="6aff0-124">Se o período de retenção for definido em 14 dias, a assinatura expirará no 14º dia somente se ocorreram mudanças nos dados do cliente alemão nos últimos 14 dias.</span><span class="sxs-lookup"><span data-stu-id="6aff0-124">If the retention period is set to 14 days, the subscription expires on day 14 only if there have been changes to the German customer data in the last 14 days.</span></span>  
  
-   <span data-ttu-id="6aff0-125">Do 14º dia até 27 dias após a última sincronização, a assinatura poderá ser reinicializada.</span><span class="sxs-lookup"><span data-stu-id="6aff0-125">From 14 days to 27 days after the last synchronization, the subscription can be reinitialized.</span></span>  
  
-   <span data-ttu-id="6aff0-126">No 28º dia após a última sincronização, a assinatura será descartada pelo trabalho de **Limpeza de assinaturas expiradas** .</span><span class="sxs-lookup"><span data-stu-id="6aff0-126">At 28 days after the last synchronization, the subscription is dropped by the **Expired subscription clean up** job.</span></span> <span data-ttu-id="6aff0-127">Se uma assinatura push expirar, ela é completamente removida, mas não as assinaturas pull.</span><span class="sxs-lookup"><span data-stu-id="6aff0-127">If a push subscription expires, it is completely removed, but pull subscriptions are not.</span></span> <span data-ttu-id="6aff0-128">Você deve limpar as assinaturas pull no Assinante.</span><span class="sxs-lookup"><span data-stu-id="6aff0-128">You must clean up pull subscriptions at the Subscriber.</span></span> <span data-ttu-id="6aff0-129">Para obter mais informações, consulte [Delete a Pull Subscription](delete-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="6aff0-129">For more information, see [Delete a Pull Subscription](delete-a-pull-subscription.md).</span></span>  
  
### <a name="considerations-for-setting-the-publication-retention-period-for-merge-publications"></a><span data-ttu-id="6aff0-130">Considerações para definir o período de retenção da publicação para as publicações de mesclagem</span><span class="sxs-lookup"><span data-stu-id="6aff0-130">Considerations for Setting the Publication Retention Period for Merge Publications</span></span>  
 <span data-ttu-id="6aff0-131">Lembre-se das considerações a seguir ao definir o período de retenção para publicações de mesclagem:</span><span class="sxs-lookup"><span data-stu-id="6aff0-131">Keep the following considerations in mind when setting the retention period for merge publications:</span></span>  
  
-   <span data-ttu-id="6aff0-132">O período de retenção para publicações de mesclagem tem um período de tolerância de 24 horas para incluir os Assinantes em fusos horários diferentes.</span><span class="sxs-lookup"><span data-stu-id="6aff0-132">The retention period for merge publications has a 24-hour grace period to accommodate Subscribers in different time zones.</span></span> <span data-ttu-id="6aff0-133">Por exemplo, se você definir um período de retenção de um dia, o período de retenção real será de 48 horas.</span><span class="sxs-lookup"><span data-stu-id="6aff0-133">If, for example, you set a retention period of one day, the actual retention period is 48 hours.</span></span>  
  
-   <span data-ttu-id="6aff0-134">A limpeza dos metadados da replicação de mesclagem depende do período de retenção da publicação:</span><span class="sxs-lookup"><span data-stu-id="6aff0-134">Cleanup of merge replication metadata is dependent on the publication retention period:</span></span>  
  
    -   <span data-ttu-id="6aff0-135">A replicação não poderá limpar os metadados na publicação e nos bancos de dados de assinatura antes de o período de retenção ser atingido.</span><span class="sxs-lookup"><span data-stu-id="6aff0-135">Replication cannot clean up metadata in the publication and subscription databases until the retention period is reached.</span></span> <span data-ttu-id="6aff0-136">Cuidado ao especificar um valor alto para o período de retenção, pois poderá impactar negativamente o desempenho da replicação.</span><span class="sxs-lookup"><span data-stu-id="6aff0-136">Use caution in specifying a high value for the retention period, because it can negatively impact replication performance.</span></span> <span data-ttu-id="6aff0-137">Recomendamos que use uma definição mais baixa se puder prevenir com certeza que todos os Assinantes sincronizarão normalmente dentro daquele período de tempo.</span><span class="sxs-lookup"><span data-stu-id="6aff0-137">It is recommended that you use a lower setting if you can reliably predict that all Subscribers will synchronize regularly within that time period.</span></span>  
  
    -   <span data-ttu-id="6aff0-138">É possível especificar que as assinaturas nunca expirem (um valor de 0 para **@retention** ), mas é altamente recomendável que você não use esse valor, pois os metadados não podem ser limpos.</span><span class="sxs-lookup"><span data-stu-id="6aff0-138">It is possible to specify that subscriptions never expire (a value of 0 for **@retention**), but it is strongly recommended that you do not use this value, because metadata cannot be cleaned up.</span></span>  
  
-   <span data-ttu-id="6aff0-139">O período de retenção para qualquer republicador deve ser definido com um valor igual ou inferior ao período de retenção definido no Publicador original.</span><span class="sxs-lookup"><span data-stu-id="6aff0-139">The retention period for any republisher must be set to a value equal to or less than the retention period set at the original Publisher.</span></span> <span data-ttu-id="6aff0-140">Você também deve usar os mesmos valores de retenção da publicação para todos os Publicadores e seus parceiros de sincronização alternativos.</span><span class="sxs-lookup"><span data-stu-id="6aff0-140">You should also use the same publication retention values for all Publishers and their alternate synchronization partners.</span></span> <span data-ttu-id="6aff0-141">O uso de valores diferentes pode levar a uma não convergência.</span><span class="sxs-lookup"><span data-stu-id="6aff0-141">Using different values may lead to non-convergence.</span></span> <span data-ttu-id="6aff0-142">Se precisar alterar o valor de retenção da publicação, reinicialize o Assinante para evitar a não convergência de dados.</span><span class="sxs-lookup"><span data-stu-id="6aff0-142">If you need to change the publication retention value, reinitialize the Subscriber to avoid the non-convergence of data.</span></span>  
  
-   <span data-ttu-id="6aff0-143">Se, após a limpeza, o período de retenção da publicação aumentar e uma assinatura tentar a mesclagem com o Publicador (que já excluiu os metadados), a assinatura não expirará devido ao aumento no valor da retenção.</span><span class="sxs-lookup"><span data-stu-id="6aff0-143">If, after a clean up, the publication retention period is increased and a subscription tries to merge with the Publisher (which has already deleted the metadata), the subscription will not expire because of the increased retention value.</span></span> <span data-ttu-id="6aff0-144">Porém, o Publicador não tem metadados suficientes para baixar as mudanças para o Assinante, o que resulta em uma não convergência.</span><span class="sxs-lookup"><span data-stu-id="6aff0-144">However, the Publisher does not have enough metadata to download changes to the Subscriber, which leads to non-convergence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aff0-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6aff0-145">See Also</span></span>  
 <span data-ttu-id="6aff0-146">[Reinicializar as assinaturas](reinitialize-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="6aff0-146">[Reinitialize Subscriptions](reinitialize-subscriptions.md) </span></span>  
 <span data-ttu-id="6aff0-147">[Administração do agente de replicação](agents/replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="6aff0-147">[Replication Agent Administration](agents/replication-agent-administration.md) </span></span>  
 [<span data-ttu-id="6aff0-148">Assinar publicações</span><span class="sxs-lookup"><span data-stu-id="6aff0-148">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  