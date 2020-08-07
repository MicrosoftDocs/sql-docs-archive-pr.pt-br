---
title: Gerenciador de Configurações do Reporting Services (modo nativo) | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Configuration tool
- configuration options [Reporting Services]
- report servers [Reporting Services], configuring
- components [Reporting Services], Reporting Services Configuration tool
ms.assetid: 379eab68-7f13-4997-8d64-38810240756e
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 656d4fad8034afedde642e0badab820146453e0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583973"
---
# <a name="reporting-services-configuration-manager-native-mode"></a><span data-ttu-id="99377-102">Gerenciador de Configurações do Reporting Services (Modo Nativo).</span><span class="sxs-lookup"><span data-stu-id="99377-102">Reporting Services Configuration Manager (Native Mode)</span></span>
  <span data-ttu-id="99377-103">Use o Gerenciador de Configurações do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para configurar uma instalação do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] no Modo Nativo.</span><span class="sxs-lookup"><span data-stu-id="99377-103">Use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager to configure a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native Mode installation.</span></span> <span data-ttu-id="99377-104">Se você instalou um servidor de relatório usando a opção de instalação somente arquivos, deverá usar o Gerenciador de Configuração para configurar o servidor antes de poder usá-lo.</span><span class="sxs-lookup"><span data-stu-id="99377-104">If you installed a report server by using the files-only installation option, you must use the Configuration Manager to configure the server before you can use it.</span></span> <span data-ttu-id="99377-105">Se você instalou um servidor de relatório usando a opção de instalação de configuração padrão, poderá usar o Gerenciador de Configurações para verificar ou modificar as configurações que foram especificadas durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="99377-105">If you installed a report server by using the default configuration installation option, you can use the Configuration Manager to verify or modify the settings that were specified during setup.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="99377-106">pode ser usado para configurar uma instância local ou remota do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="99377-106">Configuration Manager can be used to configure a local or remote report server instance.</span></span>  
  
 [!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="99377-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo nativo.</span><span class="sxs-lookup"><span data-stu-id="99377-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="99377-108">A partir da versão [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , o Gerenciador de Configurações do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] não foi desenvolvido para gerenciar servidores de relatório no modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="99377-108">Starting with the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] release, the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager is not designed to manage SharePoint mode report servers.</span></span> <span data-ttu-id="99377-109">O modo do SharePoint é gerenciado e configurado por meio de scripts da Administração Central do SharePoint e do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99377-109">SharePoint mode is managed and configured by using SharePoint Central Administration and PowerShell scripts.</span></span> <span data-ttu-id="99377-110">Para obter informações, consulte [Reporting Services instalação do modo sharepoint &#40;sharepoint 2010 e sharepoint 2013&#41;](../../reporting-services/install-windows/install-reporting-services-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="99377-110">For information, see [Reporting Services SharePoint Mode Installation &#40;SharePoint 2010 and SharePoint 2013&#41;](../../reporting-services/install-windows/install-reporting-services-sharepoint-mode.md).</span></span>  
  
 <span data-ttu-id="99377-111">**Nesta seção:**</span><span class="sxs-lookup"><span data-stu-id="99377-111">**In this section:**</span></span>  
  
 [<span data-ttu-id="99377-112">Configurar a conta de serviço do servidor de relatório &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="99377-112">Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../../reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="99377-113">Fornece recomendações e etapas sobre como modificar a conta do serviço e a senha.</span><span class="sxs-lookup"><span data-stu-id="99377-113">Provides recommendations and steps on how to modify the service account and password.</span></span>  
  
 [<span data-ttu-id="99377-114">Configurar as URLs do servidor de relatório &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="99377-114">Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;</span></span>](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
 <span data-ttu-id="99377-115">Descreve como configurar as URLs usadas para acessar o serviço Web Servidor de Relatórios e o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="99377-115">Describes how to configure URLs used to access the Report Server Web service and Report Manager.</span></span>  
  
 [<span data-ttu-id="99377-116">Criar um banco de dados do servidor de relatório &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="99377-116">Create a Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../../../2014/sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md)  
 <span data-ttu-id="99377-117">Descreve como criar um banco de dados de servidor de relatório, exigido por armazenar metadados e objetos de servidor.</span><span class="sxs-lookup"><span data-stu-id="99377-117">Describes how to create a report server database, required for storing server metadata and objects.</span></span>  
  
 [<span data-ttu-id="99377-118">Configurar uma conexão de banco de dados do servidor de relatório &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="99377-118">Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;</span></span>](../../../2014/sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md)  
 <span data-ttu-id="99377-119">Descreve como modificar a cadeia de conexão usada pelo servidor de relatório para conexão com o banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="99377-119">Describes how to modify the connection string used by the report server to connect to the report server database.</span></span>  
  
 [<span data-ttu-id="99377-120">Configurar a conta de execução autônoma &#40;Gerenciador de configurações do SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="99377-120">Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;</span></span>](../../reporting-services/install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="99377-121">Descreve como configurar uma conta do usuário para processar relatórios no modo autônomo.</span><span class="sxs-lookup"><span data-stu-id="99377-121">Describes how to configure a user account to process reports in unattended mode.</span></span>  
  
 [<span data-ttu-id="99377-122">Configurar um servidor de relatório para entrega de email &#40;Configuration Manager SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="99377-122">Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;</span></span>](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)  
 <span data-ttu-id="99377-123">Descreve como configurar um servidor de relatório para dar suporte à distribuição de relatório por email.</span><span class="sxs-lookup"><span data-stu-id="99377-123">Describes how to configure a report server to support e-mail report distribution.</span></span>  
  
 [<span data-ttu-id="99377-124">Configurar uma implantação de expansão do servidor de relatório no modo nativo &#40;Gerenciador de configurações do SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="99377-124">Configure a Native Mode Report Server Scale-Out Deployment &#40;SSRS Configuration Manager&#41;</span></span>](../../reporting-services/install-windows/configure-a-native-mode-report-server-scale-out-deployment.md)  
 <span data-ttu-id="99377-125">Fornece informações sobre como configurar várias instâncias do servidor de relatório para usar um banco de dados de servidor de relatório compartilhado.</span><span class="sxs-lookup"><span data-stu-id="99377-125">Provides information about configuring multiple report server instances to use a shared report server database.</span></span>  
  
 [<span data-ttu-id="99377-126">Configurar e gerenciar chaves de criptografia &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="99377-126">Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;</span></span>](../../reporting-services/install-windows/ssrs-encryption-keys-manage-encryption-keys.md)  
 <span data-ttu-id="99377-127">Explica como usar e gerenciar as chaves de criptografia utilizadas ao armazenar dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="99377-127">Explains how to use and manage encryption keys that are used when storing sensitive data.</span></span>  
  
 [<span data-ttu-id="99377-128">Gerenciar um servidor de relatórios de Modo Nativo do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="99377-128">Manage a Reporting Services Native Mode Report Server</span></span>](../../reporting-services/report-server/manage-a-reporting-services-native-mode-report-server.md)  
 <span data-ttu-id="99377-129">Fornece instruções passo a passo para tarefas comuns.</span><span class="sxs-lookup"><span data-stu-id="99377-129">Provides step-by-step instruction for common tasks.</span></span>  
  
 [<span data-ttu-id="99377-130">Gerenciador de Configurações do Reporting Services F1 tópicos de ajuda &#40;modo nativo do SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="99377-130">Reporting Services Configuration Manager F1 Help Topics &#40;SSRS Native Mode&#41;</span></span>](../../../2014/sql-server/install/reporting-services-configuration-manager-f1-help-topics-ssrs-native-mode.md)  
 <span data-ttu-id="99377-131">Fornece tópicos de ajuda para as páginas da ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99377-131">Provides help topics for the pages in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span>  
  
 <span data-ttu-id="99377-132">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="99377-132">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="99377-133">Cenários a serem usados Gerenciador de Configurações do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="99377-133">Scenarios to use Reporting Services Configuration Manager</span></span>](#bkmk_scenarios)  
  
-   [<span data-ttu-id="99377-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99377-134">Requirements</span></span>](#bkmk_requirements)  
  
-   [<span data-ttu-id="99377-135">Para iniciar o Gerenciador de Configuração do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="99377-135">To Start the Reporting Services Configuration Manager</span></span>](#bkmk_start_configuration_manager)  
  
##  <a name="scenarios-to-use-reporting-services-configuration-manager"></a><a name="bkmk_scenarios"></a> <span data-ttu-id="99377-136">Cenários para usar o Gerenciador de Configuração do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="99377-136">Scenarios to use Reporting Services Configuration Manager</span></span>  
 <span data-ttu-id="99377-137">Você pode usar a ferramenta Gerenciador de Configurações do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="99377-137">You can use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="99377-138">Configurar a conta de serviço do Servidor de Relatório.</span><span class="sxs-lookup"><span data-stu-id="99377-138">Configure the Report Server service account.</span></span> <span data-ttu-id="99377-139">A conta é configurada inicialmente durante a instalação, mas pode ser modificada usando a ferramenta Gerenciador de Configurações do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] se você atualizar a senha ou quiser usar uma conta diferente.</span><span class="sxs-lookup"><span data-stu-id="99377-139">The account is initially configured during setup, but can be modified by using the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager if you update the password or want to use a different account.</span></span>  
  
-   <span data-ttu-id="99377-140">Crie e configure os URLs.</span><span class="sxs-lookup"><span data-stu-id="99377-140">Create and configure URLs.</span></span> <span data-ttu-id="99377-141">O servidor de relatório e o Gerenciador de Relatórios são aplicativos [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] acessados através de URLs.</span><span class="sxs-lookup"><span data-stu-id="99377-141">The report server and Report Manager are [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications accessed through URLs.</span></span> <span data-ttu-id="99377-142">O URL do servidor de relatório fornece acesso aos pontos de extremidade SOAP do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="99377-142">The report server URL provides access to the SOAP endpoints of the report server.</span></span> <span data-ttu-id="99377-143">O URL do Gerenciador de Relatórios é usado para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="99377-143">The Report Manager URL is used to open Report Manager.</span></span> <span data-ttu-id="99377-144">Você pode configurar um único URL ou vários URLs para cada aplicativo.</span><span class="sxs-lookup"><span data-stu-id="99377-144">You can configure a single URL or multiple URLs for each application.</span></span>  
  
-   <span data-ttu-id="99377-145">Crie e configure o banco de dados de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="99377-145">Create and configure the report server database.</span></span> <span data-ttu-id="99377-146">O servidor de relatório é um servidor sem monitoração de estado que requer um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para armazenamento interno.</span><span class="sxs-lookup"><span data-stu-id="99377-146">The report server is a stateless server that requires a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for internal storage.</span></span> <span data-ttu-id="99377-147">Você pode usar a ferramenta Gerenciador de Configurações do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para criar e configurar uma conexão ao banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="99377-147">You can use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager to create and configure a connection to the report server database.</span></span> <span data-ttu-id="99377-148">Você também pode selecionar um banco de dados de servidor de relatório existente que já tenha o conteúdo você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="99377-148">You can also select an existing report server database that already contains the content you want to use.</span></span>  
  
-   <span data-ttu-id="99377-149">Configure uma implantação de expansão no modo Nativo.</span><span class="sxs-lookup"><span data-stu-id="99377-149">Configure a Native mode scale-out deployment.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="99377-150">oferece suporte a uma topologia de implantação que permite que várias instâncias do servidor de relatório usem um único banco de dados de servidor de relatório compartilhado.</span><span class="sxs-lookup"><span data-stu-id="99377-150">supports a deployment topology that allows multiple report server instances use a single, shared report server database.</span></span> <span data-ttu-id="99377-151">Para fazer uma implantação de expansão de servidor de relatório, use a ferramenta Gerenciador de Configurações do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para conectar cada servidor de relatório ao banco de dados de servidor de relatório compartilhado.</span><span class="sxs-lookup"><span data-stu-id="99377-151">To deploy a report server scale-out deployment, you use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager to connect each report server to the shared report server database.</span></span>  
  
-   <span data-ttu-id="99377-152">Faça backup, restaure ou substitua a chave simétrica que é usada para criptografar cadeias de caracteres e credenciais de conexões armazenadas.</span><span class="sxs-lookup"><span data-stu-id="99377-152">Backup, restore, or replace the symmetric key that is used to encrypt stored connection strings and credentials.</span></span> <span data-ttu-id="99377-153">Você deve ter uma cópia de backup da chave simétrica caso altere a conta de serviço ou mova um banco de dados do servidor de relatório para outro computador.</span><span class="sxs-lookup"><span data-stu-id="99377-153">You must have a backup of the symmetric key if you change the service account, or move a report server database to another computer.</span></span>  
  
-   <span data-ttu-id="99377-154">Configure a conta de execução autônoma.</span><span class="sxs-lookup"><span data-stu-id="99377-154">Configure the unattended execution account.</span></span> <span data-ttu-id="99377-155">Essa conta é usada para conexões remotas durante operações agendadas ou quando as credenciais de usuário não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="99377-155">This account is used for remote connections during scheduled operations or when user credentials are not available.</span></span>  
  
-   <span data-ttu-id="99377-156">Configure o email do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="99377-156">Configure report server e-mail.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="99377-157">inclui uma extensão de entrega de email do servidor de relatório que usa o protocolo SMTP para entregar relatórios ou notificação de processamento de relatórios a uma caixa de correio eletrônica.</span><span class="sxs-lookup"><span data-stu-id="99377-157">includes a report server e-mail delivery extension that uses a Simple Mail Transfer Protocol (SMTP) to deliver reports or report processing notification to an electronic mailbox.</span></span> <span data-ttu-id="99377-158">Você pode usar o Gerenciador de Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para especificar qual servidor ou gateway SMTP na sua rede será usado para entrega de e-mail.</span><span class="sxs-lookup"><span data-stu-id="99377-158">You can use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager to specify which SMTP server or gateway on your network to use for e-mail delivery.</span></span>  
  
 <span data-ttu-id="99377-159">A ferramenta Gerenciador de Configurações do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] não o ajuda a gerenciar o conteúdo do servidor de relatório, habilitar recursos adicionais ou conceder acesso ao servidor.</span><span class="sxs-lookup"><span data-stu-id="99377-159">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager does not help you manage report server content, enable additional features, or grant access to the server.</span></span> <span data-ttu-id="99377-160">A implantação completa requer que você também use o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para habilitar recursos adicionais ou modificar valores padrão e Report Manager para conceder acesso de usuário ao servidor.</span><span class="sxs-lookup"><span data-stu-id="99377-160">Full deployment requires that you also use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to enable additional features or modify default values, and Report Manager to grant user access to the server.</span></span>  
  
##  <a name="requirements"></a><a name="bkmk_requirements"></a> <span data-ttu-id="99377-161">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99377-161">Requirements</span></span>  
 <span data-ttu-id="99377-162">O Gerenciador de Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] é específico da versão.</span><span class="sxs-lookup"><span data-stu-id="99377-162">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration manager is version-specific.</span></span> <span data-ttu-id="99377-163">O Gerenciador de Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instalada com esta versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pode ser usado para configurar uma versão anterior do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99377-163">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager that installs with this version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be used to configure an earlier version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="99377-164">Se você estiver executando versões mais antigas e mais novas do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] lado a lado no mesmo computador, deverá usar o Gerenciador de Configurações do Reporting Services fornecido com cada versão para configurar cada instância.</span><span class="sxs-lookup"><span data-stu-id="99377-164">If you are running older and newer versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] side-by-side on the same computer, you must use the Reporting Service Configuration manager that comes with each version to configure each instance.</span></span>  
  
 <span data-ttu-id="99377-165">Para usar o Gerenciador de Configurações do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , você deve ter o seguinte:</span><span class="sxs-lookup"><span data-stu-id="99377-165">To use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration manager, you must have the following:</span></span>  
  
-   <span data-ttu-id="99377-166">Permissões de administrador de sistema local no computador que hospeda o servidor de relatório que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="99377-166">Local system administrator permissions on the computer that hosts the report server you want to configure.</span></span> <span data-ttu-id="99377-167">Se você estiver configurando um computador remoto, deverá ter permissões de administrador de sistema locais nesse computador também.</span><span class="sxs-lookup"><span data-stu-id="99377-167">If you are configuring a remote computer, you must have local system administrator permissions on that computer as well.</span></span>  
  
-   <span data-ttu-id="99377-168">É necessário ter permissão para criar bancos de dados no [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] usado para hospedar o banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="99377-168">You must have permission to create databases on the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] used to host the report server database.</span></span>  
  
-   <span data-ttu-id="99377-169">O serviço WMI (Instrumentação de Gerenciamento do Windows) deve ser ativado e executado em qualquer servidor de relatório que você estiver configurando.</span><span class="sxs-lookup"><span data-stu-id="99377-169">Windows Management Instrumentation (WMI) service must be enabled and running on any report server you are configuring.</span></span> <span data-ttu-id="99377-170">O Gerenciador de Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] usa o provedor WMI do servidor de relatório para se conectar a servidores de relatório locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="99377-170">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager uses the report server WMI provider to connect to local and remote report servers.</span></span> <span data-ttu-id="99377-171">Se você estiver configurando um servidor de relatório remoto, o computador deverá conceder acesso WMI remoto.</span><span class="sxs-lookup"><span data-stu-id="99377-171">If you are configuring a remote report server, the computer must allow remote WMI access.</span></span> <span data-ttu-id="99377-172">Para obter mais informações, consulte [Configurar um Servidor de Relatório para Administração Remota](../../reporting-services/report-server/configure-a-report-server-for-remote-administration.md).</span><span class="sxs-lookup"><span data-stu-id="99377-172">For more information, see [Configure a Report Server for Remote Administration](../../reporting-services/report-server/configure-a-report-server-for-remote-administration.md).</span></span>  
  
-   <span data-ttu-id="99377-173">Antes de conectar-se a e configurar uma instância remota do servidor de relatório, você deve habilitar as chamadas remotas à WMI (Instrumentação de Gerenciamento do Windows) para passar pelo o Firewall do Windows.</span><span class="sxs-lookup"><span data-stu-id="99377-173">Before you can connect to and configure a remote report server instance, you must enable remote Windows Management Instrumentation (WMI) calls to pass through Windows Firewall.</span></span> <span data-ttu-id="99377-174">Para obter mais informações, consulte [Configurar um Servidor de Relatório para Administração Remota](../../reporting-services/report-server/configure-a-report-server-for-remote-administration.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99377-174">For more information, see [Configure a Report Server for Remote Administration](../../reporting-services/report-server/configure-a-report-server-for-remote-administration.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="99377-175">A ferramenta Gerenciador de Configurações do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] é instalado automaticamente quando o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99377-175">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager is installed automatically when you install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]</span></span>  
  
##  <a name="to-start-the-reporting-services-configuration-manager"></a><a name="bkmk_start_configuration_manager"></a><span data-ttu-id="99377-176">Para iniciar o Gerenciador de Configurações do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="99377-176">To Start the Reporting Services Configuration Manager</span></span>  
  
#### <a name="to-start-reporting-services-configuration"></a><span data-ttu-id="99377-177">Para iniciar a Configuração do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="99377-177">To start Reporting Services Configuration</span></span>  
  
1.  <span data-ttu-id="99377-178">Use a seguinte etapa que for apropriada para sua versão do Microsoft Windows:</span><span class="sxs-lookup"><span data-stu-id="99377-178">Use the following step that is appropriate for your version of Microsoft Windows:</span></span>  
  
    -   <span data-ttu-id="99377-179">Na tela inicial do Windows, digite **Relatórios** e selecione **Gerenciador de Configurações do Reporting Services** nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="99377-179">From the Windows start screen, type **Reporting** and select **Reporting Services Configuration Manager** from the search results.</span></span>  
  
    -   <span data-ttu-id="99377-180">Clique em **Iniciar**, aponte para **Todos os Programas**, aponte para [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)]e aponte para **Ferramentas de Configuração**.</span><span class="sxs-lookup"><span data-stu-id="99377-180">Click **Start**, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], and then point to **Configuration Tools**.</span></span>  
  
         <span data-ttu-id="99377-181">Para configurar uma instância do servidor de relatório de uma versão anterior do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], abra a pasta do programa dessa versão.</span><span class="sxs-lookup"><span data-stu-id="99377-181">If you want to configure a report server instance from a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], open the program folder for that version.</span></span> <span data-ttu-id="99377-182">Por exemplo, aponte para [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] , em vez de [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)] para abrir as ferramentas de configuração para os componentes de servidor do [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99377-182">For example, point to [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] instead of [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)] to open the configuration tools for [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] server components.</span></span>  
  
         <span data-ttu-id="99377-183">Clique em **Gerenciador de Configuração do Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="99377-183">Click **Reporting Services Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="99377-184">A caixa de diálogo **Conexão de Configuração do Reporting Services** será exibida, para que você possa selecionar a instância do servidor de relatório que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="99377-184">The **Reporting Services Configuration Connection** dialog box appears so that you can select the report server instance you want to configure.</span></span> <span data-ttu-id="99377-185">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="99377-185">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="99377-186">Em **Nome do Servidor**, especifique o nome do computador no qual a instância do servidor de relatório está instalada.</span><span class="sxs-lookup"><span data-stu-id="99377-186">In **Server Name**, specify the name of the computer on which the report server instance is installed.</span></span> <span data-ttu-id="99377-187">O nome do computador local aparece por padrão, mas você pode digitar o nome de uma instância remota do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para conectar-se a um servidor de relatório que esteja instalado em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="99377-187">The name of the local computer appears by default, but you can type the name of a remote [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance if you want to connect to a report server that is installed on a remote computer.</span></span>  
  
4.  <span data-ttu-id="99377-188">Se você especificar um computador remoto, clique em **Localizar** para estabelecer uma conexão.</span><span class="sxs-lookup"><span data-stu-id="99377-188">If you specify a remote computer, click **Find** to establish a connection.</span></span>  
  
5.  <span data-ttu-id="99377-189">Em **Instância do Servidor de Relatório**, selecione a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="99377-189">In **Report Server Instance**, select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span> <span data-ttu-id="99377-190">Somente instâncias de servidor de relatório para esta versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aparecem na lista.</span><span class="sxs-lookup"><span data-stu-id="99377-190">Only report server instances for this version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] appear in the list.</span></span> <span data-ttu-id="99377-191">Você não pode configurar versões anteriores do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99377-191">You cannot configure earlier versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
6.  <span data-ttu-id="99377-192">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="99377-192">Click **Connect**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99377-193">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="99377-193">See Also</span></span>  
 <span data-ttu-id="99377-194">[Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="99377-194">[Report Manager  &#40;SSRS Native Mode&#41;](../../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="99377-195">[Ferramentas de Reporting Services](../../reporting-services/tools/reporting-services-tools.md) </span><span class="sxs-lookup"><span data-stu-id="99377-195">[Reporting Services Tools](../../reporting-services/tools/reporting-services-tools.md) </span></span>  
 <span data-ttu-id="99377-196">[Configurar uma conexão de banco de dados do servidor de relatório &#40;Configuration Manager SSRS&#41;](../../../2014/sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="99377-196">[Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;](../../../2014/sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="99377-197">[SQL Server Configuration Manager](../../relational-databases/sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="99377-197">[SQL Server Configuration Manager](../../relational-databases/sql-server-configuration-manager.md) </span></span>  
 [<span data-ttu-id="99377-198">Configurar e administrar um servidor de relatório &#40;modo nativo do SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="99377-198">Configure and Administer a Report Server &#40;SSRS Native Mode&#41;</span></span>](../../reporting-services/report-server/configure-and-administer-a-report-server-ssrs-native-mode.md)  
  
  