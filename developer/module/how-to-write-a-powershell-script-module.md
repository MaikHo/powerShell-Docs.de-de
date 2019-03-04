---
title: 'Gewusst wie: Schreiben Sie ein PowerShell-Skriptmodul | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed7645ea-5e52-4a45-81a7-aa3c2d605cde
caps.latest.revision: 16
ms.openlocfilehash: e8b7151538235cdf7183b78aa8df7e596d6bcfd9
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859006"
---
# <a name="how-to-write-a-powershell-script-module"></a><span data-ttu-id="f7f5b-102">Schreiben eines PowerShell-Skriptmoduls</span><span class="sxs-lookup"><span data-stu-id="f7f5b-102">How to Write a PowerShell Script Module</span></span>

<span data-ttu-id="f7f5b-103">Ein Skriptmodul ist im Wesentlichen alle gültigen PowerShell-Skript in einer psm1-Erweiterung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-103">A script module is essentially any valid PowerShell script saved in a .psm1 extension.</span></span> <span data-ttu-id="f7f5b-104">Diese Erweiterung ermöglicht die PowerShell-Engine eine Reihe von Regeln und -Cmdlets auf die Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-104">This extension allows the PowerShell engine to use a number of rules and cmdlets on your file.</span></span> <span data-ttu-id="f7f5b-105">Die meisten dieser Funktionen gibt es können Sie Ihren Code sowie das Verwalten der Bereichsdefinition auf anderen Systemen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-105">Most of these capabilities are there to help you install your code on other systems, as well as manage scoping.</span></span> <span data-ttu-id="f7f5b-106">Sie können auch eine modulmanifestdatei, die noch komplexer Installationen und -Lösungen beschreiben können.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-106">You can also use a module manifest file, which can describe even more complex installations and solutions.</span></span>

## <a name="writing-a-powershell-script-module"></a><span data-ttu-id="f7f5b-107">Erstellen eines PowerShell-Skript-Moduls</span><span class="sxs-lookup"><span data-stu-id="f7f5b-107">Writing a PowerShell Script Module</span></span>

<span data-ttu-id="f7f5b-108">Sie erstellen ein Skriptmodul ein gültigen PowerShell-Skripts in einer psm1-Datei speichern, und klicken Sie dann die Datei speichern, in einem Verzeichnis befinden, in dem Sie PowerShell gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-108">You create a script module by saving a valid PowerShell script to a .psm1 file, and then saving that file in a directory located where PowerShell can find it.</span></span> <span data-ttu-id="f7f5b-109">In diesem Ordner, den Sie auch alle Ressourcen platzieren können, die Sie das Skript ausführen müssen, sowie eine Manifestdatei, die an PowerShell Ihres Moduls wird die Funktionsweise beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-109">In that folder you can also place any resources you need to run your script, as well as a manifest file that describes to PowerShell how your module works.</span></span>

#### <a name="to-create-a-basic-powershell-module"></a><span data-ttu-id="f7f5b-110">Erstellen eines grundlegenden PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="f7f5b-110">To create a basic PowerShell Module</span></span>

