---
title: AccessDBProviderSample06 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46dc0657-110f-4367-8bb6-a95dca2c5016
caps.latest.revision: 8
ms.openlocfilehash: 9c00ec6de987729fec42dc57245a949d11e31f4b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366329"
---
# <a name="accessdbprovidersample06"></a><span data-ttu-id="82d8e-102">AccessDBProviderSample06</span><span class="sxs-lookup"><span data-stu-id="82d8e-102">AccessDBProviderSample06</span></span>

<span data-ttu-id="82d8e-103">Dieses Beispiel zeigt, wie Inhalts Methoden überschrieben werden, um Aufrufe der Cmdlets "`Clear-Content`", "`Get-Content`" und "`Set-Content`" zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="82d8e-103">This sample shows how to overwrite content methods to support calls to the `Clear-Content`, `Get-Content`, and `Set-Content` cmdlets.</span></span> <span data-ttu-id="82d8e-104">Diese Methoden sollten implementiert werden, wenn der Benutzer den Inhalt der Elemente im Datenspeicher verwaltet muss.</span><span class="sxs-lookup"><span data-stu-id="82d8e-104">These methods should be implemented when the user needs to manage the content of the items in the data store.</span></span> <span data-ttu-id="82d8e-105">Die Anbieter Klasse in diesem Beispiel wird von der [System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Klasse abgeleitet und implementiert die [System. Management. Automation. Provider. icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="82d8e-105">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class, and it implements the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="82d8e-106">Deutlich</span><span class="sxs-lookup"><span data-stu-id="82d8e-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82d8e-107">Ihre Anbieter Klasse wird wahrscheinlich von einer der folgenden Klassen abgeleitet und kann möglicherweise andere Anbieter Schnittstellen implementieren:</span><span class="sxs-lookup"><span data-stu-id="82d8e-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> -   <span data-ttu-id="82d8e-108">[System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="82d8e-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="82d8e-109">Siehe [AccessDBProviderSample03](./accessdbprovidersample03.md).</span><span class="sxs-lookup"><span data-stu-id="82d8e-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> -   <span data-ttu-id="82d8e-110">[System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="82d8e-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="82d8e-111">Siehe [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="82d8e-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> -   <span data-ttu-id="82d8e-112">[System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="82d8e-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="82d8e-113">Weitere Informationen zum Auswählen der Anbieter Klasse, von der basierend auf den Anbieter Features abgeleitet werden soll, finden [Sie unter Entwerfen des Windows PowerShell-Anbieters](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="82d8e-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="82d8e-114">In diesem Beispiel wird Folgendes veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="82d8e-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="82d8e-115">Deklarieren des `CmdletProvider`-Attributs.</span><span class="sxs-lookup"><span data-stu-id="82d8e-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="82d8e-116">Definieren einer Anbieter Klasse, die von der [System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Klasse abgeleitet wird und die die [System. Management. Automation. Provider. icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) -Schnittstelle deklariert.</span><span class="sxs-lookup"><span data-stu-id="82d8e-116">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class and that declares the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span>

- <span data-ttu-id="82d8e-117">Überschreiben der [System. Management. Automation. Provider. icontentcmdletprovider. ClearContent \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) -Methode, um das Verhalten des Cmdlets "`Clear-Content`" zu ändern, sodass der Benutzer den Inhalt aus einem Element entfernen kann.</span><span class="sxs-lookup"><span data-stu-id="82d8e-117">Overwriting the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method to change the behavior of the `Clear-Content` cmdlet, allowing the user to remove the content from an item.</span></span> <span data-ttu-id="82d8e-118">(In diesem Beispiel wird nicht gezeigt, wie dem `Clear-Content`-Cmdlet dynamische Parameter hinzugefügt werden.)</span><span class="sxs-lookup"><span data-stu-id="82d8e-118">(This sample does not show how to add dynamic parameters to the `Clear-Content` cmdlet.)</span></span>

- <span data-ttu-id="82d8e-119">Überschreiben der [System. Management. Automation. Provider. icontentcmdletprovider. getcontentreader \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) -Methode, um das Verhalten des Cmdlets "`Get-Content`" zu ändern, sodass der Benutzer den Inhalt eines Elements abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="82d8e-119">Overwriting the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) method to change the behavior of the `Get-Content` cmdlet, allowing the user to retrieve the content of an item.</span></span> <span data-ttu-id="82d8e-120">(In diesem Beispiel wird nicht gezeigt, wie dem `Get-Content`-Cmdlet dynamische Parameter hinzugefügt werden.)</span><span class="sxs-lookup"><span data-stu-id="82d8e-120">(This sample does not show how to add dynamic parameters to the `Get-Content` cmdlet.).</span></span>

- <span data-ttu-id="82d8e-121">Überschreiben der [Microsoft. PowerShell. Commands. filesystemprovider. getcontentwriter \*](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) -Methode, um das Verhalten des Cmdlets "`Set-Content`" zu ändern, sodass der Benutzer den Inhalt eines Elements aktualisieren kann.</span><span class="sxs-lookup"><span data-stu-id="82d8e-121">Overwriting the [Microsoft.PowerShell.Commands.Filesystemprovider.Getcontentwriter\*](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) method to change the behavior of the `Set-Content` cmdlet, allowing the user to update the content of an item.</span></span> <span data-ttu-id="82d8e-122">(In diesem Beispiel wird nicht gezeigt, wie dem `Set-Content`-Cmdlet dynamische Parameter hinzugefügt werden.)</span><span class="sxs-lookup"><span data-stu-id="82d8e-122">(This sample does not show how to add dynamic parameters to the `Set-Content` cmdlet.)</span></span>

## <a name="example"></a><span data-ttu-id="82d8e-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="82d8e-123">Example</span></span>

<span data-ttu-id="82d8e-124">Dieses Beispiel zeigt, wie Sie die Methoden überschreiben, die zum Löschen, abrufen und Festlegen des Inhalts von Elementen in einer Microsoft Access-Datenbasis erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="82d8e-124">This sample shows how to overwrite the methods needed to clear, get, and set the content of items in a Microsoft Access data base.</span></span>

[!code-csharp[AccessDBProviderSample06.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L2399 "AccessDBProviderSample06.cs")]

## <a name="see-also"></a><span data-ttu-id="82d8e-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="82d8e-125">See Also</span></span>

[<span data-ttu-id="82d8e-126">System. Management. Automation. Provider. itemcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="82d8e-126">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="82d8e-127">System. Management. Automation. Provider. containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="82d8e-127">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="82d8e-128">System. Management. Automation. Provider. navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="82d8e-128">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="82d8e-129">Entwerfen Ihres Windows PowerShell-Anbieters</span><span class="sxs-lookup"><span data-stu-id="82d8e-129">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)