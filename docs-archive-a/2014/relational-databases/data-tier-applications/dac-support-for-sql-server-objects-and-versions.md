---
title: Suporte de DAC para objetos e versões do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- data-tier application [SQL Server], supported objects
- objects [SQL Server], data-tier applications
ms.assetid: b1b78ded-16c0-4d69-8657-ec57925e68fd
author: stevestein
ms.author: sstein
ms.openlocfilehash: fa1ea498f603992ce2a62b51d95e74e0f9a9c584
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581935"
---
# <a name="dac-support-for-sql-server-objects-and-versions"></a><span data-ttu-id="f5894-102">Suporte de DAC para objetos e versões do SQL Server</span><span class="sxs-lookup"><span data-stu-id="f5894-102">DAC Support For SQL Server Objects and Versions</span></span>
  <span data-ttu-id="f5894-103">Um aplicativo da camada de dados (DAC) dá suporte aos objetos do [!INCLUDE[ssDE](../../includes/ssde-md.md)] mais usados.</span><span class="sxs-lookup"><span data-stu-id="f5894-103">A data-tier application (DAC) supports the most commonly used [!INCLUDE[ssDE](../../includes/ssde-md.md)] objects.</span></span>  
  
 <span data-ttu-id="f5894-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="f5894-104">**In This Topic**</span></span>  
  
