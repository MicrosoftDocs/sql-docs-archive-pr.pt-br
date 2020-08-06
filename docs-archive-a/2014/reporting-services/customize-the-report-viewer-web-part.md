---
title: Personalizar a Web Part do Visualizador de relatórios | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SharePoint integration [Reporting Services], viewing reports
- Web Parts [Reporting Services]
- Report Viewer Web Part [Reporting Services]
ms.assetid: 086d6546-7299-41bc-bca9-083a15a53679
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bab401254cbe49f1239b4dc983d6a4ad68e077e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685457"
---
# <a name="customize-the-report-viewer-web-part"></a><span data-ttu-id="5af01-102">Personalizar a Web Part do Visualizador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="5af01-102">Customize the Report Viewer Web Part</span></span>
  <span data-ttu-id="5af01-103">Você pode usar a Web Part do Visualizador de Relatórios para exibir relatórios executados em um servidor de relatório configurado para integração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5af01-103">You can use the Report Viewer Web Part to view reports that run on a report server that is configured for SharePoint integration.</span></span> <span data-ttu-id="5af01-104">Os relatórios que você pode exibir incluem arquivos de definição de relatório (.rdl) e relatórios do Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="5af01-104">Reports that you can display include report definition (.rdl) files and Report Builder reports.</span></span> <span data-ttu-id="5af01-105">Os relatórios são abertos na Web Part do Visualizador de Relatórios em uma nova página automaticamente, mas você também pode adicionar uma Web Part do Visualizador de Relatórios a uma página ou site existente se quiser que um determinado relatório sempre esteja visível nessa página.</span><span class="sxs-lookup"><span data-stu-id="5af01-105">Reports open in the Report Viewer Web Part in a new page automatically, but you can also add a Report Viewer Web Part to an existing Web page or site if you want a particular report to always be visible on that page.</span></span>  
  
 <span data-ttu-id="5af01-106">Você pode personalizar a Web Part do Visualizador de Relatórios das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="5af01-106">You can customize the Report Viewer Web Part in the following ways:</span></span>  
  
-   <span data-ttu-id="5af01-107">Altere a aparência da Web Part definindo propriedades.</span><span class="sxs-lookup"><span data-stu-id="5af01-107">Change the appearance of the Web Part by setting properties.</span></span>  
  
-   <span data-ttu-id="5af01-108">Escolha quais recursos de relatórios interativos estão disponíveis na barra de ferramentas do relatório.</span><span class="sxs-lookup"><span data-stu-id="5af01-108">Choose which interactive reporting features are available on the report toolbar.</span></span>  
  
-   <span data-ttu-id="5af01-109">Especifique quais áreas de exibição estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5af01-109">Specify which view areas are available.</span></span> <span data-ttu-id="5af01-110">A Web Part do Visualizador de Relatórios tem uma área de exibição de relatório, uma área de Parâmetros e uma área de Credenciais.</span><span class="sxs-lookup"><span data-stu-id="5af01-110">The Report Viewer Web Part has a report view area, a Parameters area, and a Credentials area.</span></span>  
  
 <span data-ttu-id="5af01-111">Você não pode ampliar a Web Part do Visualizador de Relatórios para oferecer suporte a diferentes tipos de arquivos e não pode substituir a barra de ferramentas do relatório por uma barra de ferramentas personalizada nem adicionar nova funcionalidade à barra de ferramentas existente.</span><span class="sxs-lookup"><span data-stu-id="5af01-111">You cannot extend the Report Viewer Web Part to support different file types, and you cannot replace the report toolbar with a custom toolbar or add new functionality to the existing toolbar.</span></span> <span data-ttu-id="5af01-112">Se você precisar de personalização de recursos padrão, deverá criar uma Web Part personalizada.</span><span class="sxs-lookup"><span data-stu-id="5af01-112">If you require customization of the standard features, you should create a custom Web Part.</span></span>  
  
## <a name="setting-web-part-properties"></a><span data-ttu-id="5af01-113">Definindo propriedades da Web Part</span><span class="sxs-lookup"><span data-stu-id="5af01-113">Setting Web Part Properties</span></span>  
 <span data-ttu-id="5af01-114">Uma Web Part tem propriedades personalizadas usadas para configurar a funcionalidade específica.</span><span class="sxs-lookup"><span data-stu-id="5af01-114">A Web Part has custom properties that are used to configure specific functionality.</span></span> <span data-ttu-id="5af01-115">Uma Web Part também tem propriedades comuns que são padrão para toda Web Part.</span><span class="sxs-lookup"><span data-stu-id="5af01-115">A Web Part also has common properties that are standard for every Web Part.</span></span>  
  
