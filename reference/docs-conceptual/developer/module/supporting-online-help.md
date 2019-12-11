---
title: Unterstützung der Online Hilfe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3204599c-7159-47aa-82ec-4a476f461027
caps.latest.revision: 7
ms.openlocfilehash: 5c5707d1c533e0498c6794b60f4499e530e25813
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360659"
---
# <a name="supporting-online-help"></a><span data-ttu-id="30687-102">Unterstützung für Onlinehilfe</span><span class="sxs-lookup"><span data-stu-id="30687-102">Supporting Online Help</span></span>

<span data-ttu-id="30687-103">Ab Windows PowerShell 3,0 gibt es zwei Möglichkeiten, das `Get-Help`-Online Feature für Windows PowerShell-Befehle zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="30687-103">Beginning in Windows PowerShell 3.0, there are two ways to support the `Get-Help` Online feature for Windows PowerShell commands.</span></span> <span data-ttu-id="30687-104">In diesem Thema wird erläutert, wie diese Funktion für verschiedene Befehls Typen implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="30687-104">This topic explains how to implement this feature for different command types.</span></span>

## <a name="about-online-help"></a><span data-ttu-id="30687-105">Informationen zur Online Hilfe</span><span class="sxs-lookup"><span data-stu-id="30687-105">About Online Help</span></span>

<span data-ttu-id="30687-106">Die Online Hilfe war immer ein wesentlicher Bestandteil von Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30687-106">Online help has always been a vital part of Windows PowerShell.</span></span> <span data-ttu-id="30687-107">Obwohl das Cmdlet "`Get-Help`" Hilfe Themen an der Eingabeaufforderung anzeigt, bevorzugen viele Benutzer das Lesen der Online Dokumentation, einschließlich Farbcodierung, Hyperlinks und Freigabe von Ideen in Communityinhalten und Wiki-basierten Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="30687-107">Although the `Get-Help` cmdlet displays help topics at the command prompt, many users prefer the experience of reading online, including color-coding, hyperlinks, and sharing ideas in Community Content and wiki-based documents.</span></span> <span data-ttu-id="30687-108">Vor der Einführung der aktualisierbaren Hilfe stellte die Online Hilfe die aktuelle Version der Hilfedateien bereit.</span><span class="sxs-lookup"><span data-stu-id="30687-108">Most importantly, before the advent of Updatable Help, online help provided the most up-to-date version of the help files.</span></span>

<span data-ttu-id="30687-109">Mit der Einführung der aktualisierbaren Hilfe in Windows PowerShell 3,0 spielt die Online Hilfe immer noch eine wichtige Rolle.</span><span class="sxs-lookup"><span data-stu-id="30687-109">With the advent of Updatable Help in Windows PowerShell 3.0, online help still plays a vital role.</span></span> <span data-ttu-id="30687-110">Zusätzlich zur flexiblen Benutzer Darstellung bietet die Online Hilfe Benutzern Hilfe, die keine aktualisierbare Hilfe zum Herunterladen von Hilfe Themen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="30687-110">In addition to the flexible user experience, online help provides help to users who do not or cannot use Updatable Help to download help topics.</span></span>

## <a name="how-get-help--online-works"></a><span data-ttu-id="30687-111">Funktionsweise von "Get-Help-Online"</span><span class="sxs-lookup"><span data-stu-id="30687-111">How Get-Help -Online Works</span></span>

<span data-ttu-id="30687-112">Um Benutzern die Suche nach den Online Hilfe Themen für Befehle zu erleichtern, hat der `Get-Help`-Befehl einen Online-Parameter, der die Online Version des Hilfe Themas für einen Befehl im Standard Internet Browser des Benutzers öffnet.</span><span class="sxs-lookup"><span data-stu-id="30687-112">To help users find the online help topics for commands, the `Get-Help` command has an Online parameter that opens the online version of help topic for a command in the user's default Internet browser.</span></span>

