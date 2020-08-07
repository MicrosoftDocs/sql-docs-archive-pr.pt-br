---
title: Orientador de Otimização do Mecanismo de Banco de Dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.dta.general.f1
ms.assetid: 50dd0a0b-a407-4aeb-bc8b-b02a793aa30a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c49b771fb5a79da36d29f52dd065ca7ca0092aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583559"
---
# <a name="database-engine-tuning-advisor"></a><span data-ttu-id="60955-102">Database Engine Tuning Advisor</span><span class="sxs-lookup"><span data-stu-id="60955-102">Database Engine Tuning Advisor</span></span>
  <span data-ttu-id="60955-103">O DTA (Orientador de Otimização do Mecanismo de Banco de Dados) do [!INCLUDE[msCoName](../../includes/msconame-md.md)] analisa bancos de dados e faz recomendações que você pode usar para otimizar desempenho de consulta.</span><span class="sxs-lookup"><span data-stu-id="60955-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Database Engine Tuning Advisor (DTA) analyzes databases and makes recommendations that you can use to optimize query performance.</span></span> <span data-ttu-id="60955-104">Você pode usar o Orientador de Otimização do Mecanismo de Banco de Dados para selecionar e criar um conjunto ideal de índices, exibições indexadas e partições de tabela sem precisar de conhecimentos avançados sobre a estrutura do banco de dados ou dos recursos internos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60955-104">You can use the Database Engine Tuning Advisor to select and create an optimal set of indexes, indexed views, or table partitions without having an expert understanding of the database structure or the internals of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="60955-105">Com o DTA, é possível executar as tarefas a seguir.</span><span class="sxs-lookup"><span data-stu-id="60955-105">Using the DTA, you can perform the following tasks.</span></span>  
  
-   <span data-ttu-id="60955-106">Solucionar problemas de desempenho de uma consulta de problema específica</span><span class="sxs-lookup"><span data-stu-id="60955-106">Troubleshoot the performance of a specific problem query</span></span>  
  
-   <span data-ttu-id="60955-107">Ajustar um conjunto grande de consultas por um ou mais bancos de dados</span><span class="sxs-lookup"><span data-stu-id="60955-107">Tune a large set of queries across one or more databases</span></span>  
  
-   <span data-ttu-id="60955-108">Executar uma análise E-Se exploratória de possíveis alterações de design físico</span><span class="sxs-lookup"><span data-stu-id="60955-108">Perform an exploratory what-if analysis of potential physical design changes</span></span>  
  
-   <span data-ttu-id="60955-109">Gerenciar o espaço de armazenamento</span><span class="sxs-lookup"><span data-stu-id="60955-109">Manage storage space</span></span>  
  
## <a name="database-engine-tuning-advisor-benefits"></a><span data-ttu-id="60955-110">Benefícios do Orientador de Otimização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="60955-110">Database Engine Tuning Advisor Benefits</span></span>  
 <span data-ttu-id="60955-111">A otimização do desempenho de consulta pode ser difícil sem uma compreensão completa da estrutura de banco de dados e as consultas que são executadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="60955-111">Optimizing query performance can be difficult without a full understanding the database structure and the queries that are run against the database.</span></span> <span data-ttu-id="60955-112">O Orientador de Otimização do Mecanismo de Banco de Dados pode fazer essa tarefa com mais facilidade analisando o cache de planos da consulta atual ou analisando uma carga de trabalho de consultas [!INCLUDE[tsql](../../includes/tsql-md.md)] que você cria e recomendando um design físico apropriado.</span><span class="sxs-lookup"><span data-stu-id="60955-112">The Database Engine Tuning Advisor can make this task easier by analyzing the current query plan cache or by analyzing a workload of [!INCLUDE[tsql](../../includes/tsql-md.md)] queries that you create and recommending an appropriate physical design.</span></span> <span data-ttu-id="60955-113">Para administradores de banco de dados mais experientes, o DTA expõe um mecanismo avançado para executar a análise E-Se exploratória de diferentes alternativas de design físico.</span><span class="sxs-lookup"><span data-stu-id="60955-113">For more advanced database administrators, DTA exposes a powerful mechanism to perform exploratory what-if analysis of different physical design alternatives.</span></span> <span data-ttu-id="60955-114">O DTA pode fornecer as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="60955-114">The DTA can provide the following information.</span></span>  
  
