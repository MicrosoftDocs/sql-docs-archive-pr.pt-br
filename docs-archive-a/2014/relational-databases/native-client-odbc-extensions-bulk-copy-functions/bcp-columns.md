---
title: bcp_columns | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_columns
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_columns function
ms.assetid: 5376f6fe-9508-439a-8c66-778d77f19ac3
author: rothja
ms.author: jroth
ms.openlocfilehash: 028bb80e88a29b366e3a489abae06c8b3b30cdf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679939"
---
# <a name="bcp_columns"></a><span data-ttu-id="a297a-102">bcp_columns</span><span class="sxs-lookup"><span data-stu-id="a297a-102">bcp_columns</span></span>
  <span data-ttu-id="a297a-103">Define o número total de colunas encontrado no arquivo de usuário para uso com uma cópia em massa dentro ou fora do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a297a-103">Sets the total number of columns found in the user file for use with a bulk copy into or out of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a297a-104">[bcp_setbulkmode](bcp-setbulkmode.md) pode ser usado em vez de bcp_columns e [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="a297a-104">[bcp_setbulkmode](bcp-setbulkmode.md) can be used instead of bcp_columns and [bcp_colfmt](bcp-colfmt.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a297a-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a297a-105">Syntax</span></span>  
  
```  
  
RETCODE bcp_columns (  
HDBC   
hdbc  
,  
INT   
nColumns  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="a297a-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a297a-106">Arguments</span></span>  
 <span data-ttu-id="a297a-107">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="a297a-107">*hdbc*</span></span>  
 <span data-ttu-id="a297a-108">É o identificador de conexão ODBC habilitado para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="a297a-108">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="a297a-109">*nColumns*</span><span class="sxs-lookup"><span data-stu-id="a297a-109">*nColumns*</span></span>  
 <span data-ttu-id="a297a-110">É o número total de colunas no arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="a297a-110">Is the total number of columns in the user file.</span></span> <span data-ttu-id="a297a-111">Mesmo que você esteja se preparando para copiar dados em massa do arquivo de usuário para uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabela e não pretende copiar todas as colunas no arquivo de usuário, você ainda deve definir *nColumns* para o número total de colunas do arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="a297a-111">Even if you are preparing to bulk copy data from the user file to an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table and do not intend to copy all columns in the user file, you must still set *nColumns* to the total number of user-file columns.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="a297a-112">Retornos</span><span class="sxs-lookup"><span data-stu-id="a297a-112">Returns</span></span>  
 <span data-ttu-id="a297a-113">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="a297a-113">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a297a-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="a297a-114">Remarks</span></span>  
 <span data-ttu-id="a297a-115">Essa função pode ser chamada somente depois que [bcp_init](bcp-init.md) tiver sido chamado com um nome de arquivo válido.</span><span class="sxs-lookup"><span data-stu-id="a297a-115">This function can be called only after [bcp_init](bcp-init.md) has been called with a valid file name.</span></span>  
  
 <span data-ttu-id="a297a-116">Você só deveria chamar esta função se pretender usar um formato de arquivo de usuário diferente do padrão.</span><span class="sxs-lookup"><span data-stu-id="a297a-116">You should call this function only if you intend to use a user-file format that differs from the default.</span></span> <span data-ttu-id="a297a-117">Para obter mais informações sobre uma descrição do formato de arquivo de usuário padrão, consulte **bcp_init**.</span><span class="sxs-lookup"><span data-stu-id="a297a-117">For more information about a description of the default user-file format, see **bcp_init**.</span></span>  
  
 <span data-ttu-id="a297a-118">Depois de chamar `bcp_columns` , você deve chamar [bcp_colfmt](bcp-colfmt.md)para cada coluna no arquivo de usuário para definir completamente um formato de arquivo personalizado.</span><span class="sxs-lookup"><span data-stu-id="a297a-118">After calling `bcp_columns`, you must call [bcp_colfmt](bcp-colfmt.md)for each column in the user file to completely define a custom file format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a297a-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a297a-119">See Also</span></span>  
 [<span data-ttu-id="a297a-120">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="a297a-120">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
