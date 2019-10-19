---
ms.date: 09/20/2019
keywords: dsc,powershell,configuration,setup
title: DSC-Ressource „ServiceSet“
ms.openlocfilehash: 97c25f46940d69ed6c696e2692e29131e9a997b0
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953027"
---
# <a name="dsc-serviceset-resource"></a><span data-ttu-id="88528-103">DSC-Ressource „ServiceSet“</span><span class="sxs-lookup"><span data-stu-id="88528-103">DSC ServiceSet Resource</span></span>

> <span data-ttu-id="88528-104">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="88528-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="88528-105">Die Ressource **ServiceSet** in Windows PowerShell DSC bietet einen Mechanismus zum Verwalten von Diensten auf dem Zielknoten.</span><span class="sxs-lookup"><span data-stu-id="88528-105">The **ServiceSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span> <span data-ttu-id="88528-106">Diese Ressource ist eine [zusammengesetzte Ressource](../../../resources/authoringResourceComposite.md), die die Ressource [Service](serviceResource.md) für jeden Dienst aufruft, der in der **Name**-Eigenschaft angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="88528-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [Service resource](serviceResource.md) for each service specified in the **Name** property.</span></span>

<span data-ttu-id="88528-107">Verwenden Sie diese Ressource, wenn Sie verschiedene Dienste mit demselben Status konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="88528-107">Use this resource when you want to configure a number of services to the same state.</span></span>

## <a name="syntax"></a><span data-ttu-id="88528-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="88528-108">Syntax</span></span>

```Syntax
ServiceSet [string] #ResourceName
{
    Name = [string[]]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="88528-109">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="88528-109">Properties</span></span>

|<span data-ttu-id="88528-110">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="88528-110">Property</span></span> |<span data-ttu-id="88528-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88528-111">Description</span></span> |
|---|---|
|<span data-ttu-id="88528-112">Name</span><span class="sxs-lookup"><span data-stu-id="88528-112">Name</span></span> |<span data-ttu-id="88528-113">Gibt den Namen des Diensts an.</span><span class="sxs-lookup"><span data-stu-id="88528-113">Indicates the service names.</span></span> <span data-ttu-id="88528-114">Beachten Sie, dass sich dieser mitunter vom Anzeigenamen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="88528-114">Note that sometimes this is different from the display names.</span></span> <span data-ttu-id="88528-115">Mit dem Cmdlet `Get-Service` können Sie eine Liste der Dienste und ihren aktuellen Status abrufen.</span><span class="sxs-lookup"><span data-stu-id="88528-115">You can get a list of the services and their current state with the `Get-Service` cmdlet.</span></span> |
|<span data-ttu-id="88528-116">StartupType</span><span class="sxs-lookup"><span data-stu-id="88528-116">StartupType</span></span> |<span data-ttu-id="88528-117">Gibt den Starttyp für die Dienste an.</span><span class="sxs-lookup"><span data-stu-id="88528-117">Indicates the startup type for the services.</span></span> <span data-ttu-id="88528-118">Die für diese Eigenschaft zulässigen Werte sind: **Automatic**, **Disabled** und **Manual**.</span><span class="sxs-lookup"><span data-stu-id="88528-118">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**.</span></span> |
|<span data-ttu-id="88528-119">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="88528-119">BuiltInAccount</span></span> |<span data-ttu-id="88528-120">Gibt das zu verwendende Anmeldekonto für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="88528-120">Indicates the sign-in account to use for the services.</span></span> <span data-ttu-id="88528-121">Die für diese Eigenschaft zulässigen Werte sind: **LocalService**, **LocalSystem** und **NetworkService**.</span><span class="sxs-lookup"><span data-stu-id="88528-121">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span> |
|<span data-ttu-id="88528-122">Status</span><span class="sxs-lookup"><span data-stu-id="88528-122">State</span></span> |<span data-ttu-id="88528-123">Gibt den Status an, den Sie für die Dienste sicherstellen möchten. **Stopped** oder **Running**.</span><span class="sxs-lookup"><span data-stu-id="88528-123">Indicates the state you want to ensure for the services: **Stopped** or **Running**.</span></span> |
|<span data-ttu-id="88528-124">Credential</span><span class="sxs-lookup"><span data-stu-id="88528-124">Credential</span></span> |<span data-ttu-id="88528-125">Gibt die Anmeldeinformationen für das Konto an, unter dem die Dienstressource ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="88528-125">Indicates credentials for the account that the service resource will run under.</span></span> <span data-ttu-id="88528-126">Diese Eigenschaft und die **BuiltinAccount**-Eigenschaft können nicht zusammen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="88528-126">This property and the **BuiltinAccount** property cannot be used together.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="88528-127">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="88528-127">Common properties</span></span>

|<span data-ttu-id="88528-128">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="88528-128">Property</span></span> |<span data-ttu-id="88528-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88528-129">Description</span></span> |
|---|---|
|<span data-ttu-id="88528-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="88528-130">DependsOn</span></span> |<span data-ttu-id="88528-131">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="88528-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="88528-132">Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="88528-132">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="88528-133">Ensure</span><span class="sxs-lookup"><span data-stu-id="88528-133">Ensure</span></span> |<span data-ttu-id="88528-134">Gibt an, ob die Dienste auf dem System vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="88528-134">Indicates whether the services exist on the system.</span></span> <span data-ttu-id="88528-135">Legen Sie diese Eigenschaft auf **Absent** fest, um sicherzustellen, dass die Dienste nicht vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="88528-135">Set this property to **Absent** to ensure that the services do not exist.</span></span> <span data-ttu-id="88528-136">Das Festlegen auf **Present** stellt sicher, dass der Zieldienst vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="88528-136">Setting it to **Present** ensures that target services exist.</span></span> <span data-ttu-id="88528-137">Der Standardwert ist **Present**.</span><span class="sxs-lookup"><span data-stu-id="88528-137">The default value is **Present**.</span></span> |
|<span data-ttu-id="88528-138">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="88528-138">PsDscRunAsCredential</span></span> |<span data-ttu-id="88528-139">Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest.</span><span class="sxs-lookup"><span data-stu-id="88528-139">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="88528-140">Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="88528-140">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="88528-141">Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).</span><span class="sxs-lookup"><span data-stu-id="88528-141">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="88528-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="88528-142">Example</span></span>

<span data-ttu-id="88528-143">Die folgende Konfiguration startet die Dienste „Windows-Audio“ und „Remotedesktopdienste“.</span><span class="sxs-lookup"><span data-stu-id="88528-143">The following configuration starts the "Windows Audio" and "Remote Desktop Services" services.</span></span>

```powershell
configuration ServiceSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {
        ServiceSet ServiceSetExample
        {
            Name        = @("TermService", "Audiosrv")
            StartupType = "Manual"
            State       = "Running"
        }
    }
}
```