---
title: Assistente de importação e exportação do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- exporting data
- mapping files [Integration Services]
- SQL Server Import and Export Wizard
- SSIS packages, creating
- packages [Integration Services], copying
- Integration Services packages, creating
- packages [Integration Services], creating
- SQL Server Integration Services packages, creating
- Import and Export Wizard
- copying data [Integration Services]
- importing data, SSIS packages
- sources [Integration Services], copying data
ms.assetid: c0e4d867-b2a9-4b2a-844b-2fe45be88f81
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1c175bd005a9f3b9d55467abbbb278e13dafc521
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575934"
---
# <a name="sql-server-import-and-export-wizard"></a><span data-ttu-id="12e58-102">Assistente de Importação e Exportação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="12e58-102">SQL Server Import and Export Wizard</span></span>
  <span data-ttu-id="12e58-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Assistente de importação e exportação do oferece o método mais simples para criar um [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] pacote que copia dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="12e58-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard offers the simplest method to create a [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that copies data from a source to a destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12e58-104">Em um computador de 64 bits, o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] instala a versão de 64 bits do Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (DTSWizard.exe).</span><span class="sxs-lookup"><span data-stu-id="12e58-104">On a 64-bit computer, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installs the 64-bit version of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard (DTSWizard.exe).</span></span> <span data-ttu-id="12e58-105">No entanto, algumas fontes de dados, como Access ou Excel, só têm um provedor de 32 bits disponível.</span><span class="sxs-lookup"><span data-stu-id="12e58-105">However, some data sources, such as Access or Excel, only have a 32-bit provider available.</span></span> <span data-ttu-id="12e58-106">Para funcionar com essas fontes de dados, talvez seja necessário instalar e executar a versão de 32 bits do assistente.</span><span class="sxs-lookup"><span data-stu-id="12e58-106">To work with these data sources, you might have to install and run the 32-bit version of the wizard.</span></span> <span data-ttu-id="12e58-107">Para instalar a versão de 32 bits do assistente, selecione Ferramentas de Cliente ou [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="12e58-107">To install the 32-bit version of the wizard, select either Client Tools or [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] during setup.</span></span>  
  
 <span data-ttu-id="12e58-108">Você pode iniciar o Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no menu Iniciar, do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] ou no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="12e58-108">You can start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard from the Start menu, from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], from [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], or at the command prompt.</span></span> <span data-ttu-id="12e58-109">Para obter mais informações, consulte [executar o assistente de importação e exportação SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="12e58-109">For more information, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="12e58-110">O Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode copiar dados de e em qualquer fonte de dados para a qual um provedor de dados [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] gerenciado ou um provedor OLE DB nativo está disponível.</span><span class="sxs-lookup"><span data-stu-id="12e58-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard can copy data to and from any data source for which a managed [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider or a native OLE DB provider is available.</span></span> <span data-ttu-id="12e58-111">A lista de provedores disponíveis inclui as seguintes fontes de dados:</span><span class="sxs-lookup"><span data-stu-id="12e58-111">The list of available providers includes the following data sources:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]  
  
-   <span data-ttu-id="12e58-112">Arquivos simples</span><span class="sxs-lookup"><span data-stu-id="12e58-112">Flat files</span></span>  
  
-   <span data-ttu-id="12e58-113">Microsoft Office Access</span><span class="sxs-lookup"><span data-stu-id="12e58-113">Microsoft Office Access</span></span>  
  
-   <span data-ttu-id="12e58-114">Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="12e58-114">Microsoft Office Excel</span></span>  
  
 <span data-ttu-id="12e58-115">Alguns recursos de assistente funcionam de forma diferente, dependendo do ambiente em que o assistente é iniciado:</span><span class="sxs-lookup"><span data-stu-id="12e58-115">Some wizard features work differently, depending on the environment in which you start the wizard:</span></span>  
  
-   <span data-ttu-id="12e58-116">Se você iniciar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Assistente de importação e exportação no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , execute o pacote imediatamente marcando a caixa de seleção **executar imediatamente** .</span><span class="sxs-lookup"><span data-stu-id="12e58-116">If you start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you run the package immediately by selecting the **Execute immediately** check box.</span></span> <span data-ttu-id="12e58-117">Por padrão, essa caixa de seleção é marcada e o pacote é executado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="12e58-117">By default, this check box is selected and the package runs immediately.</span></span>  
  
     <span data-ttu-id="12e58-118">Você também pode decidir se deseja salvar o pacote no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="12e58-118">You can also decide whether to save the package to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to the file system.</span></span> <span data-ttu-id="12e58-119">Se você optar por salvar o pacote, também deverá especificar um nível de proteção de pacote.</span><span class="sxs-lookup"><span data-stu-id="12e58-119">If you select to save the package, you must also specify a package protection level.</span></span> <span data-ttu-id="12e58-120">Para obter mais informações sobre os níveis de proteção do pacote, consulte [controle de acesso para dados confidenciais em pacotes](../security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="12e58-120">For more information about package protection levels, see [Access Control for Sensitive Data in Packages](../security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
     <span data-ttu-id="12e58-121">Depois que o Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tiver criado o pacote e copiado os dados, você pode usar o [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer para abrir e alterar o pacote salvo com a adição de tarefas, transformações e lógica controlada por evento.</span><span class="sxs-lookup"><span data-stu-id="12e58-121">After the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard has created the package and copied the data, you can use the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer to open and change the saved package by adding tasks, transformations, and event-driven logic.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="12e58-122">No [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] , a opção para salvar o pacote criado pelo assistente não está disponível.</span><span class="sxs-lookup"><span data-stu-id="12e58-122">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
-   <span data-ttu-id="12e58-123">Se você iniciar o Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a partir de um projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], o pacote não poderá ser executado como uma etapa na conclusão do assistente.</span><span class="sxs-lookup"><span data-stu-id="12e58-123">If you start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard from an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], the package cannot be run as a step in completing the wizard.</span></span> <span data-ttu-id="12e58-124">Em vez disso, o pacote será adicionado ao projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] a partir do qual você iniciou o assistente.</span><span class="sxs-lookup"><span data-stu-id="12e58-124">Instead, the package is added to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project from which you started the wizard.</span></span> <span data-ttu-id="12e58-125">Você pode então executar o pacote ou estendê-lo adicionando tarefas, transformações e lógica controlada por evento usando o Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12e58-125">You can then run the package or extend it by adding tasks, transformations, and event-driven logic by using [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="12e58-126">Para obter mais informações, consulte [executar o assistente de importação e exportação SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="12e58-126">For more information, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
## <a name="permissions-required-by-the-import-and-export-wizard"></a><span data-ttu-id="12e58-127">Permissões exigidas pelo Assistente de Importação e Exportação</span><span class="sxs-lookup"><span data-stu-id="12e58-127">Permissions Required by the Import and Export Wizard</span></span>  
 <span data-ttu-id="12e58-128">Para concluir o Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com sucesso, você deve ter pelo menos as seguintes permissões:</span><span class="sxs-lookup"><span data-stu-id="12e58-128">To complete the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard successfully, you must have at least the following permissions:</span></span>  
  
-   <span data-ttu-id="12e58-129">Permissões para se conectar aos bancos de dados de origem e destino ou compartilhamentos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="12e58-129">Permissions to connect to the source and destination databases or file shares.</span></span> <span data-ttu-id="12e58-130">No [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], isso requer direitos de logon de servidor e banco de dados.</span><span class="sxs-lookup"><span data-stu-id="12e58-130">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], this requires server and database login rights.</span></span>  
  
