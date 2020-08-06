---
title: Requisitos para usar tabelas com otimização de memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 47d9a7e8-c597-4b95-a58a-dcf66df8e572
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ecb9d388fd0e1362bb8844e874cd89162912e93e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684744"
---
# <a name="requirements-for-using-memory-optimized-tables"></a><span data-ttu-id="221c2-102">Requisitos para usar tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="221c2-102">Requirements for Using Memory-Optimized Tables</span></span>
  <span data-ttu-id="221c2-103">Além dos requisitos de [hardware e software para a instalação do SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md), veja a seguir os requisitos para usar o OLTP na memória:</span><span class="sxs-lookup"><span data-stu-id="221c2-103">In addition to the [Hardware and Software Requirements for Installing SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md), the following are requirements to use In-Memory OLTP:</span></span>  
  
-   <span data-ttu-id="221c2-104">Enterprise, Developer ou Evaluation edition de 64 bits do [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="221c2-104">64-bit Enterprise, Developer, or Evaluation edition of [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span></span>  
  
-   <span data-ttu-id="221c2-105">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precisa de memória suficiente para manter os dados nas tabelas e índices com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="221c2-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] needs enough memory to hold the data in memory-optimized tables and indexes.</span></span> <span data-ttu-id="221c2-106">Para considerar versões de linha, você deve fornecer uma quantidade de memória duas vezes maior que o tamanho esperado de tabelas e índices com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="221c2-106">To account for row versions, you should provide an amount of memory that is two times the expected size of memory-optimized tables and indexes.</span></span> <span data-ttu-id="221c2-107">Mas a quantidade real de memória necessária dependerá da carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="221c2-107">But the actual amount of memory needed will depend on your workload.</span></span> <span data-ttu-id="221c2-108">Você deve monitorar o uso de memória e fazer ajustes quando necessário.</span><span class="sxs-lookup"><span data-stu-id="221c2-108">You should monitor your memory usage and make adjustments as needed.</span></span> <span data-ttu-id="221c2-109">O tamanho dos dados nas tabelas com otimização de memória não deve exceder a porcentagem permitida do pool.</span><span class="sxs-lookup"><span data-stu-id="221c2-109">The size of data in memory-optimized tables must not exceed the allowed percentage of the pool.</span></span> <span data-ttu-id="221c2-110">Para descobrir o tamanho de uma tabela com otimização de memória, consulte [Sys. dm_db_xtp_table_memory_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="221c2-110">To discover the size of a memory-optimized table, see [sys.dm_db_xtp_table_memory_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql).</span></span>  
  
     <span data-ttu-id="221c2-111">Se você tiver tabelas baseadas em disco no banco de dados, precisará fornecer memória suficiente para o pool de buffers e o processamento de consulta nessas tabelas.</span><span class="sxs-lookup"><span data-stu-id="221c2-111">If you have disk-based tables in the database, you need to provide enough memory for the buffer pool and query processing on those tables.</span></span>  
  
     <span data-ttu-id="221c2-112">É importante saber quanto de memória seu aplicativo OLTP na memória exigirá.</span><span class="sxs-lookup"><span data-stu-id="221c2-112">It is important to know how much memory your In-Memory OLTP application will require.</span></span> <span data-ttu-id="221c2-113">Consulte [Estimar requisitos de memória para tabelas com otimização de memória](memory-optimized-tables.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="221c2-113">See [Estimate Memory Requirements for Memory-Optimized Tables](memory-optimized-tables.md) for more information.</span></span>  
  
-   <span data-ttu-id="221c2-114">O espaço livre em disco é duas vezes o tamanho das tabelas duráveis com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="221c2-114">Free disk space for that is two times the size of your durable memory-optimized tables.</span></span>  
  
-   <span data-ttu-id="221c2-115">Um processador precisa dar suporte à instrução **cmpxchg16b** para usar o OLTP in-memory.</span><span class="sxs-lookup"><span data-stu-id="221c2-115">A processor needs to support the instruction **cmpxchg16b** to use In-Memory OLTP.</span></span> <span data-ttu-id="221c2-116">Todos os processadores de 64 bits modernos dão suporte a **cmpxchg16b**.</span><span class="sxs-lookup"><span data-stu-id="221c2-116">All modern 64-bit processors support **cmpxchg16b**.</span></span>  
  
     <span data-ttu-id="221c2-117">Se você estiver usando um aplicativo host de VM e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exibir um erro causado por um processador mais antigo, verifique se o aplicativo tem uma opção de configuração para permitir **cmpxchg16b**.</span><span class="sxs-lookup"><span data-stu-id="221c2-117">If you are using a VM host application and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] displays an error caused by an older processor, see if the application has a configuration option to allow **cmpxchg16b**.</span></span> <span data-ttu-id="221c2-118">Caso contrário, você pode usar Hyper-V, que dá suporte a **cmpxchg16b** sem precisar modificar uma opção de configuração.</span><span class="sxs-lookup"><span data-stu-id="221c2-118">If not, you could use Hyper-V, which supports **cmpxchg16b** without needing to modify a configuration option.</span></span>  
  
-   <span data-ttu-id="221c2-119">Para instalar OLTP na memória, selecione **Serviços de Mecanismo de Banco de Dados** ao instalar o [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="221c2-119">To install In-Memory OLTP, select **Database Engine Services** when you install [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
     <span data-ttu-id="221c2-120">Para instalar a geração de relatórios ([determinando se uma tabela ou um procedimento armazenado deve ser movido para OLTP na memória](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)) e [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] (para gerenciar o OLTP na memória por meio do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] pesquisador de objetos), selecione **ferramentas de gerenciamento-básicas** ou **ferramentas de gerenciamento-avançadas** ao instalar o [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="221c2-120">To install report generation ([Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)) and [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] (to manage In-Memory OLTP via [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Object Explorer), select **Management Tools-Basic** or **Management Tools-Advanced** when you install [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="important-notes-on-using-hek_2"></a><span data-ttu-id="221c2-121">Observações importantes sobre o uso do [!INCLUDE[hek_2](../../../includes/hek-2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="221c2-121">Important Notes on Using [!INCLUDE[hek_2](../../../includes/hek-2-md.md)]</span></span>  
  
-   <span data-ttu-id="221c2-122">O tamanho total da memória de todas as tabelas duráveis em um banco de dados não deve exceder 250 GB.</span><span class="sxs-lookup"><span data-stu-id="221c2-122">The total in-memory size of all durable tables in a database should not exceed 250 GB.</span></span> <span data-ttu-id="221c2-123">Para obter mais informações, consulte [durabilidade para tabelas com otimização de memória](durability-for-memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="221c2-123">For more information, see [Durability for Memory-Optimized Tables](durability-for-memory-optimized-tables.md).</span></span>  
  
-   <span data-ttu-id="221c2-124">Esta versão do [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] é direcionada para executar de forma otimizada em sistemas com 2 ou 4 soquetes e menos de 60 núcleos.</span><span class="sxs-lookup"><span data-stu-id="221c2-124">This release of [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] is targeted to perform optimally on systems with 2 or 4 sockets and fewer than 60 cores.</span></span>  
  
-   <span data-ttu-id="221c2-125">Os arquivos de ponto de verificação não devem ser excluídos manualmente.</span><span class="sxs-lookup"><span data-stu-id="221c2-125">Checkpoint files must not be manually deleted.</span></span> <span data-ttu-id="221c2-126">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executa automaticamente a coleta de lixo em arquivos de ponto de verificação desnecessários.</span><span class="sxs-lookup"><span data-stu-id="221c2-126">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] automatically performs garbage collection on unneeded checkpoint files.</span></span> <span data-ttu-id="221c2-127">Para obter mais informações, consulte a discussão sobre mesclagem de dados e arquivos Delta em [durabilidade para tabelas com otimização de memória](durability-for-memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="221c2-127">For more information, see the discussion on merging data and delta files in [Durability for Memory-Optimized Tables](durability-for-memory-optimized-tables.md).</span></span>  
  
-   <span data-ttu-id="221c2-128">Na primeira versão do OLTP na memória (no [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]), a única maneira de remover um grupo de arquivos com otimização de memória é descartar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="221c2-128">In this first release of In-Memory OLTP (in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]), the only way to remove a memory-optimized filegroup is to drop the database.</span></span>  
  
-   <span data-ttu-id="221c2-129">Se você tentar excluir um lote grande de linhas enquanto há uma inserção ou atualização de carga de trabalho simultânea afetando o intervalo de linhas que você está tentando excluir, a exclusão poderá falhar.</span><span class="sxs-lookup"><span data-stu-id="221c2-129">If you attempt to delete a large batch of rows while there is a concurrent insert or update workload affecting the range of rows you are trying to delete, the delete will likely fail.</span></span> <span data-ttu-id="221c2-130">A solução alternativa é interromper a inserção ou atualização da carga de trabalho antes de fazer a exclusão.</span><span class="sxs-lookup"><span data-stu-id="221c2-130">The workaround is to stop the insert or update workload before doing the delete.</span></span> <span data-ttu-id="221c2-131">Como alternativa, você pode configurar a transação em transações menores, que seriam menos prováveis de serem corrompidas por uma carga de trabalho simultânea.</span><span class="sxs-lookup"><span data-stu-id="221c2-131">Alternatively, you could configure the transaction into smaller transactions, which would be less likely to be disrupted by a concurrent workload.</span></span> <span data-ttu-id="221c2-132">Como ocorre com todas as operações de gravação em tabelas com otimização de memória, use a lógica de repetição ([Guidelines for Retry Logic for Transactions on Memory-Optimized Tables](../../database-engine/guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables.md)).</span><span class="sxs-lookup"><span data-stu-id="221c2-132">As with all write operations on memory-optimized tables, use retry logic ([Guidelines for Retry Logic for Transactions on Memory-Optimized Tables](../../database-engine/guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables.md)).</span></span>  
  
-   <span data-ttu-id="221c2-133">Se você criar um ou vários bancos de dados com tabelas com otimização de memória, deverá habilitar a inicialização imediata de arquivo (conceda à conta de inicialização do serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o direito de usuário SE_MANAGE_VOLUME_NAME) para a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="221c2-133">If you create one or more databases with memory-optimized tables, you should enable Instant File Initialization (grant the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service startup account the SE_MANAGE_VOLUME_NAME user right) for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="221c2-134">Sem a inicialização imediata de arquivo, os arquivos de armazenamento com otimização de memória (arquivos delta e de dados) serão inicializados após a criação, que pode ter um impacto negativo no desempenho de sua carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="221c2-134">Without Instant File Initialization, memory-optimized storage files (data and delta files) will be initialized upon creation, which can have negative impact on the performance of your workload.</span></span> <span data-ttu-id="221c2-135">Para obter mais informações sobre a inicialização imediata de arquivo, consulte [Inicialização de arquivo de banco de dados](../databases/database-instant-file-initialization.md).</span><span class="sxs-lookup"><span data-stu-id="221c2-135">For more information about Instant File Initialization, see [Database File Initialization](../databases/database-instant-file-initialization.md).</span></span> <span data-ttu-id="221c2-136">Para obter informações sobre como habilitar a inicialização imediata de arquivo, consulte [Como e por que habilitar a inicialização imediata de arquivo](https://blogs.msdn.com/b/sql_pfe_blog/archive/2009/12/23/how-and-why-to-enable-instant-file-initialization.aspx).</span><span class="sxs-lookup"><span data-stu-id="221c2-136">For information on how to enable Instant File Initialization, see [How and Why to Enable Instant File Initialization](https://blogs.msdn.com/b/sql_pfe_blog/archive/2009/12/23/how-and-why-to-enable-instant-file-initialization.aspx).</span></span>  
  
## <a name="did-this-article-help-you-were-listening"></a><span data-ttu-id="221c2-137">Este artigo foi útil para você?</span><span class="sxs-lookup"><span data-stu-id="221c2-137">Did this Article Help You?</span></span> <span data-ttu-id="221c2-138">Estamos ouvindo</span><span class="sxs-lookup"><span data-stu-id="221c2-138">We're Listening</span></span>  
 <span data-ttu-id="221c2-139">Quais são as informações que você está procurando? Você as localizou?</span><span class="sxs-lookup"><span data-stu-id="221c2-139">What information are you looking for, and did you find it?</span></span> <span data-ttu-id="221c2-140">Estamos ouvindo seus comentários para melhorar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="221c2-140">We're listening to your feedback to improve the content.</span></span> <span data-ttu-id="221c2-141">Envie seus comentários para [sqlfeedback@microsoft.com](mailto:sqlfeedback@microsoft.com?subject=Your%20feedback%20about%20the%20Requirements%20for%20Using%20Memory-Optimized%20Tables%20page) .</span><span class="sxs-lookup"><span data-stu-id="221c2-141">Please submit your comments to [sqlfeedback@microsoft.com](mailto:sqlfeedback@microsoft.com?subject=Your%20feedback%20about%20the%20Requirements%20for%20Using%20Memory-Optimized%20Tables%20page).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="221c2-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="221c2-142">See Also</span></span>  
 [<span data-ttu-id="221c2-143">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="221c2-143">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp-in-memory-optimization.md)  
  
  