-   <span data-ttu-id="60955-115">Recomendar a melhor combinação de índices para bancos de dados utilizando o otimizador de consulta para analisar consultas em uma carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="60955-115">Recommend the best mix of indexes for databases by using the query optimizer to analyze queries in a workload.</span></span>  
  
-   <span data-ttu-id="60955-116">Recomendar partições alinhadas ou desalinhadas para bancos de dados referenciados em uma carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="60955-116">Recommend aligned or non-aligned partitions for databases referenced in a workload.</span></span>  
  
-   <span data-ttu-id="60955-117">Recomendar exibições indexadas para bancos de dados referenciados em uma carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="60955-117">Recommend indexed views for databases referenced in a workload.</span></span>  
  
-   <span data-ttu-id="60955-118">Analisar os efeitos das mudanças propostas, inclusive o uso de índice, distribuição de consultas entre tabelas e desempenho de consultas na carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="60955-118">Analyze the effects of the proposed changes, including index usage, query distribution among tables, and query performance in the workload.</span></span>  
  
-   <span data-ttu-id="60955-119">Recomendar modos de ajuste do banco de dados para um pequeno conjunto de consultas de problema.</span><span class="sxs-lookup"><span data-stu-id="60955-119">Recommend ways to tune the database for a small set of problem queries.</span></span>  
  
-   <span data-ttu-id="60955-120">Permitir a personalização da recomendação especificando opções avançadas, como restrição de espaço em disco.</span><span class="sxs-lookup"><span data-stu-id="60955-120">Allow you to customize the recommendation by specifying advanced options such as disk space constraints.</span></span>  
  
-   <span data-ttu-id="60955-121">Fornecer relatórios que resumam os efeitos de implementação das recomendações para uma determinada carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="60955-121">Provide reports that summarize the effects of implementing the recommendations for a given workload.</span></span>  
  
 <span data-ttu-id="60955-122">O Orientador de Otimização do Mecanismo de Banco de Dados é projetado para tratar os seguintes tipos de cargas de trabalho de consulta.</span><span class="sxs-lookup"><span data-stu-id="60955-122">The Database Engine Tuning Advisor is designed to handle the following types of query workloads.</span></span>  
  
-   <span data-ttu-id="60955-123">Processamento de transações online (OLTP) somente consulta</span><span class="sxs-lookup"><span data-stu-id="60955-123">Online transaction processing (OLTP) queries only</span></span>  
  
-   <span data-ttu-id="60955-124">Processamento analítico online (OLAP) somente consulta</span><span class="sxs-lookup"><span data-stu-id="60955-124">Online analytical processing (OLAP) queries only</span></span>  
  
-   <span data-ttu-id="60955-125">Consultas OLAP e OLTP mistas</span><span class="sxs-lookup"><span data-stu-id="60955-125">Mixed OLTP and OLAP queries</span></span>  
  
-   <span data-ttu-id="60955-126">Cargas de trabalho de consulta pesadas (mais consultas do que modificações de dados)</span><span class="sxs-lookup"><span data-stu-id="60955-126">Query-heavy workloads (more queries than data modifications)</span></span>  
  
-   <span data-ttu-id="60955-127">Cargas de trabalho de atualização pesadas (mais modificações de dados do que consultas)</span><span class="sxs-lookup"><span data-stu-id="60955-127">Update-heavy workloads (more data modifications than queries)</span></span>  
  
