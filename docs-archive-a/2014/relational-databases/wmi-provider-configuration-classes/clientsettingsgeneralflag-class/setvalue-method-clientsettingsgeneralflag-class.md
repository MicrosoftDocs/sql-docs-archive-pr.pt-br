---
title: Método SetValue (classe ClientSettingsGeneralFlag) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetValue Method (ClientSettingsGeneralFlag Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetValue method
ms.assetid: 34443689-a0e0-4668-a811-17532c6fd271
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: fffa44bd8743f96a43ca4d1787d8d2afaad5e6cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679266"
---
# <a name="setvalue-method-clientsettingsgeneralflag-class"></a>Método SetValue (classe ClientSettingsGeneralFlag)
  Define todos os valores do sinalizador referenciado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
object  
.SetValue(  
Value  
)  
  
```  
  
## <a name="parts"></a>Partes  
 *object*  
 Um objeto da [classe ClientSettingsGeneralFlag](clientsettingsgeneralflag-class.md) que representa um sinalizador geral para as configurações de servidor.  
  
#### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|*Valor*|Um valor booliano que especifica o valor do sinalizador.|  
  
## <a name="property-valuereturn-value"></a>Valor da propriedade/Valor do retorno  
 Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.  
  
## <a name="remarks"></a>Comentários  
  
## <a name="see-also"></a>Consulte Também  
 [Configurar protocolos de cliente](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
