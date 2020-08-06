---
title: Tarefa Consulta de Mineração de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingquerytask.f1
helpviewer_keywords:
- prediction queries [Integration Services]
- Data Mining Query task [Integration Services]
ms.assetid: f489348c-2008-4f66-8c2c-c07c3029439a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6bb3cea630401f92395e2ca4416c03bcd870c881
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574859"
---
# <a name="data-mining-query-task"></a><span data-ttu-id="cbedb-102">Data Mining Query Task</span><span class="sxs-lookup"><span data-stu-id="cbedb-102">Data Mining Query Task</span></span>
  <span data-ttu-id="cbedb-103">A tarefa Consulta de Mineração de Dados executa consultas de previsão com base em modelos internos de mineração de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbedb-103">The Data Mining Query task runs prediction queries based on data mining models built in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="cbedb-104">A consulta de previsão cria uma previsão para novos dados usando modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="cbedb-104">The prediction query creates a prediction for new data by using mining models.</span></span> <span data-ttu-id="cbedb-105">Por exemplo, uma consulta de previsão pode prever quantos veleiros serão vendidos durante os meses de verão ou gerar uma lista de possíveis clientes para a compra de um veleiro.</span><span class="sxs-lookup"><span data-stu-id="cbedb-105">For example, a prediction query can predict how many sailboats are likely to sell during the summer months or generate a list of prospective customers who are likely to buy a sailboat.</span></span>  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="cbedb-106">fornece tarefas que desempenham outras operações de business intelligence, como executar instruções DDL (linguagem de definição de dados) e objetos de análise de processamento.</span><span class="sxs-lookup"><span data-stu-id="cbedb-106">provides tasks that perform other business intelligence operations, such as running Data Definition Language (DDL) statements and processing analytic objects.</span></span>  
  
 <span data-ttu-id="cbedb-107">Para obter mais informações sobre outras tarefas de business intelligence, clique em um dos tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="cbedb-107">For more information about other business intelligence tasks, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="cbedb-108">Tarefa Executar DDL do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cbedb-108">Analysis Services Execute DDL Task</span></span>](analysis-services-execute-ddl-task.md)  
  
