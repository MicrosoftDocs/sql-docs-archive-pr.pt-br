---
title: Renderizando dados (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a458fdf9-fb2a-4fee-9fbd-b38f36e91753
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bc2757d308529c8b5a03e206a827fce7028edbfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683415"
---
# <a name="rendering-data-report-builder-and-ssrs"></a><span data-ttu-id="df620-102">Renderizando dados (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="df620-102">Rendering Data (Report Builder and SSRS)</span></span>
  <span data-ttu-id="df620-103">Quando você usa os renderizadores de layout, como HTML, MHTML, Word, Excel, PDF ou Image, os dados e suas organizações permanecem inalterados.</span><span class="sxs-lookup"><span data-stu-id="df620-103">When using layout renderers, such as HTML, MHTML, Word, Excel, PDF or Image, the data and its organization remains unchanged.</span></span> <span data-ttu-id="df620-104">Ao exportar usando um formato de renderizador de dados, como CSV (Comma-Separated Value) ou XML, nenhum elemento de layout visual é renderizado.</span><span class="sxs-lookup"><span data-stu-id="df620-104">When exporting using a data renderer format, such as Comma-Separated Value (CSV) or XML, no visual layout elements are rendered.</span></span> <span data-ttu-id="df620-105">O CSV e o XML aplicam determinadas regras ao relatório e seu conteúdo ao renderizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="df620-105">CSV and XML apply certain rules to the report body and its contents when rendering the report.</span></span> <span data-ttu-id="df620-106">Essas regras determinam como os dados são renderizados nesses formatos.</span><span class="sxs-lookup"><span data-stu-id="df620-106">These rules determine how the data is rendered in these formats.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="df620-107">Você pode usar os renderizadores de dados para:</span><span class="sxs-lookup"><span data-stu-id="df620-107">You can use data renderers to:</span></span>  
  
-   <span data-ttu-id="df620-108">Importar para um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="df620-108">Import to a database.</span></span> <span data-ttu-id="df620-109">O CSV é um formato comum que pode ser facilmente importado por muitos aplicativos de banco de dados, inclusive o SQL Server e o Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="df620-109">CSV is a common format that is easily importable by many database applications including SQL Server and Microsoft Access.</span></span>  
  
-   <span data-ttu-id="df620-110">Importar para o Excel.</span><span class="sxs-lookup"><span data-stu-id="df620-110">Import to Excel.</span></span> <span data-ttu-id="df620-111">Use o renderizador de CSV para exportar seus dados para o Excel sem o layout visual.</span><span class="sxs-lookup"><span data-stu-id="df620-111">Use the CSV renderer to export your data to Excel without the visual layout.</span></span> <span data-ttu-id="df620-112">Depois que os dados estiverem no Excel, você poderá usar as ferramentas padrão do Excel, como gráficos, fórmulas e tabelas dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="df620-112">After your data is in Excel, you can take advantage of standard Excel tools such as charts, formulas, and pivot tables.</span></span>  
  
-   <span data-ttu-id="df620-113">Transformações XSLT.</span><span class="sxs-lookup"><span data-stu-id="df620-113">XSLT transformations.</span></span> <span data-ttu-id="df620-114">Um XSLT pode ser se aplicado à saída do renderizador de XML.</span><span class="sxs-lookup"><span data-stu-id="df620-114">An XSLT can be applied to the output of the XML renderer.</span></span> <span data-ttu-id="df620-115">Essa transformação do lado do servidor é uma técnica poderosa para transformar seus dados virtuais em qualquer formato.</span><span class="sxs-lookup"><span data-stu-id="df620-115">This server-side transformation is a powerful technique to transform your data to virtually any format.</span></span>  
  
-   <span data-ttu-id="df620-116">Troca de dados/EDI.</span><span class="sxs-lookup"><span data-stu-id="df620-116">Data exchange/EDI.</span></span> <span data-ttu-id="df620-117">Um processo externo pode solicitar uma renderização CSV ou XML de um relatório e consumir seus dados.</span><span class="sxs-lookup"><span data-stu-id="df620-117">An external process can request a CSV or XML rendering of a report and consume that data.</span></span>  
  
 <span data-ttu-id="df620-118">Os formatos de renderização de dados são controlados por um conjunto de propriedades diferente dos renderizadores de layout.</span><span class="sxs-lookup"><span data-stu-id="df620-118">Data renderer formats are controlled by a different set of properties than layout renderers.</span></span> <span data-ttu-id="df620-119">A seguir está uma lista de conjuntos de propriedades no painel **Propriedades** que só se aplica aos renderizadores de dados:</span><span class="sxs-lookup"><span data-stu-id="df620-119">The following is a list of properties set in the **Properties** pane that apply only to data renderers:</span></span>  
  
-   <span data-ttu-id="df620-120">A propriedade DataElementOutput controla se um determinado item estará ou não presente nos dados quando forem exportados.</span><span class="sxs-lookup"><span data-stu-id="df620-120">The DataElementOutput property controls whether or not a specific item is present in the data when exported.</span></span>  
  
-   <span data-ttu-id="df620-121">A propriedade DataElementName controla o nome do elemento de dados.</span><span class="sxs-lookup"><span data-stu-id="df620-121">The DataElementName property controls the name of the data element.</span></span> <span data-ttu-id="df620-122">No CSV, isso controla o nome do cabeçalho de coluna CSV.</span><span class="sxs-lookup"><span data-stu-id="df620-122">In CSV, this controls the name of the CSV column header.</span></span> <span data-ttu-id="df620-123">Em XML, isso se transforma no nome do elemento XML ou atributo para o item.</span><span class="sxs-lookup"><span data-stu-id="df620-123">In XML, this becomes the name of the XML element or attribute for the item.</span></span>  
  
-   <span data-ttu-id="df620-124">A propriedade DataElementStyle controla, em XML, se o item de relatório será ou não renderizado como um elemento ou um atributo.</span><span class="sxs-lookup"><span data-stu-id="df620-124">The DataElementStyle property controls, in XML, whether or not the report item is rendered as an element or an attribute.</span></span>  
  
 <span data-ttu-id="df620-125">A opção de exportação CSV salva os dados do relatório como arquivos de texto delimitado por vírgula, sem qualquer formatação.</span><span class="sxs-lookup"><span data-stu-id="df620-125">The CSV export option saves report data as comma-delimited plain text files, without any formatting.</span></span> <span data-ttu-id="df620-126">Por padrão, o arquivo usa uma vírgula (,) para delimitar campos e linhas, mas essa configuração pode ser definida usando as Configurações de Informações de Dispositivo.</span><span class="sxs-lookup"><span data-stu-id="df620-126">By default, the file uses a comma (,) to delimit fields and rows but this setting is configurable using the Device Information Settings.</span></span> <span data-ttu-id="df620-127">O arquivo resultante pode ser aberto em um programa de planilhas como o Office SharePoint Server ou usado como formato de importação por outros programas.</span><span class="sxs-lookup"><span data-stu-id="df620-127">The resulting file can be opened in a spreadsheet program like Office SharePoint Server or used as an import format for other programs.</span></span> <span data-ttu-id="df620-128">O arquivo .csv é aberto em um editor de textos, como Bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="df620-128">The .csv file opens in a text editor such as Notepad.</span></span> <span data-ttu-id="df620-129">Caso seja acessado como URL, o arquivo .csv retorna um tipo MIME de **text/csv**.</span><span class="sxs-lookup"><span data-stu-id="df620-129">If accessed as a URL, the .csv file returns a MIME type of **text/csv**.</span></span> <span data-ttu-id="df620-130">Os arquivos são MIME versão 1.0.</span><span class="sxs-lookup"><span data-stu-id="df620-130">The files are MIME version 1.0.</span></span> <span data-ttu-id="df620-131">Para obter mais informações sobre como renderizar seu relatório no tipo de arquivo CSV, consulte [Exportando para um arquivo CSV &#40;Construtor de Relatórios e SSRS&#41;](../report-builder/exporting-to-a-csv-file-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="df620-131">For more information about rendering your report in the CSV file type, see [Exporting to a CSV File &#40;Report Builder and SSRS&#41;](../report-builder/exporting-to-a-csv-file-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="df620-132">O arquivo XML com opção de exportação dos dados de relatório salva um relatório como arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="df620-132">The XML file with report data export option saves a report as an XML file.</span></span> <span data-ttu-id="df620-133">O esquema XML para o relatório é específico ao relatório.</span><span class="sxs-lookup"><span data-stu-id="df620-133">The XML schema for the report is specific to the report.</span></span> <span data-ttu-id="df620-134">As informações sobre o layout do relatório não são salvas pela opção de exportação XML.</span><span class="sxs-lookup"><span data-stu-id="df620-134">The report layout information is not saved by the XML export option.</span></span> <span data-ttu-id="df620-135">O XML gerado usando essa opção pode ser importado para um banco de dados, usado como mensagem de dados XML ou enviado para um aplicativo personalizado.</span><span class="sxs-lookup"><span data-stu-id="df620-135">The XML generated using this option can be imported into a database, used as an XML data message, or sent to a custom application.</span></span> <span data-ttu-id="df620-136">Para obter mais informações sobre como renderizar seu relatório no tipo de arquivo XML, consulte [Exportando para XML &#40;Construtor de Relatórios e SSRS&#41;](../report-builder/exporting-to-xml-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="df620-136">For more information about rendering your report in the XML file type, see [Exporting to XML &#40;Report Builder and SSRS&#41;](../report-builder/exporting-to-xml-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df620-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="df620-137">See Also</span></span>  
 <span data-ttu-id="df620-138">[Paginação no Reporting Services &#40;Construtor de Relatórios e SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="df620-138">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="df620-139">[Comportamentos de renderização &#40;Construtor de Relatórios e SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="df620-139">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="df620-140">[Funcionalidade interativa para extensões de renderização de relatório diferentes &#40;Construtor de Relatórios e SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="df620-140">[Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md) </span></span>  
 <span data-ttu-id="df620-141">[Renderizando itens de relatório &#40;Construtor de Relatórios e SSRS&#41;](rendering-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="df620-141">[Rendering Report Items &#40;Report Builder and SSRS&#41;](rendering-report-items-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="df620-142">[Lista &#40;Construtor de Relatórios e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="df620-142">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="df620-143">Configurações de informações de dispositivo do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="df620-143">Reporting Services Device Information Settings</span></span>](https://go.microsoft.com/fwlink/?LinkId=102515)  
  
  