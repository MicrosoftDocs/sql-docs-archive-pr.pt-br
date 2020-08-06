---
title: Replicação transacional bidirecional | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- bidirectional replication
- transactional replication, bidirectional replication
- bidirectional transactional replication
ms.assetid: 98772e95-67ed-4010-8108-5113dbe709ff
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 57b18dde2e7134e0ba9eb6a9b2e8f5357d171a55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574639"
---
# <a name="bidirectional-transactional-replication"></a><span data-ttu-id="42f0b-102">replicação transacional bidirecional</span><span class="sxs-lookup"><span data-stu-id="42f0b-102">Bidirectional Transactional Replication</span></span>
  <span data-ttu-id="42f0b-103">Replicação transacional bidirecional é uma topologia de replicação transacional específica que permite a dois servidores trocarem alterações entre si: cada servidor publica dados e, então, assina uma publicação com os mesmos dados do outro servidor.</span><span class="sxs-lookup"><span data-stu-id="42f0b-103">Bidirectional transactional replication is a specific transactional replication topology that allows two servers to exchange changes with each other: each server publishes data and then subscribes to a publication with the same data from the other server.</span></span> <span data-ttu-id="42f0b-104">O **@loopback_detection** parâmetro de [sp_addsubscription &#40;&#41;TRANSACT-SQL](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) é definido como true para garantir que as alterações sejam enviadas somente ao Assinante e não resultem na alteração de retorno ao Publicador.</span><span class="sxs-lookup"><span data-stu-id="42f0b-104">The **@loopback_detection** parameter of [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) is set to TRUE to ensure that changes are only sent to the Subscriber and do not result in the change being sent back to the Publisher.</span></span>  
  
 <span data-ttu-id="42f0b-105">Em [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] e versões posteriores, essa topologia também tem suporte para replicação transacional ponto a ponto, mas replicação bidirecional pode fornecer desempenho aprimorado.</span><span class="sxs-lookup"><span data-stu-id="42f0b-105">In [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] and later versions, this topology is also supported by peer-to-peer transactional replication, but bidirectional replication can provide improved performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42f0b-106">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="42f0b-106">See Also</span></span>  
 [<span data-ttu-id="42f0b-107">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="42f0b-107">Peer-to-Peer Transactional Replication</span></span>](peer-to-peer-transactional-replication.md)  
  
  
