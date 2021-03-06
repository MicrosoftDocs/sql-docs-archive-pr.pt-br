---
title: Selecionar Membros (Assistente de Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.memberconversion.f1
ms.assetid: 1a147461-d594-41e7-a41d-09d2d003e1e0
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd5f184e0d9670725609531b6d0a101f8e7f8647
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571631"
---
# <a name="select-members-business-intelligence-wizard"></a>Selecionar Membros (Assistente de Business Intelligence)
  Use a página **Selecionar Membros** para determinar a quais membros o Assistente de Business Intelligence deve aplicar a funcionalidade de conversão de moeda especificada na página **Definir Opções de Conversão de Moeda** .  
  
> [!NOTE]  
>  Essa página não será exibida se o Assistente de Business Intelligence tiver sido iniciado no Designer de Dimensão ou clicando com o botão direito do mouse em uma dimensão no Gerenciador de Soluções no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].  
  
## <a name="options"></a>Opções  
 **Dimensão de medidas**  
 Selecione para aplicar a funcionalidade de conversão de moeda a uma ou mais medidas no cubo.  
  
 Se selecionada, a grade exibirá as opções listadas na tabela a seguir.  
  
|Opção|Descrição|  
|------------|-----------------|  
|**Tipos de Medidas Internas**|Selecione para incluir funcionalidade de conversão de moeda para a medida especificada.|  
|**Determina**|Selecione a medida do grupo de medidas de taxa que contém a taxa de câmbio a ser usada ao converter a medida selecionada em **Tipos de Medidas Internas** .|  
  
 **Hierarquia de contas**  
 Selecione para aplicar a funcionalidade de conversão de moeda a um ou mais membros da hierarquia de contas da dimensão de conta incluída no cubo. A hierarquia de conta é a hierarquia dentro da dimensão de conta cuja `Type` propriedade está definida como *conta*.  
  
 Se selecionada, a grade exibirá as opções listadas na tabela a seguir.  
  
|Opção|Descrição|  
|------------|-----------------|  
|**Membro da Conta**|Selecione para incluir funcionalidade de conversão de moeda para o membro especificado da hierarquia de contas.|  
|**Determina**|Selecione a medida do grupo de medidas de taxa que contém a taxa de câmbio a ser usada quando as medidas do membro selecionado em **Membro da Conta** forem convertidas.|  
  
 **Hierarquia de contas baseada no tipo**  
 Selecione para aplicar a funcionalidade de conversão de moeda a todos os membros de atributos na hierarquia de contas cuja propriedade `Type` está definida como um tipo de conta especificado.  
  
 Se selecionada, a grade exibirá as opções listadas na tabela a seguir.  
  
|Opção|Descrição|  
|------------|-----------------|  
|**Tipo de conta**|Selecione para incluir funcionalidade de conversão de moeda para o tipo de conta especificado.|  
|**Determina**|Selecione a medida do grupo de medidas de taxa que contém a taxa de câmbio a ser usada ao converter medidas para os membros de atributos usando o tipo de conta selecionado em **Tipo de Conta** .|  
  
## <a name="see-also"></a>Consulte Também  
 [Ajuda F1 do assistente de Business Intelligence](business-intelligence-wizard-f1-help.md)   
 [O designer de cubo &#40;Analysis Services-dados multidimensionais&#41;](cube-designer-analysis-services-multidimensional-data.md)   
 [O designer de dimensão &#40;Analysis Services de dados multidimensionais&#41;](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
