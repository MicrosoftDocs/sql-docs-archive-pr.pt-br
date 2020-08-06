---
title: Possíveis falhas durante o espelhamento de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- time-out period [SQL Server database mirroring]
- soft errors [SQL Server]
- database mirroring [SQL Server], troubleshooting
- timeout errors [SQL Server]
- troubleshooting [SQL Server], database mirroring
- hard errors
- failed database mirroring sessions [SQL Server]
ms.assetid: d7031f58-5f49-4e6d-9a62-9b420f2bb17e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 25ba1ccc87c024fa3da370f2ff19251a1bee9f30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681169"
---
# <a name="possible-failures-during-database-mirroring"></a><span data-ttu-id="4f1cf-102">Possíveis falhas durante espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="4f1cf-102">Possible Failures During Database Mirroring</span></span>
  <span data-ttu-id="4f1cf-103">Problemas físicos, do sistema operacional ou do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem causar uma falha em uma sessão de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-103">Physical, operating system, or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] problems can cause a failure in a database mirroring session.</span></span> <span data-ttu-id="4f1cf-104">O espelhamento de banco de dados não verifica regularmente os componentes dos quais o Sqlservr.exe depende para verificar se estão funcionando corretamente ou se houve falha.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-104">Database mirroring does not regularly check the components on which Sqlservr.exe relies to verify whether they are functioning correctly or have failed.</span></span> <span data-ttu-id="4f1cf-105">Porém, para alguns tipos de falhas, o componente afetado informa um erro ao Sqlservr.exe.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-105">However, for some types of failures, the affected component reports an error to Sqlservr.exe.</span></span> <span data-ttu-id="4f1cf-106">Um erro informado por outro componente é chamado um *erro de hardware*.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-106">An error reported by another component is called a *hard error*.</span></span> <span data-ttu-id="4f1cf-107">Para detectar outras falhas que de outra forma passariam despercebidas, o espelhamento de banco de dados implementa seu próprio mecanismo de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-107">To detect other failures that would otherwise go unnoticed, database mirroring implements its own time-out mechanism.</span></span> <span data-ttu-id="4f1cf-108">Quando ocorre um tempo limite de espelhamento, o espelhamento de banco de dados assume que ocorreu uma falha e declara um *erro de software*.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-108">When a mirroring time-out occurs, database mirroring assumes that a failure has occurred and declares a *soft error*.</span></span> <span data-ttu-id="4f1cf-109">Porém, algumas falhas que acontecem no nível da instância do SQL Server não causam espelhamento para tempo limite e podem não ser detectadas.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-109">However, some failures that happen at the SQL Server instance level do not cause mirroring to time-out and can go undetected.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4f1cf-110">Falhas em bancos de dados diferentes do banco de dados espelho não são detectáveis em uma sessão de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-110">Failures in databases other than the mirrored database are not detectable in a database mirroring session.</span></span> <span data-ttu-id="4f1cf-111">Além disso, é improvável que uma falha de disco de dados seja detectável, a menos que o banco de dados seja reiniciado por causa de uma falha no disco de dados.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-111">Moreover, a data disk failure is unlikely to be detected, unless the database is restarted because of a data disk failure.</span></span>  
  
 <span data-ttu-id="4f1cf-112">A velocidade da detecção de erro e, consequentemente, o tempo de reação da sessão de espelhamento a uma falha depende do tipo de falha: de hardware ou de software.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-112">The speed of error detection and, therefore, the reaction time of the mirroring session to a failure, depends on whether the error is hard or soft.</span></span> <span data-ttu-id="4f1cf-113">Alguns erros de hardware, como falhas de rede, são informados imediatamente.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-113">Some hard errors, such as network failures are reported immediately.</span></span> <span data-ttu-id="4f1cf-114">Porém, em alguns casos, períodos de tempo limite específicos do componente podem atrasar o relatório de alguns erros de hardware.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-114">However, in some cases, component-specific time-out periods can delay the reporting of some hard errors.</span></span> <span data-ttu-id="4f1cf-115">Para erros de software, a duração do período de tempo limite de espelhamento determina a velocidade de detecção de erros.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-115">For soft errors, the length of the mirroring time-out period determines the speed of error detection.</span></span> <span data-ttu-id="4f1cf-116">Por padrão, esse período é 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-116">By default, this period is 10 seconds.</span></span> <span data-ttu-id="4f1cf-117">Esse é o valor mínimo recomendado.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-117">This is the minimum recommended value.</span></span>  
  