## <a name="dta-components-and-concepts"></a><span data-ttu-id="60955-128">Componentes e conceitos do DTA</span><span class="sxs-lookup"><span data-stu-id="60955-128">DTA Components and Concepts</span></span>  
 <span data-ttu-id="60955-129">Interface gráfica do usuário do Orientador de Otimização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="60955-129">Database Engine Tuning Advisor Graphical User Interface</span></span>  
 <span data-ttu-id="60955-130">Uma interface fácil de usar na qual você pode especificar a carga de trabalho e selecionar várias opções de ajuste.</span><span class="sxs-lookup"><span data-stu-id="60955-130">An easy-to-use interface in which you can specify the workload and select various tuning options.</span></span>  
  
 <span data-ttu-id="60955-131">Utilitário**dta**</span><span class="sxs-lookup"><span data-stu-id="60955-131">**dta** Utility</span></span>  
 <span data-ttu-id="60955-132">A versão do prompt de comando do Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="60955-132">The command prompt version of Database Engine Tuning Advisor.</span></span> <span data-ttu-id="60955-133">O utilitário **dta** foi projetado para permitir o uso da funcionalidade do Orientador de Otimização do Mecanismo de Banco de Dados em aplicativos e scripts.</span><span class="sxs-lookup"><span data-stu-id="60955-133">The **dta** utility is designed to allow you to use Database Engine Tuning Advisor functionality in applications and scripts.</span></span>  
  
 <span data-ttu-id="60955-134">workload</span><span class="sxs-lookup"><span data-stu-id="60955-134">workload</span></span>  
 <span data-ttu-id="60955-135">Um arquivo de script, um arquivo de rastreamento ou uma tabela de rastreamento Transact-SQL que contém uma carga de trabalho representativa para os bancos de dados a serem ajustados.</span><span class="sxs-lookup"><span data-stu-id="60955-135">A Transact-SQL script file, trace file, or trace table that contains a representative workload for the databases you want to tune.</span></span> <span data-ttu-id="60955-136">Começando com o [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], você pode especificar o cache de planos como carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="60955-136">Beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], you can specify the plan cache as the workload.</span></span>  
  
 <span data-ttu-id="60955-137">Arquivo de entrada XML</span><span class="sxs-lookup"><span data-stu-id="60955-137">XML input file</span></span>  
 <span data-ttu-id="60955-138">Um arquivo formatado pelo XML que o Orientador de Otimização do Mecanismo de Banco de Dados pode usar para ajustar cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="60955-138">An XML-formatted file that Database Engine Tuning Advisor can use to tune workloads.</span></span> <span data-ttu-id="60955-139">O arquivo de entrada XML dá suporte a opções de ajuste avançadas que não estão disponível na GUI nem no utilitário **dta** .</span><span class="sxs-lookup"><span data-stu-id="60955-139">The XML input file supports advanced tuning options that are not available in either the GUI or **dta** utility.</span></span>  
  
## <a name="limitations-and-restrictions"></a><span data-ttu-id="60955-140">Limitações e Restrições</span><span class="sxs-lookup"><span data-stu-id="60955-140">Limitations and Restrictions</span></span>  
 <span data-ttu-id="60955-141">O Orientador de Otimização do Mecanismo de Banco de Dados tem as seguintes limitações e restrições:</span><span class="sxs-lookup"><span data-stu-id="60955-141">The Database Engine Tuning Advisor has the following limitations and restrictions.</span></span>  
  
-   <span data-ttu-id="60955-142">Ele não pode adicionar ou remover índices exclusivos ou índices que impõem restrições PRIMARY KEY ou UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="60955-142">It cannot add or drop unique indexes or indexes that enforce PRIMARY KEY or UNIQUE constraints.</span></span>  
  
-   <span data-ttu-id="60955-143">Ele não pode analisar um banco de dados que está definido para modo de usuário único.</span><span class="sxs-lookup"><span data-stu-id="60955-143">It cannot analyze a database that is set to single-user mode.</span></span>  
  
