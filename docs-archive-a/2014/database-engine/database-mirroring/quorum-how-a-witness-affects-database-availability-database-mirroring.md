---
title: 'Quorum: como uma testemunha afeta a disponibilidade do banco de dados (Espelhamento de Banco de Dados) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- quorum [SQL Server], database mirroring
- running exposed in database mirroring [SQL Server]
- witness-to-partner quorum [SQL Server]
- partners [SQL Server], partner-to-partner quorum
- witness [SQL Server], quorum
- have quorum [SQL Server]
- quorum [SQL Server]
- mirror database [SQL Server]
- full quorum [SQL Server]
- high-availability mode [SQL Server]
ms.assetid: a62d9dd7-3667-4751-a294-a61fc9caae7c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ada152f280a4ac75543f09e5f5afa7c72c0cbef6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681160"
---
# <a name="quorum-how-a-witness-affects-database-availability-database-mirroring"></a><span data-ttu-id="71a70-102">Quorum: como uma testemunha afeta a disponibilidade do banco de dados (Espelhamento de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="71a70-102">Quorum: How a Witness Affects Database Availability (Database Mirroring)</span></span>
  <span data-ttu-id="71a70-103">Sempre que uma testemunha é definida para uma sessão de espelhamento de banco de dados, é necessário usar o *quorum* .</span><span class="sxs-lookup"><span data-stu-id="71a70-103">Whenever a witness is set for a database mirroring session, *quorum* is required.</span></span> <span data-ttu-id="71a70-104">Quorum é a relação criada quando duas ou mais instâncias do servidor na sessão de espelhamento de banco de dados são conectadas entre si.</span><span class="sxs-lookup"><span data-stu-id="71a70-104">Quorum is a relationship that exists when two or more server instances in a database mirroring session are connected to each other.</span></span> <span data-ttu-id="71a70-105">Normalmente, o quorum envolve três instâncias do servidor interconectadas.</span><span class="sxs-lookup"><span data-stu-id="71a70-105">Typically, quorum involves three interconnected server instances.</span></span> <span data-ttu-id="71a70-106">Quando uma testemunha é definida, o quorum é exigido para tornar o banco de dados disponível.</span><span class="sxs-lookup"><span data-stu-id="71a70-106">When a witness is set, quorum is required to make the database available.</span></span> <span data-ttu-id="71a70-107">Desenvolvido para o modo de segurança alta com failover automático, o quorum verifica o banco de dados pertence a somente um parceiro por vez.</span><span class="sxs-lookup"><span data-stu-id="71a70-107">Designed for high-safety mode with automatic failover, quorum makes sure that a database is owned by only one partner at a time.</span></span>  
  
 <span data-ttu-id="71a70-108">Se uma determinada instância do servidor for desconectada da sessão de espelhamento, aquela instância perderá o quorum.</span><span class="sxs-lookup"><span data-stu-id="71a70-108">If a particular server instance becomes disconnected from a mirroring session, that instance loses quorum.</span></span> <span data-ttu-id="71a70-109">Se nenhuma instância do servidor estiver conectada, a sessão perderá quorum e o banco de dados ficará indisponível.</span><span class="sxs-lookup"><span data-stu-id="71a70-109">If no server instances are connected, the session loses quorum and the database becomes unavailable.</span></span> <span data-ttu-id="71a70-110">Há três tipos possíveis de quorum:</span><span class="sxs-lookup"><span data-stu-id="71a70-110">Three types of quorum are possible:</span></span>  
  
-   <span data-ttu-id="71a70-111">Um *quorum cheio* inclui parceiros e a testemunha.</span><span class="sxs-lookup"><span data-stu-id="71a70-111">A *full quorum* includes both partners and the witness.</span></span>  
  
-   <span data-ttu-id="71a70-112">Um *quorum testemunha a parceiro* consiste na testemunha e em qualquer parceiro.</span><span class="sxs-lookup"><span data-stu-id="71a70-112">A *witness-to-partner quorum* consists of the witness and either partner.</span></span>  
  
