---
title: Adicionando atributos a dimensões | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 80551dad-97ac-40d0-90af-b810780321ce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76a04c42cc501fdca3e5ceb6481452052966796b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568832"
---
# <a name="adding-attributes-to-dimensions"></a><span data-ttu-id="452f3-102">Adicionando atributos em dimensões</span><span class="sxs-lookup"><span data-stu-id="452f3-102">Adding Attributes to Dimensions</span></span>
  <span data-ttu-id="452f3-103">Agora que você definiu dimensões, pode populá-las com atributos que representam cada elemento de dados na dimensão.</span><span class="sxs-lookup"><span data-stu-id="452f3-103">Now that you have defined dimensions, you can populate them with attributes that represent each data element in the dimension.</span></span> <span data-ttu-id="452f3-104">Os atributos geralmente são baseados em campos de uma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="452f3-104">Attributes are commonly based on fields from a data source view.</span></span> <span data-ttu-id="452f3-105">Ao adicionar atributos a uma dimensão, você pode incluir campos de qualquer tabela na exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="452f3-105">When adding attributes to a dimension, you can include fields from any table in the data source view.</span></span>  
  
 <span data-ttu-id="452f3-106">Nesta tarefa, você usará o Designer de Dimensão para adicionar atributos às dimensões Cliente e Produto.</span><span class="sxs-lookup"><span data-stu-id="452f3-106">In this task, you will use Dimension Designer to add attributes to the Customer and Product dimensions.</span></span> <span data-ttu-id="452f3-107">A dimensão de Cliente incluirá atributos baseados em campos de ambas as tabelas de Cliente e Geografia.</span><span class="sxs-lookup"><span data-stu-id="452f3-107">The Customer dimension will include attributes based on fields from both the Customer and Geography tables.</span></span>  
  
## <a name="adding-attributes-to-the-customer-dimension"></a><span data-ttu-id="452f3-108">Adicionando atributos à dimensão Cliente</span><span class="sxs-lookup"><span data-stu-id="452f3-108">Adding Attributes to the Customer Dimension</span></span>  
  
#### <a name="to-add-attributes"></a><span data-ttu-id="452f3-109">Para adicionar atributos</span><span class="sxs-lookup"><span data-stu-id="452f3-109">To add attributes</span></span>  
  
1.  <span data-ttu-id="452f3-110">Abra o Designer de Dimensão da dimensão Cliente.</span><span class="sxs-lookup"><span data-stu-id="452f3-110">Open Dimension Designer for the Customer dimension.</span></span> <span data-ttu-id="452f3-111">Para fazer isso, clique duas vezes na dimensão **Cliente** no nó **Dimensões** do Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="452f3-111">To do this, double-click the **Customer** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="452f3-112">No painel **Atributos** , observe os atributos Customer Key e Geography Key que foram criados pelo Assistente para Cubos.</span><span class="sxs-lookup"><span data-stu-id="452f3-112">In the **Attributes** pane, notice the Customer Key and Geography Key attributes that were created by the Cube Wizard.</span></span>  
  
3.  <span data-ttu-id="452f3-113">Na barra de ferramentas da guia **Estrutura da Dimensão** , verifique se o ícone Zoom para exibir as tabelas do painel **Exibição da Fonte de Dados** está definido para 100%.</span><span class="sxs-lookup"><span data-stu-id="452f3-113">On the toolbar of the **Dimension Structure** tab, make sure the Zoom icon to view the tables in the **Data Source View** pane is set at 100 percent.</span></span>  
  
