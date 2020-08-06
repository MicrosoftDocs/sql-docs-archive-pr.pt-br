---
title: Editor da tarefa consulta de mineração de dados (guia modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dmquerytask.miningmodel.f1
helpviewer_keywords:
- Data Mining Query Task Editor
ms.assetid: 0ede9b86-be27-471e-b012-22a65adce579
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 794365c8d15ff9725fc385bb43d51e70ffa529b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681812"
---
# <a name="data-mining-query-task-editor-mining-model-tab"></a><span data-ttu-id="df97f-102">Editor da Tarefa Consulta de Mineração de Dados (guia Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="df97f-102">Data Mining Query Task Editor (Mining Model Tab)</span></span>
  <span data-ttu-id="df97f-103">Use a guia **Modelo de Mineração** da caixa de diálogo **Tarefa Consulta de Mineração de Dados** para especificar a estrutura e o modelo de mineração a serem usados.</span><span class="sxs-lookup"><span data-stu-id="df97f-103">Use the **Mining Model** tab of the **Data Mining Query Task** dialog box to specify the mining structure and mining model to use.</span></span>  
  
 <span data-ttu-id="df97f-104">Para saber mais sobre como implementar a mineração de dados em pacotes, consulte [Tarefa Consulta de mineração de dados](control-flow/data-mining-query-task.md) e [Soluções de mineração de dados](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span><span class="sxs-lookup"><span data-stu-id="df97f-104">To learn about implementing data mining in packages, see [Data Mining Query Task](control-flow/data-mining-query-task.md) and [Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="df97f-105">Opções gerais</span><span class="sxs-lookup"><span data-stu-id="df97f-105">General Options</span></span>  
 <span data-ttu-id="df97f-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="df97f-106">**Name**</span></span>  
 <span data-ttu-id="df97f-107">Forneça um nome exclusivo para a tarefa Consulta de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="df97f-107">Provide a unique name for the Data Mining Query task.</span></span> <span data-ttu-id="df97f-108">Esse nome é usado como rótulo no ícone de tarefa.</span><span class="sxs-lookup"><span data-stu-id="df97f-108">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="df97f-109">Os nomes das tarefas devem ser exclusivos em um pacote.</span><span class="sxs-lookup"><span data-stu-id="df97f-109">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="df97f-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="df97f-110">**Description**</span></span>  
 <span data-ttu-id="df97f-111">Digite uma descrição para a tarefa Consulta de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="df97f-111">Type a description of the Data Mining Query task.</span></span>  
  
## <a name="mining-model-tab-options"></a><span data-ttu-id="df97f-112">Opções da guia Modelo de Mineração</span><span class="sxs-lookup"><span data-stu-id="df97f-112">Mining Model Tab Options</span></span>  
 <span data-ttu-id="df97f-113">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="df97f-113">**Connection**</span></span>  
 <span data-ttu-id="df97f-114">Selecione um gerenciador de conexões do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] na lista, ou clique em **Novo** para criar um novo gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="df97f-114">Select an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] connection manager in the list or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="df97f-115">**Tópicos relacionados:**  [Gerenciador de conexões do Analysis Services](connection-manager/analysis-services-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="df97f-115">**Related Topics:**  [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md)</span></span>  
  
 <span data-ttu-id="df97f-116">**Novo**</span><span class="sxs-lookup"><span data-stu-id="df97f-116">**New**</span></span>  
 <span data-ttu-id="df97f-117">Crie um novo gerenciador de conexões do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df97f-117">Create a new [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] connection manager.</span></span>  
  
 <span data-ttu-id="df97f-118">**Tópicos relacionados:** [Referência da interface do usuário da caixa de diálogo Adicionar Gerenciador de Conexões do Analysis Services](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span><span class="sxs-lookup"><span data-stu-id="df97f-118">**Related Topics:** [Add Analysis Services Connection Manager Dialog Box UI Reference](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span></span>  
  
 <span data-ttu-id="df97f-119">**Estrutura de mineração**</span><span class="sxs-lookup"><span data-stu-id="df97f-119">**Mining structure**</span></span>  
 <span data-ttu-id="df97f-120">Selecione uma estrutura de mineração na lista.</span><span class="sxs-lookup"><span data-stu-id="df97f-120">Select a mining structure in the list.</span></span>  
  
 <span data-ttu-id="df97f-121">**Modelos de mineração**</span><span class="sxs-lookup"><span data-stu-id="df97f-121">**Mining models**</span></span>  
 <span data-ttu-id="df97f-122">Selecione um modelo de mineração com base na estrutura de mineração selecionada.</span><span class="sxs-lookup"><span data-stu-id="df97f-122">Select a mining model built on the selected mining structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df97f-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="df97f-123">See Also</span></span>  
 <span data-ttu-id="df97f-124">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="df97f-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="df97f-125">[Editor da tarefa consulta de mineração de dados &#40;guia consulta&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span><span class="sxs-lookup"><span data-stu-id="df97f-125">[Data Mining Query Task Editor &#40;Query Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span></span>  
 <span data-ttu-id="df97f-126">[Editor da tarefa consulta de mineração de dados &#40;guia saída&#41;](../../2014/integration-services/data-mining-query-task-editor-output-tab.md) </span><span class="sxs-lookup"><span data-stu-id="df97f-126">[Data Mining Query Task Editor &#40;Output Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-output-tab.md) </span></span>  
 [<span data-ttu-id="df97f-127">Data Mining Designer</span><span class="sxs-lookup"><span data-stu-id="df97f-127">Data Mining Designer</span></span>](https://docs.microsoft.com/analysis-services/data-mining/data-mining-designer)  
  
  
