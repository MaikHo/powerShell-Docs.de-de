---
ms.date: 07/16/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: DSC-Ressource „WindowsFeatureSet“
ms.openlocfilehash: 856c56e0b35a26add729ef77db9dca71fdc0a4d0
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463855"
---
# <a name="dsc-windowsfeatureset-resource"></a>DSC-Ressource „WindowsFeatureSet“

> Gilt für: Windows PowerShell 5.x

Die Ressource **WindowsFeatureSet** in Windows PowerShell DSC (Desired State Configuration) bietet einen Mechanismus, um sicherzustellen, dass Rollen und Features einem Zielknoten hinzugefügt oder von diesem entfernt werden. Diese Ressource ist eine [zusammengesetzte Ressource](../../../resources/authoringResourceComposite.md), die die Ressource [WindowsFeature](windowsfeatureResource.md) für jedes Feature aufruft, das in der **Name**-Eigenschaft angegeben ist.

Verwenden Sie diese Ressource, wenn Sie verschiedene Windows-Features mit demselben Status konfigurieren möchten.

## <a name="syntax"></a>Syntax

```Syntax
WindowsFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ Source = [string] ]
    [ IncludeAllSubFeature = [Boolean] ]
    [ Credential = [PSCredential] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Eigenschaften

|  Eigenschaft  |  BESCHREIBUNG   |
|---|---|
|Name |Die Namen der Rollen oder Features an, die hinzugefügt oder entfernt werden sollen. Dies ist identisch mit der **Name**-Eigenschaft des Cmdlets [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature?view=winserver2012r2-ps) und nicht mit dem Anzeigenamen der Rollen oder Features. |
|`Source` |Gibt bei Bedarf den Speicherort der Quelldatei an, die für die Installation verwendet werden soll. |
|IncludeAllSubFeature |Legen Sie diese Eigenschaft auf `$true` fest, um alle erforderlichen Teilfeatures in die Features einzubeziehen, die Sie mit der **Name**-Eigenschaft angeben. |
|Anmeldeinformationen |Die Anmeldeinformationen zum Hinzufügen oder Entfernen der Rollen oder Features. |
|LogPath |Der Pfad zu einer Protokolldatei, in der der Ressourcenanbieter den Vorgang protokollieren soll. |

## <a name="common-properties"></a>Allgemeine Eigenschaften

|Eigenschaft |BESCHREIBUNG |
|---|---|
|DependsOn |Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird. Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Gibt an, ob die Rollen oder Features hinzugefügt werden. Um sicherzustellen, dass die Rollen oder Features hinzugefügt werden, legen Sie diese Eigenschaft auf **Present** fest. Um sicherzustellen, dass die Rollen oder Features entfernt werden, legen Sie diese Eigenschaft auf **Absent** fest. Der Standardwert ist **Present**. |
|PsDscRunAsCredential |Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest. |

> [!NOTE]
> Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen. Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).

## <a name="example"></a>Beispiel

Mit der folgenden Konfiguration wird sichergestellt, dass die Features **Webserver** (IIS) und **SMTP-Server** sowie alle Teilfeatures installiert werden.

```powershell
configuration FeatureSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        WindowsFeatureSet WindowsFeatureSetExample
        {
            Name                    = @("SMTP-Server", "Web-Server")
            Ensure                  = 'Present'
            IncludeAllSubFeature    = $true
        }
    }
}
```
