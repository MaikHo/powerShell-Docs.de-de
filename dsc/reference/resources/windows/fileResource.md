---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: DSC-Ressource „File“
ms.openlocfilehash: b5bc2c305b8cfccbd044274811df631264a24279
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "55679297"
---
# <a name="dsc-file-resource"></a><span data-ttu-id="a7be5-103">DSC-Ressource „File“</span><span class="sxs-lookup"><span data-stu-id="a7be5-103">DSC File Resource</span></span>

> <span data-ttu-id="a7be5-104">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="a7be5-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="a7be5-105">Die Ressource „File“ in Windows PowerShell DSC bietet einen Mechanismus zum Verwalten von Dateien und Verzeichnissen auf einem Zielknoten.</span><span class="sxs-lookup"><span data-stu-id="a7be5-105">The File resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage files and folders on the target node.</span></span> <span data-ttu-id="a7be5-106">Die **DestinationPath** und **SourcePath** müssen vom Ziel Knoten zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a7be5-106">The **DestinationPath** and **SourcePath** must both be accessible by the target Node.</span></span>

## <a name="syntax"></a><span data-ttu-id="a7be5-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7be5-107">Syntax</span></span>

```
File [string] #ResourceName
{
    DestinationPath = [string]
    [ Attributes = [string[]] { Archive | Hidden | ReadOnly | System }]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Contents = [string] ]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present } ]
    [ Force = [bool] ]
    [ Recurse = [bool] ]
    [ DependsOn = [string[]] ]
    [ SourcePath = [string] ]
    [ Type = [string] { Directory | File } ]
    [ MatchSource = [bool] ]
}
```

## <a name="properties"></a><span data-ttu-id="a7be5-108">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a7be5-108">Properties</span></span>

