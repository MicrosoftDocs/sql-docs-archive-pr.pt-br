---
title: Editor da tarefa inserção em massa (página Opções) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.bulkinserttask.options.f1
helpviewer_keywords:
- Bulk Insert Task Editor
ms.assetid: b3702811-3eb8-4b28-9190-5ae7a1a7bb6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1751d1e0ac01d5459a8c76e6a48626c2ad6deafd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684301"
---
# <a name="bulk-insert-task-editor-options-page"></a>Editor da Tarefa Inserção em Massa (página de Opções)
  Use a página **Opções** da caixa de diálogo **Editor da Tarefa Inserção em Massa** para definir as propriedades da operação de inserção em massa. A tarefa Bulk Insert copia uma grande quantidade de dados em uma exibição ou tabela do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].  
  
 Para saber mais sobre como trabalhar com inserções em massa, consulte [Tarefa Inserção em Massa](control-flow/bulk-insert-task.md) e [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).  
  
## <a name="options"></a>Opções  
 **CodePage**  
 Especifique a página de código dos dados no arquivo de dados.  
  
 **DataFileType**  
 Especifique o valor do tipo de dados a ser usado na operação de carregamento.  
  
 **BatchSize**  
 Especifique o número de linhas em um lote. O padrão é todo o arquivo de dados. Se você definir **BatchSize** para zero, os dados serão carregados em um único lote.  
  
 **LastRow**  
 Especifique a última linha a ser copiada.  
  
 **FirstRow**  
 Especifique a primeira linha da qual começar a copiar.  
  
 **Opções**  
 |Termo|Definição|  
|----------|----------------|  
|**Verificar restrições**|Selecione para verificar as restrições de tabelas e colunas.|  
|**Manter nulos**|Selecione para reter valores nulos durante a operação de inserção em massa, em vez de inserir qualquer valor padrão para colunas vazias.|  
|**Habilitar inserção de identidade**|Selecione para inserir valores existentes em uma coluna de identidade.|  
|**Bloqueio de tabela**|Selecione para bloquear a tabela durante a inserção em massa.|  
|**Acionadores**|Selecione para acionar qualquer inserção, atualização ou exclusão de gatilhos na tabela.|  
  
 **SortedData**  
 Especifique a cláusula ORDER BY na instrução de inserção em massa. O nome da coluna que você fornece deve ser uma coluna válida na tabela de destino. O padrão é `false`. Isto significa que os dados não são classificados por uma cláusula ORDER BY.  
  
 **MaxErrors**  
 Especifique o número máximo de erros que podem ocorrer antes que a operação de inserção em massa seja cancelada. Um valor de 0 indica que um número infinito de erros é permitido.  
  
> [!NOTE]  
>  Cada linha que não pode ser importada pela operação de carregamento em massa é contada como um erro.  
  
## <a name="see-also"></a>Consulte Também  
 [Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor da tarefa inserção em massa &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md)   
 [Editor da tarefa inserção em massa &#40;página conexão&#41;](../../2014/integration-services/bulk-insert-task-editor-connection-page.md)   
 [Página Expressões](expressions/expressions-page.md)   
 [Fluxo de Controle](control-flow/control-flow.md)  
  
  
