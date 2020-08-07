---
title: MSSQL_ENG014162 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014162 error
ms.assetid: a15eef3f-219f-45d3-8286-6a864c85a723
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 78c6eb13087a7f7d5b2711af4484df7a384d7835
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583537"
---
# <a name="mssql_eng014162"></a><span data-ttu-id="aa255-102">MSSQL_ENG014162</span><span class="sxs-lookup"><span data-stu-id="aa255-102">MSSQL_ENG014162</span></span>
    
## <a name="message-details"></a><span data-ttu-id="aa255-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="aa255-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa255-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="aa255-104">Product Name</span></span>|<span data-ttu-id="aa255-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="aa255-105">SQL Server</span></span>|  
|<span data-ttu-id="aa255-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="aa255-106">Event ID</span></span>|<span data-ttu-id="aa255-107">14162</span><span class="sxs-lookup"><span data-stu-id="aa255-107">14162</span></span>|  
|<span data-ttu-id="aa255-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="aa255-108">Event Source</span></span>|<span data-ttu-id="aa255-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="aa255-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="aa255-110">Componente</span><span class="sxs-lookup"><span data-stu-id="aa255-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="aa255-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="aa255-111">Symbolic Name</span></span>||  
|<span data-ttu-id="aa255-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="aa255-112">Message Text</span></span>|<span data-ttu-id="aa255-113">O limite [%s:%s] da publicação [%s] foi definido.</span><span class="sxs-lookup"><span data-stu-id="aa255-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="aa255-114">Verifique se o agente de mesclagem está sendo executado e pode atender ao requisito esperado.</span><span class="sxs-lookup"><span data-stu-id="aa255-114">Please make sure that the merge agent is running and can match the expected requirement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aa255-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="aa255-115">Explanation</span></span>  
 <span data-ttu-id="aa255-116">A replicação permite habilitar avisos para várias condições.</span><span class="sxs-lookup"><span data-stu-id="aa255-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="aa255-117">Isso inclui exceder um período especificado para sincronizar alterações entre uma mesclagem de Publicador e Assinante.</span><span class="sxs-lookup"><span data-stu-id="aa255-117">This includes exceeding a specified length of time for synchronizing changes between a merge Publisher and Subscriber.</span></span> <span data-ttu-id="aa255-118">É possível especificar horários diferentes para conexões discadas e LAN.</span><span class="sxs-lookup"><span data-stu-id="aa255-118">Different times can be specified for LAN connections and dial-up connections.</span></span>  
  
 <span data-ttu-id="aa255-119">Ao habilitar um aviso usando o Replication Monitor ou o [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), você especifica um limite que determina quando um aviso é disparado.</span><span class="sxs-lookup"><span data-stu-id="aa255-119">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="aa255-120">Quando esse limite é atingido ou excedido, um aviso é exibido no Replication Monitor e um evento é gravado no log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="aa255-120">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="aa255-121">Ao atingir um limite, também é possível disparar um alerta do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="aa255-121">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="aa255-122">Para obter mais informações, consulte [Definir limites e avisos no Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) e [Monitorar a replicação de forma programática](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="aa255-122">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aa255-123">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="aa255-123">User Action</span></span>  
 <span data-ttu-id="aa255-124">Se uma assinatura exceder um limite de duração, será necessário determinar se há um problema de desempenho no sistema ou se o limite deve ser ajustado.</span><span class="sxs-lookup"><span data-stu-id="aa255-124">If a subscription exceeds a duration threshold, you must determine whether there is a performance issue with the system or whether the threshold should be adjusted.</span></span> <span data-ttu-id="aa255-125">Após configurar a replicação, desenvolva uma linha de base de desempenho, a qual permitirá determinar como a replicação se comporta com uma carga de trabalho típica para seus aplicativos e topologia.</span><span class="sxs-lookup"><span data-stu-id="aa255-125">After you configure replication, develop a performance baseline that will let you determine how replication behaves with a workload that is typical for your applications and topology.</span></span> <span data-ttu-id="aa255-126">Inclua a duração da sincronização na linha de base para que seja possível definir um valor apropriado para o limite.</span><span class="sxs-lookup"><span data-stu-id="aa255-126">Include duration of synchronization in this baseline so that you can set an appropriate value for the threshold.</span></span>  
  
 <span data-ttu-id="aa255-127">Se o valor do limite for apropriado, mas estiver sendo excedido, será necessário determinar se há algum gargalo no desempenho do sistema.</span><span class="sxs-lookup"><span data-stu-id="aa255-127">If the threshold value is appropriate, but it is being exceeded, you must determine where the performance bottleneck is in the system.</span></span> <span data-ttu-id="aa255-128">Para obter mais informações sobre como monitorar e solucionar problemas relacionados a desempenho de replicação, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="aa255-128">For more information about how to monitor and troubleshoot replication performance, see the following topics:</span></span>  
  
-   <span data-ttu-id="aa255-129">[Monitorar o desempenho com o Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) (especialmente, a seção “Exibindo o desempenho de sincronização detalhado para replicação de mesclagem”)</span><span class="sxs-lookup"><span data-stu-id="aa255-129">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) (especially the section "Viewing Detailed Synchronization Performance for Merge Replication")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa255-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aa255-130">See Also</span></span>  
 [<span data-ttu-id="aa255-131">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="aa255-131">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  