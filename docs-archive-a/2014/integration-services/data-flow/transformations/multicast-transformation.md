---
title: Transformação Multicast | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multicasttrans.f1
helpviewer_keywords:
- multiple outputs
- Multicast transformation
- datasets [Integration Services], multiple outputs
- multiple transformations
ms.assetid: 32194784-1684-40cd-9f91-1aba4d8360d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7b5c0a38c966c89f426a213f302b45c390b77cfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686359"
---
# <a name="multicast-transformation"></a>Transformação Difusão Seletiva
  A transformação Multicast distribui sua entrada em uma ou mais saídas. Essa transformação é semelhante à transformação de divisão condicional. Ambas as transformações dirigem uma entrada para saídas múltiplas. A diferença entre as duas é que a transformação de difusão seletiva dirige todas as linhas para todas as saídas e a divisão condicional dirige uma linha para uma única saída. Para obter mais informações, consulte [Conditional Split Transformation](conditional-split-transformation.md).  
  
 Configura-se a transformação de difusão seletiva adicionando saídas.  
  
 Usando a transformação de difusão seletiva, um pacote pode criar cópias lógicas de dados. Essa capacidade é útil quando o pacote precisar aplicar vários conjuntos de transformações aos mesmos dados. Por exemplo, uma cópia dos dados é agregada e somente o resumo informativo é carregado em seu destino, enquanto outra cópia dos dados é estendida com valores de pesquisa e colunas derivadas antes que seja carregada em seu destino.  
  
 Essa transformação tem uma entrada e múltiplas saídas. Não dá suporte a uma saída de erro.  
  
## <a name="configuration-of-the-multicast-transformation"></a>Configuração da transformação Multicast  
 Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.  
  
 Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Transformação Multicast** , consulte [Multicast Transformation Editor](../../multicast-transformation-editor.md).  
  
 Para obter informações sobre as propriedades que podem ser definidas programaticamente, consulte [Common Properties](../../common-properties.md).  
  
## <a name="related-tasks"></a>Related Tasks  
 Para obter informações sobre como definir as propriedades deste componente, consulte [Definir as propriedades de um componente de fluxo de dados](../set-the-properties-of-a-data-flow-component.md).  
  
## <a name="see-also"></a>Consulte Também  
 [Fluxo de Dados](../data-flow.md)   
 [Transformações do Integration Services](integration-services-transformations.md)  
  
  
