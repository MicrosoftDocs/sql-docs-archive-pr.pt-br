---
title: Definindo uma relação referenciada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 4a34ba52-e3b3-4e8a-8e55-73e0cd5a97bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7b14699ad098ba8c0931c00a3cbd30a6a8026771
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583219"
---
# <a name="defining-a-referenced-relationship"></a><span data-ttu-id="3a63d-102">Definindo uma relação referenciada</span><span class="sxs-lookup"><span data-stu-id="3a63d-102">Defining a Referenced Relationship</span></span>
  <span data-ttu-id="3a63d-103">Até este ponto no tutorial, cada dimensão de cubo que você definiu teve como base uma tabela que estava diretamente vinculada à tabela de fatos de um grupo de medidas por uma relação de chave primária para chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="3a63d-103">Up to this point in the tutorial, each cube dimension that you defined was based on a table that was directly linked to the fact table for a measure group by a primary key to foreign key relationship.</span></span> <span data-ttu-id="3a63d-104">Nas tarefas deste tópico, você vinculará a dimensão **Geografia** à tabela de fatos para vendas do revendedor por meio da dimensão **Revendedor** , conhecida como *dimensão de referência*.</span><span class="sxs-lookup"><span data-stu-id="3a63d-104">In the tasks in this topic, you link the **Geography** dimension to the fact table for reseller sales through the **Reseller** dimension, which is called a *reference dimension*.</span></span> <span data-ttu-id="3a63d-105">Isso permite aos usuários dimensionar as vendas do revendedor por geografia.</span><span class="sxs-lookup"><span data-stu-id="3a63d-105">This enables users to dimension reseller sales by geography.</span></span> <span data-ttu-id="3a63d-106">Para obter mais informações, consulte [Definir uma relação referenciada e as propriedades da relação referenciada](multidimensional-models/define-a-referenced-relationship-and-referenced-relationship-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3a63d-106">For more information, see [Define a Referenced Relationship and Referenced Relationship Properties](multidimensional-models/define-a-referenced-relationship-and-referenced-relationship-properties.md).</span></span>

## <a name="dimensioning-reseller-sales-by-geography"></a><span data-ttu-id="3a63d-107">Dimensionando as vendas do revendedor por geografia</span><span class="sxs-lookup"><span data-stu-id="3a63d-107">Dimensioning Reseller Sales by Geography</span></span>

1.  <span data-ttu-id="3a63d-108">No Gerenciador de Soluções, clique com o botão direito do mouse em **Tutorial do Analysis Services** na pasta **Cubos** e clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="3a63d-108">In Solution Explorer, right-click **Analysis Services Tutorial** in the **Cubes** folder, and then click **Browse**.</span></span>

2.  <span data-ttu-id="3a63d-109">Remova todas as hierarquias do painel de dados e verifique se a medida **Vendas do Revendedor/Valor das Vendas** é exibida na área de dados do painel de dados.</span><span class="sxs-lookup"><span data-stu-id="3a63d-109">Remove all hierarchies from the data pane, and then verify that the **Reseller Sales-Sales Amount** measure appears in the data area of the data pane.</span></span> <span data-ttu-id="3a63d-110">Adicione-a ao painel de dados caso ela ainda não esteja lá.</span><span class="sxs-lookup"><span data-stu-id="3a63d-110">Add it to the data pane if it is not already there.</span></span>

3.  <span data-ttu-id="3a63d-111">Na dimensão **Geografia** no painel de metadados, arraste a hierarquia definida pelo usuário **Geografias** até a área **Solte os Campos Linha Aqui** do painel de dados.</span><span class="sxs-lookup"><span data-stu-id="3a63d-111">From the **Geography** dimension in the metadata pane, drag the **Geographies** user-defined hierarchy to the **Drop Row Fields Here** area of the data pane.</span></span>

     <span data-ttu-id="3a63d-112">Observe que a medida **Vendas do Revendedor/Valor das Vendas** não foi dimensionada corretamente pelos membros do atributo **País/Região** na hierarquia **Regiões** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-112">Notice that the **Reseller Sales-Sales Amount** measure is not correctly dimensioned by the **Country-Region** attribute members in the **Regions** hierarchy.</span></span> <span data-ttu-id="3a63d-113">O valor de **Vendas do Revendedor/Valor das Vendas** é repetido para cada membro de atributo **País/Região** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-113">The value for **Reseller Sales-Sales Amount** repeats for each **Country-Region** attribute member.</span></span>

     <span data-ttu-id="3a63d-114">![Medida Vendas de Revendedor Dimensionadas-Valor das Vendas](../../2014/tutorials/media/l5-referencedrelationship-1.gif "Medida Vendas de Revendedor Dimensionadas-Valor das Vendas")</span><span class="sxs-lookup"><span data-stu-id="3a63d-114">![Dimensioned Reseller Sales-Sales Amount measure](../../2014/tutorials/media/l5-referencedrelationship-1.gif "Dimensioned Reseller Sales-Sales Amount measure")</span></span>

4.  <span data-ttu-id="3a63d-115">Abra o Designer de Exibição da Fonte de Dados para a exibição da fonte de dados do **Adventure Works DW 2012**</span><span class="sxs-lookup"><span data-stu-id="3a63d-115">Open Data Source View Designer for the **Adventure Works DW 2012** data source view.</span></span>

5.  <span data-ttu-id="3a63d-116">No painel **Organizador de Diagramas** , exiba a relação entre a tabela **Geography** e a tabela **ResellerSales** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-116">In the **Diagram Organizer** pane, view the relationship between the **Geography** table and the **ResellerSales** table.</span></span>

     <span data-ttu-id="3a63d-117">Observe que não há nenhum vínculo direto entre essas tabelas.</span><span class="sxs-lookup"><span data-stu-id="3a63d-117">Notice that there is no direct link between these tables.</span></span> <span data-ttu-id="3a63d-118">No entanto, existe um vínculo indireto entre elas pela tabela **Reseller** ou **SalesTerritory** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-118">However, there is an indirect link between these tables through either the **Reseller** table or the **SalesTerritory** table.</span></span>

6.  <span data-ttu-id="3a63d-119">Clique duas vezes na seta que representa a relação entre a tabela **Geography** e a tabela **Reseller** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-119">Double-click the arrow that represents the relationship between the **Geography** table and the **Reseller** table.</span></span>

     <span data-ttu-id="3a63d-120">Na caixa de diálogo **Editar Relação** , observe que a coluna **GeographyKey** é a chave primária na tabela **Geography** e a chave estrangeira na tabela **Reseller** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-120">In the **Edit Relationship** dialog box, notice that the **GeographyKey** column is the primary key in the **Geography** table and the foreign key in the **Reseller** table.</span></span>

7.  <span data-ttu-id="3a63d-121">Clique em **Cancelar**, mude para o Designer do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e clique na guia **Uso da Dimensão** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-121">Click **Cancel**, switch to Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Dimension Usage** tab.</span></span>

     <span data-ttu-id="3a63d-122">Observe que, neste momento, a dimensão de cubo **Geography** não tem uma relação com os grupos de medidas **Vendas pela Internet** e **Vendas do Revendedor** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-122">Notice that the **Geography** cube dimension does not currently have a relationship with either the **Internet Sales** measure group or the **Reseller Sales** measure group.</span></span>

8.  <span data-ttu-id="3a63d-123">Clique no botão de reticências (**...**) na célula **nome completo** na interseção da dimensão **cliente** e do grupo de medidas **vendas pela Internet** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-123">Click the ellipsis button (**...**) in the **Full Name** cell at the intersection of the **Customer** dimension and the **Internet Sales** measure group.</span></span>

     <span data-ttu-id="3a63d-124">Na caixa de diálogo **Definir Relação** , observe que uma relação **Regular** está definida entre a tabela de dimensões **DimCustomer** e a tabela de grupos de medidas **FactInternetSales** com base na coluna **CustomerKey** de cada uma dessas tabelas.</span><span class="sxs-lookup"><span data-stu-id="3a63d-124">In the **Define Relationship** dialog box, notice that a **Regular** relationship is defined between the **DimCustomer** dimension table and the **FactInternetSales** measure group table based on the **CustomerKey** column in each of these tables.</span></span> <span data-ttu-id="3a63d-125">Todas as relações que você definiu dentro deste tutorial até este momento foram relações regulares.</span><span class="sxs-lookup"><span data-stu-id="3a63d-125">All the relationships that you have defined within this tutorial up to this point have been regular relationships.</span></span>

     <span data-ttu-id="3a63d-126">A imagem a seguir mostra a caixa de diálogo **Definir Relação** com uma relação normal entre a tabela de dimensões **DimCustomer** e a tabela de grupos de medidas **FactInternetSales** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-126">The following image shows the **Define Relationship** dialog box with a regular relationship between the **DimCustomer** dimension table and the **FactInternetSales** measure group table.</span></span>

     <span data-ttu-id="3a63d-127">![Caixa de diálogo Definir Relação](../../2014/tutorials/media/l5-referencedrelationship-4.gif "Caixa de diálogo Definir Relação")</span><span class="sxs-lookup"><span data-stu-id="3a63d-127">![Define Relationship dialog box](../../2014/tutorials/media/l5-referencedrelationship-4.gif "Define Relationship dialog box")</span></span>

9. <span data-ttu-id="3a63d-128">Clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="3a63d-128">Click **Cancel**.</span></span>

10. <span data-ttu-id="3a63d-129">Clique no botão de reticências (**...**) na célula sem nome na interseção da dimensão **geografia** e no grupo de medidas **vendas do revendedor** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-129">Click the ellipsis button (**...**) in the unnamed cell at the intersection of the **Geography** dimension and the **Reseller Sales** measure group.</span></span>

     <span data-ttu-id="3a63d-130">Na caixa de diálogo **Definir Relação** , observe que não há relações definidas entre a dimensão de cubo Geografia e o grupo de medidas Vendas do Revendedor.</span><span class="sxs-lookup"><span data-stu-id="3a63d-130">In the **Define Relationship** dialog box, notice that no relationship is currently defined between the Geography cube dimension and the Reseller Sales measure group.</span></span> <span data-ttu-id="3a63d-131">Não é possível definir uma relação regular porque não há uma relação direta entre a tabela de dimensões da dimensão Geografia e a tabela de fatos do grupo de medidas Vendas do Revendedor.</span><span class="sxs-lookup"><span data-stu-id="3a63d-131">You cannot define a regular relationship because there is no direct relationship between the dimension table for the Geography dimension and the fact table for the Reseller Sales measure group.</span></span>

11. <span data-ttu-id="3a63d-132">Na lista **Selecionar tipo de relação** , selecione **Referenciada**.</span><span class="sxs-lookup"><span data-stu-id="3a63d-132">In the **Select relationship type** list, select **Referenced**.</span></span>

     <span data-ttu-id="3a63d-133">Uma relação referenciada é definida pela especificação de uma dimensão conectada diretamente à tabela de grupos de medidas, chamada *dimensão intermediária*, que pode ser usada pelo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] para vincular a dimensão de referência à tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="3a63d-133">You define a referenced relationship by specifying a dimension that is directly connected to the measure group table, called an *intermediate dimension*, that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] can use to link the reference dimension to the fact table.</span></span> <span data-ttu-id="3a63d-134">Em seguida, você especifica o atributo que vincula a dimensão de referência à dimensão intermediária.</span><span class="sxs-lookup"><span data-stu-id="3a63d-134">You then specify the attribute that links the reference dimension to the intermediate dimension.</span></span>

