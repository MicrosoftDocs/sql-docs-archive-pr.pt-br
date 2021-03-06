---
title: Solucionar problemas de indexação de texto completo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- indexes [full-text search]
- troubleshooting [SQL Server], full-text search
- troubleshooting [full-text search]
ms.assetid: 964c43a8-5019-4179-82aa-63cd0ef592ef
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: eaca5fcf2dfbac57fc6d3ba6178251927d15aba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583461"
---
# <a name="troubleshoot-full-text-indexing"></a>Solucionar problemas na indexação de texto completo
     
##  <a name="troubleshoot-full-text-indexing-failures"></a><a name="failure"></a> Solucionar problemas de falhas na indexação de texto completo  
 Ao popular ou manter um índice de texto completo, o indexador de texto completo, pelas razões descritas a seguir, talvez falhe ao indexar uma ou mais linhas. Esses erros em nível de linha não impedem a conclusão da população. O indexador ignora essas linhas, o que significa que não é possível consultar seu conteúdo.  
  
 As falhas de indexação podem ocorrer quando:  
  
-   O indexador não consegue localizar ou carregar um filtro ou componente do separador de palavra. Essa falha pode ocorrer se a linha da tabela tiver um formato de documento ou conteúdo em idioma não registrado com a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Essa falha também pode ocorrer se o componente do filtro ou o separador de palavra registrado não estava assinado ou se houve falha na verificação de assinatura ao carregar.  
  
-   Um componente, como um separador de palavra ou filtro, falha e retorna um erro para o indexador, o que pode ocorrer se o documento a indexar estiver corrompido e o filtro não conseguir extrair seu texto. Isso também pode ocorrer quando um componente não puder tratar o conteúdo de uma única linha acima de um determinado tamanho, devido a limites de memória no host do daemon do filtro (fdhost.exe).  
  
 Para cada falha do nível de linha, o log de rastreamento contém detalhes da razão da falha. As contas de erro são resumidas no término de uma população completa ou com incremento.  
  
 Há outras falhas que podem impactar o próprio processo de indexação e impedir a conclusão da população:  
  
-   O índice de texto completo excede o limite para o número de linhas que podem ser contidas em um catálogo de texto completo.  
  
-   Um índice clusterizado ou um índice de chave de texto completo da tabela em indexação são alterados, descartados ou recriados.  
  
-   Uma falha no hardware ou disco corrompido resulta em corrupção do catálogo de texto completo.  
  
-   Um grupo de arquivo que contém a tabela cujo texto completo passa por indexação fica offline ou é do tipo somente leitura.  
  
 Você deve exibir o registro de rastreamento no final de qualquer operação significativa de indexação de texto completo ou ao descobrir que a população não foi concluída.  
  
### <a name="unsigned-components"></a>Componentes não assinados  
 Por padrão, o indexador de texto completo requer os filtros e separadores de palavras que carrega ao assinar. Se não estiverem assinados, o que algumas vezes é o caso quando os componentes personalizados são instalados, é necessário configurar o indexador de texto completo para ignorar a verificação de assinatura.  
  
> [!IMPORTANT]  
>  Ignorar a verificação de assinatura torna menos segura a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Recomendamos assinar quaisquer componentes implementados ou garantir que os componentes que você adquirir estão assinados. Para obter informações sobre componentes de assinatura, veja [sp_fulltext_service &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).  
  

  
##  <a name="full-text-index-in-inconsistent-state-after-transaction-log-restored"></a><a name="state"></a> Índice de texto completo em estado inconsistente após o log de transações ser restaurado  
 Ao restaurar o log de transações de um banco de dados, é possível que apareça um aviso indicando que o índice de texto completo não está em um estado consistente. O motivo pelo qual isso ocorre é que o índice de texto completo de uma tabela foi modificado após ter sido feito o backup do banco de dados. Para trazer o índice de texto completo a um estado consistente, você deve executar uma população completa (rastreamento) na tabela. Para obter mais informações, veja [Popular índices de texto completo](../indexes/indexes.md).  
  

  
## <a name="see-also"></a>Consulte Também  
 [ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql)   
 [Popular índices de texto completo](../indexes/indexes.md)  
  
  
