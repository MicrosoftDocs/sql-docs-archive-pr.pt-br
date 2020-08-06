---
title: Tarefa de Fluxo de Dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataflowtask.f1
helpviewer_keywords:
- data flow task [Integration Services]
- performance [Integration Services]
- data flow [Integration Services], performance
- data flow [Integration Services], Data Flow task
- Integration Services, performance
ms.assetid: c27555c4-208c-43c8-b511-a4de2a8a3344
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 75531332d059c1c3fb95dddb3a4a81048ff99201
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574861"
---
# <a name="data-flow-task"></a><span data-ttu-id="48a11-102">Tarefa de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="48a11-102">Data Flow Task</span></span>
  <span data-ttu-id="48a11-103">A tarefa de Fluxo de Dados encapsula o mecanismo de fluxo de dados que move dados entre as origens e os destinos, permitindo que o usuário transforme, limpe e modifique os dados à medida que são movidos.</span><span class="sxs-lookup"><span data-stu-id="48a11-103">The Data Flow task encapsulates the data flow engine that moves data between sources and destinations, and lets the user transform, clean, and modify data as it is moved.</span></span> <span data-ttu-id="48a11-104">A adição de uma tarefa de Fluxo de Dados em um pacote de fluxo de controle permite que o pacote extraia, transforme e carregue dados.</span><span class="sxs-lookup"><span data-stu-id="48a11-104">Addition of a Data Flow task to a package control flow makes it possible for the package to extract, transform, and load data.</span></span>  
  
 <span data-ttu-id="48a11-105">Um fluxo de dados consiste em pelo menos um componente de fluxo de dados, mas normalmente é um conjunto de componentes de fluxo de dados conectados: fontes que extraem dados; transformações que modificam, roteiam ou resumem dados; e destinos que carregam dados.</span><span class="sxs-lookup"><span data-stu-id="48a11-105">A data flow consists of at least one data flow component, but it is typically a set of connected data flow components: sources that extract data; transformations that modify, route, or summarize data; and destinations that load data.</span></span>  
  
 <span data-ttu-id="48a11-106">Em tempo de execução, a tarefa de Fluxo de Dados cria um plano de execução a partir do fluxo de dados e o mecanismo de fluxo de dados executa o plano.</span><span class="sxs-lookup"><span data-stu-id="48a11-106">At run time, the Data Flow task builds an execution plan from the data flow, and the data flow engine executes the plan.</span></span> <span data-ttu-id="48a11-107">Você pode criar uma tarefa de Fluxo de Dados que não tenha nenhum fluxo de dados, porém a tarefa será executada somente se pelo menos um fluxo de dados for incluído.</span><span class="sxs-lookup"><span data-stu-id="48a11-107">You can create a Data Flow task that has no data flow, but the task executes only if it includes at least one data flow.</span></span>  
  
 <span data-ttu-id="48a11-108">Para inserir dados de arquivos de texto em massa em um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , você pode usar a tarefa Inserção em Massa em vez de uma tarefa de Fluxo de Dados e um fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="48a11-108">To bulk insert data from text files into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, you can use the Bulk Insert task instead of a Data Flow task and a data flow.</span></span> <span data-ttu-id="48a11-109">Porém, a tarefa de Inserção em Massa não pode transformar dados.</span><span class="sxs-lookup"><span data-stu-id="48a11-109">However, the Bulk Insert task cannot transform data.</span></span> <span data-ttu-id="48a11-110">Para obter mais informações, veja [Tarefa Inserção em Massa](bulk-insert-task.md).</span><span class="sxs-lookup"><span data-stu-id="48a11-110">For more information, see [Bulk Insert Task](bulk-insert-task.md).</span></span>  
  
