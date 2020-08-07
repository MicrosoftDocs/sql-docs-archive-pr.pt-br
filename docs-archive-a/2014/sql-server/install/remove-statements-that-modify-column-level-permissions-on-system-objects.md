---
title: Remover instruções que modificam permissões em nível de coluna em objetos do sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- column-level permissions [SQL Server]
- removed statement permissions [SQL Server]
ms.assetid: 7f4fbbef-2696-4911-903b-63f6d9e4484a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e55af3dca0c55c2babd09bc6cfc48ed0ddf3ad7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576154"
---
# <a name="remove-statements-that-modify-column-level-permissions-on-system-objects"></a><span data-ttu-id="eddd3-102">Remover instruções que modificam permissões em nível de coluna nos objetos do sistema</span><span class="sxs-lookup"><span data-stu-id="eddd3-102">Remove statements that modify column-level permissions on system objects</span></span>
  <span data-ttu-id="eddd3-103">O Supervisor de Atualização detectou permissões em nível de coluna não padrão nos objetos do sistema.</span><span class="sxs-lookup"><span data-stu-id="eddd3-103">The Upgrade Advisor detected nonstandard column-level permissions on system objects.</span></span> <span data-ttu-id="eddd3-104">Essas alterações de permissão não serão mantidas quando você fizer a atualização.</span><span class="sxs-lookup"><span data-stu-id="eddd3-104">These permission changes will not be maintained when you upgrade.</span></span> <span data-ttu-id="eddd3-105">Além disso, não há mais suporte para permissões em nível de coluna nos objetos do sistema em versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="eddd3-105">Additionally, column-level permissions on system objects are no longer supported.</span></span> <span data-ttu-id="eddd3-106">Remova as instruções que definem permissões em nível de coluna nos objetos do sistema dos seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="eddd3-106">Remove statements from your applications that set column-level permissions on system objects.</span></span>  
  
## <a name="component"></a><span data-ttu-id="eddd3-107">Componente</span><span class="sxs-lookup"><span data-stu-id="eddd3-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="eddd3-108">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="eddd3-108">Corrective Action</span></span>  
 <span data-ttu-id="eddd3-109">Remova as instruções do seu aplicativo que concedem, negam ou revocam permissões em nível de coluna dos objetos do sistema.</span><span class="sxs-lookup"><span data-stu-id="eddd3-109">Remove statements from your application that grant, deny, or revoke column-level permissions on system objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eddd3-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eddd3-110">See Also</span></span>  
 <span data-ttu-id="eddd3-111">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="eddd3-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="eddd3-112">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="eddd3-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
