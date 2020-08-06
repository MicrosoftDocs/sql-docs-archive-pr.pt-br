---
title: 'Não é possível atualizar dados de uma conexão de dados na pasta de trabalho. Tente outra vez ou entre em contato com o administrador do sistema. As seguintes conexões não foram atualizadas: dados PowerPivot | Microsoft Docs'
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0f6fd52d-ac72-43e3-aa08-05a2d2bb873d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9c25c2597bbc7aa16fb8b66d4ffddbf0df14515e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683732"
---
# <a name="unable-to-refresh-data-for-a-data-connection-in-the-workbook-try-again-or-contact-your-system-administrator-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="065de-104">Não é possível atualizar dados de uma conexão de dados na pasta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="065de-104">Unable to refresh data for a data connection in the workbook.</span></span> <span data-ttu-id="065de-105">Tente outra vez ou entre em contato com o administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="065de-105">Try again or contact your system administrator.</span></span> <span data-ttu-id="065de-106">As conexões a seguir não foram atualizadas: Dados PowerPivot</span><span class="sxs-lookup"><span data-stu-id="065de-106">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="065de-107">Para pastas de trabalho do Excel contendo dados PowerPivot, os Serviços do Excel retornam este erro quando submetem uma solicitação de conexão a um servidor do PowerPivot e a solicitação falha.</span><span class="sxs-lookup"><span data-stu-id="065de-107">For Excel workbooks that contain PowerPivot data, Excel Services returns this error if it submits a connection request to a PowerPivot server and the request fails.</span></span>  
  
