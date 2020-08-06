---
title: Criar Rowsets com ICommand::Execute | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowsets [OLE DB], creating
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets, creating
- Execute method
ms.assetid: 9b530b7d-8165-49d4-a978-5ced17c6705e
author: rothja
ms.author: jroth
ms.openlocfilehash: f4403ba79fada44d9eca47b533a718fe7167689d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684688"
---
# <a name="creating-rowsets-with-icommandexecute"></a><span data-ttu-id="711e5-102">Criando conjuntos de linhas com ICommand::Execute</span><span class="sxs-lookup"><span data-stu-id="711e5-102">Creating Rowsets with ICommand::Execute</span></span>
  <span data-ttu-id="711e5-103">Para conjuntos de linhas criados usando o método **ICommand::Execute**, as propriedades que você deseja obter no conjunto de linhas resultante podem restringir o texto do comando.</span><span class="sxs-lookup"><span data-stu-id="711e5-103">For rowsets created by using the **ICommand::Execute** method, the properties that you want in the resulting rowset can constrain the text of the command.</span></span> <span data-ttu-id="711e5-104">Isto é especialmente crítico para consumidores que dão suporte a texto de comando dinâmico.</span><span class="sxs-lookup"><span data-stu-id="711e5-104">This is especially critical for consumers that support dynamic command text.</span></span>  
  
 <span data-ttu-id="711e5-105">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo não pode usar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursores para dar suporte aos resultados de vários conjuntos de linhas gerados por muitos comandos.</span><span class="sxs-lookup"><span data-stu-id="711e5-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider cannot use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursors to support the multiple-rowset results generated by many commands.</span></span> <span data-ttu-id="711e5-106">Se um consumidor solicitar um conjunto de linhas que exigir suporte de cursor do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ocorrerá um erro se o texto do comando gerar mais de um só conjunto de linhas como seu resultado.</span><span class="sxs-lookup"><span data-stu-id="711e5-106">If a consumer requests a rowset requiring [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursor support, an error occurs if the command text generates more than a single rowset as its result.</span></span> <span data-ttu-id="711e5-107">Confira mais informações em [Comandos que geram resultados de vários conjuntos de linhas](../native-client-ole-db-commands/commands-generating-multiple-rowset-results.md).</span><span class="sxs-lookup"><span data-stu-id="711e5-107">For more information, see [Commands Generating Multiple-Rowset Results](../native-client-ole-db-commands/commands-generating-multiple-rowset-results.md).</span></span>  
  
 <span data-ttu-id="711e5-108">Os [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conjuntos de linhas do provedor de OLE DB de cliente nativo rolável são suportados pelos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursores.</span><span class="sxs-lookup"><span data-stu-id="711e5-108">Scrollable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets are supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursors.</span></span> <span data-ttu-id="711e5-109">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] indica limitações sobre cursores que são sensíveis às alterações feitas por outros usuários do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="711e5-109">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] imposes limitations on cursors that are sensitive to changes made by other users of the database.</span></span> <span data-ttu-id="711e5-110">Especificamente, as linhas em alguns cursores não podem ser ordenadas e a tentativa de criar um conjunto de linhas usando um comando que contenha uma cláusula SQL ORDER BY pode falhar.</span><span class="sxs-lookup"><span data-stu-id="711e5-110">Specifically, the rows in some cursors cannot be ordered, and trying to create a rowset by using a command that contains an SQL ORDER BY clause can fail.</span></span> <span data-ttu-id="711e5-111">Para obter mais informações, confira [Conjuntos de linha e cursores do SQL Server](rowsets-and-sql-server-cursors.md).</span><span class="sxs-lookup"><span data-stu-id="711e5-111">For more information, see [Rowsets and SQL Server Cursors](rowsets-and-sql-server-cursors.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="711e5-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="711e5-112">See Also</span></span>  
 [<span data-ttu-id="711e5-113">Conjuntos de linhas</span><span class="sxs-lookup"><span data-stu-id="711e5-113">Rowsets</span></span>](rowsets.md)  
  
  