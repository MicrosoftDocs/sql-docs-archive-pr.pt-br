---
title: Suporte a namespace no modo PATH | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode, namespace support
- namespaces [XML in SQL Server]
ms.assetid: 5f128ea2-0ceb-4b23-bce7-c8b3fd615466
author: rothja
ms.author: jroth
ms.openlocfilehash: abd6cd1f5590bffcd841b07897c9685faed4726f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679192"
---
# <a name="namespace-support-in-path-mode"></a>Suporte a namespace em modo PATH
  O suporte a namespace em modo PATH é fornecido usando WITH NAMESPACES. Por exemplo, a consulta a seguir demonstra a sintaxe de WITH NAMESPACES para declarar um namespace ("a:") que pode , em seguida, ser usado na instrução SELECT subsequente.  
  
```  
WITH XMLNAMESPACES('a' as a)  
SELECT 1 as 'a:b'  
FOR XML PATH  
```  
  
## <a name="examples"></a>Exemplos  
 Esses exemplos ilustram o uso do modo PATH para gerar XML de uma consulta SELECT. Muitas dessas consultas são especificadas em relação a documentos XML de instruções da fabricação de bicicletas que são armazenados na coluna Instructions da tabela ProductModel.  
  
## <a name="see-also"></a>Consulte Também  
 [Usar o modo PATH com FOR XML](use-path-mode-with-for-xml.md)  
  
  
