---
title: ListControl-Element (Format) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37beeb0b-7a81-4747-becb-e309e17278fb
caps.latest.revision: 12
ms.openlocfilehash: 7a117c25b0d117dc846ba8e060e31e838b5edd52
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362779"
---
# <a name="listcontrol-element-format"></a><span data-ttu-id="1ee1d-102">Element „ListControl“ (Format)</span><span class="sxs-lookup"><span data-stu-id="1ee1d-102">ListControl Element (Format)</span></span>

<span data-ttu-id="1ee1d-103">Definiert ein Listenformat für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="1ee1d-103">Defines a list format for the view.</span></span>

<span data-ttu-id="1ee1d-104">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) ListControl-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="1ee1d-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1ee1d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ee1d-105">Syntax</span></span>

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="1ee1d-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1ee1d-106">Attributes and Elements</span></span>

<span data-ttu-id="1ee1d-107">In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des `ListControl`-Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1ee1d-107">The following sections describe the attributes, child elements, and the parent element of the `ListControl` element.</span></span> <span data-ttu-id="1ee1d-108">Dieses Element darf nur ein einzelnes untergeordnetes Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="1ee1d-108">This element must contain only a single child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1ee1d-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="1ee1d-109">Attributes</span></span>

<span data-ttu-id="1ee1d-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="1ee1d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1ee1d-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1ee1d-111">Child Elements</span></span>

|<span data-ttu-id="1ee1d-112">Element</span><span class="sxs-lookup"><span data-stu-id="1ee1d-112">Element</span></span>|<span data-ttu-id="1ee1d-113">Description</span><span class="sxs-lookup"><span data-stu-id="1ee1d-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1ee1d-114">ListEntries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="1ee1d-114">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="1ee1d-115">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="1ee1d-115">Required element.</span></span><br /><br /> <span data-ttu-id="1ee1d-116">Stellt die Definitionen der Listenansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="1ee1d-116">Provides the definitions of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1ee1d-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1ee1d-117">Parent Elements</span></span>

|<span data-ttu-id="1ee1d-118">Element</span><span class="sxs-lookup"><span data-stu-id="1ee1d-118">Element</span></span>|<span data-ttu-id="1ee1d-119">Description</span><span class="sxs-lookup"><span data-stu-id="1ee1d-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1ee1d-120">View-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="1ee1d-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="1ee1d-121">Definiert eine Ansicht, die zum Anzeigen der Member von einem oder mehreren-Objekten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1ee1d-121">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1ee1d-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ee1d-122">Remarks</span></span>

<span data-ttu-id="1ee1d-123">Weitere Informationen zum Erstellen einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="1ee1d-123">For more information about creating a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="1ee1d-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ee1d-124">Example</span></span>

<span data-ttu-id="1ee1d-125">Dieses Beispiel zeigt eine Listenansicht für das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="1ee1d-125">This example shows a list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>...</ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="1ee1d-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ee1d-126">See Also</span></span>

[<span data-ttu-id="1ee1d-127">View-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="1ee1d-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="1ee1d-128">ListEntries-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="1ee1d-128">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="1ee1d-129">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="1ee1d-129">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="1ee1d-130">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="1ee1d-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)