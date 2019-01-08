---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: Das ISEOptions-Objekt
ms.assetid: 75e2a76f-f3d1-490b-ad5d-e3829946aabb
ms.openlocfilehash: e756da21aaa5465f7fa6a90563b4180f0c89e87b
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2018
ms.locfileid: "53401901"
---
# <a name="the-iseoptions-object"></a><span data-ttu-id="f1c38-103">Das ISEOptions-Objekt</span><span class="sxs-lookup"><span data-stu-id="f1c38-103">The ISEOptions Object</span></span>

<span data-ttu-id="f1c38-104">Das **ISEOptions**-Objekt stellt verschiedene Einstellungen für Windows PowerShell ISE dar.</span><span class="sxs-lookup"><span data-stu-id="f1c38-104">The **ISEOptions** object represents various settings for Windows PowerShell ISE.</span></span> <span data-ttu-id="f1c38-105">Es ist eine Instanz der **Microsoft.PowerShell.Host.ISE.ISEOptions**-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f1c38-105">It is an instance of the **Microsoft.PowerShell.Host.ISE.ISEOptions** class.</span></span>

<span data-ttu-id="f1c38-106">Das **ISEOptions**-Objekt stellt die folgenden Methoden und Eigenschaften bereit.</span><span class="sxs-lookup"><span data-stu-id="f1c38-106">The **ISEOptions** object provides the following methods and properties.</span></span>

## <a name="methods"></a><span data-ttu-id="f1c38-107">Methoden</span><span class="sxs-lookup"><span data-stu-id="f1c38-107">Methods</span></span>

### <a name="restoredefaultconsoletokencolors"></a><span data-ttu-id="f1c38-108">RestoreDefaultConsoleTokenColors\(\)</span><span class="sxs-lookup"><span data-stu-id="f1c38-108">RestoreDefaultConsoleTokenColors\(\)</span></span>

<span data-ttu-id="f1c38-109">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-110">Stellt die Standardwerte für die Tokenfarben im Konsolenbereich wieder her.</span><span class="sxs-lookup"><span data-stu-id="f1c38-110">Restores the default values of the token colors in the Console pane.</span></span>

```powershell
# Changes the color of the commands in the Console pane to red and then restores it to its default value.
$psISE.Options.ConsoleTokenColors["Command"] = 'red'
$psISE.Options.RestoreDefaultConsoleTokenColors()
```

### <a name="restoredefaults"></a><span data-ttu-id="f1c38-111">RestoreDefaults\(\)</span><span class="sxs-lookup"><span data-stu-id="f1c38-111">RestoreDefaults\(\)</span></span>

<span data-ttu-id="f1c38-112">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-112">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-113">Stellt die Standardwerte aller Optionseinstellungen im Konsolenbereich wieder her.</span><span class="sxs-lookup"><span data-stu-id="f1c38-113">Restores the default values of all options settings in the Console pane.</span></span> <span data-ttu-id="f1c38-114">Außerdem wird das Verhalten von verschiedenen Warnmeldungen zurückgesetzt, in denen das Standardkontrollkästchen angezeigt wird, mit dem das erneute Anzeigen der Nachricht verhindert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f1c38-114">It also resets the behavior of various warning messages that provide the standard check box to prevent the message from being shown again.</span></span>

```powershell
# Changes the background color in the Console pane and then restores it to its default value.
$psISE.Options.ConsolePaneBackgroundColor = 'orange'
$psISE.Options.RestoreDefaults()
```

### <a name="restoredefaulttokencolors"></a><span data-ttu-id="f1c38-115">RestoreDefaultTokenColors\(\)</span><span class="sxs-lookup"><span data-stu-id="f1c38-115">RestoreDefaultTokenColors\(\)</span></span>

<span data-ttu-id="f1c38-116">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-116">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-117">Stellt die Standardwerte für die Tokenfarben im Skriptbereich wieder her.</span><span class="sxs-lookup"><span data-stu-id="f1c38-117">Restores the default values of the token colors in the Script pane.</span></span>

```powershell
# Changes the color of the comments in the Script pane to red and then restores it to its default value.
$psISE.Options.TokenColors["Comment"] = 'red'
$psISE.Options.RestoreDefaultTokenColors()
```

### <a name="restoredefaultxmltokencolors"></a><span data-ttu-id="f1c38-118">RestoreDefaultXmlTokenColors\(\)</span><span class="sxs-lookup"><span data-stu-id="f1c38-118">RestoreDefaultXmlTokenColors\(\)</span></span>

<span data-ttu-id="f1c38-119">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-119">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-120">Stellt die Standardwerte für die Tokenfarben für XML-Elemente wieder her, die in Windows PowerShell ISE angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f1c38-120">Restores the default values of the token colors for XML elements that are displayed in Windows PowerShell ISE.</span></span> <span data-ttu-id="f1c38-121">Siehe auch [XmlTokenColors](#xmltokencolors).</span><span class="sxs-lookup"><span data-stu-id="f1c38-121">Also see [XmlTokenColors](#xmltokencolors).</span></span>

```powershell
# Changes the color of the comments in XML data to red and then restores it to its default value.
$psISE.Options.XmlTokenColors["Comment"] = 'red'
$psISE.Options.RestoreDefaultXmlTokenColors()
```

## <a name="properties"></a><span data-ttu-id="f1c38-122">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f1c38-122">Properties</span></span>

### <a name="autosaveminuteinterval"></a><span data-ttu-id="f1c38-123">AutoSaveMinuteInterval</span><span class="sxs-lookup"><span data-stu-id="f1c38-123">AutoSaveMinuteInterval</span></span>

<span data-ttu-id="f1c38-124">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-124">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-125">Gibt die Anzahl der Minuten zwischen automatischen Speichervorgängen Ihrer Dateien durch Windows PowerShell ISE an.</span><span class="sxs-lookup"><span data-stu-id="f1c38-125">Specifies the number of minutes between automatic save operations of your files by Windows PowerShell ISE.</span></span> <span data-ttu-id="f1c38-126">Der Standardwert beträgt 2 Minuten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-126">The default value is 2 minutes.</span></span> <span data-ttu-id="f1c38-127">Der Wert ist eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="f1c38-127">The value is an integer.</span></span>

```powershell
# Changes the number of minutes between automatic save operations to every 3 minutes.
$psISE.Options.AutoSaveMinuteInterval = 3
```

