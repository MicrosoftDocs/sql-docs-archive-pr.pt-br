---
title: Método SetSecureConnectionLevel (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetSecureConnectionLevel (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetSecureConnectionLevel method
ms.assetid: 0fac7d5e-2670-4657-9439-331e7d93babb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4361f09eb38b3e5650b68ae6f86b7f2266bbf1a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683993"
---
# <a name="setsecureconnectionlevel-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="e81a2-102">Método SetSecureConnectionLevel (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="e81a2-102">SetSecureConnectionLevel Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="e81a2-103">Define o nível de conexão segura do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="e81a2-103">Sets the secure connection level of the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e81a2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e81a2-104">Syntax</span></span>  
  
```vb  
Public Sub SetSecureConnectionLevel(Level as Integer, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetSecureConnectionLevel(Int32 Level,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e81a2-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e81a2-105">Parameters</span></span>  
 <span data-ttu-id="e81a2-106">*Level*</span><span class="sxs-lookup"><span data-stu-id="e81a2-106">*Level*</span></span>  
 <span data-ttu-id="e81a2-107">Um valor de inteiro que representa um nível de conexão segura.</span><span class="sxs-lookup"><span data-stu-id="e81a2-107">An integer value representing a secure connection level.</span></span>  
  
 <span data-ttu-id="e81a2-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="e81a2-108">*HRESULT*</span></span>  
 <span data-ttu-id="e81a2-109">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="e81a2-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e81a2-110">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="e81a2-110">Return Value</span></span>  
 <span data-ttu-id="e81a2-111">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="e81a2-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="e81a2-112">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="e81a2-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="e81a2-113">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="e81a2-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e81a2-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="e81a2-114">Remarks</span></span>  
 <span data-ttu-id="e81a2-115">Quando chamada, a propriedade SecureConnectionLevel do servidor de relatório será definida como o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="e81a2-115">When called, the report server SecureConnectionLevel property is set to the value specified.</span></span> <span data-ttu-id="e81a2-116">Um valor de 0 indica que o SSL está desativado.</span><span class="sxs-lookup"><span data-stu-id="e81a2-116">A value of 0 indicates that SSL is turned off.</span></span> <span data-ttu-id="e81a2-117">Um valor maior que ou igual a 1indica que o SSL está ligado.</span><span class="sxs-lookup"><span data-stu-id="e81a2-117">A value greater than or equal to 1 indicates that SSL is turned on.</span></span>  
  
-   <span data-ttu-id="e81a2-118">Quando o valor é definido, o elemento SecureConnectionLevel no arquivo de configuração do servidor de relatório é alterado e o `URLRoot` elemento no arquivo de configuração é definido para usar "https://" se o *nível* especificado for maior ou igual a 1, ou "http://" se o *nível* especificado for 0.</span><span class="sxs-lookup"><span data-stu-id="e81a2-118">When the value is set, the SecureConnectionLevel element in the report server configuration file is changed, and the `URLRoot` element in the configuration file is set to use "https://" if the specified *Level* is greater than or equal to 1, or "http://" if the specified *Level* is 0.</span></span>  
  
 <span data-ttu-id="e81a2-119">Em [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], transforma-se SecureConnectionLevel em uma opção ativado/desativado, cujo valor padrão é 0.</span><span class="sxs-lookup"><span data-stu-id="e81a2-119">In [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], SecureConnectionLevel is made an on/off switch, default value is 0.</span></span> <span data-ttu-id="e81a2-120">Para qualquer valor maior ou igual a 1 passado pela API de método de SetSecureConnectionLevel, o SSL é considerado ativado e a propriedade de configuração SecureConnectionLevel é definida de forma condizente no arquivo rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="e81a2-120">For any value greater than or equal to 1 passed through SetSecureConnectionLevel method API, SSL is considered on and the configuration property SecureConnectionLevel is set accordingly in the rsreportserver.config file.</span></span> <span data-ttu-id="e81a2-121">Os valores 2 e 3 ainda são permitidos para compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="e81a2-121">Values of 2 and 3 are still allowed for backward compatibility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e81a2-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e81a2-122">Requirements</span></span>  
 <span data-ttu-id="e81a2-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e81a2-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e81a2-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e81a2-124">See Also</span></span>  
 [<span data-ttu-id="e81a2-125">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="e81a2-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  