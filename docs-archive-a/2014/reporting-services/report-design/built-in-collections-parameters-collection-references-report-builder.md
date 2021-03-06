---
title: Referências de coleções de parâmetros (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c4b47e15-0484-4c13-9182-898db825f01f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 163fe7c93c61088e48d37d0567674d5cee1a79a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683445"
---
# <a name="parameters-collection-references-report-builder-and-ssrs"></a>Referências de coleções de parâmetros (Construtor de Relatórios e SSRS)
  Os parâmetros de relatório são umas das coleções internas que você pode fazer referência a partir de uma expressão. Incluindo parâmetros em uma expressão, é possível personalizar os dados e a aparência do relatório com base nas opções feitas por um usuário. As expressões podem ser usadas para qualquer propriedade de item de relatório ou propriedade de caixa de texto que forneça a opção (*FX*) ou \<**Expression**> . As expressões também são usadas para controlar o conteúdo e a aparência do relatório de outras maneiras. Para obter mais informações, consulte [Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md).  
  
 Quando você compara os valores do parâmetro com os valores do campo do conjunto de dados em tempo de execução, os tipos de dados para os dois itens que você está comparando devem ser os mesmos. Os parâmetros de relatório podem ser de um dos seguintes tipos: Boolean, DateTime, Integer, Float, ou Text, que representa a String de tipo de dados subjacentes. Se necessário, você pode precisar converter o tipo de dados do valor do parâmetro para corresponder ao valor do conjunto de dados. Para obter mais informações, consulte [Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md).  
  
 Para incluir uma referência de parâmetro em uma expressão, você deve entender como especificar a sintaxe correta para a referência de parâmetro que varia, dependendo de se o parâmetro tem diversos valores ou um valor único.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="using-a-single-valued-parameter-in-an-expression"></a><a name="Single"></a> Usando um parâmetro de valor único em uma expressão  
 A tabela a seguir mostra exemplos da sintaxe a ser usada ao incluir uma referência a um parâmetro de valor único de qualquer tipo de dados em uma expressão.  
  
|Exemplo|DESCRIÇÃO|  
|-------------|-----------------|  
|`=Parameters!` *\<ParameterName>* `.IsMultiValue`|Retorna `False`.<br /><br /> Verifica se um parâmetro é de diversos valores. Se `True` , o parâmetro é de vários valores e é uma coleção de objetos. Se `False` , o parâmetro é de valor único e é um único objeto.|  
|`=Parameters!` *\<ParameterName>* `.Count`|Retorna um valor inteiro 1. Para um parâmetro de valor único, a contagem é sempre 1.|  
|`=Parameters!` *\<ParameterName>* `.Label`|Retorna o rótulo do parâmetro, geralmente usado como o nome para exibição em uma lista suspensa de valores disponíveis.|  
|`=Parameters!` *\<ParameterName>* `.Value`|Retorna o valor de parâmetro. Se a propriedade Label não tiver sido definida, este valor será exibido na lista suspensa de valores disponíveis.|  
|`=CStr(Parameters!`  *\<ParameterName>* `.Value)`|Retorna o valor de parâmetro como uma cadeia de caracteres.|  
|`=Fields(Parameters!` *\<ParameterName>* `.Value).Value`|Retorna o valor para o campo que tem o mesmo nome do parâmetro.|  
  
 Para obter mais informações sobre como usar parâmetros em um filtro, consulte [Adicionar filtros de conjunto de dados, de região de dados e de grupo &#40;Construtor de Relatórios e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md).  
  
##  <a name="using-a-multivalue-parameter-in-an-expression"></a><a name="Multi"></a> Usando um parâmetro de diversos valores em uma expressão  
 A tabela a seguir mostra exemplos da sintaxe a ser usada ao incluir uma referência a um parâmetro de diversos valores de qualquer tipo de dados em uma expressão.  
  
|Exemplo|DESCRIÇÃO|  
|-------------|-----------------|  
|`=Parameters!` *\<MultivalueParameterName>* `.IsMultiValue`|Retorna `True` ou `False`.<br /><br /> Verifica se um parâmetro é de diversos valores. Se for `True`, o parâmetro é de diversos valores e é uma coleção de objetos. Se for `False`, o parâmetro é de valor único e é um único objeto.|  
|`=Parameters!` *\<MultivalueParameterName>* `.Count`|Retorna um valor inteiro.<br /><br /> Refere-se ao número de valores. Para um parâmetro de valor único, a contagem é sempre 1. Para um parâmetro de diversos valores, a contagem é 0 ou mais.|  
|`=Parameters!` *\<MultivalueParameterName>* `.Value(0)`|Retorna o primeiro valor em um parâmetro de diversos valores.|  
|`=Parameters!` *\<MultivalueParameterName>* `.Value(Parameters!` *\<MultivalueParameterName>* `.Count-1)`|Retorna o último valor em um parâmetro de diversos valores.|  
|`=Split("Value1,Value2,Value3",",")`|Retorna uma matriz de valores.<br /><br /> Crie uma matriz de valores para um parâmetro `String` de diversos valores. Você pode usar qualquer delimitador no segundo parâmetro para Divisão. Esta expressão pode ser usada para definir padrões para um parâmetro de diversos valores ou para criar um parâmetro de diversos valores para ser enviado a um sub-relatório ou relatório detalhado.|  
|`=Join(Parameters!` *\<MultivalueParameterName>* `.Value,", ")`|Retorna `String` que é composta por uma lista de valores delimitada por vírgulas em um parâmetro de vários valores. Você pode usar qualquer delimitador no segundo parâmetro para Unir.|  
  
 Para obter mais informações sobre como usar parâmetros em um filtro, consulte [Parâmetros de relatório &#40;Construtor de Relatórios e Designer de Relatórios&#41;](report-parameters-report-builder-and-report-designer.md).  
  
## <a name="see-also"></a>Consulte Também  
 [Expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md)   
 [Filtros geralmente usados &#40;Construtor de Relatórios e SSRS&#41;](commonly-used-filters-report-builder-and-ssrs.md)   
 [Adicionar, alterar ou excluir um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md)   
 [Tutorial: Adicionar um parâmetro ao relatório &#40;Construtor de Relatórios&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md)   
 [TUTORIAIS &#40;Construtor de Relatórios&#41;](../report-builder-tutorials.md)   
 [Coleções internas em expressões &#40;Construtor de Relatórios e SSRS&#41;](built-in-collections-in-expressions-report-builder.md)  
  
  
