---
title: Implantando objetos de banco de dados CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- deployment script [CLR integration]
- common language runtime [SQL Server], deploying
- deploying assemblies [CLR integration]
- deploying [CLR integration]
ms.assetid: 00752573-3367-41a7-af98-7b7a29e8e2f2
author: rothja
ms.author: jroth
ms.openlocfilehash: daf069bc37a58a879224b2217f4dcb700c1d6e99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568629"
---
# <a name="deploying-clr-database-objects"></a><span data-ttu-id="a3006-102">Implantando objetos de banco de dados CLR</span><span class="sxs-lookup"><span data-stu-id="a3006-102">Deploying CLR Database Objects</span></span>
  <span data-ttu-id="a3006-103">Implantação é o processo pelo qual você distribui um aplicativo concluído ou módulo a ser instalado e executado em outro computador.</span><span class="sxs-lookup"><span data-stu-id="a3006-103">Deployment is the process by which you distribute a finished application or module to be installed and run on another computer.</span></span> <span data-ttu-id="a3006-104">Usando o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio, é possível desenvolver objetos de banco de dados do CLR (Common Language Runtime) e implantá-los em um servidor de teste.</span><span class="sxs-lookup"><span data-stu-id="a3006-104">Using [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio, you can develop common language runtime (CLR) database objects and deploy them to a test server.</span></span> <span data-ttu-id="a3006-105">Os objetos de banco de dados gerenciados também podem ser compilados com os arquivos de redistribuição do [!INCLUDE[msCoName](../../../includes/msconame-md.md)].NET Framework, e não o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a3006-105">Alternatively, the managed database objects can also be compiled with the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework redistribution files, instead of Visual Studio.</span></span> <span data-ttu-id="a3006-106">Quando compilados, os assemblies que contêm os objetos de banco de dados do CLR podem ser implantados em um servidor de teste que usa o Visual Studio ou as instruções [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3006-106">Once compiled, the assemblies containing the CLR database objects can then be deployed to a test server using Visual Studio or [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="a3006-107">Observe que o Visual Studio .NET 2003 não pode ser usado na programação de integração ou no desenvolvimento do CLR.</span><span class="sxs-lookup"><span data-stu-id="a3006-107">Note that Visual Studio .NET 2003 cannot be used for CLR integration programming or deployment.</span></span> <span data-ttu-id="a3006-108">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fornece o .NET Framework pré-instalado, e o Visual Studio .NET 2003 não pode usar os assemblies do .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="a3006-108">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] includes the .NET Framework pre-installed, and Visual Studio .NET 2003 cannot use the .NET Framework 2.0 assemblies.</span></span>  
  
 <span data-ttu-id="a3006-109">Quando testados e verificados no servidor de teste, os métodos do CLR podem ser distribuídos para servidores de produção usando um script de implantação.</span><span class="sxs-lookup"><span data-stu-id="a3006-109">Once the CLR methods have been tested and verified on the test server, they can be distributed to production servers using a deployment script.</span></span> <span data-ttu-id="a3006-110">O script de implantação pode ser gerado manualmente ou usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] (consulte o procedimento posteriormente neste tópico).</span><span class="sxs-lookup"><span data-stu-id="a3006-110">The deployment script can be generated manually, or by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] (see the procedure later in this topic).</span></span>  
  
 <span data-ttu-id="a3006-111">O recurso de integração CLR permanece desativado por padrão no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e deve ser habilitado para usar assemblies CLR.</span><span class="sxs-lookup"><span data-stu-id="a3006-111">The CLR integration feature is turned off by default in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and must be enabled in order to use CLR assemblies.</span></span> <span data-ttu-id="a3006-112">Para obter mais informações, consulte [Enabling CLR Integration](clr-integration-enabling.md).</span><span class="sxs-lookup"><span data-stu-id="a3006-112">For more information, see [Enabling CLR Integration](clr-integration-enabling.md).</span></span>  
  
