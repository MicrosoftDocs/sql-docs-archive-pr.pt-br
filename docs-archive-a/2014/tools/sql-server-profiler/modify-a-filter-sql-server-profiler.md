---
title: Modificar um filtro (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], modifying
- modifying filters, modifying
- filters [SQL Server], traces
ms.assetid: 8b317813-4918-4485-b930-77b1951aa00c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5a7bab18952820a3dc49c9479797a411521f8e71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572887"
---
# <a name="modify-a-filter-sql-server-profiler"></a>Modificar um filtro (SQL Server Profiler)
  Os filtros são adicionados aos modelos de rastreamento, que contêm as definições de rastreamento, para limitar o número de eventos coletados por um rastreamento. Limitar o número de eventos coletados pode reduzir os efeitos do desempenho do rastreamento. Se definir filtros para um modelo de rastreamento e achar que o rastreamento não está coletando o tipo de informações de que necessita, você poderá editar o filtro.  
  
### <a name="to-modify-a-filter"></a>Para modificar um filtro  
  
1.  No [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], abra o modelo referente ao filtro de rastreamento que você deseja modificar. No menu **Arquivo** , clique em **Modelos**e escolha **Editar Modelo**.  
  
2.  Na guia **Geral** da caixa de diálogo **Propriedades do Modelo de Rastreamento** , selecione um modelo na lista **Selecionar nome do modelo** .  
  
3.  Clique na guia **Seleção de Eventos** .  
  
     A guia **Seleção de Eventos** contém um controle de grade. O controle de grade é uma tabela que contém cada uma das classes de evento rastreáveis. A tabela contém uma linha para cada classe de evento. As classes de evento podem diferir ligeiramente, dependendo do tipo e versão de servidor com o qual você está conectado. As classes de evento são identificadas na coluna **Events**da grade e são agrupadas por categoria de evento. As colunas restantes listam as colunas de dados que podem ser retornadas para cada classe de evento.  
  
4.  Clique em **Filtros de Coluna**.  
  
5.  Na caixa de diálogo **Editar Filtro** , clique no valor próximo ao operador de comparação que você deseja editar e exclua-o ou digite o novo valor. Você também pode adicionar outros filtros.  
  
6.  Clique em **OK** e salve o modelo.  
  
## <a name="see-also"></a>Consulte Também  
 [SQL Server Profiler](sql-server-profiler.md)  
  
  
