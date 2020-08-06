---
title: Visão geral do Monitor de Espelhamento de Banco de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dbmmonitor.main.f1
helpviewer_keywords:
- Database Mirroring Monitor [SQL Server], interface
ms.assetid: 8ebbdcd6-565a-498f-b674-289c84b985eb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d19f9a2aa66aaee30bcf623e254d6f24aa690277
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681176"
---
# <a name="database-mirroring-monitor-overview"></a><span data-ttu-id="e7602-102">Visão geral do Monitor de Espelhamento de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="e7602-102">Database Mirroring Monitor Overview</span></span>
  <span data-ttu-id="e7602-103">Se tiver as permissões corretas, você pode usar o Monitor de Espelhamento de Banco de Dados para monitorar qualquer subconjunto de bancos de dados espelhado em uma instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="e7602-103">If you have the correct permissions, you can use Database Mirroring Monitor to monitor any subset of the mirrored databases on a server instance.</span></span> <span data-ttu-id="e7602-104">O monitoramento permite verificar como e se os dados estão fluindo satisfatoriamente na sessão de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e7602-104">Monitoring enables you to verify whether and how well data is flowing in the database mirroring session.</span></span> <span data-ttu-id="e7602-105">O Monitor de Espelhamento de Banco de Dados é também útil para solucionar problemas da causa da redução do fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="e7602-105">Database Mirroring Monitor is also useful for troubleshooting the cause of reduced data flow.</span></span>  
  
 <span data-ttu-id="e7602-106">Você pode registrar qualquer um dos bancos de dados espelhados para monitoramento em cada um dos parceiros de failover individualmente.</span><span class="sxs-lookup"><span data-stu-id="e7602-106">You can register any of your mirrored databases for monitoring on each of the failover partners individually.</span></span> <span data-ttu-id="e7602-107">Quando você registra um banco de dados, o Monitor de Espelhamento de Banco de Dados armazenará em cache as seguintes informações do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e7602-107">When you register a database, Database Mirroring Monitor caches the following information about the database:</span></span>  
  
-   <span data-ttu-id="e7602-108">Nome do banco de dados</span><span class="sxs-lookup"><span data-stu-id="e7602-108">Database name</span></span>  
  
-   <span data-ttu-id="e7602-109">Os nomes de ambas as instâncias do servidor parceiro.</span><span class="sxs-lookup"><span data-stu-id="e7602-109">The names of the two partner server instances</span></span>  
  
-   <span data-ttu-id="e7602-110">As últimas funções conhecidas de cada parceiro (principal ou espelho)</span><span class="sxs-lookup"><span data-stu-id="e7602-110">The last known roles of each partner (principal or mirror)</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="e7602-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="e7602-111">Permissions</span></span>  
 <span data-ttu-id="e7602-112">Para monitorar o espelhamento de banco de dados é necessário ser um membro da função de servidor fixa **sysadmin** ou da função de banco de dados fixa **dbm_monitor** no banco de dados **msdb** na instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="e7602-112">To monitor database mirroring, you must be a member of either the **sysadmin** fixed server role or the **dbm_monitor** fixed database role in the **msdb** database on the server instance.</span></span> <span data-ttu-id="e7602-113">Se você for um membro do **sysadmin** ou do **dbm_monitor** em apenas uma das instâncias do servidor parceiro, o monitor poderá se conectar apenas àquele parceiro e não poderá recuperar as informações do outro parceiro.</span><span class="sxs-lookup"><span data-stu-id="e7602-113">If you are a member of **sysadmin** or **dbm_monitor** on only one of the partner server instances, the monitor can connect only to that partner; the monitor cannot retrieve information from the other partner.</span></span>  
  
 <span data-ttu-id="e7602-114">Se você for um membro de **dbm_monitor** em apenas uma instância de servidor, terá permissões limitadas naquela instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="e7602-114">If you are a member of just **dbm_monitor** on a server instance, you will have limited permissions on that server instance.</span></span> <span data-ttu-id="e7602-115">Você só poderá visualizar a linha de status mais recente.</span><span class="sxs-lookup"><span data-stu-id="e7602-115">You will only be able to view the most recent status row.</span></span> <span data-ttu-id="e7602-116">Se você se conectar a uma instância de servidor usando as permissões do **dbm_monitor** em uma instância de servidor, o Monitor de Espelhamento de Banco de Dados vai informá-lo de que suas permissões são limitadas.</span><span class="sxs-lookup"><span data-stu-id="e7602-116">If you connect to a server instance using **dbm_monitor** permissions, Database Mirroring Monitor informs you that you have limited permissions.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e7602-117">A função fixa **dbm_monitor** do banco de dados é criada no banco de dados **msdb** quando o primeiro banco de dados for registrado no Monitor de Espelhamento de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="e7602-117">The **dbm_monitor** fixed database role is created in the **msdb** database when the first database is registered in Database Mirroring Monitor.</span></span> <span data-ttu-id="e7602-118">A nova função **dbm_monitor** não tem nenhum membro até que um administrador de sistemas atribua usuários à função.</span><span class="sxs-lookup"><span data-stu-id="e7602-118">The new **dbm_monitor** role has no members until a system administrator assigns users to the role.</span></span>  
  
