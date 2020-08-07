---
title: Exibir o relatório de envio de logs (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- viewing log shipping reports
- displaying log shipping reports
- log shipping [SQL Server], monitoring
- log shipping [SQL Server], viewing reports
ms.assetid: 3b549f2f-3683-45e5-b8e8-8095276c41ab
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0d6c372a9b1f9af9e5948732e3bfb9384362f545
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583775"
---
# <a name="view-the-log-shipping-report-sql-server-management-studio"></a><span data-ttu-id="90b1f-102">Exibir o relatório de envio de logs (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="90b1f-102">View the Log Shipping Report (SQL Server Management Studio)</span></span>
  <span data-ttu-id="90b1f-103">Este tópico explica como exibir o relatório de Status de Envio do Log de Transações no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90b1f-103">This topic explains how to view the Transaction Log Shipping Status report in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="90b1f-104">Você pode executar um relatório de status em um servidor monitor, servidor primário ou servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="90b1f-104">You can run a status report at a monitor server, primary server, or secondary server.</span></span> <span data-ttu-id="90b1f-105">Para ver as informações mais completas sobre sua configuração de envio de logs, exiba o relatório na instância do servidor monitor.</span><span class="sxs-lookup"><span data-stu-id="90b1f-105">To see the  most complete information about your log shipping configuration, view the report at the monitor server instance.</span></span>  
  
 <span data-ttu-id="90b1f-106">O relatório exibe o status de qualquer atividade de envio de logs cujo status esteja disponível a partir da instância de servidor à qual você está conectado.</span><span class="sxs-lookup"><span data-stu-id="90b1f-106">The report displays the status of any log shipping activity whose status is available from the server instance to which you are connected.</span></span> <span data-ttu-id="90b1f-107">Se essa instância de servidor estiver envolvida em várias configurações em funções diferentes (como servir como monitor para um banco de dados e servidor secundário para outro banco de dados), os resultados exibidos conterão as informações de toda a configuração a partir da perspectiva de cada função.</span><span class="sxs-lookup"><span data-stu-id="90b1f-107">If that server instance is involved in multiple configurations in different roles (such as serving as a monitor for one database and a secondary for another database), the displayed results contain the information of every configuration from the perspective of each role.</span></span> <span data-ttu-id="90b1f-108">Se o procedimento armazenado puder conectar-se à instância do servidor monitor para uma determinada configuração de envio de logs, o relatório exibirá um status adicional para essa configuração.</span><span class="sxs-lookup"><span data-stu-id="90b1f-108">If the stored procedure can connect to the monitor server instance for a given log shipping configuration, the report displays additional status for that configuration.</span></span>  
  
 <span data-ttu-id="90b1f-109">Para cada função executada pela instância de servidor atual, você pode exibir as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="90b1f-109">For each role performed by the current server instance, you can view the following information:</span></span>  
  
|<span data-ttu-id="90b1f-110">Função</span><span class="sxs-lookup"><span data-stu-id="90b1f-110">Role</span></span>|<span data-ttu-id="90b1f-111">Informações exibidas</span><span class="sxs-lookup"><span data-stu-id="90b1f-111">Information displayed</span></span>|  
|----------|---------------------------|  
|<span data-ttu-id="90b1f-112">Monitoramento</span><span class="sxs-lookup"><span data-stu-id="90b1f-112">Monitor</span></span>|<span data-ttu-id="90b1f-113">O nome e status de todos os servidores primários e servidores secundários que usam essa instância de servidor como servidor monitor.</span><span class="sxs-lookup"><span data-stu-id="90b1f-113">The name and status of every primary server and secondary server that uses this server instance as its monitor server.</span></span>|  
|<span data-ttu-id="90b1f-114">Primária</span><span class="sxs-lookup"><span data-stu-id="90b1f-114">Primary</span></span>|<span data-ttu-id="90b1f-115">Para cada banco de dados primário, o status e nome da instância de servidor atual (como o servidor primário), junto com o nome de banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="90b1f-115">For each primary database, the status and name of the current server instance (as the primary server), along with the primary database name.</span></span> <span data-ttu-id="90b1f-116">O relatório exibe o status do trabalho de backup (que é armazenado localmente no servidor primário).</span><span class="sxs-lookup"><span data-stu-id="90b1f-116">The report displays the status of the backup job (which is stored locally on the primary server).</span></span><br /><br /> <span data-ttu-id="90b1f-117">O relatório também contém uma linha para cada um dos servidores secundários correspondentes.</span><span class="sxs-lookup"><span data-stu-id="90b1f-117">The report also contains a row for each of the corresponding secondary servers.</span></span> <span data-ttu-id="90b1f-118">Se a configuração usar um servidor monitor e o procedimento armazenado puder conectar-se ao monitor, essas linhas exibirão o status da cópia e o status de restauração do backup de log mais recente.</span><span class="sxs-lookup"><span data-stu-id="90b1f-118">If the configuration uses a monitor server and the stored procedure can connect to the monitor, these rows display the copy status and restore status for the most recent log backup.</span></span>|  
|<span data-ttu-id="90b1f-119">Secundário</span><span class="sxs-lookup"><span data-stu-id="90b1f-119">Secondary</span></span>|<span data-ttu-id="90b1f-120">Para cada banco de dados secundário, o status e nome da instância de servidor atual (como o servidor secundário), junto com o nome de banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="90b1f-120">For each secondary database, the status and name of the current server instance (as the secondary server), along with the secondary database name.</span></span><br /><br /> <span data-ttu-id="90b1f-121">O relatório exibe o status da cópia e trabalhos de restauração no servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="90b1f-121">The report displays the status of the copy and restore jobs at the secondary server.</span></span><br /><br /> <span data-ttu-id="90b1f-122">O relatório também contém uma linha para o servidor primário correspondente.</span><span class="sxs-lookup"><span data-stu-id="90b1f-122">The report also contains a row for the corresponding primary server.</span></span> <span data-ttu-id="90b1f-123">Se a configuração usar um servidor monitor e o procedimento armazenado puder conectar-se ao monitor, essa linha exibirá o status do backup de log mais recente.</span><span class="sxs-lookup"><span data-stu-id="90b1f-123">If the configuration uses a monitor server and the stored procedure can connect to the monitor, this row displays the status of the most recent log backup.</span></span>|  
  
 <span data-ttu-id="90b1f-124">As informações exibidas dependerão de a instância de servidor ser um servidor monitor, servidor primário ou servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="90b1f-124">The information displayed depends on whether the server instance is a monitor server, primary server, or secondary server.</span></span> <span data-ttu-id="90b1f-125">Se as informações não estiverem disponíveis, as células correspondentes ficarão esmaecidas.</span><span class="sxs-lookup"><span data-stu-id="90b1f-125">If information is not available, the corresponding cells are grayed out.</span></span>  
  
 <span data-ttu-id="90b1f-126">O relatório chama **sp_help_log_shipping_monitor** para obter os dados.</span><span class="sxs-lookup"><span data-stu-id="90b1f-126">The report calls **sp_help_log_shipping_monitor** to get the data.</span></span> <span data-ttu-id="90b1f-127">Para obter informações sobre as permissões necessárias, consulte [sp_help_log_shipping_monitor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="90b1f-127">For information about the required permissions, see [sp_help_log_shipping_monitor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-transact-sql).</span></span>  
  
### <a name="to-display-the-transaction-log-shipping-status-report-on-a-server-instance"></a><span data-ttu-id="90b1f-128">Para exibir o relatório de status de envio do log de transações em uma instância de servidor</span><span class="sxs-lookup"><span data-stu-id="90b1f-128">To display the Transaction Log Shipping Status report on a server instance</span></span>  
  
1.  <span data-ttu-id="90b1f-129">Conecte-se a um servidor monitor, servidor primário ou servidor secundário.</span><span class="sxs-lookup"><span data-stu-id="90b1f-129">Connect to a monitor server, primary server, or secondary server.</span></span>  
  
2.  <span data-ttu-id="90b1f-130">Clique com o botão direito do mouse na instância de servidor no Pesquisador de Objetos, aponte para **Relatórios**e aponte para **Relatórios Padrão**.</span><span class="sxs-lookup"><span data-stu-id="90b1f-130">Right-click the server instance in Object Explorer, point to **Reports**, and point to **Standard Reports**.</span></span>  
  
3.  <span data-ttu-id="90b1f-131">Clique em **Status de Envio do Log de Transações**.</span><span class="sxs-lookup"><span data-stu-id="90b1f-131">Click **Transaction Log Shipping Status**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90b1f-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="90b1f-132">See Also</span></span>  
 [<span data-ttu-id="90b1f-133">Monitorar o envio de logs &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="90b1f-133">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
  