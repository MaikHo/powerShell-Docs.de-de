---
ms.date: 11/06/2018
contributor: JKeithB
keywords: gallery,powershell,cmdlet,psgallery,psget
title: Arbeiten mit lokalen PSRepositories
ms.openlocfilehash: 94824ea584c097838b24c6f2cd02407b6147a781
ms.sourcegitcommit: 91786b03704fbd2d185f674df0bc67faddfb6288
ms.translationtype: MTE95
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2018
ms.locfileid: "51619209"
---
# <a name="working-with-local-powershellget-repositories"></a><span data-ttu-id="6cab6-103">Arbeiten mit lokalen PowerShellGet-Repositorys</span><span class="sxs-lookup"><span data-stu-id="6cab6-103">Working with local PowerShellGet Repositories</span></span>

<span data-ttu-id="6cab6-104">Die PowerShellGet-Modul unterstützt Repositorys als PowerShell-Katalog.</span><span class="sxs-lookup"><span data-stu-id="6cab6-104">The PowerShellGet module support repositories other than the PowerShell Gallery.</span></span>
<span data-ttu-id="6cab6-105">Diese Cmdlets ermöglichen die folgenden Szenarien:</span><span class="sxs-lookup"><span data-stu-id="6cab6-105">These cmdlets enable the following scenarios:</span></span>

- <span data-ttu-id="6cab6-106">Einen vertrauenswürdige, bereits überprüften Satz von PowerShell-Module für die Verwendung in Ihrer Umgebung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6cab6-106">Support a trusted, pre-validated set of PowerShell modules for use in your environment</span></span>
- <span data-ttu-id="6cab6-107">Testen einer CI/CD-Pipeline, in dem PowerShell-Module oder Skripts erstellt.</span><span class="sxs-lookup"><span data-stu-id="6cab6-107">Testing a CI/CD pipeline that builds PowerShell modules or scripts</span></span>
- <span data-ttu-id="6cab6-108">Übermitteln Sie PowerShell-Skripts und Module auf Systeme, die auf das Internet zugreifen können nicht</span><span class="sxs-lookup"><span data-stu-id="6cab6-108">Deliver PowerShell scripts and modules to systems that can't access the internet</span></span>

<span data-ttu-id="6cab6-109">Dieser Artikel beschreibt, wie Sie ein lokales Repository mit PowerShell einrichten.</span><span class="sxs-lookup"><span data-stu-id="6cab6-109">This article describes how to set up a local PowerShell repository.</span></span> <span data-ttu-id="6cab6-110">Der Artikel befasst sich auch die [OfflinePowerShellGetDeploy][] aus dem PowerShell-Katalog verfügbaren Modul.</span><span class="sxs-lookup"><span data-stu-id="6cab6-110">The article also covers the [OfflinePowerShellGetDeploy][] module available from the PowerShell Gallery.</span></span> <span data-ttu-id="6cab6-111">Dieses Modul enthält Cmdlets, um die neueste Version von PowerShellGet in das lokale Repository zu installieren.</span><span class="sxs-lookup"><span data-stu-id="6cab6-111">This module contains cmdlets to install the latest version of PowerShellGet into your local repository.</span></span>

## <a name="local-repository-types"></a><span data-ttu-id="6cab6-112">Lokales Repository-Typen</span><span class="sxs-lookup"><span data-stu-id="6cab6-112">Local repository types</span></span>

<span data-ttu-id="6cab6-113">Es gibt zwei Möglichkeiten zum Erstellen einer lokalen PSRepository: NuGet-Server oder eine Dateifreigabe.</span><span class="sxs-lookup"><span data-stu-id="6cab6-113">There are two ways to create a local PSRepository: NuGet server or file share.</span></span> <span data-ttu-id="6cab6-114">Jeder Typ verfügt über vor- und Nachteile:</span><span class="sxs-lookup"><span data-stu-id="6cab6-114">Each type has advantages and disadvantages:</span></span>

