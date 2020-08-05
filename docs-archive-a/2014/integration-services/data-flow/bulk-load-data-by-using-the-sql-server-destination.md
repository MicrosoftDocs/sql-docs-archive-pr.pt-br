---
title: Carregar dados em massa por meio do destino do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server destination
- loading data
- destinations [Integration Services], SQL Server
- inserting data
- bulk load [Integration Services]
ms.assetid: 8f982f85-a82e-4e2d-9cd8-cd2f85402d8e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 92ed530ae849f7a4ce123cded421ac0cd0c411ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573221"
---
# <a name="bulk-load-data-by-using-the-sql-server-destination"></a><span data-ttu-id="d5ae6-102">Carregar dados em massa por meio do destino do SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5ae6-102">Bulk Load Data by Using the SQL Server Destination</span></span>
  <span data-ttu-id="d5ae6-103">Para adicionar e configurar um destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o pacote já deve incluir pelo menos uma tarefa de Fluxo de Dados e uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-103">To add and configure a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, the package must already include at least one Data Flow task and a data source.</span></span>  
  
### <a name="to-load-data-using-a-sql-server-destination"></a><span data-ttu-id="d5ae6-104">Para carregar dados usando um destino de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5ae6-104">To load data using a SQL Server destination</span></span>  
  
1.  <span data-ttu-id="d5ae6-105">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="d5ae6-106">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="d5ae6-107">Clique na guia **Fluxo de Dados** , e então, na **Caixa de Ferramentas**, arraste o destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination to the design surface.</span></span>  
  
4.  <span data-ttu-id="d5ae6-108">Conecte o destino a uma fonte ou a uma transformação prévia no fluxo de dados arrastando um conector para o destino.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-108">Connect the destination to a source or a previous transformation in the data flow by dragging a connector to the destination.</span></span>  
  
5.  <span data-ttu-id="d5ae6-109">Clique duas vezes no destino.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-109">Double-click the destination.</span></span>  
  
6.  <span data-ttu-id="d5ae6-110">No **Editor de Destino do SQL Server**, na página **Gerenciador de Conexões** , selecione um gerenciador de conexões OLE DB existente ou clique em **Novo** para criar um gerenciador de conexões novo.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-110">In the **SQL Server Destination Editor**, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="d5ae6-111">Para obter mais informações, consulte [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d5ae6-111">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="d5ae6-112">Para especificar a tabela ou exibir em qual tabela serão carregados os dados, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="d5ae6-112">To specify the table or view into which to load the data, do one of the following:</span></span>  
  
    -   <span data-ttu-id="d5ae6-113">Selecione uma tabela ou exibição existente.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-113">Select an existing table or view.</span></span>  
  
    -   <span data-ttu-id="d5ae6-114">Clique em **Novo**e, na caixa de diálogo **Criar Tabela** , escreva uma instrução SQL que cria uma tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-114">Click **New**, and in the **Create Table** dialog boxwrite an SQL statement that creates a table or view.</span></span>  
  
        > [!NOTE]  
        >  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="d5ae6-115">gera uma instrução CREATE TABLE padrão baseada na fonte de dados conectada.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-115">generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="d5ae6-116">A instrução CREATE TABLE padrão não incluirá o atributo FILESTREAM mesmo que a tabela de origem inclua uma coluna com o atributo FILESTREAM declarado.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-116">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="d5ae6-117">Para executar um componente [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] com o atributo FILESTREAM, implemente primeiro o armazenamento FILESTREAM no banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-117">To run an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="d5ae6-118">Em seguida, adicione o atributo FILESTREAM à instrução CREATE TABLE na caixa de diálogo **Criar Tabela** .</span><span class="sxs-lookup"><span data-stu-id="d5ae6-118">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="d5ae6-119">Para obter mais informações, consulte [Dados de blob &#40;objeto binário grande&#41; &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d5ae6-119">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
8.  <span data-ttu-id="d5ae6-120">Clique em **Mapeamentos** e mapeie as colunas da lista **Colunas de Entrada Disponíveis** para colunas na lista **Colunas de Destino Disponíveis** arrastando colunas de uma lista para outra.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-120">Click **Mappings** and map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d5ae6-121">O destino mapeia colunas do mesmo nome automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-121">The destination automatically maps same-named columns.</span></span>  
  
9. <span data-ttu-id="d5ae6-122">Clique em **Avançado** e defina as opções de carregamento em massa: **Manter identidade**, **Manter nulos**, **Bloqueio de tabela**, **Verificar restrições**e **Gatilhos**.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-122">Click **Advanced** and set the bulk load options: **Keep identity**, **Keep nulls**, **Table lock**, **Check constraints**, and **Fire triggers**.</span></span>  
  
     <span data-ttu-id="d5ae6-123">Opcionalmente, especifique a primeira e a última linha de entrada a serem inseridas, o número máximo de erros que podem acontecer antes da operação de inserção ser interrompida e as colunas em que a inserção é classificada.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-123">Optionally, specify the first and last input rows to insert, the maximum number of errors that can occur before the insert operation stops, and the columns on which the insert is sorted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d5ae6-124">A ordem de classificação é determinada pela ordem em que as colunas são relacionadas.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-124">The sort order is determined by the order in which the columns are listed.</span></span>  
  
10. <span data-ttu-id="d5ae6-125">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5ae6-125">Click **OK**.</span></span>  
  
11. <span data-ttu-id="d5ae6-126">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="d5ae6-126">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ae6-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d5ae6-127">See Also</span></span>  
 <span data-ttu-id="d5ae6-128">[SQL Server Destination](sql-server-destination.md) </span><span class="sxs-lookup"><span data-stu-id="d5ae6-128">[SQL Server Destination](sql-server-destination.md) </span></span>  
 <span data-ttu-id="d5ae6-129">[Transformações do Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="d5ae6-129">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="d5ae6-130">[Caminhos do Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="d5ae6-130">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="d5ae6-131">Tarefa de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="d5ae6-131">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
