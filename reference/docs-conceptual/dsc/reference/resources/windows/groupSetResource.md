---
ms.date: 09/20/2019
keywords: dsc,powershell,configuration,setup
description: Stellt einen Mechanismus zum Verwalten lokaler Gruppen auf dem Zielknoten zur Verfügung.
title: DSC-Ressource „GroupSet“
ms.openlocfilehash: d36274741b2c96a0852f384ccf5d187ac8d27131
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953177"
---
# <a name="dsc-groupset-resource"></a><span data-ttu-id="2b860-104">DSC-Ressource „GroupSet“</span><span class="sxs-lookup"><span data-stu-id="2b860-104">DSC GroupSet Resource</span></span>

> <span data-ttu-id="2b860-105">Gilt für: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="2b860-105">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="2b860-106">Die Ressource **GroupSet** in Windows PowerShell DSC bietet einen Mechanismus zum Verwalten lokaler Gruppen auf dem Zielknoten.</span><span class="sxs-lookup"><span data-stu-id="2b860-106">The **GroupSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on the target node.</span></span> <span data-ttu-id="2b860-107">Diese Ressource ist eine [zusammengesetzte Ressource](../../../resources/authoringResourceComposite.md), die die Ressource [Group](groupResource.md) für jede Gruppe aufruft, die im `GroupName`-Parameter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="2b860-107">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [Group resource](groupResource.md) for each group specified in the `GroupName` parameter.</span></span>

<span data-ttu-id="2b860-108">Verwenden Sie diese Ressource, wenn Sie dieselbe Liste von Mitgliedern mehreren Gruppen hinzufügen oder aus diesen entfernen möchten, mehr als eine Gruppe entfernen möchten oder mehr als eine Gruppe mit derselben Liste von Mitgliedern hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="2b860-108">Use this resource when you want to add and/or remove the same list of members to more than one group, remove more than one group, or add more than one group with the same list of members.</span></span>

## <a name="syntax"></a><span data-ttu-id="2b860-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b860-109">Syntax</span></span>

