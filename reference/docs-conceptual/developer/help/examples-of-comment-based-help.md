---
title: Beispiele für die Kommentar basierte Hilfe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 868194a2-17e9-4184-bc36-c04a33f26494
caps.latest.revision: 4
ms.openlocfilehash: 30e98bfcf06b1720005a73ee8294aeba7e1ae066
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367819"
---
# <a name="examples-of-comment-based-help"></a><span data-ttu-id="c57b0-102">Beispiele für die kommentarbasierte Hilfe</span><span class="sxs-lookup"><span data-stu-id="c57b0-102">Examples of Comment-Based Help</span></span>

<span data-ttu-id="c57b0-103">Dieses Thema enthält ein Beispiel für die Verwendung der Kommentar basierten Hilfe für Skripts und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="c57b0-103">This topic includes example that demonstrate how to use comment-based help for scripts and functions.</span></span>

## <a name="example-1-comment-based-help-for-a-function"></a><span data-ttu-id="c57b0-104">Beispiel 1: Kommentar basierte Hilfe für eine Funktion</span><span class="sxs-lookup"><span data-stu-id="c57b0-104">Example 1: Comment-Based Help for a Function</span></span>

 <span data-ttu-id="c57b0-105">Die folgende Beispiel Funktion enthält eine Kommentar basierte Hilfe.</span><span class="sxs-lookup"><span data-stu-id="c57b0-105">The following sample function includes comment-based Help.</span></span>

```powershell
function Add-Extension
{
    param ([string]$Name,[string]$Extension = "txt")
    $name = $name + "." + $extension
    $name

    <#
        .SYNOPSIS
        Adds a file name extension to a supplied name.

        .DESCRIPTION
        Adds a file name extension to a supplied name.
        Takes any strings for the file name or extension.

        .PARAMETER Name
        Specifies the file name.

        .PARAMETER Extension
        Specifies the extension. "Txt" is the default.

        .INPUTS
        None. You cannot pipe objects to Add-Extension.

        .OUTPUTS
        System.String. Add-Extension returns a string with the extension or file name.

        .EXAMPLE
        C:\PS> extension -name "File"
        File.txt

        .EXAMPLE
        C:\PS> extension -name "File" -extension "doc"
        File.doc

        .EXAMPLE
        C:\PS> extension "File" "doc"
        File.doc

        .LINK
        Online version: http://www.fabrikam.com/extension.html

        .LINK
        Set-Item
    #>
}
```

<span data-ttu-id="c57b0-106">Die folgende Ausgabe zeigt die Ergebnisse eines Get-Help-Befehls, der die Hilfe für die Add-Extension-Funktion anzeigt.</span><span class="sxs-lookup"><span data-stu-id="c57b0-106">The following output shows the results of a Get-Help command that displays the help for the Add-Extension function.</span></span>

```powershell
C:\PS> get-help add-extension -full
```

```output
        NAME
            Add-Extension

        SYNOPSIS
            Adds a file name extension to a supplied name.

        SYNTAX
            Add-Extension [[-Name] <String>] [[-Extension] <String>] [<CommonParameters>]

        DESCRIPTION
            Adds a file name extension to a supplied name. Takes any strings for the file name or extension.

        PARAMETERS
           -Name
               Specifies the file name.

               Required?                    false
               Position?                    0
               Default value
               Accept pipeline input?       false
               Accept wildcard characters?

           -Extension
               Specifies the extension. "Txt" is the default.

               Required?                    false
               Position?                    1
               Default value
               Accept pipeline input?       false
               Accept wildcard characters?

            <CommonParameters>
               This cmdlet supports the common parameters: -Verbose, -Debug,
               -ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
               -OutBuffer and -OutVariable. For more information, type
               "get-help about_commonparameters".

        INPUTS
            None. You cannot pipe objects to Add-Extension.

        OUTPUTS
            System.String. Add-Extension returns a string with the extension or file name.

            -------------------------- EXAMPLE 1 --------------------------

            C:\PS> extension -name "File"
            File.txt

            -------------------------- EXAMPLE 2 --------------------------

            C:\PS> extension -name "File" -extension "doc"
            File.doc

            -------------------------- EXAMPLE 3 --------------------------

            C:\PS> extension "File" "doc"
            File.doc

        RELATED LINKS
            Online version: http://www.fabrikam.com/extension.html
            Set-Item
```

