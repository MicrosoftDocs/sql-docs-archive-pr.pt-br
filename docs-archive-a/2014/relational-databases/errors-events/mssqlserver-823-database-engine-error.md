---
title: MSSQLSERVER_823 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 823 (Database Engine error)
ms.assetid: 0d9fce3c-3772-46ce-a7a3-4f4988dc6cae
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fa5858bbdc9452a33a3d43fdd783e59556a11e57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574000"
---
# <a name="mssqlserver_823"></a>MSSQLSERVER_823
    
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do Produto|SQL Server|  
|ID do evento|823|  
|Origem do Evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|B_HARDERR|  
|Texto da mensagem|O sistema operacional retornou o erro %ls para o SQL Server durante um %S_MSG no deslocamento %#016I64x do arquivo '%ls'. Additional messages in the SQL Server error log and system event log may provide more detail. Essa é uma condição de erro grave em nível de sistema que ameaça a integridade do banco de dados e deve ser corrigida imediatamente. Faça uma verificação completa da consistência do banco de dados (DBCC CHECKDB). Esse erro pode ter sido causado por vários fatores. Para obter mais informações, consulte os Manuais Online do SQL Server.|  
  
## <a name="explanation"></a>Explicação  
 Falha de solicitação de leitura ou gravação do Windows. O código de erro retornado pelo Windows e o texto correspondente estão inseridos na mensagem. No caso de leitura, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] já terá tentado novamente a solicitação de leitura quatro vezes. Normalmente, esse erro se deve a um erro de hardware, mas pode ser causado pelo driver de dispositivo. Para obter mais informações sobre o erro 823, consulte [https://support.microsoft.com/kb/828339](https://support.microsoft.com/kb/828339) . Para obter mais informações sobre erros de E/S, consulte [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)) (Noções básicas de E/S do Microsoft SQL Server, Capítulo 2).  
  
## <a name="user-action"></a>Ação do usuário  
 Verifique se há mais informações no log de eventos do sistema. Entre em contato com o fabricante de hardware ou o Atendimento ao Cliente e o Suporte da Microsoft para determinar a causa e ação corretiva. Depois que o erro de hardware for corrigido, restaure todos os bancos de dados e execute o DBCC CHECKDB.  
  
  
