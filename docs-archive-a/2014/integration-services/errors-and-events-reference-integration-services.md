---
title: Referência de erros e eventos (Integration Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, events
- events [Integration Services]
- errors [Integration Services]
- Integration Services, errors
ms.assetid: cf4f0f14-8087-42d7-9b67-e4929228abd6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c434e68aa676508d8a50d89bc18b79b6167b48ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574816"
---
# <a name="errors-and-events-reference-integration-services"></a><span data-ttu-id="b75d7-102">Referência de erros e eventos (Integration Services)</span><span class="sxs-lookup"><span data-stu-id="b75d7-102">Errors and Events Reference (Integration Services)</span></span>
  <span data-ttu-id="b75d7-103">Esta seção da documentação contém informações sobre vários erros e eventos relacionados ao [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b75d7-103">This section of the documentation contains information about several errors and events related to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="b75d7-104">Causa e informações de resolução estão incluídas para mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="b75d7-104">Cause and resolution information is included for error messages.</span></span>  
  
 <span data-ttu-id="b75d7-105">Para obter mais informações sobre mensagens de erro do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , incluindo uma lista da maior parte dos erros do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e suas descrições, consulte [Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md).</span><span class="sxs-lookup"><span data-stu-id="b75d7-105">For more information about [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] error messages, including a list of most [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] errors and their descriptions, see [Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md).</span></span> <span data-ttu-id="b75d7-106">No entanto a lista atual não inclui informações de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="b75d7-106">However, the list currently does not include troubleshooting information.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b75d7-107">Muitas das mensagens de erro que você pode ver quando está trabalhando com o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] originam-se de outros componentes.</span><span class="sxs-lookup"><span data-stu-id="b75d7-107">Many of the error messages that you may see when you are working with [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] come from other components.</span></span> <span data-ttu-id="b75d7-108">Entre eles, provedores OLE DB, outros componentes de banco de dados, como o [!INCLUDE[ssDE](../includes/ssde-md.md)] e [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , ou outros serviços ou componentes, como o sistema de arquivos, servidor SMTP, MSMQ (serviço de enfileiramento de mensagens) e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="b75d7-108">These may include OLE DB providers, other database components such as the [!INCLUDE[ssDE](../includes/ssde-md.md)] and [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , or other services or components such as the file system, the SMTP server, or Microsoft Message Queueing.</span></span> <span data-ttu-id="b75d7-109">Para obter informações sobre essas mensagens externas de erro, consulte a documentação específica do componente.</span><span class="sxs-lookup"><span data-stu-id="b75d7-109">To find information about these external error messages, see the documentation specific to the component.</span></span>  
  
## <a name="error-messages"></a><span data-ttu-id="b75d7-110">Mensagens de erro</span><span class="sxs-lookup"><span data-stu-id="b75d7-110">Error Messages</span></span>  
  
|<span data-ttu-id="b75d7-111">Nome simbólico de erro</span><span class="sxs-lookup"><span data-stu-id="b75d7-111">Symbolic name of error</span></span>|<span data-ttu-id="b75d7-112">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="b75d7-112">Description</span></span>|  
|----------------------------|-----------------|  
|<span data-ttu-id="b75d7-113">DTS_E_CACHELOADEDFROMFILE</span><span class="sxs-lookup"><span data-stu-id="b75d7-113">DTS_E_CACHELOADEDFROMFILE</span></span>|<span data-ttu-id="b75d7-114">Indica que o pacote não pode ser executado porque uma Transformação Cache está tentando gravar dados no cache na memória.</span><span class="sxs-lookup"><span data-stu-id="b75d7-114">Indicates that the package cannot run because a Cache Transform transformation is trying to write data to the in-memory cache.</span></span> <span data-ttu-id="b75d7-115">No entanto, um gerenciador de conexões de Cache já carregou um arquivo de cache no cache na memória.</span><span class="sxs-lookup"><span data-stu-id="b75d7-115">However, a Cache connection manager has already loaded a cache file into the in-memory cache.</span></span>|  
|<span data-ttu-id="b75d7-116">DTS_E_CANNOTACQUIRECONNECTIONFROMCONNECTIONMANAGER</span><span class="sxs-lookup"><span data-stu-id="b75d7-116">DTS_E_CANNOTACQUIRECONNECTIONFROMCONNECTIONMANAGER</span></span>|<span data-ttu-id="b75d7-117">Indica que o pacote não pode ser executado porque ocorreu uma falha na conexão especificada.</span><span class="sxs-lookup"><span data-stu-id="b75d7-117">Indicates that the package cannot run because a specified connection failed.</span></span>|  
|<span data-ttu-id="b75d7-118">DTS_E_CANNOTCONVERTBETWEENUNICODEANDNONUNICODESTRINGCOLUMN</span><span class="sxs-lookup"><span data-stu-id="b75d7-118">DTS_E_CANNOTCONVERTBETWEENUNICODEANDNONUNICODESTRINGCOLUMN</span></span>|<span data-ttu-id="b75d7-119">Indica que um componente de fluxo de dados está tentando passar dados de cadeia de caracteres Unicode para outro componente que espera dados de cadeia de caracteres não Unicode na coluna correspondente ou vice-versa.</span><span class="sxs-lookup"><span data-stu-id="b75d7-119">Indicates that a data flow component is trying to pass Unicode string data to another component that expects non-Unicode string data in the corresponding column, or vice versa.</span></span>|  
|<span data-ttu-id="b75d7-120">DTS_E_CANNOTCONVERTBETWEENUNICODEANDNONUNICODESTRINGCOLUMNS</span><span class="sxs-lookup"><span data-stu-id="b75d7-120">DTS_E_CANNOTCONVERTBETWEENUNICODEANDNONUNICODESTRINGCOLUMNS</span></span>|<span data-ttu-id="b75d7-121">Indica que um componente de fluxo de dados está tentando passar dados de cadeia de caracteres Unicode para outro componente que espera dados de cadeia de caracteres não Unicode na coluna correspondente ou vice-versa.</span><span class="sxs-lookup"><span data-stu-id="b75d7-121">Indicates that a data flow component is trying to pass Unicode string data to another component that expects non-Unicode string data in the corresponding column, or vice versa.</span></span>|  
|<span data-ttu-id="b75d7-122">DTS_E_CANTINSERTCOLUMNTYPE</span><span class="sxs-lookup"><span data-stu-id="b75d7-122">DTS_E_CANTINSERTCOLUMNTYPE</span></span>|<span data-ttu-id="b75d7-123">Indica que a coluna não pode ser adicionada à tabela de banco de dados porque a conversão entre o tipo de dados de coluna e o tipo de dados de coluna de banco de dados do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="b75d7-123">Indicates that the column cannot be added to the database table because the conversion between the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] column data type and the database column data type is not supported.</span></span>|  
|<span data-ttu-id="b75d7-124">DTS_E_CONNECTIONNOTFOUND</span><span class="sxs-lookup"><span data-stu-id="b75d7-124">DTS_E_CONNECTIONNOTFOUND</span></span>|<span data-ttu-id="b75d7-125">Indica que o pacote não pode ser executado porque o gerenciador de conexões especificado não pode ser localizado.</span><span class="sxs-lookup"><span data-stu-id="b75d7-125">Indicates that the package cannot run because the specified connection manager cannot be found.</span></span>|  
|<span data-ttu-id="b75d7-126">DTS_E_CONNECTIONREQUIREDFORMETADATA</span><span class="sxs-lookup"><span data-stu-id="b75d7-126">DTS_E_CONNECTIONREQUIREDFORMETADATA</span></span>|<span data-ttu-id="b75d7-127">Indica que o Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] deve conectar-se a uma fonte de dados para recuperar metadados novos ou atualizados para uma origem ou destino e que não é possível conectar-se à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b75d7-127">Indicates that [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer must connect to a data source to retrieve new or updated metadata for a source or destination, and that it is unable to connect to the data source.</span></span>|  
|<span data-ttu-id="b75d7-128">DTS_E_MULTIPLECACHEWRITES</span><span class="sxs-lookup"><span data-stu-id="b75d7-128">DTS_E_MULTIPLECACHEWRITES</span></span>|<span data-ttu-id="b75d7-129">Indica que o pacote não pode ser executado porque uma Transformação Cache está tentando gravar dados no cache na memória.</span><span class="sxs-lookup"><span data-stu-id="b75d7-129">Indicates that the package cannot run because a Cache Transform transformation is trying to write data to the in-memory cache.</span></span> <span data-ttu-id="b75d7-130">No entanto outra Transformação Cache já foi gravada no cache na memória.</span><span class="sxs-lookup"><span data-stu-id="b75d7-130">However, another Cache Transform transformation has already written to the in-memory cache.</span></span>|  
|<span data-ttu-id="b75d7-131">DTS_E_PRODUCTLEVELTOLOW</span><span class="sxs-lookup"><span data-stu-id="b75d7-131">DTS_E_PRODUCTLEVELTOLOW</span></span>|<span data-ttu-id="b75d7-132">Indica que o pacote não pode ser executado porque a versão apropriada do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] não foi instalada.</span><span class="sxs-lookup"><span data-stu-id="b75d7-132">Indicates that the package cannot run because the appropriate version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is not installed.</span></span>|  
|<span data-ttu-id="b75d7-133">DTS_E_READNOTFILLEDCACHE</span><span class="sxs-lookup"><span data-stu-id="b75d7-133">DTS_E_READNOTFILLEDCACHE</span></span>|<span data-ttu-id="b75d7-134">Indica que uma transformação Pesquisa está tentando ler dados do cache na memória ao mesmo tempo que uma transformação Cache está gravando dados no cache.</span><span class="sxs-lookup"><span data-stu-id="b75d7-134">Indicates that a Lookup transformation is trying to read data from the in-memory cache at the same time that a Cache Transform transformation is writing data to the cache.</span></span>|  
|<span data-ttu-id="b75d7-135">DTS_E_UNPROTECTXMLFAILED</span><span class="sxs-lookup"><span data-stu-id="b75d7-135">DTS_E_UNPROTECTXMLFAILED</span></span>|<span data-ttu-id="b75d7-136">Indica que o sistema não descriptografou um nó XML protegido.</span><span class="sxs-lookup"><span data-stu-id="b75d7-136">Indicates that the system did not decrypt a protected XML node.</span></span>|  
|<span data-ttu-id="b75d7-137">DTS_E_WRITEWHILECACHEINUSE</span><span class="sxs-lookup"><span data-stu-id="b75d7-137">DTS_E_WRITEWHILECACHEINUSE</span></span>|<span data-ttu-id="b75d7-138">Indica que uma Transformação Cache está tentando gravar dados no cache na memória ao mesmo tempo que uma transformação Pesquisa está lendo dados no cache na memória.</span><span class="sxs-lookup"><span data-stu-id="b75d7-138">Indicates that a Cache Transform transformation is trying to write data to the in-memory cache at the same time that a Lookup transformation is reading data from the in-memory cache.</span></span>|  
|<span data-ttu-id="b75d7-139">DTS_W_EXTERNALMETADATACOLUMNSOUTOFSYNC</span><span class="sxs-lookup"><span data-stu-id="b75d7-139">DTS_W_EXTERNALMETADATACOLUMNSOUTOFSYNC</span></span>|<span data-ttu-id="b75d7-140">Indica que os metadados da coluna na fonte de dados não correspondem aos metadados da coluna no componente de origem ou de destino que está conectado à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b75d7-140">Indicates that the column metadata in the data source does not match the column metadata in the source or destination component that is connected to the data source.</span></span>|  
  
