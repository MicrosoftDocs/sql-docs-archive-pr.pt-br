---
title: Especificar valores padrão para colunas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], defaults
- default values
ms.assetid: 64514aed-b846-407b-992e-cf813f9a1a91
author: stevestein
ms.author: sstein
ms.openlocfilehash: 650347c29e1175c5a1fe646fc079478520dc8c6d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581703"
---
# <a name="specify-default-values-for-columns"></a><span data-ttu-id="dfc57-102">Especificar valores padrão para colunas</span><span class="sxs-lookup"><span data-stu-id="dfc57-102">Specify Default Values for Columns</span></span>
  <span data-ttu-id="dfc57-103">Você pode especificar um valor padrão que será inserido na coluna no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfc57-103">You can specify a default value that will be entered in the column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="dfc57-104">Se você não atribuir um valor padrão e o usuário deixar a coluna em branco:</span><span class="sxs-lookup"><span data-stu-id="dfc57-104">If you do not assign a default value and the user leaves the column blank, then:</span></span>  
  
-   <span data-ttu-id="dfc57-105">Se você definir a opção para permitir valores nulos, será inserido NULL na coluna.</span><span class="sxs-lookup"><span data-stu-id="dfc57-105">If you set the option to allow null values, NULL will be inserted into the column.</span></span>  
  
-   <span data-ttu-id="dfc57-106">Se você não definir a opção para permitir valores nulos, a coluna permanecerá em branco, mas o usuário não poderá salvar a linha até fornecer um valor para a coluna.</span><span class="sxs-lookup"><span data-stu-id="dfc57-106">If you do not set the option to allow null values, the column will remain blank, but the user will not be able to save the row until they supply a value for the column.</span></span>  
  
 <span data-ttu-id="dfc57-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="dfc57-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dfc57-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="dfc57-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dfc57-109">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="dfc57-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="dfc57-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="dfc57-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dfc57-111">**Para especificar um valor padrão usando:**</span><span class="sxs-lookup"><span data-stu-id="dfc57-111">**To specify a default value, using:**</span></span>  
  
     [<span data-ttu-id="dfc57-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dfc57-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="dfc57-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dfc57-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dfc57-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="dfc57-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="dfc57-115">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="dfc57-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="dfc57-116">Se sua entrada no campo **Valor Padrão** substituir um padrão associado (exibido sem parênteses), será solicitado que você desvincule o padrão e substitua-o pelo novo padrão.</span><span class="sxs-lookup"><span data-stu-id="dfc57-116">If your entry in the **Default Value** field replaces a bound default (which is shown without parentheses), you will be prompted to unbind the default and replace it with your new default.</span></span>  
  
-   <span data-ttu-id="dfc57-117">Para inserir uma cadeia de caracteres de texto, coloque o valor entre aspas simples ('); não utilize aspas duplas ("), pois elas estão reservadas para identificadores entre aspas.</span><span class="sxs-lookup"><span data-stu-id="dfc57-117">To enter a text string, enclose the value in single quotation marks ('); do not use double quotation marks (") because they are reserved for quoted identifiers.</span></span>  
  
-   <span data-ttu-id="dfc57-118">Para inserir um padrão numérico, insira o número sem colocá-lo entre aspas.</span><span class="sxs-lookup"><span data-stu-id="dfc57-118">To enter a numeric default, enter the number without quotation marks around it.</span></span>  
  
-   <span data-ttu-id="dfc57-119">Para inserir um objeto/função, digite o nome do objeto/função sem aspas.</span><span class="sxs-lookup"><span data-stu-id="dfc57-119">To enter an object/function, enter the name of the object/function without quotation marks around it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dfc57-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="dfc57-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dfc57-121">Permissões</span><span class="sxs-lookup"><span data-stu-id="dfc57-121">Permissions</span></span>  
 <span data-ttu-id="dfc57-122">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="dfc57-122">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dfc57-123">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dfc57-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-default-value-for-a-column"></a><span data-ttu-id="dfc57-124">Para especificar um valor padrão para uma coluna</span><span class="sxs-lookup"><span data-stu-id="dfc57-124">To specify a default value for a column</span></span>  
  
1.  <span data-ttu-id="dfc57-125">No **Pesquisador de Objetos**, clique com o botão direito do mouse na tabela com as colunas cuja escala você deseja alterar e clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="dfc57-125">In **Object Explorer**, right-click the table with columns for which you want to change the scale and click **Design**.</span></span>  
  
2.  <span data-ttu-id="dfc57-126">Selecione a coluna para a qual você deseja especificar o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="dfc57-126">Select the column for which you want to specify a default value.</span></span>  
  
3.  <span data-ttu-id="dfc57-127">Na guia **Propriedades da Coluna** , insira o novo valor padrão na propriedade **Valor ou Associação Padrão** .</span><span class="sxs-lookup"><span data-stu-id="dfc57-127">In the **Column Properties** tab, enter the new default value in the **Default Value or Binding** property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dfc57-128">Para inserir um valor numérico padrão, insira o número.</span><span class="sxs-lookup"><span data-stu-id="dfc57-128">To enter a numeric default value, enter the number.</span></span> <span data-ttu-id="dfc57-129">Para um objeto ou função insira seu nome.</span><span class="sxs-lookup"><span data-stu-id="dfc57-129">For an object or function enter its name.</span></span> <span data-ttu-id="dfc57-130">Para um padrão alfanumérico insira o valor entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="dfc57-130">For an alphanumeric default enter the value inside single quotes.</span></span>  
  
4.  <span data-ttu-id="dfc57-131">No menu **Arquivo**, clique em **Salvar**_nome da tabela_.</span><span class="sxs-lookup"><span data-stu-id="dfc57-131">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dfc57-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dfc57-132">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-default-value-for-a-column"></a><span data-ttu-id="dfc57-133">Para especificar um valor padrão para uma coluna</span><span class="sxs-lookup"><span data-stu-id="dfc57-133">To specify a default value for a column</span></span>  
  
1.  <span data-ttu-id="dfc57-134">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfc57-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dfc57-135">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="dfc57-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dfc57-136">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="dfc57-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    CREATE TABLE dbo.doc_exz ( column_a INT, column_b INT) ;  
    GO  
    INSERT INTO dbo.doc_exz (column_a)VALUES ( 7 ) ;  
    GO  
    ALTER TABLE dbo.doc_exz  
    ADD CONSTRAINT col_b_def  
    DEFAULT 50 FOR column_b ;  
    GO  
  
    ```  
  
 <span data-ttu-id="dfc57-137">Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dfc57-137">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
