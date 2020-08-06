---
title: Monitorar o uso de memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- tuning databases [SQL Server], memory
- monitoring server performance [SQL Server], memory usage
- isolating memory [SQL Server]
- paging rate [SQL Server]
- memory [SQL Server], monitoring usage
- monitoring [SQL Server], memory usage
- low-memory conditions
- database monitoring [SQL Server], memory usage
- available memory [SQL Server]
- page faults [SQL Server]
- monitoring performance [SQL Server], memory usage
- server performance [SQL Server], memory
ms.assetid: 1aee3933-a11c-4b87-91b7-32f5ea38c87f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1986d9576f9b067cad18f27d4febbf097ed52703
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684667"
---
# <a name="monitor-memory-usage"></a>Monitorar o uso da memória
  Monitore uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodicamente para confirmar que o uso de memória está dentro de intervalos normais.  
  
 Para monitorar uma condição da memória baixa, use os seguintes contadores de objetos:  
  
-   **Memória: Bytes Disponíveis**  
  
-   **Memória: Páginas/segundo**  
  
 O contador **Bytes disponíveis** indica quantos bytes de memória estão atualmente disponíveis para uso dos processos. O contador **Páginas/s** indica o número de páginas que foram recuperadas do disco devido a falhas de página física ou gravadas no disco para liberar espaço no conjunto de trabalho devido a falhas de página.  
  
 Baixos valores no contador **Bytes disponíveis** podem indicar a existência de uma escassez global de memória no computador ou que um aplicativo não está liberando a memória. Uma taxa alta no contador **Páginas/s** pode indicar paginação excessiva. Monitore o contador **Memória: Falhas de página/segundo** para ter certeza de que a atividade no disco não é provocada por paginação.  
  
 Uma taxa baixa de paginação (e, logo, de falhas de página) é normal, mesmo que o computador tenha muita memória disponível. O Gerenciador de Memória Virtual (VMM) do Microsoft Windows conta as páginas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e de outros processos, organizando os tamanhos de conjunto de trabalho desses processos. Essa atividade do VMM tende a causar falhas de página. Para determinar se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou outro processo é a causa da paginação excessiva, monitore o contador **Processo: Falhas de página/segundo** para a instância de processo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 Para obter mais informações sobre como solucionar a paginação excessiva, consulte a documentação do sistema operacional Windows.  
  
## <a name="isolating-memory-used-by-sql-server"></a>Isolando a memória usada pelo SQL Server  
 Por padrão, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] altera seus requisitos de memória dinamicamente, com base nos recursos de sistema disponíveis. Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precisar de mais memória, ele consultará o sistema operacional para determinar se há memória física livre disponível e a usará. Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não precisar da memória alocada para ele atualmente, ele a liberará para o sistema operacional. Porém, é possível substituir a opção de usar a memória dinamicamente, por meio das opções de configuração de servidor **minservermemory**e **maxservermemory** . Para obter mais informações, consulte [Opções de memória do servidor](../../database-engine/configure-windows/server-memory-server-configuration-options.md).  
  
 Para monitorar a quantidade de memória utilizada pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , examine os seguintes contadores de desempenho:  
  
-   **Processo: Conjunto de trabalho**  
  
-   **SQL Server: Gerenciador de buffer: Índice de Ocorrências no Cache do Buffer**  
  
-   **SQL Server: Gerenciador de buffer: Páginas do Banco de Dados**  
  
-   **SQL Server: Gerenciador de memória: Memória Total do Servidor (KB)**  
  
 O contador **WorkingSet** mostra a quantidade de memória utilizada por um processo. Se esse número estiver consistentemente abaixo da quantidade de memória definida pelas opções de servidor **min server memory** e **max server memory** , o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está configurado para usar memória demais.  
  
 O contador **Taxa de acertos do cache do buffer** é específico ao aplicativo. Porém, uma taxa de 90 por cento ou mais é desejável. Adicione memória até que o valor seja consistentemente maior que 90%. Um valor maior que 90% indica que mais de 90% de todas as solicitações de dados foram satisfeitas pelo cache de dados.  
  
 Se o contador **TotalServerMemory (KB)** estiver consistentemente alto, em comparação com a quantidade de memória física disponível no computador, isso pode indicar a necessidade de mais memória.  
  
## <a name="determining-current-memory-allocation"></a>Determinando a alocação de memória atual  
 A instrução a seguir retorna informações sobre a memória alocada atualmente.  
  
```  
SELECT  
(physical_memory_in_use_kb/1024) AS Memory_usedby_Sqlserver_MB,  
(locked_page_allocations_kb/1024) AS Locked_pages_used_Sqlserver_MB,  
(total_virtual_address_space_kb/1024) AS Total_VAS_in_MB,  
process_physical_memory_low,  
process_virtual_memory_low  
FROM sys.dm_os_process_memory;  
```  
  
  
