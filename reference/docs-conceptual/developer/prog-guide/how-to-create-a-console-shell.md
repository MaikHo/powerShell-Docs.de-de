---
title: Erstellen einer Konsolen Shell | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Make-Shell [PowerShell Programmer's Guide]
ms.assetid: 6c24dd44-a8ec-421d-ac86-90912e1a8cc6
caps.latest.revision: 5
ms.openlocfilehash: 7166881bd1403ea8c81ec2928321f6b93e3ac58d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360269"
---
# <a name="how-to-create-a-console-shell"></a><span data-ttu-id="90b6d-102">Erstellen einer Konsolenshell</span><span class="sxs-lookup"><span data-stu-id="90b6d-102">How to Create a Console Shell</span></span>

<span data-ttu-id="90b6d-103">Windows PowerShell stellt ein Make-Shell-Tool bereit, das auch als "Make-Kit" bezeichnet wird und zum Erstellen einer Konsolen Shell verwendet wird, die nicht erweiterbar ist.</span><span class="sxs-lookup"><span data-stu-id="90b6d-103">Windows PowerShell provides a Make-Shell tool, also referred to as the "make-kit", that is used to create a console shell that is not extensible.</span></span> <span data-ttu-id="90b6d-104">Mit diesem neuen Tool erstellte Shells können nicht später über ein Windows PowerShell-Snap-in erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="90b6d-104">Shells created with this new tool cannot be extended later through a Windows PowerShell snap-in.</span></span>

## <a name="syntax"></a><span data-ttu-id="90b6d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="90b6d-105">Syntax</span></span>

<span data-ttu-id="90b6d-106">Im folgenden finden Sie die Syntax, die zum Ausführen von Make-Shell aus einer Make-Datei verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="90b6d-106">Here is the syntax used to run Make-Shell from within a make-file.</span></span>

```
make-shell
  -out n.exe
  -namespace ns
  [ -lib libdirectory1[,libdirectory2,..] ]
  [ -reference ca1.dll[,ca2.dll,...] ]
  [ -formatdata fd1.format.ps1xml[,fd2.format.ps1xml,...] ]
  [ -typedata td1.type.ps1xml[,td2.type.ps1xml,...] ]
  [ -source c1.cs [,c2.cs,...] ]
  [ -authorizationmanager authorizationManagerType ]
  [ -win32icon i.ico ]
  [ -initscript p.ps1 ]
  [ -builtinscript s1.ps1[,s2.ps1,...] ]
  [ -resource resourcefile.txt ]
  [ -cscflags cscFlags ]
  [ -? | -help ]
```

## <a name="parameters"></a><span data-ttu-id="90b6d-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="90b6d-107">Parameters</span></span>

<span data-ttu-id="90b6d-108">Im folgenden finden Sie eine kurze Beschreibung der Parameter von Make-Shell.</span><span class="sxs-lookup"><span data-stu-id="90b6d-108">Here is a brief description of the parameters of Make-Shell.</span></span>

> [!CAUTION]
> <span data-ttu-id="90b6d-109">UNC-Pfade zu Assemblys werden von der Make-Shell nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="90b6d-109">UNC paths to assemblies are not supported by Make-Shell.</span></span>

|<span data-ttu-id="90b6d-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="90b6d-110">Parameter</span></span>|<span data-ttu-id="90b6d-111">Description</span><span class="sxs-lookup"><span data-stu-id="90b6d-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="90b6d-112">-Out n. exe</span><span class="sxs-lookup"><span data-stu-id="90b6d-112">-out n.exe</span></span>|<span data-ttu-id="90b6d-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="90b6d-113">Required.</span></span> <span data-ttu-id="90b6d-114">Der Name der zu erstellenden Shell.</span><span class="sxs-lookup"><span data-stu-id="90b6d-114">The name of the shell to produce.</span></span> <span data-ttu-id="90b6d-115">Der Pfad wird als Teil dieses Parameters angegeben.</span><span class="sxs-lookup"><span data-stu-id="90b6d-115">The path is specified as part of this parameter.</span></span><br /><br /> <span data-ttu-id="90b6d-116">"Make-Shell" fügt ". exe" an diesen Wert an, wenn er nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="90b6d-116">Make-shell will append ".exe" to this value if it is not specified.</span></span> <span data-ttu-id="90b6d-117">**Vorsicht:**  Erstellen Sie keine Ausgabedatei mit demselben Namen wie die DLL-Datei, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="90b6d-117">**Caution:**  Do not create an output file with the same name as the referenced .dll file.</span></span> <span data-ttu-id="90b6d-118">Wenn Sie dies versuchen, erstellt das Make-Shell-Tool eine CS-Datei mit dem gleichen Namen, die die CS-Datei mit dem Cmdlet-Quellcode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="90b6d-118">If you attempt this, the Make-Shell tool creates a .cs file with the same name, which will overwrite the .cs file that has your cmdlet source code.</span></span>|
|<span data-ttu-id="90b6d-119">-Namespace-NS</span><span class="sxs-lookup"><span data-stu-id="90b6d-119">-namespace ns</span></span>|<span data-ttu-id="90b6d-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="90b6d-120">Required.</span></span> <span data-ttu-id="90b6d-121">Der Namespace, der für die abgeleitete [System. Management. Automation. Runspaces. runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) -Klasse verwendet werden soll, die vom Make-Kit generiert und kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="90b6d-121">The namespace to use for the derived [System.Management.Automation.Runspaces.Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) class that the make-kit generates and compiles.</span></span>|
|<span data-ttu-id="90b6d-122">-lib libdirectory1 [, libdirectory2,..]</span><span class="sxs-lookup"><span data-stu-id="90b6d-122">-lib libdirectory1[,libdirectory2,..]</span></span>|<span data-ttu-id="90b6d-123">Die Verzeichnisse, die nach .NET-Assemblys durchsucht werden, einschließlich der Windows PowerShell-Assemblys, Assemblys, die vom Parameter "`reference`" angegeben werden, werden indirekt von einer anderen Assembly referenzierte Assemblys</span><span class="sxs-lookup"><span data-stu-id="90b6d-123">The directories that are searched for .NET assemblies, including the Windows PowerShell assemblies, assemblies specified by the `reference` parameter, assemblies indirectly referenced by another assembly, and the .NET system assemblies.</span></span>|
|<span data-ttu-id="90b6d-124">-Reference CA1. dll [, Ca2. dll,...]</span><span class="sxs-lookup"><span data-stu-id="90b6d-124">-reference ca1.dll[,ca2.dll,...]</span></span>|<span data-ttu-id="90b6d-125">Eine durch Trennzeichen getrennte Liste der Assemblys, die in der Shell enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="90b6d-125">A comma-separated list of the assemblies to include in the shell.</span></span> <span data-ttu-id="90b6d-126">Diese Assemblys enthalten alle Cmdlets und anbieteassemblys sowie Ressourcenassemblys, die geladen werden sollten.</span><span class="sxs-lookup"><span data-stu-id="90b6d-126">These assemblies  includes all cmdlet and provider assemblies, as well as resource assemblies that should be loaded.</span></span> <span data-ttu-id="90b6d-127">Wenn dieser Parameter nicht angegeben wird, wird eine Shell erstellt, die nur die Kern-Cmdlets und Anbieter enthält, die von Windows PowerShell bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="90b6d-127">If this parameter is not specified, then a shell is produced that contains only the core cmdlets and providers provided by Windows PowerShell.</span></span><br /><br /> <span data-ttu-id="90b6d-128">Die Assemblys können mithilfe Ihres vollständigen Pfads angegeben werden. andernfalls werden Sie nach dem durch den `lib`-Parameter angegebenen Pfad durchsucht.</span><span class="sxs-lookup"><span data-stu-id="90b6d-128">The assemblies can be specified using their full path, otherwise they will be searched for using the path specified by the `lib` parameter.</span></span>|
|<span data-ttu-id="90b6d-129">-formatdata fd1. Format. ps1xml [, FD2. Format. ps1xml,...]</span><span class="sxs-lookup"><span data-stu-id="90b6d-129">-formatdata fd1.format.ps1xml[,fd2.format.ps1xml,...]</span></span>|<span data-ttu-id="90b6d-130">Eine durch Trennzeichen getrennte Liste von Format Daten, die in der Shell enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="90b6d-130">A comma-separated list of format data to include in the shell.</span></span> <span data-ttu-id="90b6d-131">Wenn dieser Parameter nicht angegeben wird, wird eine Shell erstellt, die nur die von Windows PowerShell bereitgestellten Formatierungsdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="90b6d-131">If this parameter is not specified, then a shell is produced that contains only the format data provided by Windows PowerShell.</span></span>|
|<span data-ttu-id="90b6d-132">-typedata TD1. Type. ps1xml [, TD2. Type. ps1xml,...]</span><span class="sxs-lookup"><span data-stu-id="90b6d-132">-typedata td1.type.ps1xml[,td2.type.ps1xml,...]</span></span>|<span data-ttu-id="90b6d-133">Eine durch Trennzeichen getrennte Liste von Typdaten, die in der Shell enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="90b6d-133">A comma-separated list of type data to include in the shell.</span></span> <span data-ttu-id="90b6d-134">Wenn dieser Parameter nicht angegeben wird, wird eine Shell erstellt, die nur die Typdaten enthält, die von Windows PowerShell bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="90b6d-134">If this parameter is not specified, then a shell is produced that contains only the type data provided by Windows PowerShell.</span></span>|
|<span data-ttu-id="90b6d-135">-Quelle C1.cs [, C2.cs,...]</span><span class="sxs-lookup"><span data-stu-id="90b6d-135">-source c1.cs [,c2.cs,...]</span></span>|<span data-ttu-id="90b6d-136">Der Name einer Datei, die vom shellentwickler bereitgestellt wird und den Quellcode enthält, der zum Erstellen der Shell erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="90b6d-136">The name of a file, provided by the shell developer, that contains any source code needed to build the shell.</span></span><br /><br /> <span data-ttu-id="90b6d-137">Die Quell Code Datei kann jeden der folgenden Quell Code enthalten:</span><span class="sxs-lookup"><span data-stu-id="90b6d-137">The source code file can contain any of the following source code:</span></span><br /><br /> <span data-ttu-id="90b6d-138">: Die Autorisierungs-Manager-Implementierung, die den Standard Autorisierungs-Manager überschreibt.</span><span class="sxs-lookup"><span data-stu-id="90b6d-138">-   The Authorization manager implementation that overrides the default authorization manager.</span></span> <span data-ttu-id="90b6d-139">(Dies kann auch in eine Assembly kompiliert werden.)</span><span class="sxs-lookup"><span data-stu-id="90b6d-139">(This could also be supplied compiled into an assembly.)</span></span><br /><span data-ttu-id="90b6d-140">-Assembly-Informations Attribut Deklarationen: z. b. AssemblyCompanyAttribute, AssemblyCopyrightAttribute, AssemblyFileVersionAttribute, AssemblyInformationalVersionAttribute, AssemblyProductAttribute und AssemblyTrademarkAttribute.</span><span class="sxs-lookup"><span data-stu-id="90b6d-140">-   Assembly informational attribute declarations: such as the AssemblyCompanyAttribute, AssemblyCopyrightAttribute, AssemblyFileVersionAttribute, AssemblyInformationalVersionAttribute, AssemblyProductAttribute, and AssemblyTrademarkAttribute.</span></span>|
|<span data-ttu-id="90b6d-141">-AuthorizationManager authorizationmanagertype</span><span class="sxs-lookup"><span data-stu-id="90b6d-141">-authorizationmanager authorizationManagerType</span></span>|<span data-ttu-id="90b6d-142">Der Typ, der die Autorisierungs-Manager-Implementierung enthält.</span><span class="sxs-lookup"><span data-stu-id="90b6d-142">The type that contains the authorization manager implementation.</span></span> <span data-ttu-id="90b6d-143">Dies kann im Quellcode definiert oder in eine Assembly kompiliert werden (angegeben durch den `reference`-Parameter).</span><span class="sxs-lookup"><span data-stu-id="90b6d-143">This can be defined in source code, or compiled into an assembly (specified by the `reference` parameter).</span></span> <span data-ttu-id="90b6d-144">Wenn dieser Parameter nicht angegeben wird, wird der Standard Sicherheits-Manager verwendet.</span><span class="sxs-lookup"><span data-stu-id="90b6d-144">If this parameter is not specified, the default security manager is used.</span></span> <span data-ttu-id="90b6d-145">Der Wert muss der vollständige Typname sein, einschließlich der Namespaces.</span><span class="sxs-lookup"><span data-stu-id="90b6d-145">The value should be the full type name, including namespaces.</span></span>|
|<span data-ttu-id="90b6d-146">-win32icon i. ico</span><span class="sxs-lookup"><span data-stu-id="90b6d-146">-win32icon i.ico</span></span>|<span data-ttu-id="90b6d-147">Das Symbol für die exe-Datei für die Shell.</span><span class="sxs-lookup"><span data-stu-id="90b6d-147">The icon for the .exe file for the shell.</span></span> <span data-ttu-id="90b6d-148">Wenn kein Wert angegeben wird, hat die Shell das Symbol, das der c#-Compiler enthält (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="90b6d-148">If not specified, then the shell will have the icon that the c# compiler includes (if any).</span></span>|
|<span data-ttu-id="90b6d-149">-Initscript p. ps1</span><span class="sxs-lookup"><span data-stu-id="90b6d-149">-initscript p.ps1</span></span>|<span data-ttu-id="90b6d-150">Das Start Profil für die Shell.</span><span class="sxs-lookup"><span data-stu-id="90b6d-150">The startup profile for the shell.</span></span> <span data-ttu-id="90b6d-151">Die Datei ist "unverändert" enthalten. keine Gültigkeits Überprüfung erfolgt durch make-Shell.</span><span class="sxs-lookup"><span data-stu-id="90b6d-151">The file is included "as-is"; no validity checking is done by Make-Shell.</span></span>|
|<span data-ttu-id="90b6d-152">-builtinscript S1. ps1 [, S2. ps1,...]</span><span class="sxs-lookup"><span data-stu-id="90b6d-152">-builtinscript s1.ps1[,s2.ps1,...]</span></span>|<span data-ttu-id="90b6d-153">Eine Liste der integrierten Skripts für die Shell.</span><span class="sxs-lookup"><span data-stu-id="90b6d-153">A list of built-in scripts for the shell.</span></span> <span data-ttu-id="90b6d-154">Diese Skripts werden vor Skripts im Pfad erkannt, und ihre Inhalte können nicht mehr geändert werden, nachdem die Shell erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="90b6d-154">These scripts are discovered before scripts in the path, and their contents cannot be changed once the shell is built.</span></span><br /><br /> <span data-ttu-id="90b6d-155">Die Dateien sind unverändert enthalten. keine Gültigkeits Überprüfung erfolgt durch make-Shell.</span><span class="sxs-lookup"><span data-stu-id="90b6d-155">The files are included "as-is"; no validity checking is done by Make-Shell.</span></span>|
|<span data-ttu-id="90b6d-156">-Resource resourceFile. txt</span><span class="sxs-lookup"><span data-stu-id="90b6d-156">-resource resourcefile.txt</span></span>|<span data-ttu-id="90b6d-157">Die txt-Datei, die Hilfe-und Banner Ressourcen für die Shell enthält.</span><span class="sxs-lookup"><span data-stu-id="90b6d-157">The .txt file containing help and banner resources for the shell.</span></span> <span data-ttu-id="90b6d-158">Die erste Ressource heißt "shellhelp" und enthält den Text, der angezeigt wird, wenn die Shell mit dem Parameter "`help`" aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="90b6d-158">The first resource is named ShellHelp, and contains the text displayed if the shell is invoked with the `help` parameter.</span></span> <span data-ttu-id="90b6d-159">Die zweite Ressource heißt shellbanner und enthält den Text und die Copyright Informationen, die angezeigt werden, wenn die Shell im interaktiven Modus gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="90b6d-159">The second resource is named ShellBanner, and it contains the text and copyright information displayed when the shell is launched in interactive mode.</span></span><br /><br /> <span data-ttu-id="90b6d-160">Wenn dieser Parameter nicht angegeben wird oder diese Ressourcen nicht vorhanden sind, werden eine generische Hilfe und ein Banner verwendet.</span><span class="sxs-lookup"><span data-stu-id="90b6d-160">If this parameter is not provided, or these resources are not present, then a generic help and banner are used.</span></span>|
|<span data-ttu-id="90b6d-161">cscflags-cscflags</span><span class="sxs-lookup"><span data-stu-id="90b6d-161">-cscflags cscFlags</span></span>|<span data-ttu-id="90b6d-162">Flags, die an den C# Compiler (CSC. exe) übermittelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="90b6d-162">Flags that should be passed to the C# compiler (csc.exe).</span></span> <span data-ttu-id="90b6d-163">Diese werden unverändert übermittelt.</span><span class="sxs-lookup"><span data-stu-id="90b6d-163">These are passed through unchanged.</span></span> <span data-ttu-id="90b6d-164">Wenn dieser Parameter Leerzeichen enthält, sollte er in doppelte Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="90b6d-164">If this parameter includes spaces, it should be surrounded in double-quotes.</span></span>|
|<span data-ttu-id="90b6d-165">-?</span><span class="sxs-lookup"><span data-stu-id="90b6d-165">-?</span></span><br /><br /> <span data-ttu-id="90b6d-166">-Hilfe</span><span class="sxs-lookup"><span data-stu-id="90b6d-166">-help</span></span>|<span data-ttu-id="90b6d-167">Zeigt die Copyright Meldung und die Befehlszeilenoptionen für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="90b6d-167">Displays the copyright message and Make-Shell command line options.</span></span>|
|<span data-ttu-id="90b6d-168">-Verbose</span><span class="sxs-lookup"><span data-stu-id="90b6d-168">-verbose</span></span>|<span data-ttu-id="90b6d-169">Zeigt ausführliche Informationen an, während die Shell erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="90b6d-169">Displays detailed information while the shell is being created.</span></span>|

## <a name="see-also"></a><span data-ttu-id="90b6d-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90b6d-170">See Also</span></span>

[<span data-ttu-id="90b6d-171">Windows PowerShell-Programmier Handbuch</span><span class="sxs-lookup"><span data-stu-id="90b6d-171">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="90b6d-172">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="90b6d-172">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)