---
title: Viewselectedby-Element (Format) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdeef4d-3554-4f39-a7e6-a684e3848fd7
caps.latest.revision: 19
ms.openlocfilehash: efc1c5d1338889ecd0be7150b7733842ce78979e
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367969"
---
# <a name="viewselectedby-element-format"></a><span data-ttu-id="46e2c-102">Element „ViewSelectedBy“ (Format)</span><span class="sxs-lookup"><span data-stu-id="46e2c-102">ViewSelectedBy Element (Format)</span></span>

<span data-ttu-id="46e2c-103">Definiert die .NET-Objekte, die von der Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="46e2c-103">Defines the .NET objects that are displayed by the view.</span></span> <span data-ttu-id="46e2c-104">Jede Ansicht muss mindestens ein .NET-Objekt angeben.</span><span class="sxs-lookup"><span data-stu-id="46e2c-104">Each view must specify at least one .NET object.</span></span>

<span data-ttu-id="46e2c-105">Viewdefinitions-Element (Format) View-Element (Format) viewselectedby-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="46e2c-105">ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="46e2c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="46e2c-106">Syntax</span></span>

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="46e2c-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="46e2c-107">Attributes and Elements</span></span>

<span data-ttu-id="46e2c-108">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des `ViewSelectedBy`-Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="46e2c-108">The following sections describe the attributes, child elements, and parent element of the `ViewSelectedBy` element.</span></span> <span data-ttu-id="46e2c-109">Dieses Element muss mindestens ein untergeordnetes `TypeName`-oder `SelectionSetName`-Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="46e2c-109">This element must contain at least one `TypeName` or `SelectionSetName` child element.</span></span> <span data-ttu-id="46e2c-110">Es gibt keine Beschränkung für die Anzahl der untergeordneten Elemente, die angegeben werden können, und ihre Reihenfolge ist nicht signifikant.</span><span class="sxs-lookup"><span data-stu-id="46e2c-110">There is no limit to the number of child elements that can be specified nor is their order significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="46e2c-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="46e2c-111">Attributes</span></span>

<span data-ttu-id="46e2c-112">Keine.</span><span class="sxs-lookup"><span data-stu-id="46e2c-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="46e2c-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="46e2c-113">Child Elements</span></span>

|<span data-ttu-id="46e2c-114">Element</span><span class="sxs-lookup"><span data-stu-id="46e2c-114">Element</span></span>|<span data-ttu-id="46e2c-115">Description</span><span class="sxs-lookup"><span data-stu-id="46e2c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="46e2c-116">Tyname-Element für viewselectedby (Format)</span><span class="sxs-lookup"><span data-stu-id="46e2c-116">TypeName Element for ViewSelectedBy (Format)</span></span>](./typename-element-for-viewselectedby-format.md)|<span data-ttu-id="46e2c-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="46e2c-117">Optional element.</span></span><br /><br /> <span data-ttu-id="46e2c-118">Gibt ein .NET-Objekt an, das von der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="46e2c-118">Specifies a .NET object that is displayed by the view.</span></span>|
|[<span data-ttu-id="46e2c-119">Selectionsetname-Element für viewselectedby (Format)</span><span class="sxs-lookup"><span data-stu-id="46e2c-119">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)|<span data-ttu-id="46e2c-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="46e2c-120">Optional element.</span></span><br /><br /> <span data-ttu-id="46e2c-121">Gibt einen Satz von .NET-Objekten an, die von der Sicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="46e2c-121">Specifies a set of .NET objects that are displayed by the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="46e2c-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="46e2c-122">Parent Elements</span></span>

|<span data-ttu-id="46e2c-123">Element</span><span class="sxs-lookup"><span data-stu-id="46e2c-123">Element</span></span>|<span data-ttu-id="46e2c-124">Description</span><span class="sxs-lookup"><span data-stu-id="46e2c-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="46e2c-125">View-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="46e2c-125">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="46e2c-126">Definiert eine Ansicht, in der ein oder mehrere .NET-Objekte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="46e2c-126">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="46e2c-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="46e2c-127">Remarks</span></span>

<span data-ttu-id="46e2c-128">Weitere Informationen zur Verwendung dieses Elements in verschiedenen Ansichten finden Sie unter [Tabellen Ansichts Komponenten](./creating-a-table-view.md), [Listen Ansichts Komponenten](./creating-a-list-view.md), [Wide View Components](./creating-a-wide-view.md)und [Custom Control Components](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="46e2c-128">For more information about how this element is used in different views, see [Table View Components](./creating-a-table-view.md), [List View Components](./creating-a-list-view.md), [Wide View Components](./creating-a-wide-view.md), and [Custom Control Components](./creating-custom-controls.md).</span></span>

<span data-ttu-id="46e2c-129">Das `SelectionSetName`-Element wird verwendet, wenn die Formatierungs Datei eine Gruppe von Objekten definiert, die von mehreren Ansichten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="46e2c-129">The `SelectionSetName` element is used when the formatting file defines a set of objects that are displayed by multiple views.</span></span> <span data-ttu-id="46e2c-130">Weitere Informationen zum Definieren und referenziert von Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="46e2c-130">For more information about how selection sets are defined and referenced, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="46e2c-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46e2c-131">Example</span></span>

<span data-ttu-id="46e2c-132">Im folgenden Beispiel wird gezeigt, wie das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt für eine Listenansicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="46e2c-132">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="46e2c-133">Das gleiche Schema wird für Tabellen-, breiten-und benutzerdefinierte Sichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="46e2c-133">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="46e2c-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46e2c-134">See Also</span></span>

[<span data-ttu-id="46e2c-135">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="46e2c-135">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="46e2c-136">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="46e2c-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="46e2c-137">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="46e2c-137">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="46e2c-138">Erstellen benutzerdefinierter Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="46e2c-138">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="46e2c-139">Definieren von Auswahl Sätzen</span><span class="sxs-lookup"><span data-stu-id="46e2c-139">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="46e2c-140">Selectionsetname-Element für viewselectedby (Format)</span><span class="sxs-lookup"><span data-stu-id="46e2c-140">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

[<span data-ttu-id="46e2c-141">Tyname-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="46e2c-141">TypeName Element (Format)</span></span>](./typename-element-for-viewselectedby-format.md)

[<span data-ttu-id="46e2c-142">Schreiben einer PowerShell-Formatierungs Datei</span><span class="sxs-lookup"><span data-stu-id="46e2c-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)