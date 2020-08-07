---
title: Editor da tarefa Transferir trabalhos (página trabalhos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferjobstask.jobs.f1
helpviewer_keywords:
- Transfer Jobs Task Editor
ms.assetid: e72b1dc7-8cda-4ee6-abb5-d438370f04df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d2d506da6997965e40d66521f7dccb8218e165fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584199"
---
# <a name="transfer-jobs-task-editor-jobs-page"></a>Editor da Tarefa Transferir Trabalhos (página Trabalhos)
  Use a página **Trabalhos** da caixa de diálogo **Editor da Tarefa de Transferir Trabalhos** para especificar as propriedades para cópia de um ou mais trabalhos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent de uma instância de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para outra. Para obter mais informações sobre a tarefa Transferir Trabalhos, consulte [Transfer Jobs Task](control-flow/transfer-jobs-task.md).  
  
> [!NOTE]  
>  Para acessar trabalhos no servidor de origem, é necessário que os usuários sejam membros pelo menos da função do banco de dados fixa **SQLAgentUserRole** no servidor. Para criar trabalhos no servidor de destino com êxito, é necessário que o usuário seja um membro da função de servidor fixa **sysadmin** ou uma das funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent. Para obter mais informações sobre as funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent e suas permissões, consulte [Funções de banco de dados fixas do SQL Server Agent](../ssms/agent/sql-server-agent-fixed-database-roles.md).  
  
## <a name="options"></a>Opções  
 **SourceConnection**  
 Selecione um gerenciador de conexões SMO na lista ou clique em **\<New connection...>** para criar uma conexão com o servidor de origem.  
  
 **DestinationConnection**  
 Selecione um gerenciador de conexões SMO na lista ou clique em **\<New connection...>** para criar uma conexão com o servidor de destino.  
  
 **TransferAllJobs**  
 Selecione se a tarefa deve copiar todas ou apenas os trabalhos de Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] especificados do servidor de origem para o servidor de destino.  
  
 As opções desta propriedade estão listadas na seguinte tabela:  
  
|Valor|Descrição|  
|-----------|-----------------|  
|**Verdadeiro**|Copia todas as tarefas.|  
|**Falso**|Copia apenas os trabalhos especificados.|  
  
 **JobsList**  
 Clique no botão Procurar **(...)** para selecionar os trabalhos a serem copiados. Pelo menos um trabalho deve ser selecionado.  
  
> [!NOTE]  
>  Especifique a **SourceConnection** antes de selecionar trabalhos para copiar.  
  
 A opção **JobsList** não estará disponível quando **TransferAllJobs** for definido como **True**.  
  
 **IfObjectExists**  
 Selecione como a tarefa deve tratar trabalhos que tenham o mesmo nome já existente no servidor de destino.  
  
 As opções desta propriedade estão listadas na seguinte tabela:  
  
|Valor|DESCRIÇÃO|  
|-----------|-----------------|  
|**FailTask**|A tarefa irá falhar se já existirem trabalhos com o mesmo nome no servidor de destino.|  
|**Overwrite**|A tarefa irá substituir trabalhos de mesmo nome no servidor de destino.|  
|**Ignorar**|A tarefa irá ignorar os trabalhos de mesmo nome que existem no servidor de destino.|  
  
 **EnableJobsAtDestination**  
 Selecione se os trabalhos copiados para o servidor de destino devem ser habilitados.  
  
 As opções desta propriedade estão listadas na seguinte tabela:  
  
|Valor|Descrição|  
|-----------|-----------------|  
|**Verdadeiro**|Habilita trabalhos no servidor de destino.|  
|**Falso**|Desabilita trabalhos no servidor de destino.|  
  
## <a name="see-also"></a>Consulte Também  
 [Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Tarefas do Integration Services](control-flow/integration-services-tasks.md)   
 [Editor da tarefa Transferir trabalhos &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md)   
 [Página Expressões](expressions/expressions-page.md)   
 [Gerenciador de Conexões SMO](connection-manager/smo-connection-manager.md)  
  
  
