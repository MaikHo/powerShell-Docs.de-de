---
title: Frame-Element für customItem für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: fa435b8d6b868d2d7c94b7926321d94edc2ec290
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781476"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a>Element „Frame“ für CustomItem für Controls für Configuration (Format)

Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts. Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.

Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl for Configuration (Format) customentry-Element für CustomControl for Controls for Configuration (Format) customItem-Element für customentry für Steuerelemente für das Configuration Frame-Element für customItem

## <a name="syntax"></a>Syntax

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `Frame` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`CustomItem Element`|Erforderliches Element|
|[Element „FirstLineHanging“ für Frame für Controls für Configuration (Format)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Gibt an, wie viele Zeichen die erste Zeile der Daten nach links verschoben wird.|
|[Element „FirstLineIndent“ für Frame für Controls für Configuration (Format)](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Gibt an, wie viele Zeichen die erste Zeile der Daten nach rechts verschoben wird.|
|[Element „LeftIndent“ für Frame für Controls für Configuration (Format)](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Gibt an, wie viele Zeichen die Daten vom linken Rand entfernt werden.|
|[Element „RightIndent“ für Frame für Controls für Configuration (Format)](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|Optionales Element.<br /><br /> Gibt an, wie viele Zeichen die Daten vom rechten Rand entfernt werden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[CustomItem-Element für customentry für Steuerelemente für die Konfiguration](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|Definiert, welche Daten vom Steuerelement angezeigt werden und wie es angezeigt wird.|

## <a name="remarks"></a>Bemerkungen

Sie können die Elemente [firstlinehanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) und [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) nicht im selben Element angeben `Frame` .

## <a name="see-also"></a>Weitere Informationen

[Element „FirstLineHanging“ für Frame für Controls für Configuration (Format)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[Element „FirstLineIndent“ für Frame für Controls für Configuration (Format)](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[Element „LeftIndent“ für Frame für Controls für Configuration (Format)](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[Element „RightIndent“ für Frame für Controls für Configuration (Format)](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[CustomItem-Element für customentry für Steuerelemente für die Konfiguration](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
