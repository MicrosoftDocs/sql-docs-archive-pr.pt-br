---
title: Painel de Diagrama (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Query Designer [SQL Server], Diagram pane
- View Designer, Diagram pane
- joins [SQL Server], Query and View Designer
- Diagram pane [Visual Database Tools]
ms.assetid: 399dfc7b-e2e7-47d3-bd11-163cbe0ce13c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6bbc25365771b4d0fa571cb128baf5bc1890ddf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684977"
---
# <a name="diagram-pane-visual-database-tools"></a><span data-ttu-id="aa99d-102">Painel de Diagrama (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="aa99d-102">Diagram Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="aa99d-103">O painel Diagrama apresenta uma exibição gráfica das tabelas ou objetos com valor de tabela selecionados na conexão de dados.</span><span class="sxs-lookup"><span data-stu-id="aa99d-103">The Diagram pane presents a graphic display of the tables or table-valued objects you have selected from the data connection.</span></span> <span data-ttu-id="aa99d-104">Mostra também todas as relações de junção entre eles.</span><span class="sxs-lookup"><span data-stu-id="aa99d-104">It also shows any join relationships among them.</span></span>  
  
 <span data-ttu-id="aa99d-105">No painel Diagrama você pode:</span><span class="sxs-lookup"><span data-stu-id="aa99d-105">In the Diagram pane you can:</span></span>  
  
-   <span data-ttu-id="aa99d-106">Adicionar ou remover tabelas e objetos com valor de tabela e especificar colunas de dados para saída.</span><span class="sxs-lookup"><span data-stu-id="aa99d-106">Add or remove tables and table-valued objects and specify data columns for output.</span></span>  
  
-   <span data-ttu-id="aa99d-107">Criar ou modificar junções entre tabelas e objetos com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="aa99d-107">Create or modify joins between tables and table-valued objects.</span></span>  
  
 <span data-ttu-id="aa99d-108">Quando você faz uma alteração no painel Diagrama, o painel Critérios e o painel SQL são atualizados para refletir a sua alteração.</span><span class="sxs-lookup"><span data-stu-id="aa99d-108">When you make a change in the Diagram pane, the Criteria pane and SQL pane are updated to reflect your change.</span></span> <span data-ttu-id="aa99d-109">Por exemplo, se você selecionar uma coluna para saída em uma tabela ou janela de objeto com valor de tabela no painel Diagrama, o Designer de Consulta e Exibição adicionará a coluna de dados ao painel Critérios e à instrução SQL no painel SQL.</span><span class="sxs-lookup"><span data-stu-id="aa99d-109">For example, if you select a column for output in a table or table-valued object window in the Diagram pane, the Query and View Designer adds the data column to the Criteria pane and to the SQL statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="aa99d-110">Cada tabela ou objeto com valor de tabela é exibido como uma janela separada no painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="aa99d-110">Each table or table-valued object appears as a separate window in the Diagram pane.</span></span> <span data-ttu-id="aa99d-111">O ícone na barra de título de cada retângulo indica qual tipo de objeto o retângulo representa, conforme ilustrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="aa99d-111">The icon in the title bar of each rectangle indicates what type of object the rectangle represents, as illustrated in the following table.</span></span>  
  
## <a name="options"></a><span data-ttu-id="aa99d-112">Opções</span><span class="sxs-lookup"><span data-stu-id="aa99d-112">Options</span></span>  
 <span data-ttu-id="aa99d-113">**Tabelas**</span><span class="sxs-lookup"><span data-stu-id="aa99d-113">**Tables**</span></span>  
 <span data-ttu-id="aa99d-114">Lista as tabelas que você pode adicionar ao painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="aa99d-114">Lists the tables you can add to the Diagram pane.</span></span> <span data-ttu-id="aa99d-115">Para adicionar uma tabela, selecione-a e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="aa99d-115">To add a table, select it and click **Add**.</span></span> <span data-ttu-id="aa99d-116">Para adicionar várias tabelas de uma vez, selecione-as e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="aa99d-116">To add several tables at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="aa99d-117">**Exibições**</span><span class="sxs-lookup"><span data-stu-id="aa99d-117">**Views**</span></span>  
 <span data-ttu-id="aa99d-118">Lista as exibições que você pode adicionar ao painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="aa99d-118">Lists the views you can add to the Diagram pane.</span></span> <span data-ttu-id="aa99d-119">Para adicionar um modo de exibição, selecione-o e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="aa99d-119">To add a view, select it and click **Add**.</span></span> <span data-ttu-id="aa99d-120">Para adicionar vários modos de exibição de uma vez, selecione-os e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="aa99d-120">To add several views at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="aa99d-121">**Funções**</span><span class="sxs-lookup"><span data-stu-id="aa99d-121">**Functions**</span></span>  
 <span data-ttu-id="aa99d-122">Lista as funções definidas pelo usuário que você pode adicionar ao painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="aa99d-122">Lists the user-defined functions you can add to the Diagram pane.</span></span> <span data-ttu-id="aa99d-123">Para adicionar uma função, selecione-a e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="aa99d-123">To add a function, select it and click **Add**.</span></span> <span data-ttu-id="aa99d-124">Para adicionar várias funções de uma vez, selecione-as em clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="aa99d-124">To add several functions at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="aa99d-125">**Tabelas Locais**</span><span class="sxs-lookup"><span data-stu-id="aa99d-125">**Local Tables**</span></span>  
 <span data-ttu-id="aa99d-126">Lista as tabelas criadas por consultas em vez daquelas que pertencem ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aa99d-126">Lists tables created by queries rather than the ones that belong to the database.</span></span>  
  
 <span data-ttu-id="aa99d-127">**Sinônimos**</span><span class="sxs-lookup"><span data-stu-id="aa99d-127">**Synonyms**</span></span>  
 <span data-ttu-id="aa99d-128">Lista os sinônimos que você pode adicionar ao painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="aa99d-128">Lists the synonyms you can add to the Diagram pane.</span></span> <span data-ttu-id="aa99d-129">Para adicionar um sinônimo, selecione-o e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="aa99d-129">To add a synonym, select it and click **Add**.</span></span> <span data-ttu-id="aa99d-130">Para adicionar vários sinônimos de uma vez, selecione-os em clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="aa99d-130">To add several synonyms at once, select them and click **Add**.</span></span>  
  
|<span data-ttu-id="aa99d-131">ícone</span><span class="sxs-lookup"><span data-stu-id="aa99d-131">Icon</span></span>|<span data-ttu-id="aa99d-132">Tipo de objeto</span><span class="sxs-lookup"><span data-stu-id="aa99d-132">Object type</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="aa99d-133">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbi1.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-133">![Visual Database Tools icon](../../database-engine/media//dv3wbi1.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-134">Tabela</span><span class="sxs-lookup"><span data-stu-id="aa99d-134">Table</span></span>|  
|<span data-ttu-id="aa99d-135">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbi2.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-135">![Visual Database Tools icon](../../database-engine/media//dv3wbi2.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-136">Consulta ou Exibição</span><span class="sxs-lookup"><span data-stu-id="aa99d-136">Query or View</span></span>|  
|<span data-ttu-id="aa99d-137">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbi3.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-137">![Visual Database Tools icon](../../database-engine/media//dv3wbi3.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-138">Tabela vinculada</span><span class="sxs-lookup"><span data-stu-id="aa99d-138">Linked Table</span></span>|  
|<span data-ttu-id="aa99d-139">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dvudficon.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-139">![Visual Database Tools icon](../../database-engine/media//dvudficon.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-140">Função definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="aa99d-140">User-Defined Function</span></span>|  
|<span data-ttu-id="aa99d-141">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbi5.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-141">![Visual Database Tools icon](../../database-engine/media//dv3wbi5.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-142">Exibição vinculada</span><span class="sxs-lookup"><span data-stu-id="aa99d-142">Linked View</span></span>|  
  
 <span data-ttu-id="aa99d-143">Cada retângulo mostra as colunas de dados da tabela ou objeto com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="aa99d-143">Each rectangle shows the data columns for the table or table-valued object.</span></span> <span data-ttu-id="aa99d-144">As caixas de seleção e os símbolos são exibidos ao lado dos nomes das colunas para indicar como as colunas são usadas na consulta.</span><span class="sxs-lookup"><span data-stu-id="aa99d-144">Check boxes and symbols appear next to the names of columns to indicate how the columns are used in the query.</span></span> <span data-ttu-id="aa99d-145">As dicas de ferramentas exibem informações como tipo de dados e tamanho das colunas.</span><span class="sxs-lookup"><span data-stu-id="aa99d-145">ToolTips display information such as data type and size for columns.</span></span>  
  
 <span data-ttu-id="aa99d-146">A tabela a seguir lista as caixas de seleção e os símbolos usados no retângulo para cada tabela ou objeto com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="aa99d-146">The following table lists the check boxes and symbols used in the rectangle for each table or table-valued object.</span></span>  
  
|<span data-ttu-id="aa99d-147">Caixa de seleção ou símbolo</span><span class="sxs-lookup"><span data-stu-id="aa99d-147">Check box or symbol</span></span>|<span data-ttu-id="aa99d-148">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="aa99d-148">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="aa99d-149">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbi7.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-149">![Visual Database Tools icon](../../database-engine/media//dv3wbi7.gif "Visual Database Tools icon")</span></span><br /><br /> <span data-ttu-id="aa99d-150">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbi8.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-150">![Visual Database Tools icon](../../database-engine/media//dv3wbi8.gif "Visual Database Tools icon")</span></span><br /><br /> <span data-ttu-id="aa99d-151">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbi9.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-151">![Visual Database Tools icon](../../database-engine/media//dv3wbi9.gif "Visual Database Tools icon")</span></span><br /><br /> <span data-ttu-id="aa99d-152">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbia.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-152">![Visual Database Tools icon](../../database-engine/media//dv3wbia.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-153">Especifica se uma coluna de dados é exibida no conjunto de resultados da consulta (consulta  Select) ou se é usada em uma consulta Update, Insert From, Make Table ou Insert Into.</span><span class="sxs-lookup"><span data-stu-id="aa99d-153">Specifies whether a data column appears in the query result set (Select query) or is used in an Update, Insert From, Make Table, or Insert Into query.</span></span> <span data-ttu-id="aa99d-154">Selecione a coluna a ser adicionada aos resultados.</span><span class="sxs-lookup"><span data-stu-id="aa99d-154">Select the column to add it to the results.</span></span> <span data-ttu-id="aa99d-155">Se **(Todas as Colunas)** for selecionado, todas as colunas de dados serão exibidas na saída.</span><span class="sxs-lookup"><span data-stu-id="aa99d-155">If **(All Columns)** is selected, all data columns appear in the output.</span></span><br /><br /> <span data-ttu-id="aa99d-156">O ícone usado com a caixa de seleção é alterado de acordo com o tipo de consulta que você está criando.</span><span class="sxs-lookup"><span data-stu-id="aa99d-156">The icon used with the check box changes according to the type of query you are creating.</span></span> <span data-ttu-id="aa99d-157">Ao criar uma consulta Excluir, não podem ser selecionadas colunas individuais.</span><span class="sxs-lookup"><span data-stu-id="aa99d-157">When creating a Delete query, you cannot select individual columns.</span></span>|  
|<span data-ttu-id="aa99d-158">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbib.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-158">![Visual Database Tools icon](../../database-engine/media//dv3wbib.gif "Visual Database Tools icon")</span></span><br /><br /> <span data-ttu-id="aa99d-159">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbic.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-159">![Visual Database Tools icon](../../database-engine/media//dv3wbic.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-160">Indica que a coluna de dados está sendo usada para ordenar os resultados da consulta (faz parte de uma cláusula ORDER BY).</span><span class="sxs-lookup"><span data-stu-id="aa99d-160">Indicates that the data column is being used to order the query results (is part of an ORDER BY clause).</span></span> <span data-ttu-id="aa99d-161">O ícone é exibido como A-Z se a ordem de classificação for crescente ou Z-A se ordem de classificação for decrescente.</span><span class="sxs-lookup"><span data-stu-id="aa99d-161">The icon appears as A-Z if the sort order is ascending or Z-A if sort order is descending.</span></span>|  
|<span data-ttu-id="aa99d-162">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbid.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-162">![Visual Database Tools icon](../../database-engine/media//dv3wbid.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-163">Indica que a coluna de dados está sendo usada para criar um conjunto de resultados agrupado (faz parte de uma cláusula GROUP BY) em uma consulta de agregação.</span><span class="sxs-lookup"><span data-stu-id="aa99d-163">Indicates that the data column is being used to create a grouped result set (is part of a GROUP BY clause) in an aggregate query.</span></span>|  
|<span data-ttu-id="aa99d-164">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbie.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-164">![Visual Database Tools icon](../../database-engine/media//dv3wbie.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-165">Indica que a coluna de dados está incluída em um critério de pesquisa da consulta (faz parte de um cláusula WHERE ou HAVING).</span><span class="sxs-lookup"><span data-stu-id="aa99d-165">Indicates that the data column is included in a search condition for the query (is part of a WHERE or HAVING clause).</span></span>|  
|<span data-ttu-id="aa99d-166">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbif.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-166">![Visual Database Tools icon](../../database-engine/media//dv3wbif.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-167">Indica que os conteúdos da coluna de dados estão sendo resumidos para saída (são incluídos em uma função de agregação SUM, AVG ou outra função de agregação).</span><span class="sxs-lookup"><span data-stu-id="aa99d-167">Indicates that the contents of the data column are being summarized for output (are included in a SUM, AVG, or other aggregate function).</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="aa99d-168">O Designer de Consulta e Exibição não exibirá colunas de dados para uma tabela ou objeto com valor de tabela se você não tiver direitos de acesso suficientes às mesmas ou se o driver do banco de dados não puder retornar informações sobre as mesmas.</span><span class="sxs-lookup"><span data-stu-id="aa99d-168">Query and View Designer will not display data columns for a table or table-valued object if you do not have sufficient access rights to it or if the database driver cannot return information about it.</span></span> <span data-ttu-id="aa99d-169">Nesses casos, o Designer de Consulta e Exibição exibirá somente uma barra de título para a tabela ou objeto com estrutura de tabela.</span><span class="sxs-lookup"><span data-stu-id="aa99d-169">In such cases, the Query and View Designer displays only a title bar for the table or table-structured object.</span></span>  
  
## <a name="joined-tables-on-the-diagram-pane"></a><span data-ttu-id="aa99d-170">Tabelas unidas no painel Diagrama</span><span class="sxs-lookup"><span data-stu-id="aa99d-170">Joined Tables on the Diagram Pane</span></span>  
 <span data-ttu-id="aa99d-171">Se a consulta envolver uma junção, uma linha de junção é exibida entre as colunas de dados envolvidas na junção.</span><span class="sxs-lookup"><span data-stu-id="aa99d-171">If the query involves a join, a join line appears between the data columns involved in the join.</span></span> <span data-ttu-id="aa99d-172">Se as colunas de dados unidas não forem exibidas (por exemplo, a janela da tabela ou do objeto com valor de tabela está minimizada ou a junção envolve uma expressão), o Designer de Consulta e Exibição colocará a linha de junção na barra de título do retângulo que representa a tabela ou o objeto com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="aa99d-172">If the joined data columns are not displayed (for example, the table or table-valued object window is minimized or the join involves an expression), the Query and View Designer places the join line in the title bar of the rectangle representing the table or table-valued object.</span></span> <span data-ttu-id="aa99d-173">O Designer de Consulta e Exibição exibe uma linha de junção para cada condição de junção.</span><span class="sxs-lookup"><span data-stu-id="aa99d-173">The Query and View Designer displays one join line for each join condition.</span></span>  
  
 <span data-ttu-id="aa99d-174">A forma do ícone no meio da linha de junção indica como são unidas as tabelas ou objetos com estrutura de tabela.</span><span class="sxs-lookup"><span data-stu-id="aa99d-174">The shape of the icon in the middle of the join line indicates how the tables or table-structured objects are joined.</span></span> <span data-ttu-id="aa99d-175">Se a cláusula de junção usar um operador diferente de igual (=), o operador será exibido no ícone da linha de junção.</span><span class="sxs-lookup"><span data-stu-id="aa99d-175">If the join clause uses an operator other than equal (=), the operator is displayed in the join line icon.</span></span> <span data-ttu-id="aa99d-176">A tabela a seguir lista os ícones que podem ser exibidos em uma linha de junção.</span><span class="sxs-lookup"><span data-stu-id="aa99d-176">The following table lists the icons that can be displayed in a join line.</span></span>  
  
|<span data-ttu-id="aa99d-177">Ícone de linha de junção</span><span class="sxs-lookup"><span data-stu-id="aa99d-177">Join line icon</span></span>|<span data-ttu-id="aa99d-178">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="aa99d-178">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="aa99d-179">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbih.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-179">![Visual Database Tools icon](../../database-engine/media//dv3wbih.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-180">Junção interna (criada usando o sinal de igual).</span><span class="sxs-lookup"><span data-stu-id="aa99d-180">Inner join (created using equal sign).</span></span>|  
|<span data-ttu-id="aa99d-181">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbii.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-181">![Visual Database Tools icon](../../database-engine/media//dv3wbii.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-182">Junção interna baseada no operador "maior que".</span><span class="sxs-lookup"><span data-stu-id="aa99d-182">Inner join based on the "greater than" operator.</span></span> <span data-ttu-id="aa99d-183">(O operador exibido no ícone da linha de junção reflete o operador usado na junção.)</span><span class="sxs-lookup"><span data-stu-id="aa99d-183">(The operator displayed in the join line icon reflects the operator used in the join.)</span></span>|  
|<span data-ttu-id="aa99d-184">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbij.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-184">![Visual Database Tools icon](../../database-engine/media//dv3wbij.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-185">A junção externa em que todas as linhas da tabela representada à esquerda serão incluídas, mesmo se não tiverem correspondências na tabela relacionada.</span><span class="sxs-lookup"><span data-stu-id="aa99d-185">Outer join in which all rows from the table represented on the left will be included, even if they do not have matches in the related table.</span></span>|  
|<span data-ttu-id="aa99d-186">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbik.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-186">![Visual Database Tools icon](../../database-engine/media//dv3wbik.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-187">A junção externa em que todas as linhas da tabela representada à direita serão incluídas, mesmo se não tiverem correspondências na tabela relacionada.</span><span class="sxs-lookup"><span data-stu-id="aa99d-187">Outer join in which all rows from the table represented on the right will be included, even if they do not have matches in the related table.</span></span>|  
|<span data-ttu-id="aa99d-188">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbil.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-188">![Visual Database Tools icon](../../database-engine/media//dv3wbil.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-189">A junção externa completa em que todas as linhas de ambas as tabelas serão incluídas, mesmo se não tiverem correspondências na tabela relacionada.</span><span class="sxs-lookup"><span data-stu-id="aa99d-189">A full outer join in which all rows from both tables will be included, even if they do not have matches in the related table.</span></span>|  
  
 <span data-ttu-id="aa99d-190">Os ícones nas extremidades da linha de junção indicam o tipo de junção.</span><span class="sxs-lookup"><span data-stu-id="aa99d-190">Icons on the ends of the join line indicate the type of join.</span></span> <span data-ttu-id="aa99d-191">A tabela a seguir lista os tipos de junções e os ícones que podem ser exibidos nas extremidades da linha de junção.</span><span class="sxs-lookup"><span data-stu-id="aa99d-191">The following table lists the types of joins and the icons that can be displayed on the ends of the join line.</span></span>  
  
|<span data-ttu-id="aa99d-192">Ícone nas extremidades da linha de junção</span><span class="sxs-lookup"><span data-stu-id="aa99d-192">Icon on ends of join line</span></span>|<span data-ttu-id="aa99d-193">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="aa99d-193">Description</span></span>|  
|-------------------------------|-----------------|  
|<span data-ttu-id="aa99d-194">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbim.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-194">![Visual Database Tools icon](../../database-engine/media//dv3wbim.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-195">Junção uma para uma</span><span class="sxs-lookup"><span data-stu-id="aa99d-195">One-to-one join</span></span>|  
|<span data-ttu-id="aa99d-196">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbin.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-196">![Visual Database Tools icon](../../database-engine/media//dv3wbin.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-197">Junção uma para muitas</span><span class="sxs-lookup"><span data-stu-id="aa99d-197">One-to-many join</span></span>|  
|<span data-ttu-id="aa99d-198">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbio.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="aa99d-198">![Visual Database Tools icon](../../database-engine/media//dv3wbio.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="aa99d-199">O Designer de Consulta e Exibição não pode determinar o tipo de junção</span><span class="sxs-lookup"><span data-stu-id="aa99d-199">Query and View Designer cannot determine join type</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa99d-200">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aa99d-200">See Also</span></span>  
 <span data-ttu-id="aa99d-201">[Tópicos de instruções sobre como criar consultas e exibições &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="aa99d-201">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="aa99d-202">[Painel de critérios &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="aa99d-202">[Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="aa99d-203">Classificar e agrupar resultados da consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="aa99d-203">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  