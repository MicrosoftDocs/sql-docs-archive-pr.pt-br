---
title: 'Tarefa 2: testando e publicando a política de correspondência | Microsoft Docs'
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: e1ffb6d7-fbc5-4695-b538-cc2302d1a17d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 88bed2e91ca1fee3eab6136fb94df0d13328dc80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581644"
---
# <a name="task-2-testing-and-publishing-the-matching-policy"></a><span data-ttu-id="0fab5-102">Tarefa 2: Testando e publicando a política de correspondência</span><span class="sxs-lookup"><span data-stu-id="0fab5-102">Task 2: Testing and Publishing the Matching Policy</span></span>
  <span data-ttu-id="0fab5-103">Nesta tarefa, você testará e publicará a política de correspondência **remover fornecedores duplicados** .</span><span class="sxs-lookup"><span data-stu-id="0fab5-103">In this task, you test and publish the **Remove Duplicate Suppliers** matching policy.</span></span>  
  
1.  <span data-ttu-id="0fab5-104">Na página **resultados da correspondência** , clique em **Iniciar** para testar a política inteira.</span><span class="sxs-lookup"><span data-stu-id="0fab5-104">In the **Matching Results** page, click **Start** to test the entire policy.</span></span> <span data-ttu-id="0fab5-105">No seu caso, você tem uma única regra na política; portanto, os resultados do teste da regra e da política devem ser os mesmos.</span><span class="sxs-lookup"><span data-stu-id="0fab5-105">In your case, you have only rule in the policy, so the results from testing the rule and the policy should be the same.</span></span>  
  
2.  <span data-ttu-id="0fab5-106">Revise todos os registros correspondentes e sua pontuação na caixa de listagem.</span><span class="sxs-lookup"><span data-stu-id="0fab5-106">Review all the matched records and their matching score in the list box.</span></span> <span data-ttu-id="0fab5-107">Um registro que tem um ícone **verde** associado a ele é uma duplicata do registro dinâmico que o precede.</span><span class="sxs-lookup"><span data-stu-id="0fab5-107">A record that has a **Green** icon associated with it is a duplicate of the pivot record that precedes it.</span></span> <span data-ttu-id="0fab5-108">Aqui estão os pares de exemplos:</span><span class="sxs-lookup"><span data-stu-id="0fab5-108">Here are couple of examples:</span></span>  
  
    1.  <span data-ttu-id="0fab5-109">O registro com **ID de registro: 1000005** é uma correspondência do registro com a **ID de registro: 1000004** com **Pontuação: 100%** porque ambos os registros têm os mesmos valores para **CódigoDoFornecedor (pré-requisito)**, **nome do fornecedor**e **colunas ContactEmailAddress**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-109">The record with **Record ID: 1000005** is a match of the record with **Record Id: 1000004** with **Score: 100%** because both the records have the same values for **SupplierID (prerequisite)**, **Supplier Name**, and **ContactEmailAddress columns**.</span></span> <span data-ttu-id="0fab5-110">O DQS escolherá aleatoriamente um registro como registro dinâmico de um cluster.</span><span class="sxs-lookup"><span data-stu-id="0fab5-110">DQS randomly picks a record as the pivot record for a cluster.</span></span>  
  
    2.  <span data-ttu-id="0fab5-111">O registro **1000023** é uma correspondência do registro **1000022** com a pontuação de correspondência: 93% porque os dois registros têm os mesmos valores para as colunas **CódigoDoFornecedor (pré-requisito)** e **nome do fornecedor** , mas valores diferentes para a coluna **ContactEmailAddress** .</span><span class="sxs-lookup"><span data-stu-id="0fab5-111">The record **1000023** is a match of the record **1000022** with the matching score: 93% because the two records have the same values for **SupplierID (prerequisite)** and **Supplier Name** columns, but different values for the **ContactEmailAddress** column.</span></span>  
  
    3.  <span data-ttu-id="0fab5-112">Role até a parte inferior da lista para ver dois registros com IDs de registros: **1000051** e **1000052**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-112">Scroll to the bottom of the list to see two records with records IDs: **1000051** and **1000052**.</span></span> <span data-ttu-id="0fab5-113">O registro **1000052** é considerado uma correspondência com a pontuação de correspondência **91%** porque os dois registros têm os mesmos valores para as colunas **CódigoDoFornecedor** e **ContactEmailAddress** , mas valores diferentes para a coluna **nome do fornecedor** .</span><span class="sxs-lookup"><span data-stu-id="0fab5-113">Record **1000052** is considered a match with matching score **91%** because the two records have the same values for the **SupplierID** and **ContactEmailAddress** columns, but different values for the **Supplier Name** column.</span></span>  
  
     <span data-ttu-id="0fab5-114">![Definição de Políticas - Resultados de Políticas](../../2014/tutorials/media/et-testingandpublishingthematchingpolicy-01.jpg "Definição de Políticas - Resultados de Políticas")</span><span class="sxs-lookup"><span data-stu-id="0fab5-114">![Policy Definition - Policy Results](../../2014/tutorials/media/et-testingandpublishingthematchingpolicy-01.jpg "Policy Definition - Policy Results")</span></span>  
  
