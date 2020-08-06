---
title: Tutorial do DMX de cesta de mercado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- DMX [Analysis Services], tutorials
- data mining [Analysis Services], tutorials
- statements [DMX], tutorials
- Data Mining Extensions [Analysis Services], tutorials
- market basket analysis [Analysis Services]
- tutorials [Data Mining]
- tutorials [DMX]
ms.assetid: 6e262a1d-c89e-4033-8368-46cf25168ef5
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: fe12f1c4ca1c0946572c61e89f4f4edb8ba9a762
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683191"
---
# <a name="market-basket-dmx-tutorial"></a><span data-ttu-id="f82f4-102">Tutorial de DMX do Market Basket</span><span class="sxs-lookup"><span data-stu-id="f82f4-102">Market Basket DMX Tutorial</span></span>
  <span data-ttu-id="f82f4-103">Nesse tutorial, você aprenderá como criar, treinar e explorar modelos de mineração de dados, utilizando a linguagem de consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="f82f4-103">In this tutorial, you will learn how to create, train, and explore mining models by using the Data Mining Extensions (DMX) query language.</span></span> <span data-ttu-id="f82f4-104">Você então utilizará esses modelos de mineração de dados para criar previsões que descrevem quais produtos tendem a ser adquiridos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f82f4-104">You will then use these mining models to create predictions that describe which products tend to be purchased at the same time.</span></span>  
  
 <span data-ttu-id="f82f4-105">Os modelos de mineração serão criados a partir dos dados contidos no banco de dados de exemplo [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] , que armazena dados para a empresa fictícia [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f82f4-105">The mining models will be created from the data contained in the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database, which stores data for the fictitious company [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)].</span></span> [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] <span data-ttu-id="f82f4-106">é uma grande empresa industrial e multinacional.</span><span class="sxs-lookup"><span data-stu-id="f82f4-106">is a large, multinational manufacturing company.</span></span> <span data-ttu-id="f82f4-107">A empresa fabrica e vende bicicletas de metal e compostas para os mercados norte-americano, europeu e asiático.</span><span class="sxs-lookup"><span data-stu-id="f82f4-107">The company manufactures and sells metal and composite bicycles to North American, European, and Asian commercial markets.</span></span> <span data-ttu-id="f82f4-108">Suas operações principais estão situadas em Bothell, Washington, com 290 funcionários, e tem várias equipes regionais de vendas distribuídas por toda a sua base de mercado internacional.</span><span class="sxs-lookup"><span data-stu-id="f82f4-108">Its base operation is located in Bothell, Washington, with 290 employees, and it has several regional sales teams are located throughout their international market base.</span></span>  
  
## <a name="tutorial-scenario"></a><span data-ttu-id="f82f4-109">Cenário do tutorial</span><span class="sxs-lookup"><span data-stu-id="f82f4-109">Tutorial Scenario</span></span>  
 [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] <span data-ttu-id="f82f4-110">decidiu criar um aplicativo personalizado que utilize a funcionalidade de mineração de dados para prever que tipos de produtos seus clientes tendem a comprar ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f82f4-110">has decided to create a custom application that employs data mining functionality to predict what types of products their customers tend to purchase at the same time.</span></span> <span data-ttu-id="f82f4-111">A meta do aplicativo personalizado é poder especificar um conjunto de produtos e prever quais produtos adicionais serão adquiridos com os produtos especificados.</span><span class="sxs-lookup"><span data-stu-id="f82f4-111">The goal for the custom application is to be able to specify a set of products, and predict what additional products will be purchased with the specified products.</span></span> <span data-ttu-id="f82f4-112">O [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] usará essas informações para adicionar um recurso de "sugestão" a seu site, e também para organizar melhor a maneira como as informações são apresentadas a seus clientes.</span><span class="sxs-lookup"><span data-stu-id="f82f4-112">[!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] will then use this information to add a "suggest" feature to their website, and also to better organize the way that they present information to their customers.</span></span>  
  
 [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="f82f4-113">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] fornece várias ferramentas que podem ser usadas para realizar essa tarefa:</span><span class="sxs-lookup"><span data-stu-id="f82f4-113">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides several tools that can be used to accomplish this task:</span></span>  
  
-   <span data-ttu-id="f82f4-114">A linguagem de consulta DMX</span><span class="sxs-lookup"><span data-stu-id="f82f4-114">The DMX query language</span></span>  
  
-   <span data-ttu-id="f82f4-115">O [algoritmo de associação da Microsoft](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md)</span><span class="sxs-lookup"><span data-stu-id="f82f4-115">The [Microsoft Association Algorithm](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md)</span></span>  
  
-   <span data-ttu-id="f82f4-116">Editor de Consultas do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f82f4-116">Query Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]</span></span>  
  
 <span data-ttu-id="f82f4-117">DMX (Extensões de Mineração de Dados) é uma linguagem de consulta fornecida por [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que pode ser usada para criar e trabalhar com modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="f82f4-117">Data Mining Extensions (DMX) is a query language provided by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you can use to create and work with mining models.</span></span> <span data-ttu-id="f82f4-118">O [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo de associação cria modelos que podem prever os produtos que provavelmente serão comprados juntos.</span><span class="sxs-lookup"><span data-stu-id="f82f4-118">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm creates models that can predict the products that are likely to be purchased together.</span></span>  
  
 <span data-ttu-id="f82f4-119">O objetivo deste tutorial é fornecer as consultas DMX que serão usadas no aplicativo personalizado.</span><span class="sxs-lookup"><span data-stu-id="f82f4-119">The goal of this tutorial is to provide the DMX queries that will be used in the custom application.</span></span>  
  
 <span data-ttu-id="f82f4-120">**Para obter mais informações: soluções de mineração de** [dados](../../2014/analysis-services/data-mining/data-mining-solutions.md)</span><span class="sxs-lookup"><span data-stu-id="f82f4-120">**For more information:** [Data Mining Solutions](../../2014/analysis-services/data-mining/data-mining-solutions.md)</span></span>  
  
## <a name="mining-structure-and-mining-models"></a><span data-ttu-id="f82f4-121">Estrutura de mineração e modelos de mineração</span><span class="sxs-lookup"><span data-stu-id="f82f4-121">Mining Structure and Mining Models</span></span>  
 <span data-ttu-id="f82f4-122">Antes de começar a criar instruções DMX, é importante compreender os objetos principais que o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] usa para criar modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="f82f4-122">Before you begin to create DMX statements, it is important to understand the main objects that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to create mining models.</span></span> <span data-ttu-id="f82f4-123">A *estrutura de mineração* é uma estrutura de dados que define o domínio de dados do qual os modelos de mineração são criados.</span><span class="sxs-lookup"><span data-stu-id="f82f4-123">The *mining structure* is a data structure that defines the data domain from which mining models are built.</span></span> <span data-ttu-id="f82f4-124">Uma única estrutura de mineração pode conter vários *modelos de mineração* que compartilham o mesmo domínio.</span><span class="sxs-lookup"><span data-stu-id="f82f4-124">A single mining structure can contain multiple *mining models* that share the same domain.</span></span> <span data-ttu-id="f82f4-125">Um modelo de mineração aplica um algoritmo de modelo de mineração aos dados que são representados por uma estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="f82f4-125">A mining model applies a mining model algorithm to the data, which is represented by a mining structure.</span></span>  
  
 <span data-ttu-id="f82f4-126">Os blocos de construção da estrutura de mineração são as colunas da estrutura de mineração, que descrevem os dados que a fonte de dados contém.</span><span class="sxs-lookup"><span data-stu-id="f82f4-126">The building blocks of the mining structure are the mining structure columns, which describe the data that the data source contains.</span></span> <span data-ttu-id="f82f4-127">Essas colunas contêm informações como tipo de dados, tipo de conteúdo e como os dados são distribuídos.</span><span class="sxs-lookup"><span data-stu-id="f82f4-127">These columns contain information such as data type, content type, and how the data is distributed.</span></span>  
  
 <span data-ttu-id="f82f4-128">Os modelos de mineração devem conter a coluna de chave descrita na estrutura de mineração, bem como um subconjunto das colunas restantes.</span><span class="sxs-lookup"><span data-stu-id="f82f4-128">Mining models must contain the key column described in the mining structure, as well as a subset of the remaining columns.</span></span> <span data-ttu-id="f82f4-129">O modelo de mineração define o uso para cada coluna e define o algoritmo que é utilizado para criar o modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="f82f4-129">The mining model defines the usage for each column and defines the algorithm that is used to create the mining model.</span></span> <span data-ttu-id="f82f4-130">Por exemplo, em DMX você pode especificar que uma coluna é uma coluna de chave ou uma coluna PREDICT.</span><span class="sxs-lookup"><span data-stu-id="f82f4-130">For example, in DMX you can specify that a column is a Key column or a PREDICT column.</span></span> <span data-ttu-id="f82f4-131">Se uma coluna não for especificada, será assumido que é uma coluna de entrada.</span><span class="sxs-lookup"><span data-stu-id="f82f4-131">If a column is left unspecified, it is assumed to be an input column.</span></span>  
  
 <span data-ttu-id="f82f4-132">Em DMX, há dois modos para criar modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="f82f4-132">In DMX, there are two ways to create mining models.</span></span> <span data-ttu-id="f82f4-133">Você pode criar a estrutura de mineração e o modelo de mineração associado juntos utilizando a instrução `CREATE MINING MODEL`, ou pode criar primeiro uma estrutura de mineração utilizando a instrução `CREATE MINING STRUCTURE` e, em seguida, adicionar um modelo de mineração à estrutura utilizando a instrução `ALTER STRUCTURE`.</span><span class="sxs-lookup"><span data-stu-id="f82f4-133">You can either create the mining structure and associated mining model together by using the `CREATE MINING MODEL` statement, or you can first create a mining structure by using the `CREATE MINING STRUCTURE` statement, and then add a mining model to the structure by using the `ALTER STRUCTURE` statement.</span></span> <span data-ttu-id="f82f4-134">Estes métodos são descritos abaixo.</span><span class="sxs-lookup"><span data-stu-id="f82f4-134">These methods are described below.</span></span>  
  
 `CREATE MINING MODEL`  
 <span data-ttu-id="f82f4-135">Use esta instrução para criar juntos uma estrutura de mineração e um modelo de mineração associado que usa o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="f82f4-135">Use this statement to create a mining structure and associated mining model together using the same name.</span></span> <span data-ttu-id="f82f4-136">O nome de modelo de mineração é acrescentado com "Structure" para diferenciá-lo da estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="f82f4-136">The mining model name is appended with "Structure" to differentiate it from the mining structure.</span></span>  
  
 <span data-ttu-id="f82f4-137">Esta instrução será útil se você estiver criando uma estrutura de mineração que conterá um único modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="f82f4-137">This statement is useful if you are creating a mining structure that will contain a single mining model.</span></span>  
  
 <span data-ttu-id="f82f4-138">Para obter mais informações, consulte [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx).</span><span class="sxs-lookup"><span data-stu-id="f82f4-138">For more information, see [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx).</span></span>  
  
 <span data-ttu-id="f82f4-139">CRIAR UMA ESTRUTURA DE MINERAÇÃO</span><span class="sxs-lookup"><span data-stu-id="f82f4-139">CREATE MINING STRUCTURE</span></span>  
 <span data-ttu-id="f82f4-140">Use essa declaração para criar uma nova estrutura de mineração sem-modelos.</span><span class="sxs-lookup"><span data-stu-id="f82f4-140">Use this statement to create a new mining structure without any models.</span></span>  
  
 <span data-ttu-id="f82f4-141">Ao usar CREATE MINING STRUCTURE, você também poderá criar um conjunto de dados de validação que poderá ser usado para teste de modelos baseados na mesma estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="f82f4-141">When you use CREATE MINING STRUCTURE, you can also create a holdout data set that can be used for testing any models that are based on the same mining structure.</span></span>  
  
 <span data-ttu-id="f82f4-142">Para obter mais informações, consulte [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx).</span><span class="sxs-lookup"><span data-stu-id="f82f4-142">For more information, see [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx).</span></span>  
  
 `ALTER MINING STRUCTURE`  
 <span data-ttu-id="f82f4-143">Use esta instrução para acrescentar um modelo de mineração a uma estrutura de mineração que já existe no servidor.</span><span class="sxs-lookup"><span data-stu-id="f82f4-143">Use this statement to add a mining model to a mining structure that already exists on the server.</span></span>  
  
 <span data-ttu-id="f82f4-144">Há várias razões pelas quais você deseja adicionar mais de um modelo de mineração em uma única estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="f82f4-144">There are several reasons that you would want to add more than one mining model in a single mining structure.</span></span> <span data-ttu-id="f82f4-145">Por exemplo, você poderia criar vários modelos de mineração utilizando algoritmos diferentes para ver qual trabalha melhor.</span><span class="sxs-lookup"><span data-stu-id="f82f4-145">For example, you might create several mining models using different algorithms to see which one works best.</span></span> <span data-ttu-id="f82f4-146">Como alternativa, você poderia criar vários modelos de mineração usando o mesmo algoritmo, mas com um conjunto de parâmetros definido de modo diferente para cada modelo de mineração a fim de encontrar a melhor definição para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="f82f4-146">Alternatively, you might create several mining models using the same algorithm, but with a parameter set differently for each mining model to find the best setting for that parameter.</span></span>  
  
 <span data-ttu-id="f82f4-147">Para obter mais informações, consulte [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016).</span><span class="sxs-lookup"><span data-stu-id="f82f4-147">For more information, see [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016).</span></span>  
  
 <span data-ttu-id="f82f4-148">Como você criará uma estrutura que contém vários modelos de mineração, utilizará o método secundário neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="f82f4-148">Because you will create a mining structure that contains several mining models, you will use the second method in this tutorial.</span></span>  
  
 <span data-ttu-id="f82f4-149">**Para obter mais informações**</span><span class="sxs-lookup"><span data-stu-id="f82f4-149">**For More Information**</span></span>  
  
 <span data-ttu-id="f82f4-150">[As extensões de mineração de dados &#40;referência&#41; DMX](/sql/dmx/data-mining-extensions-dmx-reference), [compreendendo a instrução DMX SELECT](/sql/dmx/understanding-the-dmx-select-statement), a [estrutura e o uso de consultas de previsão DMX](/sql/dmx/structure-and-usage-of-dmx-prediction-queries)</span><span class="sxs-lookup"><span data-stu-id="f82f4-150">[Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference), [Understanding the DMX Select Statement](/sql/dmx/understanding-the-dmx-select-statement), [Structure and Usage of DMX Prediction Queries](/sql/dmx/structure-and-usage-of-dmx-prediction-queries)</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="f82f4-151">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="f82f4-151">What You Will Learn</span></span>  
 <span data-ttu-id="f82f4-152">Ele se divide nas lições a seguir:</span><span class="sxs-lookup"><span data-stu-id="f82f4-152">This tutorial is divided into the following lessons:</span></span>  
  
 [<span data-ttu-id="f82f4-153">Lição 1: Criando a estrutura de mineração do Market Basket</span><span class="sxs-lookup"><span data-stu-id="f82f4-153">Lesson 1: Creating the Market Basket Mining Structure</span></span>](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md)  
 <span data-ttu-id="f82f4-154">Nesta lição, você aprenderá a usar a instrução `CREATE` para criar estruturas de mineração.</span><span class="sxs-lookup"><span data-stu-id="f82f4-154">In this lesson, you will learn how to use the `CREATE` statement to create mining structures.</span></span>  
  
 [<span data-ttu-id="f82f4-155">Lição 2: Adicionando modelos de mineração à estrutura de mineração do Market Basket</span><span class="sxs-lookup"><span data-stu-id="f82f4-155">Lesson 2: Adding Mining Models to the Market Basket Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md)  
 <span data-ttu-id="f82f4-156">Nesta lição, você aprenderá a usar a instrução `ALTER` para adicionar modelos de mineração a uma estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="f82f4-156">In this lesson, you will learn how to use the `ALTER` statement to add mining models to a mining structure.</span></span>  
  
 [<span data-ttu-id="f82f4-157">Lição 3: Processando a estrutura de mineração do Market Basket</span><span class="sxs-lookup"><span data-stu-id="f82f4-157">Lesson 3: Processing the Market Basket Mining Structure</span></span>](../../2014/tutorials/lesson-3-processing-the-market-basket-mining-structure.md)  
 <span data-ttu-id="f82f4-158">Nesta lição, você aprenderá a usar a instrução `INSERT INTO` para processar estruturas de mineração e seus modelos de mineração associados.</span><span class="sxs-lookup"><span data-stu-id="f82f4-158">In this lesson, you will learn how to use the `INSERT INTO` statement to process mining structures and their associated mining models.</span></span>  
  
 [<span data-ttu-id="f82f4-159">Lição 4: Executando previsões de Market Basket</span><span class="sxs-lookup"><span data-stu-id="f82f4-159">Lesson 4: Executing Market Basket Predictions</span></span>](../../2014/tutorials/lesson-4-executing-market-basket-predictions.md)  
 <span data-ttu-id="f82f4-160">Nesta lição, você aprenderá a usar a instrução `PREDICTION JOIN` para criar previsões em relação aos modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="f82f4-160">In this lesson, you will learn how to use the `PREDICTION JOIN` statement to create predictions against mining models.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f82f4-161">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f82f4-161">Requirements</span></span>  
 <span data-ttu-id="f82f4-162">Antes de fazer este tutorial, verifique se os seguintes itens estão instalados:</span><span class="sxs-lookup"><span data-stu-id="f82f4-162">Before doing this tutorial, make sure that the following are installed:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="f82f4-163">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f82f4-163">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="f82f4-164">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f82f4-164">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="f82f4-165">O banco de dados [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f82f4-165">The [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database</span></span>  
  
 <span data-ttu-id="f82f4-166">Por padrão, e para reforçar a segurança, os bancos de dados de exemplo não são instalados.</span><span class="sxs-lookup"><span data-stu-id="f82f4-166">By default, the sample databases are not installed, to enhance security.</span></span> <span data-ttu-id="f82f4-167">Para instalar os bancos de dados de exemplo oficiais do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vá para [http://www.CodePlex.com/MSFTDBProdSamples](https://go.microsoft.com/fwlink/?LinkId=88417) ou no Microsoft SQL Server exemplos e projetos da Comunidade home page na seção Microsoft SQL Server exemplos de produto.</span><span class="sxs-lookup"><span data-stu-id="f82f4-167">To install the official sample databases for [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], go to [http://www.CodePlex.com/MSFTDBProdSamples](https://go.microsoft.com/fwlink/?LinkId=88417) or on the Microsoft SQL Server Samples and Community Projects home page in the section Microsoft SQL Server Product Samples.</span></span> <span data-ttu-id="f82f4-168">Clique em **Bancos de Dados**e, em seguida, clique na guia **Releases** e selecione o banco de dados desejado.</span><span class="sxs-lookup"><span data-stu-id="f82f4-168">Click **Databases**, then click the **Releases** tab and select the databases that you want.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f82f4-169">Ao examinar os tutoriais, recomendamos que você adicione os botões **Próximo Tópico** e **Tópico Anterior** à barra de ferramentas do visualizador de documentos.</span><span class="sxs-lookup"><span data-stu-id="f82f4-169">When you review tutorials, we recommend that you add **Next topic** and **Previous topic** buttons to the document viewer toolbar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f82f4-170">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f82f4-170">See Also</span></span>  
 <span data-ttu-id="f82f4-171">[Tutorial DMX do comprador de bicicletas](../../2014/tutorials/bike-buyer-dmx-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="f82f4-171">[Bike Buyer DMX Tutorial](../../2014/tutorials/bike-buyer-dmx-tutorial.md) </span></span>  
 <span data-ttu-id="f82f4-172">[Tutorial de mineração de dados básico](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="f82f4-172">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="f82f4-173">Lição 3: Criando um cenário de cesta de compras &#40;Tutorial intermediário de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="f82f4-173">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
  