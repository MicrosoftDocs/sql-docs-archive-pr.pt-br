---
title: Assinantes não SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [SQL Server replication], non-SQL Server Subscribers
- heterogeneous data sources, non-SQL Server Subscribers
- heterogeneous data sources
- heterogeneous database replication, non-SQL Server Subscribers
- non-SQL Server Subscribers, about non-SQL Server Subscribers
- heterogeneous Subscribers
- heterogeneous Subscribers, about heterogeneous Subscribers
- Subscribers [SQL Server replication], non-SQL Server Subscribers
- non-SQL Server Subscribers
ms.assetid: 831e7586-2949-4b9b-a2f3-7b0b699b23ff
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3a42ba5aedff4f23c6fb6be4155b1c6d4bf20471
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681576"
---
# <a name="non-sql-server-subscribers"></a>Non-SQL Server Subscribers
  Os seguintes Assinantes não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] podem assinar as publicações de instantâneo e transacionais usando assinaturas push. As assinaturas oferecem suporte para as duas versões mais recentes de cada banco de dados listadas usando a mais recente versão do provedor OLE DB listado.  
  
 A replicação heterogênea para assinantes que não são do SQL Server foi preterida. A publicação Oracle foi preterida. Para mover dados, crie soluções usando a captura de dados de alterações e o [!INCLUDE[ssIS](../../../includes/ssis-md.md)].  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
|Banco de dados|Sistema operacional|Provedor|  
|--------------|----------------------|--------------|  
|Oracle|Todas as plataformas que o Oracle dá suporte|Provedor Oracle OLE DB (fornecido pelo Oracle)|  
|IBM DB2|MVS, AS400, Unix, Linux, Windows menos 9.x|Microsoft Host Integration Server (HIS) provedor de OLE DB|  
  
 Para obter mais informações sobre como criar assinaturas ao Oracle e IBM DB2, consulte [Assinantes Oracle](oracle-subscribers.md) e [IBM DB2 Subscribers](ibm-db2-subscribers.md).  
  
## <a name="considerations-for-non-sql-server-subscribers"></a>Considerações para Assinantes não SQL Server  
 Lembre-se das seguintes considerações ao replicar Assinantes não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :  
  
### <a name="general-considerations"></a>Considerações gerais  
  
-   A replicação dá suporte a tabelas de publicação e exibições indexadas como tabelas para Assinantes não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (exibições indexadas não podem ser replicadas como exibições indexadas).  
  
-   Ao criar uma publicação no Assistente para nova publicação e, em seguida, habilitá-la para assinantes não SQL Server usando a caixa de diálogo Propriedades da publicação, o proprietário de todos os objetos no banco de dados de assinatura não é especificado para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] assinantes não, enquanto para [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] assinantes, ele é definido como o proprietário do objeto correspondente no banco de dados de publicação.  
  
