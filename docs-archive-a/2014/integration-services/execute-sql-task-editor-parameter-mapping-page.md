---
title: Editor da tarefa Executar SQL (página mapeamento de parâmetros) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executesqltask.parametermapping.f1
helpviewer_keywords:
- Execute SQL Task Editor
ms.assetid: 8ebe020a-7921-46b2-8823-398748f379b2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cfbb4468cb69947dfa54fb519b7698286393d578
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572127"
---
# <a name="execute-sql-task-editor-parameter-mapping-page"></a>Editor da Tarefa Executar SQL (página Mapeamento de Parâmetros)
  Use a página **Mapeamento de Parâmetros** da caixa de diálogo **Editor da Tarefa Executar SQL** para mapear as variáveis para os parâmetros na instrução SQL.  
  
 Para saber mais sobre essa tarefa, consulte [Tarefa Executar SQL](control-flow/execute-sql-task.md) e [Parâmetros e códigos de retorno na Tarefa Executar SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).  
  
## <a name="options"></a>Opções  
 **Nome da Variável**  
 Após ter adicionado um mapeamento de parâmetros clicando em **Adicionar**, selecione uma variável de sistema ou definida pelo usuário na lista ou clique em \<**New variable...**> para adicionar uma nova variável usando a caixa de diálogo **Adicionar Variável**.  
  
 **Tópicos relacionados:** [Variáveis do SSIS &#40;Integration Services&#41;](integration-services-ssis-variables.md)  
  
 **Direção**  
 Selecione a direção do parâmetro. Mapeie cada variável para um parâmetro de entrada, parâmetro de saída ou um código de retorno.  
  
 **Tipo de Dados**  
 Selecione o tipo de dados do parâmetro. A lista de tipos de dados disponíveis é específica para o provedor selecionado no gerenciador de conexões usado pela tarefa.  
  
 **Nome do parâmetro**  
 Forneça um nome de parâmetro.  
  
 Dependendo do tipo de gerenciador de conexões usado pela tarefa, você deve usar números ou nomes de parâmetro. Alguns tipos de gerenciadores de conexões exigem que o primeiro caractere do nome do parâmetro seja o sinal \@, nomes específicos como \@Param1, ou nomes de coluna como nomes de parâmetro.  
  
 **Tópicos relacionados:** [Parâmetros e códigos de retorno na Tarefa Executar SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md)  
  
 **Tamanho do Parâmetro**  
 Informe o tamanho dos parâmetros com comprimento variável, como cadeias de caracteres e campos binários.  
  
 Esta configuração garante que o provedor aloque espaço suficiente para obter valores de parâmetro de comprimento variável.  
  
 **Adicionar**  
 Clique para adicionar um mapeamento de parâmetros.  
  
 **Remover**  
 Selecione um mapeamento de parâmetros na lista e clique em **Remover**.  
  
## <a name="see-also"></a>Consulte Também  
 [Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor da tarefa Executar SQL &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md)   
 [Editor da tarefa Executar SQL &#40;página conjunto de resultados&#41;](../../2014/integration-services/execute-sql-task-editor-result-set-page.md)   
 [Referência do Transact-SQL &#40;Mecanismo de Banco de Dados&#41;](/sql/t-sql/language-reference)  
  
  
