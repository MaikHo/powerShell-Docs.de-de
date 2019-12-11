---
ms.date: 06/12/2017
contributor: manikb
keywords: gallery,powershell,cmdlet,psget
title: Bootstrapping von NuGet
ms.openlocfilehash: 6d8f106bc3b8741203e87e4c097948a843f06d6e
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "71328431"
---
# <a name="bootstrap-the-nuget-provider-and-nugetexe"></a><span data-ttu-id="0e916-103">Bootstrapping des NuGet-Anbieters und von „NuGet.exe“</span><span class="sxs-lookup"><span data-stu-id="0e916-103">Bootstrap the NuGet provider and NuGet.exe</span></span>

<span data-ttu-id="0e916-104">„NuGet.exe“ ist im neuesten NuGet-Anbieter nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="0e916-104">NuGet.exe is not included in the latest NuGet provider.</span></span> <span data-ttu-id="0e916-105">Für die Veröffentlichung eines Moduls oder Skripts benötigt PowerShell die binäre ausführbare Datei „NuGet.exe“.</span><span class="sxs-lookup"><span data-stu-id="0e916-105">For publish operations of either a module or script, PowerShellGet requires the binary executable NuGet.exe.</span></span> <span data-ttu-id="0e916-106">Für alle weiteren Vorgänge, darunter *find*, *install*, *save* und *uninstall*, ist nur der NuGet-Anbieter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0e916-106">Only the NuGet provider is required for all other operations, including *find*, *install*, *save*, and *uninstall*.</span></span>
<span data-ttu-id="0e916-107">PowerShell umfasst Logik für ein kombiniertes Bootstrappings des NuGet-Anbieters und der Datei „NuGet.exe“ oder ein ausschließliches Bootstrapping des NuGet-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="0e916-107">PowerShellGet includes logic to handle either a combined bootstrap of the NuGet provider and NuGet.exe, or bootstrap of only the NuGet provider.</span></span> <span data-ttu-id="0e916-108">In beiden Fällen sollte nur eine einzige Aufforderungsmeldung erfolgen.</span><span class="sxs-lookup"><span data-stu-id="0e916-108">In either case, only a single prompt message should occur.</span></span> <span data-ttu-id="0e916-109">Wenn der Computer nicht mit dem Internet verbunden ist, muss der Benutzer oder Administrator eine vertrauenswürdige Instanz des NuGet-Anbieters und/oder der Datei „NuGet.exe“ auf den getrennten Computer kopieren.</span><span class="sxs-lookup"><span data-stu-id="0e916-109">If the machine is not connected to the Internet, the user or an administrator must copy a trusted instance of the NuGet provider and/or the NuGet.exe file to the disconnected machine.</span></span>

> [!NOTE]
> <span data-ttu-id="0e916-110">Ab Version 6 ist der NuGet-Anbieter in der Installation von PowerShell enthalten.</span><span class="sxs-lookup"><span data-stu-id="0e916-110">Starting with version 6, the NuGet provider is included in the installation of PowerShell.</span></span>

## <a name="resolving-error-when-the-nuget-provider-has-not-been-installed-on-a-machine-that-is-internet-connected"></a><span data-ttu-id="0e916-111">Fehlerbehebung, wenn der NuGet-Anbieter auf einem Computer ohne Internetverbindung nicht installiert ist</span><span class="sxs-lookup"><span data-stu-id="0e916-111">Resolving error when the NuGet provider has not been installed on a machine that is Internet connected</span></span>

```powershell
Find-Module -Repository PSGallery -Verbose -Name Contoso
```

```output
NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with NuGet-based repositories. The NuGet provider must be available in 'C:\Program Files\PackageManagement\ProviderAssemblies' or
'C:\Users\manikb\AppData\Local\PackageManagement\ProviderAssemblies'. You can also install the NuGet provider by running 'Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force'. Do you want PowerShellGet to install and import the NuGet provider
now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): n
Find-Module : NuGet provider is required to interact with NuGet-based repositories. Please ensure that '2.8.5.201' or newer version of NuGet provider is installed.
At line:1 char:1
+ Find-Module -Repository PSGallery -Verbose -Name Contoso
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Find-Module], InvalidOperationException
   + FullyQualifiedErrorId : CouldNotInstallNuGetProvider,Find-Module
```

```powershell
Find-Module -Repository PSGallery -Verbose -Name Contoso
```

