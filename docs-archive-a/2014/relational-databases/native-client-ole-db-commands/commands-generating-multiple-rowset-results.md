---
title: Comandos que geram resultados de vários conjuntos de linhas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- multiple rowsets
- rowsets [OLE DB], multiple
- SQL Server Native Client OLE DB provider, commands
- SQL Server Native Client OLE DB provider, multiple rowsets
- commands [OLE DB]
- multiple-rowset results
ms.assetid: 4567668d-35fd-4162-b61f-f7536862cdcb
author: rothja
ms.author: jroth
ms.openlocfilehash: 8b42a89c0b043e4c72e8b5634cf70e16b435167a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678732"
---
# <a name="commands-generating-multiple-rowset-results"></a>Comandos que geram resultados de vários conjuntos de linhas
  O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo pode retornar vários conjuntos de linhas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instruções. As instruções do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retornam resultados de vários conjuntos de linhas nas seguintes condições:  
  
-   Instruções SQL processadas em lotes são enviadas como um único comando.  
  
-   Os procedimentos armazenados implementam um lote de instruções SQL.  
  
## <a name="batches"></a>Lotes  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo reconhece o caractere ponto e vírgula como um delimitador de lote para instruções SQL:  
  
```  
WCHAR*       wSQLString = L"SELECT * FROM Categories; "  
                          L"SELECT * FROM Products";  
```  
  
 Enviar várias instruções SQL em um único lote é mais eficiente do que executar cada instrução SQL separadamente. O envio de um lote reduz as viagens de ida e volta de rede do cliente para o servidor.  
  
## <a name="stored-procedures"></a>Procedimentos armazenados  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retorna um conjunto de resultados para cada instrução em um procedimento armazenado, assim a maioria dos procedimentos armazenados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retorna vários conjuntos de resultados.  
  
## <a name="in-this-section"></a>Nesta seção  
  
-   [Usando IMultipleResults para processar vários conjuntos de resultados](using-imultipleresults-to-process-multiple-result-sets.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Comandos](commands.md)  
  
  
