---
title: Introdução ao monitoramento de Analysis Services com SQL Server Profiler | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, Analysis Services
- monitoring Analysis Services [SQL Server]
- performance [Analysis Services]
- performance [Analysis Services], SQL Server Profiler
- Profiler [SQL Server Profiler], Analysis Services
ms.assetid: 568ec549-5ddc-493a-b9f8-3bdc548b562e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9e6275e9192f52c646793aed2e0273d418f42f2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576047"
---
# <a name="introduction-to-monitoring-analysis-services-with-sql-server-profiler"></a><span data-ttu-id="5c616-102">Introdução ao monitoramento do Analysis Services com o SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="5c616-102">Introduction to Monitoring Analysis Services with SQL Server Profiler</span></span>
  <span data-ttu-id="5c616-103">Você pode usar [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] o para monitorar eventos gerados por uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5c616-103">You can use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to monitor events generated by an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="5c616-104">Usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5c616-104">By using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can do the following:</span></span>  
  
-   <span data-ttu-id="5c616-105">Monitorar o desempenho de uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c616-105">Monitor the performance of an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="5c616-106">Depurar as instruções da linguagem MDX.</span><span class="sxs-lookup"><span data-stu-id="5c616-106">Debug Multidimensional Expressions (MDX) statements.</span></span>  
  
-   <span data-ttu-id="5c616-107">Identificar as instruções MDX executadas lentamente.</span><span class="sxs-lookup"><span data-stu-id="5c616-107">Identify MDX statements that run slowly.</span></span>  
  
-   <span data-ttu-id="5c616-108">Testar as instruções MDX na fase de desenvolvimento de um projeto, percorrendo as instruções para confirmar se o código funciona conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="5c616-108">Test MDX statements in the development phase of a project by stepping through statements to confirm that the code works as expected.</span></span>  
  
-   <span data-ttu-id="5c616-109">Solucionar problemas no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] capturando eventos em um sistema de produção e repeti-los em um sistema de teste.</span><span class="sxs-lookup"><span data-stu-id="5c616-109">Troubleshoot problems in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by capturing events on a production system and replaying them on a test system.</span></span> <span data-ttu-id="5c616-110">Essa abordagem é útil para testar ou depurar propósitos e permite que os usuários continuem a usar o sistema de produção sem interferência.</span><span class="sxs-lookup"><span data-stu-id="5c616-110">This approach is useful for testing or debugging purposes and lets users continue to use the production system without interference.</span></span>  
  
-   <span data-ttu-id="5c616-111">Auditar e revisar atividades ocorridas em uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c616-111">Audit and review activity that occurred on an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="5c616-112">Um administrador de segurança pode revisar qualquer um dos eventos auditados.</span><span class="sxs-lookup"><span data-stu-id="5c616-112">A security administrator can review any one of the audited events.</span></span> <span data-ttu-id="5c616-113">A revisão inclui o êxito ou a falha de uma tentativa de logon e o êxito ou a falha das permissões ao acessar instruções e objetos.</span><span class="sxs-lookup"><span data-stu-id="5c616-113">This includes the success or failure of a login try and the success or failure of permissions in accessing statements and objects.</span></span>  
  
-   <span data-ttu-id="5c616-114">Exibir dados sobre os eventos capturados na tela ou capturar e salvar dados sobre cada evento em um arquivo ou na tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para análise ou reprodução futura.</span><span class="sxs-lookup"><span data-stu-id="5c616-114">Display data about the captured events to the screen, or capture and save data about each event to a file or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table for future analysis or playback.</span></span> <span data-ttu-id="5c616-115">Ao repetir os dados, é possível executar novamente os eventos salvos conforme ocorreram originalmente, seja em tempo real ou passo a passo.</span><span class="sxs-lookup"><span data-stu-id="5c616-115">When you replay data, you can rerun the saved events as they originally occurred, either in real time or step by step.</span></span>  
  
## <a name="using-sql-server-profiler"></a><span data-ttu-id="5c616-116">Usando o SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="5c616-116">Using SQL Server Profiler</span></span>  
 <span data-ttu-id="5c616-117">Para usar o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para criar ou repetir rastreamentos, você deve ser um membro da função de servidor [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5c616-117">To use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to create or replay traces, you must be a member of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server role.</span></span> <span data-ttu-id="5c616-118">Se você for um membro da função de servidor [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , inicie o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] a partir do grupo de programas [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no menu **Iniciar** .</span><span class="sxs-lookup"><span data-stu-id="5c616-118">If you are a member of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server role, you can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] program group on the **Start** menu.</span></span>  
  
 <span data-ttu-id="5c616-119">Ao usar o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5c616-119">When you use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], note the following:</span></span>  
  
-   <span data-ttu-id="5c616-120">As definições de rastreamento são armazenadas no banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usando a instrução CREATE.</span><span class="sxs-lookup"><span data-stu-id="5c616-120">Trace definitions are stored with the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database by using the CREATE statement.</span></span>  
  
-   <span data-ttu-id="5c616-121">Vários rastreamentos podem ser executados ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="5c616-121">Multiple traces can be running at the same time.</span></span>  
  
-   <span data-ttu-id="5c616-122">Várias conexões podem receber eventos do mesmo rastreamento.</span><span class="sxs-lookup"><span data-stu-id="5c616-122">Multiple connections can receive events from the same trace.</span></span>  
  
-   <span data-ttu-id="5c616-123">Um rastreamento pode continuar quando o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] parar e for reiniciado.</span><span class="sxs-lookup"><span data-stu-id="5c616-123">A trace can continue when [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stops and restarts.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5c616-124">As senhas não são reveladas em eventos de rastreamento, mas são substituídas por \* \* \* \* \* \* no evento.</span><span class="sxs-lookup"><span data-stu-id="5c616-124">Passwords are not revealed in trace events, but are replaced by \*\*\*\*\*\* in the event.</span></span>  
  
 <span data-ttu-id="5c616-125">Para obter o desempenho ideal, use o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para monitorar somente os eventos pelos quais você tem maior interesse.</span><span class="sxs-lookup"><span data-stu-id="5c616-125">For optimal performance, use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to monitor only those events in which you are most interested.</span></span> <span data-ttu-id="5c616-126">O monitoramento de muitos eventos pode causar sobrecarga e aumentar muito a tabela ou o arquivo de rastreamento, especialmente durante o monitoramento em um longo período de tempo.</span><span class="sxs-lookup"><span data-stu-id="5c616-126">Monitoring too many events adds overhead and can cause the trace file or table to grow very large, especially when you monitor over a long period of time.</span></span> <span data-ttu-id="5c616-127">Além disso, use a filtragem para limitar a quantidade de dados coletados e impedir o aumento em excesso dos rastreamentos.</span><span class="sxs-lookup"><span data-stu-id="5c616-127">In addition, use filtering to limit the amount of data that is collected and to prevent traces from becoming too large.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c616-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5c616-128">See Also</span></span>  
 <span data-ttu-id="5c616-129">[Eventos de rastreamento de Analysis Services](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events) </span><span class="sxs-lookup"><span data-stu-id="5c616-129">[Analysis Services Trace Events](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events) </span></span>  
 [<span data-ttu-id="5c616-130">Criar rastreamentos do Profiler para reprodução &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c616-130">Create Profiler Traces for Replay &#40;Analysis Services&#41;</span></span>](create-profiler-traces-for-replay-analysis-services.md)  
  
  