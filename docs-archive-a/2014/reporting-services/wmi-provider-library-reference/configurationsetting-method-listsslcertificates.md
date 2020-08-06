---
title: Método ListSSLCertificates (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListSSLCertificates method
ms.assetid: 88cd0936-b202-4ab8-90f2-d9c3f66d37f4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6a5ced8371817adc44bbbc89400dc83e0dfccef0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572902"
---
# <a name="listsslcertificates-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="2ff4b-102">Método ListSSLCertificates (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="2ff4b-102">ListSSLCertificates Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="2ff4b-103">Retorna uma lista de certificados no computador do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="2ff4b-103">Returns a list of certificates on the report server computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ff4b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2ff4b-104">Syntax</span></span>  
  
```vb  
Public Sub CreateSSLCertificateBinding (ByRef CertificateHash() as String, _  
    ByRef CertName() as String, ByRef HostName() as String, ByRef Length as Int32, _   
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListSSLCertificates(out string[] CertificateHash,   
    out string[] CertName, out string[] Hostname, out Int32 length,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ff4b-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="2ff4b-105">Parameters</span></span>  
 <span data-ttu-id="2ff4b-106">*CertificateHash[]*</span><span class="sxs-lookup"><span data-stu-id="2ff4b-106">*CertificateHash[]*</span></span>  
 <span data-ttu-id="2ff4b-107">[fora] O certificado efetua hash.</span><span class="sxs-lookup"><span data-stu-id="2ff4b-107">[out] The certificate hashes.</span></span>  
  
 <span data-ttu-id="2ff4b-108">*CertName[]*</span><span class="sxs-lookup"><span data-stu-id="2ff4b-108">*CertName[]*</span></span>  
 <span data-ttu-id="2ff4b-109">[fora] Nomes do certificado.</span><span class="sxs-lookup"><span data-stu-id="2ff4b-109">[out] Names of the certificate.</span></span>  
  
 <span data-ttu-id="2ff4b-110">*HostName[]*</span><span class="sxs-lookup"><span data-stu-id="2ff4b-110">*HostName[]*</span></span>  
 <span data-ttu-id="2ff4b-111">[fora] Nomes de host dos certificados.</span><span class="sxs-lookup"><span data-stu-id="2ff4b-111">[out] The host names for the certificates.</span></span>  
  
 <span data-ttu-id="2ff4b-112">*Comprimento*</span><span class="sxs-lookup"><span data-stu-id="2ff4b-112">*Length*</span></span>  
 <span data-ttu-id="2ff4b-113">[out] Representa o comprimento das matrizes *CertificateHash*, *CertName* e *HostName* .</span><span class="sxs-lookup"><span data-stu-id="2ff4b-113">[out] Represents the length of the *CertificateHash*, *CertName* and *HostName* arrays.</span></span>  
  
 <span data-ttu-id="2ff4b-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="2ff4b-114">*HRESULT*</span></span>  
 <span data-ttu-id="2ff4b-115">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="2ff4b-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ff4b-116">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="2ff4b-116">Return Value</span></span>  
 <span data-ttu-id="2ff4b-117">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="2ff4b-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="2ff4b-118">Um valor 0 indica que a chamada do método foi bem-sucedida; um código de erro indica que a chamada não foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="2ff4b-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ff4b-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="2ff4b-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ff4b-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ff4b-120">Requirements</span></span>  
 <span data-ttu-id="2ff4b-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ff4b-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ff4b-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2ff4b-122">See Also</span></span>  
 [<span data-ttu-id="2ff4b-123">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="2ff4b-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
