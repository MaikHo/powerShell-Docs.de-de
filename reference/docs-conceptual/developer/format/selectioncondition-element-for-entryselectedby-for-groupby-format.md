---
title: Selectioncondition-Element für entryselectedby für GroupBy (Format) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dc2093a-dc54-42c4-ada3-c8d089ba1e8e
caps.latest.revision: 6
ms.openlocfilehash: a6738a7c4c934b2d6a16695a711f7c6c80afdd2d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368429"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="97c5e-102">Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="97c5e-102">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="97c5e-103">Definiert eine Bedingung, die vorhanden sein muss, damit eine Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="97c5e-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="97c5e-104">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="97c5e-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="97c5e-105">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) entryselectedby-Element für customentry für GroupBy (Format) selectioncondition-Element für entryselectedby für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="97c5e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="97c5e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="97c5e-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="97c5e-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="97c5e-107">Attributes and Elements</span></span>

<span data-ttu-id="97c5e-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des `SelectionCondition`-Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="97c5e-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="97c5e-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="97c5e-109">Attributes</span></span>

<span data-ttu-id="97c5e-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="97c5e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="97c5e-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="97c5e-111">Child Elements</span></span>

|<span data-ttu-id="97c5e-112">Element</span><span class="sxs-lookup"><span data-stu-id="97c5e-112">Element</span></span>|<span data-ttu-id="97c5e-113">Description</span><span class="sxs-lookup"><span data-stu-id="97c5e-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="97c5e-114">PropertyName-Element für selectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="97c5e-114">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="97c5e-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="97c5e-115">Optional element.</span></span><br /><br /> <span data-ttu-id="97c5e-116">Gibt eine .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="97c5e-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="97c5e-117">ScriptBlock-Element für selectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="97c5e-117">ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="97c5e-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="97c5e-118">Optional element.</span></span><br /><br /> <span data-ttu-id="97c5e-119">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="97c5e-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="97c5e-120">Selectionsetname-Element für selectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="97c5e-120">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="97c5e-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="97c5e-121">Optional element.</span></span><br /><br /> <span data-ttu-id="97c5e-122">Gibt den Satz von .NET-Typen an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="97c5e-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="97c5e-123">Typname-Element für selectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="97c5e-123">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="97c5e-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="97c5e-124">Optional element.</span></span><br /><br /> <span data-ttu-id="97c5e-125">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="97c5e-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="97c5e-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="97c5e-126">Parent Elements</span></span>

|<span data-ttu-id="97c5e-127">Element</span><span class="sxs-lookup"><span data-stu-id="97c5e-127">Element</span></span>|<span data-ttu-id="97c5e-128">Description</span><span class="sxs-lookup"><span data-stu-id="97c5e-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="97c5e-129">Entryselectedby-Element für customentry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="97c5e-129">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="97c5e-130">Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="97c5e-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="97c5e-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="97c5e-131">Remarks</span></span>

<span data-ttu-id="97c5e-132">Wenn Sie eine Auswahlbedingung definieren, gelten die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="97c5e-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="97c5e-133">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="97c5e-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="97c5e-134">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="97c5e-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="97c5e-135">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="97c5e-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="97c5e-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="97c5e-136">See Also</span></span>

[<span data-ttu-id="97c5e-137">PropertyName-Element für selectioncondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="97c5e-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="97c5e-138">ScriptBlock-Element für selectioncondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="97c5e-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="97c5e-139">Selectionsetname-Element für selectioncondition für benutzerdefiniertes Steuer Element für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="97c5e-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="97c5e-140">Typname-Element für selectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="97c5e-140">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="97c5e-141">Entryselectedby-Element für customentry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="97c5e-141">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="97c5e-142">Schreiben einer PowerShell-Formatierungs Datei</span><span class="sxs-lookup"><span data-stu-id="97c5e-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)