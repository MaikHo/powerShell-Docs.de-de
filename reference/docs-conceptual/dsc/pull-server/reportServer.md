---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Verwenden eines DSC-Berichtsservers
ms.openlocfilehash: 1ccd4f96b782b41b7d7c953735cb41b3ba3d2bce
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953577"
---
# <a name="using-a-dsc-report-server"></a><span data-ttu-id="af541-103">Verwenden eines DSC-Berichtsservers</span><span class="sxs-lookup"><span data-stu-id="af541-103">Using a DSC report server</span></span>

<span data-ttu-id="af541-104">Gilt für: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="af541-104">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af541-105">Der Pull-Server (Windows-Feature *DSC-Dienst*) ist eine von Windows Server unterstützte Komponente, jedoch sollen keine neuen Features oder Funktionen angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="af541-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="af541-106">Es wird empfohlen, verwaltete Clients auf [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) umzustellen (enthält Features zusätzlich zum Pull-Server unter Windows Server) oder auf eine der [hier](pullserver.md#community-solutions-for-pull-service) aufgeführten Communitylösungen.</span><span class="sxs-lookup"><span data-stu-id="af541-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>
>
> [!NOTE]
> <span data-ttu-id="af541-107">Der in diesem Thema beschriebene Berichtsserver ist in PowerShell 4.0 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="af541-107">The report server described in this topic is not available in PowerShell 4.0.</span></span>

<span data-ttu-id="af541-108">Die lokale Configuration Manager (LCM) eines Knotens kann so konfiguriert werden, dass Berichte zu seinem Konfigurationsstatus an einen Pullserver gesendet werden, der zum Abrufen dieser Daten abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="af541-108">The Local Configuration Manager (LCM) of a node can be configured to send reports about its configuration status to a pull server, which can then be queried to retrieve that data.</span></span> <span data-ttu-id="af541-109">Jedes Mal, wenn der Knoten eine Konfiguration überprüft und anwendet, wird ein Bericht zum Berichtsserver gesendet.</span><span class="sxs-lookup"><span data-stu-id="af541-109">Each time the node checks and applies a configuration, it sends a report to the report server.</span></span> <span data-ttu-id="af541-110">Diese Berichte werden in einer Datenbank auf dem Server gespeichert und können durch Aufrufen des Webdiensts für die Berichtserstellung abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="af541-110">These reports are stored in a database on the server, and can be retrieved by calling the reporting web service.</span></span> <span data-ttu-id="af541-111">Jeder Bericht enthält Informationen zu den angewendeten Konfigurationen samt Zeitpunkt, verwendeten Ressourcen, ausgelösten Fehlern sowie Start- und Endzeiten.</span><span class="sxs-lookup"><span data-stu-id="af541-111">Each report contains information such as what configurations were applied and whether they succeeded, the resources used, any errors that were thrown, and start and finish times.</span></span>

## <a name="configuring-a-node-to-send-reports"></a><span data-ttu-id="af541-112">Konfigurieren eines Knotens zum Senden von Berichten</span><span class="sxs-lookup"><span data-stu-id="af541-112">Configuring a node to send reports</span></span>

<span data-ttu-id="af541-113">Sie weisen einen Knoten im **ReportServerWeb**-Block der LCM-Konfiguration des Knotens an, Berichte zu einem Server zu senden (weitere Informationen zum Konfigurieren des LCM finden Sie unter [Konfigurieren des lokalen Konfigurations-Managers](../managing-nodes/metaConfig.md)).</span><span class="sxs-lookup"><span data-stu-id="af541-113">You tell a node to send reports to a server by using a **ReportServerWeb** block in the node's LCM configuration (for information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md)).</span></span> <span data-ttu-id="af541-114">Der Server, an den der Knoten Berichte sendet, muss als Webpullserver eingerichtet werden (Sie können keine Berichte an eine SMB-Freigabe senden).</span><span class="sxs-lookup"><span data-stu-id="af541-114">The server to which the node sends reports must be set up as a web pull server (you cannot send reports to an SMB share).</span></span> <span data-ttu-id="af541-115">Weitere Informationen zum Einrichten von Pullservern finden Sie unter [Einrichten eines DSC-Webpullservers](pullServer.md).</span><span class="sxs-lookup"><span data-stu-id="af541-115">For information about setting up a pull server, see [Setting up a DSC web pull server](pullServer.md).</span></span> <span data-ttu-id="af541-116">Der Berichtsserver kann vom selben Dienst unterstützt werden, von dem der Knoten Konfigurationen und Ressourcen abruft. Es kann sich aber auch um einen anderen Dienst handeln.</span><span class="sxs-lookup"><span data-stu-id="af541-116">The report server can be the same service from which the node pulls configurations and gets resources, or it can be a different service.</span></span>

<span data-ttu-id="af541-117">Im **ReportServerWeb**-Block geben Sie die URL des Pulldiensts und einen Registrierungsschlüssel an, der dem Server bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="af541-117">In the **ReportServerWeb** block, you specify the URL of the pull service and a registration key that is known to the server.</span></span>

<span data-ttu-id="af541-118">Die folgende Konfiguration konfiguriert einen Knoten für das Abrufen von Konfiguration per Pull von einem Dienst und Senden von Berichten an einen Dienst auf einem anderen Server.</span><span class="sxs-lookup"><span data-stu-id="af541-118">The following configuration configures a node to pull configurations from one service, and send reports to a service on a different server.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration ReportClientConfig
{
    Node localhost
    {
        Settings
        {
            RefreshMode          = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded   = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL          = 'https://CONTOSO-PULL:8080/PSDSCPullServer.svc'
            RegistrationKey    = 'bbb9778f-43f2-47de-b61e-a0daff474c6d'
            ConfigurationNames = @('ClientConfig')
        }

        ReportServerWeb CONTOSO-ReportSrv
        {
            ServerURL               = 'http://CONTOSO-REPORT:8080/PSDSCPullServer.svc'
            RegistrationKey         = 'ba39daaa-96c5-4f2f-9149-f95c46460faa'
            AllowUnsecureConnection = $true
        }
    }
}

ReportClientConfig
```

<span data-ttu-id="af541-119">Mit der folgenden Konfiguration wird ein Knoten so eingerichtet, dass er einen einzigen Server für Konfigurationen, Ressourcen und Berichterstattung verwendet.</span><span class="sxs-lookup"><span data-stu-id="af541-119">The following configuration configures a node to use a single server for configurations, resources, and reporting.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfig
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }



        ReportServerWeb CONTOSO-ReportSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfig
```

> [!NOTE]
> <span data-ttu-id="af541-120">Sie können den Webdienst beim Einrichten eines Pullservers beliebig benennen, aber die Eigenschaft **ServerURL** muss mit dem Dienstnamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="af541-120">You can name the web service whatever you want when you set up a pull server, but the **ServerURL** property must match the service name.</span></span>

## <a name="getting-report-data"></a><span data-ttu-id="af541-121">Abrufen von Berichtsdaten</span><span class="sxs-lookup"><span data-stu-id="af541-121">Getting report data</span></span>

<span data-ttu-id="af541-122">Berichte, die zum Pullserver gesendet werden, gelangen in eine Datenbank auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="af541-122">Reports sent to the pull server are entered into a database on the server.</span></span> <span data-ttu-id="af541-123">Die Berichte stehen über Aufrufe des Webdiensts zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="af541-123">The reports are available through calls to the web service.</span></span> <span data-ttu-id="af541-124">Senden Sie eine HTTP-Anforderung in der folgenden Form an den Berichtswebdienst, um Berichte für einen bestimmten Knoten zu erhalten: `http://CONTOSO-REPORT:8080/PSDSCReportServer.svc/Nodes(AgentId='MyNodeAgentId')/Reports`</span><span class="sxs-lookup"><span data-stu-id="af541-124">To retrieve reports for a specific node, send an HTTP request to the report web service in the following form: `http://CONTOSO-REPORT:8080/PSDSCReportServer.svc/Nodes(AgentId='MyNodeAgentId')/Reports`</span></span>
<span data-ttu-id="af541-125">`MyNodeAgentId` ist die Agent-ID des Knotens, für den Sie Berichte erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="af541-125">where `MyNodeAgentId` is the AgentId of the node for which you want to get reports.</span></span> <span data-ttu-id="af541-126">Durch Aufrufen von [Get-DscLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager) auf einem Knoten können Sie die Agent-ID dieses Knotens abrufen.</span><span class="sxs-lookup"><span data-stu-id="af541-126">You can get the AgentID for a node by calling [Get-DscLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager) on that node.</span></span>

<span data-ttu-id="af541-127">Die Berichte werden als ein Array von JSON-Objekten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="af541-127">The reports are returned as an array of JSON objects.</span></span>

<span data-ttu-id="af541-128">Das folgende Skript gibt die Berichte für den Knoten zurück, auf dem es ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="af541-128">The following script returns the reports for the node on which it is run:</span></span>

```powershell
function GetReport
{
    param
    (
        $AgentId = "$((glcm).AgentId)", 
        $serviceURL = "http://CONTOSO-REPORT:8080/PSDSCPullServer.svc"
    )

    $requestUri = "$serviceURL/Nodes(AgentId= '$AgentId')/Reports"
    $request = Invoke-WebRequest -Uri $requestUri  -ContentType "application/json;odata=minimalmetadata;streaming=true;charset=utf-8" `
               -UseBasicParsing -Headers @{Accept = "application/json";ProtocolVersion = "2.0"} `
               -ErrorAction SilentlyContinue -ErrorVariable ev
    $object = ConvertFrom-Json $request.content
    return $object.value
}
```

## <a name="viewing-report-data"></a><span data-ttu-id="af541-129">Anzeigen von Berichtsdaten</span><span class="sxs-lookup"><span data-stu-id="af541-129">Viewing report data</span></span>

<span data-ttu-id="af541-130">Wenn Sie eine Variable auf das Ergebnis der **GetReport**-Funktion festlegen, können Sie die einzelnen Felder in einem Element des Arrays anzeigen, das zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="af541-130">If you set a variable to the result of the **GetReport** function, you can view the individual fields in an element of the array that is returned:</span></span>

```powershell
$reports = GetReport
$reports[1]
```

```output
JobId                : 019dfbe5-f99f-11e5-80c6-001dd8b8065c
OperationType        : Consistency
RefreshMode          : Pull
Status               : Success
ReportFormatVersion  : 2.0
ConfigurationVersion : 2.0.0
StartTime            : 04/03/2016 06:21:43
EndTime              : 04/03/2016 06:22:04
RebootRequested      : False
Errors               : {}
StatusData           : {{"StartDate":"2016-04-03T06:21:43.7220000-07:00","IPV6Addresses":["2001:4898:d8:f2f2:852b:b255:b071:283b","fe80::852b:b255:b071
                       :283b%12","::2000:0:0:0","::1","::2000:0:0:0"],"DurationInSeconds":"21","JobID":"{019DFBE5-F99F-11E5-80C6-001DD8B8065C}","Curren
                       tChecksum":"A7797571CB9C3AF4D74C39A0FDA11DAF33273349E1182385528FFC1E47151F7F","MetaData":"Author: configAuthor; Name:
                       Sample_ArchiveFirewall; Version: 2.0.0; GenerationDate: 04/01/2016 15:23:30; GenerationHost: CONTOSO-PullSrv;","RebootRequested":"False
                       ","Status":"Success","IPV4Addresses":["10.240.179.151","127.0.0.1"],"LCMVersion":"2.0","ResourcesNotInDesiredState":[{"SourceInf
                       o":"C:\\ReportTest\\Sample_xFirewall_AddFirewallRule.ps1::23::9::xFirewall","ModuleName":"xNetworking","DurationInSeconds":"8.785",
                       "InstanceName":"Firewall","StartDate":"2016-04-03T06:21:56.4650000-07:00","ResourceName":"xFirewall","ModuleVersion":"2.7.0.0","
                       RebootRequested":"False","ResourceId":"[xFirewall]Firewall","ConfigurationName":"Sample_ArchiveFirewall","InDesiredState":"False
                       "}],"NumberOfResources":"2","Type":"Consistency","HostName":"CONTOSO-PULLCLI","ResourcesInDesiredState":[{"SourceInfo":"C:\\ReportTest\\Sample_xFirewall_AddFirewallRule.ps1::16::9::Archive","ModuleName":"PSDesiredStateConfiguration","DurationInSeconds":"1.848",
                       "InstanceName":"ArchiveExample","StartDate":"2016-04-03T06:21:56.4650000-07:00","ResourceName":"Archive","ModuleVersion":"1.1","
                       RebootRequested":"False","ResourceId":"[Archive]ArchiveExample","ConfigurationName":"Sample_ArchiveFirewall","InDesiredState":"T
                       rue"}],"MACAddresses":["00-1D-D8-B8-06-5C","00-00-00-00-00-00-00-E0"],"MetaConfiguration":{"AgentId":"52DA826D-00DE-4166-8ACB-73F2B46A7E00",
                       "ConfigurationDownloadManagers":[{"SourceInfo":"C:\\ReportTest\\LCMConfig.ps1::14::9::ConfigurationRepositoryWeb","A
                       llowUnsecureConnection":"True","ServerURL":"http://CONTOSO-PullSrv:8080/PSDSCPullServer.svc","RegistrationKey":"","ResourceId":"[Config
                       urationRepositoryWeb]CONTOSO-PullSrv","ConfigurationNames":["ClientConfig"]}],"ActionAfterReboot":"ContinueConfiguration","LCMCo
                       mpatibleVersions":["1.0","2.0"],"LCMState":"Idle","ResourceModuleManagers":[],"ReportManagers":[{"AllowUnsecureConnection":"True
                       ","RegistrationKey":"","ServerURL":"http://CONTOSO-PullSrv:8080/PSDSCPullServer.svc","ResourceId":"[ReportServerWeb]CONTOSO-PullSrv","S
                       ourceInfo":"C:\\ReportTest\\LCMConfig.ps1::24::9::ReportServerWeb"}],"StatusRetentionTimeInDays":"10","LCMVersion":"2.0","Config
                       urationMode":"ApplyAndMonitor","RefreshFrequencyMins":"30","RebootNodeIfNeeded":"True","RefreshMode":"Pull","DebugMode":["NONE"]
                       ,"LCMStateDetail":"","AllowModuleOverwrite":"False","ConfigurationModeFrequencyMins":"15"},"Locale":"en-US","Mode":"Pull"}}
AdditionalData       : {}
```

<span data-ttu-id="af541-131">Standardmäßig werden die Berichte nach **JobID** sortiert.</span><span class="sxs-lookup"><span data-stu-id="af541-131">By default, the reports are sorted by **JobID**.</span></span> <span data-ttu-id="af541-132">Zum Abrufen des neuesten Berichts können Sie die Berichte absteigend nach der Eigenschaft **StartTime** sortieren, und dann das erste Element des Arrays abrufen:</span><span class="sxs-lookup"><span data-stu-id="af541-132">To get the most recent report, you can sort the reports by descending **StartTime** property, and then get the first element of the array:</span></span>

```powershell
$reportsByStartTime = $reports | Sort-Object {$_."StartTime" -as [DateTime] } -Descending
$reportMostRecent = $reportsByStartTime[0]
```

<span data-ttu-id="af541-133">Beachten Sie, dass das Feld **StatusData** ein Objekt mit mehreren Eigenschaften ist.</span><span class="sxs-lookup"><span data-stu-id="af541-133">Notice that the **StatusData** property is an object with a number of properties.</span></span> <span data-ttu-id="af541-134">Hier befindet sich ein Großteil der Berichtsdaten.</span><span class="sxs-lookup"><span data-stu-id="af541-134">This is where much of the reporting data is.</span></span> <span data-ttu-id="af541-135">Sehen wir uns die einzelnen Felder der Eigenschaft **StatusData** für den aktuellen Bericht an:</span><span class="sxs-lookup"><span data-stu-id="af541-135">Let's look at the individual fields of the **StatusData** property for the most recent report:</span></span>

```powershell
$statusData = $reportMostRecent.StatusData | ConvertFrom-Json
$statusData
```

```output
StartDate                  : 2016-04-04T11:21:41.2990000-07:00
IPV6Addresses              : {2001:4898:d8:f2f2:852b:b255:b071:283b, fe80::852b:b255:b071:283b%12, ::2000:0:0:0, ::1...}
DurationInSeconds          : 25
JobID                      : {135D230E-FA92-11E5-80C6-001DD8B8065C}
CurrentChecksum            : A7797571CB9C3AF4D74C39A0FDA11DAF33273349E1182385528FFC1E47151F7F
MetaData                   : Author: configAuthor; Name: Sample_ArchiveFirewall; Version: 2.0.0; GenerationDate: 04/01/2016 15:23:30; GenerationHost:
                             CONTOSO-PullSrv;
RebootRequested            : False
Status                     : Success
IPV4Addresses              : {10.240.179.151, 127.0.0.1}
LCMVersion                 : 2.0
ResourcesNotInDesiredState : {@{SourceInfo=C:\ReportTest\Sample_xFirewall_AddFirewallRule.ps1::23::9::xFirewall; ModuleName=xNetworking;
                             DurationInSeconds=10.725; InstanceName=Firewall; StartDate=2016-04-04T11:21:55.7200000-07:00; ResourceName=xFirewall;
                             ModuleVersion=2.7.0.0; RebootRequested=False; ResourceId=[xFirewall]Firewall; ConfigurationName=Sample_ArchiveFirewall;
                             InDesiredState=False}}
NumberOfResources          : 2
Type                       : Consistency
HostName                   : CONTOSO-PULLCLI
ResourcesInDesiredState    : {@{SourceInfo=C:\ReportTest\Sample_xFirewall_AddFirewallRule.ps1::16::9::Archive; ModuleName=PSDesiredStateConfiguration;
                             DurationInSeconds=2.672; InstanceName=ArchiveExample; StartDate=2016-04-04T11:21:55.7200000-07:00; ResourceName=Archive;
                             ModuleVersion=1.1; RebootRequested=False; ResourceId=[Archive]ArchiveExample; ConfigurationName=Sample_ArchiveFirewall;
                             InDesiredState=True}}
MACAddresses               : {00-1D-D8-B8-06-5C, 00-00-00-00-00-00-00-E0}
MetaConfiguration          : @{AgentId=52DA826D-00DE-4166-8ACB-73F2B46A7E00; ConfigurationDownloadManagers=System.Object[];
                             ActionAfterReboot=ContinueConfiguration; LCMCompatibleVersions=System.Object[]; LCMState=Idle;
                             ResourceModuleManagers=System.Object[]; ReportManagers=System.Object[]; StatusRetentionTimeInDays=10; LCMVersion=2.0;
                             ConfigurationMode=ApplyAndMonitor; RefreshFrequencyMins=30; RebootNodeIfNeeded=True; RefreshMode=Pull;
                             DebugMode=System.Object[]; LCMStateDetail=; AllowModuleOverwrite=False; ConfigurationModeFrequencyMins=15}
Locale                     : en-US
Mode                       : Pull
```

<span data-ttu-id="af541-136">Unter anderem wird hier deutlich, dass die neueste Konfiguration zwei Ressourcen aufgerufen hat, von denen sich die eine im gewünschten Zustand befand und die andere nicht.</span><span class="sxs-lookup"><span data-stu-id="af541-136">Among other things, this shows that the most recent configuration called two resources, and that one of them was in the desired state, and one of them was not.</span></span> <span data-ttu-id="af541-137">So können Sie eine besser lesbare Ausgabe der Eigenschaft **ResourcesNotInDesiredState** erzeugen:</span><span class="sxs-lookup"><span data-stu-id="af541-137">You can get a more readable output of just the **ResourcesNotInDesiredState** property:</span></span>

```powershell
$statusData.ResourcesInDesiredState
```

```output
SourceInfo        : C:\ReportTest\Sample_xFirewall_AddFirewallRule.ps1::16::9::Archive
ModuleName        : PSDesiredStateConfiguration
DurationInSeconds : 2.672
InstanceName      : ArchiveExample
StartDate         : 2016-04-04T11:21:55.7200000-07:00
ResourceName      : Archive
ModuleVersion     : 1.1
RebootRequested   : False
ResourceId        : [Archive]ArchiveExample
ConfigurationName : Sample_ArchiveFirewall
InDesiredState    : True
```

<span data-ttu-id="af541-138">Beachten Sie, dass diese Beispiele dazu dienen, Ihnen eine Vorstellung der Möglichkeiten von Berichtsdaten zu geben.</span><span class="sxs-lookup"><span data-stu-id="af541-138">Note that these examples are meant to give you an idea of what you can do with report data.</span></span> <span data-ttu-id="af541-139">Eine Einführung in das Arbeiten mit JSON in PowerShell finden Sie unter [Arbeiten mit JSON und PowerShell](https://blogs.technet.microsoft.com/heyscriptingguy/2015/10/08/playing-with-json-and-powershell/).</span><span class="sxs-lookup"><span data-stu-id="af541-139">For an introduction on working with JSON in PowerShell, see [Playing with JSON and PowerShell](https://blogs.technet.microsoft.com/heyscriptingguy/2015/10/08/playing-with-json-and-powershell/).</span></span>

## <a name="see-also"></a><span data-ttu-id="af541-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="af541-140">See Also</span></span>

[<span data-ttu-id="af541-141">Konfigurieren des lokalen Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="af541-141">Configuring the Local Configuration Manager</span></span>](../managing-nodes/metaConfig.md)

[<span data-ttu-id="af541-142">Einrichten eines DSC-Webpullservers</span><span class="sxs-lookup"><span data-stu-id="af541-142">Setting up a DSC web pull server</span></span>](pullServer.md)

[<span data-ttu-id="af541-143">Einrichten eines Pullclients mithilfe von Konfigurationsnamen</span><span class="sxs-lookup"><span data-stu-id="af541-143">Setting up a pull client using configuration names</span></span>](pullClientConfigNames.md)