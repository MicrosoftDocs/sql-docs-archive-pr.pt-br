---
title: 'Exemplo: especificando XSINIL com a diretiva ELEMENTS | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, specifying XSINIL example
ms.assetid: 07c873ff-1f9d-480e-8536-862c39eb8249
author: rothja
ms.author: jroth
ms.openlocfilehash: 7817d2c72909ca66fb9fac10f8fcb32a759faf56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678666"
---
# <a name="example-specifying-xsinil-with-the-elements-directive"></a><span data-ttu-id="e2eba-102">Exemplo: especificando XSINIL com a política ELEMENTS</span><span class="sxs-lookup"><span data-stu-id="e2eba-102">Example: Specifying XSINIL with the ELEMENTS Directive</span></span>
  <span data-ttu-id="e2eba-103">A consulta a seguir especifica a política `ELEMENTS` para gerar XML centrado em elemento a partir do resultado da consulta.</span><span class="sxs-lookup"><span data-stu-id="e2eba-103">The following query specifies the `ELEMENTS` directive to generate element-centric XML from the query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2eba-104">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e2eba-104">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductID, Name, Color  
FROM Production.Product  
FOR XML RAW, ELEMENTS;  
GO  
```  
  
 <span data-ttu-id="e2eba-105">Este é o resultado parcial.</span><span class="sxs-lookup"><span data-stu-id="e2eba-105">This is the partial result.</span></span>  
  
```  
<row>  
  <ProductID>1</ProductID>  
  <Name>Adjustable Race</Name>  
</row>  
...  
<row>  
  <ProductID>317</ProductID>  
  <Name>LL Crankarm</Name>  
  <Color>Black</Color>  
</row>  
```  
  
 <span data-ttu-id="e2eba-106">Como a coluna `Color` tem valores nulos para alguns produtos, o XML resultante não gerará o elemento <`Color`> correspondente.</span><span class="sxs-lookup"><span data-stu-id="e2eba-106">Because the `Color` column has null values for some products, the resulting XML will not generate the corresponding <`Color`> element.</span></span> <span data-ttu-id="e2eba-107">Adicionando a política `XSINIL` com `ELEMENTS`, é possível gerar o elemento <`Color`> mesmo para valores de cor NULL no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="e2eba-107">By adding the `XSINIL` directive with `ELEMENTS`, you can generate the <`Color`> element even for NULL color values in the result set.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductID, Name, Color  
FROM Production.Product  
FOR XML RAW, ELEMENTS XSINIL ;  
```  
  
 <span data-ttu-id="e2eba-108">Este é o resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="e2eba-108">This is the partial result:</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <ProductID>1</ProductID>  
  <Name>Adjustable Race</Name>  
  <Color xsi:nil="true" />  
</row>  
...  
<row>  
  <ProductID>317</ProductID>  
  <Name>LL Crankarm</Name>  
  <Color>Black</Color>  
</row>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2eba-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e2eba-109">See Also</span></span>  
 [<span data-ttu-id="e2eba-110">Usar o modo RAW com FOR XML</span><span class="sxs-lookup"><span data-stu-id="e2eba-110">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  