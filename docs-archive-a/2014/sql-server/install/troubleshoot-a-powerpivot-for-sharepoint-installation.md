---
title: Solucionar problemas de instalação de PowerPivot para SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 97bc2ce7-af04-4372-ad79-c96b8c3417ab
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3adc27132d976288c14ac702baae0b842e8aef0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573453"
---
# <a name="troubleshoot-a-powerpivot-for-sharepoint-installation"></a>Solução de problemas da instalação do PowerPivot para SharePoint
  Se você obtiver erros em vez das páginas e recursos que você esperava, faça o seguinte.  
  
-   Revise as notas de versão do SharePoint e do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] para obter soluções alternativas para problemas de instalação conhecidos. As notas de versão são fornecidas com a mídia de instalação ou no site da Microsoft do qual você baixou o software.  
  
    -   [Notas de versão do SQL Server 2014](https://technet.microsoft.com/library/dn169381\(v=sql.15\).aspx).  
  
-   Consulte o tópico de wiki do Technet, [Solução de problemas de instalações do PowerPivot (e outros suplementos)](https://social.technet.microsoft.com/wiki/contents/articles/13737.troubleshooting-installations-of-powerpivot-and-other-add-ins.aspx).  
  
## <a name="issues"></a>Problemas  
  
### <a name="powerpivot-gallery-thumbnail-images-show-as-a-red-x"></a>As imagens em miniatura para Galeria PowerPivot são exibidas como um X vermelho  
 Uma causa possível é que a **Integração de recursos do PowerPivot para coleções de sites** não está ativa. Preencha o seguinte:  
  
1.  Na biblioteca da Galeria PowerPivot, clique em **configurações do site** no ícone de engrenagem configurações do ![SharePoint](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "Configurações do SharePoint") ou na lista **inicial** .  
  
2.  Na seção **Administração do Conjunto de Sites** , clique em **Recursos do Conjunto de Sites**.  
  
3.  Clique em **Recursos do Conjunto de Sites**.  
  
4.  Verifique se a **Integração de recursos do PowerPivot para coleções de sites** está **Ativa**.  
  
 Para obter as causas adicionais desse problema, consulte a [Galeria PowerPivot mostra os ícones de X vermelho](https://support.microsoft.com/kb/2361559) ( https://support.microsoft.com/kb/2361559) .  
  
  