## <a name="events-sqlispackage"></a><span data-ttu-id="b75d7-141">Eventos (SQLISPackage)</span><span class="sxs-lookup"><span data-stu-id="b75d7-141">Events (SQLISPackage)</span></span>  
 <span data-ttu-id="b75d7-142">Para obter mais informações, consulte [Eventos registrados por um pacote do Integration Services](performance/events-logged-by-an-integration-services-package.md).</span><span class="sxs-lookup"><span data-stu-id="b75d7-142">For more information, see [Events Logged by an Integration Services Package](performance/events-logged-by-an-integration-services-package.md).</span></span>  
  
|<span data-ttu-id="b75d7-143">Evento</span><span class="sxs-lookup"><span data-stu-id="b75d7-143">Event</span></span>|<span data-ttu-id="b75d7-144">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="b75d7-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b75d7-145">SQLISPackage_12288</span><span class="sxs-lookup"><span data-stu-id="b75d7-145">SQLISPackage_12288</span></span>|<span data-ttu-id="b75d7-146">Indica que um pacote foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="b75d7-146">Indicates that a package started.</span></span>|  
|<span data-ttu-id="b75d7-147">SQLISPackage_12289</span><span class="sxs-lookup"><span data-stu-id="b75d7-147">SQLISPackage_12289</span></span>|<span data-ttu-id="b75d7-148">Indica que um pacote concluiu a execução com êxito.</span><span class="sxs-lookup"><span data-stu-id="b75d7-148">Indicates that a package has finished running successfully.</span></span>|  
|<span data-ttu-id="b75d7-149">SQLISPACKAGE_12291</span><span class="sxs-lookup"><span data-stu-id="b75d7-149">SQLISPACKAGE_12291</span></span>|<span data-ttu-id="b75d7-150">Indica que um pacote não pôde concluir a execução e foi interrompido.</span><span class="sxs-lookup"><span data-stu-id="b75d7-150">Indicates that a package was unable to finish running and has stopped.</span></span>|  
|<span data-ttu-id="b75d7-151">SQLISPackage_12546</span><span class="sxs-lookup"><span data-stu-id="b75d7-151">SQLISPackage_12546</span></span>|<span data-ttu-id="b75d7-152">Indica que uma tarefa ou outro executável em um pacote concluiu seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="b75d7-152">Indicates that a task or other executable in a package has finished its work.</span></span>|  
|<span data-ttu-id="b75d7-153">SQLISPackage_12549</span><span class="sxs-lookup"><span data-stu-id="b75d7-153">SQLISPackage_12549</span></span>|<span data-ttu-id="b75d7-154">Indica que uma mensagem de aviso foi gerada em um pacote.</span><span class="sxs-lookup"><span data-stu-id="b75d7-154">Indicates that a warning message was raised in a package.</span></span>|  
|<span data-ttu-id="b75d7-155">SQLISPackage_12550</span><span class="sxs-lookup"><span data-stu-id="b75d7-155">SQLISPackage_12550</span></span>|<span data-ttu-id="b75d7-156">Indica que uma mensagem de erro foi gerada em um pacote.</span><span class="sxs-lookup"><span data-stu-id="b75d7-156">Indicates that an error message was raised in a package.</span></span>|  
|<span data-ttu-id="b75d7-157">SQLISPackage_12551</span><span class="sxs-lookup"><span data-stu-id="b75d7-157">SQLISPackage_12551</span></span>|<span data-ttu-id="b75d7-158">Indica que um pacote não concluiu seu trabalho e foi interrompido.</span><span class="sxs-lookup"><span data-stu-id="b75d7-158">Indicates that a package did not finish its work and stopped.</span></span>|  
|<span data-ttu-id="b75d7-159">SQLISPackage_12557</span><span class="sxs-lookup"><span data-stu-id="b75d7-159">SQLISPackage_12557</span></span>|<span data-ttu-id="b75d7-160">Indica que um pacote concluiu a execução.</span><span class="sxs-lookup"><span data-stu-id="b75d7-160">Indicates that a package has finished running.</span></span>|  
  
