---
title: Propriedades do SQL Server Browser (guia Logon) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c77871ec-c2f4-4e4a-9a10-5aeb4ae70507
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0c1f7d0cfd9e9b05a2a04f3c3e9efba687522298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678465"
---
# <a name="sql-server-browser-properties-log-on-tab"></a>Propriedades do Navegador do SQL Server (guia Fazer Logon)
  O programa Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é executado como um serviço no servidor. O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser escuta as solicitações de entrada de recursos do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e fornece informações sobre as instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instaladas no computador.  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] O Navegador escuta em uma porta UDP e aceita as solicitações não autenticadas usando o protocolo SSRP do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 A alteração da senha de uma conta entra em vigor imediatamente sem a reinicialização do serviço.  
  
## <a name="options"></a>Opções  
 **Conta Sistema Local**  
 Execute o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no contexto de segurança da conta Sistema Local. Quando possível, use uma conta de baixa permissão.  
  
 **Esta conta**  
 Especifique um local ou conta de usuário do domínio que utilize Autenticação do Windows. É recomendável usar uma conta de usuário do domínio com direitos mínimos para serviços. Para obter informações sobre como selecionar uma conta, consulte "Configurando as contas de serviço do Windows" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 **Procurar**  
 Procure um usuário ou uma entidade de segurança incorporada.  
  
> [!IMPORTANT]  
>  Use uma conta da baixa-permissão. Para obter informações sobre as permissões necessárias para o Serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte a seção Segurança do tópico [Serviço Navegador do SQL Server](../../../2014/tools/configuration-manager/sql-server-browser-service.md).  
  
 **Senha**  
 Digite a senha da entidade de segurança.  
  
 **Confirmar senha**  
 Confirme a senha da entidade de segurança.  
  
 **Status de serviço**  
 Indica se este serviço está sendo executado, se está parado ou desabilitado. " **...** " indica que há uma alteração de estado pendente.  
  
 **Iniciar**  
 Iniciar o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 **Parar**  
 Parar o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 **Pausar**  
 Pausar o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 **Retomar**  
 Retomar um serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em pausa.  
  
## <a name="see-also"></a>Consulte Também  
 [Serviço Navegador do SQL Server](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