```output
NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with NuGet-based repositories. The NuGet provider must be available in 'C:\Program Files\PackageManagement\ProviderAssemblies' or
'C:\Users\manikb\AppData\Local\PackageManagement\ProviderAssemblies'. You can also install the NuGet provider by running 'Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force'. Do you want PowerShellGet to install and import the NuGet provider
now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
VERBOSE: Installing NuGet provider.

Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Contoso                             Module     PSGallery        Contoso module
```

## <a name="resolving-error-when-the-nuget-provider-is-available-and-nugetexe-is-not-available-during-the-publish-operation-on-a-machine-that-is-internet-connected"></a><span data-ttu-id="0e916-112">Fehlerbehebung, wenn der NuGet-Anbieter zur Verfügung steht, aber „NuGet.exe“ während eines Veröffentlichungsvorgangs auf einem Computer ohne Internetverbindung nicht verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="0e916-112">Resolving error when the NuGet provider is available and NuGet.exe is not available during the publish operation on a machine that is Internet connected</span></span>

```powershell
Publish-Module -Name Contoso -Repository PSGallery -Verbose
```

```output
NuGet.exe is required to continue
PowerShellGet requires NuGet.exe to publish an item to the NuGet-based repositories. NuGet.exe must be available under one of the paths specified in PATH environment variable value. Do you want PowerShellGet to install NuGet.exe now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): N
Publish-Module : NuGet.exe is required to interact with NuGet-based repositories. Please ensure that NuGet.exe is available under one of the paths specified in PATH environment variable value.
At line:1 char:1
+ Publish-Module -Name Contoso -Repository PSGallery -Verbose
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Publish-Module], InvalidOperationException
    + FullyQualifiedErrorId : CouldNotInstallNuGetExe,Publish-Module
```

```powershell
Publish-Module -Name Contoso -Repository PSGallery -Verbose
```

```output
NuGet.exe is required to continue
PowerShellGet requires NuGet.exe to publish an item to the NuGet-based repositories. NuGet.exe must be available under one of the paths specified in PATH environment variable value. Do you want PowerShellGet to install NuGet.exe now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
VERBOSE: Installing NuGet.exe.
VERBOSE: Successfully published module 'Contoso' to the module publish location 'https://www.powershellgallery.com/api/v2/'. Please allow few minutes for 'Contoso' to show up in the search results.
```

## <a name="resolving-error-when-both-nuget-provider-and-nugetexe-are-not-available-during-the-publish-operation-on-a-machine-that-is-internet-connected"></a><span data-ttu-id="0e916-113">Fehlerbehebung, wenn sowohl der NuGet-Anbieter als auch „NuGet.exe“ während eines Veröffentlichungsvorgangs auf einem Computer ohne Internetverbindung nicht verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="0e916-113">Resolving error when both NuGet provider and NuGet.exe are not available during the publish operation on a machine that is Internet connected</span></span>

```powershell
Publish-Module -Name Contoso -Repository PSGallery -Verbose
```

```output
NuGet.exe and NuGet provider are required to continue
PowerShellGet requires NuGet.exe and NuGet provider version '2.8.5.201' or newer to interact with the NuGet-based repositories. Do you want PowerShellGet to install both NuGet.exe and NuGet provider now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): N
Publish-Module : PowerShellGet requires NuGet.exe and NuGet provider version '2.8.5.201' or newer to interact with the NuGet-based repositories. Please ensure that '2.8.5.201' or newer version of NuGet provider is installed and NuGet.exe is available under
one of the paths specified in PATH environment variable value.
At line:1 char:1
+ Publish-Module -Name Contoso -Repository PSGallery -Verbose
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Publish-Module], InvalidOperationException
    + FullyQualifiedErrorId : CouldNotInstallNuGetBinaries,Publish-Module
```

```powershell
Publish-Module -Name Contoso -Repository PSGallery -Verbose
```

```output
NuGet.exe and NuGet provider are required to continue
PowerShellGet requires NuGet.exe and NuGet provider version '2.8.5.201' or newer to interact with the NuGet-based repositories. Do you want PowerShellGet to install both NuGet.exe and NuGet provider now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
VERBOSE: Installing NuGet provider.
VERBOSE: Installing NuGet.exe.
VERBOSE: Successfully published module 'Contoso' to the module publish location 'https://www.powershellgallery.com/api/v2/'. Please allow few minutes for 'Contoso' to show up in the search results.
```

