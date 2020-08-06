---
title: Especificar mapeamentos de tipo de dados para um Publicador Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], data type mapping
- data types [SQL Server replication], Oracle publishing
- mapping data types [SQL Server replication]
ms.assetid: f172d631-3b8c-4912-bd0f-568366cd9870
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 26331e3864940b9c7f2a2588e3d3cbfa9944c900
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683466"
---
# <a name="specify-data-type-mappings-for-an-oracle-publisher"></a><span data-ttu-id="1bcda-102">Especificar mapeamentos de tipo de dados para um Publicador Oracle</span><span class="sxs-lookup"><span data-stu-id="1bcda-102">Specify Data Type Mappings for an Oracle Publisher</span></span>
  <span data-ttu-id="1bcda-103">Este tópico descreve como especificar mapeamentos de tipo de dados para um Publicador Oracle no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bcda-103">This topic describes how to specify data type mappings for an Oracle Publisher in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1bcda-104">Embora um conjunto de mapeamentos de tipo de dados padrão seja fornecidos para Publicadores Oracle, pode ser necessário especificar diferentes mapeamentos para determinada publicação.</span><span class="sxs-lookup"><span data-stu-id="1bcda-104">Although a set of default data type mappings are provided for Oracle Publishers, it might be necessary to specify different mappings for a given publication.</span></span>  
  
 <span data-ttu-id="1bcda-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="1bcda-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1bcda-106">**Para especificar mapeamentos de tipo de dados para um Publicador Oracle, usando:**</span><span class="sxs-lookup"><span data-stu-id="1bcda-106">**To specify data type mappings for an Oracle Publisher, using:**</span></span>  
  
     [<span data-ttu-id="1bcda-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1bcda-107">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1bcda-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1bcda-108">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1bcda-109">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1bcda-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="1bcda-110">Especifique mapeamentos de tipo de dados na guia **Mapeamento de Dados** da caixa de diálogo **Propriedades do Artigo – \<Article>** .</span><span class="sxs-lookup"><span data-stu-id="1bcda-110">Specify data type mappings on the **Data Mapping** tab of the **Article Properties - \<Article>** dialog box.</span></span> <span data-ttu-id="1bcda-111">Isso está disponível na página **Artigos** do Assistente para Nova Publicação e na caixa de diálogo **Propriedades de Publicação – \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="1bcda-111">This is available from the **Articles** page of the New Publication Wizard and the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="1bcda-112">Para obter mais informações sobre como usar o assistente e acessar a caixa de diálogo, consulte [Criar uma Publicação de um Banco de Dados Oracle](create-a-publication-from-an-oracle-database.md) e [Exibir e modificar as propriedades da publicação](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1bcda-112">For more information about using the wizard and accessing the dialog box, see [Create a Publication from an Oracle Database](create-a-publication-from-an-oracle-database.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-specify-a-data-type-mapping"></a><span data-ttu-id="1bcda-113">Para especificar um mapeamento de tipo de dados</span><span class="sxs-lookup"><span data-stu-id="1bcda-113">To specify a data type mapping</span></span>  
  
1.  <span data-ttu-id="1bcda-114">Na página **Artigos** do Assistente para Nova Publicação ou na caixa de diálogo **Propriedades da Publicação – \<Publication>** , selecione uma tabela e clique em **Propriedades do Artigo**.</span><span class="sxs-lookup"><span data-stu-id="1bcda-114">On the **Articles** page of the New Publication Wizard or the **Publication Properties - \<Publication>** dialog box, select a table, and then click **Article Properties**.</span></span>  
  
2.  <span data-ttu-id="1bcda-115">Clique em **Definir as Propriedades do Artigo Realçado da Tabela**.</span><span class="sxs-lookup"><span data-stu-id="1bcda-115">Click **Set Properties of Highlighted Table Article**.</span></span>  
  
3.  <span data-ttu-id="1bcda-116">Na guia **Mapeamento de Dados** da caixa de diálogo **Propriedades do Artigo – \<Article>** , selecione os mapeamentos na coluna **Tipo de Dados do Assinante**:</span><span class="sxs-lookup"><span data-stu-id="1bcda-116">On the **Data Mapping** tab of the **Article Properties - \<Article>** dialog box, select mappings from the **Subscriber Data Type** column:</span></span>  
  
    -   <span data-ttu-id="1bcda-117">Para alguns tipos de dados, há somente um mapeamento possível; em tal caso, a coluna na grade de propriedades é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="1bcda-117">For some data types there is only one possible mapping, in which case the column in the property grid is read-only.</span></span>  
  
    -   <span data-ttu-id="1bcda-118">Para alguns tipos, é possível selecionar mais de uma opção.</span><span class="sxs-lookup"><span data-stu-id="1bcda-118">For some types, there is more than one type that you can select.</span></span> <span data-ttu-id="1bcda-119">A[!INCLUDE[msCoName](../../../includes/msconame-md.md)] recomenda que você use o mapeamento padrão, a menos que seu aplicativo exija um mapeamento diferente.</span><span class="sxs-lookup"><span data-stu-id="1bcda-119">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] recommends that you use the default mapping unless your application requires a different mapping.</span></span> <span data-ttu-id="1bcda-120">Para obter mais informações, consulte [Mapeamento de tipo de dados para Publicadores Oracle ](../non-sql/data-type-mapping-for-oracle-publishers.md).</span><span class="sxs-lookup"><span data-stu-id="1bcda-120">For more information, see [Data Type Mapping for Oracle Publishers](../non-sql/data-type-mapping-for-oracle-publishers.md).</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1bcda-121">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1bcda-121">Using Transact-SQL</span></span>  
 <span data-ttu-id="1bcda-122">Você pode especificar programaticamente mapeamentos de tipo de dados personalizados usando procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="1bcda-122">You can specify custom data type mappings programmatically using replication stored procedures.</span></span> <span data-ttu-id="1bcda-123">Você também pode definir os mapeamentos padrão que são usados ao mapear tipos de dados entre [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o e um [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] DBMS (sistema de gerenciamento de não-banco de dados).</span><span class="sxs-lookup"><span data-stu-id="1bcda-123">You can also set the default mappings that are used when mapping data types between [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database management system (DBMS).</span></span> <span data-ttu-id="1bcda-124">Para obter mais informações, consulte [Mapeamento de tipo de dados para Publicadores Oracle ](../non-sql/data-type-mapping-for-oracle-publishers.md).</span><span class="sxs-lookup"><span data-stu-id="1bcda-124">For more information, see [Data Type Mapping for Oracle Publishers](../non-sql/data-type-mapping-for-oracle-publishers.md).</span></span>  
  
#### <a name="to-define-custom-data-type-mappings-when-creating-an-article-belonging-to-an-oracle-publication"></a><span data-ttu-id="1bcda-125">Para definir mapeamentos de tipo de dados personalizados ao criar um artigo que pertence a uma publicação Oracle</span><span class="sxs-lookup"><span data-stu-id="1bcda-125">To define custom data type mappings when creating an article belonging to an Oracle publication</span></span>  
  
1.  <span data-ttu-id="1bcda-126">Se já não houver uma, crie uma publicação Oracle.</span><span class="sxs-lookup"><span data-stu-id="1bcda-126">If one does not already exist, create an Oracle publication.</span></span>  
  
2.  <span data-ttu-id="1bcda-127">No Distribuidor, execute [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1bcda-127">At the Distributor, execute [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql).</span></span> <span data-ttu-id="1bcda-128">Especifique um valor **0** para **\@use_default_datatypes**.</span><span class="sxs-lookup"><span data-stu-id="1bcda-128">Specify a value of **0** for **\@use_default_datatypes**.</span></span> <span data-ttu-id="1bcda-129">Para obter mais informações, consulte [Define an Article](define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="1bcda-129">For more information, see [Define an Article](define-an-article.md).</span></span>  
  
3.  <span data-ttu-id="1bcda-130">No Distribuidor, execute [sp_helparticlecolumns](/sql/relational-databases/system-stored-procedures/sp-helparticlecolumns-transact-sql) para exibir o mapeamento existente para uma coluna em um artigo publicado.</span><span class="sxs-lookup"><span data-stu-id="1bcda-130">At the Distributor, execute [sp_helparticlecolumns](/sql/relational-databases/system-stored-procedures/sp-helparticlecolumns-transact-sql) to view the existing mapping for a column in a published article.</span></span>  
  
4.  <span data-ttu-id="1bcda-131">No Distribuidor, execute [sp_changearticlecolumndatatype](/sql/relational-databases/system-stored-procedures/sp-changearticlecolumndatatype-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1bcda-131">At the Distributor, execute [sp_changearticlecolumndatatype](/sql/relational-databases/system-stored-procedures/sp-changearticlecolumndatatype-transact-sql).</span></span> <span data-ttu-id="1bcda-132">Especifique o nome do Editor Oracle para **\@publisher**, assim como para **\@publication**, **\@article** e **\@column**, para definir a coluna publicada.</span><span class="sxs-lookup"><span data-stu-id="1bcda-132">Specify the name of the Oracle Publisher for **\@publisher**, as well as **\@publication**, **\@article**, and **\@column** to define the published column.</span></span> <span data-ttu-id="1bcda-133">Especifique o nome do tipo de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a mapear para **\@type**, assim como para **\@length**, **\@precision** e **\@scale**, onde aplicável.</span><span class="sxs-lookup"><span data-stu-id="1bcda-133">Specify the name of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type to map to for **\@type**, as well as **\@length**, **\@precision**, and **\@scale**, where applicable.</span></span>  
  
5.  <span data-ttu-id="1bcda-134">No Distribuidor, execute [sp_articleview](/sql/relational-databases/system-stored-procedures/sp-articleview-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1bcda-134">At the Distributor, execute [sp_articleview](/sql/relational-databases/system-stored-procedures/sp-articleview-transact-sql).</span></span> <span data-ttu-id="1bcda-135">Isso cria a exibição usada para gerar o instantâneo da publicação Oracle.</span><span class="sxs-lookup"><span data-stu-id="1bcda-135">This creates the view used to generate the snapshot from the Oracle publication.</span></span>  
  
#### <a name="to-specify-a-mapping-as-the-default-mapping-for-a-data-type"></a><span data-ttu-id="1bcda-136">Para especificar um mapeamento como mapeamento padrão para um tipo de dados</span><span class="sxs-lookup"><span data-stu-id="1bcda-136">To specify a mapping as the default mapping for a data type</span></span>  
  
1.  <span data-ttu-id="1bcda-137">(Opcional) No Distribuidor de qualquer banco de dados, execute [sp_getdefaultdatatypemapping](/sql/relational-databases/system-stored-procedures/sp-getdefaultdatatypemapping-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1bcda-137">(Optional) At the Distributor on any database, execute [sp_getdefaultdatatypemapping](/sql/relational-databases/system-stored-procedures/sp-getdefaultdatatypemapping-transact-sql).</span></span> <span data-ttu-id="1bcda-138">Especifique **\@source_dbms**, **\@source_type**, **\@destination_dbms**, **\@destination_version** e quaisquer outros parâmetros necessários para identificar a DBMS de origem.</span><span class="sxs-lookup"><span data-stu-id="1bcda-138">Specify **\@source_dbms**, **\@source_type**, **\@destination_dbms**, **\@destination_version**, and any other parameters needed to identify the source DBMS.</span></span> <span data-ttu-id="1bcda-139">As informações sobre o tipo de dados atualmente mapeados no DBMS de destino são retornadas usando os parâmetros de saída.</span><span class="sxs-lookup"><span data-stu-id="1bcda-139">Information on the currently mapped data type in the destination DBMS is returned using the output parameters.</span></span>  
  
2.  <span data-ttu-id="1bcda-140">(Opcional) Para o Distribuidor em qualquer banco de dados, execute [sp_helpdatatypemap](/sql/relational-databases/system-stored-procedures/sp-helpdatatypemap-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1bcda-140">(Optional) At the Distributor on any database, execute [sp_helpdatatypemap](/sql/relational-databases/system-stored-procedures/sp-helpdatatypemap-transact-sql).</span></span> <span data-ttu-id="1bcda-141">Especifique **\@source_dbms** e quaisquer outros parâmetros necessários para filtrar o conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="1bcda-141">Specify **\@source_dbms** and any other parameters needed to filter the result set.</span></span> <span data-ttu-id="1bcda-142">Observe o valor de **mapping_id** para o mapeamento desejado no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="1bcda-142">Note the value of **mapping_id** for the desired mapping in the result set.</span></span>  
  
3.  <span data-ttu-id="1bcda-143">(Opcional) No Distribuidor em qualquer banco de dados, execute [sp_getdefaultdatatypemapping](/sql/relational-databases/system-stored-procedures/sp-setdefaultdatatypemapping-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1bcda-143">At the Distributor on any database, execute [sp_setdefaultdatatypemapping](/sql/relational-databases/system-stored-procedures/sp-setdefaultdatatypemapping-transact-sql).</span></span>  
  
    -   <span data-ttu-id="1bcda-144">Se você souber o valor desejado de **mapping_id** obtido na etapa 2, especifique-o para **\@mapping_id**.</span><span class="sxs-lookup"><span data-stu-id="1bcda-144">If you know the desired value of **mapping_id** obtained in step 2, specify it for **\@mapping_id**.</span></span>  
  
    -   <span data-ttu-id="1bcda-145">Se não souber o **mapping_id**, especifique os parâmetros **\@source_dbms**, **\@source_type**, **\@destination_dbms**, **\@destination_type** e quaisquer outros parâmetros necessários para identificar um mapeamento existente.</span><span class="sxs-lookup"><span data-stu-id="1bcda-145">If you do not know the **mapping_id**, specify the parameters **\@source_dbms**, **\@source_type**, **\@destination_dbms**, **\@destination_type**, and any other parameters required to identify an existing mapping.</span></span>  
  
#### <a name="to-find-valid-data-types-for-a-given-oracle-data-type"></a><span data-ttu-id="1bcda-146">Para localizar tipos de dados válidos para um determinado tipo de dados Oracle</span><span class="sxs-lookup"><span data-stu-id="1bcda-146">To find valid data types for a given Oracle data type</span></span>  
  
1.  <span data-ttu-id="1bcda-147">No Distribuidor em qualquer banco de dados, execute [sp_helpdatatypemap](/sql/relational-databases/system-stored-procedures/sp-helpdatatypemap-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1bcda-147">At the Distributor on any database, execute [sp_helpdatatypemap](/sql/relational-databases/system-stored-procedures/sp-helpdatatypemap-transact-sql).</span></span> <span data-ttu-id="1bcda-148">Especifique um valor de **ORACLE** para **\@source_dbms** e quaisquer outros parâmetros necessários para filtrar o conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="1bcda-148">Specify a value of **ORACLE** for **\@source_dbms** and any other parameters needed to filter the result set.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="1bcda-149">Exemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1bcda-149">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="1bcda-150">Este exemplo altera uma coluna com um tipo de dados Oracle de NUMBER, de modo que ele seja mapeado para o tipo de dados `numeric`(38,38) do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], em vez do tipo de dados padrão `float`.</span><span class="sxs-lookup"><span data-stu-id="1bcda-150">This example changes a column with an Oracle data type of NUMBER so it is mapped to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type `numeric`(38,38), instead of the default data type `float`.</span></span>  
  
 [!code-sql[HowTo#sp_changecolumndatatype](../../../snippets/tsql/SQL15/replication/howto/tsql/datatypemapping.sql#sp_changecolumndatatype)]  
  
 <span data-ttu-id="1bcda-151">Este exemplo de consulta retorna os mapeamentos padrão e alternativos para o tipo de dados `CHAR` do Oracle 9.</span><span class="sxs-lookup"><span data-stu-id="1bcda-151">This example query returns the default and alternative mappings for the Oracle 9 data type `CHAR`.</span></span>  
  
 [!code-sql[HowTo#sp_helpcolumndatatype_char](../../../snippets/tsql/SQL15/replication/howto/tsql/datatypemapping.sql#sp_helpcolumndatatype_char)]  
  
 <span data-ttu-id="1bcda-152">Este exemplo de consulta retorna os mapeamentos padrão para o tipo de dados `NUMBER` do Oracle 9 quando ele é especificado sem uma escala ou precisão.</span><span class="sxs-lookup"><span data-stu-id="1bcda-152">This example query returns the default mappings for the Oracle 9 data type `NUMBER` when it is specified without a scale or precision.</span></span>  
  
 [!code-sql[HowTo#sp_helpcolumndatatype_number](../../../snippets/tsql/SQL15/replication/howto/tsql/datatypemapping.sql#sp_helpcolumndatatype_number)]  
  
## <a name="see-also"></a><span data-ttu-id="1bcda-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1bcda-153">See Also</span></span>  
 <span data-ttu-id="1bcda-154">[Data Type Mapping for Oracle Publishers](../non-sql/data-type-mapping-for-oracle-publishers.md) </span><span class="sxs-lookup"><span data-stu-id="1bcda-154">[Data Type Mapping for Oracle Publishers](../non-sql/data-type-mapping-for-oracle-publishers.md) </span></span>  
 <span data-ttu-id="1bcda-155">[Replicação de banco de dados heterogênea](../non-sql/heterogeneous-database-replication.md) </span><span class="sxs-lookup"><span data-stu-id="1bcda-155">[Heterogeneous Database Replication](../non-sql/heterogeneous-database-replication.md) </span></span>  
 <span data-ttu-id="1bcda-156">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="1bcda-156">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="1bcda-157">Configurar um Publicador Oracle</span><span class="sxs-lookup"><span data-stu-id="1bcda-157">Configure an Oracle Publisher</span></span>](../non-sql/configure-an-oracle-publisher.md)  
  
  