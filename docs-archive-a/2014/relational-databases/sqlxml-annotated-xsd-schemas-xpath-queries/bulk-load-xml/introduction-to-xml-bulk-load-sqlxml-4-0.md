---
title: Introdução ao carregamento em massa de XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- nontransacted XML Bulk Load operations
- XML Bulk Load [SQLXML], about XML Bulk Load
- bulk load [SQLXML], about bulk load
- transacted XML Bulk Load operations
- streaming XML data
ms.assetid: 38bd3cbd-65ef-4c23-9ef3-e70ecf6bb88a
author: rothja
ms.author: jroth
ms.openlocfilehash: 4f3e0e78edd967e5fcb7377312c1811d34cb1ef8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678686"
---
# <a name="introduction-to-xml-bulk-load-sqlxml-40"></a><span data-ttu-id="ce9b9-102">Introdução ao XML Bulk Load (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="ce9b9-102">Introduction to XML Bulk Load (SQLXML 4.0)</span></span>
  <span data-ttu-id="ce9b9-103">O carregamento em massa de XML é um objeto COM autônomo que permite carregar dados XML semiestruturados em tabelas da Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce9b9-103">XML Bulk Load is a stand-alone COM object that allows you to load semistructured XML data into Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables.</span></span>  
  
 <span data-ttu-id="ce9b9-104">Você pode inserir dados XML em um banco de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando um comando INSERT e a função OPENXML; no entanto, o utilitário Bulk Load garante um melhor desempenho quando você precisa inserir grandes quantidades de dados XML.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-104">You can insert XML data into a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database by using an INSERT statement and the OPENXML function; however, the Bulk Load utility provides better performance when you need to insert large amounts of XML data.</span></span>  
  
 <span data-ttu-id="ce9b9-105">O método Execute do modelo de objeto de carregamento em massa XML usa dois parâmetros:</span><span class="sxs-lookup"><span data-stu-id="ce9b9-105">The Execute method of the XML Bulk Load object model takes two parameters:</span></span>  
  
-   <span data-ttu-id="ce9b9-106">Um esquema XSD (XML Schema Definition) anotado ou esquema XDR (XML-Data Reduced).</span><span class="sxs-lookup"><span data-stu-id="ce9b9-106">An annotated XML Schema Definition (XSD) or XML-Data Reduced (XDR) schema.</span></span> <span data-ttu-id="ce9b9-107">O utilitário XML Bulk Load interpreta esse esquema de mapeamento e as anotações especificadas no esquema ao identificar as tabelas do SQL Server nas quais os dados XML serão inseridos.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-107">The XML Bulk Load utility interprets this mapping schema and the annotations that are specified in the schema in identifying the SQL Server tables into which the XML data is to be inserted.</span></span>  
  
-   <span data-ttu-id="ce9b9-108">Um documento XML ou fragmento de documento (um documento sem elementos de alto nível).</span><span class="sxs-lookup"><span data-stu-id="ce9b9-108">An XML document or document fragment (a document fragment is a document without a single top-level element).</span></span> <span data-ttu-id="ce9b9-109">É possível especificar um nome de arquivo ou um fluxo do qual o XML Bulk Load pode ler.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-109">A file name or a stream from which XML Bulk Load can read can be specified.</span></span>  
  
 <span data-ttu-id="ce9b9-110">O XML Bulk Load interpreta o esquema de mapeamento e identifica a tabela na qual os dados XML serão inseridos.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-110">XML Bulk Load interprets the mapping schema and identifies the table(s) into which the XML data is to be inserted.</span></span>  
  
 <span data-ttu-id="ce9b9-111">Pressupõe-se que você esteja familiarizado com os seguintes recursos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ce9b9-111">It is assumed that you are familiar with the following [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features:</span></span>  
  
