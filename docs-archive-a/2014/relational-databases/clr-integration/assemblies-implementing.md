---
title: Implementando assemblies | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration], implementing
ms.assetid: c228d7bf-a906-4f37-a057-5d464d962ff8
author: rothja
ms.author: jroth
ms.openlocfilehash: 3cb3818ed644eede3cf4f2c256a0dcb94ec58c3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682291"
---
# <a name="implementing-assemblies"></a><span data-ttu-id="87947-102">Implementando assemblies</span><span class="sxs-lookup"><span data-stu-id="87947-102">Implementing Assemblies</span></span>
  <span data-ttu-id="87947-103">Este tópico fornece informações sobre as seguintes áreas para ajudá-lo a implementar e trabalhar com assemblies no banco de dados:</span><span class="sxs-lookup"><span data-stu-id="87947-103">This topic provides information about the following areas to help you implement and work with assemblies in the database:</span></span>  
  
-   <span data-ttu-id="87947-104">Criando assemblies</span><span class="sxs-lookup"><span data-stu-id="87947-104">Creating assemblies</span></span>  
  
-   <span data-ttu-id="87947-105">Modificando assemblies</span><span class="sxs-lookup"><span data-stu-id="87947-105">Modifying assemblies</span></span>  
  
-   <span data-ttu-id="87947-106">Descartando, desabilitando e habilitando assemblies</span><span class="sxs-lookup"><span data-stu-id="87947-106">Dropping, disabling, and enabling assemblies</span></span>  
  
-   <span data-ttu-id="87947-107">Gerenciando versões de assembly</span><span class="sxs-lookup"><span data-stu-id="87947-107">Managing assembly versions</span></span>  
  
## <a name="creating-assemblies"></a><span data-ttu-id="87947-108">Criando Assemblies</span><span class="sxs-lookup"><span data-stu-id="87947-108">Creating Assemblies</span></span>  
 <span data-ttu-id="87947-109">Os assemblies são criados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE ASSEMBLY ou no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] usando o Assembly Assisted Editor.</span><span class="sxs-lookup"><span data-stu-id="87947-109">Assemblies are created in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE ASSEMBLY statement, or in the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using the Assembly Assisted Editor.</span></span> <span data-ttu-id="87947-110">Além disso, a implantação de um projeto SQL Server no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] registra um assembly no banco de dados que foi especificado para o projeto.</span><span class="sxs-lookup"><span data-stu-id="87947-110">Additionally, deploying a SQL Server Project in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] registers an assembly in the database that was specified for the project.</span></span> <span data-ttu-id="87947-111">Para obter mais informações, consulte [Deploying CLR Database Objects](deploying-clr-database-objects.md).</span><span class="sxs-lookup"><span data-stu-id="87947-111">For more information, see [Deploying CLR Database Objects](deploying-clr-database-objects.md).</span></span>  
  
 <span data-ttu-id="87947-112">**Para criar um assembly usando o Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="87947-112">**To create an assembly by using Transact-SQL**</span></span>  
  
-   [<span data-ttu-id="87947-113">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="87947-113">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-assembly-transact-sql)  
  
 <span data-ttu-id="87947-114">**Para criar um assembly usando o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="87947-114">**To create an assembly by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="87947-115">Propriedades do assembly &#40;página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="87947-115">Assembly Properties &#40;General Page&#41;</span></span>](assemblies-properties.md)  
  
## <a name="modifying-assemblies"></a><span data-ttu-id="87947-116">Modificando assemblies</span><span class="sxs-lookup"><span data-stu-id="87947-116">Modifying Assemblies</span></span>  
 <span data-ttu-id="87947-117">Os assemblies são modificados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando a instrução ALTER ASSEMBLY [!INCLUDE[tsql](../../includes/tsql-md.md)] ou no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] usando o Assembly Assisted Editor.</span><span class="sxs-lookup"><span data-stu-id="87947-117">Assemblies are modified in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] ALTER ASSEMBLY statement or in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using the Assembly Assisted Editor.</span></span> <span data-ttu-id="87947-118">Você pode modificar um assembly quando quiser fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="87947-118">You can modify an assembly when you want to do the following:</span></span>  
  
