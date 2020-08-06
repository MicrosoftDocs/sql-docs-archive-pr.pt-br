---
title: Cópia em massa sem um arquivo de formato (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], file formats
- bulk copy [ODBC]
- bulk copy [ODBC], data files
- bulk copy [ODBC], about bulk copy
ms.assetid: 4ee969a7-44ba-40d0-b9ab-8306f1a2b19d
author: rothja
ms.author: jroth
ms.openlocfilehash: a65f013d92f5a5d39a580cfb3a9bd77bc6f84e9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685640"
---
# <a name="bulk-copy-without-a-format-file-odbc"></a><span data-ttu-id="2fab8-102">Copiar em massa sem um arquivo de formato (ODBC)</span><span class="sxs-lookup"><span data-stu-id="2fab8-102">Bulk Copy Without a Format File (ODBC)</span></span>
  <span data-ttu-id="2fab8-103">Este exemplo completo mostra como usar as funções de cópia em massa para criar um arquivo de dados de modo nativo, sem um arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="2fab8-103">This sample shows how to use bulk copy functions to create a native mode data file, without a format file.</span></span> <span data-ttu-id="2fab8-104">Esse exemplo foi desenvolvido para o ODBC versão 3.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="2fab8-104">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2fab8-105">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="2fab8-105">When possible, use Windows Authentication.</span></span> <span data-ttu-id="2fab8-106">Se a Autenticação do Windows não estiver disponível, solicite aos usuários que digitem suas credenciais em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="2fab8-106">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="2fab8-107">Evite armazenar as credenciais em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2fab8-107">Avoid storing credentials in a file.</span></span> <span data-ttu-id="2fab8-108">Se for necessário manter as credenciais, criptografe-as com a [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532)(em inglês).</span><span class="sxs-lookup"><span data-stu-id="2fab8-108">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-bulk-copy-without-a-format-file"></a><span data-ttu-id="2fab8-109">Para copiar em massa sem um arquivo de formato</span><span class="sxs-lookup"><span data-stu-id="2fab8-109">To bulk copy without a format file</span></span>  
  
1.  <span data-ttu-id="2fab8-110">Aloque um identificador de ambiente e um identificador de conexão.</span><span class="sxs-lookup"><span data-stu-id="2fab8-110">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="2fab8-111">Defina SQL_COPT_SS_BCP e SQL_BCP_ON para habilitar operações de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="2fab8-111">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="2fab8-112">Conecte-se ao SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2fab8-112">Connect to SQL Server.</span></span>  
  
4.  <span data-ttu-id="2fab8-113">Chame [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) para definir as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="2fab8-113">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="2fab8-114">O nome da tabela ou da exibição da qual ou para a qual será feita a cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="2fab8-114">The name of the table or view to bulk copy from or to.</span></span>  
  
    -   <span data-ttu-id="2fab8-115">O nome do arquivo de dados que contém os dados a serem copiados para o banco de dados ou que recebe os dados ao copiar do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2fab8-115">The name of the data file that contains the data to copy into the database or that receives data when copying from the database.</span></span>  
  
    -   <span data-ttu-id="2fab8-116">O nome de um arquivo de dados que receberá qualquer mensagem de erro de cópia em massa (especifique NULL se não desejar um arquivo de mensagens).</span><span class="sxs-lookup"><span data-stu-id="2fab8-116">The name of a data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="2fab8-117">A direção da cópia: DB_IN do arquivo para a exibição ou tabela, ou DB_OUT para o arquivo da tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="2fab8-117">The direction of the copy: DB_IN from the file to the view or table, or DB_OUT to the file from the table or view.</span></span>  
  
5.  <span data-ttu-id="2fab8-118">Chame [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) para executar a operação de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="2fab8-118">Call [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="2fab8-119">Quando DB_OUT é definido com essas etapas, o arquivo é criado no formato nativo.</span><span class="sxs-lookup"><span data-stu-id="2fab8-119">When DB_OUT is set with these steps, the file is created in native format.</span></span> <span data-ttu-id="2fab8-120">O arquivo pode ser copiado em massa para um servidor seguindo essas mesmas etapas, a não ser que DB_OUT seja definido em vez de DB_IN.</span><span class="sxs-lookup"><span data-stu-id="2fab8-120">The file can then be bulk copied into a server by following these same steps, except that DB_OUT is set instead of DB_IN.</span></span> <span data-ttu-id="2fab8-121">Isso só funcionará se ambas as tabelas (origem e destino) tiverem exatamente a mesma estrutura.</span><span class="sxs-lookup"><span data-stu-id="2fab8-121">This works only if both the source and target tables have exactly the same structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fab8-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2fab8-122">Example</span></span>  
 <span data-ttu-id="2fab8-123">Este exemplo não tem suporte em IA64.</span><span class="sxs-lookup"><span data-stu-id="2fab8-123">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="2fab8-124">Será necessária uma fonte de dados ODBC chamada AdventureWorks, cujo banco de dados padrão é o banco de dados de exemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2fab8-124">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="2fab8-125">(Você pode baixar o banco de dados de exemplo AdventureWorks do [Microsoft SQL Server exemplos e projetos da comunidade](https://go.microsoft.com/fwlink/?LinkID=85384) Home Page.) Essa fonte de dados deve ser baseada no driver ODBC fornecido pelo sistema operacional (o nome do driver é "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="2fab8-125">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="2fab8-126">Se você compilar e executar esse exemplo como um aplicativo de 32 bits em um sistema operacional de 64 bits, deverá criar a fonte de dados ODBC com o Administrador ODBC em %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="2fab8-126">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="2fab8-127">Esse aplicativo se conecta à instância padrão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] do computador.</span><span class="sxs-lookup"><span data-stu-id="2fab8-127">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="2fab8-128">Para conectar-se a uma instância nomeada, altere a definição da fonte de dados ODBC para especificar a instância usando o seguinte formato: servidor\instância_nomeada.</span><span class="sxs-lookup"><span data-stu-id="2fab8-128">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="2fab8-129">Por padrão, o [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] é instalado em uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="2fab8-129">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="2fab8-130">Compile com odbc32.lib e odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="2fab8-130">Compile with odbc32.lib and odbcbcp.lib.</span></span>  
  
```  
// compile with: odbc32.lib odbcbcp.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
#define MAXBUFLEN 256  
  
SQLHENV henv = SQL_NULL_HENV;  
HDBC hdbc1 = SQL_NULL_HDBC;  
  
void Cleanup() {  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
  
   // Bulk copy variables.  
   SDWORD cRows;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle, set bulk copy mode, and then connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetConnectAttr(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security, create the SQL Server DSN using Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "Purchasing.Vendor", "BCPODBC.bcp", "BCPERROR.out", DB_OUT);  
   // Test is for the bulk copy return of SUCCEED, not the ODBC return of SQL_SUCCESS.  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_exec(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied out = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2fab8-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2fab8-131">See Also</span></span>  
 [<span data-ttu-id="2fab8-132">Tópicos de instruções sobre cópia em massa com o SQL Server ODBC Driver &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="2fab8-132">Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;</span></span>](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md)  
  
  