---
title: Usar variáveis no componente de Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], using variables
ms.assetid: 92d1881a-1ef1-43ae-b1ca-48d0536bdbc2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4328a938c56ad8383c12cdae1d6511604ec65582
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683123"
---
# <a name="using-variables-in-the-script-component"></a><span data-ttu-id="e834c-102">Usando variáveis no componente Script</span><span class="sxs-lookup"><span data-stu-id="e834c-102">Using Variables in the Script Component</span></span>
  <span data-ttu-id="e834c-103">As variáveis armazenam valores que um pacote e seus contêineres, tarefas e manipuladores de eventos podem usar em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="e834c-103">Variables store values that a package and its containers, tasks, and event handlers can use at run time.</span></span> <span data-ttu-id="e834c-104">Para obter mais informações, consulte [Variáveis do SSIS &#40;Integration Services&#41;](../../integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="e834c-104">For more information, see [Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="e834c-105">Você pode disponibilizar as variáveis existentes para acesso somente leitura ou de leitura/gravação por seu script personalizado, inserindo listas delimitadas por vírgulas de variáveis nos `ReadOnlyVariables` `ReadWriteVariables` campos e na página **script** do **Editor de transformação scripts**.</span><span class="sxs-lookup"><span data-stu-id="e834c-105">You can make existing variables available for read-only or read/write access by your custom script by entering comma-delimited lists of variables in the `ReadOnlyVariables` and `ReadWriteVariables` fields on the **Script** page of the **Script Transformation Editor**.</span></span> <span data-ttu-id="e834c-106">Lembre-se de que os nomes de variáveis diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e834c-106">Keep in mind that variable names are case-sensitive.</span></span> <span data-ttu-id="e834c-107">Use a propriedade `Value` para ler e gravar em variáveis individuais.</span><span class="sxs-lookup"><span data-stu-id="e834c-107">Use the `Value` property to read from and write to individual variables.</span></span> <span data-ttu-id="e834c-108">O componente Script trata qualquer bloqueio necessário em segundo plano, à medida que seu script manipula as variáveis em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="e834c-108">The Script component handles any required locking behind the scenes as your script manipulates the variables at run time.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e834c-109">A coleção de `ReadWriteVariables` está disponível somente no método `PostExecute` para maximizar o desempenho e minimizar o risco de conflitos de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="e834c-109">The collection of `ReadWriteVariables` is only available in the `PostExecute` method to maximize performance and minimize the risk of locking conflicts.</span></span> <span data-ttu-id="e834c-110">Portanto, não será possível incrementar diretamente o valor de uma variável de pacote ao processar cada linha de dados.</span><span class="sxs-lookup"><span data-stu-id="e834c-110">Therefore you cannot directly increment the value of a package variable as you process each row of data.</span></span> <span data-ttu-id="e834c-111">Em vez disso, incremente o valor de uma variável local e defina o valor da variável do pacote como o valor da variável local no método `PostExecute` depois de todos os dados terem sido processados.</span><span class="sxs-lookup"><span data-stu-id="e834c-111">Increment the value of a local variable instead, and set the value of the package variable to the value of the local variable in the `PostExecute` method after all data has been processed.</span></span> <span data-ttu-id="e834c-112">Você também pode usar a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.VariableDispenser%2A> para funcionar nesta limitação, conforme descrito posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="e834c-112">You can also use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.VariableDispenser%2A> property to work around this limitation, as described later in this topic.</span></span> <span data-ttu-id="e834c-113">Entretanto, gravar diretamente em uma variável de pacote, à medida que cada linha for processada, afetará negativamente o desempenho e aumentará o risco de conflitos de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="e834c-113">However, writing directly to a package variable as each row is processed will negatively impact performance and increase the risk of locking conflicts.</span></span>  
  
 <span data-ttu-id="e834c-114">Para obter mais informações sobre a página **Script** do **Editor de Transformação Scripts**, consulte [Configurando o componente Script no Editor de Componentes de Script](configuring-the-script-component-in-the-script-component-editor.md) e [Editor de Transformação Scripts &#40;Página Script&#41;](../../script-transformation-editor-script-page.md).</span><span class="sxs-lookup"><span data-stu-id="e834c-114">For more information about the **Script** page of the **Script Transformation Editor**, see [Configuring the Script Component in the Script Component Editor](configuring-the-script-component-in-the-script-component-editor.md) and [Script Transformation Editor &#40;Script Page&#41;](../../script-transformation-editor-script-page.md).</span></span>  
  
 <span data-ttu-id="e834c-115">O componente Script cria uma classe de coleção `Variables` no item de projeto `ComponentWrapper` com uma propriedade de acessador com rigidez de tipos para o valor de cada variável pré-configurada  onde a propriedade tem o mesmo nome que a variável em si.</span><span class="sxs-lookup"><span data-stu-id="e834c-115">The Script component creates a `Variables` collection class in the `ComponentWrapper` project item with a strongly-typed accessor property for the value of each preconfigured variable where the property has the same name as the variable itself.</span></span> <span data-ttu-id="e834c-116">Esta coleção é exposta pela propriedade `Variables` da classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="e834c-116">This collection is exposed through the `Variables` property of the `ScriptMain` class.</span></span> <span data-ttu-id="e834c-117">A propriedade de acessador fornece permissão somente leitura ou de leitura/gravação ao valor da variável conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="e834c-117">The accessor property provides read-only or read/write permission to the value of the variable as appropriate.</span></span> <span data-ttu-id="e834c-118">Por exemplo, se você tiver adicionado uma variável de inteiro nomeada `MyIntegerVariable` à lista `ReadOnlyVariables`, poderá recuperar seu valor em seu script utilizando o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="e834c-118">For example, if you have added an integer variable named `MyIntegerVariable` to the `ReadOnlyVariables` list, you can retrieve its value in your script by using the following code:</span></span>  
  
 `Dim myIntegerVariableValue As Integer = Me.Variables.MyIntegerVariable`  
  
 <span data-ttu-id="e834c-119">Você também pode usar a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.VariableDispenser%2A>, acessada chamando `Me.VariableDispenser`, para trabalhar com variáveis no componente Script.</span><span class="sxs-lookup"><span data-stu-id="e834c-119">You can also use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.VariableDispenser%2A> property, accessed by calling `Me.VariableDispenser`, to work with variables in the Script component.</span></span> <span data-ttu-id="e834c-120">Neste caso você não está utilizando as propriedades de acessador digitadas e nomeadas para variáveis, mas acessando as variáveis diretamente.</span><span class="sxs-lookup"><span data-stu-id="e834c-120">In this case you are not using the typed and named accessor properties for variables, but accessing the variables directly.</span></span> <span data-ttu-id="e834c-121">Ao usar o <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.VariableDispenser%2A>, você deve tratar as semânticas de bloqueio e a conversão de tipos de dados para obter valores variáveis em seu próprio código.</span><span class="sxs-lookup"><span data-stu-id="e834c-121">When using the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.VariableDispenser%2A>, you must handle both the locking semantics and the casting of data types for variable values in your own code.</span></span> <span data-ttu-id="e834c-122">Você deve usar a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.VariableDispenser%2A> em vez das propriedades de acessador nomeadas e tipadas, se desejar trabalhar com uma variável que não esteja disponível no tempo de design, mas é criada programaticamente no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="e834c-122">You have to use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.VariableDispenser%2A> property instead of the named and typed accessor properties if you want to work with a variable that is not available at design time but is created programmatically at run time.</span></span>  
  
<span data-ttu-id="e834c-123">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e834c-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e834c-124">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="e834c-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e834c-125">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="e834c-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e834c-126">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="e834c-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e834c-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e834c-127">See Also</span></span>  
 <span data-ttu-id="e834c-128">[Variáveis do SSIS &#40;Integration Services&#41;](../../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="e834c-128">[Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="e834c-129">Usar variáveis em pacotes</span><span class="sxs-lookup"><span data-stu-id="e834c-129">Use Variables in Packages</span></span>](../../use-variables-in-packages.md)  
  
  