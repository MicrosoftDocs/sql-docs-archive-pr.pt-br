---
title: Fazendo backup e restaurando bancos de dados e logs de transações | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- restoring databases [SMO]
- transaction log backups [SMO]
- backing up transaction logs [SMO]
- database backups [SMO]
- restoring transaction logs [SMO]
- transaction log restores [SMO]
- backing up databases [SMO]
- database restores [SMO]
ms.assetid: 1d7bd180-fd6c-4b38-a87b-351496040542
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e88534e04435001dc4c93b58ff9ed36c4bb14fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684646"
---
# <a name="backing-up-and-restoring-databases-and-transaction-logs"></a><span data-ttu-id="ea498-102">Fazendo backup e restaurando bancos de dados e logs de transações</span><span class="sxs-lookup"><span data-stu-id="ea498-102">Backing Up and Restoring Databases and Transaction Logs</span></span>
  <span data-ttu-id="ea498-103">No SMO, as classes <xref:Microsoft.SqlServer.Management.Smo.Backup> e <xref:Microsoft.SqlServer.Management.Smo.Restore> são classes de utilitário que fornecem as ferramentas para a execução de tarefas específicas de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="ea498-103">In SMO, the <xref:Microsoft.SqlServer.Management.Smo.Backup> class and the <xref:Microsoft.SqlServer.Management.Smo.Restore> class are utility classes that provide the tools to accomplish the specific tasks of backing up and restoring.</span></span> <span data-ttu-id="ea498-104">Um <xref:Microsoft.SqlServer.Management.Smo.Backup> objeto representa uma tarefa de backup específica que é necessária em vez de um [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] objeto na instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="ea498-104">A <xref:Microsoft.SqlServer.Management.Smo.Backup> object represents a specific backup task that is required instead of a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] object on the server instance.</span></span>  
  
 <span data-ttu-id="ea498-105">Em caso de perda ou dano de dados, o backup deve ser restaurado, parcial ou totalmente.</span><span class="sxs-lookup"><span data-stu-id="ea498-105">If data loss or corruption occurs, the backup must be restored, either fully or partially.</span></span> <span data-ttu-id="ea498-106">A restauração parcial usa a coleção <xref:Microsoft.SqlServer.Management.Smo.FileGroupCollection> para segmentar os dados a serem restaurados.</span><span class="sxs-lookup"><span data-stu-id="ea498-106">Partial restoration uses the <xref:Microsoft.SqlServer.Management.Smo.FileGroupCollection> collection to segment the data to be restored.</span></span> <span data-ttu-id="ea498-107">Se o backup for de um log de transações, os dados poderão ser restaurados até um momento determinado através da propriedade <xref:Microsoft.SqlServer.Management.Smo.Restore.ToPointInTime%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Restore>.</span><span class="sxs-lookup"><span data-stu-id="ea498-107">If the backup is of a transaction log, the data can be restored up to a particular point in time by using the <xref:Microsoft.SqlServer.Management.Smo.Restore.ToPointInTime%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Restore> object.</span></span> <span data-ttu-id="ea498-108">Os dados também podem ser validados usando o método <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlVerify%2A>.</span><span class="sxs-lookup"><span data-stu-id="ea498-108">The data can also be validated by using the <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlVerify%2A> method.</span></span> <span data-ttu-id="ea498-109">O procedimento de backup recomendado é verificar a integridade do backup executando uma operação de restauração e verificando os dados no banco de dados regularmente.</span><span class="sxs-lookup"><span data-stu-id="ea498-109">The recommended backup procedure is to check the integrity of the backup by doing a restore operation and checking the data in the database on a regular basis.</span></span>  
  
 <span data-ttu-id="ea498-110">Assim como o objeto <xref:Microsoft.SqlServer.Management.Smo.Backup>, o objeto <xref:Microsoft.SqlServer.Management.Smo.Restore> não precisa ser criado através de um método `Create` pois ele não representa objetos na instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea498-110">Like the <xref:Microsoft.SqlServer.Management.Smo.Backup> object, the <xref:Microsoft.SqlServer.Management.Smo.Restore> object does not need to be created by using a `Create` method because it does not represent any object on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ea498-111">O objeto <xref:Microsoft.SqlServer.Management.Smo.Restore> é um conjunto de propriedades e métodos usados para restaurar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ea498-111">The <xref:Microsoft.SqlServer.Management.Smo.Restore> object is a set of properties and methods used to restore a database.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ea498-112">Exemplos</span><span class="sxs-lookup"><span data-stu-id="ea498-112">Examples</span></span>  
 <span data-ttu-id="ea498-113">Para usar qualquer exemplo de código fornecido, será necessário escolher o ambiente de programação, o modelo de programação e a linguagem de programação para criar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ea498-113">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="ea498-114">Para obter mais informações, consulte [criar um projeto Visual Basic Smo no Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) ou [criar um projeto do Visual C&#35; Smo no Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="ea498-114">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="backing-up-databases-and-transaction-logs-in-visual-basic"></a><span data-ttu-id="ea498-115">Fazendo backup de bancos de dados e de logs de transações no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea498-115">Backing Up Databases and Transaction Logs in Visual Basic</span></span>  
 <span data-ttu-id="ea498-116">Este exemplo de código mostra como fazer backup de um banco de dados existente em um arquivo e como restaurá-lo.</span><span class="sxs-lookup"><span data-stu-id="ea498-116">This code example shows how to back up an existing database to a file, and then how to restore it.</span></span>  
  
