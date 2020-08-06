---
title: Acessando a funcionalidade SQLXML no ambiente .NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], accessing SQLXML functionality
- SQLXML Managed Classes, accessing SQLXML functionality
- DiffGrams [SQLXML], accessing SQLXML functionality
- .NET Framework [SQLXML], accessing SQLXML functionality
ms.assetid: 74744535-2945-414d-9a5b-7e8cc363953a
author: rothja
ms.author: jroth
ms.openlocfilehash: a2ba0a54310833c0a1a1315aa94d78fe5650d480
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574593"
---
# <a name="accessing-sqlxml-functionality-in-the-net-environment"></a><span data-ttu-id="ace1c-102">Acessando a funcionalidade SQLXML no ambiente .NET</span><span class="sxs-lookup"><span data-stu-id="ace1c-102">Accessing SQLXML Functionality in the .NET Environment</span></span>
  <span data-ttu-id="ace1c-103">Este exemplo mostra:</span><span class="sxs-lookup"><span data-stu-id="ace1c-103">This example shows:</span></span>  
  
-   <span data-ttu-id="ace1c-104">Como usar [!INCLUDE[msCoName](../../../includes/msconame-md.md)] classes gerenciadas SQLXML (Microsoft. Data. SQLXML) para acessar [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a Microsoft no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] ambiente de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ace1c-104">How to use [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML Managed Classes (Microsoft.Data.SqlXml) to access Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework environment.</span></span>  
  
-   <span data-ttu-id="ace1c-105">Como os DiffGrams que são gerados no ambiente .NET Framework podem aplicar atualizações de dados a tabelas do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ace1c-105">How DiffGrams that are generated in the .NET Framework environment can apply data updates to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables.</span></span>  
  
 <span data-ttu-id="ace1c-106">Neste aplicativo, uma consulta XPath é executada em um esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="ace1c-106">In this application, an XPath query is executed against an XSD schema.</span></span> <span data-ttu-id="ace1c-107">A execução da consulta XPath retorna um documento XML que consiste em dados de contato (**FirstName**, **LastName**).</span><span class="sxs-lookup"><span data-stu-id="ace1c-107">The execution of the XPath query returns an XML document that consists of contact data (**FirstName**, **LastName**).</span></span> <span data-ttu-id="ace1c-108">O aplicativo carrega o documento XML no conjunto de dados no ambiente .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ace1c-108">The application loads the XML document in the dataset in the .NET Framework environment.</span></span> <span data-ttu-id="ace1c-109">Os dados no conjunto de dados são modificados: o nome do contato é alterado para "Susan", para o primeiro contato no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="ace1c-109">The data in the dataset is modified: the contact's first name is changed to "Susan" for the first contact in the dataset.</span></span> <span data-ttu-id="ace1c-110">O DiffGram é gerado a partir do conjunto de dados, e a atualização que é especificada no DiffGram (a alteração do nome do funcionário) é então aplicada à tabela Person.Contact.</span><span class="sxs-lookup"><span data-stu-id="ace1c-110">The DiffGram is generated from the dataset, and the update that is specified in the DiffGram (the change in the employee's first name) is then applied to the Person.Contact table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ace1c-111">No código, é necessário fornecer o nome da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="ace1c-111">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using System.Data;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=SqlServerName;database=AdventureWorks;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      DataRow row;  
      SqlXmlAdapter ad;  
      //need a memory stream to hold diff gram temporarily  
      MemoryStream ms = new MemoryStream();  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.RootTag = "ROOT";  
      cmd.CommandText = "Con";  
      cmd.CommandType = SqlXmlCommandType.XPath;  
      cmd.SchemaPath = "MySchema.xml";  
      //load data set  
      DataSet ds = new DataSet();  
      ad = new SqlXmlAdapter(cmd);  
      ad.Fill(ds);  
      row = ds.Tables["Con"].Rows[0];  
      row["FName"] = "Susan";  
      ad.Update(ds);  
      return 0;  
   }  
   public static int Main(String[] args)  
   {  
      testParams();  
      return 0;  
   }  
}  
```  
  
 <span data-ttu-id="ace1c-112">**Para testar o exemplo:**</span><span class="sxs-lookup"><span data-stu-id="ace1c-112">**To test the example:**</span></span>  
  
 <span data-ttu-id="ace1c-113">Para testar este exemplo, é necessário ter o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="ace1c-113">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
1.  <span data-ttu-id="ace1c-114">Salve este esquema XSD (MySchema.xml) em uma pasta:</span><span class="sxs-lookup"><span data-stu-id="ace1c-114">Save this XSD schema (MySchema.xml) in a folder:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="Con" sql:relation="Person.Contact" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="FName"    
                         sql:field="FirstName"   
                         type="xsd:string" />   
            <xsd:element name="LName"    
                         sql:field="LastName"    
                         type="xsd:string" />  
         </xsd:sequence>  
         <xsd:attribute name="ContactID" type="xsd:integer" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
2.  <span data-ttu-id="ace1c-115">Salve o código C# (DocSample.cs) fornecido neste exemplo na mesma pasta na qual o esquema está armazenado.</span><span class="sxs-lookup"><span data-stu-id="ace1c-115">Save the C# code (DocSample.cs) provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="ace1c-116">(Se você armazenar os arquivos em pastas diferentes, terá que editar o código e especificar o caminho de diretório apropriado para o esquema de mapeamento.)</span><span class="sxs-lookup"><span data-stu-id="ace1c-116">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="ace1c-117">Compile o código.</span><span class="sxs-lookup"><span data-stu-id="ace1c-117">Compile the code.</span></span> <span data-ttu-id="ace1c-118">Para compilar o código no prompt de comando, use:</span><span class="sxs-lookup"><span data-stu-id="ace1c-118">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="ace1c-119">Isso cria um executável (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="ace1c-119">This creates an executable (DocSample.exe).</span></span>  
  
 <span data-ttu-id="ace1c-120">No prompt de comando, execute DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="ace1c-120">At the command prompt, execute DocSample.exe.</span></span>  
  
  
