---
title: Usar funções de agregação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- aggregate functions [Analysis Services]
ms.assetid: c42166ef-b75c-45f4-859c-09a3e9617664
author: minewiskan
ms.author: owend
ms.openlocfilehash: 83cdc571019cffd8ae99e00f119541736c6f503b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575406"
---
# <a name="use-aggregate-functions"></a><span data-ttu-id="d21dc-102">Usar funções de agregação</span><span class="sxs-lookup"><span data-stu-id="d21dc-102">Use Aggregate Functions</span></span>
  <span data-ttu-id="d21dc-103">Quando uma dimensão é usada para fatiar uma medida, a medida é resumida juntamente com hierarquias contidas nessa dimensão.</span><span class="sxs-lookup"><span data-stu-id="d21dc-103">When a dimension is used to slice a measure, the measure is summarized along the hierarchies contained in that dimension.</span></span> <span data-ttu-id="d21dc-104">O comportamento da soma depende da função de agregação especificada para a medida.</span><span class="sxs-lookup"><span data-stu-id="d21dc-104">The summation behavior depends on the aggregate function specified for the measure.</span></span> <span data-ttu-id="d21dc-105">Para mais medidas contendo dados numéricos, a função de agregação é `Sum`.</span><span class="sxs-lookup"><span data-stu-id="d21dc-105">For most measures containing numeric data, the aggregate function is `Sum`.</span></span> <span data-ttu-id="d21dc-106">O valor da medida totalizará valores diferentes, dependendo de qual nível da hierarquia está ativo.</span><span class="sxs-lookup"><span data-stu-id="d21dc-106">The value of the measure will sum to different amounts depending on which level of the hierarchy is active.</span></span>  
  
 <span data-ttu-id="d21dc-107">No Analysis Services, cada medida que você cria é apoiada por uma função de agregação que determina a operação da medida.</span><span class="sxs-lookup"><span data-stu-id="d21dc-107">In Analysis Services, every measure that you create is backed by an aggregation function that determines the measure's operation.</span></span> <span data-ttu-id="d21dc-108">Os tipos de agregação predefinidos incluem `Sum` ,, `Min` , a `Max` `Count` **contagem distinta**e várias outras funções mais especializadas.</span><span class="sxs-lookup"><span data-stu-id="d21dc-108">Predefined aggregation types include `Sum`, `Min`, `Max`, `Count`, **Distinct Count**, and several other more specialized functions.</span></span> <span data-ttu-id="d21dc-109">Como alternativa, se você precisar de agregações com base em fórmulas complexas ou personalizadas, poderá criar um cálculo de MDX em vez de usar uma função de agregação pré-compilada.</span><span class="sxs-lookup"><span data-stu-id="d21dc-109">Alternatively, if you require aggregations based on complex or custom formulas, you can build an MDX calculation in lieu of using a prebuilt aggregation function.</span></span> <span data-ttu-id="d21dc-110">Por exemplo, se você quiser definir uma medida para um valor de porcentagem, faria isso no MDX, usando uma medida calculada.</span><span class="sxs-lookup"><span data-stu-id="d21dc-110">For example, if you want to define a measure for a percentage value, you would do that in MDX, using a calculated measure.</span></span> <span data-ttu-id="d21dc-111">Consulte [Instrução CREATE MEMBER &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member).</span><span class="sxs-lookup"><span data-stu-id="d21dc-111">See [CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member).</span></span>  
  
 <span data-ttu-id="d21dc-112">Medidas criadas por meio do Assistente de cubo são atribuídas a um tipo de agregação como parte da definição da medida.</span><span class="sxs-lookup"><span data-stu-id="d21dc-112">Measures that are created via the Cube Wizard are assigned an aggregation type as part of the measure definition.</span></span> <span data-ttu-id="d21dc-113">O tipo de agregação é sempre `Sum`, supondo que a coluna de origem contém dados numéricos.</span><span class="sxs-lookup"><span data-stu-id="d21dc-113">The aggregation type is always `Sum`, assuming the source column contains numeric data.</span></span> <span data-ttu-id="d21dc-114">`Sum` é atribuída, independentemente do tipo de dados da coluna de origem.</span><span class="sxs-lookup"><span data-stu-id="d21dc-114">`Sum` is assigned regardless of the source column's data type.</span></span> <span data-ttu-id="d21dc-115">Por exemplo, se você tiver usado o Assistente de cubo para criar medidas e preenchido todas as colunas por meio de uma tabela de fatos, notará que todas as medidas resultantes têm uma agregação de `Sum`, mesmo que a origem seja uma coluna de data e hora.</span><span class="sxs-lookup"><span data-stu-id="d21dc-115">For example, if you used the Cube Wizard to create measures, and you pulled in all columns from a fact table, you will notice that all of the resulting measures have an aggregation of `Sum`, even if the source is a date time column.</span></span> <span data-ttu-id="d21dc-116">Sempre examine os métodos de agregação pré-atribuídos para medidas criadas por meio do assistente para se certificar de que a função de agregação seja adequada.</span><span class="sxs-lookup"><span data-stu-id="d21dc-116">Always review the pre-assigned aggregation methods for measures created via the wizard to make sure the aggregation function is suitable.</span></span>  
  
 <span data-ttu-id="d21dc-117">Você pode atribuir ou alterar o método de agregação na definição do cubo, por meio de [!INCLUDE[ss_dtbi](../../includes/ss-dtbi-md.md)]ou por meio do MDX.</span><span class="sxs-lookup"><span data-stu-id="d21dc-117">You can assign or change the aggregation method in the either the cube definition, via [!INCLUDE[ss_dtbi](../../includes/ss-dtbi-md.md)], or via MDX.</span></span> <span data-ttu-id="d21dc-118">Consulte [Criar medidas e grupos de medidas em modelos multidimensionais](create-measures-and-measure-groups-in-multidimensional-models.md) ou [Agregação &#40;MDX&#41;](/sql/mdx/aggregate-mdx) para obter mais instruções.</span><span class="sxs-lookup"><span data-stu-id="d21dc-118">See [Create Measures and Measure Groups in Multidimensional Models](create-measures-and-measure-groups-in-multidimensional-models.md) or [Aggregate &#40;MDX&#41;](/sql/mdx/aggregate-mdx) for further instructions.</span></span>  
  
##  <a name="aggregate-functions"></a><a name="AggFunction"></a><span data-ttu-id="d21dc-119">Funções de agregação</span><span class="sxs-lookup"><span data-stu-id="d21dc-119">Aggregate Functions</span></span>  
 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="d21dc-120">fornece funções para agregar medidas às dimensões contidas em grupos de medidas.</span><span class="sxs-lookup"><span data-stu-id="d21dc-120">provides functions to aggregate measures along the dimensions that are contained in measure groups.</span></span> <span data-ttu-id="d21dc-121">A *capacidade aditiva* de uma função de agregação determina como a medida é agregada entre todas as dimensões no cubo.</span><span class="sxs-lookup"><span data-stu-id="d21dc-121">The *additivity* of an aggregation function determines how the measure is aggregated across all the dimensions in the cube.</span></span> <span data-ttu-id="d21dc-122">As funções de agregação enquadram-se em três níveis de capacidade aditiva:</span><span class="sxs-lookup"><span data-stu-id="d21dc-122">Aggregation functions fall into three levels of additivity:</span></span>  
  
 <span data-ttu-id="d21dc-123">Aditiva</span><span class="sxs-lookup"><span data-stu-id="d21dc-123">Additive</span></span>  
 <span data-ttu-id="d21dc-124">Uma medida aditiva, também chamada de medida totalmente aditiva, pode ser agregada a todas as dimensões incluídas no grupo de medidas que contém a medida, sem restrição.</span><span class="sxs-lookup"><span data-stu-id="d21dc-124">An additive measure, also called a fully additive measure, can be aggregated along all the dimensions that are included in the measure group that contains the measure, without restriction.</span></span>  
  
 <span data-ttu-id="d21dc-125">Semiaditiva</span><span class="sxs-lookup"><span data-stu-id="d21dc-125">Semiadditive</span></span>  
 <span data-ttu-id="d21dc-126">Uma medida semiaditiva pode ser agregada a algumas das dimensões, mas não a todas, incluídas no grupo de medidas que contém a medida.</span><span class="sxs-lookup"><span data-stu-id="d21dc-126">A semiadditive measure can be aggregated along some, but not all, dimensions that are included in the measure group that contains the measure.</span></span> <span data-ttu-id="d21dc-127">Por exemplo, uma medida que representa a quantidade disponível em estoque pode ser agregada à dimensão geográfica para produzir a quantidade total disponível para todos os armazéns, mas a medida não pode ser agregada a uma dimensão de tempo porque ela representa um instantâneo periódico de quantidades disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d21dc-127">For example, a measure that represents the quantity available for inventory can be aggregated along a geography dimension to produce a total quantity available for all warehouses, but the measure cannot be aggregated along a time dimension because the measure represents a periodic snapshot of quantities available.</span></span> <span data-ttu-id="d21dc-128">Agregar essa medida a uma dimensão de tempo produziria resultados incorretos.</span><span class="sxs-lookup"><span data-stu-id="d21dc-128">Aggregating such a measure along a time dimension would produce incorrect results.</span></span> <span data-ttu-id="d21dc-129">Consulte [Definir comportamento semiaditivo](define-semiadditive-behavior.md) para ver os detalhes.</span><span class="sxs-lookup"><span data-stu-id="d21dc-129">See [Define Semiadditive Behavior](define-semiadditive-behavior.md) for details.</span></span>  
  
 <span data-ttu-id="d21dc-130">Não aditiva</span><span class="sxs-lookup"><span data-stu-id="d21dc-130">Nonadditive</span></span>  
 <span data-ttu-id="d21dc-131">Uma medida não aditiva não pode ser agregada a nenhuma das dimensões incluídas no grupo de medidas que contém a medida.</span><span class="sxs-lookup"><span data-stu-id="d21dc-131">A nonadditive measure cannot be aggregated along any dimension in the measure group that contains the measure.</span></span> <span data-ttu-id="d21dc-132">Em vez disso, ela deve ser calculada individualmente para cada célula do cubo que representa a medida.</span><span class="sxs-lookup"><span data-stu-id="d21dc-132">Instead, the measure must be individually calculated for each cell in the cube that represents the measure.</span></span> <span data-ttu-id="d21dc-133">Por exemplo, uma medida calculada que retorna uma porcentagem, como margem de lucro, não pode ser agregada a partir dos valores de porcentagem de membros filho de qualquer dimensão.</span><span class="sxs-lookup"><span data-stu-id="d21dc-133">For example, a calculated measure that returns a percentage, such as profit margin, cannot be aggregated from the percentage values of child members in any dimension.</span></span>  
  
 <span data-ttu-id="d21dc-134">A tabela a seguir lista as funções de agregação do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]e descreve a capacidade aditiva e a saída prevista da função.</span><span class="sxs-lookup"><span data-stu-id="d21dc-134">The following table lists the aggregation functions in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], and describes both the additivity and expected output of the function.</span></span>  
  