### <a name="change-default-properties"></a><span data-ttu-id="5af01-116">Alterar propriedades padrão</span><span class="sxs-lookup"><span data-stu-id="5af01-116">Change Default Properties</span></span>  
 <span data-ttu-id="5af01-117">A Web Part do Visualizador de Relatórios tem propriedades padrão idealmente adequadas para abrir relatórios sob demanda a partir de uma biblioteca ou pasta.</span><span class="sxs-lookup"><span data-stu-id="5af01-117">The Report Viewer Web Part has default properties that are ideally suited for opening reports on demand from a library or folder.</span></span> <span data-ttu-id="5af01-118">Por padrão, todos os controles disponíveis são exibidos na barra de ferramentas. Altura e largura são definidos para usarem todo o espaço disponível na página da Web.</span><span class="sxs-lookup"><span data-stu-id="5af01-118">By default, all available controls are displayed on the toolbar, and height and width are set to use all of the available space on the Web page.</span></span> <span data-ttu-id="5af01-119">Se você quiser modificar as propriedades padrão, poderá personalizar a Web Part por meio **das configurações do site**.</span><span class="sxs-lookup"><span data-stu-id="5af01-119">If you want to modify the default properties, you can customize the Web Part through **Site Settings**.</span></span>  
  
1.  <span data-ttu-id="5af01-120">No menu **Ações do Site** , clique em **Configurações de Site**.</span><span class="sxs-lookup"><span data-stu-id="5af01-120">On the **Site Actions** menu, click **Site Settings**.</span></span>  
  
2.  <span data-ttu-id="5af01-121">Em galerias, clique em **Web Parts**.</span><span class="sxs-lookup"><span data-stu-id="5af01-121">Under Galleries, click **Web parts**.</span></span>  
  
3.  <span data-ttu-id="5af01-122">Clique em **ReportViewer.dwp**.</span><span class="sxs-lookup"><span data-stu-id="5af01-122">Click **ReportViewer.dwp**.</span></span>  
  
4.  <span data-ttu-id="5af01-123">Abra o painel de ferramentas e defina as propriedades que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="5af01-123">Open the tool pane and set the properties you want to use.</span></span>  
  
### <a name="customize-an-embedded-report-viewer-in-a-web-page"></a><span data-ttu-id="5af01-124">Personalizar um Visualizador de Relatórios inserido em uma página da Web</span><span class="sxs-lookup"><span data-stu-id="5af01-124">Customize an Embedded Report Viewer in a Web Page</span></span>  
 <span data-ttu-id="5af01-125">Você pode definir as propriedades para ajustar o Visualizador de Relatórios em uma página da Web.</span><span class="sxs-lookup"><span data-stu-id="5af01-125">You can set properties to make the Report Viewer fit within a Web page.</span></span> <span data-ttu-id="5af01-126">O Visualizador de Relatórios pode usar o mesmo estilo e cores que a página que o contém.</span><span class="sxs-lookup"><span data-stu-id="5af01-126">The report viewer can use the same style and colors as the page that contains it.</span></span> <span data-ttu-id="5af01-127">Você pode ocultar toda ou parte da barra de ferramentas, o mapa do documento e a área de parâmetros para maximizar a área de exibição do relatório no espaço alocado.</span><span class="sxs-lookup"><span data-stu-id="5af01-127">You can hide all or part of the toolbar, document map, and parameters area to maximize the report viewing area within the allocated space.</span></span> <span data-ttu-id="5af01-128">O relatório sempre usa os estilos definidos para ele quando ele foi criado; você não pode personalizar a aparência do relatório depois de publicá-lo em uma biblioteca do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5af01-128">The report always uses the styles that are defined for it when it was created; you cannot customize report appearance after it is published to a SharePoint library.</span></span>  
  
 <span data-ttu-id="5af01-129">Se você estiver inserindo a Web Part do Visualizador de relatórios em uma página da Web, defina a propriedade **URL do relatório** para um relatório específico.</span><span class="sxs-lookup"><span data-stu-id="5af01-129">If you are embedding the Report Viewer Web Part in a Web page, you should set the **Report URL** property to a specific report.</span></span> <span data-ttu-id="5af01-130">Se não estiver, o Visualizador de Relatórios exibirá instruções para vincular a um relatório.</span><span class="sxs-lookup"><span data-stu-id="5af01-130">If you do not, the Report Viewer will display instructions for linking to a report.</span></span> <span data-ttu-id="5af01-131">Você não pode personalizar nem remover as instruções.</span><span class="sxs-lookup"><span data-stu-id="5af01-131">You cannot customize or remove the instructions.</span></span>  
  