## <a name="example-2-comment-based-help-for-a-script"></a><span data-ttu-id="c57b0-107">Beispiel 2: Kommentar basierte Hilfe für ein Skript</span><span class="sxs-lookup"><span data-stu-id="c57b0-107">Example 2: Comment-Based Help for a Script</span></span>

<span data-ttu-id="c57b0-108">Die folgende Beispiel Funktion enthält eine Kommentar basierte Hilfe.</span><span class="sxs-lookup"><span data-stu-id="c57b0-108">The following sample function includes comment-based Help.</span></span>

<span data-ttu-id="c57b0-109">Beachten Sie die leeren Zeilen zwischen dem Schließ **enden #>** und der `Param`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c57b0-109">Notice the blank lines between the closing **#>** and the `Param` statement.</span></span> <span data-ttu-id="c57b0-110">In einem Skript, das nicht über eine `Param`-Anweisung verfügt, müssen mindestens zwei Leerzeilen zwischen dem letzten Kommentar im Hilfethema und der ersten Funktionsdeklaration vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="c57b0-110">In a script that does not have a `Param` statement, there must be at least two blank lines between the final comment in the Help topic and the first function declaration.</span></span> <span data-ttu-id="c57b0-111">Ohne diese leeren Zeilen verknüpft Get-Help das Hilfethema anstelle des Skripts mit der Funktion.</span><span class="sxs-lookup"><span data-stu-id="c57b0-111">Without these blank lines, Get-Help associates the Help topic with the function, instead of the script.</span></span>

```powershell
<#
  .SYNOPSIS
  Performs monthly data updates.

  .DESCRIPTION
  The Update-Month.ps1 script updates the registry with new data generated
  during the past month and generates a report.

  .PARAMETER InputPath
  Specifies the path to the CSV-based input file.

  .PARAMETER OutputPath
  Specifies the name and path for the CSV-based output file. By default,
  MonthlyUpdates.ps1 generates a name from the date and time it runs, and
  saves the output in the local directory.

  .INPUTS
  None. You cannot pipe objects to Update-Month.ps1.

  .OUTPUTS
  None. Update-Month.ps1 does not generate any output.

  .EXAMPLE
  C:\PS> .\Update-Month.ps1

  .EXAMPLE
  C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

  .EXAMPLE
  C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath C:\Reports\2009\January.csv
#>

param ([string]$InputPath, [string]$OutPutPath)

function Get-Data { }
```

<span data-ttu-id="c57b0-112">Der folgende Befehl ruft die Skript Hilfe ab.</span><span class="sxs-lookup"><span data-stu-id="c57b0-112">The following command gets the script Help.</span></span> <span data-ttu-id="c57b0-113">Da es sich bei dem Skript nicht um ein Verzeichnis handelt, das in der PATH-Umgebungsvariablen aufgelistet ist, muss der Get-Help-Befehl, der die Skript Hilfe abruft, den Skript Pfad angeben.</span><span class="sxs-lookup"><span data-stu-id="c57b0-113">Because the script is not n a directory that is listed in the Path environment variable, the Get-Help command that gets the script Help must specify the script path.</span></span>

```powershell
C:\PS> get-help c:\ps-test\update-month.ps1 -full
```

