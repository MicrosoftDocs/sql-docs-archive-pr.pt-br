---
title: 'Propriedades do alerta: novo alerta (página Opções) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.options.f1
ms.assetid: 6e4f41aa-832d-46ba-b6b5-cf1d3b15d33f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a1507372aa1516c2a88b8682faa77a7d57e58f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683919"
---
# <a name="alert-properties-new-alert-options-page"></a>Propriedades do Alerta: Novo Alerta (página Opções)
  Use esta página para exibir e modificar opções de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertas de agente.  
  
## <a name="options"></a>Opções  
 **Mensagens**  
 Inclua texto de erro do evento, se houver, em notificações de email.  
  
 **Pager**  
 Inclua texto de erro do evento, se houver, em notificações de pager.  
  
 **Net send**  
 Inclua texto de erro do evento, se houver, em notificações enviadas pela net.  
  
 **Mensagem de notificação adicional para enviar**  
 Digite qualquer texto adicional para incluir em mensagens de notificação.  
  
 **Atraso entre as respostas**  
 Especifique um intervalo para ocorrências repetidas do evento. Alguns eventos podem acontecer com frequência durante um curto intervalo de tempo. Nesse caso, você pode desejar saber que o evento ocorreu, mas talvez não queira uma resposta para cada evento. Use esta opção para especificar um tempo limite. Com um atraso, depois que o alerta responde a um evento, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent aguarda o atraso especificado antes de responder novamente, independentemente de o evento ocorrer durante o atraso.  
  
 **Alguns**  
 Especifique um intervalo em minutos. Para responder todas as vezes que o evento ocorrer, especifique 0 minuto e 0 segundo.  
  
 **Seg**  
 Especifique um intervalo em segundos. Para responder todas as vezes que o evento ocorrer, especifique 0 minuto e 0 segundo.  
  
## <a name="see-also"></a>Consulte Também  
 [Alertas](alerts.md)  
  
  
