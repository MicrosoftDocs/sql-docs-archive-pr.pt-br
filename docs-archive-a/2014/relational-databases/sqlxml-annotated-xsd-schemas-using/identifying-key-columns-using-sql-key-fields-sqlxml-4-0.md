---
title: 'Identificando colunas de chave usando SQL: Key-Fields (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- nesting XML results
- proper nesting in results [SQLXML]
- sql:key-fields
- XSD schemas [SQLXML], key columns
- identifying key columns [SQLXML]
- annotated XSD schemas, key columns
- key columns [SQLXML]
- relationships [SQLXML], key columns
- hierarchical relationships [SQLXML]
- key-fields annotation
ms.assetid: 1a5ad868-8602-45c4-913d-6fbb837eebb0
author: rothja
ms.author: jroth
ms.openlocfilehash: 0ab12b34874a54bad2e08a96d08ebd0cc994f946
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685478"
---
# <a name="identifying-key-columns-using-sqlkey-fields-sqlxml-40"></a>Identificando colunas de chave usando campos sql:key (SQLXML 4.0)
  Quando uma consulta XPath é especificada em um esquema XSD, as informações de chave são necessárias, na maioria das vezes, para obter o aninhamento adequado no resultado. Especificar a anotação `sql:key-fields` é uma forma de assegurar que a hierarquia apropriada seja gerada.  
  
> [!NOTE]  
>  Para assegurar o aninhamento adequado, é recomendável especificar `sql:key-fields` para elementos que são mapeados para tabelas. O XML gerado é sensível à ordenação do conjunto de resultados subjacente. Se `sql:key-fields` não for especificada, o XML gerado poderá não ser formado corretamente.  
  
 O valor de `sql:key-fields` identifica as colunas que identificam as linhas de forma exclusiva na relação. Se mais de uma coluna for necessária para identificar uma linha de forma exclusiva, os valores de coluna serão delimitados por espaços.  
  
 Você deve usar a `sql:key-fields` anotação quando um elemento contiver um **\<sql:relationship>** que esteja definido entre o elemento e um elemento filho, mas não forneça a chave primária da tabela especificada no elemento pai.  
  
## <a name="examples"></a>Exemplos  
 Para criar exemplos de funcionamento usando os exemplos a seguir, é necessário atender a determinados requisitos. Para obter mais informações, consulte [Requirements for running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).  
  
### <a name="a-producing-the-appropriate-nesting-when-sqlrelationship-does-not-provide-sufficient-information"></a>a. Produzindo o aninhamento apropriado quando o não \<sql:relationship> fornece informações suficientes  
 Esse exemplo mostra onde `sql:key-fields` deve ser especificada.  
  
 Considere o esquema a seguir. O esquema especifica uma hierarquia entre os **\<Order>** **\<Customer>** elementos e nos quais o **\<Order>** elemento é o pai e o **\<Customer>** elemento é um filho.  
  
 A **\<sql:relationship>** marca é usada para especificar a relação pai-filho. Ela identifica CustomerID na tabela Sales.SalesOrderHeader como a chave pai que faz referência à chave filho CustomerID na tabela Sales.Customer. As informações fornecidas no **\<sql:relationship>** não são suficientes para identificar exclusivamente as linhas na tabela pai (Sales. SalesOrderHeader). Portanto, sem a anotação `sql:key-fields`, a hierarquia gerada é imprecisa.  
  
 Com `sql:key-fields` o especificado em **\<Order>** , a anotação identifica exclusivamente as linhas na tabela pai (tabelas Sales. SalesOrderHeader) e seus elementos filho aparecem abaixo de seu pai.  
  
 Este é o esquema:  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrdCust"  
        parent="Sales.SalesOrderHeader"  
        parent-key="CustomerID"  
        child="Sales.Customer"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"   
               sql:key-fields="SalesOrderID">  
   <xsd:complexType>  
     <xsd:sequence>  
     <xsd:element name="Customer" sql:relation="Sales.Customer"   
                       sql:relationship="OrdCust"  >  
       <xsd:complexType>  
         <xsd:attribute name="CustID" sql:field="CustomerID" />  
         <xsd:attribute name="SoldBy" sql:field="SalesPersonID" />  
       </xsd:complexType>  
     </xsd:element>  
     </xsd:sequence>  
     <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
     <xsd:attribute name= "CustomerID" type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a>Para criar um exemplo de funcionamento deste esquema  
  
1.  Copie o código de esquema acima e cole-o em um arquivo de texto. Salve o arquivo como KeyFields1.xml.  
  
2.  Copie o modelo a seguir e cole-o em um arquivo de texto. Salve o arquivo como KeyFields1T.xml no mesmo diretório em que você salvou KeyFields1.xml. A consulta XPath no modelo retorna todos os **\<Order>** elementos com um CustomerID de menos de 3.  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="KeyFields1.xml">  
            /Order[@CustomerID < 3]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     O caminho de diretório especificado para o esquema de mapeamento (KeyFields1.xml) é relativo ao diretório onde o modelo está salvo. Também é possível especificar um caminho absoluto, por exemplo:  
  
    ```  
    mapping-schema="C:\MyDir\KeyFields1.xml"  
    ```  
  
3.  Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.  
  
     Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).  
  
 Este é o conjunto de resultados parcial:  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
    <Order SalesOrderID="43860" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    <Order SalesOrderID="44501" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    <Order SalesOrderID="45283" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    .....  
</ROOT>  
```  
  
### <a name="b-specifying-sqlkey-fields-to-produce-proper-nesting-in-the-result"></a>B. Especificar sql:key-fields para produzir o aninhamento adequado no resultado  
 No esquema a seguir, não há nenhuma hierarquia especificada usando **\<sql:relationship>** . O esquema ainda requer que a anotação `sql:key-fields` seja especificada para identificar os funcionários de forma exclusiva na tabela HumanResources.Employee.  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="HumanResources.Employee" sql:key-fields="EmployeeID" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Title">  
          <xsd:complexType>  
            <xsd:simpleContent>  
              <xsd:extension base="xsd:string">  
                 <xsd:attribute name="EmployeeID" type="xsd:integer" />  
              </xsd:extension>  
            </xsd:simpleContent>  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
   </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a>Para criar um exemplo de funcionamento deste esquema  
  
1.  Copie o código de esquema acima e cole-o em um arquivo de texto. Salve o arquivo como KeyFields2.xml.  
  
2.  Copie o modelo a seguir e cole-o em um arquivo de texto. Salve o arquivo como KeyFields2T.xml no mesmo diretório em que você salvou KeyFields2.xml. A consulta XPath no modelo retorna todos os **\<HumanResources.Employee>** elementos:  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="KeyFields2.xml">  
        /HumanResources.Employee  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     O caminho de diretório especificado para o esquema de mapeamento (KeyFields2.xml) é relativo ao diretório onde o modelo está salvo. Também é possível especificar um caminho absoluto, por exemplo:  
  
    ```  
    mapping-schema="C:\MyDir\KeyFields2.xml"  
    ```  
  
3.  Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.  
  
     Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).  
  
 Este é o resultado:  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <HumanResources.Employee>  
    <Title EmployeeID="1">Production Technician - WC60</Title>   
  </HumanResources.Employee>  
  <HumanResources.Employee>  
    <Title EmployeeID="2">Marketing Assistant</Title>   
  </HumanResources.Employee>  
  <HumanResources.Employee>  
    <Title EmployeeID="3">Engineering Manager</Title>   
  </HumanResources.Employee>  
  ...  
</ROOT>  
```  
  
  
