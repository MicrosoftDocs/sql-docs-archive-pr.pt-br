---
title: Escolher os servidores a serem configurados (Assistente para Configurar Segurança de Espelhamento de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.choosesrvrs.f1
ms.assetid: 59e23ff3-d7ee-4e32-9629-0b54d3a258f7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 18e36f5c8ec020b3859dc847d1bbfc019817bcd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571585"
---
# <a name="choose-servers-to-configure-configure-database-mirroring-security-wizard"></a>Selecionar servidores a configurar (Assistente para Configurar Segurança de Espelhamento de Banco de Dados)
  Use essa página para especificar quais instâncias de servidor serão configuradas no momento. É preciso selecionar no mínimo uma instância de servidor antes de prosseguir com o assistente.  
  
 Se você desmarcar a caixa de seleção de uma instância de servidor, o assistente não fará nenhuma alteração nessa instância. O assistente, porém, solicitará que você insira informações sobre essa instância e salvará as informações como parte da configuração das outras instâncias de servidor. Por exemplo, se você desmarcar a caixa de seleção da instância de servidor testemunha, o assistente solicitará a inserção da conta de serviços da testemunha do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , uma vez que um logon para essa conta precisará ser criado como parte da configuração de segurança salva nas instâncias do servidor principal e de espelhamento.  
  
 **Para configurar o espelhamento de banco de dados usando o SQL Server Management Studio**  
  
-   [Estabelecer uma sessão de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md)  
  
-   [Iniciar o Assistente para Configurar Segurança de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a>Opções  
 **Instância do servidor principal**  
 Selecione para configurar a segurança do servidor principal.  
  
 **Instância do servidor espelho**  
 Selecione para configurar a segurança do servidor espelho.  
  
 **Instância do servidor testemunha**  
 Selecione para configurar segurança para o servidor testemunha (se houver).  
  
## <a name="see-also"></a>Consulte Também  
 [Propriedades do banco de dados &#40;página Espelhamento&#41;](../../relational-databases/databases/database-properties-mirroring-page.md)   
 [Espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md)  
  
  