## <a name="failures-due-to-hard-errors"></a><span data-ttu-id="4f1cf-118">Falhas devido a erros de hardware</span><span class="sxs-lookup"><span data-stu-id="4f1cf-118">Failures Due to Hard Errors</span></span>  
 <span data-ttu-id="4f1cf-119">As possíveis causas de erros de hardware incluem (mas não se limitam a) as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="4f1cf-119">Possible causes of hard errors include (but are not limited to) the following conditions:</span></span>  
  
-   <span data-ttu-id="4f1cf-120">Uma conexão ou um cabo interrompido</span><span class="sxs-lookup"><span data-stu-id="4f1cf-120">A broken connection or wire</span></span>  
  
-   <span data-ttu-id="4f1cf-121">Uma placa de rede incorreta</span><span class="sxs-lookup"><span data-stu-id="4f1cf-121">A bad network card</span></span>  
  
-   <span data-ttu-id="4f1cf-122">Uma alteração no roteador</span><span class="sxs-lookup"><span data-stu-id="4f1cf-122">A router change</span></span>  
  
-   <span data-ttu-id="4f1cf-123">Alterações no firewall</span><span class="sxs-lookup"><span data-stu-id="4f1cf-123">Changes in the firewall</span></span>  
  
-   <span data-ttu-id="4f1cf-124">Reconfiguração de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="4f1cf-124">Endpoint reconfiguration</span></span>  
  
-   <span data-ttu-id="4f1cf-125">Perda da unidade onde o log de transações reside</span><span class="sxs-lookup"><span data-stu-id="4f1cf-125">Loss of the drive where the transaction log resides</span></span>  
  
-   <span data-ttu-id="4f1cf-126">Falha de sistema operacional ou de processo</span><span class="sxs-lookup"><span data-stu-id="4f1cf-126">Operating system or process failure</span></span>  
  
 <span data-ttu-id="4f1cf-127">Por exemplo, quando a unidade de log do banco de dados principal deixar de responder e apresentar falha, o sistema operacional informa ao Sqlservr.exe que ocorreu um erro grave.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-127">For example, when the log drive on the principal database becomes unresponsive and fails, the operating system informs Sqlservr.exe that a serious error has occurred.</span></span>  
  
 <span data-ttu-id="4f1cf-128">Alguns componentes, como componentes de rede e alguns subsistemas de E/S, têm seus próprios tempos limite para determinar falhas.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-128">Some components, such as network components and some IO subsystems, have their own time-outs to determine failures.</span></span> <span data-ttu-id="4f1cf-129">Esses tempos limite são independentes do espelhamento de banco de dados, que não tem conhecimento sobre eles e não sabe absolutamente nada sobre seu comportamento.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-129">Such time-outs are independent of database mirroring, which has no knowledge of them and is completely unaware of their behavior.</span></span> <span data-ttu-id="4f1cf-130">Nesses casos o atraso do tempo limite aumenta o tempo entre uma falha e o momento em que o espelhamento do banco de dados recebe o erro de hardware resultante.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-130">In these cases, the time-out delay increases the time between a failure and when database mirroring receive the resulting hard error.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f1cf-131">A única verificação de erros ativa executada para espelhamento de banco de dados ocorre nos casos de erros de software.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-131">The only active error checking performed for database mirroring occurs for soft error cases.</span></span> <span data-ttu-id="4f1cf-132">Para obter mais informações, consulte "Falhas devido a erros de software", mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-132">For more information, see "Failures Due to Soft Errors," later in this topic.</span></span>  
  
 <span data-ttu-id="4f1cf-133">Para ajudar o usuário a interpretar as condições de erro que ocorrem na rede, pergunte a um engenheiro de rede quais são as mensagens de erro enviadas a uma porta quando os seguintes eventos ocorrem em uma conexão TCP:</span><span class="sxs-lookup"><span data-stu-id="4f1cf-133">To help you interpret the error conditions that occur on the network, ask a network engineer what error messages are sent to a port when the following events occur on a TCP connection:</span></span>  
  
