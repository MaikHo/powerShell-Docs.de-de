---
title: Schreiben eines Container Anbieters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 524fd900-c0fe-4d13-87f2-14903a8fd5a4
caps.latest.revision: 5
ms.openlocfilehash: 48ab9102e8f1b17b3b533cc3b0aa1dacef0e2076
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366239"
---
# <a name="writing-a-container-provider"></a><span data-ttu-id="cffe2-102">Schreiben eines Containeranbieters</span><span class="sxs-lookup"><span data-stu-id="cffe2-102">Writing a container provider</span></span>

<span data-ttu-id="cffe2-103">In diesem Thema wird beschrieben, wie die Methoden eines Windows PowerShell-Anbieters implementiert werden, die Elemente unterstützen, die andere Elemente enthalten, z. b. Ordner im Dateisystem Anbieter.</span><span class="sxs-lookup"><span data-stu-id="cffe2-103">This topic describes how to implement the methods of a Windows PowerShell provider that support items that contain other items, such as folders in the file system provider.</span></span> <span data-ttu-id="cffe2-104">Damit Container unterstützt werden können, muss ein Anbieter von der [System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) -Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="cffe2-104">To be able to support containers, a provider must derive from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span>

<span data-ttu-id="cffe2-105">Für den Anbieter in den Beispielen in diesem Thema wird eine Access-Datenbank als Datenspeicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="cffe2-105">The provider in the examples in this topic uses an Access database as its data store.</span></span> <span data-ttu-id="cffe2-106">Es gibt mehrere Hilfsmethoden und-Klassen, die für die Interaktion mit der Datenbank verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cffe2-106">There are several helper methods and classes that are used to interact with the database.</span></span> <span data-ttu-id="cffe2-107">Das komplette Beispiel, das die-Hilfsmethoden enthält, finden Sie unter [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="cffe2-107">For the complete sample that includes the helper methods, see [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>