```output
            NAME
                C:\ps-test\Update-Month.ps1

            SYNOPSIS
                Performs monthly data updates.

            SYNTAX
                C:\ps-test\Update-Month.ps1 [-InputPath] <String> [[-OutputPath]
                <String>] [<CommonParameters>]

            DESCRIPTION
                The Update-Month.ps1 script updates the registry with new data
                generated during the past month and generates a report.

            PARAMETERS
               -InputPath
                   Specifies the path to the CSV-based input file.

                   Required?                    true
                   Position?                    0
                   Default value
                   Accept pipeline input?       false
                   Accept wildcard characters?

               -OutputPath
                   Specifies the name and path for the CSV-based output file. By
                   default, MonthlyUpdates.ps1 generates a name from the date
                   and time it runs, and saves the output in the local directory.

                   Required?                    false
                   Position?                    1
                   Default value
                   Accept pipeline input?       false
                   Accept wildcard characters?

               <CommonParameters>
                   This cmdlet supports the common parameters: -Verbose, -Debug,
                   -ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
                   -OutBuffer and -OutVariable. For more information, type,
                   "get-help about_commonparameters".

            INPUTS
                   None. You cannot pipe objects to Update-Month.ps1.

            OUTPUTS
                   None. Update-Month.ps1 does not generate any output.

            -------------------------- EXAMPLE 1 --------------------------

            C:\PS> .\Update-Month.ps1

            -------------------------- EXAMPLE 2 --------------------------

            C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

            -------------------------- EXAMPLE 3 --------------------------

            C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath
            C:\Reports\2009\January.csv

            RELATED LINKS
```

## <a name="example-3-parameter-descriptions-in-a-param-statement"></a><span data-ttu-id="c57b0-114">Beispiel 3: Parameter Beschreibungen in einer Param-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c57b0-114">Example 3: Parameter Descriptions in a Param Statement</span></span>

<span data-ttu-id="c57b0-115">In diesem Beispiel wird gezeigt, wie Parameterbeschreibungen in der `Param`-Anweisung einer Funktion oder eines Skripts eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c57b0-115">This example show how to insert parameterdescriptions in the `Param` statement of a function or script.</span></span> <span data-ttu-id="c57b0-116">Dieses Format ist besonders nützlich, wenn die Parameter Beschreibungen kurz sind.</span><span class="sxs-lookup"><span data-stu-id="c57b0-116">This format is most useful when the parameter descriptions are brief.</span></span>

```powershell
function Add-Extension
{
    param
    (
        [string]
        # Specifies the file name.
        $name,

        [string]
        # Specifies the file name extension. "Txt" is the default.
        $extension = "txt"
    )
    $name = $name + "." + $extension
    $name

    <#
        .SYNOPSIS
        Adds a file name extension to a supplied name.
...
    #>
```

<span data-ttu-id="c57b0-117">Die Ergebnisse sind identisch mit den Ergebnissen für Beispiel 1.</span><span class="sxs-lookup"><span data-stu-id="c57b0-117">The results are the same as the results for Example 1.</span></span> <span data-ttu-id="c57b0-118">"Get-Help" interpretiert die Parameter Beschreibungen so, als hätten Sie das Schlüsselwort "`.Parameter`" begleitet.</span><span class="sxs-lookup"><span data-stu-id="c57b0-118">Get-Help interprets the parameter descriptions as though they were accompanied by the `.Parameter` keyword.</span></span>

## <a name="example-4--redirecting-to-an-xml-file"></a><span data-ttu-id="c57b0-119">Beispiel 4: Umleiten an eine XML-Datei</span><span class="sxs-lookup"><span data-stu-id="c57b0-119">Example 4:  Redirecting to an XML File</span></span>

