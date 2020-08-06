---
title: Adicionando uma exibição da fonte de dados para dados do Call Center (tutorial de mineração de dados intermediários) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a448e7e4-dbd1-4d31-90bc-4d4a1c23b352
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 6d3d9aa3153b39b9ef7f4a92af20e0e8791780bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683226"
---
# <a name="adding-a-data-source-view-for-call-center-data-intermediate-data-mining-tutorial"></a><span data-ttu-id="c3cbe-102">Adicionando uma exibição da fonte de dados aos dados de call center (Tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="c3cbe-102">Adding a Data Source View for Call Center Data (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="c3cbe-103">Nesta tarefa, você adiciona uma exibição da fonte de dados que será usada para acessar os dados do call center.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-103">In this task, you add a data source view that will be used to access the call center data.</span></span> <span data-ttu-id="c3cbe-104">Os mesmos dados serão usados para criar o modelo de rede neural inicial para exploração e o modelo de regressão logística que você usará para fazer recomendações.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-104">The same data will be used to build both the initial neural network model for exploration, and the logistic regression model that you will use to make recommendations.</span></span>  
  
 <span data-ttu-id="c3cbe-105">Você também usará o Designer de Exibição da Fonte de Dados para adicionar uma coluna para o dia da semana.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-105">You will also use the Data Source View Designer to add a column for the day of the week.</span></span> <span data-ttu-id="c3cbe-106">Isso é porque, embora os dados de origem acompanhem os dados do call center por datas, sua experiência diz que há padrões recorrentes em termos de volume de chamadas e qualidade de serviço, dependendo se o dia for um fim de semana ou um dia útil.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-106">That is because, although the source data tracks call center data by dates, your experience tells you that there are recurring patterns both in terms of call volume and service quality, depending on whether the day is a weekend or a weekday.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="c3cbe-107">Procedimentos</span><span class="sxs-lookup"><span data-stu-id="c3cbe-107">Procedures</span></span>  
  
#### <a name="to-add-a-data-source-view"></a><span data-ttu-id="c3cbe-108">Para adicionar uma exibição da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="c3cbe-108">To add a data source view</span></span>  
  
1.  <span data-ttu-id="c3cbe-109">Em **Gerenciador de soluções**, clique com o botão direito do mouse em **exibições da fonte de dados**e selecione **nova exibição da fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-109">In **Solution Explorer**, right-click **Data Source Views**, and select **New Data Source View**.</span></span>  
  
     <span data-ttu-id="c3cbe-110">O Assistente de Exibição da Fonte de Dados é exibido.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-110">The Data Source View Wizard opens.</span></span>  
  
