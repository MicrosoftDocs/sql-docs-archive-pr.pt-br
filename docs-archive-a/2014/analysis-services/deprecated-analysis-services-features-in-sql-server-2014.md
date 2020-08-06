---
title: Recursos de Analysis Services preteridos no SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services, backward compatibility
- SSAS, backward compatibility
- SQL Server Analysis Services, backward compatibility
- deprecated features [Analysis Services]
ms.assetid: 2c96ecfe-a170-41d0-bee3-74503f880197
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1b3de78dfea70196e0c2855167e5ce2fda2369a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681902"
---
# <a name="deprecated-analysis-services-features-in-sql-server-2014"></a><span data-ttu-id="3d125-102">Recursos do Analysis Services preteridos no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="3d125-102">Deprecated Analysis Services Features in SQL Server 2014</span></span>
  <span data-ttu-id="3d125-103">Este tópico descreve os recursos substituídos do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que ainda estão disponíveis no [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d125-103">This topic describes the deprecated [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] features that are still available in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="3d125-104">Esses recursos estão programados para serem removidos em uma versão futura do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d125-104">These features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3d125-105">Recursos preteridos não devem ser usados em aplicativos novos.</span><span class="sxs-lookup"><span data-stu-id="3d125-105">Deprecated features should not be used in new applications.</span></span>  
  
## <a name="features-not-supported-in-the-next-version-of-sql-server"></a><span data-ttu-id="3d125-106">Recursos sem suporte na próxima versão do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3d125-106">Features Not Supported in the Next Version of SQL Server</span></span>  
 <span data-ttu-id="3d125-107">Os recursos do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] a seguir não terão suporte na próxima versão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d125-107">The following [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] features will not be supported in the next version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3d125-108">Não use esses recursos em novo trabalho de desenvolvimento e, assim que possível, modifique os aplicativos que os utilizam atualmente.</span><span class="sxs-lookup"><span data-stu-id="3d125-108">Do not use these features in new development work, and modify applications that currently use these features as soon as possible.</span></span>  
  
