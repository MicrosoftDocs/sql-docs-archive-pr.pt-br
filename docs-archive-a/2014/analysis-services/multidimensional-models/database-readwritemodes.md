---
title: Banco de dados ReadWriteModes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- databases [Analysis Services], read/write
- databases [Analysis Services], read-only
ms.assetid: 03d7cb5c-7ff0-4e15-bcd2-7075d1b0dd69
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1cd1e5585e738cd298a3bedd31e2f2f512dcae45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680109"
---
# <a name="database-readwritemodes"></a>Banco de dados ReadWriteModes
  Existem situações frequentes em que um DBA (administrador de banco de dados) do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] quer alterar o banco de dados de leitura/gravação para um banco de dados somente leitura ou vice-versa. Essas situações frequentemente são conduzidas pelas necessidades comerciais, como o compartilhamento da mesma pasta do banco de dados com vários servidores para expandir uma solução e melhorar o desempenho. Para essas situações, a `ReadWriteMode` Propriedade Database permite que o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] DBA Altere facilmente o modo operacional do banco de dados.  
  
## <a name="readwritemode-database-property"></a>Propriedade ReadWriteMode do banco de dados  
 A propriedade `ReadWriteMode` do banco de dados especifica se o banco de dados está em modo de leitura/gravação ou somente leitura. Estes são os únicos dois possíveis valores da propriedade. Quando o banco de dados está no modo somente leitura, nenhuma alteração ou atualização pode ser aplicada a ele. Entretanto, quando o banco de dados está no modo de leitura/gravação, podem ocorrer alterações e atualizações. A propriedade `ReadWriteMode` do banco de dados está definida como uma propriedade somente leitura; ela só pode ser definida por um comando `Attach`.  
  
 Quando um banco de dados é definido para o modo somente leitura, determinadas restrições entram em vigor e afetam o conjunto comum das operações permitidas no banco de dados. Consulte a tabela a seguir para obter as operações restritas.  
  
|Modo ReadOnly|Operações restritas|  
|-------------------|---------------------------|  
|Comandos XML/A<br /><br /> <br /><br /> Observação: ocorre um erro quando você executa qualquer um destes comandos.|`Create`<br /><br /> `Alter`<br /><br /> `Delete`<br /><br /> `Process`<br /><br /> `MergePartitions`<br /><br /> `DesignAggregations`<br /><br /> `CommitTransaction`<br /><br /> `Restore`<br /><br /> `Synchronize`<br /><br /> `Insert`<br /><br /> `Update`<br /><br /> `Drop`<br /><br /> <br /><br /> Observação: o write-back de célula é permitido em conjuntos de bancos de dados definidos como somente leitura, no entanto, as alterações não podem ser confirmadas.|  
|Instruções MDX<br /><br /> <br /><br /> Observação: ocorre um erro quando você executa qualquer uma destas instruções.|`COMMIT TRAN`<br /><br /> `CREATE SESSION CUBE`<br /><br /> `ALTER CUBE`<br /><br /> `ALTER DIMENSION`<br /><br /> `CREATE DIMENSION MEMBER`<br /><br /> `DROP DIMENSION MEMBER`<br /><br /> `ALTER DIMENSION`<br /><br /> <br /><br /> Observação: os usuários do Excel não podem usar o recurso de agrupamento em tabelas dinâmicas, pois esse recurso é implementado internamente usando os comandos `CREATE SESSION CUBE`.|  
|Instruções DMX<br /><br /> <br /><br /> Observação: ocorre um erro quando você executa qualquer uma destas instruções.|`CREATE [SESSION] MINING STRUCTURE`<br /><br /> `ALTER MINING STRUCTURE`<br /><br /> `DROP MINING STRUCTURE`<br /><br /> `CREATE [SESSION] MINING MODEL`<br /><br /> `DROP MINING MODEL`<br /><br /> `IMPORT`<br /><br /> `SELECT INTO`<br /><br /> `INSERT`<br /><br /> `UPDATE`<br /><br /> `DELETE`|  
|Operações em segundo plano|Todas as operações em segundo plano que poderiam modificar o banco de dados são desabilitadas. Isso inclui o processamento lento e o cache pró-ativo.|  
  
## <a name="readwritemode-usage"></a>Uso de ReadWriteMode  
 A propriedade `ReadWriteMode` do banco de dados será usada como parte de um comando `Attach` do banco de dados. O comando `Attach` permite que a propriedade do banco de dados seja definida como `ReadWrite` ou `ReadOnly`. O valor da propriedade `ReadWriteMode` do banco de dados não pode ser atualizado diretamente, pois a propriedade está definida como somente leitura. Os bancos de dados são criados com a propriedade `ReadWriteMode` definida como `ReadWrite`. Um banco de dados não pode ser criado no modo somente leitura.  
  
 Para alternar a `ReadWriteMode` propriedade de banco de dados entre `ReadWrite` e `ReadOnly` , você deve emitir uma sequência de `Detach/Attach` comandos.  
  
 Todas as operações do banco de dados, com exceção de `Attach`, mantêm a propriedade `ReadWriteMode` do banco de dados em seu estado atual. Por exemplo, operações como `Alter`, `Backup`, `Restore` e `Synchronize` preservam o valor `ReadWriteMode`.  
  
> [!NOTE]  
>  Podem ser criados cubos locais a partir de um banco de dados somente leitura.  
  
## <a name="see-also"></a>Consulte Também  
 <xref:Microsoft.AnalysisServices.Server.Attach%2A>   
 [Microsoft. AnalysisServices. Database. Detach *](/dotnet/api/microsoft.analysisservices.core.database.detach)   
 [Anexar e desanexar bancos de dados Analysis Services](attach-and-detach-analysis-services-databases.md)   
 [Mover um banco de dados Analysis Services](move-an-analysis-services-database.md)   
 [Elemento Detach](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element)   
 [Elemento Attach](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element)  
  
  
