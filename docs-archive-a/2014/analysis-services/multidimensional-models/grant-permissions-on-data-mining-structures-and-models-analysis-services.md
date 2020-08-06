---
title: Conceder permissões em estruturas e modelos de Data Mining (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.roledesignerdialog.miningmodels.f1
helpviewer_keywords:
- data mining [Analysis Services], security
- permissions [Analysis Services], mining models
- mining models [Analysis Services], security
- mining structures [Analysis Services], security
- permissions [Analysis Services], mining structures
- user access rights [Analysis Services], mining structures
- user access rights [Analysis Services], mining models
ms.assetid: a0008004-e2b7-47db-acad-5fe7e12b130f
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0db849551bdb38615f280b123c98f0e9d3053d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681870"
---
# <a name="grant-permissions-on-data-mining-structures-and-models-analysis-services"></a><span data-ttu-id="d0e56-102">Conceder permissões em estruturas e modelos de mineração de dados (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="d0e56-102">Grant permissions on data mining structures and models (Analysis Services)</span></span>
  <span data-ttu-id="d0e56-103">Por padrão, apenas um administrador do servidor do Analysis Services tem permissões para exibir estruturas ou modelos de mineração no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d0e56-103">By default, only an Analysis Services server administrator has permissions to view data mining structures or mining models in the database.</span></span> <span data-ttu-id="d0e56-104">Siga as instruções abaixo para conceder permissões a usuários não administradores.</span><span class="sxs-lookup"><span data-stu-id="d0e56-104">Follow the instructions below to grant permissions to non-administrator users.</span></span>  
  
## <a name="set-permissions-to-access-a-mining-structure"></a><span data-ttu-id="d0e56-105">Definir permissões para acessar uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="d0e56-105">Set permissions to access a mining structure</span></span>  
  
1.  <span data-ttu-id="d0e56-106">No SSMS, conecte-se ao Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d0e56-106">In SSMS, connect to Analysis Services.</span></span> <span data-ttu-id="d0e56-107">Consulte [Conectar-se de aplicativos cliente &#40;Analysis Services&#41;](../instances/connect-from-client-applications-analysis-services.md) se precisar de ajuda com as etapas.</span><span class="sxs-lookup"><span data-stu-id="d0e56-107">See [Connect from client applications &#40;Analysis Services&#41;](../instances/connect-from-client-applications-analysis-services.md) if you need help with the steps.</span></span>  
  
2.  <span data-ttu-id="d0e56-108">Abra a pasta **Bancos de Dados** e escolha um banco de dados no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="d0e56-108">Open the **Databases** folder, and select a database in Object Explorer.</span></span>  
  
3.  <span data-ttu-id="d0e56-109">Clique com o botão direito do mouse em **Funções** e escolha **Nova Função**.</span><span class="sxs-lookup"><span data-stu-id="d0e56-109">Right-click **Roles** and choose **New Role**.</span></span>  
  
4.  <span data-ttu-id="d0e56-110">Na página Geral, insira um nome e, opcionalmente, uma descrição.</span><span class="sxs-lookup"><span data-stu-id="d0e56-110">In the General page, enter a name, and optionally, a description.</span></span> <span data-ttu-id="d0e56-111">Essa página também contém várias permissões de banco de dados, tais como Controle Total, Processar Banco de Dados e Ler Definição.</span><span class="sxs-lookup"><span data-stu-id="d0e56-111">The page also contains several database permissions, such as Full Control, Process Database, and Read Definition.</span></span> <span data-ttu-id="d0e56-112">Nenhuma dessas permissões é necessária para acesso aos dados de mineração.</span><span class="sxs-lookup"><span data-stu-id="d0e56-112">None of these permissions are needed for data mining access.</span></span> <span data-ttu-id="d0e56-113">Consulte [Conceder permissões de banco de dados &#40;Analysis Services&#41;](grant-database-permissions-analysis-services.md) para obter mais informações sobre as permissões do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d0e56-113">See [Grant database permissions &#40;Analysis Services&#41;](grant-database-permissions-analysis-services.md) for more information about database permissions.</span></span>  
  
5.  <span data-ttu-id="d0e56-114">No painel **Estrutura de Mineração** , escolha **Leitura** ou **Leitura/Gravação**  para cada estrutura de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="d0e56-114">In the **Mining Structure** pane, select **Read** or **Read/Write**  for each data mining structure.</span></span>  
  
6.  <span data-ttu-id="d0e56-115">No painel **Associação** , insira as contas de usuário e de grupo do Windows que se conectam ao Analysis Services usando essa função.</span><span class="sxs-lookup"><span data-stu-id="d0e56-115">In the **Membership** pane, enter the Windows user and group accounts that connect to Analysis Services using this role.</span></span>  
  
7.  <span data-ttu-id="d0e56-116">Clique em **OK** para concluir a criação da função.</span><span class="sxs-lookup"><span data-stu-id="d0e56-116">Click **OK** to finish creating the role.</span></span>  
  
## <a name="set-permissions-to-access-a-mining-model"></a><span data-ttu-id="d0e56-117">Definir permissões para acessar um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="d0e56-117">Set permissions to access a mining model</span></span>  
 <span data-ttu-id="d0e56-118">Para um modelo de mineração de dados, uma função pode ter permissões de **Leitura** ou **Leitura/Gravação** , bem como permissões de **Detalhamento** e **Ler Definição** que permitem exibir e procurar dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="d0e56-118">For a data mining model, a role can have either **Read** or **Read/Write** permissions, as well as **Drillthrough** and **Read Definition** permissions that allow viewing and browsing the underlying data.</span></span>  
  
 <span data-ttu-id="d0e56-119">**Observação** Se você habilitar detalhamento na estrutura de mineração e no modelo de mineração, qualquer usuário que for membro de uma função que tenha permissões de detalhamento no modelo de mineração e na estrutura de mineração também poderá exibir colunas na estrutura de mineração, até mesmo se essas colunas não estiverem incluídas no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="d0e56-119">**Note** If you enable drillthrough on both the mining structure and the mining model, any user who is a member of a role that has drillthrough permissions on the mining model and the mining structure can also view columns in the mining structure, even if those columns are not included in the mining model.</span></span> <span data-ttu-id="d0e56-120">Portanto, para proteger informações confidenciais, você deveria configurar a exibição da fonte de dados para mascarar informações pessoais e só permitir acesso de detalhamento na estrutura de mineração quando necessário.</span><span class="sxs-lookup"><span data-stu-id="d0e56-120">Therefore, to protect sensitive information, you should set up the data source view to mask personal information, and allow drillthrough access on the mining structure only when necessary.</span></span>  
  
 <span data-ttu-id="d0e56-121">Para conceder a um usuário permissões de leitura ou de leitura/gravação a uma função do banco de dados, o usuário deve ser membro da função de servidor do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou membro de uma função de banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] com permissões de Controle total (Administrador).</span><span class="sxs-lookup"><span data-stu-id="d0e56-121">To grant read or read/write permissions to a database role, a user must be a member of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server role or a member of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database role that has Full Control (Administrator) permissions.</span></span>  
  
1.  <span data-ttu-id="d0e56-122">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , conecte-se à instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , expanda **funções** para o banco de dados apropriado no Pesquisador de objetos e clique em uma função de banco de dados (ou crie uma nova função de banco de dados).</span><span class="sxs-lookup"><span data-stu-id="d0e56-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], expand **Roles** for the appropriate database in Object Explorer, and then click a database role (or create a new database role).</span></span>  
  
2.  <span data-ttu-id="d0e56-123">Clique no painel **Estrutura de Mineração** , localize o modelo de mineração na lista **Modelo de Mineração** e selecione **Leitura**, **Leitura/Gravação**, **Detalhamento**ou **Procurar** para o modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="d0e56-123">In the **Mining Structure** pane, locate the mining model in the **Mining Models** list, and then select **Read**, **Read/Write**, **Drill Through**, or **Browse** for that mining model.</span></span>  
  
3.  <span data-ttu-id="d0e56-124">No painel **Associação** , insira as contas de usuário e de grupo do Windows que se conectam ao Analysis Services usando essa função.</span><span class="sxs-lookup"><span data-stu-id="d0e56-124">In the **Membership** pane, enter the Windows user and group accounts that connect to Analysis Services using this role.</span></span>  
  
4.  <span data-ttu-id="d0e56-125">Clique em **OK** para concluir a criação da função.</span><span class="sxs-lookup"><span data-stu-id="d0e56-125">Click **OK** to finish creating the role.</span></span>  
  
 <span data-ttu-id="d0e56-126">Para usar uma fonte de dados em uma consulta de detalhamento que usa a cláusula DMX (extensões DMX) OPENQUERY, a função de banco de dados precisa também de permissão de leitura/gravação no objeto de fonte de dados adequado.</span><span class="sxs-lookup"><span data-stu-id="d0e56-126">To use a data source in a drillthrough query that uses the Data Mining Extensions (DMX) OPENQUERY clause, the database role also needs read/write permission on the appropriate data source object.</span></span> <span data-ttu-id="d0e56-127">Para obter mais informações, consulte [Conceder permissões em um objeto de fonte de dados &#40;Analysis Services&#41;](grant-permissions-on-a-data-source-object-analysis-services.md) e [OPENQUERY &#40;DMX&#41;](/sql/dmx/source-data-query-openquery).</span><span class="sxs-lookup"><span data-stu-id="d0e56-127">For more information, see [Grant permissions on a data source object &#40;Analysis Services&#41;](grant-permissions-on-a-data-source-object-analysis-services.md) and [OPENQUERY &#40;DMX&#41;](/sql/dmx/source-data-query-openquery).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d0e56-128">Por padrão, o envio de consultas de DMX usando OPENROWSET está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="d0e56-128">By default, the submission of DMX queries by using OPENROWSET is disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0e56-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d0e56-129">See Also</span></span>  
 <span data-ttu-id="d0e56-130">[Permissões de administrador de servidor Grant &#40;Analysis Services&#41;](../instances/grant-server-admin-rights-to-an-analysis-services-instance.md) </span><span class="sxs-lookup"><span data-stu-id="d0e56-130">[Grant Server Administrator Permissions &#40;Analysis Services&#41;](../instances/grant-server-admin-rights-to-an-analysis-services-instance.md) </span></span>  
 <span data-ttu-id="d0e56-131">[Conceder permissões de cubo ou modelo &#40;Analysis Services&#41;](grant-cube-or-model-permissions-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="d0e56-131">[Grant cube or model permissions &#40;Analysis Services&#41;](grant-cube-or-model-permissions-analysis-services.md) </span></span>  
 <span data-ttu-id="d0e56-132">[Conceder acesso personalizado a dados de dimensão &#40;Analysis Services&#41;](grant-custom-access-to-dimension-data-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="d0e56-132">[Grant custom access to dimension data &#40;Analysis Services&#41;](grant-custom-access-to-dimension-data-analysis-services.md) </span></span>  
 [<span data-ttu-id="d0e56-133">Conceder acesso personalizado a dados de célula &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d0e56-133">Grant custom access to cell data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-cell-data-analysis-services.md)  
  
  
