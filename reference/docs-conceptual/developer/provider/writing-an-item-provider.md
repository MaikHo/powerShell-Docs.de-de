---
title: Schreiben eines Element Anbieters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 606c880c-6cf1-4ea6-8730-dbf137bfabff
caps.latest.revision: 5
ms.openlocfilehash: 12d2cb8c40c9fd6278bb964a6259d03167536195
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359879"
---
# <a name="writing-an-item-provider"></a><span data-ttu-id="4f14b-102">Schreiben eines Elementanbieters</span><span class="sxs-lookup"><span data-stu-id="4f14b-102">Writing an item provider</span></span>

<span data-ttu-id="4f14b-103">In diesem Thema wird beschrieben, wie die Methoden eines Windows PowerShell-Anbieters implementiert werden, die auf Elemente im Datenspeicher zugreifen und diese bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4f14b-103">This topic describes how to implement the methods of a Windows PowerShell provider that access and manipulate items in the data store.</span></span> <span data-ttu-id="4f14b-104">Um auf Elemente zugreifen zu können, muss ein Anbieter von der [System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) -Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="4f14b-104">To be able to access items, a provider must derive from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>

<span data-ttu-id="4f14b-105">Für den Anbieter in den Beispielen in diesem Thema wird eine Access-Datenbank als Datenspeicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="4f14b-105">The provider in the examples in this topic uses an Access database as its data store.</span></span> <span data-ttu-id="4f14b-106">Es gibt mehrere Hilfsmethoden und-Klassen, die für die Interaktion mit der Datenbank verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4f14b-106">There are several helper methods and classes that are used to interact with the database.</span></span> <span data-ttu-id="4f14b-107">Das komplette Beispiel, das die Hilfsmethoden enthält, finden Sie unter [AccessDBProviderSample03](./accessdbprovidersample03.md)</span><span class="sxs-lookup"><span data-stu-id="4f14b-107">For the complete sample that includes the helper methods, see [AccessDBProviderSample03](./accessdbprovidersample03.md)</span></span>

