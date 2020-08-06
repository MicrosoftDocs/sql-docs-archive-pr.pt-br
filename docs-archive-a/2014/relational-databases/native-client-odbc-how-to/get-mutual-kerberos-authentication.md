---
title: Obter autenticação Kerberos mútua | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 64149fd4-239b-40e4-91e2-f9011f7d9f66
author: rothja
ms.author: jroth
ms.openlocfilehash: 9845c4e0f33e67c835e57e513f47a100c75518d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684710"
---
# <a name="get-mutual-kerberos-authentication"></a><span data-ttu-id="f6c8c-102">Obter autenticação Kerberos mútua</span><span class="sxs-lookup"><span data-stu-id="f6c8c-102">Get Mutual Kerberos Authentication</span></span>
  <span data-ttu-id="f6c8c-103">Este exemplo mostra como obter autenticação mútua do Kerberos usando o ODBC em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="f6c8c-103">This sample shows how to get mutual Kerberos authentication by using ODBC in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 <span data-ttu-id="f6c8c-104">Este exemplo não funcionará com nenhuma versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anterior ao [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6c8c-104">This sample will not work with any version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="f6c8c-105">Para obter mais informações, consulte [nome da entidade de serviço &#40;SPN&#41; suporte em conexões de cliente](../native-client/features/service-principal-name-spn-support-in-client-connections.md).</span><span class="sxs-lookup"><span data-stu-id="f6c8c-105">For more information, see [Service Principal Name &#40;SPN&#41; Support in Client Connections](../native-client/features/service-principal-name-spn-support-in-client-connections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6c8c-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f6c8c-106">Example</span></span>  
 <span data-ttu-id="f6c8c-107">Se você compilar e executar esse exemplo como um aplicativo de 32 bits em um sistema operacional de 64 bits, deverá criar a fonte de dados ODBC com o Administrador ODBC em %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="f6c8c-107">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="f6c8c-108">Esse aplicativo se conecta à instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do computador.</span><span class="sxs-lookup"><span data-stu-id="f6c8c-108">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="f6c8c-109">Para conectar-se a uma instância nomeada, altere a definição da fonte de dados ODBC para especificar a instância usando o seguinte formato: servidor\instância_nomeada.</span><span class="sxs-lookup"><span data-stu-id="f6c8c-109">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="f6c8c-110">Por padrão, o [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] é instalado em uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="f6c8c-110">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="f6c8c-111">Altere "MyServer" para um nome de máquina que tenha uma instância do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (ou posterior).</span><span class="sxs-lookup"><span data-stu-id="f6c8c-111">Change "MyServer" to a machine name that has an instance of [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later).</span></span>  
  
 <span data-ttu-id="f6c8c-112">Você também terá que especificar um SPN fornecido por cliente.</span><span class="sxs-lookup"><span data-stu-id="f6c8c-112">You will also have to specify a customer-provided SPN.</span></span> <span data-ttu-id="f6c8c-113">Altere " CP_SPN " a um SPN fornecido por cliente.</span><span class="sxs-lookup"><span data-stu-id="f6c8c-113">Change " CP_SPN " to a customer-provided SPN.</span></span>  
  
 <span data-ttu-id="f6c8c-114">Compile com /EHsc, /D "_UNICODE", /D "UNICODE" e odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="f6c8c-114">Compile with /EHsc, /D "_UNICODE", /D "UNICODE", and odbc32.lib.</span></span> <span data-ttu-id="f6c8c-115">Verifique se a variável de ambiente INCLUDE inclui o diretório que contém sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="f6c8c-115">Make sure your INCLUDE environment variable includes the directory that contains sqlncli.h.</span></span>  
  
```  
// compile with: /EHsc /D "_UNICODE" /D "UNICODE" odbc32.lib  
#define WIN32_LEAN_AND_MEAN  
#include <tchar.h>  
#include <windows.h>  
#include <stdio.h>  
#include <sql.h>  
#include <sqlext.h>  
  
#define _SQLNCLI_ODBC_  
#include <sqlncli.h>  
  
#define SUCCESS(x) (!((x) & 0xFFFE))  
  
#define CHKRC(stmt) do \  
                    { \  
                    rc = (stmt); \  
                    if (!SUCCESS(rc)) \  
                    throw (RETCODE) rc; \  
                    } while(0);  
  
void PrintError(SQLSMALLINT HandleType, SQLHANDLE Handle) {  
   RETCODE rc = SQL_SUCCESS;  
   SQLTCHAR szSqlState[6], szMessage[1024];  
   SQLSMALLINT i = 1, msgLen = 0;  
   SQLINTEGER NativeError;  
  
   do {  
      i = 1;  
      while (SQL_NO_DATA != (rc = SQLGetDiagRec(HandleType, Handle, i, szSqlState, &NativeError,   
         szMessage, sizeof(szMessage)/sizeof(SQLTCHAR), &msgLen)) && SUCCESS(rc)) {  
            _tprintf(_T("SQLState=%s, NativeError=%ld, Message=%s\r\n"), szSqlState, NativeError, szMessage);  
            i++;  
      }  
   }   
   while (SQL_NO_DATA != (rc = SQLMoreResults(Handle)) && SUCCESS(rc));  
}  
  
int _tmain(int argc, _TCHAR* argv[]) {  
   RETCODE rc = SQL_SUCCESS;  
   HENV henv = SQL_NULL_HENV;  
   HDBC hdbc = SQL_NULL_HDBC;  
   SQLHSTMT hstmt = SQL_NULL_HSTMT;  
   SQLTCHAR * pszConnection = _T("DRIVER={SQL Server Native Client 10.0};")  
      _T("Server=MyServer;")          // server with SQL Server 2008 (or later)  
      _T("Trusted_Connection=Yes;")  
      _T("ServerSPN=CP_SPN");    // customer-provided SPN  
  
   TCHAR szIntgAuthMethod[64];  
   SQLSMALLINT fMutuallyAuth = 0;  
  
   try {  
      CHKRC(SQLAllocHandle(SQL_HANDLE_ENV, SQL_NULL_HENV, &henv));  
      CHKRC(SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER)SQL_OV_ODBC3, 0));  
      CHKRC(SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc));  
      CHKRC(SQLDriverConnect( hdbc, NULL, pszConnection, SQL_NTS, NULL, 0, NULL, SQL_DRIVER_NOPROMPT));  
      CHKRC(SQLGetConnectAttr(hdbc, SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD, szIntgAuthMethod, sizeof(szIntgAuthMethod)/sizeof(szIntgAuthMethod[0]), NULL));  
      CHKRC(::SQLGetConnectAttrW(hdbc, SQL_COPT_SS_MUTUALLY_AUTHENTICATED, &fMutuallyAuth, SQL_IS_SMALLINT, NULL));  
  
      _tprintf(_T("Authentication method: %s\r\n"), szIntgAuthMethod);  
      _tprintf(_T("Mutually authenticated: %s\r\n"), fMutuallyAuth?_T("yes"):_T("no"));  
   }  
   catch (RETCODE retcode) {  
      rc = retcode;  
   }  
  
   if (!SUCCESS(rc)) {  
      if (hstmt)  
         PrintError(SQL_HANDLE_STMT, hstmt);  
      else if (hdbc)  
         PrintError(SQL_HANDLE_DBC, hdbc);  
      else if(henv)  
         PrintError(SQL_HANDLE_ENV, henv);  
   }  
  
   if (hstmt)  
      SQLFreeHandle(SQL_HANDLE_STMT, hstmt);  
   if (hdbc) {  
      SQLDisconnect(hdbc);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc);  
   }  
   if (henv)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
  