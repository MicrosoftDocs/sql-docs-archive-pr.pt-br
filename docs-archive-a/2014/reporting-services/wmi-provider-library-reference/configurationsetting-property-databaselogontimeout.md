---
title: Propriedade de DatabaseLogonTimeout (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonTimeout Property
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonTimeout property
ms.assetid: 4a65162c-33de-485e-8fd3-2bd6bff8bf8d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4920f5ef2282478f4d12a19b0806cf6ff9632cac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683976"
---
# <a name="databaselogontimeout-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="8d8bb-102">Propriedade DatabaseLogonTimeout (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="8d8bb-102">DatabaseLogonTimeout Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="8d8bb-103">Especifica o número de segundos de espera antes de uma tentativa de logon no banco de dados do servidor de relatório falhar.</span><span class="sxs-lookup"><span data-stu-id="8d8bb-103">Specifies the number of seconds to wait before an attempt to log on to the report server database fails.</span></span> <span data-ttu-id="8d8bb-104">O valor **0** indica um tempo de espera infinito.</span><span class="sxs-lookup"><span data-stu-id="8d8bb-104">A value of **0** indicates an infinite wait time.</span></span> <span data-ttu-id="8d8bb-105">Somente leitura.</span><span class="sxs-lookup"><span data-stu-id="8d8bb-105">Read only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d8bb-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8d8bb-106">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonTimeout As Int32  
```  
  
```csharp  
public Int32 DatabaseLogonTimeout;  
```  
  
## <a name="property-values"></a><span data-ttu-id="8d8bb-107">Valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="8d8bb-107">Property Values</span></span>  
 <span data-ttu-id="8d8bb-108">Um objeto inteiro assinado de 32 bits que representa o número de segundos.</span><span class="sxs-lookup"><span data-stu-id="8d8bb-108">A 32-bit signed integer object that represents the number of seconds.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="8d8bb-109">Código de exemplo</span><span class="sxs-lookup"><span data-stu-id="8d8bb-109">Example Code</span></span>  
 [<span data-ttu-id="8d8bb-110">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="8d8bb-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="8d8bb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d8bb-111">Requirements</span></span>  
 <span data-ttu-id="8d8bb-112">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d8bb-112">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d8bb-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8d8bb-113">See Also</span></span>  
 [<span data-ttu-id="8d8bb-114">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="8d8bb-114">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
