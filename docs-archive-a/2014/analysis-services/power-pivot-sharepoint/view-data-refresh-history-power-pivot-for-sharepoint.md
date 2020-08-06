---
title: Exibir histórico de atualização de dados (PowerPivot para SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- unattended data refresh [Analysis Services with SharePoint]
- data refresh history [Analysis Services with SharePoint]
- scheduled data refresh [Analysis Services with SharePoint]
- data refresh [Analysis Services with SharePoint]
ms.assetid: 4c8d8aa8-794d-4f72-ace3-78d0e688e1a5
author: minewiskan
ms.author: owend
ms.openlocfilehash: c7a858aedcbca7aa1436ff06bdf9ebc61724f511
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684400"
---
# <a name="view-data-refresh-history-powerpivot-for-sharepoint"></a><span data-ttu-id="71466-102">Exibir histórico de atualização de dados (PowerPivot para SharePoint)</span><span class="sxs-lookup"><span data-stu-id="71466-102">View Data Refresh History (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="71466-103">O histórico de atualização de dados é um registro de todas as atividades de atualização de dados PowerPivot em uma pasta de trabalho do Excel.</span><span class="sxs-lookup"><span data-stu-id="71466-103">Data refresh history is a record of all data refresh activity for PowerPivot data in an Excel workbook.</span></span> <span data-ttu-id="71466-104">As operações da atualização de dados são executadas em uma instância de servidor do Analysis Services em um farm do SharePoint em uma agenda fornecida por você.</span><span class="sxs-lookup"><span data-stu-id="71466-104">Data refresh operations are performed on an Analysis Services server instance in a SharePoint farm on a schedule that you provide.</span></span> <span data-ttu-id="71466-105">Por padrão, o histórico de atualização de dados é mantido durante um ano.</span><span class="sxs-lookup"><span data-stu-id="71466-105">By default, data refresh history is retained for one year.</span></span> <span data-ttu-id="71466-106">No entanto, um administrador de farm pode especificar uma política de retenção diferente para o histórico de uso e de eventos que determine por quanto tempo os registros de atualização de dados são mantidos.</span><span class="sxs-lookup"><span data-stu-id="71466-106">However, a farm administrator can specify a different retention policy for usage and event history that determines how long data refresh records are kept.</span></span>  
  
 <span data-ttu-id="71466-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2013 | SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="71466-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2013 | SharePoint 2010</span></span>  
  
 <span data-ttu-id="71466-108">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="71466-108">**In this topic:**</span></span>  
  
 [<span data-ttu-id="71466-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="71466-109">Prerequisites</span></span>](#prereq)  
  
 [<span data-ttu-id="71466-110">Exibir o histórico da atualização de dados de uma pasta de trabalho individual</span><span class="sxs-lookup"><span data-stu-id="71466-110">View Data Refresh History for an Individual Workbook</span></span>](#viewhistory)  
  
 [<span data-ttu-id="71466-111">Exibir o histórico da atualização de dados de todas as pastas de trabalho</span><span class="sxs-lookup"><span data-stu-id="71466-111">View Data Refresh History for All Workbooks</span></span>](#viewITOps)  
  
 [<span data-ttu-id="71466-112">Usar informações do histórico</span><span class="sxs-lookup"><span data-stu-id="71466-112">Use History Information</span></span>](#pageelements)  
  
##  <a name="prerequisites"></a><a name="prereq"></a> <span data-ttu-id="71466-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="71466-113">Prerequisites</span></span>  
 <span data-ttu-id="71466-114">Você precisa ter permissões de Colaboração ou superiores para exibir o histórico de atualização de dados.</span><span class="sxs-lookup"><span data-stu-id="71466-114">You must have Contribute permissions or greater to view the data refresh history.</span></span>  
  
 <span data-ttu-id="71466-115">Você deve ter habilitado e agendado a atualização de dados em uma pasta de trabalho que contém dados PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="71466-115">You must have enabled and scheduled data refresh on a workbook that contains PowerPivot data.</span></span> <span data-ttu-id="71466-116">Se não tiver agendado a atualização de dados, você verá a página de definição da agenda em vez das informações do histórico.</span><span class="sxs-lookup"><span data-stu-id="71466-116">If you have not scheduled data refresh, you will see the schedule definition page instead of history information.</span></span>  
  
##  <a name="view-data-refresh-history-for-an-individual-workbook"></a><a name="viewhistory"></a><span data-ttu-id="71466-117">Exibir o histórico de atualização de dados de uma pasta de trabalho individual</span><span class="sxs-lookup"><span data-stu-id="71466-117">View Data Refresh History for an Individual Workbook</span></span>  
  
1.  <span data-ttu-id="71466-118">Em um site do SharePoint, abra a biblioteca contendo uma pasta de trabalho do Excel que contém dados PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="71466-118">On a SharePoint site, open the library that contains an Excel workbook that contains PowerPivot data.</span></span>  
  
     <span data-ttu-id="71466-119">Não há indicador visual que identifique quais pastas de trabalho em uma biblioteca do SharePoint contêm dados PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="71466-119">There is no visual indicator that identifies which workbooks in a SharePoint library contain PowerPivot data.</span></span> <span data-ttu-id="71466-120">Você deve saber com antecedência qual pasta de trabalho contém dados atualizáveis do PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="71466-120">You must know in advance which workbook contains refreshable PowerPivot data.</span></span>  
  
2.  <span data-ttu-id="71466-121">Selecione a pasta de trabalho e clique na seta para baixo exibida à direita.</span><span class="sxs-lookup"><span data-stu-id="71466-121">Select the workbook, and then click the down arrow that appears to the right.</span></span>  
  
3.  <span data-ttu-id="71466-122">Selecione **Gerenciar Atualização de Dados PowerPivot**.</span><span class="sxs-lookup"><span data-stu-id="71466-122">Select **Manage PowerPivot Data Refresh**.</span></span>  
  
 <span data-ttu-id="71466-123">A página de histórico é exibida mostrando um registro completo de todas as atividades de atualização de dados PowerPivot na pasta de trabalho atual do Excel.</span><span class="sxs-lookup"><span data-stu-id="71466-123">The history page appears, showing a complete record for all refresh activity for PowerPivot data in the current Excel workbook.</span></span>  
  
##  <a name="view-data-refresh-history-for-all-workbooks"></a><a name="viewITOps"></a><span data-ttu-id="71466-124">Exibir o histórico de atualização de dados para todas as pastas de trabalho</span><span class="sxs-lookup"><span data-stu-id="71466-124">View Data Refresh History for All Workbooks</span></span>  
 <span data-ttu-id="71466-125">Usando o Painel de Gerenciamento PowerPivot na Administração Central, os administradores de farm e de aplicativos de serviço podem obter uma exibição abrangente do histórico e do status da atualização de todas as pastas de trabalho PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="71466-125">Using the PowerPivot Management Dashboard in Central administration, farm administrators and service application administrators can get a comprehensive view of data refresh history and status for all PowerPivot workbooks.</span></span> <span data-ttu-id="71466-126">Para obter mais informações, consulte [PowerPivot Management Dashboard and Usage Data](power-pivot-management-dashboard-and-usage-data.md).</span><span class="sxs-lookup"><span data-stu-id="71466-126">For more information, see [PowerPivot Management Dashboard and Usage Data](power-pivot-management-dashboard-and-usage-data.md).</span></span>  
  
##  <a name="use-history-information"></a><a name="pageelements"></a><span data-ttu-id="71466-127">Usar informações de histórico</span><span class="sxs-lookup"><span data-stu-id="71466-127">Use History Information</span></span>  
 <span data-ttu-id="71466-128">A página de histórico da atualização de dados fornece informações detalhadas sobre cada operação de atualização.</span><span class="sxs-lookup"><span data-stu-id="71466-128">The data refresh history page provides detailed information about each refresh operation.</span></span> <span data-ttu-id="71466-129">Você pode usar as informações dessa página para confirmar se a atualização ocorreu ou por que falhou.</span><span class="sxs-lookup"><span data-stu-id="71466-129">You can use the information on this page to confirm whether refresh occurred or determine why it failed.</span></span>  
  
|<span data-ttu-id="71466-130">Item</span><span class="sxs-lookup"><span data-stu-id="71466-130">Item</span></span>|<span data-ttu-id="71466-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="71466-131">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="71466-132">Nome</span><span class="sxs-lookup"><span data-stu-id="71466-132">Name</span></span>|<span data-ttu-id="71466-133">Especifica o nome do arquivo da pasta de trabalho do Excel que contém dados PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="71466-133">Specifies the file name of the Excel workbook that contains PowerPivot data.</span></span>|  
|<span data-ttu-id="71466-134">Status atual</span><span class="sxs-lookup"><span data-stu-id="71466-134">Current status</span></span>|<span data-ttu-id="71466-135">Os valores incluem **Agendado**, **Atualizando**, **Êxito**ou **Falha**.</span><span class="sxs-lookup"><span data-stu-id="71466-135">Values include **Scheduled**, **Refreshing**, **Succeeded**, or **Failed**.</span></span><br /><br /> <span data-ttu-id="71466-136">**Agendado** é exibido quando a agenda é criada pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="71466-136">**Scheduled** appears when you first create the schedule.</span></span> <span data-ttu-id="71466-137">Depois que a atualização de dados ocorre pela primeira vez, essa mensagem de status não é mais exibida.</span><span class="sxs-lookup"><span data-stu-id="71466-137">After data refresh runs the first time, this status message no longer appears.</span></span><br /><br /> <span data-ttu-id="71466-138">**Atualizando** indica que a atualização de dados está em andamento.</span><span class="sxs-lookup"><span data-stu-id="71466-138">**Refreshing** indicates that data refresh is in progress.</span></span> <span data-ttu-id="71466-139">Uma solicitação está na fila de processamento ou está sendo executada ativamente no servidor.</span><span class="sxs-lookup"><span data-stu-id="71466-139">A request is either in the process queue or actively running on the server.</span></span><br /><br /> <span data-ttu-id="71466-140">**Êxito** indica que a última operação de atualização de dados foi concluída e a pasta de trabalho atualizada está verificada na biblioteca do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="71466-140">**Succeeded** indicates that the last data refresh operation completed and the updated workbook is checked back into the SharePoint library.</span></span><br /><br /> <span data-ttu-id="71466-141">**Falha** indica que a última operação de atualização de dados não obteve êxito.</span><span class="sxs-lookup"><span data-stu-id="71466-141">**Failed** indicates that the last data refresh operation did not succeed.</span></span> <span data-ttu-id="71466-142">Os dados atualizados não foram salvos.</span><span class="sxs-lookup"><span data-stu-id="71466-142">The refreshed data was not saved.</span></span> <span data-ttu-id="71466-143">A pasta de trabalho contém os mesmos dados que tinha antes do início da atualização de dados.</span><span class="sxs-lookup"><span data-stu-id="71466-143">The workbook contains the same data it had before data refresh began.</span></span>|  
|<span data-ttu-id="71466-144">Última atualização bem-sucedida</span><span class="sxs-lookup"><span data-stu-id="71466-144">Last successful refresh</span></span>|<span data-ttu-id="71466-145">Especifica a data na qual a última atualização de dados foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="71466-145">Specifies the date on which the last data refresh completed successfully.</span></span>|  
|<span data-ttu-id="71466-146">Próxima atualização agendada</span><span class="sxs-lookup"><span data-stu-id="71466-146">Next schedule refresh</span></span>|<span data-ttu-id="71466-147">Especifica a data na qual a próxima atualização de dados está agendada.</span><span class="sxs-lookup"><span data-stu-id="71466-147">Specifies the date on which the next data refresh is scheduled to occur.</span></span><br /><br /> <span data-ttu-id="71466-148">O link **Configurar agendamento** leva à página de definição da agenda.</span><span class="sxs-lookup"><span data-stu-id="71466-148">The **Configure schedule** link takes you to the schedule definition page.</span></span> <span data-ttu-id="71466-149">Se você tiver permissões de colaboração na pasta de trabalho, poderá clicar no link para exibir e modificar as informações de agenda que controlam a atualização de dados PowerPivot na pasta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="71466-149">If you have Contribute permissions on the workbook, you can click the link to view and modify the schedule information that controls unattended data refresh for PowerPivot data in the workbook.</span></span>|  
|<span data-ttu-id="71466-150">Iniciado</span><span class="sxs-lookup"><span data-stu-id="71466-150">Started</span></span>|<span data-ttu-id="71466-151">Dentro da seção de detalhes do histórico, **Iniciado** indica a hora de processamento real.</span><span class="sxs-lookup"><span data-stu-id="71466-151">Within the history details section, **Started** indicates the actual processing time.</span></span> <span data-ttu-id="71466-152">A hora de processamento real pode ser diferente da que foi agendada.</span><span class="sxs-lookup"><span data-stu-id="71466-152">The actual processing time might be different from what you scheduled.</span></span> <span data-ttu-id="71466-153">O processamento será iniciado quando houver memória suficiente disponível no servidor.</span><span class="sxs-lookup"><span data-stu-id="71466-153">Processing will begin when sufficient memory is available on the server.</span></span> <span data-ttu-id="71466-154">Se o servidor estiver muito ocupado, o processamento talvez seja iniciado várias horas depois da hora de início especificada.</span><span class="sxs-lookup"><span data-stu-id="71466-154">If the server is very busy, the processing might begin several hours after the start time you specified.</span></span>|  
|<span data-ttu-id="71466-155">Concluído</span><span class="sxs-lookup"><span data-stu-id="71466-155">Completed</span></span>|<span data-ttu-id="71466-156">Na seção de detalhes do histórico, **Concluído** indica quando a operação de atualização de dados foi concluída.</span><span class="sxs-lookup"><span data-stu-id="71466-156">Within the history details section, **Completed** indicates when the data refresh operation finished.</span></span> <span data-ttu-id="71466-157">A data e a hora indicam quando a pasta de trabalho for verificada na biblioteca.</span><span class="sxs-lookup"><span data-stu-id="71466-157">The date and time indicates when the workbook was checked back into the library.</span></span><br /><br /> <span data-ttu-id="71466-158">Se houve falha na atualização de dados, uma ou mais mensagens de erro explicam a causa da falha.</span><span class="sxs-lookup"><span data-stu-id="71466-158">If data refresh fails, one or more error messages explain the cause of the failure.</span></span> <span data-ttu-id="71466-159">Você pode expandir cada registro para exibir o status detalhado.</span><span class="sxs-lookup"><span data-stu-id="71466-159">You can expand each record to view detailed status.</span></span> <span data-ttu-id="71466-160">Cada fonte de dados é listada individualmente, junto com as mensagens de êxito ou de falha que explicam por que a atualização de dados não foi concluída.</span><span class="sxs-lookup"><span data-stu-id="71466-160">Each data source is listed individually, alongside success or failure messages that explain why data refresh did not complete.</span></span>|  
|<span data-ttu-id="71466-161">Hora</span><span class="sxs-lookup"><span data-stu-id="71466-161">Time</span></span>|<span data-ttu-id="71466-162">Fornece o tempo cumulativo entre o início e a conclusão da atualização de dados.</span><span class="sxs-lookup"><span data-stu-id="71466-162">Provides the cumulative time from when data refresh started to when it was completed.</span></span>|  
|<span data-ttu-id="71466-163">Status</span><span class="sxs-lookup"><span data-stu-id="71466-163">Status</span></span>|<span data-ttu-id="71466-164">Fornece um registro histórico da falha ou do êxito de uma operação de atualização.</span><span class="sxs-lookup"><span data-stu-id="71466-164">Provides a historical record of whether a refresh operation succeeded or failed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71466-165">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71466-165">See Also</span></span>  
 <span data-ttu-id="71466-166">[Configurar a coleta de dados de uso para &#40;PowerPivot para SharePoint](configure-usage-data-collection-for-power-pivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="71466-166">[Configure Usage Data Collection for &#40;PowerPivot for SharePoint](configure-usage-data-collection-for-power-pivot-for-sharepoint.md) </span></span>  
 <span data-ttu-id="71466-167">[Agendar uma atualização de dados &#40;PowerPivot para SharePoint&#41;](../schedule-a-data-refresh-powerpivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="71466-167">[Schedule a Data Refresh &#40;PowerPivot for SharePoint&#41;](../schedule-a-data-refresh-powerpivot-for-sharepoint.md) </span></span>  
 [<span data-ttu-id="71466-168">Atualização de dados PowerPivot</span><span class="sxs-lookup"><span data-stu-id="71466-168">PowerPivot Data Refresh</span></span>](power-pivot-data-refresh.md)  
  
  