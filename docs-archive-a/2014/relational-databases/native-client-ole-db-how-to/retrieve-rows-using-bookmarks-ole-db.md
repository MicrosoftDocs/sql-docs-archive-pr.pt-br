---
title: Recuperar linhas usando indicadores (OLE DB)| Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bookmarks [OLE DB]
- rows [OLE DB]
ms.assetid: 5e14d5c8-e7c6-498f-8041-7e006a1c2d81
author: rothja
ms.author: jroth
ms.openlocfilehash: 84a525c267d6004f6e262f21961c607a762b74ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679345"
---
# <a name="retrieve-rows-using-bookmarks-ole-db"></a><span data-ttu-id="50297-102">Recuperar linhas usando indicadores (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="50297-102">Retrieve Rows Using Bookmarks (OLE DB)</span></span>
  <span data-ttu-id="50297-103">O consumidor define o valor de campo `dwFlag` da estrutura de associação a DBCOLUMNSINFO_ISBOOKMARK para indicar que a coluna é usada como um indicador.</span><span class="sxs-lookup"><span data-stu-id="50297-103">The consumer sets the `dwFlag` field value of the binding structure to DBCOLUMNSINFO_ISBOOKMARK to indicate that the column is used as bookmark.</span></span> <span data-ttu-id="50297-104">O consumidor também define a propriedade DBPROP_BOOKMARKS do conjunto de linhas como VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="50297-104">The consumer also sets the rowset property DBPROP_BOOKMARKS to VARIANT_TRUE.</span></span> <span data-ttu-id="50297-105">Isso permite que a coluna 0 esteja presente no conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="50297-105">This allows column 0 to be present in the rowset.</span></span> <span data-ttu-id="50297-106">`IRowsetLocate::GetRowsAt` é usado para buscar linhas a partir da linha especificada por um deslocamento de um indicador.</span><span class="sxs-lookup"><span data-stu-id="50297-106">`IRowsetLocate::GetRowsAt` is then used to fetch rows starting with the row specified an offset from a bookmark.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="50297-107">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="50297-107">When possible, use Windows Authentication.</span></span> <span data-ttu-id="50297-108">Se a Autenticação do Windows não estiver disponível, solicite aos usuários que digitem suas credenciais em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="50297-108">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="50297-109">Evite armazenar as credenciais em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="50297-109">Avoid storing credentials in a file.</span></span> <span data-ttu-id="50297-110">Se for necessário manter as credenciais, criptografe-as com a [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532)(em inglês).</span><span class="sxs-lookup"><span data-stu-id="50297-110">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-retrieve-rows-using-bookmarks"></a><span data-ttu-id="50297-111">Para recuperar linhas usando indicadores</span><span class="sxs-lookup"><span data-stu-id="50297-111">To retrieve rows using bookmarks</span></span>  
  
1.  <span data-ttu-id="50297-112">Estabeleça uma conexão com a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="50297-112">Establish a connection to the data source.</span></span>  
  
2.  <span data-ttu-id="50297-113">Defina a propriedade DBPROP_IRowsetLocate do conjunto de linhas como VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="50297-113">Set the rowset DBPROP_IRowsetLocate property to VARIANT_TRUE.</span></span>  
  
3.  <span data-ttu-id="50297-114">Execute o comando.</span><span class="sxs-lookup"><span data-stu-id="50297-114">Execute the command.</span></span>  
  
4.  <span data-ttu-id="50297-115">Defina o campo `dwFlag` da estrutura associada como o sinalizador DBCOLUMNSINFO_ISBOOKMARK para a coluna que será usada como indicador.</span><span class="sxs-lookup"><span data-stu-id="50297-115">Set the `dwFlag` field of the binding structure to DBCOLUMNSINFO_ISBOOKMARK flag for the column that will be used as a bookmark.</span></span>  
  