12. <span data-ttu-id="3a63d-135">Na lista **Dimensão intermediária** , selecione **Revendedor**.</span><span class="sxs-lookup"><span data-stu-id="3a63d-135">In the **Intermediate dimension** list, select **Reseller**.</span></span>

     <span data-ttu-id="3a63d-136">A tabela subjacente da dimensão Geografia é vinculada à tabela de fatos através da tabela subjacente da dimensão Revendedor.</span><span class="sxs-lookup"><span data-stu-id="3a63d-136">The underlying table for the Geography dimension is linked to the fact table through the underlying table for the Reseller dimension.</span></span>

13. <span data-ttu-id="3a63d-137">Na lista **Atributo de dimensão de referência** , selecione **Chave de Geografia**e tente selecionar **Chave de Geografia** na lista **Atributo de dimensão intermediária** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-137">In the **Reference dimension attribute** list, select **Geography Key**, and then try to select **Geography Key** in the **Intermediate dimension attribute** list.</span></span>

     <span data-ttu-id="3a63d-138">Observe que **Chave de Geografia** não é exibido na lista **Atributo de dimensão intermediária** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-138">Notice that **Geography Key** does not appear in the **Intermediate dimension attribute** list.</span></span> <span data-ttu-id="3a63d-139">Isso ocorre porque a coluna **GeographyKey** não está definida como um atributo na dimensão **Revendedor** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-139">This is because the **GeographyKey** column is not defined as an attribute in the **Reseller** dimension.</span></span>