## <a name="deploying-the-assembly-to-the-test-server"></a><span data-ttu-id="a3006-113">Implantando o assembly no servidor de teste</span><span class="sxs-lookup"><span data-stu-id="a3006-113">Deploying the Assembly to the Test Server</span></span>  
 <span data-ttu-id="a3006-114">Usando o Visual Studio, é possível desenvolver funções, procedimentos, gatilhos, UDTs (tipos definidos pelo usuário) ou UDAs (agregações definidas pelo usuário) e implantá-los em um servidor de teste.</span><span class="sxs-lookup"><span data-stu-id="a3006-114">Using Visual Studio, you can develop CLR functions, procedures, triggers, user-defined types (UDTs), or user-defined aggregates (UDAs), and deploy them to a test server.</span></span> <span data-ttu-id="a3006-115">Os objetos de banco de dados gerenciados também podem ser compilados com os compiladores de linha de comando como, por exemplo, csc.exe e vbc.exe, incluídos nos arquivos de redistribuição do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a3006-115">These managed database objects can also be compiled with the command line compilers, such as csc.exe and vbc.exe, included with the .NET Framework redistribution files.</span></span> <span data-ttu-id="a3006-116">O ambiente de desenvolvimento integrado do Visual Studio não é obrigatório para desenvolver objetos de banco de dados gerenciados para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3006-116">The Visual Studio Integrated Development Environment is not required to develop managed database objects for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a3006-117">Verifique se todos os erros e avisos do compilador são resolvidos.</span><span class="sxs-lookup"><span data-stu-id="a3006-117">Make sure that all compiler errors and warnings are resolved.</span></span> <span data-ttu-id="a3006-118">Dessa forma, os assemblies que contêm as rotinas do CLR podem ser registrados em um banco de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que usa o Visual Studio ou as instruções [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3006-118">The assemblies containing the CLR routines can then be registered in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database using Visual Studio or [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3006-119">O protocolo de rede TCP/IP deve estar habilitado na instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para que o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio seja usado no desenvolvimento remoto, na depuração e no desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="a3006-119">The TCP/IP network protocol must be enabled on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in order to use [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio for remote development, debugging, and development.</span></span> <span data-ttu-id="a3006-120">Para obter mais informações sobre como habilitar o protocolo TCP/IP no servidor, consulte [Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="a3006-120">For more information about enabling TCP/IP protocol on the server, see [Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md).</span></span>  
  
#### <a name="to-deploy-the-assembly-using-visual-studio"></a><span data-ttu-id="a3006-121">Para implantar o assembly que usa o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a3006-121">To deploy the assembly using Visual Studio</span></span>  
  
1.  <span data-ttu-id="a3006-122">Crie o projeto selecionando **Compilar** \<project name> no menu **Compilar** .</span><span class="sxs-lookup"><span data-stu-id="a3006-122">Build the project by selecting **Build** \<project name> from the **Build** menu.</span></span>  
  
2.  <span data-ttu-id="a3006-123">Resolva todos os erros de compilação e avisos antes de implantar o assembly no servidor de teste.</span><span class="sxs-lookup"><span data-stu-id="a3006-123">Resolve all build errors and warnings before deploying the assembly to the test server.</span></span>  
  
3.  <span data-ttu-id="a3006-124">Selecione **implantar** no menu **Compilar** .</span><span class="sxs-lookup"><span data-stu-id="a3006-124">Select **Deploy** from the **Build** menu.</span></span> <span data-ttu-id="a3006-125">O assembly será registrado na instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e no banco de dados especificado quando o projeto do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] foi criado inicialmente no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a3006-125">The assembly will then be registered in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance and database specified when the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] project was first created in Visual Studio.</span></span>  
  
#### <a name="to-deploy-the-assembly-using-transact-sql"></a><span data-ttu-id="a3006-126">Para implantar o assembly que usa Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a3006-126">To deploy the assembly using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="a3006-127">Compile o assembly no arquivo de origem que usa os compiladores de linha de comando incluídos no .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a3006-127">Compile the assembly from the source file using the command line compilers included with the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="a3006-128">Em arquivos de origem do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#:</span><span class="sxs-lookup"><span data-stu-id="a3006-128">For [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C# source files:</span></span>  
  