```Syntax
Group [string] #ResourceName
{
    GroupName = [string[]]
    [ Members = [string[]] ]
    [ Description = [string[]] ]
    [ MembersToInclude = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="2b860-110">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2b860-110">Properties</span></span>

|<span data-ttu-id="2b860-111">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2b860-111">Property</span></span> |<span data-ttu-id="2b860-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b860-112">Description</span></span> |
|---|---|
|<span data-ttu-id="2b860-113">GroupName</span><span class="sxs-lookup"><span data-stu-id="2b860-113">GroupName</span></span> |<span data-ttu-id="2b860-114">Die Namen der Gruppen, für die Sie einen bestimmten Zustand sicherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="2b860-114">The names of the groups for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="2b860-115">Members</span><span class="sxs-lookup"><span data-stu-id="2b860-115">Members</span></span> |<span data-ttu-id="2b860-116">Verwenden Sie diese Eigenschaft, um die aktuelle Gruppenmitgliedschaft durch die angegebenen Member zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="2b860-116">Use this property to replace the current group membership with the specified members.</span></span> <span data-ttu-id="2b860-117">Der Wert dieser Eigenschaft ist ein Zeichenfolgenarray im Format `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="2b860-117">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="2b860-118">Wenn Sie diese Eigenschaft in einer Konfiguration festlegen, verwenden Sie weder die Eigenschaft **MembersToExclude** noch die Eigenschaft **MembersToInclude**.</span><span class="sxs-lookup"><span data-stu-id="2b860-118">If you set this property in a configuration, do not use either the **MembersToExclude** or **MembersToInclude** property.</span></span> <span data-ttu-id="2b860-119">Andernfalls wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="2b860-119">Doing so will generate an error.</span></span> |
|<span data-ttu-id="2b860-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b860-120">Description</span></span> |<span data-ttu-id="2b860-121">Die Beschreibung der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="2b860-121">The description of the group.</span></span> |
|<span data-ttu-id="2b860-122">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="2b860-122">MembersToInclude</span></span> |<span data-ttu-id="2b860-123">Verwenden Sie diese Eigenschaft, um Member zur vorhandenen Gruppenmitgliedschaft hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2b860-123">Use this property to add members to the existing membership of the group.</span></span> <span data-ttu-id="2b860-124">Der Wert dieser Eigenschaft ist ein Zeichenfolgenarray im Format `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="2b860-124">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="2b860-125">Wenn Sie diese Eigenschaft in einer Konfiguration festgelegt haben, verwenden Sie die Eigenschaft **Members** nicht.</span><span class="sxs-lookup"><span data-stu-id="2b860-125">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="2b860-126">Andernfalls wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="2b860-126">Doing so will generate an error.</span></span> |
|<span data-ttu-id="2b860-127">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="2b860-127">MembersToExclude</span></span> |<span data-ttu-id="2b860-128">Verwenden Sie diese Eigenschaft, um Mitglieder aus der vorhandenen Gruppenmitgliedschaft zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="2b860-128">Use this property to remove members from the existing membership of the groups.</span></span> <span data-ttu-id="2b860-129">Der Wert dieser Eigenschaft ist ein Zeichenfolgenarray im Format `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="2b860-129">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="2b860-130">Wenn Sie diese Eigenschaft in einer Konfiguration festgelegt haben, verwenden Sie die Eigenschaft **Members** nicht.</span><span class="sxs-lookup"><span data-stu-id="2b860-130">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="2b860-131">Andernfalls wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="2b860-131">Doing so will generate an error.</span></span> |
|<span data-ttu-id="2b860-132">Credential</span><span class="sxs-lookup"><span data-stu-id="2b860-132">Credential</span></span> |<span data-ttu-id="2b860-133">Die Anmeldeinformationen für den Zugriff auf Remoteressourcen.</span><span class="sxs-lookup"><span data-stu-id="2b860-133">The credentials required to access remote resources.</span></span> <span data-ttu-id="2b860-134">Dieses Konto muss die entsprechenden Active Directory-Berechtigungen aufweisen, um alle nicht lokalen Konten zur Gruppe hinzuzufügen. Andernfalls tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="2b860-134">This account must have the appropriate Active Directory permissions to add all non-local accounts to the group; otherwise, an error will occur.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="2b860-135">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2b860-135">Common properties</span></span>

|<span data-ttu-id="2b860-136">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2b860-136">Property</span></span> |<span data-ttu-id="2b860-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b860-137">Description</span></span> |
|---|---|
|<span data-ttu-id="2b860-138">DependsOn</span><span class="sxs-lookup"><span data-stu-id="2b860-138">DependsOn</span></span> |<span data-ttu-id="2b860-139">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="2b860-139">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="2b860-140">Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="2b860-140">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="2b860-141">Ensure</span><span class="sxs-lookup"><span data-stu-id="2b860-141">Ensure</span></span> |<span data-ttu-id="2b860-142">Gibt an, ob die Gruppen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2b860-142">Indicates whether the groups exist.</span></span> <span data-ttu-id="2b860-143">Legen Sie diese Eigenschaft auf **Absent** fest, um sicherzustellen, dass die Gruppen nicht vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2b860-143">Set this property to **Absent** to ensure that the groups do not exist.</span></span> <span data-ttu-id="2b860-144">Das Festlegen auf **Present** stellt sicher, dass die Gruppen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2b860-144">Setting it to **Present** ensures that the groups exist.</span></span> <span data-ttu-id="2b860-145">Der Standardwert ist **Present**.</span><span class="sxs-lookup"><span data-stu-id="2b860-145">The default value is **Present**.</span></span> |
|<span data-ttu-id="2b860-146">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="2b860-146">PsDscRunAsCredential</span></span> |<span data-ttu-id="2b860-147">Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest.</span><span class="sxs-lookup"><span data-stu-id="2b860-147">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="2b860-148">Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="2b860-148">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="2b860-149">Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).</span><span class="sxs-lookup"><span data-stu-id="2b860-149">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example-1-ensuring-groups-are-present"></a><span data-ttu-id="2b860-150">Beispiel 1: Sicherstellen, dass Gruppen vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="2b860-150">Example 1: Ensuring Groups are present</span></span>

<span data-ttu-id="2b860-151">Im folgenden Beispiel wird gezeigt, wie Sie sicherstellen, dass die beiden Gruppen „myGroup“ und „myOtherGroup“ vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2b860-151">The following example shows how to ensure that two groups called "myGroup" and "myOtherGroup" are present.</span></span>

```powershell
configuration GroupSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {
        GroupSet GroupSetTest
        {
            GroupName        = @("myGroup", "myOtherGroup")
            Ensure           = "Present"
            MembersToInclude = @("contoso\alice", "contoso\bob")
            MembersToExclude = $("contoso\john")
            Credential       = Get-Credential
        }
    }
}
$cd = @{
    AllNodes = @(
        @{
            NodeName                    = 'localhost'
            PSDscAllowPlainTextPassword = $true
            PSDscAllowDomainUser        = $true
        }
    )
}

GroupSetTest -ConfigurationData $cd
```

> [!NOTE]
> <span data-ttu-id="2b860-152">In diesem Beispiel werden der Einfachheit halber unverschlüsselte Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b860-152">This example uses plaintext credentials for simplicity.</span></span> <span data-ttu-id="2b860-153">Informationen zum Verschlüsseln von Anmeldeinformationen in der MOF-Konfigurationsdatei finden Sie unter [Schützen der MOF-Datei](../../../pull-server/secureMOF.md).</span><span class="sxs-lookup"><span data-stu-id="2b860-153">For information about how to encrypt credentials in the configuration MOF file, see [Securing the MOF File](../../../pull-server/secureMOF.md).</span></span>