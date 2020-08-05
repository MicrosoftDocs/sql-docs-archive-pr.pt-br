---
title: 'Lição 3: carregar uma definição de relatório do servidor de relatório | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ad8b31c-43b0-4481-a31b-090cbed4a438
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: dc6ed26703599792b9c739f8d185ae4f190fc8be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572884"
---
# <a name="lesson-3-load-a-report-definition-from-the-report-server"></a><span data-ttu-id="bacf5-102">Lição 3: Carregar uma definição de relatório do Servidor de Relatório</span><span class="sxs-lookup"><span data-stu-id="bacf5-102">Lesson 3: Load a Report Definition from the Report Server</span></span>
  <span data-ttu-id="bacf5-103">Depois que você criar seu projeto e gerar as classes do esquema RDL, estará pronto para carregar uma definição de relatório do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="bacf5-103">After you have created your project and generated the classes from the RDL schema, you are ready to load a report definition from the report server.</span></span>  
  
### <a name="to-load-a-report-definition"></a><span data-ttu-id="bacf5-104">Para carregar uma definição de relatório</span><span class="sxs-lookup"><span data-stu-id="bacf5-104">To load a report definition</span></span>  
  
1.  <span data-ttu-id="bacf5-105">Adicione um campo particular na parte superior da `ReportUpdater` classe (módulo se você estiver usando [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ) para a `Report` classe.</span><span class="sxs-lookup"><span data-stu-id="bacf5-105">Add a private field at the top of the `ReportUpdater` class (module if you are using [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) for the `Report` class.</span></span> <span data-ttu-id="bacf5-106">Este campo será usado para manter uma referência ao relatório carregado do servidor de relatório enquanto durar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bacf5-106">This field will be used to maintain a reference to report that is loaded from the report server for the life of the application.</span></span>  
  
    ```csharp  
    private Report _report;  
    ```  
  
    ```vb  
    Private m_report As Report  
    ```  
  
2.  <span data-ttu-id="bacf5-107">Substitua o código para o método `LoadReportDefinition()` no arquivo Program.cs (Module1.vb para o [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="bacf5-107">Replace the code for the `LoadReportDefinition()` method in the Program.cs file (Module1.vb for [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) with the following code:</span></span>  
  
    ```csharp  
    private void LoadReportDefinition()  
    {  
        System.Console.WriteLine("Loading Report Definition");  
  
        string reportPath =   
            "/AdventureWorks 2012 Sample Reports/Company Sales 2012";  
  
        // Retrieve the report definition   
        // from the report server  
        byte[] bytes =   
            _reportService.GetItemDefinition(reportPath);  
  
        if (bytes != null)  
        {  
            XmlSerializer serializer =   
                new XmlSerializer(typeof(Report));  
  
            // Load the report bytes into a memory stream  
            using (MemoryStream stream = new MemoryStream(bytes))  
            {  
                // Deserialize the report stream to an   
                // instance of the Report class  
                _report = (Report)serializer.Deserialize(stream);  
            }  
        }  
    }  
    ```  
  
    ```vb  
    Private Sub LoadReportDefinition()  
  
        System.Console.WriteLine("Loading Report Definition")  
  
        Dim reportPath As String = _  
            "/AdventureWorks 2012 Sample Reports/Company Sales 2012"  
  
        'Retrieve the report definition   
        'from the report server  
        Dim bytes As Byte() = _  
            m_reportService.GetItemDefinition(reportPath)  
  
        If Not (bytes Is Nothing) Then  
  
            Dim serializer As XmlSerializer = _  
                New XmlSerializer(GetType(Report))  
  
            'Load the report bytes into a memory stream  
            Using stream As MemoryStream = New MemoryStream(bytes)  
  
                'Deserialize the report stream to an   
                'instance of the Report class  
                m_report = CType(serializer.Deserialize(stream), _  
                                 Report)  
  
            End Using  
  
        End If  
  
    End Sub  
    ```  
  
## <a name="next-lesson"></a><span data-ttu-id="bacf5-108">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="bacf5-108">Next Lesson</span></span>  
 <span data-ttu-id="bacf5-109">Na próxima lição, você escreverá código para atualizar a definição de relatório carregada do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="bacf5-109">In the next lesson, you will write code to update the report definition that was loaded from the report server.</span></span> <span data-ttu-id="bacf5-110">Consulte [lição 4: atualizar a definição de relatório programaticamente](../../2014/tutorials/lesson-4-update-the-report-definition-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="bacf5-110">See [Lesson 4: Update the Report Definition Programmatically](../../2014/tutorials/lesson-4-update-the-report-definition-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bacf5-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bacf5-111">See Also</span></span>  
 <span data-ttu-id="bacf5-112">[Atualizando relatórios usando classes geradas do esquema RDL &#40;tutorial do SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="bacf5-112">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="bacf5-113">Linguagem RDL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bacf5-113">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