<span data-ttu-id="6cab6-115">NuGet-Server</span><span class="sxs-lookup"><span data-stu-id="6cab6-115">NuGet Server</span></span>

| <span data-ttu-id="6cab6-116">Vorteile</span><span class="sxs-lookup"><span data-stu-id="6cab6-116">Advantages</span></span>| <span data-ttu-id="6cab6-117">Nachteile</span><span class="sxs-lookup"><span data-stu-id="6cab6-117">Disadvantages</span></span> |
| --- | --- |
| <span data-ttu-id="6cab6-118">Eng imitiert im PowerShell-Katalog-Funktion</span><span class="sxs-lookup"><span data-stu-id="6cab6-118">Closely mimics PowerShellGallery functionality</span></span> | <span data-ttu-id="6cab6-119">App mit mehreren Ebenen ist erforderlich, Vorgänge, die Planung und support</span><span class="sxs-lookup"><span data-stu-id="6cab6-119">Multi-tier app requires operations planning & support</span></span> |
| <span data-ttu-id="6cab6-120">NuGet ist in Visual Studio, andere Tools integriert.</span><span class="sxs-lookup"><span data-stu-id="6cab6-120">NuGet integrates with Visual Studio, other tools</span></span> | <span data-ttu-id="6cab6-121">Authentifizierungsmodell und NuGet-Kontenverwaltung, die erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="6cab6-121">Authentication model and NuGet accounts management needed</span></span> |
| <span data-ttu-id="6cab6-122">NuGet unterstützt Metadaten in `.Nupkg` Pakete</span><span class="sxs-lookup"><span data-stu-id="6cab6-122">NuGet supports metadata in `.Nupkg` packages</span></span> | <span data-ttu-id="6cab6-123">Veröffentlichen muss der API-Schlüssel Verwaltung & Wartung</span><span class="sxs-lookup"><span data-stu-id="6cab6-123">Publishing requires API Key management & maintenance</span></span> |
| <span data-ttu-id="6cab6-124">Bietet Suche, Paket-Verwaltung, usw. an.</span><span class="sxs-lookup"><span data-stu-id="6cab6-124">Provides search, package administration, etc.</span></span> | |

<span data-ttu-id="6cab6-125">Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="6cab6-125">File Share</span></span>

| <span data-ttu-id="6cab6-126">Vorteile</span><span class="sxs-lookup"><span data-stu-id="6cab6-126">Advantages</span></span>| <span data-ttu-id="6cab6-127">Nachteile</span><span class="sxs-lookup"><span data-stu-id="6cab6-127">Disadvantages</span></span> |
| --- | --- |
| <span data-ttu-id="6cab6-128">Einfach zu richten, Sichern und verwalten</span><span class="sxs-lookup"><span data-stu-id="6cab6-128">Easy to set up, back up, and maintain</span></span> | <span data-ttu-id="6cab6-129">Metadaten von PowerShellGet verwendet nicht verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="6cab6-129">Metadata used by PowerShellGet isn't available</span></span> |
| <span data-ttu-id="6cab6-130">Einfache Sicherheitsmodell - Benutzerberechtigungen für die Freigabe</span><span class="sxs-lookup"><span data-stu-id="6cab6-130">Simple security model - user permissions on the share</span></span> | <span data-ttu-id="6cab6-131">Keine Benutzeroberfläche, über die einfache Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="6cab6-131">No UI beyond basic file share</span></span> |
| <span data-ttu-id="6cab6-132">Keine Einschränkungen, wie z. B. das Ersetzen von vorhandener Elementen</span><span class="sxs-lookup"><span data-stu-id="6cab6-132">No constraints such as replacing existing items</span></span> | <span data-ttu-id="6cab6-133">Eingeschränkte Sicherheit und updates, die keine Aufzeichnung</span><span class="sxs-lookup"><span data-stu-id="6cab6-133">Limited security and no recording of who updates what</span></span> |

