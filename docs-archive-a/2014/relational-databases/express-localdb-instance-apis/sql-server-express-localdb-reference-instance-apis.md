---
title: Referência da API da instância LocalDB do SQL Server Express | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: faec46da-0536-4de3-96f3-83e607c8a8b6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5934bc5159998db22d7c560b31457524773e74eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678741"
---
# <a name="sql-server-express-localdb-instance-api-reference"></a><span data-ttu-id="98701-102">Referência de API da instância LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="98701-102">SQL Server Express LocalDB Instance API Reference</span></span>
  <span data-ttu-id="98701-103">No mundo do SQL Server tradicional baseado em serviço, as instâncias individuais do SQL Server instaladas em um único computador são separadas fisicamente; ou seja, cada instância deve ser instalada e removida separadamente, ter um conjunto separado de binários e ser executada em um processo de serviço separado.</span><span class="sxs-lookup"><span data-stu-id="98701-103">In the traditional, service-based SQL Server world, individual SQL Server instances installed on a single computer are physically separated; that is, each instance must be installed and removed separately, has a separate set of binaries, and runs under a separate service process.</span></span> <span data-ttu-id="98701-104">O nome da instância do SQL Server é usado para especificar a qual instância do SQL Server o usuário deseja se conectar.</span><span class="sxs-lookup"><span data-stu-id="98701-104">The SQL Server instance name is used to specify which SQL Server instance the user wants to connect to.</span></span>  
  
 <span data-ttu-id="98701-105">A API da instância LocalDB do SQL Server Express usa um modelo de instância "leve" simplificado.</span><span class="sxs-lookup"><span data-stu-id="98701-105">The SQL Server Express LocalDB instance API uses a simplified, "light" instance model.</span></span> <span data-ttu-id="98701-106">Embora as instâncias de LocalDB individuais estejam separadas no disco e no Registro, elas usam o mesmo conjunto de binários de LocalDB compartilhados.</span><span class="sxs-lookup"><span data-stu-id="98701-106">Although individual LocalDB instances are separated on the disk and in the registry, they use the same set of shared LocalDB binaries.</span></span> <span data-ttu-id="98701-107">Além disso, o LocalDB não usa serviços; as instâncias de LocalDB são iniciadas sob demanda através das chamadas de API da instância de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="98701-107">Moreover, LocalDB does not use services; LocalDB instances are launched on demand through LocalDB instance API calls.</span></span> <span data-ttu-id="98701-108">No LocalDB, o nome de instância é usado para especificar com qual das instâncias de LocalDB o usuário deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="98701-108">In LocalDB, the instance name is used to specify which of the LocalDB instances the user wants to work with.</span></span>  
  
 <span data-ttu-id="98701-109">Uma instância de LocalDB sempre é de propriedade de um único usuário e é visível e acessível somente do contexto desse usuário, a menos que o compartilhamento de instância esteja habilitado.</span><span class="sxs-lookup"><span data-stu-id="98701-109">A LocalDB instance is always owned by a single user and is visible and accessible only from this user's context, unless instance sharing is enabled.</span></span>  
  
 <span data-ttu-id="98701-110">Embora, tecnicamente, as instâncias de LocalDB não sejam iguais às instâncias tradicionais do SQL Server, seu uso pretendido é similar.</span><span class="sxs-lookup"><span data-stu-id="98701-110">Although technically LocalDB instances are not the same as traditional SQL Server instances, their intended use is similar.</span></span> <span data-ttu-id="98701-111">Elas são chamadas de *instâncias* para enfatizar essa similaridade e torná-las mais intuitivas para SQL Server usuários.</span><span class="sxs-lookup"><span data-stu-id="98701-111">They are called *instances* to emphasize this similarity and to make them more intuitive to SQL Server users.</span></span>  
  
 <span data-ttu-id="98701-112">O LocalDB oferece suporte a dois tipos de instâncias: AI (instâncias automáticas) e NI (instâncias nomeadas).</span><span class="sxs-lookup"><span data-stu-id="98701-112">LocalDB supports two kinds of instances: automatic instances (AI) and named instances (NI).</span></span> <span data-ttu-id="98701-113">O identificador de uma instância de LocalDB é o nome da instância.</span><span class="sxs-lookup"><span data-stu-id="98701-113">The identifier for a LocalDB instance is the instance name.</span></span>  
  
