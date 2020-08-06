---
title: Criar um domínio de composição | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.createcd.f1
- sql12.dqs.dm.cdproperties.f1
ms.assetid: c7f0bd84-a02e-4a81-885d-985e6415c499
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3ea21363e088b763307017485596a54aca6605f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678975"
---
# <a name="create-a-composite-domain"></a><span data-ttu-id="60ce4-102">Criar um domínio composto</span><span class="sxs-lookup"><span data-stu-id="60ce4-102">Create a Composite Domain</span></span>
  <span data-ttu-id="60ce4-103">Este tópico descreve como criar um domínio composto em uma base de dados de conhecimento no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="60ce4-103">This topic describes how to create a composite domain in a knowledge base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="60ce4-104">Um domínio composto consiste em um ou mais domínios únicos que se aplicam a um campo de dados único.</span><span class="sxs-lookup"><span data-stu-id="60ce4-104">A composite domain consists of one or more single domains that apply to a single data field.</span></span> <span data-ttu-id="60ce4-105">Para obter mais informações sobre domínios de composição, consulte [Gerenciando um domínio de composição](../../2014/data-quality-services/managing-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="60ce4-105">For more information on composite domains, see [Managing a Composite Domain](../../2014/data-quality-services/managing-a-composite-domain.md).</span></span>  
  
 <span data-ttu-id="60ce4-106">Há duas maneiras de criar um novo domínio composto.</span><span class="sxs-lookup"><span data-stu-id="60ce4-106">There are two ways to create a new composite domain.</span></span> <span data-ttu-id="60ce4-107">A primeira é durante a etapa Mapear da atividade de descoberta da base de dados de conhecimento, quando você está no processo de analisar um exemplo de dados para adicionar conhecimento a uma base de dados de conhecimento nova ou existente.</span><span class="sxs-lookup"><span data-stu-id="60ce4-107">The first is during the Map step of the knowledge discovery activity, when you are in the process of analyzing a data sample to add knowledge to a new or existing knowledge base.</span></span> <span data-ttu-id="60ce4-108">A segunda é durante a atividade de gerenciamento de domínio, quando, em vez de alterar um domínio existente, você cria um novo domínio.</span><span class="sxs-lookup"><span data-stu-id="60ce4-108">The second is during the domain management activity, when instead of changing an existing domain, you create a new one.</span></span> <span data-ttu-id="60ce4-109">Para criar um domínio composto, você já deve ter criado pelo menos dois domínios únicos para adicionar ao domínio composto.</span><span class="sxs-lookup"><span data-stu-id="60ce4-109">In order to create a composite domain, you must already have created at least two single domains to add to the composite domain.</span></span> <span data-ttu-id="60ce4-110">Somente os domínios únicos que já foram criados e não foram adicionados a um domínio composto existente estão disponíveis quando você cria um novo domínio composto.</span><span class="sxs-lookup"><span data-stu-id="60ce4-110">Only those single domains that have already been created and that have not been added to an existing composite domain are available when you create a new composite domain.</span></span> <span data-ttu-id="60ce4-111">Um domínio único não pode ser adicionado a mais de um domínio composto e um domínio composto não pode ser adicionado a outro domínio composto.</span><span class="sxs-lookup"><span data-stu-id="60ce4-111">A single domain cannot be added to more than one composite domain, and a composite domain cannot be added to another composite domain.</span></span>  
  
 <span data-ttu-id="60ce4-112">Depois de criar um domínio composto, você pode alterar as propriedades do domínio composto, associar um serviço de dados de referência ao domínio, criar as regras de domínio cruzado ou criar relações de valor.</span><span class="sxs-lookup"><span data-stu-id="60ce4-112">After creating a composite domain, you can change the properties of the composite domain, attach a reference data service to the domain, create cross-domain rules, or create value relations.</span></span> <span data-ttu-id="60ce4-113">Para fazer isso, selecione o domínio composto na lista **Domínio** da página **Gerenciamento de Domínio** e selecione a guia apropriada.</span><span class="sxs-lookup"><span data-stu-id="60ce4-113">To do so, select the composite domain in the **Domain** list of the **Domain Management** page, and select the appropriate tab.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="60ce4-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="60ce4-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="60ce4-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="60ce4-115">Prerequisites</span></span>  
 <span data-ttu-id="60ce4-116">Para criar um domínio composto, você já deve ter criado e aberto uma base de dados de conhecimento e deve ter criado pelo menos dois domínios únicos para adicionar ao domínio composto.</span><span class="sxs-lookup"><span data-stu-id="60ce4-116">To create a composite domain, you must have created and opened a knowledge base, and you must have created at least two single domains to add to the composite domain.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="60ce4-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="60ce4-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="60ce4-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="60ce4-118">Permissions</span></span>  
 <span data-ttu-id="60ce4-119">Você deve ter a função dqs_kb_editor ou dqs_administrator no banco de dados DQS_MAIN para criar um domínio composto.</span><span class="sxs-lookup"><span data-stu-id="60ce4-119">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to create a composite domain.</span></span>  
  
##  <a name="create-a-composite-domain-in-the-knowledge-discovery-activity"></a><a name="ParsingKnowledgeDiscoveryActivity"></a><span data-ttu-id="60ce4-120">Criar um domínio composto na atividade de descoberta da base de dados de conhecimento</span><span class="sxs-lookup"><span data-stu-id="60ce4-120">Create a Composite Domain in the Knowledge Discovery Activity</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="60ce4-121">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="60ce4-121">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="60ce4-122">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Abrir base de dados de conhecimento** e selecione uma base de dados de conhecimento ou clique em **Nova base de dados de conhecimento** e insira propriedades para a nova base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="60ce4-122">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base** and then select a knowledge base, or click **New knowledge base** and enter properties for the new knowledge base.</span></span>  
  
3.  <span data-ttu-id="60ce4-123">Selecione **Descoberta da Base de Dados de Conhecimento** como a atividade e clique em **Criar** para criar a nova base de dados de conhecimento ou em **Abrir** para abrir uma base de dados de conhecimento existente.</span><span class="sxs-lookup"><span data-stu-id="60ce4-123">Select **Knowledge Discovery** as the activity, and then click **Create** to create the new knowledge base or **Open** to open an existing knowledge base.</span></span>  
  
4.  <span data-ttu-id="60ce4-124">Na página **Mapa** , especifique uma conexão com a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="60ce4-124">On the **Map** page, specify a connection to the data source.</span></span> <span data-ttu-id="60ce4-125">Para obter mais informações, consulte [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="60ce4-125">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md).</span></span>  
  
5.  <span data-ttu-id="60ce4-126">Na tabela **Mapeamentos** , selecione uma coluna de origem na lista suspensa da coluna **Coluna de Origem** de uma linha vazia.</span><span class="sxs-lookup"><span data-stu-id="60ce4-126">In the **Mappings** table, select a source column from the drop-down list for the **Source Column** column of an empty row.</span></span> <span data-ttu-id="60ce4-127">Verifique se a coluna de origem contém o domínio composto endereçado por dois domínios únicos existentes.</span><span class="sxs-lookup"><span data-stu-id="60ce4-127">Make sure that the source column contains composite domain addressed by two existing single domains.</span></span> <span data-ttu-id="60ce4-128">Se não existir nenhum domínio único correspondente, clique no ícone **Criar um Domínio** .</span><span class="sxs-lookup"><span data-stu-id="60ce4-128">If no corresponding single domains exists, click the **Create a Domain** icon.</span></span>  
  
6.  <span data-ttu-id="60ce4-129">Na tabela **Mapeamentos** , selecione uma coluna de origem na lista suspensa da coluna **Coluna de Origem** de uma linha vazia.</span><span class="sxs-lookup"><span data-stu-id="60ce4-129">In the **Mappings** table, select a source column from the drop-down list for the **Source Column** column of an empty row.</span></span> <span data-ttu-id="60ce4-130">Verifique se a coluna de origem contém as partes do domínio composto que são endereçadas por dois domínios únicos existentes.</span><span class="sxs-lookup"><span data-stu-id="60ce4-130">Ensure that the source column contains composite domain parts of which are addressed by two existing single domains.</span></span> <span data-ttu-id="60ce4-131">Se não existir nenhum domínio único correspondente, clique no ícone **Criar um Domínio** para criá-los.</span><span class="sxs-lookup"><span data-stu-id="60ce4-131">If no corresponding single domains exist, click the **Create a Domain** icon to create them.</span></span> <span data-ttu-id="60ce4-132">Para obter mais informações, consulte [Criar um domínio](../../2014/data-quality-services/create-a-domain.md).</span><span class="sxs-lookup"><span data-stu-id="60ce4-132">For more information, see [Create a Domain](../../2014/data-quality-services/create-a-domain.md).</span></span>  
  
7.  <span data-ttu-id="60ce4-133">Clique no ícone **Criar um Domínio Composto** .</span><span class="sxs-lookup"><span data-stu-id="60ce4-133">Click the **Create a Composite** Domain icon.</span></span>  
  
##  <a name="create-a-composite-domain-in-the-domain-management-activity"></a><a name="DomainManagementActivity"></a><span data-ttu-id="60ce4-134">Criar um domínio composto na atividade de gerenciamento de domínio</span><span class="sxs-lookup"><span data-stu-id="60ce4-134">Create a Composite Domain in the Domain Management Activity</span></span>  
  
1.  <span data-ttu-id="60ce4-135">Na home page do cliente Data Quality Services, clique em **Abrir base de dados de conhecimento** e selecione uma base de dados de conhecimento ou clique em **Nova base de dados de conhecimento** e insira propriedades para a nova base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="60ce4-135">In the Data Quality Services client home page, click **Open knowledge base** and then select a knowledge base, or click **New knowledge base** and enter properties for the new knowledge base.</span></span>  
  
2.  <span data-ttu-id="60ce4-136">Selecione **Gerenciamento de Domínio** como a atividade e clique em **Criar** para criar a nova base de dados de conhecimento ou em **Abrir** para abrir uma base de dados de conhecimento existente.</span><span class="sxs-lookup"><span data-stu-id="60ce4-136">Select **Domain Management** as the activity, and then click **Create** to create the new knowledge base or **Open** to open an existing knowledge base.</span></span>  
  
3.  <span data-ttu-id="60ce4-137">Verifique se existem dois ou mais domínios únicos necessários para o domínio composto.</span><span class="sxs-lookup"><span data-stu-id="60ce4-137">Ensure that two or more single domains required by the composite domain exist.</span></span> <span data-ttu-id="60ce4-138">Se não existirem, clique no ícone **Criar um Domínio** e crie-os.</span><span class="sxs-lookup"><span data-stu-id="60ce4-138">If not, click the **Create a Domain** icon and create them.</span></span> <span data-ttu-id="60ce4-139">Para obter mais informações, consulte [Criar um domínio](../../2014/data-quality-services/create-a-domain.md).</span><span class="sxs-lookup"><span data-stu-id="60ce4-139">For more information, see [Create a Domain](../../2014/data-quality-services/create-a-domain.md).</span></span>  
  
4.  <span data-ttu-id="60ce4-140">Na página **Gerenciamento de Domínio** , clique no ícone **Criar um Domínio Composto** acima da lista de domínios.</span><span class="sxs-lookup"><span data-stu-id="60ce4-140">On the **Domain Management** page, click the **Create a Composite Domain** icon above the Domain list.</span></span>  
  
5.  <span data-ttu-id="60ce4-141">Insira um nome que seja exclusivo para a base de dados de conhecimento e uma descrição com até 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="60ce4-141">Enter a name that is unique to the knowledge base and a description up to 256 characters.</span></span>  
  
6.  <span data-ttu-id="60ce4-142">Na **Lista de Domínios**, selecione os domínios que farão parte do domínio composto e clique na seta para direita para movê-los para a tabela **Domínios no Domínio Composto** .</span><span class="sxs-lookup"><span data-stu-id="60ce4-142">In the **Domains List**, select the domains that will be part of the composite domain, and click the right arrow to move them to the **Domains in Composite Domain** table.</span></span>  
  
7.  <span data-ttu-id="60ce4-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="60ce4-143">Click **OK**.</span></span>  
  
##  <a name="set-composite-domain-properties"></a><a name="CompositeDomainProperties"></a><span data-ttu-id="60ce4-144">Definir propriedades de domínio composto</span><span class="sxs-lookup"><span data-stu-id="60ce4-144">Set Composite Domain Properties</span></span>  
  
1.  <span data-ttu-id="60ce4-145">Na caixa de diálogo **Criar um Domínio Composto** , insira um nome que seja exclusivo para a base de dados de conhecimento e uma descrição com até 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="60ce4-145">In the **Create a Composite Domain** dialog box, enter a name that is unique to the knowledge base and a description up to 256 characters.</span></span>  
  
2.  <span data-ttu-id="60ce4-146">Na **Lista de Domínios**, selecione os domínios que farão parte do domínio composto e clique na seta para direita para movê-los para a tabela **Domínios no Domínio Composto** .</span><span class="sxs-lookup"><span data-stu-id="60ce4-146">In the **Domains List**, select the domains that will be part of the composite domain, and click the right arrow to move them to the **Domains in Composite Domain** table.</span></span> <span data-ttu-id="60ce4-147">Esta é uma lista de domínios únicos que estão disponíveis para adição ao domínio composto que você está criando.</span><span class="sxs-lookup"><span data-stu-id="60ce4-147">This is a list of single domains that are available to be added to the composite domain that you are creating.</span></span> <span data-ttu-id="60ce4-148">Somente os domínios únicos que já foram criados e não foram adicionados a um domínio composto existente estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="60ce4-148">Only those single domains that have already been created and that have not been added to an existing composite domain are available.</span></span> <span data-ttu-id="60ce4-149">Um domínio único não pode ser adicionado a mais de um domínio composto na base de dados de conhecimento e um domínio composto não pode ser adicionado a outro domínio composto.</span><span class="sxs-lookup"><span data-stu-id="60ce4-149">A single domain cannot be added to more than one composite domain in the knowledge base, and a composite domain cannot be added to another composite domain.</span></span>  
  
3.  <span data-ttu-id="60ce4-150">Clique em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="60ce4-150">Click **Advanced**.</span></span>  
  
4.  <span data-ttu-id="60ce4-151">Selecione uma das seguintes opções como o **Método de Análise**:</span><span class="sxs-lookup"><span data-stu-id="60ce4-151">Select one of the following for the **Parsing Method**:</span></span>  
  
    -   <span data-ttu-id="60ce4-152">**Dados de Referência**: analise os valores do campo de acordo com o modo como os dados são formatados pelo RDS (Serviços de Dados de Referência).</span><span class="sxs-lookup"><span data-stu-id="60ce4-152">**Reference Data**: Parse the field's values according to how the data is formatted by the Reference Data Service (RDS).</span></span> <span data-ttu-id="60ce4-153">O Data Quality Services enviará os valores no domínio composto ao RDS e o RDS retornará os dados corrigidos e analisados de acordo com o domínio no domínio composto.</span><span class="sxs-lookup"><span data-stu-id="60ce4-153">Data Quality Services will send the values in the composite domain to the RDS, and the RDS returns the data corrected and parsed according to the domain in the composite domain.</span></span>  
  
    -   <span data-ttu-id="60ce4-154">**Em Ordem**: analise os valores do campo de acordo com a ordem dos domínios no domínio composto.</span><span class="sxs-lookup"><span data-stu-id="60ce4-154">**In Order**: Parse the field's values according to the order of domains in the composite domain.</span></span> <span data-ttu-id="60ce4-155">O primeiro valor será incluído no primeiro domínio, o segundo valor no segundo domínio etc.</span><span class="sxs-lookup"><span data-stu-id="60ce4-155">The first value will be included in the first domain, the second value in the second domains, and so on.</span></span>  
  
    -   <span data-ttu-id="60ce4-156">**Delimitadores**: analise os valores de campo com base no delimitador selecionado dentre os botões de opção exibidos quando os Delimitadores estão selecionados.</span><span class="sxs-lookup"><span data-stu-id="60ce4-156">**Delimiters**: Parse the field's values based on the delimiter selected from the radio buttons displayed when Delimiters is selected.</span></span> <span data-ttu-id="60ce4-157">Esses podem ser: **Guia**, **Ponto-e-vírgula**, **Vírgula**, **Espaço**ou **Outro**.</span><span class="sxs-lookup"><span data-stu-id="60ce4-157">Can be **Tab**, **Semicolon**, **Comma**, **Space**, or **Other**.</span></span> <span data-ttu-id="60ce4-158">Se **Outro**, insira o valor que atuará como o delimitador.</span><span class="sxs-lookup"><span data-stu-id="60ce4-158">If **Other**, enter the value that will serve as the delimiter.</span></span>  
  
5.  <span data-ttu-id="60ce4-159">Se você selecionou **Delimitadores** como o método de análise, também poderá selecionar **Usar Análise da Base de Dados de Conhecimento**.</span><span class="sxs-lookup"><span data-stu-id="60ce4-159">If you selected **Delimiters** for the parsing method, you can also select **Use Knowledge Based Parsing**.</span></span> <span data-ttu-id="60ce4-160">Para obter mais informações, consulte [Knowledge-Based Parsing](#KnowledgeBaseParsing).</span><span class="sxs-lookup"><span data-stu-id="60ce4-160">For more information, see [Knowledge-Based Parsing](#KnowledgeBaseParsing).</span></span>  
  
6.  <span data-ttu-id="60ce4-161">Clique em **Concluir** para concluir a atividade de gerenciamento de domínio, conforme descrito em [Terminar a atividade Gerenciamento de Domínio](../../2014/data-quality-services/end-the-domain-management-activity.md).</span><span class="sxs-lookup"><span data-stu-id="60ce4-161">Click **Finish** to complete the domain management activity, as described in [End the Domain Management Activity](../../2014/data-quality-services/end-the-domain-management-activity.md).</span></span>  
  
##  <a name="follow-up-after-creating-a-composite-domain"></a><a name="FollowUp"></a><span data-ttu-id="60ce4-162">Acompanhamento: depois de criar um domínio composto</span><span class="sxs-lookup"><span data-stu-id="60ce4-162">Follow Up: After Creating a Composite Domain</span></span>  
 <span data-ttu-id="60ce4-163">Depois que você criar um domínio composto, poderá executar outras tarefas de gerenciamento de domínio, poderá executar a descoberta da base de dados de conhecimento para adicionar conhecimento ao domínio ou poderá adicionar uma política de correspondência ao domínio.</span><span class="sxs-lookup"><span data-stu-id="60ce4-163">After you create a composite domain, you can perform other domain management tasks on the domain, you can perform knowledge discovery to add knowledge to the domain, or you can add a matching policy to the domain.</span></span> <span data-ttu-id="60ce4-164">Para obter mais informações, consulte [Executar a descoberta de conhecimento](../../2014/data-quality-services/perform-knowledge-discovery.md), [Gerenciando um domínio](../../2014/data-quality-services/managing-a-domain.md) ou [Criar uma política de conciliação](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="60ce4-164">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
##  <a name="knowledge-based-parsing"></a><a name="KnowledgeBaseParsing"></a><span data-ttu-id="60ce4-165">Análise baseada em conhecimento</span><span class="sxs-lookup"><span data-stu-id="60ce4-165">Knowledge-Based Parsing</span></span>  
 <span data-ttu-id="60ce4-166">O Data Quality Services permite que você analise os dados com base no conhecimento, não apenas no delimitador ou na ordem.</span><span class="sxs-lookup"><span data-stu-id="60ce4-166">Data Quality Services enables you to parse data based on knowledge, not just on delimiter or order.</span></span> <span data-ttu-id="60ce4-167">A análise baseada em conhecimento é usada quando fontes de dados complexas são mapeadas para um domínio composto e você não está usando serviços de dados de referência.</span><span class="sxs-lookup"><span data-stu-id="60ce4-167">Knowledge-based parsing is used when complex source data is mapped to a composite domain, and you are not using reference data services.</span></span> <span data-ttu-id="60ce4-168">Você pode usar a análise baseada em conhecimento para analisar os dados a partir da fonte de dados nos domínios únicos relevantes.</span><span class="sxs-lookup"><span data-stu-id="60ce4-168">You can use knowledge-based parsing to parse the data from the data source into the relevant single domains.</span></span> <span data-ttu-id="60ce4-169">Com a análise baseada em conhecimento, o DQS primeiro tentará usar o conhecimento para analisar os dados complexos em domínios únicos.</span><span class="sxs-lookup"><span data-stu-id="60ce4-169">With knowledge-based parsing, DQS will first attempt to use knowledge to parse complex data into single domains.</span></span> <span data-ttu-id="60ce4-170">Se possível, ela identificará partes da cadeia de caracteres como em um ou mais domínios e analisará a cadeia de caracteres em seus vários domínios.</span><span class="sxs-lookup"><span data-stu-id="60ce4-170">If possible, it will identify parts of the string as in one or more domains, and parse the string into its various domains.</span></span> <span data-ttu-id="60ce4-171">Por exemplo, suponha que tem "John B. Doe" como valores complexos em um campo de nome completo representado por um domínio composto de Nome Completo.</span><span class="sxs-lookup"><span data-stu-id="60ce4-171">For example, suppose you have "John B. Doe" as a complex values in a full-name field represented by a Full Name composite domain.</span></span> <span data-ttu-id="60ce4-172">Se o DQS identificar "John" como no domínio Nome e "Doe" como no domínio Sobrenome e o DQS adicionará "B."</span><span class="sxs-lookup"><span data-stu-id="60ce4-172">If DQS identifies "John" as in the First Name domain, and "Doe" as in the Last Name domain, then DQS will add "B."</span></span> <span data-ttu-id="60ce4-173">ao domínio de Segundo Nome com base no conhecimento do domínio.</span><span class="sxs-lookup"><span data-stu-id="60ce4-173">to the Middle Name domain based on domain knowledge.</span></span>  
  
 <span data-ttu-id="60ce4-174">Você poderá usar a análise baseada em conhecimento somente se também selecionar a análise baseada no delimitador.</span><span class="sxs-lookup"><span data-stu-id="60ce4-174">You can use knowledge-based parsing only if you also select delimiter-based parsing.</span></span> <span data-ttu-id="60ce4-175">A análise baseada em conhecimento não substitui a análise baseada no delimitador, mas a aprimora.</span><span class="sxs-lookup"><span data-stu-id="60ce4-175">Knowledge-based parsing does not replace delimiter parsing, but enhances it.</span></span> <span data-ttu-id="60ce4-176">Somente se não houver nenhum conhecimento para fazer isso é que o DQS usará um delimitador para realizar a análise.</span><span class="sxs-lookup"><span data-stu-id="60ce4-176">Only if no knowledge exists to do that will DQS use a delimiter to do the parsing.</span></span> <span data-ttu-id="60ce4-177">Em algumas instâncias, o DQS poderá determinar parte da análise executando a análise baseada no conhecimento e depois determinar outra análise pela análise baseada no delimitador.</span><span class="sxs-lookup"><span data-stu-id="60ce4-177">In some instances, DQS may determine some parsing by knowledge-based parsing, and then determine other parsing by delimiter-based parsing.</span></span>  
  
 <span data-ttu-id="60ce4-178">A análise baseada no conhecimento pode ser usada quando o domínio composto abrange domínios de cadeia de caracteres ou quando o domínio composto abrange uma combinação de tipos diferentes de domínios (int, date, time etc).</span><span class="sxs-lookup"><span data-stu-id="60ce4-178">Knowledge-based parsing can be used when the composite domain is comprised of string domains or when the composite domain is comprised of a mix of different types of domains (int, date, time, etc).</span></span> <span data-ttu-id="60ce4-179">Se a fonte de dados abranger tipos de dados diferentes, a análise deverá ser feita primeiro para os tipos de dados não de cadeias de caracteres e, em seguida, conforme descrito acima com base no conhecimento do domínio do restante dos dados.</span><span class="sxs-lookup"><span data-stu-id="60ce4-179">If the data source is comprised of different types of data, then the parsing should be done first for the non-string data types and then as described above based on domain knowledge for the rest of the data.</span></span>  
  
 <span data-ttu-id="60ce4-180">Quando você está usando a análise baseada em conhecimento e há menos valores na fonte de dados do que domínios no domínio composto, o DQS coloca um valor nulo no domínio ausente.</span><span class="sxs-lookup"><span data-stu-id="60ce4-180">When you are using knowledge-based parsing, and there are fewer values in the source data than there are domains in the composite domain, then DQS will place a null in the missing domain.</span></span> <span data-ttu-id="60ce4-181">Quando há mais valores na fonte de dados do que domínios no domínio composto, o DQS adicionará os dados extras a uma das colunas.</span><span class="sxs-lookup"><span data-stu-id="60ce4-181">When there are more values in the source data than there are domains in the composite domain, then DQS will add the extra data to one of the columns.</span></span> <span data-ttu-id="60ce4-182">Se dois ou mais domínios contiverem os mesmos valores, a fonte de dados será analisada como o primeiro domínio correspondente.</span><span class="sxs-lookup"><span data-stu-id="60ce4-182">If two or more domains include the same values, the data source will be parsed to the first matched domain.</span></span>  
  
  