<span data-ttu-id="6cab6-134">PowerShellGet kann mit entweder "Typ" und "unterstützt das Suchen von Versionen und Installation der Abhängigkeit.</span><span class="sxs-lookup"><span data-stu-id="6cab6-134">PowerShellGet works with either type and supports locating versions and dependency installation.</span></span>
<span data-ttu-id="6cab6-135">Einige Funktionen, die für den PowerShell-Katalog funktioniert sind jedoch nicht verfügbar für die Basis-NuGet-Server oder Dateifreigaben.</span><span class="sxs-lookup"><span data-stu-id="6cab6-135">However, some features that work for the PowerShell Gallery aren't available for base NuGet servers or file shares.</span></span>

- <span data-ttu-id="6cab6-136">Alles, was ist ein Paket - keine Differenzierung von Skripts, Module, DSC-Ressourcen oder Funktionen der Rolle.</span><span class="sxs-lookup"><span data-stu-id="6cab6-136">Everything is a package - no differentiation of scripts, modules, DSC resources, or role capabilities.</span></span>
- <span data-ttu-id="6cab6-137">Dateiserver für die Freigabe nicht auf Metadaten von Paketen, einschließlich Tags angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6cab6-137">File share servers can't see package metadata, including tags.</span></span>

## <a name="creating-a-local-repository"></a><span data-ttu-id="6cab6-138">Erstellen eines lokalen Repositorys</span><span class="sxs-lookup"><span data-stu-id="6cab6-138">Creating a local repository</span></span>

<span data-ttu-id="6cab6-139">Im folgende Artikel sind die Schritte zum Einrichten eines eigenen NuGet-Servers aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6cab6-139">The following article lists the steps for setting up your own NuGet Server.</span></span>

- <span data-ttu-id="6cab6-140">["NuGet.Server"][]</span><span class="sxs-lookup"><span data-stu-id="6cab6-140">[NuGet.Server][]</span></span>

