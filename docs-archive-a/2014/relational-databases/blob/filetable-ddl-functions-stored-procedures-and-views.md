---
title: DDL, funções, procedimentos armazenados e exibições de FileTable | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], database objects
ms.assetid: 7e2e0f7f-94a8-4178-8bc7-d2e14ac8528c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3fca483581a47720cf0d923506f4439e3e614520
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684772"
---
# <a name="filetable-ddl-functions-stored-procedures-and-views"></a><span data-ttu-id="8d37e-102">DDL, funções, procedimentos armazenados e exibições de FileTable</span><span class="sxs-lookup"><span data-stu-id="8d37e-102">FileTable DDL, Functions, Stored Procedures, and Views</span></span>
  <span data-ttu-id="8d37e-103">Lista as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] e os objetos de banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que foram adicionados ou alterados para oferecer suporte ao recurso FileTable no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d37e-103">Lists the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database objects that have been added or changed to support the FileTable feature in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8d37e-104">A coluna de Status nas tabelas a seguir indica se o item é novo no [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], ou se estava presente em versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mas foi alterado no [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] para dar suporte à pesquisa semântica.</span><span class="sxs-lookup"><span data-stu-id="8d37e-104">The Status column in the following tables indicates whether the item is new in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], or was present in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but has been changed in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] to support semantic search.</span></span>  
  
 <span data-ttu-id="8d37e-105">Para obter a lista de instruções e objetos de banco de dados que oferecem suporte ao FILESTREAM, consulte [FILESTREAM DDL, Functions, Stored Procedures, and Views](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="8d37e-105">For the list of statements and database objects that support FILESTREAM, see [FILESTREAM DDL, Functions, Stored Procedures, and Views](../views/views.md).</span></span>  
  
##  <a name="transact-sql-data-definition-language-ddl-statements"></a><a name="ddl"></a> <span data-ttu-id="8d37e-106">Instruções DDL (linguagem de definição de dados) Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8d37e-106">Transact-SQL Data Definition Language (DDL) Statements</span></span>  
  
|<span data-ttu-id="8d37e-107">Objeto</span><span class="sxs-lookup"><span data-stu-id="8d37e-107">Object</span></span>|<span data-ttu-id="8d37e-108">Status</span><span class="sxs-lookup"><span data-stu-id="8d37e-108">Status</span></span>|<span data-ttu-id="8d37e-109">Mais informações</span><span class="sxs-lookup"><span data-stu-id="8d37e-109">More Information</span></span>|  
|------------|------------|----------------------|  
|[<span data-ttu-id="8d37e-110">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d37e-110">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)<br /><br /> [<span data-ttu-id="8d37e-111">Opções ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d37e-111">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)|<span data-ttu-id="8d37e-112">Alterado</span><span class="sxs-lookup"><span data-stu-id="8d37e-112">Changed</span></span>|[<span data-ttu-id="8d37e-113">Habilitar os pré-requisitos para o FileTable</span><span class="sxs-lookup"><span data-stu-id="8d37e-113">Enable the Prerequisites for FileTable</span></span>](enable-the-prerequisites-for-filetable.md)<br /><br /> [<span data-ttu-id="8d37e-114">Gerenciar FileTables</span><span class="sxs-lookup"><span data-stu-id="8d37e-114">Manage FileTables</span></span>](manage-filetables.md)|  
|[<span data-ttu-id="8d37e-115">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d37e-115">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)|<span data-ttu-id="8d37e-116">Alterado</span><span class="sxs-lookup"><span data-stu-id="8d37e-116">Changed</span></span>|[<span data-ttu-id="8d37e-117">Criar, alterar e remover FileTables</span><span class="sxs-lookup"><span data-stu-id="8d37e-117">Create, Alter, and Drop FileTables</span></span>](create-alter-and-drop-filetables.md)<br /><br /> [<span data-ttu-id="8d37e-118">Gerenciar FileTables</span><span class="sxs-lookup"><span data-stu-id="8d37e-118">Manage FileTables</span></span>](manage-filetables.md)|  
|[<span data-ttu-id="8d37e-119">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d37e-119">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)|<span data-ttu-id="8d37e-120">Alterado</span><span class="sxs-lookup"><span data-stu-id="8d37e-120">Changed</span></span>|[<span data-ttu-id="8d37e-121">Habilitar os pré-requisitos para o FileTable</span><span class="sxs-lookup"><span data-stu-id="8d37e-121">Enable the Prerequisites for FileTable</span></span>](enable-the-prerequisites-for-filetable.md)|  
|[<span data-ttu-id="8d37e-122">CREATE TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d37e-122">CREATE TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql)|<span data-ttu-id="8d37e-123">Alterado</span><span class="sxs-lookup"><span data-stu-id="8d37e-123">Changed</span></span>|[<span data-ttu-id="8d37e-124">Criar, alterar e remover FileTables</span><span class="sxs-lookup"><span data-stu-id="8d37e-124">Create, Alter, and Drop FileTables</span></span>](create-alter-and-drop-filetables.md)|  
|[<span data-ttu-id="8d37e-125">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d37e-125">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)<br /><br /> [<span data-ttu-id="8d37e-126">Argumentos de RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d37e-126">RESTORE Arguments &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-arguments-transact-sql)|<span data-ttu-id="8d37e-127">Alterado</span><span class="sxs-lookup"><span data-stu-id="8d37e-127">Changed</span></span>||  
  
##  <a name="functions"></a><a name="func"></a> <span data-ttu-id="8d37e-128">Funções</span><span class="sxs-lookup"><span data-stu-id="8d37e-128">Functions</span></span>  
  
|<span data-ttu-id="8d37e-129">Objeto</span><span class="sxs-lookup"><span data-stu-id="8d37e-129">Object</span></span>|<span data-ttu-id="8d37e-130">Status</span><span class="sxs-lookup"><span data-stu-id="8d37e-130">Status</span></span>|<span data-ttu-id="8d37e-131">Mais informações</span><span class="sxs-lookup"><span data-stu-id="8d37e-131">More Information</span></span>|  
|------------|------------|----------------------|  
|[<span data-ttu-id="8d37e-132">FileTableRootPath &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d37e-132">FileTableRootPath &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/filetablerootpath-transact-sql)|<span data-ttu-id="8d37e-133">**Adicionado**</span><span class="sxs-lookup"><span data-stu-id="8d37e-133">**Added**</span></span>|[<span data-ttu-id="8d37e-134">Trabalhar com diretórios e caminhos em FileTables</span><span class="sxs-lookup"><span data-stu-id="8d37e-134">Work with Directories and Paths in FileTables</span></span>](work-with-directories-and-paths-in-filetables.md)|  
|[<span data-ttu-id="8d37e-135">GetFileNamespacePath &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d37e-135">GetFileNamespacePath &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/getfilenamespacepath-transact-sql)|<span data-ttu-id="8d37e-136">**Adicionado**</span><span class="sxs-lookup"><span data-stu-id="8d37e-136">**Added**</span></span>|[<span data-ttu-id="8d37e-137">Trabalhar com diretórios e caminhos em FileTables</span><span class="sxs-lookup"><span data-stu-id="8d37e-137">Work with Directories and Paths in FileTables</span></span>](work-with-directories-and-paths-in-filetables.md)|  
|[<span data-ttu-id="8d37e-138">GetPathLocator &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d37e-138">GetPathLocator &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/getpathlocator-transact-sql)|<span data-ttu-id="8d37e-139">**Adicionado**</span><span class="sxs-lookup"><span data-stu-id="8d37e-139">**Added**</span></span>|[<span data-ttu-id="8d37e-140">Trabalhar com diretórios e caminhos em FileTables</span><span class="sxs-lookup"><span data-stu-id="8d37e-140">Work with Directories and Paths in FileTables</span></span>](work-with-directories-and-paths-in-filetables.md)|  
  
##  <a name="stored-procedures"></a><a name="sproc"></a> <span data-ttu-id="8d37e-141">Procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="8d37e-141">Stored Procedures</span></span>  
  
|<span data-ttu-id="8d37e-142">Objeto</span><span class="sxs-lookup"><span data-stu-id="8d37e-142">Object</span></span>|<span data-ttu-id="8d37e-143">Status</span><span class="sxs-lookup"><span data-stu-id="8d37e-143">Status</span></span>|<span data-ttu-id="8d37e-144">Mais informações</span><span class="sxs-lookup"><span data-stu-id="8d37e-144">More Information</span></span>|  
|------------|------------|----------------------|  
|[<span data-ttu-id="8d37e-145">sp_kill_filestream_non_transacted_handles &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d37e-145">sp_kill_filestream_non_transacted_handles &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-kill-filestream-non-transacted-handles)|<span data-ttu-id="8d37e-146">**Adicionado**</span><span class="sxs-lookup"><span data-stu-id="8d37e-146">**Added**</span></span>|[<span data-ttu-id="8d37e-147">Gerenciar FileTables</span><span class="sxs-lookup"><span data-stu-id="8d37e-147">Manage FileTables</span></span>](manage-filetables.md)|  
  
##  <a name="catalog-views"></a><a name="cv"></a> <span data-ttu-id="8d37e-148">Exibições do catálogo</span><span class="sxs-lookup"><span data-stu-id="8d37e-148">Catalog Views</span></span>  
  
|<span data-ttu-id="8d37e-149">Objeto</span><span class="sxs-lookup"><span data-stu-id="8d37e-149">Object</span></span>|<span data-ttu-id="8d37e-150">Status</span><span class="sxs-lookup"><span data-stu-id="8d37e-150">Status</span></span>|<span data-ttu-id="8d37e-151">Mais informações</span><span class="sxs-lookup"><span data-stu-id="8d37e-151">More Information</span></span>|  
|------------|------------|----------------------|  
|[<span data-ttu-id="8d37e-152">sys.database_filestream_options &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d37e-152">sys.database_filestream_options &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql)|<span data-ttu-id="8d37e-153">**Adicionado**</span><span class="sxs-lookup"><span data-stu-id="8d37e-153">**Added**</span></span>|[<span data-ttu-id="8d37e-154">Habilitar os pré-requisitos para o FileTable</span><span class="sxs-lookup"><span data-stu-id="8d37e-154">Enable the Prerequisites for FileTable</span></span>](enable-the-prerequisites-for-filetable.md)|  
|[<span data-ttu-id="8d37e-155">sys.filetable_system_defined_objects &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d37e-155">sys.filetable_system_defined_objects &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql)|<span data-ttu-id="8d37e-156">**Adicionado**</span><span class="sxs-lookup"><span data-stu-id="8d37e-156">**Added**</span></span>|[<span data-ttu-id="8d37e-157">Criar, alterar e remover FileTables</span><span class="sxs-lookup"><span data-stu-id="8d37e-157">Create, Alter, and Drop FileTables</span></span>](create-alter-and-drop-filetables.md)<br /><br /> [<span data-ttu-id="8d37e-158">Gerenciar FileTables</span><span class="sxs-lookup"><span data-stu-id="8d37e-158">Manage FileTables</span></span>](manage-filetables.md)|  
|[<span data-ttu-id="8d37e-159">sys.filetables &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d37e-159">sys.filetables &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-filetables-transact-sql)|<span data-ttu-id="8d37e-160">**Adicionado**</span><span class="sxs-lookup"><span data-stu-id="8d37e-160">**Added**</span></span>|[<span data-ttu-id="8d37e-161">Gerenciar FileTables</span><span class="sxs-lookup"><span data-stu-id="8d37e-161">Manage FileTables</span></span>](manage-filetables.md)|  
|[<span data-ttu-id="8d37e-162">sys.tables &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d37e-162">sys.tables &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql)|<span data-ttu-id="8d37e-163">Alterado</span><span class="sxs-lookup"><span data-stu-id="8d37e-163">Changed</span></span>|[<span data-ttu-id="8d37e-164">Gerenciar FileTables</span><span class="sxs-lookup"><span data-stu-id="8d37e-164">Manage FileTables</span></span>](manage-filetables.md)|  
  
##  <a name="dynamic-management-views"></a><a name="dmv"></a> <span data-ttu-id="8d37e-165">Exibições de gerenciamento dinâmico</span><span class="sxs-lookup"><span data-stu-id="8d37e-165">Dynamic Management Views</span></span>  
  
|<span data-ttu-id="8d37e-166">Objeto</span><span class="sxs-lookup"><span data-stu-id="8d37e-166">Object</span></span>|<span data-ttu-id="8d37e-167">Status</span><span class="sxs-lookup"><span data-stu-id="8d37e-167">Status</span></span>|<span data-ttu-id="8d37e-168">Mais informações</span><span class="sxs-lookup"><span data-stu-id="8d37e-168">More Information</span></span>|  
|------------|------------|----------------------|  
|[<span data-ttu-id="8d37e-169">sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d37e-169">sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql)|<span data-ttu-id="8d37e-170">**Adicionado**</span><span class="sxs-lookup"><span data-stu-id="8d37e-170">**Added**</span></span>|[<span data-ttu-id="8d37e-171">Gerenciar FileTables</span><span class="sxs-lookup"><span data-stu-id="8d37e-171">Manage FileTables</span></span>](manage-filetables.md)|  
  
## <a name="see-also"></a><span data-ttu-id="8d37e-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8d37e-172">See Also</span></span>  
 [<span data-ttu-id="8d37e-173">Gerenciar FileTables</span><span class="sxs-lookup"><span data-stu-id="8d37e-173">Manage FileTables</span></span>](manage-filetables.md)  
  
  