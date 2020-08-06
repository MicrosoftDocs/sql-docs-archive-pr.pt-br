---
title: Algoritmo rede neural da Microsoft | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- training neural networks
- output neurons [Analysis Services]
- algorithms [data mining]
- neural network algorithms [Analysis Services]
- neurons [Analysis Services]
- classification algorithms [Analysis Services]
- neural networks
- multilayer perceptron network of neurons [Analysis Services]
- hidden neurons
- Back-Propagated Delta Rule network
- input neurons [Analysis Services]
- regression algorithms [Analysis Services]
ms.assetid: 61eb4861-8a6a-4214-a4b8-1dd278ad7a68
author: minewiskan
ms.author: owend
ms.openlocfilehash: 389df77299bbf357e1b8b0f0695f03a74420f786
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568900"
---
# <a name="microsoft-neural-network-algorithm"></a><span data-ttu-id="08428-102">Microsoft Neural Network Algorithm</span><span class="sxs-lookup"><span data-stu-id="08428-102">Microsoft Neural Network Algorithm</span></span>
  <span data-ttu-id="08428-103">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , o [!INCLUDE[msCoName](../../includes/msconame-md.md)] algoritmo de rede neural combina cada Estado possível do atributo de entrada com cada Estado possível do atributo previsível e usa os dados de treinamento para calcular probabilidades.</span><span class="sxs-lookup"><span data-stu-id="08428-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Neural Network algorithm combines each possible state of the input attribute with each possible state of the predictable attribute, and uses the training data to calculate probabilities.</span></span> <span data-ttu-id="08428-104">Posteriormente, essas probabilidades podem ser usadas para classificação ou regressão e também para a previsão de um resultado do atributo previsível com base nos atributos de entrada.</span><span class="sxs-lookup"><span data-stu-id="08428-104">You can later use these probabilities for classification or regression, and to predict an outcome of the predicted attribute, based on the input attributes.</span></span>  
  
 <span data-ttu-id="08428-105">Um modelo de mineração desenvolvido com o algoritmo Rede Neural da [!INCLUDE[msCoName](../../includes/msconame-md.md)] pode conter várias redes, dependendo do número de colunas usadas para a previsão de entrada ou usadas apenas para previsão.</span><span class="sxs-lookup"><span data-stu-id="08428-105">A mining model that is constructed with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Neural Network algorithm can contain multiple networks, depending on the number of columns that are used for both input and prediction, or that are used only for prediction.</span></span> <span data-ttu-id="08428-106">O número de redes que um modelo de mineração simples contém depende do número de estados que estão contidos nas colunas de entrada e as colunas previsíveis que o modelo de mineração usa.</span><span class="sxs-lookup"><span data-stu-id="08428-106">The number of networks that a single mining model contains depends on the number of states that are contained by the input columns and predictable columns that the mining model uses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08428-107">Exemplo</span><span class="sxs-lookup"><span data-stu-id="08428-107">Example</span></span>  
 <span data-ttu-id="08428-108">O algoritmo Rede Neural da [!INCLUDE[msCoName](../../includes/msconame-md.md)] é útil para analisar dados de entrada complexos, tais como de um processo de fabricação, de comercialização ou, problemas comerciais para os quais uma quantidade significativa de dados de treinamento está disponível mas, para os quais regras não podem ser facilmente derivadas usando outros algoritmos.</span><span class="sxs-lookup"><span data-stu-id="08428-108">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Neural Network algorithm is useful for analyzing complex input data, such as from a manufacturing or commercial process, or business problems for which a significant quantity of training data is available but for which rules cannot be easily derived by using other algorithms.</span></span>  
  
 <span data-ttu-id="08428-109">Os cenários sugeridos para usar o algoritmo Rede Neural da [!INCLUDE[msCoName](../../includes/msconame-md.md)] incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="08428-109">Suggested scenarios for using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Neural Network algorithm include the following:</span></span>  
  
-   <span data-ttu-id="08428-110">Análise de promoção e marketing, tais como, medição do sucesso de uma promoção de mala direta ou de uma campanha publicitária radiofônica.</span><span class="sxs-lookup"><span data-stu-id="08428-110">Marketing and promotion analysis, such as measuring the success of a direct mail promotion or a radio advertising campaign.</span></span>  
  