-   <span data-ttu-id="4f1cf-134">DNS não está funcionando.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-134">DNS is not working.</span></span>  
  
-   <span data-ttu-id="4f1cf-135">Cabos estão desconectados.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-135">Cables are unplugged.</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="4f1cf-136">O Windows tem um firewall que bloqueia uma porta específica.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-136">Windows has a firewall that blocks a specific port.</span></span>  
  
-   <span data-ttu-id="4f1cf-137">Falha no aplicativo que está monitorando uma porta.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-137">The application that is monitoring a port fails.</span></span>  
  
-   <span data-ttu-id="4f1cf-138">Um servidor baseado no Windows é renomeado.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-138">A Windows-based server is renamed.</span></span>  
  
-   <span data-ttu-id="4f1cf-139">Um servidor baseado no Windows é reinicializado.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-139">A Windows-based server is rebooted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f1cf-140">O espelhamento não protege contra problemas específicos para clientes que acessam os servidores.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-140">Mirroring does not protect against problems specific to client accessing the servers.</span></span> <span data-ttu-id="4f1cf-141">Considere, por exemplo, um caso em que um adaptador de rede pública controla as conexões do cliente com a instância do servidor principal, enquanto uma placa de interface de rede privada controla todo o tráfego de espelhamento entre as instâncias do servidor.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-141">For example, consider a case in which a public network adapter handles client connections to the principal server instance, while a private network interface card handles all mirroring traffic among server instances.</span></span> <span data-ttu-id="4f1cf-142">Nesse caso, uma falha do adaptador de rede pública impediria os clientes de acessarem o banco de dados, embora o banco de dados continuasse a ser espelhado.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-142">In this case, failure of the public network adapter would prevent clients from accessing the database, though the database would continue to be mirrored.</span></span>  
  
## <a name="failures-due-to-soft-errors"></a><span data-ttu-id="4f1cf-143">Falhas devido a erros recuperáveis</span><span class="sxs-lookup"><span data-stu-id="4f1cf-143">Failures Due to Soft Errors</span></span>  
 <span data-ttu-id="4f1cf-144">Condições que poderiam ocasionar tempos-limite de espelhamento incluem (mas não se limitam a) o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4f1cf-144">Conditions that might cause mirroring time-outs include (but are not limited to) the following:</span></span>  
  
-   <span data-ttu-id="4f1cf-145">Erros de rede, como tempos-limite de link de TCP, pacotes descartados ou corrompidos ou pacotes que estão em ordem incorreta.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-145">Network errors such as TCP link time-outs, dropped or corrupted packets, or packets that are in an incorrect order.</span></span>  
  
-   <span data-ttu-id="4f1cf-146">Um sistema operacional, servidor ou banco de dados que não está respondendo.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-146">An operating system, server, or database that is not responding.</span></span>  
  
-   <span data-ttu-id="4f1cf-147">Um servidor Windows que atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-147">A Windows server timing out.</span></span>  
  
