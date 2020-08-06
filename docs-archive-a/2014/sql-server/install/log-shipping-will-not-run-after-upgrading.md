---
title: O envio de logs não será executado após a atualização | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server]
ms.assetid: 6727cb7d-ac01-4972-a730-dbb7cdc29705
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b2af60743cb2cbf9bf455397fe052c4e81f5a06d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583349"
---
# <a name="log-shipping-will-not-run-after-upgrading"></a><span data-ttu-id="67cf0-102">Envio de log não executará após a atualização</span><span class="sxs-lookup"><span data-stu-id="67cf0-102">Log shipping will not run after upgrading</span></span>
  <span data-ttu-id="67cf0-103">O Supervisor de Atualização detectou que você está usando envio de logs.</span><span class="sxs-lookup"><span data-stu-id="67cf0-103">Upgrade Advisor has detected that you are using log shipping.</span></span> <span data-ttu-id="67cf0-104">O envio de log do [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] não é compatível como o envio de log do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] e não pode ser atualizado diretamente.</span><span class="sxs-lookup"><span data-stu-id="67cf0-104">[!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] log shipping is incompatible with log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] and cannot be upgraded directly.</span></span> <span data-ttu-id="67cf0-105">Depois da atualização para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], reconfigure o envio de log usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="67cf0-105">After upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], reconfigure log shipping using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or stored procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67cf0-106">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="67cf0-106">See Also</span></span>  
 <span data-ttu-id="67cf0-107">[SQL Server Agent categoria de trabalho de envio de logs faz com que a atualização falhe](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span><span class="sxs-lookup"><span data-stu-id="67cf0-107">[SQL Server Agent log shipping job category causes upgrade to fail](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span></span>  
 <span data-ttu-id="67cf0-108">[A atualização alterará o SQL Server Agent conta proxy do usuário para o UpgradedProxyAccount temporário](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span><span class="sxs-lookup"><span data-stu-id="67cf0-108">[Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span></span>  
 <span data-ttu-id="67cf0-109">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="67cf0-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="67cf0-110">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="67cf0-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
