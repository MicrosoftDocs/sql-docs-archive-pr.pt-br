---
title: Adicionar dados a um relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f2e42303-e355-4c1f-bb3b-3338fbdd230d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6e7e7a8e50a4d87ab0aba5cc55f87bf08e236b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684558"
---
# <a name="add-data-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="72a2f-102">Adicionar dados a um relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="72a2f-102">Add Data to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="72a2f-103">Para adicionar dados a um relatório, você cria conjuntos de dados.</span><span class="sxs-lookup"><span data-stu-id="72a2f-103">To add data to a report, you create datasets.</span></span> <span data-ttu-id="72a2f-104">Cada conjunto de dados representa o conjunto de resultados gerado pela execução de um comando de consulta em uma fonte dados.</span><span class="sxs-lookup"><span data-stu-id="72a2f-104">Each dataset represents the result set from running a query command on a data source.</span></span> <span data-ttu-id="72a2f-105">As colunas do conjunto de resultados são a coleção de campos.</span><span class="sxs-lookup"><span data-stu-id="72a2f-105">The columns in the result set are the field collection.</span></span> <span data-ttu-id="72a2f-106">As linhas do conjunto de resultados são os dados.</span><span class="sxs-lookup"><span data-stu-id="72a2f-106">The rows in the result set are the data.</span></span> <span data-ttu-id="72a2f-107">O conjunto de resultados não contêm os dados reais.</span><span class="sxs-lookup"><span data-stu-id="72a2f-107">A dataset does not contain the actual data.</span></span> <span data-ttu-id="72a2f-108">Um conjunto de dados contém as informações necessárias para recuperar um conjunto específico de dados de uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="72a2f-108">A dataset contains the information that is needed to retrieve a specific set of data from a data source.</span></span>  
  
 <span data-ttu-id="72a2f-109">Há dois tipos de conjuntos de dados: inserido ou compartilhado.</span><span class="sxs-lookup"><span data-stu-id="72a2f-109">There are two types of datasets: embedded and shared.</span></span> <span data-ttu-id="72a2f-110">Um conjunto de dados inserido é definido em um relatório e usado apenas por esse relatório.</span><span class="sxs-lookup"><span data-stu-id="72a2f-110">An embedded dataset is defined in a report and used only by that report.</span></span> <span data-ttu-id="72a2f-111">Um conjunto de dados compartilhado é definido no servidor de relatório ou em um site do SharePoint e pode ser usado por vários relatórios.</span><span class="sxs-lookup"><span data-stu-id="72a2f-111">A shared dataset is defined on the report server or SharePoint site and can be used by multiple reports.</span></span> <span data-ttu-id="72a2f-112">No Construtor de Relatórios, você pode criar conjuntos de dados compartilhados no modo Conjunto de Dados Compartilhado ou conjuntos de dados inseridos no modo Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="72a2f-112">In Report Builder, you can create shared datasets in Shared Dataset mode or embedded datasets in Report Designer mode.</span></span> <span data-ttu-id="72a2f-113">No Designer de Relatórios do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], você pode criar conjuntos de dados compartilhados como parte de um projeto ou conjuntos de dados inseridos como parte de um relatório.</span><span class="sxs-lookup"><span data-stu-id="72a2f-113">In Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can create shared datasets as part of a project or embedded datasets as part of a report.</span></span>  
  
