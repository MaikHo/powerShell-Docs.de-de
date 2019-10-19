---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Aktualisieren von Knoten von einem Pullserver
ms.openlocfilehash: 4333a5bf82ef45f22a062942ebe93409433623f5
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2019
ms.locfileid: "71955097"
---
# <a name="update-nodes-from-a-pull-server"></a><span data-ttu-id="6be88-103">Aktualisieren von Knoten von einem Pullserver</span><span class="sxs-lookup"><span data-stu-id="6be88-103">Update Nodes from a Pull Server</span></span>

<span data-ttu-id="6be88-104">Die folgenden Abschnitte gehen davon aus, dass Sie bereits einen Pullserver eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="6be88-104">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="6be88-105">Wenn Sie noch keinen Pullserver eingerichtet haben, können Sie die folgenden Anleitungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="6be88-105">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="6be88-106">Einrichten eines DSC-SMB-Pullservers</span><span class="sxs-lookup"><span data-stu-id="6be88-106">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="6be88-107">Einrichten eines DSC-HTTP-Pullservers</span><span class="sxs-lookup"><span data-stu-id="6be88-107">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="6be88-108">Jeder Zielknoten kann zum Herunterladen von Konfigurationen, Ressourcen und sogar zum Berichten seines Status konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="6be88-108">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="6be88-109">Dieser Artikel zeigt Ihnen, wie Sie Ressourcen hochladen können, damit sie zum Download zur Verfügung stehen, und wie Sie Clients so konfigurieren, dass sie Ressourcen automatisch herunterladen.</span><span class="sxs-lookup"><span data-stu-id="6be88-109">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="6be88-110">Wenn der Knoten eine zugewiesene Konfiguration empfängt (durch **Pull** oder **Push** (v5)), lädt er automatisch alle für die Konfiguration erforderlichen Ressourcen vom in LCM angegebenen Speicherort herunter.</span><span class="sxs-lookup"><span data-stu-id="6be88-110">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="using-the-update-dscconfiguration-cmdlet"></a><span data-ttu-id="6be88-111">Verwenden des Cmdlets „Update-DSCConfiguration“</span><span class="sxs-lookup"><span data-stu-id="6be88-111">Using the Update-DSCConfiguration cmdlet</span></span>

<span data-ttu-id="6be88-112">Ab PowerShell 5.0 erzwingt das Cmdlet [Update-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration), dass ein Knoten seine Konfiguration aus dem in LCM konfigurierten Pullserver aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6be88-112">Beginning in PowerShell 5.0, the [Update-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration) cmdlet, forces a Node to update its configuration from the Pull Server configured in the LCM.</span></span>

```powershell
Update-DSCConfiguration -ComputerName "Server01"
```

## <a name="using-invoke-cimmethod"></a><span data-ttu-id="6be88-113">Verwenden von „Invoke-CimMethod“</span><span class="sxs-lookup"><span data-stu-id="6be88-113">Using Invoke-CIMMethod</span></span>

<span data-ttu-id="6be88-114">In PowerShell 4.0 können Sie einen Pullclient weiterhin manuell zwingen, seine Konfiguration mithilfe von [Invoke-CIMMethod](/powershell/module/cimcmdlets/invoke-cimmethod) zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6be88-114">In PowerShell 4.0, you can still manually force a Pull Client to update its Configuration using [Invoke-CIMMethod](/powershell/module/cimcmdlets/invoke-cimmethod).</span></span> <span data-ttu-id="6be88-115">Das folgende Beispiel erstellt eine CIM-Sitzung mit angegebenen Anmeldeinformationen, ruft die entsprechende CIM-Methode auf und entfernt die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="6be88-115">The following example creates a CIM session with specified credentials, invokes the appropriate CIM method, and removes the session.</span></span>

```powershell
$cimSession = New-CimSession -ComputerName "Server01" -Credential $(Get-Credential)
Invoke-CimMethod -CimSession $cimSession -Namespace 'root/microsoft/windows/desiredstateconfiguration' -Class 'MSFT_DscLocalConfigurationManager' -MethodName 'PerformRequiredConfigurationChecks' -Arguments @{ 'Flags' = [uint32]1 } -Verbose
$cimSession | Remove-CimSession
```

## <a name="see-also"></a><span data-ttu-id="6be88-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6be88-116">See Also</span></span>

[<span data-ttu-id="6be88-117">PerformRequiredConfigurationChecks</span><span class="sxs-lookup"><span data-stu-id="6be88-117">PerformRequiredConfigurationChecks</span></span>](/powershell/dsc/msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks)