---
title: Backup para URL do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 11be89e9-ff2a-4a94-ab5d-27d8edf9167d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6918a099e00b1de9e773320b5c6c0e4089859e02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681713"
---
# <a name="sql-server-backup-to-url"></a><span data-ttu-id="1d546-102">Backup do SQL Server para URL</span><span class="sxs-lookup"><span data-stu-id="1d546-102">SQL Server Backup to URL</span></span>
  <span data-ttu-id="1d546-103">Este tópico apresenta os conceitos, os requisitos e os componentes necessários para usar o serviço de armazenamento de BLOBs do Azure como um destino de backup.</span><span class="sxs-lookup"><span data-stu-id="1d546-103">This topic introduces the concepts, requirements and components necessary to use the Azure Blob storage service as a backup destination.</span></span> <span data-ttu-id="1d546-104">A funcionalidade de backup e restauração tem o mesmo efeito de DISK ou TAPE, com algumas diferenças.</span><span class="sxs-lookup"><span data-stu-id="1d546-104">The backup and restore functionality are same or similar to when using DISK or TAPE, with a few differences.</span></span> <span data-ttu-id="1d546-105">As diferenças, todas as exceções notáveis e alguns exemplos de código são incluídos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="1d546-105">The differences are and any notable exceptions, and a few code examples are included in this topic.</span></span>  
  
## <a name="requirements-components-and-concepts"></a><span data-ttu-id="1d546-106">Requisitos, componentes e conceitos</span><span class="sxs-lookup"><span data-stu-id="1d546-106">Requirements, Components, and Concepts</span></span>  
 <span data-ttu-id="1d546-107">**Nesta seção:**</span><span class="sxs-lookup"><span data-stu-id="1d546-107">**In this section:**</span></span>  
  
