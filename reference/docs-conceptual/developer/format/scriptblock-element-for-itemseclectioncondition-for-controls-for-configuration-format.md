---
title: ScriptBlock-Element für itemabclectioncondition für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51f7aec9-7b01-4370-84f4-1e58508a851f
caps.latest.revision: 6
ms.openlocfilehash: e92b2dfff07358132c480c47c34279e5365fe400
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362119"
---
# <a name="scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="cb023-102">Element „ScriptBlock“ für ItemSeclectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="cb023-102">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="cb023-103">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="cb023-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="cb023-104">Wenn dieses Skript `true` ausgewertet wird, wird die Bedingung erfüllt, und das-Steuerelement wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb023-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="cb023-105">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="cb023-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="cb023-106">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl for Configuration ( Format) customentry-Element für CustomControl für Steuerelemente für Configuration (Format) customItem-Element für customentry für Steuerelemente für das Configuration ExpressionBinding-Element für customItem für Steuerelemente für die Konfiguration (Format) Itemselectioncondition-Element für ExpressionBinding für Steuerelemente für das Configuration (Format) ScriptBlock-Element für itemselectioncondition für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="cb023-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cb023-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb023-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cb023-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cb023-108">Attributes and Elements</span></span>

<span data-ttu-id="cb023-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des `ScriptBlock`-Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cb023-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cb023-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="cb023-110">Attributes</span></span>

<span data-ttu-id="cb023-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="cb023-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cb023-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cb023-112">Child Elements</span></span>

<span data-ttu-id="cb023-113">Keine.</span><span class="sxs-lookup"><span data-stu-id="cb023-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cb023-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cb023-114">Parent Elements</span></span>

|<span data-ttu-id="cb023-115">Element</span><span class="sxs-lookup"><span data-stu-id="cb023-115">Element</span></span>|<span data-ttu-id="cb023-116">Description</span><span class="sxs-lookup"><span data-stu-id="cb023-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cb023-117">Itemselectioncondition-Element für ExpressionBinding für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="cb023-117">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="cb023-118">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="cb023-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="cb023-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="cb023-119">Text Value</span></span>

<span data-ttu-id="cb023-120">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="cb023-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb023-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cb023-121">Remarks</span></span>

<span data-ttu-id="cb023-122">Wenn dieses Element verwendet wird, können Sie beim Definieren der Auswahlbedingung nicht das [propertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) -Element angeben.</span><span class="sxs-lookup"><span data-stu-id="cb023-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb023-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb023-123">See Also</span></span>

[<span data-ttu-id="cb023-124">PropertyName-Element für itemabclectioncondition für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="cb023-124">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="cb023-125">Itemselectioncondition-Element für ExpressionBinding für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="cb023-125">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="cb023-126">Schreiben einer PowerShell-Formatierungs Datei</span><span class="sxs-lookup"><span data-stu-id="cb023-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)