1. <span data-ttu-id="f7f5b-111">Nehmen Sie ein vorhandenes PowerShell-Skript, und speichern Sie das Skript mit der Erweiterung. psm1.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-111">Take an existing PowerShell script, and save the script with a .psm1 extension.</span></span>

   <span data-ttu-id="f7f5b-112">Speichern eines Skripts mit den. psm1 Erweiterung bedeutet, dass Sie die Modul-Cmdlets, z. B. können [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module), darauf.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-112">Saving a script with the .psm1 extension means that you can use the module cmdlets, such as [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module), on it.</span></span> <span data-ttu-id="f7f5b-113">Diese Cmdlets sind in erster Linie, damit Sie leicht importieren und Exportieren von Ihrem Code auch auf anderen Systemen anderer Benutzer vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-113">These cmdlets exist primarily so that you can easily import and export your code onto other user's systems.</span></span> <span data-ttu-id="f7f5b-114">(Die alternative Lösung wäre Sie Ihren Code auf anderen Systemen und klicken Sie dann die Punkt-Quelle in den aktiven Arbeitsspeicher laden, die eine besonders skalierbare Lösung ist.) Weitere Informationen finden Sie unter den **-Modul-Cmdlets und Variablen** im Abschnitt [Windows PowerShell-Module](./understanding-a-windows-powershell-module.md) Beachten Sie, dass standardmäßig alle Funktionen in Ihrem Skript für Benutzer zugegriffen werden können, die Ihre. psm1 importieren Datei, aber die Eigenschaften nicht der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-114">(The alternate solution would be to load up your code on other systems and then dot-source it into active memory, which isn't a particularly scalable solution.) For more information see the **Module Cmdlets and Variables** section in [Windows PowerShell Modules](./understanding-a-windows-powershell-module.md) Note that, by default, all functions in your script will be accessible to users who import your .psm1 file, but properties will not.</span></span>

   <span data-ttu-id="f7f5b-115">Ein Beispiel-PowerShell-Skript, Show-Calendar, berechtigt ist am Ende dieses Themas verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-115">An example PowerShell script, entitled Show-Calendar, is available at the end of this topic.</span></span>

   ```powershell
   function Show-Calendar {
   param(
       [DateTime] $start = [DateTime]::Today,
       [DateTime] $end = $start,
       $firstDayOfWeek,
       [int[]] $highlightDay,
       [string[]] $highlightDate = [DateTime]::Today.ToString()
       )

       #actual code for the function goes here see the end of the topic for the complete code sample
   }
   ```

2. <span data-ttu-id="f7f5b-116">Wenn Sie Benutzerzugriff auf bestimmte Funktionen oder Eigenschaften steuern möchten, rufen Sie [Export-ModuleMember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) am Ende des Skripts.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-116">If you wish to control user access to certain functions or properties, call [Export-ModuleMember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) at the end of your script.</span></span>

   <span data-ttu-id="f7f5b-117">Der Beispielcode am unteren Rand der Seite verfügt über nur eine Funktion, die standardmäßig verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-117">The example code at the bottom of the page has only one function, which by default would be exposed.</span></span> <span data-ttu-id="f7f5b-118">Allerdings empfiehlt es sich, dass Sie explizit die Funktionen, die Sie verfügbar zu machen aufrufen,, wie im folgenden Code beschrieben möchten:</span><span class="sxs-lookup"><span data-stu-id="f7f5b-118">However, it is recommended that you explicitly call out which functions you wish to expose, as described in the following code:</span></span>

   ```powershell
   function Show-Calendar {
         }
   Export-ModuleMember -Function Show-Calendar
   ```

   <span data-ttu-id="f7f5b-119">Sie können auch einschränken, was importiert wurde, verwenden ein modulmanifest.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-119">You can also restrict what is imported using a module manifest.</span></span> <span data-ttu-id="f7f5b-120">Weitere Informationen finden Sie unter [Importieren eines PowerShell-Moduls](./importing-a-powershell-module.md) und [Gewusst wie: Schreiben eines Modulmanifests PowerShell](./how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="f7f5b-120">For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md) and [How to Write a PowerShell Module Manifest](./how-to-write-a-powershell-module-manifest.md).</span></span>

3. <span data-ttu-id="f7f5b-121">Wenn Sie Module, die Ihr eigenes Modul geladen haben haben, können sie mit einem Aufruf von `Import-Module`, am oberen Rand Ihres eigenen Moduls.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-121">If you have modules that your own module needs to have loaded, you can use them with a call to `Import-Module`, at the top of your own module.</span></span>

   <span data-ttu-id="f7f5b-122">`Import-Module` ist ein Cmdlet, mit denen eine gezielte Modul auf einem System importiert.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-122">`Import-Module` is a cmdlet that imports a targeted module onto a system.</span></span> <span data-ttu-id="f7f5b-123">Daher ist es auch zu einem späteren Zeitpunkt im Verfahren zur auch Ihr eigenes Modul zu installieren.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-123">As such, it is also used at a later point in the procedure to install your own module as well.</span></span> <span data-ttu-id="f7f5b-124">Der Beispielcode am unteren Rand dieser Seite verwendet keine Module importieren.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-124">The sample code at the bottom of this page does not use any import modules.</span></span> <span data-ttu-id="f7f5b-125">Wenn, jedoch hat würden sie am Anfang der Datei aufgelistet werden, wie im folgenden Code beschrieben:</span><span class="sxs-lookup"><span data-stu-id="f7f5b-125">If it did, however, they would be listed at the top of the file, as described in the following code:</span></span>

   ```powershell
   Import-Module GenericModule
   ```

