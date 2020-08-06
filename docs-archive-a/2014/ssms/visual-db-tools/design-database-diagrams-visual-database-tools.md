---
title: Criar diagramas de banco de dados (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65536
- vdt.DatabaseDesigner
helpviewer_keywords:
- Database Diagram Designer
- Visual Database Tools [SQL Server], database diagrams
- database diagrams [SQL Server], designing
- diagrams [SQL Server], designing
ms.assetid: 6d2c14e1-3d73-4d10-ae5b-7f2b5d6c4ea8
author: stevestein
ms.author: sstein
ms.openlocfilehash: bb4cbc518b6878ed8fb6e9f7d5d2d00803ab4d62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679623"
---
# <a name="design-database-diagrams-visual-database-tools"></a><span data-ttu-id="ca395-102">Criar diagramas de banco de dados (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="ca395-102">Design Database Diagrams (Visual Database Tools)</span></span>
  <span data-ttu-id="ca395-103">O Designer de Banco de Dados é uma ferramenta visual que permite projetar e visualizar um banco de dados ao qual se está conectado.</span><span class="sxs-lookup"><span data-stu-id="ca395-103">The Database Designer is a visual tool that allows you to design and visualize a database to which you are connected.</span></span> <span data-ttu-id="ca395-104">Ao criar um banco de dados, você pode usar o Designer de Banco de Dados para criar, editar ou excluir tabelas, colunas, chaves, índices, relações e restrições.</span><span class="sxs-lookup"><span data-stu-id="ca395-104">When designing a database, you can use Database Designer to create, edit, or delete tables, columns, keys, indexes, relationships, and constraints.</span></span> <span data-ttu-id="ca395-105">Para visualizar um banco de dados, você pode criar um ou mais diagramas que ilustrem todas ou parte das tabelas, colunas, chaves e relações.</span><span class="sxs-lookup"><span data-stu-id="ca395-105">To visualize a database, you can create one or more diagrams illustrating some or all of the tables, columns, keys, and relationships in it.</span></span>  
  
 <span data-ttu-id="ca395-106">![Diagrama de banco de dados mostrando as relações de tabela](../../database-engine/media//dv3w7c1.gif "Diagrama de banco de dados mostrando as relações de tabela")</span><span class="sxs-lookup"><span data-stu-id="ca395-106">![Database diagram illustrating table relationships](../../database-engine/media//dv3w7c1.gif "Database diagram illustrating table relationships")</span></span>  
  
 <span data-ttu-id="ca395-107">De qualquer banco de dado, você pode criar quantos diagramas desejar; cada tabela de banco de dados podendo aparecer em qualquer número de diagramas.</span><span class="sxs-lookup"><span data-stu-id="ca395-107">For any database, you can create as many database diagrams as you like; each database table can appear on any number of diagrams.</span></span> <span data-ttu-id="ca395-108">Dessa forma, é possível criar diagramas diferentes para visualizar partes diferentes do banco de dados, ou destacar aspectos diferentes do projeto.</span><span class="sxs-lookup"><span data-stu-id="ca395-108">Thus, you can create different diagrams to visualize different portions of the database, or to accentuate different aspects of the design.</span></span> <span data-ttu-id="ca395-109">Por exemplo, você pode criar um diagrama amplo, que mostre todas as tabelas e colunas, e pode criar um diagrama menor, que mostre todas as tabelas sem mostrar as colunas.</span><span class="sxs-lookup"><span data-stu-id="ca395-109">For example, you can create a large diagram showing all tables and columns, and you can create a smaller diagram showing all tables without showing the columns.</span></span>  
  
 <span data-ttu-id="ca395-110">Todo diagrama de banco de dados criado fica armazenado no banco de dados associado.</span><span class="sxs-lookup"><span data-stu-id="ca395-110">Each database diagram you create is stored in the associated database.</span></span>  
  
## <a name="tables-and-columns-in-a-database-diagram"></a><span data-ttu-id="ca395-111">Tabelas e colunas de um diagrama de banco de dados</span><span class="sxs-lookup"><span data-stu-id="ca395-111">Tables and Columns in a Database Diagram</span></span>  
 <span data-ttu-id="ca395-112">Dentro de um diagrama de banco de dados, cada tabela pode aparecer com três recursos distintos: uma barra de título, um seletor de linha e um conjunto de colunas de propriedade.</span><span class="sxs-lookup"><span data-stu-id="ca395-112">Within a database diagram, each table can appear with three distinct features: a title bar, a row selector, and a set of property columns.</span></span>  
  
 <span data-ttu-id="ca395-113">**Barra de Título** A barra de título mostra o nome da tabela</span><span class="sxs-lookup"><span data-stu-id="ca395-113">**Title Bar** The title bar shows the name of the table</span></span>  
  
 <span data-ttu-id="ca395-114">Se você modificou uma tabela e ainda não a salvou, um asterisco (\*) aparecerá no final do nome da tabela, indicando que há alterações ainda não salvas.</span><span class="sxs-lookup"><span data-stu-id="ca395-114">If you have modified a table and have not yet saved it, an asterisk (\*) appears at the end of the table name to indicate unsaved changes.</span></span> <span data-ttu-id="ca395-115">Para obter informações sobre como salvar tabelas e diagramas alterados, consulte [Trabalhar com diagramas de banco de dados &#40;Visual Database Tools&#41;](visual-database-tools.md)</span><span class="sxs-lookup"><span data-stu-id="ca395-115">For information about saving modified tables and diagrams, see [Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md)</span></span>  
  
 <span data-ttu-id="ca395-116">**Seletor de linhas** Clique no seletor de linhas para selecionar uma coluna de banco de dados na tabela.</span><span class="sxs-lookup"><span data-stu-id="ca395-116">**Row Selector** You can click the row selector to select a database column in the table.</span></span> <span data-ttu-id="ca395-117">O seletor de linhas exibirá um símbolo de chave caso a coluna conste da chave primária da tabela.</span><span class="sxs-lookup"><span data-stu-id="ca395-117">The row selector displays a key symbol if the column is in the table's primary key.</span></span> <span data-ttu-id="ca395-118">Para obter informações sobre chaves primárias, consulte [restrições de chave primária e Foreign](../../relational-databases/tables/primary-and-foreign-key-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="ca395-118">For information about primary keys, see [Primary and Foreign Key Constraints](../../relational-databases/tables/primary-and-foreign-key-constraints.md).</span></span>  
  
 <span data-ttu-id="ca395-119">**Colunas de propriedade** O conjunto de colunas de propriedade é visível em algumas exibições de sua tabela.</span><span class="sxs-lookup"><span data-stu-id="ca395-119">**Property Columns** The set of property columns is visible only in the certain views of your table.</span></span> <span data-ttu-id="ca395-120">Você pode exibir uma tabela em qualquer uma das cinco exibições diferentes para poder gerenciar o tamanho e o layout do diagrama.</span><span class="sxs-lookup"><span data-stu-id="ca395-120">You can view a table in any of five different views to help you manage the size and layout of your diagram.</span></span>  
  
 <span data-ttu-id="ca395-121">Para obter mais informações sobre modos de exibição de tabela, consulte [Personalizar a quantidade de informações exibidas em diagramas &#40;Visual Database Tools&#41;](customize-the-amount-of-information-displayed-in-diagrams-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ca395-121">For more information about table views, see [Customize the Amount of Information Displayed in Diagrams &#40;Visual Database Tools&#41;](customize-the-amount-of-information-displayed-in-diagrams-visual-database-tools.md).</span></span>  
  
## <a name="relationships-in-a-database-diagram"></a><span data-ttu-id="ca395-122">As relações no diagrama de banco de dados</span><span class="sxs-lookup"><span data-stu-id="ca395-122">Relationships in a Database Diagram</span></span>  
 <span data-ttu-id="ca395-123">Em um diagrama de banco de dados, cada relação pode aparecer com três recursos distintos: pontos de extremidade, estilo de linha e tabelas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="ca395-123">Within a database diagram, each relationship can appear with three distinct features: endpoints, a line style, and related tables.</span></span>  
  
 <span data-ttu-id="ca395-124">**Pontos de extremidade** Os pontos de extremidade da linha indicam se a relação é de um-para-um ou de um-para-muitos.</span><span class="sxs-lookup"><span data-stu-id="ca395-124">**Endpoints** The endpoints of the line indicate whether the relationship is one-to-one or one-to-many.</span></span> <span data-ttu-id="ca395-125">Se uma relação tiver uma chave em um ponto de extremidade e o dígito oito no outro, trata-se de uma relação um para muitos.</span><span class="sxs-lookup"><span data-stu-id="ca395-125">If a relationship has a key at one endpoint and a figure-eight at the other, it is a one-to-many relationship.</span></span> <span data-ttu-id="ca395-126">Se a relação tiver uma chave em cada ponto de extremidade, trata-se de uma relação um para um.</span><span class="sxs-lookup"><span data-stu-id="ca395-126">If a relationship has a key at each endpoint, it is a one-to-one relationship.</span></span>  
  
 <span data-ttu-id="ca395-127">**Estilo de linha** A linha em si (não seus pontos de extremidade) indica se o DBMS (sistema de gerenciamento de banco de dados) impõe a integridade referencial para a relação quando novos dados são adicionados à tabela de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="ca395-127">**Line Style** The line itself (not its endpoints) indicates whether the Database Management System (DBMS) enforces referential integrity for the relationship when new data is added to the foreign-key table.</span></span> <span data-ttu-id="ca395-128">Se a linha parecer sólida, o DBMS imporá a integridade referencial à relação quando houver adição ou modificação de linhas na tabela de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="ca395-128">If the line appears solid, the DBMS enforces referential integrity for the relationship when rows are added or modified in the foreign-key table.</span></span> <span data-ttu-id="ca395-129">Se a linha parecer pontilhada, o DBMS não imporá a integridade referencial à relação quando houver adição ou modificação de linhas na tabela de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="ca395-129">If the line appears dotted, the DBMS does not enforce referential integrity for the relationship when rows are added or modified in the foreign-key table.</span></span>  
  
 <span data-ttu-id="ca395-130">**Tabelas relacionadas** A linha da relação indica que existe uma relação de chave estrangeira entre uma e outra tabela.</span><span class="sxs-lookup"><span data-stu-id="ca395-130">**Related Tables** The relationship line indicates that a foreign-key relationship exists between one table and another.</span></span> <span data-ttu-id="ca395-131">Em uma relação um para muitos, a tabela de chave estrangeira é a tabela próxima ao símbolo do dígito oito da linha.</span><span class="sxs-lookup"><span data-stu-id="ca395-131">For a one-to-many relationship, the foreign-key table is the table near the line's figure-eight symbol.</span></span> <span data-ttu-id="ca395-132">Se ambas as extremidades da linha estiverem anexadas à mesma tabela, trata-se de uma relação reflexiva.</span><span class="sxs-lookup"><span data-stu-id="ca395-132">If both endpoints of the line attach to the same table, the relationship is a reflexive relationship.</span></span> <span data-ttu-id="ca395-133">Para obter mais informações, consulte [Desenhar relações reflexivas &#40;Visual Database Tools&#41;](draw-reflexive-relationships-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ca395-133">For more information, see [Draw Reflexive Relationships &#40;Visual Database Tools&#41;](draw-reflexive-relationships-visual-database-tools.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ca395-134">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ca395-134">In this Section</span></span>  
 [<span data-ttu-id="ca395-135">Compreender a propriedade do diagrama de banco de dados &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ca395-135">Understand Database Diagram Ownership &#40;Visual Database Tools&#41;</span></span>](understand-database-diagram-ownership-visual-database-tools.md)  
  
 [<span data-ttu-id="ca395-136">Navegar no Designer de Diagramas de Banco de Dados &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ca395-136">Navigate in Database Diagram Designer &#40;Visual Database Tools&#41;</span></span>](navigate-in-database-diagram-designer-visual-database-tools.md)  
  
 [<span data-ttu-id="ca395-137">Configurar o Designer de Diagramas de Banco de Dados &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ca395-137">Set Up Database Diagram Designer &#40;Visual Database Tools&#41;</span></span>](set-up-database-diagram-designer-visual-database-tools.md)  
  
 [<span data-ttu-id="ca395-138">Atualizar diagramas de banco de dados de edições anteriores &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ca395-138">Upgrade Database Diagrams from Previous Editions &#40;Visual Database Tools&#41;</span></span>](upgrade-database-diagrams-from-previous-editions-visual-database-tools.md)  
  
 [<span data-ttu-id="ca395-139">Abrir o Designer de Diagramas de Banco de Dados &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ca395-139">Open Database Diagram Designer &#40;Visual Database Tools&#41;</span></span>](open-database-diagram-designer-visual-database-tools.md)  
  
## <a name="see-also"></a><span data-ttu-id="ca395-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ca395-140">See Also</span></span>  
 <span data-ttu-id="ca395-141">[Trabalhar com diagramas de banco de dados &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ca395-141">[Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="ca395-142">[Trabalhar com tabelas no diagrama de banco de dados &#40;Visual Database Tools&#41;](work-with-tables-in-database-diagram-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ca395-142">[Work with Tables in Database Diagram &#40;Visual Database Tools&#41;](work-with-tables-in-database-diagram-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="ca395-143">Trabalhar com layout de diagrama &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ca395-143">Work with Diagram Layout &#40;Visual Database Tools&#41;</span></span>](work-with-diagram-layout-visual-database-tools.md)  
  
  