5.  <span data-ttu-id="50297-116">Use `IRowsetLocate::GetRowsAt` para buscar linhas, iniciando com a linha especificada por um deslocamento do indicador.</span><span class="sxs-lookup"><span data-stu-id="50297-116">Use `IRowsetLocate::GetRowsAt` to fetch rows, starting with the row specified by an offset from the bookmark.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50297-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="50297-117">Example</span></span>  
 <span data-ttu-id="50297-118">Este exemplo mostra como buscar linhas usando um indicador.</span><span class="sxs-lookup"><span data-stu-id="50297-118">This sample shows how to fetch rows using a bookmark.</span></span> <span data-ttu-id="50297-119">Este exemplo não tem suporte em IA64.</span><span class="sxs-lookup"><span data-stu-id="50297-119">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="50297-120">Nesse exemplo, a quinta linha é recuperada do conjunto de resultados gerado pela execução de uma instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="50297-120">In this sample, the fifth row is retrieved from the result set produced from the execution of a SELECT statement.</span></span>  
  
 <span data-ttu-id="50297-121">Este exemplo exige o banco de dados de exemplo AdventureWorks, que pode ser baixado na home page de [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) (em inglês).</span><span class="sxs-lookup"><span data-stu-id="50297-121">This sample requires the AdventureWorks sample database, which you can download from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.</span></span>  
  
 <span data-ttu-id="50297-122">Compile com ole32.lib oleaut32.lib e execute a seguinte listagem de código C++.</span><span class="sxs-lookup"><span data-stu-id="50297-122">Compile with ole32.lib oleaut32.lib and execute the following C++ code listing.</span></span> <span data-ttu-id="50297-123">Esse aplicativo se conecta à instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do computador.</span><span class="sxs-lookup"><span data-stu-id="50297-123">This application connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="50297-124">Em alguns sistemas operacionais Windows, será necessário alterar (localhost) ou (local) para o nome de sua instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="50297-124">On some Windows operating systems, you will need to change (localhost) or (local) to the name of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="50297-125">Para se conectar a uma instância nomeada, altere a cadeia de conexão de L"(local)" para L"(local)\\\name", em que name é a instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="50297-125">To connect to a named instance, change the connection string from L"(local)" to L"(local)\\\name" , where name is the named instance.</span></span> <span data-ttu-id="50297-126">Por padrão, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express é instalado em uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="50297-126">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express installs to a named instance.</span></span> <span data-ttu-id="50297-127">Verifique se a variável de ambiente INCLUDE inclui o diretório que contém sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="50297-127">Make sure your INCLUDE environment variable includes the directory that contains sqlncli.h.</span></span>  
  