<span data-ttu-id="6cab6-141">Führen Sie die Schritte bis zum Zeitpunkt des Hinzufügens von Paketen aus.</span><span class="sxs-lookup"><span data-stu-id="6cab6-141">Follow the steps up to the point of adding packages.</span></span> <span data-ttu-id="6cab6-142">Die Schritte zum [Veröffentlichen eines Pakets](#publishing-to-a-local-repository) werden weiter unten in diesem Artikel behandelt.</span><span class="sxs-lookup"><span data-stu-id="6cab6-142">The steps for [publishing a package](#publishing-to-a-local-repository) are covered later in this article.</span></span>

<span data-ttu-id="6cab6-143">Ein Repository mit Datei-Freigabe stellen Sie sicher, dass Ihre Benutzer über Berechtigungen zum Zugriff auf die Dateifreigabe verfügen.</span><span class="sxs-lookup"><span data-stu-id="6cab6-143">For a file share-based repository, make sure that your users have permissions to access the file share.</span></span>

## <a name="registering-a-local-repository"></a><span data-ttu-id="6cab6-144">Ein lokales Repository registrieren</span><span class="sxs-lookup"><span data-stu-id="6cab6-144">Registering a local repository</span></span>

<span data-ttu-id="6cab6-145">Bevor Sie ein Repository verwendet werden kann, er muss registriert werden mithilfe der `Register-PSRepository` Befehl.</span><span class="sxs-lookup"><span data-stu-id="6cab6-145">Before a repository can be used, it must be registered using the `Register-PSRepository` command.</span></span>
<span data-ttu-id="6cab6-146">In den folgenden Beispielen die **InstallationPolicy** nastaven NA hodnotu *vertrauenswürdige*, unter der Annahme, dass Sie Ihr eigenes Repository vertrauen.</span><span class="sxs-lookup"><span data-stu-id="6cab6-146">In the examples below, the **InstallationPolicy** is set to *Trusted*, on the assumption that you trust your own repository.</span></span>

```powershell
# Register a NuGet-based server
Register-PSRepository -Name LocalPSRepo -SourceLocation http://MyLocalNuget/Api/V2/ -ScriptSourceLocation http://MyLocalNuget/Api/V2 -InstallationPolicy Trusted

# Register a file share on my local machine
Register-PSRepository -Name LocalPSRepo -SourceLocation '\\localhost\PSRepoLocal\' -ScriptSourceLocation '\\localhost\PSRepoLocal\' -InstallationPolicy Trusted
```

<span data-ttu-id="6cab6-147">Notieren Sie sich den Unterschied zwischen die beiden Befehle wie behandeln **ScriptSourceLocation**.</span><span class="sxs-lookup"><span data-stu-id="6cab6-147">Take note of the difference between how the two commands handle **ScriptSourceLocation**.</span></span> <span data-ttu-id="6cab6-148">Für eine Datei-Freigabe-basierten Repositorys die die **SourceLocation** und **ScriptSourceLocation** müssen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6cab6-148">For a file share-based repositories, the **SourceLocation** and **ScriptSourceLocation** must match.</span></span> <span data-ttu-id="6cab6-149">Ein Repository webbasierte, sie müssen unterschiedlich sein, also in diesem Beispiel wird eine nachfolgende "/" wird hinzugefügt, um die **SourceLocation**.</span><span class="sxs-lookup"><span data-stu-id="6cab6-149">For a web-based repository, they must be different, so in this example a trailing "/" is added to the **SourceLocation**.</span></span>

<span data-ttu-id="6cab6-150">Wenn Sie die neu erstellte PSRepository das standardrepository sein möchten, müssen Sie alle anderen PSRepositories Registrierung aufheben.</span><span class="sxs-lookup"><span data-stu-id="6cab6-150">If you want the newly created PSRepository to be the default repository, you must unregister all other PSRepositories.</span></span> <span data-ttu-id="6cab6-151">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6cab6-151">For example:</span></span>

```powershell
Unregister-PSRepository -Name PSGallery
```

> [!NOTE]
> <span data-ttu-id="6cab6-152">Der Name des Repositorys "PSGallery" ist für die Verwendung von PowerShell-Katalog reserviert.</span><span class="sxs-lookup"><span data-stu-id="6cab6-152">The repository name 'PSGallery' is reserved for use by the PowerShell Gallery.</span></span> <span data-ttu-id="6cab6-153">Sie können die PSGallery Registrierung aufheben, aber Sie können den Namen "PSGallery" für alle anderen Repository nicht wiederverwenden.</span><span class="sxs-lookup"><span data-stu-id="6cab6-153">You can unregister PSGallery, but you cannot reuse the name PSGallery for any other repository.</span></span>

<span data-ttu-id="6cab6-154">Wenn Sie die PSGallery wiederherstellen müssen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6cab6-154">If you need to restore the PSGallery, run the following command:</span></span>

```powershell
Register-PSRepository -Default
```

## <a name="publishing-to-a-local-repository"></a><span data-ttu-id="6cab6-155">Veröffentlichen in ein lokales repository</span><span class="sxs-lookup"><span data-stu-id="6cab6-155">Publishing to a local repository</span></span>

<span data-ttu-id="6cab6-156">Nachdem Sie "lokale psrepository" registriert haben, können Sie in Ihrer lokalen PSRepository | MSDN veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6cab6-156">Once you've registered the local PSRepository, you can publish to your local PSRepository.</span></span> <span data-ttu-id="6cab6-157">Es gibt zwei Hauptszenarien veröffentlichen: Veröffentlichen Ihr eigenes Modul und veröffentlichen ein Modul aus der PSGallery.</span><span class="sxs-lookup"><span data-stu-id="6cab6-157">There are two main publishing scenarios: publishing your own module and publishing a module from the PSGallery.</span></span>

### <a name="publishing-a-module-you-authored"></a><span data-ttu-id="6cab6-158">Die Veröffentlichung eines Moduls, die Sie erstellt</span><span class="sxs-lookup"><span data-stu-id="6cab6-158">Publishing a module you authored</span></span>

<span data-ttu-id="6cab6-159">Verwendung `Publish-Module` und `Publish-Script` zu Ihrem Modul in Ihrer lokalen PSRepository genauso wie Sie für den PowerShell-Katalog veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6cab6-159">Use `Publish-Module` and `Publish-Script` to publish your module to your local PSRepository the same way you do for the PowerShell Gallery.</span></span>

- <span data-ttu-id="6cab6-160">Geben Sie den Speicherort für Ihren code</span><span class="sxs-lookup"><span data-stu-id="6cab6-160">Specify the location for your code</span></span>
- <span data-ttu-id="6cab6-161">Geben Sie einen API-Schlüssel</span><span class="sxs-lookup"><span data-stu-id="6cab6-161">Supply an API key</span></span>
- <span data-ttu-id="6cab6-162">Geben Sie den Namen des Repositorys.</span><span class="sxs-lookup"><span data-stu-id="6cab6-162">Specify the repository name.</span></span> <span data-ttu-id="6cab6-163">Beispiel: `-PSRepository LocalPSRepo`.</span><span class="sxs-lookup"><span data-stu-id="6cab6-163">For example, `-PSRepository LocalPSRepo`</span></span>

> [!NOTE]
> <span data-ttu-id="6cab6-164">Sie müssen ein Konto in der NuGet-Server erstellen und dann melden Sie sich beim Generieren und speichern Sie den API-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="6cab6-164">You must create an account in the NuGet server, then sign in to generate and save the API key.</span></span>
> <span data-ttu-id="6cab6-165">Verwenden Sie eine beliebige nicht leere Zeichenfolge für eine Dateifreigabe für den NuGet API-Schlüssel-Wert.</span><span class="sxs-lookup"><span data-stu-id="6cab6-165">For a file share, use any non-blank string for the NuGetApiKey value.</span></span>

<span data-ttu-id="6cab6-166">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="6cab6-166">Examples:</span></span>

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'

# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

> [!IMPORTANT]
> <span data-ttu-id="6cab6-167">Um die Sicherheit zu gewährleisten, sollte API-Schlüssel nicht in Skripts hartcodiert sein.</span><span class="sxs-lookup"><span data-stu-id="6cab6-167">To ensure security, API keys should not be hard-coded in scripts.</span></span> <span data-ttu-id="6cab6-168">Verwenden Sie eine sichere schlüsselverwaltung-System.</span><span class="sxs-lookup"><span data-stu-id="6cab6-168">Use a secure key management system.</span></span>

### <a name="publishing-a-module-from-the-psgallery"></a><span data-ttu-id="6cab6-169">Die Veröffentlichung eines Moduls aus dem PSGallery</span><span class="sxs-lookup"><span data-stu-id="6cab6-169">Publishing a module from the PSGallery</span></span>

<span data-ttu-id="6cab6-170">Um ein Modul aus der PSGallery auf Ihrem lokalen PSRepository zu veröffentlichen, können Sie das Cmdlet "Save-Package".</span><span class="sxs-lookup"><span data-stu-id="6cab6-170">To publish a module from the PSGallery to your local PSRepository, you can use the 'Save-Package' cmdlet.</span></span>

- <span data-ttu-id="6cab6-171">Geben Sie den Namen des Pakets</span><span class="sxs-lookup"><span data-stu-id="6cab6-171">Specify the Name of the Package</span></span>
- <span data-ttu-id="6cab6-172">Geben Sie "NuGet" als Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="6cab6-172">Specify 'NuGet' as the Provider</span></span>
- <span data-ttu-id="6cab6-173">Geben Sie den PSGallery-Speicherort als die Quelle)https://www.powershellgallery.com/api/v2)</span><span class="sxs-lookup"><span data-stu-id="6cab6-173">Specify the PSGallery location as the source (https://www.powershellgallery.com/api/v2)</span></span>
- <span data-ttu-id="6cab6-174">Geben Sie den Pfad zu Ihrem lokalen Repository</span><span class="sxs-lookup"><span data-stu-id="6cab6-174">Specify the path to your local Repository</span></span>