14. <span data-ttu-id="3a63d-140">Clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="3a63d-140">Click **Cancel**.</span></span>

 <span data-ttu-id="3a63d-141">Na próxima tarefa, você solucionará esse problema definindo um atributo que se baseia na coluna GeographyKey da dimensão Revendedor.</span><span class="sxs-lookup"><span data-stu-id="3a63d-141">In the next task, you will solve this problem by defining an attribute that is based on the GeographyKey column in the Reseller dimension.</span></span>

## <a name="defining-the-intermediate-dimension-attribute-and-the-referenced-dimension-relationship"></a><span data-ttu-id="3a63d-142">Definindo o atributo de dimensão intermediária e a relação de dimensão referenciada</span><span class="sxs-lookup"><span data-stu-id="3a63d-142">Defining the Intermediate Dimension Attribute and the Referenced Dimension Relationship</span></span>

1.  <span data-ttu-id="3a63d-143">Abra o Designer de Dimensão na dimensão **Revendedor** e exiba as colunas da tabela **Revendedor** no painel **Exibição da Fonte de Dados** . Em seguida, exiba os atributos definidos na dimensão **Revendedor** no painel **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-143">Open Dimension Designer for the **Reseller** dimension, and view the columns in the **Reseller** table in the **Data Source View** pane, and view the defined attributes in the **Reseller** dimension in the **Attributes** pane.</span></span>

     <span data-ttu-id="3a63d-144">Observe que, embora a GeographyKey esteja definida como uma coluna na tabela Revendedor, nenhum atributo de dimensão está definido na dimensão Revendedor com base nessa coluna.</span><span class="sxs-lookup"><span data-stu-id="3a63d-144">Notice that although GeographyKey is defined as a column in the Reseller table, no dimension attribute is defined in the Reseller dimension based on this column.</span></span> <span data-ttu-id="3a63d-145">A Geografia é definida como um atributo de dimensão na dimensão Geografia porque ela é a coluna principal que vincula a tabela subjacente daquela dimensão à tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="3a63d-145">Geography is defined as a dimension attribute in the Geography dimension because it is the key column that links the underlying table for that dimension to the fact table.</span></span>

