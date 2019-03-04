---
title: Laden und Exportieren von Formatierungsdaten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a48de31-7961-4b0e-b58b-93466e38370b
caps.latest.revision: 6
ms.openlocfilehash: 08c64d4094d8ba6c551b454887331666f0694f11
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860626"
---
# <a name="loading-and-exporting-formatting-data"></a><span data-ttu-id="74a4d-102">Laden und Exportieren von Formatierungsdaten</span><span class="sxs-lookup"><span data-stu-id="74a4d-102">Loading and Exporting Formatting Data</span></span>

<span data-ttu-id="74a4d-103">Nachdem Sie Ihre Formatierungsdatei erstellt haben, müssen Sie die Daten im Format der Sitzung zu aktualisieren, indem Sie Ihre Dateien in der aktuellen Sitzung zu laden.</span><span class="sxs-lookup"><span data-stu-id="74a4d-103">Once you have created your formatting file, you need to update the format data of the session by loading your files into the current session.</span></span> <span data-ttu-id="74a4d-104">(Die Formatierungsdateien, die von Windows PowerShell bereitgestellt, werden von-Snap-ins, die registriert werden, wenn die aktuelle Sitzung geöffnet wird geladen.) Nachdem die Daten im Format der aktuellen Sitzung aktualisiert wurde, verwendet Windows PowerShell die Daten zum Anzeigen der .NET Objekte, die in den geladenen Formatierungsdateien definierten Sichten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="74a4d-104">(The formatting files provided by Windows PowerShell are loaded by snap-ins that are registered when the current session is opened.) Once the format data of the current session is updated, Windows PowerShell uses that data to display the .NET objects associated with the views defined in the loaded formatting files.</span></span> <span data-ttu-id="74a4d-105">Es gibt keine Beschränkung der Anzahl der Formatierungsdateien, die Sie in der aktuellen Sitzung laden können.</span><span class="sxs-lookup"><span data-stu-id="74a4d-105">There is no limit to the number of formatting files that you can load into the current session.</span></span> <span data-ttu-id="74a4d-106">Zusätzlich zum Aktualisieren der Formatierungsdaten, können Sie die Formatdaten in der aktuellen Sitzung an eine Formatierungsdatei exportieren.</span><span class="sxs-lookup"><span data-stu-id="74a4d-106">In addition to updating the formatting data, you can export the format data in the current session back to a formatting file.</span></span>

## <a name="loading-format-data"></a><span data-ttu-id="74a4d-107">Laden von Daten im format</span><span class="sxs-lookup"><span data-stu-id="74a4d-107">Loading format data</span></span>

<span data-ttu-id="74a4d-108">Die aktuelle Sitzung mithilfe der folgenden Methoden können Formatierungsdateien geladen werden:</span><span class="sxs-lookup"><span data-stu-id="74a4d-108">Formatting files can be loaded into the current session using the following methods:</span></span>

- <span data-ttu-id="74a4d-109">Sie können die Formatierungsdatei in der aktuellen Sitzung über die Befehlszeile importieren.</span><span class="sxs-lookup"><span data-stu-id="74a4d-109">You can import the formatting file into the current session from the command line.</span></span> <span data-ttu-id="74a4d-110">Verwenden der [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) Cmdlet wie im folgenden Verfahren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74a4d-110">Use the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet as described in the following procedure.</span></span>
- <span data-ttu-id="74a4d-111">Sie können die Formatierungsdatei in der aktuellen Sitzung über die Befehlszeile importieren.</span><span class="sxs-lookup"><span data-stu-id="74a4d-111">You can import the formatting file into the current session from the command line.</span></span> <span data-ttu-id="74a4d-112">Verwenden der [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) Cmdlet wie im folgenden Verfahren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74a4d-112">Use the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet as described in the following procedure.</span></span>

