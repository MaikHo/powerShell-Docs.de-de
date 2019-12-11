---
title: Configuration-Element (Format) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d46df0cb-50b7-4b81-82ba-37186a7b7a7f
caps.latest.revision: 28
ms.openlocfilehash: 296c63d0c774a0bf56e90dbaa32f2c221d4c3dbd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363499"
---
# <a name="configuration-element-format"></a><span data-ttu-id="86da8-102">Element „Configuration“ (Format)</span><span class="sxs-lookup"><span data-stu-id="86da8-102">Configuration Element (Format)</span></span>

<span data-ttu-id="86da8-103">Stellt das Element der obersten Ebene einer Formatierungs Datei dar.</span><span class="sxs-lookup"><span data-stu-id="86da8-103">Represents the top-level element of a formatting file.</span></span>

<span data-ttu-id="86da8-104">Configuration-Element</span><span class="sxs-lookup"><span data-stu-id="86da8-104">Configuration Element</span></span>

## <a name="syntax"></a><span data-ttu-id="86da8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="86da8-105">Syntax</span></span>

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="86da8-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="86da8-106">Attributes and Elements</span></span>

<span data-ttu-id="86da8-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des `Configuration`-Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="86da8-107">The following sections describe the attributes, child elements, and the parent element of the `Configuration` element.</span></span> <span data-ttu-id="86da8-108">Dieses Element muss das root-Element für jede Formatierungs Datei sein, und dieses Element muss mindestens ein untergeordnetes Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="86da8-108">This element must be the root element for each formatting file, and this element must contain at least one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="86da8-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="86da8-109">Attributes</span></span>

<span data-ttu-id="86da8-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="86da8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="86da8-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86da8-111">Child Elements</span></span>

|<span data-ttu-id="86da8-112">Element</span><span class="sxs-lookup"><span data-stu-id="86da8-112">Element</span></span>|<span data-ttu-id="86da8-113">Description</span><span class="sxs-lookup"><span data-stu-id="86da8-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="86da8-114">Controls-Element für Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="86da8-114">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="86da8-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="86da8-115">Optional element.</span></span><br /><br /> <span data-ttu-id="86da8-116">Definiert die allgemeinen Steuerelemente, die von allen Ansichten der Formatierungs Datei verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="86da8-116">Defines the common controls that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="86da8-117">DefaultSettings-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="86da8-117">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="86da8-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="86da8-118">Optional element.</span></span><br /><br /> <span data-ttu-id="86da8-119">Definiert allgemeine Einstellungen, die für alle Sichten der Formatierungs Datei gelten.</span><span class="sxs-lookup"><span data-stu-id="86da8-119">Defines common settings that apply to all the views of the formatting file.</span></span>|
|[<span data-ttu-id="86da8-120">Selectionsets-Element Format</span><span class="sxs-lookup"><span data-stu-id="86da8-120">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="86da8-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="86da8-121">Optional element.</span></span><br /><br /> <span data-ttu-id="86da8-122">Definiert die allgemeinen Sätze von .NET-Objekten, die von allen Sichten der Formatierungs Datei verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="86da8-122">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="86da8-123">Viewdefinitions-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="86da8-123">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="86da8-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="86da8-124">Optional element.</span></span><br /><br /> <span data-ttu-id="86da8-125">Definiert die Sichten, die zum Anzeigen von Objekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="86da8-125">Defines the views used to display objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="86da8-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86da8-126">Parent Elements</span></span>

<span data-ttu-id="86da8-127">Keine.</span><span class="sxs-lookup"><span data-stu-id="86da8-127">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="86da8-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="86da8-128">Remarks</span></span>

<span data-ttu-id="86da8-129">Formatieren von Dateien definieren, wie Objekte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="86da8-129">Formatting files define how objects are displayed.</span></span> <span data-ttu-id="86da8-130">In den meisten Fällen enthält dieses root-Element ein [viewdefinitions](./viewdefinitions-element-format.md) -Element, das die Tabellen-, Listen-und breiten Ansichten der Formatierungs Datei definiert.</span><span class="sxs-lookup"><span data-stu-id="86da8-130">In most cases, this root element contains a [ViewDefinitions](./viewdefinitions-element-format.md) element that defines the table, list, and wide views of the formatting file.</span></span> <span data-ttu-id="86da8-131">Zusätzlich zu den Sicht Definitionen kann die Formatierungs Datei allgemeine Auswahl Sätze, Einstellungen und Steuerelemente definieren, die diese Sichten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="86da8-131">In addition to the view definitions, the formatting file can define common selection sets, settings, and controls that those views can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="86da8-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86da8-132">See Also</span></span>

[<span data-ttu-id="86da8-133">Controls-Element für Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="86da8-133">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="86da8-134">DefaultSettings-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="86da8-134">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="86da8-135">Selectionsets-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="86da8-135">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="86da8-136">Viewdefinitions-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="86da8-136">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="86da8-137">Schreiben einer PowerShell-Formatierungs Datei</span><span class="sxs-lookup"><span data-stu-id="86da8-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)