```vb
Imports Microsoft.SqlServer.Management.Common  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.VisualBasic.MyServices  
  
Module SMO_VBBackup3  
  
    Sub Main()  
        'Connect to the local, default instance of SQL Server.  
        Dim srv As Server  
        srv = New Server  
  
        'Reference the AdventureWorks2012 database.  
        Dim db As Database  
        db = srv.Databases("AdventureWorks2012")  
  
        'Store the current recovery model in a variable.  
        Dim recoverymod As Integer  
        recoverymod = db.DatabaseOptions.RecoveryModel  
  
        'Define a Backup object variable.   
        Dim bk As New Backup  
  
        'Specify the type of backup, the description, the name, and the database to be backed up.  
        bk.Action = BackupActionType.Database  
        bk.BackupSetDescription = "Full backup of AdventureWorks2012"  
        bk.BackupSetName = "AdventureWorks 2012 Backup"  
        bk.Database = "AdventureWorks2012"  
  
        'Declare a BackupDeviceItem by supplying the backup device file name in the constructor, and the type of device is a file.  
        Dim bdi As BackupDeviceItem  
        bdi = New BackupDeviceItem("Test_Full_Backup1", DeviceType.File)  
  
        'Add the device to the Backup object.  
        bk.Devices.Add(bdi)  
  
        'Set the Incremental property to False to specify that this is a full database backup.  
        bk.Incremental = False  
  
        'Set the expiration date.  
        Dim backupdate As New Date  
        backupdate = New Date(2006, 10, 5)  
        bk.ExpirationDate = backupdate  
  
        'Specify that the log must be truncated after the backup is complete.  
        bk.LogTruncation = BackupTruncateLogType.Truncate  
  
        'Run SqlBackup to perform the full database backup on the instance of SQL Server.  
        bk.SqlBackup(srv)  
  
        'Inform the user that the backup has been completed.  
        Console.WriteLine("Full Backup complete.")  
  
        'Remove the backup device from the Backup object.  
        bk.Devices.Remove(bdi)  
  
        'Make a change to the database, in this case, add a table called test_table.  
        Dim t As Table  
        t = New Table(db, "test_table")  
        Dim c As Column  
        c = New Column(t, "col", DataType.Int)  
        t.Columns.Add(c)  
        t.Create()  
  
        'Create another file device for the differential backup and add the Backup object.  
        Dim bdid As BackupDeviceItem  
        bdid = New BackupDeviceItem("Test_Differential_Backup1", DeviceType.File)  
  
        'Add the device to the Backup object.  
        bk.Devices.Add(bdid)  
  
        'Set the Incremental property to True for a differential backup.  
        bk.Incremental = True  
  
        'Run SqlBackup to perform the incremental database backup on the instance of SQL Server.  
        bk.SqlBackup(srv)  
  
        'Inform the user that the differential backup is complete.  
        Console.WriteLine("Differential Backup complete.")  
  
        'Remove the device from the Backup object.  
        bk.Devices.Remove(bdid)  
  
        'Delete the AdventureWorks2012 database before restoring it.  
        srv.Databases("AdventureWorks2012").Drop()  
  
        'Define a Restore object variable.  
        Dim rs As Restore  
        rs = New Restore  
  
        'Set the NoRecovery property to true, so the transactions are not recovered.  
        rs.NoRecovery = True  
  
        'Add the device that contains the full database backup to the Restore object.  
        rs.Devices.Add(bdi)  
  
        'Specify the database name.  
        rs.Database = "AdventureWorks2012"  
  
        'Restore the full database backup with no recovery.  
        rs.SqlRestore(srv)  
  
        'Inform the user that the Full Database Restore is complete.  
        Console.WriteLine("Full Database Restore complete.")  
  
        'Remove the device from the Restore object.  
        rs.Devices.Remove(bdi)  
  
        'Set te NoRecovery property to False.  
        rs.NoRecovery = False  
  
        'Add the device that contains the differential backup to the Restore object.  
        rs.Devices.Add(bdid)  
  
        'Restore the differential database backup with recovery.  
        rs.SqlRestore(srv)  
  
        'Inform the user that the differential database restore is complete.  
        Console.WriteLine("Differential Database Restore complete.")  
  
        'Remove the device.  
        rs.Devices.Remove(bdid)  
  
        'Set the database recovery mode back to its original value.  
        srv.Databases("AdventureWorks2012").DatabaseOptions.RecoveryModel = recoverymod  
  
        'Drop the table that was added.  
        srv.Databases("AdventureWorks2012").Tables("test_table").Drop()  
        srv.Databases("AdventureWorks2012").Alter()  
  
        'Remove the backup files from the hard disk.  
        My.Computer.FileSystem.DeleteFile("C:\Program Files\Microsoft SQL Server\MSSQL.12\MSSQL\Backup\Test_Full_Backup1")  
        My.Computer.FileSystem.DeleteFile("C:\Program Files\Microsoft SQL Server\MSSQL.12\MSSQL\Backup\Test_Differential_Backup1")  
    End Sub  
End Module  
```  
  
