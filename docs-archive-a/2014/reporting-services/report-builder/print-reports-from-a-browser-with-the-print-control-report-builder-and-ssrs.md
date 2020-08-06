---
title: Imprimir relatórios em um navegador com o controle de impressão (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 10054250-d915-4bcb-8a1d-26837db4e932
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8dbd4243320dd8d36dafc27ea910755fd3e70a83
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571338"
---
# <a name="print-reports-from-a-browser-with-the-print-control-report-builder-and-ssrs"></a><span data-ttu-id="7bef3-102">Imprimir relatórios em um navegador com o controle de impressão (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="7bef3-102">Print Reports from a Browser with the Print Control (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7bef3-103">Embora um navegador seja o aplicativo cliente mais usado para exibir um relatório, a funcionalidade de impressão do navegador não é ideal para imprimir relatórios.</span><span class="sxs-lookup"><span data-stu-id="7bef3-103">Although a browser is the most common client application used to view a report, browser print functionality is not ideal for printing reports.</span></span> <span data-ttu-id="7bef3-104">A funcionalidade de impressão de um navegador foi projetada para imprimir páginas da Web.</span><span class="sxs-lookup"><span data-stu-id="7bef3-104">Print functionality in a browser is designed for printing Web pages.</span></span> <span data-ttu-id="7bef3-105">Normalmente, as páginas impressas em um navegador incluem todos os elementos visuais presentes em uma página da Web, além das informações de cabeçalho e rodapé que identificam a página ou o site.</span><span class="sxs-lookup"><span data-stu-id="7bef3-105">Typically, pages that you print from a browser include all of the visual elements that are on a Web page, plus header and footer information that identifies the page or Web site.</span></span> <span data-ttu-id="7bef3-106">Imprimir em um navegador imprime o conteúdo da janela atual.</span><span class="sxs-lookup"><span data-stu-id="7bef3-106">Printing from a browser prints the contents of the current window.</span></span> <span data-ttu-id="7bef3-107">Em um relatório com várias páginas, o navegador normalmente imprime a primeira ou menos caso a página do relatório exceda as dimensões de uma página impressa.</span><span class="sxs-lookup"><span data-stu-id="7bef3-107">For a multipage report, the browser prints the first page at most, and possibly less if the report page extends beyond the dimensions of a printed page.</span></span>  
  
 <span data-ttu-id="7bef3-108">Para melhorar a qualidade de impressão dos relatórios exibidos em um navegador e imprimir várias páginas, você pode usar a funcionalidade de impressão do lado do cliente fornecida no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bef3-108">To improve the print quality of reports that you view in a browser and to print multiple pages, you can use the client-side print functionality provided in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="7bef3-109">A impressão do lado do cliente fornece uma caixa de diálogo **Imprimir** padrão, que pode ser usada para selecionar uma impressora, especificar páginas e margens e visualizar o relatório antes da impressão.</span><span class="sxs-lookup"><span data-stu-id="7bef3-109">Client-side printing provides a standard **Print** dialog box that can be used to select a printer, specify pages and margins, and preview the report before you print.</span></span> <span data-ttu-id="7bef3-110">Ela destina-se a ser usada no lugar do comando **Imprimir** no menu **Arquivo** de um navegador.</span><span class="sxs-lookup"><span data-stu-id="7bef3-110">Client-side printing is intended to be used in place of the **Print** command on the browser's **File** menu.</span></span> <span data-ttu-id="7bef3-111">Quando você usa a impressão de cliente, o relatório é impresso como foi criado, sem os elementos adicionais exibidos em impressões de páginas da Web.</span><span class="sxs-lookup"><span data-stu-id="7bef3-111">When you use client-side printing, the report is printed as it was designed, without the extra elements you see in a Web page print out.</span></span>  
  
 <span data-ttu-id="7bef3-112">Para usar a impressão do lado do cliente, você precisa instalar um controle ActiveX do [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bef3-112">To use client-side printing, you need to install a [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX control.</span></span> <span data-ttu-id="7bef3-113">Para obter mais informações, consulte [Habilitar e desabilitar a impressão do lado do cliente para Reporting Services](../report-server/enable-and-disable-client-side-printing-for-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="7bef3-113">For more information, see [Enable and Disable Client-Side Printing for Reporting Services](../report-server/enable-and-disable-client-side-printing-for-reporting-services.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="print-options"></a><span data-ttu-id="7bef3-114">Opções de impressão</span><span class="sxs-lookup"><span data-stu-id="7bef3-114">Print Options</span></span>  
 <span data-ttu-id="7bef3-115">Para configurar as propriedades de impressão do relatório, na caixa de diálogo **Imprimir** , clique no botão **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="7bef3-115">To configure print properties for your report, in the **Print** dialog box, click the **Properties** button.</span></span> <span data-ttu-id="7bef3-116">O**tamanho do papel** é determinado pela altura e pela largura padrão do tamanho da página do relatório, conforme estabelecido na definição do relatório.</span><span class="sxs-lookup"><span data-stu-id="7bef3-116">**Paper size** is determined by the default height and width of the report page size as defined in the report definition.</span></span> <span data-ttu-id="7bef3-117">Os valores disponíveis dependem do tipo de impressora e de seus recursos.</span><span class="sxs-lookup"><span data-stu-id="7bef3-117">The available values are dependent on the printer type and its capabilities.</span></span> <span data-ttu-id="7bef3-118">Largura e altura usam valores padrão, conforme a determinação dos drivers de impressão configurados no computador.</span><span class="sxs-lookup"><span data-stu-id="7bef3-118">Width and height display default values as determined by the print drivers that are configured on the computer.</span></span> <span data-ttu-id="7bef3-119">Alterar esses valores faz com que o relatório seja impresso usando as novas dimensões.</span><span class="sxs-lookup"><span data-stu-id="7bef3-119">Changing these values causes the report to print using the new dimensions.</span></span> <span data-ttu-id="7bef3-120">A largura e a altura da página são determinadas pela **Orientação**, que é definida como **Retrato** ou **Paisagem**.</span><span class="sxs-lookup"><span data-stu-id="7bef3-120">Page width and height are each determined by **Orientation**, which is set to either **Portrait** or **Landscape**.</span></span> <span data-ttu-id="7bef3-121">A orientação padrão exibida depende da largura e da altura da página do relatório.</span><span class="sxs-lookup"><span data-stu-id="7bef3-121">The default orientation displayed is dependent on the page width and page height of the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7bef3-122">A caixa de diálogo **Imprimir** e as configurações de impressora padrão para largura, altura e orientação de página são determinadas pela definição do relatório.</span><span class="sxs-lookup"><span data-stu-id="7bef3-122">The **Print** dialog box and the default printer settings for width, height, and page orientation are determined by the report definition.</span></span>  
  
### <a name="print-preview"></a><span data-ttu-id="7bef3-123">Visualizar Impressão</span><span class="sxs-lookup"><span data-stu-id="7bef3-123">Print Preview</span></span>  
 <span data-ttu-id="7bef3-124">Para visualizar um relatório, na caixa de diálogo **Imprimir** , clique no botão **Visualizar** .</span><span class="sxs-lookup"><span data-stu-id="7bef3-124">To preview a report, in the **Print** dialog box, click the **Preview** button.</span></span> <span data-ttu-id="7bef3-125">Clicar na visualização abre a primeira página do relatório em uma janela de visualização separada.</span><span class="sxs-lookup"><span data-stu-id="7bef3-125">Clicking preview opens the first page of the report in a separate preview window.</span></span> <span data-ttu-id="7bef3-126">Páginas adicionais ficam disponíveis quando o relatório é processado no servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="7bef3-126">Additional pages are made available as the report is rendered on the report server.</span></span> <span data-ttu-id="7bef3-127">Um relatório visualizado é processado em formato EMF.</span><span class="sxs-lookup"><span data-stu-id="7bef3-127">A previewed report is rendered in EMF format.</span></span> <span data-ttu-id="7bef3-128">É possível navegar até a página anterior ou a próxima chegando até a última, e o botão **Avançar** é desabilitado.</span><span class="sxs-lookup"><span data-stu-id="7bef3-128">You can navigate to the previous or next page until the last page is reached, and the **Next** button is disabled.</span></span>  
  
### <a name="adjusting-print-margins"></a><span data-ttu-id="7bef3-129">Ajustando margens de impressão</span><span class="sxs-lookup"><span data-stu-id="7bef3-129">Adjusting Print Margins</span></span>  
 <span data-ttu-id="7bef3-130">É possível modificar as margens de impressão no relatório EMF processado antes de imprimi-lo.</span><span class="sxs-lookup"><span data-stu-id="7bef3-130">You can modify the print margins in the rendered EMF report prior to printing the report.</span></span> <span data-ttu-id="7bef3-131">Para isso, na caixa de diálogo **Imprimir** , clique no botão **Visualizar** .</span><span class="sxs-lookup"><span data-stu-id="7bef3-131">To do this, in the **Print** dialog box, click the **Preview** button.</span></span> <span data-ttu-id="7bef3-132">Na parte superior da página de visualização, clique no botão **Margens** .</span><span class="sxs-lookup"><span data-stu-id="7bef3-132">At the top of the preview page, click the **Margins** button.</span></span> <span data-ttu-id="7bef3-133">A caixa de diálogo Margens é exibida.</span><span class="sxs-lookup"><span data-stu-id="7bef3-133">The Margins dialog box is displayed.</span></span> <span data-ttu-id="7bef3-134">Configure as margens superior, inferior, direita e esquerda conforme desejado.</span><span class="sxs-lookup"><span data-stu-id="7bef3-134">Configure the top, bottom, right, and left margins as desired.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)] <span data-ttu-id="7bef3-135">A caixa de diálogo é fechada, e as configurações são armazenadas para a renderização da visualização e da impressão.</span><span class="sxs-lookup"><span data-stu-id="7bef3-135">The dialog box closes and the settings are stored for rendering preview and printing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bef3-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7bef3-136">See Also</span></span>  
 <span data-ttu-id="7bef3-137">[Imprimir relatórios &#40;Construtor de Relatórios e SSRS&#41;](print-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7bef3-137">[Print Reports &#40;Report Builder and SSRS&#41;](print-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7bef3-138">Imprimir um relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7bef3-138">Print a Report &#40;Report Builder and SSRS&#41;</span></span>](print-a-report-report-builder-and-ssrs.md)  
  
  