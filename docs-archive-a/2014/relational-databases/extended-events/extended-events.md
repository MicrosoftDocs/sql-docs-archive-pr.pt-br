---
title: Eventos estendidos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server]
- xe
ms.assetid: bf3b98a6-51ed-4f2d-9c26-92f07f1fa947
author: rothja
ms.author: jroth
ms.openlocfilehash: 6ef183a218c2930199696aa1e0144714006e12ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583585"
---
# <a name="extended-events"></a><span data-ttu-id="671f4-102">Eventos estendidos</span><span class="sxs-lookup"><span data-stu-id="671f4-102">Extended Events</span></span>
  <span data-ttu-id="671f4-103">Os Eventos Estendidos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] têm uma arquitetura altamente escalonável e configurável que permite aos usuários coletar o máximo ou o mínimo de informações, conforme necessário, para solucionar ou identificar um problema.</span><span class="sxs-lookup"><span data-stu-id="671f4-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events has a highly scalable and highly configurable architecture that allows users to collect as much or as little information as is necessary to troubleshoot or identify a performance problem.</span></span>  
  
 <span data-ttu-id="671f4-104">Você pode encontrar mais informações sobre os Eventos Estendidos na Web em [Eventos Estendidos do SQL Server](https://blogs.msdn.com/b/extended_events/).</span><span class="sxs-lookup"><span data-stu-id="671f4-104">You can find more information about Extended Events on the web at [SQL Server Extended Events](https://blogs.msdn.com/b/extended_events/).</span></span>  
  
## <a name="benefits-of-ssnoversion-extended-events"></a><span data-ttu-id="671f4-105">Benefícios de Eventos Estendidos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="671f4-105">Benefits of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events</span></span>  
 <span data-ttu-id="671f4-106">Eventos Estendidos são um sistema de monitoramento de desempenho de peso leve que usa poucos recursos de desempenho.</span><span class="sxs-lookup"><span data-stu-id="671f4-106">Extended Events is a light weight performance monitoring system that uses very few performance resources.</span></span> <span data-ttu-id="671f4-107">Os Eventos Estendidos fornecem duas interfaces gráficas do usuário (**Assistente de Nova Sessão** e **Nova Sessão**) para criar, modificar, exibir e analisar os dados da sessão.</span><span class="sxs-lookup"><span data-stu-id="671f4-107">Extended Events provides two graphical user interfaces (**New Session Wizard** and **New Session**) to create, modify, display, and analyze your session data.</span></span>  
  
## <a name="extended-events-concepts"></a><span data-ttu-id="671f4-108">Conceitos de eventos estendidos</span><span class="sxs-lookup"><span data-stu-id="671f4-108">Extended Events Concepts</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="671f4-109">Os Eventos Estendidos são criados com base em conceitos existentes, como um evento ou um consumidor do evento, usam conceitos de Rastreamento de Eventos para Windows e apresentam novos conceitos.</span><span class="sxs-lookup"><span data-stu-id="671f4-109">Extended Events (Extended Events) builds on existing concepts, such as an event or an event consumer, uses concepts from Event Tracing for Windows, and introduces new concepts.</span></span>  
  
 <span data-ttu-id="671f4-110">A tabela a seguir descreve os conceitos em Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="671f4-110">The following table describes the concepts in Extended Events.</span></span>  
  
|<span data-ttu-id="671f4-111">Tópico</span><span class="sxs-lookup"><span data-stu-id="671f4-111">Topic</span></span>|<span data-ttu-id="671f4-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="671f4-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="671f4-113">Pacotes de eventos estendidos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="671f4-113">SQL Server Extended Events Packages</span></span>](sql-server-extended-events-packages.md)|<span data-ttu-id="671f4-114">Descreve os pacotes de Eventos Estendidos que contêm objetos usados para obter e processar dados quando uma sessão de Eventos Estendidos é executada.</span><span class="sxs-lookup"><span data-stu-id="671f4-114">Describes the Extended Events packages that contain objects that are used for obtaining and processing data when an Extended Events session is running.</span></span>|  
|[<span data-ttu-id="671f4-115">Destinos de eventos estendidos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="671f4-115">SQL Server Extended Events Targets</span></span>](../../database-engine/sql-server-extended-events-targets.md)|<span data-ttu-id="671f4-116">Descreve os consumidores de evento que podem receber dados durante uma sessão de evento.</span><span class="sxs-lookup"><span data-stu-id="671f4-116">Describes the event consumers that can receive data during an event session.</span></span>|  
|[<span data-ttu-id="671f4-117">Mecanismo de eventos estendidos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="671f4-117">SQL Server Extended Events Engine</span></span>](sql-server-extended-events-engine.md)|<span data-ttu-id="671f4-118">Descreve o mecanismo que implementa e gerencia uma sessão de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="671f4-118">Describes the engine that implements and manages an Extended Events session.</span></span>|  
|[<span data-ttu-id="671f4-119">Sessões de eventos estendidos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="671f4-119">SQL Server Extended Events Sessions</span></span>](sql-server-extended-events-sessions.md)|<span data-ttu-id="671f4-120">Descreve a sessão de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="671f4-120">Describes the Extended Events session.</span></span>|  
  
