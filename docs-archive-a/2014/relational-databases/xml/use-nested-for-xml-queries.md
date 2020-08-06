---
title: Usar consultas FOR XML aninhadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, nested FOR XML queries
- queries [XML in SQL Server], nested FOR XML
- nested FOR XML queries
ms.assetid: 7604161a-a958-446d-b102-7dee432979d0
author: rothja
ms.author: jroth
ms.openlocfilehash: 60c4198697f8d19c9b2e5bc1b415e0787861d40a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684106"
---
# <a name="use-nested-for-xml-queries"></a><span data-ttu-id="d85a6-102">Usar consultas FOR XML aninhadas</span><span class="sxs-lookup"><span data-stu-id="d85a6-102">Use Nested FOR XML Queries</span></span>
  <span data-ttu-id="d85a6-103">O `xml` tipo de dados e a [diretiva Type em consultas for XML](type-directive-in-for-xml-queries.md) habilitam o XML RETORNADO pelas consultas for XML a serem processadas no servidor, bem como no cliente.</span><span class="sxs-lookup"><span data-stu-id="d85a6-103">The `xml` data type and the [TYPE directive in FOR XML queries](type-directive-in-for-xml-queries.md) enable the XML returned by the FOR XML queries to be processed on the server as well as on the client.</span></span>  
  
## <a name="processing-with-xml-type-variables"></a><span data-ttu-id="d85a6-104">Processando com variáveis de tipo xml</span><span class="sxs-lookup"><span data-stu-id="d85a6-104">Processing with xml Type Variables</span></span>  
 <span data-ttu-id="d85a6-105">É possível atribuir o resultado da consulta FOR XML a uma variável de tipo `xml`, ou usar a XQuery para consultar o resultado e atribuir esse resultado a uma variável de tipo `xml` para processamento adicional.</span><span class="sxs-lookup"><span data-stu-id="d85a6-105">You can assign the FOR XML query result to an `xml` type variable, or use XQuery to query the result, and assign that result to an `xml` type variable for more processing.</span></span>  
  