-   <span data-ttu-id="72a2f-114">**Conjuntos de dados inseridos.**</span><span class="sxs-lookup"><span data-stu-id="72a2f-114">**Embedded datasets.**</span></span> <span data-ttu-id="72a2f-115">Diferente de aplicativos como o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office Excel, em que você trabalha diretamente com dados em uma planilha, no Construtor de Relatórios ou no Designer de Relatórios, você trabalha com metadados que representam os dados a serem recuperados quando o relatório for processado.</span><span class="sxs-lookup"><span data-stu-id="72a2f-115">Unlike applications such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office Excel where you work with data directly in a worksheet, in Report Builder or Report Designer you work with metadata that represents the data that will be retrieved when the report is processed.</span></span> <span data-ttu-id="72a2f-116">Para criar um conjunto de dados inserido, selecione a fonte de dados e especifique uma consulta.</span><span class="sxs-lookup"><span data-stu-id="72a2f-116">To create an embedded dataset, select the source of data and specify a query.</span></span> <span data-ttu-id="72a2f-117">Depois que você criar um conjunto de dados, use o painel Dados do Relatório para exibir a coleção de campos.</span><span class="sxs-lookup"><span data-stu-id="72a2f-117">After you create the dataset, use the Report Data pane to view the field collection.</span></span> <span data-ttu-id="72a2f-118">Você pode exibir dados de um conjunto de dados em uma região de dados, como uma tabela ou gráfico.</span><span class="sxs-lookup"><span data-stu-id="72a2f-118">You can display data from a dataset in a data region like a table or chart.</span></span> <span data-ttu-id="72a2f-119">Em cada região de dados, é possível agrupar, filtrar e classificar os dados para organizá-los.</span><span class="sxs-lookup"><span data-stu-id="72a2f-119">In each data region, you can group, filter, and sort the data to organize it.</span></span> <span data-ttu-id="72a2f-120">Depois de criar o layout de relatório, execute o relatório para ver os dados reais.</span><span class="sxs-lookup"><span data-stu-id="72a2f-120">After you design the report layout, you run the report to see the actual data.</span></span>  
  
     <span data-ttu-id="72a2f-121">Na figura a seguir, o painel Dados do Relatório exibe uma fonte de dados denominada [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)], um conjunto de dados denominado DataSet1 e cinco campos da coleção de campos do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="72a2f-121">In the following figure, the Report Data pane displays a data source named [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)], a dataset named DataSet1, and five fields in the dataset field collection.</span></span> <span data-ttu-id="72a2f-122">O painel Layout mostra uma tabela com a linha superior de títulos de coluna e a linha inferior com células de tabela que contêm texto.</span><span class="sxs-lookup"><span data-stu-id="72a2f-122">The Layout pane shows a table with the top row of column headings and the bottom row with table cells that contain text.</span></span> <span data-ttu-id="72a2f-123">O texto do espaço reservado [Nome] contém metadados para o nome do campo.</span><span class="sxs-lookup"><span data-stu-id="72a2f-123">The placeholder text [Name] is the metadata for the field Name.</span></span> <span data-ttu-id="72a2f-124">Quando o relatório é executado, o texto do espaço reservado é substituído pelos valores de dados reais.</span><span class="sxs-lookup"><span data-stu-id="72a2f-124">When the report runs, the placeholder text is replaced by the actual data values.</span></span> <span data-ttu-id="72a2f-125">A tabela é expandida conforme necessário para exibir todos os dados.</span><span class="sxs-lookup"><span data-stu-id="72a2f-125">The table expands as required to display all the data.</span></span>  
  
     <span data-ttu-id="72a2f-126">![rs_DataDesignandPreview](../media/rs-datadesignandpreview.gif "rs_DataDesignandPreview")</span><span class="sxs-lookup"><span data-stu-id="72a2f-126">![rs_DataDesignandPreview](../media/rs-datadesignandpreview.gif "rs_DataDesignandPreview")</span></span>  
  
