---
title: Atualização e atualização de servidores do grupo de disponibilidade com tempo de inatividade mínimo e perda de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: f670af56-dbcc-4309-9119-f919dcad8a65
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6bac882b93016a430fbcace2d590e6cc087123d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685282"
---
# <a name="upgrade-and-update-of-availability-group-servers-with-minimal-downtime-and-data-loss"></a><span data-ttu-id="1db27-102">Fazer upgrade e atualização dos servidores de grupo de disponibilidade com tempo de inatividade e perda de dados mínimos</span><span class="sxs-lookup"><span data-stu-id="1db27-102">Upgrade and Update of Availability Group Servers with Minimal Downtime and Data Loss</span></span>
  <span data-ttu-id="1db27-103">Ao atualizar ou fazer upgrade de instâncias de servidor do SQL Server 2012 para um service pack ou uma versão mais recente, você pode reduzir o tempo de inatividade de um grupo de disponibilidade para apenas um único failover manual executando uma atualização ou um upgrade sequencial.</span><span class="sxs-lookup"><span data-stu-id="1db27-103">When updating or upgrading server instances from SQL Server 2012 to a service pack or a newer version, you can reduce downtime for an availability group to only a single manual failover by performing a sequential update or upgrade.</span></span> <span data-ttu-id="1db27-104">Para fazer upgrade de versões do SQL Server, essa ação é conhecida como upgrade sem interrupção; para atualizar a versão atual do SQL Server com hotfixes ou service packs, essa ação é conhecida como atualização sem interrupção.</span><span class="sxs-lookup"><span data-stu-id="1db27-104">For upgrading SQL Server versions, it is known as rolling upgrade; for updating the current SQL Server version with hotfixes or service packs, it is known as rolling update.</span></span>  
  
 <span data-ttu-id="1db27-105">Este tópico limita a discussão somente a upgrades/atualizações do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1db27-105">This topic limits the discussion to SQL Server upgrades/updates only.</span></span> <span data-ttu-id="1db27-106">Para upgrades/atualizações relacionadas ao sistema operacional nas quais as instâncias de SQL Server altamente disponíveis estão em execução, consulte [migração entre clusters de grupos de disponibilidade AlwaysOn para atualizações do sistema operacional](https://msdn.microsoft.com/library/jj873730.aspx)</span><span class="sxs-lookup"><span data-stu-id="1db27-106">For operating system-related upgrades/updates that the highly-available SQL Server instances are running on, see [Cross-cluster Migration of AlwaysOn Availability Groups for Operating System Upgrades](https://msdn.microsoft.com/library/jj873730.aspx)</span></span>  
  
## <a name="rolling-upgradeupdate-best-practices-for-alwayson-availability-groups"></a><span data-ttu-id="1db27-107">Práticas recomendadas de upgrade/atualização sem interrupção de grupos de disponibilidade AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="1db27-107">Rolling Upgrade/Update Best Practices for AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="1db27-108">As práticas recomendadas a seguir devem ser observadas durante os upgrades/atualizações de servidor para minimizar o tempo de inatividade e a perda de dados dos grupos de disponibilidade:</span><span class="sxs-lookup"><span data-stu-id="1db27-108">The following best practices should be observed when performing server upgrades/updates in order to minimize downtime and data loss for your availability groups:</span></span>  
  
-   <span data-ttu-id="1db27-109">Antes de iniciar o upgrade/atualização sem interrupção,</span><span class="sxs-lookup"><span data-stu-id="1db27-109">Before starting the rolling upgrade/update,</span></span>  
  
    -   <span data-ttu-id="1db27-110">Execute um failover manual em, pelo menos, uma das réplicas de confirmação síncrona</span><span class="sxs-lookup"><span data-stu-id="1db27-110">Perform a practice manual failover on at least one of your synchronous-commit replicas</span></span>  
  
    -   <span data-ttu-id="1db27-111">Proteja os dados executando um backup completo em cada banco de dados de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="1db27-111">Protect your data by performing a full database backup on every availability database</span></span>  
  
    -   <span data-ttu-id="1db27-112">Execute o comando DBCC CHECKDB em cada banco de dados de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="1db27-112">Run DBCC CHECKDB on every availability database</span></span>  
  
