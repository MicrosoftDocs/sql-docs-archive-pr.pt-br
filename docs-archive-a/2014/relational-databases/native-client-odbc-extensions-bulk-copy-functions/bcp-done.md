---
title: bcp_done | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_done
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_done function
ms.assetid: e59b3f16-5b59-40da-880f-f3edf657d1ee
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9b0cbcc927fcd10c2d81b3c5c3d39bb80a8e9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568536"
---
# <a name="bcp_done"></a><span data-ttu-id="36a95-102">bcp_done</span><span class="sxs-lookup"><span data-stu-id="36a95-102">bcp_done</span></span>
  <span data-ttu-id="36a95-103">Termina uma cópia em massa de variáveis de programa para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executada com [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="36a95-103">Ends a bulk copy from program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performed with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36a95-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="36a95-104">Syntax</span></span>  
  
```  
  
DBINT bcp_done (  
    HDBC   
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="36a95-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="36a95-105">Arguments</span></span>  
 <span data-ttu-id="36a95-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="36a95-106">*hdbc*</span></span>  
 <span data-ttu-id="36a95-107">É o identificador de conexão ODBC habilitado para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="36a95-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="36a95-108">Retornos</span><span class="sxs-lookup"><span data-stu-id="36a95-108">Returns</span></span>  
 <span data-ttu-id="36a95-109">O número de linhas permanentemente salvas depois da última chamada para [bcp_batch](bcp-batch.md) , ou -1 em caso de erro.</span><span class="sxs-lookup"><span data-stu-id="36a95-109">The number of rows permanently saved after the last call to [bcp_batch](bcp-batch.md) or -1 in case of error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36a95-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="36a95-110">Remarks</span></span>  
 <span data-ttu-id="36a95-111">Chame **bcp_done** depois da última chamada para [bcp_sendrow](bcp-sendrow.md) ou [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="36a95-111">Call **bcp_done** after the last call to [bcp_sendrow](bcp-sendrow.md) or [bcp_moretext](bcp-moretext.md).</span></span> <span data-ttu-id="36a95-112">Falha ao chamar **bcp_done** depois de copiar todos os resultados de dados dos erros.</span><span class="sxs-lookup"><span data-stu-id="36a95-112">Failure to call **bcp_done** after copying all data results in errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a95-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="36a95-113">See Also</span></span>  
 [<span data-ttu-id="36a95-114">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="36a95-114">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