## <a name="backing-up-databases-and-transaction-logs-in-visual-c"></a><span data-ttu-id="ea498-117">Fazendo backup de bancos de dados e de logs de transações no Visual C#</span><span class="sxs-lookup"><span data-stu-id="ea498-117">Backing Up Databases and Transaction Logs in Visual C#</span></span>  
 <span data-ttu-id="ea498-118">Este exemplo de código mostra como fazer backup de um banco de dados existente em um arquivo e como restaurá-lo.</span><span class="sxs-lookup"><span data-stu-id="ea498-118">This code example shows how to back up an existing database to a file, and then how to restore it.</span></span>  
  
```csharp
using Microsoft.SqlServer.Management.Common;  
using Microsoft.SqlServer.Management.Smo;  
  
class A {  
   public static void Main() {  
      // Connect to the local, default instance of SQL Server.   
      Server srv = new Server();  
      // Reference the AdventureWorks2012 database.   
      Database db = default(Database);  
      db = srv.Databases["AdventureWorks2012"];  
  
      // Store the current recovery model in a variable.   
      int recoverymod;  
      recoverymod = (int)db.DatabaseOptions.RecoveryModel;  
  
      // Define a Backup object variable.   
      Backup bk = new Backup();  
  
      // Specify the type of backup, the description, the name, and the database to be backed up.   
      bk.Action = BackupActionType.Database;  
      bk.BackupSetDescription = "Full backup of Adventureworks2012";  
      bk.BackupSetName = "AdventureWorks2012 Backup";  
      bk.Database = "AdventureWorks2012";  
  
      // Declare a BackupDeviceItem by supplying the backup device file name in the constructor, and the type of device is a file.   
      BackupDeviceItem bdi = default(BackupDeviceItem);  
      bdi = new BackupDeviceItem("Test_Full_Backup1", DeviceType.File);  
  
      // Add the device to the Backup object.   
      bk.Devices.Add(bdi);  
      // Set the Incremental property to False to specify that this is a full database backup.   
      bk.Incremental = false;  
  
      // Set the expiration date.   
      System.DateTime backupdate = new System.DateTime();  
      backupdate = new System.DateTime(2006, 10, 5);  
      bk.ExpirationDate = backupdate;  
  
      // Specify that the log must be truncated after the backup is complete.   
      bk.LogTruncation = BackupTruncateLogType.Truncate;  
  
      // Run SqlBackup to perform the full database backup on the instance of SQL Server.   
      bk.SqlBackup(srv);  
  
      // Inform the user that the backup has been completed.   
      System.Console.WriteLine("Full Backup complete.");  
  
      // Remove the backup device from the Backup object.   
      bk.Devices.Remove(bdi);  
  
      // Make a change to the database, in this case, add a table called test_table.   
      Table t = default(Table);  
      t = new Table(db, "test_table");  
      Column c = default(Column);  
      c = new Column(t, "col", DataType.Int);  
      t.Columns.Add(c);  
      t.Create();  
  
      // Create another file device for the differential backup and add the Backup object.   
      BackupDeviceItem bdid = default(BackupDeviceItem);  
      bdid = new BackupDeviceItem("Test_Differential_Backup1", DeviceType.File);  
  
      // Add the device to the Backup object.   
      bk.Devices.Add(bdid);  
  
      // Set the Incremental property to True for a differential backup.   
      bk.Incremental = true;  
  
      // Run SqlBackup to perform the incremental database backup on the instance of SQL Server.   
      bk.SqlBackup(srv);  
  
      // Inform the user that the differential backup is complete.   
      System.Console.WriteLine("Differential Backup complete.");  
  
      // Remove the device from the Backup object.   
      bk.Devices.Remove(bdid);  
  
      // Delete the AdventureWorks2012 database before restoring it  
      // db.Drop();  
  
      // Define a Restore object variable.  
      Restore rs = new Restore();  
  
      // Set the NoRecovery property to true, so the transactions are not recovered.   
      rs.NoRecovery = true;  
  
      // Add the device that contains the full database backup to the Restore object.   
      rs.Devices.Add(bdi);  
  
      // Specify the database name.   
      rs.Database = "AdventureWorks2012";  
  
      // Restore the full database backup with no recovery.   
      rs.SqlRestore(srv);  
  
      // Inform the user that the Full Database Restore is complete.   
      Console.WriteLine("Full Database Restore complete.");  
  
      // reacquire a reference to the database  
      db = srv.Databases["AdventureWorks2012"];  
  
      // Remove the device from the Restore object.  
      rs.Devices.Remove(bdi);  
  
      // Set the NoRecovery property to False.   
      rs.NoRecovery = false;  
  
      // Add the device that contains the differential backup to the Restore object.   
      rs.Devices.Add(bdid);  
  
      // Restore the differential database backup with recovery.   
      rs.SqlRestore(srv);  
  
      // Inform the user that the differential database restore is complete.   
      System.Console.WriteLine("Differential Database Restore complete.");  
  
      // Remove the device.   
      rs.Devices.Remove(bdid);  
  
      // Set the database recovery mode back to its original value.  
      db.RecoveryModel = (RecoveryModel)recoverymod;  
  
      // Drop the table that was added.   
      db.Tables["test_table"].Drop();  
      db.Alter();  
  
      // Remove the backup files from the hard disk.  
      // This location is dependent on the installation of SQL Server  
      System.IO.File.Delete("C:\\Program Files\\Microsoft SQL Server\\MSSQL12.MSSQLSERVER\\MSSQL\\Backup\\Test_Full_Backup1");  
      System.IO.File.Delete("C:\\Program Files\\Microsoft SQL Server\\MSSQL12.MSSQLSERVER\\MSSQL\\Backup\\Test_Differential_Backup1");  
   }  
}  
```  
  
