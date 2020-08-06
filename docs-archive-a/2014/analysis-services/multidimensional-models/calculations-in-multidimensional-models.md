---
title: Cálculos em modelos multidimensionais | Microsoft Docs
ms.custom: ''
ms.date: 12/10/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- calculations [Analysis Services], creating
- deleting calculations
- calculations [Analysis Services], scripts
- Cube Designer
- modifying scripts
- removing calculations
- calculations [Analysis Services], deleting
- scripts [Analysis Services], calculations
- cubes [Analysis Services], calculations
- solve orders [Analysis Services]
ms.assetid: c21b3459-9bef-45a2-aba5-c992eba5b66e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 64a9733c4fd198a9906e28c437f7ba4fb10dd39a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683806"
---
# <a name="calculations-in-multidimensional-models"></a><span data-ttu-id="414f9-102">Cálculos em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="414f9-102">Calculations in Multidimensional Models</span></span>
  <span data-ttu-id="414f9-103">Use a guia **Cálculos** do Designer de Cubo para criar membros calculados, conjuntos nomeados e outros cálculos de expressões multidimensionais (MDX).</span><span class="sxs-lookup"><span data-stu-id="414f9-103">Use the **Calculations** tab of Cube Designer to create calculated members, named sets, and other Multidimensional Expressions (MDX) calculations.</span></span>  
  
 <span data-ttu-id="414f9-104">A guia **Cálculos** possui três painéis:</span><span class="sxs-lookup"><span data-stu-id="414f9-104">The **Calculations** tab has the following three panes:</span></span>  
  
-   <span data-ttu-id="414f9-105">O painel **Organizador de Script** lista os cálculos de um cubo.</span><span class="sxs-lookup"><span data-stu-id="414f9-105">The **Script Organizer** pane lists the calculations in a cube.</span></span> <span data-ttu-id="414f9-106">Use-o para criar, organizar e selecionar cálculos para edição.</span><span class="sxs-lookup"><span data-stu-id="414f9-106">Use this pane to create, organize, and select calculations for editing.</span></span>  
  
-   <span data-ttu-id="414f9-107">O painel **Ferramentas de Cálculo** fornece metadados, funções e modelos com os quais criar cálculos.</span><span class="sxs-lookup"><span data-stu-id="414f9-107">The **Calculation Tools** pane provides metadata, functions, and templates with which to create calculations.</span></span>  
  