## <a name="automatic-localdb-instances"></a><span data-ttu-id="98701-114">Instâncias automáticas de LocalDB</span><span class="sxs-lookup"><span data-stu-id="98701-114">Automatic LocalDB Instances</span></span>  
 <span data-ttu-id="98701-115">As instâncias automáticas de LocalDB são "públicas"; Eles são criados e gerenciados automaticamente para o usuário e podem ser usados por qualquer aplicativo.</span><span class="sxs-lookup"><span data-stu-id="98701-115">Automatic LocalDB instances are "public"; they are created and managed automatically for the user and can be used by any application.</span></span> <span data-ttu-id="98701-116">Existe uma instância de LocalDB automática para cada versão do LocalDB instalada no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="98701-116">One automatic LocalDB instance exists for every version of LocalDB that is installed on the user's computer.</span></span>  
  
 <span data-ttu-id="98701-117">As instâncias automáticas de LocalDB fornecem gerenciamento de instância contínuo.</span><span class="sxs-lookup"><span data-stu-id="98701-117">Automatic LocalDB instances provide seamless instance management.</span></span> <span data-ttu-id="98701-118">O usuário não precisa criar a instância.</span><span class="sxs-lookup"><span data-stu-id="98701-118">The user does not need to create the instance.</span></span> <span data-ttu-id="98701-119">Isso permite que os usuários instalem facilmente os aplicativos e migrem para computadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="98701-119">This enables users to easily install applications and to migrate to different computers.</span></span> <span data-ttu-id="98701-120">Se o computador de destino tiver a versão especificada de LocalDB instalada, a instância automática de LocalDB para essa versão também estará disponível nesse computador.</span><span class="sxs-lookup"><span data-stu-id="98701-120">If the target computer has the specified version of LocalDB installed, the automatic LocalDB instance for that version is also available on that computer.</span></span>  
  
### <a name="automatic-instance-management"></a><span data-ttu-id="98701-121">Gerenciamento automático de instância</span><span class="sxs-lookup"><span data-stu-id="98701-121">Automatic Instance Management</span></span>  
 <span data-ttu-id="98701-122">Um usuário não precisa criar uma instância automática de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="98701-122">A user does not need to create an automatic LocalDB instance.</span></span> <span data-ttu-id="98701-123">A instância é criada lentamente na primeira vez em que a instância é usada, desde que a versão especificada do LocalDB esteja disponível no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="98701-123">The instance is lazily created the first time the instance is used, provided that the specified version of LocalDB is available on the user's computer.</span></span> <span data-ttu-id="98701-124">Do ponto de vista do usuário, a instância automática sempre estará presente se os binários LocalDB estiverem presentes.</span><span class="sxs-lookup"><span data-stu-id="98701-124">From the user's point of view, the automatic instance is always present if the LocalDB binaries are present.</span></span>  
  
 <span data-ttu-id="98701-125">Outras operações de gerenciamento de instância, como Excluir, Compartilhar e Descompartilhar, também funcionam para instâncias automáticas.</span><span class="sxs-lookup"><span data-stu-id="98701-125">Other instance management operations, such as Delete, Share, and Unshare, also work for automatic instances.</span></span> <span data-ttu-id="98701-126">Em particular, a exclusão de uma instância automática redefine a instância, que será recriada na próxima operação Iniciar.</span><span class="sxs-lookup"><span data-stu-id="98701-126">In particular, deleting an automatic instance effectively resets the instance, which will be re-created on the next Start operation.</span></span> <span data-ttu-id="98701-127">A exclusão de uma instância automática possivelmente será necessária se os bancos de dados do sistema forem danificados.</span><span class="sxs-lookup"><span data-stu-id="98701-127">Deleting an automatic instance may be required if the system databases become corrupted.</span></span>  
  