```  
// compile with: ole32.lib oleaut32.lib  
int InitializeAndEstablishConnection();  
int ProcessResultSet();  
  
#define UNICODE  
#define _UNICODE  
#define DBINITCONSTANTS  
#define INITGUID  
#define OLEDBVER 0x0250   // to include correct interfaces  
  
#include <stdio.h>  
#include <tchar.h>  
#include <stddef.h>  
#include <windows.h>  
#include <iostream>  
#include <oledb.h>  
#include <sqlncli.h>  
  
using namespace std;  
  
IDBInitialize*       pIDBInitialize      = NULL;  
IDBProperties*       pIDBProperties      = NULL;  
IDBCreateSession*    pIDBCreateSession   = NULL;  
IDBCreateCommand*    pIDBCreateCommand   = NULL;  
ICommandProperties*  pICommandProperties = NULL;  
ICommandText*        pICommandText       = NULL;  
IRowset*             pIRowset            = NULL;  
IColumnsInfo*        pIColumnsInfo       = NULL;  
DBCOLUMNINFO*        pDBColumnInfo       = NULL;  
IAccessor*           pIAccessor          = NULL;  
IRowsetLocate*       pIRowsetLocate      = NULL;  
  
DBPROP        InitProperties[4];  
DBPROPSET     rgInitPropSet[1];   
DBPROPSET     rgPropSets[1];  
DBPROP        rgProperties[1];  
ULONG         i, j;                
HRESULT       hresult;  
DBROWCOUNT    cNumRows = 0;  
DBORDINAL     lNumCols;  
WCHAR*        pStringsBuffer;  
DBBINDING*    pBindings;  
DBLENGTH      ConsumerBufferColOffset = 0;  
HACCESSOR     hAccessor;  
DBCOUNTITEM   lNumRowsRetrieved;  
HROW          hRows[5];           
HROW*         pRows = &hRows[0];  
char*         pBuffer;  
  
int main() {  
   // The command to execute.  
   // WCHAR* wCmdString = OLESTR(" SELECT title_id, title FROM titles ");  
   WCHAR* wCmdString = OLESTR(" SELECT Name FROM Production.Product");  
  
   // Initialize and establish a connection to the data source.  
   if (InitializeAndEstablishConnection() == -1) {  
      // Handle error.  
      cout << "Failed to initialize and connect to the server.\n";  
      return -1;  
   }  
  
   // Create a session object.  
   if (FAILED(pIDBInitialize->QueryInterface(IID_IDBCreateSession, (void**) &pIDBCreateSession))) {  
      cout << "Failed to obtain IDBCreateSession interface.\n";  
      // Handle error.  
      return -1;  
   }  
  
   if (FAILED(pIDBCreateSession->CreateSession(NULL, IID_IDBCreateCommand, (IUnknown**) &pIDBCreateCommand))) {  
      cout << "pIDBCreateSession->CreateSession failed.\n";  
      // Handle error.  
      return -1;  
   }  
  
   // Access the ICommandText interface.  
   if (FAILED(pIDBCreateCommand->CreateCommand( NULL, IID_ICommandText, (IUnknown**) &pICommandText))) {  
      cout << "Failed to access ICommand interface.\n";  
      // Handle error.  
      return -1;  
   }  
  
   // Set DBPROP_IRowsetLocate  
   if (FAILED(pICommandText->QueryInterface( IID_ICommandProperties, (void **) &pICommandProperties ))) {  
      cout << "Failed to obtain ICommandProperties interface.\n";  
      // Handle error.  
      return -1;  
   }  
  
   // Set DBPROP_IRowsetLocate to VARIANT_TRUE to get the IRowsetLocate interface.  
   VariantInit(&rgProperties[0].vValue);  
  
   rgPropSets[0].guidPropertySet = DBPROPSET_ROWSET;  
   rgPropSets[0].cProperties = 1;  
   rgPropSets[0].rgProperties = rgProperties;  
  
   // Set properties in the property group (DBPROPSET_ROWSET)   
   rgPropSets[0].rgProperties[0].dwPropertyID  = DBPROP_IRowsetLocate;  
   rgPropSets[0].rgProperties[0].dwOptions     = DBPROPOPTIONS_REQUIRED;  
   rgPropSets[0].rgProperties[0].colid         = DB_NULLID;  
   rgPropSets[0].rgProperties[0].vValue.vt     = VT_BOOL;  
   rgPropSets[0].rgProperties[0].vValue.boolVal= VARIANT_TRUE;  
  
   // Set the rowset properties.  
   hresult = pICommandText->QueryInterface( IID_ICommandProperties,(void **)&pICommandProperties);  
   if (FAILED(hresult)) {  
      printf("Failed to get ICommandProperties to set rowset properties.\n");  
      // Release any references and return.  
      return -1;  
   }  
  
   hresult = pICommandProperties->SetProperties(1, rgPropSets);  
   if (FAILED(hresult)) {  
      printf("Execute failed to set rowset properties.\n");  
      // Release any references and return.  
      return -1;  
   }   
  
   pICommandProperties->Release();  
  
   // Specify the command text.  
   if (FAILED(pICommandText->SetCommandText(DBGUID_DBSQL, wCmdString))) {  
      cout << "Failed to set command text.\n";  
      // Handle error.  
      return -1;  
   }  
  
   // Execute the command.  
   if (FAILED(hresult =   
      pICommandText->Execute( NULL, IID_IRowset, NULL, &cNumRows, (IUnknown **) &pIRowset))) {  
      cout << "Failed to execute command.\n";  
      // Handle error.  
      return -1;  
   }  
  
   ProcessResultSet();   
  
   pIRowset->Release();  
  
   // Free up memory.  
   pICommandText->Release();  
   pIDBCreateCommand->Release();  
   pIDBCreateSession->Release();  
  
   pIDBInitialize->Uninitialize();  
   pIDBInitialize->Release();  
  
   // Release COM library.  
   CoUninitialize();  
  
   return -1;  
}  
  
int InitializeAndEstablishConnection() {      
   // Initialize the COM library.  
   CoInitialize(NULL);  
  
   // Obtain access to the SQL Server Native Client OLe DB provider.  
   CoCreateInstance( CLSID_SQLNCLI11, NULL, CLSCTX_INPROC_SERVER, IID_IDBInitialize, (void **) &pIDBInitialize);  
  
   // Initialize the property values that are the same for each property.  
   for ( i = 0 ; i < 4 ; i++ ) {  
      VariantInit(&InitProperties[i].vValue);  
      InitProperties[i].dwOptions = DBPROPOPTIONS_REQUIRED;  
      InitProperties[i].colid = DB_NULLID;  
   }  
  
   // Server name.  
   InitProperties[0].dwPropertyID = DBPROP_INIT_DATASOURCE;  
   InitProperties[0].vValue.vt = VT_BSTR;  
   InitProperties[0].vValue.bstrVal = SysAllocString(L"(local)");  
  
   // Database.  
   InitProperties[1].dwPropertyID = DBPROP_INIT_CATALOG;  
   InitProperties[1].vValue.vt = VT_BSTR;  
   InitProperties[1].vValue.bstrVal = SysAllocString(L"AdventureWorks");  
  
   InitProperties[2].dwPropertyID = DBPROP_AUTH_INTEGRATED;   
   InitProperties[2].vValue.vt = VT_BSTR;  
   InitProperties[2].vValue.bstrVal = SysAllocString(L"SSPI");  
  
   // Construct the PropertySet array.  
   rgInitPropSet[0].guidPropertySet = DBPROPSET_DBINIT;  
   rgInitPropSet[0].cProperties = 4;  
   rgInitPropSet[0].rgProperties = InitProperties;  
  
   // Set initialization properties.  
   pIDBInitialize->QueryInterface(IID_IDBProperties, (void **)&pIDBProperties);  
  
   hresult = pIDBProperties->SetProperties(1, rgInitPropSet);   
   if (FAILED(hresult)) {  
      cout << "Failed to set initialization properties.\n";  
      // Handle error.  
      return -1;  
   }  
  
   pIDBProperties->Release();  
  
   // Call the initialization method to establish the connection.  
   if (FAILED(pIDBInitialize->Initialize())) {  
      cout << "Problem initializing and connecting to the data source.\n";  
      // Handle error.  
      return -1;  
   }  
  
   return 0;  
}  
  
#ifdef _WIN64  
#define BUFFER_ALIGNMENT 8  
#else  
#define BUFFER_ALIGNMENT 4  
#endif  
  
#define ROUND_UP(value) (value + (BUFFER_ALIGNMENT - 1) & ~(BUFFER_ALIGNMENT - 1))  
  
int ProcessResultSet() {  
   HRESULT hr;  
  
   // Retrieve 5th row from the rowset (for example).  
   DBBKMARK iBookmark = 5;  
  
   pIRowset->QueryInterface(IID_IColumnsInfo, (void **)&pIColumnsInfo);  
  
   pIColumnsInfo->GetColumnInfo( &lNumCols, &pDBColumnInfo, &pStringsBuffer );  
  
   // Create a DBBINDING array.  
   pBindings = new DBBINDING[lNumCols];  
   if (!(pBindings /* = new DBBINDING[lNumCols] */ )) {  
      // Handle error.  
      return -1;  
   }  
  
   // Using the ColumnInfo strucuture, fill out the pBindings array.  
   for ( j = 0 ; j < lNumCols ; j++ ) {  
      pBindings[j].iOrdinal  = j;  
      pBindings[j].obValue   = ConsumerBufferColOffset;  
      pBindings[j].pTypeInfo = NULL;  
      pBindings[j].pObject   = NULL;  
      pBindings[j].pBindExt  = NULL;  
      pBindings[j].dwPart    = DBPART_VALUE;  
      pBindings[j].dwMemOwner = DBMEMOWNER_CLIENTOWNED;  
      pBindings[j].eParamIO  = DBPARAMIO_NOTPARAM;  
      pBindings[j].cbMaxLen  = pDBColumnInfo[j].ulColumnSize + 1;   // + 1 for null terminator  
      pBindings[j].dwFlags   = 0;  
      pBindings[j].wType      = pDBColumnInfo[j].wType;  
      pBindings[j].bPrecision = pDBColumnInfo[j].bPrecision;  
      pBindings[j].bScale     = pDBColumnInfo[j].bScale;  
  
      // Recalculate the next buffer offset.  
      ConsumerBufferColOffset = ConsumerBufferColOffset + pDBColumnInfo[j].ulColumnSize;  
  ConsumerBufferColOffset = ROUND_UP(ConsumerBufferColOffset);  
  
   };  
   // Indicate that the first field is used as a bookmark by setting  
   // dwFlags to DBCOLUMNFLAGS_ISBOOKMARK.  
   pBindings[0].dwFlags = DBCOLUMNFLAGS_ISBOOKMARK;  
  
   // Get IAccessor interface.  
   hr = pIRowset->QueryInterface( IID_IAccessor, (void **)&pIAccessor);  
   if (FAILED(hr)) {  
      printf("Failed to get IAccessor interface.\n");  
      // Handle error.  
      return -1;  
   }  
  
   // Create accessor.  
   hr = pIAccessor->CreateAccessor( DBACCESSOR_ROWDATA,  
                                    lNumCols,  
                                    pBindings,  
                                    0,  
                                    &hAccessor,  
                                    NULL);  
  
   if (FAILED(hr)) {  
      printf("Failed to create an accessor.\n");  
      // Handle error.  
      return -1;  
   }  
  
   hr = pIRowset->QueryInterface( IID_IRowsetLocate, (void **) &pIRowsetLocate);  
   if (FAILED(hr)) {  
      printf("Failed to get IRowsetLocate interface.\n");  
      // Handle error.  
      return -1;  
   }  
  
   hr = pIRowsetLocate->GetRowsAt( 0,  
                                   NULL,  
                                   sizeof(DBBKMARK),  
                                   (BYTE *) &iBookmark,  
                                   0,  
                                   1,  
                                   &lNumRowsRetrieved,  
                                   &pRows);  
  
   if (FAILED(hr)) {  
      printf("Calling the GetRowsAt method failed.\n");  
      // Handle error.  
      return -1;  
   }  
  
   // Create buffer and retrieve data.  
   pBuffer = new char[ConsumerBufferColOffset];  
   if (!(pBuffer /* = new char[ConsumerBufferColOffset] */ )) {  
      // Handle error.  
      return -1;  
   }  
  
   memset(pBuffer, 0, ConsumerBufferColOffset);  
  
   hr = pIRowset->GetData(hRows[0], hAccessor, pBuffer);  
   if (FAILED(hr)) {  
      printf("Failed GetDataCall.\n");  
      // Handle error.  
      return -1;  
   }  
  
   char szTitle[7] = {0};  
   strncpy_s(szTitle, &pBuffer[pBindings[1].obValue], 6);  
  
   printf("%S\n", &pBuffer[pBindings[1].obValue]);  
  
   pIRowset->ReleaseRows(lNumRowsRetrieved, hRows, NULL, NULL, NULL);  
  
   // Release allocated memory.  
   delete [] pBuffer;  
   pIAccessor->ReleaseAccessor(hAccessor, NULL);  
   pIAccessor->Release();  
   delete [] pBindings;  
  
   return 0;  
}  
```  
  
  
