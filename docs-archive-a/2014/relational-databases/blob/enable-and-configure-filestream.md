---
title: Habilitar e configurar FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], enabling
ms.assetid: 78737e19-c65b-48d9-8fa9-aa6f1e1bce73
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f6c0e505bd32636d045519b36e439bc21c7079d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568651"
---
# <a name="enable-and-configure-filestream"></a>Habilitar e configurar FILESTREAM
  Antes de começar a usar FILESTREAM, é necessário habilitá-lo na instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]. Este tópico descreve como habilitar o FILESTREAM usando o SQL Server Configuration Manager.  
  
> [!NOTE]  
>  Você não pode habilitar o FILESTREAM em uma versão de 32 bits do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sendo executada em um sistema operacional de 64 bits.  
  
##  <a name="enabling-filestream"></a><a name="enabling"></a> Habilitando FILESTREAM  
  
#### <a name="to-enable-and-change-filestream-settings"></a>Para habilitar e alterar configurações de FILESTREAM  
  
1.  No menu **Iniciar** , aponte para **Todos os Programas**, aponte para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], aponte para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.  
  
2.  Na lista de serviços, clique com o botão direito do mouse em **Serviços do SQL Server**e clique em **Abrir**.  
  
3.  No snap-in **SQL Server Configuration Manager** , localize a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] na qual deseja habilitar o FILESTREAM.  
  
4.  Clique com o botão direito do mouse na instância e clique em **Propriedades**.  
  
5.  Na caixa de diálogo **Propriedades do SQL Server** , clique na guia **FILESTREAM** .  
  
6.  Marque a caixa de seleção **Habilitar FILESTREAM para acesso a Transact-SQL** .  
  
7.  Se você quiser ler e gravar dados FILESTREAM no Windows, clique em **Habilitar FILESTREAM para acesso de streaming de E/S de arquivos**. Insira o nome do compartilhamento do Windows na caixa **Nome de Compartilhamento do Windows** .  
  
8.  Se os clientes remotos precisarem acessar os dados do FILESTREAM armazenados em seu compartilhamento, selecione **Permitir que os clientes remotos tenham acesso de streaming aos dados de FILESTREAM**.  
  
9. Clique em **Aplicar**.  
  
10. No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], clique em **Nova Consulta** para exibir o Editor de Consultas.  
  
11. No Editor de Consultas, insira o seguinte código [!INCLUDE[tsql](../../includes/tsql-md.md)] :  
  
    ```sql  
    EXEC sp_configure filestream_access_level, 2  
    RECONFIGURE  
    ```  
  
12. Clique em **Executar**.  
  
13. Reinicie o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  

  
##  <a name="best-practices"></a><a name="best"></a> Práticas recomendadas  
  
###  <a name="physical-configuration-and-maintenance"></a><a name="config"></a>Configuração física e manutenção  
 Ao configurar volumes de armazenamento de FILESTREAM, considere as seguintes diretrizes:  
  
-   Desative nomes de arquivos curtos em sistemas de computador FILESTREAM. Nomes de arquivos curtos precisam de significativamente mais tempo para serem criados. Para desabilitar nomes de arquivos curtos, use o utilitário **fsutil** do Windows.  
  
-   Desfragmente regularmente os sistemas de computador FILESTREAM.  
  
-   Use clusters de NTFS de 64 KB. Volumes compactados devem ser definidos como clusters de NTFS de 4 KB.  
  
-   Desabilite a indexação em volumes de FILESTREAM e defina **disablelastaccess** . Para definir **disablelastaccess**, use o utilitário **fsutil** do Windows.  
  
-   Desabilite a verificação antivírus de volumes FILESTREAM quando ela for desnecessária. Se a verificação antivírus for necessária, evite políticas de configuração que excluirão automaticamente os arquivos incorretos.  
  
-   Configure e ajuste o nível de RAID para tolerância a falhas e para o desempenho exigido por um aplicativo.  
  
||||||  
|-|-|-|-|-|  
|Nível de RAID|Desempenho de gravação|Desempenho de leitura|Tolerância a falhas|Comentários|  
|RAID 5|Normal|Normal|Excelente|O desempenho é melhor do que o de um disco ou JBOD; e menor do que o do RAID 0 ou do RAID 5 com distribuição.|  
|RAID 0|Excelente|Excelente|Nenhum||  
|RAID 5 + distribuição|Excelente|Excelente|Excelente|A opção mais cara.|  
  

  
###  <a name="physical-database-design"></a><a name="database"></a>Design de banco de dados físico  
 Ao criar um banco de dados de FILESTREAM, considere as seguintes diretrizes:  
  
-   As colunas FILESTREAM devem ser acompanhadas por uma `uniqueidentifier` coluna rowguid correspondente. Esses tipos de tabelas também devem ser acompanhados por um índice exclusivo. Normalmente esse índice não é um índice clusterizado. Se a lógica corporativa do bancos de dados exigir um índice clusterizado, você precisará verificar se os valores armazenados no índice não são aleatórios. Valores aleatórios farão com que o índice seja reorganizado toda vez que uma linha for adicionada ou removida da tabela.  
  
-   Por razões de desempenho, grupos de arquivos e contêineres de FILESTREAM devem residir em volumes diferentes do sistema operacional, do banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , do log do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , do tempdb ou do arquivo de paginação.  
  
-   Gerenciamento e políticas de espaço não são diretamente suportados por FILESTREAM. No entanto, você pode gerenciar espaço e aplicar políticas indiretamente atribuindo cada grupo de arquivos de FILESTREAM a um volume separado e usando os recursos do gerenciamento do volume.  
  
  