|<span data-ttu-id="d21dc-135">Função de agregação</span><span class="sxs-lookup"><span data-stu-id="d21dc-135">Aggregation function</span></span>|<span data-ttu-id="d21dc-136">capacidade aditiva</span><span class="sxs-lookup"><span data-stu-id="d21dc-136">Additivity</span></span>|<span data-ttu-id="d21dc-137">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="d21dc-137">Returned value</span></span>|  
|--------------------------|----------------|--------------------|  
|`Sum`|<span data-ttu-id="d21dc-138">Aditiva</span><span class="sxs-lookup"><span data-stu-id="d21dc-138">Additive</span></span>|<span data-ttu-id="d21dc-139">Calcula a soma de valores de todos os membros filho.</span><span class="sxs-lookup"><span data-stu-id="d21dc-139">Calculates the sum of values for all child members.</span></span> <span data-ttu-id="d21dc-140">Essa é a função de agregação padrão.</span><span class="sxs-lookup"><span data-stu-id="d21dc-140">This is the default aggregation function.</span></span>|  
|`Count`|<span data-ttu-id="d21dc-141">Aditiva</span><span class="sxs-lookup"><span data-stu-id="d21dc-141">Additive</span></span>|<span data-ttu-id="d21dc-142">Recupera a contagem de todos os membros filho.</span><span class="sxs-lookup"><span data-stu-id="d21dc-142">Retrieves the count of all child members.</span></span>|  
|`Min`|<span data-ttu-id="d21dc-143">Semiaditiva</span><span class="sxs-lookup"><span data-stu-id="d21dc-143">Semiadditive</span></span>|<span data-ttu-id="d21dc-144">Recupera o valor mais baixo de todos os membros filho.</span><span class="sxs-lookup"><span data-stu-id="d21dc-144">Retrieves the lowest value for all child members.</span></span>|  
|`Max`|<span data-ttu-id="d21dc-145">Semiaditiva</span><span class="sxs-lookup"><span data-stu-id="d21dc-145">Semiadditive</span></span>|<span data-ttu-id="d21dc-146">Recupera o valor mais alto de todos os membros filho.</span><span class="sxs-lookup"><span data-stu-id="d21dc-146">Retrieves the highest value for all child members.</span></span>|  
|`DistinctCount`|<span data-ttu-id="d21dc-147">Não aditiva</span><span class="sxs-lookup"><span data-stu-id="d21dc-147">Nonadditive</span></span>|<span data-ttu-id="d21dc-148">Recupera a contagem de todos os membros filho exclusivos.</span><span class="sxs-lookup"><span data-stu-id="d21dc-148">Retrieves the count of all unique child members.</span></span> <span data-ttu-id="d21dc-149">Para obter mais detalhes, consulte [Sobre medidas de contagem distintas](use-aggregate-functions.md#bkmk_distinct) na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="d21dc-149">For more details, see [About Distinct Count Measures](use-aggregate-functions.md#bkmk_distinct) in the next section.</span></span>|  
|`None`|<span data-ttu-id="d21dc-150">Não aditiva</span><span class="sxs-lookup"><span data-stu-id="d21dc-150">Nonadditive</span></span>|<span data-ttu-id="d21dc-151">Nenhuma agregação é executada e todos os valores de membros folha e não folha de uma dimensão são fornecidos diretamente da tabela de fatos para o grupo de medidas que contém a medida.</span><span class="sxs-lookup"><span data-stu-id="d21dc-151">No aggregation is performed, and all values for leaf and nonleaf members in a dimension are supplied directly from the fact table for the measure group that contains the measure.</span></span> <span data-ttu-id="d21dc-152">Se não for possível ler um valor da tabela de fatos para um membro, o valor desse membro será definido como nulo.</span><span class="sxs-lookup"><span data-stu-id="d21dc-152">If no value can be read from the fact table for a member, the value for that member is set to null.</span></span>|  
|`ByAccount`|<span data-ttu-id="d21dc-153">Semiaditiva</span><span class="sxs-lookup"><span data-stu-id="d21dc-153">Semiadditive</span></span>|<span data-ttu-id="d21dc-154">Calcula a agregação de acordo com a função de agregação atribuída ao tipo de conta de um membro em uma dimensão de conta.</span><span class="sxs-lookup"><span data-stu-id="d21dc-154">Calculates the aggregation according to the aggregation function assigned to the account type for a member in an account dimension.</span></span> <span data-ttu-id="d21dc-155">Se não existir uma dimensão de tipo de conta no grupo de medidas, é tratada como a função de agregação `None`.</span><span class="sxs-lookup"><span data-stu-id="d21dc-155">If no account type dimension exists in the measure group, treated as the `None` aggregation function.</span></span><br /><br /> <span data-ttu-id="d21dc-156">Para obter mais informações sobre dimensões de conta, consulte [Criar uma Conta de Finanças de dimensão de tipo pai-filho](database-dimensions-finance-account-of-parent-child-type.md).</span><span class="sxs-lookup"><span data-stu-id="d21dc-156">For more information about account dimensions, see [Create a Finance Account of parent-child type Dimension](database-dimensions-finance-account-of-parent-child-type.md).</span></span>|  
|`AverageOfChildren`|<span data-ttu-id="d21dc-157">Semiaditiva</span><span class="sxs-lookup"><span data-stu-id="d21dc-157">Semiadditive</span></span>|<span data-ttu-id="d21dc-158">Calcula a média de valores de todos os membros filho não vazios.</span><span class="sxs-lookup"><span data-stu-id="d21dc-158">Calculates the average of values for all non-empty child members.</span></span>|  
|`FirstChild`|<span data-ttu-id="d21dc-159">Semiaditiva</span><span class="sxs-lookup"><span data-stu-id="d21dc-159">Semiadditive</span></span>|<span data-ttu-id="d21dc-160">Recupera o valor do primeiro membro filho.</span><span class="sxs-lookup"><span data-stu-id="d21dc-160">Retrieves the value of the first child member.</span></span>|  
|`LastChild`|<span data-ttu-id="d21dc-161">Semiaditiva</span><span class="sxs-lookup"><span data-stu-id="d21dc-161">Semiadditive</span></span>|<span data-ttu-id="d21dc-162">Recupera o valor do último membro filho.</span><span class="sxs-lookup"><span data-stu-id="d21dc-162">Retrieves the value of the last child member.</span></span>|  
|`FirstNonEmpty`|<span data-ttu-id="d21dc-163">Semiaditiva</span><span class="sxs-lookup"><span data-stu-id="d21dc-163">Semiadditive</span></span>|<span data-ttu-id="d21dc-164">Recupera o valor do primeiro membro filho não vazio.</span><span class="sxs-lookup"><span data-stu-id="d21dc-164">Retrieves the value of the first non-empty child member.</span></span>|  
|`LastNonEmpty`|<span data-ttu-id="d21dc-165">Semiaditiva</span><span class="sxs-lookup"><span data-stu-id="d21dc-165">Semiadditive</span></span>|<span data-ttu-id="d21dc-166">Recupera o valor do último membro filho não vazio.</span><span class="sxs-lookup"><span data-stu-id="d21dc-166">Retrieves the value of the last non-empty child member.</span></span>|  
  
##  <a name="about-distinct-count-measures"></a><a name="bkmk_distinct"></a> <span data-ttu-id="d21dc-167">Sobre medidas de contagem distintas</span><span class="sxs-lookup"><span data-stu-id="d21dc-167">About Distinct Count Measures</span></span>  
 <span data-ttu-id="d21dc-168">Uma medida com o valor da propriedade **Função Aggregate** de **Contagem Distinta** é chamada de medida de contagem distinta.</span><span class="sxs-lookup"><span data-stu-id="d21dc-168">A measure with an **Aggregate Function** property value of **Distinct Count** is called a distinct count measure.</span></span> <span data-ttu-id="d21dc-169">Uma medida de contagem distinta pode ser usada para contar ocorrências dos membros de nível mais baixo de uma dimensão da tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="d21dc-169">A distinct count measure can be used to count occurrences of a dimension's lowest-level members in the fact table.</span></span> <span data-ttu-id="d21dc-170">Como a contagem é distinta, se um membro ocorrer várias vezes, ele será contado apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="d21dc-170">Because the count is distinct, if a member occurs multiple times, it is counted only once.</span></span> <span data-ttu-id="d21dc-171">Uma medida de contagem distinta é sempre colocada em um grupo de medidas dedicado.</span><span class="sxs-lookup"><span data-stu-id="d21dc-171">A distinct count measure is always placed in a dedicated measure group.</span></span> <span data-ttu-id="d21dc-172">Colocar uma medida de contagem distinta em seu próprio grupo de medidas é uma prática recomendada que foi criada no designer como uma técnica de otimização do desempenho.</span><span class="sxs-lookup"><span data-stu-id="d21dc-172">Putting a distinct count measure into its own measure group is a best practice that has been built into the designer as a performance optimization technique.</span></span>  
  
 <span data-ttu-id="d21dc-173">Normalmente, as medidas de contagem distinta são usadas para determinar para cada membro de uma dimensão quantos membros de nível inferior e distintos de outra dimensão compartilham linhas da tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="d21dc-173">Distinct count measures are commonly used to determine for each member of a dimension how many distinct, lowest-level members of another dimension share rows in the fact table.</span></span> <span data-ttu-id="d21dc-174">Por exemplo, em um cubo Vendas, para cada cliente e grupo de clientes, quantos produtos distintos foram comprados?</span><span class="sxs-lookup"><span data-stu-id="d21dc-174">For example, in a Sales cube, for each customer and customer group, how many distinct products were purchased?</span></span> <span data-ttu-id="d21dc-175">(Quer dizer, para cada membro da dimensão Clientes, quantos membros distintos, em nível inferior da dimensão Produtos, compartilham linhas na tabela de fatos?) Por exemplo, em um cubo Visitas ao Site da Internet, para cada visitante de site e grupo de visitantes de site, quantas páginas distintas no site da Internet foram visitadas?</span><span class="sxs-lookup"><span data-stu-id="d21dc-175">(That is, for each member of the Customers dimension, how many distinct, lowest-level members of the Products dimension share rows in the fact table?) Or, for example, in an Internet Site Visits cube, for each site visitor and site visitor group, how many distinct pages on the Internet site were visited?</span></span> <span data-ttu-id="d21dc-176">(Quer dizer, para cada membro da dimensão Visitantes de Site, quantos membros distintos, em nível inferior da dimensão Páginas, compartilham linhas na tabela de fatos?) Em cada um desses exemplos, os membros em nível inferior da segunda dimensão são contados por uma medida de contagem distinta.</span><span class="sxs-lookup"><span data-stu-id="d21dc-176">(That is, for each member of the Site Visitors dimension, how many distinct, lowest-level members of the Pages dimension share rows in the fact table?) In each of these examples, the second dimension's lowest-level members are counted by a distinct count measure.</span></span>  
  
 <span data-ttu-id="d21dc-177">Esse tipo de análise não precisa ser limitada a duas dimensões.</span><span class="sxs-lookup"><span data-stu-id="d21dc-177">This kind of analysis need not be limited to two dimensions.</span></span> <span data-ttu-id="d21dc-178">Na verdade, uma medida de contagem distinta pode ser separada e dividida em qualquer combinação de dimensões do cubo, incluindo dimensões que contêm membros contados.</span><span class="sxs-lookup"><span data-stu-id="d21dc-178">In fact, a distinct count measure can be separated and sliced by any combination of dimensions in the cube, including the dimension that contains the counted members.</span></span>  
  
 <span data-ttu-id="d21dc-179">Uma medida de contagem distinta que conta membros baseia-se m uma coluna de chave estrangeira da tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="d21dc-179">A distinct count measure that counts members is based on a foreign key column in the fact table.</span></span> <span data-ttu-id="d21dc-180">(Ou seja, a propriedade **Source Column** da medida identifica essa coluna.) Essa coluna une a coluna da tabela de dimensões que identifica os membros contados pela medida de contagem distinta.</span><span class="sxs-lookup"><span data-stu-id="d21dc-180">(That is, the measure's **Source Column** property identifies this column.) This column joins the dimension table column that identifies the members counted by the distinct count measure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d21dc-181">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d21dc-181">See Also</span></span>  
 <span data-ttu-id="d21dc-182">[Medidas e grupos de medidas](measures-and-measure-groups.md) </span><span class="sxs-lookup"><span data-stu-id="d21dc-182">[Measures and Measure Groups](measures-and-measure-groups.md) </span></span>  
 <span data-ttu-id="d21dc-183">[Referência de função MDX &#40;&#41;MDX](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="d21dc-183">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 [<span data-ttu-id="d21dc-184">Definir um comportamento semiaditivo</span><span class="sxs-lookup"><span data-stu-id="d21dc-184">Define Semiadditive Behavior</span></span>](define-semiadditive-behavior.md)  
  
  