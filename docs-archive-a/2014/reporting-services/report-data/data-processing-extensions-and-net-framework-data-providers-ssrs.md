---
title: Extensões de processamento de dados e provedores de dados .NET Framework (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], data
- data processing extensions [Reporting Services]
- data providers [Reporting Services]
- data retrieval [Reporting Services]
- Reporting Services, data sources
- report data [Report Builder], accessing
ms.assetid: 42a5afb5-f4c8-4957-b1fd-77bf39afa5be
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fd84af68af54b165c75317280bc19bb23da53366
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679174"
---
# <a name="data-processing-extensions-and-net-framework-data-providers-ssrs"></a><span data-ttu-id="e227e-102">Extensões de processamento de dados e provedores de dados do .NET Framework (SSRS)</span><span class="sxs-lookup"><span data-stu-id="e227e-102">Data Processing Extensions and .NET Framework Data Providers (SSRS)</span></span>
  <span data-ttu-id="e227e-103">Uma extensão de processamento de dados [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] é um componente instalado com [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], projetado para recuperar dados de um tipo específico de fonte de dados e para fornecer funcionalidade adicional para oferecer suporte ao design de relatórios e processamento de relatórios.</span><span class="sxs-lookup"><span data-stu-id="e227e-103">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] data processing extension is a component installed with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], designed to retrieve data from a specific type of data source and to provide extra functionality to support report design and report processing.</span></span> <span data-ttu-id="e227e-104">Uma extensão de processamento de dados [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] é um componente disponível do [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou de fontes de terceiros que dá suporte às interfaces <xref:System.Data> que permitem que você recupere e modifique dados de um tipo específico de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e227e-104">A [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider is a component available from [!INCLUDE[msCoName](../../includes/msconame-md.md)] or third-party sources that supports <xref:System.Data> interfaces that allow you to retrieve and to modify data from a specific type of data source.</span></span>  
  
## <a name="understanding-a-data-processing-extension"></a><span data-ttu-id="e227e-105">Entendendo uma extensão de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="e227e-105">Understanding a Data Processing Extension</span></span>  
 <span data-ttu-id="e227e-106">Uma extensão de processamento de dados [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dá suporte a um subconjunto das interfaces <xref:System.Data> .</span><span class="sxs-lookup"><span data-stu-id="e227e-106">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] data processing extension supports a subset of the <xref:System.Data> interfaces.</span></span> <span data-ttu-id="e227e-107">As extensões de processamento de dados exigem apenas o acesso somente leitura a uma fonte de dados para que as interfaces para gravação e atualização não sejam implementadas.</span><span class="sxs-lookup"><span data-stu-id="e227e-107">Data processing extensions require only read-only access to a data source, so the interfaces for write and update are not implemented.</span></span> <span data-ttu-id="e227e-108">Cada extensão de processamento de dados pode fornecer recursos personalizados para dar suporte ao processamento de relatório.</span><span class="sxs-lookup"><span data-stu-id="e227e-108">Each data processing extension can provide custom features to support report processing.</span></span> <span data-ttu-id="e227e-109">Por exemplo, uma extensão de processamento de dados pode oferecer suporte aos seguintes tipos de recursos:</span><span class="sxs-lookup"><span data-stu-id="e227e-109">For example, a data processing extension might support the following types of features:</span></span>  
  
-   <span data-ttu-id="e227e-110">Gerenciamento de credenciais separadamente da cadeia de conexão</span><span class="sxs-lookup"><span data-stu-id="e227e-110">Managing credentials separately from the connection string</span></span>  
  
-   <span data-ttu-id="e227e-111">Suportando parâmetros de vários valores</span><span class="sxs-lookup"><span data-stu-id="e227e-111">Supporting multivalue parameters</span></span>  
  
-   <span data-ttu-id="e227e-112">Recuperação de agregações de servidor, que são calculadas na fonte de dados</span><span class="sxs-lookup"><span data-stu-id="e227e-112">Retrieving server aggregates, which are calculated on the data source</span></span>  
  
-   <span data-ttu-id="e227e-113">Recuperando propriedades de dados bem como valores de dados da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="e227e-113">Retrieving data properties as well as data values from the data source</span></span>  
  
## <a name="understanding-a-data-provider"></a><span data-ttu-id="e227e-114">Entendendo um provedor de dados</span><span class="sxs-lookup"><span data-stu-id="e227e-114">Understanding a Data Provider</span></span>  
 <span data-ttu-id="e227e-115">Uma extensão de processamento de dados [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] (às vezes, conhecido como um driver) dá suporte a um conjunto padrão de interfaces <xref:System.Data> para ler, gravar e atualizar dados em uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e227e-115">A [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider (sometimes known as a driver) supports a standard set of <xref:System.Data> interfaces for reading, writing, and updating data on a data source.</span></span> <span data-ttu-id="e227e-116">Um provedor de dados pode ser usado quando não houver nenhuma extensão de processamento de dados disponível para um tipo específico de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e227e-116">A data provider can be used when there is no data processing extension available for a specific type of data source.</span></span> <span data-ttu-id="e227e-117">Muitos provedores de dados [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] padrão de terceiros estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e227e-117">Many third-party standard [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data providers are available.</span></span>  
  
 <span data-ttu-id="e227e-118">Uma vez que [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] tem uma arquitetura de provedor de dados extensível, você pode criar uma extensão de processamento de dados personalizada para incluir a funcionalidade extra fornecida pelas extensões de processamento de dados do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e227e-118">Because [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] has an extensible data provider architecture, you can build a custom data processing extension to include the extra functionality supplied by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] data processing extensions.</span></span> <span data-ttu-id="e227e-119">Para obter mais informações, consulte [Implementing a Data Processing Extension](../extensions/data-processing/implementing-a-data-processing-extension.md).</span><span class="sxs-lookup"><span data-stu-id="e227e-119">For more information, see [Implementing a Data Processing Extension](../extensions/data-processing/implementing-a-data-processing-extension.md).</span></span> <span data-ttu-id="e227e-120">Para as extensões de processamento de dados de terceiros, consulte a documentação que acompanha a extensão de processamento de dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="e227e-120">For third-party data processing extensions, see the documentation that comes with the third-party data processing extension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e227e-121">Um provedor de dados [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] ou uma extensão de processamento de dados personalizada deve ser instalada e registrada antes de ser usada para acessar dados de uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e227e-121">A [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider or custom data processing extension must be installed and registered before it can be used to access data from a data source.</span></span> <span data-ttu-id="e227e-122">A extensão de processamento de dados deve ser instalada e registrada tanto no cliente de relatório para criá-lo quanto no servidor de relatórios para exibir o relatório publicado.</span><span class="sxs-lookup"><span data-stu-id="e227e-122">The data processing extension must be installed and registered both on the reporting client to author the report and on the report server to view the published report.</span></span> <span data-ttu-id="e227e-123">Nem todos os provedores de dados se destinam a funcionar em um ambiente de servidor.</span><span class="sxs-lookup"><span data-stu-id="e227e-123">Not all data providers are designed to work in a server environment.</span></span> <span data-ttu-id="e227e-124">Para obter mais informações, consulte [Registrar um provedor de dados .NET Framework padrão &#40;SSRS&#41;](register-a-standard-net-framework-data-provider-ssrs.md) e [Implantando uma extensão de processamento de dados](../extensions/data-processing/deploying-a-data-processing-extension.md).</span><span class="sxs-lookup"><span data-stu-id="e227e-124">For more information, see [Register a Standard .NET Framework Data Provider &#40;SSRS&#41;](register-a-standard-net-framework-data-provider-ssrs.md).and [Deploying a Data Processing Extension](../extensions/data-processing/deploying-a-data-processing-extension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e227e-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e227e-125">See Also</span></span>  
 <span data-ttu-id="e227e-126">[Visão geral das extensões de processamento de dados](../extensions/data-processing/data-processing-extensions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="e227e-126">[Data Processing Extensions Overview](../extensions/data-processing/data-processing-extensions-overview.md) </span></span>  
 [<span data-ttu-id="e227e-127">Conjuntos de dados inseridos e compartilhados de relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e227e-127">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
  
  