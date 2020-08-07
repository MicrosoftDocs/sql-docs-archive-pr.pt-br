---
title: Definir um artigo | Microsoft Docs
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- articles [SQL Server replication], defining
- sp_addmergearticle
- adding articles
- sp_addarticle
- articles [SQL Server replication], adding
ms.assetid: 220584d8-b291-43ae-b036-fbba3cc07a2e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d7ff1f5f516d438ed07a203223acf32970a7961
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583504"
---
# <a name="define-an-article"></a><span data-ttu-id="69ee3-102">Defina um Artigo</span><span class="sxs-lookup"><span data-stu-id="69ee3-102">Define an Article</span></span>
  <span data-ttu-id="69ee3-103">Este tópico descreve como definir um artigo no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], ou RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="69ee3-103">This topic describes how to define an article in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="69ee3-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="69ee3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="69ee3-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="69ee3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="69ee3-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="69ee3-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="69ee3-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="69ee3-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="69ee3-108">**Para definir um artigo, usando:**</span><span class="sxs-lookup"><span data-stu-id="69ee3-108">**To define an article, using:**</span></span>  
  
     [<span data-ttu-id="69ee3-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="69ee3-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="69ee3-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="69ee3-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="69ee3-111">RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="69ee3-111">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="69ee3-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="69ee3-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="69ee3-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="69ee3-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="69ee3-114">Os nomes de artigos não podem incluir nenhum dos caracteres a seguir: % , \* , [ , ] , | , : , " , ?</span><span class="sxs-lookup"><span data-stu-id="69ee3-114">Article names cannot include any of the following characters: % , \* , [ , ] , | , : , " , ?</span></span> <span data-ttu-id="69ee3-115">, ' , \ , / , \< , >.</span><span class="sxs-lookup"><span data-stu-id="69ee3-115">, ' , \ , / , \< , >.</span></span> <span data-ttu-id="69ee3-116">Se algum objeto do banco de dados incluir qualquer um desses caracteres, para replicá-los será necessário especificar um nome de artigo que seja diferente do nome do objeto.</span><span class="sxs-lookup"><span data-stu-id="69ee3-116">If objects in the database include any of these characters and you want to replicate them, you must specify an article name that is different from the object name.</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="69ee3-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="69ee3-117">Security</span></span>  
 <span data-ttu-id="69ee3-118">Quando possível, solicite que os usuários insiram as credenciais de segurança em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="69ee3-118">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="69ee3-119">Se for preciso armazenar credenciais, use os serviços [criptográficos](https://go.microsoft.com/fwlink/?LinkId=34733) fornecidos pelo [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework do Windows.</span><span class="sxs-lookup"><span data-stu-id="69ee3-119">If you must store credentials, use the [cryptographic services](https://go.microsoft.com/fwlink/?LinkId=34733) provided by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows .NET Framework.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="69ee3-120">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="69ee3-120">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="69ee3-121">Crie publicações e defina artigos com o Assistente para Nova Publicação.</span><span class="sxs-lookup"><span data-stu-id="69ee3-121">Create publications and define articles with the New Publication Wizard.</span></span> <span data-ttu-id="69ee3-122">Após a criação de uma publicação, veja e modifique as propriedades da publicação na caixa de diálogo **Propriedades da Publicação – \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="69ee3-122">After a publication is created, view and modify publication properties in the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="69ee3-123">Para obter informações sobre como criar uma publicação de um banco de dados Oracle, consulte [Criar uma publicação de um banco de dados Oracle](create-a-publication-from-an-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="69ee3-123">For information about creating a publication from an Oracle database, see [Create a Publication from an Oracle Database](create-a-publication-from-an-oracle-database.md).</span></span>  
  
#### <a name="to-create-a-publication-and-define-articles"></a><span data-ttu-id="69ee3-124">Para criar uma publicação e definir artigos</span><span class="sxs-lookup"><span data-stu-id="69ee3-124">To create a publication and define articles</span></span>  
  
1.  <span data-ttu-id="69ee3-125">Conecte-se ao Publicador no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] e, em seguida, expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="69ee3-125">Connect to the Publisher in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="69ee3-126">Expanda a pasta **Replicação** e clique com o botão direito do mouse na pasta **Publicações Locais** .</span><span class="sxs-lookup"><span data-stu-id="69ee3-126">Expand the **Replication** folder, and then right-click the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="69ee3-127">Clique em **Nova Publicação**.</span><span class="sxs-lookup"><span data-stu-id="69ee3-127">Click **New Publication**.</span></span>  
  
4.  <span data-ttu-id="69ee3-128">Siga as páginas no Assistente para Nova Publicação para:</span><span class="sxs-lookup"><span data-stu-id="69ee3-128">Follow the pages in the New Publication Wizard to:</span></span>  
  
    -   <span data-ttu-id="69ee3-129">Especificar um Distribuidor se a distribuição não foi configurada no servidor.</span><span class="sxs-lookup"><span data-stu-id="69ee3-129">Specify a Distributor if distribution has not been configured on the server.</span></span> <span data-ttu-id="69ee3-130">Para obter mais informações sobre a configuração de distribuição, consulte [Configure Publishing and Distribution](../configure-publishing-and-distribution.md) (Configurar publicação e distribuição).</span><span class="sxs-lookup"><span data-stu-id="69ee3-130">For more information about configuring distribution, see [Configure Publishing and Distribution](../configure-publishing-and-distribution.md).</span></span>  
  
         <span data-ttu-id="69ee3-131">Se especificar na página do **Distribuidor** que o servidor do Publicador atuará como o seu próprio Distribuidor (um Distribuidor local) e o servidor não estiver configurado como um Distribuidor, o Assistente para Nova Publicação configurará o servidor.</span><span class="sxs-lookup"><span data-stu-id="69ee3-131">If you specify on the **Distributor** page that the Publisher server will act as its own Distributor (a local Distributor), and the server is not configured as a Distributor, the New Publication Wizard will configure the server.</span></span> <span data-ttu-id="69ee3-132">Você especificará uma pasta de instantâneo padrão para o Distribuidor na página **Pasta de Instantâneos** .</span><span class="sxs-lookup"><span data-stu-id="69ee3-132">You will specify a default snapshot folder for the Distributor on the **Snapshot Folder** page.</span></span> <span data-ttu-id="69ee3-133">A pasta de instantâneo é simplesmente um diretório que você designou como um compartilhamento, agentes que leem essa pasta e gravam nela devem ter permissões suficientes para acessá-la.</span><span class="sxs-lookup"><span data-stu-id="69ee3-133">The snapshot folder is simply a directory that you have designated as a share; agents that read from and write to this folder must have sufficient permissions to access it.</span></span> <span data-ttu-id="69ee3-134">Para obter mais informações sobre como proteger a pasta adequadamente, consulte [Secure the Snapshot Folder](../security/secure-the-snapshot-folder.md) (Proteger a pasta de instantâneo).</span><span class="sxs-lookup"><span data-stu-id="69ee3-134">For more information about securing the folder appropriately, see [Secure the Snapshot Folder](../security/secure-the-snapshot-folder.md).</span></span>  
  
         <span data-ttu-id="69ee3-135">Se você especificar que um outro servidor deverá atuar como um Distribuidor, você deverá inserir uma senha na página **Senha Administrativa** para conexões feitas do Publicador ao Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="69ee3-135">If you specify that another server should act as the Distributor, you must enter a password on the **Administrative Password** page for connections made from the Publisher to the Distributor.</span></span> <span data-ttu-id="69ee3-136">Esta senha deve corresponder à senha especificada quando o Publicador foi habilitado no Distribuidor remoto.</span><span class="sxs-lookup"><span data-stu-id="69ee3-136">This password must match the password specified when the Publisher was enabled at the remote Distributor.</span></span>  
  
         <span data-ttu-id="69ee3-137">Para obter mais informações, consulte [Configure Distribution](../configure-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="69ee3-137">For more information, see [Configure Distribution](../configure-distribution.md).</span></span>  
  
    -   <span data-ttu-id="69ee3-138">Escolha um banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="69ee3-138">Choose a publication database.</span></span>  
  
    -   <span data-ttu-id="69ee3-139">Selecione um tipo de publicação.</span><span class="sxs-lookup"><span data-stu-id="69ee3-139">Select a publication type.</span></span> <span data-ttu-id="69ee3-140">Para obter mais informações, consulte [Types of Replication](../types-of-replication.md) (Tipos de replicação).</span><span class="sxs-lookup"><span data-stu-id="69ee3-140">For more information, see [Types of Replication](../types-of-replication.md).</span></span>  
  
    -   <span data-ttu-id="69ee3-141">Especifique os dados e os objetos de banco de dados para serem publicados; opcionalmente filtre as colunas de artigos de tabela e defina as propriedades dos artigos.</span><span class="sxs-lookup"><span data-stu-id="69ee3-141">Specify data and database objects to publish; optionally filter columns from table articles, and set article properties.</span></span>  
  
    -   <span data-ttu-id="69ee3-142">Opcionalmente filtre as linhas de artigos de tabela.</span><span class="sxs-lookup"><span data-stu-id="69ee3-142">Optionally filter rows from table articles.</span></span> <span data-ttu-id="69ee3-143">Para obter mais informações, consulte [Filter Published Data](filter-published-data.md) (Filtrar dados publicados).</span><span class="sxs-lookup"><span data-stu-id="69ee3-143">For more information, see [Filter Published Data](filter-published-data.md).</span></span>  
  
    -   <span data-ttu-id="69ee3-144">Defina a agenda do Snapshot Agent.</span><span class="sxs-lookup"><span data-stu-id="69ee3-144">Set the Snapshot Agent schedule.</span></span>  
  
    -   <span data-ttu-id="69ee3-145">Especifique as credenciais sob as quais os agentes de replicação a seguir executam e fazem conexões:</span><span class="sxs-lookup"><span data-stu-id="69ee3-145">Specify the credentials under which the following replication agents run and make connections:</span></span>  
  
         <span data-ttu-id="69ee3-146">\- Snapshot Agent para todas as publicações.</span><span class="sxs-lookup"><span data-stu-id="69ee3-146">\- Snapshot Agent for all publications.</span></span>  
  
         <span data-ttu-id="69ee3-147">\- O Agente de Leitor de Log para todas as publicações transacionais.</span><span class="sxs-lookup"><span data-stu-id="69ee3-147">\- Log Reader Agent for all transactional publications.</span></span>  
  
         <span data-ttu-id="69ee3-148">\- O Queue Reader Agent para as publicações transacionais que permitem atualização de assinaturas.</span><span class="sxs-lookup"><span data-stu-id="69ee3-148">\- Queue Reader Agent for transactional publications that allow updating subscriptions.</span></span>  
  
         <span data-ttu-id="69ee3-149">Para obter mais informações, consulte [Replication Agent Security Model](../security/replication-agent-security-model.md) e [Replication Security Best Practices](../security/replication-security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="69ee3-149">For more information, see [Replication Agent Security Model](../security/replication-agent-security-model.md) and [Replication Security Best Practices](../security/replication-security-best-practices.md).</span></span>  
  
    -   <span data-ttu-id="69ee3-150">Opcionalmente faça o script da publicação.</span><span class="sxs-lookup"><span data-stu-id="69ee3-150">Optionally script the publication.</span></span> <span data-ttu-id="69ee3-151">Para obter mais informações, consulte [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="69ee3-151">For more information, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
    -   <span data-ttu-id="69ee3-152">Especifique um nome para a publicação.</span><span class="sxs-lookup"><span data-stu-id="69ee3-152">Specify a name for the publication.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="69ee3-153">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="69ee3-153">Using Transact-SQL</span></span>  
 <span data-ttu-id="69ee3-154">Após a criação da publicação, artigos poderão ser criados de forma programática, usando os procedimentos armazenados da replicação.</span><span class="sxs-lookup"><span data-stu-id="69ee3-154">After a publication has been created, articles can be created programmatically using replication stored procedures.</span></span> <span data-ttu-id="69ee3-155">Os procedimentos armazenados usados para criar um artigo dependem do tipo de publicação para o qual o artigo é definido.</span><span class="sxs-lookup"><span data-stu-id="69ee3-155">The stored procedures used to create an article will depend on the type of publication for which the article is being defined.</span></span> <span data-ttu-id="69ee3-156">Para obter mais informações, consulte [Criar uma assinatura](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="69ee3-156">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-define-an-article-for-a-snapshot-or-transactional-publication"></a><span data-ttu-id="69ee3-157">Para definir um artigo para um instantâneo ou publicação transacional</span><span class="sxs-lookup"><span data-stu-id="69ee3-157">To define an article for a Snapshot or Transactional Publication</span></span>  
  
1.  <span data-ttu-id="69ee3-158">No Publicador do banco de dados de publicação, execute [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="69ee3-158">At the Publisher on the publication database, execute [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql).</span></span> <span data-ttu-id="69ee3-159">Especifique o nome da publicação à qual o artigo pertence para \*\* \@ publicação**, um nome para o artigo para o \*\* \@ artigo**, o objeto de banco de dados que está sendo publicado para \*\* \@ source_object\*\*e quaisquer outros parâmetros opcionais.</span><span class="sxs-lookup"><span data-stu-id="69ee3-159">Specify the name of the publication to which the article belongs for **\@publication**, a name for the article for **\@article**, the database object being published for **\@source_object**, and any other optional parameters.</span></span> <span data-ttu-id="69ee3-160">Use \*\* \@ source_owner\*\* para especificar a propriedade do esquema do objeto, se não for **dbo**.</span><span class="sxs-lookup"><span data-stu-id="69ee3-160">Use **\@source_owner** to specify the schema ownership of the object, if not **dbo**.</span></span> <span data-ttu-id="69ee3-161">Se o artigo não for um artigo de tabela baseada em log, especifique o tipo de artigo para \*\* \@ tipo\*\*; para obter mais informações, consulte [especificar tipos de artigo &#40;Programação Transact-SQL de replicação&#41;](specify-article-types-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="69ee3-161">If the article is not a log-based table article, specify the article type for **\@type**; for more information, see [Specify Article Types &#40;Replication Transact-SQL Programming&#41;](specify-article-types-replication-transact-sql-programming.md).</span></span>  
  
2.  <span data-ttu-id="69ee3-162">Para filtrar linhas horizontalmente em uma tabela ou exibir um artigo, use [sp_articlefilter](/sql/relational-databases/system-stored-procedures/sp-articlefilter-transact-sql) para definir a cláusula de filtro.</span><span class="sxs-lookup"><span data-stu-id="69ee3-162">To horizontally filter rows in a table or view an article, use [sp_articlefilter](/sql/relational-databases/system-stored-procedures/sp-articlefilter-transact-sql) to define the filter clause.</span></span> <span data-ttu-id="69ee3-163">Para obter mais informações, consulte [Definir e modificar um filtro de linha estático](define-and-modify-a-static-row-filter.md).</span><span class="sxs-lookup"><span data-stu-id="69ee3-163">For more information, see [Define and Modify a Static Row Filter](define-and-modify-a-static-row-filter.md).</span></span>  
  
3.  <span data-ttu-id="69ee3-164">Para filtrar colunas verticalmente em uma tabela ou exibir um artigo, use [sp_articlecolumn](/sql/relational-databases/system-stored-procedures/sp-articlecolumn-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="69ee3-164">To vertically filter columns in a table or view an article, use [sp_articlecolumn](/sql/relational-databases/system-stored-procedures/sp-articlecolumn-transact-sql).</span></span> <span data-ttu-id="69ee3-165">Para obter mais informações, consulte [Definir e modificar um filtro de colunas](define-and-modify-a-column-filter.md).</span><span class="sxs-lookup"><span data-stu-id="69ee3-165">For more information, see [Define and Modify a Column Filter](define-and-modify-a-column-filter.md).</span></span>  
  
4.  <span data-ttu-id="69ee3-166">Execute [sp_articleview](/sql/relational-databases/system-stored-procedures/sp-articleview-transact-sql) se o artigo for filtrado.</span><span class="sxs-lookup"><span data-stu-id="69ee3-166">Execute [sp_articleview](/sql/relational-databases/system-stored-procedures/sp-articleview-transact-sql) if the article is filtered.</span></span>  
  
5.  <span data-ttu-id="69ee3-167">Se a publicação tiver assinaturas existentes e [sp_helppublication](/sql/relational-databases/system-stored-procedures/sp-helppublication-transact-sql) retornar um valor de **0** na coluna **immediate_sync** , será preciso chamar [sp_addsubscription](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) para adicionar o artigo a cada uma das assinaturas existentes.</span><span class="sxs-lookup"><span data-stu-id="69ee3-167">If the publication has existing subscriptions and [sp_helppublication](/sql/relational-databases/system-stored-procedures/sp-helppublication-transact-sql) returns a value of **0** in the **immediate_sync** column, you must call [sp_addsubscription](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) to add the article to each existing subscription.</span></span>  
  
6.  <span data-ttu-id="69ee3-168">Se a publicação tiver assinaturas pull existentes, execute [sp_refreshsubscriptions](/sql/relational-databases/system-stored-procedures/sp-refreshsubscriptions-transact-sql) no Publicador para criar um novo instantâneo para as assinaturas pull existentes que contêm apenas o novo artigo.</span><span class="sxs-lookup"><span data-stu-id="69ee3-168">If the publication has existing pull subscriptions, execute [sp_refreshsubscriptions](/sql/relational-databases/system-stored-procedures/sp-refreshsubscriptions-transact-sql) at the Publisher to create a new snapshot for existing pull subscriptions that contains just the new article.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="69ee3-169">Para assinaturas que não são iniciadas por meio de instantâneo, não há necessidade de executar [sp_refreshsubscriptions](/sql/relational-databases/system-stored-procedures/sp-refreshsubscriptions-transact-sql) , uma vez que esse procedimento é executado por [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="69ee3-169">For subscriptions that are not initialized using a snapshot, you do not need to execute [sp_refreshsubscriptions](/sql/relational-databases/system-stored-procedures/sp-refreshsubscriptions-transact-sql) as this procedure is executed by [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql).</span></span>  
  
#### <a name="to-define-an-article-for-a-merge-publication"></a><span data-ttu-id="69ee3-170">Para definir um artigo para uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="69ee3-170">To define an article for a Merge Publication</span></span>  
  
1.  <span data-ttu-id="69ee3-171">No Publicador do banco de dados de publicação, execute o [sp_addmergearticle](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="69ee3-171">At the Publisher on the publication database, execute [sp_addmergearticle](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql).</span></span> <span data-ttu-id="69ee3-172">Especifique o nome da publicação para \*\* \@ publicação**, um nome para o nome do artigo para o \*\* \@ artigo**e o objeto que está sendo publicado para \*\* \@ source_object\*\*.</span><span class="sxs-lookup"><span data-stu-id="69ee3-172">Specify the name of the publication for **\@publication**, a name for the article name for **\@article**, and the object being published for **\@source_object**.</span></span> <span data-ttu-id="69ee3-173">Para filtrar horizontalmente as linhas da tabela, especifique um valor para \*\* \@ subset_filterclause\*\*.</span><span class="sxs-lookup"><span data-stu-id="69ee3-173">To horizontally filter table rows, specify a value for **\@subset_filterclause**.</span></span> <span data-ttu-id="69ee3-174">Para obter mais informações, consulte [Definir e modificar um filtro de linha com parâmetros para um artigo de mesclagem](define-and-modify-a-parameterized-row-filter-for-a-merge-article.md) e [Definir e modificar um filtro de linha estático](define-and-modify-a-static-row-filter.md).</span><span class="sxs-lookup"><span data-stu-id="69ee3-174">For more information, see [Define and Modify a Parameterized Row Filter for a Merge Article](define-and-modify-a-parameterized-row-filter-for-a-merge-article.md) and [Define and Modify a Static Row Filter](define-and-modify-a-static-row-filter.md).</span></span> <span data-ttu-id="69ee3-175">Se o artigo não for um artigo de tabela, especifique o tipo de artigo para \*\* \@ tipo\*\*.</span><span class="sxs-lookup"><span data-stu-id="69ee3-175">If the article is not a table article, specify the article type for **\@type**.</span></span> <span data-ttu-id="69ee3-176">Para obter mais informações, consulte [Especificar tipos de artigo &#40;Programação Transact-SQL de replicação&#41;](specify-article-types-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="69ee3-176">For more information, see [Specify Article Types &#40;Replication Transact-SQL Programming&#41;](specify-article-types-replication-transact-sql-programming.md).</span></span>  
  
2.  <span data-ttu-id="69ee3-177">(Opcional) No Assinante do banco de dados de publicação, execute [sp_addmergefilter](/sql/relational-databases/system-stored-procedures/sp-addmergefilter-transact-sql) para definir um filtro de junção entre dois artigos.</span><span class="sxs-lookup"><span data-stu-id="69ee3-177">(Optional) At the Publisher on the publication database, execute [sp_addmergefilter](/sql/relational-databases/system-stored-procedures/sp-addmergefilter-transact-sql) to define a join filter between two articles.</span></span> <span data-ttu-id="69ee3-178">Para obter mais informações, consulte [Definir e modificar um filtro de junção entre artigos de mesclagem](define-and-modify-a-join-filter-between-merge-articles.md).</span><span class="sxs-lookup"><span data-stu-id="69ee3-178">For more information, see [Define and Modify a Join Filter Between Merge Articles](define-and-modify-a-join-filter-between-merge-articles.md).</span></span>  
  
3.  <span data-ttu-id="69ee3-179">(Opcional) No Publicador do banco de dados de publicação, execute [sp_mergearticlecolumn](/sql/relational-databases/system-stored-procedures/sp-mergearticlecolumn-transact-sql) para filtrar colunas de tabela.</span><span class="sxs-lookup"><span data-stu-id="69ee3-179">(Optional) At the Publisher on the publication database, execute [sp_mergearticlecolumn](/sql/relational-databases/system-stored-procedures/sp-mergearticlecolumn-transact-sql) to filter table columns.</span></span> <span data-ttu-id="69ee3-180">Para obter mais informações, consulte [Definir e modificar um filtro de colunas](define-and-modify-a-column-filter.md).</span><span class="sxs-lookup"><span data-stu-id="69ee3-180">For more information, see [Define and Modify a Column Filter](define-and-modify-a-column-filter.md).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="69ee3-181">Exemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="69ee3-181">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="69ee3-182">Esse exemplo define um artigo com base na tabela `Product` para uma publicação transacional, onde o artigo é filtrado horizontal e verticalmente.</span><span class="sxs-lookup"><span data-stu-id="69ee3-182">This example defines an article based on the `Product` table for a transactional publication, where the article is filtered both horizontally and vertically.</span></span>  
  
 [!code-sql[HowTo#sp_AddTranArticle](../../../snippets/tsql/SQL15/replication/howto/tsql/createtranpub.sql#sp_addtranarticle)]  
  
 <span data-ttu-id="69ee3-183">Este exemplo define artigos para uma publicação de mesclagem, onde o artigo `SalesOrderHeader` é filtrado estatisticamente com base em **SalesPersonID**, e o artigo `SalesOrderDetail` é filtrado por junção, com base em `SalesOrderHeader`.</span><span class="sxs-lookup"><span data-stu-id="69ee3-183">This example defines articles for a merge publication, where the `SalesOrderHeader` article is statically filtered based on **SalesPersonID**, and the `SalesOrderDetail` article is join filtered based on `SalesOrderHeader`.</span></span>  
  
 [!code-sql[HowTo#sp_AddMergeArticle](../../../snippets/tsql/SQL15/replication/howto/tsql/createmergepub.sql#sp_addmergearticle)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="69ee3-184">Usando o RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="69ee3-184">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="69ee3-185">Defina artigos de forma programada, usando o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="69ee3-185">You can define articles programmatically by using Replication Management Objects (RMO).</span></span> <span data-ttu-id="69ee3-186">As classes de RMO usadas para definir um artigo dependem do tipo de publicação para a qual o artigo é definido.</span><span class="sxs-lookup"><span data-stu-id="69ee3-186">The RMO classes that you use to define an article depend on the type of publication for which the article is defined.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="69ee3-187">Exemplos (RMO)</span><span class="sxs-lookup"><span data-stu-id="69ee3-187">Examples (RMO)</span></span>  
 <span data-ttu-id="69ee3-188">O exemplo a seguir adiciona um artigo com filtros de linha e de coluna para uma publicação transacional.</span><span class="sxs-lookup"><span data-stu-id="69ee3-188">The following example adds an article with row and column filters to a transactional publication.</span></span>  
  
 [!code-csharp[HowTo#rmo_CreateTranArticles](../../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_createtranarticles)]  
  
 [!code-vb[HowTo#rmo_vb_CreateTranArticles](../../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_createtranarticles)]  
  
 <span data-ttu-id="69ee3-189">O exemplo a seguir adiciona três artigos a uma publicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="69ee3-189">The following example adds three articles to a merge publication.</span></span> <span data-ttu-id="69ee3-190">Os artigos têm filtros de coluna, e dois filtros de função são usados para propagar o filtro de linha com parâmetros para os outros artigos.</span><span class="sxs-lookup"><span data-stu-id="69ee3-190">The articles have column filters, and two join filters are used to propagate a parameterized row filter to the other articles.</span></span>  
  
 [!code-csharp[HowTo#rmo_CreateMergeArticles](../../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_createmergearticles)]  
  
 [!code-vb[HowTo#rmo_vb_CreateMergeArticles](../../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_createmergearticles)]  
  
## <a name="see-also"></a><span data-ttu-id="69ee3-191">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="69ee3-191">See Also</span></span>  
 <span data-ttu-id="69ee3-192">[Create a Publication](create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="69ee3-192">[Create a Publication](create-a-publication.md) </span></span>  
 <span data-ttu-id="69ee3-193">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="69ee3-193">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 <span data-ttu-id="69ee3-194">[Adicionar e remover artigos de publicações existentes](add-articles-to-and-drop-articles-from-existing-publications.md) </span><span class="sxs-lookup"><span data-stu-id="69ee3-194">[Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md) </span></span>  
 <span data-ttu-id="69ee3-195">[Filtrar os dados publicados](filter-published-data.md) </span><span class="sxs-lookup"><span data-stu-id="69ee3-195">[Filter Published Data](filter-published-data.md) </span></span>  
 <span data-ttu-id="69ee3-196">[Publicar dados e objetos de banco de dados](publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="69ee3-196">[Publish Data and Database Objects](publish-data-and-database-objects.md) </span></span>  
 [<span data-ttu-id="69ee3-197">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="69ee3-197">Replication System Stored Procedures Concepts</span></span>](../concepts/replication-system-stored-procedures-concepts.md)  
  
  