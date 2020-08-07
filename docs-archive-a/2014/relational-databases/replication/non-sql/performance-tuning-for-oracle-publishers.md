---
title: Ajuste de desempenho para Publicadores Oracle | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], performance tuning
ms.assetid: 32c0b4ec-c166-45a3-b41e-38a30fd56813
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 83d660eee839d525fa0bdabf88a313da0ed44244
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568447"
---
# <a name="performance-tuning-for-oracle-publishers"></a><span data-ttu-id="84873-102">Ajuste de desempenho para Editores Oracle</span><span class="sxs-lookup"><span data-stu-id="84873-102">Performance Tuning for Oracle Publishers</span></span>
  <span data-ttu-id="84873-103">A arquitetura de publicação Oracle é semelhante à arquitetura de publicação do [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , entretanto, a primeira etapa é ajustar a replicação Oracle para requisitos de desempenho, seguindo as recomendações gerais de ajuste encontradas em [Enhance General Replication Performance](../administration/enhance-general-replication-performance.md).</span><span class="sxs-lookup"><span data-stu-id="84873-103">The Oracle publishing architecture is similar to the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] publishing architecture; therefore the first step in tuning Oracle replication for performance requires following the general tuning recommendations found in [Enhance General Replication Performance](../administration/enhance-general-replication-performance.md).</span></span>  
  
 <span data-ttu-id="84873-104">Além disso há duas opções para Editores Oracle que estão relacionadas ao desempenho:</span><span class="sxs-lookup"><span data-stu-id="84873-104">In addition there are two options for Oracle Publishers that are performance related:</span></span>  
  
-   <span data-ttu-id="84873-105">Especificando a opção de publicação apropriada: Oracle ou Oracle Gateway.</span><span class="sxs-lookup"><span data-stu-id="84873-105">Specifying the appropriate publishing option: Oracle or Oracle Gateway.</span></span>  
  
-   <span data-ttu-id="84873-106">Configurando o trabalho de conjunto da transação para processar alterações no Publicador em um intervalo apropriado.</span><span class="sxs-lookup"><span data-stu-id="84873-106">Configuring the transaction set job to process changes on the Publisher at an appropriate interval.</span></span>  
  
