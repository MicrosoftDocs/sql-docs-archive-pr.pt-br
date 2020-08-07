---
title: Procurar um modelo usando o Visualizador de cluster da Microsoft | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- clusters [Analysis Services]
- discrimination [Analysis Services]
- names [Analysis Services], clusters
- Microsoft Cluster Viewer
- mining model content, viewing
- comparing clusters
- viewing clusters
- displaying clusters
- data mining [Analysis Services], clusters
- Cluster Viewer [Analysis Services]
- mining models [Analysis Services], clusters
ms.assetid: 591fe30b-d88f-4a71-94d4-4a3907fc275d
author: minewiskan
ms.author: owend
ms.openlocfilehash: d3597c97ad285d8ddc40b398723f6d3ec652ceb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583272"
---
# <a name="browse-a-model-using-the-microsoft-cluster-viewer"></a><span data-ttu-id="2aa4f-102">Procurar um modelo usando o Visualizador de Cluster da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2aa4f-102">Browse a Model Using the Microsoft Cluster Viewer</span></span>
  <span data-ttu-id="2aa4f-103">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visualizador de cluster no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] exibe modelos de mineração criados com o [!INCLUDE[msCoName](../../includes/msconame-md.md)] algoritmo de clustering.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Cluster Viewer in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] displays mining models that are built with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Clustering algorithm.</span></span> <span data-ttu-id="2aa4f-104">O algoritmo Cluster da [!INCLUDE[msCoName](../../includes/msconame-md.md)] é um algoritmo de segmentação para ser usado na exploração de dados para identificar anomalias nos dados e criar previsões.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Clustering algorithm is a segmentation algorithm for use in exploring data to identify anomalies in the data and to create predictions.</span></span> <span data-ttu-id="2aa4f-105">Para obter mais informações sobre esse algoritmo, consulte [Microsoft Clustering Algorithm](microsoft-clustering-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="2aa4f-105">For more information about this algorithm, see [Microsoft Clustering Algorithm](microsoft-clustering-algorithm.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2aa4f-106">Para exibir informações detalhadas sobre as equações usadas no modelo e os padrões identificados, use o Visualizador de Árvore de Conteúdo Genérica da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2aa4f-106">To view detailed information about the equations used in the model and the patterns that were discovered, use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree viewer.</span></span> <span data-ttu-id="2aa4f-107">Para obter mais informações, consulte [Procurar um modelo usando o Visualizador de Árvore de Conteúdo Genérica da Microsoft](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) ou [Visualizador de Árvore de Conteúdo Genérica da Microsoft &#40;Mineração de Dados&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="2aa4f-107">For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) or [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span>  
  
##  <a name="viewer-tabs"></a><a name="BKMK_ViewerTabs"></a><span data-ttu-id="2aa4f-108">Guias do Visualizador</span><span class="sxs-lookup"><span data-stu-id="2aa4f-108">Viewer Tabs</span></span>  
 <span data-ttu-id="2aa4f-109">Quando você navega em um modelo de mineração do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], ele é exibido na guia **Visualizador do Modelo de Mineração** do Designer de Mineração de Dados no visualizador adequado ao modelo.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-109">When you browse a mining model in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the model is displayed on the **Mining Model Viewer** tab of Data Mining Designer in the appropriate viewer for the model.</span></span> <span data-ttu-id="2aa4f-110">O Visualizador de Cluster da [!INCLUDE[msCoName](../../includes/msconame-md.md)] fornece as seguintes guias para serem usadas na exploração de modelos de mineração de cluster:</span><span class="sxs-lookup"><span data-stu-id="2aa4f-110">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Cluster Viewer provides the following tabs for use in exploring clustering mining models:</span></span>  
  
-   [<span data-ttu-id="2aa4f-111">Diagrama de Cluster</span><span class="sxs-lookup"><span data-stu-id="2aa4f-111">Cluster Diagram</span></span>](#BKMK_Diagram)  
  
-   [<span data-ttu-id="2aa4f-112">Perfis de cluster</span><span class="sxs-lookup"><span data-stu-id="2aa4f-112">Cluster Profiles</span></span>](#BKMK_Profile)  
  
-   [<span data-ttu-id="2aa4f-113">Características do cluster</span><span class="sxs-lookup"><span data-stu-id="2aa4f-113">Cluster Characteristics</span></span>](#BKMK_Characteristics)  
  
-   [<span data-ttu-id="2aa4f-114">Discriminação do Cluster</span><span class="sxs-lookup"><span data-stu-id="2aa4f-114">Cluster Discrimination</span></span>](#BKMK_Discrimination)  
  
###  <a name="cluster-diagram"></a><a name="BKMK_Diagram"></a><span data-ttu-id="2aa4f-115">Diagrama de cluster</span><span class="sxs-lookup"><span data-stu-id="2aa4f-115">Cluster Diagram</span></span>  
 <span data-ttu-id="2aa4f-116">A guia **Diagrama de Cluster** do Visualizador de Cluster da [!INCLUDE[msCoName](../../includes/msconame-md.md)] exibe todos os clusters existentes em um modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-116">The **Cluster Diagram** tab of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Cluster Viewer displays all the clusters that are in a mining model.</span></span> <span data-ttu-id="2aa4f-117">O sombreamento da linha que conecta um cluster a outro expressa o grau de semelhança entre os clusters.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-117">The shading of the line that connects one cluster to another represents the strength of the similarity of the clusters.</span></span> <span data-ttu-id="2aa4f-118">Um sombreamento claro ou a ausência dele indica que os clusters não são muito parecidos.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-118">If the shading is light or nonexistent, the clusters are not very similar.</span></span> <span data-ttu-id="2aa4f-119">Quanto mais escura a linha, maior a semelhança entre os links.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-119">As the line becomes darker, the similarity of the links becomes stronger.</span></span> <span data-ttu-id="2aa4f-120">É possível selecionar o número de linhas exibido no visualizador, ajustando-se o controle deslizante à direita dos clusters.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-120">You can adjust how many lines the viewer shows by adjusting the slider to the right of the clusters.</span></span> <span data-ttu-id="2aa4f-121">Diminuindo o controle deslizante, somente os links mais fortes serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-121">Lowering the slider shows only the strongest links.</span></span>  
  
 <span data-ttu-id="2aa4f-122">Por padrão, a sombra representa a população do cluster.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-122">By default, the shade represents the population of the cluster.</span></span> <span data-ttu-id="2aa4f-123">Usando as opções de **ShadingVariable** e **estado** , você pode selecionar o atributo e o par de estado que o sombreamento representa.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-123">By using the **ShadingVariable** and **State** options, you can select which attribute and state pair the shading represents.</span></span> <span data-ttu-id="2aa4f-124">Quanto mais escuro o sombreamento, maior a distribuição de atributo para um estado específico.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-124">The darker the shading, the greater the attribute distribution is for a specific state.</span></span> <span data-ttu-id="2aa4f-125">A distribuição diminui conforme o sombreamento clareia.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-125">The distribution decreases as the shading gets lighter.</span></span>  
  
 <span data-ttu-id="2aa4f-126">Para renomear um cluster, clique com o botão direito do mouse em seu nó e selecione **Renomear Cluster**.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-126">To rename a cluster, right-click its node and select **Rename Cluster**.</span></span> <span data-ttu-id="2aa4f-127">Para o servidor, o nome novo é persistente.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-127">The new name is persisted to the server.</span></span>  
  
 <span data-ttu-id="2aa4f-128">Para copiar a seção visível do diagrama na Área de Transferência, clique em **Copiar Exibição de Gráfico**.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-128">To copy the visible section of the diagram to the Clipboard, click **Copy Graph View**.</span></span> <span data-ttu-id="2aa4f-129">Para copiar o diagrama completo, clique em **Copiar Gráfico Inteiro**.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-129">To copy the complete diagram, click **Copy Entire Graph**.</span></span> <span data-ttu-id="2aa4f-130">Também é possível aplicar o zoom usando **Mais Zoom** e **Menos Zoom**ou ainda ajustar o diagrama à tela usando **Dimensionar Diagrama para Ajustar à Janela**.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-130">You can also zoom in and out by using **Zoom In** and **Zoom Out**, or you can fit the diagram to the screen by using **Scale Diagram to Fit in Window**.</span></span>  
  
 [<span data-ttu-id="2aa4f-131">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="2aa4f-131">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
###  <a name="cluster-profiles"></a><a name="BKMK_Profile"></a> <span data-ttu-id="2aa4f-132">Perfis de Cluster</span><span class="sxs-lookup"><span data-stu-id="2aa4f-132">Cluster Profiles</span></span>  
 <span data-ttu-id="2aa4f-133">A guia **Perfis de Cluster** oferece uma exibição geral dos clusters criados pelo algoritmo em seu modelo.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-133">The **Cluster Profiles** tab provides an overall view of the clusters that the algorithm in your model creates.</span></span> <span data-ttu-id="2aa4f-134">Essa exibição mostra cada atributo, junto com a distribuição do atributo em cada cluster.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-134">This view displays each attribute, together with the distribution of the attribute in each cluster.</span></span> <span data-ttu-id="2aa4f-135">Uma InfoDica de cada célula exibe as estatísticas de distribuição e uma InfoDica de cada cabeçalho de coluna exibe a população de cluster.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-135">An InfoTip for each cell displays the distribution statistics, and an InfoTip for each column heading displays the cluster population.</span></span> <span data-ttu-id="2aa4f-136">Atributos discretos são mostrados como barras coloridas, e os atributos contínuos são mostrados como um gráfico de diamante que representa o desvio médio e padrão em cada cluster.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-136">Discrete attributes are shown as colored bars, and continuous attributes are shown as a diamond chart that represents the mean and standard deviation in each cluster.</span></span> <span data-ttu-id="2aa4f-137">A opção **Barras de histograma** controla o número de barras visíveis no histograma.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-137">The **Histogram bars** option controls the number of bars that are visible in the histogram.</span></span> <span data-ttu-id="2aa4f-138">Caso haja mais barras do que você optou por exibir, as barras mais altas serão retidas e as restantes, agrupadas em um recipiente cinza.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-138">If more bars exist than you choose to display, the bars of highest importance are retained, and the remaining bars are grouped together into a gray bucket.</span></span>  
  
 <span data-ttu-id="2aa4f-139">É possível alterar a nomenclatura padrão dos clusters e torná-la mais descritiva.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-139">You can change the default names of the clusters, to make the names more descriptive.</span></span> <span data-ttu-id="2aa4f-140">Renomeie um cluster clicando com o botão direito do mouse no título da coluna e selecionando **Renomear cluster**.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-140">Rename a cluster by right-clicking its column heading and selecting **Rename cluster**.</span></span> <span data-ttu-id="2aa4f-141">Você também pode ocultar clusters selecionando **Ocultar coluna**.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-141">You can also hide clusters by selecting **Hide column**.</span></span>  
  
 <span data-ttu-id="2aa4f-142">Para abrir uma janela que possibilite uma exibição maior e mais detalhada dos clusters, clique duas vezes em uma célula na coluna **Estados** ou em um histograma no visualizador.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-142">To open a window that provides a larger, more detailed view of the clusters, double-click either a cell in the **States** column or a histogram in the viewer.</span></span>  
  
 <span data-ttu-id="2aa4f-143">Clique em um cabeçalho de coluna para classificar os atributos em ordem de importância para aquele cluster.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-143">Click a column heading to sort the attributes in order of importance for that cluster.</span></span> <span data-ttu-id="2aa4f-144">Você também pode arrastar colunas para reordená-las no visualizador.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-144">You can also drag columns to reorder them in the viewer.</span></span>  
  
 [<span data-ttu-id="2aa4f-145">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="2aa4f-145">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
###  <a name="cluster-characteristics"></a><a name="BKMK_Characteristics"></a> <span data-ttu-id="2aa4f-146">Características do Cluster</span><span class="sxs-lookup"><span data-stu-id="2aa4f-146">Cluster Characteristics</span></span>  
 <span data-ttu-id="2aa4f-147">Para usar a guia **Características do Cluster** , selecione um cluster da lista **Cluster** .</span><span class="sxs-lookup"><span data-stu-id="2aa4f-147">To use the **Cluster Characteristics** tab, select a cluster from the **Cluster** list.</span></span> <span data-ttu-id="2aa4f-148">Depois de selecionado um cluster, é possível examinar as características particulares daquele cluster específico.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-148">After you select a cluster, you can examine the characteristics that make up that specific cluster.</span></span> <span data-ttu-id="2aa4f-149">Os atributos contidos no cluster são listados nas colunas **Variáveis** , e o estado do atributo listado é relacionado na coluna **Valores** .</span><span class="sxs-lookup"><span data-stu-id="2aa4f-149">The attributes that the cluster contains are listed in the **Variables** columns, and the state of the listed attribute is listed in the **Values** column.</span></span> <span data-ttu-id="2aa4f-150">Os estados de atributo são listados em ordem de importância, descritos segundo a probabilidade com que aparecerão no cluster.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-150">Attribute states are listed in order of importance, described by the probability that they will appear in the cluster.</span></span> <span data-ttu-id="2aa4f-151">A probabilidade é exibida na coluna **Probabilidade** .</span><span class="sxs-lookup"><span data-stu-id="2aa4f-151">The probability is shown in the **Probability** column.</span></span>  
  
 [<span data-ttu-id="2aa4f-152">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="2aa4f-152">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
###  <a name="cluster-discrimination"></a><a name="BKMK_Discrimination"></a><span data-ttu-id="2aa4f-153">Discriminação de cluster</span><span class="sxs-lookup"><span data-stu-id="2aa4f-153">Cluster Discrimination</span></span>  
 <span data-ttu-id="2aa4f-154">Você pode usar a guia **Distinção de Cluster** para comparar os atributos entre dois clusters.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-154">You can use the **Cluster Discrimination** tab to compare attributes between two clusters.</span></span> <span data-ttu-id="2aa4f-155">Use as listas **Cluster 1** e **Cluster 2** para selecionar os clusters a serem comparados.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-155">Use the **Cluster 1** and **Cluster 2** lists to select the clusters to compare.</span></span> <span data-ttu-id="2aa4f-156">O visualizador determina as diferenças mais importantes entre os clusters e exibe os estados de atributo relativos às diferenças, por ordem de importância.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-156">The viewer determines the most important differences between the clusters, and displays the attribute states that are associated with the differences, in order of importance.</span></span> <span data-ttu-id="2aa4f-157">Uma barra à direita do atributo mostra que cluster o estado favorece, e o tamanho da barra indica a intensidade desse favorecimento.</span><span class="sxs-lookup"><span data-stu-id="2aa4f-157">A bar to the right of the attribute shows which cluster the state favors, and the size of the bar shows how strongly the state favors the cluster.</span></span>  
  
 [<span data-ttu-id="2aa4f-158">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="2aa4f-158">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
## <a name="see-also"></a><span data-ttu-id="2aa4f-159">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2aa4f-159">See Also</span></span>  
 <span data-ttu-id="2aa4f-160">[Algoritmo Microsoft Clustering](microsoft-clustering-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="2aa4f-160">[Microsoft Clustering Algorithm](microsoft-clustering-algorithm.md) </span></span>  
 <span data-ttu-id="2aa4f-161">[Tarefas e instruções do Visualizador do modelo de mineração](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="2aa4f-161">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="2aa4f-162">[Tarefas e instruções do Visualizador do modelo de mineração](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="2aa4f-162">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="2aa4f-163">[Ferramentas de mineração de dados](data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2aa4f-163">[Data Mining Tools](data-mining-tools.md) </span></span>  
 [<span data-ttu-id="2aa4f-164">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="2aa4f-164">Data Mining Model Viewers</span></span>](data-mining-model-viewers.md)  
  
  