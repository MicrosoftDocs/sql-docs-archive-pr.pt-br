---
title: Fazer backup da chave mestra de serviço | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server], exporting
ms.assetid: f60b917c-6408-48be-b911-f93b05796904
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: b79212040df67c22ae7e34cd380a1a1f1bd10773
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685506"
---
# <a name="back-up-the-service-master-key"></a><span data-ttu-id="27e32-102">Fazer backup da chave mestra de serviço</span><span class="sxs-lookup"><span data-stu-id="27e32-102">Back Up the Service Master Key</span></span>
  <span data-ttu-id="27e32-103">Este tópico descreve como fazer backup da Chave mestra de serviço no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27e32-103">This topic describes how to back-up the Service Master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="27e32-104">A chave mestra de serviço é a raiz da hierarquia de criptografia.</span><span class="sxs-lookup"><span data-stu-id="27e32-104">The service master key is the root of the encryption hierarchy.</span></span> <span data-ttu-id="27e32-105">Ela deve ter seu backup feito e armazenado em um local seguro, fora do site.</span><span class="sxs-lookup"><span data-stu-id="27e32-105">It should be backed up and stored in a secure, off-site location.</span></span> <span data-ttu-id="27e32-106">Criar este backup deveria ser uma das primeiras ações administrativas executadas no servidor.</span><span class="sxs-lookup"><span data-stu-id="27e32-106">Creating this backup should be one of the first administrative actions performed on the server.</span></span>  
  
 <span data-ttu-id="27e32-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="27e32-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="27e32-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="27e32-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="27e32-109">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="27e32-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="27e32-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="27e32-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="27e32-111">Para fazer backup da Chave mestra de serviço</span><span class="sxs-lookup"><span data-stu-id="27e32-111">To back-up the Service Master key</span></span>](#Procedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="27e32-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="27e32-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="27e32-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="27e32-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="27e32-114">A chave mestra deve estar aberta e, portanto, descriptografada antes de ser feito o back up.</span><span class="sxs-lookup"><span data-stu-id="27e32-114">The master key must be open and, therefore, decrypted before it is backed up.</span></span> <span data-ttu-id="27e32-115">Se for criptografada com a chave mestra de serviço, a chave mestra não precisará ser aberta explicitamente; porém, se a chave mestra só for criptografada com uma senha, deverá ser aberta explicitamente.</span><span class="sxs-lookup"><span data-stu-id="27e32-115">If it is encrypted with the service master key, the master key does not have to be explicitly opened; however, if the master key is encrypted only with a password, it must be explicitly opened.</span></span>  
  
-   <span data-ttu-id="27e32-116">Recomendamos que você faça o backup da chave mestra assim que ela for criada e armazene o backup em um local externo seguro.</span><span class="sxs-lookup"><span data-stu-id="27e32-116">We recommend that you back up the master key as soon as it is created, and store the backup in a secure, off-site location.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="27e32-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="27e32-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="27e32-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="27e32-118">Permissions</span></span>  
 <span data-ttu-id="27e32-119">Exige a permissão CONTROL no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="27e32-119">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="Procedure"></a> <span data-ttu-id="27e32-120">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="27e32-120">Using Transact-SQL</span></span>  
  
#### <a name="to-back-up-the-service-master-key"></a><span data-ttu-id="27e32-121">Para fazer backup da Chave mestra de serviço</span><span class="sxs-lookup"><span data-stu-id="27e32-121">To back-up the Service Master key</span></span>  
  
1.  <span data-ttu-id="27e32-122">No [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], conecte-se à instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que contém a chave mestra de serviço da qual você deseja fazer backup.</span><span class="sxs-lookup"><span data-stu-id="27e32-122">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance containing the service master key you wish to back up.</span></span>  
  
2.  <span data-ttu-id="27e32-123">Escolha uma senha que será usada para criptografar a chave mestra na mídia de backup.</span><span class="sxs-lookup"><span data-stu-id="27e32-123">Choose a password that will be used to encrypt the service master key on the backup medium.</span></span> <span data-ttu-id="27e32-124">Esta senha está sujeita à verificação de complexidade.</span><span class="sxs-lookup"><span data-stu-id="27e32-124">This password is subject to complexity checks.</span></span> <span data-ttu-id="27e32-125">Para obter mais informações, consulte [Password Policy](../password-policy.md).</span><span class="sxs-lookup"><span data-stu-id="27e32-125">For more information, see [Password Policy](../password-policy.md).</span></span>  
  
3.  <span data-ttu-id="27e32-126">Obtenha uma mídia de backup removível para armazenar uma cópia da chave de backup.</span><span class="sxs-lookup"><span data-stu-id="27e32-126">Obtain a removable backup medium for storing a copy of the backed-up key.</span></span>  
  
4.  <span data-ttu-id="27e32-127">Identifique um diretório NTFS no qual criar o backup da chave.</span><span class="sxs-lookup"><span data-stu-id="27e32-127">Identify an NTFS directory in which to create the backup of the key.</span></span> <span data-ttu-id="27e32-128">É aí que você criará o arquivo especificado na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="27e32-128">This is where you will create the file specified in the next step.</span></span> <span data-ttu-id="27e32-129">O diretório deve ser protegido com ACLs (listas de controle de acesso) altamente restritivas.</span><span class="sxs-lookup"><span data-stu-id="27e32-129">The directory should be protected with highly restrictive access control lists (ACLs).</span></span>  
  
5.  <span data-ttu-id="27e32-130">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27e32-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
6.  <span data-ttu-id="27e32-131">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="27e32-131">On the Standard bar, click **New Query**.</span></span>  
  
7.  <span data-ttu-id="27e32-132">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="27e32-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a backup of the "AdventureWorks2012" master key.  
    -- Because this master key is not encrypted by the service master key, a password must be specified when it is opened.  
    USE AdventureWorks2012;  
    GO  
    BACKUP SERVICE MASTER KEY TO FILE = 'c:\temp_backups\keys\service_master_ key'   
        ENCRYPTION BY PASSWORD = '3dH85Hhk003GHk2597gheij4';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="27e32-133">O caminho do arquivo para a chave e a senha da chave (se existir) serão diferentes do que é indicado acima.</span><span class="sxs-lookup"><span data-stu-id="27e32-133">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="27e32-134">Verifique se ambos são específicos da sua configuração de servidor e chave.</span><span class="sxs-lookup"><span data-stu-id="27e32-134">Make sure that both are specific to your server and key set-up.</span></span>  
  
8.  <span data-ttu-id="27e32-135">Copie o arquivo na mídia de backup e verifique a cópia.</span><span class="sxs-lookup"><span data-stu-id="27e32-135">Copy the file to the backup medium and verify the copy.</span></span>  
  
9. <span data-ttu-id="27e32-136">Armazene o backup em um local seguro, fora do site.</span><span class="sxs-lookup"><span data-stu-id="27e32-136">Store the backup in a secure, off-site location.</span></span>  
  
 <span data-ttu-id="27e32-137">Para obter mais informações, veja [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) e [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="27e32-137">For more information, see [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) and [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
  