-   <span data-ttu-id="1db27-113">Sempre execute o upgrade/atualização dos nós remotos da réplica secundária primeiro; depois, dos nós locais da réplica secundária; por fim, do nó da réplica primária.</span><span class="sxs-lookup"><span data-stu-id="1db27-113">Always upgrade/update the remote secondary replica nodes first, then local secondary replica nodes next, and the primary replica node last.</span></span>  
  
-   <span data-ttu-id="1db27-114">Os backups não podem ocorrer em um banco de dados que está no processo de ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="1db27-114">Backups cannot occur on a database that is in the process of being upgraded.</span></span>  <span data-ttu-id="1db27-115">Antes de atualizar as réplicas secundárias, configure a preferência de backup automatizado para executar backups apenas na réplica primária.</span><span class="sxs-lookup"><span data-stu-id="1db27-115">Prior to upgrading the secondary replicas, configure the automated backup preference to run backups only on the primary replica.</span></span>  <span data-ttu-id="1db27-116">Antes de atualizar a réplica primária, modifique essa configuração para executar backups apenas nas réplicas secundárias.</span><span class="sxs-lookup"><span data-stu-id="1db27-116">Prior to upgrading the primary replica, modify this setting to run backups only on the secondary replicas.</span></span>  
  
-   <span data-ttu-id="1db27-117">Para proteger o grupo de disponibilidade contra failovers indesejados durante o processo de upgrade/atualização, remova o failover de disponibilidade de todas as réplicas de confirmação síncrona antes de começar.</span><span class="sxs-lookup"><span data-stu-id="1db27-117">To prevent the availability group from unintended failovers during the upgrade/update process, remove availability failover from all synchronous-commit replicas before you begin.</span></span>  
  
-   <span data-ttu-id="1db27-118">Não faça upgrade do nó da réplica primária antes de fazer failover do grupo de disponibilidade para um nó submetido a upgrade com uma réplica secundária primeiro.</span><span class="sxs-lookup"><span data-stu-id="1db27-118">Do not upgrade the primary replica node before failing over the availability group to an upgraded node with a secondary replica first.</span></span> <span data-ttu-id="1db27-119">Do contrário, os aplicativos cliente poderão passar por um longo tempo de inatividade durante o upgrade/atualização na réplica primária.</span><span class="sxs-lookup"><span data-stu-id="1db27-119">Otherwise, client applications may suffer extended downtime during the upgrade/update on the primary replica.</span></span>  
  
-   <span data-ttu-id="1db27-120">Sempre faça failover do grupo de disponibilidade em um nó da réplica secundária de confirmação síncrona.</span><span class="sxs-lookup"><span data-stu-id="1db27-120">Always fail over the availability group to a synchronous-commit secondary replica node.</span></span> <span data-ttu-id="1db27-121">Se você fizer failover para uma réplica secundária de confirmação assíncrona, os bancos de dados sofrerão perda de dados, e a movimentação dos dados será automaticamente suspensa até que você a retome manualmente.</span><span class="sxs-lookup"><span data-stu-id="1db27-121">If you fail over to an asynchronous-commit secondary replica, the databases will suffer data loss, and data movement is automatically suspended until you manually resume data movement.</span></span>  
  
-   <span data-ttu-id="1db27-122">Não faça upgrade/atualização do nó da réplica primária antes de fazer upgrade/atualização de qualquer outro nó da réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="1db27-122">Do not upgrade/update the primary replica node before upgrading/updating any other secondary replica nodes.</span></span> <span data-ttu-id="1db27-123">Uma réplica primária submetida a upgrade não pode mais enviar logs para nenhuma réplica secundária que ainda não tenha sido submetida a upgrade para a mesma versão.</span><span class="sxs-lookup"><span data-stu-id="1db27-123">An upgraded primary replica can no longer ship logs to any secondary replica that has not yet been upgraded to the same version.</span></span> <span data-ttu-id="1db27-124">Quando a movimentação dos dados para uma réplica secundária for suspensa, nenhum failover automático poderá ocorrer nessa réplica, e os bancos de dados de disponibilidade ficarão vulneráveis à perda de dados.</span><span class="sxs-lookup"><span data-stu-id="1db27-124">When data movement to a secondary replica is suspended, no automatic failover can occur for that replica, and your availability databases are vulnerable to data loss.</span></span>  
  