## <a name="manually-bootstrapping-the-nuget-provider-on-a-machine-that-is-not-connected-to-the-internet"></a><span data-ttu-id="0e916-114">Manuelles Bootstrapping des NuGet-Anbieters auf einem Computer ohne Internetverbindung</span><span class="sxs-lookup"><span data-stu-id="0e916-114">Manually bootstrapping the NuGet provider on a machine that is not connected to the Internet</span></span>

<span data-ttu-id="0e916-115">Die oben gezeigten Prozesse setzen voraus, dass der Computer mit dem Internet verbunden ist und dass Dateien von einem öffentlichen Speicherort heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="0e916-115">The processes demonstrated above assume the machine is connected to the Internet and can download files from a public location.</span></span> <span data-ttu-id="0e916-116">Wenn dies nicht möglich ist, kann für einen Computer nur mithilfe der oben gezeigten Prozesse ein Bootstrapping durchgeführt werden, und der Anbieter muss über einen vertrauenswürdigen Offlineprozess auf den isolierten Knoten kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="0e916-116">If that is not possible, the only option is to bootstrap a machine using the processes given above, and manually copy the provider to the isolated node through an offline trusted process.</span></span> <span data-ttu-id="0e916-117">Der gängigste Anwendungsfall für dieses Szenario ist die Verwendung eines privaten Katalogs zur Unterstützung einer isolierten Umgebung.</span><span class="sxs-lookup"><span data-stu-id="0e916-117">The most common use case for this scenario is when a private gallery is available to support an isolated environment.</span></span>

<span data-ttu-id="0e916-118">Nach der Durchführung des Prozesses für das Bootstrapping eines Computers mit Internetverbindung finden Sie Anbieterdateien in diesem Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="0e916-118">After following the process above to bootstrap an Internet connected machine, you will find provider files in the location:</span></span>