## <a name="extended-events-architecture"></a><span data-ttu-id="671f4-121">Arquitetura de eventos estendidos</span><span class="sxs-lookup"><span data-stu-id="671f4-121">Extended Events Architecture</span></span>  
 <span data-ttu-id="671f4-122">Os Eventos Estendidos são um sistema geral de manipulação de eventos para sistemas de servidores.</span><span class="sxs-lookup"><span data-stu-id="671f4-122">Extended Events (Extended Events) is a general event-handling system for server systems.</span></span> <span data-ttu-id="671f4-123">A infraestrutura de Eventos Estendidos oferece suporte à correlação de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]e, em certas condições, à correlação de dados entre sistema operacional e aplicativos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="671f4-123">The Extended Events infrastructure supports the correlation of data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and under certain conditions, the correlation of data from the operating system and database applications.</span></span> <span data-ttu-id="671f4-124">No último caso, a saída dos Eventos Estendidos deve ser direcionada para o ETW (Rastreamento de Eventos do Windows) a fim de correlacionar dados de evento com o sistema operacional ou os dados de evento do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="671f4-124">In the latter case, Extended Events output must be directed to Event Tracing for Windows (ETW) to correlate the event data with operating system or application event data.</span></span>  
  
 <span data-ttu-id="671f4-125">Todos os aplicativos têm pontos de execução que são úteis dentro e fora de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="671f4-125">All applications have execution points that are useful both inside and outside an application.</span></span> <span data-ttu-id="671f4-126">Dentro do aplicativo, o processamento assíncrono pode ser enfileirado usando informações coletadas durante a execução inicial de uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="671f4-126">Inside the application, asynchronous processing may be enqueued using information that is collected during the initial execution of a task.</span></span> <span data-ttu-id="671f4-127">Fora do aplicativo, pontos de execução fornecem utilitários de monitoramento com informações sobre as características comportamentais e de desempenho do aplicativo monitorado.</span><span class="sxs-lookup"><span data-stu-id="671f4-127">Outside the application, execution points provide monitoring utilities with information about the behavioral and performance characteristics of the monitored application.</span></span>  
  
 <span data-ttu-id="671f4-128">O sistema Eventos Estendidos oferece suporte a dados de evento fora de um processo.</span><span class="sxs-lookup"><span data-stu-id="671f4-128">Extended Events supports using event data outside a process.</span></span> <span data-ttu-id="671f4-129">Esses dados são geralmente usados por:</span><span class="sxs-lookup"><span data-stu-id="671f4-129">This data is typically used by:</span></span>  
  
-   <span data-ttu-id="671f4-130">Ferramentas de rastreamento, como o Rastreamento do SQL e o Monitor do Sistema.</span><span class="sxs-lookup"><span data-stu-id="671f4-130">Tracing tools, such as SQL Trace and System Monitor.</span></span>  
  
-   <span data-ttu-id="671f4-131">Ferramentas de log, como o log de eventos do Windows ou o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="671f4-131">Logging tools, such as the Windows event log or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
-   <span data-ttu-id="671f4-132">Usuários que administram um produto ou desenvolvem aplicativos em um produto.</span><span class="sxs-lookup"><span data-stu-id="671f4-132">Users administering a product or developing applications on a product.</span></span>  
  
 <span data-ttu-id="671f4-133">Os Eventos Estendidos têm os estes aspectos de design principais:</span><span class="sxs-lookup"><span data-stu-id="671f4-133">Extended Events has the following key design aspects:</span></span>  
  
