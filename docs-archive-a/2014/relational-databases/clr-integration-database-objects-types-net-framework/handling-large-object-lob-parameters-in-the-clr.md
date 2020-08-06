---
title: Manipulando parâmetros de LOB (objeto grande) no CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- large data, CLR integration
- LOB data [SQL Server], CLR integration
- SqlBytes data type
- SqlChars data type
ms.assetid: d07956f6-9543-4476-9426-536f95991150
author: rothja
ms.author: jroth
ms.openlocfilehash: ee791c73a6610761c2086723f9e41c2351b37dd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685784"
---
# <a name="handling-large-object-lob-parameters-in-the-clr"></a><span data-ttu-id="c9ad9-102">Manipulando parâmetros de LOB (objeto grande) no CLR</span><span class="sxs-lookup"><span data-stu-id="c9ad9-102">Handling Large Object (LOB) Parameters in the CLR</span></span>
  <span data-ttu-id="c9ad9-103">Use `SqlBytes` e `SqlChars` para passar parâmetros dos tipos objeto grande binário (LOB) (`varbinary(max)`) e caractere LOB (`nvarchar(max)`), respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c9ad9-103">Use `SqlBytes` and `SqlChars` to pass large object (LOB) binary type (`varbinary(max)`) and LOB character type (`nvarchar(max)`) parameters, respectively.</span></span> <span data-ttu-id="c9ad9-104">Estes tipos permitem o fluxo contínuo de valores LOB do banco de dados para a rotina CLR (common language runtime), em vez de copiar todo o valor para o espaço gerenciado.</span><span class="sxs-lookup"><span data-stu-id="c9ad9-104">These types allow streaming the LOB values from the database to the common language runtime (CLR) routine, instead of copying the entire value into managed space.</span></span> <span data-ttu-id="c9ad9-105">`SqlBinary` e `SqlString` devem ser usados somente para valores baixos de cadeia de caracteres e binários.</span><span class="sxs-lookup"><span data-stu-id="c9ad9-105">`SqlBinary` and `SqlString` should be used only for small binary and character string values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9ad9-106">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c9ad9-106">See Also</span></span>  
 [<span data-ttu-id="c9ad9-107">Tipos de dados do SQL Server no .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c9ad9-107">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