## <a name="backing-up-databases-and-transaction-logs-in-powershell"></a><span data-ttu-id="ea498-119">Fazendo backup de bancos de dados e de logs de transações no PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea498-119">Backing Up Databases and Transaction Logs in PowerShell</span></span>  
 <span data-ttu-id="ea498-120">Este exemplo de código mostra como fazer backup de um banco de dados existente em um arquivo e como restaurá-lo.</span><span class="sxs-lookup"><span data-stu-id="ea498-120">This code example shows how to back up an existing database to a file, and then how to restore it.</span></span>  
  
```powershell
#Connect to the local, default instance of SQL Server.  
  
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Reference the AdventureWorks database.  
$db = $srv.Databases["AdventureWorks"]  
  
#Store the current recovery model in a variable.  
$recoverymod = $db.DatabaseOptions.RecoveryModel  
  
#Create a Backup object  
$bk = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Backup  
  
#set to backup the database  
$bk.Action = [Microsoft.SqlServer.Management.SMO.BackupActionType]::Database  
  
#Set back up properties  
$bk.BackupSetDescription = "Full backup of AdventureWorks"  
$bk.BackupSetName = "AdventureWorks Backup"  
$bk.Database = "AdventureWorks"  
  
#Declare a BackupDeviceItem by supplying the backup device file name in the constructor,   
#and the type of device is a file.  
$dt = [Microsoft.SqlServer.Management.SMO.DeviceType]::File  
$bdi = New-Object -TypeName Microsoft.SqlServer.Management.SMO.BackupDeviceItem `  
-argumentlist "Test_FullBackup1", $dt  
  
