---
title: MSSQLSERVER_4064 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4064 (Database Engine error)
ms.assetid: 32112b90-0a2f-4834-a027-756811732be7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 201098aadeb6bd091f0312532138f692ae8079b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582459"
---
# <a name="mssqlserver_4064"></a>MSSQLSERVER_4064
    
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do Produto|SQL Server|  
|ID do evento|4064|  
|Origem do Evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|DB_UFAIL_FATAL|  
|Texto da mensagem|Não é possível abrir o banco de dados padrão do usuário. Falha no logon.|  
  
## <a name="explanation"></a>Explicação  
 O logon do SQL Server não pôde se conectar devido a um problema com o banco de dados padrão. O próprio banco de dados é inválido ou o logon não tem a permissão CONNECT no banco de dados.  
  
## <a name="user-action"></a>Ação do usuário  
 Use ALTER LOGIN para alterar o banco de dados padrão do logon. Conceda a permissão CONNECT para o logon.  
  
  
