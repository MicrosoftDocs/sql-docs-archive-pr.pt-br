---
title: Cursores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- results [SQL Server], cursors
- Transact-SQL cursors, about cursors
- cursors [SQL Server]
- data access [SQL Server], cursors
- result sets [SQL Server], cursors
- requesting cursors
- cursors [SQL Server], about cursors
ms.assetid: e668b40c-bd4d-4415-850d-20fc4872ee72
author: rothja
ms.author: jroth
ms.openlocfilehash: 055482a8cf64527f58ed983b449121a99960f566
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583630"
---
# <a name="cursors"></a><span data-ttu-id="4bf5d-102">Cursores</span><span class="sxs-lookup"><span data-stu-id="4bf5d-102">Cursors</span></span>
  <span data-ttu-id="4bf5d-103">As operações em um ato de banco de dados relacional em um conjunto completo de linhas.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-103">Operations in a relational database act on a complete set of rows.</span></span> <span data-ttu-id="4bf5d-104">Por exemplo, o conjunto de linhas retornado por uma instrução SELECT consiste de todas as linhas que satisfazem as condições na cláusula WHERE da instrução.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-104">For example, the set of rows returned by a SELECT statement consists of all the rows that satisfy the conditions in the WHERE clause of the statement.</span></span> <span data-ttu-id="4bf5d-105">Este conjunto completo de linhas retornado pela instrução é conhecido como conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-105">This complete set of rows returned by the statement is known as the result set.</span></span> <span data-ttu-id="4bf5d-106">Aplicativos, especialmente aplicativos online interativos, não podem sempre trabalhar efetivamente com todo o conjunto de resultados como uma unidade.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-106">Applications, especially interactive online applications, cannot always work effectively with the entire result set as a unit.</span></span> <span data-ttu-id="4bf5d-107">Esses aplicativos precisam de um mecanismo para trabalhar com uma linha ou um bloco pequeno de linhas de cada vez.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-107">These applications need a mechanism to work with one row or a small block of rows at a time.</span></span> <span data-ttu-id="4bf5d-108">Os cursores são uma extensão dos conjuntos de resultados que proveem esse mecanismo.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-108">Cursors are an extension to result sets that provide that mechanism.</span></span>  
  
 <span data-ttu-id="4bf5d-109">Os cursores estendem o resultado de processamento por:</span><span class="sxs-lookup"><span data-stu-id="4bf5d-109">Cursors extend result processing by:</span></span>  
  
-   <span data-ttu-id="4bf5d-110">Permitirem o posicionamento em linhas específicas do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-110">Allowing positioning at specific rows of the result set.</span></span>  
  
-   <span data-ttu-id="4bf5d-111">Recuperarem uma linha ou bloco de linhas de posições atuais em um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-111">Retrieving one row or block of rows from the current position in the result set.</span></span>  
  
-   <span data-ttu-id="4bf5d-112">Oferecerem suporte às modificações de dados nas linhas da posição atual no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-112">Supporting data modifications to the rows at the current position in the result set.</span></span>  
  
-   <span data-ttu-id="4bf5d-113">Oferecerem suporte a diferentes níveis de visibilidade às mudanças feitas por outros usuários ao banco de dados que são apresentados no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-113">Supporting different levels of visibility to changes made by other users to the database data that is presented in the result set.</span></span>  
  
-   <span data-ttu-id="4bf5d-114">Fornecerem instruções [!INCLUDE[tsql](../includes/tsql-md.md)] em scripts, procedimentos armazenados, e acionarem o acesso de gatilho aos dados em um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-114">Providing [!INCLUDE[tsql](../includes/tsql-md.md)] statements in scripts, stored procedures, and triggers access to the data in a result set.</span></span>  
  
