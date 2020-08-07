---
title: Pesquisa de texto completo de DDL, funções, procedimentos armazenados e exibições | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
ms.assetid: 98c36715-4195-482e-a4a3-d93ff65b75f1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 29b026ac60fd3f7d00ca519c4ced84533ce9740f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582393"
---
# <a name="full-text-search-ddl-functions-stored-procedures-and-views"></a><span data-ttu-id="b0119-102">DDL, funções, procedimentos armazenados e exibições de pesquisa de texto completo</span><span class="sxs-lookup"><span data-stu-id="b0119-102">Full-Text Search DDL, Functions, Stored Procedures, and Views</span></span>
  <span data-ttu-id="b0119-103">Lista as instruções Transact-SQL e os objetos de banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que oferecem suporte à pesquisa de texto completo, incluindo o recurso de pesquisa de propriedade.</span><span class="sxs-lookup"><span data-stu-id="b0119-103">Lists the Transact-SQL statements and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database objects that support full-text search, including the property search feature.</span></span>  
  
 <span data-ttu-id="b0119-104">Essa lista não inclui objetos preteridos.</span><span class="sxs-lookup"><span data-stu-id="b0119-104">This list does not include deprecated objects.</span></span>  
  
 <span data-ttu-id="b0119-105">Para obter a lista de objetos de banco de dados que oferecem suporte à pesquisa semântica, consulte [Pesquisa de semântica DDL, funções, procedimentos armazenados e exibições](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="b0119-105">For the list of database objects that support semantic search, see [Semantic Search DDL, Functions, Stored Procedures, and Views](../views/views.md).</span></span>  
  
##  <a name="transact-sql-data-definition-language-ddl-statements"></a><a name="ddl"></a> <span data-ttu-id="b0119-106">Instruções DDL (linguagem de definição de dados) Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b0119-106">Transact-SQL Data Definition Language (DDL) Statements</span></span>  
  
-   [<span data-ttu-id="b0119-107">CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-107">CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-catalog-transact-sql)  
  
-   [<span data-ttu-id="b0119-108">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-108">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
-   [<span data-ttu-id="b0119-109">CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-109">CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql)  
  
-   [<span data-ttu-id="b0119-110">CREATE SEARCH PROPERTY LIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-110">CREATE SEARCH PROPERTY LIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-search-property-list-transact-sql)  
  
-   [<span data-ttu-id="b0119-111">ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-111">ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql)  
  
-   [<span data-ttu-id="b0119-112">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-112">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
-   [<span data-ttu-id="b0119-113">ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-113">ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql)  
  
-   [<span data-ttu-id="b0119-114">ALTER SEARCH PROPERTY LIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-114">ALTER SEARCH PROPERTY LIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-search-property-list-transact-sql)  
  
-   [<span data-ttu-id="b0119-115">DROP FULLTEXT CATALOG &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-115">DROP FULLTEXT CATALOG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-catalog-transact-sql)  
  
-   [<span data-ttu-id="b0119-116">DROP FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-116">DROP FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-index-transact-sql)  
  
-   [<span data-ttu-id="b0119-117">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-117">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql)  
  
-   [<span data-ttu-id="b0119-118">DROP SEARCH PROPERTY LIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-118">DROP SEARCH PROPERTY LIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-search-property-list-transact-sql)  
  
##  <a name="system-predicates-and-functions"></a><a name="func"></a> <span data-ttu-id="b0119-119">Predicados de sistema e funções</span><span class="sxs-lookup"><span data-stu-id="b0119-119">System Predicates and Functions</span></span>  
  
-   [<span data-ttu-id="b0119-120">CONTAINS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-120">CONTAINS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/contains-transact-sql)  
  
-   [<span data-ttu-id="b0119-121">CONTAINSTABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-121">CONTAINSTABLE &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/containstable-transact-sql)  
  
-   [<span data-ttu-id="b0119-122">FREETEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-122">FREETEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/freetext-transact-sql)  
  
-   [<span data-ttu-id="b0119-123">FREETEXTTABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-123">FREETEXTTABLE &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/freetexttable-transact-sql)  
  
##  <a name="system-metadata-functions"></a><a name="meta"></a> <span data-ttu-id="b0119-124">Funções de metadados do sistema</span><span class="sxs-lookup"><span data-stu-id="b0119-124">System Metadata Functions</span></span>  
  
-   [<span data-ttu-id="b0119-125">COLUMNPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-125">COLUMNPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/columnproperty-transact-sql)  
  
-   [<span data-ttu-id="b0119-126">FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-126">FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql)  
  
-   [<span data-ttu-id="b0119-127">FULLTEXTSERVICEPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-127">FULLTEXTSERVICEPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/fulltextserviceproperty-transact-sql)  
  
-   [<span data-ttu-id="b0119-128">INDEXPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-128">INDEXPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/indexproperty-transact-sql)  
  
-   [<span data-ttu-id="b0119-129">OBJECTPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-129">OBJECTPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/objectpropertyex-transact-sql)  
  
-   [<span data-ttu-id="b0119-130">OBJECTPROPERTYEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-130">OBJECTPROPERTYEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/objectproperty-transact-sql)  
  
-   [<span data-ttu-id="b0119-131">SERVERPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-131">SERVERPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/serverproperty-transact-sql)  
  
##  <a name="system-stored-procedures"></a><a name="proc"></a> <span data-ttu-id="b0119-132">Procedimentos armazenados do sistema</span><span class="sxs-lookup"><span data-stu-id="b0119-132">System Stored Procedures</span></span>  
  
-   [<span data-ttu-id="b0119-133">sp_fulltext_keymappings &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-133">sp_fulltext_keymappings &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-keymappings-transact-sql)  
  
-   [<span data-ttu-id="b0119-134">sp_fulltext_load_thesaurus_file &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-134">sp_fulltext_load_thesaurus_file &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql)  
  
-   [<span data-ttu-id="b0119-135">sp_fulltext_pendingchanges &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-135">sp_fulltext_pendingchanges &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-pendingchanges-transact-sql)  
  
-   [<span data-ttu-id="b0119-136">sp_fulltext_service &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-136">sp_fulltext_service &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql)  
  
-   [<span data-ttu-id="b0119-137">sp_help_fulltext_system_components &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-137">sp_help_fulltext_system_components &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql)  
  
##  <a name="system-views---catalog-views"></a><a name="cat"></a> <span data-ttu-id="b0119-138">Exibições do sistema – Exibições do catálogo</span><span class="sxs-lookup"><span data-stu-id="b0119-138">System Views - Catalog Views</span></span>  
  
-   [<span data-ttu-id="b0119-139">sys.fulltext_catalogs &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-139">sys.fulltext_catalogs &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql)  
  
-   [<span data-ttu-id="b0119-140">sys.fulltext_document_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-140">sys.fulltext_document_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-document-types-transact-sql)  
  
-   [<span data-ttu-id="b0119-141">sys.fulltext_index_catalog_usages &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-141">sys.fulltext_index_catalog_usages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-index-catalog-usages-transact-sql)  
  
-   [<span data-ttu-id="b0119-142">sys.fulltext_index_columns &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-142">sys.fulltext_index_columns &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql)  
  
-   [<span data-ttu-id="b0119-143">sys.fulltext_index_fragments &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-143">sys.fulltext_index_fragments &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-index-fragments-transact-sql)  
  
-   [<span data-ttu-id="b0119-144">sys.fulltext_indexes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-144">sys.fulltext_indexes &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql)  
  
-   [<span data-ttu-id="b0119-145">sys.fulltext_languages &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-145">sys.fulltext_languages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql)  
  
-   [<span data-ttu-id="b0119-146">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-146">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql)  
  
-   [<span data-ttu-id="b0119-147">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-147">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
-   [<span data-ttu-id="b0119-148">sys.fulltext_system_stopwords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-148">sys.fulltext_system_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-system-stopwords-transact-sql)  
  
-   [<span data-ttu-id="b0119-149">sys.registered_search_properties &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-149">sys.registered_search_properties &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-registered-search-properties-transact-sql)  
  
-   [<span data-ttu-id="b0119-150">sys.registered_search_property_lists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-150">sys.registered_search_property_lists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-registered-search-property-lists-transact-sql)  
  
##  <a name="system-views---dynamic-management-views"></a><a name="dmv"></a> <span data-ttu-id="b0119-151">Exibições do sistema – Exibições de gerenciamento dinâmico</span><span class="sxs-lookup"><span data-stu-id="b0119-151">System Views - Dynamic Management Views</span></span>  
  
-   [<span data-ttu-id="b0119-152">sys.dm_fts_active_catalogs &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-152">sys.dm_fts_active_catalogs &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-active-catalogs-transact-sql)  
  
-   [<span data-ttu-id="b0119-153">sys.dm_fts_fdhosts &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-153">sys.dm_fts_fdhosts &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-fdhosts-transact-sql)  
  
-   [<span data-ttu-id="b0119-154">sys.dm_fts_index_keywords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-154">sys.dm_fts_index_keywords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-keywords-transact-sql)  
  
-   [<span data-ttu-id="b0119-155">sys.dm_fts_index_keywords_by_document &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-155">sys.dm_fts_index_keywords_by_document &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-keywords-by-document-transact-sql)  
  
-   [<span data-ttu-id="b0119-156">sys.dm_fts_index_keywords_by_property &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-156">sys.dm_fts_index_keywords_by_property &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-keywords-by-property-transact-sql)  
  
-   [<span data-ttu-id="b0119-157">sys.dm_fts_index_population &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-157">sys.dm_fts_index_population &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql)  
  
-   [<span data-ttu-id="b0119-158">sys.dm_fts_memory_buffers &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-158">sys.dm_fts_memory_buffers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-memory-buffers-transact-sql)  
  
-   [<span data-ttu-id="b0119-159">sys.dm_fts_memory_pools &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-159">sys.dm_fts_memory_pools &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-memory-pools-transact-sql)  
  
-   [<span data-ttu-id="b0119-160">sys.dm_fts_outstanding_batches &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-160">sys.dm_fts_outstanding_batches &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-outstanding-batches-transact-sql)  
  
-   [<span data-ttu-id="b0119-161">sys.dm_fts_parser &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-161">sys.dm_fts_parser &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-parser-transact-sql)  
  
-   [<span data-ttu-id="b0119-162">sys.dm_fts_population_ranges &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0119-162">sys.dm_fts_population_ranges &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-population-ranges-transact-sql)  
  
  