-   [<span data-ttu-id="1d546-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="1d546-108">Security</span></span>](#security)  
  
-   [<span data-ttu-id="1d546-109">Introdução aos principais componentes e conceitos</span><span class="sxs-lookup"><span data-stu-id="1d546-109">Introduction to Key Components and Concepts</span></span>](#intorkeyconcepts)  
  
-   [<span data-ttu-id="1d546-110">Serviço de armazenamento de BLOBs do Azure</span><span class="sxs-lookup"><span data-stu-id="1d546-110">Azure Blob Storage Service</span></span>](#Blob)  
  
-   [<span data-ttu-id="1d546-111">Componentes do SQL Server</span><span class="sxs-lookup"><span data-stu-id="1d546-111">SQL Server Components</span></span>](#sqlserver)  
  
-   [<span data-ttu-id="1d546-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="1d546-112">Limitations</span></span>](#limitations)  
  
-   [<span data-ttu-id="1d546-113">Suporte para instruções de backup/restauração</span><span class="sxs-lookup"><span data-stu-id="1d546-113">Support for Backup/Restore Statements</span></span>](#Support)  
  
-   [<span data-ttu-id="1d546-114">Usando a tarefa de backup no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1d546-114">Using Backup Task in SQL Server Management Studio</span></span>](sql-server-backup-to-url.md#BackupTaskSSMS)  
  
-   [<span data-ttu-id="1d546-115">Backup do SQL Server para a URL usando o Assistente de Plano de Manutenção</span><span class="sxs-lookup"><span data-stu-id="1d546-115">SQL Server Backup to URL Using Maintenance Plan Wizard</span></span>](sql-server-backup-to-url.md#MaintenanceWiz)  
  
-   [<span data-ttu-id="1d546-116">Restaurar a partir do armazenamento do Azure por meio do SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1d546-116">Restoring from Azure storage Using SQL Server Management Studio</span></span>](sql-server-backup-to-url.md#RestoreSSMS)  
  
###  <a name="security"></a><a name="security"></a> <span data-ttu-id="1d546-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="1d546-117">Security</span></span>  
 <span data-ttu-id="1d546-118">Veja a seguir as considerações e os requisitos de segurança ao fazer backup ou restauração dos serviços de armazenamento de BLOBs do Azure.</span><span class="sxs-lookup"><span data-stu-id="1d546-118">The following are security considerations and requirements when backing up to or restoring from the Azure Blob storage services.</span></span>  
  
-   <span data-ttu-id="1d546-119">Ao criar um contêiner para o serviço de armazenamento de BLOBs do Azure, recomendamos que você defina o acesso como **particular**.</span><span class="sxs-lookup"><span data-stu-id="1d546-119">When creating a container for the Azure Blob storage service, we recommend that you set the access to **private**.</span></span> <span data-ttu-id="1d546-120">A definição do acesso como privado restringe o acesso a usuários ou contas capazes de fornecer as informações necessárias para realizar a autenticação na conta do Azure.</span><span class="sxs-lookup"><span data-stu-id="1d546-120">Setting the access to private restricts the access to users or accounts able to provide the necessary information to authenticate to the Azure account.</span></span>  
  
    > [!IMPORTANT]  
    >  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="1d546-121">requer que o nome da conta do Azure e a autenticação de chave de acesso sejam armazenados em uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] credencial.</span><span class="sxs-lookup"><span data-stu-id="1d546-121">requires Azure account name and access key authentication to be stored in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential.</span></span> <span data-ttu-id="1d546-122">Essas informações são usadas para autenticar a conta do Azure quando ele executa operações de backup ou restauração.</span><span class="sxs-lookup"><span data-stu-id="1d546-122">This information is used to authenticate to the Azure account when it performs backup or restore operations.</span></span>  
  
-   <span data-ttu-id="1d546-123">A conta de usuário usada para emitir os comandos BACKUP ou RESTORE deve estar na função de banco de dados **operador db_backup** com as permissões **Alterar qualquer credencial** .</span><span class="sxs-lookup"><span data-stu-id="1d546-123">The user account that is used to issue BACKUP or RESTORE commands should be in the **db_backup operator** database role with **Alter any credential** permissions.</span></span>  
  
###  <a name="introduction-to-key-components-and-concepts"></a><a name="intorkeyconcepts"></a><span data-ttu-id="1d546-124">Introdução aos principais componentes e conceitos</span><span class="sxs-lookup"><span data-stu-id="1d546-124">Introduction to Key Components and Concepts</span></span>  
 <span data-ttu-id="1d546-125">As duas seções a seguir introduzem o serviço de armazenamento de BLOBs do Azure e os [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componentes usados durante o backup ou a restauração do serviço de armazenamento de BLOBs do Azure.</span><span class="sxs-lookup"><span data-stu-id="1d546-125">The following two sections introduce the Azure Blob storage service, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components used when backing up to or restoring from the Azure Blob storage service.</span></span> <span data-ttu-id="1d546-126">É importante entender os componentes e a interação entre eles para fazer um backup ou restauração a partir do serviço de armazenamento de BLOBs do Azure.</span><span class="sxs-lookup"><span data-stu-id="1d546-126">It is important to understand the components and the interaction between them to do a backup to or restore from the Azure Blob storage service.</span></span>  
  
 <span data-ttu-id="1d546-127">A criação de uma conta do Azure é a primeira etapa desse processo.</span><span class="sxs-lookup"><span data-stu-id="1d546-127">Creating an Azure account is the first step to this process.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="1d546-128">usa o **nome da conta de armazenamento do Azure** e seus valores de **chave de acesso** para autenticar e gravar e ler BLOBs no serviço de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="1d546-128">uses the **Azure storage account name** and its **access key** values to authenticate and write and read blobs to the storage service.</span></span> <span data-ttu-id="1d546-129">A credencial do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] armazena essas informações de autenticação e é usada durante as operações de backup ou restauração.</span><span class="sxs-lookup"><span data-stu-id="1d546-129">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential stores this authentication information and is used during the backup or restore operations.</span></span> <span data-ttu-id="1d546-130">Para obter uma explicação completa de como criar uma conta de armazenamento e executar uma restauração simples, consulte [tutorial usando o serviço de armazenamento do Azure para SQL Server Backup e restauração](https://go.microsoft.com/fwlink/?LinkId=271615).</span><span class="sxs-lookup"><span data-stu-id="1d546-130">For a complete walkthrough of creating a storage account and performing a simple restore, see [Tutorial Using Azure Storage Service for SQL Server Backup and Restore](https://go.microsoft.com/fwlink/?LinkId=271615).</span></span>  
  
 <span data-ttu-id="1d546-131">![mapeando a conta de armazenamento para as credenciais do sql](../../tutorials/media/backuptocloud-storage-credential-mapping.gif "mapeando a conta de armazenamento para as credenciais do sql")</span><span class="sxs-lookup"><span data-stu-id="1d546-131">![mapping storage account to sql credentials](../../tutorials/media/backuptocloud-storage-credential-mapping.gif "mapping storage account to sql credentials")</span></span>  
  
###  <a name="azure-blob-storage-service"></a><a name="Blob"></a><span data-ttu-id="1d546-132">Serviço de armazenamento de BLOBs do Azure</span><span class="sxs-lookup"><span data-stu-id="1d546-132">Azure Blob Storage Service</span></span>  
 <span data-ttu-id="1d546-133">**Conta de armazenamento:** A conta de armazenamento é o ponto de partida de todos os serviços de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="1d546-133">**Storage Account:** The storage account is the starting point for all storage services.</span></span> <span data-ttu-id="1d546-134">Para acessar o serviço de armazenamento de BLOBs do Azure, primeiro crie uma conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="1d546-134">To access the Azure Blob Storage service, first create an Azure storage account.</span></span> <span data-ttu-id="1d546-135">O **nome da conta de armazenamento** e suas propriedades de **chave de acesso** são necessários para autenticar o serviço de armazenamento de BLOBs do Azure e seus componentes.</span><span class="sxs-lookup"><span data-stu-id="1d546-135">The **storage account name** and its **access key** properties are required to authenticate to the Azure Blob Storage service and its components.</span></span>  
  
 <span data-ttu-id="1d546-136">**Contêiner:** Um contêiner fornece um agrupamento de um conjunto de BLOBs e pode armazenar um número ilimitado de BLOBs.</span><span class="sxs-lookup"><span data-stu-id="1d546-136">**Container:** A container provides a grouping of a set of Blobs, and can store an unlimited number of Blobs.</span></span> <span data-ttu-id="1d546-137">Para gravar um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup no serviço blob do Azure, você deve ter pelo menos o contêiner raiz criado.</span><span class="sxs-lookup"><span data-stu-id="1d546-137">To write a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup to the Azure Blob service, you must have at least the root container created.</span></span>  
  
 <span data-ttu-id="1d546-138">**Blob:** Um arquivo de qualquer tipo e tamanho.</span><span class="sxs-lookup"><span data-stu-id="1d546-138">**Blob:** A file of any type and size.</span></span> <span data-ttu-id="1d546-139">Há dois tipos de BLOBs que podem ser armazenados no serviço de armazenamento de BLOBs do Azure: blobs de bloco e de página.</span><span class="sxs-lookup"><span data-stu-id="1d546-139">There are two types of blobs that can be stored in the Azure Blob storage service: block and page blobs.</span></span> <span data-ttu-id="1d546-140">O backup do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa Blobs de página.</span><span class="sxs-lookup"><span data-stu-id="1d546-140">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup uses page Blobs as the Blob type.</span></span> <span data-ttu-id="1d546-141">Os BLOBs são endereçáveis usando o seguinte formato de URL: https:// \<storage account> . blob.Core.Windows.net/\<container>/\<blob></span><span class="sxs-lookup"><span data-stu-id="1d546-141">Blobs are addressable using the following URL format: https://\<storage account>.blob.core.windows.net/\<container>/\<blob></span></span>  
  
 <span data-ttu-id="1d546-142">![Armazenamento do Blobs do Azure](../../database-engine/media/backuptocloud-blobarchitecture.gif "Armazenamento do Blobs do Azure")</span><span class="sxs-lookup"><span data-stu-id="1d546-142">![Azure Blob Storage](../../database-engine/media/backuptocloud-blobarchitecture.gif "Azure Blob Storage")</span></span>  
  
 <span data-ttu-id="1d546-143">Para obter mais informações sobre o serviço de armazenamento de BLOBs do Azure, consulte [como usar o serviço de armazenamento de BLOBs do Azure](https://www.windowsazure.com/develop/net/how-to-guides/blob-storage/)</span><span class="sxs-lookup"><span data-stu-id="1d546-143">For more information about the Azure Blob storage service, see [How to use the Azure Blob Storage Service](https://www.windowsazure.com/develop/net/how-to-guides/blob-storage/)</span></span>  
  
 <span data-ttu-id="1d546-144">Para obter mais informações sobre blobs de páginas, consulte [Noções gerais sobre blobs de blocos e blobs de páginas](https://msdn.microsoft.com/library/windowsazure/ee691964.aspx)</span><span class="sxs-lookup"><span data-stu-id="1d546-144">For more information about page Blobs, see [Understanding Block and Page Blobs](https://msdn.microsoft.com/library/windowsazure/ee691964.aspx)</span></span>  
  
###  <a name="ssnoversion-components"></a><a name="sqlserver"></a> <span data-ttu-id="1d546-145">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Componentes</span><span class="sxs-lookup"><span data-stu-id="1d546-145">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components</span></span>  
 <span data-ttu-id="1d546-146">**URL:** Uma URL especifica um URI (Uniform Resource Identifier) para um arquivo de backup exclusivo.</span><span class="sxs-lookup"><span data-stu-id="1d546-146">**URL:** A URL specifies a Uniform Resource Identifier (URI) to a unique backup file.</span></span> <span data-ttu-id="1d546-147">A URL é usada para fornecer o local e o nome do arquivo de backup do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d546-147">The URL is used to provide the location and name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup file.</span></span> <span data-ttu-id="1d546-148">Nessa implementação, a única URL válida é aquela que aponta para um blob de páginas em uma conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="1d546-148">In this implementation, the only valid URL is one that points to a page Blob in an Azure storage account.</span></span> <span data-ttu-id="1d546-149">A URL deve apontar para um Blob real, e não apenas para um contêiner.</span><span class="sxs-lookup"><span data-stu-id="1d546-149">The URL must point to an actual Blob, not just a container.</span></span> <span data-ttu-id="1d546-150">Se o Blob não existir, ele será criado.</span><span class="sxs-lookup"><span data-stu-id="1d546-150">If the Blob does not exist, it is created.</span></span> <span data-ttu-id="1d546-151">Se um blob existente for especificado, o BACKUP falhará, a menos que a opção "com formato" seja especificada.</span><span class="sxs-lookup"><span data-stu-id="1d546-151">If an existing Blob is specified, BACKUP fails, unless the "WITH FORMAT" option is specified.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="1d546-152">Se você optar por copiar e carregar um arquivo de backup para o serviço de armazenamento de BLOBs do Azure, use o blob de páginas como sua opção de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="1d546-152">If you choose to copy and upload a backup file to the Azure Blob storage service, use page blob as your storage option.</span></span> <span data-ttu-id="1d546-153">Não há suporte para restaurações de Blobs de bloco.</span><span class="sxs-lookup"><span data-stu-id="1d546-153">Restores from Block Blobs are not supported.</span></span> <span data-ttu-id="1d546-154">A RESTAURAÇÃO de um blob de bloco falhará.</span><span class="sxs-lookup"><span data-stu-id="1d546-154">RESTORE from a block blob type fails with an error.</span></span>  
  
 <span data-ttu-id="1d546-155">Aqui está um exemplo de valor de URL: http [s]://ACCOUNTNAME.Blob.core.windows.net/ \<CONTAINER> / \<FILENAME.bak> .</span><span class="sxs-lookup"><span data-stu-id="1d546-155">Here is a sample URL value: http[s]://ACCOUNTNAME.Blob.core.windows.net/\<CONTAINER>/\<FILENAME.bak>.</span></span> <span data-ttu-id="1d546-156">O HTTPS não é obrigatório, mas é recomendado.</span><span class="sxs-lookup"><span data-stu-id="1d546-156">HTTPS is not required, but is recommended.</span></span>  
  
 <span data-ttu-id="1d546-157">**Credencial:** Uma credencial do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é um objeto usado para armazenar as informações de autenticação necessárias para se conectar a um recurso fora do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1d546-157">**Credential:** A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span>  <span data-ttu-id="1d546-158">Aqui, os [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processos de backup e restauração usam a credencial para autenticar o serviço de armazenamento de BLOBs do Azure.</span><span class="sxs-lookup"><span data-stu-id="1d546-158">Here, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore processes use credential to authenticate to the Azure Blob storage service.</span></span> <span data-ttu-id="1d546-159">A Credencial armazena o nome da conta de armazenamento e os valores de **access key** da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="1d546-159">The Credential stores the name of the storage account and the storage account **access key** values.</span></span> <span data-ttu-id="1d546-160">Depois que a credencial for criada, ela deverá ser especificada na opção WITH CREDENTIAL ao emitir instruções BACKUP/RESTORE.</span><span class="sxs-lookup"><span data-stu-id="1d546-160">Once the credential is created, it must be specified in the WITH CREDENTIAL option when issuing the BACKUP/RESTORE statements.</span></span> <span data-ttu-id="1d546-161">Para obter mais informações sobre como exibir, copiar ou gerar novamente as **access keys**da conta de armazenamento, consulte [Chaves de acesso da conta de armazenamento](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span><span class="sxs-lookup"><span data-stu-id="1d546-161">For more information about how to view, copy or regenerate storage account **access keys**, see [Storage Account Access Keys](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span></span>  
  
 <span data-ttu-id="1d546-162">Para obter instruções passo a passo sobre como criar uma credencial do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte o exemplo [Create a Credential](#credential) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="1d546-162">For step by step instructions about how to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential, see [Create a Credential](#credential) example later in this topic.</span></span>  
  
 <span data-ttu-id="1d546-163">Para obter informações gerais sobre credenciais, consulte [Credenciais](../security/authentication-access/credentials-database-engine.md)</span><span class="sxs-lookup"><span data-stu-id="1d546-163">For general information about credentials, see [Credentials](../security/authentication-access/credentials-database-engine.md)</span></span>  
  
 <span data-ttu-id="1d546-164">Para obter informações, em outros exemplos em que as credenciais são usadas, consulte [criar um proxy de SQL Server Agent](../../ssms/agent/create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="1d546-164">For information, on other examples where credentials are used, see [Create a SQL Server Agent Proxy](../../ssms/agent/create-a-sql-server-agent-proxy.md).</span></span>  
  
###  <a name="limitations"></a><a name="limitations"></a> <span data-ttu-id="1d546-165">Limitações</span><span class="sxs-lookup"><span data-stu-id="1d546-165">Limitations</span></span>  
  
-   <span data-ttu-id="1d546-166">Não há suporte para backup em armazenamento premium.</span><span class="sxs-lookup"><span data-stu-id="1d546-166">Backup to premium storage is not supported.</span></span>  
  
-   <span data-ttu-id="1d546-167">O tamanho máximo de backup com suporte é 1 TB.</span><span class="sxs-lookup"><span data-stu-id="1d546-167">The maximum backup size supported is 1 TB.</span></span>  
  
-   <span data-ttu-id="1d546-168">Você pode emitir instruções de backup ou restauração usando cmdlets do TSQL, SMO ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d546-168">You can issue backup or restore statements by using TSQL, SMO, or PowerShell cmdlets.</span></span> <span data-ttu-id="1d546-169">Um backup ou restauração do serviço de armazenamento de BLOBs do Azure usando SQL Server Management Studio assistente de backup ou restauração não está habilitado no momento.</span><span class="sxs-lookup"><span data-stu-id="1d546-169">A backup to or restoring from the Azure Blob storage service by using SQL Server Management Studio Backup or Restore wizard is not currently enabled.</span></span>  
  
-   <span data-ttu-id="1d546-170">Não há suporte para a criação de um nome de dispositivo lógico.</span><span class="sxs-lookup"><span data-stu-id="1d546-170">Creating a logical device name is not supported.</span></span> <span data-ttu-id="1d546-171">Portanto, não há suporte para a adição de uma URL como dispositivo de backup por meio de sp_dumpdevice ou do SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="1d546-171">So adding URL as a backup device using sp_dumpdevice or through SQL Server Management Studio is not supported.</span></span>  
  
-   <span data-ttu-id="1d546-172">Não há suporte para a anexação de blobs de backup.</span><span class="sxs-lookup"><span data-stu-id="1d546-172">Appending to existing backup blobs is not supported.</span></span> <span data-ttu-id="1d546-173">Os backups em um Blob existente só podem ser substituídos através da opção WITH FORMAT.</span><span class="sxs-lookup"><span data-stu-id="1d546-173">Backups to an existing Blob can only be overwritten by using the WITH FORMAT option.</span></span>  
  
-   <span data-ttu-id="1d546-174">Não há suporte para backup em vários blobs em uma única operação de backup.</span><span class="sxs-lookup"><span data-stu-id="1d546-174">Backup to multiple blobs in a single backup operation is not supported.</span></span> <span data-ttu-id="1d546-175">O exemplo a seguir retornará um erro:</span><span class="sxs-lookup"><span data-stu-id="1d546-175">For example, the following returns an error:</span></span>  
  
    ```sql
    BACKUP DATABASE AdventureWorks2012
    TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_1.bak'
       URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_2.bak'
          WITH CREDENTIAL = 'mycredential'
         ,STATS = 5;  
    GO
    ```  
  
-   <span data-ttu-id="1d546-176">Não há suporte para a especificação de um tamanho de bloco com `BACKUP`.</span><span class="sxs-lookup"><span data-stu-id="1d546-176">Specifying a block size with `BACKUP` is not supported.</span></span>  
  
-   <span data-ttu-id="1d546-177">Não há suporte para a especificação de `MAXTRANSFERSIZE`.</span><span class="sxs-lookup"><span data-stu-id="1d546-177">Specifying `MAXTRANSFERSIZE` is not supported.</span></span>  
  
-   <span data-ttu-id="1d546-178">Não há suporte para a especificação das opções de conjunto de backup - `RETAINDAYS` e `EXPIREDATE`.</span><span class="sxs-lookup"><span data-stu-id="1d546-178">Specifying backupset options - `RETAINDAYS` and `EXPIREDATE` are not supported.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1d546-179">tem um limite máximo de 259 caracteres em um nome de dispositivo de backup.</span><span class="sxs-lookup"><span data-stu-id="1d546-179">has a maximum limit of 259 characters for a backup device name.</span></span> <span data-ttu-id="1d546-180">O BACKUP TO URL consome 36 caracteres para os elementos necessários usados para especificar a URL – 'https://.blob.core.windows.net//.bak ', deixando 223 caracteres para os nomes da conta, do contêiner e do blob juntos.</span><span class="sxs-lookup"><span data-stu-id="1d546-180">The BACKUP TO URL consumes 36 characters for the required elements used to specify the URL - 'https://.blob.core.windows.net//.bak', leaving 223 characters for account, container, and blob names put together.</span></span>  
  
###  <a name="support-for-backuprestore-statements"></a><a name="Support"></a> <span data-ttu-id="1d546-181">Suporte a instruções de backup/restauração</span><span class="sxs-lookup"><span data-stu-id="1d546-181">Support for Backup/Restore Statements</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="1d546-182">Instrução de backup/restauração</span><span class="sxs-lookup"><span data-stu-id="1d546-182">Backup/Restore Statement</span></span>|<span data-ttu-id="1d546-183">Com suporte</span><span class="sxs-lookup"><span data-stu-id="1d546-183">Supported</span></span>|<span data-ttu-id="1d546-184">Exceções</span><span class="sxs-lookup"><span data-stu-id="1d546-184">Exceptions</span></span>|<span data-ttu-id="1d546-185">Comentários</span><span class="sxs-lookup"><span data-stu-id="1d546-185">Comments</span></span>|  
|<span data-ttu-id="1d546-186">BACKUP</span><span class="sxs-lookup"><span data-stu-id="1d546-186">BACKUP</span></span>|<span data-ttu-id="1d546-187">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-187">&#x2713;</span></span>|<span data-ttu-id="1d546-188">Não há suporte para BLOCKSIZE e MAXTRANSFERSIZE.</span><span class="sxs-lookup"><span data-stu-id="1d546-188">BLOCKSIZE, and MAXTRANSFERSIZE are not supported.</span></span>|<span data-ttu-id="1d546-189">Requer a especificação de WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="1d546-189">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="1d546-190">RESTORE</span><span class="sxs-lookup"><span data-stu-id="1d546-190">RESTORE</span></span>|<span data-ttu-id="1d546-191">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-191">&#x2713;</span></span>||<span data-ttu-id="1d546-192">Requer a especificação de WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="1d546-192">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="1d546-193">RESTORE FILELISTONLY</span><span class="sxs-lookup"><span data-stu-id="1d546-193">RESTORE FILELISTONLY</span></span>|<span data-ttu-id="1d546-194">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-194">&#x2713;</span></span>||<span data-ttu-id="1d546-195">Requer a especificação de WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="1d546-195">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="1d546-196">RESTORE HEADERONLY</span><span class="sxs-lookup"><span data-stu-id="1d546-196">RESTORE HEADERONLY</span></span>|<span data-ttu-id="1d546-197">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-197">&#x2713;</span></span>||<span data-ttu-id="1d546-198">Requer a especificação de WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="1d546-198">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="1d546-199">RESTORE LABELONLY</span><span class="sxs-lookup"><span data-stu-id="1d546-199">RESTORE LABELONLY</span></span>|<span data-ttu-id="1d546-200">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-200">&#x2713;</span></span>||<span data-ttu-id="1d546-201">Requer a especificação de WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="1d546-201">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="1d546-202">RESTORE VERIFYONLY</span><span class="sxs-lookup"><span data-stu-id="1d546-202">RESTORE VERIFYONLY</span></span>|<span data-ttu-id="1d546-203">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-203">&#x2713;</span></span>||<span data-ttu-id="1d546-204">Requer a especificação de WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="1d546-204">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="1d546-205">RESTORE REWINDONLY</span><span class="sxs-lookup"><span data-stu-id="1d546-205">RESTORE REWINDONLY</span></span>|<span data-ttu-id="1d546-206">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-206">&#x2713;</span></span>|||  
  
 <span data-ttu-id="1d546-207">Para obter a sintaxe e informações gerais sobre as instruções de backup, consulte [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1d546-207">For syntax and general information about backup statements, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
 <span data-ttu-id="1d546-208">Para obter a sintaxe e informações gerais sobre as instruções de restauração, consulte [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1d546-208">For syntax and general information about restore statements, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
### <a name="support-for-backup-arguments"></a><span data-ttu-id="1d546-209">Suporte para argumentos de backup</span><span class="sxs-lookup"><span data-stu-id="1d546-209">Support for Backup Arguments</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="1d546-210">Argumento</span><span class="sxs-lookup"><span data-stu-id="1d546-210">Argument</span></span>|<span data-ttu-id="1d546-211">Com suporte</span><span class="sxs-lookup"><span data-stu-id="1d546-211">Supported</span></span>|<span data-ttu-id="1d546-212">Exceção</span><span class="sxs-lookup"><span data-stu-id="1d546-212">Exception</span></span>|<span data-ttu-id="1d546-213">Comentários</span><span class="sxs-lookup"><span data-stu-id="1d546-213">Comments</span></span>|  
|<span data-ttu-id="1d546-214">DATABASE</span><span class="sxs-lookup"><span data-stu-id="1d546-214">DATABASE</span></span>|<span data-ttu-id="1d546-215">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-215">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-216">LOG</span><span class="sxs-lookup"><span data-stu-id="1d546-216">LOG</span></span>|<span data-ttu-id="1d546-217">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-217">&#x2713;</span></span>|||  
||  
|<span data-ttu-id="1d546-218">TO (URL)</span><span class="sxs-lookup"><span data-stu-id="1d546-218">TO (URL)</span></span>|<span data-ttu-id="1d546-219">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-219">&#x2713;</span></span>|<span data-ttu-id="1d546-220">Diferente de DISK e TAPE, a URL não oferece suporte para a especificação ou criação de um nome lógico.</span><span class="sxs-lookup"><span data-stu-id="1d546-220">Unlike DISK and TAPE, URL does not support specifying or creating a logical name.</span></span>|<span data-ttu-id="1d546-221">Esse argumento é usado para especificar o caminho da URL para o arquivo de backup.</span><span class="sxs-lookup"><span data-stu-id="1d546-221">This argument is used to specify the URL path for the backup file.</span></span>|  
|<span data-ttu-id="1d546-222">MIRROR TO</span><span class="sxs-lookup"><span data-stu-id="1d546-222">MIRROR TO</span></span>|<span data-ttu-id="1d546-223">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-223">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-224">**Opções WITH:**</span><span class="sxs-lookup"><span data-stu-id="1d546-224">**WITH OPTIONS:**</span></span>||||  
|<span data-ttu-id="1d546-225">CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="1d546-225">CREDENTIAL</span></span>|<span data-ttu-id="1d546-226">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-226">&#x2713;</span></span>||<span data-ttu-id="1d546-227">COM a CREDENCIAl só tem suporte ao usar a opção BACKUP TO URL para fazer backup no serviço de armazenamento de BLOBs do Azure.</span><span class="sxs-lookup"><span data-stu-id="1d546-227">WITH CREDENTIAL is only supported when using BACKUP TO URL option to back up to the Azure Blob storage service.</span></span>|  
|<span data-ttu-id="1d546-228">DIFFERENTIAL</span><span class="sxs-lookup"><span data-stu-id="1d546-228">DIFFERENTIAL</span></span>|<span data-ttu-id="1d546-229">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-229">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-230">COPY_ONLY</span><span class="sxs-lookup"><span data-stu-id="1d546-230">COPY_ONLY</span></span>|<span data-ttu-id="1d546-231">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-231">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-232">COMPRESSION&#124;NO_COMPRESSION</span><span class="sxs-lookup"><span data-stu-id="1d546-232">COMPRESSION&#124;NO_COMPRESSION</span></span>|<span data-ttu-id="1d546-233">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-233">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-234">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1d546-234">DESCRIPTION</span></span>|<span data-ttu-id="1d546-235">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-235">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-236">NAME</span><span class="sxs-lookup"><span data-stu-id="1d546-236">NAME</span></span>|<span data-ttu-id="1d546-237">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-237">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-238">EXPIREDATE &#124; RETAINDAYS</span><span class="sxs-lookup"><span data-stu-id="1d546-238">EXPIREDATE &#124; RETAINDAYS</span></span>|<span data-ttu-id="1d546-239">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-239">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-240">NOINIT &#124; INIT</span><span class="sxs-lookup"><span data-stu-id="1d546-240">NOINIT &#124; INIT</span></span>|<span data-ttu-id="1d546-241">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-241">&#x2713;</span></span>||<span data-ttu-id="1d546-242">Esta opção será ignorada se for usada.</span><span class="sxs-lookup"><span data-stu-id="1d546-242">This option is ignored if used.</span></span><br /><br /> <span data-ttu-id="1d546-243">Não é possível anexar aos blobs.</span><span class="sxs-lookup"><span data-stu-id="1d546-243">Appending to blobs is not possible.</span></span> <span data-ttu-id="1d546-244">Para substituir um backup, use o argumento FORMAT.</span><span class="sxs-lookup"><span data-stu-id="1d546-244">To overwrite a backup use the FORMAT argument.</span></span>|  
|<span data-ttu-id="1d546-245">NOSKIP &#124; SKIP</span><span class="sxs-lookup"><span data-stu-id="1d546-245">NOSKIP &#124; SKIP</span></span>|<span data-ttu-id="1d546-246">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-246">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-247">NOFORMAT &#124; FORMAT</span><span class="sxs-lookup"><span data-stu-id="1d546-247">NOFORMAT &#124; FORMAT</span></span>|<span data-ttu-id="1d546-248">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-248">&#x2713;</span></span>||<span data-ttu-id="1d546-249">Esta opção será ignorada se for usada.</span><span class="sxs-lookup"><span data-stu-id="1d546-249">This option is ignored if used.</span></span><br /><br /> <span data-ttu-id="1d546-250">Um backup feito em um blob existente falhará, a menos que WITH FORMAT seja especificado.</span><span class="sxs-lookup"><span data-stu-id="1d546-250">A backup taken to an existing blob fails unless WITH FORMAT is specified.</span></span> <span data-ttu-id="1d546-251">O blob existente será substituído quando WITH FORMAT for especificado.</span><span class="sxs-lookup"><span data-stu-id="1d546-251">The existing blob is overwritten when WITH FORMAT is specified.</span></span>|  
|<span data-ttu-id="1d546-252">MEDIADESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1d546-252">MEDIADESCRIPTION</span></span>|<span data-ttu-id="1d546-253">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-253">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-254">MEDIANAME</span><span class="sxs-lookup"><span data-stu-id="1d546-254">MEDIANAME</span></span>|<span data-ttu-id="1d546-255">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-255">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-256">BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="1d546-256">BLOCKSIZE</span></span>|<span data-ttu-id="1d546-257">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-257">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-258">BUFFERCOUNT</span><span class="sxs-lookup"><span data-stu-id="1d546-258">BUFFERCOUNT</span></span>|<span data-ttu-id="1d546-259">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-259">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-260">MAXTRANSFERSIZE</span><span class="sxs-lookup"><span data-stu-id="1d546-260">MAXTRANSFERSIZE</span></span>|<span data-ttu-id="1d546-261">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-261">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-262">NO_CHECKSUM &#124; CHECKSUM</span><span class="sxs-lookup"><span data-stu-id="1d546-262">NO_CHECKSUM &#124; CHECKSUM</span></span>|<span data-ttu-id="1d546-263">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-263">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-264">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span><span class="sxs-lookup"><span data-stu-id="1d546-264">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span></span>|<span data-ttu-id="1d546-265">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-265">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-266">ESTATÍSTICAS</span><span class="sxs-lookup"><span data-stu-id="1d546-266">STATS</span></span>|<span data-ttu-id="1d546-267">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-267">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-268">REWIND &#124; NOREWIND</span><span class="sxs-lookup"><span data-stu-id="1d546-268">REWIND &#124; NOREWIND</span></span>|<span data-ttu-id="1d546-269">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-269">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-270">UNLOAD &#124; NOUNLOAD</span><span class="sxs-lookup"><span data-stu-id="1d546-270">UNLOAD &#124; NOUNLOAD</span></span>|<span data-ttu-id="1d546-271">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-271">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-272">NORECOVERY &#124; STANDBY</span><span class="sxs-lookup"><span data-stu-id="1d546-272">NORECOVERY &#124; STANDBY</span></span>|<span data-ttu-id="1d546-273">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-273">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-274">NO_TRUNCATE</span><span class="sxs-lookup"><span data-stu-id="1d546-274">NO_TRUNCATE</span></span>|<span data-ttu-id="1d546-275">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-275">&#x2713;</span></span>|||  
  
 <span data-ttu-id="1d546-276">Para obter mais informações sobre os argumentos de backup, consulte [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1d546-276">For more information about backup arguments, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
### <a name="support-for-restore-arguments"></a><span data-ttu-id="1d546-277">Suporte para argumentos de restauração</span><span class="sxs-lookup"><span data-stu-id="1d546-277">Support for Restore Arguments</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="1d546-278">Argumento</span><span class="sxs-lookup"><span data-stu-id="1d546-278">Argument</span></span>|<span data-ttu-id="1d546-279">Com suporte</span><span class="sxs-lookup"><span data-stu-id="1d546-279">Supported</span></span>|<span data-ttu-id="1d546-280">Exceções</span><span class="sxs-lookup"><span data-stu-id="1d546-280">Exceptions</span></span>|<span data-ttu-id="1d546-281">Comentários</span><span class="sxs-lookup"><span data-stu-id="1d546-281">Comments</span></span>|  
|<span data-ttu-id="1d546-282">DATABASE</span><span class="sxs-lookup"><span data-stu-id="1d546-282">DATABASE</span></span>|<span data-ttu-id="1d546-283">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-283">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-284">LOG</span><span class="sxs-lookup"><span data-stu-id="1d546-284">LOG</span></span>|<span data-ttu-id="1d546-285">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-285">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-286">FROM (URL)</span><span class="sxs-lookup"><span data-stu-id="1d546-286">FROM (URL)</span></span>|<span data-ttu-id="1d546-287">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-287">&#x2713;</span></span>||<span data-ttu-id="1d546-288">O argumento FROM URL é usado para especificar o caminho da URL do arquivo de backup.</span><span class="sxs-lookup"><span data-stu-id="1d546-288">The FROM URL argument is used to specify the URL path for the backup file.</span></span>|  
|<span data-ttu-id="1d546-289">**WITH Options:**</span><span class="sxs-lookup"><span data-stu-id="1d546-289">**WITH Options:**</span></span>||||  
|<span data-ttu-id="1d546-290">CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="1d546-290">CREDENTIAL</span></span>|<span data-ttu-id="1d546-291">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-291">&#x2713;</span></span>||<span data-ttu-id="1d546-292">COM a CREDENCIAl só tem suporte ao usar a opção restaurar de URL para restaurar do serviço de armazenamento de BLOBs do Azure.</span><span class="sxs-lookup"><span data-stu-id="1d546-292">WITH CREDENTIAL is only supported when using RESTORE FROM URL option to restore from Azure Blob Storage service.</span></span>|  
|<span data-ttu-id="1d546-293">PARTIAL</span><span class="sxs-lookup"><span data-stu-id="1d546-293">PARTIAL</span></span>|<span data-ttu-id="1d546-294">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-294">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-295">RECOVERY &#124; NORECOVERY &#124; STANDBY</span><span class="sxs-lookup"><span data-stu-id="1d546-295">RECOVERY &#124; NORECOVERY &#124; STANDBY</span></span>|<span data-ttu-id="1d546-296">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-296">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-297">LOADHISTORY</span><span class="sxs-lookup"><span data-stu-id="1d546-297">LOADHISTORY</span></span>|<span data-ttu-id="1d546-298">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-298">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-299">MOVE</span><span class="sxs-lookup"><span data-stu-id="1d546-299">MOVE</span></span>|<span data-ttu-id="1d546-300">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-300">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-301">REPLACE</span><span class="sxs-lookup"><span data-stu-id="1d546-301">REPLACE</span></span>|<span data-ttu-id="1d546-302">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-302">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-303">RESTART</span><span class="sxs-lookup"><span data-stu-id="1d546-303">RESTART</span></span>|<span data-ttu-id="1d546-304">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-304">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-305">RESTRICTED_USER</span><span class="sxs-lookup"><span data-stu-id="1d546-305">RESTRICTED_USER</span></span>|<span data-ttu-id="1d546-306">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-306">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-307">FILE</span><span class="sxs-lookup"><span data-stu-id="1d546-307">FILE</span></span>|<span data-ttu-id="1d546-308">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-308">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-309">PASSWORD</span><span class="sxs-lookup"><span data-stu-id="1d546-309">PASSWORD</span></span>|<span data-ttu-id="1d546-310">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-310">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-311">MEDIANAME</span><span class="sxs-lookup"><span data-stu-id="1d546-311">MEDIANAME</span></span>|<span data-ttu-id="1d546-312">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-312">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-313">MEDIAPASSWORD</span><span class="sxs-lookup"><span data-stu-id="1d546-313">MEDIAPASSWORD</span></span>|<span data-ttu-id="1d546-314">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-314">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-315">BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="1d546-315">BLOCKSIZE</span></span>|<span data-ttu-id="1d546-316">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-316">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-317">BUFFERCOUNT</span><span class="sxs-lookup"><span data-stu-id="1d546-317">BUFFERCOUNT</span></span>|<span data-ttu-id="1d546-318">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-318">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-319">MAXTRANSFERSIZE</span><span class="sxs-lookup"><span data-stu-id="1d546-319">MAXTRANSFERSIZE</span></span>|<span data-ttu-id="1d546-320">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-320">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-321">CHECKSUM &#124; NO_CHECKSUM</span><span class="sxs-lookup"><span data-stu-id="1d546-321">CHECKSUM &#124; NO_CHECKSUM</span></span>|<span data-ttu-id="1d546-322">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-322">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-323">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span><span class="sxs-lookup"><span data-stu-id="1d546-323">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span></span>|<span data-ttu-id="1d546-324">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-324">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-325">FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="1d546-325">FILESTREAM</span></span>|<span data-ttu-id="1d546-326">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-326">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-327">ESTATÍSTICAS</span><span class="sxs-lookup"><span data-stu-id="1d546-327">STATS</span></span>|<span data-ttu-id="1d546-328">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-328">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-329">REWIND &#124; NOREWIND</span><span class="sxs-lookup"><span data-stu-id="1d546-329">REWIND &#124; NOREWIND</span></span>|<span data-ttu-id="1d546-330">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-330">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-331">UNLOAD &#124; NOUNLOAD</span><span class="sxs-lookup"><span data-stu-id="1d546-331">UNLOAD &#124; NOUNLOAD</span></span>|<span data-ttu-id="1d546-332">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-332">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-333">KEEP_REPLICATION</span><span class="sxs-lookup"><span data-stu-id="1d546-333">KEEP_REPLICATION</span></span>|<span data-ttu-id="1d546-334">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-334">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-335">KEEP_CDC</span><span class="sxs-lookup"><span data-stu-id="1d546-335">KEEP_CDC</span></span>|<span data-ttu-id="1d546-336">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-336">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-337">ENABLE_BROKER &#124; ERROR_BROKER_CONVERSATIONS &#124; NEW_BROKER</span><span class="sxs-lookup"><span data-stu-id="1d546-337">ENABLE_BROKER &#124; ERROR_BROKER_CONVERSATIONS &#124; NEW_BROKER</span></span>|<span data-ttu-id="1d546-338">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-338">&#x2713;</span></span>|||  
|<span data-ttu-id="1d546-339">STOPAT &#124; STOPATMARK &#124; STOPBEFOREMARK</span><span class="sxs-lookup"><span data-stu-id="1d546-339">STOPAT &#124; STOPATMARK &#124; STOPBEFOREMARK</span></span>|<span data-ttu-id="1d546-340">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="1d546-340">&#x2713;</span></span>|||  
  
 <span data-ttu-id="1d546-341">Para obter mais informações sobre os argumentos de restauração, consulte [Argumentos de RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1d546-341">For more information about Restore arguments, see [RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span></span>  
  
##  <a name="using-backup-task-in-sql-server-management-studio"></a><a name="BackupTaskSSMS"></a><span data-ttu-id="1d546-342">Usando a tarefa de backup no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1d546-342">Using Backup Task in SQL Server Management Studio</span></span>  
 <span data-ttu-id="1d546-343">A tarefa de backup no SQL Server Management Studio foi aprimorada para incluir a URL como uma das opções de destino e outros objetos de suporte necessários para fazer backup no armazenamento do Azure, como a credencial SQL.</span><span class="sxs-lookup"><span data-stu-id="1d546-343">The Backup task in SQL Server Management Studio has been enhanced to include URL as one of the destination options, and other supporting objects required to backup to Azure storage like the SQL Credential.</span></span>  
  
 <span data-ttu-id="1d546-344">As etapas a seguir descrevem as alterações feitas na tarefa backup de banco de dados para permitir o backup no armazenamento do Azure.:</span><span class="sxs-lookup"><span data-stu-id="1d546-344">The following steps describe the changes made to the Back Up Database task to allow for backing up to Azure storage.:</span></span>  
  
1.  <span data-ttu-id="1d546-345">Inicie o SQL Server Management Studio e conecte-se à instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1d546-345">Start SQL Server Management Studio and connect to the SQL Server instance.</span></span>  <span data-ttu-id="1d546-346">Selecione um banco de dados cujo backup você deseja fazer e clique com o botão direito do mouse em **tarefas**e selecione **fazer backup.**.. Isso abre a caixa de diálogo backup de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1d546-346">Select a database you want to backup, and right click on **Tasks**, and select **Back Up..**. This opens the Back Up Database dialog box.</span></span>  
  
2.  <span data-ttu-id="1d546-347">Na página geral, a opção **URL** é usada para criar um backup para o armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="1d546-347">On the general page the **URL** option is used to create a backup to Azure storage.</span></span> <span data-ttu-id="1d546-348">Quando você selecionar essa opção, verá outras opções habilitadas na página:</span><span class="sxs-lookup"><span data-stu-id="1d546-348">When you select this option, you see other options enabled on this page:</span></span>  
  
    1.  <span data-ttu-id="1d546-349">**Nome do arquivo:** Nome do arquivo de backup.</span><span class="sxs-lookup"><span data-stu-id="1d546-349">**File Name:** Name of the backup file.</span></span>  
  
    2.  <span data-ttu-id="1d546-350">**Credencial SQL:** Você pode especificar uma credencial de SQL Server existente ou pode criar uma nova clicando na caixa **criar** ao lado da credencial do SQL.</span><span class="sxs-lookup"><span data-stu-id="1d546-350">**SQL Credential:** You can either specify an existing SQL Server Credential, or can create a new one by clicking on the **Create** next to the SQL Credential box.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="1d546-351">A caixa de diálogo que é aberta quando você clica em **Criar** exige um certificado de gerenciamento ou o perfil da publicação para a assinatura.</span><span class="sxs-lookup"><span data-stu-id="1d546-351">The dialog that opens when you click **Create** requires a management certificate or the publishing profile for the subscription.</span></span> <span data-ttu-id="1d546-352">No momento, o SQL Server oferece suporte à versão do perfil de publicação 2.0.</span><span class="sxs-lookup"><span data-stu-id="1d546-352">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="1d546-353">Para baixar a versão com suporte do perfil de publicação, consulte [Download do perfil de publicação 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="1d546-353">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
        >   
        >  <span data-ttu-id="1d546-354">Se você não tiver acesso ao certificado de gerenciamento ou perfil de publicação, poderá criar uma credencial de SQL especificando o nome da conta de armazenamento e as informações da chave de acesso usando Transact-SQL ou SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="1d546-354">If you do not have access to the management certificate or publishing profile, you can create a SQL Credential by specifying the storage account name and access key information using Transact-SQL or SQL Server Management Studio.</span></span> <span data-ttu-id="1d546-355">Consulte o código de exemplo na seção [Criar uma credencial](#credential) para criar uma credencial usando Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="1d546-355">See the sample code in the [Create a Credential](#credential) section to create a credential using Transact-SQL.</span></span> <span data-ttu-id="1d546-356">Como alternativa, usando o SQL Server Management Studio, na instância do mecanismo de banco de dados, clique com o botão direito do mouse em **Segurança**, selecione **Novo**e **Credencial**.</span><span class="sxs-lookup"><span data-stu-id="1d546-356">Alternatively, using SQL Server Management Studio, from the database engine instance, right click **Security**, select **New**, and select **Credential**.</span></span> <span data-ttu-id="1d546-357">Especifique o nome da conta de armazenamento para **Identidade** e a chave de acesso no campo **Senha** .</span><span class="sxs-lookup"><span data-stu-id="1d546-357">Specify the storage account name for **Identity** and the access key in the **Password** field.</span></span>  
  
    3.  <span data-ttu-id="1d546-358">**Contêiner de armazenamento do Azure:** O nome do contêiner de armazenamento do Azure para armazenar os arquivos de backup.</span><span class="sxs-lookup"><span data-stu-id="1d546-358">**Azure storage container:** The name of the Azure storage container to store the backup files.</span></span>  
  
    4.  <span data-ttu-id="1d546-359">**Prefixo da URL:** Isso é criado automaticamente usando as informações especificadas nos campos descritos nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="1d546-359">**URL prefix:** This is built automatically using the information specified in the fields described in the previous steps.</span></span> <span data-ttu-id="1d546-360">Se você editar esse valor manualmente, verifique se ele corresponde às outras informações fornecidas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1d546-360">If you do edit this value manually, make sure it matches with the other information you provided previously.</span></span> <span data-ttu-id="1d546-361">Por exemplo, se você modificar a URL de armazenamento, verifique se a Credencial SQL será definida para ser autenticada na mesma conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="1d546-361">For example if you modify the storage URL, make sure the SQL Credential is set to authenticate to the same storage account.</span></span>  
  
 <span data-ttu-id="1d546-362">Quando você selecionar URL como destino, determinadas opções na página **Opções de Mídia** serão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="1d546-362">When you select URL as the destination, certain options in the **Media Options** page are disabled.</span></span>  <span data-ttu-id="1d546-363">Os tópicos a seguir têm mais informações na caixa de diálogo Backup de Banco de Dados:</span><span class="sxs-lookup"><span data-stu-id="1d546-363">The following topics have more information on the Back Up Database dialog:</span></span>  
  
 [<span data-ttu-id="1d546-364">Fazer backup do banco de dados &#40;página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="1d546-364">Back Up Database &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
 [<span data-ttu-id="1d546-365">Fazer backup do banco de dados &#40;página Opções de Mídia&#41;</span><span class="sxs-lookup"><span data-stu-id="1d546-365">Back Up Database &#40;Media Options Page&#41;</span></span>](back-up-database-media-options-page.md)  
  
 [<span data-ttu-id="1d546-366">Fazer backup do banco de dados &#40;página Opções de Backup&#41;</span><span class="sxs-lookup"><span data-stu-id="1d546-366">Back Up Database &#40;Backup Options Page&#41;</span></span>](back-up-database-backup-options-page.md)  
  
 [<span data-ttu-id="1d546-367">Criar credencial – autenticar no Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="1d546-367">Create Credential - Authenticate to Azure Storage</span></span>](create-credential-authenticate-to-azure-storage.md)  
  
##  <a name="sql-server-backup-to-url-using-maintenance-plan-wizard"></a><a name="MaintenanceWiz"></a><span data-ttu-id="1d546-368">SQL Server Backup para URL usando o assistente de plano de manutenção</span><span class="sxs-lookup"><span data-stu-id="1d546-368">SQL Server Backup to URL Using Maintenance Plan Wizard</span></span>  
 <span data-ttu-id="1d546-369">Semelhante à tarefa de backup descrita anteriormente, o assistente de plano de manutenção no SQL Server Management Studio foi aprimorado para incluir a **URL** como uma das opções de destino e outros objetos de suporte necessários para fazer backup no armazenamento do Azure, como a credencial SQL.</span><span class="sxs-lookup"><span data-stu-id="1d546-369">Similar to the backup task described previously, the Maintenance Plan Wizard in SQL Server Management Studio has been enhanced to include **URL** as one of the destination options, and other supporting objects required to backup to Azure storage like the SQL Credential.</span></span> <span data-ttu-id="1d546-370">Para obter mais informações, consulte a seção **Definir tarefas de Backup** em [Using Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure).</span><span class="sxs-lookup"><span data-stu-id="1d546-370">For more information, see  the **Define Backup Tasks** section in [Using Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure).</span></span>  
  
##  <a name="restoring-from-azure-storage-using-sql-server-management-studio"></a><a name="RestoreSSMS"></a><span data-ttu-id="1d546-371">Restaurando do armazenamento do Azure usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1d546-371">Restoring from Azure storage Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="1d546-372">Se você estiver restaurando um banco de dados, a **URL** será incluída como o dispositivo a partir do qual a restauração será realizada.</span><span class="sxs-lookup"><span data-stu-id="1d546-372">If you are restoring a database, **URL** is included as the device to restore from.</span></span> <span data-ttu-id="1d546-373">As etapas a seguir descrevem as alterações na tarefa de restauração para permitir a restauração do armazenamento do Azure:</span><span class="sxs-lookup"><span data-stu-id="1d546-373">Following steps describe the changes in the Restore task to allow restoring from Azure storage:</span></span>  
  
1.  <span data-ttu-id="1d546-374">Quando você seleciona **Dispositivos** na página **Geral** da tarefa Restaurar no SQL Server Management Studio, a caixa de diálogo **Selecione dispositivos de backup** , que inclui **URL** como um tipo de mídia de backup, é exibida.</span><span class="sxs-lookup"><span data-stu-id="1d546-374">When you select **Devices** in the **General** page of the Restore task in SQL Server Management Studio, this takes you to the **Select backup devices** dialog box which includes **URL** as a backup media type.</span></span>  
  
2.  <span data-ttu-id="1d546-375">Quando você seleciona **URL** e clica em **Adicionar**, a caixa de diálogo **Conectar-se ao armazenamento do Windows Azure** é aberta.</span><span class="sxs-lookup"><span data-stu-id="1d546-375">When you select **URL** and click **Add**, this opens the **Connect to Azure storage** dialog.</span></span> <span data-ttu-id="1d546-376">Especifique as informações de credencial do SQL para autenticar no armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="1d546-376">Specify the SQL Credential information to authenticate to Azure storage.</span></span>  
  
3.  <span data-ttu-id="1d546-377">Em seguida, o SQL Server se conecta ao armazenamento do Azure usando as informações de credencial do SQL fornecidas e abre a caixa de diálogo **localizar arquivo de backup no Azure** .</span><span class="sxs-lookup"><span data-stu-id="1d546-377">SQL Server then connects to Azure storage using the SQL Credential information you provided and opens the **Locate Backup File in Azure** dialog.</span></span> <span data-ttu-id="1d546-378">Os arquivos de backup que residem no armazenamento são exibidos nessa página.</span><span class="sxs-lookup"><span data-stu-id="1d546-378">The backup files residing in the storage are displayed on this page.</span></span> <span data-ttu-id="1d546-379">Selecione o arquivo que deseja usar para restaurar e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d546-379">Select the file you want to use to restore and click **OK**.</span></span> <span data-ttu-id="1d546-380">Isso o levará de volta para a caixa de diálogo **selecionar dispositivos de backup** e clicar em **OK** nessa caixa de diálogo o levará de volta para a caixa de diálogo de **restauração** principal, na qual você poderá concluir a restauração.</span><span class="sxs-lookup"><span data-stu-id="1d546-380">This takes you back to the **Select Backup Devices** dialog, and Clicking **OK** on this dialog takes you back to the main **Restore** dialog where you will be able complete the restore.</span></span>  <span data-ttu-id="1d546-381">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="1d546-381">For more information see, the following topics:</span></span>  
  
     [<span data-ttu-id="1d546-382">Restaurar banco de dados &#40;página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="1d546-382">Restore Database &#40;General Page&#41;</span></span>](restore-database-general-page.md)  
  
     [<span data-ttu-id="1d546-383">Restaurar banco de dados &#40;página Arquivos&#41;</span><span class="sxs-lookup"><span data-stu-id="1d546-383">Restore Database &#40;Files Page&#41;</span></span>](restore-database-files-page.md)  
  
     [<span data-ttu-id="1d546-384">Restaurar banco de dados &#40;página Opções&#41;</span><span class="sxs-lookup"><span data-stu-id="1d546-384">Restore Database &#40;Options Page&#41;</span></span>](restore-database-options-page.md)  
  
##  <a name="code-examples"></a><a name="Examples"></a> <span data-ttu-id="1d546-385">Exemplos de código</span><span class="sxs-lookup"><span data-stu-id="1d546-385">Code Examples</span></span>  
 <span data-ttu-id="1d546-386">Esta seção contém os seguintes exemplos:</span><span class="sxs-lookup"><span data-stu-id="1d546-386">This section contains the following examples.</span></span>  
  
-   [<span data-ttu-id="1d546-387">Criar uma credencial</span><span class="sxs-lookup"><span data-stu-id="1d546-387">Create a Credential</span></span>](#credential)  
  
-   [<span data-ttu-id="1d546-388">Fazendo backup de um banco de dados completo</span><span class="sxs-lookup"><span data-stu-id="1d546-388">Backing up a complete database</span></span>](#complete)  
  
-   [<span data-ttu-id="1d546-389">Fazendo backup do banco de dados e do log</span><span class="sxs-lookup"><span data-stu-id="1d546-389">Backing up the database and log</span></span>](#databaselog)  
  
-   [<span data-ttu-id="1d546-390">Criando um backup de arquivo completo do grupo de arquivos primário</span><span class="sxs-lookup"><span data-stu-id="1d546-390">Creating a full file backup of the primary filegroup</span></span>](#filebackup)  
  
-   [<span data-ttu-id="1d546-391">Criando um backup de arquivo diferencial dos grupos de arquivos primários</span><span class="sxs-lookup"><span data-stu-id="1d546-391">Creating a differential file backup of the primary filegroups</span></span>](#differential)  
  
-   [<span data-ttu-id="1d546-392">Restaurando um banco de dados e movendo arquivos</span><span class="sxs-lookup"><span data-stu-id="1d546-392">Restoring a database and move files</span></span>](#restoredbwithmove)  
  
-   [<span data-ttu-id="1d546-393">Restauração pontual usando STOPAT</span><span class="sxs-lookup"><span data-stu-id="1d546-393">Restoring to a point-in-time using STOPAT</span></span>](#PITR)  
  
###  <a name="create-a-credential"></a><a name="credential"></a> <span data-ttu-id="1d546-394">Criar uma credencial</span><span class="sxs-lookup"><span data-stu-id="1d546-394">Create a Credential</span></span>  
 <span data-ttu-id="1d546-395">O exemplo a seguir cria uma credencial que armazena as informações de autenticação do armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="1d546-395">The following example creates a credential that stores the Azure Storage authentication information.</span></span>  

   ```sql
   IF NOT EXISTS  
   (SELECT * FROM sys.credentials   
   WHERE credential_identity = 'mycredential')  
   CREATE CREDENTIAL mycredential WITH IDENTITY = 'mystorageaccount'  
   ,SECRET = '<storage access key>' ;  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
   string secret = "<storage access key>";  
  
   // Create a Credential  
   string credentialName = "mycredential";  
   Credential credential = new Credential(server, credentialName);  
   credential.Create(identity, secret);  
   ```  
  
   ```powershell
   # create variables  
   $storageAccount = "mystorageaccount"  
   $storageKey = "<storage access key>"  
   $secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
   $credentialName = "mycredential"  
  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # Create a credential  
   New-SqlCredential -Name $credentialName -Path $srvpath -Identity $storageAccount -Secret $secureString
   ```  
  
###  <a name="backing-up-a-complete-database"></a><a name="complete"></a><span data-ttu-id="1d546-396">Fazendo backup de um banco de dados completo</span><span class="sxs-lookup"><span data-stu-id="1d546-396">Backing up a complete database</span></span>  
 <span data-ttu-id="1d546-397">O exemplo a seguir faz backup do banco de dados AdventureWorks2012 para o serviço de armazenamento de BLOBs do Azure.</span><span class="sxs-lookup"><span data-stu-id="1d546-397">The following example backs up the AdventureWorks2012 database to the Azure Blob storage service.</span></span>
  
   ```sql
   BACKUP DATABASE AdventureWorks2012   
   TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'   
         WITH CREDENTIAL = 'mycredential'   
         ,COMPRESSION  
         ,STATS = 5;  
   GO
   ```  
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server);  
   ```
  
   ```powershell
   # create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"   
   # for default instance, the $srvpath varilable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance  
   CD $srvPath   
   $backupFile = $backupUrlContainer + "AdventureWorks2012" +  ".bak"  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On
   ```  
  
###  <a name="backing-up-the-database-and-log"></a><a name="databaselog"></a><span data-ttu-id="1d546-398">Fazendo backup do banco de dados e do log</span><span class="sxs-lookup"><span data-stu-id="1d546-398">Backing up the database and log</span></span>  
 <span data-ttu-id="1d546-399">O exemplo a seguir faz backup do banco de dados de exemplo AdventureWorks2012, que, por padrão, usa o modelo de recuperação simples.</span><span class="sxs-lookup"><span data-stu-id="1d546-399">The following example backups up the AdventureWorks2012 sample database, which uses the simple recovery model by default.</span></span> <span data-ttu-id="1d546-400">Para oferecer suporte a backups de log, o banco de dados AdventureWorks2012 é modificado para usar o modelo de recuperação completa.</span><span class="sxs-lookup"><span data-stu-id="1d546-400">To support log backups, the AdventureWorks2012 database is modified to use the full recovery model.</span></span> <span data-ttu-id="1d546-401">Em seguida, o exemplo cria um backup de banco de dados completo para o blob do Azure e, após um período de atividade de atualização, faz o backup do log.</span><span class="sxs-lookup"><span data-stu-id="1d546-401">The example then creates a full database backup to Azure Blob, and after a period of update activity, backs up the log.</span></span> <span data-ttu-id="1d546-402">Esse exemplo cria um nome de arquivo de backup com um carimbo de data/hora.</span><span class="sxs-lookup"><span data-stu-id="1d546-402">This example creates a backup file name with a datetime stamp.</span></span>  
  
   ```sql
   -- To permit log backups, before the full database backup, modify the database   
   -- to use the full recovery model.  
   USE master;  
   GO  
   ALTER DATABASE AdventureWorks2012  
      SET RECOVERY FULL;  
   GO  
  
   -- Back up the full AdventureWorks2012 database.  
          -- First create a file name for the backup file with DateTime stamp  
  
   DECLARE @Full_Filename AS VARCHAR (300);  
   SET @Full_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Full_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.bak';   
   --Back up Adventureworks2012 database  
  
   BACKUP DATABASE AdventureWorks2012  
   TO URL =  @Full_Filename  
   WITH CREDENTIAL = 'mycredential';  
   ,COMPRESSION  
   GO  
   -- Back up the AdventureWorks2012 log.  
   DECLARE @Log_Filename AS VARCHAR (300);  
   SET @Log_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Log_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.trn';  
   BACKUP LOG AdventureWorks2012  
    TO URL = @Log_Filename  
    WITH CREDENTIAL = 'mycredential'  
    ,COMPRESSION;  
   GO  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url for data backup  
   string urlDataBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}_Data-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Database to Url  
   Backup backupData = new Backup();  
   backupData.CredentialName = credentialName;  
   backupData.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backupData.Devices.AddDevice(urlDataBackup, DeviceType.Url);  
   backupData.SqlBackup(server);  
  
   // Generate Unique Url for data backup  
   string urlLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}_Log-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Database Log to Url  
   Backup backupLog = new Backup();  
   backupLog.CredentialName = credentialName;  
   backupLog.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backupLog.Devices.AddDevice(urlLogBackup, DeviceType.Url);  
   backupLog.Action = BackupActionType.Log;  
   backupLog.SqlBackup(server);  
   ```  

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to theSQL Server Instance
   CD $srvPath   
   #Create a unique file name for the full database backup  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   #Backup Database to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Database    
  
   #Create a unique file name for log backup  
  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup Log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Log
   ```  
  
###  <a name="creating-a-full-file-backup-of-the-primary-filegroup"></a><a name="filebackup"></a><span data-ttu-id="1d546-403">Criando um backup de arquivo completo do grupo de arquivos primário</span><span class="sxs-lookup"><span data-stu-id="1d546-403">Creating a full file backup of the primary filegroup</span></span>  
 <span data-ttu-id="1d546-404">O exemplo a seguir cria um backup de arquivo completo do grupo de arquivos primário.</span><span class="sxs-lookup"><span data-stu-id="1d546-404">The following example creates a full file backup of the primary filegroup.</span></span>
  
   ```sql
   --Back up the files in Primary:  
   BACKUP DATABASE AdventureWorks2012  
       FILEGROUP = 'Primary'  
       TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012files.bck'  
       WITH CREDENTIAL = 'mycredential'  
       ,COMPRESSION;  
   GO  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bck",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Action = BackupActionType.Files;  
   backup.DatabaseFileGroups.Add("PRIMARY");  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server);
   ```
  
   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to the SQL Server Instance  
  
   CD $srvPath   
   #Create a unique file name for the file backup  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bck"  
  
   #Backup Primary File Group to URL  
  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Files -DatabaseFileGroup Primary
   ```  
  
###  <a name="creating-a-differential-file-backup-of-the-primary-filegroup"></a><a name="differential"></a><span data-ttu-id="1d546-405">Criando um backup de arquivo diferencial do grupo de arquivos primário</span><span class="sxs-lookup"><span data-stu-id="1d546-405">Creating a differential file backup of the primary filegroup</span></span>  
 <span data-ttu-id="1d546-406">O exemplo a seguir cria um backup de arquivo diferencial do grupo de arquivos primário.</span><span class="sxs-lookup"><span data-stu-id="1d546-406">The following example creates a differential file backup of the primary filegroup.</span></span>  
  
   ```sql
   --Back up the files in Primary:  
   BACKUP DATABASE AdventureWorks2012  
       FILEGROUP = 'Primary'  
       TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012filesdiff.bck'  
       WITH   
          CREDENTIAL = 'mycredential'  
          ,COMPRESSION  
      ,DIFFERENTIAL;  
   GO
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Action = BackupActionType.Files;  
   backup.DatabaseFileGroups.Add("PRIMARY");  
   backup.Incremental = true;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server); 
   ```

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   #Create a differential backup of the primary filegroup
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Files -DatabaseFileGroup Primary -Incremental
   ```  
  
###  <a name="restore-a-database-and-move-files"></a><a name="restoredbwithmove"></a><span data-ttu-id="1d546-407">Restaurar um banco de dados e mover arquivos</span><span class="sxs-lookup"><span data-stu-id="1d546-407">Restore a database and move files</span></span>  
 <span data-ttu-id="1d546-408">Para restaurar um backup de banco de dados completo e mover o banco de dados restaurado para o diretório C:\Arquivos de Programas\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data, execute as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="1d546-408">To restore a full database backup and move the restored database to C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data directory, use the following steps.</span></span>
  
   ```sql
   -- Backup the tail of the log first
   DECLARE @Log_Filename AS VARCHAR (300);  
   SET @Log_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Log_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.trn';  
   BACKUP LOG AdventureWorks2012  
    TO URL = @Log_Filename  
    WITH CREDENTIAL = 'mycredential'  
    ,NORECOVERY;  
   GO  
  
   RESTORE DATABASE AdventureWorks2012 FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'  
   WITH CREDENTIAL = 'mycredential'  
    ,MOVE 'AdventureWorks2012_data' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf'  
    ,MOVE 'AdventureWorks2012_log' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf'  
    ,STATS = 5
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string urlBackupData = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-Data{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   backup.SqlBackup(server);  
  
   // Generate Unique Url for tail log backup  
   string urlTailLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-TailLog{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Tail Log to Url  
   Backup backupTailLog = new Backup();  
   backupTailLog.CredentialName = credentialName;  
   backupTailLog.Database = dbName;  
   backupTailLog.Action = BackupActionType.Log;  
   backupTailLog.NoRecovery = true;  
   backupTailLog.Devices.AddDevice(urlTailLogBackup, DeviceType.Url);  
   backupTailLog.SqlBackup(server);  
  
   // Restore a database and move files  
   string newDataFilePath = server.MasterDBLogPath  + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".mdf";  
   string newLogFilePath = server.MasterDBLogPath  + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".ldf";  
  
   Restore restore = new Restore();  
   restore.CredentialName = credentialName;  
   restore.Database = dbName;  
   restore.ReplaceDatabase = true;  
   restore.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restore.RelocateFiles.Add(new RelocateFile(dbName, newDataFilePath));  
   restore.RelocateFiles.Add(new RelocateFile(dbName+ "_Log", newLogFilePath));  
   restore.SqlRestore(server);
   ```  

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTNACENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   # Full database backup to URL  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupdbFile  -SqlCredential $credentialName -CompressionOption On      
  
   #Create a unique file name for the tail log backup  
   $backuplogFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup tail log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName  -BackupAction Log -NoRecovery    
  
   # Restore Database and move files
   $newDataFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile ("AdventureWorks_Data","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf")  
   $newLogFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile("AdventureWorks_Log","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf")  
  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backupdbFile -RelocateFile @($newDataFilePath,$newLogFilePath)
   ```  
  
###  <a name="restoring-to-a-point-in-time-using-stopat"></a><a name="PITR"></a> <span data-ttu-id="1d546-409">Restauração pontual usando STOPAT</span><span class="sxs-lookup"><span data-stu-id="1d546-409">Restoring to a point-in-time using STOPAT</span></span>  
 <span data-ttu-id="1d546-410">O exemplo a seguir restaura um banco de dados para seu estado em um determinado ponto e mostra uma operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="1d546-410">The following example restores a database to its state to a point in time, and shows a restore operation.</span></span>  
  
   ```sql
   RESTORE DATABASE AdventureWorks FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'   
   WITH   
     CREDENTIAL = 'mycredential'  
    ,MOVE 'AdventureWorks2012_data' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf'  
    ,Move 'AdventureWorks2012_log' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf'  
    ,NORECOVERY  
    --,REPLACE  
    ,STATS = 5;  
   GO   
  
   RESTORE LOG AdventureWorks FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.trn'   
   WITH CREDENTIAL = 'mycredential'  
    ,RECOVERY   
    ,STOPAT = 'Oct 23, 2012 5:00 PM'   
   GO  
   ```  
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string urlBackupData = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-Data{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   backup.SqlBackup(server);  
  
   // Generate Unique Url for Tail Log backup  
   string urlTailLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-TailLog{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Tail Log to Url  
   Backup backupTailLog = new Backup();  
   backupTailLog.CredentialName = credentialName;  
   backupTailLog.Database = dbName;  
   backupTailLog.Action = BackupActionType.Log;  
   backupTailLog.NoRecovery = true;  
   backupTailLog.Devices.AddDevice(urlTailLogBackup, DeviceType.Url);  
   backupTailLog.SqlBackup(server);  
  
   // Restore a database and move files  
   string newDataFilePath = server.MasterDBLogPath + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".mdf";  
   string newLogFilePath = server.MasterDBLogPath + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".ldf";  
  
   Restore restore = new Restore();  
   restore.CredentialName = credentialName;  
   restore.Database = dbName;  
   restore.ReplaceDatabase = true;  
   restore.NoRecovery = true;  
   restore.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restore.RelocateFiles.Add(new RelocateFile(dbName, newDataFilePath));  
   restore.RelocateFiles.Add(new RelocateFile(dbName + "_Log", newLogFilePath));  
   restore.SqlRestore(server);  
      
   // Restore transaction Log with stop at   
   Restore restoreLog = new Restore();  
   restoreLog.CredentialName = credentialName;  
   restoreLog.Database = dbName;  
   restoreLog.Action = RestoreActionType.Log;  
   restoreLog.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restoreLog.ToPointInTime = DateTime.Now.ToString();   
   restoreLog.SqlRestore(server);
   ```
  
   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # Navigate to SQL Server Instance Directory
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   # Full database backup to URL  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupdbFile  -SqlCredential $credentialName -CompressionOption On     
  
   #Create a unique file name for the tail log backup  
   $backuplogFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup tail log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName  -BackupAction Log -NoRecovery     
  
   # Restore Database and move files
   $newDataFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile ("AdventureWorks_Data","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf")  
   $newLogFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile("AdventureWorks_Log","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf")  
  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backupdbFile -RelocateFile @($newDataFilePath,$newLogFilePath) -NoRecovery    
  
   # Restore Transaction log with Stop At:  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backuplogFile  -ToPointInTime (Get-Date).ToString()
   ```  
  
## <a name="see-also"></a><span data-ttu-id="1d546-411">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1d546-411">See Also</span></span>  
 <span data-ttu-id="1d546-412">[Práticas recomendadas e solução de problemas de backup do SQL Server para URL](sql-server-backup-to-url-best-practices-and-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="1d546-412">[SQL Server Backup to URL Best Practices and Troubleshooting](sql-server-backup-to-url-best-practices-and-troubleshooting.md) </span></span>  
 [<span data-ttu-id="1d546-413">Fazer backup e restaurar bancos de dados do sistema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1d546-413">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](back-up-and-restore-of-system-databases-sql-server.md)   