<span data-ttu-id="cffe2-108">Weitere Informationen zu Windows PowerShell-Anbietern finden Sie unter Übersicht über den [Windows PowerShell-Anbieter](./windows-powershell-provider-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cffe2-108">For more information about Windows PowerShell providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span>

## <a name="implementing-container-methods"></a><span data-ttu-id="cffe2-109">Implementieren von Container Methoden</span><span class="sxs-lookup"><span data-stu-id="cffe2-109">Implementing container methods</span></span>

<span data-ttu-id="cffe2-110">Die [System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) -Klasse implementiert Methoden, die Container unterstützen, und erstellt, kopiert und entfernt Elemente.</span><span class="sxs-lookup"><span data-stu-id="cffe2-110">The [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class implements methods that support containers, and create, copy, and remove items.</span></span> <span data-ttu-id="cffe2-111">Eine umfassende Liste dieser Methoden finden Sie unter [System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider?view=pscore-6.2.0#methods).</span><span class="sxs-lookup"><span data-stu-id="cffe2-111">For a complete list of these methods, see [System.Management.Automation.Provider.ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider?view=pscore-6.2.0#methods).</span></span>

> [!NOTE]
> <span data-ttu-id="cffe2-112">Dieses Thema baut auf den Informationen in der Schnellstartanleitung für den [Windows PowerShell-Anbieter](./windows-powershell-provider-quickstart.md)auf.</span><span class="sxs-lookup"><span data-stu-id="cffe2-112">This topic builds on the information in [Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md).</span></span> <span data-ttu-id="cffe2-113">Dieses Thema behandelt nicht die Grundlagen der Einrichtung eines Anbieter Projekts oder die Implementierung der Methoden, die von der [System. Management. Automation. Provider. drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) -Klasse geerbt werden, die Laufwerke erstellt und entfernt.</span><span class="sxs-lookup"><span data-stu-id="cffe2-113">This topic does not cover the basics of how to set up a provider project, or how to implement the methods inherited from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class that create and remove drives.</span></span> <span data-ttu-id="cffe2-114">Außerdem wird in diesem Thema nicht behandelt, wie Methoden implementiert werden, die von der [System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) -Klasse verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="cffe2-114">This topic also does not cover how to implement methods exposed by the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="cffe2-115">Ein Beispiel, das zeigt, wie Item-Cmdlets implementiert werden, finden Sie unter [Schreiben eines Element Anbieters](./writing-an-item-provider.md).</span><span class="sxs-lookup"><span data-stu-id="cffe2-115">For an example that shows how to implement item cmdlets, see [Writing an item provider](./writing-an-item-provider.md).</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="cffe2-116">Deklarieren der Anbieter Klasse</span><span class="sxs-lookup"><span data-stu-id="cffe2-116">Declaring the provider class</span></span>

<span data-ttu-id="cffe2-117">Deklarieren Sie den Anbieter so, dass er von der [System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) -Klasse abgeleitet wird, und versehen Sie ihn mit dem [System. Management. Automation. Provider. cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span><span class="sxs-lookup"><span data-stu-id="cffe2-117">Declare the provider to derive from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class, and decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span></span>

```csharp
[CmdletProvider("AccessDB", ProviderCapabilities.None)]
   public class AccessDBProvider : ContainerCmdletProvider
   {

   }
```

### <a name="implementing-getchilditems"></a><span data-ttu-id="cffe2-118">Implementieren von "getchilditems"</span><span class="sxs-lookup"><span data-stu-id="cffe2-118">Implementing GetChildItems</span></span>

<span data-ttu-id="cffe2-119">Die PowerShell-Engine ruft die [System. Management. Automation. Provider. containercmdletprovider. getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) -Methode auf, wenn ein Benutzer das [Microsoft. PowerShell. Commands. getchilditemcommand](/dotnet/api/Microsoft.PowerShell.Commands.Getchilditemcommand) -Cmdlet aufruft.</span><span class="sxs-lookup"><span data-stu-id="cffe2-119">The PowerShell engine calls the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method when a user calls the [Microsoft.PowerShell.Commands.GetChildItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.Getchilditemcommand) cmdlet.</span></span> <span data-ttu-id="cffe2-120">Diese Methode ruft die Elemente ab, die die untergeordneten Elemente des Elements am angegebenen Pfad sind.</span><span class="sxs-lookup"><span data-stu-id="cffe2-120">This method gets the items that are the children of the item at the specified path.</span></span>

<span data-ttu-id="cffe2-121">Im Beispiel Access Database hängt das Verhalten der [System. Management. Automation. Provider. containercmdletprovider. getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) -Methode vom Typ des angegebenen Elements ab.</span><span class="sxs-lookup"><span data-stu-id="cffe2-121">In the Access database example, the behavior of the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method depends on the type of the specified item.</span></span> <span data-ttu-id="cffe2-122">Wenn es sich bei dem Element um das Laufwerk handelt, sind die untergeordneten Elemente Tabellen, und die Methode gibt den Satz von Tabellen aus der Datenbank zurück.</span><span class="sxs-lookup"><span data-stu-id="cffe2-122">If the item is the drive, then the children are tables, and the method returns the set of tables from the database.</span></span> <span data-ttu-id="cffe2-123">Wenn das angegebene Element eine Tabelle ist, sind die untergeordneten Elemente die Zeilen dieser Tabelle.</span><span class="sxs-lookup"><span data-stu-id="cffe2-123">If the specified item is a table, then the children are the rows of that table.</span></span> <span data-ttu-id="cffe2-124">Wenn das Element eine Zeile ist, enthält es keine untergeordneten Elemente, und die Methode gibt diese Zeile nur zurück.</span><span class="sxs-lookup"><span data-stu-id="cffe2-124">If the item is a row, then it  has no children, and the method returns that row only.</span></span> <span data-ttu-id="cffe2-125">Alle untergeordneten Elemente werden von der [System. Management. Automation. Provider. cmdletprovider. beschreiteitemabject \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) -Methode zurück an die PowerShell-Engine gesendet.</span><span class="sxs-lookup"><span data-stu-id="cffe2-125">All child items are sent back to the PowerShell engine by the [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) method.</span></span>

```csharp
protected override void GetChildItems(string path, bool recurse)
       {
           // If path represented is a drive then the children in the path are
           // tables. Hence all tables in the drive represented will have to be
           // returned
           if (PathIsDrive(path))
           {
               foreach (DatabaseTableInfo table in GetTables())
               {
                   WriteItemObject(table, path, true);

                   // if the specified item exists and recurse has been set then
                   // all child items within it have to be obtained as well
                   if (ItemExists(path) && recurse)
                   {
                       GetChildItems(path + pathSeparator + table.Name, recurse);
                   }
               } // foreach (DatabaseTableInfo...
           } // if (PathIsDrive...
           else
           {
               // Get the table name, row number and type of path from the
               // path specified
               string tableName;
               int rowNumber;

               PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

               if (type == PathType.Table)
               {
                   // Obtain all the rows within the table
                   foreach (DatabaseRowInfo row in GetRows(tableName))
                   {
                       WriteItemObject(row, path + pathSeparator + row.RowNumber,
                               false);
                   } // foreach (DatabaseRowInfo...
               }
               else if (type == PathType.Row)
               {
                   // In this case the user has directly specified a row, hence
                   // just give that particular row
                   DatabaseRowInfo row = GetRow(tableName, rowNumber);
                   WriteItemObject(row, path + pathSeparator + row.RowNumber,
                               false);
               }
               else
               {
                   // In this case, the path specified is not valid
                   ThrowTerminatingInvalidPathException(path);
               }
           } // else
       }
```

### <a name="implementing-getchildnames"></a><span data-ttu-id="cffe2-126">Implementieren von "getchildnames"</span><span class="sxs-lookup"><span data-stu-id="cffe2-126">Implementing GetChildNames</span></span>

<span data-ttu-id="cffe2-127">Die [System. Management. Automation. Provider. containercmdletprovider. getchildnames \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) -Methode ähnelt der [System. Management. Automation. Provider. containercmdletprovider. getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) -Methode, mit der Ausnahme, dass Sie nur zurückgibt. die Name-Eigenschaft der Elemente und nicht die Elemente selbst.</span><span class="sxs-lookup"><span data-stu-id="cffe2-127">The [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) method is similar to the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method, except that it returns only the name property of the items, and not the items themselves.</span></span>

```csharp
protected override void GetChildNames(string path,
                                     ReturnContainers returnContainers)
       {
           // If the path represented is a drive, then the child items are
           // tables. get the names of all the tables in the drive.
           if (PathIsDrive(path))
           {
               foreach (DatabaseTableInfo table in GetTables())
               {
                   WriteItemObject(table.Name, path, true);
               } // foreach (DatabaseTableInfo...
           } // if (PathIsDrive...
           else
           {
               // Get type, table name and row number from path specified
               string tableName;
               int rowNumber;

               PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

               if (type == PathType.Table)
               {
                   // Get all the rows in the table and then write out the
                   // row numbers.
                   foreach (DatabaseRowInfo row in GetRows(tableName))
                   {
                       WriteItemObject(row.RowNumber, path, false);
                   } // foreach (DatabaseRowInfo...
               }
               else if (type == PathType.Row)
               {
                   // In this case the user has directly specified a row, hence
                   // just give that particular row
                   DatabaseRowInfo row = GetRow(tableName, rowNumber);

                   WriteItemObject(row.RowNumber, path, false);
               }
               else
               {
                   ThrowTerminatingInvalidPathException(path);
               }
           } // else
       }
```

### <a name="implementing-newitem"></a><span data-ttu-id="cffe2-128">Implementieren von "netwitem"</span><span class="sxs-lookup"><span data-stu-id="cffe2-128">Implementing NewItem</span></span>

<span data-ttu-id="cffe2-129">Die [System. Management. Automation. Provider. containercmdletprovider. netwitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) -Methode erstellt ein neues Element vom angegebenen Typ im angegebenen Pfad.</span><span class="sxs-lookup"><span data-stu-id="cffe2-129">The [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method creates a new item of the specified type at the specified path.</span></span> <span data-ttu-id="cffe2-130">Die PowerShell-Engine ruft diese Methode auf, wenn ein Benutzer das [Microsoft. PowerShell. Commands. netwitemcommand](/dotnet/api/Microsoft.PowerShell.Commands.newitemcommand) -Cmdlet aufruft.</span><span class="sxs-lookup"><span data-stu-id="cffe2-130">The PowerShell engine calls this method when a user calls the [Microsoft.PowerShell.Commands.NewItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.newitemcommand) cmdlet.</span></span>

<span data-ttu-id="cffe2-131">In diesem Beispiel implementiert die-Methode Logik, um zu bestimmen, ob der Pfad und der Typ einander entsprechen.</span><span class="sxs-lookup"><span data-stu-id="cffe2-131">In this example, the method implements logic to determine that the path and type match.</span></span> <span data-ttu-id="cffe2-132">Das heißt, es kann nur eine Tabelle direkt unterhalb des Laufwerks (der Datenbank) erstellt werden, und es kann nur eine Zeile unter einer Tabelle erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="cffe2-132">That is, only a table can be created directly under the drive (the database), and only a row can be created under a table.</span></span> <span data-ttu-id="cffe2-133">Wenn der angegebene Pfad und Elementtyp auf diese Weise nicht identisch sind, löst die Methode eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="cffe2-133">If the specified path and item type don't match in this way, the method throws an exception.</span></span>

```csharp
protected override void NewItem(string path, string type,
                                   object newItemValue)
       {
           string tableName;
           int rowNumber;

           PathType pt = GetNamesFromPath(path, out tableName, out rowNumber);

           if (pt == PathType.Invalid)
           {
               ThrowTerminatingInvalidPathException(path);
           }

           // Check if type is either "table" or "row", if not throw an
           // exception
           if (!String.Equals(type, "table", StringComparison.OrdinalIgnoreCase)
               && !String.Equals(type, "row", StringComparison.OrdinalIgnoreCase))
           {
               WriteError(new ErrorRecord
                                 (new ArgumentException("Type must be either a table or row"),
                                     "CannotCreateSpecifiedObject",
                                        ErrorCategory.InvalidArgument,
                                             path
                                  )
                         );

               throw new ArgumentException("This provider can only create items of type \"table\" or \"row\"");
           }

           // Path type is the type of path of the container. So if a drive
           // is specified, then a table can be created under it and if a table
           // is specified, then a row can be created under it. For the sake of
           // completeness, if a row is specified, then if the row specified by
           // the path does not exist, a new row is created. However, the row
           // number may not match as the row numbers only get incremented based
           // on the number of rows

           if (PathIsDrive(path))
           {
               if (String.Equals(type, "table", StringComparison.OrdinalIgnoreCase))
               {
                   // Execute command using ODBC connection to create a table
                   try
                   {
                       // create the table using an sql statement
                       string newTableName = newItemValue.ToString();

                       if (!TableNameIsValid(newTableName))
                       {
                           return;
                       }
                       string sql = "create table " + newTableName
                                            + " (ID INT)";

                       // Create the table using the Odbc connection from the
                       // drive.
                       AccessDBPSDriveInfo di = this.PSDriveInfo as AccessDBPSDriveInfo;

                       if (di == null)
                       {
                           return;
                       }
                       OdbcConnection connection = di.Connection;

                       if (ShouldProcess(newTableName, "create"))
                       {
                           OdbcCommand cmd = new OdbcCommand(sql, connection);
                           cmd.ExecuteScalar();
                       }
                   }
                   catch (Exception ex)
                   {
                       WriteError(new ErrorRecord(ex, "CannotCreateSpecifiedTable",
                                 ErrorCategory.InvalidOperation, path)
                                 );
                   }
               } // if (String...
               else if (String.Equals(type, "row", StringComparison.OrdinalIgnoreCase))
               {
                   throw new
                       ArgumentException("A row cannot be created under a database, specify a path that represents a Table");
               }
           }// if (PathIsDrive...
           else
           {
               if (String.Equals(type, "table", StringComparison.OrdinalIgnoreCase))
               {
                   if (rowNumber < 0)
                   {
                       throw new
                           ArgumentException("A table cannot be created within another table, specify a path that represents a database");
                   }
                   else
                   {
                       throw new
                           ArgumentException("A table cannot be created inside a row, specify a path that represents a database");
                   }
               } //if (String.Equals....
               // if path specified is a row, create a new row
               else if (String.Equals(type, "row", StringComparison.OrdinalIgnoreCase))
               {
                   // The user is required to specify the values to be inserted
                   // into the table in a single string separated by commas
                   string value = newItemValue as string;

                   if (String.IsNullOrEmpty(value))
                   {
                       throw new
                           ArgumentException("Value argument must have comma separated values of each column in a row");
                   }
                   string[] rowValues = value.Split(',');

                   OdbcDataAdapter da = GetAdapterForTable(tableName);

                   if (da == null)
                   {
                       return;
                   }

                   DataSet ds = GetDataSetForTable(da, tableName);
                   DataTable table = GetDataTable(ds, tableName);

                   if (rowValues.Length != table.Columns.Count)
                   {
                       string message =
                            String.Format(CultureInfo.CurrentCulture,
                                            "The table has {0} columns and the value specified must have so many comma separated values",
                                                table.Columns.Count);

                       throw new ArgumentException(message);
                   }

                   if (!Force && (rowNumber >=0 && rowNumber < table.Rows.Count))
                   {
                       string message = String.Format(CultureInfo.CurrentCulture,
                                                        "The row {0} already exists. To create a new row specify row number as {1}, or specify path to a table, or use the -Force parameter",
                                                            rowNumber, table.Rows.Count);

                       throw new ArgumentException(message);
                   }

                   if (rowNumber > table.Rows.Count)
                   {
                       string message = String.Format(CultureInfo.CurrentCulture,
                                            "To create a new row specify row number as {0}, or specify path to a table",
                                                table.Rows.Count);

                       throw new ArgumentException(message);
                   }

                   // Create a new row and update the row with the input
                   // provided by the user
                   DataRow row = table.NewRow();
                   for (int i = 0; i < rowValues.Length; i++)
                   {
                       row[i] = rowValues[i];
                   }
                   table.Rows.Add(row);

                   if (ShouldProcess(tableName, "update rows"))
                   {
                       // Update the table from memory back to the data source
                       da.Update(ds, tableName);
                   }

               }// else if (String...
           }// else ...

       }
```

### <a name="implementing-copyitem"></a><span data-ttu-id="cffe2-134">Implementieren von CopyItem</span><span class="sxs-lookup"><span data-stu-id="cffe2-134">Implementing CopyItem</span></span>

<span data-ttu-id="cffe2-135">Das [System. Management. Automation. Provider. containercmdletprovider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) kopiert das angegebene Element in den angegebenen Pfad.</span><span class="sxs-lookup"><span data-stu-id="cffe2-135">The [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) copies the specified item to the specified path.</span></span> <span data-ttu-id="cffe2-136">Die PowerShell-Engine ruft diese Methode auf, wenn ein Benutzer das [Microsoft. PowerShell. Commands. copyitemcommand](/dotnet/api/Microsoft.PowerShell.Commands.copyitemcommand) -Cmdlet aufruft.</span><span class="sxs-lookup"><span data-stu-id="cffe2-136">The PowerShell engine calls this method when a user calls the [Microsoft.PowerShell.Commands.CopyItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.copyitemcommand) cmdlet.</span></span> <span data-ttu-id="cffe2-137">Diese Methode kann auch rekursiv sein, wobei alle untergeordneten Elemente zusätzlich zum eigentlichen Element kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="cffe2-137">This method can also be recursive, copying all of the items children in addition to the item itself.</span></span>

<span data-ttu-id="cffe2-138">Ähnlich wie bei der [System. Management. Automation. Provider. containercmdletprovider. netwitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) -Methode führt diese Methode Logik aus, um sicherzustellen, dass das angegebene Element den richtigen Typ für den Pfad hat, in den Sie kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="cffe2-138">Similarly to the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method, this method performs logic to make sure that the specified item is of the correct type for the path to which it is being copied.</span></span> <span data-ttu-id="cffe2-139">Wenn der Zielpfad z. b. eine Tabelle ist, muss das zu kopierende Element eine Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="cffe2-139">For example, if the destination path is a table, the item to be copied must be a row.</span></span>

```csharp
protected override void CopyItem(string path, string copyPath, bool recurse)
       {
           string tableName, copyTableName;
           int rowNumber, copyRowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);
           PathType copyType = GetNamesFromPath(copyPath, out copyTableName, out copyRowNumber);

           if (type == PathType.Invalid)
           {
               ThrowTerminatingInvalidPathException(path);
           }

           if (type == PathType.Invalid)
           {
               ThrowTerminatingInvalidPathException(copyPath);
           }

           // Get the table and the table to copy to
           OdbcDataAdapter da = GetAdapterForTable(tableName);
           if (da == null)
           {
               return;
           }

           DataSet ds = GetDataSetForTable(da, tableName);
           DataTable table = GetDataTable(ds, tableName);

           OdbcDataAdapter cda = GetAdapterForTable(copyTableName);
           if (cda == null)
           {
               return;
           }

           DataSet cds = GetDataSetForTable(cda, copyTableName);
           DataTable copyTable = GetDataTable(cds, copyTableName);

           // if source represents a table
           if (type == PathType.Table)
           {
               // if copyPath does not represent a table
               if (copyType != PathType.Table)
               {
                   ArgumentException e = new ArgumentException("Table can only be copied on to another table location");

                   WriteError(new ErrorRecord(e, "PathNotValid",
                       ErrorCategory.InvalidArgument, copyPath));

                   throw e;
               }

               // if table already exists then force parameter should be set
               // to force a copy
               if (!Force && GetTable(copyTableName) != null)
               {
                   throw new ArgumentException("Specified path already exists");
               }

               for (int i = 0; i < table.Rows.Count; i++)
               {
                   DataRow row = table.Rows[i];
                   DataRow copyRow = copyTable.NewRow();

                   copyRow.ItemArray = row.ItemArray;
                   copyTable.Rows.Add(copyRow);
               }
           } // if (type == ...
           // if source represents a row
           else
           {
               if (copyType == PathType.Row)
               {
                   if (!Force && (copyRowNumber < copyTable.Rows.Count))
                   {
                       throw new ArgumentException("Specified path already exists.");
                   }

                   DataRow row = table.Rows[rowNumber];
                   DataRow copyRow = null;

                   if (copyRowNumber < copyTable.Rows.Count)
                   {
                       // copy to an existing row
                       copyRow = copyTable.Rows[copyRowNumber];
                       copyRow.ItemArray = row.ItemArray;
                       copyRow[0] = GetNextID(copyTable);
                   }
                   else if (copyRowNumber == copyTable.Rows.Count)
                   {
                       // copy to the next row in the table that will
                       // be created
                       copyRow = copyTable.NewRow();
                       copyRow.ItemArray = row.ItemArray;
                       copyRow[0] = GetNextID(copyTable);
                       copyTable.Rows.Add(copyRow);
                   }
                   else
                   {
                       // attempting to copy to a nonexistent row or a row
                       // that cannot be created now - throw an exception
                       string message = String.Format(CultureInfo.CurrentCulture,
                                             "The item cannot be specified to the copied row. Specify row number as {0}, or specify a path to the table.",
                                                    table.Rows.Count);

                       throw new ArgumentException(message);
                   }
               }
               else
               {
                   // destination path specified represents a table,
                   // create a new row and copy the item
                   DataRow copyRow = copyTable.NewRow();
                   copyRow.ItemArray = table.Rows[rowNumber].ItemArray;
                   copyRow[0] = GetNextID(copyTable);
                   copyTable.Rows.Add(copyRow);
               }
           }

           if (ShouldProcess(copyTableName, "CopyItems"))
           {
               cda.Update(cds, copyTableName);
           }

       } //CopyItem
```

### <a name="implementing-removeitem"></a><span data-ttu-id="cffe2-140">Implementieren von RemoveItem</span><span class="sxs-lookup"><span data-stu-id="cffe2-140">Implementing RemoveItem</span></span>

<span data-ttu-id="cffe2-141">Die [System. Management. Automation. Provider. containercmdletprovider. RemoveItem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) -Methode entfernt das Element im angegebenen Pfad.</span><span class="sxs-lookup"><span data-stu-id="cffe2-141">The [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) method removes the item at the specified path.</span></span> <span data-ttu-id="cffe2-142">Die PowerShell-Engine ruft diese Methode auf, wenn ein Benutzer das [Microsoft. PowerShell. Commands. removeitemcommand](/dotnet/api/Microsoft.PowerShell.Commands.removeitemcommand) -Cmdlet aufruft.</span><span class="sxs-lookup"><span data-stu-id="cffe2-142">The PowerShell engine calls this method when a user calls the [Microsoft.PowerShell.Commands.RemoveItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.removeitemcommand) cmdlet.</span></span>

```csharp
protected override void RemoveItem(string path, bool recurse)
       {
           string tableName;
           int rowNumber = 0;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type == PathType.Table)
           {
               // if recurse flag has been specified, delete all the rows as well
               if (recurse)
               {
                   OdbcDataAdapter da = GetAdapterForTable(tableName);
                   if (da == null)
                   {
                       return;
                   }

                   DataSet ds = GetDataSetForTable(da, tableName);
                   DataTable table = GetDataTable(ds, tableName);

                   for (int i = 0; i < table.Rows.Count; i++)
                   {
                       table.Rows[i].Delete();
                   }

                   if (ShouldProcess(path, "RemoveItem"))
                   {
                       da.Update(ds, tableName);
                       RemoveTable(tableName);
                   }
               }//if (recurse...
               else
               {
                   // Remove the table
                   if (ShouldProcess(path, "RemoveItem"))
                   {
                       RemoveTable(tableName);
                   }
               }
           }
           else if (type == PathType.Row)
           {
               OdbcDataAdapter da = GetAdapterForTable(tableName);
               if (da == null)
               {
                   return;
               }

               DataSet ds = GetDataSetForTable(da, tableName);
               DataTable table = GetDataTable(ds, tableName);

               table.Rows[rowNumber].Delete();

               if (ShouldProcess(path, "RemoveItem"))
               {
                   da.Update(ds, tableName);
               }
           }
           else
           {
               ThrowTerminatingInvalidPathException(path);
           }

       }
```

## <a name="next-steps"></a><span data-ttu-id="cffe2-143">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="cffe2-143">Next steps</span></span>

<span data-ttu-id="cffe2-144">Ein typischer Real-World-Anbieter ist in der Lage, Elemente innerhalb des Laufwerks von einem Pfad zu einem anderen zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="cffe2-144">A typical real-world provider is capable of moving items from one path to another within the drive.</span></span> <span data-ttu-id="cffe2-145">Ein Beispiel für einen Anbieter, der das Verschieben von Elementen unterstützt, finden Sie unter [Schreiben eines navigationsanbieters](./writing-a-navigation-provider.md).</span><span class="sxs-lookup"><span data-stu-id="cffe2-145">For an example of a provider that supports moving items, see [Writing a navigation provider](./writing-a-navigation-provider.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cffe2-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cffe2-146">See Also</span></span>

[<span data-ttu-id="cffe2-147">Schreiben eines navigationsanbieters</span><span class="sxs-lookup"><span data-stu-id="cffe2-147">Writing a navigation provider</span></span>](./writing-a-navigation-provider.md)

[<span data-ttu-id="cffe2-148">Windows PowerShell-Anbieter (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="cffe2-148">Windows PowerShell Provider Overview</span></span>](./windows-powershell-provider-overview.md)