-   <span data-ttu-id="87947-119">Altere a implementação do assembly carregando uma versão mais nova dos binários do assembly.</span><span class="sxs-lookup"><span data-stu-id="87947-119">Change the implementation of the assembly by uploading a newer version of the binaries of the assembly.</span></span> <span data-ttu-id="87947-120">Para obter mais informações, consulte [Gerenciando versões de assembly](#_managing) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="87947-120">For more information, see [Managing Assembly Versions](#_managing) later in this topic.</span></span>  
  
-   <span data-ttu-id="87947-121">Altere o conjunto de permissões do assembly.</span><span class="sxs-lookup"><span data-stu-id="87947-121">Change the permission set of the assembly.</span></span> <span data-ttu-id="87947-122">Para obter mais informações, confira [Criando assemblies](../../relational-databases/clr-integration/assemblies-designing.md).</span><span class="sxs-lookup"><span data-stu-id="87947-122">For more information, see [Designing Assemblies](../../relational-databases/clr-integration/assemblies-designing.md).</span></span>  
  
-   <span data-ttu-id="87947-123">Altere a visibilidade do assembly.</span><span class="sxs-lookup"><span data-stu-id="87947-123">Change the visibility of the assembly.</span></span> <span data-ttu-id="87947-124">Assemblies visíveis estão disponíveis para consulta no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87947-124">Visible assemblies are available for referencing in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="87947-125">Assemblies não visíveis não estão disponíveis, mesmo se tiverem sido carregados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="87947-125">Nonvisible assemblies are not available, even if they have been uploaded in the database.</span></span> <span data-ttu-id="87947-126">Por padrão, os assemblies carregados para uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são visíveis.</span><span class="sxs-lookup"><span data-stu-id="87947-126">By default, assemblies uploaded to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are visible.</span></span>  
  
-   <span data-ttu-id="87947-127">Adicione ou descarte um arquivo de depuração ou de origem associado ao assembly.</span><span class="sxs-lookup"><span data-stu-id="87947-127">Add or drop a debug or source file associated with the assembly.</span></span>  
  
 <span data-ttu-id="87947-128">**Para modificar um assembly usando o Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="87947-128">**To modify an assembly by using Transact-SQL**</span></span>  
  
-   [<span data-ttu-id="87947-129">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="87947-129">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-assembly-transact-sql)  
  
 <span data-ttu-id="87947-130">**Para modificar um assembly usando o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="87947-130">**To modify an assembly by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="87947-131">Propriedades do assembly &#40;página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="87947-131">Assembly Properties &#40;General Page&#41;</span></span>](assemblies-properties.md)  
  
## <a name="dropping-disabling-and-enabling-assemblies"></a><span data-ttu-id="87947-132">Descartando, desabilitando e habilitando assemblies</span><span class="sxs-lookup"><span data-stu-id="87947-132">Dropping, Disabling, and Enabling Assemblies</span></span>  
 <span data-ttu-id="87947-133">Os assemblies são descartados usando a instrução DROP ASSEMBLY [!INCLUDE[tsql](../../includes/tsql-md.md)] ou o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87947-133">Assemblies are dropped by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] DROP ASSEMBLY statement or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="87947-134">**Para descartar um assembly usando o Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="87947-134">**To drop an assembly by using Transact-SQL**</span></span>  
  
-   [<span data-ttu-id="87947-135">DROP ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="87947-135">DROP ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-assembly-transact-sql)  
  
 <span data-ttu-id="87947-136">**Para descartar um assembly usando o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="87947-136">**To drop an assembly by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="87947-137">Excluir Objetos</span><span class="sxs-lookup"><span data-stu-id="87947-137">Delete Objects</span></span>](../../ssms/object/delete-objects.md)  
  
 <span data-ttu-id="87947-138">Por padrão, todos os assemblies que são criados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estão desabilitados para execução.</span><span class="sxs-lookup"><span data-stu-id="87947-138">By default, all assemblies that are created in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are disabled from executing.</span></span> <span data-ttu-id="87947-139">Você pode usar a opção **CLR Enabled** do procedimento armazenado do sistema **sp_configure** para desabilitar ou habilitar a execução de todos os assemblies que são carregados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="87947-139">You can use the **clr enabled** option of the **sp_configure** system stored procedure to disable or enable the execution of all assemblies that are uploaded in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="87947-140">Desabilitar a execução de assemblies impede que funções CLR (Common Language Runtime), procedimentos armazenados, gatilhos, agregações e tipos definidos pelo usuário sejam executados e interrompe os que estão sendo executados no momento.</span><span class="sxs-lookup"><span data-stu-id="87947-140">Disabling assembly execution prevents common language runtime (CLR) functions, stored procedures, triggers, aggregates, and user-defined types from executing, and stops those that are currently executing.</span></span> <span data-ttu-id="87947-141">A desabilitação da execução do assembly não desabilita a capacidade de criar, alterar ou descartar assemblies.</span><span class="sxs-lookup"><span data-stu-id="87947-141">Disabling assembly execution does not disable the ability to create, alter, or drop assemblies.</span></span> <span data-ttu-id="87947-142">Para obter mais informações, consulte [opção de configuração de servidor CLR Enabled](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="87947-142">For more information, see [clr enabled Server Configuration Option](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="87947-143">**Para desabilitar e habilitar a execução de assemblies**</span><span class="sxs-lookup"><span data-stu-id="87947-143">**To disable and enable assembly execution**</span></span>  
  
-   [<span data-ttu-id="87947-144">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="87947-144">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
##  <a name="managing-assembly-versions"></a><a name="_managing"></a><span data-ttu-id="87947-145">Gerenciando versões de assembly</span><span class="sxs-lookup"><span data-stu-id="87947-145">Managing Assembly Versions</span></span>  
 <span data-ttu-id="87947-146">Quando um assembly é carregado em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o assembly é armazenado e gerenciado dentro dos catálogos do sistema de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="87947-146">When an assembly is uploaded to an instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the assembly is stored and managed within the database system catalogs.</span></span> <span data-ttu-id="87947-147">Todas as alterações feitas na definição do assembly no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] devem ser propagadas para o assembly armazenado no catálogo de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="87947-147">Any changes made to the definition of the assembly in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] should be propagated to the assembly that is stored in the database catalog.</span></span>  
  
 <span data-ttu-id="87947-148">Quando for preciso modificar um assembly, você deverá emitir uma instrução ALTER ASSEMBLY para atualizar o assembly no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="87947-148">When you have to modify an assembly, you must issue an ALTER ASSEMBLY statement to update the assembly in the database.</span></span> <span data-ttu-id="87947-149">Isso atualizará o assembly até a última cópia de módulos do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] que contenha sua implementação.</span><span class="sxs-lookup"><span data-stu-id="87947-149">This will update the assembly to the latest copy of [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] modules holding its implementation.</span></span>  
  
 <span data-ttu-id="87947-150">A cláusula WITH UNCHECKED DATA da instrução ALTER ASSEMBLY instrui o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para atualizar até mesmo os assemblies dos quais os dados persistentes no banco de dados sejam dependentes.</span><span class="sxs-lookup"><span data-stu-id="87947-150">The WITH UNCHECKED DATA clause of the ALTER ASSEMBLY statement instructs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to refresh even those assemblies upon which persisted data in the database is dependent.</span></span> <span data-ttu-id="87947-151">Especificamente, você deve especificar WITH UNCHECKED DATA se qualquer uma dessas opções existir:</span><span class="sxs-lookup"><span data-stu-id="87947-151">Specifically, you must specify WITH UNCHECKED DATA if any of the following exist:</span></span>  
  
