---
title: Planejar o suporte a relatórios de mapa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ddc97a7-7ee5-475d-bc49-3b814dce7e19
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f3d1e1774e44ae879b8c01e66289cefd4d42ee1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684586"
---
# <a name="plan-for-map-report-support"></a><span data-ttu-id="3b6cc-102">Planejar para suporte ao relatório de mapa</span><span class="sxs-lookup"><span data-stu-id="3b6cc-102">Plan for Map Report Support</span></span>
  [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)]<span data-ttu-id="3b6cc-103">dá suporte a relatórios de mapa que usam fontes de dados espaciais.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-103">supports map reports that use spatial data sources.</span></span> <span data-ttu-id="3b6cc-104">Os dados espaciais podem vir de bancos de dados do SQL Server, de arquivos de formas ESRI ou da Galeria de Mapas instalada com o Reporting Services ou o Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-104">Spatial data can come from SQL Server databases, from ESRI Shapefiles, or from the Map Gallery that is installed with either Reporting Services or Report Builder.</span></span> <span data-ttu-id="3b6cc-105">Um mapa também pode exibir um plano de fundo de peças de mapas do Bing.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-105">A map can also display a background of Bing map tiles.</span></span> <span data-ttu-id="3b6cc-106">Um autor de relatório pode criar um relatório que especifica dados espaciais ou peças de mapa do Bing como dinâmicos e recuperados em tempo de execução ou como estáticos e inseridos na definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-106">A report author can create a report that specifies spatial data or Bing map tiles as dynamic and retrieved at run time or as static and embedded in the report definition.</span></span>  
  
