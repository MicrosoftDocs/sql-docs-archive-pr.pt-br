---
title: Método RemoveSSLCertificateBindings (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RemoveSSLCertificateBindings method
ms.assetid: b8b484c9-04c4-4ae9-980e-67bbe5aa8481
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d42d17d9c92f2e100a7800e607536ff6c7eab891
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683349"
---
# <a name="removesslcertificatebindings-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="aa602-102">Método RemoveSSLCertificateBindings (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="aa602-102">RemoveSSLCertificateBindings Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="aa602-103">Remove uma associação de Certificado SSL.</span><span class="sxs-lookup"><span data-stu-id="aa602-103">Removes an SSL Certificate binding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa602-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="aa602-104">Syntax</span></span>  
  
```vb  
Public Sub RemoveSSLCertificateBinding(ByVal Application As String, _  
    ByVal CertificateHash As String, ByVal IPAddress As String, _  
    ByVal Port As Int32, ByVal Lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void RemoveSSLCertificateBindings(string Application,  
    string CertificateHash, string IPAddress, Int32 Port, Int32 Lcid,  
    out string Error, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa602-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="aa602-105">Parameters</span></span>  
 <span data-ttu-id="aa602-106">*Aplicativo*</span><span class="sxs-lookup"><span data-stu-id="aa602-106">*Application*</span></span>  
 <span data-ttu-id="aa602-107">O nome do aplicativo para o qual a associação de certificado deve ser removida.</span><span class="sxs-lookup"><span data-stu-id="aa602-107">The name of application for which the certificate binding should be removed.</span></span>  
  
 <span data-ttu-id="aa602-108">*CertificateHash*</span><span class="sxs-lookup"><span data-stu-id="aa602-108">*CertificateHash*</span></span>  
 <span data-ttu-id="aa602-109">O hash para o certificado.</span><span class="sxs-lookup"><span data-stu-id="aa602-109">The hash for the certificate.</span></span>  
  
 <span data-ttu-id="aa602-110">*EndereçoIP*</span><span class="sxs-lookup"><span data-stu-id="aa602-110">*IPAddress*</span></span>  
 <span data-ttu-id="aa602-111">O endereço IP para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="aa602-111">The IP address for the application.</span></span>  
  
 <span data-ttu-id="aa602-112">*Porta*</span><span class="sxs-lookup"><span data-stu-id="aa602-112">*Port*</span></span>  
 <span data-ttu-id="aa602-113">A porta SSL relacionada à associação.</span><span class="sxs-lookup"><span data-stu-id="aa602-113">The SSL port associated with the binding.</span></span>  
  
 <span data-ttu-id="aa602-114">*lcid*</span><span class="sxs-lookup"><span data-stu-id="aa602-114">*lcid*</span></span>  
 <span data-ttu-id="aa602-115">A localidade a ser usada para as mensagens de erro retornadas.</span><span class="sxs-lookup"><span data-stu-id="aa602-115">The locale to use for the error messages that are returned.</span></span>  
  
 <span data-ttu-id="aa602-116">*Erro*</span><span class="sxs-lookup"><span data-stu-id="aa602-116">*Error*</span></span>  
 <span data-ttu-id="aa602-117">[fora] A descrição do erro ocorrido.</span><span class="sxs-lookup"><span data-stu-id="aa602-117">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="aa602-118">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="aa602-118">*HRESULT*</span></span>  
 <span data-ttu-id="aa602-119">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="aa602-119">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa602-120">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="aa602-120">Return Value</span></span>  
 <span data-ttu-id="aa602-121">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="aa602-121">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="aa602-122">Um valor 0 indica que a chamada do método foi bem-sucedida; um código de erro indica que a chamada não foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="aa602-122">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa602-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="aa602-123">Remarks</span></span>  
 <span data-ttu-id="aa602-124">Este método remove a associação específica do arquivo rsreportserver.config e, opcionalmente, de HTTP.SYS.</span><span class="sxs-lookup"><span data-stu-id="aa602-124">This method removes the specific binding from the rsreportserver.config file and optionally HTTP.SYS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa602-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa602-125">Requirements</span></span>  
 <span data-ttu-id="aa602-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa602-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa602-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aa602-127">See Also</span></span>  
 [<span data-ttu-id="aa602-128">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="aa602-128">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  