-   <span data-ttu-id="4f1cf-148">Recursos computacionais insuficientes, tais como sobrecarga de uma CPU ou disco, filling up do log de transações ou o sistema está sendo executado sem memória ou threads.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-148">Insufficient computing resources, such as a CPU or disk overload, the transaction log filling up, or the system is running out of memory or threads.</span></span> <span data-ttu-id="4f1cf-149">Nesses casos, é preciso aumentar o período de tempo limite, reduzir a carga de trabalho ou alterar o hardware para controlar a carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-149">In these cases, you must increase the time-out period, reduce the workload, or change the hardware to handle the workload.</span></span>  
  
### <a name="the-mirroring-time-out-mechanism"></a><span data-ttu-id="4f1cf-150">O mecanismo de tempo-limite de espelhamento</span><span class="sxs-lookup"><span data-stu-id="4f1cf-150">The Mirroring Time-Out Mechanism</span></span>  
 <span data-ttu-id="4f1cf-151">Como os erros recuperáveis não são diretamente detectáveis por uma instância do servidor, um erro recuperável poderia potencialmente fazer uma instância do servidor aguardar indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-151">Because soft errors are not detectable directly by a server instance, a soft error could potentially cause a server instance to wait indefinitely.</span></span> <span data-ttu-id="4f1cf-152">Para evitar isso, o espelhamento de banco de dados implementa seu próprio mecanismo de tempo-limite com base em cada instância do servidor em uma sessão de espelhamento enviando um ping em cada conexão aberta em um intervalo fixo.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-152">To prevent this, database mirroring implements its own time-out mechanism, based on each server instance in a mirroring session sending out a ping on each open connection at a fixed interval.</span></span>  
  
 <span data-ttu-id="4f1cf-153">Para manter uma conexão aberta, uma instância do servidor deve receber um ping naquela conexão dentro do período de tempo-limite definido, mais o tempo necessário para enviar um ou mais pings.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-153">To keep a connection open, a server instance must receive a ping on that connection in the time-out period defined, plus the time that is required to send one more ping.</span></span> <span data-ttu-id="4f1cf-154">A recepção de um ping durante o período de tempo-limite indica que a conexão ainda está aberta e que as instâncias do servidor estão se comunicando por ela.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-154">Receiving a ping during the time-out period indicates that the connection is still open and that the server instances are communicating over it.</span></span> <span data-ttu-id="4f1cf-155">Ao receber um ping, uma instância do servidor reajusta seu contador de tempo-limite naquela conexão.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-155">On receiving a ping, a server instance resets its time-out counter on that connection.</span></span>  
  
 <span data-ttu-id="4f1cf-156">Se nenhum ping for recebido em uma conexão durante o período de tempo-limite, uma instância do servidor considera que a conexão esgotou seu tempo limite. A instância do servidor encerra a conexão cujo tempo-limite está esgotado e controla o evento com tempo-limite esgotado de acordo com o estado e o modo de operação da sessão.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-156">If no ping is received on a connection during the time-out period, a server instance considers the connection to have timed out. The server instance closes the timed-out connection and handles the time-out event according to the state and operating mode of the session.</span></span>  
  
 <span data-ttu-id="4f1cf-157">Até mesmo se o outro servidor estiver de fato procedendo corretamente, um tempo-limite será considerado uma falha.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-157">Even if the other server is actually proceeding correctly, a time-out is considered a failure.</span></span> <span data-ttu-id="4f1cf-158">Se o valor do tempo-limite de uma sessão for muito pequeno para uma capacidade de resposta regular de um dos parceiros, podem ocorrer falsas falhas.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-158">If the time-out value for a session is too short for the regular responsiveness of either partner, false failures can occur.</span></span> <span data-ttu-id="4f1cf-159">Uma falsa falha ocorre quando uma instância do servidor contata com êxito outra instância cujo tempo de resposta é tão lento que seus pings não são recebidos antes da expiração do período de tempo-limite.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-159">A false failure occurs when one server instance successfully contacts another whose response time is so slow that its pings are not received before the time-out period expires.</span></span>  
  
 <span data-ttu-id="4f1cf-160">Em sessões de modo de grande desempenho, o período de tempo-limite é sempre 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-160">In high-performance mode sessions, the time-out period is always 10 seconds.</span></span> <span data-ttu-id="4f1cf-161">Esse tempo é geralmente suficiente para evitar falsas falhas.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-161">This is generally enough to avoid false failures.</span></span> <span data-ttu-id="4f1cf-162">Em sessões de modo da segurança alta, o período de tempo-limite padrão é 10 segundos, mas é possível alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-162">In high-safety mode sessions, the default time-out period is 10 seconds, but you can change the duration.</span></span> <span data-ttu-id="4f1cf-163">Para evitar falsas falhas, recomendamos que o período de tempo-limite de espelhamento seja sempre de 10 segundos ou mais.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-163">To avoid false failures, we recommend that the mirroring time-out period always be 10 seconds or more.</span></span>  
  
 <span data-ttu-id="4f1cf-164">**Para alterar o valor de tempo-limite (somente modo de segurança alta)**</span><span class="sxs-lookup"><span data-stu-id="4f1cf-164">**To change the time-out value (high-safety mode only)**</span></span>  
  
