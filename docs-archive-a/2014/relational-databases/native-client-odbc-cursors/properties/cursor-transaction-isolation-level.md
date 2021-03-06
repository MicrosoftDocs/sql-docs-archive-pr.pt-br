---
title: Nível de isolamento da transação do cursor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- isolation levels [ODBC]
- ODBC applications, row versioning
- cursors [ODBC], isolation levels
- ODBC cursors, isolation levels
- row versioning [SQL Server], ODBC
ms.assetid: 0c6663a4-5a25-44aa-8fe4-e35af9bf4a83
author: rothja
ms.author: jroth
ms.openlocfilehash: 30f3dc8a9136a7cbe1d5897cb0bcc9fff8c35ab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684208"
---
# <a name="cursor-transaction-isolation-level"></a>Nível de isolamento da transação de cursor
  O comportamento de bloqueio completo de cursores se baseia em uma interação entre atributos de simultaneidade e o nível de isolamento da transação definidos pelo cliente. Os clientes ODBC definem o nível de isolamento da transação usando os atributos [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) SQL_ATTR_TXN_ISOLATION ou SQL_COPT_SS_TXN_ISOLATION. O comportamento de bloqueio de um ambiente de cursor específico é determinado pela combinação dos comportamentos de bloqueio das opções de nível de isolamento da transação e de simultaneidade.  
  
 Os seguintes níveis de isolamento da transação de cursor são suportados pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client:  
  
-   Leitura confirmada (SQL_TXN_READ_COMMITTED)  
  
-   Leitura não confirmada (SQL_TXN_READ_UNCOMMITTED)  
  
-   Leitura repetível (SQL_TXN_REPEATABLE_READ)  
  
-   Serializável (SQL_TXN_SERIALIZABLE)  
  
-   Instantâneo (SQL_TXN_SS_SNAPSHOT)  
  
 Observe que a API ODBC especifica níveis de isolamento de transação adicionais, mas eles não são suportados pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client.  
  
## <a name="see-also"></a>Consulte Também  
 [Propriedades do cursor](cursor-properties.md)  
  
  
