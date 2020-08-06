---
title: Suporte a sql_variant para tipos de data e hora | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- sql_variant data type
ms.assetid: 12ff1ea6-e2cc-40e6-910c-3126974a90b3
author: rothja
ms.author: jroth
ms.openlocfilehash: 0818f0ccee72264ea7cab69b90e18418179031ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684198"
---
# <a name="sql_variant-support-for-date-and-time-types"></a><span data-ttu-id="b29b1-102">Suporte a Sql_variant para tipos de data e hora</span><span class="sxs-lookup"><span data-stu-id="b29b1-102">sql_variant Support for Date and Time Types</span></span>
  <span data-ttu-id="b29b1-103">Este tópico descreve como o tipo de dados `sql_variant` oferece suporte à funcionalidade aprimorada de data e hora.</span><span class="sxs-lookup"><span data-stu-id="b29b1-103">This topic describes how the `sql_variant` data type supports enhanced date and time functionality.</span></span>  
  
 <span data-ttu-id="b29b1-104">O atributo de coluna SQL_CA_SS_VARIANT_TYPE é usado para retornar o tipo C de uma coluna de resultado variável.</span><span class="sxs-lookup"><span data-stu-id="b29b1-104">The column attribute SQL_CA_SS_VARIANT_TYPE is used to return the C type of a variant result column.</span></span> [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]<span data-ttu-id="b29b1-105">O  apresenta um atributo adicional, SQL_CA_SS_VARIANT_SQL_TYPE, que define o tipo SQL de uma coluna de resultado variável no IRD (descritor de linha de implementação).</span><span class="sxs-lookup"><span data-stu-id="b29b1-105">introduces an additional attribute, SQL_CA_SS_VARIANT_SQL_TYPE, which sets the SQL type of a variant result column in the implementation row descriptor (IRD).</span></span> <span data-ttu-id="b29b1-106">SQL_CA_SS_VARIANT_SQL_TYPE também pode ser usado no IPD (descritor de parâmetro de implementação) para especificar o tipo SQL de um parâmetro SQL_SS_TIME2 ou SQL_SS_TIMESTAMPOFFSET com tipo SQL_C_BINARY C associado ao tipo SQL_SS_VARIANT.</span><span class="sxs-lookup"><span data-stu-id="b29b1-106">SQL_CA_SS_VARIANT_SQL_TYPE can also be used in the implementation parameter descriptor (IPD) to specify the SQL type of a SQL_SS_TIME2 or SQL_SS_TIMESTAMPOFFSET parameter that has SQL_C_BINARY C type bound with type SQL_SS_VARIANT.</span></span>  
  
 <span data-ttu-id="b29b1-107">Os novos tipos SQL_SS_TIME2 e SQL_SS_TIMESTAMPOFFSET podem ser definidos por SQLColAttribute.</span><span class="sxs-lookup"><span data-stu-id="b29b1-107">The new types SQL_SS_TIME2 and SQL_SS_TIMESTAMPOFFSET can be set by SQLColAttribute.</span></span> <span data-ttu-id="b29b1-108">SQL_CA_SS_VARIANT_SQL_TYPE pode ser retornado por SQLGetDescField.</span><span class="sxs-lookup"><span data-stu-id="b29b1-108">SQL_CA_SS_VARIANT_SQL_TYPE can be returned by SQLGetDescField.</span></span>  
  
 <span data-ttu-id="b29b1-109">Em colunas de resultado, o driver será convertido da variante em tipos de data/hora.</span><span class="sxs-lookup"><span data-stu-id="b29b1-109">For result columns, the driver will convert from the variant to date/time types.</span></span> <span data-ttu-id="b29b1-110">Para obter mais informações, consulte [conversões de SQL para C](datetime-data-type-conversions-from-sql-to-c.md). Ao associar a SQL_C_BINARY, o comprimento do buffer deve ser grande o suficiente para receber a struct que corresponde ao tipo SQL.</span><span class="sxs-lookup"><span data-stu-id="b29b1-110">For more information, see [Conversions from SQL to C](datetime-data-type-conversions-from-sql-to-c.md). When binding to SQL_C_BINARY, the buffer length must be large enough to receive the struct that corresponds to the SQL type.</span></span>  
  
 <span data-ttu-id="b29b1-111">Para os parâmetros SQL_SS_TIME2 e SQL_SS_TIMESTAMPOFFSET, o driver converterá valores de C em valores `sql_variant`, conforme descrição na tabela abaixo.</span><span class="sxs-lookup"><span data-stu-id="b29b1-111">For the SQL_SS_TIME2 and SQL_SS_TIMESTAMPOFFSET parameters, the driver will convert C values to `sql_variant` values, as described in the table below.</span></span> <span data-ttu-id="b29b1-112">Se um parâmetro for associado como SQL_C_BINARY e o tipo de servidor for SQL_SS_VARIANT, ele será tratado como um valor binário, a menos que o aplicativo tenha definido SQL_CA_SS_VARIANT_SQL_TYPE como outro tipo SQL.</span><span class="sxs-lookup"><span data-stu-id="b29b1-112">If a parameter is bound as SQL_C_BINARY and the server type is SQL_SS_VARIANT, it will be treated as a binary value unless the application has set SQL_CA_SS_VARIANT_SQL_TYPE to some other SQL type.</span></span> <span data-ttu-id="b29b1-113">Nesse caso, SQL_CA_SS_VARIANT_SQL_TYPE tem precedência; ou seja, caso SQL_CA_SS_VARIANT_SQL_TYPE seja definido, ele substitui o comportamento padrão de dedução do tipo SQL variável do tipo C.</span><span class="sxs-lookup"><span data-stu-id="b29b1-113">In this case, SQL_CA_SS_VARIANT_SQL_TYPE takes precedence; that is, if SQL_CA_SS_VARIANT_SQL_TYPE is set, it overrides the default behavior of deducing the variant SQL type from the C type.</span></span>  
  