## <a name="support-for-bing-maps"></a><span data-ttu-id="3b6cc-107">Suporte para Bing Maps</span><span class="sxs-lookup"><span data-stu-id="3b6cc-107">Support for Bing Maps</span></span>  
 <span data-ttu-id="3b6cc-108">Os mapas podem incluir uma camada em segundo plano que exibe peças de mapa do Bing.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-108">Maps can include a background layer that displays Bing map tiles.</span></span> <span data-ttu-id="3b6cc-109">Para exibir um relatório publicado que tem uma camada de peça de mapa, o servidor de relatório deve ser configurado para recuperar peças de mapa dos Serviços Web do Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-109">To view a published report that has a map tile layer, the report server must be configured to retrieve tiles from Bing Maps Web Services.</span></span> <span data-ttu-id="3b6cc-110">Para obter mais informações, consulte [RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="3b6cc-110">For more information, see [RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md).</span></span>  
  
 <span data-ttu-id="3b6cc-111">Em cada relatório, os autores de relatório podem especificar se usar uma conexão de Protocolo SSL para recuperar peças do servidor de peças de mapa.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-111">In each report, report authors can specify whether to use a Secure Sockets Layer (SSL) connection to retrieve tiles from the tile server.</span></span> <span data-ttu-id="3b6cc-112">Para fazer isso, no painel Propriedades da camada do bloco, é necessário definir a propriedade booliana UseSecureConnection como `true` .</span><span class="sxs-lookup"><span data-stu-id="3b6cc-112">To do this, in the Properties pane for the tile layer, they must set the Boolean property UseSecureConnection to `true`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b6cc-113"> Para obter mais informações sobre o uso de peças de mapa do Bing no seu relatório, consulte [termos de uso adicionais](https://go.microsoft.com/fwlink/?LinkId=151371) e a [Política de Privacidade](https://go.microsoft.com/fwlink/?LinkId=151372).</span><span class="sxs-lookup"><span data-stu-id="3b6cc-113">For more information about the use of Bing map tiles in your report, see [Additional Terms of Use](https://go.microsoft.com/fwlink/?LinkId=151371) and [Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=151372).</span></span>  
  
## <a name="report-design-recommendations"></a><span data-ttu-id="3b6cc-114">Recomendações de design de relatórios</span><span class="sxs-lookup"><span data-stu-id="3b6cc-114">Report Design Recommendations</span></span>  
 <span data-ttu-id="3b6cc-115">O bom design para relatórios de mapa requer que o autor do relatório avalie as desvantagens entre dados espaciais estáticos e dinâmicos e encontre o equilíbrio ideal para os usuários do relatório.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-115">Good report design for map reports requires that the report author assess the trade-offs between static and dynamic spatial data and find a balance that serves the report users.</span></span> <span data-ttu-id="3b6cc-116">Elementos de mapa inseridos podem aumentar significativamente o tamanho da definição do relatório, mas reduzem o tempo necessário para exibir o mapa no relatório.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-116">Embedded map elements can significantly increase the size of the report definition, but reduce the time that is required to view the map report.</span></span> <span data-ttu-id="3b6cc-117">Elementos de mapa dinâmico reduzem o tamanho da definição do relatório, mas aumentam o tempo necessário para processar e exibir o mapa.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-117">Dynamic map elements reduce the report definition size but increase the time that is required to process and view the map.</span></span> <span data-ttu-id="3b6cc-118">O autor do relatório deve localizar o equilíbrio certo entre estes problemas.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-118">The report author must find the right balance between these opposing issues.</span></span>  
  
 <span data-ttu-id="3b6cc-119">Quando o tamanho da definição de relatório é um problema, como administrador de servidor de relatório, você pode encorajar os designers de relatório a reduzirem a quantidade de dados espaciais em uma definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-119">When report definition size is an issue, as report server administrator, you can encourage report designers to reduce the amount of spatial data in a report definition.</span></span>  
  
 <span data-ttu-id="3b6cc-120">Sob as condições a seguir, elementos de mapa são inseridos na definição de relatório:</span><span class="sxs-lookup"><span data-stu-id="3b6cc-120">Under the following conditions, map elements are embedded in the report definition:</span></span>  
  
-   <span data-ttu-id="3b6cc-121">Quando o relatório é criado, a fonte de dados espaciais está no sistema de arquivos local.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-121">When the report is created, the spatial data source is on the local file system.</span></span> <span data-ttu-id="3b6cc-122">Isso inclui dados espaciais da Galeria de Mapas ou arquivos de formas ESRI que foram instalados localmente.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-122">This includes spatial data from the Map Gallery or ESRI Shapefiles that have been installed locally.</span></span> <span data-ttu-id="3b6cc-123">Por padrão, o assistente de mapa e o assistente de camada do mapa inserem dados espaciais de fontes de dados no sistema de arquivos local.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-123">By default, the map wizard and map layer wizard embed spatial data from data sources on the local file system.</span></span>  
  
-   <span data-ttu-id="3b6cc-124">O autor do relatório escolhe a opção para inserir dados espaciais manualmente no relatório.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-124">The report author chooses the option to embed spatial data manually in the report.</span></span>  
  
 <span data-ttu-id="3b6cc-125">Para ajudar a reduzir o tamanho de definições de relatório que têm mapas, os autores de relatório podem usar um ou mais das opções seguintes:</span><span class="sxs-lookup"><span data-stu-id="3b6cc-125">To help reduce the size of report definitions that have maps, report authors can use one or more of the following options:</span></span>  
  
-   <span data-ttu-id="3b6cc-126">No Designer de Relatórios no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], adicione fontes de dados espaciais que são arquivos de formas ESRI para o projeto do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-126">From Report Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], add spatial data sources that are ESRI Shapefiles to the report server project.</span></span> <span data-ttu-id="3b6cc-127">Quando você implanta o projeto, os arquivos de formas ESRI são publicados no servidor de relatório além do relatório.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-127">When you deploy the project, the ESRI Shapefiles are published to the report server in addition to the report.</span></span> <span data-ttu-id="3b6cc-128">Quando o autor de relatório executa o assistente de Mapa, ele pode especificar uma fonte de dados espacial do projeto de Servidor de Relatório e os elementos de mapas não são incorporados por padrão nas definições de relatório.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-128">When the report author runs the Map wizard, they can specify a spatial data source from the Report Server project, and the map elements are not embedded in the report definitions by default.</span></span>  
  
-   <span data-ttu-id="3b6cc-129">No Construtor de Relatórios, adicione fontes de dados espaciais que são arquivos de formas ESRI selecionando Arquivos de formas no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-129">From Report Builder, add spatial data sources that are ESRI Shapefiles by selecting Shapefiles from the report server.</span></span> <span data-ttu-id="3b6cc-130">Quando o autor do relatório executa o assistente de Mapa, ele pode navegar e selecionar uma fonte de dados espaciais no servidor de relatório e, por padrão, os elementos de mapa não são inseridos nas definições de relatório.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-130">When the report author runs the Map wizard, they can browse to and select a spatial data source from the report server, and the map elements are not embedded in the report definitions by default.</span></span>  
  
-   <span data-ttu-id="3b6cc-131">Quando os dados de mapa devem ser inseridos, ajuste o centro do visor e o nível de zoom para incluir apenas os dados de mapa necessários para o relatório.</span><span class="sxs-lookup"><span data-stu-id="3b6cc-131">When map data must be embedded map data, adjust the viewport center and zoom level to include just the map data that is needed for the report.</span></span>  
  
 <span data-ttu-id="3b6cc-132">Para obter mais informações, [mapas &#40;Construtor de relatórios e SSRS&#41;](report-design/maps-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3b6cc-132">For more information, [Maps &#40;Report Builder and SSRS&#41;](report-design/maps-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b6cc-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3b6cc-133">See Also</span></span>  
 [<span data-ttu-id="3b6cc-134">Solucionar problemas de relatórios: Mapear relatórios &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3b6cc-134">Troubleshoot Reports: Map Reports &#40;Report Builder and SSRS&#41;</span></span>](report-design/troubleshoot-reports-map-reports-report-builder-and-ssrs.md)  
  
  