#Add the device to the Backup object.  
$bk.Devices.Add($bdi)  
  
#Set the Incremental property to False to specify that this is a full database backup.  
$bk.Incremental = $false  
  
#Set the expiration date.  
$bk.ExpirationDate = get-date "10/05/2006"  
  
#Specify that the log must be truncated after the backup is complete.  
$bk.LogTruncation = [Microsoft.SqlServer.Management.SMO.BackupTruncateLogType]::Truncate  
  
#Run SqlBackup to perform the full database backup on the instance of SQL Server.  
$bk.SqlBackup($srv)  
  
#Inform the user that the backup has been completed.  
"Full Backup complete."  
  
#Remove the backup device from the Backup object.  
$bk.Devices.Remove($bdi)  
  
#Make a change to the database, in this case, add a table called test_table.  
$t = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Table -argumentlist $db, "test_table"  
$type = [Microsoft.SqlServer.Management.SMO.DataType]::int  
$c = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Column -argumentlist $t, "col", $type       
$t.Columns.Add($c)  
$t.Create()  
  
#Create another file device for the differential backup and add the Backup object.  
# $dt is file backup device  
$bdid = New-Object -TypeName Microsoft.SqlServer.Management.SMO.BackupDeviceItem `  
-argumentlist "Test_DifferentialBackup1", $dt  
#Add this device to the backup set  
$bk.Devices.Add($bdid)  
  
#Set the Incremental property to True for a differential backup.  
$bk.Incremental = $true  
  
#Run SqlBackup to perform the incremental database backup on the instance of SQL Server.  
$bk.SqlBackup($srv)  
  
#Inform the user that the differential backup is complete.  
"Differential Backup complete."  
  
#Remove the device from the Backup object.  
$bk.Devices.Remove($bdid)  
  
#Delete the AdventureWorks database before restoring it.  
$db.Drop()  
  
#Define a Restore object variable.  
$rs = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Restore  
  
#Set the NoRecovery property to true, so the transactions are not recovered.  
$rs.NoRecovery = $true  
  
#Add the device that contains the full database backup to the Restore object.  
$rs.Devices.Add($bdi)  
  
#Specify the database name.  
$rs.Database = "AdventureWorks"  
#Restore the full database backup with no recovery.  
$rs.SqlRestore($srv)  
  
#Inform the user that the Full Database Restore is complete.  
"Full Database Restore complete."  
  
#Remove the device from the Restore object.  
$rs.Devices.Remove($bdi)  
  
#Set the NoRecovery property to False.  
$rs.NoRecovery = $false  
  
#Add the device that contains the differential backup to the Restore object.  
$rs.Devices.Add($bdid)  
  
#Restore the differential database backup with recovery.  
$rs.SqlRestore($srv)  
  
#Inform the user that the differential database restore is complete.  
"Differential Database Restore complete."  
  
#Remove the device.  
$rs.Devices.Remove($bdid)  
  
#Set the database recovery mode back to its original value.  
$db = $srv.Databases["AdventureWorks"]  
$db.DatabaseOptions.RecoveryModel = $recoverymod  
  
#Drop the table that was added.  
$db.Tables["test_table"].Drop()  
$db.Alter()  
  
#Delete the backup files - the exact location depends on your installation  
del "C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\Test_FullBackup1"  
del "C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\Test_DifferentialBackup1"  
```  
  
