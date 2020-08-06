---
title: Fontes de dados com suporte (SSAS multidimensional) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Analysis Services, data sources
- data sources [Analysis Services], about data sources
- Analysis Services, data sources
- connections [Analysis Services]
- SSAS, data sources
ms.assetid: c97e0f8d-7ddd-4941-8b51-e7832f30fbbe
author: minewiskan
ms.author: owend
ms.openlocfilehash: 93c09424a7cc5fa6a17d84b7464798c0b4412612
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576019"
---
# <a name="data-sources-supported-ssas-multidimensional"></a><span data-ttu-id="f30b1-102">Fontes de dados com suporte (SSAS multidimensional)</span><span class="sxs-lookup"><span data-stu-id="f30b1-102">Data Sources Supported (SSAS Multidimensional)</span></span>
  <span data-ttu-id="f30b1-103">Este tópico descreve os tipos de fonte de dados que você pode usar em um modelo multidimensional.</span><span class="sxs-lookup"><span data-stu-id="f30b1-103">This topic describes the types of data sources that you can use in a multidimensional model.</span></span>  
  
##  <a name="supported-data-sources"></a><a name="bkmk_supported_ds"></a><span data-ttu-id="f30b1-104">Fontes de dados com suporte</span><span class="sxs-lookup"><span data-stu-id="f30b1-104">Supported Data Sources</span></span>  
 <span data-ttu-id="f30b1-105">Você pode recuperar dados das fontes de dados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="f30b1-105">You can retrieve data from the data sources in the following table.</span></span> <span data-ttu-id="f30b1-106">Quando você instalar o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], a instalação não instala os provedores listados para cada fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f30b1-106">When you install [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], setup does not install the providers that are listed for each data source.</span></span> <span data-ttu-id="f30b1-107">Alguns deles podem já estar instalados com outros aplicativos no computador; em outros casos, você precisará baixar e instalar o provedor.</span><span class="sxs-lookup"><span data-stu-id="f30b1-107">Some providers might already be installed with other applications on your computer; in other cases you will need to download and install the provider.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f30b1-108">Também é possível usar provedores de outros fabricantes, como Oracle OLE DB Provider, na conexão com banco de dados de terceiros, com suporte fornecido por esses fabricantes.</span><span class="sxs-lookup"><span data-stu-id="f30b1-108">Third party providers, such as the Oracle OLE DB Provider, may also be used to connect to third party databases, with support provided by those third parties.</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="f30b1-109">Fonte</span><span class="sxs-lookup"><span data-stu-id="f30b1-109">Source</span></span>|<span data-ttu-id="f30b1-110">Versões</span><span class="sxs-lookup"><span data-stu-id="f30b1-110">Versions</span></span>|<span data-ttu-id="f30b1-111">Tipo de arquivo</span><span class="sxs-lookup"><span data-stu-id="f30b1-111">File type</span></span>|<span data-ttu-id="f30b1-112">Provedores <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f30b1-112">Providers <sup>1</sup></span></span>|  
