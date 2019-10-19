---
title: AccessDBProviderSample04 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3a7e56-7331-4f71-9ecb-7a59b8021c68
caps.latest.revision: 10
ms.openlocfilehash: 7096f8066568c214a5902f6943a2c093932d3b56
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366339"
---
# <a name="accessdbprovidersample04"></a><span data-ttu-id="3572b-102">AccessDBProviderSample04</span><span class="sxs-lookup"><span data-stu-id="3572b-102">AccessDBProviderSample04</span></span>

<span data-ttu-id="3572b-103">Dieses Beispiel zeigt, wie Sie Container Methoden überschreiben, um Aufrufe der Cmdlets "`Copy-Item`", "`Get-ChildItem`", "`New-Item`" und "`Remove-Item`" zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3572b-103">This sample shows how to overwrite container methods to support calls to the `Copy-Item`, `Get-ChildItem`, `New-Item`, and `Remove-Item` cmdlets.</span></span> <span data-ttu-id="3572b-104">Diese Methoden sollten implementiert werden, wenn der Datenspeicher Elemente enthält, die Container sind.</span><span class="sxs-lookup"><span data-stu-id="3572b-104">These methods should be implemented when the data store contains items that are containers.</span></span> <span data-ttu-id="3572b-105">Ein Container ist eine Gruppe von untergeordneten Elementen unter einem gemeinsamen übergeordneten Element.</span><span class="sxs-lookup"><span data-stu-id="3572b-105">A container is a group of child items under a common parent item.</span></span> <span data-ttu-id="3572b-106">Die Anbieter Klasse in diesem Beispiel wird von der [System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) -Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="3572b-106">The provider class in this sample derives from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="3572b-107">Deutlich</span><span class="sxs-lookup"><span data-stu-id="3572b-107">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3572b-108">Ihre Anbieter Klasse wird wahrscheinlich von [System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="3572b-108">Your provider class will most likely derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)</span></span>

<span data-ttu-id="3572b-109">In diesem Beispiel wird Folgendes veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="3572b-109">This sample demonstrates the following:</span></span>

- <span data-ttu-id="3572b-110">Deklarieren des `CmdletProvider`-Attributs.</span><span class="sxs-lookup"><span data-stu-id="3572b-110">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="3572b-111">Definieren einer Anbieter Klasse, die von der [System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="3572b-111">Defining a provider class that derives from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span>

- <span data-ttu-id="3572b-112">Überschreiben der [System. Management. Automation. Provider. containercmdletprovider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) -Methode, um das Verhalten des Cmdlets "`Copy-Item`" zu ändern, das dem Benutzer ermöglicht, Elemente von einem Speicherort in einen anderen zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="3572b-112">Overwriting the [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) method to change the behavior of the `Copy-Item` cmdlet which allows the user to copy items from one location to another.</span></span> <span data-ttu-id="3572b-113">(In diesem Beispiel wird nicht gezeigt, wie dem `Copy-Item`-Cmdlet dynamische Parameter hinzugefügt werden.)</span><span class="sxs-lookup"><span data-stu-id="3572b-113">(This sample does not show how to add dynamic parameters to the `Copy-Item` cmdlet.)</span></span>

- <span data-ttu-id="3572b-114">Überschreiben der [System. Management. Automation. Provider. containercmdletprovider. getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) -Methode, um das Verhalten des Cmdlets "Get-ChildItems" zu ändern, mit dem der Benutzer die untergeordneten Elemente des übergeordneten Elements abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="3572b-114">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method to change the behavior of the Get-ChildItems cmdlet, which allows the user to retrieve the child items of the parent item.</span></span> <span data-ttu-id="3572b-115">(Dieses Beispiel zeigt nicht, wie dem Cmdlet "Get-ChildItems" dynamische Parameter hinzugefügt werden.)</span><span class="sxs-lookup"><span data-stu-id="3572b-115">(This sample does not show how to add dynamic parameters to the Get-ChildItems cmdlet.)</span></span>

- <span data-ttu-id="3572b-116">Überschreiben der [System. Management. Automation. Provider. containercmdletprovider. getchildnames \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) -Methode, um das Verhalten des Cmdlets "Get-ChildItems" zu ändern, wenn der `Name`-Parameter des Cmdlets angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3572b-116">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) method to change the behavior of the Get-ChildItems cmdlet when the `Name` parameter of the cmdlet is specified.</span></span>

- <span data-ttu-id="3572b-117">Überschreiben der [System. Management. Automation. Provider. containercmdletprovider. netwitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) -Methode, um das Verhalten des Cmdlets "`New-Item`" zu ändern, das dem Benutzer das Hinzufügen von Elementen zum Datenspeicher ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="3572b-117">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method to change the behavior of the `New-Item` cmdlet, which allows the user to add items to the data store.</span></span> <span data-ttu-id="3572b-118">(In diesem Beispiel wird nicht gezeigt, wie dem `New-Item`-Cmdlet dynamische Parameter hinzugefügt werden.)</span><span class="sxs-lookup"><span data-stu-id="3572b-118">(This sample does not show how to add dynamic parameters to the `New-Item` cmdlet.)</span></span>

- <span data-ttu-id="3572b-119">Überschreiben der [System. Management. Automation. Provider. containercmdletprovider. RemoveItem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) -Methode, um das Verhalten des Cmdlets "`Remove-Item`" zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3572b-119">Overwriting the [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) method to change the behavior of the `Remove-Item` cmdlet.</span></span> <span data-ttu-id="3572b-120">(In diesem Beispiel wird nicht gezeigt, wie dem `Remove-Item`-Cmdlet dynamische Parameter hinzugefügt werden.)</span><span class="sxs-lookup"><span data-stu-id="3572b-120">(This sample does not show how to add dynamic parameters to the `Remove-Item` cmdlet.)</span></span>

## <a name="example"></a><span data-ttu-id="3572b-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3572b-121">Example</span></span>

<span data-ttu-id="3572b-122">Dieses Beispiel zeigt, wie Sie die Methoden überschreiben, die zum Kopieren, erstellen und Entfernen von Elementen erforderlich sind, sowie Methoden zum erhalten der untergeordneten Elemente eines übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="3572b-122">This sample shows how to overwrite the methods needed to copy, create, and remove items, as well as methods for getting the child items of a parent item.</span></span>

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L1635 "AccessDBProviderSample04.cs")]

## <a name="see-also"></a><span data-ttu-id="3572b-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3572b-123">See Also</span></span>

[<span data-ttu-id="3572b-124">System. Management. Automation. Provider. itemcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="3572b-124">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="3572b-125">System. Management. Automation. Provider. containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="3572b-125">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="3572b-126">System. Management. Automation. Provider. navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="3572b-126">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="3572b-127">Entwerfen Ihres Windows PowerShell-Anbieters</span><span class="sxs-lookup"><span data-stu-id="3572b-127">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)