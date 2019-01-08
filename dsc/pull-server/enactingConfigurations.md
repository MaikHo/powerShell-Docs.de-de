---
ms.date: 10/16/2017
keywords: dsc,powershell,configuration,setup
title: Inkraftsetzung von Konfigurationen
ms.openlocfilehash: 4a6e7e511446ab27307683ad3d5676391e7c791c
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2018
ms.locfileid: "53401904"
---
# <a name="enacting-configurations"></a><span data-ttu-id="45d6e-103">Inkraftsetzung von Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="45d6e-103">Enacting configurations</span></span>

><span data-ttu-id="45d6e-104">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="45d6e-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="45d6e-105">Es gibt zwei Möglichkeiten, PowerShell DSC-Konfigurationen (Desired State Configuration) anzuwenden: Push- und Pullmodus.</span><span class="sxs-lookup"><span data-stu-id="45d6e-105">There are two ways to enact PowerShell Desired State Configuration (DSC) configurations: push mode and pull mode.</span></span>

## <a name="push-mode"></a><span data-ttu-id="45d6e-106">Pushmodus</span><span class="sxs-lookup"><span data-stu-id="45d6e-106">Push mode</span></span>

<span data-ttu-id="45d6e-107">![Pushmodus](../images/pushModel.png "Funktionsweise des Pushmodus")</span><span class="sxs-lookup"><span data-stu-id="45d6e-107">![Push mode](../images/pushModel.png "How push mode works")</span></span>

<span data-ttu-id="45d6e-108">Der Pushmodus bezieht sich auf einen Benutzer, der eine Konfiguration durch Aufrufen des Cmdlets [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) aktiv auf einen Zielknoten anwendet.</span><span class="sxs-lookup"><span data-stu-id="45d6e-108">Push mode refers to a user actively applying a configuration to a target node by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

<span data-ttu-id="45d6e-109">Nach dem Erstellen und Kompilieren einer Konfiguration können Sie sie im Pushmodus anwenden, indem Sie das Cmdlet [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) aufrufen und den Parameter „-Path“ des Cmdlets auf den Pfad festlegen, in dem sich die MOF-Konfigurationsdatei befindet.</span><span class="sxs-lookup"><span data-stu-id="45d6e-109">After creating and compiling a configuration, you can enact it in push mode by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet, setting the -Path parameter of the cmdlet to the path where the configuration MOF is located.</span></span>
<span data-ttu-id="45d6e-110">Wenn sich die MOF-Konfigurationsdatei z.B. in `C:\DSC\Configurations\localhost.mof` befindet, wenden Sie sie mit dem folgenden Befehl auf den lokalen Computer an: `Start-DscConfiguration -Path 'C:\DSC\Configurations'`.</span><span class="sxs-lookup"><span data-stu-id="45d6e-110">For example, if the configuration MOF is located at `C:\DSC\Configurations\localhost.mof`, you would apply it to the local machine with the following command: `Start-DscConfiguration -Path 'C:\DSC\Configurations'`</span></span>

> <span data-ttu-id="45d6e-111">__Hinweis__: Standardmäßig wird eine Konfiguration von DSC als Hintergrundauftrag ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="45d6e-111">__Note__: By default, DSC runs a configuration as a background job.</span></span> <span data-ttu-id="45d6e-112">Um die Konfiguration interaktiv auszuführen, rufen Sie das Cmdlet [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) mit dem __-Wait__-Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="45d6e-112">To run the configuration interactively, call the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) with the __-Wait__ parameter.</span></span>

## <a name="pull-mode"></a><span data-ttu-id="45d6e-113">Pullmodus</span><span class="sxs-lookup"><span data-stu-id="45d6e-113">Pull mode</span></span>

<span data-ttu-id="45d6e-114">![Pullmodus](../images/pullModel.png "Funktionsweise des Pullmodus")</span><span class="sxs-lookup"><span data-stu-id="45d6e-114">![Pull Mode](../images/pullModel.png "How pull mode works")</span></span>