3.  `csc /target:library C:\helloworld.cs`  
  
4.  <span data-ttu-id="a3006-129">Em arquivos de origem do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="a3006-129">For [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic source files:</span></span>  
  
 `vbc /target:library C:\helloworld.vb`  
  
 <span data-ttu-id="a3006-130">Esses comandos iniciam o compilador do Visual C# ou do Visual Basic que usa a opção `/target` para especificar a compilação de uma DLL da biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a3006-130">These commands launch the Visual C# or Visual Basic compiler using the `/target` option to specify building a library DLL.</span></span>  
  
1.  <span data-ttu-id="a3006-131">Resolva todos os erros de compilação e avisos antes de implantar o assembly no servidor de teste.</span><span class="sxs-lookup"><span data-stu-id="a3006-131">Resolve all build errors and warnings before deploying the assembly to the test server.</span></span>  
  
2.  <span data-ttu-id="a3006-132">Abra o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] no servidor de teste.</span><span class="sxs-lookup"><span data-stu-id="a3006-132">Open [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] on the test server.</span></span> <span data-ttu-id="a3006-133">Crie uma consulta nova, conectada a um banco de dados de teste correspondente (como, por exemplo, AdventureWorks).</span><span class="sxs-lookup"><span data-stu-id="a3006-133">Create a new query, connected to a suitable test database (such as AdventureWorks).</span></span>  
  
3.  <span data-ttu-id="a3006-134">Crie o assembly no servidor, adicionando a seguinte [!INCLUDE[tsql](../../../includes/tsql-md.md)] à consulta.</span><span class="sxs-lookup"><span data-stu-id="a3006-134">Create the assembly in the server by adding the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] to the query.</span></span>  
  
 `CREATE ASSEMBLY HelloWorld from 'c:\helloworld.dll' WITH PERMISSION_SET = SAFE;`  
  