-   <span data-ttu-id="60955-144">Se você especificar um espaço máximo em disco para ajustar recomendações que excedem o espaço disponível real, o Orientador de Otimização do Mecanismo de Banco de Dados usará o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="60955-144">If you specify a maximum disk space for tuning recommendations that exceeds the actual available space, Database Engine Tuning Advisor uses the value you specify.</span></span> <span data-ttu-id="60955-145">No entanto, quando você executa o script de recomendação para implementá-lo, o script poderá apresentar erro se antes não for adicionado mais espaço em disco.</span><span class="sxs-lookup"><span data-stu-id="60955-145">However, when you execute the recommendation script to implement it, the script may fail if more disk space is not added first.</span></span> <span data-ttu-id="60955-146">O espaço máximo em disco pode ser especificado com a opção **-B** do utilitário **dta** , ou inserindo um valor na caixa de diálogo **Opções de Ajuste Avançadas** .</span><span class="sxs-lookup"><span data-stu-id="60955-146">Maximum disk space can be specified with the **-B** option of the **dta** utility, or by entering a value in the **Advanced Tuning Options** dialog box.</span></span>  
  
-   <span data-ttu-id="60955-147">Por razões de segurança, o Orientador de Otimização do Mecanismo de Banco de Dados não pode ajustar uma carga de trabalho em uma tabela de rastreamento que reside em um servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="60955-147">For security reasons, Database Engine Tuning Advisor cannot tune a workload in a trace table that resides on a remote server.</span></span> <span data-ttu-id="60955-148">Para driblar essa limitação, você pode usar um arquivo de rastreamento em vez de uma tabela de rastreamento ou pode copiar a tabela de rastreamento para o servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="60955-148">To work around this limitation, you can use a trace file instead of a trace table or copy the trace table to the remote server.</span></span>  
  
-   <span data-ttu-id="60955-149">Quando você impõe restrições, como as impostas quando você especifica um espaço máximo em disco ao ajustar recomendações (usando a opção **-B** ou a caixa de diálogo **Opções de Ajuste Avançadas** ), o Orientador de Otimização do Mecanismo de Banco de Dados pode ser forçado a remover certos índices existentes.</span><span class="sxs-lookup"><span data-stu-id="60955-149">When you impose constraints, such as those imposed when you specify a maximum disk space for tuning recommendations (by using the **-B** option or the **Advanced Tuning Options** dialog box), Database Engine Tuning Advisor may be forced to drop certain existing indexes.</span></span> <span data-ttu-id="60955-150">Nesse caso, a recomendação Orientador de Otimização do Mecanismo de Banco de Dados resultante pode produzir um aperfeiçoamento esperado negativo.</span><span class="sxs-lookup"><span data-stu-id="60955-150">In this case, the resulting Database Engine Tuning Advisor recommendation may produce a negative expected improvement.</span></span>  
  
-   <span data-ttu-id="60955-151">Quando você especifica uma restrição para limitar o tempo de ajuste (usando a opção **-A** com o utilitário **dta** ou marcando **Limitar tempo de ajuste** na guia **Opções de Ajuste** ), o Orientador de Otimização do Mecanismo de Banco de Dados pode exceder o tempo limite para produzir um aperfeiçoamento esperado preciso e os relatórios de análise para as porções da carga de trabalho consumidas até o momento.</span><span class="sxs-lookup"><span data-stu-id="60955-151">When you specify a constraint to limit tuning time (by using the **-A** option with the **dta** utility or by checking **Limit tuning time** on the **Tuning Options** tab), Database Engine Tuning Advisor may exceed that time limit to produce an accurate expected improvement and the analysis reports for whatever portion of the workload has been consumed so far.</span></span>  
  