<span data-ttu-id="4f14b-108">Weitere Informationen zu Windows PowerShell-Anbietern finden Sie unter Übersicht über den [Windows PowerShell-Anbieter](./windows-powershell-provider-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4f14b-108">For more information about Windows PowerShell providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span>

## <a name="implementing-item-methods"></a><span data-ttu-id="4f14b-109">Implementieren von Element Methoden</span><span class="sxs-lookup"><span data-stu-id="4f14b-109">Implementing item methods</span></span>

<span data-ttu-id="4f14b-110">Die [System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) -Klasse stellt mehrere Methoden bereit, die verwendet werden können, um auf die Elemente in einem Datenspeicher zuzugreifen und diese zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4f14b-110">The [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class exposes several methods that can be used to access and manipulate the items in a data store.</span></span> <span data-ttu-id="4f14b-111">Eine umfassende Liste dieser Methoden finden Sie unter [itemcmdletprovider-Methoden](/dotnet/api/system.management.automation.provider.itemcmdletprovider?view=pscore-6.2.0#methods).</span><span class="sxs-lookup"><span data-stu-id="4f14b-111">For a complete list of these methods, see [ItemCmdletProvider Methods](/dotnet/api/system.management.automation.provider.itemcmdletprovider?view=pscore-6.2.0#methods).</span></span> <span data-ttu-id="4f14b-112">In diesem Beispiel werden vier dieser Methoden implementiert.</span><span class="sxs-lookup"><span data-stu-id="4f14b-112">In this example, we will implement four of these methods.</span></span> <span data-ttu-id="4f14b-113">[System. Management. Automation. Provider. itemcmdletprovider. GetItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) Ruft ein Element an einem angegebenen Pfad ab.</span><span class="sxs-lookup"><span data-stu-id="4f14b-113">[System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) gets an item at a specified path.</span></span> <span data-ttu-id="4f14b-114">[System. Management. Automation. Provider. itemcmdletprovider. SetItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) legt den Wert des angegebenen Elements fest.</span><span class="sxs-lookup"><span data-stu-id="4f14b-114">[System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) sets the value of the specified item.</span></span> <span data-ttu-id="4f14b-115">[System. Management. Automation. Provider. itemcmdletprovider. itemexists \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) überprüft, ob ein Element im angegebenen Pfad vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4f14b-115">[System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) checks whether an item exists at the specified path.</span></span> <span data-ttu-id="4f14b-116">[System. Management. Automation. Provider. itemcmdletprovider. IsValidPath \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) überprüft einen Pfad, um festzustellen, ob er einem Speicherort im Datenspeicher zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4f14b-116">[System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) checks a path to see if it maps to a location in the data store.</span></span>

> [!NOTE]
> <span data-ttu-id="4f14b-117">Dieses Thema baut auf den Informationen in der Schnellstartanleitung für den [Windows PowerShell-Anbieter](./windows-powershell-provider-quickstart.md)auf.</span><span class="sxs-lookup"><span data-stu-id="4f14b-117">This topic builds on the information in [Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md).</span></span> <span data-ttu-id="4f14b-118">Dieses Thema behandelt nicht die Grundlagen der Einrichtung eines Anbieter Projekts oder die Implementierung der Methoden, die von der [System. Management. Automation. Provider. drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) -Klasse geerbt werden, die Laufwerke erstellt und entfernt.</span><span class="sxs-lookup"><span data-stu-id="4f14b-118">This topic does not cover the basics of how to set up a provider project, or how to implement the methods inherited from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class that create and remove drives.</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="4f14b-119">Deklarieren der Anbieter Klasse</span><span class="sxs-lookup"><span data-stu-id="4f14b-119">Declaring the provider class</span></span>

<span data-ttu-id="4f14b-120">Deklarieren Sie den Anbieter so, dass er von der [System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) -Klasse abgeleitet wird, und versehen Sie ihn mit dem [System. Management. Automation. Provider. cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span><span class="sxs-lookup"><span data-stu-id="4f14b-120">Declare the provider to derive from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class, and decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span></span>

```csharp
[CmdletProvider("AccessDB", ProviderCapabilities.None)]

   public class AccessDBProvider : ItemCmdletProvider
   {

  }

```

### <a name="implementing-getitem"></a><span data-ttu-id="4f14b-121">Implementieren von GetItem</span><span class="sxs-lookup"><span data-stu-id="4f14b-121">Implementing GetItem</span></span>

<span data-ttu-id="4f14b-122">Das [System. Management. Automation. Provider. itemcmdletprovider. GetItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) wird von der PowerShell-Engine aufgerufen, wenn ein Benutzer das [Microsoft. PowerShell. Commands. getitemcommand](/dotnet/api/Microsoft.PowerShell.Commands.getitemcommand) -Cmdlet für Ihren Anbieter aufruft.</span><span class="sxs-lookup"><span data-stu-id="4f14b-122">The [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) is called by the PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.GetItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.getitemcommand) cmdlet on your provider.</span></span> <span data-ttu-id="4f14b-123">Die-Methode gibt das Element am angegebenen Pfad zurück.</span><span class="sxs-lookup"><span data-stu-id="4f14b-123">The method returns the item at the specified path.</span></span> <span data-ttu-id="4f14b-124">Im Beispiel Access Database überprüft die-Methode, ob es sich bei dem Element um das Laufwerk selbst, eine Tabelle in der Datenbank oder eine Zeile in der Datenbank handelt.</span><span class="sxs-lookup"><span data-stu-id="4f14b-124">In the Access database example, the method checks whether the item is the drive itself, a table in the database, or a row in the database.</span></span> <span data-ttu-id="4f14b-125">Die-Methode sendet das Element an das PowerShell-Modul, indem Sie die [System. Management. Automation. Provider. cmdletprovider. Write teitemabject \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4f14b-125">The method sends the item to the PowerShell engine by calling the [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) method.</span></span>

```csharp
protected override void GetItem(string path)
      {
          // check if the path represented is a drive
          if (PathIsDrive(path))
          {
              WriteItemObject(this.PSDriveInfo, path, true);
              return;
          }// if (PathIsDrive...

           // Get table name and row information from the path and do
           // necessary actions
           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type == PathType.Table)
           {
               DatabaseTableInfo table = GetTable(tableName);
               WriteItemObject(table, path, true);
           }
           else if (type == PathType.Row)
           {
               DatabaseRowInfo row = GetRow(tableName, rowNumber);
               WriteItemObject(row, path, false);
           }
           else
           {
               ThrowTerminatingInvalidPathException(path);
           }

       }
```

### <a name="implementing-setitem"></a><span data-ttu-id="4f14b-126">Implementieren von "System Item"</span><span class="sxs-lookup"><span data-stu-id="4f14b-126">Implementing SetItem</span></span>

<span data-ttu-id="4f14b-127">Die [System. Management. Automation. Provider. itemcmdletprovider. SetItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) -Methode wird von den PowerShell-Engine-aufrufen aufgerufen, wenn ein Benutzer das [Microsoft. PowerShell. Commands. setitemcommand](/dotnet/api/Microsoft.PowerShell.Commands.setitemcommand) -Cmdlet aufruft.</span><span class="sxs-lookup"><span data-stu-id="4f14b-127">The [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) method is called by the PowerShell engine calls when a user calls the [Microsoft.PowerShell.Commands.SetItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.setitemcommand) cmdlet.</span></span> <span data-ttu-id="4f14b-128">Er legt den Wert des Elements im angegebenen Pfad fest.</span><span class="sxs-lookup"><span data-stu-id="4f14b-128">It sets the value of the item at the specified path.</span></span>

<span data-ttu-id="4f14b-129">Im Beispiel der Access-Datenbank ist es sinnvoll, den Wert eines Elements nur dann festzulegen, wenn das Element eine Zeile ist. Daher löst die Methode [NotSupportedException](/dotnet/api/system.notsupportedexception?view=netframework-4.8) aus, wenn das Element keine Zeile ist.</span><span class="sxs-lookup"><span data-stu-id="4f14b-129">In the Access database example, it makes sense to set the value of an item only if that item is a row, so the method throws [NotSupportedException](/dotnet/api/system.notsupportedexception?view=netframework-4.8) when the item is not a row.</span></span>

```csharp
protected override void SetItem(string path, object values)
       {
           // Get type, table name and row number from the path specified
           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type != PathType.Row)
           {
               WriteError(new ErrorRecord(new NotSupportedException(
                     "SetNotSupported"), "",
                  ErrorCategory.InvalidOperation, path));

               return;
           }

           // Get in-memory representation of table
           OdbcDataAdapter da = GetAdapterForTable(tableName);

           if (da == null)
           {
               return;
           }
           DataSet ds = GetDataSetForTable(da, tableName);
           DataTable table = GetDataTable(ds, tableName);

           if (rowNumber >= table.Rows.Count)
           {
               // The specified row number has to be available. If not
               // NewItem has to be used to add a new row
               throw new ArgumentException("Row specified is not available");
           } // if (rowNum...

           string[] colValues = (values as string).Split(',');

           // set the specified row
           DataRow row = table.Rows[rowNumber];

           for (int i = 0; i < colValues.Length; i++)
           {
               row[i] = colValues[i];
           }

           // Update the table
           if (ShouldProcess(path, "SetItem"))
           {
               da.Update(ds, tableName);
           }

       }
```

### <a name="implementing-itemexists"></a><span data-ttu-id="4f14b-130">Implementieren von itemexists</span><span class="sxs-lookup"><span data-stu-id="4f14b-130">Implementing ItemExists</span></span>

<span data-ttu-id="4f14b-131">Die [System. Management. Automation. Provider. itemcmdletprovider. itemexists \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) -Methode wird von der PowerShell-Engine aufgerufen, wenn ein Benutzer das [Microsoft. PowerShell. Commands. testpathcommand](/dotnet/api/Microsoft.PowerShell.Commands.Testpathcommand) -Cmdlet aufruft.</span><span class="sxs-lookup"><span data-stu-id="4f14b-131">The [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) method is called by the PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.TestPathCommand](/dotnet/api/Microsoft.PowerShell.Commands.Testpathcommand) cmdlet.</span></span> <span data-ttu-id="4f14b-132">Die-Methode bestimmt, ob ein Element am angegebenen Pfad vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4f14b-132">The method determines whether there is an item at the specified path.</span></span> <span data-ttu-id="4f14b-133">Wenn das Element vorhanden ist, übergibt die Methode es durch Aufrufen von [System. Management. Automation. Provider. cmdletprovider. Write](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject)Element Item \* an das PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="4f14b-133">If the item does exist, the method passes it back to the PowerShell engine by calling [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject).</span></span>

```csharp
protected override bool ItemExists(string path)
       {
           // check if the path represented is a drive
           if (PathIsDrive(path))
           {
               return true;
           }

           // Obtain type, table name and row number from path
           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           DatabaseTableInfo table = GetTable(tableName);

           if (type == PathType.Table)
           {
               // if specified path represents a table then DatabaseTableInfo
               // object for the same should exist
               if (table != null)
               {
                   return true;
               }
           }
           else if (type == PathType.Row)
           {
               // if specified path represents a row then DatabaseTableInfo should
               // exist for the table and then specified row number must be within
               // the maximum row count in the table
               if (table != null && rowNumber < table.RowCount)
               {
                   return true;
               }
           }

           return false;

       }
```

### <a name="implementing-isvalidpath"></a><span data-ttu-id="4f14b-134">Implementieren von IsValidPath</span><span class="sxs-lookup"><span data-stu-id="4f14b-134">Implementing IsValidPath</span></span>

<span data-ttu-id="4f14b-135">Die [System. Management. Automation. Provider. itemcmdletprovider. IsValidPath \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) -Methode überprüft, ob der angegebene Pfad für den aktuellen Anbieter syntaktisch gültig ist.</span><span class="sxs-lookup"><span data-stu-id="4f14b-135">The [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) method checks whether the specified path is syntactically valid for the current provider.</span></span> <span data-ttu-id="4f14b-136">Es wird nicht überprüft, ob ein Element im Pfad vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4f14b-136">It does not check whether an item exists at the path.</span></span>

```csharp
protected override bool IsValidPath(string path)
       {
           bool result = true;

           // check if the path is null or empty
           if (String.IsNullOrEmpty(path))
           {
               result = false;
           }

           // convert all separators in the path to a uniform one
           path = NormalizePath(path);

           // split the path into individual chunks
           string[] pathChunks = path.Split(pathSeparator.ToCharArray());

           foreach (string pathChunk in pathChunks)
           {
               if (pathChunk.Length == 0)
               {
                   result = false;
               }
           }
           return result;
       }
```

## <a name="next-steps"></a><span data-ttu-id="4f14b-137">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4f14b-137">Next steps</span></span>

<span data-ttu-id="4f14b-138">Ein typischer Real-World-Anbieter ist in der Lage, Elemente zu unterstützen, die andere Elemente enthalten, und Elemente innerhalb des Laufwerks von einem Pfad zu einem anderen zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="4f14b-138">A typical real-world provider is capable of supporting items that contain other items, and of moving items from one path to another within the drive.</span></span> <span data-ttu-id="4f14b-139">Ein Beispiel für einen Anbieter, der Container unterstützt, finden Sie unter [Schreiben eines Container Anbieters](./writing-a-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="4f14b-139">For an example of a provider that supports containers, see [Writing a container provider](./writing-a-container-provider.md).</span></span> <span data-ttu-id="4f14b-140">Ein Beispiel für einen Anbieter, der das Verschieben von Elementen unterstützt, finden Sie unter [Schreiben eines navigationsanbieters](./writing-a-navigation-provider.md).</span><span class="sxs-lookup"><span data-stu-id="4f14b-140">For an example of a provider that supports moving items, see [Writing a navigation provider](./writing-a-navigation-provider.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4f14b-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f14b-141">See Also</span></span>

[<span data-ttu-id="4f14b-142">Schreiben eines Container Anbieters</span><span class="sxs-lookup"><span data-stu-id="4f14b-142">Writing a container provider</span></span>](./writing-a-container-provider.md)

[<span data-ttu-id="4f14b-143">Schreiben eines navigationsanbieters</span><span class="sxs-lookup"><span data-stu-id="4f14b-143">Writing a navigation provider</span></span>](./writing-a-navigation-provider.md)

[<span data-ttu-id="4f14b-144">Windows PowerShell-Anbieter (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="4f14b-144">Windows PowerShell Provider Overview</span></span>](./windows-powershell-provider-overview.md)