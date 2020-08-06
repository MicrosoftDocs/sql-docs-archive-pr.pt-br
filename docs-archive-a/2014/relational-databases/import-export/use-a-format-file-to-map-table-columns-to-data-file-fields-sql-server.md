---
title: Usar um arquivo de formato para mapear colunas de uma tabela para campos de arquivo de dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- mapping columns to fields during import [SQL Server]
- format files [SQL Server], mapping columns to fields
ms.assetid: e7ee4f7e-24c4-4eb7-84d2-41e57ccc1ef1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c7de0b5ce486f187a1bdd27197984aa3c411f4a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571393"
---
# <a name="use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server"></a><span data-ttu-id="86fda-102">Usar um arquivo de formato para mapear colunas de uma tabela para campos de arquivo de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="86fda-102">Use a Format File to Map Table Columns to Data-File Fields (SQL Server)</span></span>
  <span data-ttu-id="86fda-103">Um arquivo de dados pode conter campos organizados em uma ordem diferente das colunas correspondentes na tabela.</span><span class="sxs-lookup"><span data-stu-id="86fda-103">A data file can contain fields arranged in a different order from the corresponding columns in the table.</span></span> <span data-ttu-id="86fda-104">Este tópico apresenta arquivos de formato não XML e XML que foram modificados para acomodar um arquivo de dados cujos campos são organizados em uma ordem diferente das colunas da tabela.</span><span class="sxs-lookup"><span data-stu-id="86fda-104">This topic presents both non-XML and XML format files that have been modified to accommodate a data file whose fields are arranged in a different order from the table columns.</span></span> <span data-ttu-id="86fda-105">O arquivo de formato modificado mapeia os campos de dados para as colunas da tabela correspondentes.</span><span class="sxs-lookup"><span data-stu-id="86fda-105">The modified format file maps the data fields to their corresponding table columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86fda-106">Um arquivo de formato não XML ou um arquivo de formato XML pode ser usado para importar em massa um arquivo de dados para a tabela usando um comando **bcp** , instrução BULK INSERT ou INSERT... Selecione \* da instrução OPENROWSET (BULK...).</span><span class="sxs-lookup"><span data-stu-id="86fda-106">Either a non-XML format file or an XML format file can be used to bulk import a data file into the table by using a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="86fda-107">Para obter mais informações, veja [Usar um arquivo de formato para importação de dados em massa &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="86fda-107">For more information, see [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span></span>  
  
## <a name="sample-table-and-data-file"></a><span data-ttu-id="86fda-108">Tabela e arquivo de dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="86fda-108">Sample Table and Data File</span></span>  
 <span data-ttu-id="86fda-109">Os exemplos de arquivos de formato modificados neste tópico baseiam-se na tabela e no arquivo de dados a seguir.</span><span class="sxs-lookup"><span data-stu-id="86fda-109">The examples of modified format files in this topic are based on the following table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="86fda-110">Tabela de exemplo</span><span class="sxs-lookup"><span data-stu-id="86fda-110">Sample Table</span></span>  
 <span data-ttu-id="86fda-111">Os exemplos neste tópico exigem a criação de uma tabela denominada `myTestOrder` no banco de dados de exemplo [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sob o esquema `dbo`.</span><span class="sxs-lookup"><span data-stu-id="86fda-111">The examples in this topic require that a table named `myTestOrder` be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="86fda-112">Para criar essa tabela, no Editor de Consultas do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], execute o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="86fda-112">To create this table, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestOrder   
   (  
   Col1 smallint,  
   Col2 nvarchar(50) ,  
   Col3 nvarchar(50) ,   
   Col4 nvarchar(50)   
   );  
GO  
  
```  
  
### <a name="data-file"></a><span data-ttu-id="86fda-113">Arquivo de dados</span><span class="sxs-lookup"><span data-stu-id="86fda-113">Data File</span></span>  
 <span data-ttu-id="86fda-114">O arquivo de dados `myTestOrder-c.txt` contém os seguintes registros:</span><span class="sxs-lookup"><span data-stu-id="86fda-114">The data file, `myTestOrder-c.txt`, contains the following records:</span></span>  
  
```  
DataField3,DataField2,1,DataField4  
DataField3,DataField2,1,DataField4  
DataField3,DataField2,1,DataField4  
  