4. <span data-ttu-id="f7f5b-126">Wenn Sie Ihr Modul an das PowerShell-Hilfesystem beschreiben möchten, können Sie entweder die Standardhilfe Kommentare in der Datei oder mit einer zusätzlichen Hilfedatei dafür.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-126">If you want to describe your module to the PowerShell Help system, you can do so either with the standard help comments inside the file, or with an additional Help file.</span></span>

   <span data-ttu-id="f7f5b-127">Das Codebeispiel am Ende dieses Themas enthält die Hilfeinformationen in den Kommentaren.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-127">The code sample at the bottom of this topic includes the help information in the comments.</span></span> <span data-ttu-id="f7f5b-128">Wenn Sie möchten, könnten Sie auch erweiterte XML-Dateien schreiben, die zusätzliche Hilfe-Inhalt enthalten.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-128">If you so choose, you could also write expanded XML files that contain additional help content.</span></span> <span data-ttu-id="f7f5b-129">Weitere Informationen finden Sie unter [Schreiben von Hilfe für Windows PowerShell-Module](./writing-help-for-windows-powershell-modules.md).</span><span class="sxs-lookup"><span data-stu-id="f7f5b-129">For more information, see [Writing Help for Windows PowerShell Modules](./writing-help-for-windows-powershell-modules.md).</span></span>

5. <span data-ttu-id="f7f5b-130">Wenn Sie haben zusätzliche Module, XML-Dateien oder andere Inhalte, die Sie mit Ihrem Modul verpacken möchten, können mit einem modulmanifest möchten.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-130">If you have additional modules, XML files, or other content you want to package up with your module, you can do so with a module manifest.</span></span>

   <span data-ttu-id="f7f5b-131">Ein modulmanifest ist eine Datei, die Namen von anderen Modulen, verzeichnislayouts, versionsverwaltung Zahlen, Autor-Daten und andere Arten von Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-131">A module manifest is a file that contains the names of other modules, directory layouts, versioning numbers, author data, and other pieces of information.</span></span> <span data-ttu-id="f7f5b-132">PowerShell verwendet der modulmanifestdatei zu organisieren und Ihre Lösung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-132">PowerShell uses the module manifest file to organize and deploy your solution.</span></span> <span data-ttu-id="f7f5b-133">Aufgrund der relativ einfache Art der in diesem Beispiel werden soll, wurde eine Manifestdatei jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-133">However, due to the relatively simple nature of this example, a manifest file was not needed.</span></span> <span data-ttu-id="f7f5b-134">Weitere Informationen finden Sie unter [Modul Manifeste](./how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="f7f5b-134">For more information, see [Module Manifests](./how-to-write-a-powershell-module-manifest.md).</span></span>