-   <span data-ttu-id="1db27-125">Antes de fazer failover em um grupo de disponibilidade, verifique se o estado da sincronização do destino do failover é SINCRONIZADO.</span><span class="sxs-lookup"><span data-stu-id="1db27-125">Before failing over an availability group, verify that the synchronization state of the failover target is SYNCHRONIZED.</span></span>  
  
## <a name="rolling-upgradeupdate-process"></a><span data-ttu-id="1db27-126">Processo de upgrade/atualização sem interrupção</span><span class="sxs-lookup"><span data-stu-id="1db27-126">Rolling Upgrade/Update Process</span></span>  
 <span data-ttu-id="1db27-127">Na prática, o processo exato dependerá de fatores como a topologia da implantação dos grupos de disponibilidade e o modo de confirmação de cada réplica.</span><span class="sxs-lookup"><span data-stu-id="1db27-127">In practice, the exact process will depend on factors such as the deployment topology of your availability groups and the commit mode of each replica.</span></span> <span data-ttu-id="1db27-128">Mas, no cenário mais simples, o upgrade/atualização sem interrupção é um processo de vários estágios que, na sua forma mais simples, envolve as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="1db27-128">But in the simplest scenario, a rolling upgrade/update is a multi-stage process that in its simplest form involves the following steps:</span></span>  
  
 <span data-ttu-id="1db27-129">![Atualização do Grupo de Disponibilidade no Cenário HADR](../../media/alwaysonupgrade-ag-hadr.gif "Atualização do Grupo de Disponibilidade no Cenário HADR")</span><span class="sxs-lookup"><span data-stu-id="1db27-129">![Availability Group Upgrade in HADR Scenario](../../media/alwaysonupgrade-ag-hadr.gif "Availability Group Upgrade in HADR Scenario")</span></span>  
  
1.  <span data-ttu-id="1db27-130">Remover o failover automático em todas as réplicas de confirmação síncrona</span><span class="sxs-lookup"><span data-stu-id="1db27-130">Remove automatic failover on all synchronous-commit replicas</span></span>  
  
2.  <span data-ttu-id="1db27-131">Fazer upgrade/atualização de todas as instâncias de servidor remotas que executam réplicas secundárias de confirmação assíncrona</span><span class="sxs-lookup"><span data-stu-id="1db27-131">Upgrade/update all remote server instances running asynchronous-commit secondary replicas</span></span>  
  
3.  <span data-ttu-id="1db27-132">Fazer upgrade/atualização de todas as instâncias de servidor locais que não estão executando a réplica primária</span><span class="sxs-lookup"><span data-stu-id="1db27-132">Upgrade/update the all local server instances that are not currently running the primary replica</span></span>  
  
4.  <span data-ttu-id="1db27-133">Fazer o failover manual do grupo de disponibilidade em uma réplica secundária de confirmação síncrona</span><span class="sxs-lookup"><span data-stu-id="1db27-133">Manually fail over the availability group to a synchronous-commit secondary replica</span></span>  
  
5.  <span data-ttu-id="1db27-134">Fazer upgrade/atualização da instância de servidor que hospedava a réplica primária</span><span class="sxs-lookup"><span data-stu-id="1db27-134">Upgrade/update the server instance that formerly hosted the primary replica</span></span>  
  
6.  <span data-ttu-id="1db27-135">Configurar parceiros de failover automático conforme desejado</span><span class="sxs-lookup"><span data-stu-id="1db27-135">Configure automatic failover partners as desired</span></span>  
  
 <span data-ttu-id="1db27-136">Se necessário, você pode executar um failover manual extra para retornar o grupo de disponibilidade à sua configuração original.</span><span class="sxs-lookup"><span data-stu-id="1db27-136">If necessary, you can perform an extra manual failover to return the availability group to its original configuration.</span></span>  
  
