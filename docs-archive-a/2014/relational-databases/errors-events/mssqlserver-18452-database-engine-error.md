---
title: MSSQLSERVER_18452 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18456 (Database Engine error)
- 18452 (Database Engine error)
ms.assetid: 21da332c-e81d-4dee-a9d2-95598911b3be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5786d5de4748f6bbf59d2bd4acecd7ca77977f11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575150"
---
# <a name="mssqlserver_18452"></a>MSSQLSERVER_18452
    
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do Produto|SQL Server|  
|ID do evento|18452|  
|Origem do Evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|LOGON_INVALID_CONNECT|  
|Texto da mensagem|Falha no logon do usuário '%.*ls'. O logon é um logon do SQL Server e não pode ser usado com a Autenticação do Windows.%.\*ls|  
  
## <a name="explanation"></a>Explicação  
 O usuário tentou fazer logon com credenciais que não podem ser validadas. Causas possíveis:  
  
-   O logon pode ser um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mas o servidor aceita somente a Autenticação do Windows (Segurança Integrada).  
  
-   Você está tentando se conectar usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mas o logon usado não existe no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
-   O logon pode usar a Autenticação do Windows (Segurança Integrada), mas é uma entidade não reconhecida do Windows. Uma entidade não reconhecida do Windows significa que o logon não pode ser verificado pelo Windows. Talvez isso ocorra porque o logon do Windows é de um domínio não confiável.  
  
 Problemas semelhantes podem causar o erro menos específico 18456.  
  
## <a name="user-action"></a>Ação do usuário  
 Se você estiver tentando se conectar usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], verifique se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está configurado no Modo de Autenticação Mista.  
  
 Se você estiver tentando se conectar usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], verifique se o logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] existe.  
  
 Se você estiver tentando se conectar usando a Autenticação do Windows, verifique se está devidamente conectado no domínio correto.  
  
  