3.  <span data-ttu-id="0fab5-115">Clique com o botão direito do mouse em qualquer registro correspondente (com o ícone verde) e clique em **Exibir detalhes** para ver mais detalhes sobre a correspondência, como contribuição de cada Pontuação de campo, para a pontuação de correspondência geral.</span><span class="sxs-lookup"><span data-stu-id="0fab5-115">Right-click on any matched record (with green icon) and click **View Details** to see more details about the matching such as contribution of each field score to the overall matching score.</span></span>  
  
     <span data-ttu-id="0fab5-116">![Caixa de diálogo Detalhes de Pontuação Correspondente](../../2014/tutorials/media/et-testingandpublishingthematchingpolicy-02.jpg "Caixa de diálogo Detalhes de Pontuação Correspondente")</span><span class="sxs-lookup"><span data-stu-id="0fab5-116">![Matching Score Details Dialog Box](../../2014/tutorials/media/et-testingandpublishingthematchingpolicy-02.jpg "Matching Score Details Dialog Box")</span></span>  
  
4.  <span data-ttu-id="0fab5-117">Clique em **fechar** para fechar a caixa de diálogo **detalhes da Pontuação de correspondência** .</span><span class="sxs-lookup"><span data-stu-id="0fab5-117">Click **Close** to close the **Matching Score Details** dialog box.</span></span>  
  
5.  <span data-ttu-id="0fab5-118">Clique na guia **resultados de correspondência** na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="0fab5-118">Click **Matching Results** tab at the bottom of the page.</span></span> <span data-ttu-id="0fab5-119">Essa guia fornece detalhes como o número de registros correspondentes, o número de registros não correspondentes, o número de clusters com registros correspondentes, o tamanho médio do cluster, o tamanho mínimo do cluster e o tamanho máximo do cluster.</span><span class="sxs-lookup"><span data-stu-id="0fab5-119">This tab gives you detail such as number of matched records, number of unmatched records, number of clusters with matched records, the average cluster size, minimum cluster size, and maximum cluster size.</span></span> <span data-ttu-id="0fab5-120">Consulte [criar uma política de correspondência](https://msdn.microsoft.com/library/hh270290.aspx) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="0fab5-120">See [Create a Matching Policy](https://msdn.microsoft.com/library/hh270290.aspx) for more details.</span></span> <span data-ttu-id="0fab5-121">Não é possível exportar resultados dessa atividade.</span><span class="sxs-lookup"><span data-stu-id="0fab5-121">You cannot export results from this activity.</span></span> <span data-ttu-id="0fab5-122">Você está apenas definindo uma política de correspondência usando os dados de exemplo para testar as regras e a política com base nesses dados.</span><span class="sxs-lookup"><span data-stu-id="0fab5-122">You are just defining a matching policy by using the sample data to test rules and the policy against the sample data.</span></span>  
  
     <span data-ttu-id="0fab5-123">![Guia Resultados Correspondentes](../../2014/tutorials/media/et-testingandpublishingthematchingpolicy-03.jpg "Guia Resultados Correspondentes")</span><span class="sxs-lookup"><span data-stu-id="0fab5-123">![Matching Results Tab](../../2014/tutorials/media/et-testingandpublishingthematchingpolicy-03.jpg "Matching Results Tab")</span></span>  
  
6.  <span data-ttu-id="0fab5-124">Clique em **concluir** para concluir a criação da política de correspondência.</span><span class="sxs-lookup"><span data-stu-id="0fab5-124">Click **Finish** to finish creating the matching policy.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0fab5-125">Você definiu a política de correspondência aqui; portanto, não é possível exportar resultados para um arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="0fab5-125">You have defined the matching policy here; therefore you cannot export results to an output file.</span></span> <span data-ttu-id="0fab5-126">Você usou basicamente um arquivo de entrada de exemplo, criou regras e testou as regras e a política com base nos dados de exemplo com o objetivo de definir a política.</span><span class="sxs-lookup"><span data-stu-id="0fab5-126">You basically used a sample input file, created rules, and tested the rules and policy against the sample data with the goal of defining the policy.</span></span>  
  
7.  <span data-ttu-id="0fab5-127">Na caixa de diálogo SQL Server Data Quality Services, clique em **publicar** e clique em **OK** na caixa de mensagem.</span><span class="sxs-lookup"><span data-stu-id="0fab5-127">In the SQL Server Data Quality Services dialog box, click **Publish** and click **OK** on the message box.</span></span> <span data-ttu-id="0fab5-128">Agora, a política de correspondência que você definiu é publicada na base de dados de conhecimento dos **fornecedores** .</span><span class="sxs-lookup"><span data-stu-id="0fab5-128">Now, the matching policy you defined is published into the **Suppliers** Knowledge Base.</span></span> <span data-ttu-id="0fab5-129">Você pode usar a base de dados de conhecimento para executar o processo de correspondência com base em um arquivo de entrada, a fim de identificar e remover duplicatas.</span><span class="sxs-lookup"><span data-stu-id="0fab5-129">You can use the knowledge base to run the matching process against an input file to identify and remove duplicates.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="0fab5-130">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="0fab5-130">Next Step</span></span>  
 [<span data-ttu-id="0fab5-131">Tarefa 3: Criando e executando um projeto de qualidade de dados para correspondência</span><span class="sxs-lookup"><span data-stu-id="0fab5-131">Task 3: Creating and Running a Data Quality Project for Matching</span></span>](../../2014/tutorials/task-3-creating-and-running-a-data-quality-project-for-matching.md)  
  
  