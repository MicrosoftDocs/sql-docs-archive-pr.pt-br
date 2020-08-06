---
title: Tarefa FTP | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftptask.f1
helpviewer_keywords:
- FTP task [Integration Services]
ms.assetid: 41c3f2c4-ee04-460a-9822-bb9ae4036c2e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 63ec58c1bff9894d0aa73112686c4b1fe9421b98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568744"
---
# <a name="ftp-task"></a><span data-ttu-id="58d1e-102">Tarefa FTP</span><span class="sxs-lookup"><span data-stu-id="58d1e-102">FTP Task</span></span>
  <span data-ttu-id="58d1e-103">A tarefa FTP carrega e baixa arquivos de dados, bem como gerencia diretórios em servidores.</span><span class="sxs-lookup"><span data-stu-id="58d1e-103">The FTP task downloads and uploads data files and manages directories on servers.</span></span> <span data-ttu-id="58d1e-104">Por exemplo, um pacote pode baixar arquivos de dados de um servidor remoto ou de um local de Internet como parte de um fluxo de trabalho de pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58d1e-104">For example, a package can download data files from a remote server or an Internet location as part of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package workflow.</span></span> <span data-ttu-id="58d1e-105">Você pode usar a tarefa FTP para os seguintes propósitos:</span><span class="sxs-lookup"><span data-stu-id="58d1e-105">You can use the FTP task for the following purposes:</span></span>  
  
-   <span data-ttu-id="58d1e-106">Copiar diretórios e arquivos de dados de um diretório para outro, antes ou depois de mover dados, e aplicar transformações nos dados.</span><span class="sxs-lookup"><span data-stu-id="58d1e-106">Copying directories and data files from one directory to another, before or after moving data, and applying transformations to the data.</span></span>  
  
-   <span data-ttu-id="58d1e-107">Fazer logon em um local FTP de origem e copiar arquivos ou pacotes em um diretório de destino.</span><span class="sxs-lookup"><span data-stu-id="58d1e-107">Logging in to a source FTP location and copying files or packages to a destination directory.</span></span>  
  
