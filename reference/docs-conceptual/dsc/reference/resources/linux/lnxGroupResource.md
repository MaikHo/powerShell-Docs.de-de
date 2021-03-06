---
ms.date: 07/17/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: DSC für Linux-Resource „nxGroup“
ms.openlocfilehash: f196c74b94ec27818d58b59d1e489facd8ab0a65
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464433"
---
# <a name="dsc-for-linux-nxgroup-resource"></a>DSC für Linux-Resource „nxGroup“

Die Ressource **nxGroup** in PowerShell DSC bietet einen Mechanismus zum Verwalten lokaler Gruppen auf einem Linux-Knoten.

## <a name="syntax"></a>Syntax

```Syntax
nxGroup <string> #ResourceName
{
    GroupName = <string>
    [ Members = <string[]> ]
    [ MembersToInclude = <string[]> ]
    [ MembersToExclude = <string[]> ]
    [ PreferredGroupID = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present } ]
}
```

## <a name="properties"></a>Eigenschaften

|Eigenschaft |BESCHREIBUNG |
|---|---|
|GroupName |Gibt den Namen der Gruppe an, für die Sie einen bestimmten Zustand sicherstellen möchten. |
|Members |Gibt die Mitglieder an, die die Gruppe bilden. |
|MembersToInclude |Gibt die Benutzer an, die Mitglied dieser Gruppe werden sollen. |
|MembersToExclude |Gibt die Benutzer an, die nicht Mitglied dieser Gruppe werden sollen. |
|PreferredGroupID |Legt nach Möglichkeit die Gruppen-ID auf den angegebenen Wert fest. Wenn die Gruppen-ID derzeit verwendet wird, wird die nächste verfügbare Gruppen-ID verwendet. |

## <a name="common-properties"></a>Allgemeine Eigenschaften

|Eigenschaft |BESCHREIBUNG |
|---|---|
|DependsOn |Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird. Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Bestimmt, ob das Vorhandensein der Gruppe geprüft werden soll. Legen Sie diese Eigenschaft auf **Present** fest, um sicherzustellen, dass die Gruppe vorhanden ist. Legen Sie sie auf **Absent** fest, um sicherzustellen, dass die Gruppe nicht vorhanden ist. Der Standardwert ist **Present**. |

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird sichergestellt, dass der Benutzer „monuser“ vorhanden und Mitglied der Gruppe „DBusers“ ist.

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxUser UserExample {
       UserName = 'monuser'
       Description = 'Monitoring user'
       Password = '$6$fZAne/Qc$MZejMrOxDK0ogv9SLiBP5J5qZFBvXLnDu8HY1Oy7ycX.Y3C7mGPUfeQy3A82ev3zIabhDQnj2ayeuGn02CqE/0'
       Ensure = 'Present'
       HomeDirectory = '/home/monuser'
    }

    nxGroup GroupExample {
       GroupName = 'DBusers'
       Ensure = 'Present'
       MembersToInclude = 'monuser'
       DependsOn = '[nxUser]UserExample'
    }
}
```