### <a name="automatic-instance-naming-rules"></a><span data-ttu-id="98701-128">Regras de nomeação de instância automática</span><span class="sxs-lookup"><span data-stu-id="98701-128">Automatic Instance Naming Rules</span></span>  
 <span data-ttu-id="98701-129">As instâncias automáticas de LocalDB têm um padrão especial para o nome de instância que pertence a um namespace reservado.</span><span class="sxs-lookup"><span data-stu-id="98701-129">Automatic LocalDB instances have a special pattern for the instance name that belongs to a reserved namespace.</span></span> <span data-ttu-id="98701-130">Isso é necessário para impedir conflitos de nomes com instâncias de LocalDB nomeadas.</span><span class="sxs-lookup"><span data-stu-id="98701-130">This is necessary to prevent name conflicts with named LocalDB instances.</span></span>  
  
 <span data-ttu-id="98701-131">O nome de instância automática é o número de versão de linha de base LocalDB precedido por um único caractere "v".</span><span class="sxs-lookup"><span data-stu-id="98701-131">The automatic instance name is the LocalDB baseline release version number preceded by a single "v" character.</span></span> <span data-ttu-id="98701-132">Isso se parece com "v" mais dois números com um ponto entre eles; por exemplo, v 11.0 ou V 12,00.</span><span class="sxs-lookup"><span data-stu-id="98701-132">This looks like "v" plus two numbers with a period between them; for example, v11.0 or V12.00.</span></span>  
  
 <span data-ttu-id="98701-133">Exemplos de nomes de instância automática ilegais:</span><span class="sxs-lookup"><span data-stu-id="98701-133">Examples of illegal automatic instance names are:</span></span>  
  
-   <span data-ttu-id="98701-134">11,0 (falta o caractere "v" no início)</span><span class="sxs-lookup"><span data-stu-id="98701-134">11.0 (missing the "v" character at the beginning)</span></span>  
  
-   <span data-ttu-id="98701-135">v11 (sem um ponto e o segundo número da versão)</span><span class="sxs-lookup"><span data-stu-id="98701-135">v11 (missing a period and the second number of the version)</span></span>  
  
-   <span data-ttu-id="98701-136">v11.</span><span class="sxs-lookup"><span data-stu-id="98701-136">v11.</span></span> <span data-ttu-id="98701-137">(sem o segundo número da versão)</span><span class="sxs-lookup"><span data-stu-id="98701-137">(missing the second number of the version)</span></span>  
  
-   <span data-ttu-id="98701-138">v11.0.1.2 (o número de versão tem mais de duas partes)</span><span class="sxs-lookup"><span data-stu-id="98701-138">v11.0.1.2 (version number has more than two parts)</span></span>  
  
## <a name="named-localdb-instances"></a><span data-ttu-id="98701-139">Instancias de LocalDB nomeadas</span><span class="sxs-lookup"><span data-stu-id="98701-139">Named LocalDB Instances</span></span>  
 <span data-ttu-id="98701-140">As instâncias nomeadas LocalDB são "privadas"; uma instância pertence a um único aplicativo que é responsável por criar e gerenciar a instância.</span><span class="sxs-lookup"><span data-stu-id="98701-140">Named LocalDB instances are "private"; an instance is owned by a single application that is responsible for creating and managing the instance.</span></span> <span data-ttu-id="98701-141">As instâncias de LocalDB nomeadas fornecem isolamento e melhoram o desempenho.</span><span class="sxs-lookup"><span data-stu-id="98701-141">Named LocalDB instances provide isolation and improve performance.</span></span>  
  