-   <span data-ttu-id="08428-111">Prevendo movimento de ações, flutuação de moeda ou demais informações financeiras altamente fluidas a partir de dados históricos.</span><span class="sxs-lookup"><span data-stu-id="08428-111">Predicting stock movement, currency fluctuation, or other highly fluid financial information from historical data.</span></span>  
  
-   <span data-ttu-id="08428-112">Analisando processos industriais e de fabricação.</span><span class="sxs-lookup"><span data-stu-id="08428-112">Analyzing manufacturing and industrial processes.</span></span>  
  
-   <span data-ttu-id="08428-113">Mineração de texto.</span><span class="sxs-lookup"><span data-stu-id="08428-113">Text mining.</span></span>  
  
-   <span data-ttu-id="08428-114">Qualquer modelo de previsão que analisa relações complexas entre muitas entradas e, relativamente, menos saídas.</span><span class="sxs-lookup"><span data-stu-id="08428-114">Any prediction model that analyzes complex relationships between many inputs and relatively fewer outputs.</span></span>  
  
## <a name="how-the-algorithm-works"></a><span data-ttu-id="08428-115">Como o algoritmo funciona</span><span class="sxs-lookup"><span data-stu-id="08428-115">How the Algorithm Works</span></span>  
 <span data-ttu-id="08428-116">O algoritmo Rede Neural da [!INCLUDE[msCoName](../../includes/msconame-md.md)] cria uma rede que é composta por até três camadas de neurônios.</span><span class="sxs-lookup"><span data-stu-id="08428-116">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Neural Network algorithm creates a network that is composed of up to three layers of neurons.</span></span> <span data-ttu-id="08428-117">Essas camadas são uma camada de entrada, uma camada opcional oculta e uma camada de saída.</span><span class="sxs-lookup"><span data-stu-id="08428-117">These layers are an input layer, an optional hidden layer, and an output layer.</span></span>  
  
 <span data-ttu-id="08428-118">**Camada de entrada:** Os neurônios de entrada definem todos os valores de atributo de entrada para o modelo de Data Mining e suas probabilidades.</span><span class="sxs-lookup"><span data-stu-id="08428-118">**Input layer:** Input neurons define all the input attribute values for the data mining model, and their probabilities.</span></span>  
  
 <span data-ttu-id="08428-119">**Camada oculta:** Os neurônios ocultos recebem entradas de neurônios de entrada e fornecem saídas para neurônios de saída.</span><span class="sxs-lookup"><span data-stu-id="08428-119">**Hidden layer:** Hidden neurons receive inputs from input neurons and provide outputs to output neurons.</span></span> <span data-ttu-id="08428-120">A camada oculta é onde as várias probabilidades de entradas são ponderadas.</span><span class="sxs-lookup"><span data-stu-id="08428-120">The hidden layer is where the various probabilities of the inputs are assigned weights.</span></span> <span data-ttu-id="08428-121">Uma ponderação descreve a relevância ou importância de uma entrada específica para o neurônio oculto.</span><span class="sxs-lookup"><span data-stu-id="08428-121">A weight describes the relevance or importance of a particular input to the hidden neuron.</span></span> <span data-ttu-id="08428-122">Quanto maior a ponderação atribuída a uma entrada, mais importante será o valor daquela entrada.</span><span class="sxs-lookup"><span data-stu-id="08428-122">The greater the weight that is assigned to an input, the more important the value of that input is.</span></span> <span data-ttu-id="08428-123">As ponderações podem ser negativas, o que significa que a entrada pode inibir, em vez de favorecer, um resultado específico.</span><span class="sxs-lookup"><span data-stu-id="08428-123">Weights can be negative, which means that the input can inhibit, rather than favor, a specific result.</span></span>  
  
 <span data-ttu-id="08428-124">**Camada de saída:** Os neurônios de saída representam valores de atributo previsíveis para o modelo de Data Mining.</span><span class="sxs-lookup"><span data-stu-id="08428-124">**Output layer:** Output neurons represent predictable attribute values for the data mining model.</span></span>  
  
 <span data-ttu-id="08428-125">Para obter uma explicação detalhada de como as camadas de entrada, oculta e de saída são criadas e pontuadas, consulte [Referência técnica do algoritmo Rede Neural da Microsoft](microsoft-neural-network-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="08428-125">For a detailed explanation of how the input, hidden, and output layers are constructed and scored, see [Microsoft Neural Network Algorithm Technical Reference](microsoft-neural-network-algorithm-technical-reference.md).</span></span>  
  
## <a name="data-required-for-neural-network-models"></a><span data-ttu-id="08428-126">Dados necessários para modelos de rede neural</span><span class="sxs-lookup"><span data-stu-id="08428-126">Data Required for Neural Network Models</span></span>  
 <span data-ttu-id="08428-127">Um modelo de rede neural deve conter uma coluna de chave, uma ou mais colunas de entrada e uma ou mais colunas previsíveis.</span><span class="sxs-lookup"><span data-stu-id="08428-127">A neural network model must contain a key column, one or more input columns, and one or more predictable columns.</span></span>  
  
 <span data-ttu-id="08428-128">Os modelos de mineração de dados que usam o algoritmo Rede Neural da [!INCLUDE[msCoName](../../includes/msconame-md.md)] são amplamente influenciados pelos valores especificados para os parâmetros disponíveis para o algoritmo.</span><span class="sxs-lookup"><span data-stu-id="08428-128">Data mining models that use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Neural Network algorithm are heavily influenced by the values that you specify for the parameters that are available to the algorithm.</span></span> <span data-ttu-id="08428-129">Esses parâmetros definem como os dados são amostrados, são distribuídos ou estimados para serem distribuídos em cada coluna e quando a seleção de recurso é chamada para limitar os valores usados no modelo final.</span><span class="sxs-lookup"><span data-stu-id="08428-129">The parameters define how data is sampled, how data is distributed or expected to be distributed in each column, and when feature selection is invoked to limit the values that are used in the final model.</span></span>  
  
 <span data-ttu-id="08428-130">Para obter mais informações sobre como definir parâmetros para personalizar o comportamento do modelo, consulte [Referência técnica do algoritmo Rede Neural da Microsoft](microsoft-neural-network-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="08428-130">For more information about setting parameters to customize model behavior, see [Microsoft Neural Network Algorithm Technical Reference](microsoft-neural-network-algorithm-technical-reference.md).</span></span>  
  
## <a name="viewing-a-neural-network-model"></a><span data-ttu-id="08428-131">Exibindo um modelo de rede neural</span><span class="sxs-lookup"><span data-stu-id="08428-131">Viewing a Neural Network Model</span></span>  
 <span data-ttu-id="08428-132">Para trabalhar com os dados e verificar como o modelo correlaciona entradas com resultados, é possível usar o **Visualizador de Rede Neural da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="08428-132">To work with the data and see how the model correlates inputs with outputs, you can use the **Microsoft Neural Network Viewer**.</span></span> <span data-ttu-id="08428-133">Com esse visualizador personalizado, você pode filtrar os atributos de entrada e seus valores e visualizar gráficos que mostram como eles afetam os resultados.</span><span class="sxs-lookup"><span data-stu-id="08428-133">With this custom viewer, you can filter on input attributes and their values, and see graphs that show how they affect the outputs.</span></span> <span data-ttu-id="08428-134">As dicas de ferramentas no visualizador mostram a probabilidade e a comparação associadas a cada par de valores de entrada e de saída.</span><span class="sxs-lookup"><span data-stu-id="08428-134">The tooltips in the viewer show you the probability and lift associated with each pair of input and output values.</span></span> <span data-ttu-id="08428-135">Para obter mais informações, consulte [Procurar um modelo usando o Visualizador de Rede Neural da Microsoft](browse-a-model-using-the-microsoft-neural-network-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="08428-135">For more information, see [Browse a Model Using the Microsoft Neural Network Viewer](browse-a-model-using-the-microsoft-neural-network-viewer.md).</span></span>  
  
 <span data-ttu-id="08428-136">A maneira mais fácil de explorar a estrutura do modelo é usando o **Visualizador de Árvore de Conteúdo Genérica da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="08428-136">The easiest way to explore the structure of the model is to use the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="08428-137">É possível visualizar as entradas, os resultados e as redes criados pelo modelo e clicar em qualquer nó para expandi-lo e exibir as estatísticas relacionadas aos nós nas camadas de entrada, de saída e oculta.</span><span class="sxs-lookup"><span data-stu-id="08428-137">You can view the inputs, outputs, and networks created by the model, and click on any node to expand it and see statistics related to the input, output, or hidden layer nodes.</span></span> <span data-ttu-id="08428-138">Para obter mais informações, consulte [Procurar um modelo usando o Visualizador de Árvore de Conteúdo Genérico da Microsoft](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="08428-138">For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span></span>  
  
## <a name="creating-predictions"></a><span data-ttu-id="08428-139">Criando previsões</span><span class="sxs-lookup"><span data-stu-id="08428-139">Creating Predictions</span></span>  
 <span data-ttu-id="08428-140">Depois de processado o modelo, você pode usar a rede e as ponderações armazenadas em cada nó para fazer previsões.</span><span class="sxs-lookup"><span data-stu-id="08428-140">After the model has been processed, you can use the network and the weights stored within each node to make predictions.</span></span> <span data-ttu-id="08428-141">Um modelo de rede neural suporta regressão, associação e análise de classificação. Portanto, o significado de cada previsão pode ser diferente.</span><span class="sxs-lookup"><span data-stu-id="08428-141">A neural network model supports regression, association, and classification analysis, Therefore, the meaning of each prediction might be different.</span></span> <span data-ttu-id="08428-142">Você também pode consultar o próprio modelo para revisar as correlações que foram localizadas e recuperar estatísticas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="08428-142">You can also query the model itself, to review the correlations that were found and retrieve related statistics.</span></span> <span data-ttu-id="08428-143">Para obter exemplos de como criar consultas em um modelo de rede neural, consulte [Exemplos de consulta de modelo de rede neural](neural-network-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="08428-143">For examples of how to create queries against a neural network model, see [Neural Network Model Query Examples](neural-network-model-query-examples.md).</span></span>  
  
 <span data-ttu-id="08428-144">Para obter informações gerais sobre como criar uma consulta em um modelo de mineração de dados, consulte [Consultas de mineração de dados](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="08428-144">For general information about how to create a query on a data mining model, see [Data Mining Queries](data-mining-queries.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08428-145">Comentários</span><span class="sxs-lookup"><span data-stu-id="08428-145">Remarks</span></span>  
  
-   <span data-ttu-id="08428-146">Não suporta detalhamento ou dimensões de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="08428-146">Does not support drillthrough or data mining dimensions.</span></span> <span data-ttu-id="08428-147">Isso acontece porque a estrutura dos nós do modelo de mineração não corresponde diretamente aos dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="08428-147">This is because the structure of the nodes in the mining model does not necessarily correspond directly to the underlying data.</span></span>  
  
-   <span data-ttu-id="08428-148">Não suporta a criação de modelos no formato PMML (Predictive Model Markup Language).</span><span class="sxs-lookup"><span data-stu-id="08428-148">Does not support the creation of models in Predictive Model Markup Language (PMML) format.</span></span>  
  
-   <span data-ttu-id="08428-149">Suporta o uso de modelos de mineração OLAP.</span><span class="sxs-lookup"><span data-stu-id="08428-149">Supports the use of OLAP mining models.</span></span>  
  
-   <span data-ttu-id="08428-150">Não suporta a criação de dimensões de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="08428-150">Does not support the creation of data mining dimensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08428-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="08428-151">See Also</span></span>  
 <span data-ttu-id="08428-152">[Referência técnica do algoritmo rede neural da Microsoft](microsoft-neural-network-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="08428-152">[Microsoft Neural Network Algorithm Technical Reference](microsoft-neural-network-algorithm-technical-reference.md) </span></span>  
 <span data-ttu-id="08428-153">[Conteúdo do modelo de mineração para modelos de rede neural &#40;Analysis Services&#41;de mineração de dados](mining-model-content-for-neural-network-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="08428-153">[Mining Model Content for Neural Network Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-neural-network-models-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="08428-154">[Exemplos de consulta de modelo de rede neural](neural-network-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="08428-154">[Neural Network Model Query Examples](neural-network-model-query-examples.md) </span></span>  
 [<span data-ttu-id="08428-155">Algoritmo Regressão Logística da Microsoft</span><span class="sxs-lookup"><span data-stu-id="08428-155">Microsoft Logistic Regression Algorithm</span></span>](microsoft-logistic-regression-algorithm.md)  
  
  