2.  <span data-ttu-id="3a63d-146">Para adicionar um atributo **Geografia Principal** à dimensão **Revendedor** , clique com o botão direito do mouse em **GeographyKey** no painel **Exibição da Fonte de Dados** e clique em **Novo Atributo da Coluna**.</span><span class="sxs-lookup"><span data-stu-id="3a63d-146">To add a **Geography Key** attribute to the **Reseller** dimension, right-click **GeographyKey** in the **Data Source View** pane, and then click **New Attribute from Column**.</span></span>

3.  <span data-ttu-id="3a63d-147">No painel **Atributos** , selecione **Chave de Geografia**. Na janela Propriedades, defina a propriedade **AttributeHierarchyOptimizedState** como **NotOptimized**, a propriedade **AttributeHierarchyOrdered** como **False**e a propriedade **AttributeHierarchyVisible** como **False**.</span><span class="sxs-lookup"><span data-stu-id="3a63d-147">In the **Attributes** pane, select **Geography Key**, and then, in the Properties window, set the **AttributeHierarchyOptimizedState** property to **NotOptimized**, the **AttributeHierarchyOrdered** property to **False**, and the **AttributeHierarchyVisible** property to **False.**</span></span>

     <span data-ttu-id="3a63d-148">O atributo Geografia Principal na dimensão Revendedor será usado apenas para vincular a dimensão Geografia à tabela de fatos Vendas do Revendedor.</span><span class="sxs-lookup"><span data-stu-id="3a63d-148">The Geography Key attribute in the Reseller dimension will only be used to link the Geography dimension to the Reseller Sales fact table.</span></span> <span data-ttu-id="3a63d-149">Como ele não será usado para pesquisa, não há valores ao definir essa hierarquia de atributo como visível.</span><span class="sxs-lookup"><span data-stu-id="3a63d-149">Because it will not be used for browsing, there is no value in defining this attribute hierarchy as visible.</span></span> <span data-ttu-id="3a63d-150">Além disso, ordenar e otimizar a hierarquia de atributo afetará negativamente o desempenho do processamento.</span><span class="sxs-lookup"><span data-stu-id="3a63d-150">Additionally, ordering and optimizing the attribute hierarchy will only negatively affect processing performance.</span></span> <span data-ttu-id="3a63d-151">Entretanto, o atributo deve estar habilitado para servir como vínculo entre as duas dimensões.</span><span class="sxs-lookup"><span data-stu-id="3a63d-151">However, the attribute must be enabled to serve as the link between the two dimensions.</span></span>

