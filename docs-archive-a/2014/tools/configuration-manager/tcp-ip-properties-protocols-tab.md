---
title: Propriedades TCP-IP (guia protocolos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- TCP/IP [SQL Server], configuration options
ms.assetid: 007638fc-3a24-4460-adbe-545ded5d6f88
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1d5bc28faddae9a86a6636b56b907b57a2d8711a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569798"
---
# <a name="tcp---ip-properties-protocols-tab"></a>Propriedades TCP-IP (guia protocolos)
  Use a caixa de diálogo **Propriedades do TCP/IP** para configurar as opções do protocolo TCP/IP. Clique em **TCP/IP** no painel esquerdo, para mostrar configurações individuais de endereço IP no painel de detalhes.  
  
 O Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve ser reiniciado para que as alterações entrem em vigor.  
  
## <a name="options"></a>Opções  
 **Enabled**  
 Os valores possíveis são **Sim** e **Não**.  
  
 **Keep Alive**  
 Especifique o intervalo (em milissegundos) no qual os pacotes keep-alive são transmitidos para verificar se o computador remoto de uma conexão ainda está disponível.  
  
 **Listen All**  
 Especifique se o SQL Server escutará em todos os endereços IP associados às placas de rede no computador. Se for definido como **No**, configure cada endereço IP separadamente usando a caixa de diálogo de propriedades de cada endereço IP. Se for definido como **Yes**, as configurações da caixa de propriedades **IPAll** se aplicarão a todos os endereços IP. O valor padrão é **Yes**.  
  
 **No Delay**  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não implementa alterações nesta propriedade.  
  
## <a name="see-also"></a>Consulte Também  
 [Escolhendo um protocolo de rede](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)   
 [Criando uma cadeia de conexão válida usando TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
  
