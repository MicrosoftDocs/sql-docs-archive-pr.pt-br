---
title: Elemento de banco de dados para carga de trabalho (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database element
ms.assetid: 112fca2a-37e5-4162-b2e7-b56eb8ab0c6f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2774bc7ed981c84c966a394c95347208cbc6d656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678444"
---
# <a name="database-element-for-workload-dta"></a>Elemento de banco de dados para carga de trabalho (DTA)
  Especifica o banco de dados em que se encontra a tabela de rastreamento da carga de trabalho.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
<Workload>  
  <Database>  
   ...code removed here...  
  </Database>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Descrição|  
|--------------------|-----------------|  
|**Comprimento e tipo de dados**|Nenhum.|  
|**Valor padrão**|Nenhum.|  
|**Ocorrência**|Exigido uma vez se não houver outro tipo de carga de trabalho especificada. É preciso especificar um elemento filho `EventString`, `File` ou  `Database` para o pai `Workload`, mas só pode ser usado um tipo. Por exemplo, se uma carga de trabalho com o elemento `Database` for especificada, não será possível especificar uma carga de trabalho com o elemento `File` no mesmo arquivo XML de entrada.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elementos|  
|------------------|--------------|  
|**Elemento pai**|[Elemento Workload &#40;DTA&#41;](workload-element-dta.md)|  
|**Elementos filho**|[Elemento Name para Database &#40;DTA&#41;](name-element-for-database-dta.md)<br /><br /> [Elemento Schema para Database &#40;DTA&#41;](schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a>Comentários  
 Esse elemento tem o nome **DatabaseDetailsTypecomplexType** no Esquema XML do Orientador de Otimização do Mecanismo de Banco de Dados. Não confunda este elemento do `Database` com aquele cujo pai raiz é o elemento `Configuration`. (Consulte [Elemento Database para Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md).)  
  
## <a name="example"></a>Exemplo  
 Para obter um exemplo de uso desse `Database` elemento, consulte o exemplo de código no [elemento de carga de trabalho &#40;DTA&#41;](workload-element-dta.md).  
  
## <a name="see-also"></a>Consulte Também  
 [Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