4.  <span data-ttu-id="3a63d-152">Alterne para o designer de cubo para o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cubo do tutorial, clique na guia **uso da dimensão** e, em seguida, clique no botão de reticências (**...**) na interseção do grupo de medidas **vendas do revendedor** e da dimensão de cubo **geografia** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-152">Switch to Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, click the **Dimension Usage** tab, and then click the ellipsis button (**...**) at the intersection of the **Reseller Sales** measure group and the **Geography** cube dimension.</span></span>

5.  <span data-ttu-id="3a63d-153">Na lista **Selecionar tipo de relação** , selecione **Referenciada**.</span><span class="sxs-lookup"><span data-stu-id="3a63d-153">In the **Select relationship type** list, select **Referenced**.</span></span>

6.  <span data-ttu-id="3a63d-154">Na lista **Dimensão intermediária** , selecione **Revendedor**.</span><span class="sxs-lookup"><span data-stu-id="3a63d-154">In the **Intermediate dimension** list, select **Reseller**.</span></span>

7.  <span data-ttu-id="3a63d-155">Na lista **Atributo de dimensão de referência** , selecione **Geografia Principal**e selecione **Geografia Principal** na lista **Atributo de dimensão intermediária** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-155">In the **Reference dimension attribute** list, select **Geography Key**, and then select **Geography Key** in the **Intermediate dimension attribute** list.</span></span>

     <span data-ttu-id="3a63d-156">Observe se a caixa de seleção **Materializar** está marcada.</span><span class="sxs-lookup"><span data-stu-id="3a63d-156">Notice that the **Materialize** check box is selected.</span></span> <span data-ttu-id="3a63d-157">Esta é a configuração padrão para as dimensões MOLAP.</span><span class="sxs-lookup"><span data-stu-id="3a63d-157">This is the default setting for MOLAP dimensions.</span></span> <span data-ttu-id="3a63d-158">A materialização do atributo de dimensão faz com que o valor do vínculo entre a tabela de fatos e a dimensão de referência de cada linha seja materializado, ou armazenado, na estrutura MOLAP da dimensão durante o processamento.</span><span class="sxs-lookup"><span data-stu-id="3a63d-158">Materializing the dimension attribute link causes the value of the link between the fact table and the reference dimension for each row to be materialized, or stored, in the dimension's MOLAP structure during processing.</span></span> <span data-ttu-id="3a63d-159">Isso terá um efeito secundário no desempenho do processamento e nos requisitos de armazenamento, mas aumentará o desempenho da consulta (algumas vezes de maneira bastante significativa).</span><span class="sxs-lookup"><span data-stu-id="3a63d-159">This will have a minor effect on processing performance and storage requirements, but will increase query performance (sometimes significantly).</span></span>

8.  <span data-ttu-id="3a63d-160">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a63d-160">Click **OK**.</span></span>

     <span data-ttu-id="3a63d-161">Observe que agora a dimensão de cubo **Geografia** está vinculada ao grupo de medidas **Vendas do Revendedor** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-161">Notice that the **Geography** cube dimension is now linked to the **Reseller Sales** measure group.</span></span> <span data-ttu-id="3a63d-162">O ícone indica que a relação é uma relação de dimensão referenciada.</span><span class="sxs-lookup"><span data-stu-id="3a63d-162">The icon indicates that the relationship is a referenced dimension relationship.</span></span>

