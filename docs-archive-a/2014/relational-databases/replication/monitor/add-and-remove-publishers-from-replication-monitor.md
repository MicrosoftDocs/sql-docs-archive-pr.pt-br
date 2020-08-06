---
title: Adicionar e remover publicadores do Replication Monitor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor, adding and removing Publishers
ms.assetid: fa36c4b4-bfa5-494e-92e3-07a02d7332c3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 16c2876b55541e347e4e638132f36ad33932abb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685566"
---
# <a name="add-and-remove-publishers-from-replication-monitor"></a><span data-ttu-id="0fe0a-102">Adicionar e remover Publicadores do Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="0fe0a-102">Add and Remove Publishers from Replication Monitor</span></span>
  <span data-ttu-id="0fe0a-103">O servidor no qual você inicia o Replication Monitor será adicionado automaticamente ao monitor se for um Publicador.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-103">The server from which you launch Replication Monitor is automatically added to the monitor if it is a Publisher.</span></span> <span data-ttu-id="0fe0a-104">Publicadores adicionais podem ser adicionados na caixa de diálogo **Adicionar Publicador** .</span><span class="sxs-lookup"><span data-stu-id="0fe0a-104">Additional Publishers can be added through the **Add Publisher** dialog box.</span></span> <span data-ttu-id="0fe0a-105">Depois de adicionar um Publicador, será exibido em um grupo no painel esquerdo do monitor.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-105">After adding a Publisher, it is displayed in a group in the left pane of the monitor.</span></span> <span data-ttu-id="0fe0a-106">O grupo **Meus Publicadores** é incluído por padrão, mas você pode criar novos grupos para gerenciar uma ou mais topologias de replicação.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-106">The **My Publishers** group is included by default, but you can create new groups to manage one or more replication topologies.</span></span> <span data-ttu-id="0fe0a-107">Para obter informações sobre como iniciar o Replication Monitor, consulte [Start the Replication Monitor](start-the-replication-monitor.md) (Iniciar o Replication Monitor).</span><span class="sxs-lookup"><span data-stu-id="0fe0a-107">For information about starting Replication Monitor, see [Start the Replication Monitor](start-the-replication-monitor.md).</span></span>  
  
### <a name="to-add-a-sql-server-publisher"></a><span data-ttu-id="0fe0a-108">Para adicionar um Editor SQL Server</span><span class="sxs-lookup"><span data-stu-id="0fe0a-108">To add a SQL Server Publisher</span></span>  
  
1.  <span data-ttu-id="0fe0a-109">Clique com o botão direito do mouse no nó **Replication Monitor** ou em um nó do Grupo do publicador no painel esquerdo e, então, clique em **Adicionar Publicador**.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-109">Right-click the **Replication Monitor** node or a Publisher group node in the left pane, and then click **Add Publisher**.</span></span>  
  
2.  <span data-ttu-id="0fe0a-110">Na caixa de diálogo **Adicionar Publicador** , clique em **Adicionar**e, então, clique em **Adicionar um Editor SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-110">In the **Add Publisher** dialog box, click **Add**, and then click **Add SQL Server Publisher**.</span></span>  
  
3.  <span data-ttu-id="0fe0a-111">Na caixa de diálogo **Conectar ao Servidor** , digite o nome do Publicador e selecione o tipo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-111">In the **Connect to Server** dialog box, enter the name of the Publisher, and then select the authentication type.</span></span> <span data-ttu-id="0fe0a-112">Se você selecionar **Autenticação do SQL Server**, digite um logon e senha.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-112">If you select **SQL Server Authentication**, enter a login and password.</span></span> <span data-ttu-id="0fe0a-113">As credenciais que você especificar serão salvas pelo Replication Monitor para usar ao conectar-se a esse servidor no futuro.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-113">The credentials you specify are saved by Replication Monitor to use when connecting to this server in the future.</span></span> <span data-ttu-id="0fe0a-114">A conta do Windows ou o logon do SQL Server especificado deve ser um membro da função de servidor fixa **sysadmin** ou membro da função de banco de dados fixa **replmonitor** no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-114">The Windows account or SQL Server login specified must be a member of the **sysadmin** fixed server role or a member of the **replmonitor** fixed database role in the distribution database.</span></span>  
  