## <a name="details"></a><span data-ttu-id="065de-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="065de-108">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="065de-109">Aplica-se a:</span><span class="sxs-lookup"><span data-stu-id="065de-109">Applies to:</span></span>|<span data-ttu-id="065de-110">Instalação do PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="065de-110">PowerPivot for SharePoint installation</span></span>|  
|<span data-ttu-id="065de-111">Versão do produto</span><span class="sxs-lookup"><span data-stu-id="065de-111">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="065de-112">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="065de-112">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="065de-113">Causa</span><span class="sxs-lookup"><span data-stu-id="065de-113">Cause</span></span>|<span data-ttu-id="065de-114">Veja abaixo.</span><span class="sxs-lookup"><span data-stu-id="065de-114">See below.</span></span>|  
|<span data-ttu-id="065de-115">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="065de-115">Message Text</span></span>|<span data-ttu-id="065de-116">Não é possível atualizar dados de uma conexão de dados na pasta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="065de-116">Unable to refresh data for a data connection in the workbook.</span></span> <span data-ttu-id="065de-117">Tente outra vez ou entre em contato com o administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="065de-117">Try again or contact your system administrator.</span></span> <span data-ttu-id="065de-118">As conexões a seguir não foram atualizadas: Dados PowerPivot</span><span class="sxs-lookup"><span data-stu-id="065de-118">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation-and-resolution"></a><span data-ttu-id="065de-119">Explicação e resolução</span><span class="sxs-lookup"><span data-stu-id="065de-119">Explanation and Resolution</span></span>  
 <span data-ttu-id="065de-120">Os Serviços do Excel não podem se conectar a nem carregar dados PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="065de-120">Excel Services cannot connect to or load the PowerPivot data.</span></span> <span data-ttu-id="065de-121">As condições que causam esse erro incluem:</span><span class="sxs-lookup"><span data-stu-id="065de-121">Conditions that cause this error to occur include the following:</span></span>  
  
 <span data-ttu-id="065de-122">**Cenário 1: o serviço não é iniciado**</span><span class="sxs-lookup"><span data-stu-id="065de-122">**Scenario 1: Service is not started**</span></span>  
  
 <span data-ttu-id="065de-123">A instância do SQL Server Analysis Services (PowerPivot) não é iniciada.</span><span class="sxs-lookup"><span data-stu-id="065de-123">The SQL Server Analysis Services (PowerPivot) instance is not started.</span></span> <span data-ttu-id="065de-124">Uma senha expirada interromperá a execução do serviço.</span><span class="sxs-lookup"><span data-stu-id="065de-124">An expired password will cause the service to stop running.</span></span> <span data-ttu-id="065de-125">Para obter mais informações sobre como alterar a senha, consulte [Configurar contas de serviço PowerPivot](configure-power-pivot-service-accounts.md) e [Iniciar ou parar um servidor de PowerPivot para SharePoint](start-or-stop-a-power-pivot-for-sharepoint-server.md).</span><span class="sxs-lookup"><span data-stu-id="065de-125">For more information about changing the password, see [Configure PowerPivot Service Accounts](configure-power-pivot-service-accounts.md) and [Start or Stop a PowerPivot for SharePoint Server](start-or-stop-a-power-pivot-for-sharepoint-server.md).</span></span>  
  
 <span data-ttu-id="065de-126">**Cenário 2a: Abrindo uma pasta de trabalho de versão anterior no servidor**</span><span class="sxs-lookup"><span data-stu-id="065de-126">**Scenario 2a: Opening an earlier version workbook n the server**</span></span>  
  
 <span data-ttu-id="065de-127">A pasta de trabalho que você está tentando abrir pode ter sido criada na versão SQL Server 2008 R2 do PowerPivot para Excel.</span><span class="sxs-lookup"><span data-stu-id="065de-127">The workbook you are attempting to open might have been created in the SQL Server 2008 R2 version of PowerPivot for Excel.</span></span> <span data-ttu-id="065de-128">Muito provavelmente, o provedor de dados do Analysis Services especificado na cadeia de conexão de dados não está presente no computador que está executando a solicitação.</span><span class="sxs-lookup"><span data-stu-id="065de-128">Most likely, the Analysis Services data provider that is specified in the data connection string is not present on the computer that is handling the request.</span></span>  
  
 <span data-ttu-id="065de-129">Se esse for o caso, você encontrará essa mensagem no log ULS: "falha na atualização de ' dados PowerPivot ' na pasta de trabalho ' \<URL to workbook> '", seguida por "não é possível obter uma conexão".</span><span class="sxs-lookup"><span data-stu-id="065de-129">If this is the case, you will find this message in the ULS log: "Refresh failed for 'PowerPivot Data' in the workbook '\<URL to workbook>'", followed by "Unable to get a connection".</span></span>  
  
 <span data-ttu-id="065de-130">Para determinar a versão da pasta de trabalho, abra-a no Excel e verifique o provedor de dados que está especificado na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="065de-130">To determine the version of the workbook, open it in Excel and check which data provider is specified in the connection string.</span></span> <span data-ttu-id="065de-131">Uma pasta de trabalho do SQL Server 2008 R2 usa MSOLAP.4 como provedor de dados.</span><span class="sxs-lookup"><span data-stu-id="065de-131">A SQL Server 2008 R2 workbook uses MSOLAP.4 as its data provider.</span></span>  
  
 <span data-ttu-id="065de-132">Para resolver esse problema, você pode atualizar a pasta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="065de-132">To work around this issue, you can upgrade the workbook.</span></span> <span data-ttu-id="065de-133">Opcionalmente, você pode instalar bibliotecas de cliente da versão SQL Server 2008 R2 do Analysis Services nos computadores físicos que executam o PowerPivot para SharePoint ou Serviços do Excel:</span><span class="sxs-lookup"><span data-stu-id="065de-133">Alternatively, you can install client libraries from the SQL Server 2008 R2 version of Analysis Services on the physical computers running PowerPivot for SharePoint or Excel Services:</span></span>  
  
 [<span data-ttu-id="065de-134">Instalar o Provedor Analysis Services OLE DB nos servidores do SharePoint</span><span class="sxs-lookup"><span data-stu-id="065de-134">Install the Analysis Services OLE DB Provider on SharePoint Servers</span></span>](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md)  
  
 <span data-ttu-id="065de-135">**Cenário 2b: Serviços do Excel em execução em um servidor de aplicativos que tem a versão incorreta das bibliotecas de cliente**</span><span class="sxs-lookup"><span data-stu-id="065de-135">**Scenario 2b: Excel Services is running on an application server that has the wrong version of the client libraries**</span></span>  
  
 <span data-ttu-id="065de-136">Por padrão, o SharePoint Server 2010 instala a versão SQL Server 2008 do provedor OLE DB do Analysis Services em servidores de aplicativos que executam Serviços do Excel.</span><span class="sxs-lookup"><span data-stu-id="065de-136">By default, SharePoint Server 2010 installs the SQL Server 2008 version of the Analysis Services OLE DB provider on application servers that run Excel Services.</span></span> <span data-ttu-id="065de-137">Em um farm com suporte para o acesso a dados PowerPivot, todos os servidores físicos que executam aplicativos que exigem dados PowerPivot, como Serviços do Excel e PowerPivot para SharePoint, devem usar uma versão posterior do provedor de dados.</span><span class="sxs-lookup"><span data-stu-id="065de-137">In a farm that supports PowerPivot data access, all physical servers running applications that request PowerPivot data, such as Excel Services and PowerPivot for SharePoint, must use a later version of the data provider.</span></span>  
  
 <span data-ttu-id="065de-138">Os servidores que executam o PowerPivot para SharePoint obtêm o provedor de dados OLE DB atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="065de-138">Servers that run PowerPivot for SharePoint get the updated OLE DB data provider automatically.</span></span> <span data-ttu-id="065de-139">Outros servidores, como os que executam uma instância autônoma dos Serviços do Excel sem o PowerPivot para SharePoint no mesmo computador, devem ser reparados para usar as bibliotecas de cliente mais recentes.</span><span class="sxs-lookup"><span data-stu-id="065de-139">Other servers, such as those running a standalone instance Excel Services without PowerPivot for SharePoint on the same computer, must be patched to use the newer client libraries.</span></span> <span data-ttu-id="065de-140">Para obter mais informações, consulte [Instalar o Provedor OLE DB do Analysis Services nos Servidores SharePoint](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span><span class="sxs-lookup"><span data-stu-id="065de-140">For more information, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span></span>  
  
 <span data-ttu-id="065de-141">**Cenário 3: o controlador de domínio está indisponível.**</span><span class="sxs-lookup"><span data-stu-id="065de-141">**Scenario 3: Domain controller is unavailable**</span></span>  
  
 <span data-ttu-id="065de-142">A causa pode ser um controlador de domínio que não está disponível para validar a identidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="065de-142">The cause might be that a domain controller is not available to validate the user identity.</span></span> <span data-ttu-id="065de-143">Um controlador de domínio é exigido pelas Reivindicações ao Windows Token Service para autenticar o usuário do SharePoint em cada conexão.</span><span class="sxs-lookup"><span data-stu-id="065de-143">A domain controller is required by the Claims to Windows Token Service to authenticate the SharePoint user on each connection.</span></span> <span data-ttu-id="065de-144">O Claims to Windows Token Service não usa credenciais armazenadas em cache.</span><span class="sxs-lookup"><span data-stu-id="065de-144">The Claims to Windows Token Service does not use cached credentials.</span></span> <span data-ttu-id="065de-145">Valida a identidade do usuário para cada conexão.</span><span class="sxs-lookup"><span data-stu-id="065de-145">It validates the user identity for each connection.</span></span>  
  
 <span data-ttu-id="065de-146">Você pode confirmar a causa desse erro exibindo o arquivo de log do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="065de-146">You can confirm the cause of this error by viewing the SharePoint log file.</span></span> <span data-ttu-id="065de-147">Se os logs do SharePoint incluírem a mensagem "Falha ao obter WindowsIdentity de IClaimsIdentity", não foi possível autenticar a identidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="065de-147">If the SharePoint logs include the message "Failed to get WindowsIdentity from IClaimsIdentity", the user identity could not be authenticated.</span></span>  
  
 <span data-ttu-id="065de-148">Para solucionar este problema, una o computador ao mesmo domínio de servidor do PowerPivot ou instale um controlador de domínio em seu computador local.</span><span class="sxs-lookup"><span data-stu-id="065de-148">To work around this problem, join the computer to the same domain as the PowerPivot server, or install a domain controller on your local computer.</span></span> <span data-ttu-id="065de-149">A segunda solução, instalar o controlador de domínio, exigirá que você crie contas de domínio locais para todos os serviços e usuários.</span><span class="sxs-lookup"><span data-stu-id="065de-149">The second solution, installing the domain controller, will require you to create local domain accounts for all services and users.</span></span> <span data-ttu-id="065de-150">Você precisará configurar contas de serviço e permissões do SharePoint para as contas que definir.</span><span class="sxs-lookup"><span data-stu-id="065de-150">You will need to configure service accounts and SharePoint permissions for the accounts you define.</span></span>  
  
 <span data-ttu-id="065de-151">Instale um controlador de domínio em seu computador será útil se o seu objetivo for usar o PowerPivot para SharePoint no estado offline.</span><span class="sxs-lookup"><span data-stu-id="065de-151">Installing a domain controller on your computer is useful if your objective is to use PowerPivot for SharePoint in an offline state.</span></span> <span data-ttu-id="065de-152">Para obter instruções detalhadas sobre como usar o PowerPivot offline, consulte a entrada de blog "colocando o servidor PowerPivot fora da rede" em [http://www.powerpivotgeek.com](https://go.microsoft.com/fwlink/?LinkId=184241) .</span><span class="sxs-lookup"><span data-stu-id="065de-152">For detailed instructions on how to use PowerPivot offline, see the blog entry for "Taking your PowerPivot server off the network" on [http://www.powerpivotgeek.com](https://go.microsoft.com/fwlink/?LinkId=184241).</span></span>  
  
 <span data-ttu-id="065de-153">**Cenário 4: servidor instável**</span><span class="sxs-lookup"><span data-stu-id="065de-153">**Scenario 4: Unstable server**</span></span>  
  
 <span data-ttu-id="065de-154">Um ou mais serviços podem estar em um estado inconsistente.</span><span class="sxs-lookup"><span data-stu-id="065de-154">One or more services might be in an inconsistent state.</span></span> <span data-ttu-id="065de-155">Em alguns casos, executar IISRESET resolverá o problema.</span><span class="sxs-lookup"><span data-stu-id="065de-155">In some cases, running IISRESET will resolve the problem.</span></span>  
  
  