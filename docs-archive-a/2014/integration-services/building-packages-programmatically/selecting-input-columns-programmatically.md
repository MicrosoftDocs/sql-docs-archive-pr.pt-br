---
title: Selecionar colunas de entrada programaticamente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- input column mapping
- data flow task [Integration Services], components
- data flow task [Integration Services], column mapping
- mapping input columns [Integration Services]
- column mapping [Integration Services]
- data flow [Integration Services], column mapping
- data flow [Integration Services], components
ms.assetid: b53b110a-dcf4-4464-ae98-81e892ab74c3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b36e465d30bc027002c94af4c8a31e4edf50ffc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678940"
---
# <a name="selecting-input-columns-programmatically"></a><span data-ttu-id="1e21b-102">Selecionando colunas de entrada programaticamente</span><span class="sxs-lookup"><span data-stu-id="1e21b-102">Selecting Input Columns Programmatically</span></span>
  <span data-ttu-id="1e21b-103">Depois de ter conectado componentes programaticamente, selecione as colunas dos componentes upstream que você transformará ou passará para os componentes downstream.</span><span class="sxs-lookup"><span data-stu-id="1e21b-103">After you have programmatically connected components, select the columns from upstream components that you will transform or pass through to downstream components.</span></span> <span data-ttu-id="1e21b-104">Se você não selecionar colunas de entrada para seu componente, o componente não receberá nenhuma linha da tarefa de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="1e21b-104">If you do not select input columns for your component, the component does not receive any rows from the data flow task.</span></span>  
  
## <a name="selecting-columns"></a><span data-ttu-id="1e21b-105">Selecionando colunas</span><span class="sxs-lookup"><span data-stu-id="1e21b-105">Selecting Columns</span></span>  
 <span data-ttu-id="1e21b-106">Chame o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.GetVirtualInput%2A> para recuperar a lista de colunas disponíveis de um componente upstream, e chame o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.SetUsageType%2A> da instância do componente de tempo de design para selecionar colunas da coleção de colunas de entrada virtual.</span><span class="sxs-lookup"><span data-stu-id="1e21b-106">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.GetVirtualInput%2A> method to retrieve the list of available columns from an upstream component, then call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.SetUsageType%2A> method of the design-time component instance to select columns from the virtual input column collection.</span></span> <span data-ttu-id="1e21b-107">Quando você chama esse método, o componente cria uma nova coluna de entrada em sua coleção de colunas de entrada com a mesma ID de linhagem da coluna correspondente da coleção de saída do componente upstream.</span><span class="sxs-lookup"><span data-stu-id="1e21b-107">When you call this method, the component creates a new input column in its input column collection that has the same lineage ID as the corresponding column in the output collection of the upstream component.</span></span>  
  
 <span data-ttu-id="1e21b-108">Não selecione colunas chamando o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSVirtualInput100.SetUsageType%2A> do objeto de entrada virtual diretamente, pois ele ignora a capacidade do componente de rejeitar colunas com base em tipos de dados inadequados ou outras propriedades.</span><span class="sxs-lookup"><span data-stu-id="1e21b-108">Do not select columns by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSVirtualInput100.SetUsageType%2A> method of the virtual input object directly, because this bypasses the component's ability to reject columns based on inappropriate data types or other properties.</span></span>  
  