## <a name="navigation-tree"></a><span data-ttu-id="e7602-119">Árvore de navegação</span><span class="sxs-lookup"><span data-stu-id="e7602-119">Navigation Tree</span></span>  
 <span data-ttu-id="e7602-120">Se algum banco de dados for registrado para monitoramento pelo Monitor de Espalhamento de Banco de Dados, uma lista dos bancos de dados registrados será exibida na árvore de navegação.</span><span class="sxs-lookup"><span data-stu-id="e7602-120">If any databases have been registered for monitoring by the Database Mirroring Monitor, a list of registered databases is displayed in the navigation tree.</span></span> <span data-ttu-id="e7602-121">A árvore é atualizada automaticamente a cada 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="e7602-121">The tree automatically refreshes every 30 seconds.</span></span> <span data-ttu-id="e7602-122">Para ver o status de um banco de dados registrado, selecione-o.</span><span class="sxs-lookup"><span data-stu-id="e7602-122">To see the status of a registered database, select it.</span></span> <span data-ttu-id="e7602-123">Para obter mais informações, consulte "Painel de Detalhes” mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="e7602-123">For more information, see "Detail Pane," later in this topic.</span></span>  
  
 <span data-ttu-id="e7602-124">Para cada banco de dados registrado, as seguintes informações serão exibidas:</span><span class="sxs-lookup"><span data-stu-id="e7602-124">For each registered database, the following information is displayed:</span></span>  
  
 <span data-ttu-id="e7602-125">_<Database_name>_ **(** _\<Status>_ **,** _<PRINCIPAL_SERVER>_ **->** _<MIRROR_SERVER>_ **)**</span><span class="sxs-lookup"><span data-stu-id="e7602-125">_<Database_name>_ **(** _\<Status>_ **,** _<PRINCIPAL_SERVER>_ **->** _<MIRROR_SERVER>_ **)**</span></span>  
  
 <span data-ttu-id="e7602-126">*<nome_do_banco_de_dados>*</span><span class="sxs-lookup"><span data-stu-id="e7602-126">*<Database_name>*</span></span>  
 <span data-ttu-id="e7602-127">O nome de um banco de dados espelho registrado no Monitor de Espelhamento de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="e7602-127">The name of a mirrored database that is registered with the Database Mirroring Monitor.</span></span>  
  
 *\<Status>*  
 <span data-ttu-id="e7602-128">Os possíveis status e seus ícones associados são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="e7602-128">The possible statuses and their associated icons are as follows:</span></span>  
  
