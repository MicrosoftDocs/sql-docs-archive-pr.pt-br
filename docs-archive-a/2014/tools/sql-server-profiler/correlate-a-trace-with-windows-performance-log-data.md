---
title: Correlacionar um rastreamento com os dados de log de desempenho do Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- correlating trace with log data
- logs [SQL Server], traces
- Profiler [SQL Server Profiler], correlating trace with log data
- traces [SQL Server], logs
- SQL Server Profiler, correlating trace with log data
ms.assetid: 1e4412c8-d27c-4aae-9b35-214128d1d00a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 879441c948f0ad04b971159a37ec0dcec90e3ada
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678416"
---
# <a name="correlate-a-trace-with-windows-performance-log-data"></a>Correlacionar um rastreamento com os dados de log de desempenho do Windows
  Usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], você pode abrir um log de desempenho do Microsoft Windows, escolher os contadores que deseja correlacionar com um rastreamento e exibir os contadores de desempenho selecionados junto com o rastreamento na interface gráfica do usuário do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] . Quando você seleciona um evento na janela de rastreamento, uma barra vermelha vertical no painel da janela de dados do Monitor do Sistema do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] indica os dados do log de desempenho que se correlacionam com o evento de rastreamento selecionado.  
  
 Para correlacionar um rastreamento com contadores de desempenho, abra um arquivo ou tabela de rastreamento que contenha as colunas de dados **StartTime** e **EndTime**, então clique em **Importar Dados de Desempenho** no menu [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]Arquivo**do**. Em seguida, você pode abrir um log de desempenho e selecionar os objetos e contadores do Monitor do Sistema que deseja correlacionar com o rastreamento.  
  
## <a name="see-also"></a>Consulte Também  
 [Correlacionar um rastreamento com dados do log de desempenho do Windows &#40;SQL Server Profiler&#41;](correlate-a-trace-with-windows-performance-log-data.md)  
  
  
