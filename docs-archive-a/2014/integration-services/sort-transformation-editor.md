---
title: Editor de transformação Classificação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sorttransformation.f1
helpviewer_keywords:
- Sort Transformation Editor
ms.assetid: 8ae23970-49a9-4d6d-9f15-c7074783347c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9f48c366f4337af29b03877f6bb20b804457a293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685821"
---
# <a name="sort-transformation-editor"></a>Editor de Transformação Classificação
  Use a caixa de diálogo **Editor de Transformação Classificação** para selecionar as colunas a classificar, definir a ordem de classificação e especificar se as duplicatas devem ser removidas.  
  
 Para saber mais sobre a transformação Classificação, consulte [Sort Transformation](data-flow/transformations/sort-transformation.md).  
  
## <a name="options"></a>Opções  
 **Colunas de Entrada Disponíveis**  
 Usando as caixas de seleção, especifique as colunas a classificar.  
  
 **Nome**  
 Visualize o nome de cada coluna de entrada disponível.  
  
 **Passagem**  
 Indique se a coluna deve ser incluída na saída classificada.  
  
 **Coluna de Entrada**  
 Selecione colunas para cada linha na lista de colunas de entrada disponíveis. As seleções se refletem naquelas da caixa de seleção da tabela **Colunas de Entrada Disponíveis** .  
  
 **Alias de Saída**  
 Digite um alias para cada coluna de saída. O padrão é o nome da coluna de entrada; no entanto, é possível escolher qualquer nome descritivo exclusivo.  
  
 **Tipo de Classificação**  
 Indique se a classificação deve ser feita em ordem ascendente ou descendente.  
  
 **Sort Order**  
 Indique a ordem na qual classificar as colunas. Deve ser definido manualmente para cada coluna.  
  
 **Sinalizadores de Comparação**  
 Para obter mais informações sobre as opções de comparação de cadeias de caracteres, consulte [Comparando dados de cadeia de caracteres](data-flow/comparing-string-data.md).  
  
 **Remover linhas com valores de classificação duplicados**  
 Indique se a transformação deve copiar as linhas duplicadas para a saída ou criar uma única entrada para todas as duplicatas, seguindo as opções de comparação de cadeia de caracteres especificadas.  
  
## <a name="see-also"></a>Consulte Também  
 [Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