|<span data-ttu-id="e7602-129">ícone</span><span class="sxs-lookup"><span data-stu-id="e7602-129">Icon</span></span>|<span data-ttu-id="e7602-130">Status</span><span class="sxs-lookup"><span data-stu-id="e7602-130">Status</span></span>|<span data-ttu-id="e7602-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="e7602-131">Description</span></span>|  
|----------|------------|-----------------|  
|<span data-ttu-id="e7602-132">Ícone de aviso:</span><span class="sxs-lookup"><span data-stu-id="e7602-132">Warning icon</span></span>|<span data-ttu-id="e7602-133">**Desconhecido**</span><span class="sxs-lookup"><span data-stu-id="e7602-133">**Unknown**</span></span>|<span data-ttu-id="e7602-134">O monitor não está conectado a nenhum parceiro.</span><span class="sxs-lookup"><span data-stu-id="e7602-134">The monitor is not connected to either partner.</span></span> <span data-ttu-id="e7602-135">As únicas informações disponíveis são aquelas armazenadas em cache pelo monitor.</span><span class="sxs-lookup"><span data-stu-id="e7602-135">The only available information is what has been cached by the monitor.</span></span>|  
|<span data-ttu-id="e7602-136">Ícone de aviso:</span><span class="sxs-lookup"><span data-stu-id="e7602-136">Warning icon</span></span>|<span data-ttu-id="e7602-137">**Sincronizando**</span><span class="sxs-lookup"><span data-stu-id="e7602-137">**Synchronizing**</span></span>|<span data-ttu-id="e7602-138">O conteúdo do banco de dados espelho está ficando atrás do conteúdo do banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="e7602-138">The contents of the mirror database are lagging behind the contents of the principal database.</span></span> <span data-ttu-id="e7602-139">A instância do servidor principal está enviando registros de log para a instância do servidor espelho, a qual está aplicando as alterações ao banco de dados espelho para rolagem para frente.</span><span class="sxs-lookup"><span data-stu-id="e7602-139">The principal server instance is sending log records to the mirror server instance, which is applying the changes to the mirror database to roll it forward.</span></span><br /><br /> <span data-ttu-id="e7602-140">No início de uma sessão de espelhamento de banco de dados, o banco de dados espelho e principal estão nesse estado.</span><span class="sxs-lookup"><span data-stu-id="e7602-140">At the start of a database mirroring session, the mirror and principal databases are in this state.</span></span>|  
|<span data-ttu-id="e7602-141">Cilindro padrão do banco de dados</span><span class="sxs-lookup"><span data-stu-id="e7602-141">Standard database cylinder</span></span>|<span data-ttu-id="e7602-142">**Sincronizado**</span><span class="sxs-lookup"><span data-stu-id="e7602-142">**Synchronized**</span></span>|<span data-ttu-id="e7602-143">Quando o servidor espelho torna-se suficientemente atualizado em relação ao servidor principal, o estado do banco de dados é alterado para **Sincronizado**.</span><span class="sxs-lookup"><span data-stu-id="e7602-143">When the mirror server becomes sufficiently caught up to the principal server, the database state changes to **Synchronized**.</span></span> <span data-ttu-id="e7602-144">O banco de dados permanece nesse estado enquanto o servidor principal continua enviando alterações para o servidor espelho e o servidor espelho continua aplicando as alterações ao banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="e7602-144">The database remains in this state as long as the principal server continues to send changes to the mirror server and the mirror server continues to apply changes to the mirror database.</span></span><br /><br /> <span data-ttu-id="e7602-145">Para o modo de alta segurança, o failover automático e o failover manual são ambos possíveis, sem perda de dados.</span><span class="sxs-lookup"><span data-stu-id="e7602-145">For high-safety mode, automatic failover and manual failover are both possible, without any data loss.</span></span><br /><br /> <span data-ttu-id="e7602-146">No modo de alto desempenho, alguma perda de dados é sempre possível, mesmo no estado **Sincronizado** .</span><span class="sxs-lookup"><span data-stu-id="e7602-146">For high-performance mode, some data loss is always possible, even in the **Synchronized** state.</span></span>|  
|<span data-ttu-id="e7602-147">Ícone de aviso:</span><span class="sxs-lookup"><span data-stu-id="e7602-147">Warning icon</span></span>|<span data-ttu-id="e7602-148">**Suspenso**</span><span class="sxs-lookup"><span data-stu-id="e7602-148">**Suspended**</span></span>|<span data-ttu-id="e7602-149">O banco de dados principal está disponível, mas não está enviando logs para o servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="e7602-149">The principal database is available but is not sending any logs to the mirror server.</span></span>|  
|<span data-ttu-id="e7602-150">Ícone de erro</span><span class="sxs-lookup"><span data-stu-id="e7602-150">Error icon</span></span>|<span data-ttu-id="e7602-151">**Desconectado**</span><span class="sxs-lookup"><span data-stu-id="e7602-151">**Disconnected**</span></span>|<span data-ttu-id="e7602-152">A instância do servidor não pode se conectar ao seu parceiro.</span><span class="sxs-lookup"><span data-stu-id="e7602-152">The server instance cannot connect to its partner.</span></span>|  
  
 <span data-ttu-id="e7602-153">*<SERVIDOR_PRINCIPAL>*</span><span class="sxs-lookup"><span data-stu-id="e7602-153">*<PRINCIPAL_SERVER>*</span></span>  
 <span data-ttu-id="e7602-154">O nome do parceiro que atualmente é a principal instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="e7602-154">The name of the partner that is currently the principal server instance.</span></span> <span data-ttu-id="e7602-155">O nome está no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="e7602-155">The name is in the following format:</span></span>  
  
 <span data-ttu-id="e7602-156">*<SYSTEM_NAME>* [ **\\** _<instance_name>_ ]</span><span class="sxs-lookup"><span data-stu-id="e7602-156">*<SYSTEM_NAME>*[**\\**_<instance_name>_]</span></span>  
  
 <span data-ttu-id="e7602-157">em que *<SYSTEM_NAME>* é o nome do sistema no qual a instância do servidor reside.</span><span class="sxs-lookup"><span data-stu-id="e7602-157">where *<SYSTEM_NAME>* is the name of the system on which the server instance resides.</span></span> <span data-ttu-id="e7602-158">Para uma instância de servidor não padrão, o nome da instância também é exibido: _<SYSTEM_NAME>_ **\\** _<instance_name>_ .</span><span class="sxs-lookup"><span data-stu-id="e7602-158">For a non-default server instance, the instance name is also displayed: _<SYSTEM_NAME>_**\\**_<instance_name>_.</span></span>  
  
 <span data-ttu-id="e7602-159">*<SERVIDOR_ESPELHO>*</span><span class="sxs-lookup"><span data-stu-id="e7602-159">*<MIRROR_SERVER>*</span></span>  
 <span data-ttu-id="e7602-160">O nome do parceiro que é atualmente a instância do servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="e7602-160">The name of the partner that is currently the mirror server instance.</span></span> <span data-ttu-id="e7602-161">O formato é o mesmo do servidor principal.</span><span class="sxs-lookup"><span data-stu-id="e7602-161">The format is the same as for the principal server.</span></span>  
  