## <a name="specifying-the-appropriate-publishing-option"></a><span data-ttu-id="84873-107">Especificando a opção Appropriate Publishing</span><span class="sxs-lookup"><span data-stu-id="84873-107">Specifying the Appropriate Publishing Option</span></span>  
 <span data-ttu-id="84873-108">A opção Oracle Gateway fornece desempenho melhorado em relação à opção Oracle Complete; entretanto, essa opção não pode ser usada para publicar a mesma tabela em várias publicações transacionais.</span><span class="sxs-lookup"><span data-stu-id="84873-108">The Oracle Gateway option provides improved performance over the Oracle Complete option; however, this option cannot be used to publish the same table in multiple transactional publications.</span></span> <span data-ttu-id="84873-109">Uma tabela pode aparecer no máximo em uma publicação transacional e em qualquer número de publicações de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="84873-109">A table can appear in at most one transactional publication and any number of snapshot publications.</span></span> <span data-ttu-id="84873-110">Se você precisa publicar a mesma tabela em várias publicações transacionais, escolha a opção Oracle Complete.</span><span class="sxs-lookup"><span data-stu-id="84873-110">If you need to publish the same table in multiple transactional publications, choose the Oracle Complete option.</span></span> <span data-ttu-id="84873-111">Especifique essa opção ao identificar o Editor Oracle no Distribuidor [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="84873-111">Specify this option when identifying the Oracle Publisher at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributor.</span></span> <span data-ttu-id="84873-112">Para obter mais informações, consulte [Create a Publication from an Oracle Database](../publish/create-a-publication-from-an-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="84873-112">For more information, see [Create a Publication from an Oracle Database](../publish/create-a-publication-from-an-oracle-database.md).</span></span>  
  
## <a name="configuring-the-transaction-set-job"></a><span data-ttu-id="84873-113">Configurando o trabalho de conjunto da transação</span><span class="sxs-lookup"><span data-stu-id="84873-113">Configuring the Transaction Set Job</span></span>  
 <span data-ttu-id="84873-114">As alterações em tabelas Oracle publicadas são processadas em grupos chamados conjuntos de transação.</span><span class="sxs-lookup"><span data-stu-id="84873-114">Changes to published Oracle tables are processed in groups called transaction sets.</span></span> <span data-ttu-id="84873-115">Para assegurar consistência transacional, cada conjunto de transação é confirmado como uma única transação no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="84873-115">To ensure transactional consistency, each transaction set is committed as a single transaction at the distribution database.</span></span> <span data-ttu-id="84873-116">Se o conjunto de transação ficar muito grande, não poderá ser processado eficazmente como uma única transação.</span><span class="sxs-lookup"><span data-stu-id="84873-116">If the transaction set becomes too large, it cannot be processed efficiently as a single transaction.</span></span>  
  
 <span data-ttu-id="84873-117">Por padrão, conjuntos de transação só são criados pelo Log Reader Agent.</span><span class="sxs-lookup"><span data-stu-id="84873-117">By default, transaction sets are created only by the Log Reader Agent.</span></span> <span data-ttu-id="84873-118">Se durante períodos da atividade de alta alteração,o Log Reader Agent não executar ou não conectar-se pelo Distribuidor [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ao Editor Oracle, os conjuntos da transação podem estar muito grandes.</span><span class="sxs-lookup"><span data-stu-id="84873-118">If, during periods of high change activity, the Log Reader Agent does not run or cannot connect from the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributor to the Oracle Publisher, transaction sets can become unmanageably large.</span></span> <span data-ttu-id="84873-119">Para evitar esse problema, certifique-se que os conjuntos da transação são criados em intervalos regulares, mesmo se o Log Reader Agent não executar ou não puder conectar-se ao Editor Oracle.</span><span class="sxs-lookup"><span data-stu-id="84873-119">To prevent this problem, ensure that transaction sets are created at regular intervals, even if the Log Reader Agent does not run or cannot connect to the Oracle Publisher.</span></span>  
  
 <span data-ttu-id="84873-120">Os conjuntos de transação podem ser criados com o trabalho de Xactset (um trabalho de banco de dados Oracle instalado por replicação), que usa o mesmo mecanismo que o Log Reader Agent usa para criar conjuntos.</span><span class="sxs-lookup"><span data-stu-id="84873-120">Transaction sets can be created with the Xactset job (an Oracle database job installed by replication), which uses the same mechanism that the Log Reader Agent does to create sets.</span></span> <span data-ttu-id="84873-121">Cada vez que o trabalho for executado, uma nova transação será criada.</span><span class="sxs-lookup"><span data-stu-id="84873-121">Each time the job runs, a new transaction set is created.</span></span> <span data-ttu-id="84873-122">Na próxima vez em que o Log Reader Agent for executado, o agente processará o conjunto que foi criado.</span><span class="sxs-lookup"><span data-stu-id="84873-122">The next time that the Log Reader Agent runs, the agent processes any sets that have been created.</span></span> <span data-ttu-id="84873-123">Se ainda existir alterações pendentes após todos os conjuntos de transações terem sido processados, o Log Reader Agent cria e processa um ou mais conjuntos de transações adicionais.</span><span class="sxs-lookup"><span data-stu-id="84873-123">If there are still pending changes after all existing transaction sets have been processed, the Log Reader Agent creates and processes one or more additional transaction sets.</span></span>  
  
 <span data-ttu-id="84873-124">Para configurar o trabalho do conjunto de transações, consulte [Configurar um Publicador Oracle no trabalho do conjunto de transações &#40;programação de Transact-SQL de replicação&#41;](../administration/configure-the-transaction-set-job-for-an-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="84873-124">To configure the transaction set job, see [Configure the Transaction Set Job for an Oracle Publisher &#40;Replication Transact-SQL Programming&#41;](../administration/configure-the-transaction-set-job-for-an-oracle-publisher.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84873-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="84873-125">See Also</span></span>  
 <span data-ttu-id="84873-126">[Configurar um Publicador Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="84873-126">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 [<span data-ttu-id="84873-127">Visão geral da publicação do Oracle</span><span class="sxs-lookup"><span data-stu-id="84873-127">Oracle Publishing Overview</span></span>](oracle-publishing-overview.md)  
  
  