-   [<span data-ttu-id="f5894-105">Objetos SQL Server com suporte</span><span class="sxs-lookup"><span data-stu-id="f5894-105">Supported SQL Server Objects</span></span>](#SupportedObjects)  
  
-   [<span data-ttu-id="f5894-106">Suporte a aplicativo da camada de dados das versões do SQL Server</span><span class="sxs-lookup"><span data-stu-id="f5894-106">Data-tier Application Support by the Versions of SQL Server</span></span>](#SupportByVersion)  
  
-   [<span data-ttu-id="f5894-107">Limitações de implantação de dados</span><span class="sxs-lookup"><span data-stu-id="f5894-107">Data Deployment Limitations</span></span>](#DeploymentLimitations)  
  
-   [<span data-ttu-id="f5894-108">Considerações adicionais para ações de implantação</span><span class="sxs-lookup"><span data-stu-id="f5894-108">Additional Considerations for Deployment Actions</span></span>](#Considerations)  
  
##  <a name="supported-sql-server-objects"></a><a name="SupportedObjects"></a><span data-ttu-id="f5894-109">Objetos SQL Server com suporte</span><span class="sxs-lookup"><span data-stu-id="f5894-109">Supported SQL Server Objects</span></span>  
 <span data-ttu-id="f5894-110">Somente objetos com suporte podem ser especificados em um aplicativo da camada de dados enquanto ele é criado ou editado.</span><span class="sxs-lookup"><span data-stu-id="f5894-110">Only supported objects can be specified in a data-tier application as it is being authored or edited.</span></span> <span data-ttu-id="f5894-111">Você não pode extrair, registrar ou importar um DAC de um banco de dados existente que contenha objetos sem suporte em um DAC.</span><span class="sxs-lookup"><span data-stu-id="f5894-111">You cannot extract, register, or import a DAC from an existing database that contains objects that are not supported in a DAC.</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="f5894-112">oferece suporte aos objetos a seguir em um DAC.</span><span class="sxs-lookup"><span data-stu-id="f5894-112">supports the following objects in a DAC.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5894-113">DATABASE ROLE</span><span class="sxs-lookup"><span data-stu-id="f5894-113">DATABASE ROLE</span></span>|<span data-ttu-id="f5894-114">FUNCTION: com valor de tabela embutido</span><span class="sxs-lookup"><span data-stu-id="f5894-114">FUNCTION: Inline Table-valued</span></span>|  
|<span data-ttu-id="f5894-115">FUNCTION: com valor de tabela de várias instruções</span><span class="sxs-lookup"><span data-stu-id="f5894-115">FUNCTION: Multistatement Table-valued</span></span>|<span data-ttu-id="f5894-116">FUNCTION: escalar</span><span class="sxs-lookup"><span data-stu-id="f5894-116">FUNCTION: Scalar</span></span>|  
|<span data-ttu-id="f5894-117">INDEX: clusterizado</span><span class="sxs-lookup"><span data-stu-id="f5894-117">INDEX: Clustered</span></span>|<span data-ttu-id="f5894-118">ÍNDICE: não clusterizado</span><span class="sxs-lookup"><span data-stu-id="f5894-118">INDEX: Nonclustered</span></span>|  
|<span data-ttu-id="f5894-119">INDEX: espacial</span><span class="sxs-lookup"><span data-stu-id="f5894-119">INDEX: Spacial</span></span>|<span data-ttu-id="f5894-120">INDEX: exclusivo</span><span class="sxs-lookup"><span data-stu-id="f5894-120">INDEX: Unique</span></span>|  
|<span data-ttu-id="f5894-121">LOGIN</span><span class="sxs-lookup"><span data-stu-id="f5894-121">LOGIN</span></span>|<span data-ttu-id="f5894-122">Permissões</span><span class="sxs-lookup"><span data-stu-id="f5894-122">Permissions</span></span>|  
|<span data-ttu-id="f5894-123">Associações de função</span><span class="sxs-lookup"><span data-stu-id="f5894-123">Role Memberships</span></span>|<span data-ttu-id="f5894-124">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f5894-124">SCHEMA</span></span>|  
|<span data-ttu-id="f5894-125">Estatísticas</span><span class="sxs-lookup"><span data-stu-id="f5894-125">Statistics</span></span>|<span data-ttu-id="f5894-126">STORED PROCEDURE: Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f5894-126">STORED PROCEDURE: Transact-SQL</span></span>|  
|<span data-ttu-id="f5894-127">Sinônimos</span><span class="sxs-lookup"><span data-stu-id="f5894-127">Synonyms</span></span>|<span data-ttu-id="f5894-128">TABLE: restrição de verificação</span><span class="sxs-lookup"><span data-stu-id="f5894-128">TABLE: Check Constraint</span></span>|  
|<span data-ttu-id="f5894-129">TABLE: ordenação</span><span class="sxs-lookup"><span data-stu-id="f5894-129">TABLE: Collation</span></span>|<span data-ttu-id="f5894-130">TABLE: coluna, incluindo colunas computadas</span><span class="sxs-lookup"><span data-stu-id="f5894-130">TABLE: Column, including computed columns</span></span>|  
|<span data-ttu-id="f5894-131">TABLE: restrição, padrão</span><span class="sxs-lookup"><span data-stu-id="f5894-131">TABLE: Constraint, Default</span></span>|<span data-ttu-id="f5894-132">TABLE: restrição, chave estrangeira</span><span class="sxs-lookup"><span data-stu-id="f5894-132">TABLE: Constraint, Foreign Key</span></span>|  
|<span data-ttu-id="f5894-133">TABLE: restrição, índice</span><span class="sxs-lookup"><span data-stu-id="f5894-133">TABLE: Constraint, Index</span></span>|<span data-ttu-id="f5894-134">TABLE: restrição, chave primária</span><span class="sxs-lookup"><span data-stu-id="f5894-134">TABLE: Constraint, Primary Key</span></span>|  
|<span data-ttu-id="f5894-135">TABLE: restrição, exclusiva</span><span class="sxs-lookup"><span data-stu-id="f5894-135">TABLE: Constraint, Unique</span></span>|<span data-ttu-id="f5894-136">TRIGGER: DML</span><span class="sxs-lookup"><span data-stu-id="f5894-136">TRIGGER: DML</span></span>|  
|<span data-ttu-id="f5894-137">TYPE: HIERARCHYID, GEOMETRY, GEOGRAPHY</span><span class="sxs-lookup"><span data-stu-id="f5894-137">TYPE: HIERARCHYID, GEOMETRY, GEOGRAPHY</span></span>|<span data-ttu-id="f5894-138">TYPE: tipo de dados definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f5894-138">TYPE: User-defined Data Type</span></span>|  
|<span data-ttu-id="f5894-139">TYPE: tipo de tabela definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f5894-139">TYPE: User-defined Table Type</span></span>|<span data-ttu-id="f5894-140">USER</span><span class="sxs-lookup"><span data-stu-id="f5894-140">USER</span></span>|  
|<span data-ttu-id="f5894-141">VIEW</span><span class="sxs-lookup"><span data-stu-id="f5894-141">VIEW</span></span>||  
  
##  <a name="data-tier-application-support-by-the-versions-of-sql-server"></a><a name="SupportByVersion"></a><span data-ttu-id="f5894-142">Suporte a aplicativos da camada de dados pelas versões do SQL Server</span><span class="sxs-lookup"><span data-stu-id="f5894-142">Data-tier Application Support by the Versions of SQL Server</span></span>  
 <span data-ttu-id="f5894-143">As versões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] têm níveis diferentes de suporte para operações do DAC.</span><span class="sxs-lookup"><span data-stu-id="f5894-143">The versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] have different levels of support for DAC operations.</span></span> <span data-ttu-id="f5894-144">Todas as operações do DAC com suporte de uma versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] têm suporte de todas as edições dessa versão.</span><span class="sxs-lookup"><span data-stu-id="f5894-144">All of the DAC operations supported by a version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are supported by all editions of that version.</span></span>  
  
 <span data-ttu-id="f5894-145">As instâncias do [!INCLUDE[ssDE](../../includes/ssde-md.md)] oferecem suporte às seguintes operações DAC:</span><span class="sxs-lookup"><span data-stu-id="f5894-145">Instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] support the following DAC operations:</span></span>  
  
