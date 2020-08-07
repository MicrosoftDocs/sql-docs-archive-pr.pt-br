---
title: Relatórios, partes de relatório e definições de relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report definitions
- reports
ms.assetid: 2d746550-f8cc-4e97-8a06-d0f03cffc18d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0926de326d0b5859e895d69da4dd2ad7863ccd2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582296"
---
# <a name="reports-report-parts-and-report-definitions-report-builder-and-ssrs"></a><span data-ttu-id="363d5-102">Relatórios, partes de relatório e definições de relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="363d5-102">Reports, Report Parts, and Report Definitions (Report Builder and SSRS)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="363d5-103">o usa uma variedade de termos para descrever um relatório em diferentes Estados, incluindo a definição inicial, o relatório publicado e o relatório exibido como ele aparece para o usuário.</span><span class="sxs-lookup"><span data-stu-id="363d5-103">uses a variety of terms to describe a report in different states, including the initial definition, the published report, and the viewed report as it appears to the user.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="report-definition-rdl-files"></a><span data-ttu-id="363d5-104">Arquivos de definição de relatório (.rdl)</span><span class="sxs-lookup"><span data-stu-id="363d5-104">Report Definition (.rdl) Files</span></span>  
 <span data-ttu-id="363d5-105">Uma definição de relatório é um arquivo que você cria no Construtor de Relatórios ou no Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="363d5-105">A report definition is a file that you create in Report Builder or Report Designer.</span></span> <span data-ttu-id="363d5-106">Ela fornece uma descrição completa das conexões de fonte de dados, das consultas usadas para recuperar dados, das expressões, dos parâmetros, das imagens, das caixas de texto, das tabelas e de todos os outros elementos de tempo de design que podem ser incluídos em um relatório.</span><span class="sxs-lookup"><span data-stu-id="363d5-106">It provides a complete description of data source connections, queries used to retrieve data, expressions, parameters, images, text boxes, tables, and any other design-time elements that you might include in a report.</span></span> <span data-ttu-id="363d5-107">Embora as definições de relatório possam ser complexas, elas especificam, no mínimo, uma consulta e outros conteúdos do relatório, propriedades de relatório e um layout de relatório.</span><span class="sxs-lookup"><span data-stu-id="363d5-107">Although report definitions can be complex, at a minimum they specify a query and other report content, report properties, and a report layout.</span></span>  
  
 <span data-ttu-id="363d5-108">As definições de relatório são renderizadas em tempo de execução como um relatório processado.</span><span class="sxs-lookup"><span data-stu-id="363d5-108">Report definitions are rendered at run time as a processed report.</span></span> <span data-ttu-id="363d5-109">Naquele momento, os dados são recuperados da fonte de dados e formatados de acordo com as instruções na definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="363d5-109">At that time, the data is retrieved from the data source and formatted according to the instructions in the report definition.</span></span> <span data-ttu-id="363d5-110">Uma definição de relatório pode ser executada diretamente de seu computador e salva localmente ou pode ser publicada em um servidor de relatório para que outros possam executá-la também.</span><span class="sxs-lookup"><span data-stu-id="363d5-110">A report definition can be run directly from your computer and saved locally, or it can be published to a report server for others to run as well.</span></span>  
  
 <span data-ttu-id="363d5-111">As definições de relatório são gravadas em XML em conformidade com uma gramática XML chamada linguagem RDL.</span><span class="sxs-lookup"><span data-stu-id="363d5-111">Report definitions are written in XML that conforms to an XML grammar called Report Definition Language (RDL).</span></span> <span data-ttu-id="363d5-112">A linguagem RDL descreve os elementos XML, abrangendo todas as possíveis variações que um relatório pode assumir.</span><span class="sxs-lookup"><span data-stu-id="363d5-112">RDL describes the XML elements, encompassing all possible variations that a report can assume.</span></span>  
  
## <a name="client-report-definition-rdlc-files"></a><span data-ttu-id="363d5-113">Arquivos de definição de relatório de cliente (.rdlc)</span><span class="sxs-lookup"><span data-stu-id="363d5-113">Client Report Definition (.rdlc) Files</span></span>  
 <span data-ttu-id="363d5-114">O Designer de Relatórios do Visual Studio produz arquivos de definição de relatório de cliente (.rdlc) a serem usados com o controle ReportViewer.</span><span class="sxs-lookup"><span data-stu-id="363d5-114">The Visual Studio Report Designer produces client report definition (.rdlc) files for use with the ReportViewer control.</span></span> <span data-ttu-id="363d5-115">Os arquivos .rdlc podem ser convertidos em arquivos .rdl para serem usados com o Designer de Relatórios do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="363d5-115">The .rdlc files can be converted to .rdl files for use with Reporting Services Report Designer.</span></span>  
  
