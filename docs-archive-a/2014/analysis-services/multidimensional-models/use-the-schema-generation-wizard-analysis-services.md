---
title: Usar o assistente de geração de esquema (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Schema Generation Wizard, steps
- relational schema [Analysis Services], Schema Generation Wizard
ms.assetid: 8c710745-d41d-4c31-b6a2-2956229df75a
author: minewiskan
ms.author: owend
ms.openlocfilehash: fa65c2c6f377a375d0fc6aa8298cdec749805b6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575397"
---
# <a name="use-the-schema-generation-wizard-analysis-services"></a><span data-ttu-id="fa721-102">Use o assistente de geração de esquema (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="fa721-102">Use the Schema Generation Wizard (Analysis Services)</span></span>
  <span data-ttu-id="fa721-103">O Assistente de Geração de Esquema requer uma quantidade limitada de informações durante a fase de geração.</span><span class="sxs-lookup"><span data-stu-id="fa721-103">The Schema Generation Wizard requires a limited amount of information during the generation phase.</span></span> <span data-ttu-id="fa721-104">A maioria das informações que o Assistente de Geração de Esquema requer para gerar esquemas relacionais é extraída dos cubos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e dimensões que você já criou no projeto.</span><span class="sxs-lookup"><span data-stu-id="fa721-104">Most of the information that the Schema Generation Wizard requires for generating relational schemas is extracted from the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cubes and dimensions that you already created in the project.</span></span> <span data-ttu-id="fa721-105">Além disso, você pode personalizar como o esquema de banco de dados de área de assunto é gerado e como são nomeados objetos no esquema.</span><span class="sxs-lookup"><span data-stu-id="fa721-105">Additionally, you can customize how the subject area database schema is generated and how objects in the schema are named.</span></span>  
  
## <a name="start-the-wizard"></a><span data-ttu-id="fa721-106">Inicie o assistente</span><span class="sxs-lookup"><span data-stu-id="fa721-106">Start the Wizard</span></span>  
 <span data-ttu-id="fa721-107">É possível abrir o Assistente de Geração de Esquema a partir do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] de vários modos diferentes:</span><span class="sxs-lookup"><span data-stu-id="fa721-107">You can open the Schema Generation Wizard from [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in several different ways:</span></span>  
  
-   <span data-ttu-id="fa721-108">Clique com o botão direito do mouse no objeto do projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e, em seguida, clique em **Novo Esquema Relacional** no menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="fa721-108">Right-click the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project object and then click **Generate Relational Schema** from the context menu.</span></span>  
  
-   <span data-ttu-id="fa721-109">Clique no objeto do projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e, em seguida, clique em **Novo Esquema Relacional** no menu **Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="fa721-109">Click the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project object, and then click **Generate Relational Schema** from the **Database** menu.</span></span>  
  
-   <span data-ttu-id="fa721-110">Inicie o assistente por meio do Assistente para Dimensões clicando na caixa de seleção **Gerar Esquema Agora** na última página do assistente.</span><span class="sxs-lookup"><span data-stu-id="fa721-110">Start the wizard from within the Dimension Wizard by clicking the **Generate Schema Now** check box on the last page of the wizard.</span></span>  
  
## <a name="step-1-specify-targets"></a><span data-ttu-id="fa721-111">Etapa 1: Especificar destinos</span><span class="sxs-lookup"><span data-stu-id="fa721-111">Step 1: Specify Targets</span></span>  
 <span data-ttu-id="fa721-112">Especifique a DSV (exibição da fonte de dados) na qual deseja que o Assistente de Geração de Esquema gere o esquema para o banco de dados da área de assunto.</span><span class="sxs-lookup"><span data-stu-id="fa721-112">You must specify the data source view (DSV) in which you want the Schema Generation Wizard to generate the schema for the subject area database.</span></span> <span data-ttu-id="fa721-113">Embora você possa selecionar um DSV existente, normalmente você cria um novo com base em uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="fa721-113">Although you can select an existing DSV, typically you create a new one based on a data source.</span></span> <span data-ttu-id="fa721-114">Você pode criar a fonte de dados a partir de uma conexão existente ou nova ou de um outro objeto.</span><span class="sxs-lookup"><span data-stu-id="fa721-114">You can create the data source based on an existing or a new connection, or based on another object.</span></span> <span data-ttu-id="fa721-115">O Assistente de Geração de Esquema gera o esquema para o banco de dados da área de assunto no banco de dados de referência da fonte de dados, bem como a exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="fa721-115">The Schema Generation Wizard generates the schema for the subject area database in the database referenced by the data source, as well as the data source view.</span></span> <span data-ttu-id="fa721-116">O Assistente de Geração de Esquema não criará o banco de dados da área de assunto; ele criará o esquema relacional que oferece suporte aos cubos e às dimensões de um banco de dados existente que você especificar.</span><span class="sxs-lookup"><span data-stu-id="fa721-116">The Schema Generation Wizard does not create the subject area database itself; instead, the wizard creates the relational schema to support the cubes and dimensions in an existing database that you specify.</span></span>  
  
 <span data-ttu-id="fa721-117">Ao gerar os objetos subjacentes, o Assistente de Geração de Esquema associará as dimensões e os cubos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] às tabelas e colunas geradas usando associações no estilo de exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="fa721-117">When the Schema Generation Wizard generates the underlying objects, it binds the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dimensions and cubes to the generated tables and columns by using data source view-style bindings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa721-118">Para desassociar dimensões e cubos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dos objetos gerados anteriormente, exclua a exibição da fonte de dados à qual as dimensões e os cubos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] foram associados e, em seguida, defina uma nova exibição da fonte de dados para eles usando o Assistente de Geração de Esquema.</span><span class="sxs-lookup"><span data-stu-id="fa721-118">To unbind [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dimensions and cubes from previously generated objects, delete the data source view to which the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cubes and dimensions are bound, and then define a new data source view for the cubes and dimensions by using the Schema Generation Wizard.</span></span>  
  