<span data-ttu-id="30687-113">Der folgende Befehl öffnet z. b. das Online Hilfethema für das Cmdlet "`Invoke-Command`".</span><span class="sxs-lookup"><span data-stu-id="30687-113">For example, the following command opens the online help topic for the `Invoke-Command` cmdlet.</span></span>

```powershell
Get-Help Invoke-Command -Online
```

<span data-ttu-id="30687-114">Um `Get-Help`-Online zu implementieren, sucht das `Get-Help`-Cmdlet in den folgenden Speicherorten nach einem Uniform Resource Identifier (URI) für das Hilfethema der Online Version.</span><span class="sxs-lookup"><span data-stu-id="30687-114">To implement `Get-Help` -Online, the `Get-Help` cmdlet looks for a Uniform Resource Identifier (URI) for the online version help topic in the following locations.</span></span>

- <span data-ttu-id="30687-115">Der erste Link im Abschnitt "Verwandte Links" des Hilfe Themas für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="30687-115">The first link in the Related Links section of the help topic for the command.</span></span> <span data-ttu-id="30687-116">Das Hilfethema muss auf dem Computer des Benutzers installiert sein.</span><span class="sxs-lookup"><span data-stu-id="30687-116">The help topic must be installed on the user's computer.</span></span> <span data-ttu-id="30687-117">Diese Funktion wurde in Windows PowerShell 2,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="30687-117">This feature was introduced in Windows PowerShell 2.0.</span></span>

- <span data-ttu-id="30687-118">Die HelpUri-Eigenschaft eines beliebigen Befehls.</span><span class="sxs-lookup"><span data-stu-id="30687-118">The HelpUri property of any command.</span></span> <span data-ttu-id="30687-119">Der Zugriff auf die HelpUri-Eigenschaft ist auch dann möglich, wenn das Hilfethema für den Befehl nicht auf dem Computer des Benutzers installiert ist.</span><span class="sxs-lookup"><span data-stu-id="30687-119">The HelpUri property is accessible even when the help topic for the command is not installed on the user's computer.</span></span> <span data-ttu-id="30687-120">Diese Funktion wurde in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="30687-120">This feature was introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="30687-121">`Get-Help` sucht im ersten Eintrag im Abschnitt "Verwandte Links" nach einem URI, bevor der Wert der HelpUri-Eigenschaft erhalten wird.</span><span class="sxs-lookup"><span data-stu-id="30687-121">`Get-Help` looks for a URI in the first entry in the Related Links section before getting the HelpUri property value.</span></span> <span data-ttu-id="30687-122">Wenn der Eigenschafts Wert falsch ist oder geändert wurde, können Sie ihn überschreiben, indem Sie im ersten verknüpften Link einen anderen Wert eingeben.</span><span class="sxs-lookup"><span data-stu-id="30687-122">If the property value is incorrect or has changed, you can override it by entering a different value in the first Related Link.</span></span> <span data-ttu-id="30687-123">Der erste Verwandte Link funktioniert jedoch nur, wenn die Hilfe Themen auf dem Computer des Benutzers installiert sind.</span><span class="sxs-lookup"><span data-stu-id="30687-123">However, the first Related Link works only when the help topics are installed on the user's computer.</span></span>

## <a name="adding-a-uri-to-the-first-related-link-of-a-command-help-topic"></a><span data-ttu-id="30687-124">Hinzufügen eines URIs zum ersten verknüpften Link eines Befehls Hilfe Themas</span><span class="sxs-lookup"><span data-stu-id="30687-124">Adding a URI to the first related link of a command help topic</span></span>

