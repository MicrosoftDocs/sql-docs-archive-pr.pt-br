---
title: Propriedade de IsSharePointIntegrated (WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- IsSharePointIntegrated property
ms.assetid: c548fed8-5e04-4faf-8b10-b37c86178056
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a1f3f38c23546ddf4dfb52c2a3af7c122af10cbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576203"
---
# <a name="issharepointintegrated-property-wmi"></a><span data-ttu-id="3a045-102">Propriedade IsSharePointIntegrated (WMI)</span><span class="sxs-lookup"><span data-stu-id="3a045-102">IsSharePointIntegrated Property (WMI)</span></span>
  <span data-ttu-id="3a045-103">Especifica se o servidor de relatório está no modo integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3a045-103">Specifies whether the report server is in SharePoint integrated mode.</span></span> <span data-ttu-id="3a045-104">A partir do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], essa propriedade sempre retorna `False` porque, em modo do SharePoint, as instâncias do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] são serviços compartilhados do SharePoint e não são controladas por provedores WMI.</span><span class="sxs-lookup"><span data-stu-id="3a045-104">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this property always returns `False` because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instances are SharePoint shared services and are not controlled by WMI providers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a045-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3a045-105">Syntax</span></span>  
  
```vb  
Public Dim IsSharePointIntegrated As Boolean  
```  
  
```csharp  
public Boolean IsSharePointIntegrated;  
```  
  
## <a name="property-values"></a><span data-ttu-id="3a045-106">Valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="3a045-106">Property Values</span></span>  
 <span data-ttu-id="3a045-107">Um objeto `Boolean` que indica se o servidor de relatório está no modo integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3a045-107">A `Boolean` object that indicates whether the report server is in SharePoint integrated mode.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="3a045-108">Código de exemplo</span><span class="sxs-lookup"><span data-stu-id="3a045-108">Example Code</span></span>  
 [<span data-ttu-id="3a045-109">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="3a045-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="3a045-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a045-110">Requirements</span></span>  
 <span data-ttu-id="3a045-111">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a045-111">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a045-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3a045-112">See Also</span></span>  
 [<span data-ttu-id="3a045-113">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="3a045-113">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
