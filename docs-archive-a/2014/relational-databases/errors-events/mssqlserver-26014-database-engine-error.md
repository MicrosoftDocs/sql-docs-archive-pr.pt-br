---
title: MSSQLSERVER_26014 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 26014 (Database Engine error)
ms.assetid: e2b0dfc7-0681-4e5d-8875-1d5f63534086
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8114183b212767d01013eee9387d8b2efa2e0d7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574041"
---
# <a name="mssqlserver_26014"></a><span data-ttu-id="f869e-102">MSSQLSERVER_26014</span><span class="sxs-lookup"><span data-stu-id="f869e-102">MSSQLSERVER_26014</span></span>
    
## <a name="details"></a><span data-ttu-id="f869e-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="f869e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f869e-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="f869e-104">Product Name</span></span>|<span data-ttu-id="f869e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f869e-105">SQL Server</span></span>|  
|<span data-ttu-id="f869e-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="f869e-106">Event ID</span></span>|<span data-ttu-id="f869e-107">26014</span><span class="sxs-lookup"><span data-stu-id="f869e-107">26014</span></span>|  
|<span data-ttu-id="f869e-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="f869e-108">Event Source</span></span>|<span data-ttu-id="f869e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f869e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f869e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f869e-110">Component</span></span>|<span data-ttu-id="f869e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f869e-111">SQLEngine</span></span>|  
|<span data-ttu-id="f869e-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="f869e-112">Symbolic Name</span></span>|<span data-ttu-id="f869e-113">SNI_SSL_USER_CERT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="f869e-113">SNI_SSL_USER_CERT_FAILURE</span></span>|  
|<span data-ttu-id="f869e-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="f869e-114">Message Text</span></span>|<span data-ttu-id="f869e-115">Não foi possível carregar o certificado especificado pelo usuário [Cert Hash (sha1) "% hs"].</span><span class="sxs-lookup"><span data-stu-id="f869e-115">Unable to load user-specified certificate [Cert Hash(sha1) "%hs"].</span></span> <span data-ttu-id="f869e-116">O servidor não aceitará uma conexão.</span><span class="sxs-lookup"><span data-stu-id="f869e-116">The server will not accept a connection.</span></span> <span data-ttu-id="f869e-117">Verifique se o certificado está instalado corretamente.</span><span class="sxs-lookup"><span data-stu-id="f869e-117">You should verify that the certificate is correctly installed.</span></span> <span data-ttu-id="f869e-118">Consulte "Configuring Certificate for Use by SSL" nos Manuais Online (em inglês).</span><span class="sxs-lookup"><span data-stu-id="f869e-118">See "Configuring Certificate for Use by SSL" in Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f869e-119">Explicação</span><span class="sxs-lookup"><span data-stu-id="f869e-119">Explanation</span></span>  
 <span data-ttu-id="f869e-120">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tentou carregar o certificado indicado na mensagem, mas a operação não foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="f869e-120">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] attempted to load the certificate named in the message but the operation failed.</span></span> <span data-ttu-id="f869e-121">Esse problema deve ser resolvido para que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possa usar o certificado.</span><span class="sxs-lookup"><span data-stu-id="f869e-121">This problem must be resolved before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can use this certificate.</span></span>  
  
 <span data-ttu-id="f869e-122">As possíveis causas do erro incluem as seguintes:</span><span class="sxs-lookup"><span data-stu-id="f869e-122">Possible causes of the error include:</span></span>  
  
-   <span data-ttu-id="f869e-123">O certificado pode ter sido movido ou excluído.</span><span class="sxs-lookup"><span data-stu-id="f869e-123">The certificate could have been moved or deleted.</span></span>  
  
-   <span data-ttu-id="f869e-124">Se o logon usado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mudou, talvez o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não tenha permissão para acessar o certificado.</span><span class="sxs-lookup"><span data-stu-id="f869e-124">If the login used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has changed, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] may not have permission to access the certificate.</span></span>  
  
-   <span data-ttu-id="f869e-125">O certificado pode ter expirado.</span><span class="sxs-lookup"><span data-stu-id="f869e-125">The certificate may have expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f869e-126">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="f869e-126">User Action</span></span>  
 <span data-ttu-id="f869e-127">Verifique se o certificado indicado na mensagem existe no sistema, se pode ser acessado e se é válido para uso.</span><span class="sxs-lookup"><span data-stu-id="f869e-127">Make sure the certificate named in the message exists on the system, is accessible, and it is valid for use.</span></span>  
  
  
