---
title: bcp_sendrow | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_sendrow
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_sendrow function
ms.assetid: ddbdb4bd-ad4e-4bf1-9a75-656aa26ce10a
author: rothja
ms.author: jroth
ms.openlocfilehash: 3d2f55486ba57101ffc7b1903de5d19ac8eaaca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572050"
---
# <a name="bcp_sendrow"></a>bcp_sendrow
  Envia uma linha de dados de variáveis de programa para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
RETCODE bcp_sendrow (  
    HDBC   
hdbc  
);  
  
```  
  
## <a name="arguments"></a>Argumentos  
 *hdbc*  
 É o identificador de conexão ODBC habilitado para cópia em massa.  
  
## <a name="returns"></a>Retornos  
 SUCCEED ou FAIL.  
  
## <a name="remarks"></a>Comentários  
 A função **bcp_sendrow** compila uma linha de variáveis de programa e a envia para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 Antes de chamar **bcp_sendrow**, você deve fazer chamadas para [bcp_bind](bcp-bind.md) para especificar as variáveis de programa que contêm os dados da linha.  
  
 Caso **bcp_bind** seja chamado especificando um tipo de dados longo de comprimento variável, por exemplo um parâmetro *eDataType* de SQLTEXT e um parâmetro *pData* diferente de NULL, **bcp_sendrow** envia todo o valor de dados, exatamente como faz para qualquer outro tipo de dados. Entretanto, se **bcp_bind** tiver um parâmetro *pData* igual a NULL, **bcp_sendrow** retorna o controle para o aplicativo imediatamente após todas as colunas com os dados especificados serem enviadas ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Então, o aplicativo pode chamar [bcp_moretext](bcp-moretext.md) repetidamente para enviar os dados longos de comprimento variável para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], uma parte de cada vez. Para obter mais informações, consulte [bcp_moretext](bcp-moretext.md).  
  
 Quando **bcp_sendrow** for usado para copiar linhas em massa de variáveis do programa para tabelas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , as linhas são confirmadas somente quando o usuário chamar [bcp_batch](bcp-batch.md) ou [bcp_done](bcp-done.md). O usuário pode escolher chamar **bcp_batch** uma vez a cada *n* linhas ou quando houver uma pausa entre períodos de dados de entrada. Se **bcp_batch** nunca for chamado, as linhas serão confirmadas quando **bcp_done** for chamado.  
  
 Para obter informações sobre uma alteração significativa na cópia em massa a partir do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , consulte [executando operações de cópia em massa &#40;&#41;ODBC ](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).  
  
## <a name="see-also"></a>Consulte Também  
 [Bulk Copy Functions](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
