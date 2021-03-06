---
title: Mesclando partições (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- merging partitions [XMLA]
- XMLA, partitions
- partitions [Analysis Services], XML for Analysis
- XML for Analysis, partitions
ms.assetid: 657e1d4d-6d50-40f8-a771-7b20c9d865f8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 65840066d3e95571db511a2015a1bee64aa8d922
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572766"
---
# <a name="merging-partitions-xmla"></a>Mesclando partições (XMLA)
  Se as partições tiverem o mesmo design e estrutura de agregação, você poderá mesclar a partição usando o comando [MergePartitions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/mergepartitions-element-xmla) no XML for Analysis (XMLA). A mesclagem de partições é uma ação importante a ser executada quando você gerencia partições, principalmente as partições que contêm dados históricos divididos por data.  
  
 Por exemplo, um cubo financeiro pode usar duas partições:  
  
-   Uma partição representa dados financeiros do ano atual, usando configurações de armazenamento ROLAP (OLAP relacional) em tempo real para desempenho.  
  
-   Outra partição contém dados financeiros dos anos anteriores, usando configurações de armazenamento MOLAP (OLAP multidimensional) para armazenamento.  
  
 Ambas as partições utilizam configurações de armazenamento diferentes, mas usam o mesmo design de agregação. Em vez de processar o cubo nos anos de dados históricos no final do ano, você pode usar o comando `MergePartitions` para mesclar a partição do ano atual com a partição dos anos anteriores. Isso preservará os dados de agregação sem exibir um processamento completo do cubo potencialmente demorado.  
  
## <a name="specifying-partitions-to-merge"></a>Especificando partições para mesclagem  
 Quando o `MergePartitions` comando é executado, os dados de agregação armazenados nas partições de origem especificadas na propriedade [Source](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla) são adicionados à partição de destino especificada na propriedade [target](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/target-element-xmla) .  
  
> [!NOTE]  
>  A propriedade `Source` pode conter mais de uma referência de objeto de partição. No entanto, a propriedade `Target` não pode.  
  
 Para que sejam mescladas com êxito, as partições especificadas em `Source` e em `Target` devem estar contidas no mesmo grupo de medidas e usar o mesmo design de agregação. Caso contrário, ocorrerá um erro.  
  
 As partições especificadas em `Source` serão excluídas depois que o comando `MergePartitions` for concluído com êxito.  
  
## <a name="examples"></a>Exemplos  
  
### <a name="description"></a>Descrição  
 O exemplo a seguir mescla todas as partições no grupo de medidas **Customer** Counts do cubo **Adventure Works** no banco de dados de exemplo do **Adventure Works DW** na [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] partição **Customers_2004** .  
  
### <a name="code"></a>Código  
  
```  
<MergePartitions xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Sources>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2001</PartitionID>  
    </Source>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2002</PartitionID>  
    </Source>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2003</PartitionID>  
    </Source>  
  </Sources>  
  <Target>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    <CubeID>Adventure Works DW</CubeID>  
    <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
    <PartitionID>Internet_Sales_2004</PartitionID>  
  </Target>  
</MergePartitions>  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Desenvolvendo com XMLA no Analysis Services](developing-with-xmla-in-analysis-services.md)  
  
  
