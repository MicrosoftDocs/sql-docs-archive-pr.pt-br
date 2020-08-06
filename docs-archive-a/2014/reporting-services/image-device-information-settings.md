---
title: Configurações de informações de dispositivo de imagem | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- images [Reporting Services], rendering
- device information settings [Reporting Services], IMAGE rendering
ms.assetid: edad9498-69f7-4726-8699-fa615f704dff
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4a177b114e331a817427fbd2ce703afa21390a9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686144"
---
# <a name="image-device-information-settings"></a>Configurações das informações do dispositivo do Image
  A tabela a seguir lista as configurações de informações de dispositivo para renderização no formato do IMAGE.  
  
|Configuração|Valor|  
|-------------|-----------|  
|**Colunas**|O número de colunas a ser definido para o relatório. Esse valor substitui as configurações originais do relatório.|  
|**ColumnSpacing**|O espaçamento entre colunas a ser definido para o relatório. Esse valor substitui as configurações originais do relatório.|  
|`DpiX`|A resolução horizontal da imagem de saída. O valor padrão é **96**. Aplica-se aos `BMP` `GIF` formatos de saída,, `PNG` e `TIFF` .|  
|`DpiY`|A resolução vertical da imagem de saída. O valor padrão é **96**. Aplica-se aos `BMP` `GIF` formatos de saída,, `PNG` e `TIFF` .|  
|**EndPage**|A última página do relatório a ser renderizado. O valor padrão é o valor de `StartPage`.|  
|**MarginBottom**|O valor da margem inferior, em polegadas, a ser definido para o relatório. Inclua um valor inteiro ou um decimal seguido de "in" (por exemplo, `1in`). Esse valor substitui as configurações originais do relatório.|  
|**MarginLeft**|O valor da margem esquerda, em polegadas, a ser definido para o relatório. Inclua um valor inteiro ou um decimal seguido de "in" (por exemplo, `1in`). Esse valor substitui as configurações originais do relatório.|  
|**MarginRight**|O valor da margem direita, em polegadas, a ser definido para o relatório. Inclua um valor inteiro ou um decimal seguido de "in" (por exemplo, `1in`). Esse valor substitui as configurações originais do relatório.|  
|**MarginTop**|O valor da margem superior, em polegadas, a ser definido para o relatório. Inclua um valor inteiro ou um decimal seguido de "in" (por exemplo, `1in`). Esse valor substitui as configurações originais do relatório.|  
|**OutputFormat**|Um dos formatos de saída com suporte do [!INCLUDE[ndptecgdiexpanded](../includes/ndptecgdiexpanded-md.md)] ([!INCLUDE[ndptecgdi](../includes/ndptecgdi-md.md)]): `BMP`, `EMF`, `GIF`, `JPEG`, `PNG` ou `TIFF`.|  
|**PageHeight**|A altura da página, em polegadas, a ser definida para o relatório. Inclua um valor inteiro ou um decimal seguido de "in" (por exemplo, `11in`). Esse valor substitui as configurações originais do relatório.|  
|**PageWidth**|A largura da página, em polegadas, a ser definida para o relatório. Inclua um valor inteiro ou um decimal seguido de "in" (por exemplo, `8.5in`). Esse valor substitui as configurações originais do relatório.|  
|**PrintDpiX**|A resolução horizontal da imagem de saída. O valor padrão é `300`. Aplica-se ao formato de saída metarquivo avançado ( `EMF` ).|  
|**PrintDpiY**|A resolução vertical da imagem de saída. O valor padrão é `300`. Aplica-se ao formato de saída metarquivo avançado ( `EMF` ).|  
|`StartPage`|A primeira página do relatório a ser renderizada. O valor `0` indica que todas as páginas serão renderizadas. O valor padrão é `1`.|  
  
## <a name="see-also"></a>Consulte Também  
 [Passando configurações de informações de dispositivo para extensões de renderização](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md)   
 [Personalizar parâmetros de extensão de renderização no RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md)   
 [Referência técnica &#40;SSRS&#41;](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