## <a name="sample"></a><span data-ttu-id="1e21b-109">Amostra</span><span class="sxs-lookup"><span data-stu-id="1e21b-109">Sample</span></span>  
 <span data-ttu-id="1e21b-110">O exemplo de código seguinte mostra como usar a instância de tempo de design de um componente para selecionar as colunas para um componente.</span><span class="sxs-lookup"><span data-stu-id="1e21b-110">The following code sample demonstrates how to use the design-time instance of a component to select the columns for a component.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      // Create a package and add a Data Flow task.  
      Package package = new Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      TaskHost thMainPipe = e as TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;  
  
      // Add an OLE DB connection manager to the package.  
      ConnectionManager conMgr = package.Connections.Add("OLEDB");  
      conMgr.ConnectionString = "Provider=SQLOLEDB.1;" +  
        "Data Source=<servername>;Initial Catalog=AdventureWorks;" +  
        "Integrated Security=SSPI;";  
      conMgr.Name = "SSIS Connection Manager for OLE DB";  
      conMgr.Description = "OLE DB connection to the AdventureWorks database.";  
  
      // Create and configure an OLE DB source component.    
      IDTSComponentMetaData100 source =  
        dataFlowTask.ComponentMetaDataCollection.New();  
      source.ComponentClassID = "DTSAdapter.OleDbSource";  
      // Create the design-time instance of the source.  
      CManagedComponentWrapper srcDesignTime = source.Instantiate();  
      // The ProvideComponentProperties method creates a default output.  
      srcDesignTime.ProvideComponentProperties();  
      // Assign the connection manager.  
      source.RuntimeConnectionCollection[0].ConnectionManager =  
        DtsConvert.GetExtendedInterface(conMgr);  
      // Set the custom properties of the source.  
      srcDesignTime.SetComponentProperty("AccessMode", 2);  
      srcDesignTime.SetComponentProperty("SqlCommand",  
        "Select * from Production.Product");  
  
      // Connect to the data source,  
      //  and then update the metadata for the source.  
      srcDesignTime.AcquireConnections(null);  
      srcDesignTime.ReinitializeMetaData();  
      srcDesignTime.ReleaseConnections();  
  
      // Create and configure an OLE DB destination.  
      IDTSComponentMetaData100 destination =  
        dataFlowTask.ComponentMetaDataCollection.New();  
      destination.ComponentClassID = "DTSAdapter.OleDbDestination";  
      // Create the design-time instance of the destination.  
      CManagedComponentWrapper destDesignTime = destination.Instantiate();  
      // The ProvideComponentProperties method creates a default input.  
      destDesignTime.ProvideComponentProperties();  
  
      // Create the path from source to destination.  
      IDTSPath100 path = dataFlowTask.PathCollection.New();  
      path.AttachPathAndPropagateNotifications(source.OutputCollection[0],  
        destination.InputCollection[0]);  
  
      // Get the destination's default input and virtual input.  
      IDTSInput100 input = destination.InputCollection[0];  
      IDTSVirtualInput100 vInput = input.GetVirtualInput();  
  
      // Iterate through the virtual input column collection.  
      foreach (IDTSVirtualInputColumn100 vColumn in vInput.VirtualInputColumnCollection)  
      {  
        // Call the SetUsageType method of the destination  
        //  to add each available virtual input column as an input column.  
        destDesignTime.SetUsageType(  
           input.ID, vInput, vColumn.LineageID, DTSUsageType.UT_READONLY);  
      }  
  
      // Verify that the columns have been added to the input.  
      foreach (IDTSInputColumn100 inputColumn in destination.InputCollection[0].InputColumnCollection)  
        Console.WriteLine(inputColumn.Name);  
      Console.Read();  
  
      // Add other components to the data flow and connect them.  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    ' Create a package and add a Data Flow task.  
    Dim package As Microsoft.SqlServer.Dts.Runtime.Package = _  
      New Microsoft.SqlServer.Dts.Runtime.Package()  
    Dim e As Executable = package.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As Microsoft.SqlServer.Dts.Runtime.TaskHost = _  
      CType(e, Microsoft.SqlServer.Dts.Runtime.TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
    ' Add an OLE DB connection manager to the package.  
    Dim conMgr As ConnectionManager = package.Connections.Add("OLEDB")  
    conMgr.ConnectionString = "Provider=SQLOLEDB.1;" & _  
      "Data Source=<servername>;Initial Catalog=AdventureWorks;" & _  
      "Integrated Security=SSPI;"  
    conMgr.Name = "SSIS Connection Manager for OLE DB"  
    conMgr.Description = "OLE DB connection to the AdventureWorks database."  
  
    ' Create and configure an OLE DB source component.    
    Dim source As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New  
    source.ComponentClassID = "DTSAdapter.OleDbSource"  
    ' Create the design-time instance of the source.  
    Dim srcDesignTime As CManagedComponentWrapper = source.Instantiate  
    ' The ProvideComponentProperties method creates a default output.  
    srcDesignTime.ProvideComponentProperties()  
    ' Assign the connection manager.  
    source.RuntimeConnectionCollection(0).ConnectionManager = _  
      DtsConvert.GetExtendedInterface(conMgr)  
    ' Set the custom properties of the source.  
    srcDesignTime.SetComponentProperty("AccessMode", 2)  
    srcDesignTime.SetComponentProperty("SqlCommand", _  
      "Select * from Production.Product")  
  
    ' Connect to the data source,  
    '  and then update the metadata for the source.  
    srcDesignTime.AcquireConnections(Nothing)  
    srcDesignTime.ReinitializeMetaData()  
    srcDesignTime.ReleaseConnections()  
  
    ' Create and configure an OLE DB destination.  
    Dim destination As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New  
    destination.ComponentClassID = "DTSAdapter.OleDbDestination"  
    ' Create the design-time instance of the destination.  
    Dim destDesignTime As CManagedComponentWrapper = destination.Instantiate  
    ' The ProvideComponentProperties method creates a default input.  
    destDesignTime.ProvideComponentProperties()  
  
    ' Create the path from source to destination.  
    Dim path As IDTSPath100 = dataFlowTask.PathCollection.New  
    path.AttachPathAndPropagateNotifications(source.OutputCollection(0), _  
      destination.InputCollection(0))  
  
    ' Get the destination's default input and virtual input.  
    Dim input As IDTSInput100 = destination.InputCollection(0)  
    Dim vInput As IDTSVirtualInput100 = input.GetVirtualInput  
  
    ' Iterate through the virtual input column collection.  
    For Each vColumn As IDTSVirtualInputColumn100 In vInput.VirtualInputColumnCollection  
      ' Call the SetUsageType method of the destination  
      '  to add each available virtual input column as an input column.  
      destDesignTime.SetUsageType(input.ID, vInput, vColumn.LineageID, DTSUsageType.UT_READONLY)  
    Next  
  
    ' Verify that the columns have been added to the input.  
    For Each inputColumn As IDTSInputColumn100 In destination.InputCollection(0).InputColumnCollection  
      Console.WriteLine(inputColumn.Name)  
    Next  
    Console.Read()  
  
    ' Add other components to the data flow and connect them.  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="1e21b-111">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="1e21b-111">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="1e21b-112">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="1e21b-112">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="1e21b-113">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="1e21b-113">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="1e21b-114">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="1e21b-114">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e21b-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1e21b-115">See Also</span></span>  
 [<span data-ttu-id="1e21b-116">Salvando um pacote programaticamente</span><span class="sxs-lookup"><span data-stu-id="1e21b-116">Saving a Package Programmatically</span></span>](../building-packages-programmatically/saving-a-package-programmatically.md)  
  
  