-   [<span data-ttu-id="cbedb-109">Tarefa Processamento do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cbedb-109">Analysis Services Processing Task</span></span>](analysis-services-processing-task.md)  
  
## <a name="prediction-queries"></a><span data-ttu-id="cbedb-110">Consultas de previsão</span><span class="sxs-lookup"><span data-stu-id="cbedb-110">Prediction Queries</span></span>  
 <span data-ttu-id="cbedb-111">A consulta é uma instrução DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="cbedb-111">The query is a Data Mining Extensions (DMX) statement.</span></span> <span data-ttu-id="cbedb-112">A linguagem DMX é uma extensão da linguagem SQL que fornece suporte ao trabalho com modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="cbedb-112">The DMX language is an extension of the SQL language that provides support for working with mining models.</span></span> <span data-ttu-id="cbedb-113">Para obter mais informações sobre como usar a linguagem DMX, consulte [Referência de extensões de Data Mining &#40;Extensão de Data Mining&#41;](/sql/dmx/data-mining-extensions-dmx-reference).</span><span class="sxs-lookup"><span data-stu-id="cbedb-113">For more information about how to use the DMX language, see [Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference).</span></span>  
  
 <span data-ttu-id="cbedb-114">A tarefa pode consultar múltiplos modelos de mineração criados com a mesma estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="cbedb-114">The task can query multiple mining models that are built on the same mining structure.</span></span> <span data-ttu-id="cbedb-115">Um modelo de mineração é criado com um dos algoritmos de mineração de dados que o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fornece.</span><span class="sxs-lookup"><span data-stu-id="cbedb-115">A mining model is built using one of the data mining algorithms that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides.</span></span> <span data-ttu-id="cbedb-116">A estrutura de mineração a que a tarefa Consulta de Mineração de Dados faz referência pode incluir vários modelos de mineração, criados com algoritmos diferentes.</span><span class="sxs-lookup"><span data-stu-id="cbedb-116">The mining structure that the Data Mining Query task references can include multiple mining models, built using different algorithms.</span></span> <span data-ttu-id="cbedb-117">Para obter mais informações, consulte [Estruturas de Mineração &#40;Analysis Services – Data Mining&#41;](https://docs.microsoft.com/analysis-services/data-mining/mining-structures-analysis-services-data-mining) e [Algoritmos de Data Mining &#40;Analysis Services – Data Mining&#41;](https://docs.microsoft.com/analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining).</span><span class="sxs-lookup"><span data-stu-id="cbedb-117">For more information, see [Mining Structures &#40;Analysis Services - Data Mining&#41;](https://docs.microsoft.com/analysis-services/data-mining/mining-structures-analysis-services-data-mining) and [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](https://docs.microsoft.com/analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining).</span></span>  
  
 <span data-ttu-id="cbedb-118">A consulta de previsão que a tarefa Consulta de Mineração de Dados executa retorna um resultado que é uma única linha ou um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="cbedb-118">The prediction query that the Data Mining Query task runs returns a result that is a single row or a data set.</span></span> <span data-ttu-id="cbedb-119">Uma consulta que retorna uma única linha é chamada consulta singleton: por exemplo, a consulta que prevê quantos veleiros serão vendidos durante os meses de verão retorna um número.</span><span class="sxs-lookup"><span data-stu-id="cbedb-119">A query that returns a single row is called a singleton query: for example, the query that predicts how many sailboats will be sold during the summer months returns a number.</span></span> <span data-ttu-id="cbedb-120">Para obter mais informações sobre consultas de previsão que retornam uma única linha, consulte [interfaces de consulta de mineração de dados](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools).</span><span class="sxs-lookup"><span data-stu-id="cbedb-120">For more information about prediction queries that return a single row, see [Data Mining Query Interfaces](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools).</span></span>  
  
 <span data-ttu-id="cbedb-121">Os resultados da consulta são salvos nas tabelas.</span><span class="sxs-lookup"><span data-stu-id="cbedb-121">The query results are saved to tables.</span></span> <span data-ttu-id="cbedb-122">Se uma tabela com o nome que a tarefa Consulta de Mineração de Dados especifica já existir, a tarefa poderá criar uma nova tabela usando o mesmo nome com um número anexado ou poderá substituir o conteúdo da tabela.</span><span class="sxs-lookup"><span data-stu-id="cbedb-122">If a table with the name that the Data Mining Query task specifies already exists, the task can create a new table, using the same name with a number appended, or it can overwrite the table content.</span></span>  
  
 <span data-ttu-id="cbedb-123">Se os resultados incluírem aninhamento, o resultado será simplificado antes de ser salvo.</span><span class="sxs-lookup"><span data-stu-id="cbedb-123">If the results include nesting, the result is flattened before it is saved.</span></span> <span data-ttu-id="cbedb-124">A simplificação de um resultado altera um resultado aninhado definido para uma tabela.</span><span class="sxs-lookup"><span data-stu-id="cbedb-124">Flattening a result changes a nested result set to a table.</span></span> <span data-ttu-id="cbedb-125">Por exemplo, simplificar um resultado aninhado com uma coluna **Cliente** e uma coluna aninhada **Produto** adiciona linhas à coluna **Cliente** para fazer uma tabela que inclui dados de produto para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="cbedb-125">For example, flattening a nested result with a **Customer** column and a nested **Product** column adds rows to the **Customer** column to make a table that includes product data for each customer.</span></span> <span data-ttu-id="cbedb-126">Por exemplo, um cliente com três produtos diferentes transforma-se em uma tabela com três linhas, repetindo o cliente em cada linha e incluindo um produto diferente em cada linha.</span><span class="sxs-lookup"><span data-stu-id="cbedb-126">For example, a customer with three different products becomes a table with three rows, repeating the customer in each row and including a different product in each row.</span></span> <span data-ttu-id="cbedb-127">Se a palavra-chave FLATTENED for omitida, a tabela conterá só a coluna **Cliente** e só uma linha por cliente.</span><span class="sxs-lookup"><span data-stu-id="cbedb-127">If the FLATTENED keyword is omitted, the table contains only the **Customer** column and only one row per customer.</span></span> <span data-ttu-id="cbedb-128">Para obter mais informações, consulte [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span><span class="sxs-lookup"><span data-stu-id="cbedb-128">For more information, see [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span></span>  
  
## <a name="configuration-of-the-data-mining-query-task"></a><span data-ttu-id="cbedb-129">Configuração da tarefa Consulta de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="cbedb-129">Configuration of the Data Mining Query Task</span></span>  
 <span data-ttu-id="cbedb-130">A tarefa Consulta de Mineração de Dados requer duas conexões.</span><span class="sxs-lookup"><span data-stu-id="cbedb-130">The Data Mining Query task requires two connections.</span></span> <span data-ttu-id="cbedb-131">A primeira conexão é um gerenciador de conexões do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que se conecta a uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou a um projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contém a estrutura de mineração e o modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="cbedb-131">The first connection is an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager that connects either to an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] or to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project that contains the mining structure and the mining model.</span></span> <span data-ttu-id="cbedb-132">A segunda conexão é um gerenciador de conexões OLE DB que se conecta ao banco de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que contém a tabela na qual a tarefa é gravada.</span><span class="sxs-lookup"><span data-stu-id="cbedb-132">The second connection is an OLE DB connection manager that connects to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database that contains the table to which the task writes.</span></span> <span data-ttu-id="cbedb-133">Para obter mais informações, consulte [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md) e [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="cbedb-133">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md) and [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
 <span data-ttu-id="cbedb-134">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="cbedb-134">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="cbedb-135">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="cbedb-135">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="cbedb-136">Editor da Tarefa Consulta de Mineração de Dados &#40;Guia Modelo de Mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="cbedb-136">Data Mining Query Task Editor &#40;Mining Model Tab&#41;</span></span>](../data-mining-query-task-editor-mining-model-tab.md)  
  
-   [<span data-ttu-id="cbedb-137">Editor da Tarefa Consulta de Mineração de Dados &#40;Guia Consulta&#41;</span><span class="sxs-lookup"><span data-stu-id="cbedb-137">Data Mining Query Task Editor &#40;Query Tab&#41;</span></span>](../data-mining-query-task-editor-query-tab.md)  
  
-   [<span data-ttu-id="cbedb-138">Editor da Tarefa Consulta de Mineração de Dados &#40;Guia Saída&#41;</span><span class="sxs-lookup"><span data-stu-id="cbedb-138">Data Mining Query Task Editor &#40;Output Tab&#41;</span></span>](../data-mining-query-task-editor-output-tab.md)  
  
> [!NOTE]  
>  <span data-ttu-id="cbedb-139">O Editor de Consultas de Mineração de Dados não tem nenhuma página Expressões.</span><span class="sxs-lookup"><span data-stu-id="cbedb-139">The Data Mining Query Editor has no Expressions page.</span></span> <span data-ttu-id="cbedb-140">Em vez disso, use a janela **Propriedades** para acessar as ferramentas de criação e gerenciamento de expressões de propriedade para as propriedades da tarefa Consulta de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="cbedb-140">Instead, use the **Properties** window to access the tools for creating and managing property expressions for properties of the Data Mining Query task.</span></span>  
  
 <span data-ttu-id="cbedb-141">Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="cbedb-141">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="cbedb-142">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="cbedb-142">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-data-mining-query-task"></a><span data-ttu-id="cbedb-143">Configuração programática da tarefa Consulta de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="cbedb-143">Programmatic Configuration of Data Mining Query Task</span></span>  
 <span data-ttu-id="cbedb-144">Para obter mais informações sobre como definir essas propriedades programaticamente, clique em um dos tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="cbedb-144">For more information about programmatically setting these properties, click one of the following topics:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.DMQueryTask.DMQueryTask>  
  
  