<span data-ttu-id="6cab6-175">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6cab6-175">Example:</span></span>

```powershell
# Publish from the PSGallery to your local Repository
Save-Package -Name 'PackageName' -Provider Nuget -Source https://www.powershellgallery.com/api/v2 -Path '\\localhost\PSRepoLocal\'
```

<span data-ttu-id="6cab6-176">Wenn Ihre lokale PSRepository webbasierte ist, erfordert es einen zusätzlichen Schritt, der nuget.exe zum Veröffentlichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="6cab6-176">If your local PSRepository is web-based, it requires an additional step that uses nuget.exe to publish.</span></span>

<span data-ttu-id="6cab6-177">Finden Sie in der Dokumentation für die Verwendung von [nuget.exe][].</span><span class="sxs-lookup"><span data-stu-id="6cab6-177">See the documentation for using [nuget.exe][].</span></span>

## <a name="installing-powershellget-on-a-disconnected-system"></a><span data-ttu-id="6cab6-178">Installieren von PowerShellGet auf einem nicht verbundenen system</span><span class="sxs-lookup"><span data-stu-id="6cab6-178">Installing PowerShellGet on a disconnected system</span></span>

<span data-ttu-id="6cab6-179">Bereitstellen von PowerShellGet ist nur schwer in Umgebungen, die Systeme verfügt, die dem Internet verbunden sein müssen.</span><span class="sxs-lookup"><span data-stu-id="6cab6-179">Deploying PowerShellGet is difficult in environments that require systems to be disconnected from the internet.</span></span> <span data-ttu-id="6cab6-180">PowerShellGet kann einen bootstrap-Prozess, der die neueste Version beim ersten installiert, die sie verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6cab6-180">PowerShellGet has a bootstrap process that installs the latest version the first time it's used.</span></span> <span data-ttu-id="6cab6-181">Das OfflinePowerShellGetDeploy-Modul im PowerShell-Katalog bietet Cmdlets, die diese bootstrap-Prozess zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6cab6-181">The OfflinePowerShellGetDeploy module in the PowerShell Gallery provides cmdlets that support this bootstrap process.</span></span>