-   <span data-ttu-id="f5894-146">Exportar e extrair têm suporte em todas as versões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5894-146">Export and extract are supported on all supported versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="f5894-147">Todas as operações têm suporte no [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] e em todas as versões do [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]e do [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5894-147">All operations are supported on [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] and all versions of [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], and [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span>  
  
-   <span data-ttu-id="f5894-148">Todas as operações têm suporte no [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] Service Pack 2 (SP2) ou posterior e no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP4 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="f5894-148">All operations are supported on [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] Service Pack 2 (SP2) or later, and [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP4 or later.</span></span>  
  
 <span data-ttu-id="f5894-149">O DAC Framework inclui as ferramentas do lado do cliente por compilar e processar pacotes do DAC e arquivos de exportação.</span><span class="sxs-lookup"><span data-stu-id="f5894-149">The DAC Framework comprises the client-side tools for building and processing DAC packages and export files.</span></span> <span data-ttu-id="f5894-150">Os produtos a seguir incluem o DAC Framework</span><span class="sxs-lookup"><span data-stu-id="f5894-150">The following products include the DAC Framework</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] <span data-ttu-id="f5894-151">e o [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] incluem o DAC Framework 3.0, com suporte a todas as operações de DAC.</span><span class="sxs-lookup"><span data-stu-id="f5894-151">and [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] includes DAC Framework 3.0, which supports all DAC operations.</span></span>  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] <span data-ttu-id="f5894-152">SP1 e o Visual Studio 2010 SP1 incluíam o DAC Framework 1.1, que oferece suporte a todas as operações de DAC, exceto a exportação e a importação.</span><span class="sxs-lookup"><span data-stu-id="f5894-152">SP1 and Visual Studio 2010 SP1 included DAC Framework 1.1, which supports all DAC operations except export and import.</span></span>  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] <span data-ttu-id="f5894-153">o Visual Studio 2010 incluíam o DAC Framework 1.0, que é compatível com todas as operações de DAC, menos exportação, importação e atualização no local.</span><span class="sxs-lookup"><span data-stu-id="f5894-153">and Visual Studio 2010 included DAC Framework 1.0, which supports all DAC operations except export, import, and in-place upgrade.</span></span>  
  