-   <span data-ttu-id="87947-152">Colunas computadas persistentes que referenciem métodos no assembly, seja direta ou indiretamente, através de funções ou métodos [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87947-152">Persisted computed columns that reference methods in the assembly, either directly, or indirectly, through [!INCLUDE[tsql](../../includes/tsql-md.md)] functions or methods.</span></span>  
  
-   <span data-ttu-id="87947-153">As colunas de um tipo de dado CLR definido pelo usuário que dependem do assembly e o tipo implementa um formato de serialização **UserDefined** (não **nativo**).</span><span class="sxs-lookup"><span data-stu-id="87947-153">Columns of a CLR user-defined type that depend on the assembly, and the type implements a **UserDefined** (non-**Native**) serialization format.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="87947-154">Se WITH UNCHECKED DATA não for especificado, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tentará impedir que ALTER ASSEMBLY seja executada se a nova versão do assembly afetar dados existentes em tabelas, índices ou outros locais persistentes.</span><span class="sxs-lookup"><span data-stu-id="87947-154">If WITH UNCHECKED DATA is not specified, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tries to prevent ALTER ASSEMBLY from executing if the new assembly version affects existing data in tables, indexes, or other persistent sites.</span></span> <span data-ttu-id="87947-155">Porém, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não garante que colunas computadas, índices, exibições indexadas ou expressões sejam consistentes com as rotinas e tipos subjacentes quando o assembly CLR for atualizado.</span><span class="sxs-lookup"><span data-stu-id="87947-155">However, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not guarantee that computed columns, indexes, indexed views, or expressions will be consistent with the underlying routines and types when the CLR assembly is updated.</span></span> <span data-ttu-id="87947-156">Tenha cuidado ao executar ALTER ASSEMBLY, para ter certeza de que não haja nenhuma desigualdade entre o resultado de uma expressão e um valor que é baseado naquela expressão armazenado no assembly.</span><span class="sxs-lookup"><span data-stu-id="87947-156">Be careful when you execute ALTER ASSEMBLY to make sure that there is no mismatch between the result of an expression and a value that is based on that expression stored in the assembly.</span></span>  
  
 <span data-ttu-id="87947-157">Somente os membros do **db_owner** e **db_ddlowner** função de banco de dados fixa podem executar a execução de ALTER assembly usando a cláusula WITH desmarcated Data.</span><span class="sxs-lookup"><span data-stu-id="87947-157">Only members of the **db_owner** and **db_ddlowner** fixed database role can execute run ALTER ASSEMBLY by using the WITH UNCHECKED DATA clause.</span></span>  
  
 <span data-ttu-id="87947-158">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] publica uma mensagem no log de eventos de aplicativos do Windows informando que o assembly foi modificado com dados não verificados nas tabelas.</span><span class="sxs-lookup"><span data-stu-id="87947-158">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] posts a message to the Windows application event log that the assembly has been modified with unchecked data in the tables.</span></span> <span data-ttu-id="87947-159">Em seguida, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] marca qualquer tabela que contenha dados dependentes do assembly como tendo dados não verificados.</span><span class="sxs-lookup"><span data-stu-id="87947-159">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] then marks any tables that contain data dependent on the assembly as having unchecked data.</span></span> <span data-ttu-id="87947-160">A coluna **has_unchecked_assembly_data** da exibição de catálogo **Sys. Tables** contém o valor 1 para tabelas que contêm dados desmarcados e 0 para tabelas sem dados desmarcados.</span><span class="sxs-lookup"><span data-stu-id="87947-160">The **has_unchecked_assembly_data** column of the **sys.tables** catalog view contains the value 1 for tables that contain unchecked data, and 0 for tables without unchecked data.</span></span>  
  
 <span data-ttu-id="87947-161">Para resolver a integridade de dados não verificados, execute DBCC CHECKTABLE em cada tabela que tiver dados não verificados.</span><span class="sxs-lookup"><span data-stu-id="87947-161">To resolve the integrity of unchecked data, run DBCC CHECKTABLE against each table that has unchecked data.</span></span> <span data-ttu-id="87947-162">Se DBCC CHECKTABLE falhar, você terá de excluir as linhas da tabela que não sejam válidas ou modificar o código do assembly para tratar de problemas e, em seguida, emitir instruções ALTER ASSEMBLY adicionais.</span><span class="sxs-lookup"><span data-stu-id="87947-162">If DBCC CHECKTABLE fails, you must either delete the table rows that are not valid or modify the assembly code to address problems, and then issue additional ALTER ASSEMBLY statements.</span></span>  
  
 <span data-ttu-id="87947-163">ALTER ASSEMBLY altera a versão do assembly.</span><span class="sxs-lookup"><span data-stu-id="87947-163">ALTER ASSEMBLY changes the assembly version.</span></span> <span data-ttu-id="87947-164">A cultura e o token de chave pública do assembly permanecem os mesmos. SQL Server não permite registrar versões diferentes de um assembly com o mesmo nome, cultura e chave pública.</span><span class="sxs-lookup"><span data-stu-id="87947-164">The culture and public key token of the assembly remain the same.SQL Server does not allow registering different versions of an assembly with the same name, culture and public key.</span></span>  
  