-   <span data-ttu-id="72a2f-127">**Conjuntos de dados compartilhados.**</span><span class="sxs-lookup"><span data-stu-id="72a2f-127">**Shared datasets.**</span></span> <span data-ttu-id="72a2f-128">Crie um conjunto de dados compartilhado quando desejar usar um conjunto de dados em mais de um relatório.</span><span class="sxs-lookup"><span data-stu-id="72a2f-128">Create a shared dataset when you want to use a dataset in more than one report.</span></span> <span data-ttu-id="72a2f-129">Para criar e salvar um conjunto de dados em um servidor de relatório ou em um site do SharePoint, use o Construtor de Relatórios na exibição de design do conjunto de dados compartilhado.</span><span class="sxs-lookup"><span data-stu-id="72a2f-129">To create and save a shared dataset to a report server or SharePoint site, use Report Builder in shared dataset design view.</span></span> <span data-ttu-id="72a2f-130">Para criar um conjunto de dados compartilhado como parte de um projeto que pode ser implantado em um servidor ou site, use o Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="72a2f-130">To create a shared dataset as part of a project that can be deployed to a server or site, use Report Designer.</span></span>  
  
     <span data-ttu-id="72a2f-131">A ilustração a seguir mostra a exibição de Design do Conjunto de Dados Compartilhado no Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="72a2f-131">The following illustration shows Shared Dataset Design view in Report Builder.</span></span> <span data-ttu-id="72a2f-132">Você pode selecionar ou modificar a conexão de dados, as propriedades de conjunto de dados, a consulta e os filtros e, se desejar, você pode marcar os filtros como parâmetros e exibir os resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="72a2f-132">You can select or modify the data connection, the dataset properties, the query, filters, and optionally mark filters as parameters, and view the query results.</span></span> <span data-ttu-id="72a2f-133">Em seguida, salve as alterações no servidor ou no site.</span><span class="sxs-lookup"><span data-stu-id="72a2f-133">You then save the changes back to the server or site.</span></span>  
  
     <span data-ttu-id="72a2f-134">![rs_SharedDatasetDesignMode](../media/rs-shareddatasetdesignmode.gif "rs_SharedDatasetDesignMode")</span><span class="sxs-lookup"><span data-stu-id="72a2f-134">![rs_SharedDatasetDesignMode](../media/rs-shareddatasetdesignmode.gif "rs_SharedDatasetDesignMode")</span></span>  
  
 <span data-ttu-id="72a2f-135">Para obter mais informações, consulte [Conjuntos de dados inseridos e compartilhados &#40;Construtor de Relatórios e SSRS&#41;](embedded-and-shared-datasets-report-builder-and-ssrs.md) e [Conexões de dados ou fontes de dados inseridas e compartilhadas &#40;Construtor de Relatórios e SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="72a2f-135">For more information, see [Embedded and Shared Datasets &#40;Report Builder and SSRS&#41;](embedded-and-shared-datasets-report-builder-and-ssrs.md) and [Embedded and Shared Data Connections or Data Sources &#40;Report Builder and SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="72a2f-136">Você também pode adicionar conjuntos de dados a um relatório adicionando partes de relatório que incluem os conjuntos de dados dos quais elas dependem.</span><span class="sxs-lookup"><span data-stu-id="72a2f-136">You can also add datasets to a report by adding report parts that include the datasets they depend on.</span></span> [!INCLUDE[ssRBrptparts](../../../includes/ssrbrptparts-md.md)]  
  
 <span data-ttu-id="72a2f-137">Para saber como criar um relatório que exibe dados de um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [Tutorial: Criando um relatório de tabela básico &#40;Construtor de Relatórios&#41;](../tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="72a2f-137">To learn how to create a report that displays data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, see [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../tutorial-creating-a-basic-table-report-report-builder.md).</span></span> <span data-ttu-id="72a2f-138">Para criar um relatório que inclui seus próprios dados, consulte [Tutorial: Criar um gráfico de relatório rápido offline &#40;Construtor de Relatórios&#41;](../report-builder/tutorial-create-a-quick-chart-report-offline-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="72a2f-138">To build a report that includes its own data, see [Tutorial: Create a Quick Chart Report Offline &#40;Report Builder&#41;](../report-builder/tutorial-create-a-quick-chart-report-offline-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="adding-report-data"></a><a name="Methods"></a> <span data-ttu-id="72a2f-139">Adicionando dados de relatório</span><span class="sxs-lookup"><span data-stu-id="72a2f-139">Adding Report Data</span></span>  
 <span data-ttu-id="72a2f-140">No Construtor de Relatórios, você pode adicionar dados de relatório das seguintes maneiras.</span><span class="sxs-lookup"><span data-stu-id="72a2f-140">In Report Builder, you can add report data in the following ways.</span></span>  
  
-   <span data-ttu-id="72a2f-141">Adicione partes de relatório de um servidor de relatório ao seu relatório.</span><span class="sxs-lookup"><span data-stu-id="72a2f-141">Add report parts from a report server to your report.</span></span> <span data-ttu-id="72a2f-142">Cada parte de relatório é autossuficiente e inclui conjuntos de dados dependentes.</span><span class="sxs-lookup"><span data-stu-id="72a2f-142">Each report part is self-contained and includes dependent datasets.</span></span> <span data-ttu-id="72a2f-143">Os conjuntos de dados são predefinidos.</span><span class="sxs-lookup"><span data-stu-id="72a2f-143">The datasets are predefined.</span></span>  
  
-   <span data-ttu-id="72a2f-144">Use os assistentes de Tabela/Matriz, Gráfico e Mapa.</span><span class="sxs-lookup"><span data-stu-id="72a2f-144">Use the Table/Matrix, Chart, and Map wizards.</span></span> <span data-ttu-id="72a2f-145">Com os assistentes, é possível selecionar fontes de dados compartilhadas e conjuntos de dados compartilhados, ou criar novos conjuntos de dados, e continuar criando o relatório.</span><span class="sxs-lookup"><span data-stu-id="72a2f-145">From the wizards, you can select shared data sources and shared datasets, or create new datasets, and continue to design the report.</span></span>  
  
-   <span data-ttu-id="72a2f-146">Adicione conjuntos de dados compartilhados de um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="72a2f-146">Add shared datasets from a report server.</span></span> <span data-ttu-id="72a2f-147">Os conjuntos de dados compartilhados são predefinidos e especificam quais dados devem ser usados de uma fonte de dados predefinida.</span><span class="sxs-lookup"><span data-stu-id="72a2f-147">Shared datasets are predefined and specify which data to use from a predefined data source.</span></span> <span data-ttu-id="72a2f-148">Ao adicionar um conjunto de dados compartilhado ao relatório, você adiciona uma referência de conjunto de dados que aponta para a definição do conjunto de dados compartilhado.</span><span class="sxs-lookup"><span data-stu-id="72a2f-148">When you add a shared dataset to your report, you add a dataset reference that points to the shared dataset definition.</span></span>  
  
 <span data-ttu-id="72a2f-149">No Construtor de Relatórios ou Designer de Relatórios, você pode adicionar dados das seguintes maneiras.</span><span class="sxs-lookup"><span data-stu-id="72a2f-149">In Report Builder or Report Designer, you can add data in the following ways.</span></span>  
  
-   <span data-ttu-id="72a2f-150">Adicione conjuntos de dados inseridos com base nas fontes de dados compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="72a2f-150">Add embedded datasets based on shared data sources.</span></span>  
  
-   <span data-ttu-id="72a2f-151">Adicione conjuntos de dados inseridos com base nas fontes de dados inseridas.</span><span class="sxs-lookup"><span data-stu-id="72a2f-151">Add embedded datasets based on embedded data sources.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72a2f-152">Em um servidor de relatório, os itens compartilhados são protegidos individualmente ou herdando permissões da pasta onde eles são publicados.</span><span class="sxs-lookup"><span data-stu-id="72a2f-152">On a report server, shared items are secured individually or by inheriting permissions from the folder where they are published.</span></span> <span data-ttu-id="72a2f-153">Para permitir que outros usuários acessem os conjuntos de dados compartilhados que você salva, é necessário entender como as permissões são concedidas.</span><span class="sxs-lookup"><span data-stu-id="72a2f-153">To enable other users to have access to shared datasets that you save, you must understand how permissions are granted.</span></span> <span data-ttu-id="72a2f-154">Para obter mais informações, consulte [Segurança &#40;Construtor de Relatórios&#41;](../report-builder/security-report-builder.md) ou [Proteger itens de conjuntos de dados compartilhados](../security/secure-shared-dataset-items.md).</span><span class="sxs-lookup"><span data-stu-id="72a2f-154">For more information, see [Security &#40;Report Builder&#41;](../report-builder/security-report-builder.md) or [Secure Shared Dataset Items](../security/secure-shared-dataset-items.md).</span></span>  
  
 <span data-ttu-id="72a2f-155">Depois de adicionar dados a um relatório, você pode organizar os dados na página de relatório com regiões de dados, modificar partes de relatório e compartilhar essas alterações com outros, além de permitir que os usuários limitem ou classifiquem os dados no relatório.</span><span class="sxs-lookup"><span data-stu-id="72a2f-155">After you add data to a report, you can organize the data on the report page with data regions, modify report parts and share those changes with others, and enable users to limit or sort the data they see in the report.</span></span> <span data-ttu-id="72a2f-156">Para obter mais informações, consulte os seguintes tópicos relacionados:</span><span class="sxs-lookup"><span data-stu-id="72a2f-156">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="72a2f-157">Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-157">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="72a2f-158">Gráficos &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-158">Charts &#40;Report Builder and SSRS&#41;</span></span>](../report-design/charts-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="72a2f-159">Minigráficos e barras de dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-159">Sparklines and Data Bars &#40;Report Builder and SSRS&#41;</span></span>](../report-design/sparklines-and-data-bars-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="72a2f-160">Indicadores &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-160">Indicators &#40;Report Builder and SSRS&#41;</span></span>](../report-design/indicators-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="72a2f-161">Parâmetros de relatório &#40;Construtor de Relatórios e Designer de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-161">Report Parameters &#40;Report Builder and Report Designer&#41;</span></span>](../report-design/report-parameters-report-builder-and-report-designer.md)  
  
-   [<span data-ttu-id="72a2f-162">Partes de relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-162">Report Parts &#40;Report Builder and SSRS&#41;</span></span>](../report-parts-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="72a2f-163">Filtrar, agrupar e classificar dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-163">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)  

##  <a name="adding-data-with-report-parts"></a><a name="QuickStart"></a> <span data-ttu-id="72a2f-164">Adicionando dados com partes de relatório</span><span class="sxs-lookup"><span data-stu-id="72a2f-164">Adding Data with Report Parts</span></span>  
 <span data-ttu-id="72a2f-165">As partes de relatório contêm os conjuntos de dados dos quais elas dependem.</span><span class="sxs-lookup"><span data-stu-id="72a2f-165">Report parts contain the datasets that they depend on.</span></span> <span data-ttu-id="72a2f-166">Esses conjuntos de dados são criados em fontes de dados compartilhadas que estão disponíveis no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="72a2f-166">These datasets are built on shared data sources that are available on the report server.</span></span> <span data-ttu-id="72a2f-167">No Construtor de Relatórios, quando você adiciona uma parte de relatório ao relatório, os conjuntos de dados dependentes são adicionados ao relatório, como se você os tivesse adicionado manualmente.</span><span class="sxs-lookup"><span data-stu-id="72a2f-167">In Report Builder, when you add a report part to your report, the dependent datasets are added to your report, just as if you had added them manually.</span></span> <span data-ttu-id="72a2f-168">Por exemplo, um gráfico predefinido contém um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="72a2f-168">For example, a predefined chart contains a dataset.</span></span> <span data-ttu-id="72a2f-169">Para ver os dados, visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="72a2f-169">To see the data, preview the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBrptparts](../../../includes/ssrbrptparts-md.md)]  
  
 <span data-ttu-id="72a2f-170">Partes de relatório, fontes de dados compartilhadas e conjuntos de dados compartilhados são definidos antecipadamente e salvos em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="72a2f-170">Report parts, shared data sources, and shared datasets are defined in advance and saved on a report server.</span></span> <span data-ttu-id="72a2f-171">Para acessá-los, você precisa abrir o Construtor de Relatórios no modo de servidor conectando-se ao servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="72a2f-171">To access them, you must open Report Builder in server mode by connecting to the report server.</span></span> <span data-ttu-id="72a2f-172">Você pode usá-los para criar suas próprias versões se tiver permissões de gravação no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="72a2f-172">You can use these to create new versions of your own if you have write permissions to the report server.</span></span>  
  