-   <span data-ttu-id="71a70-113">Um *quorum parceiro a parceiro* consiste em dois parceiros.</span><span class="sxs-lookup"><span data-stu-id="71a70-113">A *partner-to-partner quorum* consists of the two partners.</span></span>  
  
 <span data-ttu-id="71a70-114">A figura a seguir mostra esses tipos de quorum.</span><span class="sxs-lookup"><span data-stu-id="71a70-114">The following figure shows these types of quorum.</span></span>  
  
 <span data-ttu-id="71a70-115">![Quorums: completo; testemunha e parceiro; ambos os parceiros](../media/dbm-failovautoquorum.gif "Quorums: completo; testemunha e parceiro; ambos os parceiros")</span><span class="sxs-lookup"><span data-stu-id="71a70-115">![Quorums: full; witness and partner; both partners](../media/dbm-failovautoquorum.gif "Quorums: full; witness and partner; both partners")</span></span>  
  
 <span data-ttu-id="71a70-116">Enquanto o servidor principal atual tiver quorum, o servidor deterá a função de principal e continuará a servir o banco de dados, a menos que o proprietário do banco de dados execute um failover manual.</span><span class="sxs-lookup"><span data-stu-id="71a70-116">As long as the current principal server has quorum, this server owns the role of principal and continues to serve the database, unless the database owner performs a manual failover.</span></span> <span data-ttu-id="71a70-117">Se o servidor principal perder quorum, deixará de atender o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="71a70-117">If the principal server loses quorum, it stops serving the database.</span></span> <span data-ttu-id="71a70-118">O failover automático só será possível se o banco de dados principal perder quorum, garantindo que não está mais servindo o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="71a70-118">Automatic failover can occur only if the principal database has lost quorum, which guarantees that it is no longer serving the database.</span></span>  
  
 <span data-ttu-id="71a70-119">Uma instância de servidor desconectada salva sua mais recente função na sessão.</span><span class="sxs-lookup"><span data-stu-id="71a70-119">A disconnected server instance saves its most recent role in the session.</span></span> <span data-ttu-id="71a70-120">Normalmente, uma instância do servidor desconectada é reconectada à sessão ao ser reiniciada e ao recuperar quorum.</span><span class="sxs-lookup"><span data-stu-id="71a70-120">Typically, a disconnected server instance reconnects to the session when it restarts and regains quorum.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="71a70-121">A testemunha só deverá ser definida quando você pretender usar o modo da segurança alta com failover automático.</span><span class="sxs-lookup"><span data-stu-id="71a70-121">The witness should be set only when you intend to use high-safety mode with automatic failover.</span></span> <span data-ttu-id="71a70-122">Em modo de alto desempenho, para o qual uma testemunha nunca é requerida, recomendamos definir a propriedade WITNESS como OFF.</span><span class="sxs-lookup"><span data-stu-id="71a70-122">In high-performance mode, for which a witness is never required, we strongly recommend setting the WITNESS property to OFF.</span></span> <span data-ttu-id="71a70-123">Para obter informações sobre o impacto de uma testemunha no modo de alto desempenho, veja [Modos de operação de espelhamento de banco de dados](database-mirroring-operating-modes.md).</span><span class="sxs-lookup"><span data-stu-id="71a70-123">For information about the impact of a witness on high-performance mode, see [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span></span>  
  
## <a name="quorum-in-high-safety-mode-sessions"></a><span data-ttu-id="71a70-124">Quorum em sessões de modo de segurança alta</span><span class="sxs-lookup"><span data-stu-id="71a70-124">Quorum in High-Safety Mode Sessions</span></span>  
 <span data-ttu-id="71a70-125">No modo de segurança alta, o quorum permite o failover automático ao fornecer um contexto no qual as instâncias do servidor com quorum arbitram o parceiro que detém a função de principal.</span><span class="sxs-lookup"><span data-stu-id="71a70-125">In high-safety mode, quorum allows automatic failover by providing a context in which the server instances with quorum arbitrate which partner owns the role of principal.</span></span> <span data-ttu-id="71a70-126">O servidor principal atenderá o banco de dados, se o banco de dados tiver quorum.</span><span class="sxs-lookup"><span data-stu-id="71a70-126">The principal server serves the database if it has quorum.</span></span> <span data-ttu-id="71a70-127">Se o servidor principal perder quorum quando o servidor espelho sincronizado e a testemunha retiverem quorum, ocorrerá o failover automático.</span><span class="sxs-lookup"><span data-stu-id="71a70-127">If the principal server loses quorum when the synchronized mirror server and witness retain quorum, automatic failover occurs.</span></span>  
  
 <span data-ttu-id="71a70-128">Os cenários de quorum para modo da segurança alta são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="71a70-128">The quorum scenarios for high-safety mode are as follows:</span></span>  
  
-   <span data-ttu-id="71a70-129">Um *quorum cheio* que consiste em parceiros e a testemunha.</span><span class="sxs-lookup"><span data-stu-id="71a70-129">A *full quorum* that consists of both partners and the witness.</span></span>  
  
     <span data-ttu-id="71a70-130">Normalmente, todas as três instâncias do servidor participam de um quorum de três modos, chamado *quorum cheio*.</span><span class="sxs-lookup"><span data-stu-id="71a70-130">Ordinarily, all three server instances participate in a three-way quorum, called a *full quorum*.</span></span> <span data-ttu-id="71a70-131">Com quorum cheio, os servidores principal e espelho continuam executando as suas respectivas funções (a menos que ocorra um failover manual).</span><span class="sxs-lookup"><span data-stu-id="71a70-131">With a full quorum, the principal and mirror servers continue to perform their respective roles (unless manual failover occurs).</span></span>  
  
-   <span data-ttu-id="71a70-132">Um *quorum testemunha a parceiro* consiste na testemunha e em qualquer um dos parceiros.</span><span class="sxs-lookup"><span data-stu-id="71a70-132">A *witness-to-partner quorum* that consists of the witness and either partner.</span></span>  
  
     <span data-ttu-id="71a70-133">Se a conexão de rede entre os parceiros for perdida porque um dos parceiros foi perdido, há dois casos possíveis:</span><span class="sxs-lookup"><span data-stu-id="71a70-133">If the network connection between the partners is lost because one of the partners has been lost, the following cases are possible:</span></span>  
  
    -   <span data-ttu-id="71a70-134">O servidor espelho é perdido e o servidor principal e testemunha retêm quorum.</span><span class="sxs-lookup"><span data-stu-id="71a70-134">The mirror server is lost, and the principal server and witness retain quorum.</span></span>  
  
         <span data-ttu-id="71a70-135">Neste caso, o servidor principal define o seu banco de dados como DISCONNECTED e é executado com espelhamento no estado SUSPENDED.</span><span class="sxs-lookup"><span data-stu-id="71a70-135">In this case, the principal sets its database to DISCONNECTED and runs with mirroring in a SUSPENDED state.</span></span> <span data-ttu-id="71a70-136">(Isso é chamado *execução exposta*, porque o banco de dados não está sendo espelhado no momento.) Quando o servidor espelho reassocia-se à sessão, recupera o quorum como espelho e começa a sincronizar novamente a cópia do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="71a70-136">(This is referred to as *running exposed*, because the database is currently not being mirrored.) When the mirror server rejoins the session, the server regains quorum as mirror and starts resynchronizing its copy of the database.</span></span>  
  
    -   <span data-ttu-id="71a70-137">O servidor principal é perdido, e o servidor testemunha e espelho retêm quorum.</span><span class="sxs-lookup"><span data-stu-id="71a70-137">The principal server is lost, and the witness and the mirror server retain quorum.</span></span>  
  
         <span data-ttu-id="71a70-138">Nesse caso, ocorre o failover automático.</span><span class="sxs-lookup"><span data-stu-id="71a70-138">In this case, automatic failover occurs.</span></span> <span data-ttu-id="71a70-139">Para obter mais informações, consulte [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span><span class="sxs-lookup"><span data-stu-id="71a70-139">For more information, see [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span></span>  
  
    -   <span data-ttu-id="71a70-140">Todas as instâncias de servidor perdem quorum, mas subsequentemente o espelho e a testemunha são reconectados.</span><span class="sxs-lookup"><span data-stu-id="71a70-140">All the server instances lose quorum, but subsequently the mirror and witness reconnect.</span></span> <span data-ttu-id="71a70-141">O banco de dados não será servido neste caso.</span><span class="sxs-lookup"><span data-stu-id="71a70-141">The database will not be served in this case.</span></span>  
  
     <span data-ttu-id="71a70-142">Raramente, a conexão de rede entre parceiros de failover é perdida enquanto ambos os parceiros permanecem conectados à testemunha.</span><span class="sxs-lookup"><span data-stu-id="71a70-142">Rarely, the network connection between failover partners is lost while both partners remain connected to the witness.</span></span> <span data-ttu-id="71a70-143">Nesse evento, há dois quóruns individuais de testemunha a parceiro, sendo que a testemunha é o contato.</span><span class="sxs-lookup"><span data-stu-id="71a70-143">In this event, two, separate witness-to-partner quorums exist, with the witness as a liaison.</span></span> <span data-ttu-id="71a70-144">A testemunha informa ao servidor espelho que o servidor principal ainda está conectado.</span><span class="sxs-lookup"><span data-stu-id="71a70-144">The witness informs the mirror server that the principal server is still connected.</span></span> <span data-ttu-id="71a70-145">Então, o failover automático não acontece.</span><span class="sxs-lookup"><span data-stu-id="71a70-145">Therefore, automatic failover does not occur.</span></span> <span data-ttu-id="71a70-146">Ao contrário, o servidor espelho retém a função espelho e aguarda para reconectar-se ao servidor principal.</span><span class="sxs-lookup"><span data-stu-id="71a70-146">Instead, the mirror server retains the mirror role and waits to reconnect to the principal.</span></span> <span data-ttu-id="71a70-147">Nesse momento, se a fila de restauração contiver os registros de log, o servidor espelho continuará a efetuar o roll forward do banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="71a70-147">If the redo queue contains log records at this point, the mirror server continues to roll forward the mirror database.</span></span> <span data-ttu-id="71a70-148">Durante a reconexão, o servidor espelho sincronizará o banco de dados espelho novamente.</span><span class="sxs-lookup"><span data-stu-id="71a70-148">On reconnecting, the mirror server will resynchronize the mirror database.</span></span>  
  
-   <span data-ttu-id="71a70-149">Um *quorum parceiro a parceiro* consiste nos dois parceiros.</span><span class="sxs-lookup"><span data-stu-id="71a70-149">A *partner-to-partner quorum* that consists of the two partners.</span></span>  
  
     <span data-ttu-id="71a70-150">Enquanto os parceiros retiverem o quorum, o banco de dados continuará no estado SYNCHRONIZED e será possível executar o failover manual.</span><span class="sxs-lookup"><span data-stu-id="71a70-150">As long as the partners retain quorum, the database continues in a SYNCHRONIZED state, and manual failover remains possible.</span></span> <span data-ttu-id="71a70-151">Sem a testemunha, o failover automático não pode ser executado. Porém, quando a testemunha readquire o quorum, a sessão reinicia a operação regular e o failover automático pode ser executado novamente.</span><span class="sxs-lookup"><span data-stu-id="71a70-151">Without the witness, automatic failover is not possible; but when the witness regains quorum, the session resumes regular operation, and automatic failover is supported again.</span></span>  
  
-   <span data-ttu-id="71a70-152">A sessão perde quorum.</span><span class="sxs-lookup"><span data-stu-id="71a70-152">The session loses quorum.</span></span>  
  
     <span data-ttu-id="71a70-153">Se todas as instâncias do servidor forem desconectadas uma das outras, será considerado que a sessão *quorum perdido*.</span><span class="sxs-lookup"><span data-stu-id="71a70-153">If all the server instances become disconnected from each other, the session is said to have *lost quorum*.</span></span> <span data-ttu-id="71a70-154">Conforme as instâncias de servidor são reconectadas, elas readquirem quorum entre si.</span><span class="sxs-lookup"><span data-stu-id="71a70-154">As server instances reconnect to each other, they regain quorum with each other.</span></span>  
  
    -   <span data-ttu-id="71a70-155">Se o servidor principal se reconectar a qualquer uma das outras instâncias do servidor, o banco de dados ficará disponível.</span><span class="sxs-lookup"><span data-stu-id="71a70-155">If the principal server reconnects with either of the other server instances, the database becomes available.</span></span>  
  
    -   <span data-ttu-id="71a70-156">Se o servidor principal permanecer desconectado, mas o espelho e a testemunha forem reconectados, não será possível executar o failover automático, pois pode haver perda de dados.</span><span class="sxs-lookup"><span data-stu-id="71a70-156">If the principal server remains disconnected, but the mirror and witness reconnect to each other, automatic failover cannot occur because data loss might occur.</span></span> <span data-ttu-id="71a70-157">Por isso, o banco de dados permanecerá indisponível até que o servidor principal associe-se novamente à sessão.</span><span class="sxs-lookup"><span data-stu-id="71a70-157">Therefore, the database remains unavailable, until the principal server rejoins the session.</span></span>  
  
    -   <span data-ttu-id="71a70-158">Quando todas as três instâncias do servidor forem reconectadas, o quorum cheio será readquirido e a sessão retomará sua operação regular.</span><span class="sxs-lookup"><span data-stu-id="71a70-158">When all three server instances have reconnected, full quorum is regained, and the session resumes its regular operation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="71a70-159">Quando uma sessão tiver o quorum parceiro a parceiro, se qualquer parceiro perder quorum, a sessão perderá quorum.</span><span class="sxs-lookup"><span data-stu-id="71a70-159">When a session has a partner-to-partner quorum, if either partner loses quorum, the session loses quorum.</span></span> <span data-ttu-id="71a70-160">Consequentemente, caso pretenda deixar a testemunha desconectada por muito tempo, recomendamos a remoção temporária da testemunha da sessão.</span><span class="sxs-lookup"><span data-stu-id="71a70-160">Therefore, if you expect the witness to remain disconnected for lots of time, we recommend that you temporarily remove the witness from the session.</span></span> <span data-ttu-id="71a70-161">Ao remover a testemunha, os requisitos de quorum serão removidos.</span><span class="sxs-lookup"><span data-stu-id="71a70-161">Removing the witness removes the requirement for quorum.</span></span> <span data-ttu-id="71a70-162">Então, se o servidor espelho for desconectado, o servidor principal poderá continuar atendendo o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="71a70-162">Then, if the mirror server becomes disconnected, the principal server can continue to serve the database.</span></span> <span data-ttu-id="71a70-163">Para obter informações sobre como adicionar ou remover uma testemunha, veja [Testemunha de espelhamento de banco de dados](database-mirroring-witness.md).</span><span class="sxs-lookup"><span data-stu-id="71a70-163">For information about how to add or remove a witness, see [Database Mirroring Witness](database-mirroring-witness.md).</span></span>  
  
### <a name="how-quorum-affects-database-availability"></a><span data-ttu-id="71a70-164">Como o quorum afeta a disponibilidade do banco de dados</span><span class="sxs-lookup"><span data-stu-id="71a70-164">How Quorum Affects Database Availability</span></span>  
 <span data-ttu-id="71a70-165">A ilustração a seguir mostra como a testemunha e os parceiros cooperam para garantir que, em um determinado momento, somente um parceiro detenha a função de principal e apenas o servidor principal atual possa colocar o seu banco de dados online.</span><span class="sxs-lookup"><span data-stu-id="71a70-165">The following illustration shows how the witness and the partners cooperate to make sure that, at given time, only one partner owns the role of principal and only the current principal server can bring its database online.</span></span> <span data-ttu-id="71a70-166">Ambos os cenários iniciam com quorum completo, **Partner_A** na função principal e **Partner_B** na função espelho.</span><span class="sxs-lookup"><span data-stu-id="71a70-166">Both scenarios start with full quorum, and **Partner_A** in the principal role and **Partner_B** in the mirror role.</span></span>  
  
 <span data-ttu-id="71a70-167">![Como a testemunha e os parceiros cooperam](../media/dbm-quorum-scenarios.gif "Como a testemunha e os parceiros cooperam")</span><span class="sxs-lookup"><span data-stu-id="71a70-167">![How the witness and partners cooperate](../media/dbm-quorum-scenarios.gif "How the witness and partners cooperate")</span></span>  
  
 <span data-ttu-id="71a70-168">O cenário 1 mostra como, depois que o servidor principal (**Partner_A**) falha, a testemunha e o espelho concordam que o principal, **Partner_A**, não está mais disponível e formam quorum.</span><span class="sxs-lookup"><span data-stu-id="71a70-168">Scenario 1 shows how after the original principal server (**Partner_A**) fails, the witness and mirror agree that the principal, **Partner_A**, is not available any longer and form quorum.</span></span> <span data-ttu-id="71a70-169">O espelho, **Partner_B** , assume a função principal.</span><span class="sxs-lookup"><span data-stu-id="71a70-169">The mirror, **Partner_B** then assumes the principal role.</span></span> <span data-ttu-id="71a70-170">O failover automático ocorre e o **Partner_B**coloca sua cópia do banco de dados online.</span><span class="sxs-lookup"><span data-stu-id="71a70-170">Automatic failover occurs, and **Partner_B**, brings its copy of the database online.</span></span> <span data-ttu-id="71a70-171">Em seguida, **Partner_B** deixa de funcionar e o banco de dados fica offline.</span><span class="sxs-lookup"><span data-stu-id="71a70-171">Then **Partner_B** goes down, and the database goes offline.</span></span> <span data-ttu-id="71a70-172">Posteriormente, o antigo servidor principal, **Partner_A**, reconecta-se à testemunha readquirindo quorum. Porém, ao comunicar-se com a testemunha, **Partner_A** toma conhecimento de que não pode colocar a sua cópia do banco de dados online porque **Partner_B** agora detém a função principal.</span><span class="sxs-lookup"><span data-stu-id="71a70-172">Later, the former principal server, **Partner_A**, reconnects to the witness regaining quorum, but on communicating with the witness, **Partner_A** learns that it cannot bring its copy of the database online, because **Partner_B** now owns the principal role.</span></span> <span data-ttu-id="71a70-173">Quando o **Partner_B** reassocia-se à sessão, coloca o banco de dados online novamente.</span><span class="sxs-lookup"><span data-stu-id="71a70-173">When **Partner_B** rejoins the session, it brings the database back online.</span></span>  
  
 <span data-ttu-id="71a70-174">No cenário 2, a testemunha perde quorum, enquanto os parceiros, **Partner_A** e **Partner_B**, retêm quorum entre si e o banco de dados permanece online.</span><span class="sxs-lookup"><span data-stu-id="71a70-174">In Scenario 2, the witness loses quorum, while the partners, **Partner_A** and **Partner_B**, retain quorum with each other, and the database remains online.</span></span> <span data-ttu-id="71a70-175">Então, os parceiros também perdem quorum e o banco de dados fica offline.</span><span class="sxs-lookup"><span data-stu-id="71a70-175">Then the partners lose their quorum, too, and the database goes offline.</span></span> <span data-ttu-id="71a70-176">Mais tarde, o servidor principal, **Partner_A**, reconecta-se à testemunha, recuperando quorum.</span><span class="sxs-lookup"><span data-stu-id="71a70-176">Later, the principal server, **Partner_A**, reconnects to the witness regaining quorum.</span></span> <span data-ttu-id="71a70-177">A testemunha confirma se **Partner_A** ainda detém a função principal, e **Partner_A** coloca o banco de dados online.</span><span class="sxs-lookup"><span data-stu-id="71a70-177">The witness confirms that **Partner_A** still owns the principal role, and **Partner_A** brings the database back online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a70-178">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71a70-178">See Also</span></span>  
 <span data-ttu-id="71a70-179">[Modos de operação de espelhamento de banco de dados](database-mirroring-operating-modes.md) </span><span class="sxs-lookup"><span data-stu-id="71a70-179">[Database Mirroring Operating Modes](database-mirroring-operating-modes.md) </span></span>  
 <span data-ttu-id="71a70-180">[Troca de função durante uma sessão de espelhamento de banco de dados &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="71a70-180">[Role Switching During a Database Mirroring Session &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md) </span></span>  
 <span data-ttu-id="71a70-181">[Testemunha de espelhamento de banco de dados](database-mirroring-witness.md) </span><span class="sxs-lookup"><span data-stu-id="71a70-181">[Database Mirroring Witness](database-mirroring-witness.md) </span></span>  
 <span data-ttu-id="71a70-182">[Possíveis falhas durante o espelhamento de banco de dados](possible-failures-during-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="71a70-182">[Possible Failures During Database Mirroring](possible-failures-during-database-mirroring.md) </span></span>  
 [<span data-ttu-id="71a70-183">Estados de espelhamento &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71a70-183">Mirroring States &#40;SQL Server&#41;</span></span>](mirroring-states-sql-server.md)  
  
  