-   <span data-ttu-id="f5894-154">As ferramentas de cliente de versões anteriores de SQL Server ou Visual Studio não oferecem suporte a operações de DAC.</span><span class="sxs-lookup"><span data-stu-id="f5894-154">The client tools from earlier versions of SQL Server or Visual Studio do not support DAC operations.</span></span>  
  
 <span data-ttu-id="f5894-155">Um pacote de DAC ou arquivo de exportação criados com uma versão do DAC Framework não podem ser processados por uma versão anterior do DAC Framework.</span><span class="sxs-lookup"><span data-stu-id="f5894-155">A DAC package or export file built with one version of the DAC Framework cannot be processed by an earlier version of the DAC Framework.</span></span> <span data-ttu-id="f5894-156">Por exemplo, um pacote do DAC extraído usando as ferramentas de cliente [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] que usa as ferramentas de cliente [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] não pode ser implantado.</span><span class="sxs-lookup"><span data-stu-id="f5894-156">For example, a DAC package extracted using the [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] client tools cannot be deployed using the [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] client tools.</span></span>  
  
 <span data-ttu-id="f5894-157">Um pacote de DAC ou arquivo de exportação criados com uma versão do DAC Framework podem ser processados por uma versão posterior do DAC Framework.</span><span class="sxs-lookup"><span data-stu-id="f5894-157">A DAC package or export file built with one version of the DAC Framework can be processed by any later version of the DAC Framework.</span></span> <span data-ttu-id="f5894-158">Por exemplo, um pacote de DAC extraído usando as ferramentas de cliente do [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] podem ser implantadas usando as ferramentas de cliente [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] SP1 ou superiores.</span><span class="sxs-lookup"><span data-stu-id="f5894-158">For example, a DAC package extracted using the [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] client tools can be deployed using either the [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] SP1 or higher client tools.</span></span>  
  
##  <a name="data-deployment-limitations"></a><a name="DeploymentLimitations"></a><span data-ttu-id="f5894-159">Limitações de implantação de dados</span><span class="sxs-lookup"><span data-stu-id="f5894-159">Data Deployment Limitations</span></span>  
 <span data-ttu-id="f5894-160">Observe estas limitações de fidelidade do mecanismo de implantação de dados da Estrutura DAC no SQL Server 2012 SP1.</span><span class="sxs-lookup"><span data-stu-id="f5894-160">Note these fidelity limitations in the DAC Framework data deployment engine in SQL Server 2012 SP1.</span></span> <span data-ttu-id="f5894-161">As limitações se aplicam às seguintes ações da Estrutura DAC: implantar ou publicar um arquivo .dacpac, e importar um arquivo .bacpac.</span><span class="sxs-lookup"><span data-stu-id="f5894-161">The limitations apply to the following DAC Framework actions: deploy or publish a .dacpac file, and import a .bacpac file.</span></span>  
  
1.  <span data-ttu-id="f5894-162">A perda de metadados em certas condições e tipos de base nas colunas sql_variant.</span><span class="sxs-lookup"><span data-stu-id="f5894-162">Loss of metadata for certain conditions and base types within sql_variant columns.</span></span> <span data-ttu-id="f5894-163">Nos casos afetados, você verá um aviso com a seguinte mensagem:  **Algumas propriedades em alguns tipos de dados usados dentro de uma coluna sql_variant não são preservadas quando a implantação é feita pela Estrutura DAC.**</span><span class="sxs-lookup"><span data-stu-id="f5894-163">In the affected cases, you will see a warning with the following message:  **Certain properties on certain data types used within a sql_variant column are not preserved when deployed by the DAC Framework.**</span></span>  
  
    -   <span data-ttu-id="f5894-164">Tipos de base MONEY, SMALLMONEY, NUMERIC, DECIMAL: a precisão não é preservada.</span><span class="sxs-lookup"><span data-stu-id="f5894-164">MONEY, SMALLMONEY, NUMERIC, DECIMAL base types:  Precision is not preserved.</span></span>  
  
        -   <span data-ttu-id="f5894-165">Tipos de base DECIMAL/NUMERIC com precisão 38: os metadados de sql_variant “TotalBytes” são sempre definidos como 21.</span><span class="sxs-lookup"><span data-stu-id="f5894-165">DECIMAL/NUMERIC base types with precision 38:  the "TotalBytes" sql_variant metadata is always set to 21.</span></span>  
  
    -   <span data-ttu-id="f5894-166">Todos os tipos de base de texto: a ordenação padrão do banco de dados é aplicada a todo o texto.</span><span class="sxs-lookup"><span data-stu-id="f5894-166">All text base types:  The database default collation is applied for all text.</span></span>  
  
    -   <span data-ttu-id="f5894-167">Tipos de base BINARY: a propriedade de comprimento máximo não é preservada.</span><span class="sxs-lookup"><span data-stu-id="f5894-167">BINARY base types:  Max length property is not preserved.</span></span>  
  
    -   <span data-ttu-id="f5894-168">Tipos de base TIME, DATETIMEOFFSET: a precisão é sempre definida como 7.</span><span class="sxs-lookup"><span data-stu-id="f5894-168">TIME, DATETIMEOFFSET base types:  Precision is always set to 7.</span></span>  
  