-   Se a publicação tiver Assinantes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e Assinantes não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , a publicação deverá ser habilitada para Assinantes não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] antes de qualquer Assinante [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ser criado.  
  
-   Por padrão, scripts gerados pelo Agente de Instantâneo para Assinantes não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usam identificadores sem-aspas na sintaxe de CREATE TABLE. Portanto, uma tabela publicada nomeada 'teste' é reproduzida como 'TESTE'. Para usar o mesmo tipo de caixa (maiúscula/minúscula) como a tabela no banco de dados de publicação, use o parâmetro **-QuotedIdentifier** para o Agente de Distribuição. O parâmetro **-QuotedIdentifier** deve também ser usado se os nomes de objetos publicados (assim como tabelas, colunas e restrições) incluírem espaços ou palavras que são palavras reservadas na versão do banco de dados no Assinante não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . Para obter mais informações sobre esse parâmetro, consulte [Agente de Distribuição de Replicação](../agents/replication-distribution-agent.md).  
  
-   A conta na qual o Agente de Distribuição é executado deve ter acesso de leitura ao diretório de instalação do provedor OLE DB.  
  
-   Por padrão para Assinantes não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , o Agente de Distribuição usa o valor de [(destino padrão)] para o banco de dados da assinatura (o parâmetro **-SubscriberDB** para o Agente de Distribuição):  
  
    -   Para o Oracle, um servidor tem, no máximo, um banco de dados, assim não é necessário especificar o banco de dados.  
  
    -   Para IBM DB2, o banco de dados é especificado na cadeia de conexão DB2. Para obter mais informações, consulte [Criar uma assinatura para um Assinante não SQL Server](../create-a-subscription-for-a-non-sql-server-subscriber.md).  
  
-   Se o Distribuidor [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] estiver executando em uma plataforma de 64-bit, você deve usar a versão de 64-bit do provedor OLE DB do Oracle apropriado.  
  
-   A replicação move dados em formato Unicode independentemente da ordenação e das páginas de código usadas no Publicador e no Assinante. É recomendado que você escolha uma ordenação/página de código compatível ao replicar entre Publicadores e Assinantes.  
  
-   Se um artigo for adicionado ou excluído de uma publicação, assinaturas para Assinantes não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] devem ser reinicializadas.  
  
-   As únicas restrições que oferecem suporte para todos os Assinantes não -[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] são: NULL e NOT NULL. As restrições de chave primária são replicadas como índices exclusivos.  
  
-   O valor NULL é tratado de forma diferente por bancos de dados diferentes, o que afeta como um valor em branco, uma cadeia de caracteres vazia e um NULL são representados. Isto, por sua vez, afeta o comportamento de valores inseridos em colunas com restrições exclusivas definidas. Por exemplo, o Oracle permite valores múltiplos de NULL em uma coluna que é considerada exclusiva, enquanto o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] permite apenas um único valor NULL em uma coluna exclusiva.  
  
     Um fator adicional é como os valores de NULL, cadeias vazias, valores em branco são tratados quando a coluna é definida como NOT NULL. Para obter informações sobre como tratar deste assunto para Assinantes do Oracle, consulte [Assinantes Oracle](oracle-subscribers.md).  
  
-   Os metadados relacionados à replicação (tabela de sequência de transação) não são excluídos de não assinantes do[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quando a assinatura é removida.  
  
### <a name="conforming-to-the-requirements-of-the-subscriber-database"></a>Conformando aos requisitos do banco de dados do Assinante  
  
-   Esquema e dados publicados devem conformar-se aos requisitos do banco de dados no Assinante. Por exemplo, se um banco de dados não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tem um tamanho máximo de linha menor que o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], você deve assegurar-se de que o esquema e dados publicados não excedam esse tamanho.  
  
-   Tabelas replicadas para Assinantes não -[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] adotarão as convenções de nomenclatura de tabela do banco de dados no Assinante.  
  
-   Não existe suporte para DDL para Assinantes não SQL Server. Para obter mais informações sobre alterações de esquema, consulte [Fazer alterações de esquema em bancos de dados de publicação](../publish/make-schema-changes-on-publication-databases.md).  
  
### <a name="replication-feature-support"></a>Suporte de recurso da replicação  
  
-   O[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] oferece dois tipos de assinatura: push e pull. Assinantes não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] devem usar assinaturas push onde o Agente de Distribuição é executado no Distribuidor [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .  
  
-   O[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] oferece dois formatos de instantâneo: modo de bcp nativo e modo de caractere. Assinantes não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] requerem instantâneos de modo de caractere.  
  
-   Assinantes não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] não podem usar atualização imediata ou assinatura de atualização em fila ou ser nós em uma topologia de mesmo nível.  
  
-   Assinantes não[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] não podem ser inicializados automaticamente de um backup.  
  
## <a name="see-also"></a>Consulte Também  
 [Replicação de banco de dados heterogênea](heterogeneous-database-replication.md)   
 [Assinar publicações](../subscribe-to-publications.md)  
  
  