9. <span data-ttu-id="3a63d-163">Na lista **Dimensões** da guia **Uso da Dimensão** , clique com o botão direito do mouse em **Geografia**e clique em **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="3a63d-163">In the **Dimensions** list on the **Dimension Usage** tab, right-click **Geography**, and then click **Rename**.</span></span>

10. <span data-ttu-id="3a63d-164">Altere o nome dessa dimensão do cubo para `Reseller Geography` .</span><span class="sxs-lookup"><span data-stu-id="3a63d-164">Change the name of this cube dimension to `Reseller Geography`.</span></span>

     <span data-ttu-id="3a63d-165">Como agora essa dimensão de cubo está vinculada ao grupo de medidas **Vendas do Revendedor** , os usuários poderão definir seu uso explicitamente no cubo, evitando uma possível confusão do usuário.</span><span class="sxs-lookup"><span data-stu-id="3a63d-165">Because this cube dimension is now linked to the **Reseller Sales** measure group, users will benefit from explicitly defining its use in the cube, to avoid possible user confusion.</span></span>

## <a name="successfully-dimensioning-reseller-sales-by-geography"></a><span data-ttu-id="3a63d-166">Dimensionamento bem-sucedido das vendas do revendedor por geografia</span><span class="sxs-lookup"><span data-stu-id="3a63d-166">Successfully Dimensioning Reseller Sales by Geography</span></span>

1.  <span data-ttu-id="3a63d-167">No menu **Compilar** , clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="3a63d-167">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

2.  <span data-ttu-id="3a63d-168">Quando a implantação for concluída com êxito, clique na guia **Navegador** do Designer do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e clique no botão **Reconectar** .</span><span class="sxs-lookup"><span data-stu-id="3a63d-168">When deployment has successfully completed, click the **Browser** tab in Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Reconnect** button.</span></span>

3.  <span data-ttu-id="3a63d-169">No painel metadados, expanda `Reseller Geography` , clique com o botão direito do mouse em **geografia**e clique em **Adicionar à área da linha**.</span><span class="sxs-lookup"><span data-stu-id="3a63d-169">In the metadata pane, expand `Reseller Geography`, right-click **Geographies**, and then click **Add to Row Area**.</span></span>

     <span data-ttu-id="3a63d-170">Observe que agora a medida **Vendas do Revendedor/Valor das Vendas** foi dimensionada corretamente pelo atributo **País/Região** da hierarquia definida pelo usuário **Geografias** , como mostra a imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="3a63d-170">Notice that the **Reseller Sales-Sales Amount** measure is now correctly dimensioned by the **Country-Region** attribute of the **Geographies** user-defined hierarchy, as shown in the following image.</span></span>

     <span data-ttu-id="3a63d-171">![Caixa de diálogo Definir Relação](../../2014/tutorials/media/l5-referencedrelationship-5.gif "Caixa de diálogo Definir Relação")</span><span class="sxs-lookup"><span data-stu-id="3a63d-171">![Define Relationship dialog box](../../2014/tutorials/media/l5-referencedrelationship-5.gif "Define Relationship dialog box")</span></span>

## <a name="next-task-in-lesson"></a><span data-ttu-id="3a63d-172">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="3a63d-172">Next Task in Lesson</span></span>
 [<span data-ttu-id="3a63d-173">Definindo uma relação de fatos</span><span class="sxs-lookup"><span data-stu-id="3a63d-173">Defining a Fact Relationship</span></span>](lesson-5-2-defining-a-fact-relationship.md)

## <a name="see-also"></a><span data-ttu-id="3a63d-174">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3a63d-174">See Also</span></span>
 <span data-ttu-id="3a63d-175">As [relações de atributo](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md) [definem uma relação referenciada e as propriedades de relação referenciadas](multidimensional-models/define-a-referenced-relationship-and-referenced-relationship-properties.md)</span><span class="sxs-lookup"><span data-stu-id="3a63d-175">[Attribute Relationships](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md) [Define a Referenced Relationship and Referenced Relationship Properties](multidimensional-models/define-a-referenced-relationship-and-referenced-relationship-properties.md)</span></span>

