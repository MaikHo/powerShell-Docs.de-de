---
title: WideEntry-Element für WideControl (Format) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 014763cb-7716-4931-899c-8375b5d7a3dd
caps.latest.revision: 15
ms.openlocfilehash: d1d13b5c3436871053353814293d9163ea13c7fb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856526"
---
# <a name="wideentry-element-for-widecontrol-format"></a><span data-ttu-id="fb357-102">Element „WideEntry“ für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="fb357-102">WideEntry Element for WideControl (Format)</span></span>

<span data-ttu-id="fb357-103">Stellt eine Definition der breiten Ansicht.</span><span class="sxs-lookup"><span data-stu-id="fb357-103">Provides a definition of the wide view.</span></span>

<span data-ttu-id="fb357-104">-Element (Format) ViewDefinitions-Element (Format) anzeigen (Format)-Element WideControl-Element (Format) WideEntries-Element (Format) WideEntry Konfigurationselement (Format)</span><span class="sxs-lookup"><span data-stu-id="fb357-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fb357-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb357-105">Syntax</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fb357-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fb357-106">Attributes and Elements</span></span>

<span data-ttu-id="fb357-107">Die folgenden Abschnitte beschreiben die Attribute, untergeordnete Elemente und das übergeordnete Element des der `WideEntry` Element.</span><span class="sxs-lookup"><span data-stu-id="fb357-107">The following sections describe the attributes, child elements, and the parent element of the `WideEntry` element.</span></span> <span data-ttu-id="fb357-108">Sie müssen angeben, dass eine einzelne `WideItem` untergeordnetes Element.</span><span class="sxs-lookup"><span data-stu-id="fb357-108">You must specify a single `WideItem` child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fb357-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="fb357-109">Attributes</span></span>

<span data-ttu-id="fb357-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="fb357-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fb357-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fb357-111">Child Elements</span></span>

|<span data-ttu-id="fb357-112">Element</span><span class="sxs-lookup"><span data-stu-id="fb357-112">Element</span></span>|<span data-ttu-id="fb357-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb357-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fb357-114">EntrySelectedBy-Element für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fb357-114">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="fb357-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="fb357-115">Optional element.</span></span><br /><br /> <span data-ttu-id="fb357-116">Definiert die Typen von .NET, mit denen diese Breite Eintrag-Definition oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb357-116">Defines the .NET types that use this wide entry definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="fb357-117">WideItem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="fb357-117">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="fb357-118">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="fb357-118">Required element.</span></span><br /><br /> <span data-ttu-id="fb357-119">Definiert die Eigenschaft oder ein Skript, dessen Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fb357-119">Defines the property or script whose value is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="fb357-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fb357-120">Parent Elements</span></span>

|<span data-ttu-id="fb357-121">Element</span><span class="sxs-lookup"><span data-stu-id="fb357-121">Element</span></span>|<span data-ttu-id="fb357-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb357-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fb357-123">WideEntries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="fb357-123">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="fb357-124">Enthält die Definitionen der breiten Ansicht an.</span><span class="sxs-lookup"><span data-stu-id="fb357-124">Provides the definitions of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fb357-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb357-125">Remarks</span></span>

<span data-ttu-id="fb357-126">Eine Breite Ansicht ist einer Liste an, in dem eine einzelne Eigenschaft-Wert oder die Skriptwert für jedes Objekt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb357-126">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="fb357-127">Im Gegensatz zu anderen Arten von Ansichten können Sie nur eine Item-Element für jede Sichtdefinition angeben.</span><span class="sxs-lookup"><span data-stu-id="fb357-127">Unlike other types of views, you can specify only one item element for each view definition.</span></span> <span data-ttu-id="fb357-128">Weitere Informationen zu den anderen Komponenten, der eine Breite Ansicht, finden Sie unter [erstellen eine Breite Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="fb357-128">For more information about the other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="fb357-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fb357-129">Example</span></span>

<span data-ttu-id="fb357-130">Das folgende Beispiel zeigt eine `WideEntry` Element, das ein einzelnes definiert `WideItem` Element.</span><span class="sxs-lookup"><span data-stu-id="fb357-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="fb357-131">Die `WideItem` -Element definiert die Eigenschaft, deren Wert in der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fb357-131">The `WideItem` element defines the property whose value is displayed in the view.</span></span>

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

<span data-ttu-id="fb357-132">Ein vollständiges Beispiel eine Breite Ansicht, finden Sie unter [Breite Ansicht (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="fb357-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fb357-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb357-133">See Also</span></span>

[<span data-ttu-id="fb357-134">Erstellen eine Breite Ansicht</span><span class="sxs-lookup"><span data-stu-id="fb357-134">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="fb357-135">SelectionCondition-Element für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fb357-135">SelectionCondition Element for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="fb357-136">SelectionSetName-Element für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fb357-136">SelectionSetName Element for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="fb357-137">TypeName-Element für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fb357-137">TypeName Element for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="fb357-138">WideEntries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="fb357-138">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="fb357-139">WideItem-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="fb357-139">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="fb357-140">Schreiben Sie eine Formatierungsdatei PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb357-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)