<span data-ttu-id="30687-125">Sie können `Get-Help`-Online für jeden Befehl unterstützen, indem Sie dem ersten Eintrag im Abschnitt Verwandte Links des XML-basierten Hilfe Themas für den Befehl einen gültigen URI hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="30687-125">You can support `Get-Help` -Online for any command by adding a valid URI to the first entry in the Related Links section of the XML-based help topic for the command.</span></span> <span data-ttu-id="30687-126">Diese Option ist nur in XML-basierten Hilfe Themen gültig und funktioniert nur, wenn das Hilfethema auf dem Computer des Benutzers installiert ist.</span><span class="sxs-lookup"><span data-stu-id="30687-126">This option is valid only in XML-based help topics and works only when the help topic is installed on the user's computer.</span></span> <span data-ttu-id="30687-127">Wenn das Hilfethema installiert ist und der URI aufgefüllt wird, hat dieser Wert Vorrang vor der **HelpUri** -Eigenschaft des Befehls.</span><span class="sxs-lookup"><span data-stu-id="30687-127">When the help topic is installed and the URI is populated, this value takes precedence over the **HelpUri** property of the command.</span></span>

<span data-ttu-id="30687-128">Um diese Funktion zu unterstützen, muss der URI im `maml:uri`-Element unter dem ersten `maml:relatedLinks/maml:navigationLink`-Element im `maml:relatedLinks`-Element angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="30687-128">To support this feature, the URI must appear in the `maml:uri` element under the first `maml:relatedLinks/maml:navigationLink` element in the `maml:relatedLinks` element.</span></span>

<span data-ttu-id="30687-129">Der folgende XML-Code zeigt die korrekte Platzierung des URI.</span><span class="sxs-lookup"><span data-stu-id="30687-129">The following XML shows the correct placement of the URI.</span></span> <span data-ttu-id="30687-130">Der Text "Online Version:" im `maml:linkText`-Element ist eine bewährte Vorgehensweise, aber er ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="30687-130">The "Online version:" text in the `maml:linkText` element is a best practice, but it is not required.</span></span>

```xml

<maml:relatedLinks>
    <maml:navigationLink>
        <maml:linkText>Online version:</maml:linkText>
        <maml:uri>http://go.microsoft.com/fwlink/?LinkID=113279</maml:uri>
    </maml:navigationLink>
    <maml:navigationLink>
        <maml:linkText>about_History</maml:linkText>
        <maml:uri/>
    </maml:navigationLink>
</maml:relatedLinks>
```

## <a name="adding-the-helpuri-property-to-a-command"></a><span data-ttu-id="30687-131">Hinzufügen der HelpUri-Eigenschaft zu einem Befehl</span><span class="sxs-lookup"><span data-stu-id="30687-131">Adding the HelpUri property to a command</span></span>

<span data-ttu-id="30687-132">In diesem Abschnitt wird gezeigt, wie die HelpUri-Eigenschaft Befehlen verschiedener Typen hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="30687-132">This section shows how to add the HelpUri property to commands of different types.</span></span>

### <a name="adding-a-helpuri-property-to-a-cmdlet"></a><span data-ttu-id="30687-133">Hinzufügen einer HelpUri-Eigenschaft zu einem Cmdlet</span><span class="sxs-lookup"><span data-stu-id="30687-133">Adding a HelpUri Property to a Cmdlet</span></span>

<span data-ttu-id="30687-134">Fügen Sie für in C#geschriebene Cmdlets der Cmdlet-Klasse ein **HelpUri** -Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="30687-134">For cmdlets written in C#, add a **HelpUri** attribute to the Cmdlet class.</span></span> <span data-ttu-id="30687-135">Der Wert des-Attributs muss ein URI sein, der mit "http" oder "https" beginnt.</span><span class="sxs-lookup"><span data-stu-id="30687-135">The value of the attribute must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="30687-136">Der folgende Code zeigt das HelpUri-Attribut der `Get-History`-Cmdlet-Klasse.</span><span class="sxs-lookup"><span data-stu-id="30687-136">The following code shows the HelpUri attribute of the `Get-History` cmdlet class.</span></span>

```
[Cmdlet(VerbsCommon.Get, "History", HelpUri = "http://go.microsoft.com/fwlink/?LinkID=001122")]
```

