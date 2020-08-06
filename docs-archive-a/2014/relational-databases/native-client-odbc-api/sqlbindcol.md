---
title: SQLBindCol | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLBindCol function
ms.assetid: fbd7ba20-d917-4ca9-b018-018ac6af9f98
author: rothja
ms.author: jroth
ms.openlocfilehash: 72d0ca1b0fbad144117e409019d8d2247bbf918f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685665"
---
# <a name="sqlbindcol"></a><span data-ttu-id="8e72a-102">SQLBindCol</span><span class="sxs-lookup"><span data-stu-id="8e72a-102">SQLBindCol</span></span>
  <span data-ttu-id="8e72a-103">Como regra geral, considere as implicações de usar **SQLBindCol** para causar conversão de dados.</span><span class="sxs-lookup"><span data-stu-id="8e72a-103">As a general rule, consider the implications of using **SQLBindCol** to cause data conversion.</span></span> <span data-ttu-id="8e72a-104">As conversões de associações são processos do cliente, portanto, por exemplo, recuperar um valor de ponto flutuante associado a uma coluna de caracteres faz com que o driver execute a conversão flutuante para caractere localmente quando uma linha é buscada.</span><span class="sxs-lookup"><span data-stu-id="8e72a-104">Binding conversions are client processes, so, for example, retrieving a floating-point value bound to a character column causes the driver to perform the float-to-character conversion locally when a row is fetched.</span></span> <span data-ttu-id="8e72a-105">A função CONVERT do [!INCLUDE[tsql](../../includes/tsql-md.md)] pode ser usada para inserir o custo da conversão de dados no servidor.</span><span class="sxs-lookup"><span data-stu-id="8e72a-105">The [!INCLUDE[tsql](../../includes/tsql-md.md)] CONVERT function can be used to place the cost of data conversion on the server.</span></span>  
  
 <span data-ttu-id="8e72a-106">Uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode retornar vários conjuntos de linhas de resultado em uma única execução de instrução.</span><span class="sxs-lookup"><span data-stu-id="8e72a-106">An instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can return multiple sets of result rows on a single statement execution.</span></span> <span data-ttu-id="8e72a-107">Cada conjunto de resultados deve ser associado separadamente.</span><span class="sxs-lookup"><span data-stu-id="8e72a-107">Each result set must be bound separately.</span></span> <span data-ttu-id="8e72a-108">Para obter mais informações sobre como associar vários conjuntos de resultados, consulte [SQLMoreResults](sqlmoreresults.md).</span><span class="sxs-lookup"><span data-stu-id="8e72a-108">For more information about binding for multiple result sets, see [SQLMoreResults](sqlmoreresults.md).</span></span>  
  
 <span data-ttu-id="8e72a-109">O desenvolvedor pode associar colunas a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de dados C específicos usando o *TargetType* valor TargetType `SQL_C_BINARY` .</span><span class="sxs-lookup"><span data-stu-id="8e72a-109">The developer can bind columns to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific C data types using the *TargetType* value `SQL_C_BINARY`.</span></span> <span data-ttu-id="8e72a-110">Colunas associadas a tipos específicos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]não são portáteis.</span><span class="sxs-lookup"><span data-stu-id="8e72a-110">Columns bound to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific types are not portable.</span></span> <span data-ttu-id="8e72a-111">Os tipos de dados C de ODBC definidos e específicos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]correspondem às definições de tipo para DB-Library e os desenvolvedores de DB-Library portando aplicativos podem desejar tirar proveito desse recurso.</span><span class="sxs-lookup"><span data-stu-id="8e72a-111">The defined [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific ODBC C data types match the type definitions for DB-Library, and DB-Library developers porting applications may want to take advantage of this feature.</span></span>  
  
 <span data-ttu-id="8e72a-112">Informar o truncamento de dados é um processo caro para o driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="8e72a-112">Reporting data truncation is an expensive process for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="8e72a-113">Você pode evitar o truncamento assegurando que todos os buffers de dados associados tenham largura suficiente para retornar dados.</span><span class="sxs-lookup"><span data-stu-id="8e72a-113">You can avoid truncation by ensuring that all bound data buffers are wide enough to return data.</span></span> <span data-ttu-id="8e72a-114">Para dados de caracteres, a largura deve incluir espaço para um terminador da cadeia de caracteres quando o comportamento padrão do driver para a terminação da cadeia de caracteres for usado.</span><span class="sxs-lookup"><span data-stu-id="8e72a-114">For character data, the width should include space for a string terminator when the default driver behavior for string termination is used.</span></span> <span data-ttu-id="8e72a-115">Por exemplo, a associação de uma coluna [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **char(5)** a uma matriz de cinco caracteres resulta em truncagem para todos os valores buscados.</span><span class="sxs-lookup"><span data-stu-id="8e72a-115">For example, binding a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **char(5)** column to an array of five characters results in truncation for every value fetched.</span></span> <span data-ttu-id="8e72a-116">A associação da mesma coluna a uma matriz de seis caracteres evita a truncagem, fornecendo um elemento de caractere no qual armazenar o terminador nulo.</span><span class="sxs-lookup"><span data-stu-id="8e72a-116">Binding the same column to an array of six characters avoids the truncation by providing a character element in which to store the null terminator.</span></span> <span data-ttu-id="8e72a-117">[SQLGetData](sqlgetdata.md) pode ser usado para recuperar com eficiência dados de caracteres longos e dados binários sem truncagem.</span><span class="sxs-lookup"><span data-stu-id="8e72a-117">[SQLGetData](sqlgetdata.md) can be used to efficiently retrieve long character and binary data without truncation.</span></span>  
  
 <span data-ttu-id="8e72a-118">Para tipos de dados de valor grande, se o buffer fornecido pelo usuário não for grande o suficiente para conter o valor inteiro da coluna, `SQL_SUCCESS_WITH_INFO` será retornado e os "dados de cadeia de caracteres; truncamento à direita "o aviso é emitido.</span><span class="sxs-lookup"><span data-stu-id="8e72a-118">For large value data types, if the user supplied buffer isn't large enough to hold the entire value of the column, `SQL_SUCCESS_WITH_INFO` is returned and the "string data; right truncation" warning is issued.</span></span> <span data-ttu-id="8e72a-119">O argumento `StrLen_or_IndPtr` conterá o número de chars/bytes armazenados no buffer.</span><span class="sxs-lookup"><span data-stu-id="8e72a-119">The `StrLen_or_IndPtr` argument will contain the number of chars/bytes stored in the buffer.</span></span>  
  
## <a name="sqlbindcol-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="8e72a-120">Suporte de SQLBindCol a recursos aprimorados de data e hora</span><span class="sxs-lookup"><span data-stu-id="8e72a-120">SQLBindCol Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="8e72a-121">Os valores de coluna de resultado de tipos de data/hora são convertidos conforme descrito em [conversões de SQL para C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md). Observe que para recuperar as colunas time e DateTimeOffset como suas estruturas correspondentes ( `SQL_SS_TIME2_STRUCT` e **SQL_SS_TIMESTAMPOFFSET_STRUCT**), *TargetType* deve ser especificado como `SQL_C_DEFAULT` ou `SQL_C_BINARY` .</span><span class="sxs-lookup"><span data-stu-id="8e72a-121">Result column values of date/time types are converted as described in [Conversions from SQL to C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md). Note that to retrieve time and datetimeoffset columns as their corresponding structures (`SQL_SS_TIME2_STRUCT` and **SQL_SS_TIMESTAMPOFFSET_STRUCT**), *TargetType* must be specified as `SQL_C_DEFAULT` or `SQL_C_BINARY`.</span></span>  
  
 <span data-ttu-id="8e72a-122">Para obter mais informações, consulte [melhorias de data e hora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="8e72a-122">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlbindcol-support-for-large-clr-udts"></a><span data-ttu-id="8e72a-123">Suporte de SQLBindCol para CLR UDTs grandes</span><span class="sxs-lookup"><span data-stu-id="8e72a-123">SQLBindCol Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="8e72a-124">**SQLBindCol** dá suporte a tipos de dados CLR definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="8e72a-124">**SQLBindCol** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="8e72a-125">Para obter mais informações, consulte [tipos CLR grandes definidos pelo usuário &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="8e72a-125">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e72a-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e72a-126">See Also</span></span>  
 <span data-ttu-id="8e72a-127">[Função SQLBindCol](https://go.microsoft.com/fwlink/?LinkId=59327) </span><span class="sxs-lookup"><span data-stu-id="8e72a-127">[SQLBindCol Function](https://go.microsoft.com/fwlink/?LinkId=59327) </span></span>  
 [<span data-ttu-id="8e72a-128">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="8e72a-128">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  