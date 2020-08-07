---
title: Segurança do Queue Reader Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.QRA.f1
helpviewer_keywords:
- Queue Reader Agent Security dialog box
ms.assetid: 77938da0-2afd-4455-8826-f4a6a9440cb3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 22a5e5751184b626ab1af86f01782a42028b5ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582420"
---
# <a name="queue-reader-agent-security"></a><span data-ttu-id="32218-102">Segurança do Agente de Leitor de Fila</span><span class="sxs-lookup"><span data-stu-id="32218-102">Queue Reader Agent Security</span></span>
  <span data-ttu-id="32218-103">A caixa de diálogo **Segurança do Agente de Leitor de Fila** permite que você especifique a conta [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows na qual o Agente de Leitor de Fila executa e faz conexões locais com o Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="32218-103">The **Queue Reader Agent Security** dialog box allows you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Queue Reader Agent runs and makes local connections to the Distributor.</span></span> <span data-ttu-id="32218-104">O agente se conecta ao Publicador usando a conta especificada na caixa de diálogo **Propriedades do Publicador** (disponível na caixa de diálogo **Propriedades do Distribuidor** ); o agente se conecta ao Assinante usando o mesmo contexto do Agente de Distribuição para a assinatura.</span><span class="sxs-lookup"><span data-stu-id="32218-104">The agent connects to the Publisher using the account specified in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box); the agent connects to the Subscriber using the same context as the Distribution Agent for the subscription.</span></span> <span data-ttu-id="32218-105">Para obter mais informações, consulte [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="32218-105">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="32218-106">A conta deve ser válida, com a senha correta especificada.</span><span class="sxs-lookup"><span data-stu-id="32218-106">The account must be valid with the correct password specified.</span></span> <span data-ttu-id="32218-107">Contas e senhas não são validadas até que um agente seja executado.</span><span class="sxs-lookup"><span data-stu-id="32218-107">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="32218-108">Opções</span><span class="sxs-lookup"><span data-stu-id="32218-108">Options</span></span>  
 <span data-ttu-id="32218-109">**Conta do processo**</span><span class="sxs-lookup"><span data-stu-id="32218-109">**Process account**</span></span>  
 <span data-ttu-id="32218-110">Insira uma conta do Windows na qual o Agente de Leitor de Fila seja executado no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="32218-110">Enter a Windows account under which the Queue Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="32218-111">A conta do Windows especificada deve ser, no mínimo, um membro da função de banco de dados fixa **db_owner** no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="32218-111">The Windows account you specify must at minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
 <span data-ttu-id="32218-112">**Senha** e **Confirmar Senha**</span><span class="sxs-lookup"><span data-stu-id="32218-112">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="32218-113">Insira a senha para a conta do Windows.</span><span class="sxs-lookup"><span data-stu-id="32218-113">Enter the password for the Windows account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32218-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32218-114">See Also</span></span>  
 <span data-ttu-id="32218-115">[Gerenciar logons e senhas na replicação](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="32218-115">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="32218-116">[Modelo de segurança do agente de replicação](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="32218-116">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="32218-117">[Visão geral dos agentes de replicação](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="32218-117">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="32218-118">Replication Security Best Practices</span><span class="sxs-lookup"><span data-stu-id="32218-118">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  