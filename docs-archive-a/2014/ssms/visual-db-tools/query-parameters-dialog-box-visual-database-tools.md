---
title: Caixa de diálogo Parâmetros da Consulta (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:69645
- vdt.dlgbox.definequeryparameters
ms.assetid: 31cdaee2-d7cd-4d64-a45f-924b27e8b1f0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 76052876ad2899fc959aa7fc49f4299e08bac713
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679617"
---
# <a name="query-parameters-dialog-box-visual-database-tools"></a><span data-ttu-id="0101d-102">Caixa de diálogo Parâmetros da Consulta (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="0101d-102">Query Parameters Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="0101d-103">Essa caixa de diálogo permite digitar valores para os parâmetros definidos na consulta.</span><span class="sxs-lookup"><span data-stu-id="0101d-103">This dialog allows you to enter values for the parameters defined in the query.</span></span> <span data-ttu-id="0101d-104">Ela é exibida quando uma consulta contendo parâmetros que exigeem entradas de usuário final em tempo de execução é executada.</span><span class="sxs-lookup"><span data-stu-id="0101d-104">This dialog box appears when you execute a query that contains parameters that require end-user input at run time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0101d-105">Opções</span><span class="sxs-lookup"><span data-stu-id="0101d-105">Options</span></span>  
 <span data-ttu-id="0101d-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0101d-106">**Name**</span></span>  
 <span data-ttu-id="0101d-107">Lista os parâmetros definidos para a consulta em execução.</span><span class="sxs-lookup"><span data-stu-id="0101d-107">Lists the parameters defined for the query being executed.</span></span> <span data-ttu-id="0101d-108">Se a consulta contiver parâmetros nomeados, os nomes aparecerão na lista.</span><span class="sxs-lookup"><span data-stu-id="0101d-108">If the query contains named parameters, the names appear in the list.</span></span> <span data-ttu-id="0101d-109">Se a consulta contiver parâmetros sem-nome, os nomes de parâmetro definidos pelo sistema serão listados para todos os parâmetros da consulta.</span><span class="sxs-lookup"><span data-stu-id="0101d-109">If the query contains unnamed parameters, system-defined parameter names are listed for each parameter in the query.</span></span>  
  
 <span data-ttu-id="0101d-110">**Valor**</span><span class="sxs-lookup"><span data-stu-id="0101d-110">**Value**</span></span>  
 <span data-ttu-id="0101d-111">Digite o valor de cada parâmetro listado em **Nome**.</span><span class="sxs-lookup"><span data-stu-id="0101d-111">Enter the value for each parameter listed under **Name**.</span></span> <span data-ttu-id="0101d-112">O valor usado mais recentemente aparecerá como valor de parâmetro padrão.</span><span class="sxs-lookup"><span data-stu-id="0101d-112">The value used most recently appears as the default parameter value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0101d-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0101d-113">Example</span></span>  
 <span data-ttu-id="0101d-114">A consulta a seguir, do Painel SQL, abre a caixa de diálogo Parâmetros da Consulta quando executada no banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0101d-114">The following query in the SQL Pane, opens the Query Parameters dialog box when executed in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
SELECT   FirstName, LastName  
FROM    Person.Person AS Lastname  
WHERE   (LastName = @Param1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="0101d-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0101d-115">See Also</span></span>  
 [<span data-ttu-id="0101d-116">Consultar com parâmetros &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="0101d-116">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
