---
title: Caixa de diálogo Propriedades do conjunto de, campos | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasetproperties.fields.f1
- "10140"
ms.assetid: e1367556-736e-4a6b-b9e7-10432a3e50b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1b9d315f85751c0f73896e809a522613fefece5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570539"
---
# <a name="dataset-properties-dialog-box-fields"></a>Caixa de diálogo Propriedades do Conjunto de Dados, Campos
  Selecione **Campos** na caixa de diálogo **Propriedades do Conjunto de Dados** para alterar a coleção de campos para o conjunto de dados de relatório. A lista de campos é preenchida automaticamente, mas você pode usar os **Campos** para adicionar, editar e excluir campos calculados e consultas.  
  
## <a name="options"></a>Opções  
 **Adicionar**  
 Adicione um novo campo de consulta ou campo calculado ao conjunto de dados.  
  
 **Excluir**  
 Exclua o campo selecionado do conjunto de dados.  
  
 **Nome do campo**  
 Digite um nome para o campo. O campo deve ser exclusivo no conjunto de dados. Para cada campo existente na consulta de conjunto de dados, o nome é populado previamente.  
  
 **Origem de Campo**  
 Insira um valor para o campo.  
  
 Para um campo calculado, a origem do campo deve ter o nome de um campo existente recuperado pela consulta do conjunto de dados ou uma expressão criada por você. Por exemplo, para criar um campo que represente 10 vezes o valor no campo de consulta Sales, use a expressão `=10 * Fields!Sales.Value`.  
  
 Para um campo de consulta, a origem do campo deve ter o nome de um campo existente recuperado pela consulta de conjunto de dados.  
  
 **Expressão (fx)**  
 Adicione ou altere uma expressão para o campo calculado. Esse botão só é exibido quando você clica em **Adicionar** e seleciona **Campo Calculado**.  
  
## <a name="see-also"></a>Consulte Também  
 [Coleção de campos de conjuntos de dados &#40;Construtor de Relatórios e SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md)   
 [Adicionar dados a um relatório &#40;Construtor de Relatórios e SSRS&#41;](report-data/report-datasets-ssrs.md)   
 [Expressões &#40;Construtor de Relatórios e SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md)  
  
  
