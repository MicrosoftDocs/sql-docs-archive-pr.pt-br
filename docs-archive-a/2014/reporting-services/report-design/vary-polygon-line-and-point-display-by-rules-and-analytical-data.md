---
title: Variar a exibição de polígono, linha e ponto por regras e dados analíticos (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.mapembeddedpolygonlayerproperties.general.f1
- sql12.rtp.rptdesigner.maplinelayerproperties.widthrules.f1
- sql12.rtp.rptdesigner.mapembeddedpointlayerproperties.general.f1
- "10538"
- "10537"
- MICROSOFT.REPORTDESIGNER.MAPMARKER.MARKERSTYLE
- sql12.rtp.rptdesigner.mapembeddedlinelayerproperties.general.f1
- "10531"
- "10536"
ms.assetid: 7f1f5584-37b4-4fa2-ae44-8988c5f0c744
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 20757988a82f9ace8f282e8586b81f45b7eab8a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681416"
---
# <a name="vary-polygon-line-and-point-display-by-rules-and-analytical-data-report-builder-and-ssrs"></a><span data-ttu-id="ab84a-102">Variar a exibição de polígono, linha e ponto por regras e dados analíticos (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="ab84a-102">Vary Polygon, Line, and Point Display by Rules and Analytical Data (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ab84a-103">As opções de exibição para polígonos, linhas e pontos em uma camada do mapa são controladas pela definição de opções para a camada, estabelecendo regras para os elementos do mapa na camada ou substituindo opções para elementos de mapas inseridos específicos em uma camada.</span><span class="sxs-lookup"><span data-stu-id="ab84a-103">The display options for polygons, lines, and points on a map layer are controlled by setting options for the layer, by setting rules for the map elements on the layer, or by overriding options for specific embedded map elements on a layer.</span></span>  
  
 <span data-ttu-id="ab84a-104">As opções de exibição são aplicadas em uma precedência específica, listadas da precedência mais baixa para a mais alta:</span><span class="sxs-lookup"><span data-stu-id="ab84a-104">Display options apply in a specific precedence, listed from lowest to highest precedence:</span></span>  
  
1.  <span data-ttu-id="ab84a-105">As opções definidas em uma camada de polígono, uma camada de linha e uma camada de ponto se aplicam a todos os elementos do mapa nessa camada, quer os elementos do mapa sejam inseridos ou não na definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="ab84a-105">Options set on a polygon layer, a line layer, and a point layer apply to all map elements on that layer, whether or not the map elements are embedded in the report definition.</span></span>  
  
2.  <span data-ttu-id="ab84a-106">As opções definidas para regras se aplicam a todos os elementos do mapa em uma camada.</span><span class="sxs-lookup"><span data-stu-id="ab84a-106">Options set for rules apply to all map elements on a layer.</span></span> <span data-ttu-id="ab84a-107">Todas as opções de visualização de dados se aplicam apenas a elementos do mapa que são associados a dados espaciais.</span><span class="sxs-lookup"><span data-stu-id="ab84a-107">All data visualization options apply only to map elements that are associated with spatial data.</span></span> <span data-ttu-id="ab84a-108">Uma opção de visualização de dados requer que você especifique um campo de dados no qual basear as variações de exibição.</span><span class="sxs-lookup"><span data-stu-id="ab84a-108">A data visualization option requires you to specify a data field to base display variations on.</span></span> <span data-ttu-id="ab84a-109">Você deve ter definido os campos de correspondência para os dados analíticos e espaciais antes de aplicar regras de visualização de dados.</span><span class="sxs-lookup"><span data-stu-id="ab84a-109">You must have set the match fields for the analytical and spatial data before you can apply data visualization rules.</span></span> <span data-ttu-id="ab84a-110">Para obter mais informações, consulte [Mapas &#40;Construtor de Relatórios e SSRS&#41;](maps-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ab84a-110">For more information, see [Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="ab84a-111">Opções que você define para elementos do mapa inseridos selecionados.</span><span class="sxs-lookup"><span data-stu-id="ab84a-111">Options that you set for selected embedded map elements.</span></span> <span data-ttu-id="ab84a-112">Observe que, quando você substitui as opções da camada, as alterações feitas na definição de relatório são permanentes.</span><span class="sxs-lookup"><span data-stu-id="ab84a-112">Note that, when you override the layer options, the changes that you make to the report definition are permanent.</span></span> <span data-ttu-id="ab84a-113">Você pode alterar os valores de campo de dados e substituir opções de exibição para personalizar a maneira como polígonos específicos, linhas e pontos aparecem em uma camada.</span><span class="sxs-lookup"><span data-stu-id="ab84a-113">You can change the data field values as well as override display options to customize the way specific polygons, lines, and points appear on a layer.</span></span>  
  
 <span data-ttu-id="ab84a-114">Além de controlar a exibição de elementos do mapa em uma camada, você pode controlar a transparência da camada para permitir que camadas desenhadas anteriormente apareçam através de camadas desenhadas posteriormente.</span><span class="sxs-lookup"><span data-stu-id="ab84a-114">In addition to controlling the display of map elements on a layer, you can control the layer transparency to allow layers that are drawn earlier to show through layers that are drawn later.</span></span> <span data-ttu-id="ab84a-115">Para obter mais informações sobre como alterar opções que afetam o mapa o toda a camada do mapa, consulte [Personalizar os dados e a exibição de um mapa ou de uma camada do mapa &#40;Construtor de Relatórios e SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ab84a-115">For more information about changing options that affect the map or the entire map layer, see [Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="understanding-rules"></a><a name="Rules"></a> <span data-ttu-id="ab84a-116">Compreendendo regras</span><span class="sxs-lookup"><span data-stu-id="ab84a-116">Understanding Rules</span></span>  
 <span data-ttu-id="ab84a-117">Você pode definir quatro tipos de regras que o processador de relatório ajuste as propriedades de exibição automaticamente para elementos do mapa em uma camada.</span><span class="sxs-lookup"><span data-stu-id="ab84a-117">You can set four types of rules that enable the report processor to automatically adjust display properties for map elements on a layer.</span></span> <span data-ttu-id="ab84a-118">As regras variam de acordo com o tipo de elemento do mapa: polígonos, linhas ou pontos.</span><span class="sxs-lookup"><span data-stu-id="ab84a-118">Rules vary depending on the map element type: polygons, lines, or points.</span></span>  
  
-   <span data-ttu-id="ab84a-119">**Polígonos.**</span><span class="sxs-lookup"><span data-stu-id="ab84a-119">**Polygons.**</span></span> <span data-ttu-id="ab84a-120">Varie a cor do polígono.</span><span class="sxs-lookup"><span data-stu-id="ab84a-120">Vary polygon color.</span></span>  
  
    -   <span data-ttu-id="ab84a-121">**Pontos centrais de polígonos.**</span><span class="sxs-lookup"><span data-stu-id="ab84a-121">**Polygon Center Points.**</span></span> <span data-ttu-id="ab84a-122">Para marcadores exibidos no ponto central de cada polígono, varie a cor, o tamanho e o tipo de marcador.</span><span class="sxs-lookup"><span data-stu-id="ab84a-122">For markers that display at the center point of each polygon, vary marker color, marker size, and marker type.</span></span>  
  
-   <span data-ttu-id="ab84a-123">**Linhas.**</span><span class="sxs-lookup"><span data-stu-id="ab84a-123">**Lines.**</span></span> <span data-ttu-id="ab84a-124">Varie a cor e a largura da linha.</span><span class="sxs-lookup"><span data-stu-id="ab84a-124">Vary line color and line width.</span></span>  
  
-   <span data-ttu-id="ab84a-125">**Pontos.**</span><span class="sxs-lookup"><span data-stu-id="ab84a-125">**Points.**</span></span> <span data-ttu-id="ab84a-126">Para marcadores exibidos para cada ponto, varie a cor, o tamanho e o tipo de marcador.</span><span class="sxs-lookup"><span data-stu-id="ab84a-126">For markers that display for each point, vary marker color, marker size, and marker type.</span></span>  
  
##  <a name="understanding-color-rules"></a><a name="Color"></a> <span data-ttu-id="ab84a-127">Compreendendo regras de cor</span><span class="sxs-lookup"><span data-stu-id="ab84a-127">Understanding Color Rules</span></span>  
 <span data-ttu-id="ab84a-128">As regras de cores se aplicam a cores de preenchimento para polígonos, linhas e marcadores que representam pontos ou pontos centrais de polígono.</span><span class="sxs-lookup"><span data-stu-id="ab84a-128">Color rules apply to fill colors for polygons, lines, and markers that represent points or polygon center points.</span></span>  
  
 <span data-ttu-id="ab84a-129">As regras de cores oferecem suporte a quatro opções:</span><span class="sxs-lookup"><span data-stu-id="ab84a-129">Color rules support four options:</span></span>  
  
-   <span data-ttu-id="ab84a-130">Aplique o estilo do modelo.</span><span class="sxs-lookup"><span data-stu-id="ab84a-130">Apply template style.</span></span> <span data-ttu-id="ab84a-131">O tema que você escolheu no assistente define o estilo do modelo para a camada.</span><span class="sxs-lookup"><span data-stu-id="ab84a-131">The theme that you chose in the wizard defines the template style for the layer.</span></span> <span data-ttu-id="ab84a-132">O tema define o estilo da fonte, o estilo da borda e a paleta.</span><span class="sxs-lookup"><span data-stu-id="ab84a-132">Theme sets the style for font, the border style, and the palette.</span></span>  
  
-   <span data-ttu-id="ab84a-133">Visualize os dados usando a paleta de cores.</span><span class="sxs-lookup"><span data-stu-id="ab84a-133">Visualize data by using color palette.</span></span> <span data-ttu-id="ab84a-134">Especifique uma paleta pelo nome.</span><span class="sxs-lookup"><span data-stu-id="ab84a-134">You specify a palette by name.</span></span> <span data-ttu-id="ab84a-135">O processador de relatório define a cor de cada elemento do mapa em uma camada percorrendo cada cor na paleta e aplicando sucessivamente tons mais claros de cada cor na paleta.</span><span class="sxs-lookup"><span data-stu-id="ab84a-135">The report processor sets the color of each map element in a layer by stepping through each color in the palette, and then applying successively lighter shades of each color in the palette.</span></span>  
  
-   <span data-ttu-id="ab84a-136">Visualize os dados usando intervalos de cores.</span><span class="sxs-lookup"><span data-stu-id="ab84a-136">Visualize data by using color ranges.</span></span> <span data-ttu-id="ab84a-137">Especifique uma cor inicial, intermediária e final.</span><span class="sxs-lookup"><span data-stu-id="ab84a-137">You specify a beginning, middle, and end color.</span></span> <span data-ttu-id="ab84a-138">Em seguida, especifique opções de distribuição.</span><span class="sxs-lookup"><span data-stu-id="ab84a-138">Then you specify distribution options.</span></span> <span data-ttu-id="ab84a-139">O processador de relatório usa os valores de opção de distribuição para criar um conjunto de cores que gera uma exibição semelhante para um mapa de calor.</span><span class="sxs-lookup"><span data-stu-id="ab84a-139">The report processor uses the distribution option values to create a set of colors that produces a display similar to a heat map.</span></span> <span data-ttu-id="ab84a-140">Uma mapa de calor exibe a cor em relação à temperatura.</span><span class="sxs-lookup"><span data-stu-id="ab84a-140">A heat map displays color as related to temperature.</span></span> <span data-ttu-id="ab84a-141">Por exemplo, em uma escala de 0 a 100, valores baixos são azuis para representar frio e valores altos são vermelhos para representar calor.</span><span class="sxs-lookup"><span data-stu-id="ab84a-141">For example, on a scale of 0 to 100, low values are blue to represent cold and high values are red to represent hot.</span></span>  
  
-   <span data-ttu-id="ab84a-142">Visualize os dados usando cores personalizadas.</span><span class="sxs-lookup"><span data-stu-id="ab84a-142">Visualize data by using custom colors.</span></span> <span data-ttu-id="ab84a-143">Especifique um conjunto de cores.</span><span class="sxs-lookup"><span data-stu-id="ab84a-143">You specify a set of colors.</span></span> <span data-ttu-id="ab84a-144">O processador de relatório define a cor de cada elemento do mapa na camada percorrendo os valores especificados por você.</span><span class="sxs-lookup"><span data-stu-id="ab84a-144">The report processor sets the color of each map element in the layer by stepping through the values that you specify.</span></span>  
  
 <span data-ttu-id="ab84a-145">A paleta padrão incluir a cor branca.</span><span class="sxs-lookup"><span data-stu-id="ab84a-145">The default palette includes the color white.</span></span> <span data-ttu-id="ab84a-146">Para evitar o contraste forte entre o branco e as outras cores na paleta, especifique uma cor inicial que seja clara na paleta.</span><span class="sxs-lookup"><span data-stu-id="ab84a-146">To avoid the strong contrast between white and other colors in the palette, specify a start color that is a light color in the palette.</span></span>  
  
 <span data-ttu-id="ab84a-147">Para exibir elementos do mapa não associados a dados como incolores, defina **Sem Cor** como a cor padrão dos elementos de mapa na camada.</span><span class="sxs-lookup"><span data-stu-id="ab84a-147">To display map elements that are not associated with data as colorless, set **No Color** for the default color for map elements on the layer.</span></span>  
  
### <a name="color-scale"></a><span data-ttu-id="ab84a-148">Escala de cores</span><span class="sxs-lookup"><span data-stu-id="ab84a-148">Color Scale</span></span>  
 <span data-ttu-id="ab84a-149">Por padrão, todos os valores de regras de cores aparecem na escala de cores, além de aparecer na primeira legenda.</span><span class="sxs-lookup"><span data-stu-id="ab84a-149">By default, all color rule values appear in the color scale, in addition to appearing in the first legend.</span></span> <span data-ttu-id="ab84a-150">A escala de cores é criada para exibir um intervalo de cores.</span><span class="sxs-lookup"><span data-stu-id="ab84a-150">The color scale is designed to display one range of colors.</span></span> <span data-ttu-id="ab84a-151">Escolha os dados mais importantes a serem exibidos na escala de cores.</span><span class="sxs-lookup"><span data-stu-id="ab84a-151">Choose the most important data to display in the color scale.</span></span>  
  
 <span data-ttu-id="ab84a-152">Para remover os valores que você não deseja na escala de cores, desmarque a opção de escala de cores de cada regra de cor em todas as camadas.</span><span class="sxs-lookup"><span data-stu-id="ab84a-152">To remove the values that you do not want in the color scale, clear the color scale option for every color rule on every layer.</span></span>  
  
##  <a name="understanding-line-width-rules"></a><a name="Width"></a> <span data-ttu-id="ab84a-153">Compreendendo regras de largura de linha</span><span class="sxs-lookup"><span data-stu-id="ab84a-153">Understanding Line Width Rules</span></span>  
 <span data-ttu-id="ab84a-154">As regras de largura se aplicam a linhas.</span><span class="sxs-lookup"><span data-stu-id="ab84a-154">Width rules apply to lines.</span></span> <span data-ttu-id="ab84a-155">As regras de largura têm suporte para duas opções:</span><span class="sxs-lookup"><span data-stu-id="ab84a-155">Width rules support two options:</span></span>  
  
-   <span data-ttu-id="ab84a-156">Use uma largura de linha padrão.</span><span class="sxs-lookup"><span data-stu-id="ab84a-156">Use a default line width.</span></span> <span data-ttu-id="ab84a-157">Especifique a largura da linha em pontos.</span><span class="sxs-lookup"><span data-stu-id="ab84a-157">You specify the line width in points.</span></span>  
  
-   <span data-ttu-id="ab84a-158">Visualize dados usando a largura da linha.</span><span class="sxs-lookup"><span data-stu-id="ab84a-158">Visualize data by using line width.</span></span> <span data-ttu-id="ab84a-159">Defina as larguras mínima e máxima para a linha, especifique o campo de dados a ser usado para variar a largura e especifique as opções de distribuição a serem aplicadas aos dados.</span><span class="sxs-lookup"><span data-stu-id="ab84a-159">You set the minimum and maximum widths for the line, specify the data field to use to vary the width, and then specify the distribution options to apply to that data.</span></span>  
  
##  <a name="understanding-marker-size-rules"></a><a name="Size"></a> <span data-ttu-id="ab84a-160">Compreendendo regras de tipo de tamanho de marcador</span><span class="sxs-lookup"><span data-stu-id="ab84a-160">Understanding Marker Size Rules</span></span>  
 <span data-ttu-id="ab84a-161">As regras de tamanho se aplicam a marcadores que representam pontos ou pontos centrais de polígono.</span><span class="sxs-lookup"><span data-stu-id="ab84a-161">Size rules apply to markers that represent points or polygon center points.</span></span> <span data-ttu-id="ab84a-162">As regras de tamanho têm suporte para duas opções:</span><span class="sxs-lookup"><span data-stu-id="ab84a-162">Size rules support two options:</span></span>  
  
-   <span data-ttu-id="ab84a-163">Use um tamanho de marcador padrão.</span><span class="sxs-lookup"><span data-stu-id="ab84a-163">Use a default marker size.</span></span> <span data-ttu-id="ab84a-164">Especifique o tamanho em pontos.</span><span class="sxs-lookup"><span data-stu-id="ab84a-164">You specify the size in points.</span></span>  
  
-   <span data-ttu-id="ab84a-165">Visualize dados usando tamanho.</span><span class="sxs-lookup"><span data-stu-id="ab84a-165">Visualize data by using size.</span></span> <span data-ttu-id="ab84a-166">Defina os tamanhos mínimo e máximo para o marcador, especifique o campo de dados a ser usado para variar o tamanho e especifique as opções de distribuição a serem aplicadas aos dados.</span><span class="sxs-lookup"><span data-stu-id="ab84a-166">You set the minimum and maximum sizes for the marker, specify the data field to use to vary the size, and then specify the distribution options to apply to that data.</span></span>  
  
##  <a name="understanding-marker-type-rules"></a><a name="Marker"></a> <span data-ttu-id="ab84a-167">Compreendendo regras de tipo de marcador</span><span class="sxs-lookup"><span data-stu-id="ab84a-167">Understanding Marker Type Rules</span></span>  
 <span data-ttu-id="ab84a-168">As regras de tipo de marcador se aplicam a marcadores que representam pontos ou pontos centrais de polígono.</span><span class="sxs-lookup"><span data-stu-id="ab84a-168">Marker type rules apply to markers that represent points or polygon center points.</span></span> <span data-ttu-id="ab84a-169">As regras de tipo de marcador têm suporte para duas opções:</span><span class="sxs-lookup"><span data-stu-id="ab84a-169">Marker type rules support two options:</span></span>  
  
-   <span data-ttu-id="ab84a-170">Use um tipo de marcador padrão.</span><span class="sxs-lookup"><span data-stu-id="ab84a-170">Use a default marker type.</span></span> <span data-ttu-id="ab84a-171">Você especifica um dos tipos de marcador disponíveis.</span><span class="sxs-lookup"><span data-stu-id="ab84a-171">You specify one of the available marker types.</span></span>  
  
-   <span data-ttu-id="ab84a-172">Visualize dados usando marcadores.</span><span class="sxs-lookup"><span data-stu-id="ab84a-172">Visualize data by using markers.</span></span> <span data-ttu-id="ab84a-173">Você especifica um conjunto de marcadores e especifica a ordem na qual deseja que sejam usados.</span><span class="sxs-lookup"><span data-stu-id="ab84a-173">You specify a set of markers and specify the order in which you want them used.</span></span> <span data-ttu-id="ab84a-174">Os tipos de marcador incluem `Circle`, `Diamond`, `Pentagon`, `PushPin`, `Rectangle`, `Star`, `Triangle`, `Trapezoid` e `Wedge`.</span><span class="sxs-lookup"><span data-stu-id="ab84a-174">Marker types include `Circle`, `Diamond`, `Pentagon`, `PushPin`, `Rectangle`, `Star`, `Triangle`, `Trapezoid`, and `Wedge`.</span></span>  
  
##  <a name="understanding-distribution-options"></a><a name="Distribution"></a> <span data-ttu-id="ab84a-175">Compreendendo opções de distribuição</span><span class="sxs-lookup"><span data-stu-id="ab84a-175">Understanding Distribution Options</span></span>  
 <span data-ttu-id="ab84a-176">Para criar uma distribuição de valores, você pode dividir os dados em intervalos.</span><span class="sxs-lookup"><span data-stu-id="ab84a-176">To create a distribution of values, you can divide your data into ranges.</span></span> <span data-ttu-id="ab84a-177">Especifique o tipo de distribuição, o número de subintervalos e os valores de intervalo mínimo e máximo.</span><span class="sxs-lookup"><span data-stu-id="ab84a-177">You specify the distribution type, the number of subranges, and the minimum and maximum range values.</span></span>  
  
 <span data-ttu-id="ab84a-178">Na lista a seguir, vamos supor que você tenha três elementos de mapa e seis valores analíticos relacionados que variam de 1 a 9999 com os valores seguintes: 1, 10, 200, 2000, 4777, 8999.</span><span class="sxs-lookup"><span data-stu-id="ab84a-178">In the following list, assume that you have three map elements and six related analytical values that range from 1 to 9999 with the following values: 1, 10, 200, 2000, 4777, 8999.</span></span>  
  
-   <span data-ttu-id="ab84a-179">**EqualInterval**</span><span class="sxs-lookup"><span data-stu-id="ab84a-179">**EqualInterval.**</span></span> <span data-ttu-id="ab84a-180">. Crie intervalos que dividam os dados em intervalos iguais.</span><span class="sxs-lookup"><span data-stu-id="ab84a-180">Create ranges that divide the data into equal range intervals.</span></span> <span data-ttu-id="ab84a-181">Para o exemplo, os três intervalos seriam 0-2999, 3000-5999, 6000-8999.</span><span class="sxs-lookup"><span data-stu-id="ab84a-181">For the example, the three ranges would be 0-2999, 3000-5999, 6000-8999.</span></span> <span data-ttu-id="ab84a-182">Subintervalo 1: 1, 10, 200, 500.</span><span class="sxs-lookup"><span data-stu-id="ab84a-182">Subrange 1: 1, 10, 200, 500.</span></span> <span data-ttu-id="ab84a-183">Subintervalo 2: 4777.</span><span class="sxs-lookup"><span data-stu-id="ab84a-183">Subrange 2: 4777.</span></span> <span data-ttu-id="ab84a-184">Subintervalo 3: 8999.</span><span class="sxs-lookup"><span data-stu-id="ab84a-184">Subrange 3: 8999.</span></span> <span data-ttu-id="ab84a-185">Esse método não considera o modo como os dados são distribuídos.</span><span class="sxs-lookup"><span data-stu-id="ab84a-185">This method does not take into account how the data is distributed.</span></span> <span data-ttu-id="ab84a-186">Valores muito grandes ou muito pequenos podem afetar os resultados da distribuição.</span><span class="sxs-lookup"><span data-stu-id="ab84a-186">Very large values or very small values can skew the distribution results.</span></span>  
  
-   <span data-ttu-id="ab84a-187">**EqualDistribution.**</span><span class="sxs-lookup"><span data-stu-id="ab84a-187">**EqualDistribution.**</span></span> <span data-ttu-id="ab84a-188">Crie intervalos que dividam esses dados de forma que cada intervalo tenha um número de itens igual.</span><span class="sxs-lookup"><span data-stu-id="ab84a-188">Create ranges that divide that data so that each range has an equal number of items.</span></span> <span data-ttu-id="ab84a-189">Para os dados de exemplo, os três intervalos seriam 0-10, 11-500, 501-8999.</span><span class="sxs-lookup"><span data-stu-id="ab84a-189">For the example data, the three ranges would be 0-10, 11-500, 501-8999.</span></span> <span data-ttu-id="ab84a-190">Subintervalo 1: 1, 10.</span><span class="sxs-lookup"><span data-stu-id="ab84a-190">Subrange 1: 1, 10.</span></span> <span data-ttu-id="ab84a-191">Subintervalo 2: 200, 500.</span><span class="sxs-lookup"><span data-stu-id="ab84a-191">Subrange 2: 200, 500.</span></span> <span data-ttu-id="ab84a-192">Subintervalo 3: 4777, 8999.</span><span class="sxs-lookup"><span data-stu-id="ab84a-192">Subrange 3: 4777, 8999.</span></span> <span data-ttu-id="ab84a-193">Este método pode afetar a distribuição criando divisões que abrangem intervalos muito grandes ou muito pequenos.</span><span class="sxs-lookup"><span data-stu-id="ab84a-193">This method can skew the distribution by creating divisions that span very large or very small ranges.</span></span>  
  
-   <span data-ttu-id="ab84a-194">**Ideal.**</span><span class="sxs-lookup"><span data-stu-id="ab84a-194">**Optimal.**</span></span> <span data-ttu-id="ab84a-195">Crie intervalos que ajustem automaticamente a distribuição para criar subintervalos equilibrados.</span><span class="sxs-lookup"><span data-stu-id="ab84a-195">Create ranges that automatically adjust distribution to create balanced subranges.</span></span> <span data-ttu-id="ab84a-196">O número de subintervalos é determinado pelo algoritmo.</span><span class="sxs-lookup"><span data-stu-id="ab84a-196">The number of subranges is determined by the algorithm.</span></span>  
  
-   <span data-ttu-id="ab84a-197">**Personalizado.**</span><span class="sxs-lookup"><span data-stu-id="ab84a-197">**Custom.**</span></span> <span data-ttu-id="ab84a-198">Especifique seu próprio número de intervalos para controlar a distribuição de valores.</span><span class="sxs-lookup"><span data-stu-id="ab84a-198">Specify your own number of ranges to control the distribution of values.</span></span> <span data-ttu-id="ab84a-199">Para os dados do exemplo, você pode especificar 3 intervalos: 1-2, 3-8, 9.</span><span class="sxs-lookup"><span data-stu-id="ab84a-199">For the example data, you can specify ranges 3 ranges: 1-2, 3-8, 9.</span></span>  
  
 <span data-ttu-id="ab84a-200">Os valores de distribuição são usados pelas regras para variar os valores de exibição do elemento do mapa.</span><span class="sxs-lookup"><span data-stu-id="ab84a-200">The distribution values are used by the rules to vary the map element display values.</span></span>  
  
##  <a name="understanding-legends-and-legend-items"></a><a name="Legends"></a> <span data-ttu-id="ab84a-201">Compreendendo legendas e itens de legenda</span><span class="sxs-lookup"><span data-stu-id="ab84a-201">Understanding Legends and Legend Items</span></span>  
 <span data-ttu-id="ab84a-202">Os itens de legenda são criados automaticamente a partir das regras que você especifica para cada camada.</span><span class="sxs-lookup"><span data-stu-id="ab84a-202">Legend items are created automatically from the rules that you specify for each layer.</span></span> <span data-ttu-id="ab84a-203">As opções de regras controlam quantos itens são criados e em qual legenda aparecem.</span><span class="sxs-lookup"><span data-stu-id="ab84a-203">Rule options control how many items are created and which legend they appear in.</span></span> <span data-ttu-id="ab84a-204">Por padrão, todos os itens de todas as regras são adicionados na primeira legenda.</span><span class="sxs-lookup"><span data-stu-id="ab84a-204">By default, all items for all rules are added to the first legend.</span></span> <span data-ttu-id="ab84a-205">Para mover itens para fora da primeira legenda, crie tantas legendas adicionais quanto precisar e, para cada regra, especifique a legenda a ser usada para exibir os itens resultantes da regra.</span><span class="sxs-lookup"><span data-stu-id="ab84a-205">To move items out of the first legend, create as many additional legends as you need, and for each rule, specify the legend to use to display the items that result from the rule.</span></span> <span data-ttu-id="ab84a-206">Para ocultar itens com base em uma regra, especifique um nome de legenda em branco.</span><span class="sxs-lookup"><span data-stu-id="ab84a-206">To hide items based on a rule, specify a blank legend name.</span></span>  
  
 <span data-ttu-id="ab84a-207">Para controlar onde uma legenda aparece, use a caixa de diálogo Propriedades da Legenda para especificar uma posição relativa ao visor do mapa.</span><span class="sxs-lookup"><span data-stu-id="ab84a-207">To control where a legend appears, use the Legend Properties dialog box to specify a position relative to the map viewport.</span></span> <span data-ttu-id="ab84a-208">Para obter mais informações, consulte [Alterar legendas de mapa, escala de cores e regras associadas &#40;Construtor de Relatórios e SSRS&#41;](change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ab84a-208">For more information, see [Change Map Legends, Color Scale, and Associated Rules &#40;Report Builder and SSRS&#41;](change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="ab84a-209">As legendas são expandidas automaticamente para exibir o título ou o texto da legenda.</span><span class="sxs-lookup"><span data-stu-id="ab84a-209">Legends automatically expand to display the legend title or legend text.</span></span> <span data-ttu-id="ab84a-210">Para formatar o texto dos itens da legenda, use palavras-chave de legenda de mapa e formatos personalizados.</span><span class="sxs-lookup"><span data-stu-id="ab84a-210">To format the text of legend items, use map legend keywords and custom formats.</span></span> <span data-ttu-id="ab84a-211">Para obter mais informações, consulte [Alterar legendas de mapa, escala de cores e regras associadas &#40;Construtor de Relatórios e SSRS&#41;](change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ab84a-211">For more information, see [Change Map Legends, Color Scale, and Associated Rules &#40;Report Builder and SSRS&#41;](change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="ab84a-212">As tabelas a seguir mostram exemplos de formatos diferentes que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="ab84a-212">The following tables shows examples of different formats that you can use.</span></span>  
  
|<span data-ttu-id="ab84a-213">Palavra-chave e formato</span><span class="sxs-lookup"><span data-stu-id="ab84a-213">Keyword and Format</span></span>|<span data-ttu-id="ab84a-214">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="ab84a-214">Description</span></span>|<span data-ttu-id="ab84a-215">Exemplo do que é exibido como texto na legenda</span><span class="sxs-lookup"><span data-stu-id="ab84a-215">Example of what appears as text in the legend</span></span>|  
|------------------------|-----------------|---------------------------------------------------|  
|`#FROMVALUE {C0}`|<span data-ttu-id="ab84a-216">Exibe a moeda do valor total sem casas decimais</span><span class="sxs-lookup"><span data-stu-id="ab84a-216">Displays the currency of the total value with no decimal places</span></span>|<span data-ttu-id="ab84a-217">$ 400</span><span class="sxs-lookup"><span data-stu-id="ab84a-217">$400</span></span>|  
|`#FROMVALUE {C2}`|<span data-ttu-id="ab84a-218">Exibe a moeda do valor total com até duas casas decimais.</span><span class="sxs-lookup"><span data-stu-id="ab84a-218">Displays the currency of the total value to two decimal places.</span></span>|<span data-ttu-id="ab84a-219">$ 400,55</span><span class="sxs-lookup"><span data-stu-id="ab84a-219">$400.55</span></span>|  
|`#TOVALUE`|<span data-ttu-id="ab84a-220">Exibe o valor numérico real do campo de dados.</span><span class="sxs-lookup"><span data-stu-id="ab84a-220">Displays the actual numeric value of the data field.</span></span>|<span data-ttu-id="ab84a-221">10000</span><span class="sxs-lookup"><span data-stu-id="ab84a-221">10000</span></span>|  
|`#FROMVALUE{N0} - #TOVALUE{N0}`|<span data-ttu-id="ab84a-222">Exibe os valores numéricos reais do início e do fim do intervalo.</span><span class="sxs-lookup"><span data-stu-id="ab84a-222">Displays the actual numeric values of the beginning of the range and end of the range.</span></span>|<span data-ttu-id="ab84a-223">10 - 790</span><span class="sxs-lookup"><span data-stu-id="ab84a-223">10 - 790</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab84a-224">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ab84a-224">See Also</span></span>  
 <span data-ttu-id="ab84a-225">[Alterar legendas de mapa, escala de cores e regras associadas &#40;Construtor de Relatórios e SSRS&#41;](change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ab84a-225">[Change Map Legends, Color Scale, and Associated Rules &#40;Report Builder and SSRS&#41;](change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ab84a-226">[Mapas &#40;Construtor de Relatórios e SSRS&#41;](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ab84a-226">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ab84a-227">Assistente de Mapa e Assistente de Camada do Mapa &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ab84a-227">Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;</span></span>](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md)  
  
  