---
title: Propriedades da fonte de dados (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, data source properties
- properties [OLE DB]
- data source properties [OLE DB]
- OLE DB data source properties [SQL Server Native Client]
ms.assetid: 6e14fefc-4e0b-4847-a833-4cf0abe65d50
author: rothja
ms.author: jroth
ms.openlocfilehash: b3c3c2d34897b1e88894f67118fe51bd35a01089
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685084"
---
# <a name="data-source-properties-ole-db"></a><span data-ttu-id="2769c-102">Propriedades da fonte de dados (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="2769c-102">Data Source Properties (OLE DB)</span></span>
  <span data-ttu-id="2769c-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo implementa as propriedades da fonte de dados da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="2769c-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements data source properties as follows.</span></span>  
  
|<span data-ttu-id="2769c-104">ID da propriedade</span><span class="sxs-lookup"><span data-stu-id="2769c-104">Property ID</span></span>|<span data-ttu-id="2769c-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="2769c-105">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="2769c-106">DBPROP_CURRENTCATALOG</span><span class="sxs-lookup"><span data-stu-id="2769c-106">DBPROP_CURRENTCATALOG</span></span>|<span data-ttu-id="2769c-107">Leitura/gravação: leitura/gravação Padrão: nenhum</span><span class="sxs-lookup"><span data-stu-id="2769c-107">R/W: Read/write Default: None</span></span><br /><br /> <span data-ttu-id="2769c-108">Descrição: o valor de DBPROP_CURRENTCATALOG relata o banco de dados atual para uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sessão de provedor de OLE DB de cliente nativo.</span><span class="sxs-lookup"><span data-stu-id="2769c-108">Description: The value of DBPROP_CURRENTCATALOG reports the current database for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider session.</span></span> <span data-ttu-id="2769c-109">A definição do valor da propriedade tem o mesmo efeito de definir o banco de dados atual usando a instrução USE *database* do [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2769c-109">Setting the property value has the identical effect as setting the current database by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] USE *database* statement.</span></span><br /><br /> <span data-ttu-id="2769c-110">Do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] em diante, se você chamar [sp_defaultdb](/sql/relational-databases/system-stored-procedures/sp-defaultdb-transact-sql) e especificar o nome do banco de dados em minúsculas, mesmo que o banco de dados tenha sido criado originalmente com um nome com maiúsculas e minúsculas, DBPROP_CURRENTCATALOG retornará o nome em minúsculas.</span><span class="sxs-lookup"><span data-stu-id="2769c-110">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], if you call [sp_defaultdb](/sql/relational-databases/system-stored-procedures/sp-defaultdb-transact-sql) and specify the database name in lower case, even if the database was originally created with a mixed case name, DBPROP_CURRENTCATALOG will return the name in lower case.</span></span> <span data-ttu-id="2769c-111">Nas versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], DBPROP_CURRENTCATALOG retornará as maiúsculas e minúsculas esperadas.</span><span class="sxs-lookup"><span data-stu-id="2769c-111">With previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], DBPROP_CURRENTCATALOG will return the expected mixed case.</span></span>|  
|<span data-ttu-id="2769c-112">DBPROP_MULTIPLECONNECTIONS</span><span class="sxs-lookup"><span data-stu-id="2769c-112">DBPROP_MULTIPLECONNECTIONS</span></span>|<span data-ttu-id="2769c-113">Leitura/gravação: leitura/gravação Padrão: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="2769c-113">R/W: Read/write Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="2769c-114">Descrição: se a conexão estiver executando um comando que não gera um conjunto de linhas ou que gera um conjunto de linhas que não é um cursor de servidor e você executar um outro comando, será criada uma nova conexão para executar o novo comando, se DBPROP_MULTIPLECONNECTIONS for VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="2769c-114">Description: If the connection is running a command that does not produce a rowset or produces a rowset that is not a server cursor and you execute another command, a new connection will be created to execute the new command if DBPROP_MULTIPLECONNECTIONS is VARIANT_TRUE.</span></span><br /><br /> <span data-ttu-id="2769c-115">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo não criará outra conexão se DBPROP_MULTIPLECONNECTION estiver VARIANT_FALSE ou se uma transação estiver ativa na conexão.</span><span class="sxs-lookup"><span data-stu-id="2769c-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider will not create another connection if DBPROP_MULTIPLECONNECTION is VARIANT_FALSE or if a transaction is active on the connection.</span></span> <span data-ttu-id="2769c-116">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo retorna DB_E_OBJECTOPEN se DBPROP_MULTIPLECONNECTIONS é VARIANT_FALSE e retorna E_FAIL se houver uma transação ativa.</span><span class="sxs-lookup"><span data-stu-id="2769c-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns DB_E_OBJECTOPEN if DBPROP_MULTIPLECONNECTIONS is VARIANT_FALSE and returns E_FAIL if there is an active transaction.</span></span> <span data-ttu-id="2769c-117">As transações e o bloqueio são gerenciados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por conexão.</span><span class="sxs-lookup"><span data-stu-id="2769c-117">Transactions and locking are managed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a per connection basis.</span></span> <span data-ttu-id="2769c-118">Se uma segunda conexão for gerada, os comandos nas conexões separadas não compartilharão bloqueios.</span><span class="sxs-lookup"><span data-stu-id="2769c-118">If a second connection is generated, the commands on the separate connections do not share locks.</span></span> <span data-ttu-id="2769c-119">Para assegurar um comando não bloqueie o outro, mantenha os bloqueios em linhas solicitadas pelo outro comando.</span><span class="sxs-lookup"><span data-stu-id="2769c-119">To ensure that one command does not block another, hold locks on rows requested by the other command.</span></span> <span data-ttu-id="2769c-120">Isto também se aplica à criação de várias sessões.</span><span class="sxs-lookup"><span data-stu-id="2769c-120">This also holds true when creating multiple sessions.</span></span><br /><br /> <span data-ttu-id="2769c-121">Cada sessão tem uma conexão separada.</span><span class="sxs-lookup"><span data-stu-id="2769c-121">Each session has a separate connection.</span></span>|  
  
 <span data-ttu-id="2769c-122">No conjunto de propriedades específico do provedor DBPROPSET_SQLSERVERDATASOURCE, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo define as propriedades de fonte de dados adicionais a seguir.</span><span class="sxs-lookup"><span data-stu-id="2769c-122">In the provider-specific property set DBPROPSET_SQLSERVERDATASOURCE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following additional data source properties.</span></span>  
  
