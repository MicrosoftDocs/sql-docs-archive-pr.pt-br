---
title: Verificar o subsistema de saída de entrada de disco para problemas de repetição de leitura | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: cedf4097-5b73-4964-9935-74a101847019
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19809b1554e435600eb4eeae424bed17dc27bdbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678729"
---
# <a name="check-disk-input-output-subsystem-for-read-retry-problems"></a>Verificar o subsistema de entrada e saída de disco para problemas de repetição de leitura
  Esta regra verifica o log de eventos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para a mensagem de erro 825. Esta mensagem indica que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pôde ler os dados do disco na primeira tentativa. Esta mensagem indica um problema grave com o subsistema de E/S do disco. Atualmente, esta mensagem não indica um problema no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Entretanto, o problema com o disco poderia causar perda de dados ou danos no banco de dados se não for resolvido.  
  
## <a name="best-practices-recommendations"></a>Práticas Recomendadas  
 As ações a seguir podem ajudar a identificar e resolver o problema subjacente no hardware:  
  
-   Revise o log de erros e o texto variável nesta mensagem para encontrar pistas que expliquem o problema.  
  
-   Verifique o sistema de disco. O problema pode estar relacionado aos discos, aos controladores de disco, aos cartões de matriz ou aos drivers de disco.  
  
-   Contate o fabricante do disco para obter os mais recentes utilitários para verificar o status do sistema do disco.  
  
-   Contate o fabricante do disco para obter as mais recentes atualizações de driver.  
  
## <a name="for-more-information"></a>Para obter mais informações  
 [MSSQLSERVER_825](../errors-events/mssqlserver-825-database-engine-error.md)  
  
 [Fundamentos de E/S do SQL Server, Capítulo 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))  
  
  