## <a name="events-sqlisservice"></a><span data-ttu-id="b75d7-161">Eventos (SQLISService)</span><span class="sxs-lookup"><span data-stu-id="b75d7-161">Events (SQLISService)</span></span>  
 <span data-ttu-id="b75d7-162">Para obter mais informações, consulte [Eventos registrados pelo serviço do Integration Services](service/events-logged-by-the-integration-services-service.md).</span><span class="sxs-lookup"><span data-stu-id="b75d7-162">For more information, see [Events Logged by the Integration Services Service](service/events-logged-by-the-integration-services-service.md).</span></span>  
  
|<span data-ttu-id="b75d7-163">Evento</span><span class="sxs-lookup"><span data-stu-id="b75d7-163">Event</span></span>|<span data-ttu-id="b75d7-164">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="b75d7-164">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b75d7-165">SQLISService_256</span><span class="sxs-lookup"><span data-stu-id="b75d7-165">SQLISService_256</span></span>|<span data-ttu-id="b75d7-166">Indica que o serviço está prestes a ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="b75d7-166">Indicates that the service is about to start.</span></span>|  
|<span data-ttu-id="b75d7-167">SQLISService_257</span><span class="sxs-lookup"><span data-stu-id="b75d7-167">SQLISService_257</span></span>|<span data-ttu-id="b75d7-168">Indica que o serviço foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="b75d7-168">Indicates that the service has started.</span></span>|  
|<span data-ttu-id="b75d7-169">SQLISService_258</span><span class="sxs-lookup"><span data-stu-id="b75d7-169">SQLISService_258</span></span>|<span data-ttu-id="b75d7-170">Indica que o serviço está prestes a ser interrompido.</span><span class="sxs-lookup"><span data-stu-id="b75d7-170">Indicates that the service is about to stop.</span></span>|  
|<span data-ttu-id="b75d7-171">SQLISService_259</span><span class="sxs-lookup"><span data-stu-id="b75d7-171">SQLISService_259</span></span>|<span data-ttu-id="b75d7-172">Indica que o serviço foi interrompido.</span><span class="sxs-lookup"><span data-stu-id="b75d7-172">Indicates that the service has stopped.</span></span>|  
|<span data-ttu-id="b75d7-173">SQLISService_260</span><span class="sxs-lookup"><span data-stu-id="b75d7-173">SQLISService_260</span></span>|<span data-ttu-id="b75d7-174">Indica que o serviço tentou iniciar, mas não conseguiu.</span><span class="sxs-lookup"><span data-stu-id="b75d7-174">Indicates that the service tried to start, but could not.</span></span>|  
|<span data-ttu-id="b75d7-175">SQLISService_272</span><span class="sxs-lookup"><span data-stu-id="b75d7-175">SQLISService_272</span></span>|<span data-ttu-id="b75d7-176">Indica que o arquivo de configuração não existe no local especificado.</span><span class="sxs-lookup"><span data-stu-id="b75d7-176">Indicates that the configuration file does not exist at the specified location.</span></span>|  
|<span data-ttu-id="b75d7-177">SQLISService_273</span><span class="sxs-lookup"><span data-stu-id="b75d7-177">SQLISService_273</span></span>|<span data-ttu-id="b75d7-178">Indica que o arquivo de configuração não pôde ser lido ou não é válido.</span><span class="sxs-lookup"><span data-stu-id="b75d7-178">Indicates that the configuration file could not be read or is not valid.</span></span>|  
|<span data-ttu-id="b75d7-179">SQLISService_274</span><span class="sxs-lookup"><span data-stu-id="b75d7-179">SQLISService_274</span></span>|<span data-ttu-id="b75d7-180">Indica que a entrada do Registro que contém o local do arquivo de configuração não existe ou está vazia.</span><span class="sxs-lookup"><span data-stu-id="b75d7-180">Indicates that the registry entry that contains the location of the configuration file does not exist or is empty.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b75d7-181">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b75d7-181">See Also</span></span>  
 [<span data-ttu-id="b75d7-182">Referência de mensagens e erros do Integration Services</span><span class="sxs-lookup"><span data-stu-id="b75d7-182">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  