## <a name="availability-group-with-one-remote-secondary-replica"></a><span data-ttu-id="1db27-137">Grupo de disponibilidade com uma réplica secundária remota</span><span class="sxs-lookup"><span data-stu-id="1db27-137">Availability Group with One Remote Secondary Replica</span></span>  
 <span data-ttu-id="1db27-138">Se você tiver implantado um grupo de disponibilidade somente para recuperação de desastre, talvez seja necessário fazer failover do grupo de disponibilidade para uma réplica secundária de confirmação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="1db27-138">If you have deployed an availability group only for disaster recovery, you may need to fail over the availability group to an asynchronous-commit secondary replica.</span></span> <span data-ttu-id="1db27-139">Essa configuração é ilustrada na figura a seguir:</span><span class="sxs-lookup"><span data-stu-id="1db27-139">Such configuration is illustrated by the following figure:</span></span>  
  
 <span data-ttu-id="1db27-140">![Atualização do Grupo de Disponibilidade no Cenário DR](../../media/agupgrade-ag-dr.gif "Atualização do Grupo de Disponibilidade no Cenário DR")</span><span class="sxs-lookup"><span data-stu-id="1db27-140">![Availability Group Upgrade in DR Scenario](../../media/agupgrade-ag-dr.gif "Availability Group Upgrade in DR Scenario")</span></span>  
  
 <span data-ttu-id="1db27-141">Nesse caso, você deve fazer failover do grupo de disponibilidade para uma réplica secundária de confirmação assíncrona durante o upgrade/atualização sem interrupção.</span><span class="sxs-lookup"><span data-stu-id="1db27-141">In this situation, you must fail over the availability group to the asynchronous-commit secondary replica during the rolling upgrade/update.</span></span> <span data-ttu-id="1db27-142">Para evitar a perda de dados, altere o modo de confirmação para confirmação síncrona e aguarde a réplica secundária ser sincronizada para que você possa fazer o failover do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="1db27-142">To prevent data loss, change the commit mode to synchronous commit and wait for the secondary replica to be synchronized before you fail over the availability group.</span></span> <span data-ttu-id="1db27-143">Portanto, o processo de upgrade/atualização sem interrupção possivelmente será o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1db27-143">Therefore, the rolling upgrade/update process may look as follows:</span></span>  
  
1.  <span data-ttu-id="1db27-144">Fazer o upgrade/atualização do servidor remoto</span><span class="sxs-lookup"><span data-stu-id="1db27-144">Upgrade/update the remote server</span></span>  
  
2.  <span data-ttu-id="1db27-145">Alterar o modo de confirmação para confirmação síncrona</span><span class="sxs-lookup"><span data-stu-id="1db27-145">Change the commit mode to synchronous commit</span></span>  
  
3.  <span data-ttu-id="1db27-146">Aguardar até que o estado da sincronização seja SINCRONIZADO</span><span class="sxs-lookup"><span data-stu-id="1db27-146">Wait until synchronization state is SYNCHRONIZED</span></span>  
  
4.  <span data-ttu-id="1db27-147">Fazer failover do grupo de disponibilidade para o site remoto</span><span class="sxs-lookup"><span data-stu-id="1db27-147">Fail over the availability group to the remote site</span></span>  
  
5.  <span data-ttu-id="1db27-148">Fazer o upgrade/atualização do servidor local (site primário)</span><span class="sxs-lookup"><span data-stu-id="1db27-148">Upgrade/update the local (primary site) server</span></span>  
  
6.  <span data-ttu-id="1db27-149">Fazer failover do grupo de disponibilidade para o site primário</span><span class="sxs-lookup"><span data-stu-id="1db27-149">Fail over the availability group to the primary site</span></span>  
  
