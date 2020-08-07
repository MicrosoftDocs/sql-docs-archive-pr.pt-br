---
title: MSSQLSERVER_21893 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21893 (Database Engine error)
ms.assetid: 1ab1195a-fe2a-4e06-b871-b177b6bea1fe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 92479d7727ac2300d6a60d02492667d99a69b022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576440"
---
# <a name="mssqlserver_21893"></a><span data-ttu-id="a5339-102">MSSQLSERVER_21893</span><span class="sxs-lookup"><span data-stu-id="a5339-102">MSSQLSERVER_21893</span></span>
    
## <a name="details"></a><span data-ttu-id="a5339-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a5339-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a5339-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a5339-104">Product Name</span></span>|<span data-ttu-id="a5339-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a5339-105">SQL Server</span></span>|  
|<span data-ttu-id="a5339-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a5339-106">Event ID</span></span>|<span data-ttu-id="a5339-107">21893</span><span class="sxs-lookup"><span data-stu-id="a5339-107">21893</span></span>|  
|<span data-ttu-id="a5339-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a5339-108">Event Source</span></span>|<span data-ttu-id="a5339-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a5339-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a5339-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a5339-110">Component</span></span>|<span data-ttu-id="a5339-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a5339-111">SQLEngine</span></span>|  
|<span data-ttu-id="a5339-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="a5339-112">Symbolic Name</span></span>|<span data-ttu-id="a5339-113">SQLErrorNum21893</span><span class="sxs-lookup"><span data-stu-id="a5339-113">SQLErrorNum21893</span></span>|  
|<span data-ttu-id="a5339-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a5339-114">Message Text</span></span>|<span data-ttu-id="a5339-115">Os assinantes (%s) do publicador original '%s' não aparecem como servidores remotos no publicador redirecionado '%s'.</span><span class="sxs-lookup"><span data-stu-id="a5339-115">The subscribers ( %s ) of original publisher '%s' do not appear as remote servers at redirected publisher '%s'.</span></span> <span data-ttu-id="a5339-116">Execute `sp_addlinkedserver` no Publicador Redirecionado para adicionar esses assinantes como servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="a5339-116">Run `sp_addlinkedserver` at the redirected publisher to add these subscribers as remote servers .</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a5339-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="a5339-117">Explanation</span></span>  
 <span data-ttu-id="a5339-118">`sp_validate_redirected_publisher` usa as tabelas de metadados de assinatura do banco de dados publicador no servidor remoto para identificar seus assinantes associados e verifica se há entradas associadas em master.dbo.sysservers para os assinantes.</span><span class="sxs-lookup"><span data-stu-id="a5339-118">`sp_validate_redirected_publisher` uses the subscription metadata tables of the publisher database at the remote server to identify its associated subscribers and verifies that there are associated entries in master.dbo.sysservers for the subscribers.</span></span> <span data-ttu-id="a5339-119">Este erro será retornado se algum assinante identificado não estiver presente.</span><span class="sxs-lookup"><span data-stu-id="a5339-119">This error is returned if any of the identified subscribers are not present.</span></span>  
  
 <span data-ttu-id="a5339-120">Este erro não é considerado fatal.</span><span class="sxs-lookup"><span data-stu-id="a5339-120">This error is not considered a fatal error.</span></span> <span data-ttu-id="a5339-121">Os agentes que encontrarem este erro o registrará em log como erro informativo, mas não finalizarão, já que a falta entradas de assinante apropriadas no novo publicador limitou o impacto na replicação.</span><span class="sxs-lookup"><span data-stu-id="a5339-121">Agents encountering this error will log the error as informational but will not terminate, since a failure to have appropriate subscriber entries at the new publisher has limited impact on replication.</span></span> <span data-ttu-id="a5339-122">Sem uma entrada apropriada para um assinante em sysservers, algumas atividades de gerenciamento de assinatura podem falhar quando executadas por meio do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5339-122">Without an appropriate entry for a subscriber in sysservers, some subscription management activities may fail when executed through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="a5339-123">No entanto, essas mesmas atividades podem ser realizadas com êxito, executando explicitamente os procedimentos armazenados de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="a5339-123">However, these same activities can be successfully performed by executing the management stored procedures explicitly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a5339-124">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a5339-124">User Action</span></span>  
 <span data-ttu-id="a5339-125">Execute `sp_addlinkedserver` no publicador redirecionado para cada assinante identificado, a fim de adicioná-los como servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="a5339-125">Run `sp_addlinkedserver` at the redirected publisher for each of the identified subscribers to add them as remote servers.</span></span> <span data-ttu-id="a5339-126">Em seguida, execute `sp_serveroption` para definir o bit do assinante para o servidor.</span><span class="sxs-lookup"><span data-stu-id="a5339-126">Then, run `sp_serveroption` to set the subscriber bit for the server.</span></span>  
  
  
