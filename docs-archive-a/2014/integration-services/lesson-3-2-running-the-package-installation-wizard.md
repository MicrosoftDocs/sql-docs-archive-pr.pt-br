---
title: 'Etapa 2: executar o Assistente de Instalação de Pacotes | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f91fbb89-4626-4c47-b96d-56052dc45861
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9492f9ecc843ef475a3c5d32cde2952e0ff498fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678861"
---
# <a name="step-2-running-the-package-installation-wizard"></a><span data-ttu-id="dd728-102">Etapa 2: Executar o Assistente de Instalação de Pacotes</span><span class="sxs-lookup"><span data-stu-id="dd728-102">Step 2: Running the Package Installation Wizard</span></span>
  <span data-ttu-id="dd728-103">Nesta tarefa, você executará o Assistente de Instalação de Pacotes para implantar os pacotes do projeto Tutorial de Implantação em uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd728-103">In this task, you will run the Package Installation Wizard to deploy the packages from the Deployment Tutorial project to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dd728-104">Somente pacotes podem ser instalados na tabela sysssispackages no banco de dados msdb do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] . Os arquivos que dão suporte incluídos no pacote de implantação serão implantados no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="dd728-104">Only packages can be installed in the sysssispackages table in the msdb [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database, the supporting files that the deployment bundle includes will be deployed to the file system.</span></span>  
  
 <span data-ttu-id="dd728-105">O Assistente de Instalação de Pacotes o guiará pelas etapas para instalar e configurar os pacotes.</span><span class="sxs-lookup"><span data-stu-id="dd728-105">The Package Installation Wizard will guide you through the steps to install and configure the packages.</span></span> <span data-ttu-id="dd728-106">Você instalará os pacotes em uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no computador de destino (o computador em que você copiou o pacote de implantação).</span><span class="sxs-lookup"><span data-stu-id="dd728-106">You will install the packages to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the destination computer (the computer to which you copied the deployment bundle.</span></span> <span data-ttu-id="dd728-107">Você também criará uma pasta, C:\DeploymentTutorialInstall, em que o assistente instalará os arquivos que não são pacotes.</span><span class="sxs-lookup"><span data-stu-id="dd728-107">You will also create a folder, C:\DeploymentTutorialInstall, in which the wizard will install the non-package files.</span></span>  
  
 <span data-ttu-id="dd728-108">Em uma lição anterior, você modificou os pacotes no tutorial para usar as configurações.</span><span class="sxs-lookup"><span data-stu-id="dd728-108">In an earlier lesson, you modified the packages in the tutorial to use configurations.</span></span> <span data-ttu-id="dd728-109">Usando o Assistente de Instalação de Pacotes, você editará essas configurações para habilitar os pacotes a serem executados com êxito no ambiente em que foram instalados.</span><span class="sxs-lookup"><span data-stu-id="dd728-109">Using the Package Installation Wizard, you will edit these configurations to enable packages to run successfully in the installed-to environment.</span></span>  
  
### <a name="to-install-the-packages"></a><span data-ttu-id="dd728-110">Para instalar os pacotes</span><span class="sxs-lookup"><span data-stu-id="dd728-110">To install the packages</span></span>  
  
1.  <span data-ttu-id="dd728-111">No computador de destino, localize o pacote de implantação.</span><span class="sxs-lookup"><span data-stu-id="dd728-111">On the destination computer, locate the deployment bundle.</span></span>  
  
     <span data-ttu-id="dd728-112">Se você tiver usado o valor padrão – bin\Deployment – como a localização do utilitário de implantação, o pacote de implantação será a pasta de Implantação do projeto Tutorial de Implantação.</span><span class="sxs-lookup"><span data-stu-id="dd728-112">If you used the default value-bin\Deployment-as the location of the deployment utility, the deployment bundle is the Deployment folder in the Deployment Tutorial project.</span></span>  
  
2.  <span data-ttu-id="dd728-113">Na pasta Implantação, clique duas vezes no arquivo de manifesto, Deployment Tutorial.SSISDeploymentManifest.</span><span class="sxs-lookup"><span data-stu-id="dd728-113">In the Deployment folder, double-click the manifest file, Deployment Tutorial.SSISDeploymentManifest.</span></span>  
  
3.  <span data-ttu-id="dd728-114">Na página inicial do Assistente de Instalação de Pacotes, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dd728-114">On the Welcome page of the Package Installation Wizard, click **Next**.</span></span>  
  
4.  <span data-ttu-id="dd728-115">Na página Implantar Pacotes SSIS, selecione a opção **Implantação no SQL Server** , marque a caixa de seleção **Validar pacotes após instalação** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dd728-115">On the Deploy SSIS Packages page, select the **SQL Server deployment** option, select the **Validate packages after installation** check box, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="dd728-116">Na página Especificar SQL Server de Destino, especifique o **(local)** , na caixa **Nome do servidor** .</span><span class="sxs-lookup"><span data-stu-id="dd728-116">On the Specify Target SQL Server page, specify **(local**), in the **Server name** box.</span></span>  
  
6.  <span data-ttu-id="dd728-117">Se a instância do SQL Server der suporte à Autenticação do Windows, selecione **Usar Autenticação do Windows**; caso contrário, selecione **Usar Autenticação do SQL Server** e forneça um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="dd728-117">If the instance of SQL Server supports Windows Authentication, select **Use Windows Authentication**; otherwise, select **Use SQL Server Authentication** and provide a user name and a password.</span></span>  
  
7.  <span data-ttu-id="dd728-118">Verifique se a caixa de seleção **Depender do armazenamento do servidor para criptografia** está desmarcada.</span><span class="sxs-lookup"><span data-stu-id="dd728-118">Verify that the **Rely on server storage for encryption** check box is cleared.</span></span>  
  
8.  <span data-ttu-id="dd728-119">Clique em **Avançar.**</span><span class="sxs-lookup"><span data-stu-id="dd728-119">Click **Next.**</span></span>  
  
9. <span data-ttu-id="dd728-120">Na página Selecionar Pasta de Instalação, clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="dd728-120">On the Select Installation Folder page, click **Browse.**</span></span>  
  
10. <span data-ttu-id="dd728-121">Na caixa de diálogo **Procurar Pasta** , expanda **Meu Computador** e clique em **Disco Local (C:)** .</span><span class="sxs-lookup"><span data-stu-id="dd728-121">In the **Browse For Folder** dialog box, expand **My Computer** and then click **Local Disk (C:)**.</span></span>  
  
11. <span data-ttu-id="dd728-122">Clique em **Criar Nova Pasta** e substitua o nome padrão da pasta criada, **Nova Pasta**, por **DeploymentTutorialInstall**.</span><span class="sxs-lookup"><span data-stu-id="dd728-122">Click **Make New Folder** and replace the default name of the new folder, **New Folder**, with **DeploymentTutorialInstall**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="dd728-123">Este nome é mencionado no valor das variáveis de ambiente usado pelas configurações.</span><span class="sxs-lookup"><span data-stu-id="dd728-123">This name is referenced in the value of the environment variables that configurations use.</span></span> <span data-ttu-id="dd728-124">O nome da pasta e a referência devem coincidir ou o pacote não será executado.</span><span class="sxs-lookup"><span data-stu-id="dd728-124">The name of the folder and the reference must match or the package cannot run.</span></span>  
  
12. <span data-ttu-id="dd728-125">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd728-125">Click **OK**.</span></span>  
  
13. <span data-ttu-id="dd728-126">Na página Selecionar Pasta de Instalação, verifique se a caixa Pasta contém **C:\DeploymentTutorialInstall** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dd728-126">On the Select Installation Folder page, verify that the Folder box contains **C:\DeploymentTutorialInstall** and then click **Next**.</span></span>  
  
14. <span data-ttu-id="dd728-127">Na página Confirmar Instalação, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dd728-127">On the Confirm Installation page, click **Next**.</span></span>  
  
     <span data-ttu-id="dd728-128">O assistente instala os pacotes.</span><span class="sxs-lookup"><span data-stu-id="dd728-128">The wizard installs the packages.</span></span> <span data-ttu-id="dd728-129">Depois que a instalação for concluída, a página Configurar Pacotes será aberta.</span><span class="sxs-lookup"><span data-stu-id="dd728-129">After installation is completed, the Configure Packages page opens.</span></span>  
  
15. <span data-ttu-id="dd728-130">Na página Configurar Pacotes, verifique se a caixa **Arquivo de configuração** lista datatransferconfig.dtsconfig e loadxmldataconfig.dtsconfig.</span><span class="sxs-lookup"><span data-stu-id="dd728-130">On the Configure Packages page, verify that the **Configuration file** box lists datatransferconfig.dtsconfig and loadxmldataconfig.dtsconfig.</span></span>  
  
16. <span data-ttu-id="dd728-131">Na lista **Arquivo de configuração** , clique em **datatransferconfig.dtsconfig**, expanda Propriedades na coluna **Caminho** da caixa **Configurações** e atualize a coluna **Valor** com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="dd728-131">In the **Configuration file** list, click **datatransferconfig.dtsconfig**, expand Property in the **Path** column of the **Configurations** box, and update the **Value** column with the following values:</span></span>  
  
    |<span data-ttu-id="dd728-132">Propriedade</span><span class="sxs-lookup"><span data-stu-id="dd728-132">Property</span></span>|<span data-ttu-id="dd728-133">Valor</span><span class="sxs-lookup"><span data-stu-id="dd728-133">Value</span></span>|<span data-ttu-id="dd728-134">Valor atualizado</span><span class="sxs-lookup"><span data-stu-id="dd728-134">Updated Value</span></span>|  
    |--------------|-----------|-------------------|  
    |<span data-ttu-id="dd728-135">\Package.Connections[Deployment Tutorial Log].Properties[ConnectionString]</span><span class="sxs-lookup"><span data-stu-id="dd728-135">\Package.Connections[Deployment Tutorial Log].Properties[ConnectionString]</span></span>|<span data-ttu-id="dd728-136">C:\Arquivos de Programas\Microsoft SQL Server\100\Samples\Integration Services\Tutorial\Deploying Packages\Completed Packages\Deployment Tutorial Log</span><span class="sxs-lookup"><span data-stu-id="dd728-136">C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services\Tutorial\Deploying Packages\Completed Packages\Deployment Tutorial Log</span></span>|<span data-ttu-id="dd728-137">C:\DeploymentTutorialInstall\Deployment Tutorial Log</span><span class="sxs-lookup"><span data-stu-id="dd728-137">C:\DeploymentTutorialInstall\Deployment Tutorial Log</span></span>|  
    |<span data-ttu-id="dd728-138">\Package.Connections[NewCustomers].Properties[ConnectionString]</span><span class="sxs-lookup"><span data-stu-id="dd728-138">\Package.Connections[NewCustomers].Properties[ConnectionString]</span></span>|<span data-ttu-id="dd728-139">C:\Arquivos de Programas\Microsoft SQL Server\100\Samples\Integration Services\Tutorial\Deploying Packages\Sample Data\NewCustomers.txt</span><span class="sxs-lookup"><span data-stu-id="dd728-139">C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services\Tutorial\Deploying Packages\Sample Data\NewCustomers.txt</span></span>|<span data-ttu-id="dd728-140">C:\DeploymentTutorialInstall\NewCustomers.txt</span><span class="sxs-lookup"><span data-stu-id="dd728-140">C:\DeploymentTutorialInstall\NewCustomers.txt</span></span>|  
  
17. <span data-ttu-id="dd728-141">Na lista **Arquivo de configuração** , clique em loadxmldataconfig.dtsconfig, expanda Propriedades na coluna **Caminho** da caixa **Configurações** e atualize a coluna **Valor** com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="dd728-141">In the **Configuration file** list, click loadxmldataconfig.dtsconfig, expand Property in the **Path** column of the **Configurations** box, and update the **Value** column with the following values:</span></span>  
  
    |<span data-ttu-id="dd728-142">Propriedade</span><span class="sxs-lookup"><span data-stu-id="dd728-142">Property</span></span>|<span data-ttu-id="dd728-143">Valor</span><span class="sxs-lookup"><span data-stu-id="dd728-143">Value</span></span>|<span data-ttu-id="dd728-144">Valor atualizado</span><span class="sxs-lookup"><span data-stu-id="dd728-144">Updated Value</span></span>|  
    |--------------|-----------|-------------------|  
    |<span data-ttu-id="dd728-145">\Package.LoadXMLData.Properties[[XML Source].[XMLData]]</span><span class="sxs-lookup"><span data-stu-id="dd728-145">\Package.LoadXMLData.Properties[[XML Source].[XMLData]]</span></span>|<span data-ttu-id="dd728-146">C:\Arquivos de Programas\Microsoft SQL Server\100\Samples\Integration Services\Tutorial\Deploying Packages\Sample Data\orders.xml</span><span class="sxs-lookup"><span data-stu-id="dd728-146">C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services\Tutorial\Deploying Packages\Sample Data\orders.xml</span></span>|<span data-ttu-id="dd728-147">C:\DeploymentTutorialInstall\orders.xml</span><span class="sxs-lookup"><span data-stu-id="dd728-147">C:\DeploymentTutorialInstall\orders.xml</span></span>|  
    |<span data-ttu-id="dd728-148">\Package.LoadXMLData.Properties[[XML Source].[XMLSchemaDefinition]]</span><span class="sxs-lookup"><span data-stu-id="dd728-148">\Package.LoadXMLData.Properties[[XML Source].[XMLSchemaDefinition]]</span></span>|<span data-ttu-id="dd728-149">C:\Arquivos de Programas\Microsoft SQL Server\100\Samples\Integration Services\Tutorial\Deploying Packages\Sample Data\orders.xsd</span><span class="sxs-lookup"><span data-stu-id="dd728-149">C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services\Tutorial\Deploying Packages\Sample Data\orders.xsd</span></span>|<span data-ttu-id="dd728-150">C:\DeploymentTutorialInstall\orders.xsd</span><span class="sxs-lookup"><span data-stu-id="dd728-150">C:\DeploymentTutorialInstall\orders.xsd</span></span>|  
  
18. <span data-ttu-id="dd728-151">Na página Validação de Pacote, exiba os resultados de validação de cada pacote instalado e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dd728-151">On the Package Validation page, view the validation results of each package installed and then click **Next**.</span></span>  
  
     <span data-ttu-id="dd728-152">Como os valores das variáveis de ambiente no computador de destino diferem dos valores das variáveis de ambiente no computador de desenvolvimento, várias avisos são exibidos na página Validação de Pacote.</span><span class="sxs-lookup"><span data-stu-id="dd728-152">Because the values of the environment variables on the destination computer differ from the values of the environment variables on the development computer, several warnings appear on the Package Validation page.</span></span> <span data-ttu-id="dd728-153">Você deve esperar por quatro avisos:</span><span class="sxs-lookup"><span data-stu-id="dd728-153">You should expect four warnings:</span></span>  
  
    -   <span data-ttu-id="dd728-154">O arquivo de configuração: “C:\DeploymentTutorial\DataTransferConfig.dtsConfig” não é válido.</span><span class="sxs-lookup"><span data-stu-id="dd728-154">The configuration file: "C:\DeploymentTutorial\DataTransferConfig.dtsConfig" is not valid.</span></span> <span data-ttu-id="dd728-155">Verifique o nome do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="dd728-155">Check the configuration file name.</span></span>  
  
    -   <span data-ttu-id="dd728-156">Falha ao carregar pelo menos uma das entradas de configuração no pacote.</span><span class="sxs-lookup"><span data-stu-id="dd728-156">Failed to load at least one of the configuration entries in the package.</span></span> <span data-ttu-id="dd728-157">Verifique as entradas de configuração e os avisos anteriores para ver a descrição da configuração em que houve falha.</span><span class="sxs-lookup"><span data-stu-id="dd728-157">Check configuration entries and previous warnings to see description of which configuration failed.</span></span>  
  
    -   <span data-ttu-id="dd728-158">O arquivo de configuração: “C:\DeploymentTutorial\LoadXMLDataConfig.dtsConfig” não é válido.</span><span class="sxs-lookup"><span data-stu-id="dd728-158">The configuration file: "C:\DeploymentTutorial\LoadXMLDataConfig.dtsConfig is not valid.</span></span> <span data-ttu-id="dd728-159">Verifique o nome do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="dd728-159">Check the configuration file name.</span></span>  
  
    -   <span data-ttu-id="dd728-160">Falha ao carregar pelo menos uma das entradas de configuração no pacote.</span><span class="sxs-lookup"><span data-stu-id="dd728-160">Failed to load at least one of the configuration entries in the package.</span></span> <span data-ttu-id="dd728-161">Verifique as entradas de configuração e os avisos anteriores para ver a descrição da configuração em que houve falha.</span><span class="sxs-lookup"><span data-stu-id="dd728-161">Check configuration entries and previous warnings to see description of which configuration failed.</span></span>  
  
     <span data-ttu-id="dd728-162">Esses avisos não afetam a instalação do pacote.</span><span class="sxs-lookup"><span data-stu-id="dd728-162">These warnings do not affect package installation.</span></span>  
  
     <span data-ttu-id="dd728-163">Se você não tiver selecionado a opção **Validar pacotes após instalação** na página Implantar Pacotes SSIS, as páginas Validação de Pacote não serão abertas e o assistente não exibirá as informações da instalação pós-validação.</span><span class="sxs-lookup"><span data-stu-id="dd728-163">If you did not select the **Validate packages after installation** option on the Deploy SSIS Packages page, the Package Validation pages does not open and the wizard does not display post-installation information about validation.</span></span>  
  
19. <span data-ttu-id="dd728-164">Na página Concluir o Assistente de Instalação de Pacotes, leia o resumo da instalação e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="dd728-164">On the Finish the Package Installation Wizard page, read the installation summary and then click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dd728-165">Um arquivo de log temporário é criado para ser usado na validação do pacote.</span><span class="sxs-lookup"><span data-stu-id="dd728-165">A temporary log file is created to use in the package validation.</span></span> <span data-ttu-id="dd728-166">Esse arquivo não é usado quando o pacote é executado.</span><span class="sxs-lookup"><span data-stu-id="dd728-166">This file is not used when the package runs.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="dd728-167">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="dd728-167">Next Task in Lesson</span></span>  
 [<span data-ttu-id="dd728-168">Etapa 3: Testando os pacotes implantados</span><span class="sxs-lookup"><span data-stu-id="dd728-168">Step 3: Testing the Deployed Packages</span></span>](../integration-services/lesson-3-3-testing-the-deployed-packages.md)  
  
<span data-ttu-id="dd728-169">![Ícone de Integration Services (pequeno)](media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="dd728-169">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="dd728-170">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="dd728-170">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="dd728-171">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="dd728-171">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="dd728-172">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="dd728-172">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd728-173">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dd728-173">See Also</span></span>  
 <span data-ttu-id="dd728-174">[Serviço Integration Services &#40;SSIS Service&#41;](service/integration-services-service-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="dd728-174">[Integration Services Service &#40;SSIS Service&#41;](service/integration-services-service-ssis-service.md) </span></span>  
 [<span data-ttu-id="dd728-175">Gerenciar o serviço Integration Services</span><span class="sxs-lookup"><span data-stu-id="dd728-175">Manage the Integration Services Service</span></span>](../../2014/integration-services/manage-the-integration-services-service.md)  
  
  