## <a name="report-part-rsc-files"></a><span data-ttu-id="363d5-116">Arquivos de partes de relatório (.rsc)</span><span class="sxs-lookup"><span data-stu-id="363d5-116">Report Part (.rsc) Files</span></span>  
 <span data-ttu-id="363d5-117">Uma definição de parte de relatório é um fragmento XML de um arquivo de definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="363d5-117">A report part definition is an XML fragment of a report definition file.</span></span> <span data-ttu-id="363d5-118">Para criar partes de relatório, crie uma definição de relatório e depois selecione itens de relatório no relatório para publicar separadamente como partes de relatório.</span><span class="sxs-lookup"><span data-stu-id="363d5-118">You create report parts by creating a report definition, and then selecting report items in the report to publish separately as report parts.</span></span> <span data-ttu-id="363d5-119">Partes de relatório incluem regiões de dados, retângulos, além dos itens e imagens contidos neles.</span><span class="sxs-lookup"><span data-stu-id="363d5-119">Report parts include data regions, rectangles and their contained items, and images.</span></span> <span data-ttu-id="363d5-120">Você pode salvar uma parte de relatório com conjuntos de dados dependentes e referências à fonte de dados compartilhada para que ela seja reutilizada em outros relatórios.</span><span class="sxs-lookup"><span data-stu-id="363d5-120">You can save a report part with its dependent datasets and shared data source references so it can be reused in other reports.</span></span>  
  
 [!INCLUDE[ssRBrptparts](../../includes/ssrbrptparts-md.md)]  
  
## <a name="published-reports"></a><span data-ttu-id="363d5-121">Relatórios publicados</span><span class="sxs-lookup"><span data-stu-id="363d5-121">Published Reports</span></span>  
 <span data-ttu-id="363d5-122">Após criar um arquivo .rdl, você poderá salvá-lo localmente ou em uma pasta pessoal (como a pasta Meus Relatórios) no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="363d5-122">After you create an .rdl file, you can save it locally, or save it to a personal folder (such as the My Reports folder) on the report server.</span></span> <span data-ttu-id="363d5-123">Quando o relatório está pronto para verificação por outros, você o publica salvando-o do Construtor de Relatórios em uma pasta pública no servidor de relatório, carregando-o através do Gerenciador de Relatórios ou implantando uma solução de projeto de relatório do Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="363d5-123">When the report is ready for others to see, you publish it by saving it from Report Builder to a public folder on the report server, uploading it through Report Manager, or deploying a report project solution from Report Designer.</span></span> <span data-ttu-id="363d5-124">Um relatório publicado é um item que foi armazenado em um banco de dados de servidor de relatório e gerenciado em um servidor de relatório ou site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="363d5-124">A published report is an item that is stored in a report server database and managed on a report server or SharePoint site.</span></span>  
  
 <span data-ttu-id="363d5-125">Um relatório publicado é protegido por atribuições de função que usam o modelo de segurança baseada em funções do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="363d5-125">A published report is secured through role assignments using the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] role-based security model.</span></span> <span data-ttu-id="363d5-126">Os relatórios publicados são acessados por meio de URLs, de Web Parts do SharePoint ou do Gerenciador de Relatórios. Outra opção é navegar até eles e abri-los no Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="363d5-126">Published reports are accessed through URLs, SharePoint Web parts, or Report Manager, or you can navigate to and open them in Report Builder.</span></span>  
  
