---
title: Método SetEnable (classe ServerNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetEnable Method (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEnable method
ms.assetid: a287950b-086f-4b6d-a2d8-4d3973bd1b21
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8f77b7a92fe226e349a03ffba03cfe8d67c280e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571897"
---
# <a name="setenable-method-servernetworkprotocol-class"></a><span data-ttu-id="d0748-102">Método SetEnable (classe ServerNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="d0748-102">SetEnable Method (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="d0748-103">Habilita o protocolo de rede do servidor.</span><span class="sxs-lookup"><span data-stu-id="d0748-103">Enables the server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0748-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d0748-104">Syntax</span></span>  
  
```  
  
object  
.SetEnable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="d0748-105">Partes</span><span class="sxs-lookup"><span data-stu-id="d0748-105">Parts</span></span>  
 <span data-ttu-id="d0748-106">*object*</span><span class="sxs-lookup"><span data-stu-id="d0748-106">*object*</span></span>  
 <span data-ttu-id="d0748-107">A [classe ServerNetworkProtocol](servernetworkprotocol-class.md) que representa o protocolo de rede usado pela instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0748-107">A [ServerNetworkProtocol Class](servernetworkprotocol-class.md) object that represents the network protocol used by the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d0748-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="d0748-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="d0748-109">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="d0748-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0748-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="d0748-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0748-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d0748-111">See Also</span></span>  
 <span data-ttu-id="d0748-112">[Configurando protocolos de rede de servidor e Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="d0748-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
