---
title: Configurar publicação e distribuição | Microsoft Docs
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], distribution
- distribution configuration [SQL Server replication]
- publishing [SQL Server replication], configuring
ms.assetid: 3cfc8966-833e-42fa-80cb-09175d1feed7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: afd1544b5412c6ce2d83a9a1e9a50ddf662b3056
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569391"
---
# <a name="configure-publishing-and-distribution"></a>Configurar a publicação e a distribuição
  Este tópico descreve como configurar publicação e distribuição no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]ou RMO (Replication Management Objects).  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> Antes de começar  
  
###  <a name="security"></a><a name="Security"></a> Segurança  
 Para obter mais informações, consulte [implantação de replicação segura](security/view-and-modify-replication-security-settings.md).  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> Usando o SQL Server Management Studio  
 Configure a distribuição, usando o Assistente para Novas Publicações ou o Assistente para Configurar a Distribuição. Depois que o Distribuidor estiver configurado, veja e modifique as propriedades na caixa de diálogo **Propriedades do Distribuidor – \<Distributor>** . Use o Assistente para Configurar Distribuição se você desejar configurar um Distribuidor para que os membros de funções de banco de dados fixas **db_owner** possam criar publicações ou para configurar um Distribuidor remoto que não é um Publicador.  
  
#### <a name="to-configure-distribution"></a>Para configurar a distribuição  
  
1.  No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se ao servidor que será o Distribuidor (em muitos casos, o Publicador e o Distribuidor são o mesmo servidor) e, então, expanda o nó de servidor.  
  
2.  Clique com o botão direito na pasta **Replicação** e clique em **Configurar Distribuição**.  
  
3.  Siga o Assistente para Configurar Distribuição para:  
  
    -   Selecionar um Distribuidor. Para usar um distribuidor local, selecione **' \<ServerName> ' atuará como seu próprio distribuidor; SQL Server criará um banco de dados de distribuição e um log**. Para usar um Distribuidor remoto, selecione **Use o seguinte servidor como Distribuidor**e, em seguida, selecione um servidor. O servidor já deve ser configurado como um Distribuidor e o Publicador deve ser habilitado a usar o Distribuidor. Para obter mais informações, consulte [Habilitar um Publicador Remoto em um Distribuidor &#40;SQL Server Management Studio&#41;](enable-a-remote-publisher-at-a-distributor-sql-server-management-studio.md).  
  
         Se você selecionar um Distribuidor remoto, você deverá inserir uma senha na página **Senha Administrativa** para conexões feitas do Publicador ao Distribuidor. Esta senha deve corresponder à senha especificada quando o Publicador foi habilitado no Distribuidor remoto.  
  
    -   Especifique uma pasta de instantâneo de raiz (para um Distribuidor local). A pasta de instantâneo é simplesmente um diretório que você designou como um compartilhamento, agentes que leem essa pasta e gravam nela devem ter permissões suficientes para acessá-la. Cada Publicador que usa esse Distribuidor cria uma pasta na pasta raiz, e cada publicação cria pastas na pasta Publicador em que armazenará arquivos de instantâneos. Para obter mais informações sobre como proteger a pasta adequadamente, consulte [Proteger a Pasta de Instantâneos](security/secure-the-snapshot-folder.md).  
  
    -   Especifique o banco de dados de distribuição (para um Distribuidor local). O banco de dados de distribuição armazena metadados e dados de histórico para todos os tipos de replicação e transações para replicação transacional.  
  
    -   Além disso, permite que outros Publicadores usem o Distribuidor. Se outros Publicadores estiverem habilitados para usar o Distribuidor, você deverá inserir uma senha na página **Senha do Distribuidor** para conexões feitas desses Publicadores para os Distribuidores.  
  
    -   Além disso, faça o script das definições de configuração. Para obter mais informações, consulte [Scripting Replication](scripting-replication.md).  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> Usando o Transact-SQL  
 Publicação e distribuição de replicação podem ser configuradas de forma programada, usando-se procedimentos de replicação armazenados.  
  
#### <a name="to-configure-publishing-using-a-local-distributor"></a>Para configurar publicação usando um distribuidor local  
  
1.  Execute [sp_get_distributor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-get-distributor-transact-sql) para determinar se o servidor já está configurado como um Distribuidor.  
  
    -   Se o valor **installed** no resultado definido for **0**, execute [sp_adddistributor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistributor-transact-sql) no Distribuidor no banco de dados mestre.  
  
    -   Se o valor **bd de distribuição instalado** no resultado definido for **0**, execute [sp_adddistributiondb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistributiondb-transact-sql) no Distribuidor no banco de dados mestre. Especifique o nome do banco de dados de distribuição para o ** \@ banco de dados**. Opcionalmente, você pode especificar o período máximo de retenção transacional para ** \@ max_distretention** e o período de retenção do histórico para ** \@ history_retention**. Se um banco de dados novo estiver sendo criado, especifique os parâmetros de propriedade de banco de dados desejados.  
  
2.  No distribuidor, que também é o Publicador, execute [sp_adddistpublisher &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-adddistpublisher-transact-sql), especificando o compartilhamento UNC que será usado como pasta de instantâneo padrão para ** \@ working_directory**.  
  
3.  No Editor, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql). Especifique o banco de dados que está sendo publicado para ** \@ dbname**, o tipo de replicação para ** \@ OptName**e um valor de `true` para ** \@ valor**.  
  
