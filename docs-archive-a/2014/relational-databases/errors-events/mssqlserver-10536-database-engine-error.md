---
title: MSSQLSERVER_10536 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10536 (Database Engine error)
ms.assetid: 9f97b41f-0ef8-4ad2-aec0-906a5d7522ba
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 00d08f4555f38b61661a917ba94c023f9dd6c4a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681679"
---
# <a name="mssqlserver_10536"></a><span data-ttu-id="da125-102">MSSQLSERVER_10536</span><span class="sxs-lookup"><span data-stu-id="da125-102">MSSQLSERVER_10536</span></span>
    
## <a name="details"></a><span data-ttu-id="da125-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="da125-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="da125-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="da125-104">Product Name</span></span>|<span data-ttu-id="da125-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="da125-105">SQL Server</span></span>|  
|<span data-ttu-id="da125-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="da125-106">Event ID</span></span>|<span data-ttu-id="da125-107">10536</span><span class="sxs-lookup"><span data-stu-id="da125-107">10536</span></span>|  
|<span data-ttu-id="da125-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="da125-108">Event Source</span></span>|<span data-ttu-id="da125-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="da125-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="da125-110">Componente</span><span class="sxs-lookup"><span data-stu-id="da125-110">Component</span></span>|<span data-ttu-id="da125-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="da125-111">SQLEngine</span></span>|  
|<span data-ttu-id="da125-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="da125-112">Symbolic Name</span></span>|<span data-ttu-id="da125-113">PG_TOO_MANY_STMTS</span><span class="sxs-lookup"><span data-stu-id="da125-113">PG_TOO_MANY_STMTS</span></span>|  
|<span data-ttu-id="da125-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="da125-114">Message Text</span></span>|<span data-ttu-id="da125-115">Não é possível criar o guia de plano '%.\*ls' porque o lote ou o módulo correspondente ao `@plan_handle` especificado contém mais de 1.000 instruções qualificadas.</span><span class="sxs-lookup"><span data-stu-id="da125-115">Cannot create plan guide '%.\*ls' because the batch or module corresponding to the specified `@plan_handle` contains more than 1000 eligible statements.</span></span> <span data-ttu-id="da125-116">Crie um guia de plano para cada instrução do lote ou módulo especificando um valor `statement_start_offset` para cada uma.</span><span class="sxs-lookup"><span data-stu-id="da125-116">Create a plan guide for each statement in the batch or module by specifying a `statement_start_offset` value for each statement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="da125-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="da125-117">Explanation</span></span>  
 <span data-ttu-id="da125-118">O lote ou o módulo correspondente ao `@plan_handle` especificado contém mais de 1000 instruções qualificadas.</span><span class="sxs-lookup"><span data-stu-id="da125-118">The batch or module corresponding to the specified `@plan_handle` contains more than 1000 eligible statements.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="da125-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="da125-119">User Action</span></span>  
 <span data-ttu-id="da125-120">Crie um guia de plano para cada instrução do lote ou módulo especificando um valor `statement_start_offset` para cada uma.</span><span class="sxs-lookup"><span data-stu-id="da125-120">Create a plan guide for each statement in the batch or module by specifying a `statement_start_offset` value for each statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da125-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="da125-121">See Also</span></span>  
 <span data-ttu-id="da125-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="da125-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="da125-123">[Guias de plano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="da125-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="da125-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="da125-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
