---
title: MSSQLSERVER_107 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 107 (Database Engine error)
ms.assetid: f33f514c-56aa-42e2-841b-e91244da90e2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b9388bbda6f00b1aafd02caee1b6a7b8387564f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576448"
---
# <a name="mssqlserver_107"></a>MSSQLSERVER_107
    
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do Produto|SQL Server|  
|ID do evento|107|  
|Origem do Evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|P_NOCORRMATCH|  
|Texto da mensagem|O prefixo de coluna '%.*ls' não coincide com um nome de tabela ou nome de alias usado na consulta.|  
  
## <a name="explanation"></a>Explicação  
 A lista de seleção da consulta contém um asterisco (*) que é qualificado incorretamente com um prefixo de coluna. Esse erro pode ser retornado nas seguintes condições:  
  
-   O prefixo de coluna não corresponde a nenhum nome de tabela ou de alias usado na consulta. Por exemplo, a instrução a seguir utiliza um nome de alias (`T1`) como prefixo de coluna, mas o alias não está definido na cláusula FROM.  
  
    ```  
    SELECT T1.* FROM dbo.ErrorLog;  
    ```  
  
-   Um nome de tabela é especificado como prefixo de coluna quando um nome de alias da tabela é informado na cláusula FROM. Por exemplo, a instrução a seguir usa o nome de tabela `ErrorLog` como prefixo de coluna; entretanto, a tabela tem um alias (`T1`) definido na cláusula FROM.  
  
    ```  
    SELECT ErrorLog.* FROM dbo.ErrorLog AS T1;  
    ```  
  
     Se um nome de alias tiver sido especificado para um nome de tabela na cláusula FROM, você só poderá usar o alias para prefixar colunas da tabela.  
  
## <a name="user-action"></a>Ação do usuário  
 Compare os prefixos de coluna com os nomes de tabela ou de alias especificados na cláusula FROM da consulta. Por exemplo, as instruções acima podem ser corrigidas da seguinte maneira:  
  
```  
SELECT T1.* FROM dbo.ErrorLog AS T1;  
```  
  
 ou  
  
```  
SELECT ErrorLog.* FROM dbo.ErrorLog;  
```  
  
## <a name="see-also"></a>Consulte Também  
 [MSSQLSERVER_4104](mssqlserver-4104-database-engine-error.md)  
  
  