<span data-ttu-id="6cab6-182">Um eine offline-Bereitstellung zu starten, müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="6cab6-182">To bootstrap an offline deployment, you need to:</span></span>

- <span data-ttu-id="6cab6-183">Herunterladen Sie und installieren Sie das System Ihre Internetverbindung OfflinePowerShellGetDeploy und Ihren getrennten Systemen</span><span class="sxs-lookup"><span data-stu-id="6cab6-183">Download and install the OfflinePowerShellGetDeploy your internet-connected system and your disconnected systems</span></span>
- <span data-ttu-id="6cab6-184">Herunterladen von PowerShellGet und seine Abhängigkeiten auf dem Internet verbundenen System mithilfe der `Save-PowerShellGetForOffline` Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6cab6-184">Download PowerShellGet and its dependencies on the internet-connected system using the `Save-PowerShellGetForOffline` cmdlet</span></span>
- <span data-ttu-id="6cab6-185">Kopieren von PowerShellGet und seine Abhängigkeiten aus dem Internet verbundenen System in der nicht verbundenen system</span><span class="sxs-lookup"><span data-stu-id="6cab6-185">Copy PowerShellGet and its dependencies from the internet-connected system to the disconnected system</span></span>
- <span data-ttu-id="6cab6-186">Verwenden der `Install-PowerShellGetOffline` auf dem getrennten System PowerShellGet und ihre Abhängigkeiten in den entsprechenden Ordnern platzieren</span><span class="sxs-lookup"><span data-stu-id="6cab6-186">Use the `Install-PowerShellGetOffline` on the disconnected system to place PowerShellGet and its dependencies into the proper folders</span></span>

