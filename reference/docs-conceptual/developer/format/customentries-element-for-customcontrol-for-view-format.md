---
title: Customentries-Element für CustomControl für Ansicht (Format) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb412831-94f7-4054-b19e-32c1b14c66dd
caps.latest.revision: 11
ms.openlocfilehash: 827baacd22ef258dd9b0c8a383a23fce7d975f7f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364079"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a><span data-ttu-id="03b20-102">Element „CustomEntries“ für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="03b20-102">CustomEntries Element for CustomControl for View (Format)</span></span>

<span data-ttu-id="03b20-103">Stellt die Definitionen der benutzerdefinierten Steuerelement Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="03b20-103">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="03b20-104">Die benutzerdefinierte Steuerelement Ansicht muss mindestens eine Definition angeben.</span><span class="sxs-lookup"><span data-stu-id="03b20-104">The custom control view must specify one or more definitions.</span></span>

<span data-ttu-id="03b20-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="03b20-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="03b20-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="03b20-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="03b20-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="03b20-107">Attributes and Elements</span></span>

<span data-ttu-id="03b20-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des `CustomControlEntries`-Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="03b20-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlEntries` element.</span></span> <span data-ttu-id="03b20-109">Sie müssen mindestens ein untergeordnetes Element angeben.</span><span class="sxs-lookup"><span data-stu-id="03b20-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="03b20-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="03b20-110">Attributes</span></span>

<span data-ttu-id="03b20-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="03b20-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="03b20-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="03b20-112">Child Elements</span></span>

|<span data-ttu-id="03b20-113">Element</span><span class="sxs-lookup"><span data-stu-id="03b20-113">Element</span></span>|<span data-ttu-id="03b20-114">Description</span><span class="sxs-lookup"><span data-stu-id="03b20-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="03b20-115">Customentry-Element für customentries für View (Format)</span><span class="sxs-lookup"><span data-stu-id="03b20-115">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="03b20-116">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="03b20-116">Required element.</span></span><br /><br /> <span data-ttu-id="03b20-117">Stellt eine Definition der benutzerdefinierten Steuerelement Ansicht bereit.</span><span class="sxs-lookup"><span data-stu-id="03b20-117">Provides a definition of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="03b20-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="03b20-118">Parent Elements</span></span>

|<span data-ttu-id="03b20-119">Element</span><span class="sxs-lookup"><span data-stu-id="03b20-119">Element</span></span>|<span data-ttu-id="03b20-120">Description</span><span class="sxs-lookup"><span data-stu-id="03b20-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="03b20-121">CustomControl-Element für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="03b20-121">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)|<span data-ttu-id="03b20-122">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="03b20-122">Required element.</span></span><br /><br /> <span data-ttu-id="03b20-123">Definiert ein benutzerdefiniertes Steuerelement Format für die Ansicht.</span><span class="sxs-lookup"><span data-stu-id="03b20-123">Defines a custom control format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="03b20-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03b20-124">Remarks</span></span>

<span data-ttu-id="03b20-125">In den meisten Fällen verfügt ein Steuerelement nur über eine Definition, die in einem einzelnen `CustomEntry`-Element definiert ist.</span><span class="sxs-lookup"><span data-stu-id="03b20-125">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="03b20-126">Es ist jedoch möglich, mehrere Definitionen zu verwenden, wenn Sie das gleiche Steuerelement verwenden möchten, um unterschiedliche .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="03b20-126">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="03b20-127">In diesen Fällen können Sie ein `CustomEntry`-Element für jedes Objekt oder jede Gruppe von Objekten definieren.</span><span class="sxs-lookup"><span data-stu-id="03b20-127">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="03b20-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="03b20-128">See Also</span></span>

[<span data-ttu-id="03b20-129">CustomControl-Element für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="03b20-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="03b20-130">Customentry-Element für customentries für View (Format)</span><span class="sxs-lookup"><span data-stu-id="03b20-130">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="03b20-131">Schreiben einer PowerShell-Formatierungs Datei</span><span class="sxs-lookup"><span data-stu-id="03b20-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)