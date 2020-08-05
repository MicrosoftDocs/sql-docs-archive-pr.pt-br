---
title: bcp_gettypename | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_gettypename
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_gettypename function
ms.assetid: 65f036d1-f60e-4b8a-97b3-76fccf0dfed4
author: rothja
ms.author: jroth
ms.openlocfilehash: b2d92498b9d863fa2cb700ec4d88868c0984c4d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572063"
---
# <a name="bcp_gettypename"></a><span data-ttu-id="cf460-102">bcp_gettypename</span><span class="sxs-lookup"><span data-stu-id="cf460-102">bcp_gettypename</span></span>
  <span data-ttu-id="cf460-103">Retorna o nome do tipo SQL para um token do tipo BCP especificado.</span><span class="sxs-lookup"><span data-stu-id="cf460-103">Returns the SQL type name for a specified BCP type token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf460-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cf460-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_gettypename (  
INT   
token  
,  
DBBOOL   
fIsMaxType  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="cf460-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cf460-105">Arguments</span></span>  
 <span data-ttu-id="cf460-106">*token*</span><span class="sxs-lookup"><span data-stu-id="cf460-106">*token*</span></span>  
 <span data-ttu-id="cf460-107">Um valor que indica um token do tipo BCP.</span><span class="sxs-lookup"><span data-stu-id="cf460-107">A value indicating a BCP type token.</span></span>  
  
 <span data-ttu-id="cf460-108">*campo*</span><span class="sxs-lookup"><span data-stu-id="cf460-108">*field*</span></span>  
 <span data-ttu-id="cf460-109">Indica se o token solicitado é do tipo max.</span><span class="sxs-lookup"><span data-stu-id="cf460-109">Indicates if token requested is a max type.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="cf460-110">Retornos</span><span class="sxs-lookup"><span data-stu-id="cf460-110">Returns</span></span>  
 <span data-ttu-id="cf460-111">Uma cadeia de caracteres que contém o nome do tipo SQL que corresponde ao tipo BCP.</span><span class="sxs-lookup"><span data-stu-id="cf460-111">A string containing the SQL type name corresponding to the BCP type.</span></span> <span data-ttu-id="cf460-112">Se um for especificado um tipo BCP inválido, uma cadeia de caracteres vazia será retornada.</span><span class="sxs-lookup"><span data-stu-id="cf460-112">If an invalid BCP type is specified, an empty string is returned..</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf460-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="cf460-113">Remarks</span></span>  
 <span data-ttu-id="cf460-114">Os tokens do tipo BCP são definidos arquivo do cabeçalho sqlncli.h e na biblioteca sqlncli11.lib.</span><span class="sxs-lookup"><span data-stu-id="cf460-114">The BCP type tokens are defined in the sqlncli.h header file and the sqlncli11.lib library.</span></span>  
  
 <span data-ttu-id="cf460-115">A tabela a seguir especifica os possíveis tipos BCP, se eles são ou não tipos max e a saída esperada.</span><span class="sxs-lookup"><span data-stu-id="cf460-115">The table below specifies the possible BCP types, whether or not they are max types, and the expected output.</span></span>  
  
|<span data-ttu-id="cf460-116">Nome do tipo BCP</span><span class="sxs-lookup"><span data-stu-id="cf460-116">BCP type name</span></span>|<span data-ttu-id="cf460-117">MaxType</span><span class="sxs-lookup"><span data-stu-id="cf460-117">MaxType</span></span>|<span data-ttu-id="cf460-118">Saída</span><span class="sxs-lookup"><span data-stu-id="cf460-118">Output</span></span>|  
|-------------------|-------------|------------|  
|`SQLDECIMAL`|<span data-ttu-id="cf460-119">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-119">Either</span></span>|<span data-ttu-id="cf460-120">**decimal**</span><span class="sxs-lookup"><span data-stu-id="cf460-120">**decimal**</span></span>|  
|`SQLNUMERIC`|<span data-ttu-id="cf460-121">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-121">Either</span></span>|<span data-ttu-id="cf460-122">**numeric**</span><span class="sxs-lookup"><span data-stu-id="cf460-122">**numeric**</span></span>|  
|`SQLINT1`|<span data-ttu-id="cf460-123">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-123">Either</span></span>|<span data-ttu-id="cf460-124">**tinyint**</span><span class="sxs-lookup"><span data-stu-id="cf460-124">**tinyint**</span></span>|  
|`SQLINT2`|<span data-ttu-id="cf460-125">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-125">Either</span></span>|<span data-ttu-id="cf460-126">**smallint**</span><span class="sxs-lookup"><span data-stu-id="cf460-126">**smallint**</span></span>|  
|`SQLINT4`|<span data-ttu-id="cf460-127">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-127">Either</span></span>|<span data-ttu-id="cf460-128">**int**</span><span class="sxs-lookup"><span data-stu-id="cf460-128">**int**</span></span>|  
|`SQLMONEY`|<span data-ttu-id="cf460-129">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-129">Either</span></span>|<span data-ttu-id="cf460-130">**money**</span><span class="sxs-lookup"><span data-stu-id="cf460-130">**money**</span></span>|  
|`SQLFLT8`|<span data-ttu-id="cf460-131">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-131">Either</span></span>|<span data-ttu-id="cf460-132">**float**</span><span class="sxs-lookup"><span data-stu-id="cf460-132">**float**</span></span>|  
|`SQLDATETIME`|<span data-ttu-id="cf460-133">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-133">Either</span></span>|<span data-ttu-id="cf460-134">**datetime**</span><span class="sxs-lookup"><span data-stu-id="cf460-134">**datetime**</span></span>|  
|`SQLBITN`|<span data-ttu-id="cf460-135">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-135">Either</span></span>|<span data-ttu-id="cf460-136">**bit-null**</span><span class="sxs-lookup"><span data-stu-id="cf460-136">**bit-null**</span></span>|  
|`SQLBIT`|<span data-ttu-id="cf460-137">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-137">Either</span></span>|<span data-ttu-id="cf460-138">**bit**</span><span class="sxs-lookup"><span data-stu-id="cf460-138">**bit**</span></span>|  
|`SQLBIGCHAR`|<span data-ttu-id="cf460-139">Não</span><span class="sxs-lookup"><span data-stu-id="cf460-139">No</span></span>|<span data-ttu-id="cf460-140">**char**</span><span class="sxs-lookup"><span data-stu-id="cf460-140">**char**</span></span>|  
|`SQLCHARACTER`|<span data-ttu-id="cf460-141">Não</span><span class="sxs-lookup"><span data-stu-id="cf460-141">No</span></span>|<span data-ttu-id="cf460-142">**char**</span><span class="sxs-lookup"><span data-stu-id="cf460-142">**char**</span></span>|  
|`SQLBIGVARCHAR`|<span data-ttu-id="cf460-143">Não</span><span class="sxs-lookup"><span data-stu-id="cf460-143">No</span></span>|<span data-ttu-id="cf460-144">**varchar**</span><span class="sxs-lookup"><span data-stu-id="cf460-144">**varchar**</span></span>|  
|`SQLVARCHAR`|<span data-ttu-id="cf460-145">Não</span><span class="sxs-lookup"><span data-stu-id="cf460-145">No</span></span>|<span data-ttu-id="cf460-146">**varchar**</span><span class="sxs-lookup"><span data-stu-id="cf460-146">**varchar**</span></span>|  
|`SQLTEXT`|<span data-ttu-id="cf460-147">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-147">Either</span></span>|<span data-ttu-id="cf460-148">**text**</span><span class="sxs-lookup"><span data-stu-id="cf460-148">**text**</span></span>|  
|`SQLBIGBINARY`|<span data-ttu-id="cf460-149">Não</span><span class="sxs-lookup"><span data-stu-id="cf460-149">No</span></span>|<span data-ttu-id="cf460-150">**binary**</span><span class="sxs-lookup"><span data-stu-id="cf460-150">**binary**</span></span>|  
|`SQLBINARY`|<span data-ttu-id="cf460-151">Não</span><span class="sxs-lookup"><span data-stu-id="cf460-151">No</span></span>|<span data-ttu-id="cf460-152">**Binary**</span><span class="sxs-lookup"><span data-stu-id="cf460-152">**Binary**</span></span>|  
|`SQLBIGVARBINARY`|<span data-ttu-id="cf460-153">Não</span><span class="sxs-lookup"><span data-stu-id="cf460-153">No</span></span>|<span data-ttu-id="cf460-154">**Varbinary**</span><span class="sxs-lookup"><span data-stu-id="cf460-154">**Varbinary**</span></span>|  
|`SQLVARBINARY`|<span data-ttu-id="cf460-155">Não</span><span class="sxs-lookup"><span data-stu-id="cf460-155">No</span></span>|<span data-ttu-id="cf460-156">**Varbinary**</span><span class="sxs-lookup"><span data-stu-id="cf460-156">**Varbinary**</span></span>|  
|`SQLIMAGE`|<span data-ttu-id="cf460-157">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-157">Either</span></span>|<span data-ttu-id="cf460-158">**Imagem**</span><span class="sxs-lookup"><span data-stu-id="cf460-158">**Image**</span></span>|  
|`SQLINTN`|<span data-ttu-id="cf460-159">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-159">Either</span></span>|<span data-ttu-id="cf460-160">**int-null**</span><span class="sxs-lookup"><span data-stu-id="cf460-160">**int-null**</span></span>|  
|`SQLDATETIMN`|<span data-ttu-id="cf460-161">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-161">Either</span></span>|<span data-ttu-id="cf460-162">**datetime-null**</span><span class="sxs-lookup"><span data-stu-id="cf460-162">**datetime-null**</span></span>|  
|`SQLMONEYN`|<span data-ttu-id="cf460-163">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-163">Either</span></span>|<span data-ttu-id="cf460-164">**money-null**</span><span class="sxs-lookup"><span data-stu-id="cf460-164">**money-null**</span></span>|  
|`SQLFLTN`|<span data-ttu-id="cf460-165">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-165">Either</span></span>|<span data-ttu-id="cf460-166">**float-null**</span><span class="sxs-lookup"><span data-stu-id="cf460-166">**float-null**</span></span>|  
|`SQLAOPSUM`|<span data-ttu-id="cf460-167">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-167">Either</span></span>|<span data-ttu-id="cf460-168">**Quantia**</span><span class="sxs-lookup"><span data-stu-id="cf460-168">**Sum**</span></span>|  
|`SQLAOPAVG`|<span data-ttu-id="cf460-169">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-169">Either</span></span>|<span data-ttu-id="cf460-170">**Média**</span><span class="sxs-lookup"><span data-stu-id="cf460-170">**Avg**</span></span>|  
|`SQLAOPCNT`|<span data-ttu-id="cf460-171">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-171">Either</span></span>|<span data-ttu-id="cf460-172">**Count**</span><span class="sxs-lookup"><span data-stu-id="cf460-172">**Count**</span></span>|  
|`SQLAOPMIN`|<span data-ttu-id="cf460-173">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-173">Either</span></span>|<span data-ttu-id="cf460-174">**Min**</span><span class="sxs-lookup"><span data-stu-id="cf460-174">**Min**</span></span>|  
|`SQLAOPMAX`|<span data-ttu-id="cf460-175">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-175">Either</span></span>|<span data-ttu-id="cf460-176">**Maximizar**</span><span class="sxs-lookup"><span data-stu-id="cf460-176">**Max**</span></span>|  
|`SQLDATETIM4`|<span data-ttu-id="cf460-177">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-177">Either</span></span>|<span data-ttu-id="cf460-178">**smalldatetime**</span><span class="sxs-lookup"><span data-stu-id="cf460-178">**smalldatetime**</span></span>|  
|`SQLMONEY4`|<span data-ttu-id="cf460-179">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-179">Either</span></span>|<span data-ttu-id="cf460-180">**Smallmoney**</span><span class="sxs-lookup"><span data-stu-id="cf460-180">**Smallmoney**</span></span>|  
|`SQLFLT4`|<span data-ttu-id="cf460-181">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-181">Either</span></span>|<span data-ttu-id="cf460-182">**Foto**</span><span class="sxs-lookup"><span data-stu-id="cf460-182">**Real**</span></span>|  
|`SQLUNIQUEID`|<span data-ttu-id="cf460-183">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-183">Either</span></span>|<span data-ttu-id="cf460-184">**uniqueidentifier**</span><span class="sxs-lookup"><span data-stu-id="cf460-184">**uniqueidentifier**</span></span>|  
|`SQLNCHAR`|<span data-ttu-id="cf460-185">Não</span><span class="sxs-lookup"><span data-stu-id="cf460-185">No</span></span>|<span data-ttu-id="cf460-186">**Nchar**</span><span class="sxs-lookup"><span data-stu-id="cf460-186">**Nchar**</span></span>|  
|`SQLNVARCHAR`|<span data-ttu-id="cf460-187">Não</span><span class="sxs-lookup"><span data-stu-id="cf460-187">No</span></span>|<span data-ttu-id="cf460-188">**Nvarchar**</span><span class="sxs-lookup"><span data-stu-id="cf460-188">**Nvarchar**</span></span>|  
|`SQLNTEXT`|<span data-ttu-id="cf460-189">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-189">Either</span></span>|<span data-ttu-id="cf460-190">**Ntext**</span><span class="sxs-lookup"><span data-stu-id="cf460-190">**Ntext**</span></span>|  
|`SQLVARIANT`|<span data-ttu-id="cf460-191">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-191">Either</span></span>|<span data-ttu-id="cf460-192">**sql_variant**</span><span class="sxs-lookup"><span data-stu-id="cf460-192">**sql_variant**</span></span>|  
|`SQLINT8`|<span data-ttu-id="cf460-193">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-193">Either</span></span>|<span data-ttu-id="cf460-194">**Bigint**</span><span class="sxs-lookup"><span data-stu-id="cf460-194">**Bigint**</span></span>|  
|`SQLCHARACTER`|<span data-ttu-id="cf460-195">Sim</span><span class="sxs-lookup"><span data-stu-id="cf460-195">Yes</span></span>|<span data-ttu-id="cf460-196">**varchar(max)**</span><span class="sxs-lookup"><span data-stu-id="cf460-196">**varchar(max)**</span></span>|  
|`SQLBIGCHAR`|<span data-ttu-id="cf460-197">Sim</span><span class="sxs-lookup"><span data-stu-id="cf460-197">Yes</span></span>|<span data-ttu-id="cf460-198">**varchar(max)**</span><span class="sxs-lookup"><span data-stu-id="cf460-198">**varchar(max)**</span></span>|  
|`SQLBIGVARCHAR`|<span data-ttu-id="cf460-199">Sim</span><span class="sxs-lookup"><span data-stu-id="cf460-199">Yes</span></span>|<span data-ttu-id="cf460-200">**varchar(max)**</span><span class="sxs-lookup"><span data-stu-id="cf460-200">**varchar(max)**</span></span>|  
|`SQLVARCHAR`|<span data-ttu-id="cf460-201">Sim</span><span class="sxs-lookup"><span data-stu-id="cf460-201">Yes</span></span>|<span data-ttu-id="cf460-202">**varchar(max)**</span><span class="sxs-lookup"><span data-stu-id="cf460-202">**varchar(max)**</span></span>|  
|`SQLBINARY`|<span data-ttu-id="cf460-203">Sim</span><span class="sxs-lookup"><span data-stu-id="cf460-203">Yes</span></span>|<span data-ttu-id="cf460-204">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="cf460-204">**varbinary(max)**</span></span>|  
|`SQLBIGBINARY`|<span data-ttu-id="cf460-205">Sim</span><span class="sxs-lookup"><span data-stu-id="cf460-205">Yes</span></span>|<span data-ttu-id="cf460-206">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="cf460-206">**varbinary(max)**</span></span>|  
|`SQLBIGVARBINARY`|<span data-ttu-id="cf460-207">Sim</span><span class="sxs-lookup"><span data-stu-id="cf460-207">Yes</span></span>|<span data-ttu-id="cf460-208">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="cf460-208">**varbinary(max)**</span></span>|  
|`SQLVARBINARY`|<span data-ttu-id="cf460-209">Sim</span><span class="sxs-lookup"><span data-stu-id="cf460-209">Yes</span></span>|<span data-ttu-id="cf460-210">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="cf460-210">**varbinary(max)**</span></span>|  
|`SQLNCHAR`|<span data-ttu-id="cf460-211">Sim</span><span class="sxs-lookup"><span data-stu-id="cf460-211">Yes</span></span>|<span data-ttu-id="cf460-212">**nvarchar(max)**</span><span class="sxs-lookup"><span data-stu-id="cf460-212">**nvarchar(max)**</span></span>|  
|`SQLNVARCHAR`|<span data-ttu-id="cf460-213">Sim</span><span class="sxs-lookup"><span data-stu-id="cf460-213">Yes</span></span>|<span data-ttu-id="cf460-214">**nvarchar(max)**</span><span class="sxs-lookup"><span data-stu-id="cf460-214">**nvarchar(max)**</span></span>|  
|`SQLXML`|<span data-ttu-id="cf460-215">Sim</span><span class="sxs-lookup"><span data-stu-id="cf460-215">Yes</span></span>|<span data-ttu-id="cf460-216">**Xml**</span><span class="sxs-lookup"><span data-stu-id="cf460-216">**Xml**</span></span>|  
|`SQLUDT`|<span data-ttu-id="cf460-217">Você pode usar o</span><span class="sxs-lookup"><span data-stu-id="cf460-217">Either</span></span>|<span data-ttu-id="cf460-218">**UDT**</span><span class="sxs-lookup"><span data-stu-id="cf460-218">**Udt**</span></span>|  
  
## <a name="bcp_gettypename-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="cf460-219">Suporte de bcp_gettypename a recursos aprimorados de data e hora</span><span class="sxs-lookup"><span data-stu-id="cf460-219">bcp_gettypename Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="cf460-220">Os valores de parâmetro de token para tipos de data/hora são descritos na coluna "Type in sqlncli. h" da tabela em [alterações de cópia em massa para tipos de data e hora aprimorados &#40;OLE DB e ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="cf460-220">The token parameter values for date/time types are described in the "Type in sqlncli.h" column of the table in [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span> <span data-ttu-id="cf460-221">O valor retornado está na linha correspondente da coluna "Tipo de armazenamento de arquivo" coluna.</span><span class="sxs-lookup"><span data-stu-id="cf460-221">The returned value is in the corresponding row of the "File storage type" column.</span></span>  
  
 <span data-ttu-id="cf460-222">Para obter mais informações, consulte [melhorias de data e hora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="cf460-222">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf460-223">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cf460-223">See Also</span></span>  
 [<span data-ttu-id="cf460-224">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="cf460-224">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
