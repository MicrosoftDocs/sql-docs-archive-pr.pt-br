---
title: Opção de configuração de servidor blocked process threshold | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- thresholds [SQL Server]
- blocked process threshold option
ms.assetid: 3d46d143-bc6a-4220-8b55-6baa37547c25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9d5b61aaf23a8e74cb11afbf4e8bdb958fde6abe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683681"
---
# <a name="blocked-process-threshold-server-configuration-option"></a>Opção blocked process threshold de configuração de servidor
  Use a opção **blocked process threshold** para especificar o limite, em segundos, no qual os relatórios de processo bloqueado serão gerados. O limite pode ser definido de 0 a 86.400. Por padrão, não são produzidos relatórios de processo bloqueado. Esse evento não é gerado para tarefas de sistema ou tarefas que estão esperando recursos que não geram deadlocks detectáveis.  
  
 É possível definir um [alerta](../../ssms/agent/alerts.md) a ser executado quando esse evento é gerado. Assim, por exemplo, é possível optar por chamar o administrador para tomar medidas adequadas a fim de resolver a situação de bloqueio.  
  
 O limite de processo bloqueado utiliza o thread em segundo plano do monitor deadlock para orientar a lista de tarefas que esperam por um tempo maior ou vários limites configurados. O evento é gerado uma vez por intervalo de relatório para cada uma das tarefas bloqueadas.  
  
 O relatório de processo bloqueado é feito em uma melhor base de esforço. Não há nenhuma garantia de qualquer relatório em tempo real ou até mesmo próximo a tempo real.  
  
 A configuração entra em vigor imediatamente, sem que o servidor seja parado e reiniciado.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir define o `blocked process threshold` em `20` segundos, gerando um relatório de processo bloqueado para cada tarefa que é bloqueada.  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
sp_configure 'blocked process threshold', 20 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
## <a name="see-also"></a>Consulte Também  
 [sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)   
 [Classe de evento Blocked Process Report](../../relational-databases/event-classes/blocked-process-report-event-class.md)  
  
  