|<span data-ttu-id="2769c-123">ID da propriedade</span><span class="sxs-lookup"><span data-stu-id="2769c-123">Property ID</span></span>|<span data-ttu-id="2769c-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="2769c-124">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="2769c-125">SSPROP_ENABLEFASTLOAD</span><span class="sxs-lookup"><span data-stu-id="2769c-125">SSPROP_ENABLEFASTLOAD</span></span>|<span data-ttu-id="2769c-126">Leitura/gravação: leitura/gravação Padrão: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="2769c-126">R/W: Read/write Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="2769c-127">Descrição: para habilitar a cópia em massa da memória, a propriedade SSPROP_ENABLEFASTLOAD deve ser definida como VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="2769c-127">Description: To enable bulk copy from memory, SSPROP_ENABLEFASTLOAD property should be set to VARIANT_TRUE.</span></span> <span data-ttu-id="2769c-128">Com essa propriedade definida na fonte de dados, a sessão recém-criada permite que o consumidor acesse a interface [IRowsetFastLoad](../native-client-ole-db-interfaces/irowsetfastload-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="2769c-128">With this property set on the data source, the newly created session allows consumer access to the [IRowsetFastLoad](../native-client-ole-db-interfaces/irowsetfastload-ole-db.md) interface.</span></span><br /><br /> <span data-ttu-id="2769c-129">Se a propriedade for definida como VARIANT_TRUE, a interface **IRowsetFastLoad** ficará disponível por meio de **IOpenRowset::OpenRowset**, solicitando a interface **IID_IRowsetFastLoad** ou definindo **SSPROP_IRowsetFastLoad** como VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="2769c-129">If the property is set to VARIANT_TRUE, **IRowsetFastLoad** interface is available through **IOpenRowset::OpenRowset** by requesting the **IID_IRowsetFastLoad** interface or by setting **SSPROP_IRowsetFastLoad** to VARIANT_TRUE.</span></span>|  
|<span data-ttu-id="2769c-130">SSPROP_ENABLEBULKCOPY</span><span class="sxs-lookup"><span data-stu-id="2769c-130">SSPROP_ENABLEBULKCOPY</span></span>|<span data-ttu-id="2769c-131">Leitura/gravação: leitura/gravação Padrão: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="2769c-131">R/W: Read/write Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="2769c-132">Descrição: para habilitar a cópia em massa de arquivos, a propriedade SSPROP_ENABLEBULKCOPY deve ser definida como VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="2769c-132">Description: To enable bulk copy from files, SSPROP_ENABLEBULKCOPY property should be set to VARIANT_TRUE.</span></span> <span data-ttu-id="2769c-133">Com essa propriedade definida na fonte de dados, o acesso do consumidor à interface IBCPSession está disponível no nível de Sessions.</span><span class="sxs-lookup"><span data-stu-id="2769c-133">With this property set on the data source, consumer access to the IBCPSession interface is available under the same level as Sessions.</span></span><br /><br /> <span data-ttu-id="2769c-134">SSPROP_IRowsetFastLoad também deve ser definido como VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="2769c-134">SSPROP_IRowsetFastLoad must also be set to VARIANT_TRUE.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2769c-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2769c-135">See Also</span></span>  
 [<span data-ttu-id="2769c-136">Objetos de fonte de dados &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="2769c-136">Data Source Objects &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-data-source-objects/data-source-objects-ole-db.md)  
  
  