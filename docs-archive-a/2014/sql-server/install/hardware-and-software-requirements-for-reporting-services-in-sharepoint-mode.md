---
title: Requisitos de hardware e software para Reporting Services no modo do SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ed91877d-4f74-4266-a932-b824b4810c99
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: a4fc19b2871d7d5731649c61a8d5231d7e3479dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582797"
---
# <a name="hardware-and-software-requirements-for-reporting-services-in-sharepoint-mode"></a><span data-ttu-id="fcd4b-102">Requisitos de hardware e software para o Reporting Services no modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="fcd4b-102">Hardware and Software Requirements for Reporting Services in SharePoint Mode</span></span>

  <span data-ttu-id="fcd4b-103">Este tópico descreve os pré-requisitos, os requisitos de hardware e as considerações de instalação para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] execução no modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fcd4b-103">This topic describes prerequisites, hardware requirements, and installation considerations for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] running in SharePoint mode.</span></span> <span data-ttu-id="fcd4b-104">Como o modo SharePoint do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] requer um servidor do SharePoint, a maioria dos requisitos são baseados no ambiente do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fcd4b-104">Because [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode requires a SharePoint server, most of the requirements are based on the SharePoint environment.</span></span> <span data-ttu-id="fcd4b-105">Para servidores de relatório no modo nativo, o seu hardware deve atender aos requisitos mínimos de hardware e software para executar o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcd4b-105">For native mode report servers, your hardware should meet minimum hardware and software requirements for running [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="fcd4b-106">Para obter mais informações, consulte [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fcd4b-106">For more information, see [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="fcd4b-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="fcd4b-107">Prerequisites</span></span>](#bkmk_prereq)  
  
-   [<span data-ttu-id="fcd4b-108">Requisitos de banco de dados do servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="fcd4b-108">Report Server Database Requirements</span></span>](#bkmk_report_server_database)  
  
-   [<span data-ttu-id="fcd4b-109">Requisitos do Power View</span><span class="sxs-lookup"><span data-stu-id="fcd4b-109">Power View Requirements</span></span>](#bkmk_powerview)  
  
-   [<span data-ttu-id="fcd4b-110">Mais informações</span><span class="sxs-lookup"><span data-stu-id="fcd4b-110">More Information</span></span>](#bkmk_more_information)  
  
##  <a name="prerequisites"></a><a name="bkmk_prereq"></a> <span data-ttu-id="fcd4b-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="fcd4b-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="fcd4b-112">Para instalações locais, a conta registrada durante a instalação do SharePoint e do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] precisa ser membro do grupo de administradores no sistema operacional local.</span><span class="sxs-lookup"><span data-stu-id="fcd4b-112">For local installations, the account logged in during installation of SharePoint and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] needs to be a member of the administrators group in the local operating system.</span></span> <span data-ttu-id="fcd4b-113">A conta de instalação não precisa ser membro do grupo de administradores de farm do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fcd4b-113">The setup account does not need to be a member of the SharePoint farm administrators group.</span></span>  
  
     <span data-ttu-id="fcd4b-114">Para obter mais informações, consulte [Permissões de conta e configurações de segurança no SharePoint 2013](https://technet.microsoft.com/library/cc678863.aspx).</span><span class="sxs-lookup"><span data-stu-id="fcd4b-114">For more information, see [Account permissions and security settings in SharePoint 2013](https://technet.microsoft.com/library/cc678863.aspx).</span></span>  
  
-   <span data-ttu-id="fcd4b-115">O [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que é executado no modo do SharePoint exige o SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="fcd4b-115">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] running in SharePoint mode requires SharePoint Server.</span></span> <span data-ttu-id="fcd4b-116">Para obter mais informações sobre os requisitos e as configurações do SharePoint, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fcd4b-116">For more information about SharePoint requirements and configurations, see the following:</span></span>  
  
    -   <span data-ttu-id="fcd4b-117">[Requisitos de hardware e software (SharePoint 2013)](https://go.microsoft.com/fwlink/p/?LinkId=256365) (https://go.microsoft.com/fwlink/p/?LinkId=256365)</span><span class="sxs-lookup"><span data-stu-id="fcd4b-117">[Hardware and software requirements (SharePoint 2013)](https://go.microsoft.com/fwlink/p/?LinkId=256365) (https://go.microsoft.com/fwlink/p/?LinkId=256365)</span></span>  
  
    -   [<span data-ttu-id="fcd4b-118">Gerenciamento e dimensionamento de capacidade do SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcd4b-118">Capacity management and sizing for SharePoint Server 2013</span></span>](https://technet.microsoft.com/library/cc261700.aspx)  
  
    -   [<span data-ttu-id="fcd4b-119">Requisitos de software para business intelligence (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="fcd4b-119">Software requirements for business intelligence (SharePoint 2013)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=256367)  
  
    -   <span data-ttu-id="fcd4b-120">[Requisitos de hardware e de software (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262485\(v=office.14\))</span><span class="sxs-lookup"><span data-stu-id="fcd4b-120">[Hardware and software requirements (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262485\(v=office.14\))</span></span>  
  
    -   <span data-ttu-id="fcd4b-121">[Gerenciamento e dimensionamento de capacidade do SharePoint Server 2010](https://technet.microsoft.com/library/cc261700.aspx\(v=office.14\))</span><span class="sxs-lookup"><span data-stu-id="fcd4b-121">[Capacity management and sizing for SharePoint Server 2010](https://technet.microsoft.com/library/cc261700.aspx\(v=office.14\))</span></span>  
  
-   <span data-ttu-id="fcd4b-122">Se você quiser atualizar uma instalação existente do SharePoint do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] com o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], consulte [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="fcd4b-122">If you want to upgrade or update existing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint installation with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="fcd4b-123">Verifique se o serviço **Administração do SharePoint 2013** foi iniciado no Windows Server Manager.</span><span class="sxs-lookup"><span data-stu-id="fcd4b-123">Verify the **SharePoint 2013 Administration** service is started in Windows Server Manager.</span></span>  
  
###  <a name="report-server-database-requirements"></a><a name="bkmk_report_server_database"></a> <span data-ttu-id="fcd4b-124">Requisitos de banco de dados do servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="fcd4b-124">Report Server Database Requirements</span></span>  
  
-   <span data-ttu-id="fcd4b-125">Os produtos e as tecnologias do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e do SharePoint usam bancos de dados relacionais do SQL Server para armazenar dados de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fcd4b-125">Both [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and SharePoint products and technologies use SQL Server relational databases to store application data.</span></span>  
  
-   <span data-ttu-id="fcd4b-126">O [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)] requer uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] de uma edição compatível do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fcd4b-126">[!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)] requires an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] of a compatible SQL Server edition.</span></span> <span data-ttu-id="fcd4b-127">Para obter mais informações sobre requisitos de hardware e software, consulte [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fcd4b-127">For more information on hardware and software requirements, see [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
-   <span data-ttu-id="fcd4b-128">Os produtos do SharePoint poderão usar uma instância de banco de dados existente.</span><span class="sxs-lookup"><span data-stu-id="fcd4b-128">SharePoint products can use an existing database instance.</span></span> <span data-ttu-id="fcd4b-129">Se uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] não estiver instalada, a Instalação dos Produtos do SharePoint instalará o SQL Server Express Edition para os bancos de dados de aplicativo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fcd4b-129">If an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] is not installed, the SharePoint Products Setup program installs SQL Server Express Edition for the SharePoint application databases.</span></span>  
  
-   <span data-ttu-id="fcd4b-130">A instância do servidor de relatório não pode usar o SQL Server Express Edition para seu banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fcd4b-130">The report server instance cannot use the SQL Server Express Edition for its database.</span></span> <span data-ttu-id="fcd4b-131">No entanto, a instância do SQL Server Express Edition instalada pelo produto ou tecnologia do SharePoint pode existir lado a lado com outras edições do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="fcd4b-131">However, the SQL Server Express Edition instance installed by the SharePoint product can exist side-by-side with other Database Engine editions.</span></span>  
  
##  <a name="sscrescent-requirements"></a><a name="bkmk_powerview"></a><span data-ttu-id="fcd4b-132">[!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)]Requisitos do</span><span class="sxs-lookup"><span data-stu-id="fcd4b-132">[!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] Requirements</span></span>

 <span data-ttu-id="fcd4b-133">Analise a [documentação do Power View](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx) mais atualizada em Office.Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="fcd4b-133">Review the most up-to-date [Power View documentation](https://office.microsoft.com/excel-help/power-view-explore-visualize-and-present-your-data-HA102835634.aspx) on Office.Microsoft.com.</span></span> <span data-ttu-id="fcd4b-134">O [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] é um recurso do Microsoft Excel 2013 e faz parte do suplemento [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Reporting Services para Microsoft SharePoint Server 2010 e 2013 Enterprise Editions.</span><span class="sxs-lookup"><span data-stu-id="fcd4b-134">[!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] is a feature of Microsoft Excel 2013, and is part of the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Reporting Services add-in for Microsoft SharePoint Server 2010 and 2013 Enterprise Editions.</span></span>  
  
##  <a name="more-information"></a><a name="bkmk_more_information"></a> <span data-ttu-id="fcd4b-135">Mais informações</span><span class="sxs-lookup"><span data-stu-id="fcd4b-135">More Information</span></span>

 <span data-ttu-id="fcd4b-136">Para obter informações sobre as alterações do SharePoint, consulte [alterações do sharepoint 2010 para o sharepoint 2013](https://technet.microsoft.com/library/ff607742\(office.15\).aspx) ( https://technet.microsoft.com/library/ff607742(office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="fcd4b-136">For information on SharePoint changes, see [Changes from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/ff607742\(office.15\).aspx) (https://technet.microsoft.com/library/ff607742(office.15).aspx).</span></span>  
  
 <span data-ttu-id="fcd4b-137">[Notas de versão do SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296445).</span><span class="sxs-lookup"><span data-stu-id="fcd4b-137">[SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445).</span></span>  
  