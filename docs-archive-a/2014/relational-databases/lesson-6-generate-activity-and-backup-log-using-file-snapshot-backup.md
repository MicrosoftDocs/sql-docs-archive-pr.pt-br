---
title: 'Lição 7: mover seus arquivos de dados para o armazenamento do Azure | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 26aa534a-afe7-4a14-b99f-a9184fc699bd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 753863d7b8b8d8fa554f1579bee6837c525efd9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576372"
---
# <a name="lesson-7-move-your-data-files-to-azure-storage"></a>Lição 7: Migrar seus arquivos de dados para o Armazenamento do Microsoft Azure
  Nesta lição, você aprenderá a mover seus arquivos de dados para o armazenamento do Azure (mas não sua instância de SQL Server). Para acompanhar esta lição, você não precisará concluir as lições 4, 5 e 6.  
  
 Para mover seus arquivos de dados para o armazenamento do Azure, você pode usar a `ALTER DATABASE` instrução, pois ajuda a alterar o local dos arquivos de dados.  
  
 Esta lição supõe que você já concluiu as seguintes etapas:  
  
-   Você tem uma conta de armazenamento do Azure.  
  
-   Você criou um contêiner em sua conta de armazenamento do Azure.  
  
-   Você criou uma política em um contêiner com direitos de leitura, gravação e lista. Você também gerou uma chave de SAS.  
  
-   Você criou uma credencial do SQL Server no computador de origem.  
  
 Em seguida, use as seguintes etapas para mover seus arquivos de dados para o armazenamento do Azure:  
  
1.  Primeiro, crie um banco de dados de teste no computador de origem e adicione alguns dados a ele.  
  
    ```sql  
  
    USE master;   
    CREATE DATABASE TestDB1Alter;   
    GO   
    USE TestDB1Alter;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO  
  
    ```  
  
2.  Execute o código a seguir:  
  
    ```sql  
  
    -- In the following statement, modify the path specified in FILENAME to   
    -- the new location of the file in Azure Storage container.   
    ALTER DATABASE TestDB1Alter    
        MODIFY FILE ( NAME = TestDB1Alter,    
                    FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontaineralter/TestDB1AlterData.mdf');   
    GO  
  
    ```  
  
3.  Quando você executar isso, verá esta mensagem: "o arquivo" TestDB1Alter "foi modificado no catálogo do sistema. O novo caminho será usado na próxima vez que o banco de dados for iniciado. "  
  
4.  Em seguida, defina o banco de dados offline.  
  
    ```sql  
  
    ALTER DATABASE TestDB1Alter SET OFFLINE;   
    GO  
  
    ```  
  
5.  Agora, você precisa copiar os arquivos de dados para o armazenamento do Azure usando um dos seguintes métodos: [ferramenta AzCopy](https://docs.microsoft.com/archive/blogs/windowsazurestorage/azcopy-uploadingdownloading-files-for-windows-azure-blobs), [colocar página](https://msdn.microsoft.com/library/azure/ee691975.aspx), [referência da biblioteca de cliente de armazenamento](https://msdn.microsoft.com/library/azure/dn261237.aspx)ou uma ferramenta de Gerenciador de armazenamento de terceiros.  
  
     **Importante:** Ao usar esse novo aprimoramento, sempre certifique-se de criar um blob de páginas não um blob de blocos.  
  
6.  Em seguida, defina o banco de dados online.  
  
    ```sql  
  
    ALTER DATABASE TestDB1Alter SET ONLINE;   
    GO  
  
    ```  
  
 **Próxima lição:**  
  
 [Lição 8. Restaurar um banco de dados no armazenamento do Azure](lesson-7-restore-a-database-to-a-point-in-time.md)  
  
  
