---
title: Método GetNextOrderValue (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetNextOrderValue Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetNextOrderValue method
ms.assetid: d741dc5c-c225-43d9-a730-7ad664ac525f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: bdc3eecd9e151d7da32a5fd65a90552c0743b3d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584051"
---
# <a name="getnextordervalue-method-clientnetworkprotocol-class"></a><span data-ttu-id="546b0-102">Método GetNextOrderValue (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="546b0-102">GetNextOrderValue Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="546b0-103">Seleciona o protocolo que está na próxima posição na lista de protocolos.</span><span class="sxs-lookup"><span data-stu-id="546b0-103">Selects the protocol that is in the next position in the list of protocols.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="546b0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="546b0-104">Syntax</span></span>  
  
```  
  
object  
.GetNextOrderValue()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="546b0-105">Partes</span><span class="sxs-lookup"><span data-stu-id="546b0-105">Parts</span></span>  
 <span data-ttu-id="546b0-106">*object*</span><span class="sxs-lookup"><span data-stu-id="546b0-106">*object*</span></span>  
 <span data-ttu-id="546b0-107">A [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) que representa o protocolo de rede usado pelo cliente do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="546b0-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="546b0-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="546b0-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="546b0-109">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="546b0-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="546b0-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="546b0-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="546b0-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="546b0-111">See Also</span></span>  
 <span data-ttu-id="546b0-112">[Configurar protocolos de cliente](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="546b0-112">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="546b0-113">Configurando protocolos de cliente de servidor e bibliotecas de rede</span><span class="sxs-lookup"><span data-stu-id="546b0-113">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  