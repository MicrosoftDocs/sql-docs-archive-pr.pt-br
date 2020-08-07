---
title: Origem do arquivo bruto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfilesource.f1
helpviewer_keywords:
- sources [Integration Services], Raw File
- raw data [Integration Services]
- Raw File source
ms.assetid: 5b4daea5-7f76-4674-aa77-0a79f9f97f7d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cbc5800c4fb2b90b74e66b6ff161118b2b550f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571465"
---
# <a name="raw-file-source"></a><span data-ttu-id="98084-102">Origem do arquivo bruto</span><span class="sxs-lookup"><span data-stu-id="98084-102">Raw File Source</span></span>
  <span data-ttu-id="98084-103">A fonte Arquivo Bruto lê dados brutos de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="98084-103">The Raw File source reads raw data from a file.</span></span> <span data-ttu-id="98084-104">Como a representação dos dados é nativa à fonte, os dados não necessitam de conversão e praticamente nenhuma análise.</span><span class="sxs-lookup"><span data-stu-id="98084-104">Because the representation of the data is native to the source, the data requires no translation and almost no parsing.</span></span> <span data-ttu-id="98084-105">Isso significa que a fonte de arquivo bruto pode ler dados mais rapidamente do que outras fontes, como o arquivo simples e as fontes OLE DB.</span><span class="sxs-lookup"><span data-stu-id="98084-105">This means that the Raw File source can read data more quickly than other sources such as the Flat File and the OLE DB sources.</span></span>  
  
 <span data-ttu-id="98084-106">A fonte de arquivo bruto é usada para recuperar dados brutos que foram escritos previamente pelo destino de arquivo bruto.</span><span class="sxs-lookup"><span data-stu-id="98084-106">The Raw File source is used to retrieve raw data that was previously written by the Raw File destination.</span></span> <span data-ttu-id="98084-107">Você também pode apontar a origem Arquivo Bruto para um arquivo bruto vazio que contenha somente as colunas (arquivo somente de metadados).</span><span class="sxs-lookup"><span data-stu-id="98084-107">You can also point the Raw File source to an empty raw file that contains only the columns (metadata-only file).</span></span> <span data-ttu-id="98084-108">Use o destino Arquivo Bruto para gerar o arquivo de somente metadados sem precisar executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="98084-108">You use the Raw File destination to generate the metadata-only file without having to run the package.</span></span> <span data-ttu-id="98084-109">Para obter mais informações, consulte [Raw File Destination](raw-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="98084-109">For more information, see [Raw File Destination](raw-file-destination.md).</span></span>  
  
 <span data-ttu-id="98084-110">O formato de arquivo bruto contém informações de classificação.</span><span class="sxs-lookup"><span data-stu-id="98084-110">The raw file format contains sort information.</span></span> <span data-ttu-id="98084-111">O destino Arquivo Bruto salva todas as informações de classificação incluindo os sinalizadores de comparação para as colunas de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="98084-111">The Raw File Destination saves all the sort information including the comparison flags for string columns.</span></span> <span data-ttu-id="98084-112">A fonte Arquivo Bruto lê e segue as informações de classificação.</span><span class="sxs-lookup"><span data-stu-id="98084-112">The Raw File source reads and honors the sort information.</span></span> <span data-ttu-id="98084-113">Você tem a opção de configurar fonte Arquivo Bruto para ignorar os sinalizadores de classificação no arquivo, usando o Editor Avançado.</span><span class="sxs-lookup"><span data-stu-id="98084-113">You do have the option of configuring the Raw File Source to ignore the sort flags in the file, using the Advanced Editor.</span></span> <span data-ttu-id="98084-114">Para obter mais informações sobre os sinalizadores de comparação, consulte [Comparando dados de cadeia de caracteres](comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="98084-114">For more information about comparison flags, see [Comparing String Data](comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="98084-115">Você configura o arquivo bruto especificando o nome do arquivo que a fonte de arquivo bruto lê.</span><span class="sxs-lookup"><span data-stu-id="98084-115">You configure the Raw File by specifying the name of the name of the file that the Raw File source reads.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98084-116">Essa fonte não utiliza um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="98084-116">This source does not use a connection manager.</span></span>  
  
 <span data-ttu-id="98084-117">Essa fonte tem uma saída.</span><span class="sxs-lookup"><span data-stu-id="98084-117">This source has one output.</span></span> <span data-ttu-id="98084-118">Não dá suporte a uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="98084-118">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-raw-file-source"></a><span data-ttu-id="98084-119">Configuração da Fonte Arquivo Bruto</span><span class="sxs-lookup"><span data-stu-id="98084-119">Configuration of the Raw File Source</span></span>  
 <span data-ttu-id="98084-120">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="98084-120">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="98084-121">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="98084-121">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="98084-122">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="98084-122">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="98084-123">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="98084-123">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="98084-124">Propriedades personalizadas de arquivo bruto</span><span class="sxs-lookup"><span data-stu-id="98084-124">Raw File Custom Properties</span></span>](raw-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="98084-125">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="98084-125">Related Tasks</span></span>  
 <span data-ttu-id="98084-126">Para obter informações sobre como definir as propriedades do componente, consulte [Definir as propriedades de um componente de fluxo de dados](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="98084-126">For information about how to set the properties of the component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="98084-127">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="98084-127">Related Content</span></span>  
  
-   <span data-ttu-id="98084-128">Entrada de blog, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), em sqlservercentral.com</span><span class="sxs-lookup"><span data-stu-id="98084-128">Blog entry, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), on sqlservercentral.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98084-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="98084-129">See Also</span></span>  
 <span data-ttu-id="98084-130">[Destino do arquivo bruto](raw-file-destination.md) </span><span class="sxs-lookup"><span data-stu-id="98084-130">[Raw File Destination](raw-file-destination.md) </span></span>  
 [<span data-ttu-id="98084-131">Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="98084-131">Data Flow</span></span>](data-flow.md)  
  
  
