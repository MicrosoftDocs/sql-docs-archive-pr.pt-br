---
title: Renomear tabelas de consultas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting tables
- removing tables
- dropping tables
- queries [SQL Server], tables
ms.assetid: 8fea0b4f-99b7-4050-8d6f-a97ffb839619
author: stevestein
ms.author: sstein
ms.openlocfilehash: fab5380e13742f3cd289ce17f26ad2e5fb9089ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573359"
---
# <a name="remove-tables-from-queries-visual-database-tools"></a>Remover tabelas de consultas (Visual Database Tools)
  Você pode remover uma tabela ou qualquer objeto com valor de tabela da consulta.  
  
> [!NOTE]  
>  Removendo uma tabela ou objeto com valor de tabela não exclui nada do banco de dados; só remove isto da consulta atual. Para obter detalhes sobre como remover uma tabela de um banco de dados, consulte [excluir tabelas &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/tables/delete-tables-database-engine.md).  
  
### <a name="to-remove-a-table-or-table-structured-object"></a>Para remover uma tabela ou objeto estruturado por tabela  
  
-   No **Painel de Diagrama**, selecione a tabela, a exibição, a função definida pelo usuário, o sinônimo ou a consulta e, depois, pressione DELETE ou clique com o botão direito do mouse no objeto e escolha **Remover** na caixa de diálogo resultante. Você pode selecionar e remover vários objetos de uma vez.  
  
     -ou-  
  
-   Remova todas as referências ao objeto no **Painel SQL**.  
  
 Quando você remover uma tabela ou objeto com valor de tabela, o Designer de Consulta e Exibição removerá automaticamente as junções que envolvem aquela tabela ou objeto com valor de tabela e removerá as referências às colunas do objeto no **Painel SQL** e no **Painel de Critérios**. Porém, se a consulta contiver expressões complexas que envolvam o objeto, o objeto não será removido automaticamente até que todas as referências a ele sejam removidas.  
  
## <a name="see-also"></a>Consulte Também  
 [Adicionar tabelas a consultas &#40;Visual Database Tools&#41;](visual-database-tools.md)   
 [Criar aliases de tabela &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md)   
 [Especificar critérios de pesquisa &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md)   
 [Resumir os resultados da consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md)   
 [Executar operações básicas com consultas &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
