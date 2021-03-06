---
title: Executar um comando | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- commands [SQL Server Native Client]
- OLE DB, executing commands
- sessions [SQL Server Native Client]
- OLE DB extensions for XML
- SQL Server Native Client OLE DB provider, command execution
ms.assetid: bb0b3cbf-fe45-46ba-b2ec-c5a39e3c7081
author: rothja
ms.author: jroth
ms.openlocfilehash: 41e8da036d5a4b6469a31213247ad7d4edb7dbfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581778"
---
# <a name="executing-a-command"></a>Executando um comando
  Depois de estabelecida a conexão com uma fonte de dados, o consumidor chama o método **IDBCreateSession::CreateSession** para criar uma sessão. A sessão atua como um comando, conjunto de linhas ou fábrica de transação.  
  
 Para trabalhar diretamente com tabelas ou índices individuais, o consumidor solicita a interface `IOpenRowset`. O método `IOpenRowset::OpenRowset` se abre e retorna um conjunto de linhas que inclui todas as linhas de uma única tabela ou índice base.  
  
 Para executar um comando (como selecionar \* de autores), o consumidor solicita a `IDBCreateCommand` interface. O consumidor pode executar o método `IDBCreateCommand::CreateCommand` para criar um objeto de comando e solicitar a interface `ICommandText`. O método `ICommandText::SetCommandText` é usado para especificar o comando que será executado.  
  
 O comando `Execute` é usado para executar o comando. O comando pode ser qualquer instrução SQL ou nome de procedimento. Nem todos os comandos geram um objeto de conjunto de resultados (conjunto de linhas). Comandos como SELECT * FROM Authors geram um conjunto de resultados.  
  
## <a name="see-also"></a>Consulte Também  
 [Criando um aplicativo provedor OLE DB do SQL Server Native Client](creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
