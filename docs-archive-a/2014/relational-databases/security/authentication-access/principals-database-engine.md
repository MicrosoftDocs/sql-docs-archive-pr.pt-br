---
title: Entidades de segurança (mecanismo de banco de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.roleproperties.selectroll.f1
- sql12.swb.databaseuser.permissions.user.f1--May use common.permissions
helpviewer_keywords:
- certificates [SQL Server], principals
- roles [SQL Server], principals
- permissions [SQL Server], principals
- '##MS_SQLAuthenticatorCertificate##'
- principals [SQL Server]
- '##MS_SQLResourceSigningCertificate##'
- groups [SQL Server], principals
- '##MS_AgentSigningCertificate##'
- authentication [SQL Server], principals
- schemas [SQL Server], principals
- principals [SQL Server], about principals
- security [SQL Server], principals
- users [SQL Server], principals
- '##MS_SQLReplicationSigningCertificate##'
ms.assetid: 3f7adbf7-6e40-4396-a8ca-71cbb843b5c2
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 808c8516b3ed9e95ea4c724736461cb00923a7fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583457"
---
# <a name="principals-database-engine"></a>Entidades (Mecanismo de Banco de Dados)
  *Entidades* são entidades que podem solicitar recursos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . Como outros componentes do modelo de autorização do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , as entidades podem ser organizadas em uma hierarquia. O escopo de influência de uma entidade de segurança depende do escopo da definição da entidade de segurança: Windows, servidor, banco de dados e se a entidade de segurança é indivisível ou uma coleção. Um logon do Windows é um exemplo de um principal indivisível, enquanto um Grupo do Windows é um exemplo de um principal que é uma coleção. Todas as entidades têm um SID (identificador de segurança).  
  
 **Entidades no nível do Windows**  
  
-   Logon de domínio do Windows  
  
-   Logon local do Windows  
  
 **SQL Server** - **level** **entidades** de nível  
  
-   Logon do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]  
  
-   Função do servidor  
  
 **Entidades no nível do banco de dados**  
  
-   Usuário de banco de dados  
  
-   Função de banco de dados  
  
-   Função de aplicativo  
  
## <a name="the-sql-server-sa-login"></a>Logon sa do SQL Server  
 O logon sa do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] é uma entidade de segurança no nível do servidor. Por padrão, ele é criado quando uma instância é instalada. A partir do [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], o banco de dados padrão de sa é o mestre. Essa é uma alteração de comportamento de versões anteriores do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
## <a name="public-database-role"></a>Função de banco de dados pública  
 Cada usuário do banco de dados pertence à função do banco de dados público. Quando permissões específicas não são concedidas ou são negadas a um usuário em um objeto seguro, o usuário herda as permissões concedidas como públicas naquele objeto seguro.  
  
## <a name="information_schema-and-sys"></a>INFORMATION_SCHEMA e sys  
 Todo o banco de dados inclui duas entidades exibidas como usuários em exibições do catálogo: INFORMATION_SCHEMA e sys. Essas entidades são exigidas pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Elas não são entidades, tampouco podem ser modificadas ou descartadas.  
  
## <a name="certificate-based-sql-server-logins"></a>Logons do SQL Server com base em certificado  
 Entidades de servidor com nomes entre duas marcas hash (##) são somente para uso interno do sistema. As entidades a seguir são criadas com base em certificados quando o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] é instalado e não devem ser excluídas.  
  
-   \##MS_SQLResourceSigningCertificate##  
  
-   \##MS_SQLReplicationSigningCertificate##  
  
-   \##MS_SQLAuthenticatorCertificate##  
  
-   \##MS_AgentSigningCertificate##  
  
-   \##MS_PolicyEventProcessingLogin##  
  
-   \##MS_PolicySigningCertificate##  
  
-   \##MS_PolicyTsqlExecutionLogin##  
  
## <a name="the-guest-user"></a>O Usuário convidado  
 Cada banco de dados inclui um **convidado**. As permissões concedidas ao usuário **convidado** são herdadas pelos usuários que têm acesso ao banco de dados, mas que não têm uma conta de usuário no banco de dados. O usuário **convidado** não pode ser removido, mas pode ser desabilitado por meio da revogação de sua `CONNECT` permissão. A `CONNECT` permissão pode ser revogada executando `REVOKE CONNECT FROM GUEST` em qualquer banco de dados que não seja o mestre ou o tempdb.  
  
## <a name="client-and-database-server"></a>Servidor de banco de dados e cliente  
 Por definição, um cliente e um servidor de banco de dados são entidades de segurança e podem ser protegidos. Essas entidades podem ser autenticadas mutuamente antes que uma conexão de rede segura seja estabelecida. [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]dá suporte ao protocolo de autenticação [Kerberos](https://go.microsoft.com/fwlink/?LinkId=100758) , que define como os clientes interagem com um serviço de autenticação de rede.  
  
## <a name="related-tasks"></a>Related Tasks  
 Os tópicos a seguir são incluídos nesta seção dos Manuais Online do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :  
  
-   [Tópicos de instruções sobre gerenciamento de logons, usuários e esquemas](managing-logins-users-and-schemas-how-to-topics.md)  
  
-   [Funções de nível de servidor](server-level-roles.md)  
  
-   [Funções de nível de banco de dados](database-level-roles.md)  
  
-   [Funções de aplicativo](application-roles.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Protegendo o SQL Server](../securing-sql-server.md)   
 [sys.database_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql)   
 [sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql)   
 [sys.sql_logins &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql)   
 [sys.database_role_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql)   
 [Funções de nível de servidor](server-level-roles.md)   
 [Funções de nível de banco de dados](database-level-roles.md)  
  
  
