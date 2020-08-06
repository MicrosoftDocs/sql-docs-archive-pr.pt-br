---
title: Conectar ao Servidor (página Logon) Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttors.login.f1
helpviewer_keywords:
- Connect to Server dialog box, Reporting Services
ms.assetid: d312c740-19d7-4931-84a2-88b805ec8439
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 16c1a4f8b5560e2d49d9eb13ca3bdd5594461517
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684874"
---
# <a name="connect-to-server-login-page-reporting-services"></a><span data-ttu-id="6439e-102">Conectar ao Servidor (página Logon) Reporting Services</span><span class="sxs-lookup"><span data-stu-id="6439e-102">Connect to Server (Login Page) Reporting Services</span></span>
  <span data-ttu-id="6439e-103">Use essa guia para exibir ou especificar as opções a seguir ao se conectar ao [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6439e-103">Use this tab to view or specify the following options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="6439e-104">Opções</span><span class="sxs-lookup"><span data-stu-id="6439e-104">Options</span></span>  
 <span data-ttu-id="6439e-105">**Tipo de servidor**</span><span class="sxs-lookup"><span data-stu-id="6439e-105">**Server type**</span></span>  
 <span data-ttu-id="6439e-106">Ao registrar um servidor a partir do Pesquisador de Objetos, selecione o tipo de servidor ao qual se conectar: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services ou Integration Services.</span><span class="sxs-lookup"><span data-stu-id="6439e-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="6439e-107">O restante da caixa de diálogo mostra somente as opções que válidas ao tipo de servidor selecionado.</span><span class="sxs-lookup"><span data-stu-id="6439e-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="6439e-108">Ao registrar um servidor de Servidores Registrados, a caixa **Tipo de servidor** é somente leitura e corresponde ao tipo de servidor exibido no componente Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="6439e-108">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="6439e-109">Para registrar outro tipo de servidor, selecione [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services ou Integration Services na barra de ferramentas Servidores Registrados antes de iniciar o registro de um novo servidor.</span><span class="sxs-lookup"><span data-stu-id="6439e-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="6439e-110">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="6439e-110">**Server name**</span></span>  
 <span data-ttu-id="6439e-111">O modo de servidor da instância de servidor de relatório à qual você está se conectando determina o valor que você deve inserir.</span><span class="sxs-lookup"><span data-stu-id="6439e-111">The server mode of the report server instance you are connecting to determines the value you must enter.</span></span>  
  
 <span data-ttu-id="6439e-112">Para um servidor de relatório executado no modo nativo, especifique a instância do servidor de relatório à qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="6439e-112">For a report server that runs in native mode, specify the report server instance to connect to.</span></span> <span data-ttu-id="6439e-113">Se você estiver usando a instância padrão, geralmente, o nome do servidor será o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="6439e-113">If you are using the default instance, the server name is typically the name of the computer.</span></span> <span data-ttu-id="6439e-114">Se você instalou uma instância nomeada, acrescente o nome da instância ao nome do servidor neste formato: \<servername> \\<InstanceName \> .</span><span class="sxs-lookup"><span data-stu-id="6439e-114">If you installed a named instance, append the instance name to the server name in this format: \<servername>\\<InstanceName\>.</span></span> <span data-ttu-id="6439e-115">O Reporting Services usa o caractere de barra invertida para delimitar o nome da instância.</span><span class="sxs-lookup"><span data-stu-id="6439e-115">Reporting Services uses the backslash character to delimit the instance name.</span></span>  
  
 <span data-ttu-id="6439e-116">Para um servidor de relatório executado no SharePoint em modo integrado, especifique um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6439e-116">For a report server that runs in SharePoint integrated mode, you must specify a SharePoint site.</span></span> <span data-ttu-id="6439e-117">Você pode especificar qualquer site de uma coleção de sites que foi integrada ao [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6439e-117">You can specify any site in a site collection that is integrated with [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="6439e-118">O URL que você fornecer deve incluir o HTTP ou prefixo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6439e-118">The URL that you provide must include the HTTP or HTTPS prefix.</span></span> <span data-ttu-id="6439e-119">Você deve ter permissão para acessar o site do SharePoint para se conectar a ele no Management Studio.</span><span class="sxs-lookup"><span data-stu-id="6439e-119">You must have permission to access the SharePoint site in order to connect to it in Management Studio.</span></span> <span data-ttu-id="6439e-120">O nível de permissão que foi atribuído a você determinará quais itens você pode exibir e gerenciar.</span><span class="sxs-lookup"><span data-stu-id="6439e-120">The permission level you are assigned to will determine which items you can view and manage.</span></span> <span data-ttu-id="6439e-121">Para obter mais informações, consulte [Conectar-se a um servidor de relatório no Management Studio](../reporting-services/tools/connect-to-a-report-server-in-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="6439e-121">For more information, see [Connect to a Report Server in Management Studio](../reporting-services/tools/connect-to-a-report-server-in-management-studio.md).</span></span>  
  
 <span data-ttu-id="6439e-122">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="6439e-122">**Authentication**</span></span>  
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="6439e-123">pode ser configurado para aceitar solicitações de Autenticação do Windows ou de Autenticação de formulários que são manipulados por uma extensão de autenticação personalizada fornecida por você.</span><span class="sxs-lookup"><span data-stu-id="6439e-123">can be configured to accept Windows Authentication requests or Forms authentication requests that are handled by a custom authentication extension that you provide.</span></span> <span data-ttu-id="6439e-124">Selecione um dos seguintes modos de autenticação ao se conectar ao Reporting Services:</span><span class="sxs-lookup"><span data-stu-id="6439e-124">Select from one of the following authentication modes when connecting to Reporting Services:</span></span>  
  
 <span data-ttu-id="6439e-125">**Modo de Autenticação do Windows (Autenticação do Windows)**</span><span class="sxs-lookup"><span data-stu-id="6439e-125">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="6439e-126">Conecte-se à instância de servidor de relatório usando as credenciais do [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="6439e-126">Connect to the report server instance using your [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows credentials.</span></span>  
  
 <span data-ttu-id="6439e-127">**Autenticação básica**</span><span class="sxs-lookup"><span data-stu-id="6439e-127">**Basic Authentication**</span></span>  
 <span data-ttu-id="6439e-128">Conecte-se usando a **Autenticação Básica** se a instalação do Reporting Services estiver configurada para usar a Autenticação Básica.</span><span class="sxs-lookup"><span data-stu-id="6439e-128">Connect using **Basic Authentication** if your Reporting Services installation is configured to use Basic Authentication.</span></span>  
  
 <span data-ttu-id="6439e-129">**Autenticação de Formulários**</span><span class="sxs-lookup"><span data-stu-id="6439e-129">**Forms Authentication**</span></span>  
 <span data-ttu-id="6439e-130">Conecte-se usando a **Autenticação de Formulários** se a instalação do Reporting Services estiver configurada para usar uma extensão de autenticação personalizada.</span><span class="sxs-lookup"><span data-stu-id="6439e-130">Connect using **Forms Authentication** if your Reporting Services installation is configured to use a custom authentication extension.</span></span>  
  
 <span data-ttu-id="6439e-131">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="6439e-131">**User Name**</span></span>  
 <span data-ttu-id="6439e-132">Digite o nome de logon a ser usado na conexão.</span><span class="sxs-lookup"><span data-stu-id="6439e-132">Enter the login name to use for the connection.</span></span> <span data-ttu-id="6439e-133">Essa opção estará disponível somente se você selecionou **Básica** ou **Autenticação de Formulários**.</span><span class="sxs-lookup"><span data-stu-id="6439e-133">This option is only available if you have selected **Basic** or **Forms Authentication**.</span></span>  
  
 <span data-ttu-id="6439e-134">**Senha**</span><span class="sxs-lookup"><span data-stu-id="6439e-134">**Password**</span></span>  
 <span data-ttu-id="6439e-135">Digite a senha para o nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="6439e-135">Enter the password for the user name.</span></span> <span data-ttu-id="6439e-136">Essa opção só poderá ser editada se você selecionou **Básica** ou **Autenticação de Formulários**.</span><span class="sxs-lookup"><span data-stu-id="6439e-136">This option is only editable if you have selected **Basic** or **Forms Authentication**.</span></span>  
  
 <span data-ttu-id="6439e-137">**Lembrar senha**</span><span class="sxs-lookup"><span data-stu-id="6439e-137">**Remember password**</span></span>  
 <span data-ttu-id="6439e-138">Armazene a senha que você digitou.</span><span class="sxs-lookup"><span data-stu-id="6439e-138">Store the password you have entered.</span></span> <span data-ttu-id="6439e-139">Essa opção será exibida somente se você clicar em **Opções**e poderá ser editada apenas se você selecionou conectar-se usando **Básica** ou **Autenticação de Formulários**.</span><span class="sxs-lookup"><span data-stu-id="6439e-139">This option is only displayed if you click **Options**, and it is only editable if you have selected to connect using **Basic** or **Forms Authentication**.</span></span>  
  
 <span data-ttu-id="6439e-140">**Connect**</span><span class="sxs-lookup"><span data-stu-id="6439e-140">**Connect**</span></span>  
 <span data-ttu-id="6439e-141">Conecte-se ao servidor selecionado.</span><span class="sxs-lookup"><span data-stu-id="6439e-141">Connect to the selected server.</span></span>  
  
 <span data-ttu-id="6439e-142">**Opções**</span><span class="sxs-lookup"><span data-stu-id="6439e-142">**Options**</span></span>  
 <span data-ttu-id="6439e-143">Exiba opções de conexão de servidor adicionais, como lembrar a senha.</span><span class="sxs-lookup"><span data-stu-id="6439e-143">Display additional server connection options, such as remembering the password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6439e-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6439e-144">See Also</span></span>  
 <span data-ttu-id="6439e-145">[Configurar uma conexão de banco de dados do servidor de relatório &#40;Configuration Manager SSRS&#41;](../../2014/sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="6439e-145">[Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;](../../2014/sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="6439e-146">[Conectar-se a um servidor de relatório no Management Studio](../reporting-services/tools/connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="6439e-146">[Connect to a Report Server in Management Studio](../reporting-services/tools/connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="6439e-147">Autenticação com o servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="6439e-147">Authentication with the Report Server</span></span>](../reporting-services/security/authentication-with-the-report-server.md)  
  
  