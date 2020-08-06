---
title: Estabelecimento de uma conexão a uma fonte de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [SQL Server Native Client]
- connections [SQL Server Native Client]
- SQL Server Native Client OLE DB provider, data source connections
- CoCreateInstance method
- OLE DB data sources [SQL Server Native Client]
ms.assetid: 7ebd1394-cc8d-4bcf-92f3-c374a26e7ba0
author: rothja
ms.author: jroth
ms.openlocfilehash: f88454339ee932c38655819cce475ab52d79975f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581781"
---
# <a name="establishing-a-connection-to-a-data-source"></a><span data-ttu-id="b0b80-102">Estabelecendo uma conexão com uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="b0b80-102">Establishing a Connection to a Data Source</span></span>
  <span data-ttu-id="b0b80-103">Para acessar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo, o consumidor deve primeiro criar uma instância de um objeto de fonte de dados chamando o método **CoCreateInstance** .</span><span class="sxs-lookup"><span data-stu-id="b0b80-103">To access the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the consumer must first create an instance of a data source object by calling the **CoCreateInstance** method.</span></span> <span data-ttu-id="b0b80-104">Um CLSID (identificador de classe) exclusivo identifica cada provedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="b0b80-104">A unique class identifier (CLSID) identifies each OLE DB provider.</span></span> <span data-ttu-id="b0b80-105">Para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo, o identificador de classe é CLSID_SQLNCLI10.</span><span class="sxs-lookup"><span data-stu-id="b0b80-105">For the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the class identifier is CLSID_SQLNCLI10.</span></span> <span data-ttu-id="b0b80-106">Você também pode usar o símbolo SQLNCLI_CLSID que será resolvido para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo que é usado no sqlncli. h referenciado.</span><span class="sxs-lookup"><span data-stu-id="b0b80-106">You can also use the symbol SQLNCLI_CLSID that will resolve to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider that is used in the sqlncli.h that you reference.</span></span>  
  
 <span data-ttu-id="b0b80-107">O objeto da fonte de dados expõe a interface **IDBProperties**, que é usada pelo consumidor para fornecer informações básicas de autenticação, como o nome do servidor, o nome do banco de dados, a ID de usuário e a senha.</span><span class="sxs-lookup"><span data-stu-id="b0b80-107">The data source object exposes the **IDBProperties** interface, which the consumer uses to provide basic authentication information such as server name, database name, user ID, and password.</span></span> <span data-ttu-id="b0b80-108">O método **IDBProperties::SetProperties** é chamado para definir essas propriedades.</span><span class="sxs-lookup"><span data-stu-id="b0b80-108">The **IDBProperties::SetProperties** method is called to set these properties.</span></span>  
  
 <span data-ttu-id="b0b80-109">Se houver várias instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em execução no computador, o nome do servidor será especificado como ServerName\InstanceName.</span><span class="sxs-lookup"><span data-stu-id="b0b80-109">If there are multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the computer, the server name is specified as ServerName\InstanceName.</span></span>  
  
 <span data-ttu-id="b0b80-110">O objeto da fonte de dados também expõe a interface **IDBInitialize**.</span><span class="sxs-lookup"><span data-stu-id="b0b80-110">The data source object also exposes the **IDBInitialize** interface.</span></span> <span data-ttu-id="b0b80-111">Depois que as propriedades são definidas, a conexão com a fonte de dados é estabelecida pela chamada ao método **IDBInitialize::Initialize**.</span><span class="sxs-lookup"><span data-stu-id="b0b80-111">After the properties are set, connection to the data source is established by calling the **IDBInitialize::Initialize** method.</span></span> <span data-ttu-id="b0b80-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b0b80-112">For example:</span></span>  
  
```  
CoCreateInstance(CLSID_SQLNCLI10,   
                 NULL,   
                 CLSCTX_INPROC_SERVER,  
                 IID_IDBInitialize,   
                 (void **) &pIDBInitialize)  
```  
  
 <span data-ttu-id="b0b80-113">Essa chamada para **CoCreateInstance** cria um único objeto da classe associada ao CLSID_SQLNCLI10 (CSLID associado aos dados e ao código que será usado para criar o objeto).</span><span class="sxs-lookup"><span data-stu-id="b0b80-113">This call to **CoCreateInstance** creates a single object of the class associated with CLSID_SQLNCLI10 (CSLID associated with the data and code that will be used to create the object).</span></span> <span data-ttu-id="b0b80-114">IID_IDBInitialize é uma referência ao identificador da interface (**IDBInitialize**) a ser usada para a comunicação com o objeto.</span><span class="sxs-lookup"><span data-stu-id="b0b80-114">IID_IDBInitialize is a reference to the identifier of the interface (**IDBInitialize**) to be used to communicate with the object.</span></span>  
  
 <span data-ttu-id="b0b80-115">Segue uma função de exemplo que inicializa e estabelece uma conexão com a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b0b80-115">The following is a sample function that initializes and establishes a connection to the data source.</span></span>  
  
```  
void InitializeAndEstablishConnection() {  
   // Initialize the COM library.  
   CoInitialize(NULL);  
  
   // Obtain access to the SQL Server Native Client OLE DB provider.  
   hr = CoCreateInstance(CLSID_SQLNCLI10,   
                         NULL,   
                         CLSCTX_INPROC_SERVER,  
                         IID_IDBInitialize,   
                         (void **) &pIDBInitialize);  
   // Initialize property values needed to establish connection.  
   for (i = 0 ; i < 4 ; i++)   
      VariantInit(&InitProperties[i].vValue);  
  
   // Server name.  
   // See DBPROP structure for more information on InitProperties  
   InitProperties[0].dwPropertyID  = DBPROP_INIT_DATASOURCE;  
   InitProperties[0].vValue.vt    = VT_BSTR;  
   InitProperties[0].vValue.bstrVal=   
                     SysAllocString(L"Server");  
   InitProperties[0].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[0].colid       = DB_NULLID;  
  
   // Database.  
   InitProperties[1].dwPropertyID  = DBPROP_INIT_CATALOG;  
   InitProperties[1].vValue.vt    = VT_BSTR;  
   InitProperties[1].vValue.bstrVal= SysAllocString(L"database");  
   InitProperties[1].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[1].colid       = DB_NULLID;  
  
   // Username (login).  
   InitProperties[2].dwPropertyID  = DBPROP_AUTH_INTEGRATED;  
   InitProperties[2].vValue.vt    = VT_BSTR;  
   InitProperties[2].vValue.bstrVal= SysAllocString(L"SSPI");  
   InitProperties[2].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[2].colid       = DB_NULLID;  
   InitProperties[3].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[3].colid       = DB_NULLID;  
  
   // Construct the DBPROPSET structure(rgInitPropSet). The   
   // DBPROPSET structure is used to pass an array of DBPROP   
   // structures (InitProperties) to the SetProperties method.  
   rgInitPropSet[0].guidPropertySet = DBPROPSET_DBINIT;  
   rgInitPropSet[0].cProperties   = 4;  
   rgInitPropSet[0].rgProperties   = InitProperties;  
  
   // Set initialization properties.  
   hr = pIDBInitialize->QueryInterface(IID_IDBProperties,   
                           (void **)&pIDBProperties);  
   hr = pIDBProperties->SetProperties(1, rgInitPropSet);   
   pIDBProperties->Release();  
  
   // Now establish the connection to the data source.  
   pIDBInitialize->Initialize();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0b80-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b0b80-116">See Also</span></span>  
 [<span data-ttu-id="b0b80-117">Criando um aplicativo provedor OLE DB do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="b0b80-117">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
