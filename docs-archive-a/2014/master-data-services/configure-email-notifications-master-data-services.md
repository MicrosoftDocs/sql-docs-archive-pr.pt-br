---
title: Configurar notificações por email (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- e-mail [Master Data Services], configuring
- notifications [Master Data Services], configuring notifications
ms.assetid: 4241a6ab-7465-471b-9890-57c6b572037e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: baf60677435122af00f5ee5492e47bafaa45a3ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584187"
---
# <a name="configure-email-notifications-master-data-services"></a><span data-ttu-id="ffe4d-102">Configurar notificações por email (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ffe4d-102">Configure Email Notifications (Master Data Services)</span></span>
  <span data-ttu-id="ffe4d-103">Configure emails de notificação quando desejar que o [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] envie mensagens de email automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ffe4d-103">Configure notification emails when you want [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] to send email messages automatically.</span></span>  
  
### <a name="to-configure-notifications"></a><span data-ttu-id="ffe4d-104">Para configurar notificações</span><span class="sxs-lookup"><span data-stu-id="ffe4d-104">To configure notifications</span></span>  
  
1.  <span data-ttu-id="ffe4d-105">No [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)], na página **Banco de Dados** , selecione seu banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ffe4d-105">In [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)], on the **Database** page, select your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="ffe4d-106">Na seção **Configurações do Sistema** , clique em **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="ffe4d-106">In the **System Settings** section, click **Create Profile**.</span></span>  
  
3.  <span data-ttu-id="ffe4d-107">Preencha todos os campos obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="ffe4d-107">Complete all required fields.</span></span> <span data-ttu-id="ffe4d-108">Para obter mais informações, consulte [Caixa de diálogo Criar Perfil e Conta do Database Mail &#40;Gerenciador de Configuração do Master Data Services&#41;](../../2014/master-data-services/create-database-mail-profile-and-account-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="ffe4d-108">For more information, see [Create Database Mail Profile and Account Dialog Box &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-database-mail-profile-and-account-dialog-box.md).</span></span>  
  
4.  <span data-ttu-id="ffe4d-109">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffe4d-109">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ffe4d-110">Depois de configurar notificações, você não poderá usar o [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="ffe4d-110">After you configure notifications, you cannot use [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to make changes.</span></span> <span data-ttu-id="ffe4d-111">Você deve fazer alterações diretamente no banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ffe4d-111">You must make changes directly in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="ffe4d-112">Para obter mais informações, consulte [Database Mail Configuration Objects](../relational-databases/database-mail/database-mail-configuration-objects.md).</span><span class="sxs-lookup"><span data-stu-id="ffe4d-112">For more information, see [Database Mail Configuration Objects](../relational-databases/database-mail/database-mail-configuration-objects.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ffe4d-113">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="ffe4d-113">Next Steps</span></span>  
  
-   <span data-ttu-id="ffe4d-114">Existem configurações no [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] que afetam as notificações.</span><span class="sxs-lookup"><span data-stu-id="ffe4d-114">There are settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affect notifications.</span></span> <span data-ttu-id="ffe4d-115">Essas configurações podem ser ajustadas no [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] ou diretamente na tabela de Configurações do Sistema do banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ffe4d-115">You can adjust these settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="ffe4d-116">Para obter mais informações, veja [Configurações do sistema &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ffe4d-116">For more information, see [System Settings &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffe4d-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ffe4d-117">See Also</span></span>  
 <span data-ttu-id="ffe4d-118">[Master Data Services de notificações &#40;&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ffe4d-118">[Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span></span>  
 <span data-ttu-id="ffe4d-119">[Solucionando problemas de notificações por email (Master Data Services)](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx) </span><span class="sxs-lookup"><span data-stu-id="ffe4d-119">[Troubleshooting Email Notifications (Master Data Services)](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx) </span></span>  
 [<span data-ttu-id="ffe4d-120">Configurar regras de negócio para enviar notificações &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ffe4d-120">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md)  
  
  
