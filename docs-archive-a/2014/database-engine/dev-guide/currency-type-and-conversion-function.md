---
title: Tipo de moeda e função de conversão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: df516567-8689-45c2-b418-16473f8d43e4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 032afa201b6e669baf8934c608792ea6bd7f0e8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685918"
---
# <a name="currency-type-and-conversion-function"></a><span data-ttu-id="310da-102">Função de conversão e tipo de moeda</span><span class="sxs-lookup"><span data-stu-id="310da-102">Currency Type and Conversion Function</span></span>
  <span data-ttu-id="310da-103">Esse exemplo apresenta um tipo de dados de moeda definido pelo usuário usando C#.</span><span class="sxs-lookup"><span data-stu-id="310da-103">This example defines a Currency user-defined data type by using C#.</span></span> <span data-ttu-id="310da-104">Esse tipo de dados definido pelo usuário encapsula um valor e uma cultura que ajudam a determinar o modo correto de renderizar o valor como um valor de moeda nessa cultura.</span><span class="sxs-lookup"><span data-stu-id="310da-104">This user-defined data type encapsulates both an amount and a culture that helps to determine the correct way to render the amount as a currency value in that culture.</span></span> <span data-ttu-id="310da-105">Esse exemplo também fornece uma função de conversão de moeda que retorna uma instância do tipo de dados de moeda definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="310da-105">This example also provides a currency conversion function that returns an instance of the Currency user-defined data type.</span></span> <span data-ttu-id="310da-106">Se o banco de dados AdventureWorks tiver uma taxa de conversão de USD (dólares americanos) para a moeda associada à cultura especificada, a função de conversão retornará um tipo de dados de moeda definido pelo usuário com a taxa convertida e a cultura correspondente à cultura solicitada.</span><span class="sxs-lookup"><span data-stu-id="310da-106">If the AdventureWorks database has a conversion rate from U.S. dollars (USD) to the currency that is associated with the specified culture, the conversion function returns a Currency user-defined data type with the converted rate and a culture that matches the culture requested.</span></span> <span data-ttu-id="310da-107">Caso contrário, um tipo de dados de moeda definido pelo usuário será retornado com o valor original, que deve ser em USD, e com a cultura `en-us`.</span><span class="sxs-lookup"><span data-stu-id="310da-107">Otherwise, a Currency user-defined data type is returned with the original amount, which should be in USD, with the `en-us` culture.</span></span> <span data-ttu-id="310da-108">O exemplo também demonstra como cancelar o registro e registrar métodos e assemblies CLR (Common Language Runtime) usando Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="310da-108">The example also demonstrates how to unregister and register common language runtime (CLR) methods and assemblies by using Transact-SQL.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="310da-109">As taxas de câmbio usadas neste exemplo são fictícias e não devem ser usadas para transações financeiras reais.</span><span class="sxs-lookup"><span data-stu-id="310da-109">The exchange rates used in this sample are fictitious and should not be used for actual financial transactions.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="310da-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="310da-110">Prerequisites</span></span>  
 <span data-ttu-id="310da-111">Para criar e executar este projeto, o software a seguir deve estar instalado:</span><span class="sxs-lookup"><span data-stu-id="310da-111">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="310da-112">ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="310da-112">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="310da-113">É possível obter o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express gratuitamente no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] site [de Documentação e Amostras do](https://www.microsoft.com/sql-server/sql-server-editions-express)Express</span><span class="sxs-lookup"><span data-stu-id="310da-113">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/sql-server/sql-server-editions-express)</span></span>  
  
-   <span data-ttu-id="310da-114">O banco de dados AdventureWorks que está disponível no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] site [do](https://go.microsoft.com/fwlink/?linkid=62796)Developer</span><span class="sxs-lookup"><span data-stu-id="310da-114">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://go.microsoft.com/fwlink/?linkid=62796)</span></span>  
  
-   <span data-ttu-id="310da-115">.NET Framework SDK 2.0 ou posterior ou Microsoft Visual Studio 2005 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="310da-115">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="310da-116">Você pode obter o .NET Framework SDK gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="310da-116">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="310da-117">Além disso, as seguintes condições devem ser atendidas:</span><span class="sxs-lookup"><span data-stu-id="310da-117">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="310da-118">A instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que você está usando deve ter a integração CLR habilitada.</span><span class="sxs-lookup"><span data-stu-id="310da-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="310da-119">Para habilitar a integração CLR, execute as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="310da-119">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="310da-120">Habilitando integração CLR</span><span class="sxs-lookup"><span data-stu-id="310da-120">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="310da-121">Execute os seguintes comandos [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="310da-121">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="310da-122">Para habilitar o CLR, é necessário ter a permissão `ALTER SETTINGS` de nível de servidor, que é mantida implicitamente por membros das funções de servidor fixas `sysadmin` e `serveradmin`.</span><span class="sxs-lookup"><span data-stu-id="310da-122">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="310da-123">O banco de dados AdventureWorks deve estar instalado na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que você está usando.</span><span class="sxs-lookup"><span data-stu-id="310da-123">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="310da-124">Se você não for um administrador da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está usando, será preciso solicitar que um administrador conceda a permissão **CreateAssembly** a você para que seja possível concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="310da-124">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly** permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="310da-125">Compilando o exemplo</span><span class="sxs-lookup"><span data-stu-id="310da-125">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="310da-126">Crie e execute o exemplo seguindo estas instruções:</span><span class="sxs-lookup"><span data-stu-id="310da-126">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="310da-127">Abra um prompt de comando do Visual Studio ou do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="310da-127">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="310da-128">Se necessário, crie um diretório para o seu exemplo.</span><span class="sxs-lookup"><span data-stu-id="310da-128">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="310da-129">Para este exemplo, usaremos C:\MySample.</span><span class="sxs-lookup"><span data-stu-id="310da-129">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="310da-130">Em c:\MySample, crie o arquivo `Currency.cs` e copie o código de exemplo C# (abaixo) nele.</span><span class="sxs-lookup"><span data-stu-id="310da-130">In c:\MySample, create `Currency.cs` and copy the C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="310da-131">Compile o código de exemplo a partir do prompt de linha de comando executando:</span><span class="sxs-lookup"><span data-stu-id="310da-131">Compile the sample code from the command line prompt by executing:</span></span>  
  
    -   `Csc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll  /target:library Currency.cs`  
  
5.  <span data-ttu-id="310da-132">Copie o código de instalação [!INCLUDE[tsql](../../includes/tsql-md.md)] em um arquivo e salve-o como `Install.sql` no diretório de exemplo.</span><span class="sxs-lookup"><span data-stu-id="310da-132">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation code into a file and save it as `Install.sql` in the sample directory.</span></span>  
  
6.  <span data-ttu-id="310da-133">Se o exemplo tiver sido instalado em um diretório diferente de `C:\MySample\`, edite o arquivo `Install.sql` conforme indicado para apontar para esse local.</span><span class="sxs-lookup"><span data-stu-id="310da-133">If the sample is installed in a directory other then `C:\MySample\`, edit the file `Install.sql` as indicated to point to that location.</span></span>  
  
7.  <span data-ttu-id="310da-134">Implante o assembly e o procedimento armazenado executando o seguinte</span><span class="sxs-lookup"><span data-stu-id="310da-134">Deploy the assembly and stored procedure by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql`  
  
8.  <span data-ttu-id="310da-135">Copie o script de comando de teste do [!INCLUDE[tsql](../../includes/tsql-md.md)] em um arquivo e salve-o como `test.sql` no diretório de exemplo.</span><span class="sxs-lookup"><span data-stu-id="310da-135">Copy [!INCLUDE[tsql](../../includes/tsql-md.md)] test command script into a file and save it as `test.sql` in the sample directory.</span></span>  
  
9. <span data-ttu-id="310da-136">Execute o script de teste com o seguinte comando</span><span class="sxs-lookup"><span data-stu-id="310da-136">Execute the test script with the following command</span></span>  
  
    -   `sqlcmd -E -I -i test.sql`  
  
10. <span data-ttu-id="310da-137">Copie o script de limpeza [!INCLUDE[tsql](../../includes/tsql-md.md)] em um arquivo e salve-o como `cleanup.sql` no diretório de exemplo.</span><span class="sxs-lookup"><span data-stu-id="310da-137">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
11. <span data-ttu-id="310da-138">Execute o script com o seguinte comando</span><span class="sxs-lookup"><span data-stu-id="310da-138">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="310da-139">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="310da-139">Sample Code</span></span>  
 <span data-ttu-id="310da-140">As listagens de código deste exemplo são as seguintes.</span><span class="sxs-lookup"><span data-stu-id="310da-140">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="310da-141">C#</span><span class="sxs-lookup"><span data-stu-id="310da-141">C#</span></span>  
  
```  
using System;  
using System.Globalization;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Data;  
using System.Data.Sql;  
using System.IO;  
using System.Data.SqlClient;  
  
    /// <summary>  
    ///Defines a class for handing particular amounts of money in a   
    ///particular culture's monetary system.  This class is exposed as   
    ///a SQL Server UDT.  
///   
///Note that we are implementing IComparable to affect comparison behavior   
///only within the CLR.  This does not affect how SQL Server will compare the  
///     the types.  How SQL Server will compare the type is determined by the Write   
///method on IBinarySerialize.  
    /// </summary>  
[Serializable]  
    [SqlUserDefinedType(Format.UserDefined, IsByteOrdered = true, MaxByteSize = 32)]  
    public struct Currency : INullable, IComparable, IBinarySerialize  
    {  
        const string nullMarker = "\0\0\0\0\0\0\0\0\0\0";  
        const int cultureNameMaxSize = 10;  
  
        private string cultureName;//Who issued the money (en-us, for example)  
  
        private CultureInfo culture;//The object which represents cultureName  
  
        private decimal currencyValue;//The amount of money  
  
        // Public properties for private fields  
        public CultureInfo Culture  
        {  
            get  
            {  
                //A culture name is required.  If not present the entire object is considered null.  
                if (cultureName == null) return null;  
  
                //If we've got a cached copy of the culture return it.  
                if (culture != null) return culture;  
  
                //Otherwise, set the cache and return the culture for the culture name specified.  
                culture = CultureInfo.CreateSpecificCulture(cultureName);  
                return culture;  
            }  
        }  
  
        // Public property for the private field.  
        public decimal CurrencyValue  
        {  
            get  
            {  
                return currencyValue;  
            }  
        }  
  
        // Constructors for when we have the culture or the name of the culture  
  
        public Currency(CultureInfo culture, decimal currencyValue)  
        {  
if (culture == null) throw new ArgumentNullException("culture");  
            this.cultureName = culture.Name;  
            this.culture = culture;  
            this.currencyValue = currencyValue;  
        }  
  
        public Currency(string cultureName, decimal currencyValue)  
        {  
            this.cultureName = cultureName;  
            this.culture = null;  
            this.currencyValue = currencyValue;  
        }  
  
        //Return the string representation for the currency, including the currency symbol.  
        [SqlMethod(IsDeterministic = true,  
            IsPrecise = true, DataAccess = DataAccessKind.None,  
            SystemDataAccess = SystemDataAccessKind.None)]  
        public override string ToString()  
        {  
            if (this.Culture == null) return "null";  
  
            return String.Format(this.Culture, "{0:c}", currencyValue);  
        }  
  
        //The entire value of the currency is considered null if the culture name is null  
        public bool IsNull  
        {  
            get  
            {  
                return cultureName == null;  
            }  
        }  
  
        //The no-argument constructor makes a null currency.  
        public static Currency Null  
        {  
            get  
            {  
                Currency h = new Currency((String)null, 0);  
  
                return h;  
            }  
        }  
  
        //Be sure to set the current UI culture before using this method! Even better, provide the culture  
        //specifically (for the method after this one).  
        [SqlMethod(IsDeterministic = true, IsPrecise = true, DataAccess = DataAccessKind.None, SystemDataAccess = SystemDataAccessKind.None)]  
        public static Currency Parse(SqlString sqlString)  
        {  
            return ParseWithCulture(sqlString, CultureInfo.CurrentUICulture);  
        }  
  
        public static Currency ParseWithCulture(SqlString sqlString, CultureInfo culture)  
        {  
            if (sqlString.IsNull   
|| (string.Compare(sqlString.Value, "null", true, CultureInfo.CurrentUICulture) == 0))  
                return Currency.Null;  
  
            int digitPos = -1;  
            string stringValue = sqlString.Value;  
  
            while (digitPos < stringValue.Length   
                && !Char.IsDigit(stringValue, ++digitPos))  
            {  
            }  
  
            if (digitPos < stringValue.Length)  
                return new Currency(culture, decimal.Parse(  
                    stringValue.Substring(digitPos), culture));  
  
            return Currency.Null;  
        }  
  
        public override int GetHashCode()  
        {  
            if (this.IsNull)  
                return 0;  
  
            return this.ToString().GetHashCode();  
        }  
  
//Note: This only affects the behavior of CLR, not SQL Server.  Comparisions  
//for SQL Server will be determined by the Write method below.  
  
public int CompareTo(object obj)  
        {  
            if (obj == null)  
                return 1; //by definition  
  
            if (obj == null || !(obj is Currency))  
                throw new ArgumentException(  
                    "the argument to compare is not a Currency");  
  
            Currency c = (Currency)obj;  
  
            if (this.IsNull)  
            {  
                if (c.IsNull)  
                    return 0;  
  
                return -1;  
            }  
  
            if (c.IsNull)  
                return 1;  
  
            string thisCultureName = this.Culture.Name;  
            string otherCultureName = c.Culture.Name;  
            if (!thisCultureName.Equals(otherCultureName))  
                return thisCultureName.CompareTo(otherCultureName);  
            return this.CurrencyValue.CompareTo(c.CurrencyValue);  
        }  
        // IBinarySerialize methods  
        // The binary layout is as follow:  
        //    Bytes 0 - 19:Culture name, padded to the right with null characters, UTF-16 encoded  
        //    Bytes 20+:Decimal value of money  
        // If the culture name is empty, the currency is null.  
  
        public void Write(System.IO.BinaryWriter w)  
        {  
if (w == null) throw new ArgumentNullException("w");  
            if (this.IsNull)  
            {  
                w.Write(nullMarker);  
                w.Write((decimal)0);  
                return;  
            }  
  
            if (cultureName.Length > cultureNameMaxSize)  
            {  
                throw new ApplicationException(string.Format(  
                    CultureInfo.InvariantCulture,   
                    "{0} is an invalid culture name for currency as it is too long.",   
                    cultureNameMaxSize));  
            }  
  
            String paddedName = cultureName.PadRight(cultureNameMaxSize, '\0');  
            for (int i = 0; i < cultureNameMaxSize; i++)  
            {  
                w.Write(paddedName[i]);  
            }  
  
            // Normalize decimal value to two places  
            currencyValue = Decimal.Floor(currencyValue * 100) / 100;  
            w.Write(currencyValue);  
        }  
        public void Read(System.IO.BinaryReader r)  
        {  
            char[] name = r.ReadChars(cultureNameMaxSize);  
            int stringEnd = Array.IndexOf(name, '\0');  
  
            if (stringEnd == 0)  
            {  
                cultureName = null;  
                return;  
            }  
  
            cultureName = new String(name, 0, stringEnd);  
            currencyValue = r.ReadDecimal();  
        }  
    }  
  
    /// <summary>  
    /// This class is used to compute the value of US money a given region.  
    /// </summary>  
    public sealed class CurrencyConverter  
    {  
        // Classes with only static members should not be instantiable  
        private CurrencyConverter()  
        {  
        }  
  
        private static readonly CultureInfo USCulture = CultureInfo.CreateSpecificCulture("en-us");  
  
        /// <summary>  
        ///Computes the value of a certain amount of money in the USA in a different region.  
        /// </summary>  
        /// <param name="fromAmount">The quantity of money</param>  
        /// <param name="toCultureName">A culture which is a member of the region of interest</param>  
        /// <returns></returns>  
        [Microsoft.SqlServer.Server.SqlFunction(IsDeterministic = true, DataAccess = Microsoft.SqlServer.Server.DataAccessKind.Read)]  
        public static Currency ConvertCurrency(SqlMoney fromAmount, SqlString toCultureName, SqlDateTime when)  
        {  
            CultureInfo toCulture = CultureInfo.CreateSpecificCulture(toCultureName.Value);  
  
            if (toCulture.Equals(USCulture))  
            {  
                Currency c = new Currency(USCulture, (decimal)fromAmount);  
                return c;  
            }  
  
            String toCurrencyCode = new RegionInfo(toCulture.LCID).ISOCurrencySymbol;  
  
            // Find the rate closest to the specified date  
  
            using (SqlConnection conn = new SqlConnection("context connection=true"))  
            {  
  
                SqlCommand command = conn.CreateCommand();  
                command.CommandType = CommandType.StoredProcedure;  
                command.CommandText = "usp_LookupConversionRate";  
  
                SqlParameter onDateParameter  
                    = new SqlParameter("@OnDate", SqlDbType.DateTime);  
                onDateParameter.Value = when;  
                command.Parameters.Add(onDateParameter);  
  
                SqlParameter toCurrencyCodeParameter  
                    = new SqlParameter("@ToCurrencyCode", SqlDbType.NChar, 3);  
                toCurrencyCodeParameter.Value = toCurrencyCode;  
                command.Parameters.Add(toCurrencyCodeParameter);  
  
                SqlParameter resultParameter  
                    = new SqlParameter("@Result", SqlDbType.Decimal);  
                resultParameter.Precision = 10;  
                resultParameter.Scale = 4;  
                resultParameter.Direction = ParameterDirection.Output;  
                command.Parameters.Add(resultParameter);  
  
                conn.Open();  
                command.ExecuteNonQuery();  
  
                decimal conversionFactor;  
  
                if (resultParameter.Value is decimal)  
                {  
                    conversionFactor = (decimal)(resultParameter.Value);  
                }  
                else  
                {  
                    conversionFactor = 1.0M;  
                    toCulture = USCulture;  
                }  
  
                return new Currency(toCulture, ((decimal)fromAmount * conversionFactor));  
            }  
        }  
    }  
```  
  
 <span data-ttu-id="310da-142">Este é o script de instalação do [!INCLUDE[tsql](../../includes/tsql-md.md)] (`Install.sql`) que implanta o assembly e cria o procedimento armazenado no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="310da-142">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assembly and creates the stored procedure in the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = N'usp_LookupConversionRate')  
