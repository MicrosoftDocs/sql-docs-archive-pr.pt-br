---
title: Editor de transformação Union All | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unionalltransformation.f1
helpviewer_keywords:
- Union All Transformation Editor
ms.assetid: 32fbc1c1-da83-4684-9479-31fc3e2df98c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a7e84c106767aa897b2e419b51ca5b5c538501cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570745"
---
# <a name="union-all-transformation-editor"></a>Editor de Transformação Union All
  Use a caixa de diálogo **Editor de Transformação Union All** para mesclar vários conjuntos de linhas de entrada em um único conjunto de linhas de saída. Incluindo a transformação Union All em um fluxo de dados, é possível mesclar dados de vários fluxos de dados, criar conjuntos de dados complexos aninhando transformações Union All e mesclar as linhas novamente após corrigir erros nos dados.  
  
 Para saber mais sobre a transformação Union All, consulte [Union All Transformation](data-flow/transformations/union-all-transformation.md).  
  
## <a name="options"></a>Opções  
 **Nome da Coluna de Saída**  
 Digite um alias para cada coluna. O padrão é o nome da coluna de entrada da primeira entrada (referência); contudo, é possível escolher qualquer nome descritivo exclusivo.  
  
 **Union All Entrada 1**  
 Selecione a partir da lista de colunas de entrada disponíveis na primeira entrada (referência). Os metadados das colunas mapeadas devem ser correspondentes.  
  
 **Union All Entrada n**  
 Selecione a partir da lista de colunas de entrada disponíveis na segunda entrada e adicionais. Os metadados das colunas mapeadas devem ser correspondentes.  
  
## <a name="see-also"></a>Consulte Também  
 [Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Mesclar dados usando a transformação Union All](data-flow/transformations/merge-data-by-using-the-union-all-transformation.md)   
 [Transformação Mesclar](data-flow/transformations/merge-transformation.md)   
 [Transformação Junção de Mesclagem](data-flow/transformations/merge-join-transformation.md)  
  
  