2.  <span data-ttu-id="f5894-169">Perda de dados nas colunas sql_variant.</span><span class="sxs-lookup"><span data-stu-id="f5894-169">Loss of data within sql_variant columns.</span></span> <span data-ttu-id="f5894-170">Nos casos afetados, você verá um aviso com a seguinte mensagem:  **Haverá perda de dados quando um valor em uma coluna sql_variant DATETIME2 com escala maior que 3 for implantado pela Estrutura DAC. O valor DATETIME2 está limitado a uma escala igual a 3 durante a implantação.**</span><span class="sxs-lookup"><span data-stu-id="f5894-170">In the affected case, you will see a warning with the following message:  **There will be data loss when a value in a sql_variant DATETIME2 column with scale greater than 3 is deployed by the DAC Framework. The DATETIME2 value is limited to a scale equal to 3 during deployment.**</span></span>  
  
    -   <span data-ttu-id="f5894-171">Tipo de base DATETIME2 com escala maior que 3: a escala é limitada ao valor igual a 3.</span><span class="sxs-lookup"><span data-stu-id="f5894-171">DATETIME2 base type with scale greater than 3:  scale is limited to equal 3.</span></span>  
  
3.  <span data-ttu-id="f5894-172">Ocorre falha na operação de implantação com as condições em colunas sql_variant a seguir.</span><span class="sxs-lookup"><span data-stu-id="f5894-172">Deployment operation fails for the following conditions within sql_variant columns.</span></span> <span data-ttu-id="f5894-173">Nos casos afetados, você verá uma caixa de diálogo com a seguinte mensagem:  **Falha na operação devido às limitações de dados na Estrutura DAC.**</span><span class="sxs-lookup"><span data-stu-id="f5894-173">In the affected cases, you will see a dialog with the following message:  **Operation failed due to data limitations in the DAC Framework.**</span></span>  
  
    -   <span data-ttu-id="f5894-174">Tipos de base DATETIME2, SMALLDATETIME e DATE: se o valor está fora do intervalo DATETIME – por exemplo, o ano é anterior a 1753.</span><span class="sxs-lookup"><span data-stu-id="f5894-174">DATETIME2, SMALLDATETIME and DATE base types:  If the value is outside of DATETIME range - for example, the year is less than 1753.</span></span>  
  
    -   <span data-ttu-id="f5894-175">Tipo de base DECIMAL, NUMERIC: quando a precisão do valor é maior que 28.</span><span class="sxs-lookup"><span data-stu-id="f5894-175">DECIMAL, NUMERIC base type:  when precision of the value is greater than 28.</span></span>  
  
##  <a name="additional-considerations-for-deployment-actions"></a><a name="Considerations"></a> <span data-ttu-id="f5894-176">Considerações adicionais para ações de implantação</span><span class="sxs-lookup"><span data-stu-id="f5894-176">Additional Considerations for Deployment Actions</span></span>  
 <span data-ttu-id="f5894-177">Observe as seguintes considerações para ações da implantação de dados da Estrutura DAC:</span><span class="sxs-lookup"><span data-stu-id="f5894-177">Note the following considerations for DAC Framework data deployment actions:</span></span>  
  
