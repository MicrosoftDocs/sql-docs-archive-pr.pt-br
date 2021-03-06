---
title: 'Etapa 4: adicionar uma tarefa de fluxo de dados ao pacote | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 96af3073-8f11-4444-b934-fe8613a2d084
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4fda1de99e9fcaa683f9063e2feb1b71886a5cd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574137"
---
# <a name="step-4-adding-a-data-flow-task-to-the-package"></a>Etapa 4: Adicionar uma tarefa de fluxo de dados ao pacote
  Depois de criar os gerenciadores de conexões para os dados de origem e destino, a próxima tarefa é adicionar a tarefa Fluxo de Dados ao seu pacote. Essa tarefa encapsula o mecanismo de fluxo de dados que move dados entre as origens e os destinos, além de fornecer funcionalidade para transformar, limpar e modificar os dados à medida que são movidos. A tarefa Fluxo de Dados é onde a maioria do trabalho de um processo de extração, transformação e carregamento (ETL) acontece.  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]separa o fluxo de dados do fluxo de controle.  
  
### <a name="to-add-a-data-flow-task"></a>Adicionar uma tarefa Fluxo de Dados  
  
1.  Clique na guia **Fluxo de Controle** .  
  
2.  Na **Caixa de Ferramentas do SSIS**, expanda **Favoritos**e arraste uma **Tarefa de Fluxo de Dados** até a superfície de design da guia **Fluxo de Controle** .  
  
    > [!NOTE]  
    >  Se a Caixa de Ferramentas do SSIS não estiver disponível, no menu principal, selecione Caixa de Ferramentas do SSIS para exibir a Caixa de Ferramentas do SSIS.  
  
3.  Na superfície de design do **fluxo de controle** , clique com o botão direito do mouse na tarefa de **fluxo de dados**recém adicionada, clique em **renomear**e altere o nome para `Extract Sample Currency Data` .  
  
     É uma boa ideia fornecer nomes exclusivos a todos os componentes que você adiciona a uma superfície de design. Para facilitar o uso e a sustentabilidade, os nomes devem descrever a função que cada componente executa. Seguir estas diretrizes de nomeação permite que seus pacotes [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sejam documentados automaticamente. Outra forma para documentar seus pacotes é usar anotações. Para obter mais informações sobre anotações, consulte [usar anotações em pacotes](use-annotations-in-packages.md).  
  
4.  Clique com o botão direito do mouse na tarefa fluxo de dados, clique em **Propriedades**e, na janela Propriedades, verifique se a `LocaleID` propriedade está definida como **Inglês (Estados Unidos)**.  
  
## <a name="next-task-in-lesson"></a>Próxima tarefa da lição  
 [Etapa 5: Adicionar e configurar a fonte de arquivo simples](lesson-1-5-adding-and-configuring-the-flat-file-source.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Tarefa de Fluxo de Dados](control-flow/data-flow-task.md)  
  
  