|<span data-ttu-id="3d125-109">Categoria</span><span class="sxs-lookup"><span data-stu-id="3d125-109">Category</span></span>|<span data-ttu-id="3d125-110">Recurso substituído</span><span class="sxs-lookup"><span data-stu-id="3d125-110">Deprecated feature</span></span>|<span data-ttu-id="3d125-111">Substituição</span><span class="sxs-lookup"><span data-stu-id="3d125-111">Replacement</span></span>|  
|--------------|------------------------|-----------------|  
|<span data-ttu-id="3d125-112">Função MDX</span><span class="sxs-lookup"><span data-stu-id="3d125-112">MDX Function</span></span>|<span data-ttu-id="3d125-113">Função CalculationPassValue</span><span class="sxs-lookup"><span data-stu-id="3d125-113">CalculationPassValue function</span></span>|<span data-ttu-id="3d125-114">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3d125-114">None.</span></span> <span data-ttu-id="3d125-115">O mecanismo OLAP gerencia a fase de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3d125-115">The OLAP engine manages the calculation pass.</span></span> <span data-ttu-id="3d125-116">Essa função não é mais necessária.</span><span class="sxs-lookup"><span data-stu-id="3d125-116">This function is no longer needed.</span></span>|  
|<span data-ttu-id="3d125-117">Função MDX</span><span class="sxs-lookup"><span data-stu-id="3d125-117">MDX Function</span></span>|<span data-ttu-id="3d125-118">Função CalculationCurrentPass</span><span class="sxs-lookup"><span data-stu-id="3d125-118">CalculationCurrentPass function</span></span>|<span data-ttu-id="3d125-119">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3d125-119">None.</span></span> <span data-ttu-id="3d125-120">O mecanismo OLAP gerencia a fase de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3d125-120">The OLAP engine manages the calculation pass.</span></span> <span data-ttu-id="3d125-121">Essa função não é mais necessária.</span><span class="sxs-lookup"><span data-stu-id="3d125-121">This function is no longer needed.</span></span>|  
|<span data-ttu-id="3d125-122">Linguagem MDX</span><span class="sxs-lookup"><span data-stu-id="3d125-122">Multidimensional Expressions (MDX)</span></span>|<span data-ttu-id="3d125-123">A dica do otimizador de consulta NON_EMPTY_BEHAVIOR foi ativada por padrão.</span><span class="sxs-lookup"><span data-stu-id="3d125-123">NON_EMPTY_BEHAVIOR query optimizer hint was turned on by default.</span></span>|<span data-ttu-id="3d125-124">A dica do otimizador de consulta NON_EMPTY_BEHAVIOR será desativada por padrão em uma versão futura.</span><span class="sxs-lookup"><span data-stu-id="3d125-124">The NON_EMPTY_BEHAVIOR query optimizer hint will be turned off by default in a future release.</span></span> <span data-ttu-id="3d125-125">É uma dica de otimização MDX que pode gerar resultados incorretos quando não usada corretamente.</span><span class="sxs-lookup"><span data-stu-id="3d125-125">It is an MDX optimization hint that can produce incorrect results when it is not used correctly.</span></span>|  
|<span data-ttu-id="3d125-126">Outro</span><span class="sxs-lookup"><span data-stu-id="3d125-126">Other</span></span>|<span data-ttu-id="3d125-127">Propriedade de célula intrínseca CELL_EVALUATION_LIST</span><span class="sxs-lookup"><span data-stu-id="3d125-127">CELL_EVALUATION_LIST intrinsic cell property</span></span>|<span data-ttu-id="3d125-128">Originalmente fornecia uma lista de fórmulas avaliadas que se aplicam a uma célula.</span><span class="sxs-lookup"><span data-stu-id="3d125-128">Originally provided a list of evaluated formulas that apply to a cell.</span></span> <span data-ttu-id="3d125-129">Está em branco nesta versão do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="3d125-129">It is blank in this release of Analysis Services.</span></span>  <span data-ttu-id="3d125-130">A ordem de resolução agora é especificada no script MDX.</span><span class="sxs-lookup"><span data-stu-id="3d125-130">Solve order is now specified in MDX script.</span></span> <span data-ttu-id="3d125-131">Para obter mais informações, consulte [noções básicas sobre ordem de passagem e ordem de resolução &#40;&#41;MDX](multidimensional-models/mdx/mdx-data-manipulation-understanding-pass-order-and-solve-order.md)</span><span class="sxs-lookup"><span data-stu-id="3d125-131">For more information, see [Understanding Pass Order and Solve Order &#40;MDX&#41;](multidimensional-models/mdx/mdx-data-manipulation-understanding-pass-order-and-solve-order.md)</span></span>|  
|<span data-ttu-id="3d125-132">Objetos</span><span class="sxs-lookup"><span data-stu-id="3d125-132">Objects</span></span>|<span data-ttu-id="3d125-133">Assemblies COM</span><span class="sxs-lookup"><span data-stu-id="3d125-133">COM assemblies</span></span>|<span data-ttu-id="3d125-134">Os assemblies COM podem representar um risco à segurança.</span><span class="sxs-lookup"><span data-stu-id="3d125-134">COM assemblies can pose a security risk.</span></span> <span data-ttu-id="3d125-135">O suporte a assemblies COM será removido em uma versão futura.</span><span class="sxs-lookup"><span data-stu-id="3d125-135">Support for COM assemblies will be removed in a future release.</span></span>|  
  
## <a name="features-not-supported-in-a-future-version-of-sql-server"></a><span data-ttu-id="3d125-136">Recursos sem suporte em uma versão futura do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3d125-136">Features Not Supported in a Future Version of SQL Server</span></span>  
 <span data-ttu-id="3d125-137">Os recursos do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] a seguir terão suporte na próxima versão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], mas serão removidos em uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="3d125-137">The following [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] features are supported in the next version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but will be removed in a later version.</span></span> <span data-ttu-id="3d125-138">A versão específica do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] não foi determinada.</span><span class="sxs-lookup"><span data-stu-id="3d125-138">The specific version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has not been determined.</span></span>  
  
