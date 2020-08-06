---
title: Tarefa Fila de Mensagens | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.messagequeuetask.f1
helpviewer_keywords:
- Message Queue task [Integration Services]
- receiving messages
- messages [Integration Services]
- sending messages
ms.assetid: ae1d8fad-6649-4e93-b589-14a32d07da33
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c9af2ac69fbee07fdc58faf4b63cddc08317e8ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685234"
---
# <a name="message-queue-task"></a><span data-ttu-id="f6e47-102">Message Queue Task</span><span class="sxs-lookup"><span data-stu-id="f6e47-102">Message Queue Task</span></span>
  <span data-ttu-id="f6e47-103">A Tarefa Fila de Mensagens permite usar o serviço de Enfileiramento de Mensagens (também conhecido como MSMQ) para enviar e receber mensagens entre pacotes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ou enviar mensagens a uma fila de aplicativos processada por um aplicativo personalizado.</span><span class="sxs-lookup"><span data-stu-id="f6e47-103">The Message Queue task allows you to use Message Queuing (also known as MSMQ) to send and receive messages between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, or to send messages to an application queue that is processed by a custom application.</span></span> <span data-ttu-id="f6e47-104">Essas mensagens podem adotar a forma de texto simples, arquivos ou variáveis e seus valores.</span><span class="sxs-lookup"><span data-stu-id="f6e47-104">These messages can take the form of simple text, files, or variables and their values.</span></span>  
  
 <span data-ttu-id="f6e47-105">Usando a tarefa Fila de Mensagens, você pode coordenar operações em toda sua empresa.</span><span class="sxs-lookup"><span data-stu-id="f6e47-105">By using the Message Queue task, you can coordinate operations throughout your enterprise.</span></span> <span data-ttu-id="f6e47-106">As mensagens podem ser enfileiradas e entregues mais tarde se o destino estiver indisponível ou ocupado; por exemplo, a tarefa pode enfileirar mensagens para o laptop offline de representantes de vendas que recebem suas mensagens quando se conectarem à rede.</span><span class="sxs-lookup"><span data-stu-id="f6e47-106">Messages can be queued and delivered later if the destination is unavailable or busy; for example, the task can queue messages for the offline laptop computer of sales representatives, who receive their messages when they connect to the network.</span></span> <span data-ttu-id="f6e47-107">Você pode usar a tarefa Fila de Mensagens para os seguintes propósitos:</span><span class="sxs-lookup"><span data-stu-id="f6e47-107">You can use the Message Queue task for the following purposes:</span></span>  
  
-   <span data-ttu-id="f6e47-108">Atrasar a execução da tarefa até que outros pacotes façam check-in.</span><span class="sxs-lookup"><span data-stu-id="f6e47-108">Delaying task execution until other packages check in.</span></span> <span data-ttu-id="f6e47-109">Por exemplo, depois de manutenção noturna em cada um de seus sites de varejo, uma tarefa Fila de Mensagens envia uma mensagem a seu computador corporativo.</span><span class="sxs-lookup"><span data-stu-id="f6e47-109">For example, after nightly maintenance at each of your retail sites, a Message Queue task sends a message to your corporate computer.</span></span> <span data-ttu-id="f6e47-110">Um pacote que é executado no computador corporativo contém tarefas de Fila de Mensagens, cada uma esperando por uma mensagem de um site de varejo específico.</span><span class="sxs-lookup"><span data-stu-id="f6e47-110">A package running on the corporate computer contains Message Queue tasks, each waiting for a message from a particular retail site.</span></span> <span data-ttu-id="f6e47-111">Quando uma mensagem de um site chega, uma tarefa carrega dados daquele site.</span><span class="sxs-lookup"><span data-stu-id="f6e47-111">When a message from a site arrives, a task uploads data from that site.</span></span> <span data-ttu-id="f6e47-112">Depois que todos os sites fizerem check-in, o pacote computa os totais dos resumos.</span><span class="sxs-lookup"><span data-stu-id="f6e47-112">After all the sites have checked in, the package computes summary totals.</span></span>  
  
-   <span data-ttu-id="f6e47-113">Enviando arquivos de dados ao computador que os processa.</span><span class="sxs-lookup"><span data-stu-id="f6e47-113">Sending data files to the computer that processes them.</span></span> <span data-ttu-id="f6e47-114">Por exemplo, a saída da caixa registradora de um restaurante pode ser enviada em uma mensagem de arquivo de dados ao sistema de folha de pagamento corporativo, onde os dados sobre as gorjetas de cada garçom são extraídos.</span><span class="sxs-lookup"><span data-stu-id="f6e47-114">For example, the output from a restaurant cash register can be sent in a data file message to the corporate payroll system, where data about each waiter's tips is extracted.</span></span>  
  