<span data-ttu-id="c57b0-120">Sie können XML-basierte Hilfe Themen für Funktionen und Skripts schreiben.</span><span class="sxs-lookup"><span data-stu-id="c57b0-120">You can write XML-based Help topics for functions and scripts.</span></span> <span data-ttu-id="c57b0-121">Obwohl die Kommentar basierte Hilfe einfacher implementiert werden kann, ist die XML-basierte Hilfe erforderlich, wenn Sie die Hilfe Inhalte genauer steuern möchten oder wenn Sie Hilfe Themen in mehrere Sprachen übersetzen möchten. Das folgende Beispiel zeigt die ersten Zeilen des Skripts Update-month. ps1.</span><span class="sxs-lookup"><span data-stu-id="c57b0-121">Although comment-based Help is easier to implement, XML-based Help is required if you want more precise control over Help content or if you are translating Help topics into multiple languages.The following example shows the first few lines of the Update-Month.ps1 script.</span></span> <span data-ttu-id="c57b0-122">Das Skript verwendet das `.ExternalHelp`-Schlüsselwort, um den Pfad zu einem XML-basierten Hilfethema für das Skript anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c57b0-122">The script uses the `.ExternalHelp` keyword to specify the path to an XML-based Help topic for the script.</span></span>

```powershell
#  .ExternalHelp C:\MyScripts\Update-Month-Help.xml

    param ([string]$InputPath, [string]$OutPutPath)

    function Get-Data { }
```

<span data-ttu-id="c57b0-123">Das folgende Beispiel zeigt die Verwendung des-Schlüssel Worts `.ExternalHelp` in einer-Funktion.</span><span class="sxs-lookup"><span data-stu-id="c57b0-123">The following example shows the use of the `.ExternalHelp` keyword in a function.</span></span>

```powershell
function Add-Extension
{
    param ([string] $name, [string]$extension = "txt")
    $name = $name + "." + $extension
    $name

    # .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

## <a name="example-5--redirecting-to-a-different-help-topic"></a><span data-ttu-id="c57b0-124">Beispiel 5: Umleiten an ein anderes Hilfethema</span><span class="sxs-lookup"><span data-stu-id="c57b0-124">Example 5:  Redirecting to a Different Help Topic</span></span>

<span data-ttu-id="c57b0-125">Der folgende Code ist ein Auszug aus dem Anfang der integrierten `Help`-Funktion in Windows PowerShell, die jeweils einen Bildschirm mit Hilfe Text anzeigt.</span><span class="sxs-lookup"><span data-stu-id="c57b0-125">The following code is an excerpt from the beginning of the built-in `Help` function in Windows PowerShell, which displays one screen of Help text at a time.</span></span> <span data-ttu-id="c57b0-126">Da im Hilfethema für das Cmdlet "Get-Help" die Hilfe Funktion beschrieben wird, verwendet die Funktion "Help" das `.ForwardHelpTargetName`-und `.ForwardHelpCategory`-Schlüsselwort, um den Benutzer zum Hilfethema "Get-Help Cmdlet" umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="c57b0-126">Because the Help topic for the Get-Help cmdlet describes the Help function, the Help function uses the `.ForwardHelpTargetName` and `.ForwardHelpCategory` keywords to redirect the user to the Get-Help cmdlet Help topic.</span></span>

```powershell
function help
{

    <#
      .FORWARDHELPTARGETNAME Get-Help
      .FORWARDHELPCATEGORY Cmdlet
    #>
    [CmdletBinding(DefaultParameterSetName='AllUsersView')]
    param(
            [Parameter(Position=0, ValueFromPipelineByPropertyName=$true)]
            [System.String]
            ${Name},
    ...
```

<span data-ttu-id="c57b0-127">Der folgende Befehl verwendet diese Funktion.</span><span class="sxs-lookup"><span data-stu-id="c57b0-127">The following command uses this feature.</span></span> <span data-ttu-id="c57b0-128">Wenn ein Benutzer einen Get-Help-Befehl für die Hilfe Funktion eingibt, zeigt Get-Help das Hilfethema für das Cmdlet "Get-Help" an.</span><span class="sxs-lookup"><span data-stu-id="c57b0-128">When a user types a Get-Help command for the Help function, Get-Help displays the Help topic for the Get-Help cmdlet.</span></span>

```powershell
C:\PS> get-help help
```

```output
            NAME
                Get-Help

            SYNOPSIS
                Displays information about Windows PowerShell cmdlets and concepts.
            ...
```