#### <a name="to-configure-publishing-using-a-remote-distributor"></a>Para configurar publicação usando um distribuidor remoto  
  
1.  Execute [sp_get_distributor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-get-distributor-transact-sql) para determinar se o servidor já está configurado como um Distribuidor.  
  
    -   Se o valor **installed** no resultado definido for **0**, execute [sp_adddistributor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistributor-transact-sql) no Distribuidor no banco de dados mestre. Especifique uma senha forte para a ** \@ senha**. Essa senha para a conta **distributor_admin** será usada pelo Publicador ao se conectar ao Distribuidor.  
  
    -   Se o valor **bd de distribuição instalado** no resultado definido for **0**, execute [sp_adddistributiondb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistributiondb-transact-sql) no Distribuidor no banco de dados mestre. Especifique o nome do banco de dados de distribuição para o ** \@ banco de dados**. Opcionalmente, você pode especificar o período máximo de retenção transacional para ** \@ max_distretention** e o período de retenção do histórico para ** \@ history_retention**. Se um banco de dados novo estiver sendo criado, especifique os parâmetros de propriedade de banco de dados desejados.  
  
2.  No distribuidor, execute [sp_adddistpublisher &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-adddistpublisher-transact-sql), especificando o compartilhamento UNC que será usado como pasta de instantâneo padrão para ** \@ working_directory**. Se o distribuidor usar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autenticação ao se conectar ao Publicador, você também deverá especificar um valor de **0** para ** \@ security_mode** e as [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] informações de logon para ** \@ logon** e ** \@ senha**.  
  
3.  No Editor do banco de dados mestre, execute [sp_adddistributor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistributor-transact-sql). Especifique a senha forte usada na etapa 1 para ** \@ senha**. Essa senha será usada pelo Publicador ao se conectar ao Distribuidor.  
  
