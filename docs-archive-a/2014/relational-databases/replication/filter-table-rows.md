---
title: Filtrar linhas da tabela | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.filtertablerows.f1
ms.assetid: 005f5c71-0401-490e-8823-adc54a2e9675
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9adeb2501adfd37658ddf05aa9956d6c3922bb80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569900"
---
# <a name="filter-table-rows"></a><span data-ttu-id="f2163-102">Filtrar Linhas da Tabela</span><span class="sxs-lookup"><span data-stu-id="f2163-102">Filter Table Rows</span></span>
  <span data-ttu-id="f2163-103">A página **Filtrar Linhas da Tabela** permite:</span><span class="sxs-lookup"><span data-stu-id="f2163-103">The **Filter Table Rows** page allows you to:</span></span>  
  
-   <span data-ttu-id="f2163-104">Aplicar filtros de linhas estáticos a artigos de tabela em publicações de instantâneo, transacional e de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="f2163-104">Apply static row filters to table articles in snapshot, transactional, and merge publications.</span></span>  
  
-   <span data-ttu-id="f2163-105">Aplicar filtros de linha com parâmetros a artigos de tabela em publicações de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="f2163-105">Apply parameterized row filters to table articles in merge publications.</span></span>  
  
-   <span data-ttu-id="f2163-106">Usar filtros de junção para estender filtros em artigos de tabela de mesclagem para artigos de tabela relacionados.</span><span class="sxs-lookup"><span data-stu-id="f2163-106">Use join filters to extend filters on merge table articles to related table articles.</span></span>  
  
 <span data-ttu-id="f2163-107">Para obter mais informações sobre opções de filtragem, consulte [Filter Published Data](publish/filter-published-data.md) (Filtrar dados publicados).</span><span class="sxs-lookup"><span data-stu-id="f2163-107">For more information about filtering options, see [Filter Published Data](publish/filter-published-data.md).</span></span> <span data-ttu-id="f2163-108">A filtragem pode ser alterada na página **Filtrar Linhas** da caixa de diálogo **Propriedades de Publicação** .</span><span class="sxs-lookup"><span data-stu-id="f2163-108">Filtering can be changed in the **Filter Rows** page of the **Publication Properties** dialog box.</span></span>  
  
 <span data-ttu-id="f2163-109">Para maximizar o desempenho do aplicativo e reduzir a quantidade de uma armazenagem remota requerida ou restringir a disponibilidade de certos dados a Assinantes específicos, somente os dados requeridos devem ser publicados.</span><span class="sxs-lookup"><span data-stu-id="f2163-109">To maximize application performance and reduce the amount of remote storage required, or to restrict the availability of certain data to specific Subscribers, you should publish only the data required.</span></span> <span data-ttu-id="f2163-110">Sua publicação pode incluir as tabelas filtradas e não filtradas.</span><span class="sxs-lookup"><span data-stu-id="f2163-110">Your publication can include both unfiltered and filtered tables.</span></span> <span data-ttu-id="f2163-111">Por exemplo, você pode incluir a tabela completa (não filtrada) de produtos da empresa e usar filtros de linha para fornecer uma tabela filtrada aos clientes de uma região específica.</span><span class="sxs-lookup"><span data-stu-id="f2163-111">For example, you could include the complete (unfiltered) table of company products and use row filters to provide a filtered table of customers for a specific region.</span></span> <span data-ttu-id="f2163-112">Filtrando dados publicados, você pode:</span><span class="sxs-lookup"><span data-stu-id="f2163-112">By filtering published data, you can:</span></span>  
  
-   <span data-ttu-id="f2163-113">Minimizar a quantidade de dados enviada pela rede.</span><span class="sxs-lookup"><span data-stu-id="f2163-113">Minimize the amount of data sent over the network.</span></span>  
  
-   <span data-ttu-id="f2163-114">Reduzir a quantidade de espaço de armazenamento requerida no Assinante.</span><span class="sxs-lookup"><span data-stu-id="f2163-114">Reduce the amount of storage space required at the Subscriber.</span></span>  
  
-   <span data-ttu-id="f2163-115">Personalizar publicações e aplicativos com base em requisitos de Assinante individuais.</span><span class="sxs-lookup"><span data-stu-id="f2163-115">Customize publications and applications based on individual Subscriber requirements.</span></span>  
  
-   <span data-ttu-id="f2163-116">Evitar ou reduzir conflitos se o Assinante estiver atualizando dados, porque partições diferentes de dados podem ser enviadas a Assinantes diferentes (dois Assinantes não estarão atualizando os mesmos valores de dados).</span><span class="sxs-lookup"><span data-stu-id="f2163-116">Avoid or reduce conflicts if Subscribers are updating data, because different data partitions can be sent to different Subscribers (no two Subscribers will be updating the same data values).</span></span>  
  
