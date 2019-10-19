---
title: ScriptBlock-Element für selectioncondition für entryselectedby für widecontrol (Format) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ec68309-7826-4643-a521-e29c996663fb
caps.latest.revision: 11
ms.openlocfilehash: 649a978e21e9421a3f3e953261e1d309e23c3f9c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368559"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="54c56-102">Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="54c56-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="54c56-103">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="54c56-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="54c56-104">Wenn dieses Skript als `true` ausgewertet wird, wird die Bedingung erfüllt, und die Breite Eingabe Definition wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="54c56-104">When this script is evaluated to `true`, the condition is met, and the wide entry definition is used.</span></span>

<span data-ttu-id="54c56-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) entryselectedby-Element für wideentry (Format) selectioncondition-Element für Entryselectedby für wideentry (Format) ScriptBlock-Element für selectioncondition für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="54c56-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="54c56-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="54c56-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="54c56-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="54c56-107">Attributes and Elements</span></span>

<span data-ttu-id="54c56-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des `ScriptBlock`-Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="54c56-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="54c56-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="54c56-109">Attributes</span></span>

<span data-ttu-id="54c56-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="54c56-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="54c56-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="54c56-111">Child Elements</span></span>

<span data-ttu-id="54c56-112">Keine.</span><span class="sxs-lookup"><span data-stu-id="54c56-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="54c56-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="54c56-113">Parent Elements</span></span>

|<span data-ttu-id="54c56-114">Element</span><span class="sxs-lookup"><span data-stu-id="54c56-114">Element</span></span>|<span data-ttu-id="54c56-115">Description</span><span class="sxs-lookup"><span data-stu-id="54c56-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="54c56-116">Selectioncondition-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="54c56-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="54c56-117">Definiert die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="54c56-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="54c56-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="54c56-118">Text Value</span></span>

<span data-ttu-id="54c56-119">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="54c56-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="54c56-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="54c56-120">Remarks</span></span>

<span data-ttu-id="54c56-121">Die Auswahlbedingung muss mindestens ein Skript oder einen Eigenschaftsnamen angeben, der ausgewertet werden soll, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="54c56-121">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="54c56-122">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="54c56-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="54c56-123">Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="54c56-123">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="54c56-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54c56-124">See Also</span></span>

[<span data-ttu-id="54c56-125">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="54c56-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="54c56-126">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="54c56-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="54c56-127">PropertyName-Element für selectioncondition für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="54c56-127">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="54c56-128">Selectioncondition-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="54c56-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="54c56-129">Schreiben einer PowerShell-Formatierungs Datei</span><span class="sxs-lookup"><span data-stu-id="54c56-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)