`C:\Program Files\PackageManagement\ProviderAssemblies\`

<span data-ttu-id="0e916-119">Die Ordner-/Dateistruktur des NuGet-Anbieters sieht folgendermaßen aus (die Versionsnummer weicht wahrscheinlich ab):</span><span class="sxs-lookup"><span data-stu-id="0e916-119">The folder/file structure of the NuGet provider will be (possibly with a different version number):</span></span>

```
NuGet
--2.8.5.208
----Microsoft.PackageManagement.NuGetProvider.dll
```

<span data-ttu-id="0e916-120">Kopieren Sie diese Ordner und Dateien unter Verwendung eines vertrauenswürdigen Prozesses auf den Offlinecomputer.</span><span class="sxs-lookup"><span data-stu-id="0e916-120">Copy these folders and file using a trusted process to the offline machines.</span></span>

## <a name="manually-bootstrapping-nugetexe-to-support-publish-operations-on-a-machine-that-is-not-connected-to-the-internet"></a><span data-ttu-id="0e916-121">Manuelles Bootstrapping von „NuGet.exe“ zur Unterstützung von Veröffentlichungsvorgängen auf einem Computer ohne Internetverbindung</span><span class="sxs-lookup"><span data-stu-id="0e916-121">Manually bootstrapping NuGet.exe to support publish operations on a machine that is not connected to the Internet</span></span>

<span data-ttu-id="0e916-122">Zusätzlich zum Prozess des manuellen Bootstrappings des NuGet-Anbieters ist die ausführbare Binärdatei „NuGet.exe“ erforderlich, wenn mit dem Computer unter Verwendung der Cmdlets `Publish-Module` oder `Publish-Script` Module oder Skripts in einem privaten Katalog veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0e916-122">In addition to the process to manually bootstrap the NuGet provider, if the machine will be used to publish modules or scripts to a private gallery using the `Publish-Module` or `Publish-Script` cmdlets, the NuGet.exe binary executable file will be required.</span></span>

<span data-ttu-id="0e916-123">Der gängigste Anwendungsfall für dieses Szenario ist die Verwendung eines privaten Katalogs zur Unterstützung einer isolierten Umgebung.</span><span class="sxs-lookup"><span data-stu-id="0e916-123">The most common use case for this scenario is when a private gallery is available to support an isolated environment.</span></span> <span data-ttu-id="0e916-124">Es gibt zwei Optionen zum Abrufen der Datei „NuGet.exe“.</span><span class="sxs-lookup"><span data-stu-id="0e916-124">There are two options to obtain the NuGet.exe file.</span></span>

<span data-ttu-id="0e916-125">Die erste Option besteht darin, ein Bootstrapping für einen Computer mit Internetverbindung durchzuführen und die Dateien unter Verwendung eines vertrauenswürdigen Prozesses auf die Offlinecomputer zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="0e916-125">One option is to bootstrap a machine that is Internet connected and copy the files to the offline machines using a trusted process.</span></span> <span data-ttu-id="0e916-126">Nach dem Bootstrapping des Computers mit Internetverbindung befindet sich die binäre Datei „NuGet.exe“ in einem dieser zwei Ordner:</span><span class="sxs-lookup"><span data-stu-id="0e916-126">After bootstrapping the Internet connected machine, the NuGet.exe binary will be located in one of two folders:</span></span>

<span data-ttu-id="0e916-127">Wenn die Cmdlets `Publish-Module` oder `Publish-Script` mit erhöhten Rechten (als Administrator) ausgeführt wurden:</span><span class="sxs-lookup"><span data-stu-id="0e916-127">If the `Publish-Module` or `Publish-Script` cmdlets were executed with elevated permissions (As an Administrator):</span></span>

```powershell
$env:ProgramData\Microsoft\Windows\PowerShell\PowerShellGet
```

<span data-ttu-id="0e916-128">Wenn die Cmdlets als Benutzer ohne erhöhte Rechte ausgeführt wurden:</span><span class="sxs-lookup"><span data-stu-id="0e916-128">If the cmdlets were executed as a user without elevated permissions:</span></span>

```powershell
$env:userprofile\AppData\Local\Microsoft\Windows\PowerShell\PowerShellGet\
```

<span data-ttu-id="0e916-129">Eine zweite Option besteht darin, „NuGet.exe“ von der NuGet.Org-Website herunterzuladen: [https://dist.nuget.org/index.html](https://www.nuget.org/downloads) Bei Auswahl einer NuGet-Version für Produktionscomputer müssen Sie sicherstellen, eine höhere Version als 2.8.5.208 zu verwenden und die Version zu ermitteln, die als „empfohlen“ gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="0e916-129">A second option is to download NuGet.exe from the NuGet.Org website: [https://dist.nuget.org/index.html](https://www.nuget.org/downloads) When selecting a NugGet version for production machines, make sure it is later than 2.8.5.208, and identify the version that has been labeled "recommended".</span></span> <span data-ttu-id="0e916-130">Denken Sie daran, die Datei zu entsperren, wenn sie mit einem Browser heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="0e916-130">Remember to unblock the file if it was downloaded using a browser.</span></span> <span data-ttu-id="0e916-131">Sie können die Entsperrung mit dem Cmdlet `Unblock-File` durchführen.</span><span class="sxs-lookup"><span data-stu-id="0e916-131">This can be performed by using the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="0e916-132">In beiden Fällen kann die Datei „NuGet.exe“ an einen beliebigen Speicherort unter `$env:path` kopiert werden, aber dies sind die Standardspeicherorte:</span><span class="sxs-lookup"><span data-stu-id="0e916-132">In either case, the NuGet.exe file can be copied to any location in `$env:path`, but the standard locations are:</span></span>

<span data-ttu-id="0e916-133">So machen Sie die ausführbare Datei für alle Benutzer verfügbar und ermöglichen ihnen die Verwendung der Cmdlets `Publish-Module` und `Publish-Script`:</span><span class="sxs-lookup"><span data-stu-id="0e916-133">To make the executable available so that all users can use `Publish-Module` and `Publish-Script` cmdlets:</span></span>

```powershell
$env:ProgramData\Microsoft\Windows\PowerShell\PowerShellGet
```

<span data-ttu-id="0e916-134">Um die ausführbare Datei nur für einen bestimmten Benutzer verfügbar zu machen, kopieren Sie sie nur an den Speicherort innerhalb des Profils dieses Benutzers:</span><span class="sxs-lookup"><span data-stu-id="0e916-134">To make the executable available to only a specific user, copy to the location within only that user's profile:</span></span>

```powershell
$env:userprofile\AppData\Local\Microsoft\Windows\PowerShell\PowerShellGet\
```