4.  <span data-ttu-id="452f3-114">Arraste as seguintes colunas da tabela **Customer** do painel **Exibição da Fonte de Dados** para o painel **Atributos** :</span><span class="sxs-lookup"><span data-stu-id="452f3-114">Drag the following columns from the **Customer** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="452f3-115">**BirthDate**</span><span class="sxs-lookup"><span data-stu-id="452f3-115">**BirthDate**</span></span>  
  
    -   <span data-ttu-id="452f3-116">**MaritalStatus**</span><span class="sxs-lookup"><span data-stu-id="452f3-116">**MaritalStatus**</span></span>  
  
    -   <span data-ttu-id="452f3-117">**Sexo**</span><span class="sxs-lookup"><span data-stu-id="452f3-117">**Gender**</span></span>  
  
    -   <span data-ttu-id="452f3-118">**EmailAddress**</span><span class="sxs-lookup"><span data-stu-id="452f3-118">**EmailAddress**</span></span>  
  
    -   <span data-ttu-id="452f3-119">**YearlyIncome**</span><span class="sxs-lookup"><span data-stu-id="452f3-119">**YearlyIncome**</span></span>  
  
    -   <span data-ttu-id="452f3-120">**TotalChildren**</span><span class="sxs-lookup"><span data-stu-id="452f3-120">**TotalChildren**</span></span>  
  
    -   <span data-ttu-id="452f3-121">**NumberChildrenAtHome**</span><span class="sxs-lookup"><span data-stu-id="452f3-121">**NumberChildrenAtHome**</span></span>  
  
    -   <span data-ttu-id="452f3-122">**EnglishEducation**</span><span class="sxs-lookup"><span data-stu-id="452f3-122">**EnglishEducation**</span></span>  
  
    -   <span data-ttu-id="452f3-123">**EnglishOccupation**</span><span class="sxs-lookup"><span data-stu-id="452f3-123">**EnglishOccupation**</span></span>  
  
    -   <span data-ttu-id="452f3-124">**HouseOwnerFlag**</span><span class="sxs-lookup"><span data-stu-id="452f3-124">**HouseOwnerFlag**</span></span>  
  
    -   <span data-ttu-id="452f3-125">**NumberCarsOwned**</span><span class="sxs-lookup"><span data-stu-id="452f3-125">**NumberCarsOwned**</span></span>  
  
    -   <span data-ttu-id="452f3-126">**Telemóvel**</span><span class="sxs-lookup"><span data-stu-id="452f3-126">**Phone**</span></span>  
  
    -   <span data-ttu-id="452f3-127">**DateFirstPurchase**</span><span class="sxs-lookup"><span data-stu-id="452f3-127">**DateFirstPurchase**</span></span>  
  
    -   <span data-ttu-id="452f3-128">**CommuteDistance**</span><span class="sxs-lookup"><span data-stu-id="452f3-128">**CommuteDistance**</span></span>  
  
5.  <span data-ttu-id="452f3-129">Arraste as seguintes colunas da tabela **Geography** do painel **Exibição da Fonte de Dados** para o painel **Atributos** :</span><span class="sxs-lookup"><span data-stu-id="452f3-129">Drag the following columns from the **Geography** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="452f3-130">**Cidade**</span><span class="sxs-lookup"><span data-stu-id="452f3-130">**City**</span></span>  
  
    -   <span data-ttu-id="452f3-131">**StateProvinceName**</span><span class="sxs-lookup"><span data-stu-id="452f3-131">**StateProvinceName**</span></span>  
  
    -   <span data-ttu-id="452f3-132">**EnglishCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="452f3-132">**EnglishCountryRegionName**</span></span>  
  
    -   <span data-ttu-id="452f3-133">**PostalCode**</span><span class="sxs-lookup"><span data-stu-id="452f3-133">**PostalCode**</span></span>  
  
6.  <span data-ttu-id="452f3-134">No menu Arquivo, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="452f3-134">On the File menu, click **Save All**.</span></span>  
  
## <a name="adding-attributes-to-the-product-dimension"></a><span data-ttu-id="452f3-135">Adicionando atributos à dimensão Produto</span><span class="sxs-lookup"><span data-stu-id="452f3-135">Adding Attributes to the Product Dimension</span></span>  
  
#### <a name="to-add-attributes"></a><span data-ttu-id="452f3-136">Para adicionar atributos</span><span class="sxs-lookup"><span data-stu-id="452f3-136">To add attributes</span></span>  
  
1.  <span data-ttu-id="452f3-137">Abra o Designer de Dimensão da dimensão Produto.</span><span class="sxs-lookup"><span data-stu-id="452f3-137">Open Dimension Designer for the Product dimension.</span></span> <span data-ttu-id="452f3-138">Clique duas vezes na dimensão **Produto** no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="452f3-138">Double-click the **Product** dimension in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="452f3-139">No painel **Atributos** , observe o atributo Product Key que foi criado pelo Assistente para Cubos.</span><span class="sxs-lookup"><span data-stu-id="452f3-139">In the **Attributes** pane, notice the Product Key attribute that was created by the Cube Wizard.</span></span>  
  