-   <span data-ttu-id="58d1e-108">Baixar arquivos de um local FTP e aplicar transformações em dados de coluna antes de carregar os dados em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="58d1e-108">Downloading files from an FTP location and applying transformations to column data before loading the data into a database.</span></span>  
  
 <span data-ttu-id="58d1e-109">Em tempo de execução, a tarefa FTP é conectada a um servidor usando um gerenciador de conexões de FTP.</span><span class="sxs-lookup"><span data-stu-id="58d1e-109">At run time, the FTP task connects to a server by using an FTP connection manager.</span></span> <span data-ttu-id="58d1e-110">O gerenciador de conexões de FTP é configurado separadamente da tarefa FTP e, em seguida, é referido na tarefa FTP.</span><span class="sxs-lookup"><span data-stu-id="58d1e-110">The FTP connection manager is configured separately from the FTP task, and then is referenced in the FTP task.</span></span> <span data-ttu-id="58d1e-111">O gerenciador de conexões de FTP inclui as configurações do servidor, as credenciais para acessar o servidor FTP e as opções como o tempo limite e o número de tentativas para conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="58d1e-111">The FTP connection manager includes the server settings, the credentials for accessing the FTP server, and options such as the time-out and the number of retries for connecting to the server.</span></span> <span data-ttu-id="58d1e-112">Para obter mais informações, consulte [Gerenciador de Conexões de FTP](../connection-manager/ftp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="58d1e-112">For more information, see [FTP Connection Manager](../connection-manager/ftp-connection-manager.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="58d1e-113">O gerenciador de conexões de FTP dá suporte apenas para autenticação anônima e autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="58d1e-113">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="58d1e-114">Ele não suporta a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="58d1e-114">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="58d1e-115">Ao acessar um arquivo local ou um diretório local, a tarefa FTP usa um gerenciador de conexões de arquivos ou informações de caminho armazenadas em uma variável.</span><span class="sxs-lookup"><span data-stu-id="58d1e-115">When accessing a local file or a local directory, the FTP task uses a File connection manager or path information stored in a variable.</span></span> <span data-ttu-id="58d1e-116">Por outro lado, ao acessar um arquivo remoto ou um diretório remoto, a tarefa FTP usa um caminho especificado diretamente no servidor remoto, conforme especificado no gerenciador de conexões de FTP, ou as informações de caminho armazenadas em uma variável.</span><span class="sxs-lookup"><span data-stu-id="58d1e-116">In contrast, when accessing a remote file or a remote directory, the FTP task uses a directly specified path on the remote server, as specified in the FTP connection manager, or path information stored in a variable.</span></span> <span data-ttu-id="58d1e-117">Para obter mais informações, consulte [Gerenciador de Conexões de Arquivos](../connection-manager/file-connection-manager.md) e [Variáveis do Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="58d1e-117">For more information, see [File Connection Manager](../connection-manager/file-connection-manager.md) and [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="58d1e-118">Isso significa que a tarefa FTP pode receber vários arquivos e excluir diversos arquivos remotos, mas a tarefa só poderá enviar um arquivo e só poderá excluir um arquivo local se usar um gerenciador de conexões, porque um gerenciador de conexões de arquivos pode acessar só um arquivo.</span><span class="sxs-lookup"><span data-stu-id="58d1e-118">This means that the FTP task can receive multiple files and delete multiple remote files; but the task can send only one file and delete only one local file if it uses a connection manager, because a File connection manager can access only one file.</span></span> <span data-ttu-id="58d1e-119">Para acessar vários arquivos locais, a tarefa FTP deve usar uma variável para fornecer as informações de caminho.</span><span class="sxs-lookup"><span data-stu-id="58d1e-119">To access multiple local files, the FTP task must use a variable to provide the path information.</span></span> <span data-ttu-id="58d1e-120">Por exemplo, uma variável que contém “C:\Test\\*.txt” fornece um caminho que dá suporte à exclusão ou envio de todos os arquivos com uma extensão .txt no diretório Test.</span><span class="sxs-lookup"><span data-stu-id="58d1e-120">For example, a variable that contains "C:\Test\\*.txt" provides a path that supports deleting or sending all the files that have a .txt extension in the Test directory.</span></span>  
  
 <span data-ttu-id="58d1e-121">Para enviar vários arquivos e acessar diversos arquivos locais e diretórios, você também pode executar diversas vezes a tarefa FTP incluindo a tarefa em um Loop Foreach.</span><span class="sxs-lookup"><span data-stu-id="58d1e-121">To send multiple files and access multiple local files and directories, you can also execute the FTP task multiple times by including the task in a Foreach Loop.</span></span> <span data-ttu-id="58d1e-122">O Loop Foreach pode enumerar arquivos em um diretório usando o enumerador For Each File.</span><span class="sxs-lookup"><span data-stu-id="58d1e-122">The Foreach Loop can enumerate across files in a directory using the For Each File enumerator.</span></span> <span data-ttu-id="58d1e-123">Para obter mais informações, consulte [Contêiner Loop Foreach](foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="58d1e-123">For more information, see [Foreach Loop Container](foreach-loop-container.md).</span></span>  
  
 <span data-ttu-id="58d1e-124">A tarefa de FTP dá suporte para os caracteres curinga *?*</span><span class="sxs-lookup"><span data-stu-id="58d1e-124">The FTP task supports the *?*</span></span> <span data-ttu-id="58d1e-125">e *\** nos caminhos.</span><span class="sxs-lookup"><span data-stu-id="58d1e-125">and *\** wildcard characters in paths.</span></span> <span data-ttu-id="58d1e-126">Isso permite que a tarefa acesse vários arquivos.</span><span class="sxs-lookup"><span data-stu-id="58d1e-126">This lets the task access multiple files.</span></span> <span data-ttu-id="58d1e-127">Porém, você só pode usar caracteres curinga na parte do caminho que especifica o nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="58d1e-127">However, you can use wildcard characters only in the part of the path that specifies the file name.</span></span> <span data-ttu-id="58d1e-128">Por exemplo, C:\MyDirectory\\*.txt é um caminho válido, mas C:\\\*\MyText.txt não é.</span><span class="sxs-lookup"><span data-stu-id="58d1e-128">For example, C:\MyDirectory\\*.txt is a valid path, but C:\\\*\MyText.txt is not.</span></span>  
  
 <span data-ttu-id="58d1e-129">Os operações de FTP podem ser configuradas para interromper a tarefa Sistema de Arquivos quando a operação falha ou para transferir arquivos no modo ASCII.</span><span class="sxs-lookup"><span data-stu-id="58d1e-129">The FTP operations can be configured to stop the File System task when the operation fails, or to transfer files in ASCII mode.</span></span> <span data-ttu-id="58d1e-130">As operações que enviam e recebem cópias de arquivos podem ser configuradas para substituir arquivos de destino e diretórios.</span><span class="sxs-lookup"><span data-stu-id="58d1e-130">The operations that send and receive files copy can be configured to overwrite destination files and directories.</span></span>  
  
## <a name="predefined-ftp-operations"></a><span data-ttu-id="58d1e-131">Operações de FTP predefinidas</span><span class="sxs-lookup"><span data-stu-id="58d1e-131">Predefined FTP Operations</span></span>  
 <span data-ttu-id="58d1e-132">A tarefa FTP inclui um conjunto predefinido de operações.</span><span class="sxs-lookup"><span data-stu-id="58d1e-132">The FTP task includes a predefined set of operations.</span></span> <span data-ttu-id="58d1e-133">A tabela a seguir descreve essas operações.</span><span class="sxs-lookup"><span data-stu-id="58d1e-133">The following table describes these operations.</span></span>  
  
|<span data-ttu-id="58d1e-134">Operação</span><span class="sxs-lookup"><span data-stu-id="58d1e-134">Operation</span></span>|<span data-ttu-id="58d1e-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="58d1e-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58d1e-136">Enviar arquivos</span><span class="sxs-lookup"><span data-stu-id="58d1e-136">Send files</span></span>|<span data-ttu-id="58d1e-137">Envia um arquivo do computador local para o servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="58d1e-137">Sends a file from the local computer to the FTP server.</span></span>|  
|<span data-ttu-id="58d1e-138">Receber arquivos</span><span class="sxs-lookup"><span data-stu-id="58d1e-138">Receive files</span></span>|<span data-ttu-id="58d1e-139">Salva um arquivo do servidor FTP no computador local.</span><span class="sxs-lookup"><span data-stu-id="58d1e-139">Saves a file from the FTP server to the local computer.</span></span>|  
|<span data-ttu-id="58d1e-140">Criar diretório local</span><span class="sxs-lookup"><span data-stu-id="58d1e-140">Create local directory</span></span>|<span data-ttu-id="58d1e-141">Cria uma pasta no computador local.</span><span class="sxs-lookup"><span data-stu-id="58d1e-141">Creates a folder on the local computer.</span></span>|  
|<span data-ttu-id="58d1e-142">Criar diretório remoto</span><span class="sxs-lookup"><span data-stu-id="58d1e-142">Create remote directory</span></span>|<span data-ttu-id="58d1e-143">Cria uma pasta no servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="58d1e-143">Creates a folder on the FTP server.</span></span>|  
|<span data-ttu-id="58d1e-144">Remover diretório local</span><span class="sxs-lookup"><span data-stu-id="58d1e-144">Remove local directory</span></span>|<span data-ttu-id="58d1e-145">Exclui uma pasta no computador local.</span><span class="sxs-lookup"><span data-stu-id="58d1e-145">Deletes a folder on the local computer.</span></span>|  
|<span data-ttu-id="58d1e-146">Remover diretório remoto</span><span class="sxs-lookup"><span data-stu-id="58d1e-146">Remove remote directory</span></span>|<span data-ttu-id="58d1e-147">Exclui uma pasta no servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="58d1e-147">Deletes a folder on the FTP server.</span></span>|  
|<span data-ttu-id="58d1e-148">Excluir arquivos locais</span><span class="sxs-lookup"><span data-stu-id="58d1e-148">Delete local files</span></span>|<span data-ttu-id="58d1e-149">Exclui um arquivo no computador local.</span><span class="sxs-lookup"><span data-stu-id="58d1e-149">Deletes a file on the local computer.</span></span>|  
|<span data-ttu-id="58d1e-150">Excluir arquivos remotos</span><span class="sxs-lookup"><span data-stu-id="58d1e-150">Delete remote files</span></span>|<span data-ttu-id="58d1e-151">Exclui um arquivo no servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="58d1e-151">Deletes a file on the FTP server.</span></span>|  
  
## <a name="custom-log-entries-available-on-the-ftp-task"></a><span data-ttu-id="58d1e-152">Entradas de log personalizadas disponíveis na tarefa FTP</span><span class="sxs-lookup"><span data-stu-id="58d1e-152">Custom Log Entries Available on the FTP Task</span></span>  
 <span data-ttu-id="58d1e-153">A tabela a seguir relaciona as entradas de log personalizadas da tarefa FTP.</span><span class="sxs-lookup"><span data-stu-id="58d1e-153">The following table lists the custom log entries for the FTP task.</span></span> <span data-ttu-id="58d1e-154">Para obter mais informações, consulte [Log do SSIS &#40;Integration Services&#41;](../performance/integration-services-ssis-logging.md) e [Mensagens personalizadas para log](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="58d1e-154">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="58d1e-155">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="58d1e-155">Log entry</span></span>|<span data-ttu-id="58d1e-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="58d1e-156">Description</span></span>|  
|---------------|-----------------|  
|`FTPConnectingToServer`|<span data-ttu-id="58d1e-157">Indica que a tarefa iniciou uma conexão com o servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="58d1e-157">Indicates that the task initiated a connection to the FTP server.</span></span>|  
|`FTPOperation`|<span data-ttu-id="58d1e-158">Informa o início e o tipo de operação de FTP que a tarefa executa.</span><span class="sxs-lookup"><span data-stu-id="58d1e-158">Reports the beginning of and the type of FTP operation that the task performs.</span></span>|  
  
## <a name="related-tasks"></a><span data-ttu-id="58d1e-159">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="58d1e-159">Related Tasks</span></span>  
 <span data-ttu-id="58d1e-160">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="58d1e-160">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="58d1e-161">Para obter informações sobre como definir essas propriedades no Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consulte [Definir as propriedades de uma tarefa ou um contêiner](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="58d1e-161">For information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
 <span data-ttu-id="58d1e-162">Para obter mais informações sobre como definir essas propriedades de forma programática, consulte <xref:Microsoft.SqlServer.Dts.Tasks.FtpTask.FtpTask>.</span><span class="sxs-lookup"><span data-stu-id="58d1e-162">For more information about programmatically setting these properties, see <xref:Microsoft.SqlServer.Dts.Tasks.FtpTask.FtpTask>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58d1e-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="58d1e-163">See Also</span></span>  
 <span data-ttu-id="58d1e-164">[Editor da tarefa FTP &#40;página Geral&#41;](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="58d1e-164">[FTP Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="58d1e-165">[Editor da tarefa FTP &#40;página transferência de arquivos&#41;](../ftp-task-editor-file-transfer-page.md) </span><span class="sxs-lookup"><span data-stu-id="58d1e-165">[FTP Task Editor &#40;File Transfer Page&#41;](../ftp-task-editor-file-transfer-page.md) </span></span>  
 <span data-ttu-id="58d1e-166">[Tarefas do Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="58d1e-166">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="58d1e-167">Fluxo de Controle</span><span class="sxs-lookup"><span data-stu-id="58d1e-167">Control Flow</span></span>](control-flow.md)  
  
  