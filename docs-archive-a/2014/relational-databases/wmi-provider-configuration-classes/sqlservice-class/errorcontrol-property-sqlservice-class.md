---
title: Propriedade ErrorControl (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ErrorControl Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ErrorControl property
ms.assetid: cbb1e0fa-5bfc-4b1b-a6ed-f7d5cfad4d73
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 73c726af514f2880484cf927282fc0e007f07e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684122"
---
# <a name="errorcontrol-property-sqlservice-class"></a>Propriedade ErrorControl (classe SqlService)
  Obtém ou define a gravidade do erro se o serviço não for iniciado durante a inicialização.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
object  
.ErrorControl [= value]  
```  
  
## <a name="parts"></a>Partes  
 *object*  
 Um objeto da [classe SqlService](sqlservice-class.md) que representa o serviço.  
  
## <a name="property-valuereturn-value"></a>Valor da propriedade/Valor do retorno  
 Um valor da cadeia de caracteres que especifica a gravidade de erro informada se o serviço falhar durante a inicialização. A tabela a seguir mostra os valores possíveis.  
  
 Ignorar  
 O usuário não é notificado.  
  
 Normal  
 O usuário é notificado.  
  
 Severo  
 Sistema é reiniciado com a última configuração bem-sucedida conhecida.  
  
 Crítico  
 O sistema tenta reiniciar com uma configuração adequada.  
  
 Unknown (desconhecido)  
 A gravidade é desconhecida.  
  
## <a name="remarks"></a>Comentários  
 O valor indicará a ação tomada pelo programa de inicialização se ocorrer uma falha. Todos os erros são anotados pelo sistema de computador.  
  
## <a name="see-also"></a>Consulte Também  
 [Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
