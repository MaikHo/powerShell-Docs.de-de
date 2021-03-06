---
title: ColumnNumber-Element für widecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 5f151bb0e629efcebe6295cdcae6cebcbbb1b39b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783856"
---
# <a name="columnnumber-element-for-widecontrol-format"></a>Element „ColumnNumber“ für WideControl (Format)

Gibt die Anzahl der Spalten an, die in der breiten Ansicht angezeigt werden.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) widecontrol-Element (Format) ColumnNumber-Element für widecontrol (Format)

## <a name="syntax"></a>Syntax

```xml
<ColumnNumber>PositiveInteger</ColumnNumber>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ColumnNumber` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[Element „WideControl“ (Format)](./widecontrol-element-format.md)|Definiert ein breites Listenformat (Einzelwert) für die Sicht.|

## <a name="text-value"></a>Textwert

Geben Sie einen positiven ganzzahligen Wert an.

## <a name="remarks"></a>Bemerkungen

Wenn Sie eine breite Sicht definieren, können Sie das- `AutoSize` Element oder das-Element hinzufügen `ColumnNumber` , aber Sie können nicht beides hinzufügen.

Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).

Ein Beispiel für eine breite Ansicht finden Sie unter [Wide View (Basic)](./wide-view-basic.md).

## <a name="see-also"></a>Weitere Informationen

[AutoSize-Element für widecontrol (Format)](./autosize-element-for-widecontrol-format.md)

[Erstellen einer breiten Ansicht](./creating-a-wide-view.md)

[Breite Ansicht (Basic)](./wide-view-basic.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
