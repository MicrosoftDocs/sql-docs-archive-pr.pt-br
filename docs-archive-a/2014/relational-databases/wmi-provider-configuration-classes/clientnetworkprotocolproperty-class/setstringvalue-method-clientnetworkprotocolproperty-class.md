---
title: Método SetStringValue (classe ClientNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStringValue Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStringValue method
ms.assetid: 88d67b22-0eea-48c9-ab73-e0b4907953df
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ba2350b798f1d7092a37a28ca35c17d6f4536a4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685029"
---
# <a name="setstringvalue-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="6a550-102">Método SetStringValue (classe ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="6a550-102">SetStringValue Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="6a550-103">Define o valor da cadeia de caracteres da propriedade atual referenciado pelo valor [PropertyIdx Property (classe ClientNetworkProtocolProperty) (classe ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="6a550-103">Sets the string value of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a550-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6a550-104">Syntax</span></span>  
  
```  
  
object  
.SetStringValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="6a550-105">Partes</span><span class="sxs-lookup"><span data-stu-id="6a550-105">Parts</span></span>  
 <span data-ttu-id="6a550-106">*object*</span><span class="sxs-lookup"><span data-stu-id="6a550-106">*object*</span></span>  
 <span data-ttu-id="6a550-107">A [classe ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) que representa um atributo do protocolo de rede usado pelo cliente do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6a550-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="6a550-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6a550-108">Parameters</span></span>  
  
|<span data-ttu-id="6a550-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="6a550-109">Parameter</span></span>|<span data-ttu-id="6a550-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="6a550-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6a550-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="6a550-111">*StrValue*</span></span>|<span data-ttu-id="6a550-112">Um valor da cadeia de caracteres que especifica o novo valor da propriedade atual.</span><span class="sxs-lookup"><span data-stu-id="6a550-112">A string value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="6a550-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="6a550-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="6a550-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="6a550-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a550-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="6a550-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a550-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6a550-116">See Also</span></span>  
 [<span data-ttu-id="6a550-117">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="6a550-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  