4.  <span data-ttu-id="0fe0a-115">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-115">Click **Connect**.</span></span> <span data-ttu-id="0fe0a-116">Se o Publicador usar um Distribuidor remoto, você receberá uma solicitação para conectar-se ao Distribuidor na caixa de diálogo **Conectar ao Servidor** .</span><span class="sxs-lookup"><span data-stu-id="0fe0a-116">If the Publisher uses a remote Distributor, you will be prompted to connect to the Distributor in the **Connect to Server** dialog box.</span></span> <span data-ttu-id="0fe0a-117">As credenciais que você especificar serão salvas pelo Replication Monitor para usar ao conectar-se a esse servidor no futuro.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-117">The credentials you specify are saved by Replication Monitor to use when connecting to this server in the future.</span></span> <span data-ttu-id="0fe0a-118">A conta do Windows ou o logon do SQL Server especificado deve ser um membro da função de servidor fixa **sysadmin** ou membro da função de banco de dados fixa **replmonitor** no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-118">The Windows account or SQL Server login specified must be a member of the **sysadmin** fixed server role or a member of the **replmonitor** fixed database role in the distribution database.</span></span>  
  
5.  <span data-ttu-id="0fe0a-119">O nome do Publicador e do Distribuidor são exibidos na grade **Iniciar a monitoração nos seguintes Publicadores** .</span><span class="sxs-lookup"><span data-stu-id="0fe0a-119">The name of the Publisher and Distributor are displayed in the **Start monitoring the following Publisher(s)** grid.</span></span>  
  
6.  <span data-ttu-id="0fe0a-120">Para especificar opções de atualização e conexão com o Publicador, selecione o Publicador na grade e modifique as opções, se necessário.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-120">To specify refresh and connection options for the Publisher, select the Publisher in the grid, and modify options as necessary.</span></span> <span data-ttu-id="0fe0a-121">Para obter mais informações sobre essas opções de atualização, consulte [Caching, Refresh, and Replication Monitor Performance](caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="0fe0a-121">For more information about refresh options, see [Caching, Refresh, and Replication Monitor Performance](caching-refresh-and-replication-monitor-performance.md).</span></span>  
  
7.  <span data-ttu-id="0fe0a-122">Selecione o grupo no qual o Publicador deverá ser exibido no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-122">Select the group under which the Publisher should be displayed in Replication Monitor.</span></span> <span data-ttu-id="0fe0a-123">Para criar um novo grupo, clique em **Novo Grupo**e digite o nome do grupo; selecione o grupo na lista **Mostrar esses Publicadores no seguinte grupo** .</span><span class="sxs-lookup"><span data-stu-id="0fe0a-123">To create a new group, click **New Group**, and then enter a group name; select the group in the **Show this Publisher(s) in the following group** list.</span></span>  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-add-an-oracle-publisher"></a><span data-ttu-id="0fe0a-124">Para adicionar um Editor Oracle</span><span class="sxs-lookup"><span data-stu-id="0fe0a-124">To add an Oracle Publisher</span></span>  
  
1.  <span data-ttu-id="0fe0a-125">Clique com o botão direito do mouse no nó **Replication Monitor** ou em um nó do Grupo do publicador no painel esquerdo e, então, clique em **Adicionar Publicador**.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-125">Right-click the **Replication Monitor** node or a Publisher group node in the left pane, and then click **Add Publisher**.</span></span>  
  
2.  <span data-ttu-id="0fe0a-126">Na caixa de diálogo **Adicionar Publicador** , clique em **Adicionar**e, então, clique em **Adicionar um Editor Oracle**.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-126">In the **Add Publisher** dialog box, click **Add**, and then click **Add Oracle Publisher**.</span></span>  
  
3.  <span data-ttu-id="0fe0a-127">Na caixa de diálogo **Conectar ao Servidor**, digite o nome do Distribuidor [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] associado ao Editor Oracle e então selecione o tipo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-127">In the **Connect to Server** dialog box, enter the name of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributor associated with the Oracle Publisher, and then select the authentication type.</span></span> <span data-ttu-id="0fe0a-128">Se você selecionar **Autenticação do SQL Server**, digite um logon e senha.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-128">If you select **SQL Server Authentication**, enter a login and password.</span></span> <span data-ttu-id="0fe0a-129">As credenciais que você especificar serão salvas pelo Replication Monitor para usar ao conectar-se a esse servidor no futuro.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-129">The credentials you specify are saved by Replication Monitor to use when connecting to this server in the future.</span></span> <span data-ttu-id="0fe0a-130">A conta do Windows ou o logon do SQL Server especificado deve ser um membro da função de servidor fixa **sysadmin** ou membro da função de banco de dados fixa **replmonitor** no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-130">The Windows account or SQL Server login specified must be a member of the **sysadmin** fixed server role or a member of the **replmonitor** fixed database role in the distribution database.</span></span>  
  
4.  <span data-ttu-id="0fe0a-131">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-131">Click **Connect**.</span></span>  
  
5.  <span data-ttu-id="0fe0a-132">O nome do Publicador e do Distribuidor são exibidos na grade **Iniciar a monitoração nos seguintes Publicadores** .</span><span class="sxs-lookup"><span data-stu-id="0fe0a-132">The name of the Publisher and Distributor are displayed in the **Start monitoring the following Publisher(s)** grid.</span></span>  
  
