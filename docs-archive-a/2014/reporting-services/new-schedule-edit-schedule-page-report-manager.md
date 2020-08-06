---
title: 'Novo agendamento: página Editar agenda (Report Manager) | Microsoft Docs'
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 52a4d250-e185-4116-a29c-d809940a00fb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 701c1729eac1c2cf683c966dca58f47b88a2dd32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684094"
---
# <a name="new-schedule-edit-schedule-page-report-manager"></a><span data-ttu-id="e5d51-102">Novo agendamento: página Editar agenda (Report Manager)</span><span class="sxs-lookup"><span data-stu-id="e5d51-102">New Schedule: Edit Schedule Page (Report Manager)</span></span>
  <span data-ttu-id="e5d51-103">Use a página Nova Agenda / Editar Agenda para criar uma agenda para um relatório.</span><span class="sxs-lookup"><span data-stu-id="e5d51-103">Use the New Schedule / Edit Schedule page to create a schedule for a report.</span></span> <span data-ttu-id="e5d51-104">As agendas são usadas com assinaturas para atualizar relatórios armazenados em cache e criar instantâneos como itens autônomos ou em histórico de relatório.</span><span class="sxs-lookup"><span data-stu-id="e5d51-104">Schedules are used with subscriptions, to refresh cached reports, and to create snapshots as standalone items or in report history.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5d51-105">Este recurso não está disponível em todas as edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5d51-105">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e5d51-106">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="e5d51-106">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="e5d51-107">Só é possível criar agendas para relatórios que podem ser executados de modo autônomo.</span><span class="sxs-lookup"><span data-stu-id="e5d51-107">You can create schedules only for reports that can run unattended.</span></span> <span data-ttu-id="e5d51-108">A execução de um relatório autônomo requer que você armazene credenciais de fonte de dados de relatório no banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="e5d51-108">Running a report unattended requires that you store report data source credentials in the report server database.</span></span> <span data-ttu-id="e5d51-109">Para obter mais informações, consulte [página de propriedades de fontes de dados &#40;Report Manager&#41;](../../2014/reporting-services/data-sources-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e5d51-109">For more information, see [Data Sources Properties Page &#40;Report Manager&#41;](../../2014/reporting-services/data-sources-properties-page-report-manager.md).</span></span>  
  
 <span data-ttu-id="e5d51-110">Nem todas as combinações de frequência têm suporte em uma única agenda.</span><span class="sxs-lookup"><span data-stu-id="e5d51-110">Not all frequency combinations can be supported in a single schedule.</span></span> <span data-ttu-id="e5d51-111">Por exemplo, se você desejar executar um relatório às 12h00</span><span class="sxs-lookup"><span data-stu-id="e5d51-111">For example, if you want to run a report at 12:00 P.M.</span></span> <span data-ttu-id="e5d51-112">e às 16h00</span><span class="sxs-lookup"><span data-stu-id="e5d51-112">and 4:00 P.M.</span></span> <span data-ttu-id="e5d51-113">todas as sextas-feiras, você deverá criar duas agendas diárias que especifiquem uma data de execução na sexta-feira, uma com horário de início às 12h00</span><span class="sxs-lookup"><span data-stu-id="e5d51-113">every Friday, you must create two daily schedules that specify a Friday run date, one with a start time of 12:00 P.M.</span></span> <span data-ttu-id="e5d51-114">e outra com horário de início às 16h00.</span><span class="sxs-lookup"><span data-stu-id="e5d51-114">and another with a start time of 4:00 P.M.</span></span>  
  
 <span data-ttu-id="e5d51-115">O processamento da agenda se baseia no horário local do servidor de relatório que hospeda e processa a agenda.</span><span class="sxs-lookup"><span data-stu-id="e5d51-115">Schedule processing is based on the local time of the report server that hosts and processes the schedule.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="e5d51-116">Navegação</span><span class="sxs-lookup"><span data-stu-id="e5d51-116">Navigation</span></span>  
 <span data-ttu-id="e5d51-117">Use os procedimentos a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="e5d51-117">Use the following procedures to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-new-schedule-or-edit-schedule-page-from-the-execution-properties-page-of-a-report"></a><span data-ttu-id="e5d51-118">Para abrir a página Nova Agenda ou Editar Agenda a partir da página de propriedades de Execução de um relatório</span><span class="sxs-lookup"><span data-stu-id="e5d51-118">To open the New Schedule or Edit Schedule page from the Execution properties page of a report</span></span>  
  
1.  <span data-ttu-id="e5d51-119">Abra o Gerenciador de Relatórios e localize o relatório cuja agenda você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="e5d51-119">Open Report Manager, and locate the report for which you want configure a schedule.</span></span>  
  
2.  <span data-ttu-id="e5d51-120">Focalize o relatório e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="e5d51-120">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="e5d51-121">No menu suspenso, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="e5d51-121">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="e5d51-122">Esse procedimento abre a página de propriedades Geral do modelo.</span><span class="sxs-lookup"><span data-stu-id="e5d51-122">This opens the General properties page for the model.</span></span>  
  
4.  <span data-ttu-id="e5d51-123">Selecione a guia **Execução** .</span><span class="sxs-lookup"><span data-stu-id="e5d51-123">Select the **Execution** tab.</span></span>  
  
5.  <span data-ttu-id="e5d51-124">Selecione a opção **Renderizar este relatório em um instantâneo de execução de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="e5d51-124">Select the **Render this report from a report execution snapshot option**.</span></span> <span data-ttu-id="e5d51-125">Em seguida, selecione **Use a agenda a seguir para adicionar instantâneos a histórico de relatórios**e selecione **Agenda específica do relatório**.</span><span class="sxs-lookup"><span data-stu-id="e5d51-125">Then select **Use the following schedule to add snapshots to report history**, and select **Report-specific schedule**.</span></span> <span data-ttu-id="e5d51-126">Clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e5d51-126">Then click **Configure**.</span></span>  
  
### <a name="to-open-the-new-schedule-or-edit-schedule-page-from-the-history-properties-page-of-a-report"></a><span data-ttu-id="e5d51-127">Para abrir a página Nova Agenda ou Editar Agenda a partir da página de propriedades de Histórico de um relatório.</span><span class="sxs-lookup"><span data-stu-id="e5d51-127">To open the New Schedule or Edit Schedule page from the History properties page of a report</span></span>  
  
1.  <span data-ttu-id="e5d51-128">Abra o Gerenciador de Relatórios e localize o relatório cuja agenda você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="e5d51-128">Open Report Manager, and locate the report for which you want configure a schedule.</span></span>  
  
2.  <span data-ttu-id="e5d51-129">Focalize o relatório e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="e5d51-129">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="e5d51-130">No menu suspenso, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="e5d51-130">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="e5d51-131">Esse procedimento abre a página de propriedades Geral do modelo.</span><span class="sxs-lookup"><span data-stu-id="e5d51-131">This opens the General properties page for the model.</span></span>  
  
4.  <span data-ttu-id="e5d51-132">Selecione a guia **Histórico** .</span><span class="sxs-lookup"><span data-stu-id="e5d51-132">Select the **History** tab.</span></span>  
  
5.  <span data-ttu-id="e5d51-133">Selecione **Use a agenda a seguir para adicionar instantâneos a histórico de relatórios**e selecione **Agenda específica do relatório**.</span><span class="sxs-lookup"><span data-stu-id="e5d51-133">Select **Use the following schedule to add snapshots to report history**, and select **Report-specific schedule**.</span></span> <span data-ttu-id="e5d51-134">Clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e5d51-134">Then click **Configure**.</span></span>  
  
### <a name="to-open-the-new-schedule-or-edit-schedule-page-from-the-subscriptions-page"></a><span data-ttu-id="e5d51-135">Para abrir a página Nova Agenda ou Editar Agenda a partir da página Assinaturas.</span><span class="sxs-lookup"><span data-stu-id="e5d51-135">To open the New Schedule or Edit Schedule page from the Subscriptions page</span></span>  
  
1.  <span data-ttu-id="e5d51-136">Abra o Gerenciador de Relatórios e localize o relatório cuja agenda você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="e5d51-136">Open Report Manager, and locate the report for which you want configure a schedule.</span></span>  
  
2.  <span data-ttu-id="e5d51-137">Focalize o relatório e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="e5d51-137">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="e5d51-138">No menu suspenso,</span><span class="sxs-lookup"><span data-stu-id="e5d51-138">In the drop-down menu,</span></span>  
  
    -   <span data-ttu-id="e5d51-139">Clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="e5d51-139">Click **Manage**.</span></span> <span data-ttu-id="e5d51-140">Esse procedimento abre a página de propriedades Geral do relatório.</span><span class="sxs-lookup"><span data-stu-id="e5d51-140">This opens the General properties page for the report.</span></span> <span data-ttu-id="e5d51-141">Em seguida, selecione a guia **Assinaturas** .</span><span class="sxs-lookup"><span data-stu-id="e5d51-141">Then select the **Subscriptions** tab.</span></span>  
  
    -   <span data-ttu-id="e5d51-142">Clique em **Assinar**.</span><span class="sxs-lookup"><span data-stu-id="e5d51-142">Click **Subscribe**.</span></span> <span data-ttu-id="e5d51-143">Esse procedimento abre a página de propriedades de **Assinaturas** do relatório.</span><span class="sxs-lookup"><span data-stu-id="e5d51-143">This opens the **Subscriptions** properties page for the report.</span></span>  
  
4.  <span data-ttu-id="e5d51-144">Na barra de ferramentas, clique em **Nova Assinatura** ou selecione uma assinatura existente para editar.</span><span class="sxs-lookup"><span data-stu-id="e5d51-144">In the toolbar, click **New Subscription** or select an existing subscription to edit.</span></span>  
  
5.  <span data-ttu-id="e5d51-145">Em **Opções de Processamento de Assinaturas**, clique em **Nova Agenda**.</span><span class="sxs-lookup"><span data-stu-id="e5d51-145">Under **Subscription Processing Options**, click **New Schedule**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e5d51-146">Opções</span><span class="sxs-lookup"><span data-stu-id="e5d51-146">Options</span></span>  
 <span data-ttu-id="e5d51-147">**Detalhes da agenda**</span><span class="sxs-lookup"><span data-stu-id="e5d51-147">**Schedule details**</span></span>  
 <span data-ttu-id="e5d51-148">Selecione opções que determinam quando e com que frequência um relatório é executado.</span><span class="sxs-lookup"><span data-stu-id="e5d51-148">Select options that determine when and how often a report runs.</span></span> <span data-ttu-id="e5d51-149">As opções de frequência são colocadas em camadas.</span><span class="sxs-lookup"><span data-stu-id="e5d51-149">Frequency options are layered.</span></span> <span data-ttu-id="e5d51-150">O primeiro conjunto de opções especifica uma categoria de frequência (a cada hora, diariamente, semanalmente e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="e5d51-150">The first set of options specifies a category of frequency (hourly, daily, weekly, and so on).</span></span> <span data-ttu-id="e5d51-151">O segundo conjunto de opções exibido é baseado em sua seleção inicial.</span><span class="sxs-lookup"><span data-stu-id="e5d51-151">The second set of options that appears is based on your initial selection.</span></span>  
  
-   <span data-ttu-id="e5d51-152">**Hora** define uma agenda que é executada a intervalos de hora em hora.</span><span class="sxs-lookup"><span data-stu-id="e5d51-152">**Hour** defines a schedule that runs at hourly intervals.</span></span> <span data-ttu-id="e5d51-153">Use a seção **Datas de início e término** para especificar o dia em que o agendamento deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="e5d51-153">Use the **Start and end dates** section to specify the day on which to run the schedule.</span></span>  
  
-   <span data-ttu-id="e5d51-154">**Dia** define uma agenda que é executada nos dias que você seleciona, em uma hora e minuto específicos.</span><span class="sxs-lookup"><span data-stu-id="e5d51-154">**Day** defines a schedule that runs on the days you select at a specific hour and minute.</span></span> <span data-ttu-id="e5d51-155">Você pode especificar dias das seguintes maneiras: cada, todos os dias da \<*day*> semana e todos os \<*number*> dias.</span><span class="sxs-lookup"><span data-stu-id="e5d51-155">You can specify days in the following ways: Every \<*day*>, Every weekday, and Every \<*number*> day.</span></span> <span data-ttu-id="e5d51-156">A escolha de uma abordagem invalida as outras, mesmo se os outros dias parecem selecionados.</span><span class="sxs-lookup"><span data-stu-id="e5d51-156">Choosing one approach voids the others, even if the other days appear to be selected.</span></span>  
  
-   <span data-ttu-id="e5d51-157">**Semana** define uma agenda que é executada a intervalos semanais, em uma hora e minuto específicos.</span><span class="sxs-lookup"><span data-stu-id="e5d51-157">**Week** defines a schedule that runs at weekly intervals at a specific hour and minute.</span></span> <span data-ttu-id="e5d51-158">O intervalo pode ser uma semana completa (por exemplo, a cada duas semanas) ou dias dentro de uma semana.</span><span class="sxs-lookup"><span data-stu-id="e5d51-158">The interval can be a complete week (for example, every two weeks), or days within a week.</span></span>  
  
-   <span data-ttu-id="e5d51-159">**Mês** define uma agenda que é executada mensalmente.</span><span class="sxs-lookup"><span data-stu-id="e5d51-159">**Month** defines a schedule that runs on a monthly basis.</span></span> <span data-ttu-id="e5d51-160">Dentro de um mês você pode escolher um dia com base em um padrão (por exemplo, o último domingo de cada mês) ou datas de calendário específicas (como 1 e 15, para indicar o primeiro e o décimo quinto dia de cada mês).</span><span class="sxs-lookup"><span data-stu-id="e5d51-160">Within a month, you can choose a day based on a pattern (for example, the last Sunday of every month) or specific calendar dates (such as 1 and 15 to indicate the first and fifteenth day of every month).</span></span> <span data-ttu-id="e5d51-161">Usando vírgulas e hífens, você pode especificar vários dias e intervalos, por exemplo, 1, 5, 7-12, 21.</span><span class="sxs-lookup"><span data-stu-id="e5d51-161">Using commas and hyphens, you can specify multiple days and ranges, for example, 1, 5, 7-12, 21.</span></span>  
  
-   <span data-ttu-id="e5d51-162">**Uma vez** define uma agenda que só executa uma vez.</span><span class="sxs-lookup"><span data-stu-id="e5d51-162">**Once** defines a schedule that runs only once.</span></span> <span data-ttu-id="e5d51-163">Use a seção **Datas de início e término** para especificar o dia em que o agendamento deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="e5d51-163">Use the **Start and end dates** section to specify the day on which to run the schedule.</span></span> <span data-ttu-id="e5d51-164">Esta agenda expira assim que é processada.</span><span class="sxs-lookup"><span data-stu-id="e5d51-164">This schedule expires as soon as it is processed.</span></span>  
  
 <span data-ttu-id="e5d51-165">**Datas de início e término**</span><span class="sxs-lookup"><span data-stu-id="e5d51-165">**Start and end dates**</span></span>  
 <span data-ttu-id="e5d51-166">Especifique uma data de início que determina quando o agendamento entra em vigor e uma data de término que determina quando a agendamento expira.</span><span class="sxs-lookup"><span data-stu-id="e5d51-166">Specify a start date that determines when the schedule takes effect and an end date that determines when the schedule expires.</span></span>  
  
 <span data-ttu-id="e5d51-167">Os agendamentos expiram sem notificação.</span><span class="sxs-lookup"><span data-stu-id="e5d51-167">Schedules expire without notification.</span></span> <span data-ttu-id="e5d51-168">Depois da data de término, eles não são mais executados.</span><span class="sxs-lookup"><span data-stu-id="e5d51-168">After the end date, they no longer run.</span></span> <span data-ttu-id="e5d51-169">Agendamentos expirados não são excluídos.</span><span class="sxs-lookup"><span data-stu-id="e5d51-169">Expired schedules are not deleted.</span></span> <span data-ttu-id="e5d51-170">Eles só podem ser excluídos manualmente.</span><span class="sxs-lookup"><span data-stu-id="e5d51-170">Schedules can only be deleted manually.</span></span> <span data-ttu-id="e5d51-171">Assim, se você escolher continuar o agendamento, poderá estender a data de término.</span><span class="sxs-lookup"><span data-stu-id="e5d51-171">That way, if you choose to continue the schedule, you can extend the end date.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d51-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e5d51-172">See Also</span></span>  
 <span data-ttu-id="e5d51-173">[Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="e5d51-173">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="e5d51-174">[Criar, modificar e excluir agendas](subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="e5d51-174">[Create, Modify, and Delete Schedules](subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 [<span data-ttu-id="e5d51-175">Ajuda F1 do Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="e5d51-175">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  