## <a name="detail-pane"></a><span data-ttu-id="e7602-162">Painel de detalhes</span><span class="sxs-lookup"><span data-stu-id="e7602-162">Detail Pane</span></span>  
 <span data-ttu-id="e7602-163">A aparência do monitor depende se um banco de dados foi selecionado ou não.</span><span class="sxs-lookup"><span data-stu-id="e7602-163">The appearance of the monitor depends on whether a database is selected.</span></span> <span data-ttu-id="e7602-164">Quando você abre o monitor, o painel de detalhes exibe um link **Registrar Banco de Dados Espelho** .</span><span class="sxs-lookup"><span data-stu-id="e7602-164">When you open the monitor, the detail pane displays a **Register mirrored database** link.</span></span> <span data-ttu-id="e7602-165">Clique nele para registrar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e7602-165">Click this to register a database.</span></span> <span data-ttu-id="e7602-166">Os bancos de dados registrados estão listados abaixo do nó **Monitor de Espelhamento de Banco de Dados** na árvore de navegação.</span><span class="sxs-lookup"><span data-stu-id="e7602-166">Registered databases are listed below the **Database Mirroring Monitor** node in the navigation tree.</span></span> <span data-ttu-id="e7602-167">O Monitor de Espelhamento de Banco de dados tenta sempre se conectar a cada instância do servidor para a qual ele tem credenciais armazenadas.</span><span class="sxs-lookup"><span data-stu-id="e7602-167">Database Mirroring Monitor always tries to connect to every server instance for which it has stored credentials.</span></span>  
  
 <span data-ttu-id="e7602-168">Quando você selecionar um banco de dados, seu status é exibido na página com guias **Status** no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="e7602-168">When you select a database, its status is displayed on the **Status** tabbed page in the detail pane.</span></span> <span data-ttu-id="e7602-169">O conteúdo desta página vem das duas instâncias de servidor principal e espelho.</span><span class="sxs-lookup"><span data-stu-id="e7602-169">The content of this page comes from both the principal and mirror server instances.</span></span> <span data-ttu-id="e7602-170">A página é preenchida de forma assíncrona conforme o status é coletado através de conexões separadas às instâncias de servidor principal e espelho.</span><span class="sxs-lookup"><span data-stu-id="e7602-170">The page is filled asynchronously as status is gathered through separate connections to the principal and mirror server instances.</span></span> <span data-ttu-id="e7602-171">O status é atualizado automaticamente em intervalos de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="e7602-171">The status automatically refreshes at 30-second intervals.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7602-172">Não é possível alterar a taxa de atualização do monitor, mas pode atualizar a tabela de status por meio da caixa de diálogo **Histórico do Espelhamento de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="e7602-172">You cannot change the monitor's refresh rate, but you can refresh the status table from the **Database Mirroring History** dialog box.</span></span>  
  
 <span data-ttu-id="e7602-173">O administrador de sistemas pode visualizar a configuração de avisos atual do banco de dados, selecionando a página com guias **Avisos** .</span><span class="sxs-lookup"><span data-stu-id="e7602-173">A system administrator can view the current configuration of warnings for the database by selecting the **Warnings** tabbed page.</span></span> <span data-ttu-id="e7602-174">A partir deste ponto, o administrador pode iniciar a caixa de diálogo **Definir Limites de Aviso** para habilitar e configurar um ou mais limites de aviso.</span><span class="sxs-lookup"><span data-stu-id="e7602-174">From there, the administrator can launch the **Set Warning Thresholds** dialog box to enable and configure one or more warning thresholds.</span></span>  
  
 <span data-ttu-id="e7602-175">Na faixa acima das guias, o painel de detalhes exibe a última vez em que o monitor atualizou as informações de status como, **última atualização:** _\<date>_ *\<time>* .</span><span class="sxs-lookup"><span data-stu-id="e7602-175">In the banner above the tabs, the detail pane displays the last time the monitor refreshed the status information as, **Last refresh:**_\<date>_*\<time>*.</span></span> <span data-ttu-id="e7602-176">Geralmente, o Monitor de Espelhamento de Banco de Dados recupera as informações de status a partir das instâncias de servidor principal e espelho em horários diferentes.</span><span class="sxs-lookup"><span data-stu-id="e7602-176">Usually, the Database Mirroring Monitor retrieves status information from the principal and mirror server instances at different times.</span></span> <span data-ttu-id="e7602-177">O horário mais antigo dessas duas atualizações é exibido.</span><span class="sxs-lookup"><span data-stu-id="e7602-177">The older of these two refresh times is displayed.</span></span>  
  
