---
title: Minigráficos e barras de dados (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.sparklines.f1
- "10544"
ms.assetid: b287436b-fa48-4970-a1a7-1dbcb86e7411
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: eb6f050b1985cf165533e3677242bffb0d7b680f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570435"
---
# <a name="sparklines-and-data-bars-report-builder-and-ssrs"></a><span data-ttu-id="e386e-102">Minigráficos e barras de dados (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="e386e-102">Sparklines and Data Bars (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e386e-103">Minigráficos e barras de dados são gráficos pequenos e simples que transmitem muitas informações em um espaço pequeno, geralmente embutidas com o texto.</span><span class="sxs-lookup"><span data-stu-id="e386e-103">Sparklines and data bars are small, simple charts that convey a lot of information in a little space, often inline with text.</span></span> <span data-ttu-id="e386e-104">Em geral, os minigráficos e as barras de dados são usados em tabelas e matrizes.</span><span class="sxs-lookup"><span data-stu-id="e386e-104">Sparklines and data bars are often used in tables and matrices.</span></span> <span data-ttu-id="e386e-105">Seu impacto resulta da possibilidade de exibir vários deles juntos e compará-los uns sobre os outros, em vez de exibi-los individualmente.</span><span class="sxs-lookup"><span data-stu-id="e386e-105">Their impact comes from viewing many of them together and being able to quickly compare them one above the other, rather than viewing them singly.</span></span> <span data-ttu-id="e386e-106">Eles facilitam a visualização das exceções, as linhas cujo desempenho se distingue das outras.</span><span class="sxs-lookup"><span data-stu-id="e386e-106">They make it easy to see the outliers, the rows that are not performing like the others.</span></span> <span data-ttu-id="e386e-107">Embora sejam pequenos, cada minigráfico costuma representar vários pontos de dados, geralmente durante um período de tempo.</span><span class="sxs-lookup"><span data-stu-id="e386e-107">Although they are small, each sparkline often represents multiple data points, often over time.</span></span> <span data-ttu-id="e386e-108">As barras de dados podem representar vários pontos de dados, mas normalmente ilustram apenas um.</span><span class="sxs-lookup"><span data-stu-id="e386e-108">Data bars can represent multiple data points, but typically illustrate only one.</span></span> <span data-ttu-id="e386e-109">Cada minigráfico geralmente apresenta uma única série.</span><span class="sxs-lookup"><span data-stu-id="e386e-109">Each sparkline typically presents a single series.</span></span> <span data-ttu-id="e386e-110">Você não pode adicionar um minigráfico a um grupo de detalhes em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="e386e-110">You cannot add a sparkline to a detail group in a table.</span></span> <span data-ttu-id="e386e-111">Como os minigráficos exibem dados agregados, eles devem entrar em uma célula associada a um grupo.</span><span class="sxs-lookup"><span data-stu-id="e386e-111">Because sparklines display aggregated data, they must go in a cell associated with a group.</span></span> <span data-ttu-id="e386e-112">Minigráficos e barras de dados têm os mesmos elementos de gráficos básicos de categorias, séries e valores, mas não possuem legenda, linhas de eixo, rótulos nem marcas de escala.</span><span class="sxs-lookup"><span data-stu-id="e386e-112">Sparklines and data bars have the same basic chart elements of categories, series, and values, but they have no legend, axis lines, labels, or tick marks.</span></span>  
  
 <span data-ttu-id="e386e-113">![rs_SparklineExample](../media/rs-sparklineexample.gif "rs_SparklineExample")</span><span class="sxs-lookup"><span data-stu-id="e386e-113">![rs_SparklineExample](../media/rs-sparklineexample.gif "rs_SparklineExample")</span></span>  
  
 <span data-ttu-id="e386e-114">Como introdução rápida aos minigráficos, consulte [Tutorial: Adicionar um minigráfico ao relatório &#40;Construtor de Relatórios&#41;](../tutorial-add-a-sparkline-to-your-report-report-builder.md) e os vídeos [Como criar um minigráfico em uma tabela](https://go.microsoft.com/fwlink/?LinkId=197092) e [Minigráficos, gráficos de barras e indicadores no Construtor de Relatórios](https://technet.microsoft.com/bi/video/ff877165) .</span><span class="sxs-lookup"><span data-stu-id="e386e-114">To quickly get started with sparklines, see [Tutorial: Add a Sparkline to Your Report &#40;Report Builder&#41;](../tutorial-add-a-sparkline-to-your-report-report-builder.md) and the videos [How to: Create a Sparkline in a Table](https://go.microsoft.com/fwlink/?LinkId=197092) and [Sparklines, Bar Charts, and Indicators in Report Builder](https://technet.microsoft.com/bi/video/ff877165) .</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e386e-115">Você pode publicar minigráficos e barras de dados com suas tabelas, matrizes ou lista pai, separadamente de um relatório como uma parte de relatório.</span><span class="sxs-lookup"><span data-stu-id="e386e-115">You can publish sparklines and data bars with their parent table, matrix, or list, separately from a report as a report part.</span></span> [!INCLUDE[ssRBrptparts](../../includes/ssrbrptparts-md.md)]  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="types-of-sparklines"></a><a name="KindsofSparklines"></a> <span data-ttu-id="e386e-116">Tipos de minigráficos</span><span class="sxs-lookup"><span data-stu-id="e386e-116">Types of Sparklines</span></span>  
 <span data-ttu-id="e386e-117">Você pode criar praticamente tantos tipos de minigráficos quanto gráficos normais.</span><span class="sxs-lookup"><span data-stu-id="e386e-117">You can create almost as many types of sparklines as there are regular charts.</span></span> <span data-ttu-id="e386e-118">Em geral, você não pode fazer minigráficos em 3D.</span><span class="sxs-lookup"><span data-stu-id="e386e-118">In general, you cannot make 3D sparklines.</span></span> <span data-ttu-id="e386e-119">Você pode fazer versões de minigráfico destes gráficos completos:</span><span class="sxs-lookup"><span data-stu-id="e386e-119">You can make sparkline versions of these full charts:</span></span>  
  
-   <span data-ttu-id="e386e-120">[Gráficos de colunas &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md): os gráficos de coluna básicos, empilhados e 100% empilhados.</span><span class="sxs-lookup"><span data-stu-id="e386e-120">[Column Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md): The basic, stacked, and 100% stacked column charts.</span></span>  
  
-   <span data-ttu-id="e386e-121">[Gráficos de linhas &#40;Construtor de Relatórios e SSRS&#41;](line-charts-report-builder-and-ssrs.md): todos os gráficos, exceto o gráfico de linhas 3D.</span><span class="sxs-lookup"><span data-stu-id="e386e-121">[Line Charts &#40;Report Builder and SSRS&#41;](line-charts-report-builder-and-ssrs.md): All except the 3D line chart.</span></span>  
  
-   <span data-ttu-id="e386e-122">[Gráficos de áreas &#40;Construtor de Relatórios e SSRS&#41;](area-charts-report-builder-and-ssrs.md): todos os gráficos, exceto o gráfico de áreas 3D</span><span class="sxs-lookup"><span data-stu-id="e386e-122">[Area Charts &#40;Report Builder and SSRS&#41;](area-charts-report-builder-and-ssrs.md): All except the 3D area charts</span></span>  
  
-   <span data-ttu-id="e386e-123">[Gráficos de pizza &#40;Construtor de Relatórios e SSRS&#41;](pie-charts-report-builder-and-ssrs.md): e gráficos de rosca, simples e 3D, mas não as outras formas como gráficos de funil e de pirâmide.</span><span class="sxs-lookup"><span data-stu-id="e386e-123">[Pie Charts &#40;Report Builder and SSRS&#41;](pie-charts-report-builder-and-ssrs.md): And doughnut charts, both flat and 3D, but not the other shapes such as funnel and pyramid charts.</span></span>  
  
-   <span data-ttu-id="e386e-124">[Gráficos de intervalo &#40;Construtor de Relatórios e SSRS&#41;](range-charts-report-builder-and-ssrs.md): as ações, velas, barra de erros e gráficos de caixa.</span><span class="sxs-lookup"><span data-stu-id="e386e-124">[Range Charts &#40;Report Builder and SSRS&#41;](range-charts-report-builder-and-ssrs.md): The stock, candlestick, error bar, and box plot charts.</span></span>  
  
##  <a name="data-bars"></a><a name="DataBars"></a><span data-ttu-id="e386e-125">Barras de dados</span><span class="sxs-lookup"><span data-stu-id="e386e-125">Data Bars</span></span>  
 <span data-ttu-id="e386e-126">Barras de dados geralmente representam um único ponto de dados, apesar de poderem representar vários pontos de dados, como os gráficos de barras normais.</span><span class="sxs-lookup"><span data-stu-id="e386e-126">Data bars typically represent a single data point, though they can represent multiple data points, just like regular bar charts.</span></span> <span data-ttu-id="e386e-127">Normalmente contêm várias séries sem categoria ou possuem agrupamento de série.</span><span class="sxs-lookup"><span data-stu-id="e386e-127">They often contain several series with no category, or have series grouping.</span></span>  
  
 <span data-ttu-id="e386e-128">![rs_DataBars](../media/rs-databars.gif "rs_DataBars")</span><span class="sxs-lookup"><span data-stu-id="e386e-128">![rs_DataBars](../media/rs-databars.gif "rs_DataBars")</span></span>  
  
 <span data-ttu-id="e386e-129">Neste exemplo que usa barras de dados empilhadas, cada barra de dados, embora somente uma barra, ilustra mais de um ponto de dados.</span><span class="sxs-lookup"><span data-stu-id="e386e-129">In this example using stacked data bars, each data bar, although only one bar, illustrates more than one data point.</span></span> <span data-ttu-id="e386e-130">Por exemplo, as três cores diferentes da barra poderiam representar tarefas de três níveis de prioridade com o comprimento da barra representando o número total de tarefas atribuídas a cada pessoa.</span><span class="sxs-lookup"><span data-stu-id="e386e-130">For example, the three different colors of the bar could represent tasks of three levels of priority with the length of the bar representing the total number of tasks assigned to each person.</span></span> <span data-ttu-id="e386e-131">Se você fez estas barras de dados 100% empilhadas, cada barra preencheria a célula e as cores diferentes representariam o percentual do todo para cada nível de prioridade.</span><span class="sxs-lookup"><span data-stu-id="e386e-131">If you made these 100% stacked data bars instead, each bar would fill the cell, and the different colors would represent the percentage of the whole for each priority level.</span></span>  
  
 <span data-ttu-id="e386e-132">Você pode fazer versões de barra de dados destes gráficos completos:</span><span class="sxs-lookup"><span data-stu-id="e386e-132">You can make data bar versions of these full charts:</span></span>  
  
-   <span data-ttu-id="e386e-133">[Gráficos de barras &#40;Construtor de Relatórios e SSRS&#41;](bar-charts-report-builder-and-ssrs.md): os gráficos de barras básicos, empilhados e 100% empilhados.</span><span class="sxs-lookup"><span data-stu-id="e386e-133">[Bar Charts &#40;Report Builder and SSRS&#41;](bar-charts-report-builder-and-ssrs.md): Basic, stacked, and 100% stacked bar charts.</span></span>  
  
-   <span data-ttu-id="e386e-134">[Gráficos de colunas &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md): os gráficos de coluna básicos, empilhados e 100% empilhados.</span><span class="sxs-lookup"><span data-stu-id="e386e-134">[Column Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md): Basic, stacked, and 100% stacked column charts.</span></span> <span data-ttu-id="e386e-135">Os gráficos de coluna podem ser minigráficos ou barras de dados.</span><span class="sxs-lookup"><span data-stu-id="e386e-135">Column charts can be either sparklines or data bars.</span></span>  

##  <a name="aligning-sparkline-data-in-a-table-or-matrix"></a><a name="AlignDatainTableMatrix"></a> <span data-ttu-id="e386e-136">Alinhando dados de minigráfico em uma tabela ou matriz</span><span class="sxs-lookup"><span data-stu-id="e386e-136">Aligning Sparkline Data in a Table or Matrix</span></span>  
 <span data-ttu-id="e386e-137">Quando você insere um minigráfico em uma tabela ou matriz, é geralmente importante que os pontos de dados em cada minigráfico alinhem-se com os pontos de dados dos outros minigráficos naquela coluna.</span><span class="sxs-lookup"><span data-stu-id="e386e-137">When you insert a sparkline in a table or matrix, it is usually important for the data points in each sparkline to align with the data points of the other sparklines in that column.</span></span> <span data-ttu-id="e386e-138">Caso contrário, será difícil comparar os dados nas linhas diferentes.</span><span class="sxs-lookup"><span data-stu-id="e386e-138">Otherwise it is hard to compare the data in the different rows.</span></span> <span data-ttu-id="e386e-139">Por exemplo, quando você compara dados de vendas por mês para vendedores diferentes em sua empresa, é importante que os meses estejam alinhados.</span><span class="sxs-lookup"><span data-stu-id="e386e-139">For example, when you compare sales data by month for different salespeople in your company, you would want the months to align.</span></span> <span data-ttu-id="e386e-140">Se um funcionário esteve fora durante o mês de abril, não haveria dados para aquele funcionário naquele mês.</span><span class="sxs-lookup"><span data-stu-id="e386e-140">If an employee was out for the month of April, there would be no data for that employee for that month.</span></span> <span data-ttu-id="e386e-141">Você esperaria ver um intervalo para aquele mês e ver os dados durante os meses subsequentes alinhados com os dados para os outros funcionários.</span><span class="sxs-lookup"><span data-stu-id="e386e-141">You would want to see a gap for that month, and see the data for subsequent months align with the data for the other employees.</span></span> <span data-ttu-id="e386e-142">Você pode fazer isto alinhando o eixo horizontal.</span><span class="sxs-lookup"><span data-stu-id="e386e-142">You can do this by aligning the horizontal axis.</span></span> <span data-ttu-id="e386e-143">Para obter mais informações, consulte a seção sobre minigráficos em [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md) e consulte [Alinhar os dados de um gráfico em uma tabela ou matriz &#40;Construtor de Relatórios e SSRS&#41;](align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e386e-143">For more information, see the section about sparklines in [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md), and see [Align the Data in a Chart in a Table or Matrix &#40;Report Builder and SSRS&#41;](align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="e386e-144">Da mesma maneira, para estarem comparáveis por todas as linhas, os dados devem se alinhar também verticalmente, ou seja, a altura das barras ou linhas em um minigráfico ou barra de dados deve ser relativa à altura de barras e linhas em todos os outros minigráficos ou barras de dados.</span><span class="sxs-lookup"><span data-stu-id="e386e-144">Likewise, to be comparable across rows, data must also align vertically, meaning that the height of the bars or lines in one sparkline or data bar must be relative to the height of the bars and lines in all the other sparklines or data bars.</span></span> <span data-ttu-id="e386e-145">Caso contrário, você não poderá comparar as linhas entre si.</span><span class="sxs-lookup"><span data-stu-id="e386e-145">Otherwise, you can't compare the rows to each other.</span></span>  
  
 <span data-ttu-id="e386e-146">![rs_SparklineAlignData](../media/rs-sparklinealigndata.gif "rs_SparklineAlignData")</span><span class="sxs-lookup"><span data-stu-id="e386e-146">![rs_SparklineAlignData](../media/rs-sparklinealigndata.gif "rs_SparklineAlignData")</span></span>  
  
 <span data-ttu-id="e386e-147">Nesta imagem, o gráfico de coluna mostra vendas diárias para cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="e386e-147">In this image, the column chart shows daily sales for each employee.</span></span> <span data-ttu-id="e386e-148">Observe que, para os dias em que um funcionário não tem vendas, o gráfico deixa um espaço em branco e alinha os dias seguintes.</span><span class="sxs-lookup"><span data-stu-id="e386e-148">Note that for days that an employee has no sales, the chart leaves a blank and aligns subsequent days.</span></span> <span data-ttu-id="e386e-149">Este é um exemplo de alinhamento horizontal.</span><span class="sxs-lookup"><span data-stu-id="e386e-149">This is an example of horizontal alignment.</span></span> <span data-ttu-id="e386e-150">Também observe que, para alguns funcionários, toda barra é curta, e nenhuma barra alcança a parte superior da célula.</span><span class="sxs-lookup"><span data-stu-id="e386e-150">Also note that for some employees, every bar is short, and no bar reaches the top of the cell.</span></span> <span data-ttu-id="e386e-151">Este é um exemplo de alinhamento vertical; sem isto, nas linhas sem barras altas, as barras curtas expandiriam para preencher a altura da célula.</span><span class="sxs-lookup"><span data-stu-id="e386e-151">This is an example of vertical alignment; without it, in the rows with no tall bars, the short bars would expand to fill the height of the cell.</span></span>  

##  <a name="understanding-the-data-supplied-to-a-sparkline-or-data-bar"></a><a name="UnderstandScope"></a> <span data-ttu-id="e386e-152">Entendendo os dados fornecidos a um minigráfico ou barra de dados</span><span class="sxs-lookup"><span data-stu-id="e386e-152">Understanding the Data Supplied to a Sparkline or Data Bar</span></span>  
 <span data-ttu-id="e386e-153">Quando você adiciona um minigráfico ou barra de dados a uma tabela ou matriz, isso se chama *aninhar* uma região de dados dentro da outra.</span><span class="sxs-lookup"><span data-stu-id="e386e-153">When you add a sparkline or data bar to a table or matrix, this is referred to as *nesting* one data region inside another.</span></span> <span data-ttu-id="e386e-154">Aninhar significa que os dados fornecidos para o minigráfico ou barra de dados são controlados pelo conjunto de dados no qual a tabela ou matriz se baseia, e por onde você os coloca na tabela ou matriz.</span><span class="sxs-lookup"><span data-stu-id="e386e-154">Nesting means that the data supplied to the sparkline or data bar is controlled by the dataset that the table or matrix is based on, and by where you put it in the table or matrix.</span></span> <span data-ttu-id="e386e-155">Para obter mais informações, consulte [Regiões de dados aninhadas &#40;Construtor de Relatórios e SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e386e-155">For more information, see [Nested Data Regions &#40;Report Builder and SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md).</span></span>  
  
##  <a name="converting-a-sparkline-or-data-bar-to-a-full-chart"></a><a name="ConvertSparklinetoChart"></a><span data-ttu-id="e386e-156">Convertendo um minigráfico ou uma barra de dados em um gráfico completo</span><span class="sxs-lookup"><span data-stu-id="e386e-156">Converting a Sparkline or Data Bar to a Full Chart</span></span>  
 <span data-ttu-id="e386e-157">Como minigráficos e barras de dados são apenas um tipo de gráfico, se você decidir que prefere ter a funcionalidade de gráfico completo, faça a conversão clicando com o botão direito do mouse no gráfico e clicando em **Converter em Gráfico Completo**.</span><span class="sxs-lookup"><span data-stu-id="e386e-157">Because sparklines and data bars are just a kind of chart, if you decide you would rather have the full chart functionality, you can convert one to a full chart by right-clicking the chart and clicking **Convert to Full Chart**.</span></span> <span data-ttu-id="e386e-158">Quando você fizer isso, as linhas de eixo, os rótulos, as marcas de escala e a legenda serão adicionados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e386e-158">When you do, the axis lines, labels, tick marks, and legend are added automatically.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e386e-159">Você não pode converter um gráfico completo em um minigráfico ou barra de dados com um clique.</span><span class="sxs-lookup"><span data-stu-id="e386e-159">You cannot convert a full chart to a sparkline or data bar with one click.</span></span> <span data-ttu-id="e386e-160">Porém, você pode fazer um minigráfico ou barra de dados a partir de um gráfico completo bastando excluir todos os elementos de gráfico que não estão em minigráficos e barras de dados.</span><span class="sxs-lookup"><span data-stu-id="e386e-160">However, you can make a sparkline or data bar from a full chart just by deleting all the chart elements that are not in sparklines and data bars.</span></span>  

##  <a name="how-to-topics"></a><a name="HowTo"></a><span data-ttu-id="e386e-161">Tópicos de instruções</span><span class="sxs-lookup"><span data-stu-id="e386e-161">How-to Topics</span></span>  
 [<span data-ttu-id="e386e-162">Adicionar minigráficos e barras de dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e386e-162">Add Sparklines and Data Bars &#40;Report Builder and SSRS&#41;</span></span>](sparklines-and-data-bars-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e386e-163">Alinhar os dados de um gráfico em uma tabela ou matriz &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e386e-163">Align the Data in a Chart in a Table or Matrix &#40;Report Builder and SSRS&#41;</span></span>](align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs.md)  
  
### <a name="other-how-to-topics-for-charts"></a><span data-ttu-id="e386e-164">Outros tópicos de instruções para gráficos</span><span class="sxs-lookup"><span data-stu-id="e386e-164">Other how-to topics for charts</span></span>  
 <span data-ttu-id="e386e-165">Como minigráficos e barras de dados são um tipo de gráfico, você também pode achar os tópicos de instruções a seguir úteis e pertinentes:</span><span class="sxs-lookup"><span data-stu-id="e386e-165">Because sparklines and data bars are a type of chart, you might also find the following how-to topics for charts helpful and relevant:</span></span>  
  
 [<span data-ttu-id="e386e-166">Adicionar um gráfico a um relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e386e-166">Add a Chart to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-chart-to-a-report-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e386e-167">Adicionar pontos vazios ao gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e386e-167">Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;</span></span>](add-empty-points-to-a-chart-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e386e-168">Adicionar ou remover margens de um gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e386e-168">Add or Remove Margins from a Chart &#40;Report Builder and SSRS&#41;</span></span>](add-or-remove-margins-from-a-chart-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e386e-169">Alterar um tipo de gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e386e-169">Change a Chart Type &#40;Report Builder and SSRS&#41;</span></span>](change-a-chart-type-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e386e-170">Definir cores em um gráfico usando uma paleta &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e386e-170">Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;</span></span>](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e386e-171">Mostrar dicas de ferramenta em uma série &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e386e-171">Show ToolTips on a Series &#40;Report Builder and SSRS&#41;</span></span>](show-tooltips-on-a-series-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e386e-172">Especificar uma escala logarítmica &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e386e-172">Specify a Logarithmic Scale &#40;Report Builder and SSRS&#41;</span></span>](specify-a-logarithmic-scale-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e386e-173">Especificar um intervalo do eixo &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e386e-173">Specify an Axis Interval &#40;Report Builder and SSRS&#41;</span></span>](specify-an-axis-interval-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e386e-174">Especificar cores consistentes em gráficos com várias formas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e386e-174">Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;</span></span>](shape-charts-report-builder-and-ssrs.md)  
  
## <a name="see-also"></a><span data-ttu-id="e386e-175">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e386e-175">See Also</span></span>  
 <span data-ttu-id="e386e-176">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e386e-176">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e386e-177">[Tutorial: adicionar um minigráfico ao seu relatório &#40;Construtor de Relatórios&#41;](../tutorial-add-a-sparkline-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="e386e-177">[Tutorial: Add a Sparkline to Your Report &#40;Report Builder&#41;](../tutorial-add-a-sparkline-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="e386e-178">[Minigráficos, gráficos de barras e indicadores no Construtor de Relatórios (vídeo)](https://technet.microsoft.com/bi/video/ff877165) </span><span class="sxs-lookup"><span data-stu-id="e386e-178">[Sparklines, Bar Charts, and Indicators in Report Builder (video)](https://technet.microsoft.com/bi/video/ff877165) </span></span>  
 [<span data-ttu-id="e386e-179">Como: Criar um minigráfico em uma tabela (vídeo)</span><span class="sxs-lookup"><span data-stu-id="e386e-179">How to: Create a Sparkline in a Table (video)</span></span>](https://go.microsoft.com/fwlink/?LinkId=197092)  