### <a name="report-snapshots"></a><span data-ttu-id="363d5-127">Instantâneos de relatório</span><span class="sxs-lookup"><span data-stu-id="363d5-127">Report Snapshots</span></span>  
 <span data-ttu-id="363d5-128">Um relatório também pode ser publicado como um instantâneo que contém informações de layout e dados do momento em que foi executado inicialmente.</span><span class="sxs-lookup"><span data-stu-id="363d5-128">A report can also be published as a snapshot that contains both layout information and data as of the time the report was initially run.</span></span> <span data-ttu-id="363d5-129">Os instantâneos de relatório não são salvos em um formato de renderização específico.</span><span class="sxs-lookup"><span data-stu-id="363d5-129">Report snapshots are not saved in a particular rendering format.</span></span> <span data-ttu-id="363d5-130">Em vez disso, os instantâneos de relatório são renderizados em um formato de exibição final (como HTML) somente quando solicitado por um usuário ou aplicativo.</span><span class="sxs-lookup"><span data-stu-id="363d5-130">Instead, report snapshots are rendered in a final viewing format (such as HTML) only when a user or an application requests it.</span></span> <span data-ttu-id="363d5-131">Para obter mais informações, consulte [Localizando e exibindo relatórios no Gerenciador de Relatórios &#40;Construtor de Relatórios e SSRS&#41;](../report-builder/finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="363d5-131">For more information, see [Finding and Viewing Reports in Report Manager &#40;Report Builder and SSRS&#41;](../report-builder/finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md).</span></span>  
  
## <a name="rendered-reports"></a><span data-ttu-id="363d5-132">Relatórios renderizados</span><span class="sxs-lookup"><span data-stu-id="363d5-132">Rendered Reports</span></span>  
 <span data-ttu-id="363d5-133">Um relatório renderizado é um relatório totalmente processado que contém dados e informações de layout em um formato adequado para exibição (como HTML).</span><span class="sxs-lookup"><span data-stu-id="363d5-133">A rendered report is a fully processed report that contains both data and layout information in a format suitable for viewing (such as HTML).</span></span> <span data-ttu-id="363d5-134">O relatório não pode ser exibido até ser renderizado em um formato de saída.</span><span class="sxs-lookup"><span data-stu-id="363d5-134">Until a report is rendered into an output format, it cannot be viewed.</span></span> <span data-ttu-id="363d5-135">Siga um destes procedimentos para renderizar um relatório:</span><span class="sxs-lookup"><span data-stu-id="363d5-135">You can render a report by doing one of the following:</span></span>  
  
-   <span data-ttu-id="363d5-136">Crie ou abra um relatório no Construtor de Relatórios ou no Designer de Relatórios e execute-o.</span><span class="sxs-lookup"><span data-stu-id="363d5-136">Create or open a report in Report Builder or Report Designer and run it.</span></span>  
  
-   <span data-ttu-id="363d5-137">Localize e execute um relatório no Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="363d5-137">Find and run a report in Report Manager.</span></span>  
  
-   <span data-ttu-id="363d5-138">Localize e execute um relatório em um site do SharePoint integrado com um servidor de relatório do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="363d5-138">Find and run a report on a SharePoint site that is integrated with a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server.</span></span>  
  
-   <span data-ttu-id="363d5-139">Assine um relatório, que é entregue em uma caixa de entrada de email ou em um compartilhamento de arquivo em um formato de saída especificado por você.</span><span class="sxs-lookup"><span data-stu-id="363d5-139">Subscribe to a report, which is delivered to an e-mail inbox or a file share in an output format that you specify.</span></span>  
  
 <span data-ttu-id="363d5-140">Assine um relatório, que é distribuído a uma caixa de entrada de emails ou a um compartilhamento de arquivos em um formato de saída especificado por você. O formato de renderização padrão de um relatório é HTML 4.0.</span><span class="sxs-lookup"><span data-stu-id="363d5-140">Subscribe to a report, which is delivered to an e-mail inbox or a file share in an output format that you specify.The default rendering format for a report is HTML 4.0.</span></span> <span data-ttu-id="363d5-141">Além do HTML, os relatórios podem ser renderizados em diversos formatos de saída, incluindo Excel, Word, XML, PDF, TIFF e CSV.</span><span class="sxs-lookup"><span data-stu-id="363d5-141">In addition to HTML, reports can be rendered in a variety of output formats, including Excel, Word, XML, PDF, TIFF, and CSV.</span></span> <span data-ttu-id="363d5-142">Assim como os relatórios publicados, os relatórios renderizados não podem ser editados nem salvos em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="363d5-142">As with published reports, rendered reports cannot be edited or saved back to a report server.</span></span> <span data-ttu-id="363d5-143">Para obter mais informações, consulte [Exportando relatórios &#40;Construtor de relatórios e SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="363d5-143">For more information, see [Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="363d5-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="363d5-144">See Also</span></span>  
 <span data-ttu-id="363d5-145">[Conceitos de criação de relatório &#40;Construtor de Relatórios e SSRS&#41;](report-authoring-concepts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="363d5-145">[Report Authoring Concepts &#40;Report Builder and SSRS&#41;](report-authoring-concepts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="363d5-146">[Construtor de Relatórios no SQL Server 2014](../report-builder/report-builder-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="363d5-146">[Report Builder in SQL Server 2014](../report-builder/report-builder-in-sql-server-2016.md) </span></span>  
 <span data-ttu-id="363d5-147">[Instalar, desinstalar e Construtor de Relatórios suporte](../install-uninstall-and-report-builder-support.md) </span><span class="sxs-lookup"><span data-stu-id="363d5-147">[Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md) </span></span>  
 <span data-ttu-id="363d5-148">[Localizando, exibindo e gerenciando relatórios &#40;Construtor de Relatórios e SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="363d5-148">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="363d5-149">Exportando relatórios &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="363d5-149">Exporting Reports &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/export-reports-report-builder-and-ssrs.md)  
  
  