---
title: Criar exibições | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], creating
ms.assetid: 0b7bd2a1-544c-42ba-8e7b-4822f34d7b64
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8280f6d65d7252cad423abef849207111492c044
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569270"
---
# <a name="create-views"></a>Criar exibições
  Você pode criar exibições no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)]. Uma exibição pode ser usada para as finalidades a seguir:  
  
-   Para focalizar, simplificar e personalizar a percepção que cada usuário tem do banco de dados.  
  
-   Como um mecanismo de segurança permitindo que os usuários acessem dados por meio da exibição, sem conceder permissões aos usuários para acessar diretamente as tabelas base subjacentes.  
  
-   Para fornecer uma interface compatível com versões anteriores para emular uma tabela cujo esquema foi alterado.  
  
 **Neste tópico**  
  
-   **Antes de começar:**  
  
     [Limitações e restrições](#Restrictions)  
  
     [Segurança](#Security)  
  
-   **Para criar uma exibição usando:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> Antes de começar  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> Limitações e restrições  
 A exibição só pode ser criada no banco de dados atual.  
  
 Uma exibição pode ter, no máximo, 1.024 partições.  
  
###  <a name="security"></a><a name="Security"></a> Segurança  
  
####  <a name="permissions"></a><a name="Permissions"></a> Permissões  
 Requer a permissão CREATE VIEW no banco de dados e a permissão ALTER no esquema no qual a exibição está sendo criada.  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> Usando o SQL Server Management Studio  
  
#### <a name="to-create-a-view-by-using-the-query-and-view-designer"></a>Para criar uma exibição usando o Designer de Consulta e Exibição  
  
1.  No **Pesquisador de Objetos**, expanda o banco de dados em que você deseja criar a nova exibição.  
  
2.  Clique com o botão direito do mouse na pasta **Exibições** objeto e clique em **Nova Exibição...** .  
  
3.  Na caixa de diálogo **Adicionar Tabela** , selecione o elemento ou elementos que você deseja incluir em sua nova exibição de uma destas guias: Tabelas, Exibições, Funções e Sinônimos.  
  
4.  Clique em **Adicionar**e em **Fechar**.  
  
5.  No **Painel de Diagrama**, selecione as colunas ou outros elementos para incluir na nova exibição.  
  
6.  No **Painel de Critérios**, selecione os critérios adicionais de classificação ou filtragem para as colunas.  
  
7.  No menu **Arquivo** , clique em **Salvar**_view name_.  
  
8.  Na caixa de diálogo **Escolher Nome** , digite um nome para a nova exibição e clique em **OK**.  
  
     Para obter mais informações sobre o designer de consultas e exibição, veja [Ferramentas de Designer de Consultas e Exibição&#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> Usando o Transact-SQL  
  
#### <a name="to-create-a-view"></a>Para criar uma exibição  
  
1.  No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
2.  Na barra Padrão, clique em **Nova Consulta**.  
  
3.  Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    CREATE VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID ;   
    GO  
    -- Query the view  
    SELECT FirstName, LastName, HireDate  
    FROM HumanResources.EmployeeHireDate  
    ORDER BY LastName;  
  
    ```  
  
 Para obter mais informações, veja [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).  
  
  