-   <span data-ttu-id="4f1cf-165">Use a instrução [ALTER DATABASE \<database> SET PARTNER TIMEOUT \<integer>](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4f1cf-165">Use the [ALTER DATABASE \<database> SET PARTNER TIMEOUT \<integer>](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="4f1cf-166">**Exibir o valor atual de tempo-limite**</span><span class="sxs-lookup"><span data-stu-id="4f1cf-166">**To view the current time-out value**</span></span>  
  
-   <span data-ttu-id="4f1cf-167">Consulte **mirroring_connection_timeout** em [sys.database_mirroring](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4f1cf-167">Query **mirroring_connection_timeout** in [sys.database_mirroring](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span></span>  
  
## <a name="responding-to-an-error"></a><span data-ttu-id="4f1cf-168">Respondendo a um erro</span><span class="sxs-lookup"><span data-stu-id="4f1cf-168">Responding to an Error</span></span>  
 <span data-ttu-id="4f1cf-169">Independentemente do tipo de erro, uma instância do servidor que detecta um erro responde adequadamente com base na função da instância, no modo de operação da sessão e no estado de qualquer outra conexão na sessão.</span><span class="sxs-lookup"><span data-stu-id="4f1cf-169">Regardless of the type of error, a server instance that detects an error responds appropriately based on the role of the instance, the operating mode of the session, and the state of any other connection in the session.</span></span> <span data-ttu-id="4f1cf-170">Para obter informações sobre o que ocorre na perda de um parceiro, consulte [Modos de operação de espelhamento de banco de dados](database-mirroring-operating-modes.md).</span><span class="sxs-lookup"><span data-stu-id="4f1cf-170">For information about what occurs on the loss of a partner, see [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f1cf-171">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4f1cf-171">See Also</span></span>  
 <span data-ttu-id="4f1cf-172">[Estimar a interrupção do serviço durante troca de função &#40;Espelhamento de Banco de Dados&#41;](estimate-the-interruption-of-service-during-role-switching-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="4f1cf-172">[Estimate the Interruption of Service During Role Switching &#40;Database Mirroring&#41;](estimate-the-interruption-of-service-during-role-switching-database-mirroring.md) </span></span>  
 <span data-ttu-id="4f1cf-173">[Modos de operação de espelhamento de banco de dados](database-mirroring-operating-modes.md) </span><span class="sxs-lookup"><span data-stu-id="4f1cf-173">[Database Mirroring Operating Modes](database-mirroring-operating-modes.md) </span></span>  
 <span data-ttu-id="4f1cf-174">[Troca de função durante uma sessão de espelhamento de banco de dados &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4f1cf-174">[Role Switching During a Database Mirroring Session &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md) </span></span>  
 [<span data-ttu-id="4f1cf-175">Espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4f1cf-175">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  