<span data-ttu-id="6cab6-187">Die folgenden Befehle verwenden `Save-PowerShellGetForOffline` alle Komponenten in einen Ordner zu versetzen. `f:\OfflinePowerShellGet`</span><span class="sxs-lookup"><span data-stu-id="6cab6-187">The following commands use `Save-PowerShellGetForOffline` to put all the components into a folder `f:\OfflinePowerShellGet`</span></span>

```powershell
# Requires -RunAsAdministrator
#Download the OfflinePowerShellGetDeploy to a location that can be accessed
# by both the connected and disconnected systems.
Save-Module -Name OfflinePowerShellGetDeploy -Path 'F:\' -Repository PSGallery
Import-Module F:\OfflinePowerShellGetDeploy

# Put PowerShellGet somewhere locally
Save-PowerShellGetForOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

<span data-ttu-id="6cab6-188">Sie müssen an diesem Punkt, den Inhalt der `F:\OfflinePowerShellGet` Ihrer nicht verbundenen Systeme zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="6cab6-188">At this point, you must make the contents of `F:\OfflinePowerShellGet` available to your disconnected systems.</span></span> <span data-ttu-id="6cab6-189">Führen Sie die `Install-PowerShellGetOffline` Cmdlet, um die powershellget-Modul auf dem getrennten System zu installieren.</span><span class="sxs-lookup"><span data-stu-id="6cab6-189">Run the `Install-PowerShellGetOffline` cmdlet to install PowerShellGet on the disconnected system.</span></span>

> [!NOTE]
> <span data-ttu-id="6cab6-190">Es ist wichtig, dass der PowerShellGet nicht in der PowerShell-Sitzung vor dem Ausführen dieser Befehle auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6cab6-190">It is important that you do not run PowerShellGet in the PowerShell session before running these commands.</span></span> <span data-ttu-id="6cab6-191">PowerShellGet in die Sitzung geladen wurden, werden nicht die Komponenten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6cab6-191">Once PowerShellGet is loaded into the session, the components cannot be updated.</span></span> <span data-ttu-id="6cab6-192">Wenn Sie versehentlich PowerShellGet starten, beenden und starten Sie PowerShell neu.</span><span class="sxs-lookup"><span data-stu-id="6cab6-192">If you do start PowerShellGet by mistake, exit and restart PowerShell.</span></span>

```powershell
Import-Module F:\OfflinePowerShellGetDeploy

Install-PowerShellGetOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

<span data-ttu-id="6cab6-193">Nach dem Ausführen dieser Befehle können Sie sich, PowerShellGet auf Ihrem lokalen Repository zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6cab6-193">After running these commands, you are ready to publish PowerShellGet to your local repository.</span></span>

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'F:\OfflinePowershellGet' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'

# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'F:\OfflinePowerShellGet' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

> [!IMPORTANT]
> <span data-ttu-id="6cab6-194">Um die Sicherheit zu gewährleisten, sollte API-Schlüssel nicht in Skripts hartcodiert sein.</span><span class="sxs-lookup"><span data-stu-id="6cab6-194">To ensure security, API keys should not be hard-coded in scripts.</span></span> <span data-ttu-id="6cab6-195">Verwenden Sie eine sichere schlüsselverwaltung-System.</span><span class="sxs-lookup"><span data-stu-id="6cab6-195">Use a secure key management system.</span></span>

<!-- external links -->
[OfflinePowerShellGetDeploy]: https://www.powershellgallery.com/packages/OfflinePowerShellGetDeploy/0.1.1
["NuGet.Server"]: /nuget/hosting-packages/nuget-server
[Nuget.Server]: /nuget/hosting-packages/nuget-server
[NuGet.exe]: /nuget/tools/nuget-exe-cli-reference
[nuget.exe]: /nuget/tools/nuget-exe-cli-reference