1.  <span data-ttu-id="a3006-135">Assim, o procedimento, a função, a agregação, o tipo definido pelo usuário ou o gatilho deve ser criado na instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3006-135">The procedure, function, aggregate, user-defined type, or trigger must then be created in the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a3006-136">Caso o assembly `HelloWorld` contenha um método chamado `HelloWorld` na classe `Procedures`, a seguinte [!INCLUDE[tsql](../../../includes/tsql-md.md)] pode ser adicionada à consulta para criar um procedimento chamado `hello` no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3006-136">If the `HelloWorld` assembly contains a method named `HelloWorld` in the `Procedures` class, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] can be added to the query to create a procedure called `hello` in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 `CREATE PROCEDURE hello`  
  
 `AS`  
  
 `EXTERNAL NAME HelloWorld.Procedures.HelloWorld`  
  
 <span data-ttu-id="a3006-137">Para obter mais informações sobre como criar os diferentes tipos de objetos de banco de dados gerenciado no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , consulte [funções CLR](../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md)definidas pelo usuário, [agregações CLR definidas pelo](../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md)usuário, [tipos CLR definidos pelo usuário](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md), [procedimentos armazenados CLR](../../database-engine/dev-guide/clr-stored-procedures.md)e [gatilhos CLR](../../database-engine/dev-guide/clr-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="a3006-137">For more information about creating the different types of managed database objects in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see [CLR User-Defined Functions](../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md), [CLR User-Defined Aggregates](../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md), [CLR User-Defined Types](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md), [CLR Stored Procedures](../../database-engine/dev-guide/clr-stored-procedures.md), and [CLR Triggers](../../database-engine/dev-guide/clr-triggers.md).</span></span>  
  
## <a name="deploying-the-assembly-to-production-servers"></a><span data-ttu-id="a3006-138">Implantando o assembly em servidores de produção</span><span class="sxs-lookup"><span data-stu-id="a3006-138">Deploying the Assembly to Production Servers</span></span>  
 <span data-ttu-id="a3006-139">Uma vez testados e verificados no servidor de teste, os objetos de banco de dados do CLR podem ser distribuídos para servidores de produção.</span><span class="sxs-lookup"><span data-stu-id="a3006-139">Once the CLR database objects have been tested and verified on the test server, they can be distributed to production servers.</span></span> <span data-ttu-id="a3006-140">Para obter mais informações sobre como depurar objetos de banco de dados gerenciado, consulte [DEBUGGING CLR Database Objects](debugging-clr-database-objects.md).</span><span class="sxs-lookup"><span data-stu-id="a3006-140">For more information about debugging managed database objects, see [Debugging CLR Database Objects](debugging-clr-database-objects.md).</span></span>  
  
 <span data-ttu-id="a3006-141">A implantação dos objetos de banco de dados gerenciados é semelhante à dos objetos de banco de dados regulares (tabelas, rotinas [!INCLUDE[tsql](../../../includes/tsql-md.md)] etc.).</span><span class="sxs-lookup"><span data-stu-id="a3006-141">The deployment of managed database objects is similar to that of regular database objects (tables, [!INCLUDE[tsql](../../../includes/tsql-md.md)] routines, and so on).</span></span> <span data-ttu-id="a3006-142">Os assemblies que contêm os objetos de banco de dados do CLR podem ser implantados em outros servidores que usam um script de implantação.</span><span class="sxs-lookup"><span data-stu-id="a3006-142">The assemblies containing the CLR database objects can be deployed to other servers using a deployment script.</span></span> <span data-ttu-id="a3006-143">O script de implantação pode ser compilado usando a funcionalidade "Gerar Scripts" do [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3006-143">The deployment script can be built by using the "Generate Scripts" functionality of [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="a3006-144">O script de implantação também pode ser compilado manualmente, ou usando "Gerar Scripts", e alterados manualmente.</span><span class="sxs-lookup"><span data-stu-id="a3006-144">The deployment script can also be built manually, or built using "Generate Scripts" and manually altered.</span></span> <span data-ttu-id="a3006-145">Uma vez compilado, o script de implantação pode ser executado em outras instâncias do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para implantar os objetos de banco de dados gerenciados.</span><span class="sxs-lookup"><span data-stu-id="a3006-145">Once the deployment script has been built, it can be run on other instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to deploy the managed database objects.</span></span>  
  
#### <a name="to-generate-a-deployment-script-using-generate-scripts"></a><span data-ttu-id="a3006-146">Para gerar um script de implantação usando scripts de geração</span><span class="sxs-lookup"><span data-stu-id="a3006-146">To generate a deployment script using generate scripts</span></span>  
  
1.  <span data-ttu-id="a3006-147">Abra o [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] e se conecte à instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] em que o assembly gerenciado ou o objeto de banco de dados a ser implantado é registrado.</span><span class="sxs-lookup"><span data-stu-id="a3006-147">Open [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] and connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance where the managed assembly or database object to be deployed is registered.</span></span>  
  
2.  <span data-ttu-id="a3006-148">No Pesquisador de **objetos**, expanda as **\<server name>** árvores e **bancos de dados** .</span><span class="sxs-lookup"><span data-stu-id="a3006-148">In the **Object Explorer**, expand the **\<server name>** and **Databases** trees.</span></span> <span data-ttu-id="a3006-149">Clique com o botão direito do mouse no banco de dados em que o objeto de banco de dados gerenciado está registrado, selecione **tarefas**e, em seguida, selecione **gerar scripts**.</span><span class="sxs-lookup"><span data-stu-id="a3006-149">Right-click the database where the managed database object is registered, select **Tasks**, and then select **Generate Scripts**.</span></span> <span data-ttu-id="a3006-150">O Assistente de Script é aberto.</span><span class="sxs-lookup"><span data-stu-id="a3006-150">The Script Wizard opens.</span></span>  
  
3.  <span data-ttu-id="a3006-151">Selecione o banco de dados na caixa de listagem e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a3006-151">Select the database from the list box and click **Next**.</span></span>  
  
4.  <span data-ttu-id="a3006-152">No painel **escolher opções de script** , clique em **Avançar**ou altere as opções e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a3006-152">In the **Choose Script Options** pane, click **Next**, or change the options and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="a3006-153">No painel **escolher tipos de objeto** , escolha o tipo de objeto de banco de dados a ser implantado.</span><span class="sxs-lookup"><span data-stu-id="a3006-153">In the **Choose Object Types** pane, choose the type of database object to be deployed.</span></span> <span data-ttu-id="a3006-154">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a3006-154">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="a3006-155">Para cada tipo de objeto selecionado no painel **escolher tipos de objeto** , um painel \*\*escolher \<type> \*\* é apresentado.</span><span class="sxs-lookup"><span data-stu-id="a3006-155">For every object type selected in the **Choose Object Types** pane, a **Choose \<type>** pane is presented.</span></span> <span data-ttu-id="a3006-156">Nesse painel, é possível escolher uma dentre todas as instâncias do tipo de objeto de banco de dados registrado no banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="a3006-156">In this pane, you can choose from all the instances of that database object type registered in the specified database.</span></span> <span data-ttu-id="a3006-157">Selecione um ou mais objetos e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a3006-157">Select one or more objects and click **Next**.</span></span>  
  
7.  <span data-ttu-id="a3006-158">O painel **Opções de saída** aparece quando todos os tipos de objeto de banco de dados desejados foram selecionados.</span><span class="sxs-lookup"><span data-stu-id="a3006-158">The **Output Options** pane comes up when all of the desired database object types have been selected.</span></span> <span data-ttu-id="a3006-159">Selecione **script para arquivo** e especifique um caminho de arquivo para o script.</span><span class="sxs-lookup"><span data-stu-id="a3006-159">Select **Script to file** and specify a file path for the script.</span></span> <span data-ttu-id="a3006-160">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a3006-160">Select **Next**.</span></span> <span data-ttu-id="a3006-161">Examine suas seleções e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="a3006-161">Review your selections and click **Finish**.</span></span> <span data-ttu-id="a3006-162">O script de implantação é salvo no caminho do arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="a3006-162">The deployment script is saved to the specified file path.</span></span>  
  
## <a name="post-deployment-scripts"></a><span data-ttu-id="a3006-163">Scripts pós-implantação</span><span class="sxs-lookup"><span data-stu-id="a3006-163">Post Deployment Scripts</span></span>  
 <span data-ttu-id="a3006-164">É possível executar um script de pós-implantação.</span><span class="sxs-lookup"><span data-stu-id="a3006-164">You can run a post deployment script.</span></span>  
  
 <span data-ttu-id="a3006-165">Para adicionar um script de pós-implantação, adicione um arquivo chamado postdeployscript.sql no diretório do projeto do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a3006-165">To add a post deployment script, add a file called postdeployscript.sql in your Visual Studio project directory.</span></span> <span data-ttu-id="a3006-166">Por exemplo, clique com o botão direito do mouse em seu projeto no **Gerenciador de soluções** e selecione **Adicionar item existente**.</span><span class="sxs-lookup"><span data-stu-id="a3006-166">For example, right click your project in **Solution Explorer** and select **Add Existing Item**.</span></span> <span data-ttu-id="a3006-167">Adicione o arquivo na raiz do projeto, e não na pasta Test Scripts.</span><span class="sxs-lookup"><span data-stu-id="a3006-167">Add the file in the root of the project, rather than in the Test Scripts folder.</span></span>  
  
 <span data-ttu-id="a3006-168">Quando você clicar na implantação, o Visual Studio executará esse script após a implantação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a3006-168">When you click deploy, Visual Studio will run this script after the deployment of your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3006-169">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a3006-169">See Also</span></span>  
 [<span data-ttu-id="a3006-170">Conceitos de programação da Integração CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="a3006-170">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](common-language-runtime-clr-integration-programming-concepts.md)  
  
  