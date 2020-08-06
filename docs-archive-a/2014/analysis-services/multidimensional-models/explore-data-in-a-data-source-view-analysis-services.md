---
title: Explorar dados em uma exibição da fonte de dados (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- exploring data [Analysis Services]
- data source views [Analysis Services], exploring data
- viewing source data
ms.assetid: 2c922c35-fbcb-45b2-96b1-c7a846d8b419
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6adf9edecd807158ba1d0de3287cccd6fa8dd787
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583854"
---
# <a name="explore-data-in-a-data-source-view-analysis-services"></a>Explorar dados em uma exibição da fonte de dados (Analysis Services)
  Você pode usar a caixa de diálogo **Explorar Dados** do Designer de Exibição da Fonte de Dados do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] para procurar dados para uma tabela, exibição ou consulta nomeada de uma DSV (exibição da fonte de dados). Ao explorar os dados no Designer de Exibição da Fonte de Dados, você pode exibir o conteúdo de cada coluna de dados da tabela, exibição ou consulta nomeada selecionada. Exibir o conteúdo real é útil para determinar se todas as colunas são necessárias, se os cálculos nomeados são requeridos para torná-los mais amigável para o usuário e melhorar a usabilidade e se os cálculos nomeados ou as consultas nomeadas existentes retornam os valores previstos.  
  
 Para exibir os dados, é necessária uma conexão ativa com a(s) fonte(s) de dados do objeto selecionado na DSV (exibição da fonte de dados). Todos os cálculos nomeados de uma tabela também são enviados na consulta.  
  
 Os dados retornados em um formato de tabela que você pode classificar e copiar. Clique nos cabeçalhos das colunas para reclassificar as linhas das respectivas colunas. Você também pode realçar dados na grade e pressionar Ctrl-C para copiar a seleção para a área de transferência.  
  
 Você também pode controlar o método de exemplo e a contagem de exemplo. Por padrão, as 5.000 primeiras linhas são retornadas.  
  
## <a name="to-browse-data-or-change-sampling-options"></a>Para procurar dados ou alterar opções de amostragem  
  
1.  No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto ou conecte-se ao banco de dados que contém a exibição da fonte de dados na qual você deseja procurar dados.  
  
2.  No Gerenciador de Soluções, expanda a pasta **Exibições da Fonte de Dados** e clique duas vezes na exibição da fontes de dados.  
  
3.  Clique com o botão direito do mouse na tabela, exibição ou consulta nomeada que contém os dados que você deseja exibir e, em seguida, clique em **Explorar Dados**.  
  
     A fonte de dados subjacente à tabela, exibição ou consulta nomeada na exibição da fonte de dados são consultas e os resultados são exibidos na guia **explorar \<object name> tabela** .  
  
4.  Na barra de ferramentas **explorar \<object name> tabela** , clique no ícone **Opções de amostragem** .  
  
     A caixa de diálogo **Opções de Exploração de Dados** é aberta. Nela você pode especificar o método de amostragem (menos ou mais registros que o tamanho de amostragem padrão de 5000 linhas) ou a contagem de exemplo.  
  
5.  Clique em **OK** ou em **Cancelar** , conforme apropriado.  
  
6.  Para obter uma nova amostra dos dados, clique em **reamostrar dados** na barra de ferramentas da ** \<object name> tabela de exploração** .  
  
## <a name="see-also"></a>Consulte Também  
 [Exibições de fontes de dados em modelos multidimensionais](data-source-views-in-multidimensional-models.md)  
  
  