-   <span data-ttu-id="414f9-108">O painel Expressões de Cálculo oferece suporte a uma exibição de formulário e de script.</span><span class="sxs-lookup"><span data-stu-id="414f9-108">The Calculation Expressions pane supports a form view and a script view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="414f9-109">Para obter mais informações sobre scripts MDX, consulte [introdução ao script MDX no Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892)e consulte a seção recursos adicionais na página [SQL Server 2005-Analysis Services](https://go.microsoft.com/fwlink/?LinkId=80853) no site do Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="414f9-109">For more information about MDX scripting, see [Introduction to MDX Scripting in Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892), and see the Additional Resources section on the [SQL Server 2005 - Analysis Services](https://go.microsoft.com/fwlink/?LinkId=80853) page on the Microsoft TechNet Web site.</span></span> <span data-ttu-id="414f9-110">Para obter mais informações sobre questões de desempenho relacionadas ao design de cubo, consulte o [SQL Server 2005 Analysis Services Performance Guide](https://download.microsoft.com/download/8/5/e/85eea4fa-b3bb-4426-97d0-7f7151b2011c/ssas2005perfguide.doc).</span><span class="sxs-lookup"><span data-stu-id="414f9-110">For more information about performance issues related to cube design, see the [SQL Server 2005 Analysis Services Performance Guide](https://download.microsoft.com/download/8/5/e/85eea4fa-b3bb-4426-97d0-7f7151b2011c/ssas2005perfguide.doc).</span></span>  
  
## <a name="creating-a-new-calculation"></a><span data-ttu-id="414f9-111">Criando um novo cálculo</span><span class="sxs-lookup"><span data-stu-id="414f9-111">Creating a New Calculation</span></span>  
 <span data-ttu-id="414f9-112">Para criar um novo cálculo, na guia **Cálculos** do Designer de Cubo, no menu **Cubo** , clique em **Novo Membro Calculado**, **Novo Conjunto Nomeado**ou **Novo Comando de Script**, de acordo com o tipo de cálculo que você deseja criar.</span><span class="sxs-lookup"><span data-stu-id="414f9-112">To create a new calculation, on the **Calculations** tab of Cube Designer, on the **Cube** menu, click either **New Calculated Member**, **New Named Set**, or **New Script Command**, depending on the type of calculation you want to create.</span></span> <span data-ttu-id="414f9-113">Você também pode clicar em algum dos botões correspondentes na barra de ferramentas ou clicar com o botão direito do mouse em qualquer lugar do painel **Organizador de Script** e clique em um dos comandos do menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="414f9-113">You can also click any of the corresponding buttons on the toolbar, or right-click anywhere in the **Script Organizer** pane and then click one of the commands on the shortcut menu.</span></span> <span data-ttu-id="414f9-114">Essa ação adiciona um novo cálculo ao painel **Organizador de Script** e exibe campos para ele no formulário de cálculo do painel Expressões de Cálculos.</span><span class="sxs-lookup"><span data-stu-id="414f9-114">This action adds a new calculation to the **Script Organizer** pane and displays fields for it in the calculations form in the Calculations Expressions pane.</span></span> <span data-ttu-id="414f9-115">Se você criar um novo script, essa ação abrirá a exibição Script no painel Expressões de Cálculos.</span><span class="sxs-lookup"><span data-stu-id="414f9-115">If you create a new script, this action opens the Script view in the Calculation Expressions pane.</span></span> <span data-ttu-id="414f9-116">Para obter mais informações sobre a criação de três tipos de cálculos, consulte [Criar membros calculados](create-calculated-members.md), [Criar conjuntos nomeados](create-named-sets.md)e [Definir atribuições e outros comandos de Script](define-assignments-and-other-script-commands.md).</span><span class="sxs-lookup"><span data-stu-id="414f9-116">For more information about building the three types of calculations, see [Create Calculated Members](create-calculated-members.md), [Create Named Sets](create-named-sets.md), and [Define Assignments and Other Script Commands](define-assignments-and-other-script-commands.md).</span></span>  
  
## <a name="editing-scripts"></a><span data-ttu-id="414f9-117">Editando scripts</span><span class="sxs-lookup"><span data-stu-id="414f9-117">Editing Scripts</span></span>  
 <span data-ttu-id="414f9-118">Edite scripts no painel expressões de cálculo da guia **cálculos** . O painel expressões de cálculo tem duas exibições, exibição de script e exibição de formulário.</span><span class="sxs-lookup"><span data-stu-id="414f9-118">Edit scripts in the Calculation Expressions pane of the **Calculations** tab. The Calculation Expressions pane has two views, Script view and Form view.</span></span> <span data-ttu-id="414f9-119">A exibição Formulário mostra as expressões e as propriedades de um único comando.</span><span class="sxs-lookup"><span data-stu-id="414f9-119">The Form view shows the expressions and properties for a single command.</span></span> <span data-ttu-id="414f9-120">Quando você editar um script MDX, uma caixa de expressão preenche a exibição Formulário inteira.</span><span class="sxs-lookup"><span data-stu-id="414f9-120">When you edit an MDX script, an expression box fills the entire Form view.</span></span>  
  
 <span data-ttu-id="414f9-121">A exibição Script fornece um editor de código no qual editar os scripts.</span><span class="sxs-lookup"><span data-stu-id="414f9-121">The Script view provides a code editor in which to edit the scripts.</span></span> <span data-ttu-id="414f9-122">Enquanto o painel Expressões de Cálculos estiver no modo de exibição Script, o painel **Organizador de Script** ficará oculto.</span><span class="sxs-lookup"><span data-stu-id="414f9-122">While the Calculation Expressions pane is in Script view, the **Script Organizer** pane is hidden.</span></span> <span data-ttu-id="414f9-123">A Exibição de script fornece codificação por cor, correspondência de parênteses, preenchimento automático e regiões de código MDX.</span><span class="sxs-lookup"><span data-stu-id="414f9-123">The Script view provides color coding, parenthesis matching, auto-complete, and MDX code regions.</span></span> <span data-ttu-id="414f9-124">As regiões de código MDX podem ser recolhidas ou expandidas para facilitar a edição.</span><span class="sxs-lookup"><span data-stu-id="414f9-124">The MDX code regions can be collapsed or expanded to facilitate editing.</span></span>  
  
 <span data-ttu-id="414f9-125">É possível alternar entre as exibições Formulário e Script, basta clicar no menu **Cubo** , apontar para **Mostrar Cálculos em**e, em seguida, clicar em **Script** ou **Formulário**.</span><span class="sxs-lookup"><span data-stu-id="414f9-125">You can switch between the Form view and the Script view by clicking the **Cube** menu, pointing to **Show Calculations in**, and then clicking **Script** or **Form**.</span></span> <span data-ttu-id="414f9-126">Você também pode clicar em **Exibição de Formulário** ou **Exibição de Script** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="414f9-126">You can also click either **Form view** or **Script view** on the toolbar.</span></span>  
  
## <a name="changing-solve-order"></a><span data-ttu-id="414f9-127">Alterando a ordem de resolução</span><span class="sxs-lookup"><span data-stu-id="414f9-127">Changing Solve Order</span></span>  
 <span data-ttu-id="414f9-128">Os cálculos são resolvidos na ordem listada no painel **Organizador de Script** .</span><span class="sxs-lookup"><span data-stu-id="414f9-128">Calculations are solved in the order listed in the **Script Organizer** pane.</span></span> <span data-ttu-id="414f9-129">Você pode reordenar os cálculos clicando com o botão direito do mouse em qualquer cálculo e clicando em **Mover para Cima** ou em **Mover para Baixo** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="414f9-129">You can reorder the calculations by right-clicking any calculation and then clicking **Move Up** or **Move Down** on the shortcut menu.</span></span> <span data-ttu-id="414f9-130">Você também pode clicar em um cálculo e, em seguida, clicar no botão **Mover para Cima** ou **Mover para Baixo** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="414f9-130">You can also click a calculation and then click the **Move Up** or **Move Down** button on the toolbar.</span></span>  
  
 <span data-ttu-id="414f9-131">Você pode anular essa ordem manualmente para células calculadas e membros calculados.</span><span class="sxs-lookup"><span data-stu-id="414f9-131">You can override this order manually for calculated cells and calculated members.</span></span> <span data-ttu-id="414f9-132">Para obter mais informações sobre a ordem de passagem e de resolução, consulte [Entendendo a ordem de passagem e a ordem de resolução &#40;MDX&#41;](mdx/mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span><span class="sxs-lookup"><span data-stu-id="414f9-132">For more information about pass order and solve order, see [Understanding Pass Order and Solve Order &#40;MDX&#41;](mdx/mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span></span>  
  
## <a name="deleting-a-calculation"></a><span data-ttu-id="414f9-133">Excluindo um cálculo</span><span class="sxs-lookup"><span data-stu-id="414f9-133">Deleting a Calculation</span></span>  
 <span data-ttu-id="414f9-134">Para excluir um cálculo existente, na guia **Cálculos** do painel **Organizador de Script** , selecione o cálculo que será excluído e, em seguida, clique em **Excluir** no menu **Editar** ou clique no ícone **Editar** da barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="414f9-134">To delete an existing calculation, on the **Calculations** tab, in the **Script Organizer** pane, select the calculation to be deleted, and then click **Delete** on the **Edit** menu or click the **Delete** icon on the toolbar.</span></span> <span data-ttu-id="414f9-135">Você também pode clicar com o botão direito do mouse no cálculo no painel **Organizador de Script** e selecionar **Excluir** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="414f9-135">You can also right-click the calculation in the **Script Organizer** pane and select **Delete** from the short-cut menu.</span></span>  
  
  