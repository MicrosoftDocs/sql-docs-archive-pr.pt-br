---
title: Escolher uma fonte de dados (Assistente de Importação e Exportação do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.chooseadatasource.f1
ms.assetid: ebf28a62-dfc1-4b39-9db5-df1919e5fccb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 246c3b03bfefad83cbfc1d0110e1fd4cf0cedf7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575955"
---
# <a name="choose-a-data-source-sql-server-import-and-export-wizard"></a><span data-ttu-id="fa610-102">Escolher uma fonte de dados (Assistente de Importação e Exportação do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fa610-102">Choose a Data Source (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="fa610-103">Use a página **escolher uma fonte de dados** para especificar a origem dos dados que você deseja copiar.</span><span class="sxs-lookup"><span data-stu-id="fa610-103">Use the **Choose a Data Source** page to specify the source of the data that you want to copy.</span></span>  
  
 <span data-ttu-id="fa610-104">Para obter mais informações sobre este assistente, consulte [Assistente de Importação e Exportação do SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="fa610-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="fa610-105">Para saber mais sobre as opções de inicialização do assistente e sobre as permissões necessárias para executar o assistente com êxito, consulte [executar o assistente de importação e exportação do SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="fa610-105">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="fa610-106">O objetivo do Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é copiar dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="fa610-106">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="fa610-107">O assistente também pode criar um banco de dados de destino e tabelas de destino para você.</span><span class="sxs-lookup"><span data-stu-id="fa610-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="fa610-108">No entanto, se for necessário copiar vários bancos de dados ou tabelas, ou outros tipos de objetos de banco de dados, será necessário usar o Assistente para Copiar Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="fa610-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="fa610-109">Para obter mais informações, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="fa610-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="fa610-110">Opções</span><span class="sxs-lookup"><span data-stu-id="fa610-110">Options</span></span>  
 <span data-ttu-id="fa610-111">**Fonte de Dados**</span><span class="sxs-lookup"><span data-stu-id="fa610-111">**Data Source**</span></span>  
 <span data-ttu-id="fa610-112">Escolha o provedor de dados que corresponde ao formato de armazenamento da origem.</span><span class="sxs-lookup"><span data-stu-id="fa610-112">Choose the data provider that matches the data storage format of the source.</span></span> <span data-ttu-id="fa610-113">Pode haver mais de um provedor disponível para sua fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="fa610-113">There may be more than one provider available for your data source.</span></span> <span data-ttu-id="fa610-114">Por exemplo, com [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o, você pode usar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o Native Client, o .NET Framework Provedor de Dados para SQL Server ou o provedor de OLE DB da Microsoft para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fa610-114">For example, with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, the .NET Framework Data Provider for SQL Server, or the Microsoft OLE DB Provider for SQL Server.</span></span>  
  
 <span data-ttu-id="fa610-115">A propriedade **fonte de dados** tem um número variável de opções, que dependem dos provedores instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="fa610-115">The **Data Source** property has a variable number of options, which depend on the providers installed on the computer.</span></span> <span data-ttu-id="fa610-116">As tabelas a seguir listam as opções de alguns destinos usados com mais frequência.</span><span class="sxs-lookup"><span data-stu-id="fa610-116">The following tables list the options for some frequently used destinations.</span></span> <span data-ttu-id="fa610-117">Para outros provedores, consulte a documentação específica do provedor.</span><span class="sxs-lookup"><span data-stu-id="fa610-117">For other providers, see the provider-specific documentation.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="fa610-118">Opções dinâmicas</span><span class="sxs-lookup"><span data-stu-id="fa610-118">Dynamic Options</span></span>  
 <span data-ttu-id="fa610-119">As seções a seguir mostram as opções disponíveis para várias fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="fa610-119">The following sections show the options available for several data sources.</span></span> <span data-ttu-id="fa610-120">Nem todas as fontes de dados disponíveis no menu suspenso Fonte de Dados são listadas aqui.</span><span class="sxs-lookup"><span data-stu-id="fa610-120">Not all the data sources that are available in the Data Source drop-down are listed here.</span></span>  
  
### <a name="data-source--sql-server-native-client-and-microsoft-ole-db-provider-for-sql-server"></a><span data-ttu-id="fa610-121">Fonte de Dados = SQL Server Native Client e Microsoft OLE DB Provider for SQL Server</span><span class="sxs-lookup"><span data-stu-id="fa610-121">Data Source = SQL Server Native Client and Microsoft OLE DB Provider for SQL Server</span></span>  
 <span data-ttu-id="fa610-122">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="fa610-122">**Server name**</span></span>  
 <span data-ttu-id="fa610-123">Digite o nome do servidor que contém os dados ou escolha um servidor da lista.</span><span class="sxs-lookup"><span data-stu-id="fa610-123">Type the name of the server that contains the data, or choose a server from the list.</span></span>  
  
 <span data-ttu-id="fa610-124">**Usar Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="fa610-124">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="fa610-125">Especifique se o pacote deve usar a Autenticação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows para fazer login no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fa610-125">Specify whether the package should use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication to log in to the database.</span></span> <span data-ttu-id="fa610-126">A Autenticação do Windows é recomendada para obter melhor segurança.</span><span class="sxs-lookup"><span data-stu-id="fa610-126">Windows Authentication is recommended for better security.</span></span>  
  
 <span data-ttu-id="fa610-127">**Usar Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="fa610-127">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="fa610-128">Especifique se o pacote deve usar a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para fazer login no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fa610-128">Specify whether the package should use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to log in to the database.</span></span> <span data-ttu-id="fa610-129">Se você usar a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , será preciso fornecer um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="fa610-129">If you use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="fa610-130">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="fa610-130">**User name**</span></span>  
 <span data-ttu-id="fa610-131">Especifique um nome de usuário para estabelecer conexão com o banco de dados quando estiver usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa610-131">Specify a user name for the database connection when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="fa610-132">**Senha**</span><span class="sxs-lookup"><span data-stu-id="fa610-132">**Password**</span></span>  
 <span data-ttu-id="fa610-133">Forneça uma senha para estabelecer conexão de banco de dados quando estiver usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa610-133">Provide the password for the database connection when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="fa610-134">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="fa610-134">**Database**</span></span>  
 <span data-ttu-id="fa610-135">Selecione usando a lista de bancos de dados na instância especificada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa610-135">Select from the list of databases on the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fa610-136">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="fa610-136">**Refresh**</span></span>  
 <span data-ttu-id="fa610-137">Restaure a lista de bancos de dados disponíveis clicando em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="fa610-137">Restore the list of available databases by clicking **Refresh**.</span></span>  
  
### <a name="data-source--net-framework-data-provider-for-sql-server"></a><span data-ttu-id="fa610-138">Fonte de Dados = .NET Framework Data Provider for SQL Server</span><span class="sxs-lookup"><span data-stu-id="fa610-138">Data Source = .NET Framework Data Provider for SQL Server</span></span>  
 <span data-ttu-id="fa610-139">Esta página apresenta uma lista alfabética de opções para o [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa610-139">This page presents an alphabetical list of options for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fa610-140">As opções mais importantes estão listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="fa610-140">The most important options are listed in the following table.</span></span>  
  
 <span data-ttu-id="fa610-141">**Fonte de Dados**</span><span class="sxs-lookup"><span data-stu-id="fa610-141">**Data Source**</span></span>  
 <span data-ttu-id="fa610-142">Digite o nome do servidor que contém os dados ou escolha um servidor da lista.</span><span class="sxs-lookup"><span data-stu-id="fa610-142">Type the name of the server that contains the data, or choose a server from the list.</span></span>  
  
 <span data-ttu-id="fa610-143">**Catálogo Inicial**</span><span class="sxs-lookup"><span data-stu-id="fa610-143">**Initial Catalog**</span></span>  
 <span data-ttu-id="fa610-144">Digite o nome do banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="fa610-144">Type the name of the source database.</span></span>  
  
 <span data-ttu-id="fa610-145">**Segurança Integrada**</span><span class="sxs-lookup"><span data-stu-id="fa610-145">**Integrated Security**</span></span>  
 <span data-ttu-id="fa610-146">Especifique `True` para estabelecer conexão usando a autenticação integrada do Windows (recomendado) ou `False` para estabelecer conexão usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa610-146">Specify `True` to connect by using Windows integrated authentication, which is recommended, or `False` to connect by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="fa610-147">Se você especificar `False`, deverá inserir uma ID de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="fa610-147">If you specify `False`, you must enter a user ID and password.</span></span> <span data-ttu-id="fa610-148">O valor padrão é `False`.</span><span class="sxs-lookup"><span data-stu-id="fa610-148">The default value is `False`.</span></span>  
  
 <span data-ttu-id="fa610-149">**ID de usuário**</span><span class="sxs-lookup"><span data-stu-id="fa610-149">**User ID**</span></span>  
 <span data-ttu-id="fa610-150">Especifique um nome de usuário para estabelecer conexão com o banco de dados quando estiver usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa610-150">Specify a user name for the database connection when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="fa610-151">**Senha**</span><span class="sxs-lookup"><span data-stu-id="fa610-151">**Password**</span></span>  
 <span data-ttu-id="fa610-152">Forneça uma senha para estabelecer conexão de banco de dados quando estiver usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa610-152">Provide the password for the database connection when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="fa610-153">As opções adicionais que são listadas ao selecionar esse provedor não são necessárias para estabelecer uma conexão bem-sucedida com o banco de dados de origem do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa610-153">The additional options that are listed when you select this provider are not required to connect successfully to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source database.</span></span> <span data-ttu-id="fa610-154">Para obter uma descrição dessas opções, consulte a documentação do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Software Development Kit.</span><span class="sxs-lookup"><span data-stu-id="fa610-154">For a description of these additional options, see the documentation for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Software Development Kit.</span></span>  
  
### <a name="data-source--microsoft-excel"></a><span data-ttu-id="fa610-155">Fonte de Dados = Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="fa610-155">Data Source = Microsoft Excel</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa610-156">Selecione **Microsoft Excel** somente se você quiser se conectar a uma fonte de dados que usa o Excel 2003 ou anterior.</span><span class="sxs-lookup"><span data-stu-id="fa610-156">Select **Microsoft Excel** only if you want to connect to a data source that uses Excel 2003 or earlier.</span></span> <span data-ttu-id="fa610-157">Para se conectar a uma fonte de dados que usa o Excel 2007, selecione **Microsoft Office 12,0 acesso mecanismo de banco de dados provedor de OLE DB**, clique em **Propriedades**e, em seguida, na guia **tudo** da caixa de diálogo Propriedades do **vínculo de dados** , digite `Excel 12.0` como o valor das **Propriedades estendidas**.</span><span class="sxs-lookup"><span data-stu-id="fa610-157">To connect to a data source that uses Excel 2007, select **Microsoft Office 12.0 Access Database Engine OLE DB Provider**, click **Properties**, and then on the **All** tab of the **Data Link Properties** dialog box, enter `Excel 12.0` as the value for **Extended Properties**.</span></span>  
  
 <span data-ttu-id="fa610-158">**Caminho de arquivo do Excel**</span><span class="sxs-lookup"><span data-stu-id="fa610-158">**Excel file path**</span></span>  
 <span data-ttu-id="fa610-159">Especifique o caminho e nome de arquivo da planilha a partir da qual os dados serão importados.</span><span class="sxs-lookup"><span data-stu-id="fa610-159">Specify the path and file name for the spreadsheet from which to import the data.</span></span> <span data-ttu-id="fa610-160">Por exemplo, **C:\MyData.xls, \\\Sales\Database\Northwind.xls**.</span><span class="sxs-lookup"><span data-stu-id="fa610-160">For example, **C:\MyData.xls, \\\Sales\Database\Northwind.xls**.</span></span> <span data-ttu-id="fa610-161">Se preferir, clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="fa610-161">Or, click **Browse**.</span></span>  
  
 <span data-ttu-id="fa610-162">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="fa610-162">**Browse**</span></span>  
 <span data-ttu-id="fa610-163">Localize a planilha usando a caixa de diálogo **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="fa610-163">Locate the spreadsheet by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="fa610-164">**Versão do Excel**</span><span class="sxs-lookup"><span data-stu-id="fa610-164">**Excel version**</span></span>  
 <span data-ttu-id="fa610-165">Selecione a versão do Excel em que os dados de origem estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="fa610-165">Select the version of Excel that the source data is stored in.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa610-166">Quando você importa dados de uma origem do [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)], o assistente usa o componente [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Excel Source.</span><span class="sxs-lookup"><span data-stu-id="fa610-166">When you import data from a [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] source, the wizard uses the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Excel Source component.</span></span> <span data-ttu-id="fa610-167">Para obter informações sobre algumas considerações sobre uso e problemas conhecidos, consulte [Origem do Excel](../data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="fa610-167">For information about usage considerations and known issues, see [Excel Source](../data-flow/excel-source.md).</span></span>  
  
### <a name="data-source--microsoft-access"></a><span data-ttu-id="fa610-168">Fonte de Dados = Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="fa610-168">Data Source = Microsoft Access</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa610-169">Selecione **Microsoft Access** somente se você quiser se conectar a um banco de dados que usa o Access 2003 ou anterior.</span><span class="sxs-lookup"><span data-stu-id="fa610-169">Select **Microsoft Access** only if you want to connect to a database that uses Access 2003 or earlier.</span></span> <span data-ttu-id="fa610-170">Para se conectar a um banco de dados que usa o Access 2007, selecione **Microsoft Office mecanismo de banco de dados o provedor de OLE DB de acesso 12,0** .</span><span class="sxs-lookup"><span data-stu-id="fa610-170">To connect to a database that uses Access 2007, select **Microsoft Office 12.0 Access Database Engine OLE DB Provider** instead.</span></span>  
  
 <span data-ttu-id="fa610-171">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="fa610-171">**File name**</span></span>  
 <span data-ttu-id="fa610-172">Especifique o caminho e nome de arquivo do arquivo de banco de dados a partir do qual os dados serão importados.</span><span class="sxs-lookup"><span data-stu-id="fa610-172">Specify the path and file name for the database file from which to import the data.</span></span> <span data-ttu-id="fa610-173">Por exemplo, **C:\MyData.mdb, \\\Sales\Database\Northwind.mdb**.</span><span class="sxs-lookup"><span data-stu-id="fa610-173">For example, **C:\MyData.mdb, \\\Sales\Database\Northwind.mdb**.</span></span> <span data-ttu-id="fa610-174">Se preferir, clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="fa610-174">Or, click **Browse**.</span></span>  
  
 <span data-ttu-id="fa610-175">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="fa610-175">**Browse**</span></span>  
 <span data-ttu-id="fa610-176">Localize o arquivo de banco de dados usando a caixa de diálogo **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="fa610-176">Locate the database file by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="fa610-177">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="fa610-177">**User name**</span></span>  
 <span data-ttu-id="fa610-178">Especifique um nome de usuário válido para estabelecer conexão com o banco de dados quando houver um arquivo de informações do grupo de trabalho associado ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fa610-178">Specify a valid user name for the database connection when a workgroup information file is associated with the database.</span></span>  
  
 <span data-ttu-id="fa610-179">**Senha**</span><span class="sxs-lookup"><span data-stu-id="fa610-179">**Password**</span></span>  
 <span data-ttu-id="fa610-180">Forneça a senha do usuário para estabelecer conexão quando o arquivo de informações do grupo de trabalho estiver associado ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fa610-180">Provide the user's password for the database connection when a workgroup information file is associated with the database.</span></span> <span data-ttu-id="fa610-181">No entanto, se o banco de dados estiver protegido com uma única senha para todos os usuários, você deverá fornecer esse valor na caixa de diálogo **Propriedades do vínculo de dados** , que é acessada clicando em **avançado**.</span><span class="sxs-lookup"><span data-stu-id="fa610-181">However, if the database is protected with a single password for all users, you must provide this value in the **Data Link Properties** dialog box, which is accessed by clicking **Advanced**.</span></span>  
  
 <span data-ttu-id="fa610-182">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="fa610-182">**Advanced**</span></span>  
 <span data-ttu-id="fa610-183">Talvez você queira especificar opções avançadas, como a senha do banco de dados ou um arquivo de informações do grupo de trabalho não padrão, usando a caixa de diálogo **Propriedades do vínculo de dados** .</span><span class="sxs-lookup"><span data-stu-id="fa610-183">You may want to specify advanced options, such as the database password or a non-default workgroup information file, by using the **Data Link Properties** dialog box.</span></span> <span data-ttu-id="fa610-184">Para obter mais informações sobre as propriedades do provedor de OLE DB, pesquise na seção de acesso a dados da [biblioteca MSDN](https://go.microsoft.com/fwlink/?linkid=62553).</span><span class="sxs-lookup"><span data-stu-id="fa610-184">For more information about OLE DB provider properties, search in the Data Access section of the [MSDN library](https://go.microsoft.com/fwlink/?linkid=62553).</span></span>  
  
### <a name="data-source--flat-file-source"></a><span data-ttu-id="fa610-185">Fonte de Dados = Fonte de Arquivos Simples</span><span class="sxs-lookup"><span data-stu-id="fa610-185">Data Source = Flat File Source</span></span>  
 <span data-ttu-id="fa610-186">Consulte os tópicos a seguir para obter informações sobre as opções para uma fonte de dados de arquivos simples.</span><span class="sxs-lookup"><span data-stu-id="fa610-186">See the following topics for information about the options for a flat file data source.</span></span>  
  
 [<span data-ttu-id="fa610-187">Editor do Gerenciador de Conexões de Arquivos Simples &#40;Página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="fa610-187">Flat File Connection Manager Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
 [<span data-ttu-id="fa610-188">Editor do Gerenciador de Conexões de Arquivos Simples &#40;Página Colunas&#41;</span><span class="sxs-lookup"><span data-stu-id="fa610-188">Flat File Connection Manager Editor &#40;Columns Page&#41;</span></span>](../flat-file-connection-manager-editor-columns-page.md)  
  
 [<span data-ttu-id="fa610-189">Editor do Gerenciador de Conexões de Arquivos Simples &#40;Página Avançado&#41;</span><span class="sxs-lookup"><span data-stu-id="fa610-189">Flat File Connection Manager Editor &#40;Advanced Page&#41;</span></span>](../flat-file-connection-manager-editor-advanced-page.md)  
  
 [<span data-ttu-id="fa610-190">Editor do Gerenciador de Conexões de Arquivos Simples &#40;Página Visualização&#41;</span><span class="sxs-lookup"><span data-stu-id="fa610-190">Flat File Connection Manager Editor &#40;Preview Page&#41;</span></span>](../flat-file-connection-manager-editor-preview-page.md)  
  
  