-   <span data-ttu-id="f2163-117">Evitar transmitir dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="f2163-117">Avoid transmitting sensitive data.</span></span> <span data-ttu-id="f2163-118">Podem ser usados filtros de linha e filtros de coluna para restringir um acesso de Assinante aos dados.</span><span class="sxs-lookup"><span data-stu-id="f2163-118">Row filters and column filters can be used to restrict a Subscriber's access to data.</span></span> <span data-ttu-id="f2163-119">Para a replicação de mesclagem, haverá considerações de segurança se você usar um filtro com parâmetros que inclua HOST_NAME().</span><span class="sxs-lookup"><span data-stu-id="f2163-119">For merge replication, there are security considerations if you use a parameterized filter that includes HOST_NAME().</span></span> <span data-ttu-id="f2163-120">Para obter mais informações, consulte a seção "Filtrando com HOST_NAME()" em [Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="f2163-120">For more information, see the section "Filtering with HOST_NAME()" in [Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 <span data-ttu-id="f2163-121">Um filtro não deve incluir o `rowguidcol` usado por replicação para identificar linhas.</span><span class="sxs-lookup"><span data-stu-id="f2163-121">A filter must not include the `rowguidcol` used by replication to identify rows.</span></span> <span data-ttu-id="f2163-122">Por padrão, esta é a coluna adicionada no momento que você define a replicação de mesclagem e é denominada **rowguid**.</span><span class="sxs-lookup"><span data-stu-id="f2163-122">By default this is the column added at the time you set up merge replication and is named **rowguid**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f2163-123">Opções</span><span class="sxs-lookup"><span data-stu-id="f2163-123">Options</span></span>  
 <span data-ttu-id="f2163-124">**Tabelas Filtradas**</span><span class="sxs-lookup"><span data-stu-id="f2163-124">**Filtered Tables**</span></span>  
 <span data-ttu-id="f2163-125">Esse painel é populado com filtros à medida que são adicionados a artigos de tabela na publicação.</span><span class="sxs-lookup"><span data-stu-id="f2163-125">This pane is populated with filters as you add them to table articles in the publication.</span></span> <span data-ttu-id="f2163-126">Tabelas com filtros de linha são mostradas como nós de alto nível no painel.</span><span class="sxs-lookup"><span data-stu-id="f2163-126">Tables with row filters are shown as top-level nodes in the pane.</span></span> <span data-ttu-id="f2163-127">Para publicações de mesclagem, tabelas para as quais a filtragem foi estendida através de um filtro de junção são mostradas como nós filhos.</span><span class="sxs-lookup"><span data-stu-id="f2163-127">For merge publications, tables to which filtering has been extended through a join filter are shown as child nodes.</span></span>  
  
 <span data-ttu-id="f2163-128">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="f2163-128">**Add**</span></span>  
 <span data-ttu-id="f2163-129">Clique em **Adicionar** para iniciar uma caixa de diálogo que permite filtrar artigos de tabela.</span><span class="sxs-lookup"><span data-stu-id="f2163-129">Click **Add** to launch a dialog box that enables you to filter table articles.</span></span> <span data-ttu-id="f2163-130">Clicar em **Adicionar** para um instantâneo ou uma publicação transacional inicia imediatamente uma caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f2163-130">Clicking **Add** for a snapshot or transactional publication launches a dialog box immediately.</span></span> <span data-ttu-id="f2163-131">Clicar em **Adicionar** para uma publicação de mesclagem exibe três opções: **Adicionar Filtro**; **Adicionar junção para estender o filtro selecionado**; **Gerar filtros automaticamente**.</span><span class="sxs-lookup"><span data-stu-id="f2163-131">Clicking **Add** for a merge publication displays three choices: **Add Filter**; **Add Join to Extend the Selected Filter**; **Automatically Generate Filters**.</span></span>  
  
-   <span data-ttu-id="f2163-132">Selecione **Adicionar Filtro** para iniciar a caixa de diálogo **Adicionar filtro** .</span><span class="sxs-lookup"><span data-stu-id="f2163-132">Select **Add Filter** to launch the **Add Filter** dialog box.</span></span> <span data-ttu-id="f2163-133">Essa caixa de diálogo permite aplicar filtros de linha a um artigo de tabela.</span><span class="sxs-lookup"><span data-stu-id="f2163-133">This dialog box allows you to apply row filters to a table article.</span></span> <span data-ttu-id="f2163-134">Na caixa de diálogo **Adicionar Filtro** você pode, por exemplo, especificar que uma tabela com dados de cliente só contenha dados de clientes franceses quando for replicada para Assinantes.</span><span class="sxs-lookup"><span data-stu-id="f2163-134">In the **Add Filter** dialog box, you could, for example, specify that a table with customer data should only contain data on French customers when it is replicated to Subscribers.</span></span>  
  
