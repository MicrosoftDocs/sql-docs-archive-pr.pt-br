---
title: Protocolos de cliente – propriedades TCP e IP (guia Protocolo) | Microsoft Docs
description: Saiba como especificar as opções de TCP/IP em Microsoft SQL Server Configuration Manager, como o parâmetro Keep Alive e o número da porta padrão.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- TCP/IP [SQL Server], client protocols
- client protocols [SQL Server]
ms.assetid: d04f1bce-069c-4a02-b561-c87c3282be36
author: rothja
ms.author: jroth
ms.openlocfilehash: dfcf0348dc863970384a40cc9e773481adeedb35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683873"
---
# <a name="client-protocols---tcp-and-ip-properties-protocol-tab"></a>Protocolos de Cliente – Propriedades de TCP e IP (guia Protocolo)
  No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, use a guia **Protocolo** na caixa de diálogo **Propriedades de TCP/IP** para exibir ou especificar as opções a seguir. Para se conectar a uma porta diferente, digite o número da porta na caixa **Pipe Padrão** . Para obter mais informações sobre cadeias de conexão, consulte [Criando uma cadeia de conexão válida usando TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md).  
  
## <a name="options"></a>Opções  
 **Pipe Padrão**  
 Especifica a porta que a biblioteca de rede TCP/IP usará para tentar se conectar à instância de destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. O valor padrão da porta é 1433.  
  
 Ao conectar a uma instância padrão do [!INCLUDE[ssDE](../../includes/ssde-md.md)], o cliente usa esse valor. Se uma instância padrão tiver sido configurada para escutar em uma porta diferente, altere esse valor para esse número de porta.  
  
 Ao se conectar a uma instância nomeada do [!INCLUDE[ssDE](../../includes/ssde-md.md)], o cliente tentará obter o número da porta no Serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executado no computador servidor. Se o Serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não estiver sendo executado, o número da porta deverá ser fornecido por meio dessa configuração, ou como parte da cadeia de conexão.  
  
 **Habilitado**  
 Os valores possíveis são **Sim** e **não**.  
  
 **Keep Alive**  
 Este parâmetro (em milissegundos) controla a frequência das tentativas do TCP de verificar se uma conexão ociosa ainda está intacta enviando um pacote **KEEPALIVE** . O padrão é 30.000 milissegundos.  
  
 **Intervalo de Atividade**  
 Este parâmetro (em milissegundos) determina o intervalo que separa novas transmissões de **KEEPALIVE** até que uma resposta seja recebida. O padrão é 1.000 milissegundos.  
  
## <a name="see-also"></a>Consulte Também  
 [Escolhendo um protocolo de rede](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)   
 [Novo alias &#40;guia alias&#41;](../../../2014/tools/configuration-manager/new-alias-alias-tab.md)   
 [Propriedades &#60;Alias&#62; &#40;Guia Alias&#41;](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md)  
  
  