DROP PROCEDURE [dbo].[usp_LookupConversionRate]  
GO  
  
IF EXISTS (SELECT * FROM sys.types WHERE [name] = N'Currency')   
DROP TYPE Currency;  
GO  
  
IF EXISTS (SELECT [name] FROM sys.assemblies WHERE [name] = N'Currency')  
DROP ASSEMBLY Currency;  
GO  
  
IF EXISTS (SELECT * FROM sys.objects WHERE ([name] = N'ConvertCurrency') AND ([type] = 'FS'))  
DROP FUNCTION ConvertCurrency;  
GO  
  
-- You may need to modify the value of the this variable if you have installed the sample someplace other than the default location.  
DECLARE @SamplesPath nvarchar(1024)  
set @SamplesPath = 'C:\MySample\'  
CREATE ASSEMBLY Currency   
FROM @SamplesPath + 'Currency.dll'  
with permission_set = safe;  
  
USE AdventureWorks  
GO  
  
CREATE TYPE Currency EXTERNAL NAME [Currency].[Currency];  
GO  
  
CREATE FUNCTION ConvertCurrency  
(  
@fromAmount AS money,  
@toCultureName AS nvarchar(10),  
@when as DateTime  
)  
RETURNS Currency  
AS EXTERNAL NAME [Currency].[CurrencyConverter].ConvertCurrency;  
GO  
  
