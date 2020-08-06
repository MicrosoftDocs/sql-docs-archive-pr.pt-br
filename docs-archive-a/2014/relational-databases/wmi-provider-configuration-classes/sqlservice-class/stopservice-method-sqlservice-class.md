---
title: Método StopService (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StopService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StopService method
ms.assetid: ef8e1856-4930-417a-8f52-be470fd3f15c
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 534db69b9c5474638ef5e893847f7d6b9bbb645d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681470"
---
# <a name="stopservice-method-sqlservice-class"></a><span data-ttu-id="f8757-102">Método StoptService (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="f8757-102">StopService Method (SqlService Class)</span></span>
  <span data-ttu-id="f8757-103">Tenta colocar o serviço no estado de interrompido.</span><span class="sxs-lookup"><span data-stu-id="f8757-103">Attempts to place the service in the stopped state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8757-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f8757-104">Syntax</span></span>  
  
```  
  
object  
.StopService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="f8757-105">Partes</span><span class="sxs-lookup"><span data-stu-id="f8757-105">Parts</span></span>  
 <span data-ttu-id="f8757-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f8757-106">*object*</span></span>  
 <span data-ttu-id="f8757-107">Um objeto da [classe SqlService](sqlservice-class.md) que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="f8757-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f8757-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="f8757-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="f8757-109">Um valor `uint32`, que é 0 se a solicitação `ResumeService` tiver sido aceita, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="f8757-109">A `uint32` value, which is 0 if the `ResumeService` request was accepted, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8757-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="f8757-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8757-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f8757-111">See Also</span></span>  
 <span data-ttu-id="f8757-112">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f8757-112">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  