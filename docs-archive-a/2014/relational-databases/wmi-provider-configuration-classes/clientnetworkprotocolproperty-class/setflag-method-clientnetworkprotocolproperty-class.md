---
title: Método SetFlag (classe ClientNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetFlag Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetFlag method
ms.assetid: 0407520f-2f84-4f68-b2b7-429697286c1b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1c83a1d647b62f0e5c5acf0659d54bf787bf0c96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684133"
---
# <a name="setflag-method-clientnetworkprotocolproperty-class"></a>Método SetFlag (classe ClientNetworkProtocolProperty)
  Define o sinalizador da cadeia de caracteres da propriedade atual referenciado pelo valor [PropertyIdx Property (classe ClientNetworkProtocolProperty) (classe ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
object  
.SetFlag(  
BoolValue  
) [=]  
```  
  
## <a name="parts"></a>Partes  
 *object*  
 A [classe ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) que representa um atributo do protocolo de rede usado pelo cliente do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .  
  
#### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|*BoolValue*|Um valor booliano que especifica o novo valor do sinalizador.|  
  
## <a name="property-valuereturn-value"></a>Valor da propriedade/Valor do retorno  
 Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.  
  
## <a name="remarks"></a>Comentários  
  
## <a name="see-also"></a>Consulte Também  
 [Configurar protocolos de cliente](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
