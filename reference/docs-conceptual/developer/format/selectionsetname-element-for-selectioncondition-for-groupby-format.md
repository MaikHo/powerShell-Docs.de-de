---
title: Selectionsetname-Element für selectioncondition für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 6d0263aa335287f20be5b94a8eb65696d06d82a8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772619"
---
# <a name="selectionsetname-element-for-selectioncondition-for-groupby-format"></a>Element „SelectionSetName“ für SelectionCondition für GroupBy (Format)

Gibt den Satz von .NET-Typen an, die die Bedingung auslöst. Wenn einer der Typen in diesem Satz vorhanden ist, wird die Bedingung erfüllt, und das Objekt wird mithilfe dieses Steuer Elements angezeigt. Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) entryselectedby-Element für customentry für GroupBy (Format) selectioncondition-Element für entryselectedby für GroupBy (Format) selectionsetname-Element für selectioncondition für GroupBy (Format)

## <a name="syntax"></a>Syntax

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionSetName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen des Auswahl Satzes an.

## <a name="remarks"></a>Bemerkungen

Auswahl Sätze sind allgemeine Gruppen von .NET-Objekten, die von jeder Sicht verwendet werden können, die von der Formatierungs Datei definiert wird. Weitere Informationen zum Erstellen und referenzieren von Auswahl Sätzen finden Sie unter [Definieren von Auswahl Sätzen](./defining-selection-sets.md).

Wenn dieses Element angegeben ist, können Sie das [tygtame](./typename-element-for-selectioncondition-for-groupby-format.md) -Element nicht angeben. Weitere Informationen zum Definieren von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).

## <a name="see-also"></a>Weitere Informationen

[Element „TypeName“ für SelectionCondition für GroupBy (Format)](./typename-element-for-selectioncondition-for-groupby-format.md)

[Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md)

[Definieren von Auswahlgruppen](./defining-selection-sets.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
