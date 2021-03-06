---
title: Metadados (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- user-defined metadata [Master Data Services], about user-defined metadata
- metadata [Master Data Services], about metadata
- metadata [Master Data Services]
- user-defined metadata [Master Data Services]
ms.assetid: ac1aabe3-d8d4-4d7a-8954-50ee3c185d81
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 39ab95b7925306febb551962495da7ec9751589b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680021"
---
# <a name="metadata-master-data-services"></a>Metadados (Master Data Services)
  No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], metadados definidos pelo usuário são informações usadas para descrever objetos de modelo. Por exemplo, você pode acompanhar os proprietários de um modelo ou entidade específicos ou acompanhar os sistemas de origem que fornecem dados a uma entidade.  
  
 Os metadados definidos pelo usuário são gerenciados por um modelo chamado **metadados**. Esse modelo é incluído automaticamente quando o [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] é instalado e é semelhante a todos os outros modelos do MDS, exceto pelo fato de que você não pode criar versões dele.  
  
 Depois de popular o modelo de Metadados com metadados definidos pelo usuário, você pode incluí-lo em exibições de assinatura para que seja consumido por sistemas assinantes.  
  
## <a name="metadata-entities"></a>Entidades de metadados  
 O modelo Metadados inclui cinco entidades, cada uma representando um tipo de objeto de modelo de dados mestres que oferece suporte a metadados definidos pelo usuário. Por exemplo, a entidade **modelo de definição de metadados** contém membros que representam modelos e a entidade de definição de metadados de **atributo** tem membros que representam todos os atributos em todos os modelos.  
  
 Para definir metadados para um objeto de modelo, popule um destes atributos de membro. Por exemplo, na entidade de **definição de metadados de entidade** , você pode preencher o atributo de descrição do membro de preço com o texto: **o preço do produto quando vendido a um cliente**.  
  
 Os membros do modelo Metadados são atualizados automaticamente sempre que objetos de modelo que oferecem suporte a metadados definidos pelo usuário são adicionados ou excluídos.  
  
 O modelo de Metadados não pode ter controle de versão, ter sinalizadores de versão adicionados ou alterados, nem ser salvo como um pacote de implantação de modelo. No entanto, ele tem as mesmas outras funcionalidades disponíveis para outros modelos de dados mestre. Por exemplo, você pode implementar um conjunto de regras de negócio no modelo de Metadados para impor políticas de dados.  
  
## <a name="customizing-your-metadata-model"></a>Personalizando seu modelo de metadados  
 Cada entidade de definição de metadados inclui os atributos Nome, Código e Descrição. Você pode criar atributos adicionais para mais descrever seus objetos de modelo com mais detalhes.  
  
 Por exemplo, você pode criar:  
  
-   Um atributo baseado em domínio chamado Proprietário, que você usa para acompanhar o proprietário de cada objeto de modelo.  
  
-   Um atributo de forma livre chamado Data da Última Revisão, que você usa para acompanhar a data que um objeto foi revisado pela última vez pelo proprietário.  
  
-   Um atributo baseado em domínio chamado fontes, que você usa para acompanhar e gerenciar os sistemas de origem que interagem com a [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] instância do.  
  
## <a name="related-tasks"></a>Related Tasks  
  
|Descrição da tarefa|Tópico|  
|----------------------|-----------|  
|Adicionar metadados a um objeto de modelo.|[Adicionar metadados &#40;Master Data Services&#41;](add-metadata-master-data-services.md)
|&nbsp;|&nbsp;|
  
## <a name="related-content"></a>Conteúdo relacionado  
  
-   [Exportando dados &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md)  
  
  