4.  No Editor, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql). Especifique o banco de dados que está sendo publicado para ** \@ dbname**, o tipo de replicação para ** \@ OptName**e um valor de true para ** \@ Value**.  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> Exemplo (Transact-SQL)  
 O exemplo a seguir mostra como configurar publicação e distribuição programaticamente. Nesse exemplo, o nome do servidor que está sendo configurado como publicador e um distribuidor local são fornecidos usando variáveis de script. Publicação e distribuição de replicação podem ser configuradas de forma programada, usando-se procedimentos de replicação armazenados.  
  
 [!code-sql[HowTo#AddDistPub](../../snippets/tsql/SQL15/replication/howto/tsql/adddistpub.sql#adddistpub)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> Usando o RMO (Replication Management Objects)  
  
#### <a name="to-configure-publishing-and-distribution-on-a-single-server"></a>Para configurar a publicação e a distribuição em um único servidor  
  
1.  Crie uma conexão ao servidor usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .  
  
2.  Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>. Passe o <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 1.  
  
3.  Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.DistributionDatabase>.  
  
4.  Defina a propriedade <xref:Microsoft.SqlServer.Replication.DistributionDatabase.Name%2A> para o nome do banco de dados e defina a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> para o <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 1.  
  
5.  Instale o Distribuidor chamando o método <xref:Microsoft.SqlServer.Replication.ReplicationServer.InstallDistributor%2A> . Passe o objeto <xref:Microsoft.SqlServer.Replication.DistributionDatabase> da etapa 3.  
  
6.  Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.DistributionPublisher>.  
  
7.  Defina as seguintes propriedades de <xref:Microsoft.SqlServer.Replication.DistributionPublisher>:  
  
    -   <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> - nome do Publicador.  
  
    -   <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> - o <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 1.  
  
    -   <xref:Microsoft.SqlServer.Replication.DistributionPublisher.DistributionDatabase%2A> - o nome do banco de dados criado na etapa 5.  
  
    -   <xref:Microsoft.SqlServer.Replication.DistributionPublisher.WorkingDirectory%2A> - o compartilhamento usado para acessar os arquivos de instantâneos.  
  
    -   <xref:Microsoft.SqlServer.Replication.DistributionPublisher.PublisherSecurity%2A> - o modo de segurança usado durante a conexão com o Publicador. O<xref:Microsoft.SqlServer.Replication.ConnectionSecurityContext.WindowsAuthentication%2A> é recomendado.  
  
8.  Chame o método <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Create%2A> .  
  
#### <a name="to-configure-publishing-and-distribution-using-a-remote-distributor"></a>Para configurar a publicação e a distribuição usando um Distribuidor remoto  
  
1.  Crie uma conexão ao servidor do Distribuidor remoto usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .  
  
2.  Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>. Passe o <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 1.  
  
3.  Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.DistributionDatabase>.  
  
4.  Defina a propriedade <xref:Microsoft.SqlServer.Replication.DistributionDatabase.Name%2A> ao nome do banco de dados e defina a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> ao <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 1.  
  
5.  Instale o Distribuidor chamando o método <xref:Microsoft.SqlServer.Replication.ReplicationServer.InstallDistributor%2A> . Especifique uma senha segura (usada pelo Publicador ao se conectar ao Distribuidor remoto) e o objeto <xref:Microsoft.SqlServer.Replication.DistributionDatabase> da etapa 3. Para obter mais informações, consulte [Proteger o Distribuidor](security/secure-the-distributor.md).  
  
    > [!IMPORTANT]  
    >  Quando possível, solicite que os usuários insiram as credenciais de segurança em tempo de execução. Se for preciso armazenar credenciais, use os serviços [criptográficos](https://go.microsoft.com/fwlink/?LinkId=34733) fornecidos pelo [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework do Windows.  
  
6.  Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.DistributionPublisher>.  
  
7.  Defina as seguintes propriedades de <xref:Microsoft.SqlServer.Replication.DistributionPublisher>:  
  
    -   <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> - o nome do servidor do Publicador local.  
  
    -   <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> - o <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 1.  
  
    -   <xref:Microsoft.SqlServer.Replication.DistributionPublisher.DistributionDatabase%2A> - o nome do banco de dados criado na etapa 5.  
  
    -   <xref:Microsoft.SqlServer.Replication.DistributionPublisher.WorkingDirectory%2A> - o compartilhamento usado para acessar os arquivos de instantâneos.  
  
    -   <xref:Microsoft.SqlServer.Replication.DistributionPublisher.PublisherSecurity%2A> - o modo de segurança usado durante a conexão com o Publicador. O<xref:Microsoft.SqlServer.Replication.ConnectionSecurityContext.WindowsAuthentication%2A> é recomendado.  
  
8.  Chame o método <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Create%2A> .  
  
9. Crie uma conexão com o servidor do Publicador local usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .  
  
10. Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>. Passe a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 9.  
  
11. Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationServer.InstallDistributor%2A> . Passe o nome do Distribuidor remoto e a senha para o Distribuidor remoto especificados na etapa 5.  
  
    > [!IMPORTANT]  
    >  Quando possível, solicite que os usuários insiram as credenciais de segurança em tempo de execução. Se for preciso armazenar credenciais, use os [serviços criptográficos](https://go.microsoft.com/fwlink/?LinkId=34733) fornecidos pelo Windows .NET Framework.  
  
###  <a name="example-rmo"></a><a name="PShellExample"></a> Exemplo (RMO)  
 Você pode configurar a replicação da publicação e da distribuição de forma programada usando o RMO (Replication Management Objects).  
  
 [!code-csharp[HowTo#rmo_AddDistPub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_adddistpub)]  
  
 [!code-vb[HowTo#rmo_vb_AddDistPub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_adddistpub)]  
  
## <a name="see-also"></a>Consulte Também  
 [Exibir e modificar propriedades de Publicador e Distribuidor](view-and-modify-distributor-and-publisher-properties.md)   
 [Replication System Stored Procedures Concepts](concepts/replication-system-stored-procedures-concepts.md)   
 [Configurar Distribuição](configure-distribution.md)   
 [Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md)   
 [Configurar a replicação para Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/always-on-availability-groups-sql-server.md) 
  
  