## <a name="running-database-integrity-checks-in-visual-basic"></a><span data-ttu-id="ea498-121">Executando verificações da integridade do banco de dados no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea498-121">Running Database Integrity Checks in Visual Basic</span></span>  
 <span data-ttu-id="ea498-122">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fornece verificação da integridade dos dados.</span><span class="sxs-lookup"><span data-stu-id="ea498-122">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provides data integrity checking.</span></span> <span data-ttu-id="ea498-123">Este exemplo de código executa uma verificação do tipo de consistência no banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="ea498-123">This code example runs a database consistency type check on the specified database.</span></span> <span data-ttu-id="ea498-124">Nesse exemplo, <xref:Microsoft.SqlServer.Management.Smo.Database.CheckTables%2A> é usado, mas <xref:Microsoft.SqlServer.Management.Smo.Database.CheckAllocations%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.CheckCatalog%2A> ou <xref:Microsoft.SqlServer.Management.Smo.Database.CheckIdentityValues%2A> pode ser usado da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="ea498-124">In this example, <xref:Microsoft.SqlServer.Management.Smo.Database.CheckTables%2A> is used, but <xref:Microsoft.SqlServer.Management.Smo.Database.CheckAllocations%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.CheckCatalog%2A>, or <xref:Microsoft.SqlServer.Management.Smo.Database.CheckIdentityValues%2A> can be used similarly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea498-125">O objeto <xref:System.Collections.Specialized.StringCollection> exige uma referência ao namespace usando a instrução `imports System.Collections.Specialized`.</span><span class="sxs-lookup"><span data-stu-id="ea498-125">The <xref:System.Collections.Specialized.StringCollection> object requires a reference to the namespace using the `imports System.Collections.Specialized` statement.</span></span>  
  
```vb
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
Imports System.Collections.Specialized  
Module S  
   Sub Main()  
      'Connect to the local, default instance of SQL Server.  
      Dim srv As Server  
      srv = New Server  
      'Reference the AdventureWorks2012 database.  
      Dim db As Database  
      db = srv.Databases("AdventureWorks2012")  
      'Note, to use the StringCollection type the System.Collections.Specialized system namespace must be included in the imports statements.  
      Dim sc As StringCollection  
      'Run the CheckTables method and display the results from the returned StringCollection variable.  
      sc = db.CheckTables(RepairType.None)  
      Dim c As Integer  
      For c = 0 To sc.Count - 1  
         Console.WriteLine(sc.Item(c))  
      Next  
   End Sub  
End Module  
```  
  