### <a name="commandpanebackgroundcolor"></a><span data-ttu-id="f1c38-128">CommandPaneBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-128">CommandPaneBackgroundColor</span></span>

<span data-ttu-id="f1c38-129">Dieses Feature ist in Windows PowerShell ISE 2.0 enthalten, wurde in höheren Versionen von ISE aber entfernt oder umbenannt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-129">This feature is present in Windows PowerShell ISE 2.0, but was removed or renamed in later versions of the ISE.</span></span>  <span data-ttu-id="f1c38-130">Informationen zu höheren Versionen finden Sie unter [ConsolePaneBackgroundColor](#consolepanebackgroundcolor).</span><span class="sxs-lookup"><span data-stu-id="f1c38-130">For later versions, see [ConsolePaneBackgroundColor](#consolepanebackgroundcolor).</span></span>

<span data-ttu-id="f1c38-131">Gibt die Hintergrundfarbe für den Befehlsbereich an.</span><span class="sxs-lookup"><span data-stu-id="f1c38-131">Specifies the background color for the Command pane.</span></span> <span data-ttu-id="f1c38-132">Dies ist eine Instanz der **System.Windows.Media.Color**-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f1c38-132">It is an instance of the **System.Windows.Media.Color** class.</span></span>

```powershell
# Changes the background color of the Command pane to orange.
$psISE.Options.CommandPaneBackgroundColor = 'orange'
```

### <a name="commandpaneup"></a><span data-ttu-id="f1c38-133">CommandPaneUp</span><span class="sxs-lookup"><span data-stu-id="f1c38-133">CommandPaneUp</span></span>

<span data-ttu-id="f1c38-134">Dieses Feature ist in Windows PowerShell ISE 2.0 enthalten, wurde in höheren Versionen von ISE aber entfernt oder umbenannt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-134">This feature is present in Windows PowerShell ISE 2.0, but was removed or renamed in later versions of the ISE.</span></span>

<span data-ttu-id="f1c38-135">Gibt an, ob sich der Befehlsbereich oberhalb des Ausgabebereichs befindet.</span><span class="sxs-lookup"><span data-stu-id="f1c38-135">Specifies whether the Command pane is located above the Output pane.</span></span>

```powershell
# Moves the Command pane to the top of the screen.
$psISE.Options.CommandPaneUp  = $true
```

### <a name="consolepanebackgroundcolor"></a><span data-ttu-id="f1c38-136">ConsolePaneBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-136">ConsolePaneBackgroundColor</span></span>

<span data-ttu-id="f1c38-137">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-137">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-138">Gibt die Hintergrundfarbe für den Konsolenbereich an.</span><span class="sxs-lookup"><span data-stu-id="f1c38-138">Specifies the background color for the Console pane.</span></span> <span data-ttu-id="f1c38-139">Dies ist eine Instanz der **System.Windows.Media.Color**-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f1c38-139">It is an instance of the **System.Windows.Media.Color** class.</span></span>

```powershell
# Changes the background color of the Console pane to red.
$psISE.Options.ConsolePaneBackgroundColor = 'red'
```

### <a name="consolepaneforegroundcolor"></a><span data-ttu-id="f1c38-140">ConsolePaneForegroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-140">ConsolePaneForegroundColor</span></span>

<span data-ttu-id="f1c38-141">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-141">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-142">Gibt die Vordergrundfarbe des Texts im Konsolenbereich an.</span><span class="sxs-lookup"><span data-stu-id="f1c38-142">Specifies the foreground color of the text in the Console pane.</span></span>

```powershell
# Changes the foreground color of the text in the Console pane to yellow.
$psISE.Options.ConsolePaneForegroundColor  = 'yellow'
```

### <a name="consolepanetextbackgroundcolor"></a><span data-ttu-id="f1c38-143">ConsolePaneTextBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-143">ConsolePaneTextBackgroundColor</span></span>

<span data-ttu-id="f1c38-144">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-144">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-145">Gibt die Hintergrundfarbe des Texts im Konsolenbereich an.</span><span class="sxs-lookup"><span data-stu-id="f1c38-145">Specifies the background color of the text in the Console pane.</span></span>

```powershell
# Changes the background color of the Console pane text to pink.
$psISE.Options.ConsolePaneTextBackgroundColor = 'pink'
```

### <a name="consoletokencolors"></a><span data-ttu-id="f1c38-146">ConsoleTokenColors</span><span class="sxs-lookup"><span data-stu-id="f1c38-146">ConsoleTokenColors</span></span>