-   <span data-ttu-id="12e58-131">Permissão para ler dados do banco de dados de origem ou arquivo.</span><span class="sxs-lookup"><span data-stu-id="12e58-131">Permission to read data from the source database or file.</span></span> <span data-ttu-id="12e58-132">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], isso requer permissões SELECT nas tabelas de origem e exibições.</span><span class="sxs-lookup"><span data-stu-id="12e58-132">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this requires SELECT permissions on the source tables and views.</span></span>  
  
-   <span data-ttu-id="12e58-133">Permissões de gravação de dados no banco de dados ou arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="12e58-133">Permissions to write data to the destination database or file.</span></span> <span data-ttu-id="12e58-134">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], isto requer permissões INSERT nas tabelas de destino.</span><span class="sxs-lookup"><span data-stu-id="12e58-134">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this requires INSERT permissions on the destination tables.</span></span>  
  
-   <span data-ttu-id="12e58-135">Se você desejar criar um novo banco de dados, tabela ou arquivo de destino, é necessário ter as permissões suficientes para criar o banco de dados, a tabela ou o arquivo.</span><span class="sxs-lookup"><span data-stu-id="12e58-135">If you want to create a new destination database or table or file, permissions sufficient to create the new database or table or file.</span></span> <span data-ttu-id="12e58-136">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], isso requer permissões CREATE DATABASE ou CREATE TABLE.</span><span class="sxs-lookup"><span data-stu-id="12e58-136">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this requires CREATE DATABASE or CREATE TABLE permissions.</span></span>  
  
-   <span data-ttu-id="12e58-137">Se você desejar salvar o pacote criado pelo assistente, é necessário ter as permissões suficientes de gravação no banco de dados msdb ou no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="12e58-137">If you want to save the package created by the wizard, permissions sufficient to write to the msdb database or to the file system.</span></span> <span data-ttu-id="12e58-138">No [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , isso requer permissões de inserção no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="12e58-138">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], this requires INSERT permissions on the msdb database.</span></span>  
  