|<span data-ttu-id="3d125-139">Categoria</span><span class="sxs-lookup"><span data-stu-id="3d125-139">Category</span></span>|<span data-ttu-id="3d125-140">Recurso substituído</span><span class="sxs-lookup"><span data-stu-id="3d125-140">Deprecated feature</span></span>|<span data-ttu-id="3d125-141">Substituição</span><span class="sxs-lookup"><span data-stu-id="3d125-141">Replacement</span></span>|  
|--------------|------------------------|-----------------|  
|<span data-ttu-id="3d125-142">Modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="3d125-142">Multidimensional models</span></span>|<span data-ttu-id="3d125-143">Partições remotas</span><span class="sxs-lookup"><span data-stu-id="3d125-143">Remote partitions</span></span>|<span data-ttu-id="3d125-144">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3d125-144">None.</span></span> <span data-ttu-id="3d125-145">Use partições locais.</span><span class="sxs-lookup"><span data-stu-id="3d125-145">Use local partitions instead.</span></span> <span data-ttu-id="3d125-146">Consulte [criar e gerenciar uma partição Local &#40;Analysis Services&#41;](multidimensional-models/create-and-manage-a-local-partition-analysis-services.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3d125-146">See [Create and Manage a Local Partition &#40;Analysis Services&#41;](multidimensional-models/create-and-manage-a-local-partition-analysis-services.md) for more information.</span></span>|  
|<span data-ttu-id="3d125-147">Modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="3d125-147">Multidimensional models</span></span>|<span data-ttu-id="3d125-148">Grupos de medidas vinculados remotos</span><span class="sxs-lookup"><span data-stu-id="3d125-148">Remote linked measure groups</span></span>|<span data-ttu-id="3d125-149">Um grupo de medidas vinculado remoto é um grupo de medidas vinculado que usa uma fonte de dados em um servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="3d125-149">A remote linked measure group is a linked measure group using a data source on a remote server.</span></span> <span data-ttu-id="3d125-150">A capacidade de usar uma fonte de dados remotos para um grupo de medidas vinculado está agendada para substituição.</span><span class="sxs-lookup"><span data-stu-id="3d125-150">The ability to use a remote data source for a linked measure group is now scheduled for deprecation.</span></span><br /><br /> <span data-ttu-id="3d125-151">Não há substituição para esse recurso.</span><span class="sxs-lookup"><span data-stu-id="3d125-151">There is no replacement for this feature.</span></span> <span data-ttu-id="3d125-152">Recomendamos usar grupos de medidas vinculados locais nesse caso.</span><span class="sxs-lookup"><span data-stu-id="3d125-152">We recommend using local linked measure groups instead.</span></span> <span data-ttu-id="3d125-153">Consulte [Linked Measure Groups](multidimensional-models/linked-measure-groups.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3d125-153">See [Linked Measure Groups](multidimensional-models/linked-measure-groups.md) for more information.</span></span>|  
|<span data-ttu-id="3d125-154">Modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="3d125-154">Multidimensional models</span></span>|<span data-ttu-id="3d125-155">Write-back dimensional</span><span class="sxs-lookup"><span data-stu-id="3d125-155">Dimensional writeback</span></span>|<span data-ttu-id="3d125-156">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3d125-156">None.</span></span> <span data-ttu-id="3d125-157">Use o write-back de partição se você precisar do recurso de write-back.</span><span class="sxs-lookup"><span data-stu-id="3d125-157">Use partition writeback if you require writeback capability.</span></span> <span data-ttu-id="3d125-158">Consulte [definir write-back de partição](multidimensional-models/set-partition-writeback.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3d125-158">See [Set Partition Writeback](multidimensional-models/set-partition-writeback.md) for more information.</span></span>|  
|<span data-ttu-id="3d125-159">Modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="3d125-159">Multidimensional models</span></span>|<span data-ttu-id="3d125-160">Dimensões vinculadas</span><span class="sxs-lookup"><span data-stu-id="3d125-160">Linked dimensions</span></span>|<span data-ttu-id="3d125-161">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3d125-161">None.</span></span> <span data-ttu-id="3d125-162">Considere copiar dimensões para modelos adicionais, em vez de vincular a uma dimensão em outro modelo.</span><span class="sxs-lookup"><span data-stu-id="3d125-162">Consider copying dimensions to additional models rather than linking to a dimension in another model.</span></span>|  
|<span data-ttu-id="3d125-163">MDX</span><span class="sxs-lookup"><span data-stu-id="3d125-163">MDX</span></span>|<span data-ttu-id="3d125-164">Propriedade Non_Empty_Behavior</span><span class="sxs-lookup"><span data-stu-id="3d125-164">Non_Empty_Behavior property</span></span>|<span data-ttu-id="3d125-165">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3d125-165">None.</span></span> <span data-ttu-id="3d125-166">Ao criar um membro calculado, definir essa propriedade de forma incorreta aumenta a probabilidade de retorno de resultados inválidos.</span><span class="sxs-lookup"><span data-stu-id="3d125-166">When creating a calculated member, setting this property incorrectly increases the likelihood of returning invalid results.</span></span> <span data-ttu-id="3d125-167">Otimizações recentes para o mecanismo OLAP melhoraram operações em conjuntos de dados esparsos, tornando essa propriedade menos relevante.</span><span class="sxs-lookup"><span data-stu-id="3d125-167">Recent optimizations to the OLAP engine have improved operations over sparse data sets, making this property less relevant.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d125-168">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3d125-168">See Also</span></span>  
 <span data-ttu-id="3d125-169">[Compatibilidade com versões anteriores do Analysis Services](analysis-services-backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="3d125-169">[Analysis Services Backward Compatibility](analysis-services-backward-compatibility.md) </span></span>  
 [<span data-ttu-id="3d125-170">Funcionalidade descontinuada do Analysis Services no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="3d125-170">Discontinued Analysis Services Functionality in SQL Server 2014</span></span>](discontinued-analysis-services-functionality-in-sql-server-2014.md)  
  
  