|<span data-ttu-id="a7be5-109">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="a7be5-109">Property</span></span>       |<span data-ttu-id="a7be5-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7be5-110">Description</span></span>                                                                   |<span data-ttu-id="a7be5-111">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="a7be5-111">Required</span></span>|<span data-ttu-id="a7be5-112">Standardwert</span><span class="sxs-lookup"><span data-stu-id="a7be5-112">Default</span></span>|
|---------------|------------------------------------------------------------------------------|--------|-------|
|<span data-ttu-id="a7be5-113">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="a7be5-113">DestinationPath</span></span>|<span data-ttu-id="a7be5-114">Der Speicherort, auf dem Zielknoten Sie sicherstellen möchten, ist `Present` oder `Absent`.</span><span class="sxs-lookup"><span data-stu-id="a7be5-114">The location, on the target node, you want to ensure is `Present` or `Absent`.</span></span>|<span data-ttu-id="a7be5-115">Ja</span><span class="sxs-lookup"><span data-stu-id="a7be5-115">Yes</span></span>|<span data-ttu-id="a7be5-116">Nein</span><span class="sxs-lookup"><span data-stu-id="a7be5-116">No</span></span>|
|<span data-ttu-id="a7be5-117">Attributes</span><span class="sxs-lookup"><span data-stu-id="a7be5-117">Attributes</span></span>     |<span data-ttu-id="a7be5-118">Der gewünschte Zustand der Attribute für die Zieldatei oder das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a7be5-118">The desired state of the attributes for the targeted file or directory.</span></span> <span data-ttu-id="a7be5-119">Gültige Werte sind **Archiv**, **Hidden**, **ReadOnly**, und **System**.</span><span class="sxs-lookup"><span data-stu-id="a7be5-119">Valid values are **Archive**, **Hidden**, **ReadOnly**, and **System**.</span></span>|<span data-ttu-id="a7be5-120">Nein</span><span class="sxs-lookup"><span data-stu-id="a7be5-120">No</span></span>|<span data-ttu-id="a7be5-121">Keine</span><span class="sxs-lookup"><span data-stu-id="a7be5-121">None</span></span>|
|<span data-ttu-id="a7be5-122">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7be5-122">Checksum</span></span>      |<span data-ttu-id="a7be5-123">Der Checksum-Typ, mit denen Sie bestimmen, ob zwei Dateien identisch sind.</span><span class="sxs-lookup"><span data-stu-id="a7be5-123">The checksum type to use when determining whether two files are the same.</span></span> <span data-ttu-id="a7be5-124">Gültige Werte sind: SHA-1, SHA-256, SHA-512, CreatedDate, ModifiedDate.</span><span class="sxs-lookup"><span data-stu-id="a7be5-124">Valid values include: SHA-1, SHA-256, SHA-512, createdDate, modifiedDate.</span></span>|<span data-ttu-id="a7be5-125">Nein</span><span class="sxs-lookup"><span data-stu-id="a7be5-125">No</span></span>|<span data-ttu-id="a7be5-126">Nur die Datei oder Verzeichnis Namen verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="a7be5-126">Only the file or directory name is compared.</span></span>|
|<span data-ttu-id="a7be5-127">Contents</span><span class="sxs-lookup"><span data-stu-id="a7be5-127">Contents</span></span>       |<span data-ttu-id="a7be5-128">Nur gültig, bei der Verwendung mit `File` Typ.</span><span class="sxs-lookup"><span data-stu-id="a7be5-128">Only valid when used with `File` type.</span></span> <span data-ttu-id="a7be5-129">Gibt an, den Inhalt, stellen Sie sicher sind `Present` oder `Absent` aus der entsprechenden Datei.</span><span class="sxs-lookup"><span data-stu-id="a7be5-129">Indicates the contents to Ensure are `Present` or `Absent` from the targeted file.</span></span> |<span data-ttu-id="a7be5-130">Nein</span><span class="sxs-lookup"><span data-stu-id="a7be5-130">No</span></span>|<span data-ttu-id="a7be5-131">Keine</span><span class="sxs-lookup"><span data-stu-id="a7be5-131">None</span></span>|
|<span data-ttu-id="a7be5-132">Credential</span><span class="sxs-lookup"><span data-stu-id="a7be5-132">Credential</span></span>     |<span data-ttu-id="a7be5-133">Die Anmeldeinformationen, die erforderlich, um den Zugriff auf Ressourcen, wie z.B. Quelldateien sind.</span><span class="sxs-lookup"><span data-stu-id="a7be5-133">The credentials that are required to access resources, such as source files.</span></span>|<span data-ttu-id="a7be5-134">Nein</span><span class="sxs-lookup"><span data-stu-id="a7be5-134">No</span></span>|<span data-ttu-id="a7be5-135">Computerkonto für des Zielknotens.</span><span class="sxs-lookup"><span data-stu-id="a7be5-135">The target node's Computer Account.</span></span> <span data-ttu-id="a7be5-136">(*Siehe Hinweis*)</span><span class="sxs-lookup"><span data-stu-id="a7be5-136">(*see note*)</span></span>|
|<span data-ttu-id="a7be5-137">Ensure</span><span class="sxs-lookup"><span data-stu-id="a7be5-137">Ensure</span></span>         |<span data-ttu-id="a7be5-138">Der gewünschte Zustand der Zieldatei oder des Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="a7be5-138">The desired state of the target file or directory.</span></span> |<span data-ttu-id="a7be5-139">Nein</span><span class="sxs-lookup"><span data-stu-id="a7be5-139">No</span></span>|<span data-ttu-id="a7be5-140">**Vorhanden**</span><span class="sxs-lookup"><span data-stu-id="a7be5-140">**Present**</span></span>|
|<span data-ttu-id="a7be5-141">Force</span><span class="sxs-lookup"><span data-stu-id="a7be5-141">Force</span></span>          |<span data-ttu-id="a7be5-142">Überschreibt die Access-Vorgänge, die zu einem Fehler (z. B. das Überschreiben einer Datei oder das Löschen eines Verzeichnisses, das nicht leer ist) führen würde.</span><span class="sxs-lookup"><span data-stu-id="a7be5-142">Overrides access operations that would result in an error (such as overwriting a file or deleting a directory that is not empty).</span></span>|<span data-ttu-id="a7be5-143">Nein</span><span class="sxs-lookup"><span data-stu-id="a7be5-143">No</span></span>|`$false`|
|<span data-ttu-id="a7be5-144">Recurse</span><span class="sxs-lookup"><span data-stu-id="a7be5-144">Recurse</span></span>        |<span data-ttu-id="a7be5-145">Nur gültig, bei der Verwendung mit `Directory` Typ.</span><span class="sxs-lookup"><span data-stu-id="a7be5-145">Only valid when used with `Directory` type.</span></span> <span data-ttu-id="a7be5-146">Führt die Status-Vorgang rekursiv für alle Unterverzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="a7be5-146">Performs the state operation recursively to all subdirectories.</span></span>|<span data-ttu-id="a7be5-147">Nein</span><span class="sxs-lookup"><span data-stu-id="a7be5-147">No</span></span>|`$false`|
|<span data-ttu-id="a7be5-148">DependsOn</span><span class="sxs-lookup"><span data-stu-id="a7be5-148">DependsOn</span></span>      |<span data-ttu-id="a7be5-149">Legt eine Abhängigkeit auf der angegebenen Ressourcen fest.</span><span class="sxs-lookup"><span data-stu-id="a7be5-149">Sets a dependency on specified resource(s).</span></span> <span data-ttu-id="a7be5-150">Diese Ressource wird nur nach erfolgreicher Ausführung aller abhängigen Ressourcen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a7be5-150">This resource will only execute after successful execution of any dependent resources.</span></span> <span data-ttu-id="a7be5-151">Sie können angeben, dass abhängige Ressourcen, die mit der Syntax `"[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="a7be5-151">You can specify dependent resources using the syntax `"[ResourceType]ResourceName"`.</span></span> <span data-ttu-id="a7be5-152">Finden Sie unter [About_DependsOn](../../../configurations/resource-depends-on.md)</span><span class="sxs-lookup"><span data-stu-id="a7be5-152">See [about_DependsOn](../../../configurations/resource-depends-on.md)</span></span>|<span data-ttu-id="a7be5-153">Nein</span><span class="sxs-lookup"><span data-stu-id="a7be5-153">No</span></span>|<span data-ttu-id="a7be5-154">Keine</span><span class="sxs-lookup"><span data-stu-id="a7be5-154">None</span></span>|
|<span data-ttu-id="a7be5-155">SourcePath</span><span class="sxs-lookup"><span data-stu-id="a7be5-155">SourcePath</span></span>     |<span data-ttu-id="a7be5-156">Der Pfad, von dem die Datei oder Ordner kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a7be5-156">The path from which to copy the file or folder resource.</span></span>|<span data-ttu-id="a7be5-157">Nein</span><span class="sxs-lookup"><span data-stu-id="a7be5-157">No</span></span>|<span data-ttu-id="a7be5-158">Keine</span><span class="sxs-lookup"><span data-stu-id="a7be5-158">None</span></span>|
|<span data-ttu-id="a7be5-159">Type</span><span class="sxs-lookup"><span data-stu-id="a7be5-159">Type</span></span>           |<span data-ttu-id="a7be5-160">Der Typ der zu konfigurierende Ressource.</span><span class="sxs-lookup"><span data-stu-id="a7be5-160">The type of resource being configured.</span></span> <span data-ttu-id="a7be5-161">Gültige Werte sind `Directory` und `File`.</span><span class="sxs-lookup"><span data-stu-id="a7be5-161">Valid values are `Directory` and `File`.</span></span>|<span data-ttu-id="a7be5-162">Nein</span><span class="sxs-lookup"><span data-stu-id="a7be5-162">No</span></span>|`File`|
|<span data-ttu-id="a7be5-163">MatchSource</span><span class="sxs-lookup"><span data-stu-id="a7be5-163">MatchSource</span></span>    |<span data-ttu-id="a7be5-164">Bestimmt, ob die Ressource für neue Dateien, die zum Quellverzeichnis hinzugefügt werden, nachdem die erste Kopie überwachen soll.</span><span class="sxs-lookup"><span data-stu-id="a7be5-164">Determines if the resource should monitor for new files added to the source directory after the initial copy.</span></span> <span data-ttu-id="a7be5-165">Der Wert `$true` gibt an, dass nach Erstellen der ersten Kopie aller neuen Quelldateien in das Ziel kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a7be5-165">A value of `$true` indicates that, after the initial copy, any new source files should be copied to the destination.</span></span> <span data-ttu-id="a7be5-166">Wenn auf festgelegt `$False`, die Ressource speichert den Inhalt des Quellverzeichnisses und ignoriert alle Dateien hinzugefügt, nachdem die erste Kopie.</span><span class="sxs-lookup"><span data-stu-id="a7be5-166">If set to `$False`, the resource caches the contents of the source directory and ignores any files added after the initial copy.</span></span>|<span data-ttu-id="a7be5-167">Nein</span><span class="sxs-lookup"><span data-stu-id="a7be5-167">No</span></span>|`$false`|

> [!WARNING]
> <span data-ttu-id="a7be5-168">Wenn Sie einen Wert für nicht angeben `Credential` oder `PSRunAsCredential` (PS V.5), die Ressource wird mithilfe des Computerkontos des Zielknotens auf die `SourcePath`.</span><span class="sxs-lookup"><span data-stu-id="a7be5-168">If you do not specify a value for `Credential` or `PSRunAsCredential` (PS V.5), the resource will use the computer account of the target node to access the `SourcePath`.</span></span>  <span data-ttu-id="a7be5-169">Wenn die `SourcePath` ist eine UNC-Freigabe, könnte dies zu einem Fehler "Zugriff verweigert".</span><span class="sxs-lookup"><span data-stu-id="a7be5-169">When the `SourcePath` is a UNC share, this could result in an "Access Denied" error.</span></span> <span data-ttu-id="a7be5-170">Vergewissern Sie sich Ihre Berechtigungen werden entsprechend festgelegt wird, oder verwenden Sie die `Credential` oder `PSRunAsCredential` Eigenschaften für das Konto angeben, die verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a7be5-170">Please ensure your permissions are set accordingly, or use the `Credential` or `PSRunAsCredential` properties to specify the account that should be used.</span></span>

## <a name="present-vs-absent"></a><span data-ttu-id="a7be5-171">Stellen Sie die Visual Studio. Nicht vorhanden</span><span class="sxs-lookup"><span data-stu-id="a7be5-171">Present vs. Absent</span></span>

<span data-ttu-id="a7be5-172">Jede DSC-Ressource führt verschiedene Vorgänge, die auf Grundlage des Werts, die Sie, für angeben die `Ensure` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a7be5-172">Each DSC resource performs different operations based on the value you specify for the `Ensure` property.</span></span> <span data-ttu-id="a7be5-173">Die Werte, die Sie angeben, für die oben aufgeführten Eigenschaften bestimmt den Status-Vorgang ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a7be5-173">The values you specify for the above properties determines the state operation performed.</span></span>

### <a name="existence"></a><span data-ttu-id="a7be5-174">Vorhandensein</span><span class="sxs-lookup"><span data-stu-id="a7be5-174">Existence</span></span>

<span data-ttu-id="a7be5-175">Wenn Sie nur angeben, ein `DestinationPath`, die Ressource wird sichergestellt, dass der Pfad vorhanden ist (`Present`) oder ist nicht vorhanden (`Absent`).</span><span class="sxs-lookup"><span data-stu-id="a7be5-175">When you only specify a `DestinationPath`, the resource ensures that the path exists (`Present`) or does not exist (`Absent`).</span></span>

### <a name="copy-operations"></a><span data-ttu-id="a7be5-176">Kopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="a7be5-176">Copy Operations</span></span>

<span data-ttu-id="a7be5-177">Beim Angeben von eine `SourcePath` und ein `DestinationPath` mit einer `Type` Wert **Directory**, das Ressourcenverzeichnis für die Quelle von Kopien in den Zielpfad.</span><span class="sxs-lookup"><span data-stu-id="a7be5-177">When you specify a `SourcePath` and a `DestinationPath` with a `Type` value of **Directory**, the resource copies source directory to the destination path.</span></span> <span data-ttu-id="a7be5-178">Die Eigenschaften `Recurse`, `Force`, und `MatchSource` ändern Sie den Typ des Kopiervorgangs ausgeführt, während er sich `Credential` bestimmt, welches Konto Sie verwenden, um das Quellverzeichnis zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a7be5-178">The properties `Recurse`, `Force`, and `MatchSource` change the type of copy operation performed, while `Credential` determines which account to use to access the source directory.</span></span>

### <a name="limitations"></a><span data-ttu-id="a7be5-179">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a7be5-179">Limitations</span></span>

<span data-ttu-id="a7be5-180">Wenn Sie den Wert angegeben `ReadOnly` für die `Attributes` Eigenschaft zusammen mit einer `DestinationPath`, `Ensure = "Present"` würde den angegebene Pfad erstellen während `Contents` würde Legen Sie den Inhalt der Datei.</span><span class="sxs-lookup"><span data-stu-id="a7be5-180">If you specified a value of `ReadOnly` for the `Attributes` property alongside a `DestinationPath`, `Ensure = "Present"` would create the path specified, while `Contents` would set the contents of the file.</span></span>  <span data-ttu-id="a7be5-181">Ein `Absent` Zustands ignorieren würde die `Attributes` Eigenschaft vollständig, und entfernen Sie alle Dateien im angegebenen Pfad.</span><span class="sxs-lookup"><span data-stu-id="a7be5-181">An `Absent` state operation would ignore the `Attributes` property entirely, and remove any file at the specified path.</span></span>

## <a name="example"></a><span data-ttu-id="a7be5-182">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7be5-182">Example</span></span>

<span data-ttu-id="a7be5-183">Das folgende Beispiel kopiert ein Verzeichnis und seinen Unterverzeichnissen von einem pullserver auf einen Zielknoten, die mit der Ressource "File".</span><span class="sxs-lookup"><span data-stu-id="a7be5-183">The following example copies a directory and its subdirectories from a pull server to a target node using the File Resource.</span></span> <span data-ttu-id="a7be5-184">Wenn der Vorgang erfolgreich ist, schreibt die Ressource "Log" eine bestätigungsmeldung angezeigt, in das Ereignisprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="a7be5-184">If the operation succeeds, the Log resource writes a confirmation message to the event log.</span></span>

<span data-ttu-id="a7be5-185">Das Quellverzeichnis ist ein UNC-Pfad (`\\PullServer\DemoSource`) aus dem Pull-Server freigegeben.</span><span class="sxs-lookup"><span data-stu-id="a7be5-185">The source directory is a UNC path (`\\PullServer\DemoSource`) shared from the Pull Server.</span></span> <span data-ttu-id="a7be5-186">Die `Recurse` Eigenschaft wird sichergestellt, dass auch alle Unterverzeichnisse kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="a7be5-186">The `Recurse` property ensures that all subdirectories are copied as well.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7be5-187">Der LCM auf dem Ziel Knoten führt standardmäßig im Kontext des lokalen Systemkontos aus.</span><span class="sxs-lookup"><span data-stu-id="a7be5-187">The LCM on the target Node executes in the context of the local system account by default.</span></span> <span data-ttu-id="a7be5-188">Gewähren von Zugriff auf die **SourcePath**, legen Sie Berechtigungen für das Computerkonto des Zielknotens.</span><span class="sxs-lookup"><span data-stu-id="a7be5-188">To grant access to the **SourcePath**, give the target Node's computer account appropriate permissions.</span></span> <span data-ttu-id="a7be5-189">Die **Anmeldeinformationen** und **"psdscrunascredential"** (v5) Ändern der Kontext der LCM verwendet den Zugriff auf die **SourcePath**.</span><span class="sxs-lookup"><span data-stu-id="a7be5-189">The **Credential** and **PSDSCRunAsCredential** (v5) both change the context the LCM uses to access the **SourcePath**.</span></span> <span data-ttu-id="a7be5-190">Müssen Sie weiterhin Zugriff auf das Konto zu gewähren, die verwendet werden, für den Zugriff auf die **SourcePath**.</span><span class="sxs-lookup"><span data-stu-id="a7be5-190">You still need to grant access to the account that will be used to access the **SourcePath**.</span></span>

```powershell
Configuration FileResourceDemo
{
    Node "localhost"
    {
        File DirectoryCopy
        {
            Ensure = "Present" # Ensure the directory is Present on the target node.
            Type = "Directory" # The default is File.
            Recurse = $true # Recursively copy all subdirectories.
            SourcePath = "\\PullServer\DemoSource"
            DestinationPath = "C:\Users\Public\Documents\DSCDemo\DemoDestination"
        }

        Log AfterDirectoryCopy
        {
            # The message below gets written to the Microsoft-Windows-Desired State Configuration/Analytic log
            Message = "Finished running the file resource with ID DirectoryCopy"
            DependsOn = "[File]DirectoryCopy" # Depends on successful execution of the File resource.
        }
    }
}
```

<span data-ttu-id="a7be5-191">Für die weitere Verwendung von auf **Anmeldeinformationen** in DSC finden Sie unter [als Benutzer ausführen](../../../configurations/runAsUser.md) oder [Config Anmeldeinformationen](../../../configurations/configDataCredentials.md).</span><span class="sxs-lookup"><span data-stu-id="a7be5-191">For more on using **Credentials** in DSC see [Run As User](../../../configurations/runAsUser.md) or [Config Data Credentials](../../../configurations/configDataCredentials.md).</span></span>