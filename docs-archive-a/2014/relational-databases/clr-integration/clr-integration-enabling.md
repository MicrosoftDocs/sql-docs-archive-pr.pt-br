---
title: Habilitando a integração CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- clr enabled option
- common language runtime [SQL Server], enabling
ms.assetid: eb3e9c64-7486-42e7-baf6-c956fb311a2c
author: rothja
ms.author: jroth
ms.openlocfilehash: d7187906f1376deb81ca7ff4770af7b12b63c022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682274"
---
# <a name="enabling-clr-integration"></a>Habilitando integração CLR
  O recurso de integração CLR (common language runtime) está desativado por padrão, e deve ser habilitado para usar objetos implementados com a integração CLR. Para habilitar a integração CLR, use a opção **CLR Enabled** do procedimento armazenado **sp_configure** :  
  
```  
  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'clr enabled', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
 Você pode desabilitar a integração CLR definindo a opção **CLR Enabled** como 0. Quando você desabilitar integração de CLR, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] deixará de executar todas as rotinas de CLR e descarregará todos os domínios de aplicativo.  
  
> [!NOTE]  
>  Para habilitar a integração CLR, você deve ter a permissão ALTER SETTINGS no nível do servidor, que é mantida implicitamente por membros das funções de servidor fixas **sysadmin** e **ServerAdmin** .  
  
> [!NOTE]  
>  Computadores configurados com grandes quantidades de memória e um número grande de processadores podem falhar ao carregar o recurso de integração CLR do SQL Server na inicialização do servidor. Para resolver esse problema, inicie o servidor usando a opção de inicialização de serviço **-gmemory_to_reserve** [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e especifique um valor de memória grande o suficiente. Para obter mais informações, consulte [Opções de inicialização do serviço Mecanismo de Banco de Dados](../../database-engine/configure-windows/database-engine-service-startup-options.md).  
  
> [!NOTE]  
>  Não há suporte para a execução de CLR (common language runtime) com lightweight pooling. Antes de habilitar integração CLR, você deve desabilitar o lightweight pooling. Para saber mais, veja [lightweight pooling Server Configuration Option](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md).  
  
## <a name="see-also"></a>Consulte Também  
 [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)   
 [Opção clr enabled de configuração de servidor](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md)   
 [RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql)   
 [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql)   
 [Funções de nível de servidor](../security/authentication-access/server-level-roles.md)  
  
  
