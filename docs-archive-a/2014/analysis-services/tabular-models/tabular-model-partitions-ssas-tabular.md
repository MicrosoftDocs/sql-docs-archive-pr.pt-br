---
title: Partições de modelo de tabela (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.ssms.partitions.partitionmgr.imbi.f1
ms.assetid: 041c269f-a229-4a41-8794-6ba4b014ef83
author: minewiskan
ms.author: owend
ms.openlocfilehash: 58712523c3a47bffa7db9d5b32b62f8bef15166c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684354"
---
# <a name="tabular-model-partitions-ssas-tabular"></a><span data-ttu-id="16493-102">Partições de modelo tabular (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="16493-102">Tabular Model Partitions (SSAS Tabular)</span></span>
  <span data-ttu-id="16493-103">As partições dividem uma tabela em partes lógicas.</span><span class="sxs-lookup"><span data-stu-id="16493-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="16493-104">Cada partição pode ser processada (Atualizada) independentemente de outras partições.</span><span class="sxs-lookup"><span data-stu-id="16493-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="16493-105">As partições definidas para um modelo durante a criação de modelo são duplicadas em um modelo implantado.</span><span class="sxs-lookup"><span data-stu-id="16493-105">Partitions defined for a model during model authoring are duplicated in a deployed model.</span></span> <span data-ttu-id="16493-106">Uma vez implantado, você pode gerenciar essas partições e pode criar novas partições usando a caixa de diálogo **Partições** no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou usando um script.</span><span class="sxs-lookup"><span data-stu-id="16493-106">Once deployed, you can manage those partitions and create new partitions by using the **Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or by using a script.</span></span> <span data-ttu-id="16493-107">As informações fornecidas neste tópico descrevem partições em um banco de dados modelo tabular implantado.</span><span class="sxs-lookup"><span data-stu-id="16493-107">Information provided in this topic describes partitions in a deployed tabular model database.</span></span> <span data-ttu-id="16493-108">Para obter mais informações sobre como criar e gerenciar partições durante a criação de um modelo, consulte [Partições &#40;SSAS de Tabela&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="16493-108">For more information about creating and managing partitions during model authoring, see [Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="16493-109">Seções neste tópico:</span><span class="sxs-lookup"><span data-stu-id="16493-109">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="16493-110">Benefícios</span><span class="sxs-lookup"><span data-stu-id="16493-110">Benefits</span></span>](#bkmk_benefits)  
  
-   [<span data-ttu-id="16493-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="16493-111">Permissions</span></span>](#bkmk_permissions)  
  
-   [<span data-ttu-id="16493-112">Processar partições</span><span class="sxs-lookup"><span data-stu-id="16493-112">Process Partitions</span></span>](#bkmk_process_partitions)  
  
-   [<span data-ttu-id="16493-113">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="16493-113">Related Tasks</span></span>](#bkmk_related_tasks)  
  
##  <a name="benefits"></a><a name="bkmk_benefits"></a> <span data-ttu-id="16493-114">Benefícios</span><span class="sxs-lookup"><span data-stu-id="16493-114">Benefits</span></span>  
 <span data-ttu-id="16493-115">O design de modelo eficaz utiliza partições para eliminar processamento desnecessário e carga de processador subsequente em servidores do Analysis Services, enquanto, ao mesmo tempo, faz certos dados que são processados e atualizados com bastante frequência refletirem os dados mais recentes de fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="16493-115">Effective model design utilizes partitions to eliminate unnecessary processing and subsequent processor load on Analysis Services servers, while at the same time, making certain that data is processed and refreshed often enough to reflect the most recent data from data sources.</span></span>  
  
 <span data-ttu-id="16493-116">Por exemplo, um modelo de tabela pode ter uma tabela de Vendas que inclui dados de vendas durante o ano fiscal de 2011 atual e cada um dos anos fiscais anteriores.</span><span class="sxs-lookup"><span data-stu-id="16493-116">For example, a tabular model can have a Sales table which includes sales data for the current 2011 fiscal year and each of the previous fiscal years.</span></span> <span data-ttu-id="16493-117">A tabela de vendas do modelo tem as três partições a seguir:</span><span class="sxs-lookup"><span data-stu-id="16493-117">The model's Sales table has the following three partitions:</span></span>  
  
|<span data-ttu-id="16493-118">Partition</span><span class="sxs-lookup"><span data-stu-id="16493-118">Partition</span></span>|<span data-ttu-id="16493-119">Dados de</span><span class="sxs-lookup"><span data-stu-id="16493-119">Data from</span></span>|  
|---------------|---------------|  
|<span data-ttu-id="16493-120">Sales2011</span><span class="sxs-lookup"><span data-stu-id="16493-120">Sales2011</span></span>|<span data-ttu-id="16493-121">Ano fiscal atual</span><span class="sxs-lookup"><span data-stu-id="16493-121">Current fiscal year</span></span>|  
|<span data-ttu-id="16493-122">Sales2010-2001</span><span class="sxs-lookup"><span data-stu-id="16493-122">Sales2010-2001</span></span>|<span data-ttu-id="16493-123">Anos fiscais 2001, 2002, 2003, 2004, 2005, 2006.</span><span class="sxs-lookup"><span data-stu-id="16493-123">Fiscal years 2001, 2002, 2003, 2004, 2005, 2006.</span></span> <span data-ttu-id="16493-124">2007, 2008, 2009, 2010</span><span class="sxs-lookup"><span data-stu-id="16493-124">2007, 2008, 2009, 2010</span></span>|  
|<span data-ttu-id="16493-125">SalesOld</span><span class="sxs-lookup"><span data-stu-id="16493-125">SalesOld</span></span>|<span data-ttu-id="16493-126">Todos os anos fiscais antes dos últimos dez anos.</span><span class="sxs-lookup"><span data-stu-id="16493-126">All fiscal years prior to the last ten years.</span></span>|  
  
 <span data-ttu-id="16493-127">Como novos dados de vendas são adicionados durante o ano fiscal de 2011 atual, esses dados devem ser processados diariamente para serem refletido com precisão na análise de dados de vendas do ano fiscal atual, de modo que a partição Sales2011 seja processada a cada noite.</span><span class="sxs-lookup"><span data-stu-id="16493-127">As new sales data is added for the current 2011 fiscal year; that data must be processed daily to accurately be reflected in current fiscal year sales data analysis, thus the Sales2011 partition is processed nightly.</span></span>  
  
 <span data-ttu-id="16493-128">Não há nenhuma necessidade de processar dados na partição Sales2010-2001 a cada noite; no entanto, como os dados de vendas durante os dez anos fiscais anteriores ainda podem ser alterados ocasionalmente por causa de devoluções de produtos e outros ajustes, eles ainda devem ser processados regularmente, assim, os dados na partição Sales2010-2001 são processados mensalmente.</span><span class="sxs-lookup"><span data-stu-id="16493-128">There is no need to process data in the Sales2010-2001 partition nightly; however, because sales data for the previous ten fiscal years can still occasionally change because of product returns and other adjustments, it must still be processed regularly, thus data in the Sales2010-2001 partition is processed monthly.</span></span> <span data-ttu-id="16493-129">Os dados na partição SalesOld nunca são alterados; portanto só são processados anualmente.</span><span class="sxs-lookup"><span data-stu-id="16493-129">Data in the SalesOld partition never changes therefore only processed annually.</span></span>  
  
 <span data-ttu-id="16493-130">Ao entrar no ano fiscal de 2012, uma nova partição Sales2012 é adicionada à tabela Sales do modo.</span><span class="sxs-lookup"><span data-stu-id="16493-130">When entering the 2012 fiscal year, a new Sales2012 partition is added to the mode's Sales table.</span></span> <span data-ttu-id="16493-131">A partição Sales2011 pode então ser mesclada com a partição Sales2010-2001 e renomeada como Sales2011-2002.</span><span class="sxs-lookup"><span data-stu-id="16493-131">The Sales2011 partition can then be merged with the Sales2010-2001 partition and renamed to Sales2011-2002.</span></span> <span data-ttu-id="16493-132">Os dados do ano fiscal 2001 são eliminados da nova partição Sales2011-2002 e movidos para a partição SalesOld.</span><span class="sxs-lookup"><span data-stu-id="16493-132">Data from the 2001 fiscal year is eliminated from the new Sales2011-2002 partition and moved into the SalesOld partition.</span></span> <span data-ttu-id="16493-133">Todas as partições são então processadas para refletir as alterações.</span><span class="sxs-lookup"><span data-stu-id="16493-133">All partitions are then processed to reflect changes.</span></span>  
  
 <span data-ttu-id="16493-134">A maneira como você implementa uma estratégia de partição para os modelos de tabela de sua organização dependerá em grande parte de suas necessidades de processamento de dados de modelo e dos recursos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="16493-134">How you implement a partition strategy for your organization's tabular models will largely be dependent on your particular model data processing needs and available resources.</span></span>  
  
##  <a name="permissions"></a><a name="bkmk_permissions"></a> <span data-ttu-id="16493-135">Permissões</span><span class="sxs-lookup"><span data-stu-id="16493-135">Permissions</span></span>  
 <span data-ttu-id="16493-136">Para criar, gerenciar e processar partições no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], você deverá ter as permissões do Analysis Services apropriadas definidas em uma função de segurança.</span><span class="sxs-lookup"><span data-stu-id="16493-136">In order to create, manage, and process partitions in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must have the appropriate Analysis Services permissions defined in a security role.</span></span> <span data-ttu-id="16493-137">Cada função de segurança tem uma das seguintes permissões:</span><span class="sxs-lookup"><span data-stu-id="16493-137">Each security role has one of the following permissions:</span></span>  
  
|<span data-ttu-id="16493-138">Permissão</span><span class="sxs-lookup"><span data-stu-id="16493-138">Permission</span></span>|<span data-ttu-id="16493-139">Ações</span><span class="sxs-lookup"><span data-stu-id="16493-139">Actions</span></span>|  
|----------------|-------------|  
|<span data-ttu-id="16493-140">Administrador</span><span class="sxs-lookup"><span data-stu-id="16493-140">Administrator</span></span>|<span data-ttu-id="16493-141">Ler, processar, criar, copiar, mesclar, excluir</span><span class="sxs-lookup"><span data-stu-id="16493-141">Read, process, create, copy, merge, delete</span></span>|  
|<span data-ttu-id="16493-142">Processo</span><span class="sxs-lookup"><span data-stu-id="16493-142">Process</span></span>|<span data-ttu-id="16493-143">Leitura e processo</span><span class="sxs-lookup"><span data-stu-id="16493-143">Read, process</span></span>|  
|<span data-ttu-id="16493-144">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="16493-144">Read Only</span></span>|<span data-ttu-id="16493-145">Ler</span><span class="sxs-lookup"><span data-stu-id="16493-145">Read</span></span>|  
  
 <span data-ttu-id="16493-146">Para saber mais sobre como criar funções durante a criação do modelo usando o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], consulte [Funções &#40;SSAS de Tabela&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="16493-146">To learn more about creating roles during model authoring by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span> <span data-ttu-id="16493-147">Para saber mais sobre como gerenciar os membros de função para funções de modelo de tabela implantadas usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], consulte [Funções de modelo de tabela &#40;SSAS de Tabela&#41;](tabular-model-roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="16493-147">To learn more about managing role members for deployed tabular model roles by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], see [Tabular Model Roles &#40;SSAS Tabular&#41;](tabular-model-roles-ssas-tabular.md).</span></span>  
  
##  <a name="process-partitions"></a><a name="bkmk_process_partitions"></a><span data-ttu-id="16493-148">Processar partições</span><span class="sxs-lookup"><span data-stu-id="16493-148">Process Partitions</span></span>  
 <span data-ttu-id="16493-149">As partições podem ser processadas (atualizadas) de forma independente de outras partições com a caixa de diálogo **Partições** no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] ou usando um script.</span><span class="sxs-lookup"><span data-stu-id="16493-149">Partitions can be processed (refreshed) independent of other partitions by using the **Partitions** dialog box in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] or by using a script.</span></span> <span data-ttu-id="16493-150">O processamento tem as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="16493-150">Processing has the following options:</span></span>  
  
|<span data-ttu-id="16493-151">Mode</span><span class="sxs-lookup"><span data-stu-id="16493-151">Mode</span></span>|<span data-ttu-id="16493-152">Descrição</span><span class="sxs-lookup"><span data-stu-id="16493-152">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="16493-153">Processar Padrão</span><span class="sxs-lookup"><span data-stu-id="16493-153">Process Default</span></span>|<span data-ttu-id="16493-154">Detecta o estado de processamento de um objeto de partição e realiza o processamento necessário para passar os objetos de partição não processados ou parcialmente processados para um estado completamente processado.</span><span class="sxs-lookup"><span data-stu-id="16493-154">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="16493-155">Os dados para tabelas vazias e partições são carregados; hierarquias, colunas calculadas e relações são criadas ou recriadas.</span><span class="sxs-lookup"><span data-stu-id="16493-155">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
|<span data-ttu-id="16493-156">Processar Completo</span><span class="sxs-lookup"><span data-stu-id="16493-156">Process Full</span></span>|<span data-ttu-id="16493-157">Processa um objeto de partição e todos os objetos que ele contém.</span><span class="sxs-lookup"><span data-stu-id="16493-157">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="16493-158">Quando o comando Processar Completo for executado para um objeto que já foi processado, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] removerá todos os dados do objeto e processará o objeto.</span><span class="sxs-lookup"><span data-stu-id="16493-158">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="16493-159">Esse tipo de processamento é necessário quando uma alteração estrutural é feita em um objeto.</span><span class="sxs-lookup"><span data-stu-id="16493-159">This kind of processing is required when a structural change has been made to an object.</span></span>|  
|<span data-ttu-id="16493-160">Processar Dados</span><span class="sxs-lookup"><span data-stu-id="16493-160">Process Data</span></span>|<span data-ttu-id="16493-161">Carregue os dados em uma partição ou uma tabela sem recriar hierarquias ou relações ou recalcular colunas calculadas e medidas.</span><span class="sxs-lookup"><span data-stu-id="16493-161">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
|<span data-ttu-id="16493-162">Processar Limpeza</span><span class="sxs-lookup"><span data-stu-id="16493-162">Process Clear</span></span>|<span data-ttu-id="16493-163">Remove todos os dados de uma partição.</span><span class="sxs-lookup"><span data-stu-id="16493-163">Removes all data from a partition.</span></span>|  
|<span data-ttu-id="16493-164">Processar adição</span><span class="sxs-lookup"><span data-stu-id="16493-164">Process Add</span></span>|<span data-ttu-id="16493-165">Atualize a partição incrementalmente com novos dados.</span><span class="sxs-lookup"><span data-stu-id="16493-165">Incrementally update partition with new data.</span></span>|  
  
##  <a name="related-tasks"></a><a name="bkmk_related_tasks"></a> <span data-ttu-id="16493-166">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="16493-166">Related Tasks</span></span>  
  
|<span data-ttu-id="16493-167">Tarefa</span><span class="sxs-lookup"><span data-stu-id="16493-167">Task</span></span>|<span data-ttu-id="16493-168">Descrição</span><span class="sxs-lookup"><span data-stu-id="16493-168">Description</span></span>|  
|----------|-----------------|  
|[<span data-ttu-id="16493-169">Criar e gerenciar partições de modelos de tabela &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="16493-169">Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;</span></span>](create-and-manage-tabular-model-partitions-ssas-tabular.md)|<span data-ttu-id="16493-170">Descreve como criar e gerenciar partições em um modelo de tabela implantado usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16493-170">Describes how to create and manage partitions in a deployed tabular model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>|  
|[<span data-ttu-id="16493-171">Processar partições de modelo de tabela &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="16493-171">Process Tabular Model Partitions &#40;SSAS Tabular&#41;</span></span>](process-tabular-model-partitions-ssas-tabular.md)|<span data-ttu-id="16493-172">Descreve como processar partições em um modelo tabular implantado usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16493-172">Describes how to process partitions in a deployed tabular model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>|  
  
  