-   <span data-ttu-id="ce9b9-112">Esquemas XSD e XDR anotados.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-112">Annotated XSD and XDR schemas.</span></span> <span data-ttu-id="ce9b9-113">Para obter mais informações sobre esquemas XSD anotados, consulte [introdução aos esquemas XSD anotados &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ce9b9-113">For more information about annotated XSD schemas, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="ce9b9-114">Para obter informações sobre esquemas XDR anotados, consulte [esquemas XDR anotados &#40;preteridos no SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ce9b9-114">For information about annotated XDR schemas, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="ce9b9-115">Os mecanismos de inserção em massa do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], como a instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)]BULK INSERT e o utilitário bcp.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-115">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] bulk insert mechanisms, such as the [!INCLUDE[tsql](../../../includes/tsql-md.md)] BULK INSERT statement and the bcp utility.</span></span> <span data-ttu-id="ce9b9-116">Para obter mais informações, consulte [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) e o [utilitário bcp](../../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ce9b9-116">For more information, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) and [bcp Utility](../../../tools/bcp-utility.md).</span></span>  
  
## <a name="streaming-of-xml-data"></a><span data-ttu-id="ce9b9-117">Fluindo de dados XML </span><span class="sxs-lookup"><span data-stu-id="ce9b9-117">Streaming of XML Data</span></span>  
 <span data-ttu-id="ce9b9-118">Como o documento XML de origem pode ser grande, ele não é lido na memória para o processamento do carregamento em massa.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-118">Because the source XML document can be large, the entire document is not read into memory for bulk load processing.</span></span> <span data-ttu-id="ce9b9-119">Em vez disso, o XML Bulk Load interpreta os dados XML como um fluxo e faz a leitura deles.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-119">Instead, XML Bulk Load interprets the XML data as a stream and reads it.</span></span> <span data-ttu-id="ce9b9-120">À medida que o utilitário lê os dados, ele identifica a(s) tabela(s) de banco de dados, gera o(s) registro(s) apropriado(s) a partir da fonte de dados XML e envia o(s) registro(s) para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para inserção.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-120">As the utility reads the data, it identifies the database table(s), generates the appropriate record(s) from the XML data source, and then sends the record(s) to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for insertion.</span></span>  
  
 <span data-ttu-id="ce9b9-121">Por exemplo, o seguinte documento XML de origem consiste em **\<Customer>** elementos e **\<Order>** elementos filho:</span><span class="sxs-lookup"><span data-stu-id="ce9b9-121">For example, the following source XML document consists of **\<Customer>** elements and **\<Order>** child elements:</span></span>  
  
```  
<Customer ...>  
    <Order.../>  
    <Order .../>  
     ...  
</Customer>  
...  
```  
  
 <span data-ttu-id="ce9b9-122">Como o carregamento em massa de XML lê o **\<Customer>** elemento, ele gera um registro para o CustomerTable.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-122">As XML Bulk Load reads the **\<Customer>** element, it generates a record for the Customertable.</span></span> <span data-ttu-id="ce9b9-123">Quando ele lê a **\</Customer>** marca de fim, o carregamento em massa de XML insere esse registro na tabela no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce9b9-123">When it reads the **\</Customer>** end tag, XML Bulk Load inserts that record into the table in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ce9b9-124">Da mesma forma, quando ele lê o **\<Order>** elemento, o carregamento em massa de XML gera um registro para ordertable e insere esse registro na tabela ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ler a marca de **\</Order>** fim.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-124">In the same way, when it reads the **\<Order>** element, XML Bulk Load generates a record for the Ordertable, and then inserts that record into the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] table upon reading the **\</Order>** end tag.</span></span>  
  
## <a name="transacted-and-nontransacted-xml-bulk-load-operations"></a><span data-ttu-id="ce9b9-125">Operações de carregamento em massa de XML transacionadas e não transacionadas</span><span class="sxs-lookup"><span data-stu-id="ce9b9-125">Transacted and Nontransacted XML Bulk Load Operations</span></span>  
 <span data-ttu-id="ce9b9-126">O XML Bulk Load pode operar no modo transacionado ou não transacionado.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-126">XML Bulk Load can operate in either a transacted or a nontransacted mode.</span></span> <span data-ttu-id="ce9b9-127">O desempenho geralmente é ideal se você estiver carregando em massa em um modo não-Transacted: ou seja, a propriedade Transaction está definida como FALSE) e qualquer uma das condições a seguir é verdadeira:</span><span class="sxs-lookup"><span data-stu-id="ce9b9-127">Performance is usually optimal if you are bulk loading in a nontransacted mode: that is, the Transaction property is set to FALSE) and either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="ce9b9-128">As tabelas nas quais os dados são carregados em massa são vazias e não têm índices.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-128">The tables into which the data is bulk loaded are empty with no indexes.</span></span>  
  
