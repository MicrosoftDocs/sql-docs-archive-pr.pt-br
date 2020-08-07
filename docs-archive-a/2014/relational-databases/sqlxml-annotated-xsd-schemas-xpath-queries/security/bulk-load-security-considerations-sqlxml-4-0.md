---
title: Considerações de segurança de carregamento em massa (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, XML Bulk Load
- bulk load [SQLXML], security
- security [SQLXML], XML Bulk Load
- XML Bulk Load [SQLXML], security
ms.assetid: 192fc6d4-ecbc-4a4d-a5cb-55e1f64af318
author: rothja
ms.author: jroth
ms.openlocfilehash: 21c1cbe7f94ef42327aa7b81f75fa521d9f7c0e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584116"
---
# <a name="bulk-load-security-considerations-sqlxml-40"></a><span data-ttu-id="411a9-102">Considerações sobre segurança de carregamento em massa (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="411a9-102">Bulk Load Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="411a9-103">Estas são as diretrizes de segurança para o uso do carregamento em massa XML:</span><span class="sxs-lookup"><span data-stu-id="411a9-103">The following are security guidelines for using XML Bulk Load:</span></span>  
  
-   <span data-ttu-id="411a9-104">Ao especificar que a operação de carregamento em massa deve ser realizada como uma transação, você usa a propriedade `TempFilePath` para especificar uma pasta na qual criar os arquivos temporários.</span><span class="sxs-lookup"><span data-stu-id="411a9-104">When you specify that the Bulk Load operation is to be performed as a transaction, you use the `TempFilePath` property to specify a folder in which to create the temporary files.</span></span>  
  
     <span data-ttu-id="411a9-105">O processo de carregamento em massa cria esses arquivos temporários com as seguintes permissões:</span><span class="sxs-lookup"><span data-stu-id="411a9-105">The Bulk Load process creates these temporary files with the following permissions:</span></span>  
  
    -   <span data-ttu-id="411a9-106">O acesso de leitura/gravação/exclusão é concedido ao processo de carregamento em massa.</span><span class="sxs-lookup"><span data-stu-id="411a9-106">Read/Write/Delete access is granted to the Bulk Load process.</span></span>  
  
    -   <span data-ttu-id="411a9-107">A permissão de leitura é concedida a todos os usuários, porque a conta na qual o Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] acessará esses arquivos é desconhecida.</span><span class="sxs-lookup"><span data-stu-id="411a9-107">Read permission is granted to all users, because the account under which Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] will access these files is unknown.</span></span> <span data-ttu-id="411a9-108">É possível restringir o acesso a esses arquivos temporários, definindo as permissões apropriadas na pasta em que estão contidos.</span><span class="sxs-lookup"><span data-stu-id="411a9-108">You can restrict the access to these temporary files by setting the appropriate permissions on the folder that contains them.</span></span>  
  
-   <span data-ttu-id="411a9-109">O carregamento em massa XML propriamente dito não tem nenhuma configuração de permissão.</span><span class="sxs-lookup"><span data-stu-id="411a9-109">XML Bulk Load does not itself have any permissions settings.</span></span> <span data-ttu-id="411a9-110">Supõe-se que o banco de dados esteja configurado corretamente e que o contexto do usuário (ou seja, o logon em que o carregamento em massa está definido) tenha o conjunto de permissões apropriado.</span><span class="sxs-lookup"><span data-stu-id="411a9-110">It is assumed that the database is set up correctly and that the user context (that is, the login that Bulk Load is set use) has appropriate permissions set.</span></span>  
  
-   <span data-ttu-id="411a9-111">Em modo não transacional, caso ocorra um erro durante o processo de carregamento em massa, os dados podem permanecer em um estado de carregamento parcial.</span><span class="sxs-lookup"><span data-stu-id="411a9-111">In non-transactional mode, if an error occurs during the Bulk Load process, data may be left in a partially loaded state.</span></span> <span data-ttu-id="411a9-112">Quando isso acontecer, o carregamento em massa apenas será interrompido no ponto em que parou.</span><span class="sxs-lookup"><span data-stu-id="411a9-112">Bulk Load will simply stop at the point where it is when this happens.</span></span> <span data-ttu-id="411a9-113">O modo transacional pode ser usado para aliviar esse problema.</span><span class="sxs-lookup"><span data-stu-id="411a9-113">Transactional mode can be used to alleviate this issue.</span></span>  
  
-   <span data-ttu-id="411a9-114">Quando ocorrem erros no carregamento em massa, eles podem incluir informações sobre o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="411a9-114">When Bulk Load errors occur, they may include information about the database.</span></span> <span data-ttu-id="411a9-115">Por exemplo, eles podem incluir o nome de uma tabela ou coluna, ou informações do tipo de coluna.</span><span class="sxs-lookup"><span data-stu-id="411a9-115">For example, they may include the name of a table or column, or column type information.</span></span> <span data-ttu-id="411a9-116">Ao usar o carregamento em massa, você deve tomar o cuidado de identificar erros no processo e retornar uma mensagem de erro genérica, e não expor diretamente os erros aos usuários.</span><span class="sxs-lookup"><span data-stu-id="411a9-116">When you use Bulk Load, you should take care to catch errors from the Bulk Load process and return a generic error message, rather than exposing errors directly to users.</span></span>  
  