2.  <span data-ttu-id="c3cbe-111">Na página **Bem-vindo ao Assistente de Exibição da Fonte de Dados** , clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-111">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="c3cbe-112">Na página **selecionar uma fonte de dados** , em **fontes de dados relacionais**, selecione a [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-112">On the **Select a Data Source** page, under **Relational data sources**, select the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source.</span></span> <span data-ttu-id="c3cbe-113">Se você não tiver essa fonte de dados, consulte o [tutorial básico de mineração de dados](../../2014/tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="c3cbe-113">If you do not have this data source, see [Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md).</span></span> <span data-ttu-id="c3cbe-114">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-114">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="c3cbe-115">Na página **selecionar tabelas e exibições** , selecione a tabela a seguir e clique na seta para a direita para adicioná-la à exibição da fonte de dados:</span><span class="sxs-lookup"><span data-stu-id="c3cbe-115">On the **Select Tables and Views** page, select the following table and then click the right arrow to add it to the data source view:</span></span>  
  
    -   <span data-ttu-id="c3cbe-116">**FactCallCenter (dbo)**</span><span class="sxs-lookup"><span data-stu-id="c3cbe-116">**FactCallCenter (dbo)**</span></span>  
  
    -   <span data-ttu-id="c3cbe-117">**DimDate**</span><span class="sxs-lookup"><span data-stu-id="c3cbe-117">**DimDate**</span></span>  
  
5.  <span data-ttu-id="c3cbe-118">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-118">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="c3cbe-119">Na página **concluindo o assistente** , por padrão, a exibição da fonte de dados é denominada [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c3cbe-119">On the **Completing the Wizard** page, by default the data source view is named [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span> <span data-ttu-id="c3cbe-120">Altere o nome para **callcenter**e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-120">Change the name to **CallCenter**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="c3cbe-121">O designer de exibição da fonte de dados é aberto para exibir a exibição da fonte de dados **callcenter** .</span><span class="sxs-lookup"><span data-stu-id="c3cbe-121">Data Source View Designer opens to display the **CallCenter** data source view.</span></span>  
  
7.  <span data-ttu-id="c3cbe-122">Clique com o botão direito do mouse dentro do painel exibição da fonte de dados e selecione **Adicionar/remover tabelas**.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-122">Right-click inside the Data Source View pane, and select **Add/Remove Tables**.</span></span> <span data-ttu-id="c3cbe-123">Selecione a tabela **DimDate** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-123">Select the table, **DimDate** and click **OK**.</span></span>  
  
     <span data-ttu-id="c3cbe-124">Uma relação deve ser adicionada automaticamente entre as `DateKey` colunas em cada tabela.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-124">A relationship should be automatically added between the `DateKey` columns in each table.</span></span> <span data-ttu-id="c3cbe-125">Você usará essa relação para obter a coluna, **EnglishDayNameOfWeek**, da tabela **DimDate** e usá-la em seu modelo.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-125">You will use this relationship to get the column, **EnglishDayNameOfWeek**, from the **DimDate** table and use it in your model.</span></span>  
  
8.  <span data-ttu-id="c3cbe-126">No designer de exibição da fonte de dados, clique com o botão direito do mouse na tabela, **FactCallCenter**e selecione **novo cálculo nomeado**.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-126">In the Data Source View designer, right-click the table, **FactCallCenter**, and select **New Named Calculation**.</span></span>  
  
     <span data-ttu-id="c3cbe-127">Na caixa de diálogo **criar cálculo nomeado** , digite os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c3cbe-127">In the **Create Named Calculation** dialog box, type the following values:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="c3cbe-128">**Nome da coluna**</span><span class="sxs-lookup"><span data-stu-id="c3cbe-128">**Column name**</span></span>|<span data-ttu-id="c3cbe-129">DayOfWeek</span><span class="sxs-lookup"><span data-stu-id="c3cbe-129">DayOfWeek</span></span>|  
    |<span data-ttu-id="c3cbe-130">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c3cbe-130">**Description**</span></span>|<span data-ttu-id="c3cbe-131">Obter dia de semana da tabela DimDate</span><span class="sxs-lookup"><span data-stu-id="c3cbe-131">Get day of week from DimDate table</span></span>|  
    |<span data-ttu-id="c3cbe-132">**Expression**</span><span class="sxs-lookup"><span data-stu-id="c3cbe-132">**Expression**</span></span>|`(SELECT EnglishDayNameOfWeek AS DayOfWeek FROM DimDate where FactCallCenter.DateKey = DimDate.DateKey)`|  
  
     <span data-ttu-id="c3cbe-133">Para verificar se a expressão cria os dados necessários, clique com o botão direito do mouse na tabela **FactCallCenter**e selecione **explorar dados**.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-133">To verify that the expression creates the data you need, right-click the table **FactCallCenter**, and then select **Explore Data**.</span></span>  
  
9. <span data-ttu-id="c3cbe-134">Reserve um minuto para revisar os dados disponíveis, para que você possa entender como são usados na mineração de dados:</span><span class="sxs-lookup"><span data-stu-id="c3cbe-134">Take a minute to review the data that is available, so that you can understand how it is used in data mining:</span></span>  
  
|<span data-ttu-id="c3cbe-135">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="c3cbe-135">Column name</span></span>|<span data-ttu-id="c3cbe-136">Contém</span><span class="sxs-lookup"><span data-stu-id="c3cbe-136">Contains</span></span>|  
|-----------------|--------------|  
|<span data-ttu-id="c3cbe-137">FactCallCenterID</span><span class="sxs-lookup"><span data-stu-id="c3cbe-137">FactCallCenterID</span></span>|<span data-ttu-id="c3cbe-138">Uma chave arbitrária criada durante a importação dos dados para o data warehouse.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-138">An arbitrary key created when the data was imported to the data warehouse.</span></span><br /><br /> <span data-ttu-id="c3cbe-139">Esta coluna identifica registros exclusivos e deve ser usada como o chave de caso para o modelo de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-139">This column identifies unique records and should be used as the case key for the data mining model.</span></span>|  
|<span data-ttu-id="c3cbe-140">DateKey</span><span class="sxs-lookup"><span data-stu-id="c3cbe-140">DateKey</span></span>|<span data-ttu-id="c3cbe-141">A data da operação do call center, expressa como um inteiro.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-141">The date of the call center operation, expressed as an integer.</span></span> <span data-ttu-id="c3cbe-142">Chaves de datas em valores inteiros são usadas frequentemente em data warehouses, mas você pode obter a data no formato data/hora se agrupar por valores de data.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-142">Integer date keys are often used in data warehouses, but you might want to obtain the date in date/time format if you were going to group by date values.</span></span><br /><br /> <span data-ttu-id="c3cbe-143">Observe que as datas não são exclusivas porque o fornecedor oferece um relatório separado para cada turno em cada dia de operação.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-143">Note that dates are not unique because the vendor provides a separate report for each shift in each day of operation.</span></span>|  
|<span data-ttu-id="c3cbe-144">WageType</span><span class="sxs-lookup"><span data-stu-id="c3cbe-144">WageType</span></span>|<span data-ttu-id="c3cbe-145">Indica se o dia era um dia da semana, um fim de semana ou um feriado.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-145">Indicates whether the day was a weekday, a weekend, or a holiday.</span></span><br /><br /> <span data-ttu-id="c3cbe-146">É possível que haja uma diferença na qualidade do atendimento ao cliente em fins de semana versus dias da semana, portanto, você usará essa coluna como uma entrada.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-146">It is possible that there is a difference in quality of customer service on weekends vs. weekdays so you will use this column as an input.</span></span>|  
|<span data-ttu-id="c3cbe-147">Turno</span><span class="sxs-lookup"><span data-stu-id="c3cbe-147">Shift</span></span>|<span data-ttu-id="c3cbe-148">Indica o turno para o qual as chamadas são registradas.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-148">Indicates the shift for which calls are recorded.</span></span> <span data-ttu-id="c3cbe-149">Esse call center divide o dia de trabalho em quatro turnos: AM, PM1, PM2 e Meia-noite.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-149">This call center divides the working day into four shifts: AM, PM1, PM2, and Midnight.</span></span><br /><br /> <span data-ttu-id="c3cbe-150">É possível que o turno influencie na qualidade de atendimento ao consumidor; então, você usará isso como entrada.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-150">It is possible that the shift influences the quality of customer service so you will use this as an input.</span></span>|  
|<span data-ttu-id="c3cbe-151">LevelOneOperators</span><span class="sxs-lookup"><span data-stu-id="c3cbe-151">LevelOneOperators</span></span>|<span data-ttu-id="c3cbe-152">Indica o número de operadores de nível 1 no imposto.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-152">Indicates the number of Level 1 operators on duty.</span></span><br /><br /> <span data-ttu-id="c3cbe-153">Os funcionários do call center começam no Nível 1. Então, esses funcionários são menos experientes.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-153">Call center employees start at Level 1 so these employees are less experienced.</span></span>|  
|<span data-ttu-id="c3cbe-154">LevelTwoOperators</span><span class="sxs-lookup"><span data-stu-id="c3cbe-154">LevelTwoOperators</span></span>|<span data-ttu-id="c3cbe-155">Indica o número de operadores de Nível 2 em serviço.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-155">Indicates the number of Level 2 operators on duty.</span></span><br /><br /> <span data-ttu-id="c3cbe-156">Um funcionário deve registrar um certo número de horas de serviço para ser qualificado como operador de Nível 2.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-156">An employee must log a certain number of service hours to qualify as a Level 2 operator.</span></span>|  
|<span data-ttu-id="c3cbe-157">TotalOperators</span><span class="sxs-lookup"><span data-stu-id="c3cbe-157">TotalOperators</span></span>|<span data-ttu-id="c3cbe-158">O número total de operadores presentes durante o turno.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-158">The total number of operators present during the shift.</span></span>|  
|<span data-ttu-id="c3cbe-159">Chamadas</span><span class="sxs-lookup"><span data-stu-id="c3cbe-159">Calls</span></span>|<span data-ttu-id="c3cbe-160">O número de chamadas recebidas durante o turno.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-160">Number of calls received during the shift.</span></span>|  
|<span data-ttu-id="c3cbe-161">AutomaticResponses</span><span class="sxs-lookup"><span data-stu-id="c3cbe-161">AutomaticResponses</span></span>|<span data-ttu-id="c3cbe-162">O número de chamadas administradas totalmente pelo processamento de chamada automatizado (Resposta Interativa de Voz ou IVR).</span><span class="sxs-lookup"><span data-stu-id="c3cbe-162">The number of calls that were handled entirely by automated call processing (Interactive Voice Response, or IVR).</span></span>|  
|<span data-ttu-id="c3cbe-163">Pedidos</span><span class="sxs-lookup"><span data-stu-id="c3cbe-163">Orders</span></span>|<span data-ttu-id="c3cbe-164">O número de pedidos resultantes das chamadas.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-164">The number of orders that resulted from calls.</span></span>|  
|<span data-ttu-id="c3cbe-165">IssuesRaised</span><span class="sxs-lookup"><span data-stu-id="c3cbe-165">IssuesRaised</span></span>|<span data-ttu-id="c3cbe-166">O número de emissões geradas pelas chamadas que exigem acompanhamento.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-166">The number of issues requiring follow-up that were generated by calls.</span></span>|  
|<span data-ttu-id="c3cbe-167">AverageTimePerIssue</span><span class="sxs-lookup"><span data-stu-id="c3cbe-167">AverageTimePerIssue</span></span>|<span data-ttu-id="c3cbe-168">O tempo médio necessário para responder a uma chamada de entrada.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-168">The average time required to respond to an incoming call.</span></span>|  
|<span data-ttu-id="c3cbe-169">ServiceGrade</span><span class="sxs-lookup"><span data-stu-id="c3cbe-169">ServiceGrade</span></span>|<span data-ttu-id="c3cbe-170">Uma métrica que indica a qualidade de serviço geral, medida como a *taxa de abandono* para toda a mudança.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-170">A metric that indicates the general quality of service, measured as the *abandon rate* for the entire shift.</span></span> <span data-ttu-id="c3cbe-171">Quanto maior a taxa de abandono, maior a probabilidade de insatisfação dos clientes e de perda dos pedidos em potencial.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-171">The higher the abandon rate, the more likely it is that customers are dissatisfied and that potential orders are being lost.</span></span>|  
  
 <span data-ttu-id="c3cbe-172">Observe que os dados incluem quatro colunas diferentes com base em uma única coluna de data: `WageType` , **DayOfWeek**, `Shift` e `DateKey` .</span><span class="sxs-lookup"><span data-stu-id="c3cbe-172">Note that the data includes four different columns that are based on a single date column: `WageType`, **DayOfWeek**, `Shift`, and `DateKey`.</span></span> <span data-ttu-id="c3cbe-173">Normalmente, na mineração de dados não é uma boa ideia usar várias colunas derivadas dos mesmos dados, já que os valores se correlacionam entre si muito fortemente e podem ofuscar outros padrões.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-173">Ordinarily in data mining it is not a good idea to use multiple columns that are derived from the same data, as the values correlate with each other too strongly and can obscure other patterns.</span></span>  
  
 <span data-ttu-id="c3cbe-174">No entanto, não usaremos `DateKey` no modelo porque ele contém um número excessivo de valores exclusivos.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-174">However, we will not use `DateKey` in the model because it contains too many unique values.</span></span> <span data-ttu-id="c3cbe-175">Não há nenhuma relação direta entre `Shift` e **DayOfWeek**, e `WageType` e **DayOfWeek** estão apenas parcialmente relacionados.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-175">There is no direct relationship between `Shift` and **DayOfWeek**, and `WageType` and **DayOfWeek** are only partly related.</span></span> <span data-ttu-id="c3cbe-176">Se você estivesse preocupado com a colinearidade, poderia criar a estrutura usando todas as colunas disponíveis e depois ignorar colunas diferentes em cada modelo e testar o efeito.</span><span class="sxs-lookup"><span data-stu-id="c3cbe-176">If you were worried about collinearity, you could create the structure using all of the available columns, and then ignore different columns in each model and test the effect.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="c3cbe-177">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="c3cbe-177">Next Task in Lesson</span></span>  
 [<span data-ttu-id="c3cbe-178">Criando uma estrutura de rede neural e um modelo &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="c3cbe-178">Creating a Neural Network Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-neural-network-structure-and-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="c3cbe-179">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c3cbe-179">See Also</span></span>  
 [<span data-ttu-id="c3cbe-180">Exibições de fontes de dados em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="c3cbe-180">Data Source Views in Multidimensional Models</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models)  
  
  