-   <span data-ttu-id="f2163-135">Selecione **Adicionar Junção para Estender o Filtro Selecionado** para iniciar a caixa de diálogo **Adicionar Junção** .</span><span class="sxs-lookup"><span data-stu-id="f2163-135">Select **Add Join to Extend the Selected Filter** to launch the **Add Join** dialog box.</span></span> <span data-ttu-id="f2163-136">A caixa de diálogo **Adicionar Junção** permite estender um filtro de linha para que filtre linhas em tabelas relacionadas à tabela com filtro de linha.</span><span class="sxs-lookup"><span data-stu-id="f2163-136">The **Add Join** dialog box allows you to extend a row filter so that it filters data in tables related to the table with the row filter.</span></span> <span data-ttu-id="f2163-137">Por exemplo, se uma tabela de cliente for filtrada para que contenha apenas dados de clientes franceses e houver uma tabela relacionada para pedidos de clientes, você pode definir uma junção entre as duas tabelas para que a tabela de pedidos só inclua pedidos de clientes franceses.</span><span class="sxs-lookup"><span data-stu-id="f2163-137">For example, if a customer table is filtered so that it only contains data on French customers and there is a related table for customer orders, you can define a join between the two tables so that the orders table only includes orders from French customers.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f2163-138">Essa opção só estará disponível se você selecionar primeiro  a tabela base da junção no painel de filtro.</span><span class="sxs-lookup"><span data-stu-id="f2163-138">This option is available only if you first select the base table of the join in the filter pane.</span></span>  
  
