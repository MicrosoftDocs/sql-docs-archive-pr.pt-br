---
title: Tipos de gráfico (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10423"
ms.assetid: 57b00017-69ae-4e71-8d78-44744e208ac7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e578d8259a0b6fa4ad94b6889ecb6e96afdd7b67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582304"
---
# <a name="chart-types-report-builder-and-ssrs"></a><span data-ttu-id="c92a3-102">Tipos de gráficos (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="c92a3-102">Chart Types (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c92a3-103">É importante escolher um tipo de gráfico apropriado para o tipo de dados que você está apresentando.</span><span class="sxs-lookup"><span data-stu-id="c92a3-103">It is important to choose an appropriate chart type for the type of data that you are presenting.</span></span> <span data-ttu-id="c92a3-104">Isto determinará como os dados podem ser interpretados quando colocados em formato de gráfico.</span><span class="sxs-lookup"><span data-stu-id="c92a3-104">This will determine how well the data can be interpreted when put in chart form.</span></span> <span data-ttu-id="c92a3-105">Por exemplo, se o conjunto de dados contiver muitos pontos de dados relacionados ao tamanho do gráfico, talvez seja melhor apresentá-lo usando um grafico de área, linha ou de dispersão.</span><span class="sxs-lookup"><span data-stu-id="c92a3-105">For example, if your dataset contains a lot of data points relative to the size of the chart, it may be better presented using an area, line, or scatter chart.</span></span> <span data-ttu-id="c92a3-106">Para discussão em como preparar seus dados dependendo do tipo de gráfico selecionado, consulte [Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c92a3-106">For discussion on how to prepare your data depending on the chart type selected, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="choosing-a-chart-type"></a><span data-ttu-id="c92a3-107">Escolhendo um tipo de gráfico</span><span class="sxs-lookup"><span data-stu-id="c92a3-107">Choosing a Chart Type</span></span>  
 <span data-ttu-id="c92a3-108">Cada tipo de gráfico tem características exclusivas para lhe ajudar a visualizar seu conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="c92a3-108">Each chart type has unique characteristics to help you visualize your dataset.</span></span> <span data-ttu-id="c92a3-109">Você pode usar qualquer tipo de gráfico para exibir seus dados, mas esses serão mais facilmente lidos se usar um tipo de gráfico adequado para os seus dados, baseado no assunto que está tentando mostrar no seu relatório.</span><span class="sxs-lookup"><span data-stu-id="c92a3-109">You can use any chart type to display your data, but your data will be easier to read when you use a chart type that is suitable to your data, based on what you are trying to show in your report.</span></span> <span data-ttu-id="c92a3-110">A tabela a seguir resume os recursos de gráfico que afetam a adequação de um gráfico a seu conjunto de dados específico.</span><span class="sxs-lookup"><span data-stu-id="c92a3-110">The following table summarizes chart features that affect the suitability of a chart to your particular dataset.</span></span>  
  
 <span data-ttu-id="c92a3-111">Você poderá alterar o tipo de gráfico depois de criá-lo.</span><span class="sxs-lookup"><span data-stu-id="c92a3-111">You can change the chart type after you have created it.</span></span> <span data-ttu-id="c92a3-112">Para obter mais informações, consulte [Alterar um tipo de gráfico &#40;Construtor de Relatórios e SSRS&#41;](change-a-chart-type-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c92a3-112">For more information, see [Change a Chart Type &#40;Report Builder and SSRS&#41;](change-a-chart-type-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="c92a3-113">Exemplos de muitos desses tipos de gráficos estão disponíveis como relatórios de exemplo.</span><span class="sxs-lookup"><span data-stu-id="c92a3-113">Examples of many of these types of charts are available as sample reports.</span></span> <span data-ttu-id="c92a3-114">Para obter mais informações sobre como baixar relatórios de exemplo, consulte [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Construtor de Relatórios e Report Designer relatórios de exemplo](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="c92a3-114">For more information about downloading sample reports, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
|<span data-ttu-id="c92a3-115">Tipo de gráfico</span><span class="sxs-lookup"><span data-stu-id="c92a3-115">Chart type</span></span>|<span data-ttu-id="c92a3-116">Exibir dados de taxa</span><span class="sxs-lookup"><span data-stu-id="c92a3-116">Display ratio data</span></span>|<span data-ttu-id="c92a3-117">Exibir dados de estoque</span><span class="sxs-lookup"><span data-stu-id="c92a3-117">Display stock data</span></span>|<span data-ttu-id="c92a3-118">Exibir dados lineares</span><span class="sxs-lookup"><span data-stu-id="c92a3-118">Display linear data</span></span>|<span data-ttu-id="c92a3-119">Exibir dados de vários valores</span><span class="sxs-lookup"><span data-stu-id="c92a3-119">Display multi-value data</span></span>|  
|----------------|------------------------|------------------------|-------------------------|-------------------------------|  
|[<span data-ttu-id="c92a3-120">Gráficos de área &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c92a3-120">Area Charts &#40;Report Builder and SSRS&#41;</span></span>](area-charts-report-builder-and-ssrs.md)|||<span data-ttu-id="c92a3-121">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-121">![Available](../media/greencheck.gif "Available")</span></span>||  
|[<span data-ttu-id="c92a3-122">Gráficos de barras &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c92a3-122">Bar Charts &#40;Report Builder and SSRS&#41;</span></span>](bar-charts-report-builder-and-ssrs.md)|||<span data-ttu-id="c92a3-123">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-123">![Available](../media/greencheck.gif "Available")</span></span>||  
|[<span data-ttu-id="c92a3-124">Barras de dados</span><span class="sxs-lookup"><span data-stu-id="c92a3-124">Data Bars</span></span>](sparklines-and-data-bars-report-builder-and-ssrs.md)|||<span data-ttu-id="c92a3-125">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-125">![Available](../media/greencheck.gif "Available")</span></span>||  
|[<span data-ttu-id="c92a3-126">Gráficos de colunas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c92a3-126">Column Charts &#40;Report Builder and SSRS&#41;</span></span>](column-charts-report-builder-and-ssrs.md)|||<span data-ttu-id="c92a3-127">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-127">![Available](../media/greencheck.gif "Available")</span></span>||  
|[<span data-ttu-id="c92a3-128">Gráficos de linhas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c92a3-128">Line Charts &#40;Report Builder and SSRS&#41;</span></span>](line-charts-report-builder-and-ssrs.md)|||<span data-ttu-id="c92a3-129">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-129">![Available](../media/greencheck.gif "Available")</span></span>||  
|[<span data-ttu-id="c92a3-130">Gráficos de pizza &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c92a3-130">Pie Charts &#40;Report Builder and SSRS&#41;</span></span>](pie-charts-report-builder-and-ssrs.md)|<span data-ttu-id="c92a3-131">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-131">![Available](../media/greencheck.gif "Available")</span></span>||||  
|[<span data-ttu-id="c92a3-132">Gráficos polares &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c92a3-132">Polar Charts &#40;Report Builder and SSRS&#41;</span></span>](polar-charts-report-builder-and-ssrs.md)|<span data-ttu-id="c92a3-133">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-133">![Available](../media/greencheck.gif "Available")</span></span>||||  
|[<span data-ttu-id="c92a3-134">Gráficos de intervalo &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c92a3-134">Range Charts &#40;Report Builder and SSRS&#41;</span></span>](range-charts-report-builder-and-ssrs.md)|||<span data-ttu-id="c92a3-135">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-135">![Available](../media/greencheck.gif "Available")</span></span>|<span data-ttu-id="c92a3-136">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-136">![Available](../media/greencheck.gif "Available")</span></span>|  
|[<span data-ttu-id="c92a3-137">Gráficos de dispersão &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c92a3-137">Scatter Charts &#40;Report Builder and SSRS&#41;</span></span>](scatter-charts-report-builder-and-ssrs.md)|<span data-ttu-id="c92a3-138">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-138">![Available](../media/greencheck.gif "Available")</span></span>||<span data-ttu-id="c92a3-139">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-139">![Available](../media/greencheck.gif "Available")</span></span>||  
|[<span data-ttu-id="c92a3-140">Gráficos de forma &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c92a3-140">Shape Charts &#40;Report Builder and SSRS&#41;</span></span>](shape-charts-report-builder-and-ssrs.md)|<span data-ttu-id="c92a3-141">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-141">![Available](../media/greencheck.gif "Available")</span></span>||||  
|[<span data-ttu-id="c92a3-142">Minigráficos</span><span class="sxs-lookup"><span data-stu-id="c92a3-142">Sparklines</span></span>](sparklines-and-data-bars-report-builder-and-ssrs.md)|<span data-ttu-id="c92a3-143">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-143">![Available](../media/greencheck.gif "Available")</span></span>|<span data-ttu-id="c92a3-144">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-144">![Available](../media/greencheck.gif "Available")</span></span>|<span data-ttu-id="c92a3-145">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-145">![Available](../media/greencheck.gif "Available")</span></span>|<span data-ttu-id="c92a3-146">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-146">![Available](../media/greencheck.gif "Available")</span></span>|  
|[<span data-ttu-id="c92a3-147">Gráficos de estoque &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c92a3-147">Stock Charts &#40;Report Builder and SSRS&#41;</span></span>](stock-charts-report-builder-and-ssrs.md)||<span data-ttu-id="c92a3-148">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-148">![Available](../media/greencheck.gif "Available")</span></span>||<span data-ttu-id="c92a3-149">![Disponível](../media/greencheck.gif "Disponível")</span><span class="sxs-lookup"><span data-stu-id="c92a3-149">![Available](../media/greencheck.gif "Available")</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c92a3-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c92a3-150">See Also</span></span>  
 <span data-ttu-id="c92a3-151">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c92a3-151">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c92a3-152">[Pontos de dados vazios e nulos em gráficos &#40;Construtor de Relatórios e SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c92a3-152">[Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c92a3-153">Adicionar um gráfico a um relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c92a3-153">Add a Chart to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-chart-to-a-report-report-builder-and-ssrs.md)  
  
  