---
title: Remova o esquema CDC se você planeja habilitar a captura de dados de alterações | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- cdc schema
- change data capture
ms.assetid: 6a84aa25-0f31-4be3-b2dd-4f249b8254ae
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: abdb33fa3d1ff022a65ed569f19d48bcf4468501
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576149"
---
# <a name="remove-the-cdc-schema-if-you-plan-to-enable-change-data-capture"></a><span data-ttu-id="39598-102">Remover o esquema cdc se você planeja habilitar o Change Data Capture</span><span class="sxs-lookup"><span data-stu-id="39598-102">Remove the cdc schema if you plan to enable change data capture</span></span>
  <span data-ttu-id="39598-103">Um banco de dados já contém um esquema cdc.</span><span class="sxs-lookup"><span data-stu-id="39598-103">A database already contains a cdc schema.</span></span> <span data-ttu-id="39598-104">Se você estiver planejando habilitar o Change Data Capture após a atualização, primeiro descarte esse esquema cdc.</span><span class="sxs-lookup"><span data-stu-id="39598-104">If you plan to enable change data capture after upgrade, you must first drop this cdc schema.</span></span> <span data-ttu-id="39598-105">Quando você habilitar um banco de dados para o Change Data Capture, o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] criará um novo esquema denominado cdc.</span><span class="sxs-lookup"><span data-stu-id="39598-105">When you enable a database for change data capture, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] will create a new schema named cdc.</span></span>  
  
  