|<span data-ttu-id="b29b1-114">Tipo de C</span><span class="sxs-lookup"><span data-stu-id="b29b1-114">C type</span></span>|<span data-ttu-id="b29b1-115">Tipo de servidor</span><span class="sxs-lookup"><span data-stu-id="b29b1-115">Server type</span></span>|<span data-ttu-id="b29b1-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="b29b1-116">Comments</span></span>|  
|------------|-----------------|--------------|  
|<span data-ttu-id="b29b1-117">SQL_C_CHAR</span><span class="sxs-lookup"><span data-stu-id="b29b1-117">SQL_C_CHAR</span></span>|<span data-ttu-id="b29b1-118">varchar</span><span class="sxs-lookup"><span data-stu-id="b29b1-118">varchar</span></span>|<span data-ttu-id="b29b1-119">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-119">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-120">SQL_C_WCHAR</span><span class="sxs-lookup"><span data-stu-id="b29b1-120">SQL_C_WCHAR</span></span>|<span data-ttu-id="b29b1-121">nvarcar</span><span class="sxs-lookup"><span data-stu-id="b29b1-121">nvarcar</span></span>|<span data-ttu-id="b29b1-122">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-122">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-123">SQL_C_TINYINT</span><span class="sxs-lookup"><span data-stu-id="b29b1-123">SQL_C_TINYINT</span></span>|<span data-ttu-id="b29b1-124">SMALLINT</span><span class="sxs-lookup"><span data-stu-id="b29b1-124">smallint</span></span>|<span data-ttu-id="b29b1-125">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-125">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-126">SQL_C_STINYINT</span><span class="sxs-lookup"><span data-stu-id="b29b1-126">SQL_C_STINYINT</span></span>|<span data-ttu-id="b29b1-127">SMALLINT</span><span class="sxs-lookup"><span data-stu-id="b29b1-127">smallint</span></span>|<span data-ttu-id="b29b1-128">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-128">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-129">SQL_C_SHORT</span><span class="sxs-lookup"><span data-stu-id="b29b1-129">SQL_C_SHORT</span></span>|<span data-ttu-id="b29b1-130">SMALLINT</span><span class="sxs-lookup"><span data-stu-id="b29b1-130">smallint</span></span>|<span data-ttu-id="b29b1-131">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-131">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-132">SQL_C_SSHORT</span><span class="sxs-lookup"><span data-stu-id="b29b1-132">SQL_C_SSHORT</span></span>|<span data-ttu-id="b29b1-133">SMALLINT</span><span class="sxs-lookup"><span data-stu-id="b29b1-133">smallint</span></span>|<span data-ttu-id="b29b1-134">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-134">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-135">SQL_C_USHORT</span><span class="sxs-lookup"><span data-stu-id="b29b1-135">SQL_C_USHORT</span></span>|<span data-ttu-id="b29b1-136">int</span><span class="sxs-lookup"><span data-stu-id="b29b1-136">int</span></span>|<span data-ttu-id="b29b1-137">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-137">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-138">SQL_C_LONG</span><span class="sxs-lookup"><span data-stu-id="b29b1-138">SQL_C_LONG</span></span>|<span data-ttu-id="b29b1-139">int</span><span class="sxs-lookup"><span data-stu-id="b29b1-139">int</span></span>|<span data-ttu-id="b29b1-140">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-140">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-141">SQL_C_SLONG</span><span class="sxs-lookup"><span data-stu-id="b29b1-141">SQL_C_SLONG</span></span>|<span data-ttu-id="b29b1-142">int</span><span class="sxs-lookup"><span data-stu-id="b29b1-142">int</span></span>|<span data-ttu-id="b29b1-143">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-143">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-144">SQL_C_ULONG</span><span class="sxs-lookup"><span data-stu-id="b29b1-144">SQL_C_ULONG</span></span>|<span data-ttu-id="b29b1-145">BIGINT</span><span class="sxs-lookup"><span data-stu-id="b29b1-145">bigint</span></span>|<span data-ttu-id="b29b1-146">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-146">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-147">SQL_C_SBIGINT</span><span class="sxs-lookup"><span data-stu-id="b29b1-147">SQL_C_SBIGINT</span></span>|<span data-ttu-id="b29b1-148">BIGINT</span><span class="sxs-lookup"><span data-stu-id="b29b1-148">bigint</span></span>|<span data-ttu-id="b29b1-149">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-149">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-150">SQL_C_FLOAT</span><span class="sxs-lookup"><span data-stu-id="b29b1-150">SQL_C_FLOAT</span></span>|<span data-ttu-id="b29b1-151">real</span><span class="sxs-lookup"><span data-stu-id="b29b1-151">real</span></span>|<span data-ttu-id="b29b1-152">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-152">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-153">SQL_C_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="b29b1-153">SQL_C_DOUBLE</span></span>|<span data-ttu-id="b29b1-154">FLOAT</span><span class="sxs-lookup"><span data-stu-id="b29b1-154">float</span></span>|<span data-ttu-id="b29b1-155">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-155">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-156">SQL_C_BIT</span><span class="sxs-lookup"><span data-stu-id="b29b1-156">SQL_C_BIT</span></span>|<span data-ttu-id="b29b1-157">bit</span><span class="sxs-lookup"><span data-stu-id="b29b1-157">bit</span></span>|<span data-ttu-id="b29b1-158">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-158">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-159">SQL_C_UTINYINT</span><span class="sxs-lookup"><span data-stu-id="b29b1-159">SQL_C_UTINYINT</span></span>|<span data-ttu-id="b29b1-160">TINYINT</span><span class="sxs-lookup"><span data-stu-id="b29b1-160">tinyint</span></span>|<span data-ttu-id="b29b1-161">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-161">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-162">SQL_C_BINARY</span><span class="sxs-lookup"><span data-stu-id="b29b1-162">SQL_C_BINARY</span></span>|<span data-ttu-id="b29b1-163">varbinary</span><span class="sxs-lookup"><span data-stu-id="b29b1-163">varbinary</span></span>|<span data-ttu-id="b29b1-164">SQL_CA_SS_VARIANT_SQL_TYPE não é definido.</span><span class="sxs-lookup"><span data-stu-id="b29b1-164">SQL_CA_SS_VARIANT_SQL_TYPE is not set.</span></span>|  
|<span data-ttu-id="b29b1-165">SQL_C_BINARY</span><span class="sxs-lookup"><span data-stu-id="b29b1-165">SQL_C_BINARY</span></span>|<span data-ttu-id="b29b1-166">time</span><span class="sxs-lookup"><span data-stu-id="b29b1-166">time</span></span>|<span data-ttu-id="b29b1-167">SQL_CA_SS_VARIANT_SQL_TYPE = SQL_SS_TIME2</span><span class="sxs-lookup"><span data-stu-id="b29b1-167">SQL_CA_SS_VARIANT_SQL_TYPE = SQL_SS_TIME2</span></span><br /><br /> <span data-ttu-id="b29b1-168">Scale é definido como SQL_DESC_PRECISION (o parâmetro *DecimalDigits* de `SQLBindParameter` ).</span><span class="sxs-lookup"><span data-stu-id="b29b1-168">Scale is set to SQL_DESC_PRECISION (the *DecimalDigits* parameter of `SQLBindParameter`).</span></span>|  
|<span data-ttu-id="b29b1-169">SQL_C_BINARY</span><span class="sxs-lookup"><span data-stu-id="b29b1-169">SQL_C_BINARY</span></span>|<span data-ttu-id="b29b1-170">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="b29b1-170">datetimeoffset</span></span>|<span data-ttu-id="b29b1-171">SQL_CA_SS_VARIANT_SQL_TYPE = SQL_SS_TIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="b29b1-171">SQL_CA_SS_VARIANT_SQL_TYPE = SQL_SS_TIMESTAMPOFFSET</span></span><br /><br /> <span data-ttu-id="b29b1-172">Scale é definido como SQL_DESC_PRECISION (o parâmetro *DecimalDigits* de `SQLBindParameter` ).</span><span class="sxs-lookup"><span data-stu-id="b29b1-172">Scale is set to SQL_DESC_PRECISION (the *DecimalDigits* parameter of `SQLBindParameter`).</span></span>|  
|<span data-ttu-id="b29b1-173">SQL_C_TYPE_DATE</span><span class="sxs-lookup"><span data-stu-id="b29b1-173">SQL_C_TYPE_DATE</span></span>|<span data-ttu-id="b29b1-174">date</span><span class="sxs-lookup"><span data-stu-id="b29b1-174">date</span></span>|<span data-ttu-id="b29b1-175">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-175">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-176">SQL_C_TYPE_TIME</span><span class="sxs-lookup"><span data-stu-id="b29b1-176">SQL_C_TYPE_TIME</span></span>|<span data-ttu-id="b29b1-177">time(0)</span><span class="sxs-lookup"><span data-stu-id="b29b1-177">time(0)</span></span>|<span data-ttu-id="b29b1-178">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b29b1-178">SQL_CA_SS_VARIANT_SQL_TYPE is ignored.</span></span>|  
|<span data-ttu-id="b29b1-179">SQL_C_TYPE_TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="b29b1-179">SQL_C_TYPE_TIMESTAMP</span></span>|<span data-ttu-id="b29b1-180">datetime2</span><span class="sxs-lookup"><span data-stu-id="b29b1-180">datetime2</span></span>|<span data-ttu-id="b29b1-181">Scale é definido como SQL_DESC_PRECISION (o parâmetro *DecimalDigits* de `SQLBindParameter` ).</span><span class="sxs-lookup"><span data-stu-id="b29b1-181">Scale is set to SQL_DESC_PRECISION (the *DecimalDigits* parameter of `SQLBindParameter`).</span></span>|  
|<span data-ttu-id="b29b1-182">SQL_C_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="b29b1-182">SQL_C_NUMERIC</span></span>|<span data-ttu-id="b29b1-183">decimal</span><span class="sxs-lookup"><span data-stu-id="b29b1-183">decimal</span></span>|<span data-ttu-id="b29b1-184">A precisão é definida como SQL_DESC_PRECISION (o parâmetro *colunasize* de `SQLBindParameter` ).</span><span class="sxs-lookup"><span data-stu-id="b29b1-184">Precision is set to SQL_DESC_PRECISION (the *ColumnSize* parameter of `SQLBindParameter`).</span></span><br /><br /> <span data-ttu-id="b29b1-185">Conjunto de dimensionamento para SQL_DESC_SCALE (o parâmetro *DecimalDigits* de SQLBindParameter).</span><span class="sxs-lookup"><span data-stu-id="b29b1-185">Scale set to SQL_DESC_SCALE (the *DecimalDigits* parameter of SQLBindParameter).</span></span>|  
|<span data-ttu-id="b29b1-186">SQL_C_SS_TIME2</span><span class="sxs-lookup"><span data-stu-id="b29b1-186">SQL_C_SS_TIME2</span></span>|<span data-ttu-id="b29b1-187">time</span><span class="sxs-lookup"><span data-stu-id="b29b1-187">time</span></span>|<span data-ttu-id="b29b1-188">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado</span><span class="sxs-lookup"><span data-stu-id="b29b1-188">SQL_CA_SS_VARIANT_SQL_TYPE is ignored</span></span>|  
|<span data-ttu-id="b29b1-189">SQL_C_SS_TIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="b29b1-189">SQL_C_SS_TIMESTAMPOFFSET</span></span>|<span data-ttu-id="b29b1-190">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="b29b1-190">datetimeoffset</span></span>|<span data-ttu-id="b29b1-191">SQL_CA_SS_VARIANT_SQL_TYPE é ignorado</span><span class="sxs-lookup"><span data-stu-id="b29b1-191">SQL_CA_SS_VARIANT_SQL_TYPE is ignored</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b29b1-192">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b29b1-192">See Also</span></span>  
 [<span data-ttu-id="b29b1-193">Melhorias de data e hora &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="b29b1-193">Date and Time Improvements &#40;ODBC&#41;</span></span>](date-and-time-improvements-odbc.md)  
  
  