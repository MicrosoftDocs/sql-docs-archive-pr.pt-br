---
title: Layout da página e renderização (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e2358653-35bc-4496-810a-d3ccf02f229f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 360bb15df7ccd1620474010409a44fe01f8d53d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681435"
---
# <a name="page-layout-and-rendering-report-builder-and-ssrs"></a><span data-ttu-id="38f2f-102">Layout de página e renderização (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="38f2f-102">Page Layout and Rendering (Report Builder and SSRS)</span></span>
  <span data-ttu-id="38f2f-103">Quando você cria relatórios, é importante compreender o comportamento dos renderizadores do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para garantir que o relatório renderizado tenha a aparência desejada, incluindo o layout de página e as quebras de páginas.</span><span class="sxs-lookup"><span data-stu-id="38f2f-103">When you author reports it is important to understand the behavior of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] renderers to ensure the rendered report looks the way you want, including page layout and page breaks.</span></span> <span data-ttu-id="38f2f-104">Provavelmente, você também deseja ter certeza de que o relatório renderizado se ajusta ao tamanho do papel geralmente usado na sua organização.</span><span class="sxs-lookup"><span data-stu-id="38f2f-104">You likely also want to make sure the rendered report fits on the paper size that you or your organization commonly uses.</span></span>  
  
 <span data-ttu-id="38f2f-105">Quando você exibe relatórios no Gerenciador de Relatórios ou no painel de visualização do Construtor de Relatórios ou o Designer de Relatórios, o relatório é renderizado primeiro pelo renderizador HTML.</span><span class="sxs-lookup"><span data-stu-id="38f2f-105">When you view reports in Report Manager or the preview pane of Report Builder or Report Designer, the report in first rendered by the HTML renderer.</span></span> <span data-ttu-id="38f2f-106">Você pode exportar o relatório então para formatos diferentes, como Excel ou CSV.</span><span class="sxs-lookup"><span data-stu-id="38f2f-106">You can then export the report to different formats such as Excel or Comma Separated File (CSV).</span></span> <span data-ttu-id="38f2f-107">O relatório exportado pode ser usado então para análise adicional no Excel ou como fonte de dados para aplicativos que podem importar e usar arquivos de dados CSV.</span><span class="sxs-lookup"><span data-stu-id="38f2f-107">The exported report can then be used for further analysis in Excel or as data source for applications that can import and use CSV data files.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="38f2f-108">inclui um conjunto de renderizadores para exportar relatórios para formatos diferentes.</span><span class="sxs-lookup"><span data-stu-id="38f2f-108">includes a set of renderers for exporting reports to different formats.</span></span> <span data-ttu-id="38f2f-109">Cada renderizador aplica regras ao renderizar relatórios.</span><span class="sxs-lookup"><span data-stu-id="38f2f-109">Each renderer has applies rules when rendering reports.</span></span> <span data-ttu-id="38f2f-110">Quando você exporta um relatório para um formato de arquivo diferente, principalmente para renderizadores como o Adobe Acrobat (PDF), que usa paginação com base no tamanho de página físico, talvez seja necessário alterar o layout de seu relatório para que o relatório exportado pareça e seja impresso corretamente após a aplicação das regras de renderização.</span><span class="sxs-lookup"><span data-stu-id="38f2f-110">When you export a report to a different file format, especially for renderers such as the Adobe Acrobat (PDF) renderer that uses pagination based on the physical page size, you might need to change the layout of your report to have the exported report look and print correctly after the rendering rules are applied.</span></span>  
  
 <span data-ttu-id="38f2f-111">A obtenção dos melhores resultados para relatórios exportados é frequentemente um processo iterativo; você cria e visualiza o relatório no Construtor de Relatórios ou no Designer de Relatórios, exporta o relatório para o formato de sua preferência, examina o relatório exportado e faz as alterações no relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-111">Getting the best results for exported reports is often an iterative process; you author and preview the report in Report Builder or Report Designer, export the report to the preferred format, review the exported report, and then make changes to the report.</span></span>  
  
 <span data-ttu-id="38f2f-112">Este tópico fornece informações sobre as extensões de renderização do Reporting Services e como trabalhar com elas.</span><span class="sxs-lookup"><span data-stu-id="38f2f-112">This topic provides information about the Reporting Services rendering extensions and how to work with them.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="page-layout-and-report-items"></a><a name="PageLayout"></a><span data-ttu-id="38f2f-113">Layout de página e itens de relatório</span><span class="sxs-lookup"><span data-stu-id="38f2f-113">Page Layout and Report Items</span></span>  
 <span data-ttu-id="38f2f-114">Os itens de relatório são elementos de layout que são associados a diferentes tipos de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-114">Report items are layout elements that are associated with different types of report data.</span></span> <span data-ttu-id="38f2f-115">Tabela, matriz, lista, gráfico e medidor são itens de relatório da região de dados que se vinculam a um conjunto de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-115">Table, Matrix, List, Chart, and Gauge are data region report items that each link to a report dataset.</span></span> <span data-ttu-id="38f2f-116">Quando o relatório é processado, a região de dados é expandida para cima e para baixo da página de relatório para exibir dados.</span><span class="sxs-lookup"><span data-stu-id="38f2f-116">When the report is processed, the data region expands across and down the report page to display data.</span></span> <span data-ttu-id="38f2f-117">Outros itens de relatório são vinculados e exibem um item simples.</span><span class="sxs-lookup"><span data-stu-id="38f2f-117">Other report items link to and display a single item.</span></span> <span data-ttu-id="38f2f-118">Um item de relatório **Imagem** é vinculado a uma imagem.</span><span class="sxs-lookup"><span data-stu-id="38f2f-118">An **Image** report item links to a picture.</span></span> <span data-ttu-id="38f2f-119">Um item de relatório **Caixa de Texto** contém texto simples, como um título ou uma expressão que pode incluir referências a campos internos, parâmetros de relatório ou campos do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="38f2f-119">A **Text Box** report item contains either simple text like a title or an expression that can include references to built-in fields, report parameters, or dataset fields.</span></span> <span data-ttu-id="38f2f-120">Os itens de relatório **Linha** e **Retângulo** fornecem elementos gráficos simples para a página do relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-120">The **Line** and **Rectangle** report items provide simple graphical elements on the report page.</span></span> <span data-ttu-id="38f2f-121">O **Retângulo** também pode ser um contêiner para outros itens de relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-121">The **Rectangle** can also be a container for other report items.</span></span> <span data-ttu-id="38f2f-122">Um relatório pode conter sub-relatórios.</span><span class="sxs-lookup"><span data-stu-id="38f2f-122">A report can contain subreports.</span></span>  
  
 <span data-ttu-id="38f2f-123">Com o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], você pode colocar itens de relatório em qualquer local na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="38f2f-123">With [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can place report items anywhere on the design surface.</span></span> <span data-ttu-id="38f2f-124">De maneira interativa, é possível colocar, expandir e assumir a forma inicial do item de relatório usando linhas ajustadas e redimensionando alças.</span><span class="sxs-lookup"><span data-stu-id="38f2f-124">You can interactively position, expand, and contract the initial shape of the report item using snap lines and resizing handles.</span></span> <span data-ttu-id="38f2f-125">Você poderá colocar regiões de dados com diferentes conjuntos de dados ou até os mesmos dados em diferentes formatos, lado a lado.</span><span class="sxs-lookup"><span data-stu-id="38f2f-125">You can place data regions with different sets of data, or even the same data in different formats, side-by-side.</span></span> <span data-ttu-id="38f2f-126">Ao colocar um item de relatório na superfície de design, ele apresenta tamanho, forma e relação inicial padrão com relação a todos os outros itens de relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-126">When you place a report item on the design surface, it has a default size and shape and an initial relationship to all other report items.</span></span> <span data-ttu-id="38f2f-127">Você pode colocar muitos itens de relatório um ao outro criar mais designs de relatório complexos.</span><span class="sxs-lookup"><span data-stu-id="38f2f-127">You can place many report items each other to create more complex report designs.</span></span> <span data-ttu-id="38f2f-128">Por exemplo, traça um gráfico ou imagens em células de tabela, tabelas em células de tabela e várias imagens em um retângulo.</span><span class="sxs-lookup"><span data-stu-id="38f2f-128">For example, charts or images in table cells, tables in table cells, and multiple images in a rectangle.</span></span> <span data-ttu-id="38f2f-129">Além de fornecer a organização e olha você deseja no relatório, colocando itens de relatório em contêineres como retângulos ajuda controlar o modo que os itens de relatório são exibidos na página de relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-129">In addition to providing the organization and look you want in the report, placing report items in containers such as rectangles help control the way the report items are displayed on the report page.</span></span>  
  
 <span data-ttu-id="38f2f-130">Um relatório pode ajustar várias páginas, com cabeçalho e rodapé iguais em cada uma das páginas.</span><span class="sxs-lookup"><span data-stu-id="38f2f-130">A report can span multiple pages, with a page header and page footer that are repeated on each page.</span></span> <span data-ttu-id="38f2f-131">Além disso, um relatório pode conter elementos gráficos, como imagens e linhas, além de várias fontes, cores e estilos que podem ter como base as expressões.</span><span class="sxs-lookup"><span data-stu-id="38f2f-131">A report can contain graphical elements such as images and lines, and it can have multiple fonts, colors, and styles, which can be based on expressions.</span></span>  
  
##  <a name="report-sections"></a><a name="ReportSections"></a> <span data-ttu-id="38f2f-132">Seções do relatório</span><span class="sxs-lookup"><span data-stu-id="38f2f-132">Report Sections</span></span>  
 <span data-ttu-id="38f2f-133">Um relatório é formado por três seções principais: um cabeçalho de página opcional, um rodapé de página opcional e um corpo para a mensagem.</span><span class="sxs-lookup"><span data-stu-id="38f2f-133">A report consists of three main sections: an optional page header, an optional page footer, and a report body.</span></span> <span data-ttu-id="38f2f-134">O cabeçalho e o rodapé do relatório não são seções separadas do relatório, mas fazem parte dos itens de relatório que são colocados na parte superior e inferior do corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-134">The report header and footer are not separate sections of the report, but rather are comprised of the report items that are placed at the top and bottom of the report body.</span></span> <span data-ttu-id="38f2f-135">O cabeçalho e o rodapé repetem o mesmo conteúdo na parte superior e inferior de cada página do relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-135">The page header and page footer repeat the same content at the top and bottom of each page of the report.</span></span> <span data-ttu-id="38f2f-136">Você pode colocar imagens, caixas de texto e linhas em cabeçalhos e rodapés.</span><span class="sxs-lookup"><span data-stu-id="38f2f-136">You can place images, text boxes, and lines in headers and footers.</span></span> <span data-ttu-id="38f2f-137">Todos os tipos de itens de relatório podem ser colocados no corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-137">You can place all types of report items in the report body.</span></span>  
  
 <span data-ttu-id="38f2f-138">Você também pode definir propriedades nos itens de relatório para inicialmente ocultá-los ou mostrá-los na página.</span><span class="sxs-lookup"><span data-stu-id="38f2f-138">You can set properties on report items to initially hide or show them on the page.</span></span> <span data-ttu-id="38f2f-139">As propriedades de visibilidade podem ser definidas em linhas, colunas ou grupos para regiões de dados e fornecer botões de alternância, permitindo ao usuário mostrar ou ocultar os dados do relatório de maneira interativa.</span><span class="sxs-lookup"><span data-stu-id="38f2f-139">You can set visibility properties on rows or columns or groups for data regions and provide toggle buttons to allow the user to interactively show or hide report data.</span></span> <span data-ttu-id="38f2f-140">Também é possível definir a visibilidade ou a visibilidade inicial usando expressões, inclusive expressões baseadas em parâmetros de relatórios.</span><span class="sxs-lookup"><span data-stu-id="38f2f-140">You can set visibility or initial visibility by using expressions, including expressions based on report parameters.</span></span>  
  
 <span data-ttu-id="38f2f-141">Quando um relatório é processado, os dados do relatório são combinados com os elementos de layout do relatório e os dados combinados são enviados para um processador de relatórios.</span><span class="sxs-lookup"><span data-stu-id="38f2f-141">When a report is processed, report data is combined with the report layout elements and the combined data is sent to a report renderer.</span></span> <span data-ttu-id="38f2f-142">O processador segue regras predefinidas de item de expansão e determina a quantidade de dados que será ajustada em cada página.</span><span class="sxs-lookup"><span data-stu-id="38f2f-142">The renderer follows predefined rules for report item expansion and determines how much data fits on each page.</span></span> <span data-ttu-id="38f2f-143">Para desenvolver com êxito um relatório que seja lido facilmente e que seja otimizado para o processador que você pretende usar, é preciso compreender as regras usadas para controlar a paginação no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38f2f-143">To design an easy-to-read report that is optimized for the renderer that you plan to use, you should understand the rules used to control pagination in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="38f2f-144">Para obter mais informações, consulte [Paginação no Reporting Services &#40;Construtor de Relatórios e SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="38f2f-144">For more information, see [Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md).</span></span>  
  
##  <a name="renderers"></a><a name="RenderingExtensions"></a> <span data-ttu-id="38f2f-145">Renderizadores</span><span class="sxs-lookup"><span data-stu-id="38f2f-145">Renderers</span></span>  
 <span data-ttu-id="38f2f-146">O Reporting Services inclui um conjunto de renderizadores, também chamado extensões de renderização, que você pode usar para exportar relatórios para formatos diferentes.</span><span class="sxs-lookup"><span data-stu-id="38f2f-146">Reporting Services includes a set of renderers, also referred to as rendering extensions, that you can use to export reports to different formats.</span></span> <span data-ttu-id="38f2f-147">Há três tipos de renderizadores:</span><span class="sxs-lookup"><span data-stu-id="38f2f-147">There are three types of renderers:</span></span>  
  
-   <span data-ttu-id="38f2f-148">**Renderizadores de dados** Os renderizadores de dados eliminam todas as informações de formatação e layout do relatório e exibem apenas os dados.</span><span class="sxs-lookup"><span data-stu-id="38f2f-148">**Data renderers** Data renderers strip all formatting and layout information from the report and display only the data.</span></span> <span data-ttu-id="38f2f-149">O arquivo resultante pode ser usado para importar os dados brutos do relatório para outro tipo de arquivo, como o Excel, ou outro banco de dados, como uma mensagem de dados XML ou um aplicativo personalizado.</span><span class="sxs-lookup"><span data-stu-id="38f2f-149">The resulting file can be used to import the raw report data into another file type, such as Excel, or another database, an XML data message, or a custom application.</span></span> <span data-ttu-id="38f2f-150">Os renderizadores de dados disponíveis são: CSV e XML.</span><span class="sxs-lookup"><span data-stu-id="38f2f-150">The available data renders are: CSV and XML.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="38f2f-151">Embora não forneça exportação direta para um formato diferente, a renderização Atom gera arquivos de dados com base em relatórios.</span><span class="sxs-lookup"><span data-stu-id="38f2f-151">Although it does not provide direct export to a different format, Atom rendering generates data files from reports.</span></span>  
  
-   <span data-ttu-id="38f2f-152">**Renderizadores de quebra de página flexível** Os renderizadores de quebra de página flexível mantêm o layout e a formatação do relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-152">**Soft page-break renderers** Soft page-break renderers maintain the report layout and formatting.</span></span> <span data-ttu-id="38f2f-153">O arquivo resultante é otimizado para exibição e entrega com base na tela, como em uma página da Web.</span><span class="sxs-lookup"><span data-stu-id="38f2f-153">The resulting file is optimized for screen-based viewing and delivery, such as on a Web page.</span></span> <span data-ttu-id="38f2f-154">Os renderizadores de quebra de página flexível disponíveis são: o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel, o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Word, MHTML (arquivo da Web) e HTML.</span><span class="sxs-lookup"><span data-stu-id="38f2f-154">The available soft page-break renderers are: [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Word, Web archive (MHTML), and HTML.</span></span>  
  
-   <span data-ttu-id="38f2f-155">**Renderizadores de quebra de página impressa** Os renderizadores de quebra de página impressa mantêm o layout e a formatação do relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-155">**Hard page-break renderers** Hard page-break renderers maintain the report layout and formatting.</span></span> <span data-ttu-id="38f2f-156">O arquivo resultante é otimizado para uma experiência consistente de impressão, ou para exibir o relatório online em formato de um livro.</span><span class="sxs-lookup"><span data-stu-id="38f2f-156">The resulting file is optimized for a consistent printing experience, or to view the report online in a book format.</span></span> <span data-ttu-id="38f2f-157">Os renderizadores de quebra de página não flexíveis disponíveis têm suporte: TIFF e PDF.</span><span class="sxs-lookup"><span data-stu-id="38f2f-157">The available hard page-break renderers are supported: TIFF and PDF.</span></span>  
  
 <span data-ttu-id="38f2f-158">Quando você visualiza um relatório no Construtor de Relatórios ou no Designer de Relatórios, ou executa um relatório no Gerenciador de Relatórios, ele é sempre renderizado primeiro em HTML.</span><span class="sxs-lookup"><span data-stu-id="38f2f-158">When you preview  a report in Report Builder or Report Designer or run a report in Report Manager, the report is always first rendered in HTML.</span></span> <span data-ttu-id="38f2f-159">Depois que executar o relatório, é possível exportá-lo para diversos formatos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="38f2f-159">After you run the report, you can export it to different file formats.</span></span> <span data-ttu-id="38f2f-160">Para obter mais informações, consulte [Exportando relatórios &#40;Construtor de relatórios e SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="38f2f-160">For more information, see [Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md).</span></span>  
  
  
  
##  <a name="rendering-behaviors"></a><a name="RenderingBehaviors"></a><span data-ttu-id="38f2f-161">Comportamentos de renderização</span><span class="sxs-lookup"><span data-stu-id="38f2f-161">Rendering Behaviors</span></span>  
 <span data-ttu-id="38f2f-162">Dependendo do renderizador selecionado, algumas regras são aplicadas durante a renderização do relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-162">Depending on the renderer you select, certain rules are applied when rendering the report.</span></span> <span data-ttu-id="38f2f-163">Como os itens de relatório são ajustados juntos em uma página é determinado pela combinação destes fatores:</span><span class="sxs-lookup"><span data-stu-id="38f2f-163">How report items fit together on a page is determined by the combination of these factors:</span></span>  
  
-   <span data-ttu-id="38f2f-164">Renderizando regras.</span><span class="sxs-lookup"><span data-stu-id="38f2f-164">Rendering rules.</span></span>  
  
-   <span data-ttu-id="38f2f-165">A largura e altura dos itens de relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-165">The width and height of report items.</span></span>  
  
-   <span data-ttu-id="38f2f-166">O tamanho do corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-166">The size of the report body.</span></span>  
  
-   <span data-ttu-id="38f2f-167">A largura e altura da página.</span><span class="sxs-lookup"><span data-stu-id="38f2f-167">The width and height of the page.</span></span>  
  
-   <span data-ttu-id="38f2f-168">Suporte específico do renderizador para paginação.</span><span class="sxs-lookup"><span data-stu-id="38f2f-168">Renderer-specific support for paging.</span></span>  
  
 <span data-ttu-id="38f2f-169">Por exemplo, os relatórios renderizados para formatos HTML e MHTML são otimizados para uma experiência baseada em telas de computador em que as páginas podem ter vários comprimentos.</span><span class="sxs-lookup"><span data-stu-id="38f2f-169">For example, reports rendered to HTML and MHTML formats are optimized for a computer screen-based experience where pages can be various lengths.</span></span>  
  
 <span data-ttu-id="38f2f-170">Para obter mais informações, consulte [Comportamentos de renderização &#40;Construtor de Relatórios e SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="38f2f-170">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
  
  
##  <a name="pagination"></a><a name="Pagination"></a><span data-ttu-id="38f2f-171">Pagina</span><span class="sxs-lookup"><span data-stu-id="38f2f-171">Pagination</span></span>  
 <span data-ttu-id="38f2f-172">A paginação se refere ao número de páginas dentro de um relatório e ao modo como os itens de relatório são organizados nessas páginas.</span><span class="sxs-lookup"><span data-stu-id="38f2f-172">Pagination refers to the number of pages within a report and how report items are arranged on these pages.</span></span> <span data-ttu-id="38f2f-173">A paginação no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] varia, dependendo da extensão de renderização que você usa para exibir e entregar o relatório e das opções de quebra de página e keep-together configuradas para uso do relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-173">Pagination in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] varies depending on the rendering extension you use to view and deliver the report and the page break and keep-together options you configure the report to use.</span></span>  
  
 <span data-ttu-id="38f2f-174">Para desenvolver com êxito um relatório que seja facilmente lido pelos seus usuários bem como que seja otimizado para o processador que pretende usar na entrega do relatório, você deve entender as regras utilizadas para controlar a paginação no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38f2f-174">To successfully design an easy-to-read report for your users that is optimized for the renderer that you plan to use to deliver your report, you need to understand the rules used to control pagination in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="38f2f-175">Os relatórios exportados com o uso dos dados e extensões de renderização de página flexível na memória não são afetados geralmente pela paginação.</span><span class="sxs-lookup"><span data-stu-id="38f2f-175">Reports exported by using the data and soft page rendering extensions are typically not affected by pagination.</span></span> <span data-ttu-id="38f2f-176">Quando você usa uma extensão de renderização de dados, o relatório é renderizado como conjunto de linhas de tabela no formato XML ou CSV.</span><span class="sxs-lookup"><span data-stu-id="38f2f-176">When you use a data rendering extension the report is rendered as tabular rowset in an XML or CSV format.</span></span> <span data-ttu-id="38f2f-177">Para assegurar que os dados de relatório exportados sejam utilizáveis, você deve entender as regras aplicadas para renderizar um conjunto de linhas de tabela mescladas de um relatório.</span><span class="sxs-lookup"><span data-stu-id="38f2f-177">To ensure the exported report data is usable you should understand the rules applied to rendered a flattened tabular rowset from a report.</span></span>  
  
 <span data-ttu-id="38f2f-178">Ao usar uma extensão de renderização de página flexível, como a extensão de renderização HTML, talvez você queira saber qual a aparência do relatório quando impresso e também como ele será renderizado usando um renderizador de página de não flexível como PDF.</span><span class="sxs-lookup"><span data-stu-id="38f2f-178">When you use a soft page rendering extension such as the HTML rendering extension, you might want to know how the report looks printed and also how well it renders using a hard page renderer such as PDF.</span></span> <span data-ttu-id="38f2f-179">Durante a criação ou a atualização de um relatório você pode visualizá-lo e exportá-lo no Construtor de Relatórios e no Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="38f2f-179">During the creation or updating of a report you can preview and export it in Report Builder and Report Designer.</span></span>  
  
 <span data-ttu-id="38f2f-180">Os renderizadores de página de hardware têm o maior impacto no layout do relatório e o tamanho de página física.</span><span class="sxs-lookup"><span data-stu-id="38f2f-180">The hard page renderers have the most impact on report layout and physical page size.</span></span> <span data-ttu-id="38f2f-181">Para saber mais, consulte [Paginação no Reporting Services &#40;Construtor de Relatórios e SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="38f2f-181">To learn more, see [Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md).</span></span>  
  
  
  
##  <a name="how-to-topics"></a><a name="HowTo"></a><span data-ttu-id="38f2f-182">Tópicos de instruções</span><span class="sxs-lookup"><span data-stu-id="38f2f-182">How-To Topics</span></span>  
 <span data-ttu-id="38f2f-183">Esta seção lista procedimentos que mostram a você, passo a passo, como trabalhar com a paginação em relatórios.</span><span class="sxs-lookup"><span data-stu-id="38f2f-183">This section lists procedures that show you, step by step, how to work with pagination in reports.</span></span>  
  
-   [<span data-ttu-id="38f2f-184">Adicionar uma quebra de página &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="38f2f-184">Add a Page Break &#40;Report Builder and SSRS&#41;</span></span>](add-a-page-break-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="38f2f-185">Exibir cabeçalhos de linhas e colunas em várias páginas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="38f2f-185">Display Row and Column Headers on Multiple Pages &#40;Report Builder and SSRS&#41;</span></span>](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="38f2f-186">Adicionar ou remover um cabeçalho ou rodapé de página &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="38f2f-186">Add or Remove a Page Header or Footer &#40;Report Builder and SSRS&#41;</span></span>](add-or-remove-a-page-header-or-footer-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="38f2f-187">Manter os cabeçalhos visíveis ao rolar por um relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="38f2f-187">Keep Headers Visible When Scrolling Through a Report &#40;Report Builder and SSRS&#41;</span></span>](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="38f2f-188">Exibir números de página ou outras propriedades do relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="38f2f-188">Display Page Numbers or Other Report Properties &#40;Report Builder and SSRS&#41;</span></span>](display-page-numbers-or-other-report-properties-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="38f2f-189">Ocultar um cabeçalho ou rodapé de página na primeira ou na última página &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="38f2f-189">Hide a Page Header or Footer on the First or Last Page &#40;Report Builder and SSRS&#41;</span></span>](hide-a-page-header-or-footer-on-the-first-or-last-page-report-builder-and-ssrs.md)  
  
  
  
##  <a name="in-this-section"></a><a name="InThisSection"></a> <span data-ttu-id="38f2f-190">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="38f2f-190">In This Section</span></span>  
 <span data-ttu-id="38f2f-191">Os tópicos a seguir fornecem informações adicionais sobre layout e renderização de página.</span><span class="sxs-lookup"><span data-stu-id="38f2f-191">The following topics provide additional information about page layout and rendering.</span></span>  
  
 [<span data-ttu-id="38f2f-192">Cabeçalhos e rodapés de página &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="38f2f-192">Page Headers and Footers &#40;Report Builder and SSRS&#41;</span></span>](page-headers-and-footers-report-builder-and-ssrs.md)  
 <span data-ttu-id="38f2f-193">Fornece informações sobre como usar cabeçalhos e rodapés em relatórios e como controlar a paginação usando esses recursos.</span><span class="sxs-lookup"><span data-stu-id="38f2f-193">Provides information about using headers and footers in reports and how to control pagination using them.</span></span>  
  
 [<span data-ttu-id="38f2f-194">Controlando quebras de páginas, títulos, colunas e linhas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="38f2f-194">Controlling Page Breaks, Headings, Columns, and Rows &#40;Report Builder and SSRS&#41;</span></span>](controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md)  
 <span data-ttu-id="38f2f-195">Fornece informações sobre como usar quebras de página.</span><span class="sxs-lookup"><span data-stu-id="38f2f-195">Provides information about using page breaks.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="38f2f-196">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38f2f-196">See Also</span></span>  
 <span data-ttu-id="38f2f-197">[Funcionalidade interativa para extensões de renderização de relatório diferentes &#40;Construtor de Relatórios e SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="38f2f-197">[Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md) </span></span>  
 [<span data-ttu-id="38f2f-198">Exportando relatórios &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="38f2f-198">Exporting Reports &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/export-reports-report-builder-and-ssrs.md)  
  
  