## <a name="concepts"></a><span data-ttu-id="4bf5d-115">Conceitos</span><span class="sxs-lookup"><span data-stu-id="4bf5d-115">Concepts</span></span>  
 <span data-ttu-id="4bf5d-116">Implementações de cursor</span><span class="sxs-lookup"><span data-stu-id="4bf5d-116">Cursor Implementations</span></span>  
 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="4bf5d-117">dá suporte a três implementações de cursor.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-117">supports three cursor implementations.</span></span>  
  
 <span data-ttu-id="4bf5d-118">cursores Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4bf5d-118">Transact-SQL cursors</span></span>  
 <span data-ttu-id="4bf5d-119">Baseiam-se na sintaxe DECLARE CURSOR e são usados principalmente nos scripts [!INCLUDE[tsql](../includes/tsql-md.md)] , procedimentos armazenados e disparadores.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-119">Are based on the DECLARE CURSOR syntax and are used mainly in [!INCLUDE[tsql](../includes/tsql-md.md)] scripts, stored procedures, and triggers.</span></span> [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="4bf5d-120">os cursores são implementados no servidor e gerenciados pelas instruções [!INCLUDE[tsql](../includes/tsql-md.md)] enviadas do cliente ao servidor.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-120">cursors are implemented on the server and are managed by [!INCLUDE[tsql](../includes/tsql-md.md)] statements sent from the client to the server.</span></span> <span data-ttu-id="4bf5d-121">Eles também podem ser contidos em lotes, procedimentos armazenados ou gatilhos.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-121">They may also be contained in batches, stored procedures, or triggers.</span></span>  
  
 <span data-ttu-id="4bf5d-122">Cursores de servidor de API (interface de programação de aplicativo)</span><span class="sxs-lookup"><span data-stu-id="4bf5d-122">Application programming interface (API) server cursors</span></span>  
 <span data-ttu-id="4bf5d-123">Dão suporte a funções de cursor API no OLE DB e ODBC.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-123">Support the API cursor functions in OLE DB and ODBC.</span></span> <span data-ttu-id="4bf5d-124">Cursores de servidor API são implementados no servidor.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-124">API server cursors are implemented on the server.</span></span> <span data-ttu-id="4bf5d-125">Sempre que um aplicativo cliente chama uma função de cursor da API, o provedor OLE DB ou do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client ou o driver ODBC transmite a solicitação ao servidor para ação contra o cursor de servidor API.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-125">Each time a client application calls an API cursor function, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client OLE DB provider or ODBC driver transmits the request to the server for action against the API server cursor.</span></span>  
  
 <span data-ttu-id="4bf5d-126">Cursores do cliente</span><span class="sxs-lookup"><span data-stu-id="4bf5d-126">Client cursors</span></span>  
 <span data-ttu-id="4bf5d-127">São implementados internamente pelo driver ODBC do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client e pela DLL que implementa a API do ADO.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-127">Are implemented internally by the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client ODBC driver and by the DLL that implements the ADO API.</span></span> <span data-ttu-id="4bf5d-128">Cursores do cliente são implementados fazendo o cache de todas as linhas do conjunto de resultados no cliente.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-128">Client cursors are implemented by caching all the result set rows on the client.</span></span> <span data-ttu-id="4bf5d-129">Sempre que um aplicativo cliente chama uma função de cursor API, o driver ODBC do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client ou a DLL ADO executa a operação de cursor nas linhas do conjunto de resultados em cache no cliente.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-129">Each time a client application calls an API cursor function, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client ODBC driver or the ADO DLL performs the cursor operation on the result set rows cached on the client.</span></span>  
  
 <span data-ttu-id="4bf5d-130">Tipos de cursores</span><span class="sxs-lookup"><span data-stu-id="4bf5d-130">Type of Cursors</span></span>  
 <span data-ttu-id="4bf5d-131">Somente avanço</span><span class="sxs-lookup"><span data-stu-id="4bf5d-131">Forward-only</span></span>  
 <span data-ttu-id="4bf5d-132">Um cursor de somente avanço não dá suporte a rolagem; ele suporta apenas a busca das linhas em série do início ao término do cursor.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-132">A forward-only cursor does not support scrolling; it supports only fetching the rows serially from the start to the end of the cursor.</span></span> <span data-ttu-id="4bf5d-133">As linhas não são recuperadas do banco de dados até que sejam buscadas.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-133">The rows are not retrieved from the database until they are fetched.</span></span> <span data-ttu-id="4bf5d-134">Os efeitos de todas as instruções INSERT, UPDATE e DELETE feitas pelo usuário atual ou confirmadas por outros usuários que afetam as linhas no conjunto de resultados são visíveis como as linhas buscadas pelo cursor.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-134">The effects of all INSERT, UPDATE, and DELETE statements made by the current user or committed by other users that affect rows in the result set are visible as the rows are fetched from the cursor.</span></span>  
  
 <span data-ttu-id="4bf5d-135">Como o cursor não podem ser revertido, a maioria das alterações feitas nas linhas no banco de dados depois que a linha foi buscada não são visíveis pelo cursor.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-135">Because the cursor cannot be scrolled backward, most changes made to rows in the database after the row was fetched are not visible through the cursor.</span></span> <span data-ttu-id="4bf5d-136">Nos casos em que um valor usado para determinar o local da linha dentro do conjunto de resultados é modificado, como a atualização de uma coluna coberta por um índice clusterizado, o valor modificado é visível pelo cursor.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-136">In cases where a value used to determine the location of the row within the result set is modified, such as updating a column covered by a clustered index, the modified value is visible through the cursor.</span></span>  
  
 <span data-ttu-id="4bf5d-137">Embora os modelos de cursor de API do banco de dados considerem um cursor de somente avanço um tipo distinto de cursor, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] não faz isso.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-137">Although the database API cursor models consider a forward-only cursor to be a distinct type of cursor, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] does not.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="4bf5d-138">considera tanto somente de avanço quanto rolagem como opções que podem ser aplicadas a cursores estáticos, controlados por conjuntos de chaves e dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-138">considers both forward-only and scroll as options that can be applied to static, keyset-driven, and dynamic cursors.</span></span> [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="4bf5d-139">os cursores dão suporte a cursores estáticos somente de avanço, controlados por conjuntos de chaves e dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-139">cursors support forward-only static, keyset-driven, and dynamic cursors.</span></span> <span data-ttu-id="4bf5d-140">Os modelos de cursor de API de banco de dados assumem que os cursores estáticos, controlados por conjunto de chaves e dinâmicos são sempre roláveis.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-140">The database API cursor models assume that static, keyset-driven, and dynamic cursors are always scrollable.</span></span> <span data-ttu-id="4bf5d-141">Quando um atributo ou propriedade de cursor de API de banco de dados é definido como somente de avanço, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o implementa como um cursor dinâmico somente de avanço.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-141">When a database API cursor attribute or property is set to forward-only, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] implements this as a forward-only dynamic cursor.</span></span>  
  
 <span data-ttu-id="4bf5d-142">Estático</span><span class="sxs-lookup"><span data-stu-id="4bf5d-142">Static</span></span>  
 <span data-ttu-id="4bf5d-143">O conjunto completo de resultados de um cursor estático é criado em **tempdb** quando o cursor está aberto.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-143">The complete result set of a static cursor is built in **tempdb** when the cursor is opened.</span></span> <span data-ttu-id="4bf5d-144">Um cursor estático sempre exibe o conjunto de resultados como ele estava quando o cursor estava aberto.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-144">A static cursor always displays the result set as it was when the cursor was opened.</span></span> <span data-ttu-id="4bf5d-145">Os cursores estáticos detectam poucas ou nenhuma alteração, porém consomem relativamente poucos recursos durante a rolagem.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-145">Static cursors detect few or no changes, but consume relatively few resources while scrolling.</span></span>  
  
 <span data-ttu-id="4bf5d-146">O cursor não reflete qualquer mudança feita no banco de dados que afeta a associação do conjunto de resultados ou as alterações feitas nos valores nas colunas das linhas que compõem o conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-146">The cursor does not reflect any changes made in the database that affect either the membership of the result set or changes to the values in the columns of the rows that make up the result set.</span></span> <span data-ttu-id="4bf5d-147">Um cursor estático não exibe novas linhas inseridas no banco de dados após o cursor ter sido aberto, mesmo se elas corresponderem aos critérios de pesquisa da instrução SELECT do cursor.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-147">A static cursor does not display new rows inserted in the database after the cursor was opened, even if they match the search conditions of the cursor SELECT statement.</span></span> <span data-ttu-id="4bf5d-148">Se as filas que constituem o conjunto de resultados forem atualizadas por outros usuários, os novos valores de dados não serão exibidos no cursor estático.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-148">If rows making up the result set are updated by other users, the new data values are not displayed in the static cursor.</span></span> <span data-ttu-id="4bf5d-149">O cursor estático exibe linhas excluídas do banco de dados após o cursor ter sido aberto.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-149">The static cursor displays rows deleted from the database after the cursor was opened.</span></span> <span data-ttu-id="4bf5d-150">Nenhuma operação UPDATE, INSERT ou DELETE são refletidas em um cursor estático (a menos que o cursor esteja fechado e reaberto), nem mesmo alterações feitas usando a mesma conexão que abriu o cursor.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-150">No UPDATE, INSERT, or DELETE operations are reflected in a static cursor (unless the cursor is closed and reopened), not even modifications made using the same connection that opened the cursor.</span></span>  
  
 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="4bf5d-151">cursores estáticos são sempre somente leitura.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-151">static cursors are always read-only.</span></span>  
  
 <span data-ttu-id="4bf5d-152">Como o conjunto de resultados de um cursor estático é armazenado em uma tabela de trabalho no **tempdb**, o tamanho das linhas do conjunto de resultados não pode exceder o tamanho máximo de linhas para uma tabela [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4bf5d-152">Because the result set of a static cursor is stored in a work table in **tempdb**, the size of the rows in the result set cannot exceed the maximum row size for a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="4bf5d-153">usa o termo insensitive para cursores estáticos.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-153">uses the term insensitive for static cursors.</span></span> <span data-ttu-id="4bf5d-154">Algum banco de dados APIs os identificam como cursores de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-154">Some database APIs identify them as snapshot cursors.</span></span>  
  
 <span data-ttu-id="4bf5d-155">Keyset</span><span class="sxs-lookup"><span data-stu-id="4bf5d-155">Keyset</span></span>  
 <span data-ttu-id="4bf5d-156">A associação e a ordem de linhas em um cursor controlado por conjunto de chaves são fixadas quando o cursor é aberto.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-156">The membership and order of rows in a keyset-driven cursor are fixed when the cursor is opened.</span></span> <span data-ttu-id="4bf5d-157">Os cursores controlados por conjuntos de chaves são controlados por um conjunto exclusivo de identificadores, as chaves, conhecido como conjunto de chaves.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-157">Keyset-driven cursors are controlled by a set of unique identifiers, keys, known as the keyset.</span></span> <span data-ttu-id="4bf5d-158">As chaves são criadas a partir de um conjunto de colunas, que identificam exclusivamente as linhas no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-158">The keys are built from a set of columns that uniquely identify the rows in the result set.</span></span> <span data-ttu-id="4bf5d-159">O conjunto de chaves é o conjunto dos valores de chaves de todas as linhas qualificadas para a instrução SELECT no momento em que o cursor foi aberto.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-159">The keyset is the set of the key values from all the rows that qualified for the SELECT statement at the time the cursor was opened.</span></span> <span data-ttu-id="4bf5d-160">O conjunto de chaves para um cursor controlado por conjunto de chaves é criado no **tempdb** quando o cursor é aberto.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-160">The keyset for a keyset-driven cursor is built in **tempdb** when the cursor is opened.</span></span>  
  
 <span data-ttu-id="4bf5d-161">Dinâmico</span><span class="sxs-lookup"><span data-stu-id="4bf5d-161">Dynamic</span></span>  
 <span data-ttu-id="4bf5d-162">Os cursores dinâmicos são o oposto dos cursores estáticos.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-162">Dynamic cursors are the opposite of static cursors.</span></span> <span data-ttu-id="4bf5d-163">Cursores dinâmicos refletem todas as alterações feitas nas linhas de seu conjunto de resultados ao rolar pelo cursor.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-163">Dynamic cursors reflect all changes made to the rows in their result set when scrolling through the cursor.</span></span> <span data-ttu-id="4bf5d-164">Os valores de dados, a ordem e a associação das linhas do conjunto de resultados podem ser alterados em cada busca.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-164">The data values, order, and membership of the rows in the result set can change on each fetch.</span></span> <span data-ttu-id="4bf5d-165">Todas as instruções UPDATE, INSERT e DELETE feitas por todos os usuários são visíveis pelo cursor.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-165">All UPDATE, INSERT, and DELETE statements made by all users are visible through the cursor.</span></span> <span data-ttu-id="4bf5d-166">As atualizações são visíveis imediatamente se forem feitas por meio do cursor usando uma função de API como **SQLSetPos** ou a cláusula [!INCLUDE[tsql](../includes/tsql-md.md)] WHERE CURRENT OF.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-166">Updates are visible immediately if they are made through the cursor using either an API function such as **SQLSetPos** or the [!INCLUDE[tsql](../includes/tsql-md.md)] WHERE CURRENT OF clause.</span></span> <span data-ttu-id="4bf5d-167">As atualizações feitas fora do cursor não são visíveis até serem confirmadas, a menos que o nível de isolamento da transação do cursor esteja definido para ler não confirmadas.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-167">Updates made outside the cursor are not visible until they are committed, unless the cursor transaction isolation level is set to read uncommitted.</span></span> <span data-ttu-id="4bf5d-168">Planos de cursor dinâmicos nunca usam índices espaciais.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-168">Dynamic cursor plans never use spatial indexes.</span></span>  
  
## <a name="requesting-a-cursor"></a><span data-ttu-id="4bf5d-169">Solicitando um cursor</span><span class="sxs-lookup"><span data-stu-id="4bf5d-169">Requesting a Cursor</span></span>  
 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="4bf5d-170">dá suporte a dois métodos de solicitação de cursor:</span><span class="sxs-lookup"><span data-stu-id="4bf5d-170">supports two methods for requesting a cursor:</span></span>  
  
-   [!INCLUDE[tsql](../includes/tsql-md.md)]  
  
     <span data-ttu-id="4bf5d-171">A linguagem [!INCLUDE[tsql](../includes/tsql-md.md)] oferece suporte a uma sintaxe para utilizar cursores modelados após a sintaxe de cursor ISO.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-171">The [!INCLUDE[tsql](../includes/tsql-md.md)] language supports a syntax for using cursors modeled after the ISO cursor syntax.</span></span>  
  
-   <span data-ttu-id="4bf5d-172">Funções de cursor de interface de programação de aplicativo (API) de banco de dados</span><span class="sxs-lookup"><span data-stu-id="4bf5d-172">Database application programming interface (API) cursor functions</span></span>  
  
     [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="4bf5d-173">dá suporte à funcionalidade do cursor dessas APIs de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="4bf5d-173">supports the cursor functionality of these database APIs:</span></span>  
  
    -   <span data-ttu-id="4bf5d-174">ADO ([!INCLUDE[msCoName](../includes/msconame-md.md)] ActiveX Data Object)</span><span class="sxs-lookup"><span data-stu-id="4bf5d-174">ADO ([!INCLUDE[msCoName](../includes/msconame-md.md)] ActiveX Data Object)</span></span>  
  
    -   <span data-ttu-id="4bf5d-175">OLE DB</span><span class="sxs-lookup"><span data-stu-id="4bf5d-175">OLE DB</span></span>  
  
    -   <span data-ttu-id="4bf5d-176">ODBC (Open Database Connectivity)</span><span class="sxs-lookup"><span data-stu-id="4bf5d-176">ODBC (Open Database Connectivity)</span></span>  
  
 <span data-ttu-id="4bf5d-177">Um aplicativo não deve nunca misturar estes dois métodos de solicitar um cursor.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-177">An application should never mix these two methods of requesting a cursor.</span></span> <span data-ttu-id="4bf5d-178">Um aplicativo que tenha usado um API para especificar comportamentos de cursor não deveria portanto executar uma instrução [!INCLUDE[tsql](../includes/tsql-md.md)] DECLARE CURSOR para também solicitar um cursor [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4bf5d-178">An application that has used the API to specify cursor behaviors should not then execute a [!INCLUDE[tsql](../includes/tsql-md.md)] DECLARE CURSOR statement to also request a [!INCLUDE[tsql](../includes/tsql-md.md)] cursor.</span></span> <span data-ttu-id="4bf5d-179">Um aplicativo deve apenas executar DECLARE CURSOR se ele tiver retornado todos os atributos API do cursor de volta ao seu padrão.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-179">An application should only execute DECLARE CURSOR if it has set all the API cursor attributes back to their defaults.</span></span>  
  
 <span data-ttu-id="4bf5d-180">Se não tiver havido uma solicitação de um cursor API, o [!INCLUDE[tsql](../includes/tsql-md.md)] , [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] padroniza para retornar um conjunto completo de resultados, conhecido como um conjunto padrão de resultados, para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-180">If neither a [!INCLUDE[tsql](../includes/tsql-md.md)] nor API cursor has been requested, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] defaults to returning a complete result set, known as a default result set, to the application.</span></span>  
  
## <a name="cursor-process"></a><span data-ttu-id="4bf5d-181">Processo do cursor</span><span class="sxs-lookup"><span data-stu-id="4bf5d-181">Cursor Process</span></span>  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="4bf5d-182">cursores e cursores da API têm sintaxe diferente, mas o seguinte processo geral é usado com todos os cursores do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4bf5d-182">cursors and API cursors have different syntax, but the following general process is used with all [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cursors:</span></span>  
  
1.  <span data-ttu-id="4bf5d-183">Associe um cursor ao conjunto de resultados de uma instrução [!INCLUDE[tsql](../includes/tsql-md.md)] e defina as características do cursor, tais como se as filas no cursor podem ser atualizadas ou não.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-183">Associate a cursor with the result set of a [!INCLUDE[tsql](../includes/tsql-md.md)] statement, and define characteristics of the cursor, such as whether the rows in the cursor can be updated.</span></span>  
  
2.  <span data-ttu-id="4bf5d-184">Execute a instrução [!INCLUDE[tsql](../includes/tsql-md.md)] para preencher o cursor.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-184">Execute the [!INCLUDE[tsql](../includes/tsql-md.md)] statement to populate the cursor.</span></span>  
  
3.  <span data-ttu-id="4bf5d-185">Recupere as linhas no cursor que você quer visualizar.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-185">Retrieve the rows in the cursor you want to see.</span></span> <span data-ttu-id="4bf5d-186">A operação para recuperar uma linha ou um bloco de linhas de um cursor é denominada busca.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-186">The operation to retrieve one row or one block of rows from a cursor is called a fetch.</span></span> <span data-ttu-id="4bf5d-187">Executar uma série de buscas para recuperar linhas em direção para frente ou para trás é chamado rolagem.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-187">Performing a series of fetches to retrieve rows in either a forward or backward direction is called scrolling.</span></span>  
  
4.  <span data-ttu-id="4bf5d-188">Opcionalmente, execute operações de modificação (atualização ou exclusão) na fila da posição atual no cursor.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-188">Optionally, perform modification operations (update or delete) on the row at the current position in the cursor.</span></span>  
  
5.  <span data-ttu-id="4bf5d-189">Feche o cursor.</span><span class="sxs-lookup"><span data-stu-id="4bf5d-189">Close the cursor.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="4bf5d-190">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="4bf5d-190">Related Content</span></span>  
 <span data-ttu-id="4bf5d-191">[Comportamentos de cursor](native-client-odbc-cursors/cursor-behaviors.md) [Como os cursores são implementados](native-client-odbc-cursors/implementation/how-cursors-are-implemented.md)</span><span class="sxs-lookup"><span data-stu-id="4bf5d-191">[Cursor Behaviors](native-client-odbc-cursors/cursor-behaviors.md) [How Cursors Are Implemented](native-client-odbc-cursors/implementation/how-cursors-are-implemented.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bf5d-192">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4bf5d-192">See Also</span></span>  
 <span data-ttu-id="4bf5d-193">[DECLARAR CURSOR &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-cursor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4bf5d-193">[DECLARE CURSOR &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-cursor-transact-sql) </span></span>  
 <span data-ttu-id="4bf5d-194">[Cursores &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/cursors-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4bf5d-194">[Cursors &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/cursors-transact-sql) </span></span>  
 <span data-ttu-id="4bf5d-195">[Funções de cursor &#40;&#41;Transact-SQL](/sql/t-sql/functions/cursor-functions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4bf5d-195">[Cursor Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/cursor-functions-transact-sql) </span></span>  
 [<span data-ttu-id="4bf5d-196">Procedimentos armazenados de cursor &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4bf5d-196">Cursor Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/cursor-stored-procedures-transact-sql)  
  
  