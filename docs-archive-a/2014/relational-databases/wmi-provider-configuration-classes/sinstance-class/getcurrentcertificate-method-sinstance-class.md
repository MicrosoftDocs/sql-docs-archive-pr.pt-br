---
title: Método GetCurrentCertificate (classe SInstance) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetCurrentCertificate Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetCurrentCertificate method
ms.assetid: 9d2b72df-cb21-414a-abef-917f13d4de62
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 47838190e3791e01f8482e3fb064a9dca3a764af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584042"
---
# <a name="getcurrentcertificate-method-sinstance-class"></a><span data-ttu-id="7a173-102">Método GetCurrentCertificate (classe SInstance)</span><span class="sxs-lookup"><span data-stu-id="7a173-102">GetCurrentCertificate Method (SInstance Class)</span></span>
  <span data-ttu-id="7a173-103">Obtém o certificado de segurança atual.</span><span class="sxs-lookup"><span data-stu-id="7a173-103">Gets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a173-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7a173-104">Syntax</span></span>  
  
```  
  
object  
.GetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="7a173-105">Partes</span><span class="sxs-lookup"><span data-stu-id="7a173-105">Parts</span></span>  
 <span data-ttu-id="7a173-106">*object*</span><span class="sxs-lookup"><span data-stu-id="7a173-106">*object*</span></span>  
 <span data-ttu-id="7a173-107">Um objeto da [classe SInstance](sinstance-class.md) que representa as configurações de servidor em uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a173-107">An [SInstance Class](sinstance-class.md) object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="7a173-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7a173-108">Parameters</span></span>  
  
|<span data-ttu-id="7a173-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="7a173-109">Parameter</span></span>|<span data-ttu-id="7a173-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="7a173-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7a173-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="7a173-111">*SHA*</span></span>|<span data-ttu-id="7a173-112">Um valor de objeto da cadeia de caracteres (parâmetro de saída) que especifica o certificado de segurança atual depois que o método é concluído.</span><span class="sxs-lookup"><span data-stu-id="7a173-112">A string object value (output parameter) that specifies the current security certificate after the method completes.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="7a173-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="7a173-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="7a173-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="7a173-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a173-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="7a173-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a173-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7a173-116">See Also</span></span>  
 <span data-ttu-id="7a173-117">[Configurando protocolos de rede de servidor e Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7a173-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  