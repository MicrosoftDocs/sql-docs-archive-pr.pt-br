---
title: Banco de dados de publicação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.publicationdatabase.f1
ms.assetid: a9fafc9b-9963-4b59-97a0-3472158fa665
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 511e5f2e2caa934313ba96fb3dbc4cadddace968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569352"
---
# <a name="publication-database"></a>Banco de dados de publicação
  O banco de dados de publicação é o banco de dados no publicador que é a fonte dos dados e objetos de banco de dados a serem replicados. Cada banco de dados de publicação usado na replicação deve ser habilitado. O banco de dados está habilitado quando um membro da função de servidor fixa **sysadmin** :  
  
-   Cria uma publicação naquele banco de dados usando o Assistente para Nova Publicação.  
  
-   Seleciona o banco de dados na caixa de diálogo **Propriedades do Publicador** .  
  
-   Executa **sp_replicationdboption** e define a opção **publish** (para publicações transacionais ou de instantâneo) ou **merge publish** (para publicações de mesclagem) como **True**.  
  
## <a name="options"></a>Opções  
 **Bancos de dados**  
 Selecione o nome do banco de dados que contém os dados e os objetos de banco de dados que você quer publicar.  
  
## <a name="see-also"></a>Consulte Também  
 [Publicar dados e objetos de banco de dados](publish/publish-data-and-database-objects.md)   
 [Create a Publication](publish/create-a-publication.md)   
 [Exibir e modificar propriedades de Publicador e Distribuidor](view-and-modify-distributor-and-publisher-properties.md)   
 [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql)  
  
  
