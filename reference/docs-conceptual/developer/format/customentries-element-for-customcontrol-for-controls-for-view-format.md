---
title: Customentries-Element für CustomControl für Steuerelemente für Ansicht (Format) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3485958a-ba87-4932-907c-a8f140c4abdb
caps.latest.revision: 8
ms.openlocfilehash: 4856aee930285781a101868bd6cb67824585bce1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368809"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a><span data-ttu-id="16ece-102">Element „CustomEntries“ für CustomControl für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="16ece-102">CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

<span data-ttu-id="16ece-103">Stellt die Definitionen für das-Steuerelement bereit.</span><span class="sxs-lookup"><span data-stu-id="16ece-103">Provides the definitions for the control.</span></span> <span data-ttu-id="16ece-104">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="16ece-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="16ece-105">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) steuert Element (Format) Steuerelement (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelement für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für Steuerelemente für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="16ece-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="16ece-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="16ece-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="16ece-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="16ece-107">Attributes and Elements</span></span>

<span data-ttu-id="16ece-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und übergeordnete Elemente des `CustomEntries`-Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="16ece-108">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="16ece-109">Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="16ece-109">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="16ece-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="16ece-110">Attributes</span></span>

<span data-ttu-id="16ece-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="16ece-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="16ece-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16ece-112">Child Elements</span></span>

|<span data-ttu-id="16ece-113">Element</span><span class="sxs-lookup"><span data-stu-id="16ece-113">Element</span></span>|<span data-ttu-id="16ece-114">Description</span><span class="sxs-lookup"><span data-stu-id="16ece-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="16ece-115">Customentry-Element für customentries für Steuerelemente für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="16ece-115">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="16ece-116">Erforderliches Element.</span><span class="sxs-lookup"><span data-stu-id="16ece-116">Required element.</span></span><br /><br /> <span data-ttu-id="16ece-117">Stellt eine Definition des-Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="16ece-117">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="16ece-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16ece-118">Parent Elements</span></span>

|<span data-ttu-id="16ece-119">Element</span><span class="sxs-lookup"><span data-stu-id="16ece-119">Element</span></span>|<span data-ttu-id="16ece-120">Description</span><span class="sxs-lookup"><span data-stu-id="16ece-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="16ece-121">CustomControl-Element für Steuerelemente für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="16ece-121">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="16ece-122">Definiert das Steuerelement, das von der Ansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="16ece-122">Defines the control used by the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="16ece-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16ece-123">Remarks</span></span>

<span data-ttu-id="16ece-124">In den meisten Fällen verfügt ein Steuerelement nur über eine Definition, die in einem einzelnen `CustomEntry`-Element angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="16ece-124">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="16ece-125">Es ist jedoch möglich, mehrere Definitionen bereitzustellen, wenn Sie das gleiche Steuerelement zum Anzeigen verschiedener .NET-Objekte verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="16ece-125">However, it is possible to provide multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="16ece-126">In diesen Fällen können Sie ein `CustomEntry`-Element für jedes Objekt oder jede Gruppe von Objekten definieren.</span><span class="sxs-lookup"><span data-stu-id="16ece-126">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="16ece-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="16ece-127">See Also</span></span>

[<span data-ttu-id="16ece-128">Customentry-Element für customentries für Steuerelemente für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="16ece-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="16ece-129">CustomControl-Element für Steuerelemente für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="16ece-129">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="16ece-130">Schreiben einer PowerShell-Formatierungs Datei</span><span class="sxs-lookup"><span data-stu-id="16ece-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)