```  
DECLARE @x xml  
SET @x=(SELECT ProductModelID, Name  
        FROM Production.ProductModel  
        WHERE ProductModelID=122 or ProductModelID=119  
        FOR XML RAW, TYPE)  
SELECT @x  
-- Result  
--<row ProductModelID="122" Name="All-Purpose Bike Stand" />  
--<row ProductModelID="119" Name="Bike Wash" />  
```  
  
 <span data-ttu-id="d85a6-106">Além disso, é possível processar o XML retornado na variável, `@x`, usando um dos métodos de tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="d85a6-106">You can additionally process the XML returned in the variable, `@x`, by using one of the `xml` data type methods.</span></span> <span data-ttu-id="d85a6-107">Por exemplo, é possível recuperar o valor do atributo `ProductModelID` usando o [método value()](/sql/t-sql/xml/value-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="d85a6-107">For example, you can retrieve the `ProductModelID` attribute value by using the [value() method](/sql/t-sql/xml/value-method-xml-data-type).</span></span>  
  
```  
DECLARE @i int;  
SET @i = (SELECT @x.value('/row[1]/@ProductModelID[1]', 'int'));  
SELECT @i;  
```  
  
 <span data-ttu-id="d85a6-108">No exemplo a seguir, o resultado da consulta `FOR XML` é retornado como um tipo `xml`, porque a diretiva `TYPE` é especificada na cláusula `FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="d85a6-108">In the following example, the `FOR XML` query result is returned as an `xml` type, because the `TYPE` directive is specified in the `FOR XML` clause.</span></span>  
  
```  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=119 or ProductModelID=122  
FOR XML RAW, TYPE,ROOT('myRoot');  
  
```  
  
 <span data-ttu-id="d85a6-109">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="d85a6-109">This is the result:</span></span>  
  
```  
<myRoot>  
  <row ProductModelID="122" Name="All-Purpose Bike Stand" />  
  <row ProductModelID="119" Name="Bike Wash" />  
</myRoot>  
```  
  
 <span data-ttu-id="d85a6-110">Como o resultado é de tipo `xml`, é possível especificar um dos métodos de tipo de dados `xml` diretamente em relação a esse XML, conforme mostrado na consulta a seguir.</span><span class="sxs-lookup"><span data-stu-id="d85a6-110">Because the result is of `xml` type, you can specify one of the `xml` data type methods directly against this XML, as shown in the following query.</span></span> <span data-ttu-id="d85a6-111">Na consulta, o [método query() (tipo de dados xml)](/sql/t-sql/xml/query-method-xml-data-type) é usado para recuperar o primeiro elemento filho <`row`> do elemento <`myRoot`>.</span><span class="sxs-lookup"><span data-stu-id="d85a6-111">In the query, the [query() method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) is used to retrieve the first <`row`> element child of the <`myRoot`> element.</span></span>  
  
```  
SELECT  (SELECT ProductModelID, Name  
         FROM Production.ProductModel  
         WHERE ProductModelID=119 or ProductModelID=122  
         FOR XML RAW, TYPE,ROOT('myRoot')).query('/myRoot[1]/row[1]');  
  
```  
  
 <span data-ttu-id="d85a6-112">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="d85a6-112">This is the result:</span></span>  
  
```  
<row ProductModelID="122" Name="All-Purpose Bike Stand" />  
```  
  
## <a name="returning-inner-for-xml-query-results-to-outer-queries-as-xml-type-instances"></a><span data-ttu-id="d85a6-113">Retornando resultados de consulta FOR XML interna para consultas externas como instâncias de tipo xml</span><span class="sxs-lookup"><span data-stu-id="d85a6-113">Returning Inner FOR XML Query Results to Outer Queries as xml Type Instances</span></span>  
 <span data-ttu-id="d85a6-114">É possível escrever consultas `FOR XML` aninhadas em que o resultado da consulta interna é retornado como um tipo `xml` para a consulta externa.</span><span class="sxs-lookup"><span data-stu-id="d85a6-114">You can write nested `FOR XML` queries where the result of the inner query is returned as an `xml` type to the outer query.</span></span> <span data-ttu-id="d85a6-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d85a6-115">For example:</span></span>  
  
```  
SELECT Col1,   
       Col2,   
       ( SELECT Col3, Col4   
        FROM  T2  
        WHERE T2.Col = T1.Col  
        ...  
        FOR XML AUTO, TYPE )  
FROM T1  
WHERE ...  
FOR XML AUTO, TYPE;  
```  
  
 <span data-ttu-id="d85a6-116">Observe o seguinte na consulta anterior:</span><span class="sxs-lookup"><span data-stu-id="d85a6-116">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="d85a6-117">O XML gerado pela consulta `FOR XML` interna é adicionado ao XML gerado pela `FOR XML`externa.</span><span class="sxs-lookup"><span data-stu-id="d85a6-117">The XML generated by the inner `FOR XML` query is added to the XML generated by the outer `FOR XML`.</span></span>  
  
-   <span data-ttu-id="d85a6-118">A consulta interna especifica a diretiva `TYPE` .</span><span class="sxs-lookup"><span data-stu-id="d85a6-118">The inner query specifies the `TYPE` directive.</span></span> <span data-ttu-id="d85a6-119">Portanto, os dados XML retornados pela consulta interna são de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="d85a6-119">Therefore, the XML data returned by the inner query is of `xml` type.</span></span> <span data-ttu-id="d85a6-120">Se a diretiva TYPE não for especificada, o resultado da consulta `FOR XML` interna será retornado como `nvarchar(max)` e os dados XML terão a entidade definida.</span><span class="sxs-lookup"><span data-stu-id="d85a6-120">If the TYPE directive is not specified, the result of the inner `FOR XML` query is returned as `nvarchar(max)` and the XML data is entitized.</span></span>  
  
## <a name="controlling-the-shape-of-resulting-xml-data"></a><span data-ttu-id="d85a6-121">Controlando a forma dos dados XML resultantes</span><span class="sxs-lookup"><span data-stu-id="d85a6-121">Controlling the Shape of Resulting XML Data</span></span>  
 <span data-ttu-id="d85a6-122">Consultas FOR XML aninhadas fornecem mais controle para definir a forma dos dados XML resultantes.</span><span class="sxs-lookup"><span data-stu-id="d85a6-122">Nested FOR XML queries give you more control in defining the shape of the resulting XML data.</span></span> <span data-ttu-id="d85a6-123">É possível usar consultas aninhadas FOR XML para construir XML parcialmente centrado em atributo e parcialmente centrado em elemento.</span><span class="sxs-lookup"><span data-stu-id="d85a6-123">You can use nested FOR XML queries to construct XML that is partly attribute-centric and partly element-centric.</span></span>  
  
 <span data-ttu-id="d85a6-124">Para obter mais informações sobre como especificar um XML centrado em atributo e em elemento com consultas FOR XML aninhadas, veja [Consulta FOR XML comparada com consulta FOR XML aninhada](../xml/for-xml-query-compared-to-nested-for-xml-query.md) e [Formar XML com consultas FOR XML aninhadas](../xml/shape-xml-with-nested-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="d85a6-124">For more information about specifying both attribute-centric and element-centric XML with nested FOR XML queries, see [FOR XML Query Compared to Nested FOR XML Query](../xml/for-xml-query-compared-to-nested-for-xml-query.md) and [Shape XML with Nested FOR XML Queries](../xml/shape-xml-with-nested-for-xml-queries.md).</span></span>  
  
 <span data-ttu-id="d85a6-125">É possível gerar hierarquias XML que incluem irmãos especificando consultas aninhadas FOR XML em modo AUTO.</span><span class="sxs-lookup"><span data-stu-id="d85a6-125">You can generate XML hierarchies that include siblings by specifying nested AUTO mode FOR XML queries.</span></span> <span data-ttu-id="d85a6-126">Para obter mais informações, veja [Gerar irmãos com uma consulta aninhada em modo AUTO](../xml/generate-siblings-with-a-nested-auto-mode-query.md).</span><span class="sxs-lookup"><span data-stu-id="d85a6-126">For more information, see [Generate Siblings with a Nested AUTO Mode Query](../xml/generate-siblings-with-a-nested-auto-mode-query.md).</span></span>  
  
 <span data-ttu-id="d85a6-127">Independentemente do modo usado, consultas FOR XML aninhadas fornecem mais controle para descrever a forma do XML resultante.</span><span class="sxs-lookup"><span data-stu-id="d85a6-127">Regardless of which mode you use, nested FOR XML queries provide more control in describing the shape of the resulting XML.</span></span> <span data-ttu-id="d85a6-128">Elas podem ser usadas no lugar de consultas em modo EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="d85a6-128">They can be used in the place of EXPLICIT mode queries.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d85a6-129">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d85a6-129">Examples</span></span>  
 <span data-ttu-id="d85a6-130">Os tópicos a seguir fornecem exemplos de consultas FOR XML aninhadas.</span><span class="sxs-lookup"><span data-stu-id="d85a6-130">The following topics provide examples of nested FOR XML queries.</span></span>  
  
 [<span data-ttu-id="d85a6-131">Consulta XML FOR comparada com consulta XML FOR aninhada</span><span class="sxs-lookup"><span data-stu-id="d85a6-131">FOR XML Query Compared to Nested FOR XML Query</span></span>](../xml/for-xml-query-compared-to-nested-for-xml-query.md)  
 <span data-ttu-id="d85a6-132">Compara uma consulta FOR XML de nível único com uma consulta FOR XML aninhada.</span><span class="sxs-lookup"><span data-stu-id="d85a6-132">Compares a single-level FOR XML query to a nested FOR XML query.</span></span> <span data-ttu-id="d85a6-133">Este exemplo inclui uma demonstração de como especificar XML centrado em atributo e centrado em elemento como o resultado da consulta.</span><span class="sxs-lookup"><span data-stu-id="d85a6-133">This example includes a demonstration of how to specify both attribute-centric and element-centric XML as the result of the query.</span></span>  
  
 [<span data-ttu-id="d85a6-134">Gerar irmãos com uma consulta aninhada em modo AUTO</span><span class="sxs-lookup"><span data-stu-id="d85a6-134">Generate Siblings with a Nested AUTO Mode Query</span></span>](../xml/generate-siblings-with-a-nested-auto-mode-query.md)  
 <span data-ttu-id="d85a6-135">Mostra como gerar irmãos usando uma consulta aninhada em modo AUTO</span><span class="sxs-lookup"><span data-stu-id="d85a6-135">Shows how to generate siblings by using a nested AUTO mode query</span></span>  
  
 [<span data-ttu-id="d85a6-136">Usar consultas FOR XML aninhadas no ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d85a6-136">Use Nested FOR XML Queries in ASP.NET</span></span>](use-nested-for-xml-queries-in-asp-net.md)  
 <span data-ttu-id="d85a6-137">Demonstra como um aplicativo ASPX pode usar FOR XML para retornar XML do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d85a6-137">Demonstrates how an ASPX application can use FOR XML to return XML from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="d85a6-138">Formar XML com consultas FOR XML aninhadas</span><span class="sxs-lookup"><span data-stu-id="d85a6-138">Shape XML with Nested FOR XML Queries</span></span>](../xml/shape-xml-with-nested-for-xml-queries.md)  
 <span data-ttu-id="d85a6-139">Mostra como usar consultas FOR XML aninhadas para controlar a estrutura de um documento XML criado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d85a6-139">Shows how to use nested FOR XML queries to control the structure of an XML document created by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
  
