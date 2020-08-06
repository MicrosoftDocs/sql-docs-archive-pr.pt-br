---
title: 'Lição 1: Criando objetos de banco de dados | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
ms.assetid: 9fb8656b-0e4e-4ada-b404-4db4d3eea995
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 172fdbcaedc10f9c359befd48ed09ec825aea9bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683264"
---
# <a name="lesson-1-creating-database-objects"></a><span data-ttu-id="cc25b-102">Lição 1: Criando objetos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="cc25b-102">Lesson 1: Creating Database Objects</span></span>
  <span data-ttu-id="cc25b-103">Esta lição mostra como criar um banco de dados, criar uma tabela no banco de dados e, então, acessar e alterar os dados na tabela.</span><span class="sxs-lookup"><span data-stu-id="cc25b-103">This lesson shows you how to create a database, create a table in the database, and then access and change the data in the table.</span></span> <span data-ttu-id="cc25b-104">Como esta lição é uma introdução ao uso de [!INCLUDE[tsql](../includes/tsql-md.md)], ela não usa nem descreve as várias opções disponíveis para essas instruções.</span><span class="sxs-lookup"><span data-stu-id="cc25b-104">Because this lesson is an introduction to using [!INCLUDE[tsql](../includes/tsql-md.md)], it does not use or describe the many options that are available for these statements.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="cc25b-105">As instruções podem ser escritas e enviadas ao [!INCLUDE[ssDE](../includes/ssde-md.md)] das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="cc25b-105">statements can be written and submitted to the [!INCLUDE[ssDE](../includes/ssde-md.md)] in the following ways:</span></span>  
  
-   <span data-ttu-id="cc25b-106">Usando [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc25b-106">By using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="cc25b-107">Este tutorial pressupõe que você esteja usando o [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], mas também é possível usar o [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Express, que está disponível como um download gratuito no [Centro de Download da Microsoft](https://www.microsoft.com/download/details.aspx?id=14630).</span><span class="sxs-lookup"><span data-stu-id="cc25b-107">This tutorial assumes that you are using [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], but you can also use [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Express, which is available as a free download from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=14630).</span></span>  
  
-   <span data-ttu-id="cc25b-108">Usando o [utilitário sqlcmd](../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="cc25b-108">By using the [sqlcmd utility](../tools/sqlcmd-utility.md).</span></span>  
  
-   <span data-ttu-id="cc25b-109">Conectando de um aplicativo criado por você.</span><span class="sxs-lookup"><span data-stu-id="cc25b-109">By connecting from an application that you create.</span></span>  
  
 <span data-ttu-id="cc25b-110">O código é executado da mesma maneira no [!INCLUDE[ssDE](../includes/ssde-md.md)] e com as mesmas permissões, independentemente de como você envia as instruções de código.</span><span class="sxs-lookup"><span data-stu-id="cc25b-110">The code executes on the [!INCLUDE[ssDE](../includes/ssde-md.md)] in the same way and with the same permissions, regardless of how you submit the code statements.</span></span>  
  
 <span data-ttu-id="cc25b-111">Para executar [!INCLUDE[tsql](../includes/tsql-md.md)] instruções no [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], abra [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] e conecte-se a uma instância de [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc25b-111">To run [!INCLUDE[tsql](../includes/tsql-md.md)] statements in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], open [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] and connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cc25b-112">Eis os tópicos desta lição:</span><span class="sxs-lookup"><span data-stu-id="cc25b-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="cc25b-113">Criando um banco de dados &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="cc25b-113">Creating a Database &#40;Tutorial&#41;</span></span>](lesson-1-1-creating-a-database.md)  
  
-   [<span data-ttu-id="cc25b-114">Criando uma tabela &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="cc25b-114">Creating a Table &#40;Tutorial&#41;</span></span>](lesson-1-2-creating-a-table.md)  
  
-   [<span data-ttu-id="cc25b-115">Inserindo e atualizando dados em uma tabela &#40;tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="cc25b-115">Inserting and Updating Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-3-inserting-and-updating-data-in-a-table.md)  
  
-   [<span data-ttu-id="cc25b-116">Lendo os dados em uma tabela &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="cc25b-116">Reading the Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-4-reading-the-data-in-a-table.md)  
  
-   [<span data-ttu-id="cc25b-117">Resumo: Criando objetos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="cc25b-117">Summary: Creating Database Objects</span></span>](lesson-1-5-summary-creating-database-objects.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="cc25b-118">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="cc25b-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="cc25b-119">Criando um banco de dados &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="cc25b-119">Creating a Database &#40;Tutorial&#41;</span></span>](lesson-1-1-creating-a-database.md)  
  
  
