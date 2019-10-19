---
title: Selectionsetname-Element für entryselectedby für enumerableexpansion (Format) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 936d09f2-2c48-49e8-ab2d-0c8729199a2e
caps.latest.revision: 8
ms.openlocfilehash: 8ba8931ea5e34f610878351396cad42023393ad6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368329"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="b70e6-102">Element „SelectionSetName“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="b70e6-102">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="b70e6-103">Gibt den Satz von .NET-Typen an, die durch diese Definition erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="b70e6-103">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="b70e6-104">Configuration-Element (Format) DefaultSettings-Element (Format) enumerableerweiterungen-Element (Format) enumerableweiterung-Element (Format) entryselectedby-Element für enumerableexpansion (Format) selectionsetname-Element für entryselectedby Enumerableerweiterung (Format)</span><span class="sxs-lookup"><span data-stu-id="b70e6-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b70e6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b70e6-105">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="b70e6-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b70e6-106">Attributes and Elements</span></span>

<span data-ttu-id="b70e6-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des `SelectionSetName`-Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b70e6-107">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b70e6-108">Attributes</span><span class="sxs-lookup"><span data-stu-id="b70e6-108">Attributes</span></span>

<span data-ttu-id="b70e6-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="b70e6-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b70e6-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b70e6-110">Child Elements</span></span>

<span data-ttu-id="b70e6-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="b70e6-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b70e6-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b70e6-112">Parent Elements</span></span>

|<span data-ttu-id="b70e6-113">Element</span><span class="sxs-lookup"><span data-stu-id="b70e6-113">Element</span></span>|<span data-ttu-id="b70e6-114">Description</span><span class="sxs-lookup"><span data-stu-id="b70e6-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b70e6-115">Entryselectedby-Element für enumerableexpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="b70e6-115">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="b70e6-116">Definiert die .net-Auflistungs Objekte, die durch diese Definition erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="b70e6-116">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b70e6-117">Textwert</span><span class="sxs-lookup"><span data-stu-id="b70e6-117">Text Value</span></span>

<span data-ttu-id="b70e6-118">Geben Sie den Namen des Auswahl Satzes an.</span><span class="sxs-lookup"><span data-stu-id="b70e6-118">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="b70e6-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b70e6-119">Remarks</span></span>

<span data-ttu-id="b70e6-120">Jede Definition muss einen oder mehrere Typnamen, einen Auswahl Satz oder eine Auswahlbedingung angeben.</span><span class="sxs-lookup"><span data-stu-id="b70e6-120">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="b70e6-121">Auswahl Sätze werden in der Regel verwendet, wenn Sie eine Gruppe von Objekten definieren möchten, die in mehreren Ansichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b70e6-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="b70e6-122">Beispielsweise können Sie eine Tabellenansicht und eine Listenansicht für denselben Satz von Objekten erstellen.</span><span class="sxs-lookup"><span data-stu-id="b70e6-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="b70e6-123">Weitere Informationen zum Definieren von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen für eine Sicht](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b70e6-123">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b70e6-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b70e6-124">See Also</span></span>

[<span data-ttu-id="b70e6-125">Definieren von Auswahl Sätzen</span><span class="sxs-lookup"><span data-stu-id="b70e6-125">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="b70e6-126">Entryselectedby-Element für enumerableexpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="b70e6-126">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="b70e6-127">Schreiben einer PowerShell-Formatierungs Datei</span><span class="sxs-lookup"><span data-stu-id="b70e6-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)