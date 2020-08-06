---
title: Hierarquias (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e3e50e89-f85d-485b-a271-1e0550520212
author: minewiskan
ms.author: owend
ms.openlocfilehash: a50b014dd6096b0bfa66ff34389789fcd34efdae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679031"
---
# <a name="hierarchies-ssas-tabular"></a><span data-ttu-id="c8e3a-102">Hierarquias (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="c8e3a-102">Hierarchies (SSAS Tabular)</span></span>
  <span data-ttu-id="c8e3a-103">Hierarquias, em modelos de tabela, são metadados que definem relações entre duas ou mais colunas em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-103">Hierarchies, in tabular models, are metadata that define relationships between two or more columns in a table.</span></span> <span data-ttu-id="c8e3a-104">As hierarquias podem parecer separadas de outras colunas em uma lista de campo de cliente de relatório, facilitando para usuários clientes navegarem e incluírem em um relatório.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-104">Hierarchies can appear separate from other columns in a reporting client field list, making them easier for client users to navigate and include in a report.</span></span>  
  
 <span data-ttu-id="c8e3a-105">Seções neste tópico:</span><span class="sxs-lookup"><span data-stu-id="c8e3a-105">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="c8e3a-106">Benefícios</span><span class="sxs-lookup"><span data-stu-id="c8e3a-106">Benefits</span></span>](#bkmk_benefits)  
  
-   [<span data-ttu-id="c8e3a-107">Definindo hierarquias</span><span class="sxs-lookup"><span data-stu-id="c8e3a-107">Defining Hierarchies</span></span>](#bkmk_define)  
  
-   [<span data-ttu-id="c8e3a-108">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="c8e3a-108">Related Tasks</span></span>](#bkmk_related_tasks)  
  
##  <a name="benefits"></a><a name="bkmk_benefits"></a> <span data-ttu-id="c8e3a-109">Benefícios</span><span class="sxs-lookup"><span data-stu-id="c8e3a-109">Benefits</span></span>  
 <span data-ttu-id="c8e3a-110">As tabelas podem incluir dúzias ou até mesmo centenas de colunas com nomes de coluna incomuns em nenhuma ordem aparente.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-110">Tables can include dozens or even hundreds of columns with unusual column names in no apparent order.</span></span> <span data-ttu-id="c8e3a-111">Isto pode levar a uma aparência não ordenada ao reportar listas de campo de cliente, dificultando aos usuários localizarem e incluírem dados em um relatório.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-111">This can lead to an unordered appearance in reporting client field lists, making it difficult for users to find and include data in a report.</span></span> <span data-ttu-id="c8e3a-112">As hierarquias podem fornecer uma exibição simples e intuitiva de uma estrutura de dados que, de outra maneira, seria complexa.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-112">Hierarchies can provide a simple, intuitive view of an otherwise complex data structure.</span></span>  
  
 <span data-ttu-id="c8e3a-113">Por exemplo, em uma tabela de Data, você pode criar uma hierarquia de Calendário.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-113">For example, in a Date table, you can create a Calendar hierarchy.</span></span> <span data-ttu-id="c8e3a-114">O Ano civil é usado como o nível pai mais alto, com Mês, Semana e Dia incluídos como níveis filho (Ano civil->Mês->Semana->Dia).</span><span class="sxs-lookup"><span data-stu-id="c8e3a-114">Calendar Year is used as the top-most parent level, with Month, Week, and Day included as child levels (Calendar Year->Month->Week->Day).</span></span> <span data-ttu-id="c8e3a-115">Esta hierarquia mostra uma relação lógica de Ano civil a Dia.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-115">This hierarchy shows a logical relationship from Calendar Year to Day.</span></span> <span data-ttu-id="c8e3a-116">Um usuário de cliente pode selecionar Ano Civil de uma Lista de campos para incluir todos os níveis em uma Tabela Dinâmica ou expandir a hierarquia e selecionar somente níveis específicos para serem incluídos na Tabela Dinâmica.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-116">A client user can then select Calendar Year from a Field List to include all levels in a PivotTable, or expand the hierarchy, and select only particular levels to be included in the PivotTable.</span></span>  
  
 <span data-ttu-id="c8e3a-117">Como cada nível em uma hierarquia é uma representação de uma coluna em uma tabela, o nível pode ser renomeado.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-117">Because each level in a hierarchy is a representation of a column in a table, the level can be renamed.</span></span> <span data-ttu-id="c8e3a-118">Embora não seja exclusivo para hierarquias (qualquer coluna pode ser renomeada em um modelo de tabela), a renomeação de níveis de hierarquia pode facilitar a localização e a inclusão de níveis em um relatório por usuários.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-118">While not exclusive to hierarchies (any column can be renamed in a tabular model), renaming hierarchy levels can make it easier for users to find and include levels in a report.</span></span> <span data-ttu-id="c8e3a-119">Renomear um nível não renomeia a coluna que a referencia; simplesmente torna o nível mais identificável.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-119">Renaming a level does not rename the column it references; it simply makes the level more identifiable.</span></span> <span data-ttu-id="c8e3a-120">Em nosso exemplo de hierarquia de Ano Civil, na tabela de Data em Exibição de Dados, as colunas: CalendarYear, CalendarMonth, CalendarWeek e CalendarDay foram renomeadas para Ano Civil, Mês, Semana e Dia para torná-las mais identificáveis.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-120">In our Calendar Year hierarchy example, in the Date table in Data View, the columns: CalendarYear, CalendarMonth, CalendarWeek, and CalendarDay were renamed to Calendar Year, Month, Week, and Day to make them more easily identifiable.</span></span> <span data-ttu-id="c8e3a-121">Renomear os níveis tem o benefício adicional de fornecer consistência em relatórios, já que os usuários não precisarão alterar nomes de coluna para torná-los mais legíveis em Tabelas Dinâmicas, gráficos, etc.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-121">Renaming levels has the additional benefit of providing consistency in reports, since users will less likely need to change column names to make them more readable in PivotTables, charts, etc.</span></span>  
  
 <span data-ttu-id="c8e3a-122">As hierarquias podem ser incluídas em perspectivas.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-122">Hierarchies can be included in perspectives.</span></span> <span data-ttu-id="c8e3a-123">As perspectivas definem subconjuntos visíveis de um modelo que fornece pontos de vista concentrados, específicos à empresa ou específicos ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-123">Perspectives define viewable subsets of a model that provide focused, business-specific, or application-specific viewpoints of the model.</span></span> <span data-ttu-id="c8e3a-124">Por exemplo, uma perspectiva pode fornecer aos usuários uma lista visível (hierarquia) de apenas os itens de dados necessários para os seus requisitos específicos de relatório.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-124">A perspective, for example, could provide users a viewable list (hierarchy) of only those data items necessary for their specific reporting requirements.</span></span> <span data-ttu-id="c8e3a-125">Para obter mais informações, consulte [Perspectivas &#40;SSAS de Tabela&#41;](perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="c8e3a-125">For more information, see [Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="c8e3a-126">As hierarquias não se destinam a serem usadas como um mecanismo de segurança, mas como uma ferramenta para fornecer uma melhor experiência.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-126">Hierarchies are not meant to be used as a security mechanism, but as a tool for providing a better user experience.</span></span> <span data-ttu-id="c8e3a-127">Toda a segurança de uma determinada hierarquia é herdada do modelo subjacente.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-127">All security for a particular hierarchy is inherited from the underlying model.</span></span> <span data-ttu-id="c8e3a-128">As hierarquias não podem fornecer acesso a objetos de modelo aos quais o usuário ainda não tem acesso.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-128">Hierarchies cannot provide access to model objects to which a user does not already have access.</span></span> <span data-ttu-id="c8e3a-129">A segurança para o banco de dados modelo deve ser resolvida antes que o acesso a objetos no modelo possa ser fornecido por meio de uma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-129">Security for the model database must be resolved before access to objects in the model can be provided through a hierarchy.</span></span> <span data-ttu-id="c8e3a-130">As funções de segurança podem ser usadas para proteger metadados e dados do modelo.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-130">Security roles can be used to secure model metadata and data.</span></span> <span data-ttu-id="c8e3a-131">Para obter mais informações, consulte [Funções &#40;SSAS de Tabela&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="c8e3a-131">For more information, see [Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
##  <a name="defining-hierarchies"></a><a name="bkmk_define"></a><span data-ttu-id="c8e3a-132">Definindo hierarquias</span><span class="sxs-lookup"><span data-stu-id="c8e3a-132">Defining Hierarchies</span></span>  
 <span data-ttu-id="c8e3a-133">Você cria e gerencia hierarquias usando o designer de modelo em Exibição de Diagrama.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-133">You create and manage hierarchies by using the model designer in Diagram View.</span></span> <span data-ttu-id="c8e3a-134">Não há suporte para a criação e o gerenciamento de hierarquias no designer de modelos na Exibição de Dados.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-134">Creating and managing hierarchies is not supported in the model designer in Data View.</span></span> <span data-ttu-id="c8e3a-135">Para exibir o designer de modelos na Exibição de Diagrama, clique no menu **Modelo** , aponte para **Exibição de Modelo**e clique em **Exibição de Diagrama**.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-135">To view the model designer in Diagram View, click the **Model** menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
 <span data-ttu-id="c8e3a-136">Para criar uma hierarquia, clique com o botão direito do mouse em uma coluna que você deseja especificar como o nível pai e clique em **Criar Hierarquia**.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-136">To create a hierarchy, right-click a column you want to specify as the parent level, and then click **Create Hierarchy**.</span></span> <span data-ttu-id="c8e3a-137">Você pode fazer seleções múltiplas de qualquer número de colunas (dentro de uma única tabela) para incluir ou pode adicionar colunas posteriormente como níveis filho clicando e arrastando colunas para o nível pai.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-137">You can multi-select any number of columns (within a single table) to include, or you can later add columns as child levels by clicking and dragging columns to the parent level.</span></span> <span data-ttu-id="c8e3a-138">Quando são selecionadas várias colunas, elas são colocadas automaticamente em uma ordem com base na cardinalidade.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-138">When multiple columns are selected, columns are automatically placed in an order based on cardinality.</span></span> <span data-ttu-id="c8e3a-139">Você pode alterar a ordem clicando e arrastando uma coluna (nível) para uma ordem diferente ou usando controles de navegação Para cima e Para baixo no menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-139">You can change the order by clicking and dragging a column (level) to a different order or by using Up and Down navigation controls on the context menu.</span></span> <span data-ttu-id="c8e3a-140">Ao adicionar uma coluna como um nível filho, você pode usar detecção automática arrastando e removendo a coluna no nível pai.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-140">When adding a column as a child level, you can use auto-detect by dragging and dropping the column onto the parent level.</span></span>  
  
 <span data-ttu-id="c8e3a-141">Uma coluna pode aparecer em mais de uma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-141">A column can appear in more than one hierarchy.</span></span> <span data-ttu-id="c8e3a-142">Hierarquias não podem incluir objetos que não sejam colunas como medidas ou KPIs.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-142">Hierarchies cannot include non-column objects such as measures or KPIs.</span></span> <span data-ttu-id="c8e3a-143">Uma hierarquia pode ser baseada em colunas de dentro de somente uma única tabela.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-143">A hierarchy can be based on columns from within a single table only.</span></span> <span data-ttu-id="c8e3a-144">Se você fizer multisseleção de uma medida junto com uma ou mais colunas, ou se você selecionar colunas de várias tabelas, o comando **Criar Hierarquia** estará desabilitado no menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-144">If you multi-select a measure along with one or more columns, or if you select columns from multiple tables, the **Create Hierarchy** command is disabled in the context menu.</span></span> <span data-ttu-id="c8e3a-145">Para adicionar uma coluna de uma tabela diferente, use a função RELATED DAX para adicionar uma coluna calculada que faz referência à coluna da tabela relacionada.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-145">To add a column from a different table, use the RELATED DAX function to add a calculated column that references the column from the related table.</span></span> <span data-ttu-id="c8e3a-146">A função usa a seguinte sintaxe: `=RELATED(TableName[ColumnName])`.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-146">The function uses the following syntax: `=RELATED(TableName[ColumnName])`.</span></span> <span data-ttu-id="c8e3a-147">Para obter mais informações, consulte a função RELATED.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-147">For more information, see RELATED Function.</span></span>  
  
 <span data-ttu-id="c8e3a-148">Por padrão, as novas hierarquias são chamadas de hierarquia 1, hierarquia 2 etc. Você deve alterar os nomes das hierarquias para refletir a natureza da relação pai-filho, tornando-os mais identificáveis a usuários.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-148">By default, new hierarchies are named hierarchy1, hierarchy 2, etc. You should change hierarchy names to reflect the nature of the parent-child relationship, making them more identifiable to users.</span></span>  
  
 <span data-ttu-id="c8e3a-149">Depois de criar hierarquias, você pode testar a sua eficácia usando o recurso Analisar no Excel.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-149">After you have created hierarchies, you can test their efficacy by using the Analyze in Excel feature.</span></span> <span data-ttu-id="c8e3a-150">Para obter mais informações, consulte [Analisar no Excel &#40;SSAS de Tabela&#41;](analyze-in-excel-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="c8e3a-150">For more information, see [Analyze in Excel &#40;SSAS Tabular&#41;](analyze-in-excel-ssas-tabular.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="bkmk_related_tasks"></a> <span data-ttu-id="c8e3a-151">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="c8e3a-151">Related Tasks</span></span>  
  
|<span data-ttu-id="c8e3a-152">Tarefa</span><span class="sxs-lookup"><span data-stu-id="c8e3a-152">Task</span></span>|<span data-ttu-id="c8e3a-153">Descrição</span><span class="sxs-lookup"><span data-stu-id="c8e3a-153">Description</span></span>|  
|----------|-----------------|  
|[<span data-ttu-id="c8e3a-154">Criar e Gerenciar hierarquias &#40;SSAS Tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="c8e3a-154">Create and Manage Hierarchies &#40;SSAS Tabular&#41;</span></span>](hierarchies-ssas-tabular.md)|<span data-ttu-id="c8e3a-155">Descreve como criar e gerenciar hierarquias usando o designer de modelo em Exibição de Diagrama.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-155">Describes how to create and manage hierarchies by using the model designer in Diagram View.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8e3a-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c8e3a-156">See Also</span></span>  
 <span data-ttu-id="c8e3a-157">[Designer de modelo de tabela &#40;SSAS de tabela&#41;](../tabular-model-designer-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c8e3a-157">[Tabular Model Designer &#40;SSAS Tabular&#41;](../tabular-model-designer-ssas-tabular.md) </span></span>  
 <span data-ttu-id="c8e3a-158">[Perspectivas &#40;SSAS de tabela&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c8e3a-158">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="c8e3a-159">Funções &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="c8e3a-159">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  