6.  <span data-ttu-id="0fe0a-133">Para especificar opções de atualização e conexão com o Publicador, selecione o Publicador na grade e modifique as opções, se necessário.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-133">To specify refresh and connection options for the Publisher, select the Publisher in the grid, and modify options as necessary.</span></span> <span data-ttu-id="0fe0a-134">Para obter mais informações sobre essas opções de atualização, consulte [Caching, Refresh, and Replication Monitor Performance](caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="0fe0a-134">For more information about refresh options, see [Caching, Refresh, and Replication Monitor Performance](caching-refresh-and-replication-monitor-performance.md).</span></span>  
  
7.  <span data-ttu-id="0fe0a-135">Selecione o grupo no qual o Publicador deverá ser exibido no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-135">Select the group under which the Publisher should be displayed in Replication Monitor.</span></span> <span data-ttu-id="0fe0a-136">Para criar um novo grupo, clique em **Novo Grupo**e digite o nome do grupo; selecione o grupo na lista **Mostrar esses Publicadores no seguinte grupo** .</span><span class="sxs-lookup"><span data-stu-id="0fe0a-136">To create a new group, click **New Group**, and then enter a group name; select the group in the **Show this Publisher(s) in the following group** list.</span></span>  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-add-one-or-more-publishers-that-use-the-same-distributor"></a><span data-ttu-id="0fe0a-137">Para adicionar um ou mais Publicadores que usam o mesmo Distribuidor</span><span class="sxs-lookup"><span data-stu-id="0fe0a-137">To add one or more Publishers that use the same Distributor</span></span>  
  
1.  <span data-ttu-id="0fe0a-138">Clique com o botão direito do mouse no nó **Replication Monitor** ou em um nó do Grupo do publicador no painel esquerdo e, então, clique em **Adicionar Publicador**.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-138">Right-click the **Replication Monitor** node or a Publisher group node in the left pane, and then click **Add Publisher**.</span></span>  
  
2.  <span data-ttu-id="0fe0a-139">Na caixa de diálogo **Adicionar Publicador** , clique em **Adicionar**e então clique em **Especificar um Distribuidor e Adicionar seus Publicadores**.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-139">In the **Add Publisher** dialog box, click **Add**, and then click **Specify a Distributor and Add Its Publishers**.</span></span>  
  
3.  <span data-ttu-id="0fe0a-140">Na caixa de diálogo **Conectar ao Servidor** , digite o nome do Distribuidor e selecione o tipo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-140">In the **Connect to Server** dialog box, enter the name of the Distributor, and then select the authentication type.</span></span> <span data-ttu-id="0fe0a-141">Se você selecionar **Autenticação do SQL Server**, digite um logon e senha.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-141">If you select **SQL Server Authentication**, enter a login and password.</span></span> <span data-ttu-id="0fe0a-142">As credenciais que você especificar serão salvas pelo Replication Monitor para usar ao conectar-se a esse servidor no futuro.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-142">The credentials you specify are saved by Replication Monitor to use when connecting to this server in the future.</span></span> <span data-ttu-id="0fe0a-143">A conta do Windows ou o logon do SQL Server especificado deve ser um membro da função de servidor fixa **sysadmin** ou membro da função de banco de dados fixa **replmonitor** no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-143">The Windows account or SQL Server login specified must be a member of the **sysadmin** fixed server role or a member of the **replmonitor** fixed database role in the distribution database.</span></span>  
  
4.  <span data-ttu-id="0fe0a-144">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-144">Click **Connect**.</span></span>  
  
5.  <span data-ttu-id="0fe0a-145">O nome do Distribuidor e de cada Publicador são exibidos na grade **Iniciar a monitoração nos seguintes Publicadores** .</span><span class="sxs-lookup"><span data-stu-id="0fe0a-145">The name of the Distributor and each Publisher are displayed in the **Start monitoring the following Publisher(s)** grid.</span></span> <span data-ttu-id="0fe0a-146">Se um Publicador já foi adicionado ao Replication Monitor, não será exibido na grade.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-146">If a Publisher has already been added to Replication Monitor, it does not appear in the grid.</span></span>  
  
6.  <span data-ttu-id="0fe0a-147">Para especificar opções de atualização e conexão com o Publicador, selecione o Publicador na grade e modifique as opções, se necessário.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-147">To specify refresh and connection options for the Publisher, select the Publisher in the grid, and modify options as necessary.</span></span> <span data-ttu-id="0fe0a-148">Para obter mais informações sobre essas opções de atualização, consulte [Caching, Refresh, and Replication Monitor Performance](caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="0fe0a-148">For more information about refresh options, see [Caching, Refresh, and Replication Monitor Performance](caching-refresh-and-replication-monitor-performance.md).</span></span>  
  
