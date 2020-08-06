---
title: Editor de transformação coluna derivada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.derivedcolumntransformation.f1
helpviewer_keywords:
- Derived Column Transformation Editor
ms.assetid: ff73923e-d245-43d8-bf24-af3bdc942e51
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41a0f0dcd253473f78f2f38426b5fbd3d2ac2812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582555"
---
# <a name="derived-column-transformation-editor"></a><span data-ttu-id="33429-102">Editor de Transformação Colunas Derivadas</span><span class="sxs-lookup"><span data-stu-id="33429-102">Derived Column Transformation Editor</span></span>
  <span data-ttu-id="33429-103">Use a caixa de diálogo **Editor de Transformação Colunas Derivadas** para criar expressões que populem colunas novas ou de substituição.</span><span class="sxs-lookup"><span data-stu-id="33429-103">Use the **Derived Column Transformation Editor** dialog box to create expressions that populate new or replacement columns.</span></span>  
  
 <span data-ttu-id="33429-104">Para saber mais sobre a transformação Coluna Derivada, consulte [Transformação Coluna Derivada](data-flow/transformations/derived-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="33429-104">To learn more about the Derived Column transformation, see [Derived Column Transformation](data-flow/transformations/derived-column-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="33429-105">Opções</span><span class="sxs-lookup"><span data-stu-id="33429-105">Options</span></span>  
 <span data-ttu-id="33429-106">**Variáveis e Colunas**</span><span class="sxs-lookup"><span data-stu-id="33429-106">**Variables and Columns**</span></span>  
 <span data-ttu-id="33429-107">Crie uma expressão que use uma variável ou uma coluna de entrada arrastando a variável ou coluna da lista de variáveis e colunas disponíveis para uma linha de tabela existente no painel abaixo, ou para uma linha nova no final da lista.</span><span class="sxs-lookup"><span data-stu-id="33429-107">Build an expression that uses a variable or an input column by dragging the variable or column from the list of available variables and columns to an existing table row in the pane below, or to a new row at the bottom of the list.</span></span>  
  
 <span data-ttu-id="33429-108">**Funções e operadores**</span><span class="sxs-lookup"><span data-stu-id="33429-108">**Functions and Operators**</span></span>  
 <span data-ttu-id="33429-109">Crie uma expressão que use uma função ou um operador para avaliar dados de entrada e dados de saída diretos arrastando funções e operadores da lista para o painel abaixo.</span><span class="sxs-lookup"><span data-stu-id="33429-109">Build an expression that uses a function or an operator to evaluate input data and direct output data by dragging functions and operators from the list to the pane below.</span></span>  
  
 <span data-ttu-id="33429-110">**Nome da coluna derivada**</span><span class="sxs-lookup"><span data-stu-id="33429-110">**Derived Column Name**</span></span>  
 <span data-ttu-id="33429-111">Forneça um nome de coluna derivada.</span><span class="sxs-lookup"><span data-stu-id="33429-111">Provide a derived column name.</span></span> <span data-ttu-id="33429-112">O padrão é uma lista numerada de colunas derivadas; no entanto, é possível escolher qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="33429-112">The default is a numbered list of derived columns; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="33429-113">**Coluna Derivada**</span><span class="sxs-lookup"><span data-stu-id="33429-113">**Derived Column**</span></span>  
 <span data-ttu-id="33429-114">Selecione uma coluna derivada da lista.</span><span class="sxs-lookup"><span data-stu-id="33429-114">Select a derived column from the list.</span></span> <span data-ttu-id="33429-115">Escolha se deseja adicionar a coluna derivada como uma nova coluna de saída ou substituir os dados em uma coluna existente.</span><span class="sxs-lookup"><span data-stu-id="33429-115">Choose whether to add the derived column as a new output column, or to replace the data in an existing column.</span></span>  
  
 <span data-ttu-id="33429-116">**Expression**</span><span class="sxs-lookup"><span data-stu-id="33429-116">**Expression**</span></span>  
 <span data-ttu-id="33429-117">Digite uma expressão ou compile uma arrastando da lista anterior de colunas, variáveis, funções e operadores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="33429-117">Type an expression or build one by dragging from the previous list of available columns, variables, functions, and operators.</span></span>  
  
 <span data-ttu-id="33429-118">O valor dessa propriedade pode ser especificado com uma expressão de propriedades.</span><span class="sxs-lookup"><span data-stu-id="33429-118">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="33429-119">**Tópicos relacionados**: [Expressões do Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md), [Operadores &#40;Expressão SSIS&#41;](expressions/operators-ssis-expression.md) e [Funções &#40;Expressão SSIS&#41;](expressions/functions-ssis-expression.md)</span><span class="sxs-lookup"><span data-stu-id="33429-119">**Related topics**: [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md), [Operators &#40;SSIS Expression&#41;](expressions/operators-ssis-expression.md), and [Functions &#40;SSIS Expression&#41;](expressions/functions-ssis-expression.md)</span></span>  
  
 <span data-ttu-id="33429-120">**Tipo de Dados**</span><span class="sxs-lookup"><span data-stu-id="33429-120">**Data Type**</span></span>  
 <span data-ttu-id="33429-121">Se acrescentar dados a uma nova coluna, a caixa de diálogo **TransformationEditor de Coluna Derivada** avaliará a expressão automaticamente e definirá o tipo de dados adequadamente.</span><span class="sxs-lookup"><span data-stu-id="33429-121">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically evaluates the expression and sets the data type appropriately.</span></span> <span data-ttu-id="33429-122">O valor desta coluna é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="33429-122">The value of this column is read-only.</span></span> <span data-ttu-id="33429-123">Para obter mais informações, consulte [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="33429-123">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="33429-124">**Comprimento**</span><span class="sxs-lookup"><span data-stu-id="33429-124">**Length**</span></span>  
 <span data-ttu-id="33429-125">Se acrescentar dados a uma nova coluna, a caixa de diálogo **TransformationEditor de Coluna Derivada** avaliará a expressão automaticamente e definirá a largura de coluna para os dados da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="33429-125">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically evaluates the expression and sets the column length for string data.</span></span> <span data-ttu-id="33429-126">O valor desta coluna é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="33429-126">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="33429-127">**Precisão**</span><span class="sxs-lookup"><span data-stu-id="33429-127">**Precision**</span></span>  
 <span data-ttu-id="33429-128">Se acrescentar dados a uma nova coluna, a caixa de diálogo **TransformationEditor de Coluna Derivada** automaticamente definirá a precisão de dados numéricos com base no tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="33429-128">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets the precision for numeric data based on the data type.</span></span> <span data-ttu-id="33429-129">O valor desta coluna é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="33429-129">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="33429-130">**Escala**</span><span class="sxs-lookup"><span data-stu-id="33429-130">**Scale**</span></span>  
 <span data-ttu-id="33429-131">Se acrescentar dados a uma nova coluna, a caixa de diálogo **TransformationEditor de Coluna Derivada** automaticamente definirá a escala dos dados numéricos com base no tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="33429-131">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets the scale for numeric data based on the data type.</span></span> <span data-ttu-id="33429-132">O valor desta coluna é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="33429-132">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="33429-133">**Página de código**</span><span class="sxs-lookup"><span data-stu-id="33429-133">**Code Page**</span></span>  
 <span data-ttu-id="33429-134">Se acrescentar dados a uma nova coluna, a caixa de diálogo **TransformationEditor de Coluna Derivada** automaticamente definirá a página de código para o tipo de dados DT_STR.</span><span class="sxs-lookup"><span data-stu-id="33429-134">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets code page for the DT_STR data type.</span></span> <span data-ttu-id="33429-135">Será possível atualizar a **Página de Código**.</span><span class="sxs-lookup"><span data-stu-id="33429-135">You can update **Code Page**.</span></span>  
  
 <span data-ttu-id="33429-136">**Configurar saída de erro**</span><span class="sxs-lookup"><span data-stu-id="33429-136">**Configure error output**</span></span>  
 <span data-ttu-id="33429-137">Especifique como tratar os erros usando a caixa de diálogo [Configurar Saída de Erro](../../2014/integration-services/configure-error-output.md) .</span><span class="sxs-lookup"><span data-stu-id="33429-137">Specify how to handle errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33429-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="33429-138">See Also</span></span>  
 <span data-ttu-id="33429-139">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="33429-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="33429-140">Derivar valores de coluna por meio da transformação Coluna Derivada</span><span class="sxs-lookup"><span data-stu-id="33429-140">Derive Column Values by Using the Derived Column Transformation</span></span>](data-flow/transformations/derive-column-values-by-using-the-derived-column-transformation.md)  
  
  
