---
title: Alternar um ponto de interrupção
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c477ab89-a1cd-4f2c-aa7c-40525041100f
author: rothja
ms.author: jroth
ms.openlocfilehash: 72e26e9b1d04bc2eced6bcb6d93d3c86a016d308
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581744"
---
# <a name="toggle-a-breakpoint"></a>Alternar um ponto de interrupção
  O ato de definir um ponto de interrupção em uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] é chamado de alternar um ponto de interrupção.  
  
## <a name="breakpoints"></a>Pontos de interrupção  
 Quando o ponto de interrupção foi definido, ele é representado por um ícone na barra cinza à esquerda da instrução. O ícone é chamado de um glifo de ponto de interrupção. [!INCLUDE[tsql](../../includes/tsql-md.md)] são aplicados a uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] completa. Quando um ponto de interrupção é ativado, o depurador realça a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] associada.  
  
 Se houver várias instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] em uma linha, você poderá alternar um ponto de interrupção para cada instrução. Clicar na barra cinza à esquerda da janela alterna um ponto de interrupção na primeira instrução na linha. Você poderá alternar um ponto de interrupção em uma instrução subsequente realçando qualquer parte da instrução, ou movendo o cursor na instrução, e pressionando F9 ou clicando em **Alternar Ponto de Interrupção** no menu **Depurar** . Se você tiver vários pontos de interrupção em uma linha, haverá somente um glifo de ponto de interrupção na barra cinza à esquerda.  
  
 Depois que um ponto de interrupção for alternado, você poderá executar várias ações no ponto de interrupção, como editar suas propriedades ou desabilitá-las temporariamente. Para obter mais informações, veja [Pontos de interrupção Transact-SQL](transact-sql-breakpoints.md).  
  
## <a name="toggle-a-breakpoint"></a>Alternar um ponto de interrupção  
 **Para alternar um ponto de interrupção em uma instrução Transact-SQL**  
  
1.  Clique na barra cinza à esquerda da instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] .  
  
2.  Outra alternativa é realçar qualquer parte da instrução ou mover o cursor para a instrução, e depois executar uma das ações:  
  
    -   Pressione F9.  
  
    -   No menu **Depurar** , clique em **Alternar Ponto de Interrupção**.  
  
  