7.  <span data-ttu-id="1db27-150">Alterar o modo de confirmação para confirmação assíncrona</span><span class="sxs-lookup"><span data-stu-id="1db27-150">Change the commit mode to asynchronous commit</span></span>  
  
 <span data-ttu-id="1db27-151">Como o modo de confirmação síncrona não é uma configuração recomendada para a sincronização de dados em um site remoto, os aplicativos cliente podem observar um aumento imediato na latência do banco de dados depois que a configuração é alterada.</span><span class="sxs-lookup"><span data-stu-id="1db27-151">Since the synchronous-commit mode is not a recommended setting for data synchronization to a remote site, client applications may notice an immediate increase in database latency after the setting change.</span></span> <span data-ttu-id="1db27-152">Além disso, a execução de um failover fará com que todas as mensagens de log não confirmadas sejam descartadas.</span><span class="sxs-lookup"><span data-stu-id="1db27-152">Moreover, performing a failover will cause all unacknowledged log messages to be discarded.</span></span> <span data-ttu-id="1db27-153">A quantidade de mensagens de log descartadas pode ser muito grande devido à alta latência da rede entre os dois sites, fazendo com que os clientes experimentem um alto volume de falha transacional.</span><span class="sxs-lookup"><span data-stu-id="1db27-153">The amount of discarded log messages can be quite large due to the high network latency between the two sites, causing clients to experience a high volume of transactional failure.</span></span> <span data-ttu-id="1db27-154">Você pode minimizar o impacto nos aplicativos cliente fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1db27-154">You can minimize impact to client applications by doing the following:</span></span>  
  
-   <span data-ttu-id="1db27-155">Selecione cuidadosamente uma janela de manutenção durante o baixo tráfego do cliente</span><span class="sxs-lookup"><span data-stu-id="1db27-155">Carefully select a maintenance window during low client traffic</span></span>  
  
-   <span data-ttu-id="1db27-156">Durante o upgrade/atualização do SQL Server no site primário, altere o modo de disponibilidade novamente para confirmação assíncrona e, em seguida, reverta para confirmação síncrona quando estiver pronto para fazer failover para o site primário novamente</span><span class="sxs-lookup"><span data-stu-id="1db27-156">While upgrading/updating SQL Server on the primary site, change the availability mode back to asynchronous commit, then revert to synchronous commit when you are ready to fail over to the primary site again</span></span>  
  
## <a name="availability-group-with-failover-cluster-instance-nodes"></a><span data-ttu-id="1db27-157">Grupo de disponibilidade com nós de instância de cluster de failover</span><span class="sxs-lookup"><span data-stu-id="1db27-157">Availability Group with Failover Cluster Instance Nodes</span></span>  
 <span data-ttu-id="1db27-158">Se um grupo de disponibilidade contiver nós de FCI (instância de cluster de failover), você deverá fazer upgrade/atualização dos nós inativos antes de fazer upgrade/atualização dos nós ativos.</span><span class="sxs-lookup"><span data-stu-id="1db27-158">If an availability group contains failover cluster instance (FCI) nodes, you should upgrade/update the inactive nodes before you upgrade/update the active nodes.</span></span> <span data-ttu-id="1db27-159">A figura a seguir ilustra um cenário de grupo de disponibilidade comum com FCIs para alta disponibilidade local e confirmação assíncrona entre as FCIs de recuperação de desastre remota, e a sequência de upgrade.</span><span class="sxs-lookup"><span data-stu-id="1db27-159">The figure below illustrates a common availability group scenario with FCIs for local high availability and asynchronous commit between the FCIs for remote disaster recovery, and the upgrade sequence.</span></span>  
  
 <span data-ttu-id="1db27-160">![Atualização do Grupo de Disponibilidade com FCIs](../../media/agupgrade-ag-fci-dr.gif "Atualização do Grupo de Disponibilidade com FCIs")</span><span class="sxs-lookup"><span data-stu-id="1db27-160">![Availability Group Upgrade with FCIs](../../media/agupgrade-ag-fci-dr.gif "Availability Group Upgrade with FCIs")</span></span>  
  
1.  <span data-ttu-id="1db27-161">Fazer upgrade/atualização de REMOTE2</span><span class="sxs-lookup"><span data-stu-id="1db27-161">Upgrade/update REMOTE2</span></span>  
  
