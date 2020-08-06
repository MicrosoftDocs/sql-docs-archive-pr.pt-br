---
title: Adicionar um relatório novo ou existente a um projeto de relatório (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], creating
ms.assetid: 8bc0bb53-ad8a-464d-bb6a-7fea5fa62c5c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b66bf8ef0181b549900d984d20b1279f9b5005c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684060"
---
# <a name="add-a-new-or-existing-report-to-a-report-project-ssrs"></a><span data-ttu-id="81d06-102">Adicionar um relatório novo ou existente a um projeto de relatório (SSRS)</span><span class="sxs-lookup"><span data-stu-id="81d06-102">Add a New or Existing Report to a Report Project (SSRS)</span></span>
  <span data-ttu-id="81d06-103">Em [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], você pode adicionar um relatório novo usando o Assistente de Relatório ou acrescentando um novo relatório em branco ao projeto.</span><span class="sxs-lookup"><span data-stu-id="81d06-103">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can add a new report by using the Report Wizard or by adding a new blank report to your project.</span></span> <span data-ttu-id="81d06-104">Também é possível adicionar um relatório existente.</span><span class="sxs-lookup"><span data-stu-id="81d06-104">You can also add an existing report.</span></span> <span data-ttu-id="81d06-105">Depois de adicionar um relatório, você poderá ver o nome do relatório listado na pasta **Relatórios** do seu projeto.</span><span class="sxs-lookup"><span data-stu-id="81d06-105">After you add a report, you can see the report name listed under the **Reports** folder in your project.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81d06-106">Para visualizar um relatório com fontes de dados existentes, é preciso ter as permissões para a fonte de dados do cliente que está criando o relatório.</span><span class="sxs-lookup"><span data-stu-id="81d06-106">To preview a report with existing data sources, you must have permissions to the data source from your report authoring client.</span></span> <span data-ttu-id="81d06-107">Para obter mais informações, consulte [criar uma fonte de dados inserida ou compartilhada &#40;&#41;SSRS ](../create-an-embedded-or-shared-data-source-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="81d06-107">For more information, see [Create an Embedded or Shared Data Source &#40;SSRS&#41;](../create-an-embedded-or-shared-data-source-ssrs.md).</span></span>  
  
 <span data-ttu-id="81d06-108">Depois de adicionar um relatório, é possível definir as fontes de dados e os conjuntos de dados, e criar um layout de relatório.</span><span class="sxs-lookup"><span data-stu-id="81d06-108">After you add a report, you can define data sources, datasets, and design a report layout.</span></span> <span data-ttu-id="81d06-109">Para começar, consulte [Criar um relatório de tabela básico &#40;Tutorial do SSRS&#41;](../create-a-basic-table-report-ssrs-tutorial.md) ou [Tabelas &#40;Construtor de Relatórios e SSRS&#41;](../report-design/tables-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="81d06-109">To get started, see [Create a Basic Table Report &#40;SSRS Tutorial&#41;](../create-a-basic-table-report-ssrs-tutorial.md) or [Tables &#40;Report Builder  and SSRS&#41;](../report-design/tables-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-add-a-new-report-using-the-report-wizard"></a><span data-ttu-id="81d06-110">Para adicionar um novo relatório usando o Assistente de Relatórios</span><span class="sxs-lookup"><span data-stu-id="81d06-110">To add a new report using the Report Wizard</span></span>  
  
1.  <span data-ttu-id="81d06-111">No Gerenciador de Soluções, clique com o botão direito do mouse na pasta Relatórios e clique em **Adicionar Novo Relatório**.</span><span class="sxs-lookup"><span data-stu-id="81d06-111">In Solution Explorer, right-click the Reports folder, and then click **Add New Report**.</span></span> <span data-ttu-id="81d06-112">A caixa de diálogo **Assistente de Relatório** é aberta.</span><span class="sxs-lookup"><span data-stu-id="81d06-112">The **Report Wizard** dialog box opens.</span></span>  
  
     <span data-ttu-id="81d06-113">O assistente conduzirá você pela criação de uma fonte de dados, a criação de um conjunto de dados com uma consulta, a definição de grupos, a escolha de um estilo que inclua cor e fonte, e a criação do relatório.</span><span class="sxs-lookup"><span data-stu-id="81d06-113">The wizard steps you through creating a data source, creating a dataset with a query, defining groups, specifying a layout, choosing a style that includes color and font, and creating the report.</span></span> <span data-ttu-id="81d06-114">As etapas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="81d06-114">The steps include:</span></span>  
  
    -   <span data-ttu-id="81d06-115">**Selecionar uma fonte de dados.**</span><span class="sxs-lookup"><span data-stu-id="81d06-115">**Select a Data Source.**</span></span> <span data-ttu-id="81d06-116">A primeira etapa ao criar um relatório é definir uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="81d06-116">The first step in creating a report is to define a data source.</span></span> <span data-ttu-id="81d06-117">O Assistente de Relatório apresenta uma lista de todas as fontes de dados compartilhadas no projeto de relatório, além de uma opção para criar uma nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="81d06-117">Report Wizard provides a list of all shared data sources in the report project, in addition to an option to create a new data source.</span></span>  
  
    -   <span data-ttu-id="81d06-118">**Criar uma consulta.**</span><span class="sxs-lookup"><span data-stu-id="81d06-118">**Design a Query.**</span></span> <span data-ttu-id="81d06-119">A próxima etapa é criar uma consulta.</span><span class="sxs-lookup"><span data-stu-id="81d06-119">The next step is to design a query.</span></span> <span data-ttu-id="81d06-120">É possível digitar a cadeia de caracteres da consulta, gerar no Designer de Consulta ou importar uma consulta a partir de outro relatório.</span><span class="sxs-lookup"><span data-stu-id="81d06-120">You can type the query string, build it using Query Designer, or import a query from another report.</span></span> <span data-ttu-id="81d06-121">Para obter informações sobre Designers de Consulta, consulte [Designers de Consulta do Reporting Services](../reporting-services-query-designers.md).</span><span class="sxs-lookup"><span data-stu-id="81d06-121">For information about Query Designers, see [Reporting Services Query Designers](../reporting-services-query-designers.md).</span></span>  
  
    -   <span data-ttu-id="81d06-122">**Escolher um tipo de relatório.**</span><span class="sxs-lookup"><span data-stu-id="81d06-122">**Choose a Report Type.**</span></span> <span data-ttu-id="81d06-123">A próxima etapa é selecionar o tipo de relatório desejado.</span><span class="sxs-lookup"><span data-stu-id="81d06-123">The next step is to select the type of report you want.</span></span> <span data-ttu-id="81d06-124">Você pode optar por um relatório tabular ou de matriz.</span><span class="sxs-lookup"><span data-stu-id="81d06-124">You can choose a tabular or matrix report.</span></span> <span data-ttu-id="81d06-125">Um relatório tabular tem um número fixo de colunas.</span><span class="sxs-lookup"><span data-stu-id="81d06-125">A tabular report has a fixed number of columns.</span></span> <span data-ttu-id="81d06-126">Uma relatório de matriz ou de tabulação cruzada apresenta um número variável de colunas com base nos resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="81d06-126">A matrix, or crosstab, report has a variable number of columns based on the results of the query.</span></span> <span data-ttu-id="81d06-127">Um relatório de mapa exibe dados analíticos em relação a um plano de fundo geográfico.</span><span class="sxs-lookup"><span data-stu-id="81d06-127">A map report displays analytical against a geographic background.</span></span>  
  
    -   <span data-ttu-id="81d06-128">**Escolha um estilo.**</span><span class="sxs-lookup"><span data-stu-id="81d06-128">**Choose a Style.**</span></span> <span data-ttu-id="81d06-129">A próxima etapa é aplicar um estilo ao relatório que usa um modelo de estilo.</span><span class="sxs-lookup"><span data-stu-id="81d06-129">The next step is to apply a style to the report using a style template.</span></span> <span data-ttu-id="81d06-130">Selecione um modelo para aplicar estilos como fonte, cor e estilo de borda ao relatório.</span><span class="sxs-lookup"><span data-stu-id="81d06-130">Select a template to apply styles such as font, color, and border style to the report.</span></span> <span data-ttu-id="81d06-131">O Designer de Relatórios fornece seis modelos de estilo: Ardósia, Floresta, Corporativo, Negrito, Azul-marinho e Genérico.</span><span class="sxs-lookup"><span data-stu-id="81d06-131">Report Designer provides six style templates: Slate, Forest, Corporate, Bold, Ocean, and Generic.</span></span> <span data-ttu-id="81d06-132">Você também pode adicionar modelos de estilo adicionais.</span><span class="sxs-lookup"><span data-stu-id="81d06-132">You can also add additional style templates.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="81d06-133">Você pode alterar os modelos existentes ou adicionar novos, editando o arquivo de StyleTemplates.xml na pasta \Program Files\Microsoft Visual Studio 10.0 \ Common7\IDE\PrivateAssemblies\Business Intelligence Wizards\Reports\Styles \\<Lang \> , em que \<lang> é o idioma que você está usando (por exemplo, se você estiver usando a versão do idioma inglês do [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] , o nome da pasta será "en").</span><span class="sxs-lookup"><span data-stu-id="81d06-133">You can alter existing templates or add new ones by editing the StyleTemplates.xml file in the \Program Files\Microsoft Visual Studio 10.0\Common7\IDE\PrivateAssemblies\Business Intelligence Wizards\Reports\Styles\\<lang\> folder, where \<lang> is the language you are using (for example, if you are using the English language version of [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], the folder name is "EN").</span></span> <span data-ttu-id="81d06-134">Esta pasta está localizada no computador em que o Designer de Relatórios está instalado.</span><span class="sxs-lookup"><span data-stu-id="81d06-134">This folder is located on the computer on which Report Designer is installed.</span></span> <span data-ttu-id="81d06-135">Há duas cópias do arquivo ModelosDeEstilo.xml.</span><span class="sxs-lookup"><span data-stu-id="81d06-135">There are two copies of the StyleTemplates.xml file.</span></span> <span data-ttu-id="81d06-136">Para modificar os estilos aplicados por meio do Assistente de Relatório, edite o arquivo na pasta criada para o idioma que está em uso.</span><span class="sxs-lookup"><span data-stu-id="81d06-136">To modify the styles that are applied through the Report Wizard, edit the file that is in the folder created for the language you are using.</span></span>  
  
    -   <span data-ttu-id="81d06-137">**Nome do relatório.**</span><span class="sxs-lookup"><span data-stu-id="81d06-137">**Name the Report.**</span></span>  <span data-ttu-id="81d06-138">A etapa final é nomear o relatório e verificar os campos que serão incluídos no relatório.</span><span class="sxs-lookup"><span data-stu-id="81d06-138">The final step is to name the report and verify the fields that will be included in the report.</span></span> <span data-ttu-id="81d06-139">Quando todas as etapas forem concluídas, o Designer de Relatórios criará o relatório e o adicionará ao projeto de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="81d06-139">When all steps are completed, Report Designer creates the report and adds it to the report server project.</span></span>  
  
### <a name="to-add-a-new-blank-report"></a><span data-ttu-id="81d06-140">Para adicionar um novo relatório em branco</span><span class="sxs-lookup"><span data-stu-id="81d06-140">To add a new blank report</span></span>  
  
1.  <span data-ttu-id="81d06-141">No menu **Projeto** , clique em **Adicionar Novo Item**.</span><span class="sxs-lookup"><span data-stu-id="81d06-141">From the **Project** menu, click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="81d06-142">Em **Modelos**, clique em **Relatório**.</span><span class="sxs-lookup"><span data-stu-id="81d06-142">In **Templates**, click **Report**.</span></span>  
  
3.  <span data-ttu-id="81d06-143">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="81d06-143">Click **Add**.</span></span>  
  
     <span data-ttu-id="81d06-144">Um novo relatório em branco é adicionado ao projeto e exibido na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="81d06-144">A new blank report is added to the project and displayed on the design surface.</span></span>  
  
### <a name="to-add-an-existing-report"></a><span data-ttu-id="81d06-145">Para adicionar um relatório existente</span><span class="sxs-lookup"><span data-stu-id="81d06-145">To add an existing report</span></span>  
  
1.  <span data-ttu-id="81d06-146">No menu **projeto** , clique em **Adicionar**e em **Item existente**.</span><span class="sxs-lookup"><span data-stu-id="81d06-146">From the **Project** menu, click **Add**, and then **Existing Item**.</span></span>  
  
2.  <span data-ttu-id="81d06-147">Navegue até o local do arquivo .rdl, selecione-o e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="81d06-147">Navigate to the location of the .rdl file, select it, and then click **Add**.</span></span>  
  
     <span data-ttu-id="81d06-148">O relatório é acrescentado ao projeto na pasta **Relatórios** .</span><span class="sxs-lookup"><span data-stu-id="81d06-148">The report is added to the project under the **Reports** folder.</span></span> <span data-ttu-id="81d06-149">Quando você fechar e reabrir o projeto, os relatórios serão classificados pela ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="81d06-149">When you close and re-open the project, reports are sorted alphabetically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81d06-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="81d06-150">See Also</span></span>  
 [<span data-ttu-id="81d06-151">Tutoriais do Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="81d06-151">Reporting Services Tutorials &#40;SSRS&#41;</span></span>](../reporting-services-tutorials-ssrs.md)  
  
  