## <a name="action-menu"></a><span data-ttu-id="e7602-178">Menu Ação</span><span class="sxs-lookup"><span data-stu-id="e7602-178">Action Menu</span></span>  
 <span data-ttu-id="e7602-179">O menu **Ação** contém sempre os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="e7602-179">The **Action** menu always contains the following commands:</span></span>  
  
|<span data-ttu-id="e7602-180">Comando</span><span class="sxs-lookup"><span data-stu-id="e7602-180">Command</span></span>|<span data-ttu-id="e7602-181">Descrição</span><span class="sxs-lookup"><span data-stu-id="e7602-181">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7602-182">**Registrar um Banco de Dados Espelho**</span><span class="sxs-lookup"><span data-stu-id="e7602-182">**Register Mirrored Database...**</span></span>|<span data-ttu-id="e7602-183">Abre a caixa de diálogo **Registrar Banco de Dados Espelho** .</span><span class="sxs-lookup"><span data-stu-id="e7602-183">Opens the **Register Mirrored Database** dialog box.</span></span> <span data-ttu-id="e7602-184">Use esta caixa de diálogo para registrar um ou mais bancos de dado espelhados em uma determinada instância do servidor, adicionando o banco de dados, ou bancos de dados, ao Monitor de Espelhamento de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="e7602-184">Use this dialog box to register one or more mirrored databases on a given server instance by adding the database or databases to the Database Mirroring Monitor.</span></span> <span data-ttu-id="e7602-185">Quando um banco de dados é adicionado, o Monitor de Espelhamento de Banco de Dados armazena localmente em cache as informações do banco de dados, seus parceiros e como se conectar aos parceiros.</span><span class="sxs-lookup"><span data-stu-id="e7602-185">When a database is added, Database Mirroring Monitor locally caches information about the database, its partners, and how to connect to the partners.</span></span>|  
|<span data-ttu-id="e7602-186">**Gerenciar Conexões das Instâncias do Servidor...**</span><span class="sxs-lookup"><span data-stu-id="e7602-186">**Manage Server Instance Connections...**</span></span>|<span data-ttu-id="e7602-187">Quando você seleciona este comando, a caixa de diálogo **Gerenciar Conexões do Servidor** é exibida.</span><span class="sxs-lookup"><span data-stu-id="e7602-187">When you select this command, the **Manage Server Connections** dialog box opens.</span></span> <span data-ttu-id="e7602-188">Nela, você pode escolher uma instância de servidor para a qual deseja especificar as credencias a serem usadas pelo monitor quando se conectar a um determinado parceiro de failover.</span><span class="sxs-lookup"><span data-stu-id="e7602-188">There, you can choose a server instance for which you want to specify credentials for the monitor to use when connecting to a given partner.</span></span><br /><br /> <span data-ttu-id="e7602-189">Para editar as credenciais para o parceiro, localize sua entrada na grade **Instância de servidor** , e clique em **Editar** naquela linha.</span><span class="sxs-lookup"><span data-stu-id="e7602-189">To edit the credentials for a partner, locate its entry in the **Server instances** grid, and click **Edit** on that row.</span></span> <span data-ttu-id="e7602-190">Isto exibe a caixa de diálogo **Conectar ao Servidor** com o nome de instância de servidor e com os controles de credenciais inicializados com o valor atual em cache.</span><span class="sxs-lookup"><span data-stu-id="e7602-190">The **Connect to Server** dialog box appears with the server instance name fixed and the credential controls initialized to the current cached value.</span></span> <span data-ttu-id="e7602-191">Altere as informações de autenticação conforme necessário e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="e7602-191">Change the authentication information as necessary and click **Connect**.</span></span> <span data-ttu-id="e7602-192">Se as credenciais tiverem privilégios suficientes, a coluna **Conectar Usando** é atualizada com as novas credenciais.</span><span class="sxs-lookup"><span data-stu-id="e7602-192">If the credentials have sufficient privileges, the **Connect Using** column is updated with the new credentials.</span></span>|  
  
 <span data-ttu-id="e7602-193">Se você selecionar o banco de dados, o menu **Ação** também conterá os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="e7602-193">If you select a database, the **Action** menu also contains the following commands.</span></span>  
  