2.  <span data-ttu-id="1db27-162">Fazer failover de FCI2 para REMOTE2</span><span class="sxs-lookup"><span data-stu-id="1db27-162">Fail over FCI2 to REMOTE2</span></span>  
  
3.  <span data-ttu-id="1db27-163">Fazer upgrade/atualização de REMOTE1</span><span class="sxs-lookup"><span data-stu-id="1db27-163">Upgrade/update REMOTE1</span></span>  
  
4.  <span data-ttu-id="1db27-164">Fazer upgrade/atualização de PRIMARY2</span><span class="sxs-lookup"><span data-stu-id="1db27-164">Upgrade/update PRIMARY2</span></span>  
  
5.  <span data-ttu-id="1db27-165">Fazer failover de FCI1 para PRIMARY2</span><span class="sxs-lookup"><span data-stu-id="1db27-165">Fail over FCI1 to PRIMARY2</span></span>  
  
6.  <span data-ttu-id="1db27-166">Fazer upgrade/atualização de PRIMARY1</span><span class="sxs-lookup"><span data-stu-id="1db27-166">Upgrade/update PRIMARY1</span></span>  
  
## <a name="upgradeupdate-sql-server-instances-with-multiple-availability-groups"></a><span data-ttu-id="1db27-167">Fazer upgrade/atualização de instâncias do SQL Server com vários grupos de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="1db27-167">Upgrade/Update SQL Server Instances with Multiple Availability Groups</span></span>  
 <span data-ttu-id="1db27-168">Se você estiver executando vários grupos de disponibilidade com réplicas primárias em nós de servidor separados (uma configuração Ativo/Ativo), o caminho do upgrade/atualização envolverá mais etapas de failover para preservar a alta disponibilidade no processo.</span><span class="sxs-lookup"><span data-stu-id="1db27-168">If you are running multiple availability groups with primary replicas on separate server nodes (an Active/Active configuration), the upgrade/update path involves more failover steps to preserve high availability in the process.</span></span> <span data-ttu-id="1db27-169">Suponhamos que você esteja executando três grupos de disponibilidade nos três nós de servidor, conforme mostrado na tabela a seguir, e que todas as réplicas secundárias estejam em execução no modo de confirmação síncrona.</span><span class="sxs-lookup"><span data-stu-id="1db27-169">Suppose you are running three availability groups on three server nodes as shown in the following table, and all secondary replicas are running in synchronous-commit mode.</span></span>  
  
|<span data-ttu-id="1db27-170">Grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="1db27-170">Availability Group</span></span>|<span data-ttu-id="1db27-171">Node1</span><span class="sxs-lookup"><span data-stu-id="1db27-171">Node1</span></span>|<span data-ttu-id="1db27-172">Node2</span><span class="sxs-lookup"><span data-stu-id="1db27-172">Node2</span></span>|<span data-ttu-id="1db27-173">Node3</span><span class="sxs-lookup"><span data-stu-id="1db27-173">Node3</span></span>|  
|------------------------|-----------|-----------|-----------|  
|<span data-ttu-id="1db27-174">AG1</span><span class="sxs-lookup"><span data-stu-id="1db27-174">AG1</span></span>|<span data-ttu-id="1db27-175">Primária</span><span class="sxs-lookup"><span data-stu-id="1db27-175">Primary</span></span>|||  
|<span data-ttu-id="1db27-176">AG2</span><span class="sxs-lookup"><span data-stu-id="1db27-176">AG2</span></span>||<span data-ttu-id="1db27-177">Primária</span><span class="sxs-lookup"><span data-stu-id="1db27-177">Primary</span></span>||  
|<span data-ttu-id="1db27-178">AG3</span><span class="sxs-lookup"><span data-stu-id="1db27-178">AG3</span></span>|||<span data-ttu-id="1db27-179">Primária</span><span class="sxs-lookup"><span data-stu-id="1db27-179">Primary</span></span>|  
  
 <span data-ttu-id="1db27-180">Talvez seja apropriado na sua situação executar um upgrade/atualização sem interrupção com balanceamento de carga na sequência a seguir:</span><span class="sxs-lookup"><span data-stu-id="1db27-180">It may be appropriate in your situation to perform a load-balanced rolling upgrade/update in the following sequence:</span></span>  
  
