---
title: Usando variáveis e parâmetros (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- parameters [MDX]
- queries [MDX], variables
- queries [MDX], parameters
- variables [MDX]
ms.assetid: a4754d16-d9c4-49f6-9be0-392180b912e4
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd01cf78ea5e3284aa51cad7dc848176a5dc9298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683750"
---
# <a name="using-variables-and-parameters-mdx"></a><span data-ttu-id="93c29-102">Usando variáveis e parâmetros (MDX)</span><span class="sxs-lookup"><span data-stu-id="93c29-102">Using Variables and Parameters (MDX)</span></span>
  <span data-ttu-id="93c29-103">No [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , você pode parametrizar uma instrução MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="93c29-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], you can parameterize a Multidimensional Expressions (MDX) statement.</span></span> <span data-ttu-id="93c29-104">Uma instrução parametrizada permite a criação de instruções genéricas que podem ser personalizadas no runtime.</span><span class="sxs-lookup"><span data-stu-id="93c29-104">A parameterized statement lets you create generic statements that can be customized at runtime.</span></span>  
  
 <span data-ttu-id="93c29-105">Ao criar uma instrução parametrizada, você identifica o nome do parâmetro incluindo um prefixo ao nome com o sinal arroba (@).</span><span class="sxs-lookup"><span data-stu-id="93c29-105">In creating a parameterized statement, you identify the parameter name by prefixing the name with the at sign (@).</span></span> <span data-ttu-id="93c29-106">Por exemplo, @Year seria um nome de parâmetro válido</span><span class="sxs-lookup"><span data-stu-id="93c29-106">For example, @Year would be a valid parameter name</span></span>  
  
 <span data-ttu-id="93c29-107">A linguagem MDX oferece suporte apenas a valores literais ou escalares.</span><span class="sxs-lookup"><span data-stu-id="93c29-107">MDX supports only parameters for literal or scalar values.</span></span> <span data-ttu-id="93c29-108">Para criar um parâmetro que faça referência a um membro, conjunto ou tupla, use uma função como [StrToMember](/sql/mdx/strtomember-mdx) ou [StrToSet](/sql/mdx/strtoset-mdx).</span><span class="sxs-lookup"><span data-stu-id="93c29-108">To create a parameter that references a member, set, or tuple, you would have to use a function such as [StrToMember](/sql/mdx/strtomember-mdx) or [StrToSet](/sql/mdx/strtoset-mdx).</span></span>  
  
 <span data-ttu-id="93c29-109">No seguinte exemplo de XML for Analysis (XMLA), o @CountryName parâmetro conterá o país para o qual os dados do cliente são recuperados:</span><span class="sxs-lookup"><span data-stu-id="93c29-109">In the following XML for Analysis (XMLA) example, the @CountryName parameter will contain the country for which customer data is retrieved:</span></span>  
  
```  
<Envelope xmlns="http://schemas.xmlsoap.org/soap/envelope/">  
  <Body>  
    <Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
      <Command>  
        <Statement>  
select [Measures].members on 0,   
       Filter(Customer.[Customer Geography].Country.members,   
              Customer.[Customer Geography].CurrentMember.Name =  
              @CountryName) on 1  
from [Adventure Works]  
</Statement>  
      </Command>  
      <Properties />  
      <Parameters>  
        <Parameter>  
          <Name>CountryName</Name>  
          <Value>'United Kingdom'</Value>  
        </Parameter>  
      </Parameters>  
    </Execute>  
  </Body>  
</Envelope>  
```  
  
 <span data-ttu-id="93c29-110">Para usar essa funcionalidade com OLE DB, use a interface `ICommandWithParameters`.</span><span class="sxs-lookup"><span data-stu-id="93c29-110">To use this functionality with OLE DB, you would use the `ICommandWithParameters` interface.</span></span> <span data-ttu-id="93c29-111">Para usar essa funcionalidade com ADOMD.Net, use a interface **AdomdCommand.Parameters** .</span><span class="sxs-lookup"><span data-stu-id="93c29-111">To use this functionality with ADOMD.Net, you would use the **AdomdCommand.Parameters** collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93c29-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="93c29-112">See Also</span></span>  
 [<span data-ttu-id="93c29-113">Conceitos básicos do script MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="93c29-113">MDX Scripting Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-scripting-fundamentals-analysis-services.md)  
  
  