### <a name="named-instance-creation"></a><span data-ttu-id="98701-142">Criação da instância nomeada</span><span class="sxs-lookup"><span data-stu-id="98701-142">Named Instance Creation</span></span>  
 <span data-ttu-id="98701-143">O usuário deve criar as instâncias nomeadas explicitamente através da API de gerenciamento de LocalDB ou implicitamente através do arquivo app.config de um aplicativo gerenciado.</span><span class="sxs-lookup"><span data-stu-id="98701-143">The user must create named instances explicitly through the LocalDB management API, or implicitly through the app.config file for a managed application.</span></span> <span data-ttu-id="98701-144">Um aplicativo gerenciado também pode usar a API.</span><span class="sxs-lookup"><span data-stu-id="98701-144">A managed application may also use the API.</span></span>  
  
 <span data-ttu-id="98701-145">Cada instância nomeada tem uma versão de LocalDB associada; ou seja, ela indica um conjunto especificado de binários de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="98701-145">Each named instance has an associated LocalDB version; that is, it points to a specified set of LocalDB binaries.</span></span> <span data-ttu-id="98701-146">A versão da instância nomeada é definida durante o processo de criação de instância.</span><span class="sxs-lookup"><span data-stu-id="98701-146">The version for the named instance is set during the instance creation process.</span></span>  
  
### <a name="named-instance-naming-rules"></a><span data-ttu-id="98701-147">Regras de nomeação de instância nomeada</span><span class="sxs-lookup"><span data-stu-id="98701-147">Named Instance Naming Rules</span></span>  
 <span data-ttu-id="98701-148">Um nome de instância de LocalDB pode ter até 128 caracteres (o limite é imposto pelo tipo de dados `sysname`).</span><span class="sxs-lookup"><span data-stu-id="98701-148">A LocalDB instance name can have up to a total of 128 characters (the limit is imposed by the `sysname` data type).</span></span> <span data-ttu-id="98701-149">Essa é uma diferença significativa se comparada aos nomes de instância tradicionais do SQL Server, que são limitados aos nomes NetBIOS de 16 caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="98701-149">This is a significant difference compared to traditional SQL Server instance names, which are limited to NetBIOS names of 16 ASCII characters.</span></span> <span data-ttu-id="98701-150">A razão para essa diferença é que o LocalDB trata os bancos de dados como arquivos e, portanto, implica a semântica baseada em arquivo, portanto, é intuitivo para os usuários terem mais liberdade na escolha de nomes de instância.</span><span class="sxs-lookup"><span data-stu-id="98701-150">The reason for this difference is that LocalDB treats databases as files, and therefore implies file-based semantics, so it's intuitive for users to have more freedom in choosing instance names.</span></span>  
  
 <span data-ttu-id="98701-151">Um nome de instância de LocalDB pode conter qualquer caractere Unicode que seja legal no componente de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="98701-151">A LocalDB instance name can contain any Unicode characters that are legal within the filename component.</span></span> <span data-ttu-id="98701-152">Caracteres ilegais em um componente filename geralmente incluem os seguintes caracteres: caracteres ASCII/Unicode de 1 a 31, bem como aspas ("), menor que ( \<), greater than (> ), pipe (|), backspace (\b), tabulação (\t), dois-pontos (:), asterisco (\*), ponto de interrogação (?), barra invertida ( \\ ) e barra (/)</span><span class="sxs-lookup"><span data-stu-id="98701-152">Illegal characters in a filename component generally include the following characters: ASCII/Unicode characters 1 through 31, as well as quote ("), less than (\<), greater than (>), pipe (|), backspace (\b), tab (\t), colon (:), asterisk (\*), question mark (?), backslash (\\), and forward slash (/).</span></span> <span data-ttu-id="98701-153">Observe que o caractere nulo (\0) é permitido porque é usado na terminação de cadeias de caracteres; tudo o que aparecer após o primeiro caractere nulo será ignorado.</span><span class="sxs-lookup"><span data-stu-id="98701-153">Note that the null character (\0) is allowed because it is used for string termination; everything after the first null character will be ignored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98701-154">A lista de caracteres ilegais possivelmente dependerá do sistema operacional e mudará nas versões futuras.</span><span class="sxs-lookup"><span data-stu-id="98701-154">The list of illegal characters may depend on the operating system and may change in future releases.</span></span>  
  
 <span data-ttu-id="98701-155">Os espaços em branco à esquerda e à direita nos nomes de instância serão ignorados e cortados.</span><span class="sxs-lookup"><span data-stu-id="98701-155">Leading and trailing white spaces in instance names are ignored and will be trimmed.</span></span>  
  
 <span data-ttu-id="98701-156">Para evitar conflitos de nomenclatura, as instâncias nomeadas LocalDB não podem ter um nome que siga o padrão de nomenclatura para instâncias automáticas, conforme descrito anteriormente em "regras de nomenclatura de instância automática".</span><span class="sxs-lookup"><span data-stu-id="98701-156">To avoid naming conflicts, named LocalDB instances cannot have a name that follows the naming pattern for automatic instances, as described earlier in "Automatic Instance Naming Rules."</span></span> <span data-ttu-id="98701-157">Uma tentativa de criar uma instância nomeada com um nome que segue o padrão de nomeação de instância automática cria efetivamente uma instância padrão.</span><span class="sxs-lookup"><span data-stu-id="98701-157">An attempt to create a named instance with a name that follows the automatic instance naming pattern effectively creates a default instance.</span></span>  
  
