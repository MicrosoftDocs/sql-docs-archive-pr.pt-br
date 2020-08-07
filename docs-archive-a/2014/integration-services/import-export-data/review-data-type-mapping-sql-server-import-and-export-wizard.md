---
title: Examinar Mapeamento de Tipo de Dados (Assistente para Importação e Exportação do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.reviewissues.f1
ms.assetid: 0625c4f9-b8ff-4593-b884-39398b9d43af
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 693abfdc3bd19b8e39ba6b53d31c86b36944c16c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575926"
---
# <a name="review-data-type-mapping-sql-server-import-and-export-wizard"></a><span data-ttu-id="71eba-102">Revisar mapeamento de tipo de dados (Assistente de Importação e Exportação do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="71eba-102">Review Data Type Mapping (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="71eba-103">Use a página **examinar mapeamento de tipo de dados** para examinar informações detalhadas sobre conversões de tipo de dados que o assistente precisa executar para tornar os dados de origem compatíveis com o destino.</span><span class="sxs-lookup"><span data-stu-id="71eba-103">Use the **Review Data Type Mapping** page to review detailed information about data type conversions that the wizard has to perform to make the source data compatible with the destination.</span></span> <span data-ttu-id="71eba-104">As informações incluem dicas visuais para fazer distinção entre conversões que se espera sejam bem sucedidas de conversões que podem causar erros ou truncamentos.</span><span class="sxs-lookup"><span data-stu-id="71eba-104">This information includes visual cues to distinguish conversions that are expected to succeed from conversions that might cause errors or truncations.</span></span> <span data-ttu-id="71eba-105">Para cada conversão, é possível decidir se deseja aceitar a conversão sugerida pelo assistente, além de especificar como manipular qualquer eventual erro.</span><span class="sxs-lookup"><span data-stu-id="71eba-105">For each conversion, you can decide whether to accept the conversion that the wizard suggests, and you can specify how to handle any errors that occur.</span></span>  
  
 <span data-ttu-id="71eba-106">Para obter mais informações sobre este assistente, consulte [Assistente de Importação e Exportação do SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="71eba-106">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="71eba-107">Para saber mais sobre as opções de inicialização do assistente e sobre as permissões necessárias para executar o assistente com êxito, consulte [executar o assistente de importação e exportação do SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="71eba-107">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="71eba-108">O objetivo do Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é copiar dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="71eba-108">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="71eba-109">O assistente também pode criar um banco de dados de destino e tabelas de destino para você.</span><span class="sxs-lookup"><span data-stu-id="71eba-109">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="71eba-110">No entanto, se for necessário copiar vários bancos de dados ou tabelas, ou outros tipos de objetos de banco de dados, será necessário usar o Assistente para Copiar Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="71eba-110">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="71eba-111">Para obter mais informações, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="71eba-111">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="71eba-112">Opções</span><span class="sxs-lookup"><span data-stu-id="71eba-112">Options</span></span>  
 <span data-ttu-id="71eba-113">A página **Revisar Mapeamento de Tipo de Dados** consiste de uma lista **Tabela** , uma lista de **Mapeamento de tipo de dados** e opções de tratamento de erros.</span><span class="sxs-lookup"><span data-stu-id="71eba-113">The **Review Data Type Mapping** page consists of a **Table** list, a **Data type mapping** list, and error handling options.</span></span>  
  
### <a name="table-list"></a><span data-ttu-id="71eba-114">Lista Tabela</span><span class="sxs-lookup"><span data-stu-id="71eba-114">Table List</span></span>  
 <span data-ttu-id="71eba-115">A parte superior da página **examinar problemas de tipo de dados** é **uma lista de tabelas que** lista as tabelas a serem transferidas da origem para o destino.</span><span class="sxs-lookup"><span data-stu-id="71eba-115">The upper part of the **Review Data Type Issues** page is a **Table** list that lists the tables to be transferred from the source to the destination.</span></span> <span data-ttu-id="71eba-116">A tabela a seguir descreve as colunas nessa lista.</span><span class="sxs-lookup"><span data-stu-id="71eba-116">The following table describes the columns in this list.</span></span>  
  
|<span data-ttu-id="71eba-117">Coluna</span><span class="sxs-lookup"><span data-stu-id="71eba-117">Column</span></span>|<span data-ttu-id="71eba-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="71eba-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="71eba-119">Ícone da fonte</span><span class="sxs-lookup"><span data-stu-id="71eba-119">Source icon</span></span>|<span data-ttu-id="71eba-120">Indica a probabilidade de sucesso para as conversões de tipo de dados:</span><span class="sxs-lookup"><span data-stu-id="71eba-120">Indicates the probability of success for the data type conversions:</span></span><br /><br /> <span data-ttu-id="71eba-121">Um ícone de sinal de verificação, verde, indica que o assistente espera que todas as conversões de tipo de dados da tabela sejam bem sucedidas.</span><span class="sxs-lookup"><span data-stu-id="71eba-121">A green check mark icon indicates that the wizard expects all data type conversions for this table to succeed.</span></span><br /><br /> <span data-ttu-id="71eba-122">Um ícone de advertência, amarelo, indica que você deveria revisar as conversões individuais que o assistente executará.</span><span class="sxs-lookup"><span data-stu-id="71eba-122">A yellow warning icon indicates that you should review the individual conversions that the wizard will perform.</span></span> <span data-ttu-id="71eba-123">Para revisar essas conversões, selecione a tabela e revise as conversões das colunas individuais na lista **Mapeamento de tipo de dados** .</span><span class="sxs-lookup"><span data-stu-id="71eba-123">To review these conversions, select the table, and then review the conversions for individual columns in the **Data type mapping** list.</span></span><br /><br /> <span data-ttu-id="71eba-124">Um ícone de erro, vermelho, indica que o assistente não pode executar algumas das conversões da tabela de maneira segura.</span><span class="sxs-lookup"><span data-stu-id="71eba-124">A red error icon indicates that the wizard is not able to perform some of the conversions for this table reliably.</span></span>|  
|<span data-ttu-id="71eba-125">**Origem**</span><span class="sxs-lookup"><span data-stu-id="71eba-125">**Source**</span></span>|<span data-ttu-id="71eba-126">Exibe o nome da tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="71eba-126">Displays the name of the source table.</span></span>|  
|<span data-ttu-id="71eba-127">Ícone de destino</span><span class="sxs-lookup"><span data-stu-id="71eba-127">Destination icon</span></span>|<span data-ttu-id="71eba-128">Indica se o destino já existe ou será criado pelo assistente:</span><span class="sxs-lookup"><span data-stu-id="71eba-128">Indicates whether the destination already exists or will be created by the wizard:</span></span><br /><br /> <span data-ttu-id="71eba-129">Um ícone de tabela indica que o destino é uma tabela existente.</span><span class="sxs-lookup"><span data-stu-id="71eba-129">A table icon indicates that the destination is an existing table.</span></span><br /><br /> <span data-ttu-id="71eba-130">Um ícone de tabela com um clarão de sol indica que o destino é uma tabela nova que será criada pelo assistente.</span><span class="sxs-lookup"><span data-stu-id="71eba-130">A table icon with a sunburst indicates that the destination is a new table that the wizard will create.</span></span>|  
|<span data-ttu-id="71eba-131">**Destino**</span><span class="sxs-lookup"><span data-stu-id="71eba-131">**Destination**</span></span>|<span data-ttu-id="71eba-132">Exibe o nome da tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="71eba-132">Displays the name of the destination table.</span></span>|  
  
 <span data-ttu-id="71eba-133">Para exibir informações de conversão sobre uma tabela individual, selecione uma tabela nesta grade de **tabela** .</span><span class="sxs-lookup"><span data-stu-id="71eba-133">To view conversion information about an individual table, select a table in this **Table** grid.</span></span> <span data-ttu-id="71eba-134">As informações de conversão da tabela selecionada são exibidas nas colunas na grade **Mapeamento de tipo de dados** localizada na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="71eba-134">The conversion information for the selected table appears in the columns in the **Data type mapping grid** in the lower part of the page.</span></span>  
  
### <a name="data-type-mapping-list"></a><span data-ttu-id="71eba-135">Lista Mapeamento de tipo de dados</span><span class="sxs-lookup"><span data-stu-id="71eba-135">Data type mapping List</span></span>  
 <span data-ttu-id="71eba-136">A parte inferior da página **examinar problemas de tipo de dados** é a lista **mapeamento de tipo de dados** .</span><span class="sxs-lookup"><span data-stu-id="71eba-136">The lower part of the **Review Data Type Issues** page is the **Data type mapping** list.</span></span> <span data-ttu-id="71eba-137">Esta grade fornece informações detalhadas de conversão sobre as colunas na tabela selecionada na lista **Tabela** .</span><span class="sxs-lookup"><span data-stu-id="71eba-137">This grid provides detailed conversion information about the columns in the table that is selected in the **Table** list.</span></span> <span data-ttu-id="71eba-138">A tabela a seguir descreve as colunas nessa lista.</span><span class="sxs-lookup"><span data-stu-id="71eba-138">The following table describes the columns in this list.</span></span>  
  
|<span data-ttu-id="71eba-139">Coluna</span><span class="sxs-lookup"><span data-stu-id="71eba-139">Column</span></span>|<span data-ttu-id="71eba-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="71eba-140">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="71eba-141">Ícone de conversão</span><span class="sxs-lookup"><span data-stu-id="71eba-141">Conversion icon</span></span>|<span data-ttu-id="71eba-142">Indica a probabilidade de sucesso para as conversões de tipo de dados:</span><span class="sxs-lookup"><span data-stu-id="71eba-142">Indicates the probability of success for the data type conversions:</span></span><br /><br /> <span data-ttu-id="71eba-143">Um ícone de sinal de verificação, verde,  indica que o assistente espera que a conversão de tipo de dados da coluna sejam bem sucedida.</span><span class="sxs-lookup"><span data-stu-id="71eba-143">A green check mark icon indicates that the wizard expects that the data type conversion for this column to succeed.</span></span><br /><br /> <span data-ttu-id="71eba-144">Um ícone de advertência, amarelo, indica que você deveria revisar a conversão que o assistente executará.</span><span class="sxs-lookup"><span data-stu-id="71eba-144">A yellow warning icon indicates that you should review the conversion that the wizard will perform.</span></span> <span data-ttu-id="71eba-145">Para examinar a conversão, clique duas vezes na coluna para exibir a caixa de diálogo **Detalhes da Conversão de Coluna** .</span><span class="sxs-lookup"><span data-stu-id="71eba-145">To review the conversion, double-click on the column to view the **Column Conversion Details** dialog box.</span></span><br /><br /> <span data-ttu-id="71eba-146">Um ícone de erro, vermelho, indica que o assistente não pode executar a conversão de maneira segura.</span><span class="sxs-lookup"><span data-stu-id="71eba-146">A red error icon indicates that the wizard is not able to perform the conversion reliably.</span></span>|  
|<span data-ttu-id="71eba-147">**Coluna de Origem**</span><span class="sxs-lookup"><span data-stu-id="71eba-147">**Source Column**</span></span>|<span data-ttu-id="71eba-148">Exibe o nome da coluna de origem.</span><span class="sxs-lookup"><span data-stu-id="71eba-148">Displays the name of the source column.</span></span>|  
|<span data-ttu-id="71eba-149">**Tipo de origem**</span><span class="sxs-lookup"><span data-stu-id="71eba-149">**Source Type**</span></span>|<span data-ttu-id="71eba-150">Exibe o tipo de dados da coluna de origem.</span><span class="sxs-lookup"><span data-stu-id="71eba-150">Displays the data type of the source column.</span></span>|  
|<span data-ttu-id="71eba-151">**Coluna de Destino**</span><span class="sxs-lookup"><span data-stu-id="71eba-151">**Destination Column**</span></span>|<span data-ttu-id="71eba-152">Exibe o nome da coluna de destino.</span><span class="sxs-lookup"><span data-stu-id="71eba-152">Displays the name of the destination column.</span></span>|  
|<span data-ttu-id="71eba-153">**Tipo de destino**</span><span class="sxs-lookup"><span data-stu-id="71eba-153">**Destination Type**</span></span>|<span data-ttu-id="71eba-154">Exibe o tipo de dados da coluna de destino.</span><span class="sxs-lookup"><span data-stu-id="71eba-154">Displays the data type of the destination column.</span></span>|  
|<span data-ttu-id="71eba-155">**Converter**</span><span class="sxs-lookup"><span data-stu-id="71eba-155">**Convert**</span></span>|<span data-ttu-id="71eba-156">Especifique se a conversão planejada deve prosseguir:</span><span class="sxs-lookup"><span data-stu-id="71eba-156">Specify whether the planned conversion should continue:</span></span><br /><br /> <span data-ttu-id="71eba-157">Marque a caixa de seleção para que o assistente continue com a conversão planejada.</span><span class="sxs-lookup"><span data-stu-id="71eba-157">Select the check box to have the wizard continue with the planned conversion.</span></span><br /><br /> <span data-ttu-id="71eba-158">Desmarque a caixa de seleção para cancelar a conversão de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="71eba-158">Clear the check box to cancel the data type conversion.</span></span>|  
|<span data-ttu-id="71eba-159">**Se houver erro**</span><span class="sxs-lookup"><span data-stu-id="71eba-159">**On Error**</span></span>|<span data-ttu-id="71eba-160">Especifique como o assistente lida com erros:</span><span class="sxs-lookup"><span data-stu-id="71eba-160">Specify how the wizard handles errors:</span></span><br /><br /> <span data-ttu-id="71eba-161">Use a configuração se houver **erro (global)** .</span><span class="sxs-lookup"><span data-stu-id="71eba-161">Use the **On Error (global)** setting.</span></span><br /><br /> <span data-ttu-id="71eba-162">Falha com um erro, e interrompe o processo de importação ou exportação.</span><span class="sxs-lookup"><span data-stu-id="71eba-162">Fail with an error, and stop the import or export process.</span></span><br /><br /> <span data-ttu-id="71eba-163">Ignore o erro.</span><span class="sxs-lookup"><span data-stu-id="71eba-163">Ignore the error.</span></span>|  
|<span data-ttu-id="71eba-164">**Se Houver Truncamento**</span><span class="sxs-lookup"><span data-stu-id="71eba-164">**On Truncation**</span></span>|<span data-ttu-id="71eba-165">Especifique como o assistente controla truncamentos:</span><span class="sxs-lookup"><span data-stu-id="71eba-165">Specify how the wizard handles truncation:</span></span><br /><br /> <span data-ttu-id="71eba-166">Use a configuração **em truncamento (global)** .</span><span class="sxs-lookup"><span data-stu-id="71eba-166">Use the **On Truncation (global)** setting.</span></span><br /><br /> <span data-ttu-id="71eba-167">Falha com um erro e interrompe o processo de importação ou exportação</span><span class="sxs-lookup"><span data-stu-id="71eba-167">Fail with an error, and stop the import or export process</span></span><br /><br /> <span data-ttu-id="71eba-168">Ignore o truncamento.</span><span class="sxs-lookup"><span data-stu-id="71eba-168">Ignore the truncation.</span></span>|  
  
 <span data-ttu-id="71eba-169">Para exibir informações detalhadas sobre a conversão de uma coluna particular de dados, clique duas vezes em qualquer linha na lista.</span><span class="sxs-lookup"><span data-stu-id="71eba-169">To view detailed information about the conversion of a particular column of data, double-click any row in the list.</span></span> <span data-ttu-id="71eba-170">A caixa de diálogo **Detalhes da Conversão de Coluna** abre e exibe informações de conversão mais detalhadas da coluna.</span><span class="sxs-lookup"><span data-stu-id="71eba-170">The **Column Conversion Details** dialog box opens and displays more detailed conversion information for the column.</span></span>  
  
### <a name="error-handling-options"></a><span data-ttu-id="71eba-171">Opções de tratamento de erros</span><span class="sxs-lookup"><span data-stu-id="71eba-171">Error Handling Options</span></span>  
 <span data-ttu-id="71eba-172">**Se Houver Erro (global)**</span><span class="sxs-lookup"><span data-stu-id="71eba-172">**On Error (global)**</span></span>  
 <span data-ttu-id="71eba-173">Especifique como o assistente lida com erros:</span><span class="sxs-lookup"><span data-stu-id="71eba-173">Specify how the wizard handles errors:</span></span>  
  
-   <span data-ttu-id="71eba-174">Falha com um erro, e interrompe o processo de importação ou exportação.</span><span class="sxs-lookup"><span data-stu-id="71eba-174">Fail with an error, and stop the import or export process.</span></span>  
  
-   <span data-ttu-id="71eba-175">Ignore o erro e continue o processo de importação ou exportação.</span><span class="sxs-lookup"><span data-stu-id="71eba-175">Ignore the error, and continue the import or export process.</span></span>  
  
 <span data-ttu-id="71eba-176">Esta configuração é aplicável a todas as conversões com **Usar Global** selecionado na coluna **Se Houver Erro** da lista **Mapeamento de tipo de dados** .</span><span class="sxs-lookup"><span data-stu-id="71eba-176">This setting applies to all conversions that have **Use Global** selected in the **On Error** column of the **Data type mapping** list.</span></span>  
  
 <span data-ttu-id="71eba-177">**Se Houver Truncamento (global)**</span><span class="sxs-lookup"><span data-stu-id="71eba-177">**On Truncation (global)**</span></span>  
 <span data-ttu-id="71eba-178">Especifique como o assistente controla truncamentos:</span><span class="sxs-lookup"><span data-stu-id="71eba-178">Specify how the wizard handles truncation:</span></span>  
  
-   <span data-ttu-id="71eba-179">Falha com um erro, e interrompe o processo de importação ou exportação.</span><span class="sxs-lookup"><span data-stu-id="71eba-179">Fail with an error, and stop the import or export process.</span></span>  
  
-   <span data-ttu-id="71eba-180">Ignore o truncamento e continue o processo de importação ou exportação.</span><span class="sxs-lookup"><span data-stu-id="71eba-180">Ignore the truncation, and continue the import or export process.</span></span>  
  
 <span data-ttu-id="71eba-181">Esta configuração é aplicável a todas as conversões com **Usar Global** selecionado na coluna **Se Houver Truncamento** da lista **Mapeamento de tipo de dados** .</span><span class="sxs-lookup"><span data-stu-id="71eba-181">This setting applies to all conversions that have **Use Global** selected in the **On Truncation** column of the **Data type mapping** list.</span></span>  
  
  