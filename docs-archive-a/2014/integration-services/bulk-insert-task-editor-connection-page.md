---
title: Editor da tarefa inserção em massa (página conexão) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.bulkinserttask.connection.f1
helpviewer_keywords:
- Bulk Insert Task Editor
ms.assetid: 51252c20-8865-4ede-a3fd-bd73a968f47d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b2cd722fd8520ff011c0d57040a55d624178e15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684306"
---
# <a name="bulk-insert-task-editor-connection-page"></a>Editor da Tarefa Inserção em Massa (página Conexão)
  Use a página **Conexão** da caixa de diálogo **Editor da Tarefa Inserção em Massa** para especificar a origem e o destino da operação de inserção em massa e o formato a ser usado.  
  
 Para saber mais sobre como trabalhar com inserções em massa, consulte [Tarefa Inserção em Massa](control-flow/bulk-insert-task.md) e [Arquivos de formato para importação ou exportação de dados &#40;SQL Server&#41;](../relational-databases/import-export/format-files-for-importing-or-exporting-data-sql-server.md).  
  
## <a name="options"></a>Opções  
 **Conexão**  
 Selecione um gerenciador de conexões OLE DB na lista ou clique em \<**New connection...**> para criar uma conexão.  
  
 **Tópicos relacionados:** [Gerenciador de conexões OLE DB](connection-manager/ole-db-connection-manager.md), [Configurar Gerenciador de Conexões OLE DB](../../2014/integration-services/configure-ole-db-connection-manager.md)  
  
 **Tabela de Destino**  
 Digite o nome da tabela ou exibição de destino ou selecione uma tabela ou exibição na lista.  
  
 **Formato**  
 Selecione a fonte do formato para a inserção em massa. As opções dessa propriedade são listadas na tabela a seguir.  
  
|Valor|Descrição|  
|-----------|-----------------|  
|**Usar Arquivo**|Selecione um arquivo que contém a especificação de formato. Selecionar esta opção faz com que seja exibida a opção dinâmica **Arquivo de Formato**.|  
|**Especificar**|Especifique o formato. A seleção dessa opção exibe as opções dinâmicas `RowDelimiter` e `ColumnDelimiter` .|  
  
 **Arquivo**  
 Selecione um gerenciador de conexões de Arquivo ou de Arquivo Simple na lista ou clique em \<**New connection...**> para criar uma conexão.  
  
 O local do arquivo está relacionado ao Mecanismo de Banco de Dados do SQL Server especificado no gerenciador de conexões para esta tarefa. O arquivo de texto deve ser acessível pelo Mecanismo de Banco de Dados do SQL Server em um disco rígido local no servidor, por um compartilhamento ou unidade mapeada para o SQL Server. O arquivo não pode ser acessado pelo Runtime do SSIS.  
  
 Se você acessa o arquivo de origem usando um gerenciador de conexões de Arquivo Simples, a tarefa de Inserção em Massa não usa o formato especificado no gerenciador de conexões de Arquivos Simples. Em vez disso, a tarefa de Inserção em massa usa o formato especificado em um arquivo de formato ou os valores das propriedades RowDelimiter e ColumnDelimiter da tarefa.  
  
 **Tópicos relacionados:** [Gerenciador de Conexões de Arquivo](connection-manager/file-connection-manager.md), [Editor do Gerenciador de Conexões de Arquivos](../../2014/integration-services/file-connection-manager-editor.md), [Editor do Gerenciador de Conexões de Arquivos Simples](connection-manager/flat-file-connection-manager.md), [Editor do Gerenciador de Conexões de Arquivos Simples &#40;Página Geral&#41;](general-page-of-integration-services-designers-options.md), [Editor do Gerenciador de Conexões de Arquivos Simples &#40;Página Colunas&#41](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md), [Editor do Gerenciador de Conexões de Arquivos Simples &#40;Página Avançado&#41](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md)  
  
 **Atualizar Tabelas**  
 Atualize a lista de tabelas e exibições.  
  
## <a name="format-dynamic-options"></a>Opções Dinâmicas de Formato  
  
### <a name="format--use-file"></a>Formato = Usar Arquivo  
 **Arquivo de Formato**  
 Digite o caminho do arquivo de formato ou clique no botão de reticências **(…)** para localizar o arquivo.  
  
### <a name="format--specify"></a>Formato = Especificar  
 `RowDelimiter`  
 Especifique o delimitador de linhas no arquivo de origem. O valor padrão é **{CR}{LF}** .  
  
 `ColumnDelimiter`  
 Especifique o delimitador de colunas no arquivo de origem. O padrão é **Tab**.  
  
## <a name="see-also"></a>Consulte Também  
 [Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor da tarefa inserção em massa &#40;página Geral&#41;](../../2014/integration-services/bulk-insert-task-editor-general-page.md)   
 [Editor da tarefa inserção em massa &#40;página opções&#41;](../../2014/integration-services/bulk-insert-task-editor-options-page.md)   
 [Página Expressões](expressions/expressions-page.md)   
 [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql)   
 [Fluxo de Controle](control-flow/control-flow.md)  
  
  
