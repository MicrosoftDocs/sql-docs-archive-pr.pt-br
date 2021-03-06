---
title: Guia manipuladores de eventos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.eventhandlerwindow.f1
ms.assetid: 94fc8916-8032-490c-b9d5-ded8b6217e49
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a5f25a9b0d602a3189feab797b7ef9c333decabb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574813"
---
# <a name="event-handlers-tab"></a>Guia Manipuladores de Eventos
  Use a guia **Manipuladores de Eventos** do Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] para criar um fluxo de controle em um pacote [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] . Um manipulador de eventos é executado em resposta a um evento criado pelo pacote ou por uma tarefa ou contêiner no pacote.  
  
## <a name="options"></a>Opções  
 **Executável**  
 Selecione o executável para o qual deseja criar um manipulador de eventos. O executável pode ser o pacote ou uma tarefa ou contêineres no pacote.  
  
 **Manipulador de eventos**  
 Selecione um tipo de manipulador de eventos. Crie o manipulador de eventos, arrastando os itens da **Caixa de Ferramentas**.  
  
 **Delete (excluir)**  
 Selecione um manipulador de eventos e remova-o do pacote, clicando em **Excluir**.  
  
 **Clique aqui para criar um \<event handler name> para o executável \<executable name>**  
 Clique para criar o manipulador de eventos.  
  
 Crie o fluxo de controle arrastando os objetos gráficos que representam as tarefas e os contêiners [!INCLUDE[ssIS](../includes/ssis-md.md)] da **Caixa de Ferramentas** para a superfície de design da guia **Manipuladores de Eventos** e, em seguida, conectando os objetos usando as restrições de precedência para definir a sequência na qual eles serão executados.  
  
 Além disso, para adicionar anotações, clique com o botão direito do mouse na superfície de design e, em seguida, no menu, clique em **Adicionar Anotação**.  
  
## <a name="see-also"></a>Consulte Também  
 [Manipuladores de eventos do SSIS &#40;Integration Services&#41;](integration-services-ssis-event-handlers.md)   
 [Fluxo de Controle](control-flow/control-flow.md)   
 [Designer SSIS](ssis-designer.md)   
 [Manipuladores de eventos do SSIS &#40;Integration Services&#41;](integration-services-ssis-event-handlers.md)  
  
  