### <a name="custom-properties-of-the-report-viewer-web-part"></a><span data-ttu-id="5af01-132">Propriedades personalizadas da Web Part do Visualizador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="5af01-132">Custom Properties of the Report Viewer Web Part</span></span>  
 <span data-ttu-id="5af01-133">Ao definir propriedades personalizadas, verifique se algumas propriedades são usadas somente quando a Web Part do Visualizador de Relatórios está inserida em uma página.</span><span class="sxs-lookup"><span data-stu-id="5af01-133">When setting custom properties, be aware that some properties are used only when the Report Viewer Web Part is embedded in a page.</span></span> <span data-ttu-id="5af01-134">Os exemplos incluem Título, Altura, Largura, Tipo de cromado e Zona.</span><span class="sxs-lookup"><span data-stu-id="5af01-134">Examples include Title, Height, Width, Chrome type, and Zone.</span></span> <span data-ttu-id="5af01-135">Outras propriedades, como as configurações da Barra de Ferramentas e Parâmetros, são usadas independentemente de o Visualizador de Relatórios aparecer em uma página ou abrir um relatório em modo de página inteira.</span><span class="sxs-lookup"><span data-stu-id="5af01-135">Other properties, such as Toolbar settings and Parameters settings, are used regardless of whether the Report Viewer appears within a page or opens a report in full-page mode.</span></span>  
  
 <span data-ttu-id="5af01-136">As propriedades personalizadas da Web Part do Visualizador de Relatórios são listadas a seguir.</span><span class="sxs-lookup"><span data-stu-id="5af01-136">The custom properties of the Report Viewer Web Part are listed below.</span></span>  
  
