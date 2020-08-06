---
title: Criando um logon | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating a login
ms.assetid: a2512310-bdb6-41dc-858a-e866b2b58afc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 400a57693fbea10270a51f5735a19b9639112ce9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683872"
---
# <a name="creating-a-login"></a><span data-ttu-id="dedf7-102">criando um logon</span><span class="sxs-lookup"><span data-stu-id="dedf7-102">Creating a Login</span></span>
  <span data-ttu-id="dedf7-103">Para acessar o [!INCLUDE[ssDE](../includes/ssde-md.md)], os usuários precisam de um logon.</span><span class="sxs-lookup"><span data-stu-id="dedf7-103">To access the [!INCLUDE[ssDE](../includes/ssde-md.md)], users require a login.</span></span> <span data-ttu-id="dedf7-104">O logon pode representar a identidade do usuário como conta do Windows ou como membro de um grupo do Windows, ou o logon pode ser um logon do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que exista apenas no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dedf7-104">The login can represent the user's identity as a Windows account or as a member of a Windows group, or the login can be a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login that exists only in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dedf7-105">Sempre que possível, você deverá usar a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="dedf7-105">Whenever possible you should use Windows Authentication.</span></span>  
  
 <span data-ttu-id="dedf7-106">Por padrão, os administradores têm acesso completo ao [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]no seu computador.</span><span class="sxs-lookup"><span data-stu-id="dedf7-106">By default, administrators on your computer have full access to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dedf7-107">Nesta lição, pretendemos ter um usuário menos privilegiado. Dessa forma, você criará uma nova conta local de Autenticação do Windows em seu computador.</span><span class="sxs-lookup"><span data-stu-id="dedf7-107">For this lesson, we want to have a less privileged user; therefore, you will create a new local Windows Authentication account on your computer.</span></span> <span data-ttu-id="dedf7-108">Para fazer isso, você precisa ser administrador do computador.</span><span class="sxs-lookup"><span data-stu-id="dedf7-108">To do this, you must be an administrator on your computer.</span></span> <span data-ttu-id="dedf7-109">E conceder acesso ao [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]ao novo usuário.</span><span class="sxs-lookup"><span data-stu-id="dedf7-109">Then you will grant that new user access to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-create-a-new-windows-account"></a><span data-ttu-id="dedf7-110">Para criar uma nova conta do Windows</span><span class="sxs-lookup"><span data-stu-id="dedf7-110">To create a new Windows account</span></span>  
  
1.  <span data-ttu-id="dedf7-111">Clique em **Iniciar**, em **executar**, na caixa **abrir** , digite `%SystemRoot%\system32\compmgmt.msc /s` e clique em **OK** para abrir o programa de gerenciamento do computador.</span><span class="sxs-lookup"><span data-stu-id="dedf7-111">Click **Start**, click **Run**, in the **Open** box, type `%SystemRoot%\system32\compmgmt.msc /s`, and then click **OK** to open the Computer Management program.</span></span>  
  
2.  <span data-ttu-id="dedf7-112">Em **Ferramentas do Sistema**, expanda **Usuários e Grupos Locais**, clique com o botão direito do mouse em **Usuários**e clique em **Novo Usuário**.</span><span class="sxs-lookup"><span data-stu-id="dedf7-112">Under **System Tools**, expand **Local Users and Groups**, right-click **Users**, and then click **New User**.</span></span>  
  
3.  <span data-ttu-id="dedf7-113">Na caixa **Nome de usuário** digite **Mary**.</span><span class="sxs-lookup"><span data-stu-id="dedf7-113">In the **User name** box type **Mary**.</span></span>  
  
4.  <span data-ttu-id="dedf7-114">Na caixa **Senha** e **Confirmar senha** , digite uma senha forte e clique em **Criar** para gerar um novo usuário local do Windows.</span><span class="sxs-lookup"><span data-stu-id="dedf7-114">In the **Password** and **Confirm password** box, type a strong password, and then click **Create** to create a new local Windows user.</span></span>  
  
### <a name="to-create-a-login"></a><span data-ttu-id="dedf7-115">Para criar um logon</span><span class="sxs-lookup"><span data-stu-id="dedf7-115">To create a login</span></span>  
  
1.  <span data-ttu-id="dedf7-116">Em uma janela do Editor de Consulta do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], digite e execute o código a seguir substituindo `computer_name` pelo nome de seu computador.</span><span class="sxs-lookup"><span data-stu-id="dedf7-116">In a Query Editor window of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], type and execute the following code replacing `computer_name` with the name of your computer.</span></span> <span data-ttu-id="dedf7-117">`FROM WINDOWS` indica que o Windows autenticará o usuário.</span><span class="sxs-lookup"><span data-stu-id="dedf7-117">`FROM WINDOWS` indicates that Windows will authenticate the user.</span></span> <span data-ttu-id="dedf7-118">O argumento opcional `DEFAULT_DATABASE` é conectado `Mary` ao banco de dados `TestData` , a menos que a cadeia de caracteres de conexão indique outro banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dedf7-118">The optional `DEFAULT_DATABASE` argument connects `Mary` to the `TestData` database, unless her connection string indicates another database.</span></span> <span data-ttu-id="dedf7-119">Essa instrução introduz o ponto-e-vírgula como término opcional para uma instrução [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dedf7-119">This statement introduces the semicolon as an optional termination for a [!INCLUDE[tsql](../includes/tsql-md.md)] statement.</span></span>  
  
    ```  
    CREATE LOGIN [computer_name\Mary]  
        FROM WINDOWS  
        WITH DEFAULT_DATABASE = [TestData];  
    GO  
    ```  
  
     <span data-ttu-id="dedf7-120">Isso autoriza o nome de usuário `Mary`, autenticado pelo seu computador, a acessar a instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dedf7-120">This authorizes a user name `Mary`, authenticated by your computer, to access this instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dedf7-121">Se houver mais de uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no computador, você deverá criar o logon em cada instância que `Mary` deve acessar.</span><span class="sxs-lookup"><span data-stu-id="dedf7-121">If there is more than one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the computer, you must create the login on each instance that `Mary` must access.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dedf7-122">Como `Mary` não é uma conta de domínio, esse nome de usuário só poderá ser autenticado nesse computador.</span><span class="sxs-lookup"><span data-stu-id="dedf7-122">Because `Mary` is not a domain account, this user name can only be authenticated on this computer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="dedf7-123">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="dedf7-123">Next Task in Lesson</span></span>  
 [<span data-ttu-id="dedf7-124">concedendo acesso a um banco de dados</span><span class="sxs-lookup"><span data-stu-id="dedf7-124">Granting Access to a Database</span></span>](lesson-2-2-granting-access-to-a-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="dedf7-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dedf7-125">See Also</span></span>  
 <span data-ttu-id="dedf7-126">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dedf7-126">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 [<span data-ttu-id="dedf7-127">Escolher um modo de autenticação</span><span class="sxs-lookup"><span data-stu-id="dedf7-127">Choose an Authentication Mode</span></span>](../relational-databases/security/choose-an-authentication-mode.md)  
  
  