-   <span data-ttu-id="72a2f-173">Para obter mais informações, consulte [Partes de relatório &#40;Construtor de Relatórios e SSRS&#41;](../report-parts-report-builder-and-ssrs.md) e [Partes de relatório no Designer de Relatórios &#40;SSRS&#41;](../report-design/report-parts-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="72a2f-173">For more information, see [Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md) and [Report Parts in Report Designer &#40;SSRS&#41;](../report-design/report-parts-in-report-designer-ssrs.md).</span></span>  

##  <a name="queries-and-query-designers"></a><a name="Queries"></a> <span data-ttu-id="72a2f-174">Consultas e designers de consulta</span><span class="sxs-lookup"><span data-stu-id="72a2f-174">Queries and Query Designers</span></span>  
 <span data-ttu-id="72a2f-175">Para especificar quais dados deseja em uma fonte de dados, crie um comando de consulta.</span><span class="sxs-lookup"><span data-stu-id="72a2f-175">To specify which data you want from a data source, you build a query command.</span></span> <span data-ttu-id="72a2f-176">Cada tipo de fonte de dados fornece um *designer de consulta* relacionado para ajudar você a criar a consulta.</span><span class="sxs-lookup"><span data-stu-id="72a2f-176">Each data source type provides a related *query designer* to help you build the query.</span></span> <span data-ttu-id="72a2f-177">O designer de consulta pode ser gráfico ou baseado em texto.</span><span class="sxs-lookup"><span data-stu-id="72a2f-177">The query designer can be graphical or text-based.</span></span> <span data-ttu-id="72a2f-178">Em um designer de consulta gráfica, você exibe metadados que representam os dados na fonte de dados externa e criam interativamente uma consulta arrastando campos ou entidades para a superfície de design de consulta.</span><span class="sxs-lookup"><span data-stu-id="72a2f-178">In a graphical query designer, you view metadata that represents the data on the external data source and interactively build a query by dragging fields or entities to the query design surface.</span></span> <span data-ttu-id="72a2f-179">Em um designer de consulta baseado em texto, você escreve ou importa consultas na sintaxe de consulta que tem suporte da fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="72a2f-179">In a text-based query designer, you write or import queries in the query syntax that is supported by the external data source.</span></span>  
  
 <span data-ttu-id="72a2f-180">No designer de consulta, você pode executar a consulta para exibir dados de exemplo e validar a sintaxe do comando de consulta.</span><span class="sxs-lookup"><span data-stu-id="72a2f-180">In the query designer, you can run the query to view example data and validate the query command syntax.</span></span> <span data-ttu-id="72a2f-181">Os nomes de coluna no conjunto de resultados tornam-se os nomes de campo que você vê no painel Dados do Relatório.</span><span class="sxs-lookup"><span data-stu-id="72a2f-181">Column names in the result set become the field names that you see in the Report Data pane.</span></span> <span data-ttu-id="72a2f-182">O conjunto de resultados deve ser um único conjunto de linhas e colunas em que o mesmo número de valores existe para cada linha de dados.</span><span class="sxs-lookup"><span data-stu-id="72a2f-182">The result set must be a single set of rows and columns where the same number of values exist for each row of data.</span></span> <span data-ttu-id="72a2f-183">Não há suporte para vários conjuntos de resultados a partir de uma única consulta.</span><span class="sxs-lookup"><span data-stu-id="72a2f-183">Multiple results sets from a single query are not supported.</span></span> <span data-ttu-id="72a2f-184">Não há suporte para hierarquias imperfeitas, que não têm um número constante de colunas e podem gerar um número diferente de valores de dados para cada linha.</span><span class="sxs-lookup"><span data-stu-id="72a2f-184">Ragged hierarchies, which do not have a constant number of columns and can produce different number of data values for each row, are not supported.</span></span>  
  
 <span data-ttu-id="72a2f-185">Para executar uma consulta, é necessário ter credenciais de tempo de design.</span><span class="sxs-lookup"><span data-stu-id="72a2f-185">To run a query, you must have design time credentials.</span></span> <span data-ttu-id="72a2f-186">Para obter mais informações, consulte [especificar credenciais em Construtor de relatórios](../specify-credentials-in-report-builder.md) e [conexões de dados, fontes de dados e cadeias de conexão no Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="72a2f-186">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md) and [Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span></span>  
  
 <span data-ttu-id="72a2f-187">A comunicação entre uma extensão de dados e a fonte de dados externa é gerenciada pelos provedores de dados.</span><span class="sxs-lookup"><span data-stu-id="72a2f-187">Communication between a data extension and the external data source is handled by data providers.</span></span> <span data-ttu-id="72a2f-188">O suporte para sintaxe do comando de consulta, parâmetros de consulta e tipos de dados para obter valores no conjunto de resultados é determinado por cada provedor de dados.</span><span class="sxs-lookup"><span data-stu-id="72a2f-188">Support for query command syntax, query parameters, and data types for values in the result set is determined by each data provider.</span></span> <span data-ttu-id="72a2f-189">Para obter mais informações, consulte o tópico para o tipo específico de extensão de dados e [Designers de Consulta &#40;Construtor de Relatórios&#41;](../query-designers-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="72a2f-189">For more information, see the topic for the specific type of data extension and [Query Designers &#40;Report Builder&#41;](../query-designers-report-builder.md).</span></span>  

##  <a name="how-to-topics"></a><a name="HowTo"></a> <span data-ttu-id="72a2f-190">Tópicos de instruções</span><span class="sxs-lookup"><span data-stu-id="72a2f-190">How-To Topics</span></span>  
 [<span data-ttu-id="72a2f-191">Adicionar e verificar uma conexão de dados ou uma fonte de dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-191">Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;</span></span>](add-and-verify-a-data-connection-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="72a2f-192">Criar um conjunto de dados compartilhado ou um conjunto de dados inserido &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-192">Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;</span></span>](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="72a2f-193">Adicionar, editar e atualizar campos no painel de dados do relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-193">Add, Edit, Refresh Fields in the Report Data Pane &#40;Report Builder and SSRS&#41;</span></span>](add-edit-refresh-fields-in-the-report-data-pane-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="72a2f-194">Compilar uma consulta no designer de consulta relacional &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-194">Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;</span></span>](build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="72a2f-195">Mostrar conjuntos de dados ocultos para obter valores de parâmetros para dados multidimensionais &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-195">Show Hidden Datasets for Parameter Values for Multidimensional Data &#40;Report Builder and SSRS&#41;</span></span>](show-hidden-datasets-for-parameter-values-multidimensional-data.md)  
  
 [<span data-ttu-id="72a2f-196">Adicionar um filtro a um conjunto de dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-196">Add a Filter to a Dataset &#40;Report Builder and SSRS&#41;</span></span>](add-a-filter-to-a-dataset-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="72a2f-197">Definir uma mensagem Nenhum Dado para uma região de dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-197">Set a No Data Message for a Data Region &#40;Report Builder and SSRS&#41;</span></span>](set-a-no-data-message-for-a-data-region-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="72a2f-198">Associar um parâmetro de consulta a um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-198">Associate a Query Parameter with a Report Parameter &#40;Report Builder and SSRS&#41;</span></span>](associate-a-query-parameter-with-a-report-parameter-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="72a2f-199">Definir parâmetros no Designer de Consulta MDX do Analysis Services &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-199">Define Parameters in the MDX Query Designer for Analysis Services &#40;Report Builder and SSRS&#41;</span></span>](define-parameters-in-the-mdx-query-designer-for-analysis-services.md)  

##  <a name="in-this-section"></a><a name="Section"></a> <span data-ttu-id="72a2f-200">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="72a2f-200">In This Section</span></span>  
 [<span data-ttu-id="72a2f-201">Partes de relatório e conjuntos de dados no Construtor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="72a2f-201">Report Parts and Datasets in Report Builder</span></span>](report-parts-and-datasets-in-report-builder.md)  
  
 [<span data-ttu-id="72a2f-202">Conexões de dados, fontes de dados e cadeias de conexão no Construtor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="72a2f-202">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../data-connections-data-sources-and-connection-strings-in-report-builder.md)  
  
 [<span data-ttu-id="72a2f-203">Especificar as credenciais no Construtor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="72a2f-203">Specify Credentials in Report Builder</span></span>](../specify-credentials-in-report-builder.md)  
  
 [<span data-ttu-id="72a2f-204">Conjuntos de dados inseridos e compartilhados de relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-204">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="72a2f-205">Coleção de campos de conjuntos de dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-205">Dataset Fields Collection &#40;Report Builder and SSRS&#41;</span></span>](dataset-fields-collection-report-builder-and-ssrs.md)  

## <a name="see-also"></a><span data-ttu-id="72a2f-206">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="72a2f-206">See Also</span></span>  
 <span data-ttu-id="72a2f-207">[Modo de exibição de Design de relatório &#40;Construtor de Relatórios&#41;](../report-builder/report-design-view-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="72a2f-207">[Report Design View &#40;Report Builder&#41;](../report-builder/report-design-view-report-builder.md) </span></span>  
 [<span data-ttu-id="72a2f-208">Conceitos de criação de relatórios &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72a2f-208">Report Authoring Concepts &#40;Report Builder and SSRS&#41;</span></span>](../report-design/report-authoring-concepts-report-builder-and-ssrs.md)  