---
title: Especificando o tipo de dados e o tipo de conteúdo (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 72484d27-3ef1-4f16-813c-2f43231fc2da
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 73ff61dbe439b9f2fb50f3a8004f4e7bcad8369a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683185"
---
# <a name="specifying-the-data-type-and-content-type-basic-data-mining-tutorial"></a>Especificando o tipo de dados e o tipo de conteúdo (Tutorial de mineração de dados básico)
  Agora que você selecionou as colunas a serem usadas na criação da sua estrutura e no treinamento de seus modelos, faça as alterações necessárias nos dados padrão e nos tipos de conteúdo definidos pelo assistente.  
  
#### <a name="review-and-modify-content-type-and-data-type-for-each-column"></a>Revise e modifique o tipo de conteúdo e o tipo de dados de cada coluna.  
  
1.  Na página **especificar conteúdo e tipo de dados das colunas** , clique em **detectar** para executar um algoritmo que determina os tipos de conteúdo e dados padrão para cada coluna.  
  
2.  Examine as entradas nas colunas **tipo de conteúdo** e **tipo de dados** e altere-as, se necessário, para certificar-se de que as configurações sejam as mesmas listadas na tabela a seguir.  
  
     Em geral, o assistente detectará números e atribuirá um tipo de dados numérico apropriado, mas há muitos cenários em que talvez você queira manipular um número como texto. Por exemplo, o **GeographyKey** deve ser tratado como texto, porque seria inadequado executar operações matemáticas nesse identificador.  
  
    |Column|Tipo de conteúdo|Tipo de Dados|  
    |------------|------------------|---------------|  
    |**Endereço linha1**|**Discreto**|**Texto**|  
    |**Endereço Linha2**|**Discreto**|**Texto**|  
    |**Idade**|**Visa**|**Long**|  
    |**Bike Buyer**|**Discreto**|**Long**|  
    |**Distância do Trabalho**|**Discreto**|**Texto**|  
    |**CustomerKey**|**Chave**|**Long**|  
    |**DateLastPurchase**|**Visa**|**Data**|  
    |**Endereço de Email**|**Discreto**|**Texto**|  
    |**Educação em Inglês**|**Discreto**|**Texto**|  
    |**Ocupação em Inglês**|**Discreto**|**Texto**|  
    |**Nome**|**Discreto**|**Texto**|  
    |**Sexo**|**Discreto**|**Texto**|  
    |**Geografia Principal**|**Discreto**|**Texto**|  
    |**Sinalizador do Proprietário da Casa**|**Discreto**|**Texto**|  
    |**Sobrenome**|**Discreto**|**Texto**|  
    |**Estado Civil**|**Discreto**|**Texto**|  
    |**Número de Carros**|**Discreto**|**Long**|  
    |**Número de filhos em casa**|**Discreto**|**Long**|  
    |**Região**|**Discreto**|**Texto**|  
    |**Total de Filhos**|**Discreto**|**Long**|  
    |**Renda Anual**|**Visa**|**Double**|  
  
3.  Clique em **Avançar**.  
  
## <a name="next-task-in-lesson"></a>Próxima tarefa da lição  
 [Especificação de um conjunto de dados de teste para a estrutura &#40;tutorial de mineração de dados básico&#41;](../../2014/tutorials/specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a>Tarefa anterior da lição  
 [Criando uma estrutura de modelo de mineração de mala direta direcionada &#40;tutorial de mineração de dados básico&#41;](../../2014/tutorials/creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Tipos de conteúdo &#40;mineração de dados&#41;](../../2014/analysis-services/data-mining/content-types-data-mining.md)   
 [Tipos de dados &#40;Mineração de dados&#41;](../../2014/analysis-services/data-mining/data-types-data-mining.md)  
  
  
