---
title: Monitorar o desempenho com o Replication Monitor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], Replication Monitor
- Log Reader Agent, monitoring
- Replication Monitor, performance
- Merge Agent, monitoring
- Queue Reader Agent, monitoring
- Snapshot Agent, monitoring
- Distribution Agent, monitoring
- monitoring performance [SQL Server replication]
ms.assetid: f212397d-1bfd-496b-a246-668952891d09
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d02cb17aae5dfe72a9660de62e516e61313ef03c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571940"
---
# <a name="monitor-performance-with-replication-monitor"></a><span data-ttu-id="a4fac-102">Monitorar o desempenho com o Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="a4fac-102">Monitor Performance with Replication Monitor</span></span>
  <span data-ttu-id="a4fac-103">O [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor permite monitorar o desempenho da replicação transacional e replicação de mesclagem das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="a4fac-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor allows you to monitor the performance of transactional replication and merge replication in the following ways:</span></span>  
  
-   <span data-ttu-id="a4fac-104">Definindo as advertências e os limites</span><span class="sxs-lookup"><span data-stu-id="a4fac-104">Setting warnings and thresholds</span></span>  
  
-   <span data-ttu-id="a4fac-105">Exibindo as medições de desempenho</span><span class="sxs-lookup"><span data-stu-id="a4fac-105">Viewing performance measurements</span></span>  
  
-   <span data-ttu-id="a4fac-106">Determinando a latência com os tokens de rastreamento (replicação transacional)</span><span class="sxs-lookup"><span data-stu-id="a4fac-106">Determining latency with tracer tokens (transactional replication)</span></span>  
  
-   <span data-ttu-id="a4fac-107">Exibindo as estatísticas de sincronização detalhadas (replicação de mesclagem)</span><span class="sxs-lookup"><span data-stu-id="a4fac-107">Viewing detailed synchronization statistics (merge replication)</span></span>  
  
-   <span data-ttu-id="a4fac-108">Exibindo as transações e a hora de entrega (replicação transacional)</span><span class="sxs-lookup"><span data-stu-id="a4fac-108">Viewing transactions and delivery time (transactional replication)</span></span>  
  
## <a name="set-warnings-and-thresholds"></a><span data-ttu-id="a4fac-109">Definir avisos e limites</span><span class="sxs-lookup"><span data-stu-id="a4fac-109">Set Warnings and Thresholds</span></span>  
 <span data-ttu-id="a4fac-110">O Replication Monitor permite ativar avisos para várias condições de desempenho.</span><span class="sxs-lookup"><span data-stu-id="a4fac-110">Replication Monitor allows you to enable warnings for a number of performance conditions.</span></span> <span data-ttu-id="a4fac-111">Ao habilitar um aviso, você especifica um limite.</span><span class="sxs-lookup"><span data-stu-id="a4fac-111">When you enable a warning, you specify a threshold.</span></span> <span data-ttu-id="a4fac-112">Se o limite especificado for alcançado ou ultrapassado, será exibido um aviso na coluna **Status** para a assinatura e a publicação com a qual ela sincroniza (exceto se um problema com prioridade mais alta for exibido).</span><span class="sxs-lookup"><span data-stu-id="a4fac-112">When that threshold is met or exceeded, a warning is displayed in the **Status** column for the subscription and the publication with which it synchronizes (unless an issue with a higher priority needs to be displayed).</span></span> <span data-ttu-id="a4fac-113">Além de exibir de um aviso no Replication Monitor, atingir um limite também pode disparar um alerta.</span><span class="sxs-lookup"><span data-stu-id="a4fac-113">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="a4fac-114">Você pode habilitar avisos para as seguintes condições de desempenho:</span><span class="sxs-lookup"><span data-stu-id="a4fac-114">You can enable warnings for the following performance conditions:</span></span>  
  
-   <span data-ttu-id="a4fac-115">Exceder a latência especificada (o período decorrido entre a confirmação de uma transação no Publicador e a confirmação da transação correspondente no Assinante).</span><span class="sxs-lookup"><span data-stu-id="a4fac-115">Exceeding the specified latency (the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber).</span></span>  
  
     <span data-ttu-id="a4fac-116">Isso se aplica à replicação transacional.</span><span class="sxs-lookup"><span data-stu-id="a4fac-116">This applies to transactional replication.</span></span> <span data-ttu-id="a4fac-117">Se o limite especificado for atingido ou excedido, o status será exibido como **Desempenho crítico**.</span><span class="sxs-lookup"><span data-stu-id="a4fac-117">If the specified threshold is met or exceeded, the status is displayed as **Performance critical**.</span></span>  
  
-   <span data-ttu-id="a4fac-118">Excedendo o tempo de sincronização especificado.</span><span class="sxs-lookup"><span data-stu-id="a4fac-118">Exceeding the specified synchronization time.</span></span>  
  
     <span data-ttu-id="a4fac-119">Isso se aplica à replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="a4fac-119">This applies to merge replication.</span></span> <span data-ttu-id="a4fac-120">Se o limite especificado for atingido ou excedido, o status será exibido como **Mesclagem de execução longa**.</span><span class="sxs-lookup"><span data-stu-id="a4fac-120">If the specified threshold is met or exceeded, the status is displayed as **Long-running merge**.</span></span> <span data-ttu-id="a4fac-121">Você pode especificar limites diferentes para conexões discadas e Rede local (LAN).</span><span class="sxs-lookup"><span data-stu-id="a4fac-121">You can specify different thresholds for dial-up and Local Area Network (LAN) connections.</span></span>  
  
-   <span data-ttu-id="a4fac-122">Falha no processamento do número especificado de linhas em um determinado período.</span><span class="sxs-lookup"><span data-stu-id="a4fac-122">Falling short of processing the specified number of rows in a given amount of time.</span></span>  
  
     <span data-ttu-id="a4fac-123">Isso se aplica à replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="a4fac-123">This applies to merge replication.</span></span> <span data-ttu-id="a4fac-124">Se o limite especificado for atingido ou excedido, o status será exibido como **Desempenho crítico**.</span><span class="sxs-lookup"><span data-stu-id="a4fac-124">If the specified threshold is met or exceeded, the status is displayed as **Performance critical**.</span></span> <span data-ttu-id="a4fac-125">Você pode especificar limites diferentes para conexões discadas e LAN.</span><span class="sxs-lookup"><span data-stu-id="a4fac-125">You can specify different thresholds for dial-up and LAN connections.</span></span>  
  
 <span data-ttu-id="a4fac-126">Para obter mais informações, consulte [Set Thresholds and Warnings in Replication Monitor](set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="a4fac-126">For more information, see [Set Thresholds and Warnings in Replication Monitor](set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
## <a name="view-performance-measurements"></a><span data-ttu-id="a4fac-127">Exibir as medições de desempenho</span><span class="sxs-lookup"><span data-stu-id="a4fac-127">View Performance Measurements</span></span>  
 <span data-ttu-id="a4fac-128">O Replication Monitor exibe os valores de qualidade de desempenho para a replicação transacional e a replicação de mesclagem nas colunas **Desempenho Médio Atual** e **Pior Desempenho Atual** para publicações e na coluna **Desempenho** para assinaturas.</span><span class="sxs-lookup"><span data-stu-id="a4fac-128">Replication Monitor displays performance quality values for transactional replication and merge replication in the **Current Average Performance** and **Current Worst Performance** columns for publications and the **Performance** column for subscriptions.</span></span> <span data-ttu-id="a4fac-129">Os valores são:</span><span class="sxs-lookup"><span data-stu-id="a4fac-129">The values are:</span></span>  
  
-   <span data-ttu-id="a4fac-130">Excelente</span><span class="sxs-lookup"><span data-stu-id="a4fac-130">Excellent</span></span>  
  
-   <span data-ttu-id="a4fac-131">Bom</span><span class="sxs-lookup"><span data-stu-id="a4fac-131">Good</span></span>  
  
-   <span data-ttu-id="a4fac-132">Razoável</span><span class="sxs-lookup"><span data-stu-id="a4fac-132">Fair</span></span>  
  
-   <span data-ttu-id="a4fac-133">Fraco</span><span class="sxs-lookup"><span data-stu-id="a4fac-133">Poor</span></span>  
  
-   <span data-ttu-id="a4fac-134">Crítico (replicação transacional somente)</span><span class="sxs-lookup"><span data-stu-id="a4fac-134">Critical (transactional replication only)</span></span>  
  
 <span data-ttu-id="a4fac-135">Os valores são determinados das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="a4fac-135">The values are determined in the following ways:</span></span>  
  
-   <span data-ttu-id="a4fac-136">Para a replicação transacional, a qualidade de desempenho é determinada pelo limite de latência.</span><span class="sxs-lookup"><span data-stu-id="a4fac-136">For transactional replication, performance quality is determined by the latency threshold.</span></span> <span data-ttu-id="a4fac-137">Se o limite não for definido, não será exibido um valor.</span><span class="sxs-lookup"><span data-stu-id="a4fac-137">If the threshold is not set, a value is not displayed.</span></span> <span data-ttu-id="a4fac-138">A tabela a seguir mostra a correlação entre o limite e o valor de qualidade de desempenho.</span><span class="sxs-lookup"><span data-stu-id="a4fac-138">The following table shows the correlation between the threshold and the performance quality value.</span></span> <span data-ttu-id="a4fac-139">Por exemplo, se a latência for selecionada para 60 segundos e a latência real for de 30 segundos, a latência será 50% do limite, resultando em um valor Bom.</span><span class="sxs-lookup"><span data-stu-id="a4fac-139">For example, if the threshold is set to 60 seconds and the actual latency is 30 seconds, latency is 50% of the threshold, resulting in a value of Good.</span></span>  
  
    |<span data-ttu-id="a4fac-140">Excelente</span><span class="sxs-lookup"><span data-stu-id="a4fac-140">Excellent</span></span>|<span data-ttu-id="a4fac-141">Bom</span><span class="sxs-lookup"><span data-stu-id="a4fac-141">Good</span></span>|<span data-ttu-id="a4fac-142">Razoável</span><span class="sxs-lookup"><span data-stu-id="a4fac-142">Fair</span></span>|<span data-ttu-id="a4fac-143">Fraco</span><span class="sxs-lookup"><span data-stu-id="a4fac-143">Poor</span></span>|<span data-ttu-id="a4fac-144">Crítico</span><span class="sxs-lookup"><span data-stu-id="a4fac-144">Critical</span></span>|  
    |---------------|----------|----------|----------|--------------|  
    |<span data-ttu-id="a4fac-145">0 – 34%</span><span class="sxs-lookup"><span data-stu-id="a4fac-145">0 - 34%</span></span>|<span data-ttu-id="a4fac-146">35 – 59%</span><span class="sxs-lookup"><span data-stu-id="a4fac-146">35 - 59%</span></span>|<span data-ttu-id="a4fac-147">60 – 84%</span><span class="sxs-lookup"><span data-stu-id="a4fac-147">60 - 84%</span></span>|<span data-ttu-id="a4fac-148">85 – 99%</span><span class="sxs-lookup"><span data-stu-id="a4fac-148">85 - 99%</span></span>|<span data-ttu-id="a4fac-149">100% +</span><span class="sxs-lookup"><span data-stu-id="a4fac-149">100% +</span></span>|  
  
-   <span data-ttu-id="a4fac-150">Para replicação de mesclagem, a qualidade do desempenho é independente (o limite de processamento da linha determina se o valor de **Performance crítica** é mostrado na coluna de **Status** ).</span><span class="sxs-lookup"><span data-stu-id="a4fac-150">For merge replication, performance quality is independent of either threshold (the row processing threshold does determine if a value of **Performance critical** is displayed in the **Status** column).</span></span> <span data-ttu-id="a4fac-151">A qualidade de desempenho é determinada comparando-se o desempenho de uma assinatura individual, do desempenho histórico médio de assinaturas, com a publicação que tem o mesmo tipo de conexão (discada ou LAN).</span><span class="sxs-lookup"><span data-stu-id="a4fac-151">Performance quality is determined by comparing individual subscription performance to the average historical performance of subscriptions to the publication that have the same connection type (dial-up or LAN).</span></span> <span data-ttu-id="a4fac-152">O Replication Monitor exibe um valor após a ocorrência de cinco sincronizações com 50 ou mais alterações cada, no mesmo tipo de conexão.</span><span class="sxs-lookup"><span data-stu-id="a4fac-152">Replication Monitor displays a value after five synchronizations have occurred with 50 or more changes each over the same type of connection.</span></span> <span data-ttu-id="a4fac-153">Se houver menos de cinco sincronizações com 50 ou mais alterações ou se a sincronização mais recente tiver menos de 50 alterações, o Replication Monitor não exibirá um valor.</span><span class="sxs-lookup"><span data-stu-id="a4fac-153">If there have been less than five synchronizations with 50 or more changes or the most recent synchronization has less than 50 changes, Replication Monitor does not display a value.</span></span>  
  
     <span data-ttu-id="a4fac-154">A tabela seguinte mostra a correlação entre o desempenho médio e o valor de qualidade de desempenho.</span><span class="sxs-lookup"><span data-stu-id="a4fac-154">The following table shows the correlation between the average performance and the performance quality value.</span></span> <span data-ttu-id="a4fac-155">Por exemplo, se dez Assinantes tiverem sincronizado em uma conexão LAN com uma taxa média de 100 linhas por segundo, e uma das assinaturas sincronizar a uma taxa de 125 linhas por segundo, o desempenho da sincronização do Assinante será 125% da média, resultando em um valor Bom.</span><span class="sxs-lookup"><span data-stu-id="a4fac-155">For example, if ten Subscribers have synchronized over a LAN connection with an average rate of 100 rows per second, and one of the subscriptions then synchronizes at a rate of 125 rows per second, the performance for that Subscriber's synchronization is 125% of the average, resulting in a value of Good.</span></span>  
  
    |<span data-ttu-id="a4fac-156">Excelente</span><span class="sxs-lookup"><span data-stu-id="a4fac-156">Excellent</span></span>|<span data-ttu-id="a4fac-157">Bom</span><span class="sxs-lookup"><span data-stu-id="a4fac-157">Good</span></span>|<span data-ttu-id="a4fac-158">Razoável</span><span class="sxs-lookup"><span data-stu-id="a4fac-158">Fair</span></span>|<span data-ttu-id="a4fac-159">Fraco</span><span class="sxs-lookup"><span data-stu-id="a4fac-159">Poor</span></span>|  
    |---------------|----------|----------|----------|  
    |<span data-ttu-id="a4fac-160">151+%</span><span class="sxs-lookup"><span data-stu-id="a4fac-160">151+%</span></span>|<span data-ttu-id="a4fac-161">76 – 150%</span><span class="sxs-lookup"><span data-stu-id="a4fac-161">76 - 150%</span></span>|<span data-ttu-id="a4fac-162">26 – 75%</span><span class="sxs-lookup"><span data-stu-id="a4fac-162">26 - 75%</span></span>|<span data-ttu-id="a4fac-163">0 – 25%</span><span class="sxs-lookup"><span data-stu-id="a4fac-163">0 - 25%</span></span>|  
  
 <span data-ttu-id="a4fac-164">Para obter mais informações sobre como exibir informações de assinatura, confira [Exibir informações e executar tarefas usando o Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="a4fac-164">For more information about viewing subscription information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
## <a name="determine-latency-with-tracer-tokens"></a><span data-ttu-id="a4fac-165">Determinar a latência com os tokens de rastreamento</span><span class="sxs-lookup"><span data-stu-id="a4fac-165">Determine Latency with Tracer Tokens</span></span>  
 <span data-ttu-id="a4fac-166">A replicação transacional permite medir a latência em um sistema inserindo um token (uma pequena quantidade de dados) no log de transações do banco de dados de publicação e registrando o tempo necessário para chegar até o Distribuidor e os Assinantes.</span><span class="sxs-lookup"><span data-stu-id="a4fac-166">Transactional replication allows you to measure the latency in a system by inserting a token (a small amount of data) in the transaction log of the publication database and recording how long it takes to arrive at the Distributor and Subscribers.</span></span> <span data-ttu-id="a4fac-167">O token permitirá também a identificação de dados que não chegam até o Distribuidor ou Assinante.</span><span class="sxs-lookup"><span data-stu-id="a4fac-167">The token also allows you to identify if data is not reaching the Distributor or Subscriber.</span></span> <span data-ttu-id="a4fac-168">Para obter mais informações, consulte [Medir a latência e validar as conexões para a replicação transacional](measure-latency-and-validate-connections-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="a4fac-168">For more information, see [Measure Latency and Validate Connections for Transactional Replication](measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
## <a name="view-detailed-synchronization-performance-for-merge-replication"></a><span data-ttu-id="a4fac-169">Exibir o desempenho de sincronização detalhado para replicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="a4fac-169">View Detailed Synchronization Performance for Merge Replication</span></span>  
 <span data-ttu-id="a4fac-170">Para a replicação de mesclagem, o Replication Monitor exibe as estatísticas detalhadas para cada artigo processado durante a sincronização, incluindo o tempo gasto em cada fase do processamento (carregar alterações, baixar alterações e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="a4fac-170">For merge replication, Replication Monitor displays detailed statistics for each article processed during synchronization, including the amount of time spent in each processing phase (uploading changes, downloading changes, and so on).</span></span> <span data-ttu-id="a4fac-171">Ajuda a definir tabelas específicas que estão causando lentidão e é o melhor local para a solução de problemas de desempenho com assinaturas de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="a4fac-171">It can help pinpoint specific tables that are causing slow downs and is the best place to troubleshoot performance issues with merge subscriptions.</span></span> <span data-ttu-id="a4fac-172">Para obter mais informações sobre como exibir estatísticas detalhadas, confira [Exibir informações e executar tarefas usando o Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="a4fac-172">For more information on viewing detailed statistics, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
## <a name="view-transactions-and-delivery-time-for-transactional-replication"></a><span data-ttu-id="a4fac-173">Exibir as transações e a hora de entrega para replicação transacional</span><span class="sxs-lookup"><span data-stu-id="a4fac-173">View Transactions and Delivery Time for Transactional Replication</span></span>  
 <span data-ttu-id="a4fac-174">Para replicação transacional, o Replication Monitor exibe informações sobre o número de transações no banco de dados de distribuição que ainda não foi distribuído ao Assinante e o tempo estimado para distribuir essas transações.</span><span class="sxs-lookup"><span data-stu-id="a4fac-174">For transactional replication, Replication Monitor displays information about the number of transactions in the distribution database that have not yet been distributed to a Subscriber and the estimated time for distributing these transactions.</span></span> <span data-ttu-id="a4fac-175">Para obter mais informações, confira [Exibir informações e executar tarefas usando o Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="a4fac-175">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4fac-176">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a4fac-176">See Also</span></span>  
 <span data-ttu-id="a4fac-177">[Monitorando a Replicação](../monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="a4fac-177">[Monitoring Replication](../monitoring-replication.md) </span></span>  
 [<span data-ttu-id="a4fac-178">Definir limites e avisos no Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="a4fac-178">Set Thresholds and Warnings in Replication Monitor</span></span>](set-thresholds-and-warnings-in-replication-monitor.md)  
  
  