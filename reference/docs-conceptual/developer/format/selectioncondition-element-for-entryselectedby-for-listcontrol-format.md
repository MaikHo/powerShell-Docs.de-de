---
title: Selectioncondition-Element für entryselectedby für ListControl (Format) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7649d5d0-2b56-49b5-a670-dde46caca343
caps.latest.revision: 11
ms.openlocfilehash: 7150b29ad84dfb587215ee3e64c356adbd5a6305
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417541"
---
# <a name="selectioncondition-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="323a5-102">Element „SelectionCondition“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="323a5-102">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="323a5-103">Definiert die Bedingung, die vorhanden sein muss, um diese Definition der Listenansicht zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="323a5-103">Defines the condition that must exist to use this definition of the list view.</span></span> <span data-ttu-id="323a5-104">Es gibt keine Beschränkung für die Anzahl der Auswahl Bedingungen, die für eine Listen Definition angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="323a5-104">There is no limit to the number of selection conditions that can be specified for a list definition.</span></span>

<span data-ttu-id="323a5-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element (Format) ListEntry-Element (Format) entryselectedby-Element für ListEntry (Format) selectioncondition-Element für Entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="323a5-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="323a5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="323a5-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="323a5-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="323a5-107">Attributes and Elements</span></span>

<span data-ttu-id="323a5-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des `SelectionCondition`-Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="323a5-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="323a5-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="323a5-109">Attributes</span></span>

<span data-ttu-id="323a5-110">Keine</span><span class="sxs-lookup"><span data-stu-id="323a5-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="323a5-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="323a5-111">Child Elements</span></span>

|<span data-ttu-id="323a5-112">Element</span><span class="sxs-lookup"><span data-stu-id="323a5-112">Element</span></span>|<span data-ttu-id="323a5-113">Description</span><span class="sxs-lookup"><span data-stu-id="323a5-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="323a5-114">PropertyName-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="323a5-114">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="323a5-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="323a5-115">Optional element.</span></span><br /><br /> <span data-ttu-id="323a5-116">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="323a5-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="323a5-117">ScriptBlock-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="323a5-117">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="323a5-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="323a5-118">Optional element.</span></span><br /><br /> <span data-ttu-id="323a5-119">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="323a5-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="323a5-120">Selectionsetname-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="323a5-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)|<span data-ttu-id="323a5-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="323a5-121">Optional element.</span></span><br /><br /> <span data-ttu-id="323a5-122">Gibt den Satz von .NET-Typen an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="323a5-122">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="323a5-123">Typname-Element für selectioncondition für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="323a5-123">TypeName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="323a5-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="323a5-124">Optional element.</span></span><br /><br /> <span data-ttu-id="323a5-125">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="323a5-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="323a5-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="323a5-126">Parent Elements</span></span>

|<span data-ttu-id="323a5-127">Element</span><span class="sxs-lookup"><span data-stu-id="323a5-127">Element</span></span>|<span data-ttu-id="323a5-128">Description</span><span class="sxs-lookup"><span data-stu-id="323a5-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="323a5-129">Entryselectedby-Element für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="323a5-129">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="323a5-130">Definiert die .NET-Typen, die diesen Tabelleneintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="323a5-130">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="323a5-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="323a5-131">Remarks</span></span>

<span data-ttu-id="323a5-132">lWenn Sie eine Auswahlbedingung definieren, gelten die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="323a5-132">lWhen you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="323a5-133">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="323a5-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="323a5-134">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="323a5-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="323a5-135">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="323a5-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="323a5-136">Weitere Informationen zu anderen Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="323a5-136">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="323a5-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="323a5-137">See Also</span></span>

[<span data-ttu-id="323a5-138">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="323a5-138">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="323a5-139">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="323a5-139">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="323a5-140">ListEntry-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="323a5-140">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="323a5-141">Selectionsetname-Element für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="323a5-141">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="323a5-142">Typname-Element für entryselectedby für ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="323a5-142">TypeName Element for EntrySelectedBy for ListEntry (Format)</span></span>](/powershell/scripting/developer/format/typename-element-for-entryselectedby-for-listcontrol-format)

[<span data-ttu-id="323a5-143">Schreiben einer PowerShell-Formatierungs Datei</span><span class="sxs-lookup"><span data-stu-id="323a5-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)