## <a name="mapping-data-types-in-the-import-and-export-wizard"></a><span data-ttu-id="12e58-139">Mapeando tipos de dados no Assistente de Importação e Exportação</span><span class="sxs-lookup"><span data-stu-id="12e58-139">Mapping Data Types in the Import and Export Wizard</span></span>  
 <span data-ttu-id="12e58-140">O Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece poucos recursos de transformação.</span><span class="sxs-lookup"><span data-stu-id="12e58-140">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard provides minimal transformation capabilities.</span></span> <span data-ttu-id="12e58-141">Com exceção da configuração do nome, do tipo de dados e das propriedades de tipo de dados das colunas em novas tabelas e arquivos de destino, o Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não dá suporte a nenhuma transformação de nível de coluna.</span><span class="sxs-lookup"><span data-stu-id="12e58-141">Except for setting the name, the data type, and the data type properties of columns in new destination tables and files, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard supports no column-level transformations.</span></span>  
  
 <span data-ttu-id="12e58-142">O Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa os arquivos de mapeamento fornecidos pelo [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para mapear tipos de dados de uma versão de banco de dados ou sistema para outra.</span><span class="sxs-lookup"><span data-stu-id="12e58-142">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard uses the mapping files that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides to map data types from one database version or system to another.</span></span> <span data-ttu-id="12e58-143">Por exemplo, é possível mapear do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o Oracle.</span><span class="sxs-lookup"><span data-stu-id="12e58-143">For example, it can map from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to Oracle.</span></span> <span data-ttu-id="12e58-144">Por padrão, os arquivos de mapeamento no formato XML serão instalados em C:\Arquivos de Programas\Microsoft SQL Server\100\DTS\MappingFiles.</span><span class="sxs-lookup"><span data-stu-id="12e58-144">By default, the mapping files in XML format are installed to C:\Program Files\Microsoft SQL Server\100\DTS\MappingFiles.</span></span> <span data-ttu-id="12e58-145">Se sua empresa exigir diferentes mapeamentos entre tipos de dados, você poderá atualizá-los para afetar os mapeamentos executados pelo assistente.</span><span class="sxs-lookup"><span data-stu-id="12e58-145">If your business requires different mappings between data types, you can update the mappings to affect the mappings that the wizard performs.</span></span> <span data-ttu-id="12e58-146">Por exemplo, se você quiser que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo de dados **nchar** seja mapeado para o tipo de dados **gráfico** DB2 em vez do tipo de dados DB2 **VARGRAPHIC** ao transferir dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o DB2, altere o mapeamento **nchar** no arquivo de mapeamento SqlClientToIBMDB2.xml para usar o **elemento gráfico** em vez de **VARGRAPHIC.**</span><span class="sxs-lookup"><span data-stu-id="12e58-146">For example, if you want the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **nchar** data type to map to the DB2 **GRAPHIC** data type instead of the DB2 **VARGRAPHIC** data type when transferring data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to DB2, you change the **nchar** mapping in the SqlClientToIBMDB2.xml mapping file to use **GRAPHIC** instead of **VARGRAPHIC.**</span></span>  
  
 <span data-ttu-id="12e58-147">O [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inclui mapeamentos entre várias combinações de origem e destino usadas geralmente e é possível adicionar novos arquivos de mapeamento ao diretório Mapping Files para oferecer suporte a outras fontes e destinos.</span><span class="sxs-lookup"><span data-stu-id="12e58-147">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes mappings between many commonly used source and destination combinations, and you can add new mapping files to the Mapping Files directory to support additional sources and destinations.</span></span> <span data-ttu-id="12e58-148">Os novos arquivos de mapeamento devem estar em conformidade com o esquema XSD publicado e devem mapear uma combinação exclusiva de origem e destino.</span><span class="sxs-lookup"><span data-stu-id="12e58-148">The new mapping files must conform to the published XSD schema and map between a unique combination of source and destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12e58-149">Se você editar um arquivo de mapeamento existente ou adicionar um novo arquivo de mapeamento à pasta, feche e reabra o Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] para que os arquivos novos ou alterados sejam reconhecidos.</span><span class="sxs-lookup"><span data-stu-id="12e58-149">If you edit an existing mapping file, or add a new mapping file to the folder, you must close and reopen the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard or [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] for the new or changed files to be recognized.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="12e58-150">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="12e58-150">External Resources</span></span>  
  
-   <span data-ttu-id="12e58-151">Vídeo, [exportando dados SQL Server para o Excel (SQL Server vídeo)](https://go.microsoft.com/fwlink/?LinkID=200975), em technet.Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="12e58-151">Video, [Exporting SQL Server Data to Excel (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkID=200975), on technet.microsoft.com</span></span>  
  
-   <span data-ttu-id="12e58-152">Exemplo de CodePlex, [exportando do ODBC para um arquivo simples usando um tutorial do assistente: pacotes de lição](https://go.microsoft.com/fwlink/?LinkId=217657), em msftisprodsamples.codeplex.com</span><span class="sxs-lookup"><span data-stu-id="12e58-152">CodePlex sample, [Exporting from ODBC to a Flat File Using a Wizard Tutorial: Lesson Packages](https://go.microsoft.com/fwlink/?LinkId=217657), on msftisprodsamples.codeplex.com</span></span>  
  
  