|<span data-ttu-id="5af01-137">Propriedade</span><span class="sxs-lookup"><span data-stu-id="5af01-137">Property</span></span>|<span data-ttu-id="5af01-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="5af01-138">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="5af01-139">Relatório</span><span class="sxs-lookup"><span data-stu-id="5af01-139">Report</span></span>|<span data-ttu-id="5af01-140">Um caminho totalmente qualificado para um relatório que esteja no site do SharePoint atual ou em um site no mesmo aplicativo Web ou farm.</span><span class="sxs-lookup"><span data-stu-id="5af01-140">A fully-qualified path to a report that is on the current SharePoint site, or on a site within the same Web application or farm.</span></span> <span data-ttu-id="5af01-141">Para obter os melhores resultados ao definir propriedades adicionais, clique em Aplicar depois de especificar a URL do relatório.</span><span class="sxs-lookup"><span data-stu-id="5af01-141">For best results when setting additional properties, click Apply after you specify the report URL.</span></span>|  
|<span data-ttu-id="5af01-142">Destino do Hiperlink</span><span class="sxs-lookup"><span data-stu-id="5af01-142">Hyperlink Target</span></span>|<span data-ttu-id="5af01-143">HTML padrão que especifica o quadro de destino para exibir conteúdo vinculado no documento atual.</span><span class="sxs-lookup"><span data-stu-id="5af01-143">Standard HTML that specifies the target frame for displaying linked content within the current document.</span></span> <span data-ttu-id="5af01-144">Para relatórios que incluem hiperlinks para sites externos, você pode especificar se um documento de destino substitui o relatório existente dentro da janela atual ou se ele é aberto em uma nova janela do navegador.</span><span class="sxs-lookup"><span data-stu-id="5af01-144">For reports that include hyperlinks to external Web sites, you can specify whether a target document replaces the existing report within the current window, or opens in a new browser window.</span></span> <span data-ttu-id="5af01-145">Os valores válidos incluem `_Top`, `_Blank` e `_Self`.</span><span class="sxs-lookup"><span data-stu-id="5af01-145">Valid values include `_Top`, `_Blank`, and `_Self`.</span></span> <span data-ttu-id="5af01-146">`_Top` usa a janela atual, `_Blank` carrega o documento em uma nova janela do navegador e `_Self` abre o documento dentro do quadro atual.</span><span class="sxs-lookup"><span data-stu-id="5af01-146">`_Top` uses the current window, `_Blank` loads the document in a new browser window, and `_Self` opens the document within the current frame.</span></span> <span data-ttu-id="5af01-147">Embora `_Parent` seja um valor válido para o atributo Target em HTML, ele não deve ser usado para uma Web Part do Visualizador de Relatórios inserida em uma página.</span><span class="sxs-lookup"><span data-stu-id="5af01-147">Although `_Parent` is a valid value for the Target attribute in HTML, do not use it for a Report Viewer Web Part that is embedded in a page.</span></span>|  
|<span data-ttu-id="5af01-148">Gerar automaticamente o título da Web Part</span><span class="sxs-lookup"><span data-stu-id="5af01-148">Auto-Generate Web Part Title</span></span>|<span data-ttu-id="5af01-149">Um título gerado que inclui o nome da Web Part do Visualizador de Relatórios e o nome do relatório, separados por um traço.</span><span class="sxs-lookup"><span data-stu-id="5af01-149">A generated title that includes the name of the Report Viewer Web Part plus the name of the report, separated by a dash.</span></span> <span data-ttu-id="5af01-150">Se o relatório não tiver um título, será usado o nome do arquivo do relatório.</span><span class="sxs-lookup"><span data-stu-id="5af01-150">If the report does not have a title, the report file name is used.</span></span> <span data-ttu-id="5af01-151">O título fica visível quando você adiciona uma Web Part a uma página.</span><span class="sxs-lookup"><span data-stu-id="5af01-151">The title is visible when you add a Web Part to a page.</span></span> <span data-ttu-id="5af01-152">Se essa caixa de seleção estiver marcada, o título será gerado sempre que a página for atualizada.</span><span class="sxs-lookup"><span data-stu-id="5af01-152">If this check box is selected, the title will be generated each time the page is refreshed.</span></span>|  
|<span data-ttu-id="5af01-153">Gerar automaticamente o link de detalhes da Web Part</span><span class="sxs-lookup"><span data-stu-id="5af01-153">Auto-Generate Web Part Title Detail Link</span></span>|<span data-ttu-id="5af01-154">Um hiperlink gerado que é exibido acima da Web Part.</span><span class="sxs-lookup"><span data-stu-id="5af01-154">A generated hyperlink that appears above the Web Part.</span></span> <span data-ttu-id="5af01-155">Você pode clicar no link para abrir o relatório em uma nova página, em modo de página inteira.</span><span class="sxs-lookup"><span data-stu-id="5af01-155">You can click the link to open the report in a new page, in full-page mode.</span></span>|  
|<span data-ttu-id="5af01-156">Mostrar item de menu do construtor de relatórios</span><span class="sxs-lookup"><span data-stu-id="5af01-156">Show report builder menu item</span></span>|<span data-ttu-id="5af01-157">Mostra ou oculta a opção de menu **Ações** para abrir o Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="5af01-157">Shows or hides the **Actions** menu option to open Report Builder.</span></span>|  
|<span data-ttu-id="5af01-158">Mostrar item de menu de assinatura</span><span class="sxs-lookup"><span data-stu-id="5af01-158">Show subscription menu item</span></span>|<span data-ttu-id="5af01-159">Mostra ou oculta a opção de menu **Ações** para criar uma assinatura para o relatório.</span><span class="sxs-lookup"><span data-stu-id="5af01-159">Shows or hides the **Actions** menu option to create a subscription for the report.</span></span>|  
|<span data-ttu-id="5af01-160">Mostrar item do menu imprimir</span><span class="sxs-lookup"><span data-stu-id="5af01-160">Show print menu item</span></span>|<span data-ttu-id="5af01-161">Mostra ou oculta a opção de menu **Ações** para imprimir o relatório.</span><span class="sxs-lookup"><span data-stu-id="5af01-161">Shows or hides the **Actions** menu option to print the report.</span></span>|  
|<span data-ttu-id="5af01-162">Mostrar item do menu exportar</span><span class="sxs-lookup"><span data-stu-id="5af01-162">Show export menu item</span></span>|<span data-ttu-id="5af01-163">Mostra ou oculta a opção de menu **Ações** para exportar o relatório.</span><span class="sxs-lookup"><span data-stu-id="5af01-163">Shows or hides the **Actions** menu option to export the report.</span></span>|  
|<span data-ttu-id="5af01-164">Mostrar botão atualizar</span><span class="sxs-lookup"><span data-stu-id="5af01-164">Show refresh button</span></span>|<span data-ttu-id="5af01-165">Mostra ou oculta o botão atualizar na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="5af01-165">Shows or hides the refresh button on the toolbar.</span></span>|  
|<span data-ttu-id="5af01-166">Mostrar controles de navegação de página</span><span class="sxs-lookup"><span data-stu-id="5af01-166">Show page navigation controls</span></span>|<span data-ttu-id="5af01-167">Mostra ou oculta os botões de navegação de relatório na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="5af01-167">Shows or hides the report navigation buttons on the toolbar.</span></span> <span data-ttu-id="5af01-168">Esta opção altera a visibilidade de todos os controles de navegação.</span><span class="sxs-lookup"><span data-stu-id="5af01-168">This option changes the visibility of all the navigation controls.</span></span>|  
|<span data-ttu-id="5af01-169">Mostrar botão voltar</span><span class="sxs-lookup"><span data-stu-id="5af01-169">Show back button</span></span>|<span data-ttu-id="5af01-170">Mostra ou oculta o botão voltar na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="5af01-170">Shows or hides the back button on the toolbar.</span></span>|  
|<span data-ttu-id="5af01-171">Mostrar controles de localização</span><span class="sxs-lookup"><span data-stu-id="5af01-171">Show find controls</span></span>|<span data-ttu-id="5af01-172">Mostra ou oculta os controles de localização na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="5af01-172">Shows or hides the find controls on the toolbar.</span></span> <span data-ttu-id="5af01-173">Esses controles permitem que um usuário procure texto no relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="5af01-173">The find controls allow a user to search for text in the rendered report.</span></span> <span data-ttu-id="5af01-174">Esta opção altera a visibilidade de todos os controles de localização.</span><span class="sxs-lookup"><span data-stu-id="5af01-174">This option changes the visibility of all the find controls.</span></span>|  
|<span data-ttu-id="5af01-175">Mostrar controle de zoom</span><span class="sxs-lookup"><span data-stu-id="5af01-175">Show zoom control</span></span>|<span data-ttu-id="5af01-176">Mostra ou oculta o controle de zoom na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="5af01-176">Shows or hides the zoom control on the toolbar.</span></span>|  
|<span data-ttu-id="5af01-177">Mostrar botão feed ATOM</span><span class="sxs-lookup"><span data-stu-id="5af01-177">Show ATOM feed button</span></span>|<span data-ttu-id="5af01-178">Mostra ou oculta o botão feed ATOM na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="5af01-178">Shows or hides the ATOM feed button on the toolbar.</span></span><br /><br /> <span data-ttu-id="5af01-179">![htmlviewer_datafeed](media/htmlviewer-datafeed.gif "htmlviewer_datafeed")</span><span class="sxs-lookup"><span data-stu-id="5af01-179">![htmlviewer_datafeed](media/htmlviewer-datafeed.gif "htmlviewer_datafeed")</span></span>|  
|<span data-ttu-id="5af01-180">Localização da Barra de Ferramentas</span><span class="sxs-lookup"><span data-stu-id="5af01-180">ToolBar location</span></span>|<span data-ttu-id="5af01-181">Determina o local da barra de ferramentas dentro do visualizador de relatórios.</span><span class="sxs-lookup"><span data-stu-id="5af01-181">Determines the location of the toolbar within the report viewer.</span></span> <span data-ttu-id="5af01-182">Os valores válidos incluem `Top` e `Bottom`.</span><span class="sxs-lookup"><span data-stu-id="5af01-182">Valid values include `Top` and `Bottom`.</span></span>|  
|<span data-ttu-id="5af01-183">Área de prompt</span><span class="sxs-lookup"><span data-stu-id="5af01-183">Prompt area</span></span>|<span data-ttu-id="5af01-184">Os valores válidos incluem `Displayed`, `Collapsed` e `Hidden`.</span><span class="sxs-lookup"><span data-stu-id="5af01-184">Valid values include `Displayed`, `Collapsed`, and `Hidden`.</span></span> <span data-ttu-id="5af01-185">`Displayed` é exibido na área Parâmetros para os relatórios que incluem valores com parâmetros e que exigem a entrada do usuário antes de o relatório ser executado.</span><span class="sxs-lookup"><span data-stu-id="5af01-185">`Displayed` displays the Parameters area for reports that include parameterized values and that require user input before the report will run.</span></span> <span data-ttu-id="5af01-186">Use `Hidden` se todos os parâmetros do relatório estiverem especificados e você não quiser que a área de parâmetros fique visível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="5af01-186">Use `Hidden` if all of the report parameters are specified and you do not want the parameters area to be visible to users.</span></span>|  
|<span data-ttu-id="5af01-187">Largura da Área de Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5af01-187">Parameters Area Width</span></span>|<span data-ttu-id="5af01-188">Você pode escolher a medida e o valor.</span><span class="sxs-lookup"><span data-stu-id="5af01-188">You can choose the measurement and value.</span></span> <span data-ttu-id="5af01-189">O padrão é 200 pixels.</span><span class="sxs-lookup"><span data-stu-id="5af01-189">The default is 200 pixels.</span></span> <span data-ttu-id="5af01-190">A única exigência desta propriedade é que o valor seja maior do que zero.</span><span class="sxs-lookup"><span data-stu-id="5af01-190">The only requirement for this property is that it is greater than zero.</span></span>|  
|<span data-ttu-id="5af01-191">Mapa do documento</span><span class="sxs-lookup"><span data-stu-id="5af01-191">Document Map</span></span>|<span data-ttu-id="5af01-192">Um controle de navegação definido em um relatório e usado para fornecer acesso com um único clique a seções específicas do relatório.</span><span class="sxs-lookup"><span data-stu-id="5af01-192">A report navigation control that is defined in the report and used to provide one-click access to specific sections of a report.</span></span> <span data-ttu-id="5af01-193">Ele está disponível em relatórios HTML.</span><span class="sxs-lookup"><span data-stu-id="5af01-193">It is available in HTML reports.</span></span> <span data-ttu-id="5af01-194">O mapa do documento é exibido em uma área recolhível ao lado da área de exibição do relatório.</span><span class="sxs-lookup"><span data-stu-id="5af01-194">The document map is displayed in a collapsible area next to the report viewing area.</span></span> <span data-ttu-id="5af01-195">Os valores válidos incluem `Displayed`, `Collapsed` e `Hidden`.</span><span class="sxs-lookup"><span data-stu-id="5af01-195">Valid values include `Displayed`, `Collapsed`, and `Hidden`.</span></span> <span data-ttu-id="5af01-196">Se um mapa do documento estiver definido para um relatório, a área será expandida por padrão a menos que seja marcada como oculta ou recolhida nas propriedades da Web Part.</span><span class="sxs-lookup"><span data-stu-id="5af01-196">If a document map is defined for a report, the area is expanded by default unless marked as hidden or collapsed in the Web Part properties.</span></span> <span data-ttu-id="5af01-197">Se o mapa do documento estiver recolhido, você poderá clicar na seta para expandi-lo.</span><span class="sxs-lookup"><span data-stu-id="5af01-197">If the document map is collapsed, you can click the arrow to expand it.</span></span>|  
|<span data-ttu-id="5af01-198">Largura da Área de Mapa do Documento</span><span class="sxs-lookup"><span data-stu-id="5af01-198">Document Map Area Width</span></span>|<span data-ttu-id="5af01-199">Você pode escolher a medida e o valor.</span><span class="sxs-lookup"><span data-stu-id="5af01-199">You can choose the measurement and value.</span></span> <span data-ttu-id="5af01-200">O padrão é 200 pixels.</span><span class="sxs-lookup"><span data-stu-id="5af01-200">The default is 200 pixels.</span></span> <span data-ttu-id="5af01-201">A única exigência desta propriedade é que o valor seja maior do que zero.</span><span class="sxs-lookup"><span data-stu-id="5af01-201">The only requirement for this property is that it is greater than zero.</span></span>|  
|<span data-ttu-id="5af01-202">Carregar Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5af01-202">Load Parameters</span></span>|<span data-ttu-id="5af01-203">Recupera as propriedades dos parâmetros do relatório.</span><span class="sxs-lookup"><span data-stu-id="5af01-203">Retrieve parameter properties for the report.</span></span> <span data-ttu-id="5af01-204">Nem todos os relatórios têm parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5af01-204">Not all reports have parameters.</span></span> <span data-ttu-id="5af01-205">Se o relatório não tiver parâmetros, nenhum valor será retornado.</span><span class="sxs-lookup"><span data-stu-id="5af01-205">If the report does not have parameters, no values will be returned.</span></span> <span data-ttu-id="5af01-206">Se você estiver definindo propriedades de um relatório recém-carregado, poderá receber um erro indicando que a conexão da fonte de dados foi excluída.</span><span class="sxs-lookup"><span data-stu-id="5af01-206">If you are setting properties for a report that you just uploaded, you might get an error indicating that the data source connection has been deleted.</span></span> <span data-ttu-id="5af01-207">Se isso acontecer, redefina a conexão e termine de definir as propriedades dos parâmetros depois que a conexão for especificada.</span><span class="sxs-lookup"><span data-stu-id="5af01-207">If this occurs, reset the connection and then finish setting parameter properties after the connection is specified.</span></span> <span data-ttu-id="5af01-208">Para obter mais informações sobre como definir a conexão, consulte [Criar e gerenciar fontes de dados compartilhadas &#40;Reporting Services no modo integrado do SharePoint&#41;](../../2014/reporting-services/create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span><span class="sxs-lookup"><span data-stu-id="5af01-208">For more information about how to set the connection, see [Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../../2014/reporting-services/create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span></span><br /><br /> <span data-ttu-id="5af01-209">Para obter os melhores resultados, clique em **Aplicar** antes de clicar em Carregar Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5af01-209">For best results, click **Apply** before clicking Load Parameters.</span></span><br /><br /> <span data-ttu-id="5af01-210">Depois de carregar as propriedades dos parâmetros, você poderá defini-las da mesma maneira como faria nas páginas de propriedades de parâmetros do relatório.</span><span class="sxs-lookup"><span data-stu-id="5af01-210">After you load parameter properties, you can set them the same way you would in the parameter property pages of the report.</span></span> <span data-ttu-id="5af01-211">Para obter mais informações sobre como definir parâmetros, consulte [Definir parâmetros em um relatório publicado &#40;Reporting Services no modo integrado do SharePoint&#41;](report-design/set-parameters-on-a-published-report-sharepoint-integrated-mode.md).</span><span class="sxs-lookup"><span data-stu-id="5af01-211">For more information about how to set parameters, see [Set Parameters on a Published Report &#40;Reporting Services in SharePoint Integrated Mode&#41;](report-design/set-parameters-on-a-published-report-sharepoint-integrated-mode.md).</span></span>|  
  
## <a name="customizing-the-toolbar"></a><span data-ttu-id="5af01-212">Personalizando a caixa de ferramentas</span><span class="sxs-lookup"><span data-stu-id="5af01-212">Customizing the Toolbar</span></span>  
 <span data-ttu-id="5af01-213">A barra de ferramentas é exibida abaixo do título e abrange a parte superior do relatório.</span><span class="sxs-lookup"><span data-stu-id="5af01-213">The toolbar appears beneath the title and extends across the top of the report.</span></span> <span data-ttu-id="5af01-214">Ela proporciona o menu **Ações** , a navegação de página para relatórios paginados, atualização e zoom.</span><span class="sxs-lookup"><span data-stu-id="5af01-214">The toolbar provides an **Actions** menu, page navigation for paginated reports, refresh, and zoom.</span></span> <span data-ttu-id="5af01-215">Também inclui um controle de mapa do documento para relatórios que têm um mapa do documento.</span><span class="sxs-lookup"><span data-stu-id="5af01-215">It includes a document map control for reports that have a document map.</span></span> <span data-ttu-id="5af01-216">O menu **Ações** inclui comandos para exportar o relatório, procurar texto ou números no relatório, imprimir o relatório e abrir o relatório no Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="5af01-216">The **Actions** menu includes commands for exporting the report, searching for text or numbers within a report, printing the report, and, opening the report in Report Builder.</span></span>  
  
 <span data-ttu-id="5af01-217">Não é possível adicionar novos comandos ao menu  **Ações** , mas é possível personalizá-lo alterando as opções que ficam visíveis para os usuários.</span><span class="sxs-lookup"><span data-stu-id="5af01-217">You cannot add new commands to the  **Actions** menu but you can customize it by changing the options that are visible to users.</span></span> <span data-ttu-id="5af01-218">Para alterar a visibilidade dos botões e controles da barra de ferramentas, altere as opções na seção **visibilidade de itens da barra** de ferramentas da Web Part.</span><span class="sxs-lookup"><span data-stu-id="5af01-218">To change the visibility of toolbar buttons and controls, you change options in the **ToolBar Items Visibility** section of the Web part.</span></span> <span data-ttu-id="5af01-219">Também é possível remover apenas o comando **Imprimir** ou formatos de exportação específicos tornando esses recursos não disponíveis no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="5af01-219">You can also remove the **Print** command or specific export formats by making these features unavailable on the report server.</span></span> <span data-ttu-id="5af01-220">Os controles de navegação de página estão disponíveis para relatórios que têm quebras de página; caso contrário, o relatório é uma única página de comprimento variável.</span><span class="sxs-lookup"><span data-stu-id="5af01-220">Page navigation controls are available for reports that have page breaks; otherwise, the report is a single page of variable length.</span></span> <span data-ttu-id="5af01-221">**Atualizar** reprocessa o relatório usando os parâmetros atuais.</span><span class="sxs-lookup"><span data-stu-id="5af01-221">**Refresh** re-processes the report using the parameters that are current for the report.</span></span> <span data-ttu-id="5af01-222">Para exibir todos os controles em uma linha, defina a largura geral da Web Part até pelo menos 400 pixels.</span><span class="sxs-lookup"><span data-stu-id="5af01-222">To display all the controls on one line, set the overall width of the Web Part to at least 400 pixels.</span></span>  
  
## <a name="customizing-the-viewing-area"></a><span data-ttu-id="5af01-223">Personalizando a área de exibição</span><span class="sxs-lookup"><span data-stu-id="5af01-223">Customizing the Viewing Area</span></span>  
 <span data-ttu-id="5af01-224">A área de exibição é usada para exibir relatórios.</span><span class="sxs-lookup"><span data-stu-id="5af01-224">The view area is used to display reports.</span></span> <span data-ttu-id="5af01-225">A área de exibição de relatório é compartilhada com as áreas Parâmetros e Credenciais, se elas forem usadas.</span><span class="sxs-lookup"><span data-stu-id="5af01-225">The report view area is shared with the Parameters and Credentials area, if they are used.</span></span> <span data-ttu-id="5af01-226">Se forem necessárias credenciais, a área Credenciais será exibida ao lado de uma área de exibição de relatório em branco.</span><span class="sxs-lookup"><span data-stu-id="5af01-226">If credentials are required, the Credentials area is displayed next to an empty report view area.</span></span> <span data-ttu-id="5af01-227">A área Credenciais é fechada depois que o usuário fornecer credenciais e executar o relatório.</span><span class="sxs-lookup"><span data-stu-id="5af01-227">The Credentials area closes after the user provides credentials and runs the report.</span></span> <span data-ttu-id="5af01-228">Para personalizar o texto que pede aos usuários para definir credenciais, modifique as propriedades de conexão da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="5af01-228">To customize the text that prompts users to set credentials, modify the data source connection properties.</span></span> <span data-ttu-id="5af01-229">Para obter mais informações, consulte [Criar e gerenciar fontes de dados compartilhadas &#40;Reporting Services no modo integrado do SharePoint&#41;](../../2014/reporting-services/create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span><span class="sxs-lookup"><span data-stu-id="5af01-229">For more information, see [Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../../2014/reporting-services/create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span></span>  
  
 <span data-ttu-id="5af01-230">A área Parâmetros fornece campos para digitar valores antes de executar o relatório.</span><span class="sxs-lookup"><span data-stu-id="5af01-230">The Parameters area provides fields for entering values before running the report.</span></span> <span data-ttu-id="5af01-231">Ela só é usada quando a definição de um relatório inclui parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5af01-231">It is only used when a report definition includes parameters.</span></span> <span data-ttu-id="5af01-232">Quando as áreas Parâmetros ou Credenciais são exibidas, a exibição do relatório é ajustada para usar a largura restante da Web Part.</span><span class="sxs-lookup"><span data-stu-id="5af01-232">When either the Parameters or Credentials areas are displayed, the report view is adjusted to use the remaining width of the Web Part.</span></span> <span data-ttu-id="5af01-233">Você pode definir propriedades na Web Part para personalizar a largura da área Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5af01-233">You can set properties on the Web Part to customize the width of Parameters.</span></span> <span data-ttu-id="5af01-234">Também pode definir os rótulos exibidos ao lado dos parâmetros individuais na página.</span><span class="sxs-lookup"><span data-stu-id="5af01-234">You can also define the labels that appear next to individual parameters on the page.</span></span> <span data-ttu-id="5af01-235">Para obter mais informações sobre como modificar rótulos de parâmetros, consulte [Definir parâmetros em um relatório publicado &#40;Reporting Services no modo integrado do SharePoint&#41;](report-design/set-parameters-on-a-published-report-sharepoint-integrated-mode.md).</span><span class="sxs-lookup"><span data-stu-id="5af01-235">For more information about how to modify parameter labels, see [Set Parameters on a Published Report &#40;Reporting Services in SharePoint Integrated Mode&#41;](report-design/set-parameters-on-a-published-report-sharepoint-integrated-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5af01-236">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5af01-236">See Also</span></span>  
 <span data-ttu-id="5af01-237">[Web Part do Visualizador de relatórios em um site do SharePoint](../../2014/reporting-services/report-viewer-web-part-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="5af01-237">[Report Viewer Web Part on a SharePoint Site](../../2014/reporting-services/report-viewer-web-part-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="5af01-238">Adicionar a Web Part do Visualizador de Relatórios a uma página da Web &#40;Reporting Services no modo integrado do SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="5af01-238">Add the Report Viewer Web Part to a Web Page &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](report-server-sharepoint/add-reporting-services-content-types-to-a-sharepoint-library.md)  
  
  