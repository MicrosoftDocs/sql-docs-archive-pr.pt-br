---
title: Fazer check-out de arquivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- Visual Studio.SourceControl.CheckOutDialog
helpviewer_keywords:
- checking out files
ms.assetid: cc033727-51bb-4b58-a12b-8977ce61ff56
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 151f554742bd6c381b27b58155d3f0e40e9eeb0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575368"
---
# <a name="check-out-files"></a>Fazer check-out de arquivos
  A menos que você tenha configurado o ambiente do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para permitir a edição de arquivos que tenham feito check-in, faça o check-out de um arquivo antes de modificá-lo. Quando você faz o check-out de um arquivo, uma cópia da versão de arquivo é copiada no disco local e o atributo somente leitura é removido.  
  
 Você pode fazer o check-out de arquivos em modo exclusivo ou compartilhado. Quando você fizer o check-out de um arquivo exclusivamente, nenhum outro usuário poderá fazer o check-out do arquivo até você concluir seu check-out. Quando você faz o check-out de um arquivo no modo compartilhado, outros usuários podem fazer o check-out e modificar o arquivo; talvez seja necessário mesclar a versão de check-out com as versões criadas por outros usuários.  
  
 Use o comando **Check-Out** para fazer o check-out de arquivos e projetos com controle do código-fonte. Se você usar esse comando para fazer o check-out de uma solução ou projeto, todos os arquivos na solução ou no projeto também serão submetidos a check-out. No entanto, o check-out de um arquivo de código-fonte individual não resulta no check-out do projeto ou da solução à qual ele pertence.  
  
> [!NOTE]  
>  Se o banco de dados do [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe do projeto for configurado para permitir vários check-outs e você quiser fazer o check-out de um arquivo exclusivamente, desmarque a opção **Permitir múltiplos check-outs** na caixa de diálogo **Opções Avançadas de Check-Out** antes de fazer o check-out do arquivo. Você deve reiniciar o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para que essa configuração entre em vigor.  
  
### <a name="to-check-out-a-file"></a>Para fazer check-out de um arquivo  
  
1.  No Gerenciador de Soluções, selecione o projeto ou o arquivo.  
  
2.  No menu **Arquivo** , aponte para **Controle do Código-Fonte**e clique em **Check-Out para Edição**.  
  
3.  Se a caixa de diálogo **check-out para editar** for exibida, selecione os itens desejados e clique em **fazer check-out**. Se você tiver configurado o [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] ambiente para não exibir a caixa de diálogo **check-out** , os itens selecionados em Gerenciador de soluções e quaisquer filhos que eles possam ter terão check-out imediatamente.  
  
     **Fazer Check-out**  
     Faça check-out de todos os itens selecionados.  
  
     **Colunas**  
     Identifique as colunas a serem exibidas e a ordem em que elas são exibidas.  
  
     **Comentários**  
     Especifique um comentário a ser associado com a operação de check-out.  
  
     **Não mostrar a caixa de diálogo Check-out ao fazer check-out dos itens**  
     Suprima a caixa de diálogo durante operações de check-out.  
  
     **Exibição Simples**  
     Exiba os itens de check-out como listas simples em suas conexões de controle do código fonte.  
  
     **Editar**  
     Modificar um item sem verificá-lo. O botão **Editar** será exibido somente se você tiver [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] configurado o para dar suporte à edição de arquivos com check-in.  
  
     **Nome**  
     Exibe os nomes dos itens disponíveis para check-out. Os itens selecionados são exibidos com caixas de seleção ao lado. Se não quiser fazer check-out de um item em particular, desmarque sua caixa de seleção.  
  
     **Opções**  
     Exibe opções de check-out específico de plug-ins de controle do código fonte quando a seta à direita do botão é clicada.  
  
     **Sort**  
     Classifique a ordem das colunas exibidas.  
  
     **Exibição de árvore**  
     Exiba a hierarquia de pastas e arquivos do item de check-out.  
  
## <a name="see-also"></a>Consulte Também  
 [Editar arquivos com check-in](../../2014/database-engine/edit-checked-in-files.md)   
 [Fazer check-out automático de arquivos após editar](../../2014/database-engine/automatically-check-out-files-upon-edit.md)   
 [Desfazer check-outs](../../2014/database-engine/undo-checkouts.md)   
 [Gerenciar check-outs](../../2014/database-engine/manage-checkouts.md)  
  
  
