---
title: MultiPoint | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiPoint geometry subtype [SQL Server]
ms.assetid: 2aaab211-3aba-4dbd-90b7-095d997b1f62
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: b741071b7986aceea4e49d4fde8293ef2c96fc2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582909"
---
# <a name="multipoint"></a>MultiPoint
  Um `MultiPoint` é uma coleção de zero ou mais pontos. O limite de uma instância `MultiPoint` é vazio.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir cria uma instância `geometry MultiPoint` com SRID 23 e dois pontos: um ponto com as coordenadas (2, 3), um ponto com as coordenadas (7, 8) e um valor Z de 9,5.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('MULTIPOINT((2 3), (7 8 9.5))', 23);  
```  
  
 Essa instância `MultiPoint` também pode ser expressada usando `STMPointFromText()` conforme mostrado a seguir.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STMPointFromText('MULTIPOINT((2 3), (7 8 9.5))', 23);  
```  
  
 O exemplo a seguir usa o método `STGeometryN()` para recuperar uma descrição do primeiro ponto na coleção.  
  
```  
SELECT @g.STGeometryN(1).STAsText();  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Empresas](point.md)   
 [Dados espaciais &#40;SQL Server&#41;](spatial-data-sql-server.md)  
  
  