3.  <span data-ttu-id="452f3-140">Na barra de ferramentas da guia **Estrutura da Dimensão** , verifique se o ícone Zoom para exibir as tabelas do painel **Exibição da Fonte de Dados** está definido para 100%.</span><span class="sxs-lookup"><span data-stu-id="452f3-140">On the toolbar of the **Dimension Structure** tab, make sure the Zoom icon to view the tables in the **Data Source View** pane is set at 100 percent.</span></span>  
  
4.  <span data-ttu-id="452f3-141">Arraste as seguintes colunas da tabela **Product** do painel **Exibição da Fonte de Dados** para o painel **Atributos** :</span><span class="sxs-lookup"><span data-stu-id="452f3-141">Drag the following columns from the **Product** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="452f3-142">**StandardCost**</span><span class="sxs-lookup"><span data-stu-id="452f3-142">**StandardCost**</span></span>  
  
    -   <span data-ttu-id="452f3-143">**Cor**</span><span class="sxs-lookup"><span data-stu-id="452f3-143">**Color**</span></span>  
  
    -   <span data-ttu-id="452f3-144">**SafetyStockLevel**</span><span class="sxs-lookup"><span data-stu-id="452f3-144">**SafetyStockLevel**</span></span>  
  
    -   <span data-ttu-id="452f3-145">**ReorderPoint**</span><span class="sxs-lookup"><span data-stu-id="452f3-145">**ReorderPoint**</span></span>  
  
    -   <span data-ttu-id="452f3-146">**ListPrice**</span><span class="sxs-lookup"><span data-stu-id="452f3-146">**ListPrice**</span></span>  
  
    -   <span data-ttu-id="452f3-147">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="452f3-147">**Size**</span></span>  
  
    -   <span data-ttu-id="452f3-148">**SizeRange**</span><span class="sxs-lookup"><span data-stu-id="452f3-148">**SizeRange**</span></span>  
  
    -   <span data-ttu-id="452f3-149">**Weight**</span><span class="sxs-lookup"><span data-stu-id="452f3-149">**Weight**</span></span>  
  
    -   <span data-ttu-id="452f3-150">**DaysToManufacture**</span><span class="sxs-lookup"><span data-stu-id="452f3-150">**DaysToManufacture**</span></span>  
  
    -   <span data-ttu-id="452f3-151">**ProductLine**</span><span class="sxs-lookup"><span data-stu-id="452f3-151">**ProductLine**</span></span>  
  
    -   <span data-ttu-id="452f3-152">**DealerPrice**</span><span class="sxs-lookup"><span data-stu-id="452f3-152">**DealerPrice**</span></span>  
  
    -   <span data-ttu-id="452f3-153">**Classe**</span><span class="sxs-lookup"><span data-stu-id="452f3-153">**Class**</span></span>  
  
    -   <span data-ttu-id="452f3-154">**Estilo**</span><span class="sxs-lookup"><span data-stu-id="452f3-154">**Style**</span></span>  
  
    -   <span data-ttu-id="452f3-155">**ModelName**</span><span class="sxs-lookup"><span data-stu-id="452f3-155">**ModelName**</span></span>  
  
    -   <span data-ttu-id="452f3-156">**Início**</span><span class="sxs-lookup"><span data-stu-id="452f3-156">**StartDate**</span></span>  
  
    -   <span data-ttu-id="452f3-157">**Término**</span><span class="sxs-lookup"><span data-stu-id="452f3-157">**EndDate**</span></span>  
  
    -   <span data-ttu-id="452f3-158">**Status**</span><span class="sxs-lookup"><span data-stu-id="452f3-158">**Status**</span></span>  
  
5.  <span data-ttu-id="452f3-159">No menu Arquivo, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="452f3-159">On the File menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="452f3-160">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="452f3-160">Next Task in Lesson</span></span>  
 [<span data-ttu-id="452f3-161">Revisando as propriedades de dimensão e cubo</span><span class="sxs-lookup"><span data-stu-id="452f3-161">Reviewing Cube and Dimension Properties</span></span>](lesson-2-4-reviewing-cube-and-dimension-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="452f3-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="452f3-162">See Also</span></span>  
 [<span data-ttu-id="452f3-163">Referência de propriedades de atributo de dimensão</span><span class="sxs-lookup"><span data-stu-id="452f3-163">Dimension Attribute Properties Reference</span></span>](multidimensional-models/dimension-attribute-properties-reference.md)  
  
  
