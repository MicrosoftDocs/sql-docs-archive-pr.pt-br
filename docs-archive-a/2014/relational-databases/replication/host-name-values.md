---
title: Valores HOST_NAME | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.hostnamevalue.f1
ms.assetid: 21548f08-2910-4a55-baac-b911ba9afaf1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 67d01df05c8d56fd435eb0ee1b42ba2da6a312ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569888"
---
# <a name="host_name-values"></a>Valores HOST_NAME
  Asp ublicações de mesclagem com filtros com parâmetros usam a função SUSER_SNAME() e/ou a função HOST_NAME() para filtrar dados. A função é especificada no Assistente para Nova Publicação ou na caixa de diálogo **Propriedades de Publicação** .  
  
 Por padrão, a função HOST_NAME() retorna o nome do computador que conecta ao Publicador. É comum substituir esse valor, ao usar filtros com parâmetros, fornecendo um valor nessa página do assistente. Uma função HOST_NAME() retorna o valor que você especifica em lugar do nome do computador. Para mais informações, consulte a seção “Substituindo o valor do HOST_NAME()” de [Filtros de linha com parâmetros](merge/parameterized-filters-parameterized-row-filters.md).  
  
> [!NOTE]  
>  Se substituir HOST_NAME(), todas as chamadas para a função HOST_NAME() retornarão o valor que você especificou. Assegure-se de que outros aplicativos não estão dependendo de que HOST_NAME() retorne o nome do computador.  
  
## <a name="options"></a>Opções  
 **Propriedades da assinatura**  
 Insira um valor para cada Assinante na coluna **Valor de HOST_NAME** ou aceite o padrão, que é o nome do computador do Assinante.  
  
## <a name="see-also"></a>Consulte Também  
 [Create a Pull Subscription](create-a-pull-subscription.md)   
 [Create a Push Subscription](create-a-push-subscription.md)   
 [Exibir e modificar propriedades de assinatura pull](view-and-modify-pull-subscription-properties.md)   
 [Exibir e modificar propriedades de assinatura push](view-and-modify-push-subscription-properties.md)   
 [HOST_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/host-name-transact-sql)   
 [Assinar publicações](subscribe-to-publications.md)  
  
  
