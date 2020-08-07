---
title: Classe de evento PreConnect:Completed | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- PreConnect:Completed Event Class
ms.assetid: 7ed2f620-6511-4985-9961-d2927c2b1759
author: stevestein
ms.author: sstein
ms.openlocfilehash: 74a837337a1353811d10aa0bb58dc018f9c17571
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575816"
---
# <a name="preconnectcompleted-event-class"></a><span data-ttu-id="6192c-102">Classe de evento PreConnect:Completed</span><span class="sxs-lookup"><span data-stu-id="6192c-102">PreConnect:Completed Event Class</span></span>
  <span data-ttu-id="6192c-103">A classe de evento PreConnect:Completed indica quando um gatilho LOGON ou a função de classificação do Administrador de Recursos conclui a execução.</span><span class="sxs-lookup"><span data-stu-id="6192c-103">The PreConnect:Completedevent class indicates when a LOGON trigger or the Resource Governor classifier function finishes execution.</span></span>  
  
## <a name="preconnectcompleted-event-class-data-columns"></a><span data-ttu-id="6192c-104">Colunas de dados da classe de evento PreConnect:Completed</span><span class="sxs-lookup"><span data-stu-id="6192c-104">PreConnect:Completed Event Class Data Columns</span></span>  
  
|<span data-ttu-id="6192c-105">Nome da coluna de dados</span><span class="sxs-lookup"><span data-stu-id="6192c-105">Data column name</span></span>|<span data-ttu-id="6192c-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="6192c-106">Data type</span></span>|<span data-ttu-id="6192c-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="6192c-107">Description</span></span>|<span data-ttu-id="6192c-108">ID da coluna</span><span class="sxs-lookup"><span data-stu-id="6192c-108">Column ID</span></span>|<span data-ttu-id="6192c-109">Filtrável</span><span class="sxs-lookup"><span data-stu-id="6192c-109">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="6192c-110">EventClass</span><span class="sxs-lookup"><span data-stu-id="6192c-110">EventClass</span></span>|`int`|<span data-ttu-id="6192c-111">216</span><span class="sxs-lookup"><span data-stu-id="6192c-111">216</span></span>|<span data-ttu-id="6192c-112">27</span><span class="sxs-lookup"><span data-stu-id="6192c-112">27</span></span>|<span data-ttu-id="6192c-113">Não</span><span class="sxs-lookup"><span data-stu-id="6192c-113">No</span></span>|  
|<span data-ttu-id="6192c-114">SPID</span><span class="sxs-lookup"><span data-stu-id="6192c-114">SPID</span></span>|`int`|<span data-ttu-id="6192c-115">O ID de processo de servidor que dispara este evento.</span><span class="sxs-lookup"><span data-stu-id="6192c-115">The ID of server process that fires this event.</span></span>|<span data-ttu-id="6192c-116">12</span><span class="sxs-lookup"><span data-stu-id="6192c-116">12</span></span>|<span data-ttu-id="6192c-117">Sim</span><span class="sxs-lookup"><span data-stu-id="6192c-117">Yes</span></span>|  
|<span data-ttu-id="6192c-118">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="6192c-118">EventSubClass</span></span>|`int`|<span data-ttu-id="6192c-119">1 para a função de classificador definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="6192c-119">1 for the user-defined classifier function.</span></span>|<span data-ttu-id="6192c-120">21</span><span class="sxs-lookup"><span data-stu-id="6192c-120">21</span></span>|<span data-ttu-id="6192c-121">Sim</span><span class="sxs-lookup"><span data-stu-id="6192c-121">Yes</span></span>|  
|<span data-ttu-id="6192c-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="6192c-122">StartTime</span></span>|`datetime`|<span data-ttu-id="6192c-123">A hora que inicia a função de classificador definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="6192c-123">The time when the user-defined classifier function starts.</span></span>|<span data-ttu-id="6192c-124">14</span><span class="sxs-lookup"><span data-stu-id="6192c-124">14</span></span>|<span data-ttu-id="6192c-125">Sim</span><span class="sxs-lookup"><span data-stu-id="6192c-125">Yes</span></span>|  
|<span data-ttu-id="6192c-126">EndTime</span><span class="sxs-lookup"><span data-stu-id="6192c-126">EndTime</span></span>|`datetime`|<span data-ttu-id="6192c-127">A hora que inicia a função de classificador definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="6192c-127">The time when the user-defined classifier function starts.</span></span>|<span data-ttu-id="6192c-128">15</span><span class="sxs-lookup"><span data-stu-id="6192c-128">15</span></span>|<span data-ttu-id="6192c-129">Sim</span><span class="sxs-lookup"><span data-stu-id="6192c-129">Yes</span></span>|  
|<span data-ttu-id="6192c-130">Duration</span><span class="sxs-lookup"><span data-stu-id="6192c-130">Duration</span></span>|`bigint`|<span data-ttu-id="6192c-131">O número de hora, em microssegundo, usado pela função de classificação.</span><span class="sxs-lookup"><span data-stu-id="6192c-131">The amount of time, in microseconds, used by the classifier function.</span></span>|<span data-ttu-id="6192c-132">13</span><span class="sxs-lookup"><span data-stu-id="6192c-132">13</span></span>|<span data-ttu-id="6192c-133">Sim</span><span class="sxs-lookup"><span data-stu-id="6192c-133">Yes</span></span>|  
|<span data-ttu-id="6192c-134">ObjectID</span><span class="sxs-lookup"><span data-stu-id="6192c-134">ObjectID</span></span>|`int`|<span data-ttu-id="6192c-135">A ID do objeto do classificador definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="6192c-135">The ID of the user-defined classifier object.</span></span>|<span data-ttu-id="6192c-136">22</span><span class="sxs-lookup"><span data-stu-id="6192c-136">22</span></span>|<span data-ttu-id="6192c-137">Sim</span><span class="sxs-lookup"><span data-stu-id="6192c-137">Yes</span></span>|  
|<span data-ttu-id="6192c-138">CPU</span><span class="sxs-lookup"><span data-stu-id="6192c-138">CPU</span></span>|`int`|<span data-ttu-id="6192c-139">Uso de CPU em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="6192c-139">CPU usage in milliseconds.</span></span>|<span data-ttu-id="6192c-140">18</span><span class="sxs-lookup"><span data-stu-id="6192c-140">18</span></span>|<span data-ttu-id="6192c-141">Sim</span><span class="sxs-lookup"><span data-stu-id="6192c-141">Yes</span></span>|  
|<span data-ttu-id="6192c-142">Leituras</span><span class="sxs-lookup"><span data-stu-id="6192c-142">Reads</span></span>|`int`|<span data-ttu-id="6192c-143">O número de leituras lógicas.</span><span class="sxs-lookup"><span data-stu-id="6192c-143">The number of logical reads.</span></span>|<span data-ttu-id="6192c-144">16</span><span class="sxs-lookup"><span data-stu-id="6192c-144">16</span></span>|<span data-ttu-id="6192c-145">Sim</span><span class="sxs-lookup"><span data-stu-id="6192c-145">Yes</span></span>|  
|<span data-ttu-id="6192c-146">Gravações</span><span class="sxs-lookup"><span data-stu-id="6192c-146">Writes</span></span>|`int`|<span data-ttu-id="6192c-147">O número de gravações lógicas.</span><span class="sxs-lookup"><span data-stu-id="6192c-147">The number of logical writes.</span></span>|<span data-ttu-id="6192c-148">17</span><span class="sxs-lookup"><span data-stu-id="6192c-148">17</span></span>|<span data-ttu-id="6192c-149">Sim</span><span class="sxs-lookup"><span data-stu-id="6192c-149">Yes</span></span>|  
|<span data-ttu-id="6192c-150">GroupID</span><span class="sxs-lookup"><span data-stu-id="6192c-150">GroupID</span></span>|`int`|<span data-ttu-id="6192c-151">O ID do grupo de cargas de trabalho classificado.</span><span class="sxs-lookup"><span data-stu-id="6192c-151">The ID of the classified workload group.</span></span>|<span data-ttu-id="6192c-152">66</span><span class="sxs-lookup"><span data-stu-id="6192c-152">66</span></span>|<span data-ttu-id="6192c-153">Sim</span><span class="sxs-lookup"><span data-stu-id="6192c-153">Yes</span></span>|  
|<span data-ttu-id="6192c-154">Erro</span><span class="sxs-lookup"><span data-stu-id="6192c-154">Error</span></span>|`int`|<span data-ttu-id="6192c-155">O último número do erro, caso a função de classificação definida pelo usuário não seja executada.</span><span class="sxs-lookup"><span data-stu-id="6192c-155">The last error number if the user-defined classifier function fails to execute.</span></span>|<span data-ttu-id="6192c-156">31</span><span class="sxs-lookup"><span data-stu-id="6192c-156">31</span></span>|<span data-ttu-id="6192c-157">Sim</span><span class="sxs-lookup"><span data-stu-id="6192c-157">Yes</span></span>|  
|<span data-ttu-id="6192c-158">Estado</span><span class="sxs-lookup"><span data-stu-id="6192c-158">State</span></span>|`int`|<span data-ttu-id="6192c-159">O estado do último erro.</span><span class="sxs-lookup"><span data-stu-id="6192c-159">The state of the last error.</span></span>|<span data-ttu-id="6192c-160">30</span><span class="sxs-lookup"><span data-stu-id="6192c-160">30</span></span>|<span data-ttu-id="6192c-161">Sim</span><span class="sxs-lookup"><span data-stu-id="6192c-161">Yes</span></span>|  
|<span data-ttu-id="6192c-162">TargetUserName</span><span class="sxs-lookup"><span data-stu-id="6192c-162">TargetUserName</span></span>|`sysname`|<span data-ttu-id="6192c-163">O valor de retorno (nome do grupo de cargas de trabalho) para a função de classificação definida pelo usuário, caso o sistema não consiga encontrar um grupo ativo correspondente.</span><span class="sxs-lookup"><span data-stu-id="6192c-163">The return value (workload group name) for the user-defined classifier function if the system can not find a corresponding active group.</span></span> <span data-ttu-id="6192c-164">Caso contrário, essa coluna será definida como NULL.</span><span class="sxs-lookup"><span data-stu-id="6192c-164">Otherwise, this column is set to NULL.</span></span>|<span data-ttu-id="6192c-165">39</span><span class="sxs-lookup"><span data-stu-id="6192c-165">39</span></span>|<span data-ttu-id="6192c-166">Sim</span><span class="sxs-lookup"><span data-stu-id="6192c-166">Yes</span></span>|  
|<span data-ttu-id="6192c-167">ObjectName</span><span class="sxs-lookup"><span data-stu-id="6192c-167">ObjectName</span></span>|`nvarchar(256)`|<span data-ttu-id="6192c-168">O nome de duas partes da função de classificador definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="6192c-168">The two-part name of the classifier user-defined function.</span></span> <span data-ttu-id="6192c-169">Por exemplo, dbo.classifier.</span><span class="sxs-lookup"><span data-stu-id="6192c-169">For example, dbo.classifier.</span></span>|<span data-ttu-id="6192c-170">34</span><span class="sxs-lookup"><span data-stu-id="6192c-170">34</span></span>|<span data-ttu-id="6192c-171">Sim</span><span class="sxs-lookup"><span data-stu-id="6192c-171">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6192c-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6192c-172">See Also</span></span>  
 <span data-ttu-id="6192c-173">[Eventos estendidos](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="6192c-173">[Extended Events](../extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="6192c-174">[Classe de evento PreConnect: Starting](preconnect-starting-event-class.md) </span><span class="sxs-lookup"><span data-stu-id="6192c-174">[PreConnect:Starting Event Class](preconnect-starting-event-class.md) </span></span>  
 [<span data-ttu-id="6192c-175">Resource Governor</span><span class="sxs-lookup"><span data-stu-id="6192c-175">Resource Governor</span></span>](../resource-governor/resource-governor.md)  
  
  