-   <span data-ttu-id="671f4-134">O mecanismo Eventos Estendidos é agnóstico.</span><span class="sxs-lookup"><span data-stu-id="671f4-134">The Extended Events engine is event agnostic.</span></span> <span data-ttu-id="671f4-135">Ele permite que o mecanismo associe qualquer evento a qualquer destino porque o mecanismo não é restrito ao conteúdo do evento.</span><span class="sxs-lookup"><span data-stu-id="671f4-135">This enables the engine to bind any event to any target because the engine is not constrained by event content.</span></span> <span data-ttu-id="671f4-136">Para obter mais informações sobre o mecanismo Eventos Estendidos, consulte [SQL Server Extended Events Engine](sql-server-extended-events-engine.md).</span><span class="sxs-lookup"><span data-stu-id="671f4-136">For more information about the Extended Events engine, see [SQL Server Extended Events Engine](sql-server-extended-events-engine.md).</span></span>  
  
-   <span data-ttu-id="671f4-137">Os eventos são separados dos consumidores de evento, que são chamados *destinos* em Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="671f4-137">Events are separated from event consumers, which are called *targets* in Extended Events.</span></span> <span data-ttu-id="671f4-138">Isso significa que qualquer destino pode receber qualquer evento.</span><span class="sxs-lookup"><span data-stu-id="671f4-138">This means that any target can receive any event.</span></span> <span data-ttu-id="671f4-139">Além disso, qualquer evento gerado pode ser consumido automaticamente pelo destino, que pode registrar em log ou fornecer contexto de evento adicional.</span><span class="sxs-lookup"><span data-stu-id="671f4-139">In addition, any event that is raised can be automatically consumed by the target, which can log or provide additional event context.</span></span> <span data-ttu-id="671f4-140">Para obter mais informações, consulte [SQL Server Extended Events Targets](../../database-engine/sql-server-extended-events-targets.md).</span><span class="sxs-lookup"><span data-stu-id="671f4-140">For more information, see [SQL Server Extended Events Targets](../../database-engine/sql-server-extended-events-targets.md).</span></span>  
  
-   <span data-ttu-id="671f4-141">Os eventos são distintos quanto à ação quando ocorre um evento.</span><span class="sxs-lookup"><span data-stu-id="671f4-141">Events are distinct from the action to take when an event occurs.</span></span> <span data-ttu-id="671f4-142">Portanto, qualquer ação pode ser associada a qualquer evento.</span><span class="sxs-lookup"><span data-stu-id="671f4-142">Therefore, any action can be associated with any event.</span></span>  
  
-   <span data-ttu-id="671f4-143">Os predicados podem filtrar dinamicamente quando os dados de evento devem ser capturados.</span><span class="sxs-lookup"><span data-stu-id="671f4-143">Predicates can dynamically filter when event data should be captured.</span></span> <span data-ttu-id="671f4-144">Isso confere flexibilidade à infraestrutura de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="671f4-144">This adds to the flexibility of the Extended Events infrastructure.</span></span> <span data-ttu-id="671f4-145">Para obter mais informações, consulte [SQL Server Extended Events Packages](sql-server-extended-events-packages.md).</span><span class="sxs-lookup"><span data-stu-id="671f4-145">For more information, see [SQL Server Extended Events Packages](sql-server-extended-events-packages.md).</span></span>  
  
 <span data-ttu-id="671f4-146">O mecanismo Eventos Estendidos pode gerar dados de evento de forma síncrona (e processar os dados de forma assíncrona) o que fornece uma solução flexível para manipulação de eventos.</span><span class="sxs-lookup"><span data-stu-id="671f4-146">Extended Events can synchronously generate event data (and asynchronously process that data) which provides a flexible solution for event handling.</span></span> <span data-ttu-id="671f4-147">Além disso, o mecanismo Eventos Estendidos fornece os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="671f4-147">In addition, Extended Events provides the following features:</span></span>  
  
-   <span data-ttu-id="671f4-148">Uma abordagem unificada no tratamento de eventos em todo o sistema de servidor, permitindo, ao mesmo tempo, que os usuários isolem eventos específicos com a finalidade de solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="671f4-148">A unified approach to handling events across the server system, while enabling users to isolate specific events for troubleshooting purposes.</span></span>  
  