7.  <span data-ttu-id="0fe0a-149">Selecione o grupo no qual os Publicadores deverão ser exibidos no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-149">Select the group under which Publishers should be displayed in Replication Monitor.</span></span> <span data-ttu-id="0fe0a-150">Para criar um novo grupo, clique em **Novo Grupo**e digite o nome do grupo; selecione o grupo na lista **Mostrar esses Publicadores no seguinte grupo** .</span><span class="sxs-lookup"><span data-stu-id="0fe0a-150">To create a new group, click **New Group**, and then enter a group name; select the group in the **Show this Publisher(s) in the following group** list.</span></span>  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-modify-settings-for-the-publisher-and-publisher-groups"></a><span data-ttu-id="0fe0a-151">Para modificar as configurações para o Publicador e o Grupo do publicador</span><span class="sxs-lookup"><span data-stu-id="0fe0a-151">To modify settings for the Publisher and Publisher Groups</span></span>  
  
1.  <span data-ttu-id="0fe0a-152">Clique com o botão direito do mouse no Publicador do painel esquerdo, e, então, clique em **Configurações do Publicador**.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-152">Right-click a Publisher in the left pane, and then click **Publisher Settings**.</span></span>  
  
2.  <span data-ttu-id="0fe0a-153">Faça todas as alterações na caixa de diálogo **Configurações do Publicador** :</span><span class="sxs-lookup"><span data-stu-id="0fe0a-153">Make any changes in the **Publisher Settings** dialog box:</span></span>  
  
    -   <span data-ttu-id="0fe0a-154">Para alterar as credenciais que o Replication Monitor usa para conectar ao servidor, clique em **Conexão do Publicador** ou **Conexão do Distribuidor**e, então, digite as credenciais na caixa de diálogo **Conectar ao Servidor** .</span><span class="sxs-lookup"><span data-stu-id="0fe0a-154">To change the credentials that Replication Monitor uses to connect to a server, click **Publisher Connection** or **Distributor Connection**, and then enter credentials in the **Connect to Server** dialog box.</span></span>  
  
    -   <span data-ttu-id="0fe0a-155">Para mover um Publicador de um grupo para o outro, selecione o Publicador na grade **Iniciar a monitoração nos seguintes Publicadores** e selecione o novo grupo na lista **Mostrar esses Publicadores no seguinte grupo** .</span><span class="sxs-lookup"><span data-stu-id="0fe0a-155">To move a Publisher from one group to another, select the Publisher in the **Start monitoring the following Publisher(s)** grid, and then select the new group in the **Show this Publisher(s) in the following group** list.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-remove-a-publisher-from-replication-monitor"></a><span data-ttu-id="0fe0a-156">Para remover o Publicador do Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="0fe0a-156">To remove a Publisher from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="0fe0a-157">Clique com o botão direito do mouse em um Publicador no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-157">Right-click a Publisher in the left pane.</span></span>  
  
2.  <span data-ttu-id="0fe0a-158">Clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-158">Click **Remove**.</span></span>  
  
### <a name="to-add-a-publisher-group-to-replication-monitor"></a><span data-ttu-id="0fe0a-159">Para adicionar um Grupo do publicador ao Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="0fe0a-159">To add a Publisher group to Replication Monitor</span></span>  
  
1.  <span data-ttu-id="0fe0a-160">Só podem ser criados Grupos do publicador ao adicionar um Publicador ou modificar as configurações de um Publicador.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-160">Publisher groups can be created only when adding a Publisher or modifying settings for a Publisher.</span></span> <span data-ttu-id="0fe0a-161">Para obter mais informações, consulte os procedimentos sobre como adicionar um Publicador.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-161">See the how to procedures on adding a Publisher for more information.</span></span>  
  
### <a name="to-remove-a-publisher-group-from-replication-monitor"></a><span data-ttu-id="0fe0a-162">Para remover um grupo do Publicador do Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="0fe0a-162">To remove a Publisher group from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="0fe0a-163">Mova todos os Publicadores para um grupo diferente ou remova-os do Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-163">Move all Publishers to a different group or remove them from Replication Monitor.</span></span> <span data-ttu-id="0fe0a-164">Para obter mais informações, consulte os procedimentos anteriores neste tópico.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-164">For more information, see previous procedures in this topic.</span></span>  
  
2.  <span data-ttu-id="0fe0a-165">Clique com o botão direito do mouse no grupo do Publicador e, então, clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="0fe0a-165">Right-click the Publisher group, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fe0a-166">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0fe0a-166">See Also</span></span>  
 <span data-ttu-id="0fe0a-167">[Configurar Distribuição](../configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="0fe0a-167">[Configure Distribution](../configure-distribution.md) </span></span>  
 [<span data-ttu-id="0fe0a-168">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="0fe0a-168">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  