|<span data-ttu-id="f30b1-113">Bancos de dados do Access</span><span class="sxs-lookup"><span data-stu-id="f30b1-113">Access databases</span></span>|<span data-ttu-id="f30b1-114">Microsoft Access 2007, 2010, 2013.</span><span class="sxs-lookup"><span data-stu-id="f30b1-114">Microsoft Access 2007, 2010, 2013.</span></span>|<span data-ttu-id="f30b1-115">.accdb ou .mdb</span><span class="sxs-lookup"><span data-stu-id="f30b1-115">.accdb or .mdb</span></span>|<span data-ttu-id="f30b1-116">Provedor OLE DB do Microsoft Jet 4.0</span><span class="sxs-lookup"><span data-stu-id="f30b1-116">Microsoft Jet 4.0 OLE DB provider</span></span>|  
|<span data-ttu-id="f30b1-117">SQL Server bancos de dados relacionais <sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f30b1-117">SQL Server relational databases <sup>5</sup></span></span>|<span data-ttu-id="f30b1-118">Microsoft SQL Server 2005, 2008, 2008 R2, 2012, 2014 [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] <sup>2</sup>, SQL Server Parallel Data Warehouse (PDW) <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f30b1-118">Microsoft SQL Server 2005, 2008, 2008 R2, 2012, 2014 [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]<sup>2</sup>, SQL Server Parallel Data Warehouse (PDW) <sup>3</sup></span></span>|<span data-ttu-id="f30b1-119">(não se aplica)</span><span class="sxs-lookup"><span data-stu-id="f30b1-119">(not applicable)</span></span>|<span data-ttu-id="f30b1-120">Provedor OLE DB para SQL Server</span><span class="sxs-lookup"><span data-stu-id="f30b1-120">OLE DB Provider for SQL Server</span></span><br /><br /> <span data-ttu-id="f30b1-121">Provedor OLE DB do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="f30b1-121">SQL Server Native Client OLE DB Provider</span></span><br /><br /> <span data-ttu-id="f30b1-122">Provedor OLE DB do SQL Server Native 11.0 Client</span><span class="sxs-lookup"><span data-stu-id="f30b1-122">SQL Server Native 11.0 Client OLE DB Provider</span></span><br /><br /> <span data-ttu-id="f30b1-123">Provedor de dados .NET Framework para SQL Client</span><span class="sxs-lookup"><span data-stu-id="f30b1-123">.NET Framework Data Provider for SQL Client</span></span>|  
|<span data-ttu-id="f30b1-124">Bancos de dados relacionais da Oracle</span><span class="sxs-lookup"><span data-stu-id="f30b1-124">Oracle relational databases</span></span>|<span data-ttu-id="f30b1-125">Oracle 9i, 10g, 11g.</span><span class="sxs-lookup"><span data-stu-id="f30b1-125">Oracle 9i, 10g, 11g.</span></span>|<span data-ttu-id="f30b1-126">(não se aplica)</span><span class="sxs-lookup"><span data-stu-id="f30b1-126">(not applicable)</span></span>|<span data-ttu-id="f30b1-127">Provedor OLE DB Oracle</span><span class="sxs-lookup"><span data-stu-id="f30b1-127">Oracle OLE DB Provider</span></span><br /><br /> <span data-ttu-id="f30b1-128">Provedor de Dados .NET Framework para Cliente Oracle</span><span class="sxs-lookup"><span data-stu-id="f30b1-128">.NET Framework Data Provider for Oracle Client</span></span><br /><br /> <span data-ttu-id="f30b1-129">Provedor de dados do .NET Framework para SQL Server</span><span class="sxs-lookup"><span data-stu-id="f30b1-129">.NET Framework Data Provider for SQL Server</span></span><br /><br /> <span data-ttu-id="f30b1-130">Provedor de OLE DB MSDAORA <sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f30b1-130">MSDAORA OLE DB provider <sup>4</sup></span></span><br /><br /> <span data-ttu-id="f30b1-131">OraOLEDB</span><span class="sxs-lookup"><span data-stu-id="f30b1-131">OraOLEDB</span></span><br /><br /> <span data-ttu-id="f30b1-132">MSDASQL</span><span class="sxs-lookup"><span data-stu-id="f30b1-132">MSDASQL</span></span>|  
|<span data-ttu-id="f30b1-133">Bancos de dados relacionais do Teradata</span><span class="sxs-lookup"><span data-stu-id="f30b1-133">Teradata relational databases</span></span>|<span data-ttu-id="f30b1-134">Teradata V2R6, V12</span><span class="sxs-lookup"><span data-stu-id="f30b1-134">Teradata V2R6, V12</span></span>|<span data-ttu-id="f30b1-135">(não se aplica)</span><span class="sxs-lookup"><span data-stu-id="f30b1-135">(not applicable)</span></span>|<span data-ttu-id="f30b1-136">Provedor OLE DB TDOLEDB</span><span class="sxs-lookup"><span data-stu-id="f30b1-136">TDOLEDB OLE DB provider</span></span><br /><br /> <span data-ttu-id="f30b1-137">Provedor de .NET Data para Teradata</span><span class="sxs-lookup"><span data-stu-id="f30b1-137">.Net Data Provider for Teradata</span></span>|  
|<span data-ttu-id="f30b1-138">Bancos de dados relacionais do Informix</span><span class="sxs-lookup"><span data-stu-id="f30b1-138">Informix relational databases</span></span>|<span data-ttu-id="f30b1-139">V11.10</span><span class="sxs-lookup"><span data-stu-id="f30b1-139">V11.10</span></span>|<span data-ttu-id="f30b1-140">(não se aplica)</span><span class="sxs-lookup"><span data-stu-id="f30b1-140">(not applicable)</span></span>|<span data-ttu-id="f30b1-141">Provedor OLE DB para Informix</span><span class="sxs-lookup"><span data-stu-id="f30b1-141">Informix OLE DB provider</span></span>|  
|<span data-ttu-id="f30b1-142">Bancos de dados relacionais IBM DB2</span><span class="sxs-lookup"><span data-stu-id="f30b1-142">IBM DB2 relational databases</span></span>|<span data-ttu-id="f30b1-143">8.1</span><span class="sxs-lookup"><span data-stu-id="f30b1-143">8.1</span></span>|<span data-ttu-id="f30b1-144">(não se aplica)</span><span class="sxs-lookup"><span data-stu-id="f30b1-144">(not applicable)</span></span>|<span data-ttu-id="f30b1-145">DB2OLEDB</span><span class="sxs-lookup"><span data-stu-id="f30b1-145">DB2OLEDB</span></span>|  
|<span data-ttu-id="f30b1-146">Bancos de dados relacionais do Sybase Adaptive Server Enterprise (ASE)</span><span class="sxs-lookup"><span data-stu-id="f30b1-146">Sybase Adaptive Server Enterprise (ASE) relational databases</span></span>|<span data-ttu-id="f30b1-147">15.0.2</span><span class="sxs-lookup"><span data-stu-id="f30b1-147">15.0.2</span></span>|<span data-ttu-id="f30b1-148">(não se aplica)</span><span class="sxs-lookup"><span data-stu-id="f30b1-148">(not applicable)</span></span>|<span data-ttu-id="f30b1-149">Provedor OLE DB para Sybase</span><span class="sxs-lookup"><span data-stu-id="f30b1-149">Sybase OLE DB provider</span></span>|  
|<span data-ttu-id="f30b1-150">Outros bancos de dados relacionais</span><span class="sxs-lookup"><span data-stu-id="f30b1-150">Other relational databases</span></span>|<span data-ttu-id="f30b1-151">(não se aplica)</span><span class="sxs-lookup"><span data-stu-id="f30b1-151">(not applicable)</span></span>|<span data-ttu-id="f30b1-152">(não se aplica)</span><span class="sxs-lookup"><span data-stu-id="f30b1-152">(not applicable)</span></span>|<span data-ttu-id="f30b1-153">Um provedor de OLE DB</span><span class="sxs-lookup"><span data-stu-id="f30b1-153">An OLE DB provider</span></span>|  
  
 <span data-ttu-id="f30b1-154"><sup>1</sup> fontes de dados ODBC não têm suporte para soluções multidimensionais.</span><span class="sxs-lookup"><span data-stu-id="f30b1-154"><sup>1</sup> ODBC data sources are not supported for multidimensional solutions.</span></span> <span data-ttu-id="f30b1-155">Embora o próprio Analysis Services trate a conexão, os designers no [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] usado para criar soluções não podem se conectar a uma fonte de dados ODBC, mesmo ao usar driver do MSDASQL.</span><span class="sxs-lookup"><span data-stu-id="f30b1-155">Although Analysis Services itself will handle the connection, the designers in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] used for building solutions cannot connect to an ODBC data source, even when using the MSDASQL driver.</span></span> <span data-ttu-id="f30b1-156">Se seus requisitos comerciais incluírem uma fonte de dados ODBC, crie uma solução tabelar em vez disso.</span><span class="sxs-lookup"><span data-stu-id="f30b1-156">If your business requirements include an ODBC data source, consider building a tabular solution instead.</span></span>  
  
 <span data-ttu-id="f30b1-157"><sup>2</sup> para obter mais informações, consulte [!INCLUDE[ssSDS](../../includes/sssds-md.md)] , em [Azure.Microsoft.com](https://go.microsoft.com/fwlink/?LinkID=157856).</span><span class="sxs-lookup"><span data-stu-id="f30b1-157"><sup>2</sup> For more information, see [!INCLUDE[ssSDS](../../includes/sssds-md.md)], on [azure.microsoft.com](https://go.microsoft.com/fwlink/?LinkID=157856).</span></span>  
  
 <span data-ttu-id="f30b1-158"><sup>3</sup> para obter mais informações sobre o [!INCLUDE[ssSDS](../../includes/sssds-md.md)] PDW, consulte [SQL Server Data Warehouse paralelos](https://go.microsoft.com/fwlink/?LinkId=150895).</span><span class="sxs-lookup"><span data-stu-id="f30b1-158"><sup>3</sup> For more information about [!INCLUDE[ssSDS](../../includes/sssds-md.md)] PDW, see [SQL Server Parallel Data Warehouse](https://go.microsoft.com/fwlink/?LinkId=150895).</span></span>  
  
 <span data-ttu-id="f30b1-159"><sup>4</sup> em alguns casos, usar o provedor de OLE DB MSDAORA pode resultar em erros de conexão, especialmente com versões mais recentes do Oracle.</span><span class="sxs-lookup"><span data-stu-id="f30b1-159"><sup>4</sup> In some cases, using the MSDAORA OLE DB provider can result in connection errors, particularly with newer versions of Oracle.</span></span> <span data-ttu-id="f30b1-160">Se você encontrar algum erro, será recomendável usar um dos outros provedores listados para Oracle.</span><span class="sxs-lookup"><span data-stu-id="f30b1-160">If you encounter any errors, we recommend that you use one of the other providers listed for Oracle.</span></span>  
  
 <span data-ttu-id="f30b1-161"><sup>5</sup> alguns recursos exigem um SQL Server banco de dados relacional que é executado localmente.</span><span class="sxs-lookup"><span data-stu-id="f30b1-161"><sup>5</sup> Some features require a SQL Server relational database that runs on-premises.</span></span> <span data-ttu-id="f30b1-162">Mais especificamente, os armazenamentos ROLAP e de write-back requerem que a fonte de dados subjacente seja um banco de dados relacional do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f30b1-162">Specifically, writeback and ROLAP storage require that the underlying data source is a SQL Server relational database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f30b1-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f30b1-163">See Also</span></span>  
 <span data-ttu-id="f30b1-164">[Fontes de dados com suporte &#40;SSAS de tabela&#41;](../tabular-models/data-sources-supported-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="f30b1-164">[Data Sources Supported &#40;SSAS Tabular&#41;](../tabular-models/data-sources-supported-ssas-tabular.md) </span></span>  
 <span data-ttu-id="f30b1-165">[Fontes de dados em modelos multidimensionais](data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="f30b1-165">[Data Sources in Multidimensional Models](data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="f30b1-166">Exibições de fontes de dados em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="f30b1-166">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  