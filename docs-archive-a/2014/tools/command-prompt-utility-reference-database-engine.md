---
title: Referência do utilitário de prompt de comando (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- command prompt utilities [SQL Server]
- command prompt utilities [SQL Server], about command prompt utilities
- command prompt [SQL Server]
- utilities [SQL Server], command prompt
- command prompt [SQL Server], utilities
ms.assetid: 48364bd9-6ea7-45e9-a332-acf3d81bbfae
author: stevestein
ms.author: sstein
ms.openlocfilehash: ffb5f15bb37bd4e15dd93404be3df47ce359586b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679118"
---
# <a name="command-prompt-utility-reference-database-engine"></a><span data-ttu-id="2b323-102">Referência de utilitários de prompt de comando (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="2b323-102">Command Prompt Utility Reference (Database Engine)</span></span>
  <span data-ttu-id="2b323-103">Utilitários de prompt de comando permitem executar scripts de operações do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b323-103">Command prompt utilities enable you to script [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] operations.</span></span> <span data-ttu-id="2b323-104">A tabela a seguir contém uma lista de utilitários de prompt de comando que integram o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b323-104">The following table contains a list of command prompt utilities that ship with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="2b323-105">**Utilitário**</span><span class="sxs-lookup"><span data-stu-id="2b323-105">**Utility**</span></span>|<span data-ttu-id="2b323-106">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2b323-106">**Description**</span></span>|<span data-ttu-id="2b323-107">**Instalado no**</span><span class="sxs-lookup"><span data-stu-id="2b323-107">**Installed in**</span></span>|  
|-----------------|---------------------|----------------------|  
|[<span data-ttu-id="2b323-108">Utilitário bcp</span><span class="sxs-lookup"><span data-stu-id="2b323-108">bcp Utility</span></span>](bcp-utility.md)|<span data-ttu-id="2b323-109">Usado para copiar dados entre uma instância do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e um arquivo de dados em formato especificado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="2b323-109">Used to copy data between an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and a data file in a user-specified format.</span></span>|<span data-ttu-id="2b323-110">\<*drive*:>\Arquivos de Programas\\[!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]\Client SDK\ODBC\110\Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-110">\<*drive*:>\Program Files\\[!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]\Client SDK\ODBC\110\Tools\Binn</span></span>|  
|[<span data-ttu-id="2b323-111">Utilitário dta</span><span class="sxs-lookup"><span data-stu-id="2b323-111">dta Utility</span></span>](dta/dta-utility.md)|<span data-ttu-id="2b323-112">Usado para analisar uma carga de trabalho e recomendar estruturas de design físicas para otimizar o desempenho do servidor dessa carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2b323-112">Used to analyze a workload and recommend physical design structures to optimize server performance for that workload.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="2b323-113">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-113">Tools\Binn</span></span>|  
|[<span data-ttu-id="2b323-114">Utilitário dtexec</span><span class="sxs-lookup"><span data-stu-id="2b323-114">dtexec Utility</span></span>](../integration-services/packages/dtexec-utility.md)|<span data-ttu-id="2b323-115">Usado para configurar e executar um pacote [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b323-115">Used to configure and execute an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="2b323-116">A versão da interface do usuário desse utilitário de prompt de comando é chamada **DTExecUI**e ativa o Utilitário de Execução de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="2b323-116">A user interface version of this command prompt utility is called **DTExecUI**, which brings up the Execute Package Utility.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="2b323-117">DTS\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-117">DTS\Binn</span></span>|  
|[<span data-ttu-id="2b323-118">Utilitário dtutil</span><span class="sxs-lookup"><span data-stu-id="2b323-118">dtutil Utility</span></span>](../integration-services/dtutil-utility.md)|<span data-ttu-id="2b323-119">Usado para gerenciar pacotes SSIS.</span><span class="sxs-lookup"><span data-stu-id="2b323-119">Used to manage SSIS packages.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="2b323-120">DTS\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-120">DTS\Binn</span></span>|  
|[<span data-ttu-id="2b323-121">Implantar soluções de modelo com o Utilitário de Implantação</span><span class="sxs-lookup"><span data-stu-id="2b323-121">Deploy Model Solutions with the Deployment Utility</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/deploy-model-solutions-with-the-deployment-utility)|<span data-ttu-id="2b323-122">Usado para implantar projetos [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] em instâncias do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b323-122">Used to deploy [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projects to instances of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="2b323-123">Tools\Binn\VShell\Common7\IDE</span><span class="sxs-lookup"><span data-stu-id="2b323-123">Tools\Binn\VShell\Common7\IDE</span></span>|  
|[<span data-ttu-id="2b323-124">Utilitário osql</span><span class="sxs-lookup"><span data-stu-id="2b323-124">osql Utility</span></span>](osql-utility.md)|<span data-ttu-id="2b323-125">Permite a inserção de instruções [!INCLUDE[tsql](../includes/tsql-md.md)] , procedimentos do sistema e arquivos de script no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="2b323-125">Allows you to enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements, system procedures, and script files at the command prompt.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="2b323-126">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-126">Tools\Binn</span></span>|  
|[<span data-ttu-id="2b323-127">Utilitário Profiler</span><span class="sxs-lookup"><span data-stu-id="2b323-127">Profiler Utility</span></span>](profiler-utility.md)|<span data-ttu-id="2b323-128">Usado para iniciar o [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] em um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="2b323-128">Used to start [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] from a command prompt.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="2b323-129">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-129">Tools\Binn</span></span>|  
|[<span data-ttu-id="2b323-130">Utilitário RS.exe &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2b323-130">RS.exe Utility &#40;SSRS&#41;</span></span>](../reporting-services/tools/rs-exe-utility-ssrs.md)|<span data-ttu-id="2b323-131">Usado para executar scripts criados para gerenciar servidores de relatório do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b323-131">Used to run scripts designed for managing [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report servers.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="2b323-132">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-132">Tools\Binn</span></span>|  
|[<span data-ttu-id="2b323-133">Utilitário rsconfig &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2b323-133">rsconfig Utility &#40;SSRS&#41;</span></span>](../reporting-services/tools/rsconfig-utility-ssrs.md)|<span data-ttu-id="2b323-134">Usado para configurar uma conexão de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="2b323-134">Used to configure a report server connection.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="2b323-135">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-135">Tools\Binn</span></span>|  
|[<span data-ttu-id="2b323-136">Utilitário rskeymgmt &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2b323-136">rskeymgmt Utility &#40;SSRS&#41;</span></span>](../reporting-services/tools/rskeymgmt-utility-ssrs.md)|<span data-ttu-id="2b323-137">Usado para gerenciar chaves de criptografia em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="2b323-137">Used to manage encryption keys on a report server.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="2b323-138">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-138">Tools\Binn</span></span>|  
|[<span data-ttu-id="2b323-139">Aplicativo sqlagent90</span><span class="sxs-lookup"><span data-stu-id="2b323-139">sqlagent90 Application</span></span>](sqlagent90-application.md)|<span data-ttu-id="2b323-140">Usado para iniciar o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent a partir de um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="2b323-140">Used to start [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent from a command prompt.</span></span>|<span data-ttu-id="2b323-141">\<drive>:\Arquivo de Programas\Microsoft SQL Server\\<*instance_name*>\MSSQL\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-141">\<drive>:\Program Files\Microsoft SQL Server\\<*instance_name*>\MSSQL\Binn</span></span>|  
|[<span data-ttu-id="2b323-142">Utilitário sqlcmd</span><span class="sxs-lookup"><span data-stu-id="2b323-142">sqlcmd Utility</span></span>](sqlcmd-utility.md)|<span data-ttu-id="2b323-143">Permite a inserção de instruções [!INCLUDE[tsql](../includes/tsql-md.md)] , procedimentos do sistema e arquivos de script no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="2b323-143">Allows you to enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements, system procedures, and script files at the command prompt.</span></span>|<span data-ttu-id="2b323-144">\<*drive*:>\Arquivos de Programas\\[!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]\Client SDK\ODBC\110\Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-144">\<*drive*:>\Program Files\\[!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]\Client SDK\ODBC\110\Tools\Binn</span></span>|  
|[<span data-ttu-id="2b323-145">Utilitário SQLdiag</span><span class="sxs-lookup"><span data-stu-id="2b323-145">SQLdiag Utility</span></span>](sqldiag-utility.md)|<span data-ttu-id="2b323-146">Usado para coletar informações de diagnóstico para o Suporte e Atendimento ao Cliente [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b323-146">Used to collect diagnostic information for [!INCLUDE[msCoName](../includes/msconame-md.md)] Customer Service and Support.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="2b323-147">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-147">Tools\Binn</span></span>|  
|[<span data-ttu-id="2b323-148">Aplicativo sqllogship</span><span class="sxs-lookup"><span data-stu-id="2b323-148">sqllogship Application</span></span>](sqllogship-application.md)|<span data-ttu-id="2b323-149">Usado pelos aplicativos para executar as operações de backup, cópia e restauração, além das tarefas associadas de limpeza da configuração de envio de logs sem execução dos trabalhos de backup, cópia e restauração.</span><span class="sxs-lookup"><span data-stu-id="2b323-149">Used by applications to perform backup, copy, and restore operations and associated clean-up tasks for a log shipping configuration without running the backup, copy, and restore jobs.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="2b323-150">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-150">Tools\Binn</span></span>|  
|[<span data-ttu-id="2b323-151">Utilitário SqlLocalDB</span><span class="sxs-lookup"><span data-stu-id="2b323-151">SqlLocalDB Utility</span></span>](sqllocaldb-utility.md)|<span data-ttu-id="2b323-152">Um modo de execução do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] destinado a desenvolvedores de programas.</span><span class="sxs-lookup"><span data-stu-id="2b323-152">An execution mode of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] targeted to program developers.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="2b323-153">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-153">Tools\Binn</span></span>|  
|[<span data-ttu-id="2b323-154">Utilitário sqlmaint</span><span class="sxs-lookup"><span data-stu-id="2b323-154">sqlmaint Utility</span></span>](sqlmaint-utility.md)|<span data-ttu-id="2b323-155">Usado para executar planos de manutenção de banco de dados criados em versões anteriores do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b323-155">Used to execute database maintenance plans created in previous versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>|<span data-ttu-id="2b323-156">\<drive>: \Arquivos de Programas\microsoft SQL Server\MSSQL12. MSSQLSERVER\MSSQL\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-156">\<drive>:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn</span></span>|  
|[<span data-ttu-id="2b323-157">Utilitário sqlps</span><span class="sxs-lookup"><span data-stu-id="2b323-157">sqlps Utility</span></span>](sqlps-utility.md)|<span data-ttu-id="2b323-158">Usado para executar comandos e scripts PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b323-158">Used to run PowerShell commands and scripts.</span></span> <span data-ttu-id="2b323-159">Carrega e registra o provedor e os cmdlets do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b323-159">Loads and registers the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider and cmdlets.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="2b323-160">Tools\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-160">Tools\Binn</span></span>|  
|[<span data-ttu-id="2b323-161">Aplicativo sqlservr</span><span class="sxs-lookup"><span data-stu-id="2b323-161">sqlservr Application</span></span>](sqlservr-application.md)|<span data-ttu-id="2b323-162">Usado para iniciar e parar uma instância de [!INCLUDE[ssDE](../includes/ssde-md.md)] no prompt de comando para solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="2b323-162">Used to start and stop an instance of [!INCLUDE[ssDE](../includes/ssde-md.md)] from the command prompt for troubleshooting.</span></span>|<span data-ttu-id="2b323-163">\<drive>: \Arquivos de Programas\microsoft SQL Server\MSSQL12. MSSQLSERVER\MSSQL\Binn</span><span class="sxs-lookup"><span data-stu-id="2b323-163">\<drive>:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn</span></span>|  
|[<span data-ttu-id="2b323-164">Utilitário de Ssms</span><span class="sxs-lookup"><span data-stu-id="2b323-164">Ssms Utility</span></span>](../ssms/ssms-utility.md)|<span data-ttu-id="2b323-165">Usado para iniciar o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] em um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="2b323-165">Used to start [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="2b323-166">Tools\Binn\VSShell\Common7\IDE</span><span class="sxs-lookup"><span data-stu-id="2b323-166">Tools\Binn\VSShell\Common7\IDE</span></span>|  
|[<span data-ttu-id="2b323-167">Utilitário tablediff</span><span class="sxs-lookup"><span data-stu-id="2b323-167">tablediff Utility</span></span>](tablediff-utility.md)|<span data-ttu-id="2b323-168">Usado para comparar os dados em duas tabelas para não convergência, que é útil na solução de problemas de topologia de replicação.</span><span class="sxs-lookup"><span data-stu-id="2b323-168">Used to compare the data in two tables for non-convergence, which is useful when troubleshooting a replication topology.</span></span>|[!INCLUDE[ssInstallPathVar](../includes/ssinstallpathvar-md.md)]<span data-ttu-id="2b323-169">COM</span><span class="sxs-lookup"><span data-stu-id="2b323-169">COM</span></span>|  
  
 <span data-ttu-id="2b323-170">**Para acessar o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager usando o [!INCLUDE[win8](../includes/win8-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="2b323-170">**To access [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager Using [!INCLUDE[win8](../includes/win8-md.md)]**</span></span>  
  
 <span data-ttu-id="2b323-171">Como o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager é um snap-in do programa [!INCLUDE[msCoName](../includes/msconame-md.md)] Management Console (MMC) e não um programa autônomo, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager não aparece como um aplicativo ao executar o [!INCLUDE[win8](../includes/win8-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b323-171">Because [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager is a snap-in for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Management Console program and not a stand-alone program, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager not does not appear as an application when running [!INCLUDE[win8](../includes/win8-md.md)].</span></span> <span data-ttu-id="2b323-172">Para abrir o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager, no botão **Pesquisar**, em **Aplicativos**, digite **SQLServerManager12.msc** (para [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]) ou **SQLServerManager11.msc** (para [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]) e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="2b323-172">To open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager, in the **Search** charm, under **Apps**, type **SQLServerManager12.msc** (for [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]) or **SQLServerManager11.msc** for ([!INCLUDE[ssSQL11](../includes/sssql11-md.md)]), and then press **Enter**.</span></span>  
  
## <a name="command-prompt-utilities-syntax-conventions"></a><span data-ttu-id="2b323-173">Convenções de sintaxe de utilitários de prompt de comando</span><span class="sxs-lookup"><span data-stu-id="2b323-173">Command Prompt Utilities Syntax Conventions</span></span>  
  
|<span data-ttu-id="2b323-174">**Convenção**</span><span class="sxs-lookup"><span data-stu-id="2b323-174">**Convention**</span></span>|<span data-ttu-id="2b323-175">**Usadas para**</span><span class="sxs-lookup"><span data-stu-id="2b323-175">**Used for**</span></span>|  
|--------------------|------------------|  
|<span data-ttu-id="2b323-176">LETRAS MAIÚSCULAS</span><span class="sxs-lookup"><span data-stu-id="2b323-176">UPPERCASE</span></span>|<span data-ttu-id="2b323-177">Instruções e termos usados no sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="2b323-177">Statements and terms used at the operating system level.</span></span>|  
|`monospace`|<span data-ttu-id="2b323-178">Comandos de exemplo e código de programa.</span><span class="sxs-lookup"><span data-stu-id="2b323-178">Sample commands and program code.</span></span>|  
|<span data-ttu-id="2b323-179">*italic*</span><span class="sxs-lookup"><span data-stu-id="2b323-179">*italic*</span></span>|<span data-ttu-id="2b323-180">Parâmetros fornecidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="2b323-180">User-supplied parameters.</span></span>|  
|<span data-ttu-id="2b323-181">**bold**</span><span class="sxs-lookup"><span data-stu-id="2b323-181">**bold**</span></span>|<span data-ttu-id="2b323-182">Comandos, parâmetros e outra sintaxe que precisam ser digitados exatamente conforme mostrado.</span><span class="sxs-lookup"><span data-stu-id="2b323-182">Commands, parameters, and other syntax that must be typed exactly as shown.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b323-183">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2b323-183">See Also</span></span>  
 <span data-ttu-id="2b323-184">[Replication Distribution Agent](../relational-databases/replication/agents/replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="2b323-184">[Replication Distribution Agent](../relational-databases/replication/agents/replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="2b323-185">[Replication Log Reader Agent](../relational-databases/replication/agents/replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="2b323-185">[Replication Log Reader Agent](../relational-databases/replication/agents/replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="2b323-186">[Replication Merge Agent](../relational-databases/replication/agents/replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="2b323-186">[Replication Merge Agent](../relational-databases/replication/agents/replication-merge-agent.md) </span></span>  
 <span data-ttu-id="2b323-187">[Replication Queue Reader Agent](../relational-databases/replication/agents/replication-queue-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="2b323-187">[Replication Queue Reader Agent](../relational-databases/replication/agents/replication-queue-reader-agent.md) </span></span>  
 [<span data-ttu-id="2b323-188">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="2b323-188">Replication Snapshot Agent</span></span>](../relational-databases/replication/agents/replication-snapshot-agent.md)  
  
  