-   <span data-ttu-id="f2163-139">Selecione **Gerar Filtros Automaticamente** para iniciar a caixa de diálogo **Gerar Filtros** .</span><span class="sxs-lookup"><span data-stu-id="f2163-139">Select **Automatically Generate Filters** to launch the **Generate Filters** dialog box.</span></span> <span data-ttu-id="f2163-140">Essa caixa de diálogo permite definir um filtro de linha em uma tabela em uma publicação de mesclagem para que a replicação se estenda automaticamente a outras tabelas relacionadas por relações de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="f2163-140">This dialog box allows you to define a row filter on one table in a merge publication that replication automatically extends to other tables that are related through foreign key relationships.</span></span> <span data-ttu-id="f2163-141">Por exemplo, uma publicação pode incluir três tabelas: uma tabela de cliente, uma tabela de pedidos (com uma chave estrangeira para a tabela de cliente), e uma tabela de detalhes do pedido (com uma chave estrangeira para a tabela de pedidos).</span><span class="sxs-lookup"><span data-stu-id="f2163-141">For example, a publication could include three tables: a customer table, an orders table (with a foreign key to the customer table), and an order details table (with a foreign key to the orders table).</span></span> <span data-ttu-id="f2163-142">Defina um filtro de linha na tabela de cliente e replicação o estenderá às outras tabelas.</span><span class="sxs-lookup"><span data-stu-id="f2163-142">Define a row filter on the customer table, and replication will extend it to the other tables.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f2163-143">Quando os filtros são gerados automaticamente por replicação, qualquer filtro existente na publicação é excluído.</span><span class="sxs-lookup"><span data-stu-id="f2163-143">When filters are automatically generated by replication, any existing filters on the publication are deleted.</span></span> <span data-ttu-id="f2163-144">Para incluir os filtros gerados automaticamente e um especificado manualmente, gere os filtros primeiro.</span><span class="sxs-lookup"><span data-stu-id="f2163-144">To include both filters generated automatically and ones specified manually, generate filters first.</span></span> <span data-ttu-id="f2163-145">Você só pode especificar um conjunto de filtros gerado automaticamente para cada publicação.</span><span class="sxs-lookup"><span data-stu-id="f2163-145">You can only specify one set of automatically generated filters for each publication.</span></span>  
  
 <span data-ttu-id="f2163-146">**Editar**</span><span class="sxs-lookup"><span data-stu-id="f2163-146">**Edit**</span></span>  
 <span data-ttu-id="f2163-147">Selecione um filtro de linha ou um filtro de junção no painel de filtros e clique em **Editar** para iniciar a caixa de diálogo **Editar Filtro** ou **Editar Junção** .</span><span class="sxs-lookup"><span data-stu-id="f2163-147">Select a row filter or join filter in the filter pane and click **Edit** to launch the **Edit Filter** or **Edit Join** dialog box.</span></span>  
  
 <span data-ttu-id="f2163-148">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="f2163-148">**Delete**</span></span>  
 <span data-ttu-id="f2163-149">Selecione um filtro de linha ou um filtro de junção no painel de filtro e clique em **Excluir** para excluir o filtro.</span><span class="sxs-lookup"><span data-stu-id="f2163-149">Select a row filter or join filter in the filter pane and click **Delete** to delete the filter.</span></span>  
  
 <span data-ttu-id="f2163-150">**Localizar Tabela**</span><span class="sxs-lookup"><span data-stu-id="f2163-150">**Find Table**</span></span>  
 <span data-ttu-id="f2163-151">Mescle publicações apenas com filtros de junção.</span><span class="sxs-lookup"><span data-stu-id="f2163-151">Merge publications with join filters only.</span></span> <span data-ttu-id="f2163-152">Clique em **Localizar Tabela** para localizar uma tabela em uma árvore de filtro complexa.</span><span class="sxs-lookup"><span data-stu-id="f2163-152">Click **Find Table** to find a table in a complex filter tree.</span></span> <span data-ttu-id="f2163-153">Em um banco de dados com relações complexas, pode haver junção de uma tabela com várias tabelas e, portanto, ela pode aparecer em mais de um lugar na árvore de filtro.</span><span class="sxs-lookup"><span data-stu-id="f2163-153">In a database with complex relationships, a table can be joined to multiple tables, and therefore can appear in more than one place in the filter tree.</span></span>  
  
 <span data-ttu-id="f2163-154">A tabela real só aparece em um lugar na árvore; em outros lugares a tabela é representada por um atalho.</span><span class="sxs-lookup"><span data-stu-id="f2163-154">The actual table appears in only one place in the tree, and in other places, the table is represented by a shortcut.</span></span> <span data-ttu-id="f2163-155">Um atalho para uma tabela é somente uma referência à tabela; ele não mostra os nós filhos da tabela.</span><span class="sxs-lookup"><span data-stu-id="f2163-155">A shortcut to a table is only a reference to the table; it does not show the child nodes of the table.</span></span> <span data-ttu-id="f2163-156">Um nó de atalho é marcado com uma seta de atalho e, expandindo esse nó, o texto **Clique em Encontrar Tabela para ver a tabela de \<tablename>** é exibido.</span><span class="sxs-lookup"><span data-stu-id="f2163-156">A shortcut node is marked with a shortcut arrow, and expanding that node shows the text **Click Find Table to see table for \<tablename>**.</span></span>  
  
 <span data-ttu-id="f2163-157">Selecione um nó de atalho no painel e clique em **Localizar Tabela**.</span><span class="sxs-lookup"><span data-stu-id="f2163-157">Select a shortcut node in the pane and click **Find Table**.</span></span> <span data-ttu-id="f2163-158">O painel é expandido e a tabela é destacada.</span><span class="sxs-lookup"><span data-stu-id="f2163-158">The pane is expanded and the table is highlighted.</span></span> <span data-ttu-id="f2163-159">Se você clicar em **Localizar Tabela** sem um nó de atalho selecionado, uma caixa de diálogo **Localizar Tabela** será ativada.</span><span class="sxs-lookup"><span data-stu-id="f2163-159">If you click **Find Table** without a shortcut node selected, a **Find Table** dialog box is launched.</span></span>  
  
 <span data-ttu-id="f2163-160">**Filter**</span><span class="sxs-lookup"><span data-stu-id="f2163-160">**Filter**</span></span>  
 <span data-ttu-id="f2163-161">Contém a definição [!INCLUDE[tsql](../../includes/tsql-md.md)] para o filtro selecionado no painel de filtro.</span><span class="sxs-lookup"><span data-stu-id="f2163-161">Contains the [!INCLUDE[tsql](../../includes/tsql-md.md)] definition for the filter selected in the filter pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2163-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f2163-162">See Also</span></span>  
 <span data-ttu-id="f2163-163">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="f2163-163">[Create a Publication](publish/create-a-publication.md) </span></span>  
 <span data-ttu-id="f2163-164">[Exibir e modificar as propriedades da publicação](publish/view-and-modify-publication-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f2163-164">[View and Modify Publication Properties](publish/view-and-modify-publication-properties.md) </span></span>  
 <span data-ttu-id="f2163-165">[Filtrar os dados publicados](publish/filter-published-data.md) </span><span class="sxs-lookup"><span data-stu-id="f2163-165">[Filter Published Data](publish/filter-published-data.md) </span></span>  
 <span data-ttu-id="f2163-166">[Join Filters](merge/join-filters.md) </span><span class="sxs-lookup"><span data-stu-id="f2163-166">[Join Filters](merge/join-filters.md) </span></span>  
 <span data-ttu-id="f2163-167">[Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md) </span><span class="sxs-lookup"><span data-stu-id="f2163-167">[Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md) </span></span>  
 [<span data-ttu-id="f2163-168">Publicar dados e objetos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="f2163-168">Publish Data and Database Objects</span></span>](publish/publish-data-and-database-objects.md)  
  
  