---
title: Excluir uma exibição da fonte de dados (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- deleting data source views
- data source views [Analysis Services], deleting
- removing data source views
ms.assetid: ae3f5ca0-ecbf-4b52-8386-eb457719d854
author: minewiskan
ms.author: owend
ms.openlocfilehash: 24b587e8d8961161ea803915c31d117c11f7cf2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583197"
---
# <a name="delete-a-data-source-view-analysis-services"></a>Excluir uma exibição da fonte de dados (Analysis Services)
  Se você não estiver mais usando uma DSV (exibição da fonte de dados) em um projeto OLAP, poderá excluí-la do projeto no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].  
  
 A exclusão de uma DSV é permanente. Não é possível restaurar uma DSV excluída para um projeto ou banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .  
  
 As DSVs das quais outros objetos dependem não podem ser excluídas de um banco de dados aberto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pelo [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] em modo online. Para excluir uma DSV de um projeto que está conectado a um banco de dados executado em um servidor, você primeiro deve excluir todos os objetos no banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que dependem da DSV antes de excluir a própria DSV.  
  
 Excluir uma DSV invalidará outros objetos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que dependem dela; portanto, antes de excluir a DSV, consulte a lista de objetos que ficarão inválidos quando a DSV for removida. Examine esta lista com cuidado para ter certeza de que ela não inclui objetos que você ainda espera usar.  
  
 ![Caixa de diálogo Excluir Objetos](../media/ssas-olapdsv-deleteobjects.gif "Caixa de diálogo Excluir Objetos")  
  
## <a name="see-also"></a>Consulte Também  
 [Exibições da fonte de dados em modelos multidimensionais](data-source-views-in-multidimensional-models.md)   
 [Alterar propriedades em uma exibição da fonte de dados &#40;Analysis Services&#41;](change-properties-in-a-data-source-view-analysis-services.md)  
  
  