6. <span data-ttu-id="f7f5b-135">Klicken Sie zum Installieren und Ausführen des Moduls, speichern Sie das Modul auf eine der entsprechenden PowerShell-Pfaden, und rufen Sie `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-135">To install and run your module, save the module to one of the appropriate PowerShell paths, and make a call to `Import-Module`.</span></span>

   <span data-ttu-id="f7f5b-136">Die Pfade, in dem Sie Ihr Modul installieren können, befinden sich in der `$env:PSModulePath` globale Variable.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-136">The paths where you can install your module are located in the `$env:PSModulePath` global variable.</span></span> <span data-ttu-id="f7f5b-137">Z. B. ein gemeinsamen Pfad um ein Modul auf einem System zu speichern wäre `%SystemRoot%/users/<user>/Documents/WindowsPowerShell/Modules/<moduleName>`.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-137">For example, a common path to save a module on a system would be `%SystemRoot%/users/<user>/Documents/WindowsPowerShell/Modules/<moduleName>`.</span></span> <span data-ttu-id="f7f5b-138">Achten Sie darauf, dass Sie einen Ordner für Ihr Modul vorhanden, zu erstellen, selbst wenn es nur eine einzelne. psm1-Datei handelt.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-138">Be sure to create a folder for your module to exist in, even if it is only a single .psm1 file.</span></span> <span data-ttu-id="f7f5b-139">Wenn Sie Ihr Modul nicht auf einen der folgenden Pfade gespeichert haben, müssen in den Speicherort Ihres Moduls im Aufruf übergeben, um `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-139">If you did not save your module to one of these paths, you would have to pass in the location of your module in the call to `Import-Module`.</span></span> <span data-ttu-id="f7f5b-140">(Andernfalls PowerShell nicht finden, es wäre.) Starten mit PowerShell 3.0, wenn Sie Ihr Modul auf einem der Pfade PowerShell-Modul platziert haben, Sie müssen nicht explizit importieren: einfach dadurch, dass einen Benutzer, die Ihre Funktion aufrufen, wird Sie automatisch geladen.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-140">(Otherwise, PowerShell would not be able to find it.) Starting with PowerShell 3.0, if you have placed your module on one of the PowerShell module paths, you do not need to explicitly import it: simply having a user call your function will automatically load it.</span></span> <span data-ttu-id="f7f5b-141">Weitere Informationen zu den Modulpfad, finden Sie unter [Importieren eines PowerShell-Moduls](./importing-a-powershell-module.md) und [PSModulePath-Umgebungsvariable](./modifying-the-psmodulepath-installation-path.md).</span><span class="sxs-lookup"><span data-stu-id="f7f5b-141">For more information on the module path, see [Importing a PowerShell Module](./importing-a-powershell-module.md) and [PSModulePath Environment Variable](./modifying-the-psmodulepath-installation-path.md).</span></span>

7. <span data-ttu-id="f7f5b-142">Stellen Sie zum Entfernen eines Moduls aus dem aktiven Dienst einen Aufruf von [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module).</span><span class="sxs-lookup"><span data-stu-id="f7f5b-142">To remove a module from active service, make a call to [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module).</span></span>

<span data-ttu-id="f7f5b-143">Beachten Sie, dass [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module) entfernt Ihres Moduls von aktivem Speicher – es werden nicht tatsächlich gelöscht es aus, in dem Sie die Moduldateien gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-143">Note that [Remove-Module](/powershell/module/Microsoft.PowerShell.Core/Remove-Module) removes your module from active memory - it does not actually delete it from where you saved the module files.</span></span>

### <a name="show-calendar-code-example"></a><span data-ttu-id="f7f5b-144">Show-Calendar-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="f7f5b-144">Show-Calendar code example</span></span>

<span data-ttu-id="f7f5b-145">Im folgende Beispiel wird ein einfaches Skript-Modul, das eine einzelne Funktion, die mit dem Namen Show-Calendar enthält.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-145">The following example is a simple script module that contains a single function named Show-Calendar.</span></span> <span data-ttu-id="f7f5b-146">Diese Funktion zeigt eine visuelle Darstellung eines Kalenders.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-146">This function displays a visual representation of a calendar.</span></span> <span data-ttu-id="f7f5b-147">Darüber hinaus enthält das Beispiel die PowerShell-Hilfe-Zeichenfolgen für die Zusammenfassung, Beschreibung, Parameterwerte und Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-147">In addition, the sample contains the PowerShell Help strings for the synopsis, description, parameter values, and example.</span></span> <span data-ttu-id="f7f5b-148">Beachten Sie, dass die letzte Zeile des Codes gibt an, dass die Show-Calendar-Funktion als Mitglied Modul exportiert werden, wenn das Modul importiert wird.</span><span class="sxs-lookup"><span data-stu-id="f7f5b-148">Note that the last line of code indicates that the Show-Calendar function will be exported as a module member when the module is imported.</span></span>