```  
  
 <span data-ttu-id="86fda-115">Para importar dados em massa do `myTestSkipCol2-c.dat` para a tabela `myTestSkipCol`, o arquivo de formato deve mapear o primeiro campo de dados para `Col3`, o segundo campo de dados para `Col2`, o terceiro campo de dados para `Col1`e o quarto campo de dados para `Col4`.</span><span class="sxs-lookup"><span data-stu-id="86fda-115">To bulk import data from `myTestSkipCol2-c.dat` into the `myTestSkipCol` table, the format file must map the first data field to `Col3`, the second data field to `Col2`, the third data field to `Col1`, and the fourth data field to `Col4`.</span></span>  
  
## <a name="using-a-non-xml-format-file"></a><span data-ttu-id="86fda-116">Usando um arquivo de formato não XML</span><span class="sxs-lookup"><span data-stu-id="86fda-116">Using a Non-XML Format File</span></span>  
 <span data-ttu-id="86fda-117">Você pode alterar a ordem de um mapeamento de coluna alterando o valor da ordem da coluna para indicar a posição do campo de dados correspondente.</span><span class="sxs-lookup"><span data-stu-id="86fda-117">You can change the order of a column mapping by changing the order value for the column to indicate the position of the corresponding data field.</span></span>  
  
 <span data-ttu-id="86fda-118">O exemplo de arquivo de formato não XML a seguir apresenta um arquivo de formato, `myTestOrder.fmt`, que mapeia os campos no `myTestOrder-c.txt` para as colunas da tabela `myTestOrder`.</span><span class="sxs-lookup"><span data-stu-id="86fda-118">The following sample non-XML format file presents a format file, `myTestOrder.fmt`, that maps the fields in `myTestOrder-c.txt` to the columns of the `myTestOrder` table.</span></span> <span data-ttu-id="86fda-119">Para obter informações sobre como criar o arquivo de dados e a tabela, consulte "Tabela e arquivo de dados de exemplo" anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="86fda-119">For information about how to create the data file and table, see "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="86fda-120">O arquivo de formato usa o formato de dados de caracteres.</span><span class="sxs-lookup"><span data-stu-id="86fda-120">The format file uses character data format.</span></span>  
  
 <span data-ttu-id="86fda-121">Ele contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="86fda-121">The format file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       100     ","     3     Col3               SQL_Latin1_General_CP1_CI_AS  
2       SQLCHAR       0       100     ","     2     Col2               SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       7       ","     1     Col1               ""  
4       SQLCHAR       0       100     "\r\n"  4     Col4               SQL_Latin1_General_CP1_CI_AS  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="86fda-122">Para obter mais informações sobre o layout dos arquivos de formato não XML, veja [Arquivos de formato não XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="86fda-122">For more information about the layout of non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="86fda-123">Exemplo</span><span class="sxs-lookup"><span data-stu-id="86fda-123">Example</span></span>  
 <span data-ttu-id="86fda-124">O exemplo abaixo usa uma instrução `BULK INSERT` para importar dados em massa do arquivo de dados `myTestOrder-c.txt` para a tabela de exemplo `myTestOrder` usando o arquivo de formato não XML `myTestOrder.fmt`.</span><span class="sxs-lookup"><span data-stu-id="86fda-124">The following example uses a `BULK INSERT` statement to bulk import data from the `myTestOrder-c.txt` data file into the `myTestOrder` sample table by using the `myTestOrder.fmt` non-XML format file.</span></span>  
  
 <span data-ttu-id="86fda-125">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], execute:</span><span class="sxs-lookup"><span data-stu-id="86fda-125">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BULK INSERT myTestOrder  
FROM 'C:\myTestOrder-c.txt'   
WITH (formatfile='C:\myTestOrder.fmt');  
GO  
  
```  
  
## <a name="using-an-xml-format-file"></a><span data-ttu-id="86fda-126">Usando um arquivo de formato XML</span><span class="sxs-lookup"><span data-stu-id="86fda-126">Using an XML Format File</span></span>  
 <span data-ttu-id="86fda-127">O exemplo de arquivo de formato não XML a seguir apresenta um arquivo de formato, `myTestOrder.xml`, que mapeia os campos no `myTestOrder-c.txt` para as colunas da tabela `myTestOrder`. Para obter informações sobre como criar o arquivo de dados e a tabela, consulte "Tabela e arquivo de dados de exemplo" anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="86fda-127">The following sample non-XML format file presents a format file, `myTestOrder.xml`, that maps the fields in `myTestOrder-c.txt` to the columns of the `myTestOrder` table For information about how to create the data file and table, see "Sample Table and Data File," earlier in this topic.</span></span>  
  
 <span data-ttu-id="86fda-128">O arquivo de formato `myTestOrder.xml` contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="86fda-128">The `myTestOrder.xml` format file contains the following information:</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>  
  <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="3" NAME="Col1" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="1" NAME="Col3" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Col4" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="86fda-129">Para obter informações sobre a sintaxe do esquema XML e exemplos adicionais de arquivos de formato XML, veja [Arquivos de formato XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="86fda-129">For information about the syntax of the XML Schema and additional samples of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="86fda-130">Exemplo</span><span class="sxs-lookup"><span data-stu-id="86fda-130">Example</span></span>  
 <span data-ttu-id="86fda-131">O exemplo abaixo usa o provedor de conjuntos de linhas em massa `OPENROWSET` para importar dados do arquivo de dados `myTestOrder-c.txt` para a tabela de exemplo `myTestOrder` usando o arquivo de formato XML `myTestOrder.xml`.</span><span class="sxs-lookup"><span data-stu-id="86fda-131">The following example uses the `OPENROWSET` bulk rowset provider to import data from the `myTestOrder-c.txt` data file into the `myTestOrder` sample table by using the `myTestOrder.xml` XML format file.</span></span> <span data-ttu-id="86fda-132">A instrução `INSERT... SELECT` especifica a lista de colunas na lista de seleção.</span><span class="sxs-lookup"><span data-stu-id="86fda-132">The `INSERT... SELECT` statement specifies the column list in the select list.</span></span>  
  
 <span data-ttu-id="86fda-133">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , execute o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="86fda-133">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestOrder   
  SELECT Col1, Col2, Col3, Col4  
      FROM  OPENROWSET(BULK  'C:\myTestOrder-c.txt',  
      FORMATFILE='C:\myTestOrder.Xml'    
       ) AS t1;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="86fda-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="86fda-134">See Also</span></span>  
 <span data-ttu-id="86fda-135">[Usar um arquivo de formato para ignorar uma coluna de tabela &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="86fda-135">[Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span></span>  
 [<span data-ttu-id="86fda-136">Usar um arquivo de formato para ignorar um campo de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="86fda-136">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
  