<span data-ttu-id="f1c38-147">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-147">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-148">Gibt die Farben der IntelliSense-Token im Windows PowerShell ISE-Konsolenbereich an.</span><span class="sxs-lookup"><span data-stu-id="f1c38-148">Specifies the colors of the IntelliSense tokens in the Windows PowerShell ISE Console pane.</span></span> <span data-ttu-id="f1c38-149">Diese Eigenschaft ist ein Wörterbuchobjekt, das Name-Wert-Paare von Tokentypen und Farben für den Konsolenbereich enthält.</span><span class="sxs-lookup"><span data-stu-id="f1c38-149">This property is a dictionary object that contains name/value pairs of token types and colors for the Console pane.</span></span> <span data-ttu-id="f1c38-150">Informationen zum Ändern der Farben der IntelliSense-Token im Skriptbereich finden Sie unter [TokenColors](#tokencolors).</span><span class="sxs-lookup"><span data-stu-id="f1c38-150">To change the colors of the IntelliSense tokens in the Script pane, see [TokenColors](#tokencolors).</span></span> <span data-ttu-id="f1c38-151">Informationen zum Zurücksetzen der Farben auf die Standardwerte finden Sie unter [RestoreDefaultConsoleTokenColors](#restoredefaultconsoletokencolors).</span><span class="sxs-lookup"><span data-stu-id="f1c38-151">To reset the colors to the default values, see [RestoreDefaultConsoleTokenColors](#restoredefaultconsoletokencolors).</span></span> <span data-ttu-id="f1c38-152">Tokenfarben können für Folgendes festgelegt werden: Attribut-Befehl, CommandArgument, CommandParameter, Comment, GroupEnd, GroupStart, -Schlüsselwort, LineContinuation, LoopLabel, Member, neue-Zeile, Anzahl, Operator, Position, StatementSeparator, Zeichenfolge, Typ, unbekannt, Variable.</span><span class="sxs-lookup"><span data-stu-id="f1c38-152">Token colors can be set for the following: Attribute, Command, CommandArgument, CommandParameter, Comment, GroupEnd, GroupStart, Keyword, LineContinuation, LoopLabel, Member, NewLine, Number, Operator, Position, StatementSeparator, String, Type, Unknown, Variable.</span></span>

```powershell
# Sets the color of commands to green.
$psISE.Options.ConsoleTokenColors["Command"] = 'green'
# Sets the color of keywords to magenta.
$psISE.Options.ConsoleTokenColors["Keyword"] = 'magenta'
```

### <a name="debugbackgroundcolor"></a><span data-ttu-id="f1c38-153">DebugBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-153">DebugBackgroundColor</span></span>

<span data-ttu-id="f1c38-154">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-154">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-155">Gibt die Hintergrundfarbe für den Debugtext an, der im Konsolenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f1c38-155">Specifies the background color for the debug text that appears in the Console pane.</span></span> <span data-ttu-id="f1c38-156">Dies ist eine Instanz der **System.Windows.Media.Color**-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f1c38-156">It is an instance of the **System.Windows.Media.Color** class.</span></span>

```powershell
# Changes the background color for the debug text that appears in the Console pane to blue.
$psISE.Options.DebugBackgroundColor = '#0000FF'
```

### <a name="debugforegroundcolor"></a><span data-ttu-id="f1c38-157">DebugForegroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-157">DebugForegroundColor</span></span>

<span data-ttu-id="f1c38-158">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-158">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-159">Gibt die Vordergrundfarbe für den Debugtext an, der im Konsolenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f1c38-159">Specifies the foreground color for the debug text that appears in the Console pane.</span></span> <span data-ttu-id="f1c38-160">Dies ist eine Instanz der **System.Windows.Media.Color**-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f1c38-160">It is an instance of the **System.Windows.Media.Color** class.</span></span>

```powershell
# Changes the foreground color for the debug text that appears in the Console pane to yellow.
$psISE.Options.DebugForegroundColor = 'yellow'
```

### <a name="defaultoptions"></a><span data-ttu-id="f1c38-161">DefaultOptions</span><span class="sxs-lookup"><span data-stu-id="f1c38-161">DefaultOptions</span></span>

<span data-ttu-id="f1c38-162">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-162">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-163">Eine Sammlung von Eigenschaften, mit denen die Standardwerte angegeben werden, die bei Verwendung der Reset-Methoden verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f1c38-163">A collection of properties that specify the default values to be used when the Reset methods are used.</span></span>

```powershell
# Displays the name of the default options. This example is from ISE 4.0.
$psISE.Options.DefaultOptions

SelectedScriptPaneState                   : Top
ShowDefaultSnippets                       : True
ShowToolBar                               : True
ShowOutlining                             : True
ShowLineNumbers                           : True
TokenColors                               : {[Attribute, #FF00BFFF], [Command, #FF0000FF], [CommandArgument, #FF8A2BE2], [CommandParameter, #FF000080]...}
ConsoleTokenColors                        : {[Attribute, #FFB0C4DE], [Command, #FFE0FFFF], [CommandArgument, #FFEE82EE], [CommandParameter, #FFFFE4B5]...}
XmlTokenColors                            : {[Comment, #FF006400], [CommentDelimiter, #FF008000], [ElementName, #FF8B0000], [MarkupExtension, #FFFF8C00]...}
DefaultOptions                            : Microsoft.PowerShell.Host.ISE.ISEOptions
FontSize                                  : 9
Zoom                                      : 100
FontName                                  : Lucida Console
ErrorForegroundColor                      : #FFFF0000
ErrorBackgroundColor                      : #00FFFFFF
WarningForegroundColor                    : #FFFF8C00
WarningBackgroundColor                    : #00FFFFFF
VerboseForegroundColor                    : #FF00FFFF
VerboseBackgroundColor                    : #00FFFFFF
DebugForegroundColor                      : #FF00FFFF
DebugBackgroundColor                      : #00FFFFFF
ConsolePaneBackgroundColor                : #FF012456
ConsolePaneTextBackgroundColor            : #FF012456
ConsolePaneForegroundColor                : #FFF5F5F5
ScriptPaneBackgroundColor                 : #FFFFFFFF
ScriptPaneForegroundColor                 : #FF000000
ShowWarningForDuplicateFiles              : True
ShowWarningBeforeSavingOnRun              : True
UseLocalHelp                              : True
AutoSaveMinuteInterval                    : 2
MruCount                                  : 10
ShowIntellisenseInConsolePane             : True
ShowIntellisenseInScriptPane              : True
UseEnterToSelectInConsolePaneIntellisense : True
UseEnterToSelectInScriptPaneIntellisense  : True
IntellisenseTimeoutInSeconds              : 3
```

### <a name="errorbackgroundcolor"></a><span data-ttu-id="f1c38-164">ErrorBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-164">ErrorBackgroundColor</span></span>

<span data-ttu-id="f1c38-165">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-165">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-166">Gibt die Hintergrundfarbe für den Fehlertext an, der im Konsolenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f1c38-166">Specifies the background color for error text that appears in the Console pane.</span></span> <span data-ttu-id="f1c38-167">Dies ist eine Instanz der **System.Windows.Media.Color**-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f1c38-167">It is an instance of the **System.Windows.Media.Color** class.</span></span>

```powershell
# Changes the background color for the error text that appears in the Console pane to black.
$psISE.Options.ErrorBackgroundColor = 'black'
```

### <a name="errorforegroundcolor"></a><span data-ttu-id="f1c38-168">ErrorForegroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-168">ErrorForegroundColor</span></span>

<span data-ttu-id="f1c38-169">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-169">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-170">Gibt die Vordergrundfarbe für den Fehlertext an, der im Konsolenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f1c38-170">Specifies the foreground color for error text that appears in the Console pane.</span></span> <span data-ttu-id="f1c38-171">Dies ist eine Instanz der **System.Windows.Media.Color**-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f1c38-171">It is an instance of the **System.Windows.Media.Color** class.</span></span>

```powershell
# Changes the foreground color for the error text that appears in the console pane to green.
$psISE.Options.ErrorForegroundColor = 'green'
```

### <a name="fontname"></a><span data-ttu-id="f1c38-172">FontName</span><span class="sxs-lookup"><span data-stu-id="f1c38-172">FontName</span></span>

<span data-ttu-id="f1c38-173">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-173">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-174">Gibt den Namen der Schriftart an, die derzeit im Skriptbereich und im Konsolenbereich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f1c38-174">Specifies the font name currently in use in both the Script pane and the Console pane.</span></span>

```powershell
# Changes the font used in both panes.
$psISE.Options.FontName = 'Courier New'
```

### <a name="fontsize"></a><span data-ttu-id="f1c38-175">FontSize</span><span class="sxs-lookup"><span data-stu-id="f1c38-175">FontSize</span></span>

<span data-ttu-id="f1c38-176">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-176">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-177">Gibt den Schriftgrad als ganze Zahl an.</span><span class="sxs-lookup"><span data-stu-id="f1c38-177">Specifies the font size as an integer.</span></span> <span data-ttu-id="f1c38-178">Dieser wird im Skriptbereich, Befehlsbereich und Ausgabebereich verwendet.</span><span class="sxs-lookup"><span data-stu-id="f1c38-178">It is used in the Script pane, the Command pane, and the Output pane.</span></span> <span data-ttu-id="f1c38-179">Der gültige Wertebereich liegt zwischen 8 und 32.</span><span class="sxs-lookup"><span data-stu-id="f1c38-179">The valid range of values is 8 through 32.</span></span>

```powershell
# Changes the font size in all panes.
$psISE.Options.FontSize = 20
```

### <a name="intellisensetimeoutinseconds"></a><span data-ttu-id="f1c38-180">IntellisenseTimeoutInSeconds</span><span class="sxs-lookup"><span data-stu-id="f1c38-180">IntellisenseTimeoutInSeconds</span></span>

<span data-ttu-id="f1c38-181">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-181">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-182">Gibt in Sekunden an, wie lange IntelliSense versucht, den gerade eingegebenen Text aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="f1c38-182">Specifies the number of seconds that IntelliSense uses to try to resolve the currently typed text.</span></span> <span data-ttu-id="f1c38-183">Nach dieser Anzahl von Sekunden tritt in IntelliSense eine Zeitüberschreitung auf, und Sie können mit der Eingabe fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f1c38-183">After this number of seconds, IntelliSense times out and enables you to continue typing.</span></span> <span data-ttu-id="f1c38-184">Der Standardwert sind 3 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="f1c38-184">The default value is 3 seconds.</span></span> <span data-ttu-id="f1c38-185">Der Wert ist eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="f1c38-185">The value is an integer.</span></span>

```powershell
# Changes the number of seconds for IntelliSense syntax recognition to 5.
$psISE.Options.IntellisenseTimeoutInSeconds = 5
```

### <a name="mrucount"></a><span data-ttu-id="f1c38-186">MruCount</span><span class="sxs-lookup"><span data-stu-id="f1c38-186">MruCount</span></span>

<span data-ttu-id="f1c38-187">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-187">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-188">Gibt die Anzahl der zuletzt geöffneten Dateien an, die Windows PowerShell ISE nachverfolgt und am unteren Rand des Menüs **Datei öffnen** anzeigt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-188">Specifies the number of recently opened files that Windows PowerShell ISE tracks and displays at the bottom of the **File Open** menu.</span></span> <span data-ttu-id="f1c38-189">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="f1c38-189">The default value is 10.</span></span> <span data-ttu-id="f1c38-190">Der Wert ist eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="f1c38-190">The value is an integer.</span></span>

```powershell
# Changes the number of recently used files that appear at the bottom of the File Open menu to 5.
$psISE.Options.MruCount = 5
```

### <a name="outputpanebackgroundcolor"></a><span data-ttu-id="f1c38-191">OutputPaneBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-191">OutputPaneBackgroundColor</span></span>

<span data-ttu-id="f1c38-192">Dieses Feature ist in Windows PowerShell ISE 2.0 enthalten, wurde in höheren Versionen von ISE aber entfernt oder umbenannt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-192">This feature is present in Windows PowerShell ISE 2.0, but was removed or renamed in later versions of the ISE.</span></span>  <span data-ttu-id="f1c38-193">Informationen zu höheren Versionen finden Sie unter [ConsolePaneBackgroundColor](#consolepanebackgroundcolor).</span><span class="sxs-lookup"><span data-stu-id="f1c38-193">For later versions, see [ConsolePaneBackgroundColor](#consolepanebackgroundcolor).</span></span>

<span data-ttu-id="f1c38-194">Die Lese-/Schreibeigenschaft, die die Hintergrundfarbe für den Ausgabebereich selbst abruft oder festlegt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-194">The read/write property that gets or sets the background color for the Output pane itself.</span></span> <span data-ttu-id="f1c38-195">Dies ist eine Instanz der **System.Windows.Media.Color**-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f1c38-195">It is an instance of the **System.Windows.Media.Color** class.</span></span>

```powershell
# Changes the background color of the Output pane to gold.
$psISE.Options.OutputPaneForegroundColor = 'gold'
```

### <a name="outputpanetextforegroundcolor"></a><span data-ttu-id="f1c38-196">OutputPaneTextForegroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-196">OutputPaneTextForegroundColor</span></span>

<span data-ttu-id="f1c38-197">Dieses Feature ist in Windows PowerShell ISE 2.0 enthalten, wurde in höheren Versionen von ISE aber entfernt oder umbenannt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-197">This feature is present in Windows PowerShell ISE 2.0, but was removed or renamed in later versions of the ISE.</span></span>  <span data-ttu-id="f1c38-198">Informationen zu höheren Versionen finden Sie unter [ConsolePaneForegroundColor](#consolepaneforegroundcolor).</span><span class="sxs-lookup"><span data-stu-id="f1c38-198">For later versions, see [ConsolePaneForegroundColor](#consolepaneforegroundcolor).</span></span>

<span data-ttu-id="f1c38-199">Die Lese-/Schreibeigenschaft, mit der die Vordergrundfarbe des Texts im Ausgabereich in Windows PowerShell ISE 2.0 geändert wird.</span><span class="sxs-lookup"><span data-stu-id="f1c38-199">The read/write property that changes the foreground color of the text in the Output pane in Windows PowerShell ISE 2.0.</span></span>

```powershell
# Changes the foreground color of the text in the Output Pane to blue.
$psISE.Options.OutputPaneTextForegroundColor  = 'blue'
```

### <a name="outputpanetextbackgroundcolor"></a><span data-ttu-id="f1c38-200">OutputPaneTextBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-200">OutputPaneTextBackgroundColor</span></span>

<span data-ttu-id="f1c38-201">Dieses Feature ist in Windows PowerShell ISE 2.0 enthalten, wurde in höheren Versionen von ISE aber entfernt oder umbenannt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-201">This feature is present in Windows PowerShell ISE 2.0, but was removed or renamed in later versions of the ISE.</span></span>  <span data-ttu-id="f1c38-202">Informationen zu höheren Versionen finden Sie unter [ConsolePaneTextBackgroundColor](#consolepanetextbackgroundcolor).</span><span class="sxs-lookup"><span data-stu-id="f1c38-202">For later versions, see [ConsolePaneTextBackgroundColor](#consolepanetextbackgroundcolor).</span></span>

<span data-ttu-id="f1c38-203">Die Lese-/Schreibeigenschaft, mit der die Hintergrundfarbe des Texts im Ausgabereich geändert wird.</span><span class="sxs-lookup"><span data-stu-id="f1c38-203">The read/write property that changes the background color of the text in the Output pane.</span></span>

```powershell
# Changes the background color of the Output pane text to pink.
$psISE.Options.OutputPaneTextBackgroundColor = 'pink'
```

### <a name="scriptpanebackgroundcolor"></a><span data-ttu-id="f1c38-204">ScriptPaneBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-204">ScriptPaneBackgroundColor</span></span>

<span data-ttu-id="f1c38-205">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-205">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-206">Die Lese-/Schreibeigenschaft, mit der die Hintergrundfarbe für Dateien abgerufen oder festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="f1c38-206">The read/write property that gets or sets the background color for files.</span></span> <span data-ttu-id="f1c38-207">Dies ist eine Instanz der **System.Windows.Media.Color**-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f1c38-207">It is an instance of the **System.Windows.Media.Color** class.</span></span>

```powershell
# Sets the color of the script pane background to yellow.
$psISE.Options.ScriptPaneBackgroundColor = 'yellow'
```

### <a name="scriptpaneforegroundcolor"></a><span data-ttu-id="f1c38-208">ScriptPaneForegroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-208">ScriptPaneForegroundColor</span></span>

<span data-ttu-id="f1c38-209">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-209">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-210">Die Lese-/Schreibeigenschaft, mit der die Vordergrundfarbe für Nicht-Skriptdateien im Skriptbereich abgerufen oder festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="f1c38-210">The read/write property that gets or sets the foreground color for non-script files in the Script pane.</span></span>
<span data-ttu-id="f1c38-211">Verwenden Sie [TokenColors](#tokencolors) zum Festlegen der Vordergrundfarbe für Skriptdateien.</span><span class="sxs-lookup"><span data-stu-id="f1c38-211">To set the foreground color for script files, use the [TokenColors](#tokencolors).</span></span>

```powershell
# Sets the foreground to color of non-script files in the script pane to green.
$psISE.Options.ScriptPaneBackgroundColor = 'green'
```

### <a name="selectedscriptpanestate"></a><span data-ttu-id="f1c38-212">SelectedScriptPaneState</span><span class="sxs-lookup"><span data-stu-id="f1c38-212">SelectedScriptPaneState</span></span>

<span data-ttu-id="f1c38-213">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-213">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-214">Die Lese-/Schreibeigenschaft, die die Position des Skriptbereichs in der Anzeige abruft oder festlegt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-214">The read/write property that gets or sets the position of the Script pane on the display.</span></span> <span data-ttu-id="f1c38-215">Die Zeichenfolge kann „Maximized“, „Top“ oder „Right“ lauten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-215">The string can be either 'Maximized', 'Top', or 'Right'.</span></span>

```powershell
# Moves the Script Pane to the top.
$psISE.Options.SelectedScriptPaneState = 'Top'
# Moves the Script Pane to the right.
$psISE.Options.SelectedScriptPaneState = 'Right'
# Maximizes the Script Pane
$psISE.Options.SelectedScriptPaneState = 'Maximized'
```

### <a name="showdefaultsnippets"></a><span data-ttu-id="f1c38-216">ShowDefaultSnippets</span><span class="sxs-lookup"><span data-stu-id="f1c38-216">ShowDefaultSnippets</span></span>

<span data-ttu-id="f1c38-217">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-217">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-218">Gibt an, ob die **STRG+J**-Codeausschnittliste den in Windows PowerShell enthaltenen Startersatz umfasst.</span><span class="sxs-lookup"><span data-stu-id="f1c38-218">Specifies whether the **CTRL+J** list of snippets includes the starter set that is included in Windows PowerShell.</span></span> <span data-ttu-id="f1c38-219">Bei **$false** werden nur benutzerdefinierte Codeausschnitte in der **STRG+J**-Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-219">When set to **$false**, only user-defined snippets appear in the **CTRL+J** list.</span></span> <span data-ttu-id="f1c38-220">Der Standardwert ist **$true**.</span><span class="sxs-lookup"><span data-stu-id="f1c38-220">The default value is **$true**.</span></span>

```powershell
# Hide the default snippets from the CTRL+J list.
$psISE.Options.ShowDefaultSnippets = $false
```

### <a name="showintellisenseinconsolepane"></a><span data-ttu-id="f1c38-221">ShowIntellisenseInConsolePane</span><span class="sxs-lookup"><span data-stu-id="f1c38-221">ShowIntellisenseInConsolePane</span></span>

<span data-ttu-id="f1c38-222">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-222">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-223">Gibt an, ob IntelliSense Syntax-, Parameter- und Wertvorschläge im Konsolenbereich anzeigt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-223">Specifies whether IntelliSense offers syntax, parameter, and value suggestions in the Console pane.</span></span> <span data-ttu-id="f1c38-224">Der Standardwert ist **$true**.</span><span class="sxs-lookup"><span data-stu-id="f1c38-224">The default value is **$true**.</span></span>

```powershell
# Turn off IntelliSense in the console pane.
$psISE.Options.ShowIntellisenseInConsolePane = $false
```

### <a name="showintellisenseinscriptpane"></a><span data-ttu-id="f1c38-225">ShowIntellisenseInScriptPane</span><span class="sxs-lookup"><span data-stu-id="f1c38-225">ShowIntellisenseInScriptPane</span></span>

<span data-ttu-id="f1c38-226">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-226">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-227">Gibt an, ob IntelliSense Syntax-, Parameter- und Wertvorschläge im Skriptbereich anzeigt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-227">Specifies whether IntelliSense offers syntax, parameter, and value suggestions in the Script pane.</span></span> <span data-ttu-id="f1c38-228">Der Standardwert ist **$true**.</span><span class="sxs-lookup"><span data-stu-id="f1c38-228">The default value is **$true**.</span></span>

```powershell
# Turn off IntelliSense in the Script pane.
$psISE.Options.ShowIntellisenseInScriptPane = $false
```

### <a name="showlinenumbers"></a><span data-ttu-id="f1c38-229">ShowLineNumbers</span><span class="sxs-lookup"><span data-stu-id="f1c38-229">ShowLineNumbers</span></span>

<span data-ttu-id="f1c38-230">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-230">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-231">Gibt an, ob im Skriptbereich Zeilennummern am linken Rand angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f1c38-231">Specifies whether the Script pane displays line numbers in the left margin.</span></span> <span data-ttu-id="f1c38-232">Der Standardwert ist **$true**.</span><span class="sxs-lookup"><span data-stu-id="f1c38-232">The default value is **$true**.</span></span>

```powershell
# Turn off line numbers in the Script pane.
$psISE.Options.ShowLineNumbers = $false
```

### <a name="showoutlining"></a><span data-ttu-id="f1c38-233">ShowOutlining</span><span class="sxs-lookup"><span data-stu-id="f1c38-233">ShowOutlining</span></span>

<span data-ttu-id="f1c38-234">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-234">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-235">Gibt an, ob im Skriptbereich erweiterbare und reduzierbare Klammern neben Codeabschnitten am linken Rand angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f1c38-235">Specifies whether the Script pane displays expandable and collapsible brackets next to sections of code in the left margin.</span></span> <span data-ttu-id="f1c38-236">Wenn sie angezeigt werden, können Sie auf das Minuszeichen \(-\) neben einem Textblock klicken, um ihn zuzuklappen, oder auf das Pluszeichen \(+\), um einen Textblock auszuklappen.</span><span class="sxs-lookup"><span data-stu-id="f1c38-236">When they are displayed, you can click the minus \(-\) icons next to a block of text to collapse it or click the plus \(+\) icon to expand a block of text.</span></span> <span data-ttu-id="f1c38-237">Der Standardwert ist **$true**.</span><span class="sxs-lookup"><span data-stu-id="f1c38-237">The default value is **$true**.</span></span>

```powershell
# Turn off outlining in the Script pane.
$psISE.Options.ShowOutlining = $false
```

### <a name="showtoolbar"></a><span data-ttu-id="f1c38-238">ShowToolBar</span><span class="sxs-lookup"><span data-stu-id="f1c38-238">ShowToolBar</span></span>

<span data-ttu-id="f1c38-239">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-239">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-240">Gibt an, ob die ISE-Symbolleiste am oberen Rand des Windows PowerShell ISE-Fensters angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f1c38-240">Specifies whether the ISE toolbar appears at the top of the Windows PowerShell ISE window.</span></span> <span data-ttu-id="f1c38-241">Der Standardwert ist **$true**.</span><span class="sxs-lookup"><span data-stu-id="f1c38-241">The default value is **$true**.</span></span>

```powershell
# Show the toolbar.
$psISE.Options.ShowToolBar = $true
```

### <a name="showwarningbeforesavingonrun"></a><span data-ttu-id="f1c38-242">ShowWarningBeforeSavingOnRun</span><span class="sxs-lookup"><span data-stu-id="f1c38-242">ShowWarningBeforeSavingOnRun</span></span>

<span data-ttu-id="f1c38-243">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-243">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-244">Gibt an, ob eine Warnung angezeigt wird, wenn ein Skript vor dem Ausführen automatisch gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f1c38-244">Specifies whether a warning message appears when a script is saved automatically before it is run.</span></span> <span data-ttu-id="f1c38-245">Der Standardwert ist **$true**.</span><span class="sxs-lookup"><span data-stu-id="f1c38-245">The default value is **$true**.</span></span>

```powershell
# Enable the warning message when an attempt
# is made to run a script without saving it first.
$psISE.Options.ShowWarningBeforeSavingOnRun = $true
```

### <a name="showwarningforduplicatefiles"></a><span data-ttu-id="f1c38-246">ShowWarningForDuplicateFiles</span><span class="sxs-lookup"><span data-stu-id="f1c38-246">ShowWarningForDuplicateFiles</span></span>

<span data-ttu-id="f1c38-247">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-247">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-248">Gibt an, ob eine Warnung angezeigt wird, wenn die gleiche Datei auf mehreren PowerShell-Registerkarten geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="f1c38-248">Specifies whether a warning message appears when the same file is opened in different PowerShell tabs.</span></span> <span data-ttu-id="f1c38-249">Wenn auf festgelegt **$true**, um der gleichen Datei in mehrere Registerkarten zeigt diese Meldung zu öffnen: "Eine Kopie dieser Datei ist in einer anderen Windows PowerShell-Registerkarte geöffnet. Änderungen an dieser Datei betreffen alle geöffneten Kopien.“</span><span class="sxs-lookup"><span data-stu-id="f1c38-249">If set to **$true**, to open the same file in multiple tabs displays this message: "A copy of this file is open in another Windows PowerShell tab. Changes made to this file will affect all open copies."</span></span> <span data-ttu-id="f1c38-250">Der Standardwert ist **$true**.</span><span class="sxs-lookup"><span data-stu-id="f1c38-250">The default value is **$true**.</span></span>

```powershell
# Enable the warning message when a file is
# opened in multiple PowerShell tabs.
$psISE.Options.ShowWarningForDuplicateFiles = $true
```

### <a name="tokencolors"></a><span data-ttu-id="f1c38-251">TokenColors</span><span class="sxs-lookup"><span data-stu-id="f1c38-251">TokenColors</span></span>

<span data-ttu-id="f1c38-252">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-252">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-253">Gibt die Farben der IntelliSense-Token im Windows PowerShell ISE-Skriptbereich an.</span><span class="sxs-lookup"><span data-stu-id="f1c38-253">Specifies the colors of the IntelliSense tokens in the Windows PowerShell ISE Script pane.</span></span> <span data-ttu-id="f1c38-254">Diese Eigenschaft ist ein Wörterbuchobjekt, das Name-Wert-Paare von Tokentypen und Farben für den Skriptbereich enthält.</span><span class="sxs-lookup"><span data-stu-id="f1c38-254">This property is a dictionary object that contains name/value pairs of token types and colors for the Script pane.</span></span> <span data-ttu-id="f1c38-255">Informationen zum Ändern der Farben der IntelliSense-Token im Konsolenbereich finden Sie unter [ConsoleTokenColors](#consoletokencolors).</span><span class="sxs-lookup"><span data-stu-id="f1c38-255">To change the colors of the IntelliSense tokens in the Console pane, see [ConsoleTokenColors](#consoletokencolors).</span></span> <span data-ttu-id="f1c38-256">Informationen zum Zurücksetzen der Farben auf die Standardwerte finden Sie unter [RestoreDefaultTokenColors](#restoredefaulttokencolors).</span><span class="sxs-lookup"><span data-stu-id="f1c38-256">To reset the colors to the default values, see [RestoreDefaultTokenColors](#restoredefaulttokencolors).</span></span> <span data-ttu-id="f1c38-257">Tokenfarben können für Folgendes festgelegt werden: Attribut-Befehl, CommandArgument, CommandParameter, Comment, GroupEnd, GroupStart, -Schlüsselwort, LineContinuation, LoopLabel, Member, neue-Zeile, Anzahl, Operator, Position, StatementSeparator, Zeichenfolge, Typ, unbekannt, Variable.</span><span class="sxs-lookup"><span data-stu-id="f1c38-257">Token colors can be set for the following: Attribute, Command, CommandArgument, CommandParameter, Comment, GroupEnd, GroupStart, Keyword, LineContinuation, LoopLabel, Member, NewLine, Number, Operator, Position, StatementSeparator, String, Type, Unknown, Variable.</span></span>

```powershell
# Sets the color of commands to green.
$psISE.Options.TokenColors["Command"] = "green"
# Sets the color of keywords to magenta.
$psISE.Options.TokenColors["Keyword"] = "magenta"
```

### <a name="useentertoselectinconsolepaneintellisense"></a><span data-ttu-id="f1c38-258">UseEnterToSelectInConsolePaneIntellisense</span><span class="sxs-lookup"><span data-stu-id="f1c38-258">UseEnterToSelectInConsolePaneIntellisense</span></span>

<span data-ttu-id="f1c38-259">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-259">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-260">Gibt an, ob Sie mit der Eingabetaste eine von IntelliSense bereitgestellte Option im Konsolenbereich auswählen können.</span><span class="sxs-lookup"><span data-stu-id="f1c38-260">Specifies whether you can use the Enter key to select an IntelliSense provided option in the Console pane.</span></span> <span data-ttu-id="f1c38-261">Der Standardwert ist **$true**.</span><span class="sxs-lookup"><span data-stu-id="f1c38-261">The default value is **$true**.</span></span>

```powershell
# Turn off using the ENTER key to select an IntelliSense provided option in the Console pane.
$psISE.Options.UseEnterToSelectInConsolePaneIntellisense = $false
```

### <a name="useentertoselectinscriptpaneintellisense"></a><span data-ttu-id="f1c38-262">UseEnterToSelectInScriptPaneIntellisense</span><span class="sxs-lookup"><span data-stu-id="f1c38-262">UseEnterToSelectInScriptPaneIntellisense</span></span>

<span data-ttu-id="f1c38-263">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-263">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-264">Gibt an, ob Sie mit der Eingabetaste eine von IntelliSense bereitgestellte Option im Skriptbereich auswählen können.</span><span class="sxs-lookup"><span data-stu-id="f1c38-264">Specifies whether you can use the Enter key to select an IntelliSense-provided option in the Script pane.</span></span> <span data-ttu-id="f1c38-265">Der Standardwert ist **$true**.</span><span class="sxs-lookup"><span data-stu-id="f1c38-265">The default value is **$true**.</span></span>

```powershell
# Turn on using the Enter key to select an IntelliSense provided option in the Console pane.
$psISE.Options.UseEnterToSelectInConsolePaneIntellisense = $true
```

### <a name="uselocalhelp"></a><span data-ttu-id="f1c38-266">UseLocalHelp</span><span class="sxs-lookup"><span data-stu-id="f1c38-266">UseLocalHelp</span></span>

<span data-ttu-id="f1c38-267">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-267">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-268">Gibt an, ob die lokal installierte Hilfe oder die Onlinehilfe der TechNet-Bibliothek angezeigt wird, wenn der Cursor auf einem Schlüsselwort positioniert ist und Sie F1 drücken.</span><span class="sxs-lookup"><span data-stu-id="f1c38-268">Specifies whether the locally installed Help or the online TechNet Library Help appears when you press F1 with the cursor positioned in a keyword.</span></span> <span data-ttu-id="f1c38-269">Wenn dies auf **$true** festgelegt ist, werden in einem Popupfenster Inhalte aus der lokal installierten Hilfe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-269">If set to **$true**, then a pop-up window shows content from the locally installed Help.</span></span> <span data-ttu-id="f1c38-270">Sie können die Hilfedateien mit dem Befehl `Update-Help` installieren.</span><span class="sxs-lookup"><span data-stu-id="f1c38-270">You can install the Help files by running the `Update-Help` command.</span></span> <span data-ttu-id="f1c38-271">Wenn dies auf **$false** festgelegt ist, wird eine Seite in der TechNet-Bibliothek im Browser geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f1c38-271">If set to **$false**, then your browser opens to a page in the TechNet Library.</span></span>

```powershell
# Sets the option for the online help to be displayed.
$psISE.Options.UseLocalHelp = $false
# Sets the option for the local Help to be displayed.
$psISE.Options.UseLocalHelp = $true
```

### <a name="verbosebackgroundcolor"></a><span data-ttu-id="f1c38-272">VerboseBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-272">VerboseBackgroundColor</span></span>

<span data-ttu-id="f1c38-273">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-273">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-274">Gibt die Hintergrundfarbe für ausführlichen Text an, der im Konsolenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f1c38-274">Specifies the background color for verbose text that appears in the Console pane.</span></span> <span data-ttu-id="f1c38-275">Dies ist ein **System.Windows.Media.Color**-Objekt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-275">It is a **System.Windows.Media.Color** object.</span></span>

```powershell
# Changes the background color for verbose text to blue.
$psISE.Options.VerboseBackgroundColor ='#0000FF'
```

### <a name="verboseforegroundcolor"></a><span data-ttu-id="f1c38-276">VerboseForegroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-276">VerboseForegroundColor</span></span>

<span data-ttu-id="f1c38-277">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-277">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-278">Gibt die Vordergrundfarbe für ausführlichen Text an, der im Konsolenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f1c38-278">Specifies the foreground color for verbose text that appears in the Console pane.</span></span> <span data-ttu-id="f1c38-279">Dies ist ein **System.Windows.Media.Color**-Objekt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-279">It is a **System.Windows.Media.Color** object.</span></span>

```powershell
# Changes the foreground color for verbose text to yellow.
$psISE.Options.VerboseForegroundColor = 'yellow'
```

### <a name="warningbackgroundcolor"></a><span data-ttu-id="f1c38-280">WarningBackgroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-280">WarningBackgroundColor</span></span>

<span data-ttu-id="f1c38-281">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-281">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-282">Gibt die Hintergrundfarbe für Warntext an, der im Konsolenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f1c38-282">Specifies the background color for warning text that appears in the Console pane.</span></span> <span data-ttu-id="f1c38-283">Dies ist ein **System.Windows.Media.Color**-Objekt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-283">It is a **System.Windows.Media.Color** object.</span></span>

```powershell
# Changes the background color for warning text to blue.
$psISE.Options.WarningBackgroundColor = '#0000FF'
```

### <a name="warningforegroundcolor"></a><span data-ttu-id="f1c38-284">WarningForegroundColor</span><span class="sxs-lookup"><span data-stu-id="f1c38-284">WarningForegroundColor</span></span>

<span data-ttu-id="f1c38-285">In Windows PowerShell ISE 2.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-285">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f1c38-286">Gibt die Vordergrundfarbe für Warntext an, der im Ausgabebereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f1c38-286">Specifies the foreground color for warning text that appears in the Output pane.</span></span> <span data-ttu-id="f1c38-287">Dies ist ein **System.Windows.Media.Color**-Objekt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-287">It is a **System.Windows.Media.Color** object.</span></span>

```powershell
# Changes the foreground color for warning text to yellow.
$psISE.Options.WarningForegroundColor = 'yellow'
```

### <a name="xmltokencolors"></a><span data-ttu-id="f1c38-288">XmlTokenColors</span><span class="sxs-lookup"><span data-stu-id="f1c38-288">XmlTokenColors</span></span>

<span data-ttu-id="f1c38-289">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-289">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-290">Gibt ein Wörterbuchobjekt an, das Name-Wert-Paare von Tokentypen und Farben für XML-Inhalte enthält, die in Windows PowerShell ISE angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f1c38-290">Specifies a dictionary object that contains name/value pairs of token types and colors for XML content that is displayed in Windows PowerShell ISE.</span></span> <span data-ttu-id="f1c38-291">Tokenfarben können für Folgendes festgelegt werden: Attribut-Befehl, CommandArgument, CommandParameter, Comment, GroupEnd, GroupStart, -Schlüsselwort, LineContinuation, LoopLabel, Member, neue-Zeile, Anzahl, Operator, Position, StatementSeparator, Zeichenfolge, Typ, unbekannt, Variable.</span><span class="sxs-lookup"><span data-stu-id="f1c38-291">Token colors can be set for the following: Attribute, Command, CommandArgument, CommandParameter, Comment, GroupEnd, GroupStart, Keyword, LineContinuation, LoopLabel, Member, NewLine, Number, Operator, Position, StatementSeparator, String, Type, Unknown, Variable.</span></span> <span data-ttu-id="f1c38-292">Siehe auch [RestoreDefaultXmlTokenColors](#restoredefaultxmltokencolors).</span><span class="sxs-lookup"><span data-stu-id="f1c38-292">Also see [RestoreDefaultXmlTokenColors](#restoredefaultxmltokencolors).</span></span>

```powershell
# Sets the color of XML element names to green.
$psISE.Options.XmlTokenColors["ElementName"] = 'green'
# Sets the color of XML comments to magenta.
$psISE.Options.XmlTokenColors["Comment"] = 'magenta'
```

### <a name="zoom"></a><span data-ttu-id="f1c38-293">Zoom</span><span class="sxs-lookup"><span data-stu-id="f1c38-293">Zoom</span></span>

<span data-ttu-id="f1c38-294">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1c38-294">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="f1c38-295">Gibt die relative Größe des Texts im Konsolenbereich und Skriptbereich an.</span><span class="sxs-lookup"><span data-stu-id="f1c38-295">Specifies the relative size of text in both the Console and Script panes.</span></span> <span data-ttu-id="f1c38-296">Der Standardwert ist 100.</span><span class="sxs-lookup"><span data-stu-id="f1c38-296">The default value is 100.</span></span> <span data-ttu-id="f1c38-297">Bei kleineren Werten wird der Text in Windows PowerShell ISE kleiner angezeigt, bei größeren Werten wird er größer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1c38-297">Smaller values cause the text in Windows PowerShell ISE to appear smaller while larger numbers cause text to appear larger.</span></span> <span data-ttu-id="f1c38-298">Der Wert ist eine ganze Zahl zwischen 20 und 400.</span><span class="sxs-lookup"><span data-stu-id="f1c38-298">The value is an integer that ranges from 20 to 400.</span></span>

```powershell
# Changes the text in the Windows PowerShell ISE to be double its normal size.
$psISE.Options.Zoom = 200
```

## <a name="see-also"></a><span data-ttu-id="f1c38-299">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1c38-299">See Also</span></span>

- [<span data-ttu-id="f1c38-300">Zweck des Windows PowerShell ISE-Skriptobjektmodells</span><span class="sxs-lookup"><span data-stu-id="f1c38-300">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="f1c38-301">Die ISE-Objektmodellhierarchie</span><span class="sxs-lookup"><span data-stu-id="f1c38-301">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)