1.  <span data-ttu-id="1db27-181">Fazer failover de AG2 para Node3 (para liberar Node2)</span><span class="sxs-lookup"><span data-stu-id="1db27-181">Fail over AG2 to Node3 (to free up Node2)</span></span>  
  
2.  <span data-ttu-id="1db27-182">Fazer upgrade/atualização de Node2</span><span class="sxs-lookup"><span data-stu-id="1db27-182">Upgrade/update Node2</span></span>  
  
3.  <span data-ttu-id="1db27-183">Fazer failover de AG1 para Node2 (para liberar Node1)</span><span class="sxs-lookup"><span data-stu-id="1db27-183">Fail over AG1 to Node2 (to free up Node1)</span></span>  
  
4.  <span data-ttu-id="1db27-184">Fazer upgrade/atualização de Node1</span><span class="sxs-lookup"><span data-stu-id="1db27-184">Upgrade/update Node1</span></span>  
  
5.  <span data-ttu-id="1db27-185">Fazer failover de AG2 e AG3 para Node1 (para liberar Node3)</span><span class="sxs-lookup"><span data-stu-id="1db27-185">Fail over both AG2 and AG3 to Node1 (to free up Node3)</span></span>  
  
6.  <span data-ttu-id="1db27-186">Fazer upgrade/atualização de Node3</span><span class="sxs-lookup"><span data-stu-id="1db27-186">Upgrade/update Node3</span></span>  
  
7.  <span data-ttu-id="1db27-187">Fazer failover de AG3 para Node3</span><span class="sxs-lookup"><span data-stu-id="1db27-187">Fail over AG3 to Node3</span></span>  
  
 <span data-ttu-id="1db27-188">Essa sequência de upgrade/atualização tem um tempo de inatividade médio inferior a dois failovers por grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="1db27-188">This upgrade/update sequence has an average downtime of less than two failovers per availability group.</span></span> <span data-ttu-id="1db27-189">A configuração resultante é mostrada na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="1db27-189">The resulting configuration is shown in the table below.</span></span>  
  
|<span data-ttu-id="1db27-190">Grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="1db27-190">Availability Group</span></span>|<span data-ttu-id="1db27-191">Node1</span><span class="sxs-lookup"><span data-stu-id="1db27-191">Node1</span></span>|<span data-ttu-id="1db27-192">Node2</span><span class="sxs-lookup"><span data-stu-id="1db27-192">Node2</span></span>|<span data-ttu-id="1db27-193">Node3</span><span class="sxs-lookup"><span data-stu-id="1db27-193">Node3</span></span>|  
|------------------------|-----------|-----------|-----------|  
|<span data-ttu-id="1db27-194">AG1</span><span class="sxs-lookup"><span data-stu-id="1db27-194">AG1</span></span>||<span data-ttu-id="1db27-195">Primária</span><span class="sxs-lookup"><span data-stu-id="1db27-195">Primary</span></span>||  
|<span data-ttu-id="1db27-196">AG2</span><span class="sxs-lookup"><span data-stu-id="1db27-196">AG2</span></span>|<span data-ttu-id="1db27-197">Primária</span><span class="sxs-lookup"><span data-stu-id="1db27-197">Primary</span></span>|||  
|<span data-ttu-id="1db27-198">AG3</span><span class="sxs-lookup"><span data-stu-id="1db27-198">AG3</span></span>|||<span data-ttu-id="1db27-199">Primária</span><span class="sxs-lookup"><span data-stu-id="1db27-199">Primary</span></span>|  
  
 <span data-ttu-id="1db27-200">Com base na sua implementação, o caminho do upgrade/atualização pode variar, bem como o tempo de inatividade experimentado pelos aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="1db27-200">Based on your specific implementation, your upgrade/update path may vary, and the downtime that client applications experience may vary as well.</span></span>  
  
  