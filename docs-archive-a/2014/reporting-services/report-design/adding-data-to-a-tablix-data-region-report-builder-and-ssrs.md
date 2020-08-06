---
title: Adicionando dados a uma região de dados Tablix (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8f1d0a76-afed-480f-98fb-89e2d4eb09b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 35f2b02c45fa384b30ef9b9051f2333c3a9b76df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681441"
---
# <a name="adding-data-to-a-tablix-data-region-report-builder-and-ssrs"></a><span data-ttu-id="4d8be-102">Adicionando dados a uma região de dados Tablix (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="4d8be-102">Adding Data to a Tablix Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4d8be-103">Para exibir dados de um conjunto de dados de relatório em uma tabela ou matriz, em cada célula de dados, especifique o nome de um campo do conjunto de dados a ser exibido.</span><span class="sxs-lookup"><span data-stu-id="4d8be-103">To display data from a report dataset in a table or matrix, in each data cell, specify the name of a dataset field to display.</span></span> <span data-ttu-id="4d8be-104">É possível exibir dados de detalhes ou dados agrupados.</span><span class="sxs-lookup"><span data-stu-id="4d8be-104">You can display detail data or grouped data.</span></span> <span data-ttu-id="4d8be-105">Se você adicionar grupos a uma tabela ou matriz, linhas e colunas para valores de grupo e dados de grupo serão adicionados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4d8be-105">If you add groups to a table or matrix, rows and columns for group values and group data are added automatically.</span></span> <span data-ttu-id="4d8be-106">Em seguida, é possível adicionar subtotais e totais aos dados.</span><span class="sxs-lookup"><span data-stu-id="4d8be-106">You can then add subtotals and totals for your data.</span></span>  
  
 <span data-ttu-id="4d8be-107">Todos os dados em uma região de dados pertencem a pelo menos um grupo.</span><span class="sxs-lookup"><span data-stu-id="4d8be-107">All data in a data region belongs to at least one group.</span></span> <span data-ttu-id="4d8be-108">Dados de detalhes são membros do grupo de detalhes.</span><span class="sxs-lookup"><span data-stu-id="4d8be-108">Detail data is a member of the details group.</span></span> <span data-ttu-id="4d8be-109">Para obter mais informações sobre dados agrupados e detalhes, consulte [Noções básicas sobre grupos &#40;Construtor de Relatórios e SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4d8be-109">For more information about detail and grouped data, see [Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="adding-detail-data"></a><span data-ttu-id="4d8be-110">Adicionando dados de detalhes</span><span class="sxs-lookup"><span data-stu-id="4d8be-110">Adding Detail Data</span></span>  
 <span data-ttu-id="4d8be-111">Dados de detalhes são todos os dados de um conjunto de dados de relatório depois da aplicação de filtros ao conjunto de dados, região de dados e grupo de detalhes.</span><span class="sxs-lookup"><span data-stu-id="4d8be-111">Detail data is all the data from a report dataset after filters are applied to the dataset, data region, and details group.</span></span> <span data-ttu-id="4d8be-112">Todos os dados de detalhes exibidos em uma única região de dados tablix devem vir do mesmo conjunto de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="4d8be-112">All detail data displayed in a single tablix data region must come from the same report dataset.</span></span>  
  
 <span data-ttu-id="4d8be-113">Para adicionar dados de detalhes de um conjunto de dados de relatório a uma região de dados tablix, arraste um campo do conjunto de dados do painel de dados do relatório para cada célula na linha de detalhes.</span><span class="sxs-lookup"><span data-stu-id="4d8be-113">To add detail data from a report dataset to a tablix data region, drag a dataset field from the Report Data pane to each cell in the detail row.</span></span> <span data-ttu-id="4d8be-114">Para células existentes em uma região de dados tablix, é possível adicionar ou editar uma expressão de conjunto de dados usando o seletor de campo em cada célula ou arrastando um campo do painel de dados do relatório para a célula.</span><span class="sxs-lookup"><span data-stu-id="4d8be-114">For existing cells in a tablix data region, you can add or edit a dataset field expression by using the field selector in each cell or by dragging a field from the Report Data pane to the cell.</span></span> <span data-ttu-id="4d8be-115">Para criar colunas adicionais, você pode arrastar o campo do painel de dados do relatório e inseri-lo em uma região de dados tablix existente.</span><span class="sxs-lookup"><span data-stu-id="4d8be-115">To create additional columns, you can drag the field from the Report Data pane and insert it into an existing tablix data region.</span></span>  
  
 <span data-ttu-id="4d8be-116">Por padrão, em tempo de execução, uma célula na linha de detalhes exibe dados de detalhes e uma célula em uma linha de grupo exibe um valor de agregação.</span><span class="sxs-lookup"><span data-stu-id="4d8be-116">By default, at run-time, a cell in the details row displays detail data and a cell in a group row displays an aggregate value.</span></span> <span data-ttu-id="4d8be-117">Para obter mais informações sobre as linhas e colunas Tablix, consulte [Células, linhas e colunas da região de dados Tablix &#40;Construtor de Relatórios&#41; e SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4d8be-117">For more information about tablix rows and columns, see [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="4d8be-118">Um modelo de tabela e um modelo de lista fornecem uma linha de detalhes.</span><span class="sxs-lookup"><span data-stu-id="4d8be-118">A table template and a list template provide a details row.</span></span> <span data-ttu-id="4d8be-119">Um modelo de matriz não tem nenhuma linha de detalhes.</span><span class="sxs-lookup"><span data-stu-id="4d8be-119">A matrix template has no details row.</span></span> <span data-ttu-id="4d8be-120">Se sua região de dados tablix não tiver nenhuma linha de detalhes, você poderá adicionar uma linha definindo um grupo de detalhes.</span><span class="sxs-lookup"><span data-stu-id="4d8be-120">If your tablix data region has no details row, you can add one by defining a details group.</span></span> <span data-ttu-id="4d8be-121">Para obter mais informações, consulte [Adicionar um grupo de detalhes &#40;Construtor de Relatórios e SSRS&#41;](add-a-details-group-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4d8be-121">For more information, see [Add a Details Group &#40;Report Builder and SSRS&#41;](add-a-details-group-report-builder-and-ssrs.md).</span></span>  
  
## <a name="adding-grouped-data"></a><span data-ttu-id="4d8be-122">Adicionando dados agrupados</span><span class="sxs-lookup"><span data-stu-id="4d8be-122">Adding Grouped Data</span></span>  
 <span data-ttu-id="4d8be-123">Dados agrupados são todos os dados de detalhes especificados por uma expressão de grupo depois da aplicação de filtros ao conjunto de dados, região de dados e o grupo.</span><span class="sxs-lookup"><span data-stu-id="4d8be-123">Grouped data is all the detail data specified by a group expression after filters are applied to the dataset, data region, and the group.</span></span> <span data-ttu-id="4d8be-124">Para organizar dados de detalhes em grupos, arraste campos do painel de dados do relatório para o painel Agrupamento.</span><span class="sxs-lookup"><span data-stu-id="4d8be-124">To organize detail data in groups, drag fields from the Report Data pane to the Grouping pane.</span></span> <span data-ttu-id="4d8be-125">Quando você adiciona um grupo, o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] adiciona automaticamente linhas ou colunas relacionadas à região de dados tablix na qual exibir dados agrupados.</span><span class="sxs-lookup"><span data-stu-id="4d8be-125">When you add a group, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] automatically adds related rows or columns to the tablix data region on which to display grouped data.</span></span> <span data-ttu-id="4d8be-126">As células dessas linhas ou colunas são associadas aos dados agrupados.</span><span class="sxs-lookup"><span data-stu-id="4d8be-126">Cells in these rows or columns are associated with grouped data.</span></span> <span data-ttu-id="4d8be-127">Para obter mais informações, consulte [Adicionar ou excluir um grupo em uma região de dados &#40;Construtor de Relatórios e SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4d8be-127">For more information, see [Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="4d8be-128">Por padrão, quando você adiciona um campo de conjunto de dados que representa dados numéricos a uma célula em uma linha ou coluna do grupo, o valor da célula é a soma dos dados agrupados com o escopo das associações do grupo de linhas e colunas da célula.</span><span class="sxs-lookup"><span data-stu-id="4d8be-128">By default, when you add a dataset field that represents numeric data to a cell in a group row or column, the value of the cell is the sum of the grouped data scoped to the innermost row and column group memberships for the cell.</span></span> <span data-ttu-id="4d8be-129">É possível alterar a função de agregação padrão Sum para qualquer outra função de agregação, como Avg ou Count.</span><span class="sxs-lookup"><span data-stu-id="4d8be-129">You can change the default aggregate function Sum to any other aggregate function, such as Avg or Count.</span></span> <span data-ttu-id="4d8be-130">Também é possível alterar o escopo padrão para um cálculo de agregação, por exemplo, para calcular a porcentagem de contribuição de um valor para um grupo de linhas.</span><span class="sxs-lookup"><span data-stu-id="4d8be-130">You can also change the default scope for an aggregate calculation, for example, to calculate the percentage a value contributes to a row group.</span></span> <span data-ttu-id="4d8be-131">Para obter mais informações, consulte [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="4d8be-131">For more information, see [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="4d8be-132">Por padrão, todos os dados agrupados vêm do mesmo conjunto de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="4d8be-132">By default, all grouped data comes from the same report dataset.</span></span> <span data-ttu-id="4d8be-133">Em uma região de dados tablix, é possível incluir valores de agregação de outro conjunto de dados especificando o nome do conjunto de dados como um escopo.</span><span class="sxs-lookup"><span data-stu-id="4d8be-133">In a tablix data region, you can include aggregate values from another dataset by specifying the dataset name as a scope.</span></span> <span data-ttu-id="4d8be-134">É possível especificar vários valores de agregação de vários conjuntos de dados dentro de uma única região de dados tablix.</span><span class="sxs-lookup"><span data-stu-id="4d8be-134">You can specify multiple aggregate values from multiple datasets within a single tablix data region.</span></span> <span data-ttu-id="4d8be-135">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span><span class="sxs-lookup"><span data-stu-id="4d8be-135">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span></span>  
  
## <a name="adding-subtotals-and-totals"></a><span data-ttu-id="4d8be-136">Adicionando subtotais e totais</span><span class="sxs-lookup"><span data-stu-id="4d8be-136">Adding Subtotals and Totals</span></span>  
 <span data-ttu-id="4d8be-137">Para adicionar subtotais a um grupo e totais gerais à região de dados, use o recurso Adicionar Total no menu de atalho em uma célula ou no painel Agrupamento.</span><span class="sxs-lookup"><span data-stu-id="4d8be-137">To add subtotals for a group and grand totals for the data region, use the Add Total feature on the shortcut menu in a cell or in the Grouping pane.</span></span> <span data-ttu-id="4d8be-138">As linhas e colunas nas quais exibir os totais são automaticamente adicionadas para você.</span><span class="sxs-lookup"><span data-stu-id="4d8be-138">The rows and columns on which to display the totals are automatically added for you.</span></span> <span data-ttu-id="4d8be-139">Expressões de subtotais e totais são padronizadas usando a função de agregação [Sum](report-builder-functions-sum-function.md) .</span><span class="sxs-lookup"><span data-stu-id="4d8be-139">Subtotal and total expressions default to using the [Sum](report-builder-functions-sum-function.md) aggregate function.</span></span> <span data-ttu-id="4d8be-140">Depois de adicionar a expressão, é possível alterar a função padrão.</span><span class="sxs-lookup"><span data-stu-id="4d8be-140">After you add the expression, you can change the default function.</span></span> <span data-ttu-id="4d8be-141">Para obter mais informações, consulte [Adicionar um total a um grupo ou a uma região de dados Tablix &#40;Construtor de Relatórios e SSRS&#41;](add-a-total-to-a-group-or-tablix-data-region-report-builder-and-ssrs.md) e [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="4d8be-141">For more information, see [Add a Total to a Group or Tablix Data Region &#40;Report Builder and SSRS&#41;](add-a-total-to-a-group-or-tablix-data-region-report-builder-and-ssrs.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="adding-labels"></a><span data-ttu-id="4d8be-142">Adicionando rótulos</span><span class="sxs-lookup"><span data-stu-id="4d8be-142">Adding Labels</span></span>  
 <span data-ttu-id="4d8be-143">Para adicionar rótulos para um grupo ou para a região de dados, adicione uma linha ou coluna fora do grupo a ser rotulado.</span><span class="sxs-lookup"><span data-stu-id="4d8be-143">To add labels for a group or for the data region, add a row or column outside the group that you want to label.</span></span> <span data-ttu-id="4d8be-144">Linhas e colunas de rótulo são semelhantes a linhas e colunas adicionadas para exibir totais.</span><span class="sxs-lookup"><span data-stu-id="4d8be-144">Label rows and columns are similar to rows and columns that you add to display totals.</span></span> <span data-ttu-id="4d8be-145">Para obter mais informações, consulte [Inserir ou excluir uma linha &#40;Construtor de Relatórios e SSRS&#41;](insert-or-delete-a-row-report-builder-and-ssrs.md) ou [Inserir ou excluir uma coluna &#40;Construtor de Relatórios e SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4d8be-145">For more information, see [Insert or Delete a Row &#40;Report Builder and SSRS&#41;](insert-or-delete-a-row-report-builder-and-ssrs.md) or [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
## <a name="adding-an-existing-tablix-data-region-from-another-report"></a><span data-ttu-id="4d8be-146">Adicionando uma região de dados Tablix existente de outro relatório</span><span class="sxs-lookup"><span data-stu-id="4d8be-146">Adding an Existing Tablix Data Region from Another Report</span></span>  
 <span data-ttu-id="4d8be-147">É possível copiar uma região de dados de outro relatório e colá-la em um relatório novo ou existente.</span><span class="sxs-lookup"><span data-stu-id="4d8be-147">You can copy a data region from another report and paste it into-a new or existing report.</span></span> <span data-ttu-id="4d8be-148">Depois que colar a região de dados, você deve assegurar que o banco de dados usado pela região de dados seja definido e que os campos do conjunto de dados tenham nomes e tipos de dados idênticos aos do relatório original.</span><span class="sxs-lookup"><span data-stu-id="4d8be-148">After you paste the data region, you must ensure that the dataset the data region uses is defined, and that the dataset fields have identical names and data types as in the original report.</span></span> <span data-ttu-id="4d8be-149">Você não pode copiar conjuntos de dados de um relatório para outro, mas se seus relatórios usarem fontes de dados compartilhadas, você poderá duplicar o conjunto de dados rapidamente no outro relatório.</span><span class="sxs-lookup"><span data-stu-id="4d8be-149">You cannot copy datasets from one report to another, but if your reports use shared data sources, you can quickly duplicate the dataset in the another report.</span></span> <span data-ttu-id="4d8be-150">Além disso, é possível importar o texto da consulta para as consultas que recuperam os dados do conjunto de dados, o que simplifica a duplicação de consultas nos relatórios.</span><span class="sxs-lookup"><span data-stu-id="4d8be-150">Also you can import the query text for the queries that retrieve the data for the dataset, which makes it simple to duplicate the queries in reports.</span></span> <span data-ttu-id="4d8be-151">Para obter mais informações, consulte [Conjuntos de dados inseridos e compartilhados de relatório &#40;Construtor de Relatórios e SSRS&#41;](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4d8be-151">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d8be-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4d8be-152">See Also</span></span>  
 <span data-ttu-id="4d8be-153">[Expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4d8be-153">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4d8be-154">[Parâmetros de relatório &#40;Construtor de Relatórios e Designer de Relatórios&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="4d8be-154">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="4d8be-155">[Classificação interativa, mapas de documentos e links &#40;Construtor de Relatórios e SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4d8be-155">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4d8be-156">[Adicionar filtros de conjunto de dados, de região de dados e de grupo &#40;Construtor de Relatórios e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="4d8be-156">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="4d8be-157">[Adicionar, editar e atualizar campos no painel de dados do relatório &#40;Construtor de Relatórios e SSRS&#41;](../report-data/add-edit-refresh-fields-in-the-report-data-pane-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4d8be-157">[Add, Edit, Refresh Fields in the Report Data Pane &#40;Report Builder and SSRS&#41;](../report-data/add-edit-refresh-fields-in-the-report-data-pane-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4d8be-158">Adicionar uma expressão &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4d8be-158">Add an Expression &#40;Report Builder and SSRS&#41;</span></span>](add-an-expression-report-builder-and-ssrs.md)  
  
  