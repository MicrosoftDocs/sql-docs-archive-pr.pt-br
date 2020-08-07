---
title: Caixa de diálogo Filtrar (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: b987b141-5abf-4161-a073-4cfc3e7f5aae
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b58fd23fe4622515c8424574ad97d61971da9262
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581982"
---
# <a name="filter-dialog-box-mds-add-in-for-excel"></a><span data-ttu-id="3b8d0-102">Caixa de diálogo Filtrar (Suplemento do MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="3b8d0-102">Filter Dialog Box (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="3b8d0-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use a caixa de diálogo **Filtrar** para restringir a lista de dados gerenciados no MDS antes de carregá-la no Excel.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use the **Filter** dialog box to narrow the list of MDS-managed data before loading it into Excel.</span></span>  
  
 <span data-ttu-id="3b8d0-104">Essa caixa de diálogo contém três seções: **Colunas**, **Linhas**e **Resumo**.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-104">This dialog box contains three sections: **Columns**, **Rows**, and **Summary**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="3b8d0-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="3b8d0-105">Columns</span></span>  
 <span data-ttu-id="3b8d0-106">Use a seção **Colunas** para determinar quais atributos (colunas) você deseja exibir no Excel.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-106">Use the **Columns** section to determine which attributes (columns) you want to display in Excel.</span></span>  
  
|<span data-ttu-id="3b8d0-107">Nome do controle</span><span class="sxs-lookup"><span data-stu-id="3b8d0-107">Control Name</span></span>|<span data-ttu-id="3b8d0-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="3b8d0-108">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="3b8d0-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="3b8d0-109">Attribute type</span></span>|<span data-ttu-id="3b8d0-110">Um tipo de atributo descreve o tipo de membros com que você deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-110">An attribute type describes the type of members you want to work with.</span></span> <span data-ttu-id="3b8d0-111">Na maioria dos casos, o tipo é **Folha**.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-111">In most cases, this is **Leaf**.</span></span> <span data-ttu-id="3b8d0-112">Para obter mais informações sobre tipos de membros, consulte [Membros &#40;Master Data Services&#41;](../members-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3b8d0-112">For more information about member types, see [Members &#40;Master Data Services&#41;](../members-master-data-services.md).</span></span>|  
|<span data-ttu-id="3b8d0-113">Hierarquia explícita</span><span class="sxs-lookup"><span data-stu-id="3b8d0-113">Explicit hierarchy</span></span>|<span data-ttu-id="3b8d0-114">Se você escolher o tipo de atributo **Consolidado** , escolha a hierarquia à qual os membros consolidados pertencem.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-114">If you chose the **Consolidated** attribute type, choose the hierarchy the consolidated members belong to.</span></span> <span data-ttu-id="3b8d0-115">Para obter mais informações, consulte [Hierarquias explícitas &#40;Master Data Services&#41;](../explicit-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3b8d0-115">For more information, see [Explicit Hierarchies &#40;Master Data Services&#41;](../explicit-hierarchies-master-data-services.md).</span></span>|  
|<span data-ttu-id="3b8d0-116">Grupos de atributos</span><span class="sxs-lookup"><span data-stu-id="3b8d0-116">Attribute Groups</span></span>|<span data-ttu-id="3b8d0-117">Grupos de atributos são uma maneira de agrupar subconjuntos de atributos.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-117">Attribute groups are a way of grouping subsets of attributes.</span></span> <span data-ttu-id="3b8d0-118">Escolha um grupo de atributos se desejar mostrar um subconjunto de atributos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-118">Choose an attribute group if you want to show a subset of available attributes.</span></span> <span data-ttu-id="3b8d0-119">Para obter mais informações sobre grupos de atributos, consulte [Grupos de atributos &#40;Master Data Services&#41;](../attribute-groups-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3b8d0-119">For more information about attribute groups, see [Attribute Groups &#40;Master Data Services&#41;](../attribute-groups-master-data-services.md).</span></span>|  
|<span data-ttu-id="3b8d0-120">Selecionar Tudo</span><span class="sxs-lookup"><span data-stu-id="3b8d0-120">Select All</span></span>|<span data-ttu-id="3b8d0-121">Clique para selecionar todos os atributos exibidos na lista.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-121">Click to select all attributes displayed in the list.</span></span>|  
|<span data-ttu-id="3b8d0-122">Limpar Tudo</span><span class="sxs-lookup"><span data-stu-id="3b8d0-122">Clear All</span></span>|<span data-ttu-id="3b8d0-123">Clique para desmarcar todos os atributos selecionados exibidos na lista.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-123">Click to clear the selected attributes displayed in the list.</span></span><br /><br /> <span data-ttu-id="3b8d0-124">Observação: não é possível limpar o **nome** e o **código**.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-124">Note: You cannot clear **Name** and **Code**.</span></span>|  
|<span data-ttu-id="3b8d0-125">Seta para Cima</span><span class="sxs-lookup"><span data-stu-id="3b8d0-125">Up Arrow</span></span>|<span data-ttu-id="3b8d0-126">Clique para mover o atributo selecionado para cima na lista.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-126">Click to move the selected attribute up in the list.</span></span> <span data-ttu-id="3b8d0-127">A ordem de cima para baixo corresponde à ordem da esquerda para a direita em que as colunas são exibidas na planilha.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-127">The top-to-bottom order corresponds to the left-to-right order the columns are displayed in the worksheet.</span></span>|  
|<span data-ttu-id="3b8d0-128">Seta para Baixo</span><span class="sxs-lookup"><span data-stu-id="3b8d0-128">Down Arrow</span></span>|<span data-ttu-id="3b8d0-129">Clique para mover para baixo o atributo selecionado na lista.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-129">Click to move the selected attribute down in the list.</span></span> <span data-ttu-id="3b8d0-130">A ordem de cima para baixo corresponde à ordem da esquerda para a direita em que as colunas são exibidas na planilha.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-130">The top-to-bottom order corresponds to the left-to-right order the columns are displayed in the worksheet.</span></span>|  
  
## <a name="rows"></a><span data-ttu-id="3b8d0-131">Linhas</span><span class="sxs-lookup"><span data-stu-id="3b8d0-131">Rows</span></span>  
 <span data-ttu-id="3b8d0-132">Use a seção **Linhas** para determinar quais membros (linhas) você deseja exibir no Excel.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-132">Use the **Rows** section to determine which members (rows) you want to display in Excel.</span></span> <span data-ttu-id="3b8d0-133">Você faz isso definindo critérios para filtrar as linhas que serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-133">You do this by defining criteria to filter the rows that will be displayed.</span></span>  
  
|<span data-ttu-id="3b8d0-134">Nome do controle</span><span class="sxs-lookup"><span data-stu-id="3b8d0-134">Control Name</span></span>|<span data-ttu-id="3b8d0-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="3b8d0-135">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="3b8d0-136">Atributo</span><span class="sxs-lookup"><span data-stu-id="3b8d0-136">Attribute</span></span>|<span data-ttu-id="3b8d0-137">Exibe um atributo pelo qual você deseja filtrar.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-137">Displays an attribute you want to filter by.</span></span> <span data-ttu-id="3b8d0-138">Se nenhum atributo está listado, é porque eles não foram adicionados.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-138">If no attributes are listed, it's because they have not been added.</span></span><br /><br /> <span data-ttu-id="3b8d0-139">Observação: você pode filtrar por atributos que não planeja mostrar na planilha.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-139">Note: You can filter by attributes that you don't plan to show in the worksheet.</span></span>|  
|<span data-ttu-id="3b8d0-140">Operador</span><span class="sxs-lookup"><span data-stu-id="3b8d0-140">Operator</span></span>|<span data-ttu-id="3b8d0-141">Exibe operadores que correspondem ao tipo de atributo que foi selecionado.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-141">Displays operators that correspond to the type of attribute that was selected.</span></span> <span data-ttu-id="3b8d0-142">Para obter mais informações, consulte [Operadores de filtro &#40;Master Data Services&#41;](../filter-operators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3b8d0-142">For more information, see [Filter Operators &#40;Master Data Services&#41;](../filter-operators-master-data-services.md).</span></span>|  
|<span data-ttu-id="3b8d0-143">Critérios</span><span class="sxs-lookup"><span data-stu-id="3b8d0-143">Criteria</span></span>|<span data-ttu-id="3b8d0-144">O critério pelo qual você deseja filtrar.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-144">The criteria you want to filter by.</span></span>|  
|<span data-ttu-id="3b8d0-145">Resumo da Atualização</span><span class="sxs-lookup"><span data-stu-id="3b8d0-145">Update Summary</span></span>|<span data-ttu-id="3b8d0-146">Ao trabalhar com conjuntos de dados grandes, clique para atualizar a seção **Resumo** com detalhes da quantidade de dados que serão carregados.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-146">When working with large datasets, click to update the **Summary** section with details of the amount of data that will be loaded.</span></span>|  
|<span data-ttu-id="3b8d0-147">Adicionar</span><span class="sxs-lookup"><span data-stu-id="3b8d0-147">Add</span></span>|<span data-ttu-id="3b8d0-148">Quando você clica em um atributo na seção **Colunas** e em **Adicionar**, um atributo é adicionado à lista de filtros.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-148">When you click an attribute in the **Columns** section and then click **Add**, an attribute is added to the list of filters.</span></span>|  
|<span data-ttu-id="3b8d0-149">Remover Tudo</span><span class="sxs-lookup"><span data-stu-id="3b8d0-149">Remove All</span></span>|<span data-ttu-id="3b8d0-150">Remove todos os filtros da lista.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-150">Removes all filters from the list.</span></span>|  
|<span data-ttu-id="3b8d0-151">Remover</span><span class="sxs-lookup"><span data-stu-id="3b8d0-151">Remove</span></span>|<span data-ttu-id="3b8d0-152">Remove o filtro selecionado da lista.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-152">Removes selected filter from the list.</span></span>|  
  
## <a name="summary"></a><span data-ttu-id="3b8d0-153">Resumo</span><span class="sxs-lookup"><span data-stu-id="3b8d0-153">Summary</span></span>  
 <span data-ttu-id="3b8d0-154">Use a seção **Resumo** para exibir detalhes sobre a quantidade de dados que serão carregados, antes de carregá-los.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-154">Use the **Summary** section to view details about the amount of data that will be loaded, before loading it.</span></span>  
  
|<span data-ttu-id="3b8d0-155">Nome do controle</span><span class="sxs-lookup"><span data-stu-id="3b8d0-155">Control Name</span></span>|<span data-ttu-id="3b8d0-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="3b8d0-156">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="3b8d0-157">Modelo</span><span class="sxs-lookup"><span data-stu-id="3b8d0-157">Model</span></span>|<span data-ttu-id="3b8d0-158">O nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-158">The name of the model.</span></span>|  
|<span data-ttu-id="3b8d0-159">Versão</span><span class="sxs-lookup"><span data-stu-id="3b8d0-159">Version</span></span>|<span data-ttu-id="3b8d0-160">O nome da versão.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-160">The name of the version.</span></span>|  
|<span data-ttu-id="3b8d0-161">Entidade</span><span class="sxs-lookup"><span data-stu-id="3b8d0-161">Entity</span></span>|<span data-ttu-id="3b8d0-162">Nome da entidade.</span><span class="sxs-lookup"><span data-stu-id="3b8d0-162">The name of the entity.</span></span>|  
|<span data-ttu-id="3b8d0-163">Linhas</span><span class="sxs-lookup"><span data-stu-id="3b8d0-163">Rows</span></span>|<span data-ttu-id="3b8d0-164">O número de linhas que serão carregadas no Excel, com base nos filtros aplicados na seção **Linhas** .</span><span class="sxs-lookup"><span data-stu-id="3b8d0-164">The number of rows that will be loaded into Excel, based on the filters applied in the **Rows** section.</span></span>|  
|<span data-ttu-id="3b8d0-165">Colunas</span><span class="sxs-lookup"><span data-stu-id="3b8d0-165">Columns</span></span>|<span data-ttu-id="3b8d0-166">O número de colunas que serão carregadas no Excel, com base nos atributos selecionados na seção **Colunas** .</span><span class="sxs-lookup"><span data-stu-id="3b8d0-166">The number of columns that will be loaded into Excel, based on the attributes selected in the **Columns** section.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3b8d0-167">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3b8d0-167">See Also</span></span>  
 <span data-ttu-id="3b8d0-168">[Filtrar dados antes de carregar &#40;Suplemento MDS para Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="3b8d0-168">[Filter Data before Loading &#40;MDS Add-in for Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="3b8d0-169">Carregando dados &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="3b8d0-169">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
  