## <a name="running-database-integrity-checks-in-visual-c"></a><span data-ttu-id="ea498-126">Executando verificações da integridade do banco de dados no Visual C#</span><span class="sxs-lookup"><span data-stu-id="ea498-126">Running Database Integrity Checks in Visual C#</span></span>  
 <span data-ttu-id="ea498-127">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fornece verificação da integridade dos dados.</span><span class="sxs-lookup"><span data-stu-id="ea498-127">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provides data integrity checking.</span></span> <span data-ttu-id="ea498-128">Este exemplo de código executa uma verificação do tipo de consistência no banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="ea498-128">This code example runs a database consistency type check on the specified database.</span></span> <span data-ttu-id="ea498-129">Nesse exemplo, <xref:Microsoft.SqlServer.Management.Smo.Database.CheckTables%2A> é usado, mas <xref:Microsoft.SqlServer.Management.Smo.Database.CheckAllocations%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.CheckCatalog%2A> ou <xref:Microsoft.SqlServer.Management.Smo.Database.CheckIdentityValues%2A> pode ser usado da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="ea498-129">In this example, <xref:Microsoft.SqlServer.Management.Smo.Database.CheckTables%2A> is used, but <xref:Microsoft.SqlServer.Management.Smo.Database.CheckAllocations%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.CheckCatalog%2A>, or <xref:Microsoft.SqlServer.Management.Smo.Database.CheckIdentityValues%2A> can be used similarly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea498-130">O objeto <xref:System.Collections.Specialized.StringCollection> exige uma referência ao namespace usando a instrução `imports System.Collections.Specialized`.</span><span class="sxs-lookup"><span data-stu-id="ea498-130">The <xref:System.Collections.Specialized.StringCollection> object requires a reference to the namespace using the `imports System.Collections.Specialized` statement.</span></span>  
  
```csharp
using Microsoft.SqlServer.Management.Common;  
using Microsoft.SqlServer.Management.Smo;  
using System;  
  
class A {  
   public static void Main() {  
      // Connect to the local, default instance of SQL Server.   
      Server srv = new Server();  
  
      // Reference the AdventureWorks2012 database.             
      Database db = srv.Databases["AdventureWorks2012"];  
  
      // Note, to use the StringCollection type the System.Collections.Specialized system namespace must be included in the imports statements.   
      System.Collections.Specialized.StringCollection sc;  
  
      // Run the CheckTables method and display the results from the returned StringCollection variable.   
      sc = db.CheckTables(RepairType.None);  
  
      foreach (string c in sc) {  
         Console.WriteLine(c);  
      }  
   }  
}  
```  
  
## <a name="running-database-integrity-checks-in-powershell"></a><span data-ttu-id="ea498-131">Executando verificações da integridade do banco de dados no PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea498-131">Running Database Integrity Checks in PowerShell</span></span>  
 <span data-ttu-id="ea498-132">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fornece verificação da integridade dos dados.</span><span class="sxs-lookup"><span data-stu-id="ea498-132">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provides data integrity checking.</span></span> <span data-ttu-id="ea498-133">Este exemplo de código executa uma verificação do tipo de consistência no banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="ea498-133">This code example runs a database consistency type check on the specified database.</span></span> <span data-ttu-id="ea498-134">Nesse exemplo, <xref:Microsoft.SqlServer.Management.Smo.Database.CheckTables%2A> é usado, mas <xref:Microsoft.SqlServer.Management.Smo.Database.CheckAllocations%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.CheckCatalog%2A> ou <xref:Microsoft.SqlServer.Management.Smo.Database.CheckIdentityValues%2A> pode ser usado da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="ea498-134">In this example, <xref:Microsoft.SqlServer.Management.Smo.Database.CheckTables%2A> is used, but <xref:Microsoft.SqlServer.Management.Smo.Database.CheckAllocations%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.CheckCatalog%2A>, or <xref:Microsoft.SqlServer.Management.Smo.Database.CheckIdentityValues%2A> can be used similarly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea498-135">O objeto <xref:System.Collections.Specialized.StringCollection> exige uma referência ao namespace usando a instrução `imports System.Collections.Specialized`.</span><span class="sxs-lookup"><span data-stu-id="ea498-135">The <xref:System.Collections.Specialized.StringCollection> object requires a reference to the namespace using the `imports System.Collections.Specialized` statement.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
$sc = $db.CheckTables([Microsoft.SqlServer.Management.SMO.RepairType]::None)  
ForEach ($c In $sc)  
{  
    $c  
}  
```  