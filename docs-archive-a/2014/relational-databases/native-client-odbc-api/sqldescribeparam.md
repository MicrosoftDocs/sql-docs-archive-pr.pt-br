---
title: SQLDescribeParam | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLDescribeParam function
ms.assetid: 396e74b1-5d08-46dc-b404-2ef2003e4689
author: rothja
ms.author: jroth
ms.openlocfilehash: 05e14ccb0fadb4f1cf05f965c79cf8c05c71f93a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575797"
---
# <a name="sqldescribeparam"></a><span data-ttu-id="43d66-102">SQLDescribeParam</span><span class="sxs-lookup"><span data-stu-id="43d66-102">SQLDescribeParam</span></span>
  <span data-ttu-id="43d66-103">Para descrever os parâmetros de qualquer instrução SQL, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client cria e executa uma [!INCLUDE[tsql](../../includes/tsql-md.md)] instrução SELECT quando SQLDescribeParam é chamado em um identificador de instrução ODBC preparado.</span><span class="sxs-lookup"><span data-stu-id="43d66-103">To describe the parameters of any SQL statement, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver builds and executes a [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statement when SQLDescribeParam is called on a prepared ODBC statement handle.</span></span> <span data-ttu-id="43d66-104">Os metadados do conjunto de resultados determinam as características dos parâmetros na instrução preparada.</span><span class="sxs-lookup"><span data-stu-id="43d66-104">The metadata of the result set determines the characteristics of the parameters in the prepared statement.</span></span> <span data-ttu-id="43d66-105">SQLDescribeParam pode retornar qualquer código de erro que SQLExecute ou SQLExecDirect possa retornar.</span><span class="sxs-lookup"><span data-stu-id="43d66-105">SQLDescribeParam can return any error code that SQLExecute or SQLExecDirect might return.</span></span>  
  
 <span data-ttu-id="43d66-106">Melhorias no mecanismo de banco de dados começando com [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] permitir SQLDescribeParam para obter descrições mais precisas dos resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="43d66-106">Improvements in the database engine starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow SQLDescribeParam to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="43d66-107">Esses resultados mais precisos podem ser diferentes dos valores retornados pelo SQLDescribeParam em versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="43d66-107">These more accurate results may differ from the values returned by SQLDescribeParam in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="43d66-108">Para obter mais informações, veja [Descoberta de metadados](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="43d66-108">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
 <span data-ttu-id="43d66-109">Também novo no [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , *ParameterSizePtr* agora retorna um valor que se alinha com a definição do tamanho, em caracteres, da coluna ou expressão do marcador de parâmetro correspondente, conforme definido na [especificação ODBC](https://go.microsoft.com/fwlink/?LinkId=207044).</span><span class="sxs-lookup"><span data-stu-id="43d66-109">Also new in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], *ParameterSizePtr* now returns a value that aligns with the definition for the size, in characters, of the column or expression of the corresponding parameter marker as defined in the [ODBC specification](https://go.microsoft.com/fwlink/?LinkId=207044).</span></span> <span data-ttu-id="43d66-110">Nas versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, *ParameterSizePtr* poderia ser o valor correspondente de `SQL_DESC_OCTET_LENGTH` para o tipo, ou um valor de tamanho de coluna irrelevante que foi fornecido a SQLBindParameter para um tipo, o valor que deve ser ignorado ( `SQL_INTEGER` , por exemplo).</span><span class="sxs-lookup"><span data-stu-id="43d66-110">In previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, *ParameterSizePtr* could be the corresponding value of `SQL_DESC_OCTET_LENGTH` for the type, or an irrelevant column size value that was supplied to SQLBindParameter for a type, the value of which should be ignored (`SQL_INTEGER`, for example).</span></span>  
  
 <span data-ttu-id="43d66-111">O driver não dá suporte à chamada de SQLDescribeParam nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="43d66-111">The driver does not support calling SQLDescribeParam in the following situations:</span></span>  
  
-   <span data-ttu-id="43d66-112">Após SQLExecDirect para quaisquer [!INCLUDE[tsql](../../includes/tsql-md.md)] instruções UPDATE ou DELETE que contenham a cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="43d66-112">After SQLExecDirect for any [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE or DELETE statements containing the FROM clause.</span></span>  
  
-   <span data-ttu-id="43d66-113">Para qualquer instrução ODBC ou [!INCLUDE[tsql](../../includes/tsql-md.md)] que contenha um parâmetro em uma cláusula HAVING, ou comparada ao resultado de uma função SUM.</span><span class="sxs-lookup"><span data-stu-id="43d66-113">For any ODBC or [!INCLUDE[tsql](../../includes/tsql-md.md)] statement containing a parameter in a HAVING clause, or compared to the result of a SUM function.</span></span>  
  
-   <span data-ttu-id="43d66-114">Para qualquer instrução ODBC ou [!INCLUDE[tsql](../../includes/tsql-md.md)] que dependa de uma subconsulta que contém parâmetros.</span><span class="sxs-lookup"><span data-stu-id="43d66-114">For any ODBC or [!INCLUDE[tsql](../../includes/tsql-md.md)] statement depending on a subquery containing parameters.</span></span>  
  
-   <span data-ttu-id="43d66-115">Para instruções SQL ODBC que contenham marcadores de parâmetro em ambas as expressões de uma comparação, like, ou predicado quantificado.</span><span class="sxs-lookup"><span data-stu-id="43d66-115">For ODBC SQL statements containing parameter markers in both expressions of a comparison, like, or quantified predicate.</span></span>  
  
-   <span data-ttu-id="43d66-116">Para qualquer consulta em que um dos parâmetros é um parâmetro para uma função.</span><span class="sxs-lookup"><span data-stu-id="43d66-116">For any queries where one of the parameters is a parameter to a function.</span></span>  
  
-   <span data-ttu-id="43d66-117">Quando houver comentários (/\* \* /) no [!INCLUDE[tsql](../../includes/tsql-md.md)] comando.</span><span class="sxs-lookup"><span data-stu-id="43d66-117">When there are comments (/\* \*/) in the [!INCLUDE[tsql](../../includes/tsql-md.md)] command.</span></span>  
  
 <span data-ttu-id="43d66-118">Ao processar um lote de [!INCLUDE[tsql](../../includes/tsql-md.md)] instruções, o driver também não oferece suporte à chamada de SQLDescribeParam para marcadores de parâmetro em instruções após a primeira instrução no lote.</span><span class="sxs-lookup"><span data-stu-id="43d66-118">When processing a batch of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, the driver also does not support calling SQLDescribeParam for parameter markers in statements after the first statement in the batch.</span></span>  
  
 <span data-ttu-id="43d66-119">Ao descrever os parâmetros dos procedimentos armazenados preparados, o SQLDescribeParam usa o procedimento armazenado do sistema [sp_sproc_columns](/sql/relational-databases/system-stored-procedures/sp-sproc-columns-transact-sql) para recuperar as características do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="43d66-119">When describing the parameters of prepared stored procedures, SQLDescribeParam uses the system stored procedure [sp_sproc_columns](/sql/relational-databases/system-stored-procedures/sp-sproc-columns-transact-sql) to retrieve parameter characteristics.</span></span> <span data-ttu-id="43d66-120">sp_sproc_columns pode relatar dados para procedimentos armazenados no banco de dados do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="43d66-120">sp_sproc_columns can report data for stored procedures within the current user database.</span></span> <span data-ttu-id="43d66-121">Preparar um nome de procedimento armazenado totalmente qualificado permite que o SQLDescribeParam seja executado em bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="43d66-121">Preparing a fully qualified stored procedure name allows SQLDescribeParam to execute across databases.</span></span> <span data-ttu-id="43d66-122">Por exemplo, o procedimento armazenado do sistema [sp_who](/sql/relational-databases/system-stored-procedures/sp-who-transact-sql) pode ser preparado e executado em qualquer banco de dados como:</span><span class="sxs-lookup"><span data-stu-id="43d66-122">For example, the system stored procedure [sp_who](/sql/relational-databases/system-stored-procedures/sp-who-transact-sql) can be prepared and executed in any database as:</span></span>  
  
```  
SQLPrepare(hstmt, "{call sp_who(?)}", SQL_NTS);  
```  
  
 <span data-ttu-id="43d66-123">A execução de SQLDescribeParam após a preparação bem-sucedida retorna um conjunto de linhas vazio quando conectado a qualquer banco de dados, mas `master` .</span><span class="sxs-lookup"><span data-stu-id="43d66-123">Executing SQLDescribeParam after successful preparation returns an empty row set when connected to any database but `master`.</span></span> <span data-ttu-id="43d66-124">A mesma chamada, preparada da seguinte maneira, faz com que o SQLDescribeParam seja bem sucedido, independentemente do banco de dados de usuário atual:</span><span class="sxs-lookup"><span data-stu-id="43d66-124">The same call, prepared as follows, causes SQLDescribeParam to succeed regardless of the current user database:</span></span>  
  
```  
SQLPrepare(hstmt, "{call master..sp_who(?)}", SQL_NTS);  
```  
  
 <span data-ttu-id="43d66-125">Para tipos de dados de valor grande, o valor retornado em *DataTypePtr* é SQL_VARCHAR, SQL_VARBINARY ou SQL_NVARCHAR.</span><span class="sxs-lookup"><span data-stu-id="43d66-125">For large value data types, the value returned in *DataTypePtr* is SQL_VARCHAR, SQL_VARBINARY, or SQL_NVARCHAR.</span></span> <span data-ttu-id="43d66-126">Para indicar que o tamanho do parâmetro de tipo de dados de valor grande é "ilimitado", o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client define *ParameterSizePtr* como 0.</span><span class="sxs-lookup"><span data-stu-id="43d66-126">To indicate that the size of the large value data type parameter is "unlimited," the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver sets *ParameterSizePtr* to 0.</span></span> <span data-ttu-id="43d66-127">Os valores de tamanho reais são retornados para os parâmetros padrão `varchar`.</span><span class="sxs-lookup"><span data-stu-id="43d66-127">Actual size values are returned for standard `varchar` parameters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43d66-128">Se o parâmetro já tiver sido associado a um tamanho máximo para os parâmetros SQL_VARCHAR, SQL_VARBINARY ou SQL_WVARCHAR, o tamanho associado do parâmetro será retornado, não "ilimitado".</span><span class="sxs-lookup"><span data-stu-id="43d66-128">If the parameter has already been bound with a maximum size for the SQL_VARCHAR, SQL_VARBINARY, or SQL_WVARCHAR parameters, the bound size of the parameter is returned, not "unlimited."</span></span>  
  
 <span data-ttu-id="43d66-129">Para associar um parâmetro de entrada de tamanho "ilimitado", dados em execução devem ser usados.</span><span class="sxs-lookup"><span data-stu-id="43d66-129">To bind an "unlimited" size input parameter, data-at-execution must be used.</span></span> <span data-ttu-id="43d66-130">Não é possível associar um parâmetro de saída de tamanho "ilimitado" (não há nenhum método para transmitir dados de um parâmetro de saída, como [SQLGetData](sqlgetdata.md) para conjuntos de resultados).</span><span class="sxs-lookup"><span data-stu-id="43d66-130">It is not possible to bind an "unlimited" size output parameter (there is no method for streaming data from an output parameter, like [SQLGetData](sqlgetdata.md) does for result sets).</span></span>  
  
 <span data-ttu-id="43d66-131">No caso de parâmetros de saída, um buffer deve ser associado e se o valor for muito extenso, o buffer será preenchido e uma mensagem SQL_SUCCESS_WITH_INFO será retornada junto com o aviso "dados de cadeia de caracteres; truncamento à direita".</span><span class="sxs-lookup"><span data-stu-id="43d66-131">For output parameters, a buffer must be bound and if the value is too large, the buffer is filled and a SQL_SUCCESS_WITH_INFO message and is returned along with the "string data; right truncation" warning.</span></span> <span data-ttu-id="43d66-132">Os dados que foram truncados são descartados em seguida.</span><span class="sxs-lookup"><span data-stu-id="43d66-132">The data that was truncated is then discarded.</span></span>  
  
## <a name="sqldescribeparam-and-table-valued-parameters"></a><span data-ttu-id="43d66-133">SQLDescribeParam e parâmetros com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="43d66-133">SQLDescribeParam and Table-Valued Parameters</span></span>  
 <span data-ttu-id="43d66-134">Um aplicativo pode recuperar informações de parâmetro com valor de tabela para uma instrução preparada com SQLDescribeParam.</span><span class="sxs-lookup"><span data-stu-id="43d66-134">An application can retrieve table-valued parameter information for a prepared statement with SQLDescribeParam.</span></span> <span data-ttu-id="43d66-135">Para obter mais informações, consulte [metadados de parâmetro com valor de tabela para instruções preparadas](../native-client-odbc-table-valued-parameters/table-valued-parameter-metadata-for-prepared-statements.md).</span><span class="sxs-lookup"><span data-stu-id="43d66-135">For more information, see [Table-Valued Parameter Metadata for Prepared Statements](../native-client-odbc-table-valued-parameters/table-valued-parameter-metadata-for-prepared-statements.md).</span></span>  
  
 <span data-ttu-id="43d66-136">Para obter mais informações sobre parâmetros com valor de tabela em geral, consulte [parâmetros com valor de tabela &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="43d66-136">For more information about table-valued parameters in general, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqldescribeparam-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="43d66-137">Suporte SQLDescribeParam para recursos avançados de data e hora</span><span class="sxs-lookup"><span data-stu-id="43d66-137">SQLDescribeParam Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="43d66-138">Os valores retornados para tipos de data/hora são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="43d66-138">The values returned for date/time types are as follows:</span></span>  
  
||<span data-ttu-id="43d66-139">*DataTypePtr*</span><span class="sxs-lookup"><span data-stu-id="43d66-139">*DataTypePtr*</span></span>|<span data-ttu-id="43d66-140">*ParameterSizePtr*</span><span class="sxs-lookup"><span data-stu-id="43d66-140">*ParameterSizePtr*</span></span>|<span data-ttu-id="43d66-141">*DecimalDigitsPtr*</span><span class="sxs-lookup"><span data-stu-id="43d66-141">*DecimalDigitsPtr*</span></span>|  
|-|-------------------|------------------------|------------------------|  
|<span data-ttu-id="43d66-142">DATETIME</span><span class="sxs-lookup"><span data-stu-id="43d66-142">datetime</span></span>|<span data-ttu-id="43d66-143">SQL_TYPE_TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="43d66-143">SQL_TYPE_TIMESTAMP</span></span>|<span data-ttu-id="43d66-144">23</span><span class="sxs-lookup"><span data-stu-id="43d66-144">23</span></span>|<span data-ttu-id="43d66-145">3</span><span class="sxs-lookup"><span data-stu-id="43d66-145">3</span></span>|  
|<span data-ttu-id="43d66-146">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="43d66-146">smalldatetime</span></span>|<span data-ttu-id="43d66-147">SQL_TYPE_TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="43d66-147">SQL_TYPE_TIMESTAMP</span></span>|<span data-ttu-id="43d66-148">16</span><span class="sxs-lookup"><span data-stu-id="43d66-148">16</span></span>|<span data-ttu-id="43d66-149">0</span><span class="sxs-lookup"><span data-stu-id="43d66-149">0</span></span>|  
|<span data-ttu-id="43d66-150">date</span><span class="sxs-lookup"><span data-stu-id="43d66-150">date</span></span>|<span data-ttu-id="43d66-151">SQL_TYPE_DATE</span><span class="sxs-lookup"><span data-stu-id="43d66-151">SQL_TYPE_DATE</span></span>|<span data-ttu-id="43d66-152">10</span><span class="sxs-lookup"><span data-stu-id="43d66-152">10</span></span>|<span data-ttu-id="43d66-153">0</span><span class="sxs-lookup"><span data-stu-id="43d66-153">0</span></span>|  
|<span data-ttu-id="43d66-154">time</span><span class="sxs-lookup"><span data-stu-id="43d66-154">time</span></span>|<span data-ttu-id="43d66-155">SQL_SS_TIME2</span><span class="sxs-lookup"><span data-stu-id="43d66-155">SQL_SS_TIME2</span></span>|<span data-ttu-id="43d66-156">8, 10..16</span><span class="sxs-lookup"><span data-stu-id="43d66-156">8, 10..16</span></span>|<span data-ttu-id="43d66-157">0..7</span><span class="sxs-lookup"><span data-stu-id="43d66-157">0..7</span></span>|  
|<span data-ttu-id="43d66-158">datetime2</span><span class="sxs-lookup"><span data-stu-id="43d66-158">datetime2</span></span>|<span data-ttu-id="43d66-159">SQL_TYPE_TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="43d66-159">SQL_TYPE_TIMESTAMP</span></span>|<span data-ttu-id="43d66-160">19, 21..27</span><span class="sxs-lookup"><span data-stu-id="43d66-160">19, 21..27</span></span>|<span data-ttu-id="43d66-161">0..7</span><span class="sxs-lookup"><span data-stu-id="43d66-161">0..7</span></span>|  
|<span data-ttu-id="43d66-162">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="43d66-162">datetimeoffset</span></span>|<span data-ttu-id="43d66-163">SQL_SS_TIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="43d66-163">SQL_SS_TIMESTAMPOFFSET</span></span>|<span data-ttu-id="43d66-164">26, 28..34</span><span class="sxs-lookup"><span data-stu-id="43d66-164">26, 28..34</span></span>|<span data-ttu-id="43d66-165">0..7</span><span class="sxs-lookup"><span data-stu-id="43d66-165">0..7</span></span>|  
  
 <span data-ttu-id="43d66-166">Para obter mais informações, consulte [melhorias de data e hora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="43d66-166">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqldescribeparam-support-for-large-clr-udts"></a><span data-ttu-id="43d66-167">Suporte SQLDescribeParam para UDTs CLR grandes</span><span class="sxs-lookup"><span data-stu-id="43d66-167">SQLDescribeParam Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="43d66-168">`SQLDescribeParam` dá suporte a UDTs grandes do CLR.</span><span class="sxs-lookup"><span data-stu-id="43d66-168">`SQLDescribeParam` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="43d66-169">Para obter mais informações, consulte [tipos CLR grandes definidos pelo usuário &#40;&#41;ODBC ](../../relational-databases/native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="43d66-169">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../../relational-databases/native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43d66-170">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="43d66-170">See Also</span></span>  
 <span data-ttu-id="43d66-171">[Função SQLDescribeParam](https://go.microsoft.com/fwlink/?LinkId=59339) </span><span class="sxs-lookup"><span data-stu-id="43d66-171">[SQLDescribeParam Function](https://go.microsoft.com/fwlink/?LinkId=59339) </span></span>  
 [<span data-ttu-id="43d66-172">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="43d66-172">ODBC API Implementation Details</span></span>](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  