-   <span data-ttu-id="f6e47-115">Distribuindo arquivos para toda a sua empresa.</span><span class="sxs-lookup"><span data-stu-id="f6e47-115">Distributing files throughout your enterprise.</span></span> <span data-ttu-id="f6e47-116">Por exemplo, um pacote pode usar uma tarefa de Fila de Mensagens para enviar um arquivo de pacote a outro computador.</span><span class="sxs-lookup"><span data-stu-id="f6e47-116">For example, a package can use a Message Queue task to send a package file to another computer.</span></span> <span data-ttu-id="f6e47-117">Um pacote que é executado no computador de destino usa então uma tarefa de Fila de Mensagens para recuperar e salvar o pacote localmente.</span><span class="sxs-lookup"><span data-stu-id="f6e47-117">A package running on the destination computer then uses a Message Queue task to retrieve and save the package locally.</span></span>  
  
 <span data-ttu-id="f6e47-118">Quando estiver enviando ou recebendo mensagens, a tarefa Fila de Mensagens usa um dos quatro tipos de mensagem: arquivo de dados, cadeia, mensagem de cadeia a variável, ou variável.</span><span class="sxs-lookup"><span data-stu-id="f6e47-118">When sending or receiving messages, the Message Queue task uses one of four message types: data file, string, string message to variable, or variable.</span></span> <span data-ttu-id="f6e47-119">O tipo de mensagem “mensagem de cadeia de caracteres para variável” só pode ser usada ao receber mensagens.</span><span class="sxs-lookup"><span data-stu-id="f6e47-119">The string message to variable message type can be used only when receiving messages.</span></span>  
  
 <span data-ttu-id="f6e47-120">A tarefa usa um gerenciador de conexões MSMQ para se conectar à uma fila de mensagens.</span><span class="sxs-lookup"><span data-stu-id="f6e47-120">The task uses an MSMQ connection manager to connect to a message queue.</span></span> <span data-ttu-id="f6e47-121">Para obter mais informações, consulte [Gerenciador de Conexão do SMO](../connection-manager/msmq-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f6e47-121">For more information, see [MSMQ Connection Manager](../connection-manager/msmq-connection-manager.md).</span></span> <span data-ttu-id="f6e47-122">Para obter mais informações sobre o serviço de enfileiramento de mensagens, consulte a [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span><span class="sxs-lookup"><span data-stu-id="f6e47-122">For more information about Message Queuing, see the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span></span>  
  
 <span data-ttu-id="f6e47-123">A tarefa Fila de Mensagens requer que o serviço [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] esteja instalado.</span><span class="sxs-lookup"><span data-stu-id="f6e47-123">The Message Queue task requires that the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service be installed.</span></span> <span data-ttu-id="f6e47-124">Alguns componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que você pode selecionar para instalação na página **Componentes a Serem Instalados** ou na página **Seleção de Recursos** do Assistente de Instalação [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalam um subconjunto parcial de componentes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6e47-124">Some [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components that you may select for installation on the **Components to Install** page or the **Feature Selection** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard install a partial subset of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components.</span></span> <span data-ttu-id="f6e47-125">Esses componentes são úteis para tarefas específicas, mas a funcionalidade do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] será limitada.</span><span class="sxs-lookup"><span data-stu-id="f6e47-125">These components are useful for specific tasks, but the functionality of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] will be limited.</span></span> <span data-ttu-id="f6e47-126">Por exemplo, a opção [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] instala os componentes [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] necessários para projetar um pacote, mas o serviço [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] não é instalado e, portanto, a tarefa Fila de Mensagens não é funcional.</span><span class="sxs-lookup"><span data-stu-id="f6e47-126">For example, the [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] option installs the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components required to design a package, but the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is not installed, and therefore the Message Queue task is not functional.</span></span> <span data-ttu-id="f6e47-127">Para assegurar uma instalação completa de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], você deve selecionar [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] na página **Componentes a Serem Instalados** .</span><span class="sxs-lookup"><span data-stu-id="f6e47-127">To ensure a complete installation of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you must select [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] on the **Components to Install** page.</span></span> <span data-ttu-id="f6e47-128">Para obter mais informações sobre como instalar e executar a tarefa Fila de Mensagens, consulte [Instalar o Integration Services](../install-windows/install-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="f6e47-128">For more information about installing and running the Message Queue task, see [Install Integration Services](../install-windows/install-integration-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6e47-129">A tarefa Fila de Mensagens não obedece ao Padrão Federal de Processamento de Informações (FIPS) 140-2 quando o sistema operacional do computador é configurado em modo FIPS e a tarefa usa criptografia.</span><span class="sxs-lookup"><span data-stu-id="f6e47-129">The Message Queue task fails to comply with Federal Information Processing Standard (FIPS) 140-2 when the computer's operating system is configured in FIPS mode and the task uses encryption.</span></span> <span data-ttu-id="f6e47-130">Se a tarefa Fila de Mensagens não usar criptografia, a tarefa poderá ser executada com êxito.</span><span class="sxs-lookup"><span data-stu-id="f6e47-130">If the Message Queue task does not use encryption, the task can run successfully.</span></span>  
  
## <a name="message-types"></a><span data-ttu-id="f6e47-131">Tipos de mensagem</span><span class="sxs-lookup"><span data-stu-id="f6e47-131">Message Types</span></span>  
 <span data-ttu-id="f6e47-132">Você pode configurar os tipos de mensagem que a tarefa Fila de Mensagens oferece dos seguintes modos:</span><span class="sxs-lookup"><span data-stu-id="f6e47-132">You can configure the message types that the Message Queue task provides in the following ways:</span></span>  
  
-   <span data-ttu-id="f6e47-133">A mensagem `Data file` especifica que um arquivo contém a mensagem.</span><span class="sxs-lookup"><span data-stu-id="f6e47-133">`Data file` message specifies that a file contains the message.</span></span> <span data-ttu-id="f6e47-134">Ao receber mensagens, você pode configurar a tarefa para gravar o arquivo, pode substituir um arquivo existente e pode especificar o pacote do qual a tarefa pode receber mensagens.</span><span class="sxs-lookup"><span data-stu-id="f6e47-134">When receiving messages, you can configure the task to save the file, overwrite an existing file, and specify the package from which the task can receive messages.</span></span>  
  
-   <span data-ttu-id="f6e47-135">A mensagem `String` especifica a mensagem como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f6e47-135">`String` message specifies the message as a string.</span></span> <span data-ttu-id="f6e47-136">Ao receber mensagens, você pode configurar a tarefa para comparar a cadeia de caracteres recebida com uma cadeia de caracteres definida pelo usuário e entrar em ação dependendo da comparação.</span><span class="sxs-lookup"><span data-stu-id="f6e47-136">When receiving messages, you can configure the task to compare the received string with a user-defined string and take action depending on the comparison.</span></span> <span data-ttu-id="f6e47-137">A comparação de cadeias de caracteres pode ser exata, diferenciar maiúsculas e minúsculas ou não diferenciar maiúsculas e minúsculas, ou usar uma subcadeia.</span><span class="sxs-lookup"><span data-stu-id="f6e47-137">String comparison can be exact, case-sensitive or case-insensitive, or use a substring.</span></span>  
  
-   <span data-ttu-id="f6e47-138">`String message to variable` especifica a mensagem de fonte como uma cadeia de caracteres que é enviada a uma variável de destino.</span><span class="sxs-lookup"><span data-stu-id="f6e47-138">`String message to variable` specifies the source message as a string that is sent to a destination variable.</span></span> <span data-ttu-id="f6e47-139">Você pode configurar a tarefa para comparar a cadeia de caracteres recebida com uma cadeia de caracteres definida pelo usuário usando uma comparação exata, que não pode diferenciar maiúsculas e minúsculas ou subcadeia.</span><span class="sxs-lookup"><span data-stu-id="f6e47-139">You can configure the task to compare the received string with a user-defined string using an exact, case-insensitive, or substring comparison.</span></span> <span data-ttu-id="f6e47-140">Esse tipo de mensagem só está disponível quando a tarefa estiver recebendo mensagens.</span><span class="sxs-lookup"><span data-stu-id="f6e47-140">This message type is available only when the task is receiving messages.</span></span>  
  
-   <span data-ttu-id="f6e47-141">`Variable` especifica que a mensagem contém uma ou mais variáveis.</span><span class="sxs-lookup"><span data-stu-id="f6e47-141">`Variable` specifies that the message contains one or more variables.</span></span> <span data-ttu-id="f6e47-142">Você pode configurar a tarefa para especificar os nomes das variáveis incluídas na mensagem.</span><span class="sxs-lookup"><span data-stu-id="f6e47-142">You can configure the task to specify the names of the variables included in the message.</span></span> <span data-ttu-id="f6e47-143">Ao receber mensagens, você pode configurar a tarefa para especificar o pacote do qual ela pode receber mensagens e a variável que será o destino da mensagem.</span><span class="sxs-lookup"><span data-stu-id="f6e47-143">When receiving messages, you can configure the task to specify both the package from which it can receive messages and the variable that is the destination of the message.</span></span>  
  
## <a name="sending-messages"></a><span data-ttu-id="f6e47-144">enviando mensagens</span><span class="sxs-lookup"><span data-stu-id="f6e47-144">Sending Messages</span></span>  
 <span data-ttu-id="f6e47-145">Ao configurar a tarefa Fila de Mensagens para enviar mensagens, você pode usar um dos algoritmos de criptografia que são atualmente suportados pela tecnologia de Serviço de enfileiramento de mensagens, RC2 e RC4, para criptografar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="f6e47-145">When configuring the Message Queue task to send messages, you can use one of the encryption algorithms that are currently supported by the Message Queuing technology, RC2 and RC4, to encrypt the message.</span></span> <span data-ttu-id="f6e47-146">Ambos esses algoritmos de criptografia são agora considerados criptograficamente fracos comparados a algoritmos mais novos que a tecnologia de Serviço de enfileiramento de mensagens ainda não aceita.</span><span class="sxs-lookup"><span data-stu-id="f6e47-146">Both of these encryption algorithms are now considered cryptographically weak compared to newer algorithms, which Message Queuing technology do not yet support.</span></span> <span data-ttu-id="f6e47-147">Então, você deve considerar cuidadosamente suas necessidades de criptografia ao enviar mensagens que usam a tarefa Fila de Mensagens.</span><span class="sxs-lookup"><span data-stu-id="f6e47-147">Therefore, you should consider your cryptography needs carefully when sending messages using the Message Queue task.</span></span>  
  
## <a name="receiving-messages"></a><span data-ttu-id="f6e47-148">recebendo mensagens</span><span class="sxs-lookup"><span data-stu-id="f6e47-148">Receiving Messages</span></span>  
 <span data-ttu-id="f6e47-149">Ao receber mensagens, a tarefa Fila de Mensagens pode ser configurada dos seguintes modos:</span><span class="sxs-lookup"><span data-stu-id="f6e47-149">When receiving messages, the Message Queue task can be configured in the following ways:</span></span>  
  
-   <span data-ttu-id="f6e47-150">Ignorar a mensagem ou remover a mensagem da fila.</span><span class="sxs-lookup"><span data-stu-id="f6e47-150">Bypassing the message, or removing the message from the queue.</span></span>  
  
-   <span data-ttu-id="f6e47-151">Especificar uma expiração.</span><span class="sxs-lookup"><span data-stu-id="f6e47-151">Specifying a time-out.</span></span>  
  
-   <span data-ttu-id="f6e47-152">Falhar, se acontecer uma expiração.</span><span class="sxs-lookup"><span data-stu-id="f6e47-152">Failing if a time-out occurs.</span></span>  
  
-   <span data-ttu-id="f6e47-153">Substituir um arquivo existente, se a mensagem for armazenada em um `Data file`.</span><span class="sxs-lookup"><span data-stu-id="f6e47-153">Overwriting an existing file, if the message is stored in a `Data file`.</span></span>  
  
-   <span data-ttu-id="f6e47-154">Gravar o arquivo de mensagem com um nome de arquivo diferente, se a mensagem usar o tipo `Data file message`.</span><span class="sxs-lookup"><span data-stu-id="f6e47-154">Saving the message file to a different file name, if the message uses the `Data file message` type.</span></span>  
  
## <a name="custom-logging-messages-available-on-the-message-queue-task"></a><span data-ttu-id="f6e47-155">Mensagens de registro personalizadas disponíveis na tarefa Fila de Mensagens</span><span class="sxs-lookup"><span data-stu-id="f6e47-155">Custom Logging Messages Available on the Message Queue Task</span></span>  
 <span data-ttu-id="f6e47-156">A tabela a seguir relaciona as entradas de log personalizadas para a tarefa Fila de Mensagens.</span><span class="sxs-lookup"><span data-stu-id="f6e47-156">The following table lists the custom log entries for the Message Queue task.</span></span> <span data-ttu-id="f6e47-157">Para obter mais informações, consulte [Log do SSIS &#40;Integration Services&#41;](../performance/integration-services-ssis-logging.md) e [Mensagens personalizadas para log](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="f6e47-157">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="f6e47-158">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="f6e47-158">Log entry</span></span>|<span data-ttu-id="f6e47-159">Descrição</span><span class="sxs-lookup"><span data-stu-id="f6e47-159">Description</span></span>|  
|---------------|-----------------|  
|`MSMQAfterOpen`|<span data-ttu-id="f6e47-160">Indica que a tarefa finalizou a abertura da fila de mensagens.</span><span class="sxs-lookup"><span data-stu-id="f6e47-160">Indicates that the task finished opening the message queue.</span></span>|  
|`MSMQBeforeOpen`|<span data-ttu-id="f6e47-161">Indica que a tarefa começou a abrir a fila de mensagens.</span><span class="sxs-lookup"><span data-stu-id="f6e47-161">Indicates that the task began to open the message queue.</span></span>|  
|`MSMQBeginReceive`|<span data-ttu-id="f6e47-162">Indica que a tarefa começou a receber uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="f6e47-162">Indicates that the task began to receive a message.</span></span>|  
|`MSMQBeginSend`|<span data-ttu-id="f6e47-163">Indica que a tarefa começou a enviar uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="f6e47-163">Indicates that the task began to send a message.</span></span>|  
|`MSMQEndReceive`|<span data-ttu-id="f6e47-164">Indica que a tarefa terminou de receber uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="f6e47-164">Indicates that the task finished receiving a message.</span></span>|  
|`MSMQEndSend`|<span data-ttu-id="f6e47-165">Indica que a tarefa terminou de enviar uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="f6e47-165">Indicates that the task finished sending a message.</span></span>|  
|`MSMQTaskInfo`|<span data-ttu-id="f6e47-166">Fornece informações descritivas sobre a tarefa.</span><span class="sxs-lookup"><span data-stu-id="f6e47-166">Provides descriptive information about the task.</span></span>|  
|`MSMQTaskTimeOut`|<span data-ttu-id="f6e47-167">Indica que o tempo limite da tarefa foi esgotado.</span><span class="sxs-lookup"><span data-stu-id="f6e47-167">Indicates that the task timed out.</span></span>|  
  
## <a name="configuration-of-the-message-queue-task"></a><span data-ttu-id="f6e47-168">Configuração da tarefa Fila de Mensagens</span><span class="sxs-lookup"><span data-stu-id="f6e47-168">Configuration of the Message Queue Task</span></span>  
 <span data-ttu-id="f6e47-169">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="f6e47-169">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span> <span data-ttu-id="f6e47-170">Para obter informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique em um dos tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="f6e47-170">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f6e47-171">Editor da Tarefa Fila de Mensagens &#40;Página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e47-171">Message Queue Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="f6e47-172">Editor da Tarefa Fila de Mensagens &#40;Página Receber&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e47-172">Message Queue Task Editor &#40;Receive Page&#41;</span></span>](../message-queue-task-editor-receive-page.md)  
  
-   [<span data-ttu-id="f6e47-173">Editor da Tarefa Fila de Mensagens &#40;Página Enviar&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e47-173">Message Queue Task Editor &#40;Send Page&#41;</span></span>](../message-queue-task-editor-send-page.md)  
  
-   [<span data-ttu-id="f6e47-174">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="f6e47-174">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="f6e47-175">Para obter mais informações sobre como definir essas propriedades programaticamente, consulte a documentação da classe **Microsoft.SqlServer.Dts.Tasks.MessageQueueTask.MessageQueueTask** no Guia do Desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="f6e47-175">For information about programmatically setting these properties, see the documentation for the **Microsoft.SqlServer.Dts.Tasks.MessageQueueTask.MessageQueueTask** class in the Developer Guide.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f6e47-176">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f6e47-176">Related Tasks</span></span>  
 <span data-ttu-id="f6e47-177">Para obter mais informações sobre como definir essas propriedades no Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consulte [Definir as propriedades de uma tarefa ou um contêiner](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="f6e47-177">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6e47-178">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f6e47-178">See Also</span></span>  
 <span data-ttu-id="f6e47-179">[Tarefas do Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="f6e47-179">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="f6e47-180">Fluxo de Controle</span><span class="sxs-lookup"><span data-stu-id="f6e47-180">Control Flow</span></span>](control-flow.md)  
  
  