```powershell
<#
 .Synopsis
  Displays a visual representation of a calendar.

 .Description
  Displays a visual representation of a calendar. This function supports multiple months
  and lets you highlight specific date ranges or days.

 .Parameter Start
  The first month to display.

 .Parameter End
  The last month to display.

 .Parameter FirstDayOfWeek
  The day of the month on which the week begins.

 .Parameter HighlightDay
  Specific days (numbered) to highlight. Used for date ranges like (25..31).
  Date ranges are specified by the Windows PowerShell range syntax. These dates are
  enclosed in square brackets.

 .Parameter HighlightDate
  Specific days (named) to highlight. These dates are surrounded by asterisks.

 .Example
   # Show a default display of this month.
   Show-Calendar

 .Example
   # Display a date range.
   Show-Calendar -Start "March, 2010" -End "May, 2010"

 .Example
   # Highlight a range of days.
   Show-Calendar -HighlightDay (1..10 + 22) -HighlightDate "December 25, 2008"
#>
function Show-Calendar {
param(
    [DateTime] $start = [DateTime]::Today,
    [DateTime] $end = $start,
    $firstDayOfWeek,
    [int[]] $highlightDay,
    [string[]] $highlightDate = [DateTime]::Today.ToString()
    )

## Determine the first day of the start and end months.
$start = New-Object DateTime $start.Year,$start.Month,1
$end = New-Object DateTime $end.Year,$end.Month,1

## Convert the highlighted dates into real dates.
[DateTime[]] $highlightDate = [DateTime[]] $highlightDate

## Retrieve the DateTimeFormat information so that the
## calendar can be manipulated.
$dateTimeFormat  = (Get-Culture).DateTimeFormat
if($firstDayOfWeek)
{
    $dateTimeFormat.FirstDayOfWeek = $firstDayOfWeek
}

$currentDay = $start

## Process the requested months.
while($start -le $end)
{
    ## Return to an earlier point in the function if the first day of the month
    ## is in the middle of the week.
    while($currentDay.DayOfWeek -ne $dateTimeFormat.FirstDayOfWeek)
    {
        $currentDay = $currentDay.AddDays(-1)
    }

    ## Prepare to store information about this date range.
    $currentWeek = New-Object PsObject
    $dayNames = @()
    $weeks = @()

    ## Continue processing dates until the function reaches the end of the month.
    ## The function continues until the week is completed with
    ## days from the next month.
    while(($currentDay -lt $start.AddMonths(1)) -or
        ($currentDay.DayOfWeek -ne $dateTimeFormat.FirstDayOfWeek))
    {
        ## Determine the day names to use to label the columns.
        $dayName = "{0:ddd}" -f $currentDay
        if($dayNames -notcontains $dayName)
        {
            $dayNames += $dayName
        }

        ## Pad the day number for display, highlighting if necessary.
        $displayDay = " {0,2} " -f $currentDay.Day

        ## Determine whether to highlight a specific date.
        if($highlightDate)
        {
            $compareDate = New-Object DateTime $currentDay.Year,
                $currentDay.Month,$currentDay.Day
            if($highlightDate -contains $compareDate)
            {
                $displayDay = "*" + ("{0,2}" -f $currentDay.Day) + "*"
            }
        }

        ## Otherwise, highlight as part of a date range.
        if($highlightDay -and ($highlightDay[0] -eq $currentDay.Day))
        {
            $displayDay = "[" + ("{0,2}" -f $currentDay.Day) + "]"
            $null,$highlightDay = $highlightDay
        }

        ## Add the day of the week and the day of the month as note properties.
        $currentWeek | Add-Member NoteProperty $dayName $displayDay

        ## Move to the next day of the month.
        $currentDay = $currentDay.AddDays(1)

        ## If the function reaches the next week, store the current week
        ## in the week list and continue.
        if($currentDay.DayOfWeek -eq $dateTimeFormat.FirstDayOfWeek)
        {
            $weeks += $currentWeek
            $currentWeek = New-Object PsObject
        }
    }

    ## Format the weeks as a table.
    $calendar = $weeks | Format-Table $dayNames -AutoSize | Out-String

    ## Add a centered header.
    $width = ($calendar.Split("'n") | Measure-Object -Maximum Length).Maximum
    $header = "{0:MMMM yyyy}" -f $start
    $padding = " " * (($width - $header.Length) / 2)
    $displayCalendar = " 'n" + $padding + $header + "'n " + $calendar
    $displayCalendar.TrimEnd()

    ## Move to the next month.
    $start = $start.AddMonths(1)

}
}
Export-ModuleMember -Function Show-Calendar
```