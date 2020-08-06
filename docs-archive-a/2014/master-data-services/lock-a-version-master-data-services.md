---
title: Bloquear uma versão (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- versions [Master Data Services], locking
- locking versions [Master Data Services]
ms.assetid: 7bb62a84-12d8-4b29-9b6e-6aa25410618e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 68ef979b14d9bd228c7ca89a260b31b2fc6efccd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684240"
---
# <a name="lock-a-version-master-data-services"></a><span data-ttu-id="6cc77-102">Bloquear uma versão (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="6cc77-102">Lock a Version (Master Data Services)</span></span>
  <span data-ttu-id="6cc77-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], bloqueie uma versão de um modelo para evitar alterações nos membros do modelo e em seus atributos.</span><span class="sxs-lookup"><span data-stu-id="6cc77-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], lock a version of a model to prevent changes to the model's members and their attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6cc77-104">Quando uma versão é bloqueada, os administradores do modelo podem continuar adicionando, editando e removendo membros.</span><span class="sxs-lookup"><span data-stu-id="6cc77-104">When a version is locked, model administrators can continue to add, edit, and remove members.</span></span> <span data-ttu-id="6cc77-105">Outros usuários com permissão para o modelo só podem exibir os membros.</span><span class="sxs-lookup"><span data-stu-id="6cc77-105">Other users with permission to the model can view members only.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6cc77-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6cc77-106">Prerequisites</span></span>  
 <span data-ttu-id="6cc77-107">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="6cc77-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="6cc77-108">Você deve ter permissão para acessar a área funcional **Gerenciamento de Versões** .</span><span class="sxs-lookup"><span data-stu-id="6cc77-108">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="6cc77-109">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="6cc77-109">You must be a model administrator.</span></span> <span data-ttu-id="6cc77-110">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6cc77-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="6cc77-111">O status da versão deve ser **Aberto**.</span><span class="sxs-lookup"><span data-stu-id="6cc77-111">The version's status must be **Open**.</span></span>  
  
### <a name="to-lock-a-version"></a><span data-ttu-id="6cc77-112">Para bloquear uma versão</span><span class="sxs-lookup"><span data-stu-id="6cc77-112">To lock a version</span></span>  
  
1.  <span data-ttu-id="6cc77-113">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Gerenciamento de Versões**.</span><span class="sxs-lookup"><span data-stu-id="6cc77-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="6cc77-114">Na página **Gerenciar Versões** , selecione a linha da versão que você deseja bloquear.</span><span class="sxs-lookup"><span data-stu-id="6cc77-114">On the **Manage Versions** page, select the row for the version that you want to lock.</span></span>  
  
3.  <span data-ttu-id="6cc77-115">Clique em **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="6cc77-115">Click **Lock**.</span></span>  
  
4.  <span data-ttu-id="6cc77-116">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cc77-116">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6cc77-117">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="6cc77-117">Next Steps</span></span>  
  
-   [<span data-ttu-id="6cc77-118">Validar uma versão em relação a regras de negócio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6cc77-118">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="6cc77-119">Confirmar uma versão &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6cc77-119">Commit a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/commit-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="6cc77-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6cc77-120">See Also</span></span>  
 <span data-ttu-id="6cc77-121">[Versões &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="6cc77-121">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="6cc77-122">Desbloquear uma versão &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6cc77-122">Unlock a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/unlock-a-version-master-data-services.md)  
  
  