|<span data-ttu-id="e7602-194">Comando</span><span class="sxs-lookup"><span data-stu-id="e7602-194">Command</span></span>|<span data-ttu-id="e7602-195">Descrição</span><span class="sxs-lookup"><span data-stu-id="e7602-195">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7602-196">**Cancelar o Registro deste Banco de Dados.**</span><span class="sxs-lookup"><span data-stu-id="e7602-196">**Unregister This Database**</span></span>|<span data-ttu-id="e7602-197">Remove o banco de dados selecionado do Monitor de Espelhamento de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="e7602-197">Removes the selected database from Database Mirroring Monitor.</span></span>|  
|<span data-ttu-id="e7602-198">**Definir Limites de Aviso...**</span><span class="sxs-lookup"><span data-stu-id="e7602-198">**Set Warning Thresholds...**</span></span>|<span data-ttu-id="e7602-199">Abre a caixa de diálogo **Definir Limites de Aviso** .</span><span class="sxs-lookup"><span data-stu-id="e7602-199">Opens the **Set Warning Thresholds** dialog box.</span></span> <span data-ttu-id="e7602-200">A partir deste ponto, o administrador pode habilitar ou desabilitar os avisos para o banco de dados em cada um dos parceiros e alterar o limite de cada aviso.</span><span class="sxs-lookup"><span data-stu-id="e7602-200">There a system administrator can enable or disable warnings for the database on each of the partners and change the threshold of each warning.</span></span> <span data-ttu-id="e7602-201">Recomendamos definir o limite de um determinado aviso em ambos os parceiros a fim de garantir que o aviso continue se houver um failover no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e7602-201">We recommend setting a threshold for a given warning on both partners to ensure that the warning persists if the database fails over.</span></span> <span data-ttu-id="e7602-202">O limite adequado para cada parceiro depende das capacidades de desempenho o sistema daquele parceiro.</span><span class="sxs-lookup"><span data-stu-id="e7602-202">The appropriate threshold for each partner depends on the performance capabilities of that partner's system.</span></span><br /><br /> <span data-ttu-id="e7602-203">Um evento de desempenho é gravado no log de eventos somente se o seu valor estiver no seu limite ou acima dele quando a tabela de status for atualizada.</span><span class="sxs-lookup"><span data-stu-id="e7602-203">An event is written to the event log for a performance only if its value is at or above its threshold when the status table is being updated.</span></span> <span data-ttu-id="e7602-204">Se um valor máximo alcançar temporariamente o limite entre as atualizações de status, este valor máximo é ignorado</span><span class="sxs-lookup"><span data-stu-id="e7602-204">If a peak value reaches the threshold momentarily between status updates that peak is missed.</span></span>|  
  
 <span data-ttu-id="e7602-205">**Para monitorar o espelhamento de banco de dados usando o SQL Server Management Studio para**</span><span class="sxs-lookup"><span data-stu-id="e7602-205">**To monitor database mirroring by using SQL Server Management Studio to**</span></span>  
  
-   [<span data-ttu-id="e7602-206">Iniciar o Monitor de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e7602-206">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="e7602-207">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e7602-207">See Also</span></span>  
 <span data-ttu-id="e7602-208">[Monitorando o espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e7602-208">[Monitoring Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="e7602-209">Iniciar o Assistente para Configurar Segurança de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e7602-209">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
  