### <a name="adding-a-helpuri-property-to-an-advanced-function"></a><span data-ttu-id="30687-137">Hinzufügen einer HelpUri-Eigenschaft zu einer erweiterten Funktion</span><span class="sxs-lookup"><span data-stu-id="30687-137">Adding a HelpUri Property to an Advanced Function</span></span>

<span data-ttu-id="30687-138">Fügen Sie für erweiterte Funktionen eine **HelpUri** -Eigenschaft zum **cmdletbinding** -Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="30687-138">For advanced functions, add a **HelpUri** property to the **CmdletBinding** attribute.</span></span> <span data-ttu-id="30687-139">Der Wert der Eigenschaft muss ein URI sein, der mit "http" oder "https" beginnt.</span><span class="sxs-lookup"><span data-stu-id="30687-139">The value of the property must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="30687-140">Der folgende Code zeigt das HelpUri-Attribut der New-Calendar-Funktion.</span><span class="sxs-lookup"><span data-stu-id="30687-140">The following code shows the HelpUri attribute of the New-Calendar function</span></span>

```powershell

function New-Calendar {
    [CmdletBinding(SupportsShouldProcess=$true,
    HelpURI="http://go.microsoft.com/fwlink/?LinkID=01122")]
```

### <a name="adding-a-helpuri-attribute-to-a-cim-command"></a><span data-ttu-id="30687-141">Hinzufügen eines HelpUri-Attributs zu einem CIM-Befehl</span><span class="sxs-lookup"><span data-stu-id="30687-141">Adding a HelpUri Attribute to a CIM Command</span></span>

<span data-ttu-id="30687-142">Fügen Sie für CIM-Befehle dem **cmdletmetadata** -Element in der cdxml-Datei ein **HelpUri** -Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="30687-142">For CIM commands, add a **HelpUri** attribute to the **CmdletMetadata** element in the CDXML file.</span></span> <span data-ttu-id="30687-143">Der Wert des-Attributs muss ein URI sein, der mit "http" oder "https" beginnt.</span><span class="sxs-lookup"><span data-stu-id="30687-143">The value of the attribute must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="30687-144">Der folgende Code zeigt das HelpUri-Attribut des Befehls Start-Debug CIM.</span><span class="sxs-lookup"><span data-stu-id="30687-144">The following code shows the HelpUri attribute of the Start-Debug CIM command</span></span>

```
<CmdletMetadata Verb="Debug" HelpUri="http://go.microsoft.com/fwlink/?LinkID=001122"/>
```

### <a name="adding-a-helpuri-attribute-to-a-workflow"></a><span data-ttu-id="30687-145">Hinzufügen eines HelpUri-Attributs zu einem Workflow</span><span class="sxs-lookup"><span data-stu-id="30687-145">Adding a HelpUri Attribute to a Workflow</span></span>

<span data-ttu-id="30687-146">Fügen Sie für Workflows, die in der Windows PowerShell-Sprache geschrieben sind, ein hinzu **. Externalhelp** -Kommentar Anweisung an den Workflow Code.</span><span class="sxs-lookup"><span data-stu-id="30687-146">For workflows that are written in the Windows PowerShell language, add an **.ExternalHelp** comment directive to the workflow code.</span></span> <span data-ttu-id="30687-147">Der Wert der Direktive muss ein URI sein, der mit "http" oder "https" beginnt.</span><span class="sxs-lookup"><span data-stu-id="30687-147">The value of the directive must be a URI that begins with "http" or "https".</span></span>

> [!NOTE]
> <span data-ttu-id="30687-148">Die HelpUri-Eigenschaft wird für XAML-basierte Workflows in Windows PowerShell nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="30687-148">The HelpUri property is not supported for XAML-based workflows in Windows PowerShell.</span></span>

<span data-ttu-id="30687-149">Der folgende Code zeigt den. Externalhelp-Direktive in einer Workflow Datei.</span><span class="sxs-lookup"><span data-stu-id="30687-149">The following code shows the .ExternalHelp directive in a workflow file.</span></span>

```powershell
# .ExternalHelp "http://go.microsoft.com/fwlink/?LinkID=138338"
```