-   <span data-ttu-id="f5894-178">**Extrair/exportar** -em ações que usam a estrutura DAC para criar um pacote de um banco de dados, por exemplo, extrair um arquivo. dacpac, exportar um arquivo. bacpac-essas limitações não se aplicam.</span><span class="sxs-lookup"><span data-stu-id="f5894-178">**Extract/Export** - On actions that use the DAC Framework to create a package from a database - for example, extract a .dacpac file, export a .bacpac file - these limitations do not apply.</span></span> <span data-ttu-id="f5894-179">Os dados no pacote são uma representação de fidelidade total dos dados no banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="f5894-179">The data in the package is a full-fidelity representation of the data in the source database.</span></span> <span data-ttu-id="f5894-180">Se alguma dessas condições estiver presente no pacote, o log de extração/exportação conterá um resumo dos problemas através das mensagens observadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f5894-180">If any of these conditions are present in the package, the extract/export log will contain a summary of the issues via the messages noted above.</span></span> <span data-ttu-id="f5894-181">Esse é um aviso ao usuário sobre problemas potenciais de implantação de dados com o pacote criado.</span><span class="sxs-lookup"><span data-stu-id="f5894-181">This is to warn the user of potential data deployment issues with the package they created.</span></span> <span data-ttu-id="f5894-182">O usuário também verá a seguinte mensagem de resumo no log:  **Essas limitações não afetam a fidelidade dos tipos de dados e valores armazenados no pacote de DAC que tenha sido criado pela Estrutura DAC; elas se aplicam apenas aos tipos de dados e valores resultantes da implantação de um pacote de DAC em um banco de dados. Para obter mais informações sobre os dados afetados e como solucionar essa limitação, confira** [este tópico](https://go.microsoft.com/fwlink/?LinkId=267086).</span><span class="sxs-lookup"><span data-stu-id="f5894-182">The user will also see the following summary message in the log:  **These limitations do not affect the fidelity of the data types and values stored in the DAC package created by the DAC Framework; they only apply to the data types and values resulting from deploying a DAC package to a database. For more information about the data that is affected and how to work around this limitation, see** [this topic](https://go.microsoft.com/fwlink/?LinkId=267086).</span></span>  
  
-   <span data-ttu-id="f5894-183">**Implantar/Publicar/Importar** – Nas ações que usam a Estrutura DAC para implantar um pacote em um banco de dados, como implantar ou publicar um arquivo .dacpac, e importar um arquivo .bacpac, essas limitações se aplicam.</span><span class="sxs-lookup"><span data-stu-id="f5894-183">**Deploy/Publish/Import** - On actions that use the DAC Framework to deploy a package to a database, like to deploy or publish a .dacpac file, and import a .bacpac file, these limitations do apply.</span></span> <span data-ttu-id="f5894-184">Os dados que resultam no banco de dados de destino não podem conter uma representação de fidelidade total dos dados no pacote.</span><span class="sxs-lookup"><span data-stu-id="f5894-184">The data that results in the target database may not contain a full-fidelity representation of the data in the package.</span></span> <span data-ttu-id="f5894-185">O log Implantar/Importar conterá uma mensagem, observada acima, para cada instância em que o problema for encontrado.</span><span class="sxs-lookup"><span data-stu-id="f5894-185">The Deploy/Import log will contain a message, noted above, for every instance the issue is encountered.</span></span> <span data-ttu-id="f5894-186">A operação será bloqueada por erros (consulte a categoria 3 anterior), mas continuará com os outros avisos.</span><span class="sxs-lookup"><span data-stu-id="f5894-186">The operation will be blocked by errors - see category 3 above - but will proceed with the other warnings.</span></span>  
  
     <span data-ttu-id="f5894-187">Para obter mais informações sobre os dados que são afetados neste cenário e como solucionar essa limitação para ações de implantação/publicação/importação, confira [este tópico](https://go.microsoft.com/fwlink/?LinkId=267087).</span><span class="sxs-lookup"><span data-stu-id="f5894-187">For more information about the data that is affected in this scenario and how to work around this limitation for deploy/publish/import actions, see [this topic](https://go.microsoft.com/fwlink/?LinkId=267087).</span></span>  
  
-   <span data-ttu-id="f5894-188">**Soluções alternativas** – as operações de extração e exportação gravarão arquivos de dados BCP de fidelidade total em arquivos. dacpac ou. bacpac.</span><span class="sxs-lookup"><span data-stu-id="f5894-188">**Workarounds** - Extract and export operations will write full-fidelity BCP data files into the .dacpac or .bacpac files.</span></span> <span data-ttu-id="f5894-189">Para evitar limitações, use o utilitário de linha de comando BCP.exe do SQL Server para implantar dados de fidelidade total em um banco de dados de destino de um pacote de DAC.</span><span class="sxs-lookup"><span data-stu-id="f5894-189">To avoid limitations, use the SQL Server BCP.exe command line utility to deploy full-fidelity data to a target database from a DAC package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5894-190">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f5894-190">See Also</span></span>  
 [<span data-ttu-id="f5894-191">Aplicativos da camada de dados</span><span class="sxs-lookup"><span data-stu-id="f5894-191">Data-tier Applications</span></span>](data-tier-applications.md)  
  
  