---
title: IRowsetFastLoad (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- IRowsetFastLoad interface
ms.assetid: d19a7097-48d9-409a-aff9-277891b7aca7
author: rothja
ms.author: jroth
ms.openlocfilehash: 7ecf72f0015d9ed197b3b7a33d4f9bb3246134b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582429"
---
# <a name="irowsetfastload-ole-db"></a>IRowsetFastLoad (OLE DB)
  A `IRowsetFastLoad` interface expõe o suporte para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] operações de cópia em massa baseadas em memória. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Os consumidores do provedor de OLE DB de cliente nativo usam a interface para adicionar dados rapidamente a uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabela existente.  
  
 Se você definir SSPROP_ENABLEFASTLOAD como VARIANT_TRUE para uma sessão, não poderá ler dados de conjuntos de linhas subsequentemente passados como retorno dessa sessão. Quando SSPROP_ENABLEFASTLOAD for definido como VARIANT_TRUE, todos os conjuntos de linhas criados na sessão serão do tipo IRowsetFastLoad. Os conjuntos de linhas IRowsetFastLoad não dão suporte à funcionalidade de fetch de conjuntos de linhas; portanto, os dados desses conjuntos de linhas não podem ser lidos.  
  
## <a name="in-this-section"></a>Nesta seção  
  
|Método|Descrição|  
|------------|-----------------|  
|[IRowsetFastLoad::Commit &#40;OLE DB&#41;](irowsetfastload-commit-ole-db.md)|Marca o término de um lote de linhas inseridas e escreve as linhas na tabela [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .|  
|[IRowsetFastLoad::InsertRow &#40;OLE DB&#41;](irowsetfastload-insertrow-ole-db.md)|Adiciona uma linha ao conjunto de linhas de cópia em massa.|  
  
## <a name="see-also"></a>Consulte Também  
 [Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md)   
 [Copiar Dados em massa usando o IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md)   
 [Enviar dados BLOB ao SQL SERVER usando IROWSETFASTLOAD e ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md)  
  
  