-   <span data-ttu-id="60955-152">O Orientador de Otimização do Mecanismo de Banco de Dados não faz recomendações nas seguintes circunstâncias:</span><span class="sxs-lookup"><span data-stu-id="60955-152">Database Engine Tuning Advisor might not make recommendations under the following circumstances:</span></span>  
  
    1.  <span data-ttu-id="60955-153">A tabela que está sendo ajustada contém menos de 10 páginas de dados.</span><span class="sxs-lookup"><span data-stu-id="60955-153">The table being tuned contains less than 10 data pages.</span></span>  
  
    2.  <span data-ttu-id="60955-154">Os índices recomendados não oferecem aperfeiçoamento suficiente no desempenho da consulta no design do banco de dados físico atual.</span><span class="sxs-lookup"><span data-stu-id="60955-154">The recommended indexes would not offer enough improvement in query performance over the current physical database design.</span></span>  
  
    3.  <span data-ttu-id="60955-155">O usuário que executa o Orientador de Otimização do Mecanismo de Banco de Dados não é um membro da função de banco de dados `db_owner` nem da função de servidor fixa `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="60955-155">The user who runs Database Engine Tuning Advisor is not a member of the `db_owner` database role or the `sysadmin` fixed server role.</span></span> <span data-ttu-id="60955-156">As consultas na carga de trabalho são analisadas no contexto de segurança do usuário que executa o Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="60955-156">The queries in the workload are analyzed in the security context of the user who runs the Database Engine Tuning Advisor.</span></span> <span data-ttu-id="60955-157">O usuário deve ser um membro da função de banco de dados `db_owner`.</span><span class="sxs-lookup"><span data-stu-id="60955-157">The user must be a member of the `db_owner` database role.</span></span>  
  
-   <span data-ttu-id="60955-158">O Orientador de Otimização do Mecanismo de Banco de Dados armazena dados de sessão de ajuste e outras informações no banco de dados `msdb`.</span><span class="sxs-lookup"><span data-stu-id="60955-158">Database Engine Tuning Advisor stores tuning session data and other information in the `msdb` database.</span></span> <span data-ttu-id="60955-159">Se forem feitas alterações no banco de dados `msdb`, você estará correndo o risco de perder dados da sessão de ajuste.</span><span class="sxs-lookup"><span data-stu-id="60955-159">If changes are made to the `msdb` database you may risk losing tuning session data.</span></span> <span data-ttu-id="60955-160">Para eliminar esse risco, implemente uma estratégia de backup apropriada para o banco de dados `msdb`.</span><span class="sxs-lookup"><span data-stu-id="60955-160">To eliminate this risk, implement an appropriate backup strategy for the `msdb` database.</span></span>  
  
## <a name="performance-considerations"></a><span data-ttu-id="60955-161">Considerações sobre desempenho</span><span class="sxs-lookup"><span data-stu-id="60955-161">Performance Considerations</span></span>  
 <span data-ttu-id="60955-162">O Orientador de Otimização do Mecanismo de Banco de Dados pode consumir recursos de processador e memória significativos durante a análise.</span><span class="sxs-lookup"><span data-stu-id="60955-162">Database Engine Tuning Advisor can consume significant processor and memory resources during analysis.</span></span> <span data-ttu-id="60955-163">Para evitar a redução de velocidade do servidor de produção, siga uma destas estratégias:</span><span class="sxs-lookup"><span data-stu-id="60955-163">To avoid slowing down your production server, follow one of these strategies:</span></span>  
  
-   <span data-ttu-id="60955-164">Ajuste os bancos de dados quando o servidor estiver livre.</span><span class="sxs-lookup"><span data-stu-id="60955-164">Tune your databases when your server is free.</span></span> <span data-ttu-id="60955-165">O Orientador de Otimização do Mecanismo de Banco de Dados pode afetar o desempenho da tarefa de manutenção.</span><span class="sxs-lookup"><span data-stu-id="60955-165">Database Engine Tuning Advisor can affect maintenance task performance.</span></span>  
  
-   <span data-ttu-id="60955-166">Use o recurso servidor de teste/servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="60955-166">Use the test server/production server feature.</span></span> <span data-ttu-id="60955-167">Para obter mais informações, consulte  [Reduzir a carga de ajuste do servidor de produção](reduce-the-production-server-tuning-load.md).</span><span class="sxs-lookup"><span data-stu-id="60955-167">For more information, see  [Reduce the Production Server Tuning Load](reduce-the-production-server-tuning-load.md).</span></span>  
  
-   <span data-ttu-id="60955-168">Especifique só as estruturas de design de banco de dados físico que você quer que o Orientador de Otimização do Mecanismo de Banco de Dados analise.</span><span class="sxs-lookup"><span data-stu-id="60955-168">Specify only the physical database design structures you want Database Engine Tuning Advisor to analyze.</span></span> <span data-ttu-id="60955-169">O Orientador de Otimização do Mecanismo de Banco de Dados fornece muitas opções, mas só especifica as que são necessárias.</span><span class="sxs-lookup"><span data-stu-id="60955-169">Database Engine Tuning Advisor provides many options, but specifies only those that are necessary.</span></span>  
  
## <a name="dependency-on-xp_msver-extended-stored-procedure"></a><span data-ttu-id="60955-170">Dependência em Procedimento armazenado estendido xp_msver</span><span class="sxs-lookup"><span data-stu-id="60955-170">Dependency on xp_msver Extended Stored Procedure</span></span>  
 <span data-ttu-id="60955-171">O Orientador de Otimização do Mecanismo de Banco de Dados depende do procedimento armazenado estendido **xp_msver** para fornecer a funcionalidade completa.</span><span class="sxs-lookup"><span data-stu-id="60955-171">Database Engine Tuning Advisor depends on the **xp_msver** extended stored procedure to provide full functionality.</span></span> <span data-ttu-id="60955-172">Esse procedimento armazenado estendido é ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="60955-172">This extended stored procedure is turned on by default.</span></span> <span data-ttu-id="60955-173">O Orientador de Otimização do Mecanismo de Banco de Dados usa esse procedimento armazenado estendido para buscar o número de processadores e a memória disponível no computador onde o banco de dados que está sendo ajustado está localizado.</span><span class="sxs-lookup"><span data-stu-id="60955-173">Database Engine Tuning Advisor uses this extended stored procedure to fetch the number of processors and available memory on the computer where the database that you are tuning resides.</span></span> <span data-ttu-id="60955-174">Se o **xp_msver** não estiver disponível, o Orientador de Otimização do Mecanismo de Banco de Dados assumirá as características de hardware do computador no qual o Orientador de Otimização do Mecanismo de Banco de Dados está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="60955-174">If **xp_msver** is unavailable, Database Engine Tuning Advisor assumes the hardware characteristics of the computer where Database Engine Tuning Advisor is running.</span></span> <span data-ttu-id="60955-175">Se as características de hardware do computador onde o Orientador de Otimização do Mecanismo de Banco de Dados está sendo executado não estiverem disponíveis, supõe-se um processador e 1024 megabytes (MBs) de memória.</span><span class="sxs-lookup"><span data-stu-id="60955-175">If the hardware characteristics of the computer where Database Engine Tuning Advisor is running are not available, one processor and 1024 megabytes (MBs) of memory are assumed.</span></span>  
  
 <span data-ttu-id="60955-176">Essa dependência afeta as recomendações de particionamento porque o número de partições recomendado depende destes dois valores (número de processadores e memória disponível).</span><span class="sxs-lookup"><span data-stu-id="60955-176">This dependency affects partitioning recommendations because the number of partitions recommended depends on these two values (number of processors and available memory).</span></span> <span data-ttu-id="60955-177">A dependência também afeta os resultados de ajustes quando você usar um servidor de teste para ajustar o servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="60955-177">The dependency also affects your tuning results when you use a test server to tune your production server.</span></span> <span data-ttu-id="60955-178">Nesse cenário,o Orientador de Otimização do Mecanismo de Banco de Dados usa o **xp_msver** para buscar propriedades de hardware do servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="60955-178">In this scenario, Database Engine Tuning Advisor uses **xp_msver** to fetch hardware properties from the production server.</span></span> <span data-ttu-id="60955-179">Após ajustar a carga de trabalho no servidor de teste, o Orientador de Otimização do Mecanismo de Banco de Dados usa estas propriedades de hardware para gerar uma recomendação.</span><span class="sxs-lookup"><span data-stu-id="60955-179">After tuning the workload on the test server, Database Engine Tuning Advisor uses these hardware properties to generate a recommendation.</span></span> <span data-ttu-id="60955-180">Para obter mais informações, veja [xp_msver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/xp-msver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="60955-180">For more information, see [xp_msver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/xp-msver-transact-sql).</span></span>  
  
## <a name="database-engine-tuning-advisor-tasks"></a><span data-ttu-id="60955-181">Tarefas do Orientador de Otimização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="60955-181">Database Engine Tuning Advisor Tasks</span></span>  
 <span data-ttu-id="60955-182">A tabela a seguir lista as tarefas comuns do Orientador de Otimização do Mecanismo de Banco de Dados e os tópicos que descrevem como executá-los.</span><span class="sxs-lookup"><span data-stu-id="60955-182">The following table lists common Database Engine Tuning Advisor tasks and the topics that describe how to perform them.</span></span>  
  
|<span data-ttu-id="60955-183">Tarefa do Orientador de Otimização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="60955-183">Database Engine Tuning Advisor Task</span></span>|<span data-ttu-id="60955-184">Tópico</span><span class="sxs-lookup"><span data-stu-id="60955-184">Topic</span></span>|  
|-----------------------------------------|-----------|  
|<span data-ttu-id="60955-185">Inicializar e iniciar o Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="60955-185">Initialize and start the Database Engine Tuning Advisor.</span></span><br /><br /> <span data-ttu-id="60955-186">Criar uma carga de trabalho especificando o cache de planos, criando um script ou gerando um arquivo de rastreamento ou uma tabela de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="60955-186">Create a workload by specifying the plan cache, by creating a script, or by generating a trace file or trace table.</span></span><br /><br /> <span data-ttu-id="60955-187">Ajuste um banco de dados usando a ferramenta de interface gráfica Orientador de Otimização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="60955-187">Tune a database by using the Database Engine Tuning Advisor graphical user interface tool.</span></span><br /><br /> <span data-ttu-id="60955-188">Criar arquivos de entrada XML para ajustar cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="60955-188">Create XML input files to tune workloads.</span></span><br /><br /> <span data-ttu-id="60955-189">Exibir as descrições das opções de interface do usuário do Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="60955-189">View descriptions of the Database Engine Tuning Advisor user interface options.</span></span>|[<span data-ttu-id="60955-190">Iniciar e usar o Orientador de Otimização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="60955-190">Start and Use the Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)|  
|<span data-ttu-id="60955-191">Exibir os resultados da operação de ajuste do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="60955-191">View the results of the database tuning operation.</span></span><br /><br /> <span data-ttu-id="60955-192">Selecionar e implementar recomendações de ajuste.</span><span class="sxs-lookup"><span data-stu-id="60955-192">Select and implement tuning recommendations.</span></span><br /><br /> <span data-ttu-id="60955-193">Executar uma análise E-Se exploratória na carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="60955-193">Perform what-if exploratory analysis against the workload.</span></span><br /><br /> <span data-ttu-id="60955-194">Revisar sessões de ajuste existente, clonar sessões com base nas existentes</span><span class="sxs-lookup"><span data-stu-id="60955-194">Review existing tuning sessions, clone sessions based on existing ones</span></span> <br /><span data-ttu-id="60955-195">ou editar recomendações de ajuste existente para avaliação adicional ou implementação.</span><span class="sxs-lookup"><span data-stu-id="60955-195">or edit existing tuning recommendations for further evaluation or implementation.</span></span><br /><br /> <span data-ttu-id="60955-196">Exibir as descrições das opções de interface do usuário do Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="60955-196">View descriptions of the Database Engine Tuning Advisor user interface options.</span></span>|[<span data-ttu-id="60955-197">Exibir e trabalhar com a saída do Orientador de Otimização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="60955-197">View and Work with the Output from the Database Engine Tuning Advisor</span></span>](view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md)|  
  
  