-   <span data-ttu-id="411a9-117">O carregamento em massa não define nenhum limite quanto à quantidade de dados com a qual funciona.</span><span class="sxs-lookup"><span data-stu-id="411a9-117">Bulk Load sets no limit on the amount of data it works over.</span></span> <span data-ttu-id="411a9-118">O carregamento em massa não faz nenhuma verificação quanto ao tamanho dos dados a serem carregados.</span><span class="sxs-lookup"><span data-stu-id="411a9-118">Bulk Load does not do any checking on the size of the data to be loaded.</span></span> <span data-ttu-id="411a9-119">É de responsabilidade do usuário executar o carregamento em massa para garantir que haja memória suficiente para processar o arquivo especificado e que haja espaço o bastante no banco de dados para armazenar os dados carregados.</span><span class="sxs-lookup"><span data-stu-id="411a9-119">It is the responsibility of the user executing Bulk Load to ensure that there is enough memory to process the specified file, and that there is enough room in the database to store the data being loaded.</span></span>  
  
-   <span data-ttu-id="411a9-120">O carregamento em massa não faz nenhuma tentativa de usar os dados fornecidos como código.</span><span class="sxs-lookup"><span data-stu-id="411a9-120">Bulk Load does not make an attempt to use the data it is given as code.</span></span> <span data-ttu-id="411a9-121">A entrada de dados jamais é executada de qualquer jeito.</span><span class="sxs-lookup"><span data-stu-id="411a9-121">The data input is never executed in any fashion.</span></span> <span data-ttu-id="411a9-122">Qualquer código ou comando nos dados de entrada é tratado como dados normais e não serão executados.</span><span class="sxs-lookup"><span data-stu-id="411a9-122">Any code or commands in the input data are treated as normal data and will not be executed.</span></span>  
  
-   <span data-ttu-id="411a9-123">O carregamento em massa pode fazer alterações na formatação dos dados fornecidos com base nas diferenças entre o XML e os modelos de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="411a9-123">Bulk Load may make formatting changes to the given data based on differences between the XML and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data models.</span></span> <span data-ttu-id="411a9-124">Por exemplo, o formato para especificar hora é diferente.</span><span class="sxs-lookup"><span data-stu-id="411a9-124">For example, the format for specifying a time is different.</span></span> <span data-ttu-id="411a9-125">O carregamento em massa tentará resolver essas diferenças.</span><span class="sxs-lookup"><span data-stu-id="411a9-125">Bulk Load will attempt to resolve these differences.</span></span> <span data-ttu-id="411a9-126">Como resultado, algumas informações de precisão podem ser perdidas.</span><span class="sxs-lookup"><span data-stu-id="411a9-126">As a result, some precision information may be lost.</span></span>  
  
-   <span data-ttu-id="411a9-127">O carregamento em massa não define nenhum limite quanto ao tempo necessário ao processamento dos dados.</span><span class="sxs-lookup"><span data-stu-id="411a9-127">Bulk Load sets no limit on the amount of time it takes to process the data.</span></span> <span data-ttu-id="411a9-128">O processamento continuará até ser concluído ou ocorrer um erro.</span><span class="sxs-lookup"><span data-stu-id="411a9-128">Processing will continue until processing is complete or an error occurs.</span></span>  
  
-   <span data-ttu-id="411a9-129">O carregamento em massa pode criar e excluir tabelas temporárias dentro do banco de dados, e precisa de permissões para isso.</span><span class="sxs-lookup"><span data-stu-id="411a9-129">Bulk Load can create and delete temporary tables within the database, and needs permissions to do so.</span></span> <span data-ttu-id="411a9-130">As permissões nessas tabelas serão dadas ao mesmo usuário que está se conectando ao banco de dados para o processo de carregamento em massa.</span><span class="sxs-lookup"><span data-stu-id="411a9-130">Permissions to these tables will be given to the same user who is connecting to the database for the Bulk Load process.</span></span>  
  
-   <span data-ttu-id="411a9-131">O carregamento em massa pode criar e excluir arquivos temporários usados durante o processamento em modo transacional, e precisa de permissões para isso.</span><span class="sxs-lookup"><span data-stu-id="411a9-131">Bulk Load can create and delete temporary files used during transactional mode processing, and needs permissions to do so.</span></span> <span data-ttu-id="411a9-132">Esses arquivos são criados com as mesmas permissões do usuário atual do thread no qual o carregamento em massa está em execução.</span><span class="sxs-lookup"><span data-stu-id="411a9-132">These files are created with the same permissions as the current user of the thread within which Bulk Load is running.</span></span>  
  
-   <span data-ttu-id="411a9-133">Caso o usuário defina um arquivo de log de erros do SQLXML no qual gravar os erros, sempre que o carregamento em massa é executado, o arquivo é substituído com dados do processo de carregamento em massa mais recente.</span><span class="sxs-lookup"><span data-stu-id="411a9-133">If the user sets an error Log file for SQLXML to write errors into, then each time Bulk Load is executed the file will be overwritten with data from the last Bulk Load process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="411a9-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="411a9-134">See Also</span></span>  
 [<span data-ttu-id="411a9-135">Como executar o carregamento em massa de dados XML &#40;SQLXML 4.0&#41;</span><span class="sxs-lookup"><span data-stu-id="411a9-135">Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;</span></span>](../bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md)  
  
  