-   <span data-ttu-id="671f4-149">Integração com e suporte às ferramentas de ETW existentes.</span><span class="sxs-lookup"><span data-stu-id="671f4-149">Integration with, and support for existing ETW tools.</span></span>  
  
-   <span data-ttu-id="671f4-150">Um mecanismo de tratamento de evento completamente configurável baseado no [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="671f4-150">A fully configurable event handling mechanism that is based on [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="671f4-151">A capacidade de monitorar processos ativos dinamicamente com efeito mínimo sobre esses processos.</span><span class="sxs-lookup"><span data-stu-id="671f4-151">The ability to dynamically monitor active processes, while having minimal effect on those processes.</span></span>  
  
-   <span data-ttu-id="671f4-152">Uma sessão de integridade de sistema padrão que é executada sem efeitos de desempenho notáveis.</span><span class="sxs-lookup"><span data-stu-id="671f4-152">A default system health session that runs without any noticeable performance effects.</span></span> <span data-ttu-id="671f4-153">A sessão coleta dados do sistema que você pode usar para ajudar a solucionar problemas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="671f4-153">The session collects system data that you can use to help troubleshoot performance issues.</span></span> <span data-ttu-id="671f4-154">Para obter mais informações, veja [Usar a sessão system_health](use-the-ssms-xe-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="671f4-154">For more information, see [Use the system_health Session](use-the-ssms-xe-profiler.md).</span></span>  
  
## <a name="extended-events-tasks"></a><span data-ttu-id="671f4-155">Tarefas de eventos estendidos</span><span class="sxs-lookup"><span data-stu-id="671f4-155">Extended Events Tasks</span></span>  
 <span data-ttu-id="671f4-156">Usando o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)] para executar instruções DDL, exibições e funções de gerenciamento dinâmico ou exibições de catálogo [!INCLUDE[tsql](../../includes/tsql-md.md)] , é possível criar soluções para problemas simples ou complexos de eventos estendidos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para seu ambiente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="671f4-156">Using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] to execute [!INCLUDE[tsql](../../includes/tsql-md.md)] Data Definition Language (DDL) statements, dynamic management views and functions, or catalog views, you can create simple or complex [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events troubleshooting solutions for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment.</span></span>  
  
|<span data-ttu-id="671f4-157">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="671f4-157">Task Description</span></span>|<span data-ttu-id="671f4-158">Tópico</span><span class="sxs-lookup"><span data-stu-id="671f4-158">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="671f4-159">Use o **Pesquisador de Objetos** para gerenciar sessões de eventos.</span><span class="sxs-lookup"><span data-stu-id="671f4-159">Use the **Object Explorer** to manage event sessions.</span></span>|[<span data-ttu-id="671f4-160">Gerenciar sessões de evento no Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="671f4-160">Manage Event Sessions in the Object Explorer</span></span>](../../ssms/object/object-explorer.md)|  
|<span data-ttu-id="671f4-161">Descreve como criar uma sessão de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="671f4-161">Describes how to create an Extended Events session.</span></span>|[<span data-ttu-id="671f4-162">Criar uma sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="671f4-162">Create an Extended Events Session</span></span>](../../database-engine/create-an-extended-events-session.md)|  
|<span data-ttu-id="671f4-163">Descreve como exibir e atualizar dados de destino.</span><span class="sxs-lookup"><span data-stu-id="671f4-163">Describes how to view and refresh target data.</span></span>|[<span data-ttu-id="671f4-164">Exibir dados de sessão de evento</span><span class="sxs-lookup"><span data-stu-id="671f4-164">View Event Session Data</span></span>](../../database-engine/view-event-session-data.md)|  
|<span data-ttu-id="671f4-165">Descreve como usar as ferramentas de Eventos Estendidos para criar e gerenciar suas sessões de Eventos Estendidos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="671f4-165">Describes how to use Extended Events tools to create and manage your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events sessions.</span></span>|[<span data-ttu-id="671f4-166">Ferramentas de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="671f4-166">Extended Events Tools</span></span>](extended-events-tools.md)|  
|<span data-ttu-id="671f4-167">Descreve como alterar uma sessão de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="671f4-167">Describes how to alter an Extended Events session.</span></span>|[<span data-ttu-id="671f4-168">Alterar uma sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="671f4-168">Alter an Extended Events Session</span></span>](alter-an-extended-events-session.md)|  
|<span data-ttu-id="671f4-169">Descreve como copiar ou exportar dados de destino.</span><span class="sxs-lookup"><span data-stu-id="671f4-169">Describes how to copy or export target data.</span></span>|[<span data-ttu-id="671f4-170">Copiar ou exportar dados de destino</span><span class="sxs-lookup"><span data-stu-id="671f4-170">Copy or Export Target Data</span></span>](../../database-engine/copy-or-export-target-data.md)|  
|<span data-ttu-id="671f4-171">Descreve como modificar sua exibição de resultados de rastreamento para personalizar como você deseja analisar seus dados.</span><span class="sxs-lookup"><span data-stu-id="671f4-171">Describes how to modify your trace results view to customize how you want to analyze your data.</span></span>|[<span data-ttu-id="671f4-172">Modificar a exibição dos resultados de rastreamento</span><span class="sxs-lookup"><span data-stu-id="671f4-172">Modify the Trace Results View</span></span>](../../database-engine/modify-the-trace-results-view.md)|  
|<span data-ttu-id="671f4-173">Descreve como obter informações sobre os campos associados aos eventos.</span><span class="sxs-lookup"><span data-stu-id="671f4-173">Describes how to get information about the fields associated with the events.</span></span>|[<span data-ttu-id="671f4-174">Obter os campos de todos os eventos</span><span class="sxs-lookup"><span data-stu-id="671f4-174">Get the Fields for All Events</span></span>](../../database-engine/get-the-fields-for-all-events.md)|  
|<span data-ttu-id="671f4-175">Descreve como descobrir quais eventos estão disponíveis nos pacotes registrados.</span><span class="sxs-lookup"><span data-stu-id="671f4-175">Describes how to find out what events are available in the registered packages.</span></span>|[<span data-ttu-id="671f4-176">Exibir os eventos de pacotes registrados</span><span class="sxs-lookup"><span data-stu-id="671f4-176">View the Events for Registered Packages</span></span>](../../database-engine/view-the-events-for-registered-packages.md)|  
|<span data-ttu-id="671f4-177">Descreve como determinar quais destinos de Eventos Estendidos estão disponíveis nos pacotes registrados.</span><span class="sxs-lookup"><span data-stu-id="671f4-177">Describes how to determine what Extended Events targets are available in the registered packages.</span></span>|[<span data-ttu-id="671f4-178">Exibir os destinos dos Eventos Estendidos de pacotes registrados</span><span class="sxs-lookup"><span data-stu-id="671f4-178">View the Extended Events Targets for Registered Packages</span></span>](../../database-engine/view-the-extended-events-targets-for-registered-packages.md)|  
|<span data-ttu-id="671f4-179">Descreve como exibir os eventos e as ações dos Eventos Estendidos que são equivalentes a cada evento de Rastreamento do SQL e suas colunas associadas.</span><span class="sxs-lookup"><span data-stu-id="671f4-179">Describes how to view the Extended Events events and actions that are equivalent to each SQL Trace event and its associated columns.</span></span>|[<span data-ttu-id="671f4-180">Exibir os Eventos Estendidos equivalentes às classes de rastreamento de eventos do SQL</span><span class="sxs-lookup"><span data-stu-id="671f4-180">View the Extended Events Equivalents to SQL Trace Event Classes</span></span>](view-the-extended-events-equivalents-to-sql-trace-event-classes.md)|  
|<span data-ttu-id="671f4-181">Descreve como localizar os parâmetros que você pode definir para o uso do argumento ADD TARGET em CREAT EVENT SESSION ou ALTER EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="671f4-181">Describes how to find the parameters you can set when you use the ADD TARGET argument in CREATE EVENT SESSION or ALTER EVENT SESSION.</span></span>|[<span data-ttu-id="671f4-182">Obter os parâmetros configuráveis para o argumento ADD TARGET</span><span class="sxs-lookup"><span data-stu-id="671f4-182">Get the Configurable Parameters for the ADD TARGET Argument</span></span>](../../database-engine/get-the-configurable-parameters-for-the-add-target-argument.md)|  
|<span data-ttu-id="671f4-183">Descreve como converter um script existente de Rastreamento do SQL em uma sessão de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="671f4-183">Describes how to convert an existing SQL Trace script to an Extended Events session.</span></span>|[<span data-ttu-id="671f4-184">Converter um script existente de Rastreamento do SQL em uma sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="671f4-184">Convert an Existing SQL Trace Script to an Extended Events Session</span></span>](convert-an-existing-sql-trace-script-to-an-extended-events-session.md)|  
|<span data-ttu-id="671f4-185">Descreve como determinar quais consultas estão mantendo o bloqueio, o plano da consulta e a pilha [!INCLUDE[tsql](../../includes/tsql-md.md)] no momento em que o bloqueio foi realizado.</span><span class="sxs-lookup"><span data-stu-id="671f4-185">Describes how to determine which queries are holding the lock, the plan of the query, and the [!INCLUDE[tsql](../../includes/tsql-md.md)] stack at the time the lock was taken.</span></span>|[<span data-ttu-id="671f4-186">Determinar quais consultas estão mantendo bloqueios</span><span class="sxs-lookup"><span data-stu-id="671f4-186">Determine Which Queries Are Holding Locks</span></span>](determine-which-queries-are-holding-locks.md)|  
|<span data-ttu-id="671f4-187">Descreve como identificar a origem de bloqueios que estão obstruindo o desempenho do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="671f4-187">Describes how to identify the source of locks that are hindering database performance.</span></span>|[<span data-ttu-id="671f4-188">Localizar os objetos que detêm a maioria dos bloqueios</span><span class="sxs-lookup"><span data-stu-id="671f4-188">Find the Objects That Have the Most Locks Taken on Them</span></span>](find-the-objects-that-have-the-most-locks-taken-on-them.md)|  
|<span data-ttu-id="671f4-189">Descreve como usar os Eventos Estendidos com o Rastreamento de Eventos do Windows para monitorar a atividade do sistema.</span><span class="sxs-lookup"><span data-stu-id="671f4-189">Describes how to use Extended Events with Event Tracing for Windows to monitor system activity.</span></span>|[<span data-ttu-id="671f4-190">Monitorar a atividade do sistema usando Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="671f4-190">Monitor System Activity Using Extended Events</span></span>](monitor-system-activity-using-extended-events.md)|  
  
## <a name="see-also"></a><span data-ttu-id="671f4-191">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="671f4-191">See Also</span></span>  
 <span data-ttu-id="671f4-192">[Aplicativos da Camada de Dados](../data-tier-applications/data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="671f4-192">[Data-tier Applications](../data-tier-applications/data-tier-applications.md) </span></span>  
 <span data-ttu-id="671f4-193">[Suporte de DAC para objetos e versões SQL Server](../data-tier-applications/dac-support-for-sql-server-objects-and-versions.md) </span><span class="sxs-lookup"><span data-stu-id="671f4-193">[DAC Support For SQL Server Objects and Versions](../data-tier-applications/dac-support-for-sql-server-objects-and-versions.md) </span></span>  
 <span data-ttu-id="671f4-194">[Implantar um aplicativo da camada de dados](../data-tier-applications/deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="671f4-194">[Deploy a Data-tier Application](../data-tier-applications/deploy-a-data-tier-application.md) </span></span>  
 <span data-ttu-id="671f4-195">[Monitorar aplicativos da camada de dados](../data-tier-applications/monitor-data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="671f4-195">[Monitor Data-tier Applications](../data-tier-applications/monitor-data-tier-applications.md) </span></span>  
 <span data-ttu-id="671f4-196">[Exibições de gerenciamento dinâmico de eventos estendidos](../views/views.md) </span><span class="sxs-lookup"><span data-stu-id="671f4-196">[Extended Events Dynamic Management Views](../views/views.md) </span></span>  
 <span data-ttu-id="671f4-197">[Exibições do catálogo de eventos estendidos &#40;&#41; Transact-SQL] (~/Relational-databases/System-Catalog-views/Extended-Events-Catalog-views-Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="671f4-197">[Extended Events Catalog Views &#40;Transact-SQL&#41;](~/relational-databases/system-catalog-views/extended-events-catalog-views-transact-sql</span></span>  
  
  