## <a name="multiple-flows"></a><span data-ttu-id="48a11-111">Vários fluxos</span><span class="sxs-lookup"><span data-stu-id="48a11-111">Multiple Flows</span></span>  
 <span data-ttu-id="48a11-112">Uma tarefa de Fluxo de Dados pode incluir vários fluxos de dados.</span><span class="sxs-lookup"><span data-stu-id="48a11-112">A Data Flow task can include multiple data flows.</span></span> <span data-ttu-id="48a11-113">Se uma tarefa copiar vários conjuntos de dados e se a ordem na qual os dados são copiados não for significativa, poderá ser mais conveniente incluir vários fluxos de dados na tarefa de Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="48a11-113">If a task copies several sets of data, and if the order in which the data is copied is not significant, it can be more convenient to include multiple data flows in the Data Flow task.</span></span> <span data-ttu-id="48a11-114">Por exemplo, você poderia criar cinco fluxos de dados, cada um copiando dados de um arquivo simples para uma tabela de dimensão diferente em um esquema em estrela de data warehouse.</span><span class="sxs-lookup"><span data-stu-id="48a11-114">For example, you might create five data flows, each copying data from a flat file into a different dimension table in a data warehouse star schema.</span></span>  
  
 <span data-ttu-id="48a11-115">Entretanto, o mecanismo de fluxo de dados determina a ordem de execução quando há vários fluxos de dados em uma tarefa de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="48a11-115">However, the data flow engine determines order of execution when there are multiple data flows within one data flow task.</span></span> <span data-ttu-id="48a11-116">Portanto, quando a ordem for importante, o pacote deverá usar várias tarefas de Fluxo de Dados, cada tarefa contendo um fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="48a11-116">Therefore, when order is important, the package should use multiple Data Flow tasks, each task containing one data flow.</span></span> <span data-ttu-id="48a11-117">Você poderá então aplicar restrições de precedência para controlar a ordem de execução das tarefas.</span><span class="sxs-lookup"><span data-stu-id="48a11-117">You can then apply precedence constraints to control the execution order of the tasks.</span></span>  
  
 <span data-ttu-id="48a11-118">O diagrama a seguir mostra uma tarefa de Fluxo de Dados com vários fluxos de dados.</span><span class="sxs-lookup"><span data-stu-id="48a11-118">The following diagram shows a Data Flow task that has multiple data flows.</span></span>  
  
 <span data-ttu-id="48a11-119">![Fluxos de dados](../media/mw-dts-09.gif "Fluxos de dados")</span><span class="sxs-lookup"><span data-stu-id="48a11-119">![Data flows](../media/mw-dts-09.gif "Data flows")</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="48a11-120">Entradas de log</span><span class="sxs-lookup"><span data-stu-id="48a11-120">Log Entries</span></span>  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="48a11-121">fornece um conjunto de eventos de log que estão disponíveis para todas as tarefas.</span><span class="sxs-lookup"><span data-stu-id="48a11-121">provides a set of log events that are available to all tasks.</span></span> [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="48a11-122">também fornece entradas de log personalizadas a muitas tarefas.</span><span class="sxs-lookup"><span data-stu-id="48a11-122">also provides custom log entries to many tasks.</span></span> <span data-ttu-id="48a11-123">Para obter mais informações, consulte [Log do SSIS &#40;Integration Services&#41;](../performance/integration-services-ssis-logging.md) e [Mensagens personalizadas para log](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="48a11-123">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span> <span data-ttu-id="48a11-124">A tarefa de Fluxo de Dados inclui as seguintes entradas de log personalizadas:</span><span class="sxs-lookup"><span data-stu-id="48a11-124">The Data Flow task includes the following custom log entries:</span></span>  
  
|<span data-ttu-id="48a11-125">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="48a11-125">Log entry</span></span>|<span data-ttu-id="48a11-126">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="48a11-126">Description</span></span>|  
|---------------|-----------------|  
|`BufferSizeTuning`|<span data-ttu-id="48a11-127">Indica que a tarefa de Fluxo de Dados alterou o tamanho do buffer.</span><span class="sxs-lookup"><span data-stu-id="48a11-127">Indicates that the Data Flow task changed the size of the buffer.</span></span> <span data-ttu-id="48a11-128">A entrada de log descreve os motivos da mudança de tamanho e relaciona o novo tamanho do buffer temporário.</span><span class="sxs-lookup"><span data-stu-id="48a11-128">The log entry describes the reasons for the size change and lists the temporary new buffer size.</span></span>|  
|`OnPipelinePostEndOfRowset`|<span data-ttu-id="48a11-129">Indica que um componente recebeu o sinal de final do conjunto de linhas, definido pela última chamada do método `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="48a11-129">Denotes that a component has been given its end-of-rowset signal, which is set by the last call of the `ProcessInput` method.</span></span> <span data-ttu-id="48a11-130">Uma entrada é gravada para cada componente no fluxo de dados que processa a entrada.</span><span class="sxs-lookup"><span data-stu-id="48a11-130">An entry is written for each component in the data flow that processes input.</span></span> <span data-ttu-id="48a11-131">A entrada contém o nome do componente.</span><span class="sxs-lookup"><span data-stu-id="48a11-131">The entry includes the name of the component.</span></span>|  
|`OnPipelinePostPrimeOutput`|<span data-ttu-id="48a11-132">Indica que o componente completou sua última chamada para o método `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="48a11-132">Indicates that the component has completed its last call to the `PrimeOutput` method.</span></span> <span data-ttu-id="48a11-133">Dependendo do fluxo de dados, várias entradas de log podem ser gravadas.</span><span class="sxs-lookup"><span data-stu-id="48a11-133">Depending on the data flow, multiple log entries may be written.</span></span> <span data-ttu-id="48a11-134">Se o componente for uma fonte, essa entrada de log significa que o componente tem linhas de processamento concluídas.</span><span class="sxs-lookup"><span data-stu-id="48a11-134">If the component is a source, this log entry means that the component has finished processing rows.</span></span>|  
|`OnPipelinePreEndOfRowset`|<span data-ttu-id="48a11-135">Indica que um componente está prestes a receber o sinal de final do conjunto de linhas, definido pela última chamada do método `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="48a11-135">Indicates that a component is about to receive its end-of-rowset signal, which is set by the last call of the `ProcessInput` method.</span></span> <span data-ttu-id="48a11-136">Uma entrada é gravada para cada componente no fluxo de dados que processa a entrada.</span><span class="sxs-lookup"><span data-stu-id="48a11-136">An entry is written for each component in the data flow that processes input.</span></span> <span data-ttu-id="48a11-137">A entrada contém o nome do componente.</span><span class="sxs-lookup"><span data-stu-id="48a11-137">The entry includes the name of the component.</span></span>|  
|`OnPipelinePrePrimeOutput`|<span data-ttu-id="48a11-138">Indica que o componente está prestes a receber sua chamada a partir do método `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="48a11-138">Indicates that the component is about to receive its call from the `PrimeOutput` method.</span></span> <span data-ttu-id="48a11-139">Dependendo do fluxo de dados, várias entradas de log podem ser gravadas.</span><span class="sxs-lookup"><span data-stu-id="48a11-139">Depending on the data flow, multiple log entries may be written.</span></span>|  
|`OnPipelineRowsSent`|<span data-ttu-id="48a11-140">Informa o número de linhas fornecido a uma entrada de componente por uma chamada para o método `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="48a11-140">Reports the number of rows provided to a component input by a call to the `ProcessInput` method.</span></span> <span data-ttu-id="48a11-141">A entrada de log inclui o nome do componente.</span><span class="sxs-lookup"><span data-stu-id="48a11-141">The log entry includes the component name.</span></span>|  
|`PipelineBufferLeak`|<span data-ttu-id="48a11-142">Fornece informações sobre qualquer componente que manteve buffers ativos depois que o gerenciador de buffers for desativado.</span><span class="sxs-lookup"><span data-stu-id="48a11-142">Provides information about any component that kept buffers alive after the buffer manager goes away.</span></span> <span data-ttu-id="48a11-143">Se um buffer ainda estiver ativo, os recursos de buffers não foram liberados e pode haver perdas de memória.</span><span class="sxs-lookup"><span data-stu-id="48a11-143">If a buffer is still alive, buffers resources were not released and may cause memory leaks.</span></span> <span data-ttu-id="48a11-144">A entrada de log fornece o nome do componente e a ID do buffer.</span><span class="sxs-lookup"><span data-stu-id="48a11-144">The log entry provides the name of the component and the ID of the buffer.</span></span>|  
|`PipelineComponentTime`|<span data-ttu-id="48a11-145">Reporta o tempo (em milissegundos) que o componente gastou em cada uma das cinco principais etapas de processamento – Validate, PreExecute, PostExecute, ProcessInput e ProcessOutput.</span><span class="sxs-lookup"><span data-stu-id="48a11-145">Reports the amount of time (in milliseconds) that the component spent in each of its five major processing steps-Validate, PreExecute, PostExecute, ProcessInput, and ProcessOutput.</span></span>|  
|`PipelineExecutionPlan`|<span data-ttu-id="48a11-146">Informa o plano de execução do fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="48a11-146">Reports the execution plan of the data flow.</span></span> <span data-ttu-id="48a11-147">O plano de execução fornece informações sobre como os buffers serão enviados para os componentes.</span><span class="sxs-lookup"><span data-stu-id="48a11-147">The execution plan provides information about how buffers will be sent to components.</span></span> <span data-ttu-id="48a11-148">Essas informações, em combinação com a entrada de log PipelineExecutionTrees, descrevem o que está ocorrendo na tarefa de Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="48a11-148">This information, in combination with the PipelineExecutionTrees log entry, describes what is happening within the Data Flow task.</span></span>|  
|`PipelineExecutionTrees`|<span data-ttu-id="48a11-149">Informa as árvores de execução sobre o layout do fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="48a11-149">Reports the execution trees of the layout in the data flow.</span></span> <span data-ttu-id="48a11-150">O agendador do mecanismo de fluxo de dados usa as árvores para criar o plano de execução do fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="48a11-150">The scheduler of the data flow engine uses the trees to build the execution plan of the data flow.</span></span>|  
|`PipelineInitialization`|<span data-ttu-id="48a11-151">Fornece informações de inicialização sobre a tarefa.</span><span class="sxs-lookup"><span data-stu-id="48a11-151">Provides initialization information about the task.</span></span> <span data-ttu-id="48a11-152">Essas informações incluem os diretórios para armazenamento temporário de dados de BLOB, o tamanho do buffer padrão e o número de linhas em um buffer.</span><span class="sxs-lookup"><span data-stu-id="48a11-152">This information includes the directories to use for temporary storage of BLOB data, the default buffer size, and the number of rows in a buffer.</span></span> <span data-ttu-id="48a11-153">Dependendo da configuração da tarefa de Fluxo de Dados, várias entradas de log podem ser gravadas.</span><span class="sxs-lookup"><span data-stu-id="48a11-153">Depending on the configuration of the Data Flow task, multiple log entries may be written.</span></span>|  
  
 <span data-ttu-id="48a11-154">Essas entradas de log fornecerão informações detalhadas sobre a execução da tarefa de Fluxo de Dados sempre que você executar um pacote.</span><span class="sxs-lookup"><span data-stu-id="48a11-154">These log entries provide a wealth of information about the execution of the Data Flow task each time you run a package.</span></span> <span data-ttu-id="48a11-155">Ao executar os pacotes repetidamente, você poderá coletar informações que com o passar do tempo fornecerá informações históricas importantes sobre o processamento que a tarefa executa, problemas que podem afetar o desempenho e o volume de dados que a tarefa controla.</span><span class="sxs-lookup"><span data-stu-id="48a11-155">As you run the packages repeatedly, you can capture information that over time provides important historical information about the processing that the task performs, issues that might affect performance, and the data volume that task handles.</span></span>  
  
 <span data-ttu-id="48a11-156">Para obter mais informações sobre como usar essas entradas de log para monitorar e melhorar o desempenho do fluxo de dados, consulte um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="48a11-156">For more information about how to use these log entries to monitor and improve the performance of the data flow, see one of the following topics:</span></span>  
  
-   [<span data-ttu-id="48a11-157">Contadores de desempenho</span><span class="sxs-lookup"><span data-stu-id="48a11-157">Performance Counters</span></span>](../performance/performance-counters.md)  
  
-   [<span data-ttu-id="48a11-158">Recursos de desempenho de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="48a11-158">Data Flow Performance Features</span></span>](../data-flow/data-flow-performance-features.md)  
  
### <a name="sample-messages-from-a-data-flow-task"></a><span data-ttu-id="48a11-159">Mensagens de amostra de uma tarefa de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="48a11-159">Sample Messages From a Data Flow Task</span></span>  
 <span data-ttu-id="48a11-160">A tabela a seguir relaciona as mensagens de amostra de entradas de log para um pacote simples.</span><span class="sxs-lookup"><span data-stu-id="48a11-160">The following table lists sample messages for log entries for a very simple package.</span></span> <span data-ttu-id="48a11-161">O pacote usa uma origem OLE DB para extrair dados de uma tabela, uma transformação Classificar para classificar os dados e um destino OLE DB para gravar os dados em uma tabela diferente.</span><span class="sxs-lookup"><span data-stu-id="48a11-161">The package uses an OLE DB source to extract data from a table, a Sort transformation to sort the data, and an OLE DB destination to writes the data to a different table.</span></span>  
  
|<span data-ttu-id="48a11-162">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="48a11-162">Log entry</span></span>|<span data-ttu-id="48a11-163">Mensagens</span><span class="sxs-lookup"><span data-stu-id="48a11-163">Messages</span></span>|  
|---------------|--------------|  
|`BufferSizeTuning`|`Rows in buffer type 0 would cause a buffer size greater than the configured maximum. There will be only 9637 rows in buffers of this type.`<br /><br /> `Rows in buffer type 2 would cause a buffer size greater than the configured maximum. There will be only 9497 rows in buffers of this type.`<br /><br /> `Rows in buffer type 3 would cause a buffer size greater than the configured maximum. There will be only 9497 rows in buffers of this type.`|  
|`OnPipelinePostEndOfRowset`|`A component will be given the end of rowset signal. : 1180 : Sort : 1181 : Sort Input`<br /><br /> `A component will be given the end of rowset signal. : 1291 : OLE DB Destination : 1304 : OLE DB Destination Input`|  
|`OnPipelinePostPrimeOutput`|`A component has returned from its PrimeOutput call. : 1180 : Sort`<br /><br /> `A component has returned from its PrimeOutput call. : 1 : OLE DB Source`|  
|`OnPipelinePreEndOfRowset`|`A component has finished processing all of its rows. : 1180 : Sort : 1181 : Sort Input`<br /><br /> `A component has finished processing all of its rows. : 1291 : OLE DB Destination : 1304 : OLE DB Destination Input`|  
|`OnPipelinePrePrimeOutput`|`PrimeOutput will be called on a component. : 1180 : Sort`<br /><br /> `PrimeOutput will be called on a component. : 1 : OLE DB Source`|  
|`OnPipelineRowsSent`|`Rows were provided to a data flow component as input. :  : 1185 : OLE DB Source Output : 1180 : Sort : 1181 : Sort Input : 76`<br /><br /> `Rows were provided to a data flow component as input. :  : 1308 : Sort Output : 1291 : OLE DB Destination : 1304 : OLE DB Destination Input : 76`|  
|`PipelineComponentTime`|`The component "Calculate LineItemTotalCost" (3522) spent 356 milliseconds in ProcessInput.`<br /><br /> `The component "Sum Quantity and LineItemTotalCost" (3619) spent 79 milliseconds in ProcessInput.`<br /><br /> `The component "Calculate Average Cost" (3662) spent 16 milliseconds in ProcessInput.`<br /><br /> `The component "Sort by ProductID" (3717) spent 125 milliseconds in ProcessInput.`<br /><br /> `The component "Load Data" (3773) spent 0 milliseconds in ProcessInput.`<br /><br /> `The component "Extract Data" (3869) spent 688 milliseconds in PrimeOutput filling buffers on output "OLE DB Source Output" (3879).`<br /><br /> `The component "Sum Quantity and LineItemTotalCost" (3619) spent 141 milliseconds in PrimeOutput filling buffers on output "Aggregate Output 1" (3621).`<br /><br /> `The component "Sort by ProductID" (3717) spent 16 milliseconds in PrimeOutput filling buffers on output "Sort Output" (3719).`|  
|`PipelineExecutionPlan`|`SourceThread0`<br /><br /> `Drives: 1`<br /><br /> `Influences: 1180 1291`<br /><br /> `Output Work List`<br /><br /> `CreatePrimeBuffer of type 1 for output ID 11.`<br /><br /> `SetBufferListener: "WorkThread0" for input ID 1181`<br /><br /> `CreatePrimeBuffer of type 3 for output ID 12.`<br /><br /> `CallPrimeOutput on component "OLE DB Source" (1)`<br /><br /> `End Output Work List`<br /><br /> `End SourceThread0`<br /><br /> `WorkThread0`<br /><br /> `Drives: 1180`<br /><br /> `Influences: 1180 1291`<br /><br /> `Input Work list, input ID 1181 (1 EORs Expected)`<br /><br /> `CallProcessInput on input ID 1181 on component "Sort" (1180) for view type 2`<br /><br /> `End Input Work list for input 1181`<br /><br /> `Output Work List`<br /><br /> `CreatePrimeBuffer of type 4 for output ID 1182.`<br /><br /> `SetBufferListener: "WorkThread1" for input ID 1304`<br /><br /> `CallPrimeOutput on component "Sort" (1180)`<br /><br /> `End Output Work List`<br /><br /> `End WorkThread0`<br /><br /> `WorkThread1`<br /><br /> `Drives: 1291`<br /><br /> `Influences: 1291`<br /><br /> `Input Work list, input ID 1304 (1 EORs Expected)`<br /><br /> `CallProcessInput on input ID 1304 on component "OLE DB Destination" (1291) for view type 5`<br /><br /> `End Input Work list for input 1304`<br /><br /> `Output Work List`<br /><br /> `End Output Work List`<br /><br /> `End WorkThread1`|  
|`PipelineExecutionTrees`|`begin execution tree 0`<br /><br /> `output "OLE DB Source Output" (11)`<br /><br /> `input "Sort Input" (1181)`<br /><br /> `end execution tree 0`<br /><br /> `begin execution tree 1`<br /><br /> `output "OLE DB Source Error Output" (12)`<br /><br /> `end execution tree 1`<br /><br /> `begin execution tree 2`<br /><br /> `output "Sort Output" (1182)`<br /><br /> `input "OLE DB Destination Input" (1304)`<br /><br /> `output "OLE DB Destination Error Output" (1305)`<br /><br /> `end execution tree 2`|  
|`PipelineInitialization`|`No temporary BLOB data storage locations were provided. The buffer manager will consider the directories in the TEMP and TMP environment variables.`<br /><br /> `The default buffer size is 10485760 bytes.`<br /><br /> `Buffers will have 10000 rows by default`<br /><br /> `The data flow will not remove unused components because its RunInOptimizedMode property is set to false.`|  
  
 <span data-ttu-id="48a11-164">Muitos eventos de log gravam várias entradas, e as mensagens para várias entradas de log contêm dados complexos.</span><span class="sxs-lookup"><span data-stu-id="48a11-164">Many log events write multiple entries, and the messages for a number of log entries contain complex data.</span></span> <span data-ttu-id="48a11-165">Para facilitar a compreensão e comunicar o conteúdo de mensagens complexas, você pode analisar a mensagem de texto.</span><span class="sxs-lookup"><span data-stu-id="48a11-165">To make it easier to understand and to communicate the content of complex messages you can parse the message text.</span></span> <span data-ttu-id="48a11-166">Dependendo do local dos logs, você poderá usar as instruções Transact-SQL ou um componente Script para separar o texto complexo em colunas ou em outros formatos que considere mais útil.</span><span class="sxs-lookup"><span data-stu-id="48a11-166">Depending on the location of the logs, you can use Transact-SQL statements or a Script component to separate the complex text into columns or other formats that you find more useful.</span></span>  
  
 <span data-ttu-id="48a11-167">Por exemplo, a tabela a seguir contém a mensagem "Foram fornecidas linhas para um componente de fluxo de dados como entrada.</span><span class="sxs-lookup"><span data-stu-id="48a11-167">For example, the following table contains the message "Rows were provided to a data flow component as input.</span></span> <span data-ttu-id="48a11-168">:  : 1185: Saída de origem OLE DB: 1180: Classificação: 1181: Classificar entrada: 76", analisado em colunas.</span><span class="sxs-lookup"><span data-stu-id="48a11-168">:  : 1185 : OLE DB Source Output : 1180 : Sort : 1181 : Sort Input : 76", parsed into columns.</span></span> <span data-ttu-id="48a11-169">A mensagem foi gravada pelo evento `OnPipelineRowsSent` quando foram enviadas linhas da origem OLE DB para a transformação Classificação.</span><span class="sxs-lookup"><span data-stu-id="48a11-169">The message was written by the `OnPipelineRowsSent` event when rows were sent from the OLE DB source to the Sort transformation.</span></span>  
  
|<span data-ttu-id="48a11-170">Column</span><span class="sxs-lookup"><span data-stu-id="48a11-170">Column</span></span>|<span data-ttu-id="48a11-171">Descrição</span><span class="sxs-lookup"><span data-stu-id="48a11-171">Description</span></span>|<span data-ttu-id="48a11-172">Valor</span><span class="sxs-lookup"><span data-stu-id="48a11-172">Value</span></span>|  
|------------|-----------------|-----------|  
|<span data-ttu-id="48a11-173">**PathID**</span><span class="sxs-lookup"><span data-stu-id="48a11-173">**PathID**</span></span>|<span data-ttu-id="48a11-174">O valor da propriedade `ID` do caminho entre a origem OLE DB e a transformação Classificação.</span><span class="sxs-lookup"><span data-stu-id="48a11-174">The value from the `ID` property of the path between the OLE DB source and the Sort transformation.</span></span>|<span data-ttu-id="48a11-175">1185</span><span class="sxs-lookup"><span data-stu-id="48a11-175">1185</span></span>|  
|<span data-ttu-id="48a11-176">**PathName**</span><span class="sxs-lookup"><span data-stu-id="48a11-176">**PathName**</span></span>|<span data-ttu-id="48a11-177">O valor da propriedade `Name` do caminho.</span><span class="sxs-lookup"><span data-stu-id="48a11-177">The value from the `Name` property of the path.</span></span>|<span data-ttu-id="48a11-178">Saída da origem OLE DB</span><span class="sxs-lookup"><span data-stu-id="48a11-178">OLE DB Source Output</span></span>|  
|<span data-ttu-id="48a11-179">**ComponentID**</span><span class="sxs-lookup"><span data-stu-id="48a11-179">**ComponentID**</span></span>|<span data-ttu-id="48a11-180">O valor da `ID` propriedade da transformação classificação.</span><span class="sxs-lookup"><span data-stu-id="48a11-180">The value of the `ID` property of the Sort transformation.</span></span>|<span data-ttu-id="48a11-181">1180</span><span class="sxs-lookup"><span data-stu-id="48a11-181">1180</span></span>|  
|<span data-ttu-id="48a11-182">**ComponentName**</span><span class="sxs-lookup"><span data-stu-id="48a11-182">**ComponentName**</span></span>|<span data-ttu-id="48a11-183">O valor da propriedade `Name` da transformação Classificação.</span><span class="sxs-lookup"><span data-stu-id="48a11-183">The value from the `Name` property of the Sort transformation.</span></span>|<span data-ttu-id="48a11-184">Classificar</span><span class="sxs-lookup"><span data-stu-id="48a11-184">Sort</span></span>|  
|<span data-ttu-id="48a11-185">**InputID**</span><span class="sxs-lookup"><span data-stu-id="48a11-185">**InputID**</span></span>|<span data-ttu-id="48a11-186">O valor da propriedade `ID` da entrada para a transformação Classificação.</span><span class="sxs-lookup"><span data-stu-id="48a11-186">The value from the `ID` property of the input to the Sort transformation.</span></span>|<span data-ttu-id="48a11-187">1181</span><span class="sxs-lookup"><span data-stu-id="48a11-187">1181</span></span>|  
|<span data-ttu-id="48a11-188">**InputName**</span><span class="sxs-lookup"><span data-stu-id="48a11-188">**InputName**</span></span>|<span data-ttu-id="48a11-189">O valor da propriedade `Name` da entrada para a transformação Classificação.</span><span class="sxs-lookup"><span data-stu-id="48a11-189">The value from the `Name` property of the input to the Sort transformation.</span></span>|<span data-ttu-id="48a11-190">Classificar entrada</span><span class="sxs-lookup"><span data-stu-id="48a11-190">Sort Input</span></span>|  
|<span data-ttu-id="48a11-191">**RowsSent**</span><span class="sxs-lookup"><span data-stu-id="48a11-191">**RowsSent**</span></span>|<span data-ttu-id="48a11-192">O número de linhas enviadas para a entrada da transformação Classificação.</span><span class="sxs-lookup"><span data-stu-id="48a11-192">The number of rows sent to the input of the Sort transformation.</span></span>|<span data-ttu-id="48a11-193">76</span><span class="sxs-lookup"><span data-stu-id="48a11-193">76</span></span>|  
  
## <a name="configuration-of-the-data-flow-task"></a><span data-ttu-id="48a11-194">Configuração da tarefa Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="48a11-194">Configuration of the Data Flow Task</span></span>  
 <span data-ttu-id="48a11-195">Você pode definir as propriedades na janela **Propriedades** ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="48a11-195">You can set properties in the **Properties** window or programmatically.</span></span>  
  
 <span data-ttu-id="48a11-196">Para obter mais informações sobre como definir essas propriedades na janela **Propriedades** , clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="48a11-196">For more information about how to set these properties in the **Properties** window, click the following topic:</span></span>  
  
-   [<span data-ttu-id="48a11-197">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="48a11-197">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-data-flow-task"></a><span data-ttu-id="48a11-198">Configuração programática da tarefa Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="48a11-198">Programmatic Configuration of the Data Flow Task</span></span>  
 <span data-ttu-id="48a11-199">Para obter mais informações sobre como adicionar uma tarefa de fluxo de dados programaticamente em um pacote e definir propriedades de fluxo de dados, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="48a11-199">For more information about programmatically adding a data flow task to a package and setting data flow properties, click the following topic:</span></span>  
  
-   [<span data-ttu-id="48a11-200">Adicionando a tarefa Fluxo de Dados programaticamente</span><span class="sxs-lookup"><span data-stu-id="48a11-200">Adding the Data Flow Task Programmatically</span></span>](../building-packages-programmatically/adding-the-data-flow-task-programmatically.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="48a11-201">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="48a11-201">Related Tasks</span></span>  
 [<span data-ttu-id="48a11-202">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="48a11-202">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="related-content"></a><span data-ttu-id="48a11-203">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="48a11-203">Related Content</span></span>  
 <span data-ttu-id="48a11-204">Vídeo, [Distribuidor de Dados Balanceados](https://go.microsoft.com/fwlink/?LinkID=226278&clcid=0x409), em technet.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="48a11-204">Video, [Balanced Data Distributer](https://go.microsoft.com/fwlink/?LinkID=226278&clcid=0x409), on technet.microsoft.com.</span></span>  
  
  