CREATE PROCEDURE usp_LookupConversionRate  
(  
@OnDate datetime,  
@ToCurrencyCode nchar(3),  
@Result decimal(10,4) OUTPUT  
)  
AS  
BEGIN  
--It is not permitted to perform certain side-effects in functions, and  
--SET NOCOUNT is one of them.  Since this sproc is called from   
--the ConvertCurrency CLR UDF, we must not do that side-effect or  
--there will be an error at runtime.  
--SET NOCOUNT ON  
  
SELECT @Result = (SELECT TOP 1 AverageRate FROM Sales.CurrencyRate   
WHERE CurrencyRateDate <= @OnDate AND FromCurrencyCode = N'USD'   
AND ToCurrencyCode = @ToCurrencyCode   
ORDER BY CurrencyRateDate DESC);  
  
IF (@Result IS NULL)  
SELECT @Result = (SELECT TOP 1 AverageRate FROM Sales.CurrencyRate   
WHERE CurrencyRateDate > @OnDate AND FromCurrencyCode = N'USD'   
AND ToCurrencyCode = @ToCurrencyCode  
ORDER BY CurrencyRateDate ASC);  
END;  
  
```  
  
 <span data-ttu-id="310da-143">Esse é o `test.sql`, que testa o exemplo por meio da execução das funções.</span><span class="sxs-lookup"><span data-stu-id="310da-143">This is `test.sql`, which tests the sample by executing the functions.</span></span>  
  
```  
use AdventureWorks  
GO  
  
DECLARE @TwoBitsEuro Currency;  
SELECT @TwoBitsEuro = dbo.ConvertCurrency(CAST('.25' as money), 'FR-FR', GetDate());  
PRINT '$0.25 in USD is equivalent to ' + @TwoBitsEuro.ToString();  
```  
  
 <span data-ttu-id="310da-144">O [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir remove o assembly, o tipo e as funções do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="310da-144">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assembly, type and functions from the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = N'usp_LookupConversionRate')  
DROP PROCEDURE [dbo].[usp_LookupConversionRate]  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="310da-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="310da-145">See Also</span></span>  
 [<span data-ttu-id="310da-146">Cenários de uso e exemplos para a integração do CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="310da-146">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