## <a name="step-3-specify-schema-options-for-the-subject-area-database"></a><span data-ttu-id="fa721-119">Etapa 3: Especificar opções de esquema para o banco de dados da área de assunto</span><span class="sxs-lookup"><span data-stu-id="fa721-119">Step 3: Specify Schema Options for the Subject Area Database</span></span>  
 <span data-ttu-id="fa721-120">O Assistente de Geração de Esquema oferece inúmeras opções para definição do esquema que é gerado para o banco de dados da área de assunto.</span><span class="sxs-lookup"><span data-stu-id="fa721-120">The Schema Generation Wizard provides a number of options for defining the schema that is generated for the subject area database.</span></span> <span data-ttu-id="fa721-121">Você pode especificar essas opções na página **Opções de Esquema de Banco de Dados da Área de Assunto** do assistente.</span><span class="sxs-lookup"><span data-stu-id="fa721-121">You can specify these options on the **Subject Area Database Schema Options** page of the wizard.</span></span>  
  
### <a name="specifying-the-schema-owner"></a><span data-ttu-id="fa721-122">Especificando o proprietário do esquema</span><span class="sxs-lookup"><span data-stu-id="fa721-122">Specifying the Schema Owner</span></span>  
 <span data-ttu-id="fa721-123">Você pode especificar o proprietário do esquema configurando o valor de **Esquema de propriedade** como uma cadeia de caracteres válida.</span><span class="sxs-lookup"><span data-stu-id="fa721-123">You can specify the owner of the schema by setting the value of **Owning schema** to a valid string.</span></span> <span data-ttu-id="fa721-124">O proprietário padrão do esquema é o projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , mas você pode especificar qualquer proprietário de esquema desejado.</span><span class="sxs-lookup"><span data-stu-id="fa721-124">The default owner of the schema is the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, but you can specify any desired schema owner.</span></span>  
  
### <a name="specifying-primary-keys-indexes-and-constraints"></a><span data-ttu-id="fa721-125">Especificando chaves primárias, índices e restrições</span><span class="sxs-lookup"><span data-stu-id="fa721-125">Specifying Primary Keys, Indexes, and Constraints</span></span>  
 <span data-ttu-id="fa721-126">Por padrão, o Assistente de Geração de Esquema cria uma restrição de chave primária em cada tabela de dimensões do banco de dados da área de assunto.</span><span class="sxs-lookup"><span data-stu-id="fa721-126">The Schema Generation Wizard by default creates a primary key constraint in each dimension table in the subject area database.</span></span> <span data-ttu-id="fa721-127">A chave primária corresponde ao atributo que é designado como o atributo de chave na dimensão correspondente do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa721-127">The primary key corresponds to the attribute that is designated as the key attribute in the corresponding [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dimension.</span></span> <span data-ttu-id="fa721-128">Essa restrição melhora o desempenho do processamento na maioria dos ambientes, a um custo mínimo.</span><span class="sxs-lookup"><span data-stu-id="fa721-128">This constraint improves processing performance in most environments, with minimal cost.</span></span> <span data-ttu-id="fa721-129">As chaves primárias lógicas são sempre criadas na exibição da fonte de dados, mesmo que você decida não criar a chave primária no banco de dados da área de assunto.</span><span class="sxs-lookup"><span data-stu-id="fa721-129">Logical primary keys are always created in the data source view, even if you choose not to create the primary key in the subject area database.</span></span> <span data-ttu-id="fa721-130">Para definir restrições de chave primária em tabelas de dimensões, selecione **Criar chaves primárias em tabelas de dimensões**.</span><span class="sxs-lookup"><span data-stu-id="fa721-130">To define primary key constraints on dimension tables, select **Create primary keys on dimension tables**.</span></span>  
  
 <span data-ttu-id="fa721-131">Por padrão, o assistente também criará índices nas colunas de chave estrangeira em cada tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="fa721-131">The wizard by default also creates indexes on the foreign key columns in each fact table.</span></span> <span data-ttu-id="fa721-132">Eles melhoram o desempenho de processamento na maioria dos ambientes.</span><span class="sxs-lookup"><span data-stu-id="fa721-132">These indexes improve processing performance in most environments.</span></span> <span data-ttu-id="fa721-133">Normalmente, o desempenho melhora porque as consultas de processamento geradas pelo [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para recuperar novos dados do banco de dados da área de assunto, em geral, contêm um número considerável de instruções de junção entre a tabela de fatos e as tabelas de dimensões.</span><span class="sxs-lookup"><span data-stu-id="fa721-133">Performance is typically improved because the processing queries that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] generates to retrieve new data from the subject area database typically include a significant number of join statements between the fact table and the dimension tables.</span></span> <span data-ttu-id="fa721-134">Para definir índices nas colunas de chave estrangeira de cada tabela de fatos, selecione **Criar índices**.</span><span class="sxs-lookup"><span data-stu-id="fa721-134">To define indexes on the foreign key columns in each fact table, select **Create indexes**.</span></span>  
  
 <span data-ttu-id="fa721-135">Finalmente, por padrão, o assistente impõe a integridade referencial entre a tabela de fatos e cada uma das tabelas de dimensões.</span><span class="sxs-lookup"><span data-stu-id="fa721-135">Finally, the wizard by default enforces referential integrity between the fact table and each of the dimension tables.</span></span> <span data-ttu-id="fa721-136">Se você preferir não impor a integridade referencial, o Assistente de Geração de Esquema ainda criará essas relações no banco de dados e na exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="fa721-136">If you choose not to enforce referential integrity, the Schema Generation Wizard still creates these relationships in the database and the data source view.</span></span> <span data-ttu-id="fa721-137">Para impor a integridade referencial, selecione **Impor a integridade referencial**.</span><span class="sxs-lookup"><span data-stu-id="fa721-137">To enforce referential integrity, select **Enforce referential integrity**.</span></span>  
  