<span data-ttu-id="45d6e-115">Im Pullmodus werden Pullclients so konfiguriert, dass sie ihre Konfigurationen des gewünschten Zustands von einem Remotepulldienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="45d6e-115">In pull mode, pull clients are configured to get their desired state configurations from a remote pull service.</span></span>
<span data-ttu-id="45d6e-116">Der Pulldienst muss so eingerichtet werden, dass er den DSC-Dienst hostet und mit den Konfigurationen und Ressourcen versehen wird, die von den Pullclients benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="45d6e-116">Likewise, the pull service has been set up to host the DSC service, and has been provisioned with the configurations and resources that are required by the pull clients.</span></span>
<span data-ttu-id="45d6e-117">Jeder der Pullclients weist ein geplantes Ereignis auf, das für die Konfiguration auf dem Knoten eine regelmäßige Kompatibilitätsprüfung durchführt.</span><span class="sxs-lookup"><span data-stu-id="45d6e-117">Each of the pull clients has a scheduled event that performs a periodic compliance check on the configuration of the node.</span></span>
<span data-ttu-id="45d6e-118">Wenn das Ereignis erstmals ausgelöst wird, sendet der lokale Konfigurations-Manager (LCM) auf dem Pullclient eine Anforderung an den Pulldienst, um die im LCM angegebene Konfiguration abzurufen.</span><span class="sxs-lookup"><span data-stu-id="45d6e-118">When the event is triggered the first time, the Local Configuration Manager (LCM) on the pull client makes a request to the pull service to get the configuration specified in the LCM.</span></span>
<span data-ttu-id="45d6e-119">Wenn diese Konfiguration auf dem Pulldienst vorhanden ist und anfängliche Überprüfungen besteht, wird die Konfiguration auf den Pullclient heruntergeladen, auf dem sie vom LCM ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="45d6e-119">If that configuration exists on the pull service, and it passes initial validation checks, the configuration is downloaded to the pull client, where it is then executed by the LCM.</span></span>

<span data-ttu-id="45d6e-120">Entsprechend den Einstellungen der Eigenschaft **ConfigurationModeFrequencyMins** des LCMs überprüft dieser in regelmäßigen Abständen, ob der Client mit der Konfiguration übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="45d6e-120">The LCM checks that the client is in compliance with the configuration at regular intervals specified by the **ConfigurationModeFrequencyMins** property of the LCM.</span></span>
<span data-ttu-id="45d6e-121">Entsprechend den Einstellungen der Eigenschaft **RefreshModeFrequency** des LCMs sucht dieser in regelmäßigen Abständen nach aktualisierten Konfigurationen auf dem Pulldienst.</span><span class="sxs-lookup"><span data-stu-id="45d6e-121">The LCM checks for updated configurations on the pull service at regular intervals specified by the **RefreshModeFrequency** property of the LCM.</span></span>
<span data-ttu-id="45d6e-122">Informationen zum Konfigurieren des LCMs finden Sie unter [Konfigurieren des lokalen Konfigurations-Managers](../managing-nodes/metaConfig.md).</span><span class="sxs-lookup"><span data-stu-id="45d6e-122">For information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md).</span></span>

<span data-ttu-id="45d6e-123">Die empfohlene Lösung für das Hosten eines Pulldiensts ist der DSC-Clouddienst, [Azure Automation](https://azure.microsoft.com/services/automation/).</span><span class="sxs-lookup"><span data-stu-id="45d6e-123">The recommended solution for hosting a Pull Service, is the DSC cloud service, [Azure Automation](https://azure.microsoft.com/services/automation/).</span></span>
<span data-ttu-id="45d6e-124">Diese gehostete Lösung ermöglicht eine grafische Verwaltung, Berichterstellung und zentrale Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="45d6e-124">This is hosted solution provides graphical management, reporting, and centralized administration.</span></span>

<span data-ttu-id="45d6e-125">Weitere Informationen zum Einrichten eines Pulldiensts unter Windows Server finden Sie unter [Einrichten eines DSC-Webpullservers](pullServer.md).</span><span class="sxs-lookup"><span data-stu-id="45d6e-125">For more information on setting up a Pull Service on Windows Server, see [Setting up a DSC web pull server](pullServer.md).</span></span>
<span data-ttu-id="45d6e-126">Beachten Sie jedoch, dass die Funktionen dieser Implementierung eingeschränkt sind und dass einige Integrationsschritte manuell durchgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="45d6e-126">Understand however, that this implementation has limited features and does require some "do it yourself" integration.</span></span>

<span data-ttu-id="45d6e-127">In den folgenden Themen werden Pulldienst und -clients erläutert:</span><span class="sxs-lookup"><span data-stu-id="45d6e-127">The following topics explain pull service and clients:</span></span>

- [<span data-ttu-id="45d6e-128">Azure Automation DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="45d6e-128">Azure Automation DSC Overview</span></span>](https://docs.microsoft.com/en-us/azure/automation/automation-dsc-overview)
- [<span data-ttu-id="45d6e-129">Einrichten eines SMB-Pullservers</span><span class="sxs-lookup"><span data-stu-id="45d6e-129">Setting up an SMB pull server</span></span>](pullServerSMB.md)
- [<span data-ttu-id="45d6e-130">Konfigurieren eines Pullclients</span><span class="sxs-lookup"><span data-stu-id="45d6e-130">Configuring a pull client</span></span>](pullClientConfigID.md)