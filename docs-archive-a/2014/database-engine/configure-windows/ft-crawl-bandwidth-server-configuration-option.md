---
title: Opção de configuração de servidor ft crawl bandwidth | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- large memory buffers
- memory [SQL Server], buffers
- ft crawl bandwidth option
ms.assetid: e5864ad9-92f5-43b5-95de-46d68ded8694
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 33821ff1fdbc4248c71906d8307a8164a7f64d24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685265"
---
# <a name="ft-crawl-bandwidth-server-configuration-option"></a><span data-ttu-id="035b0-102">Opção de configuração de servidor ft crawl bandwidth</span><span class="sxs-lookup"><span data-stu-id="035b0-102">ft crawl bandwidth Server Configuration Option</span></span>
  <span data-ttu-id="035b0-103">Use a opção **ft crawl bandwidth** para especificar o tamanho até o qual o pool de buffers de memória grandes pode se expandir.</span><span class="sxs-lookup"><span data-stu-id="035b0-103">Use the **ft crawl bandwidth** option to specify the size to which the pool of large memory buffers can grow.</span></span> <span data-ttu-id="035b0-104">Buffers de memória grandes têm o tamanho de 4 MB (megabytes).</span><span class="sxs-lookup"><span data-stu-id="035b0-104">Large memory buffers are 4 megabytes (MB) in size.</span></span> <span data-ttu-id="035b0-105">O valor do parâmetro **max** especifica o número máximo de buffers que o gerenciador de memória de texto completo deve manter em um pool de buffers grandes.</span><span class="sxs-lookup"><span data-stu-id="035b0-105">The **max** parameter value specifies the maximum number of buffers that the full-text memory manager should maintain in a large buffer pool.</span></span> <span data-ttu-id="035b0-106">Se o valor de **max** for zero, não haverá limite máximo ao número de buffers no pool de buffers grandes.</span><span class="sxs-lookup"><span data-stu-id="035b0-106">If the **max** value is zero, then there is no upper limit to the number of buffers that can be in a large buffer pool.</span></span>  
  
 <span data-ttu-id="035b0-107">O valor do parâmetro **min** especifica o número mínimo de buffers de memória que deve ser mantido no pool de buffers de memória grandes.</span><span class="sxs-lookup"><span data-stu-id="035b0-107">The **min** parameter specifies the minimum number of memory buffers that must be maintained in the pool of large memory buffers.</span></span> <span data-ttu-id="035b0-108">Mediante solicitação do gerenciador de memória do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], todos os pools de buffers extras serão liberados, mas esse número mínimo de buffers será mantido.</span><span class="sxs-lookup"><span data-stu-id="035b0-108">Upon request from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory manager, all extra buffer pools will be released but this minimum number of buffers will be maintained.</span></span> <span data-ttu-id="035b0-109">Se, contudo, o valor especificado de **min** for zero, todos os buffers de memória serão liberados.</span><span class="sxs-lookup"><span data-stu-id="035b0-109">If, however, the **min** value specified is zero, then all memory buffers are released.</span></span>  
  
 <span data-ttu-id="035b0-110">Em algumas circunstâncias, o número de buffers alocados atualmente é menor que o valor especificado pelo parâmetro **min** .</span><span class="sxs-lookup"><span data-stu-id="035b0-110">Under certain circumstances, the number of buffers currently allocated is less than the value specified by the **min** parameter.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="035b0-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="035b0-111">See Also</span></span>  
 <span data-ttu-id="035b0-112">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="035b0-112">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="035b0-113">[Opção de configuração de servidor ft notify bandwidth](ft-notify-bandwidth-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="035b0-113">[ft notify bandwidth Server Configuration Option](ft-notify-bandwidth-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="035b0-114">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="035b0-114">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
