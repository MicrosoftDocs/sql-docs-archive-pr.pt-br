---
title: Elemento de esquema para banco de dados (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Schema element
ms.assetid: d932e59c-953f-4ab4-934d-b6baf344835c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7653177878f3a832abd2d1ca266bc5feb17b9a29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570416"
---
# <a name="schema-element-for-database-dta"></a>Elemento de esquema para banco de dados (DTA)
  Especifica o esquema do banco de dados que você deseja ajustar.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
<Database>  
...code removed here...  
    <Schema>...</Schema>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Descrição|  
|--------------------|-----------------|  
|**Comprimento e tipo de dados**|Nenhum.|  
|**Valor padrão**|Nenhum.|  
|**Ocorrência**|Exigido uma vez para o elemento do **Banco de Dados** especificado no elemento **Servidor** .|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elementos|  
|------------------|--------------|  
|**Elemento pai**|[Elemento Database para Server &#40;DTA&#41;](database-element-for-server-dta.md)|  
|**Elementos filho**|[Elemento Name para Schema &#40;DTA&#41;](name-element-for-schema-dta.md)<br /><br /> [Elemento Table para Schema &#40;DTA&#41;](table-element-for-schema-dta.md)|  
  
## <a name="example"></a>Exemplo  
 Para obter um exemplo de uso desse elemento, consulte [Elemento Server &#40;DTA&#41;](server-element-dta.md).  
  
## <a name="see-also"></a>Consulte Também  
 [Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
