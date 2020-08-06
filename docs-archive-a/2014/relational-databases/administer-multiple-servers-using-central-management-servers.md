---
title: Administrar vários servidores usando os Servidores Centrais de Gerenciamento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- multiserver queries
- central management server
- multiserver administration [SQL Server]
- master servers [SQL Server], central management servers
- target configuration [SQL Server]
- server configuration [SQL Server]
ms.assetid: 427911a7-57d4-4542-8846-47c3267a5d9c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3906165b595f6faa15812f70377a3bc0f550e52e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680499"
---
# <a name="administer-multiple-servers-using-central-management-servers"></a><span data-ttu-id="957fa-102">Administrar vários servidores usando os Servidores Centrais de Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="957fa-102">Administer Multiple Servers Using Central Management Servers</span></span>
  <span data-ttu-id="957fa-103">Você pode administrar vários servidores designando servidores de gerenciamento centrais e criando grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="957fa-103">You can administer multiple servers by designating Central Management Servers and creating server groups.</span></span>  
  
## <a name="benefits-of-central-management-servers-and-server-groups"></a><span data-ttu-id="957fa-104">Benefícios dos Servidores Centrais de Gerenciamento e grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="957fa-104">Benefits of Central Management Servers and Server Groups</span></span>  
 <span data-ttu-id="957fa-105">Uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], que é designada como um Servidor Central de Gerenciamento, mantém grupos de servidores que contêm as informações de conexão de uma ou mais instâncias do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="957fa-105">An instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that is designated as a Central Management Server maintains server groups that contain the connection information for one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="957fa-106">As instruções [!INCLUDE[tsql](../includes/tsql-md.md)] e as políticas de gerenciamento baseado em política podem ser executadas ao mesmo tempo nos grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="957fa-106">[!INCLUDE[tsql](../includes/tsql-md.md)] statements and Policy-Based Management policies can be executed at the same time against server groups.</span></span> <span data-ttu-id="957fa-107">Você também pode exibir os arquivos de log [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] em instâncias que são gerenciadas por um Servidor de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="957fa-107">You can also view the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] log files on instances that are managed through a Central Management Server.</span></span> <span data-ttu-id="957fa-108">As versões do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] anteriores ao [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] não podem ser designadas como um Servidor de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="957fa-108">Versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] cannot be designated as a Central Management Server.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="957fa-109">também podem ser executadas nos grupos de servidor locais em Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="957fa-109">statements can also be executed against local server groups in Registered Servers.</span></span>  
  
### <a name="related-tasks"></a><span data-ttu-id="957fa-110">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="957fa-110">Related Tasks</span></span>  
 <span data-ttu-id="957fa-111">Para criar um Servidor de Gerenciamento Central e grupos de servidores, use a janela **Servidores Registrados** no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="957fa-111">To create a Central Management Server and server groups, use the **Registered Servers** window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="957fa-112">Observe que o Servidor Central de Gerenciamento não pode ser membro de um grupo que o mantém.</span><span class="sxs-lookup"><span data-stu-id="957fa-112">Note that the Central Management Server cannot be a member of a group that it maintains.</span></span> <span data-ttu-id="957fa-113">Para obter mais informações sobre como criar Servidores de Gerenciamento Central e grupos de servidores, consulte [Criar um Servidor de Gerenciamento Central e Grupo de Servidores &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md).</span><span class="sxs-lookup"><span data-stu-id="957fa-113">For more information about how to create Central Management Servers and server groups, see [Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="957fa-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="957fa-114">See Also</span></span>  
 [<span data-ttu-id="957fa-115">Administrar servidores com Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="957fa-115">Administer Servers by Using Policy-Based Management</span></span>](policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