### <a name="preserving-data-for-incremental-generation"></a><span data-ttu-id="fa721-138">Preservando dados para geração incremental</span><span class="sxs-lookup"><span data-stu-id="fa721-138">Preserving Data for Incremental Generation</span></span>  
 <span data-ttu-id="fa721-139">Por padrão, o Assistente de Geração de Esquema tentará preservar os dados quando o esquema do banco de dados for gerado novamente.</span><span class="sxs-lookup"><span data-stu-id="fa721-139">The Schema Generation Wizard by default attempts to preserve data when the database schema is regenerated.</span></span> <span data-ttu-id="fa721-140">Se o Assistente de Geração de Esquema tiver que excluir alguma linha devido a uma alteração no esquema, você receberá um aviso antes dessa exclusão.</span><span class="sxs-lookup"><span data-stu-id="fa721-140">If the Schema Generation Wizard has to delete any rows because of a schema change, you receive a warning before the rows are deleted.</span></span> <span data-ttu-id="fa721-141">Por exemplo, talvez seja necessário excluir linhas para resolver problemas de integridade referencial porque você descartou uma dimensão ou porque o tipo de dados mudou quando você alterou um atributo da dimensão.</span><span class="sxs-lookup"><span data-stu-id="fa721-141">For example, rows may have to be deleted to solve referential integrity issues because you dropped a dimension or because a data type changed when you changed a dimension attribute.</span></span> <span data-ttu-id="fa721-142">Para preservar os dados quando o esquema de banco de dados for gerado novamente, selecione **Preservar os dados na regeneração**.</span><span class="sxs-lookup"><span data-stu-id="fa721-142">To preserve data when the database schema is regenerated, select **Preserve data on regeneration**.</span></span>  
  
## <a name="step-4-specify-naming-conventions"></a><span data-ttu-id="fa721-143">Etapa 4: Especificar convenções de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="fa721-143">Step 4: Specify Naming Conventions</span></span>  
 <span data-ttu-id="fa721-144">É possível definir as convenções de nomenclatura que o Assistente de Geração de Esquema usará ao gerar determinados objetos no banco de dados da área de assunto na página **Especificar Convenções de Nomenclatura** do assistente.</span><span class="sxs-lookup"><span data-stu-id="fa721-144">You can define the naming conventions that the Schema Generation Wizard uses when generating certain objects in the subject area database on the **Specify Naming Conventions** page of the wizard.</span></span> <span data-ttu-id="fa721-145">Para obter mais informações sobre as opções disponíveis na página **Especificar Convenções de Nomenclatura**, consulte [Especificar Convenções de Nomenclatura &#40;Assistente de Geração de Esquema&#41; &#40;Analysis Services – Dados Multidimensionais&#41;](../specify-naming-conventions-schema-generation-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="fa721-145">For more information about the options available on the **Specify Naming Conventions** page, see [Specify Naming Conventions &#40;Schema Generation Wizard&#41; &#40;Analysis Services - Multidimensional Data&#41;](../specify-naming-conventions-schema-generation-analysis-services-multidimensional-data.md).</span></span>  
  
  