- <span data-ttu-id="74a4d-113">Sie können ein modulmanifest erstellen, die die Formatierung Datei verweist.</span><span class="sxs-lookup"><span data-stu-id="74a4d-113">You can create a module manifest that references your formatting file.</span></span> <span data-ttu-id="74a4d-114">Module können Sie die Formatierungsdateien für die Verteilung verpacken.</span><span class="sxs-lookup"><span data-stu-id="74a4d-114">Modules allow you to package you formatting files for distribution.</span></span> <span data-ttu-id="74a4d-115">Verwenden der [New-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) Cmdlet, um das Manifest zu erstellen und die [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) Cmdlet, um das Modul in die aktuelle Sitzung zu laden.</span><span class="sxs-lookup"><span data-stu-id="74a4d-115">Use the [New-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) cmdlet to create the manifest, and the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet to load the module into the current session.</span></span> <span data-ttu-id="74a4d-116">Weitere Informationen zu Modulen finden Sie unter [Schreiben eines Windows PowerShell-Moduls](../module/writing-a-windows-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="74a4d-116">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>
- <span data-ttu-id="74a4d-117">Sie können ein modulmanifest erstellen, die die Formatierung Datei verweist.</span><span class="sxs-lookup"><span data-stu-id="74a4d-117">You can create a module manifest that references your formatting file.</span></span> <span data-ttu-id="74a4d-118">Module können Sie die Formatierungsdateien für die Verteilung verpacken.</span><span class="sxs-lookup"><span data-stu-id="74a4d-118">Modules allow you to package you formatting files for distribution.</span></span> <span data-ttu-id="74a4d-119">Verwenden der [New-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) Cmdlet, um das Manifest zu erstellen und die [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) Cmdlet, um das Modul in die aktuelle Sitzung zu laden.</span><span class="sxs-lookup"><span data-stu-id="74a4d-119">Use the [New-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) cmdlet to create the manifest, and the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet to load the module into the current session.</span></span> <span data-ttu-id="74a4d-120">Weitere Informationen zu Modulen finden Sie unter [Schreiben eines Windows PowerShell-Moduls](../module/writing-a-windows-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="74a4d-120">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

- <span data-ttu-id="74a4d-121">Sie können ein Snap-in erstellen, die die Formatierung Datei verweist.</span><span class="sxs-lookup"><span data-stu-id="74a4d-121">You can create a snap-in that references your formatting file.</span></span> <span data-ttu-id="74a4d-122">Verwenden der [System.Management.Automation.Pssnapin.Formats](/dotnet/api/System.Management.Automation.PSSnapIn.Formats) auf Ihre Formatierungsdateien verweisen.</span><span class="sxs-lookup"><span data-stu-id="74a4d-122">Use the [System.Management.Automation.Pssnapin.Formats](/dotnet/api/System.Management.Automation.PSSnapIn.Formats) to reference your formatting files.</span></span> <span data-ttu-id="74a4d-123">Es wird dringend empfohlen, Module, die Paket-Cmdlets und zugeordnete Formatierung und Typen-Dateien für die Verteilung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="74a4d-123">It is strongly encouraged to use modules to package cmdlets, and any associated formatting and types files for distribution.</span></span> <span data-ttu-id="74a4d-124">Weitere Informationen zu Modulen finden Sie unter [Schreiben eines Windows PowerShell-Moduls](../module/writing-a-windows-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="74a4d-124">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

- <span data-ttu-id="74a4d-125">Wenn Sie Befehle programmgesteuert aufrufen, können Sie einen Eintrag mit Formatierung Datei auf den anfänglichen Sitzungsstatus, der den Runspace hinzufügen, in dem die Befehle ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="74a4d-125">If you are invoking commands programmatically, you can add a formatting file entry to the initial session state of the runspace where the commands are run.</span></span> <span data-ttu-id="74a4d-126">Weitere Informationen zu .NET verwendet, um die Formatierungsdatei hinzuzufügen, finden Sie unter den [System.Management.Automation.Runspaces.Sessionstateformatentry? Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Runspaces.SessionStateFormatEntry) Klasse.</span><span class="sxs-lookup"><span data-stu-id="74a4d-126">For more information about .NET type used to add the formatting file, see the [System.Management.Automation.Runspaces.Sessionstateformatentry?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Runspaces.SessionStateFormatEntry) class.</span></span>

<span data-ttu-id="74a4d-127">Wenn eine Formatierungsdatei geladen wird, wird einer internen Liste hinzugefügt, dass Windows PowerShell verwendet, um zu bestimmen, welche Ansicht in die bei der Anzeige von Objekten in der Befehlszeile verwendet.</span><span class="sxs-lookup"><span data-stu-id="74a4d-127">When a formatting file is loaded, it is added to an internal list that Windows PowerShell uses to determine which view to use when displaying objects at the command line.</span></span> <span data-ttu-id="74a4d-128">Können Sie Ihre Formatierungsdatei an den Anfang der Liste voranstellen, oder Sie fügen sie am Ende der Liste.</span><span class="sxs-lookup"><span data-stu-id="74a4d-128">You can prepend your formatting file to the beginning of the list, or you can append it to the end of the list.</span></span> <span data-ttu-id="74a4d-129">Zu wissen, wo Ihre Formatierungsdatei zu dieser Liste hinzugefügt wird ist wichtig, wenn Sie Formatierungsdatei, die eine Ansicht für ein Objekt, die eine vorhandene Ansicht, die definiert laden definiert, wie z. B. Wenn Sie ändern, wie ein Objekt, das durch ein Windows PowerShell Core Cmdlet zurückgegeben wird wird möchten  angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74a4d-129">Knowing where your formatting file is added to this list is important if you are loading formatting file that defines a view for an object that has an existing view defined, such as when you want to change how an object that is returned by a Windows PowerShell core cmdlet is displayed.</span></span> <span data-ttu-id="74a4d-130">Wenn Sie eine Formatierungsdatei, die die einzige Ansicht für ein Objekt definiert laden, können Sie eine der oben beschriebenen Methoden.</span><span class="sxs-lookup"><span data-stu-id="74a4d-130">If you are loading a formatting file that defines the only view for an object, you can use any of the methods described previously.</span></span>  <span data-ttu-id="74a4d-131">Wenn Sie eine Formatierungsdatei, die einer anderen Ansicht für ein Objekt definiert laden, müssen Sie verwenden die [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) Cmdlet, und stellen Sie die Datei auf den Anfang der Liste.</span><span class="sxs-lookup"><span data-stu-id="74a4d-131">If you are loading a formatting file that defines another view for an object, you must use the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet and prepend your file to the beginning of the list.</span></span>
<span data-ttu-id="74a4d-132">Wenn eine Formatierungsdatei geladen wird, wird einer internen Liste hinzugefügt, dass Windows PowerShell verwendet, um zu bestimmen, welche Ansicht in die bei der Anzeige von Objekten in der Befehlszeile verwendet.</span><span class="sxs-lookup"><span data-stu-id="74a4d-132">When a formatting file is loaded, it is added to an internal list that Windows PowerShell uses to determine which view to use when displaying objects at the command line.</span></span> <span data-ttu-id="74a4d-133">Können Sie Ihre Formatierungsdatei an den Anfang der Liste voranstellen, oder Sie fügen sie am Ende der Liste.</span><span class="sxs-lookup"><span data-stu-id="74a4d-133">You can prepend your formatting file to the beginning of the list, or you can append it to the end of the list.</span></span> <span data-ttu-id="74a4d-134">Zu wissen, wo Ihre Formatierungsdatei zu dieser Liste hinzugefügt wird ist wichtig, wenn Sie Formatierungsdatei, die eine Ansicht für ein Objekt, die eine vorhandene Ansicht, die definiert laden definiert, wie z. B. Wenn Sie ändern, wie ein Objekt, das durch ein Windows PowerShell Core Cmdlet zurückgegeben wird wird möchten  angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74a4d-134">Knowing where your formatting file is added to this list is important if you are loading formatting file that defines a view for an object that has an existing view defined, such as when you want to change how an object that is returned by a Windows PowerShell core cmdlet is displayed.</span></span> <span data-ttu-id="74a4d-135">Wenn Sie eine Formatierungsdatei, die die einzige Ansicht für ein Objekt definiert laden, können Sie eine der oben beschriebenen Methoden.</span><span class="sxs-lookup"><span data-stu-id="74a4d-135">If you are loading a formatting file that defines the only view for an object, you can use any of the methods described previously.</span></span>  <span data-ttu-id="74a4d-136">Wenn Sie eine Formatierungsdatei, die einer anderen Ansicht für ein Objekt definiert laden, müssen Sie verwenden die [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) Cmdlet, und stellen Sie die Datei auf den Anfang der Liste.</span><span class="sxs-lookup"><span data-stu-id="74a4d-136">If you are loading a formatting file that defines another view for an object, you must use the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet and prepend your file to the beginning of the list.</span></span>

## <a name="storing-your-formatting-file"></a><span data-ttu-id="74a4d-137">Speichern Ihre Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="74a4d-137">Storing Your Formatting File</span></span>

<span data-ttu-id="74a4d-138">Besteht keine Notwendigkeit, in dem Ihre Formatierungsdateien auf dem Datenträger gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="74a4d-138">There is no requirement for where your formatting files are stored on disk.</span></span> <span data-ttu-id="74a4d-139">Jedoch wird dringend empfohlen, dass Sie sie in den folgenden Ordner speichern: `user\documents\windowspowershell\`</span><span class="sxs-lookup"><span data-stu-id="74a4d-139">However, it is strongly suggested that you store them in the following folder: `user\documents\windowspowershell\`</span></span>

#### <a name="loading-a-format-file-using-import-formatdata"></a><span data-ttu-id="74a4d-140">Laden eine Formatdatei mit Import-FormatData</span><span class="sxs-lookup"><span data-stu-id="74a4d-140">Loading a format file using Import-FormatData</span></span>

1. <span data-ttu-id="74a4d-141">Store Ihre Formatierungsdatei auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="74a4d-141">Store your formatting file to disk.</span></span>

2. <span data-ttu-id="74a4d-142">Führen Sie die [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) Cmdlet mit einem der folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="74a4d-142">Run the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet using one of the following commands.</span></span>
2. <span data-ttu-id="74a4d-143">Führen Sie die [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) Cmdlet mit einem der folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="74a4d-143">Run the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet using one of the following commands.</span></span>

   <span data-ttu-id="74a4d-144">Verwenden Sie diesen Befehl, um Ihre Formatierung hinzufügen Datei am Anfang der Liste.</span><span class="sxs-lookup"><span data-stu-id="74a4d-144">To add your formatting file to the front of the list use this command.</span></span> <span data-ttu-id="74a4d-145">Verwenden Sie diesen Befehl aus, wenn Sie ändern möchten, wie ein Objekt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="74a4d-145">Use this command if you are changing how an object is displayed.</span></span>

   ```powershell
   Update-FormatData -PrependPath PathToFormattingFile
   ```

   <span data-ttu-id="74a4d-146">Verwenden Sie diesen Befehl, um Ihre Formatierung hinzufügen Datei am Ende der Liste.</span><span class="sxs-lookup"><span data-stu-id="74a4d-146">To add your formatting file to the end of the list use this command.</span></span>

   ```powershell
   Update-FormatData -AppendPath PathToFormattingFile
   ```

   <span data-ttu-id="74a4d-147">Nachdem Sie eine Datei mit hinzugefügt, haben die [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) -Cmdlet, Sie können nicht entfernen Sie die Datei aus der Liste während die Sitzung geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="74a4d-147">Once you have added a file using the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet, you cannot remove the file from the list while the session is open.</span></span> <span data-ttu-id="74a4d-148">Schließen Sie die Sitzung, um die Formatierungsdatei aus der Liste zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="74a4d-148">You must close the session to remove the formatting file from the list.</span></span>
   <span data-ttu-id="74a4d-149">Nachdem Sie eine Datei mit hinzugefügt, haben die [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) -Cmdlet, Sie können nicht entfernen Sie die Datei aus der Liste während die Sitzung geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="74a4d-149">Once you have added a file using the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet, you cannot remove the file from the list while the session is open.</span></span> <span data-ttu-id="74a4d-150">Schließen Sie die Sitzung, um die Formatierungsdatei aus der Liste zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="74a4d-150">You must close the session to remove the formatting file from the list.</span></span>

## <a name="exporting-format-data"></a><span data-ttu-id="74a4d-151">Exportieren von Daten im format</span><span class="sxs-lookup"><span data-stu-id="74a4d-151">Exporting format data</span></span>

<span data-ttu-id="74a4d-152">Abschnittstext hier einfügen.</span><span class="sxs-lookup"><span data-stu-id="74a4d-152">Insert section body here.</span></span>