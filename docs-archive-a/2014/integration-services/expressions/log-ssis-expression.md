---
title: LOG (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- base-10 logarithms
- LOG function
ms.assetid: f7fccace-c178-4e13-bde9-7dc4ef1d98fa
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0de84c1a92f94507bcc69c47cc4d9b6cda50a4f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575963"
---
# <a name="log-ssis-expression"></a>LOG (Expressão SSIS)
  Retorna o logaritmo de base 10 de uma expressão numérica.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
LOG(numeric_expression)  
```  
  
## <a name="arguments"></a>Argumentos  
 *numeric_expression*  
 É uma expressão numérica válida não zero ou não negativa.  
  
## <a name="result-types"></a>Tipos de resultado  
 DT_R8  
  
## <a name="remarks"></a>Comentários  
 A *expressão numérica* é convertida para o tipo de dados DT_R8 antes de o logaritmo ser computado. Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).  
  
 Se *numeric_expression* for avaliado como zero ou um valor negativo, o resultado de retorno será nulo.  
  
## <a name="expression-examples"></a>Exemplos de expressões  
 Esse exemplo usa um literal numérico. A função retorna o valor 1.988291341907488.  
  
```  
LOG(97.34)  
```  
  
 Esse exemplo usa a coluna **Length**. Se o valor da coluna for 101.24, a função retornará 2.005352136486217.  
  
```  
LOG(Length)   
```  
  
 Esse exemplo usa a variável **Length**. A variável deve ter um tipo de dados numérico ou a expressão deve incluir uma conversão explícita para um tipo de dados [!INCLUDE[ssIS](../../includes/ssis-md.md)] numérico. Se **Length** for 234.567, a função retornará 2.370266913465859.  
  
```  
LOG(@Length)   
```  
  
## <a name="see-also"></a>Consulte Também  
 [EXP &#40;Expressão SSIS&#41;](exp-ssis-expression.md)   
 [LN &#40;Expressão SSIS&#41;](ln-ssis-expression.md)   
 [Funções &#40;Expressão do SSIS&#41;](functions-ssis-expression.md)  
  
  
