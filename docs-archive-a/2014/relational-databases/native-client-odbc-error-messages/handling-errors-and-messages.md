---
title: Manipulando erros e mensagens | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC error handling, about error handling
- errors [ODBC]
- SQL Server Native Client ODBC driver, errors
- messages [ODBC], about messages
- ODBC error handling
- SQL_INVALID_HANDLE return code
- errors [ODBC], about error handling
- messages [ODBC]
ms.assetid: 74ea9630-e482-4a46-bb45-f5234f079b48
author: rothja
ms.author: jroth
ms.openlocfilehash: 4701b3224b87e7d19f1121f193d4be20f9d4c441
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679948"
---
# <a name="handling-errors-and-messages"></a>Tratando de erros e mensagens
  Quando um aplicativo chama uma função ODBC, o driver executa a função e retorna informações de diagnóstico de duas formas: um código de retorno indica o êxito ou a falha geral de uma função ODBC, e registros de diagnóstico fornecem informações detalhadas sobre a função. Os registros de diagnóstico incluem um registro de cabeçalho e registros de status. Pelo menos um registro de diagnóstico, o registro de cabeçalho, será retornado, mesmo que a função tenha êxito.  
  
 As informações de diagnóstico são usadas em tempo de desenvolvimento para capturar erros de programação, como identificadores inválidos e erros de sintaxe em instruções SQL embutidas em código. Elas também são usadas em tempo de execução para capturar erros e avisos de tempo de execução, como truncamento de dados, violações de regras e erros de sintaxe em instruções SQL inseridas pelo usuário. Em geral, a lógica de programação se baseia em códigos de retorno.  
  
 Por exemplo, depois que um aplicativo chama **SQLFetch** para recuperar as linhas em um conjunto de resultados, o código de retorno indica se o final do conjunto de resultados foi atingido (SQL_NO_DATA), se alguma mensagem informativa foi retornada (SQL_SUCCESS_WITH_INFO) ou se ocorreu um erro (SQL_ERROR).  
  
 Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client retornar algo diferente de SQL_SUCCESS, o aplicativo poderá chamar **SQLGetDiagRec** para recuperar qualquer mensagem de erro ou informativa. Use **SQLGetDiagRec** para rolar para cima e para baixo no conjunto de mensagens se houver mais de uma mensagem.  
  
 O código de retorno SQL_INVALID_HANDLE sempre indica um erro de programação e nunca deve ser encontrado em tempo de execução. Todos os outros códigos de retorno fornecem informações, embora SQL_ERROR possa indicar um erro de programação.  
  
 A [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] API nativa original, DB-Library para C, permite que um aplicativo instale as funções de tratamento de erros de retorno de chamada e tratamento de mensagens que retornam erros ou mensagens. Algumas instruções [!INCLUDE[tsql](../../includes/tsql-md.md)], como PRINT, RAISERROR, DBCC e SET, retornam seus resultados para a função de manipulador de mensagens de DB-Library e não para um conjunto de resultados. Porém, a API ODBC não tem nenhum recurso de retorno de chamada. Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client detecta mensagens retornando do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ele define o código de retorno do ODBC para SQL_SUCCESS_WITH_INFO ou SQL_ERROR e retorna a mensagem como um ou mais registros de diagnóstico. Portanto, um aplicativo ODBC deve testar cuidadosamente esses códigos de retorno e chamar **SQLGetDiagRec** para recuperar dados de mensagem.  
  
 Para obter informações sobre como rastrear erros, confira [Rastreamento do acesso a dados](https://go.microsoft.com/fwlink/?LinkId=125805). Para obter informações sobre aprimoramentos no rastreamento de erros adicionados em [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], confira [Acessar informações de diagnóstico nos logs de eventos estendidos](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).  
  
## <a name="in-this-section"></a>Nesta seção  
  
-   [Processando instruções que geram mensagens](processing-statements-that-generate-messages.md)  
  
-   [Registros e campos de diagnóstico](diagnostic-records-and-fields.md)  
  
-   [Números de erro nativos](native-error-numbers.md)  
  
-   [SQLSTATE &#40;códigos de erro ODBC&#41;](sqlstate-odbc-error-codes.md)  
  
-   [Mensagens de erro](error-messages.md)  
  
## <a name="see-also"></a>Consulte Também  
 [SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