## <a name="sql-server-express-localdb-reference-topics"></a><span data-ttu-id="98701-158">Tópicos de referência de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="98701-158">SQL Server Express LocalDB Reference Topics</span></span>  
 [<span data-ttu-id="98701-159">Cabeçalho e informações de versão de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="98701-159">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
 <span data-ttu-id="98701-160">Fornece informações do arquivo de cabeçalho e chaves do Registro para localizar a API de instância de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="98701-160">Provides header file information and registry keys for finding the LocalDB instance API.</span></span>  
  
 [<span data-ttu-id="98701-161">Ferramenta de gerenciamento da linha de comando: SqlLocalDB.exe</span><span class="sxs-lookup"><span data-stu-id="98701-161">Command-Line Management Tool: SqlLocalDB.exe</span></span>](command-line-management-tool-sqllocaldb-exe.md)  
 <span data-ttu-id="98701-162">Descreve o SqlLocalDB.exe, uma ferramenta para gerenciar instâncias de LocalDB na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="98701-162">Describes SqlLocalDB.exe, a tool for managing LocalDB instances from the command line.</span></span>  
  
 [<span data-ttu-id="98701-163">Função LocalDBCreateInstance</span><span class="sxs-lookup"><span data-stu-id="98701-163">LocalDBCreateInstance Function</span></span>](localdbcreateinstance-function.md)  
 <span data-ttu-id="98701-164">Descreve a função que cria uma nova instância de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="98701-164">Describes the function to create a new LocalDB instance.</span></span>  
  
 [<span data-ttu-id="98701-165">Função LocalDBDeleteInstance</span><span class="sxs-lookup"><span data-stu-id="98701-165">LocalDBDeleteInstance Function</span></span>](localdbdeleteinstance-function.md)  
 <span data-ttu-id="98701-166">Descreve a função que remove uma instância de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="98701-166">Describes the function to remove a LocalDB instance.</span></span>  
  
 [<span data-ttu-id="98701-167">Função LocalDBFormatMessage</span><span class="sxs-lookup"><span data-stu-id="98701-167">LocalDBFormatMessage Function</span></span>](localdbformatmessage-function.md)  
 <span data-ttu-id="98701-168">Descreve a função que retorna a descrição localizada de um erro de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="98701-168">Describes the function to return the localized description for a LocalDB error.</span></span>  
  
 [<span data-ttu-id="98701-169">Função LocalDBGetInstanceInfo</span><span class="sxs-lookup"><span data-stu-id="98701-169">LocalDBGetInstanceInfo Function</span></span>](localdbgetinstanceinfo-function.md)  
 <span data-ttu-id="98701-170">Descreve a função que obtém informações sobre uma instância de LocalDB; por exemplo, se ela existe, as informações da versão, se ela está em execução etc.</span><span class="sxs-lookup"><span data-stu-id="98701-170">Describes the function to get information for a LocalDB instance, such as whether it exists, version information, whether it is running, and so on.</span></span>  
  
 [<span data-ttu-id="98701-171">Função LocalDBGetInstances</span><span class="sxs-lookup"><span data-stu-id="98701-171">LocalDBGetInstances Function</span></span>](localdbgetinstances-function.md)  
 <span data-ttu-id="98701-172">Descreve a função que retorna todas as instância de LocalDB com uma versão especificada.</span><span class="sxs-lookup"><span data-stu-id="98701-172">Describes the function to return all the LocalDB instances with a specified version.</span></span>  
  
 [<span data-ttu-id="98701-173">Função LocalDBGetVersionInfo</span><span class="sxs-lookup"><span data-stu-id="98701-173">LocalDBGetVersionInfo Function</span></span>](localdbgetversioninfo-function.md)  
 <span data-ttu-id="98701-174">Descreve a função que retorna informações sobre uma versão de LocalDB especificada.</span><span class="sxs-lookup"><span data-stu-id="98701-174">Describes the function to return information for a specified LocalDB version.</span></span>  
  
 [<span data-ttu-id="98701-175">Função LocalDBGetVersions</span><span class="sxs-lookup"><span data-stu-id="98701-175">LocalDBGetVersions Function</span></span>](localdbgetversions-function.md)  
 <span data-ttu-id="98701-176">Descreve a função que retorna todas as versões de LocalDB disponíveis em um computador.</span><span class="sxs-lookup"><span data-stu-id="98701-176">Describes the function to return all LocalDB versions available on a computer.</span></span>  
  
 [<span data-ttu-id="98701-177">Função LocalDBShareInstance</span><span class="sxs-lookup"><span data-stu-id="98701-177">LocalDBShareInstance Function</span></span>](localdbshareinstance-function.md)  
 <span data-ttu-id="98701-178">Descreve a função que compartilha uma instância de LocalDB especificada.</span><span class="sxs-lookup"><span data-stu-id="98701-178">Describes the function to share a specified LocalDB instance.</span></span>  
  
 [<span data-ttu-id="98701-179">Função LocalDBStartInstance</span><span class="sxs-lookup"><span data-stu-id="98701-179">LocalDBStartInstance Function</span></span>](localdbstartinstance-function.md)  
 <span data-ttu-id="98701-180">Descreve a função que inicia uma instância de LocalDB especificada.</span><span class="sxs-lookup"><span data-stu-id="98701-180">Describes the function to start a specified LocalDB instance.</span></span>  
  
 [<span data-ttu-id="98701-181">Função LocalDBStartTracing</span><span class="sxs-lookup"><span data-stu-id="98701-181">LocalDBStartTracing Function</span></span>](localdbstarttracing-function.md)  
 <span data-ttu-id="98701-182">Descreve a função que habilitar o rastreamento de API para um usuário.</span><span class="sxs-lookup"><span data-stu-id="98701-182">Describes the function to enable API tracing for a user.</span></span>  
  
 [<span data-ttu-id="98701-183">Função LocalDBStopInstance</span><span class="sxs-lookup"><span data-stu-id="98701-183">LocalDBStopInstance Function</span></span>](localdbstopinstance-function.md)  
 <span data-ttu-id="98701-184">Descreve a função que interrompe a execução de uma instância de LocalDB especificada.</span><span class="sxs-lookup"><span data-stu-id="98701-184">Describes the function to stop a specified LocalDB instance from running.</span></span>  
  
 [<span data-ttu-id="98701-185">Função LocalDBStopTracing</span><span class="sxs-lookup"><span data-stu-id="98701-185">LocalDBStopTracing Function</span></span>](localdbstoptracing-function.md)  
 <span data-ttu-id="98701-186">Descreve a função que desabilita o rastramento de API para um usuário.</span><span class="sxs-lookup"><span data-stu-id="98701-186">Describes the function to disable API tracing for a user.</span></span>  
  
 [<span data-ttu-id="98701-187">Função LocalDBUnshareInstance</span><span class="sxs-lookup"><span data-stu-id="98701-187">LocalDBUnshareInstance Function</span></span>](localdbunshareinstance-function.md)  
 <span data-ttu-id="98701-188">Descreve a função que interrompe o compartilhamento de uma instância de LocalDB especificada.</span><span class="sxs-lookup"><span data-stu-id="98701-188">Describes the function to stop sharing a specified LocalDB instance.</span></span>  
  
  