### <a name="interactions-with-computer-wide-policy-for-version-binding"></a><span data-ttu-id="87947-165">Interações com a política de computadores para associação de versões</span><span class="sxs-lookup"><span data-stu-id="87947-165">Interactions with Computer-wide Policy for Version Binding</span></span>  
 <span data-ttu-id="87947-166">Se as referências a assemblies armazenadas no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] forem redirecionadas a versões específicas usando política de publicador ou política de administrador de computadores, você deve agir de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="87947-166">If references to assemblies stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are redirected to specific versions by using publisher policy or computer-wide administrator policy, you must do either of the following:</span></span>  
  
-   <span data-ttu-id="87947-167">Verificar se a nova versão para a qual esse redirecionamento é feito está no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="87947-167">Make sure the new version to which this redirection is made is in the database.</span></span>  
  
-   <span data-ttu-id="87947-168">Modificar qualquer instrução dos arquivos de política externa do computador ou de política de publicador para ter certeza de que fazem referência à versão específica que está no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="87947-168">Modify any statements to the external policy files of the computer or publisher policy to make sure that they reference the specific version that is in the database.</span></span>  
  
 <span data-ttu-id="87947-169">Caso contrário, uma tentativa para carregar uma nova versão de assembly à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] falhará.</span><span class="sxs-lookup"><span data-stu-id="87947-169">Otherwise, an attempt to load a new assembly version to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will fail.</span></span>  
  
 <span data-ttu-id="87947-170">**Para atualizar a versão de um assembly**</span><span class="sxs-lookup"><span data-stu-id="87947-170">**To update the version of an assembly**</span></span>  
  
-   [<span data-ttu-id="87947-171">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="87947-171">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-assembly-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="87947-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="87947-172">See Also</span></span>  
 <span data-ttu-id="87947-173">[Assemblies &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="87947-173">[Assemblies &#40;Database Engine&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span></span>  
 [<span data-ttu-id="87947-174">Obtendo informações sobre assemblies</span><span class="sxs-lookup"><span data-stu-id="87947-174">Getting Information About Assemblies</span></span>](../../relational-databases/clr-integration/assemblies-getting-information.md)  
  
  