-   <span data-ttu-id="ce9b9-129">As tabelas têm dados e índices exclusivos.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-129">The tables have data and unique indexes.</span></span>  
  
 <span data-ttu-id="ce9b9-130">A abordagem não transacionada não garante uma reversão se algo de errado acontecer no processo de carregamento em massa (embora reversões parciais possam ser feitas).</span><span class="sxs-lookup"><span data-stu-id="ce9b9-130">The nontransacted approach does not guarantee a rollback if something goes wrong in the bulk load process (although partial rollbacks can happen).</span></span> <span data-ttu-id="ce9b9-131">O carregamento em massa não transacionado é apropriado quando o banco de dados está vazio.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-131">The nontransacted bulk load is appropriate when the database is empty.</span></span> <span data-ttu-id="ce9b9-132">Portanto, se algo der errado, você poderá limpar o banco de dados e iniciar o XML Bulk Load novamente.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-132">Therefore, if something does go wrong, you can clean the database and start XML Bulk Load again.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce9b9-133">No modo não transacionado, o XML Bulk Load usa uma transação interna padrão e a confirma.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-133">In nontransacted mode, XML Bulk Load uses a default internal transaction and commits it.</span></span> <span data-ttu-id="ce9b9-134">Quando a propriedade Transaction é definida como TRUE, o carregamento em massa de XML não chama Commit nessa transação.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-134">When the Transaction property is set to TRUE, XML Bulk Load does not call commit on this transaction.</span></span>  
  
 <span data-ttu-id="ce9b9-135">Se a propriedade Transaction for definida como TRUE, o carregamento em massa de XML criará arquivos temporários, um para cada tabela identificada no esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-135">If the Transaction property is set to TRUE, XML Bulk Load creates temporary files, one for each table that is identified in the mapping schema.</span></span> <span data-ttu-id="ce9b9-136">O XML Bulk Load primeiro armazena os registros do documento XML de origem nesses arquivos temporários.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-136">XML Bulk Load first stores the records from the source XML document in these temporary files.</span></span> <span data-ttu-id="ce9b9-137">Em seguida, uma instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)] BULK INSERT recupera esses registros dos arquivos e os armazena nas tabelas correspondentes.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-137">Then, a [!INCLUDE[tsql](../../../includes/tsql-md.md)] BULK INSERT statement retrieves these records from the files and stores them in the corresponding tables.</span></span> <span data-ttu-id="ce9b9-138">Você pode especificar o local para esses arquivos temporários usando a propriedade TempFilePath.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-138">You can specify the location for these temporary files by using the TempFilePath property.</span></span> <span data-ttu-id="ce9b9-139">Você deve assegurar que a conta [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usada com o XML Bulk Load tenha acesso a esse caminho.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-139">You must ensure that the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] account used with XML Bulk Load has access to this path.</span></span> <span data-ttu-id="ce9b9-140">Se a propriedade TempFilePath não for especificada, o caminho de arquivo padrão especificado na variável de ambiente TEMP será usado para criar os arquivos temporários.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-140">If the TempFilePath property is not specified, the default file path that is specified in the TEMP environment variable is used to create the temporary files.</span></span>  
  
 <span data-ttu-id="ce9b9-141">Se a propriedade Transaction for definida como FALSE (a configuração padrão), o carregamento em massa de XML usará a interface OLE DB IRowsetFastLoad para carregar os dados em massa.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-141">If the Transaction property is set to FALSE (the default setting), XML Bulk Load uses the OLE DB interface IRowsetFastLoad to bulk load the data.</span></span>  
  
 <span data-ttu-id="ce9b9-142">Se a propriedade ConnectionString definir a cadeia de conexão e a propriedade Transaction for definida como TRUE, o carregamento em massa de XML funcionará em seu próprio contexto de transação.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-142">If the ConnectionString property sets the connection string, and the Transaction property is set to TRUE, XML Bulk Load operates in its own transaction context.</span></span> <span data-ttu-id="ce9b9-143">(Por exemplo, o XML Bulk Load inicia sua própria transação e confirma ou reverte conforme apropriado.)</span><span class="sxs-lookup"><span data-stu-id="ce9b9-143">(For example, XML Bulk Load starts its own transaction, and commits or rolls back as appropriate.)</span></span>  
  
 <span data-ttu-id="ce9b9-144">Se a propriedade ConnectionCommand definir a conexão com um objeto de conexão existente e a propriedade Transaction for definida como TRUE, o carregamento em massa de XML não emitirá uma instrução COMMIT ou ROLLBACK no caso de um êxito ou uma falha, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-144">If the ConnectionCommand property sets the connection with an existing connection object and the Transaction property is set to TRUE, XML Bulk Load does not issue a COMMIT or ROLLBACK statement in the case of a success or a failure, respectively.</span></span> <span data-ttu-id="ce9b9-145">Caso haja um erro, o XML Bulk Load retornará a mensagem de erro apropriada.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-145">If there is an error, XML Bulk Load returns the appropriate error message.</span></span> <span data-ttu-id="ce9b9-146">A decisão de executar uma instrução COMMIT ou ROLLBACK fica a cargo do cliente que iniciou o carregamento em massa.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-146">The decision to issue a COMMIT or ROLLBACK statement is left to the client that initiated the bulk load.</span></span> <span data-ttu-id="ce9b9-147">O objeto de conexão usado para o carregamento em massa de XML deve ser do tipo ICommand ou ser um objeto de comando ADO.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-147">The connection object that is used for XML Bulk Load should be of type ICommand or be an ADO command object.</span></span>  
  
 <span data-ttu-id="ce9b9-148">No SQLXML 4,0, um ConnectionObject não pode ser usado com a propriedade Transaction definida como FALSE.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-148">In SQLXML 4.0, a ConnectionObject cannot be used with the Transaction property set to FALSE.</span></span> <span data-ttu-id="ce9b9-149">Não há suporte para o modo não-Transacted com um ConnectionObject porque é impossível abrir mais de uma interface IRowsetFastLoad em uma sessão passada.</span><span class="sxs-lookup"><span data-stu-id="ce9b9-149">The nontransacted mode is not supported with a ConnectionObject because it is impossible to open more than one IRowsetFastLoad interface on a passed-in session.</span></span>  
  
  