---
title: AccessDBProviderSample01 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 853b7e5d-76c1-490e-8269-0ef31ba2ff13
caps.latest.revision: 10
ms.openlocfilehash: dc1ae92af8a57d6197b595db8e098256ac444b78
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359999"
---
# <a name="accessdbprovidersample01"></a><span data-ttu-id="eeb14-102">AccessDBProviderSample01</span><span class="sxs-lookup"><span data-stu-id="eeb14-102">AccessDBProviderSample01</span></span>

<span data-ttu-id="eeb14-103">Dieses Beispiel zeigt, wie Sie eine Anbieter Klasse deklarieren, die direkt von der [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="eeb14-103">This sample shows how to declare a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span> <span data-ttu-id="eeb14-104">Wird hier nur aus Gründen der Vollständigkeit aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="eeb14-104">It is included here only for completeness.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="eeb14-105">Deutlich</span><span class="sxs-lookup"><span data-stu-id="eeb14-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eeb14-106">Ihre Anbieter Klasse wird wahrscheinlich von einer der folgenden Klassen abgeleitet und kann möglicherweise andere Anbieter Schnittstellen implementieren:</span><span class="sxs-lookup"><span data-stu-id="eeb14-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> -   <span data-ttu-id="eeb14-107">[System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="eeb14-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="eeb14-108">Siehe [AccessDBProviderSample03](./accessdbprovidersample03.md).</span><span class="sxs-lookup"><span data-stu-id="eeb14-108">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> -   <span data-ttu-id="eeb14-109">[System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="eeb14-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="eeb14-110">Siehe [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="eeb14-110">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> -   <span data-ttu-id="eeb14-111">[System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="eeb14-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="eeb14-112">Siehe [AccessDBProviderSample05](./accessdbprovidersample05.md).</span><span class="sxs-lookup"><span data-stu-id="eeb14-112">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="eeb14-113">Weitere Informationen zum Auswählen der Anbieter Klasse, von der basierend auf den Anbieter Features abgeleitet werden soll, finden [Sie unter Entwerfen des Windows PowerShell-Anbieters](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="eeb14-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="eeb14-114">In diesem Beispiel wird Folgendes veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="eeb14-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="eeb14-115">Deklarieren des `CmdletProvider`-Attributs.</span><span class="sxs-lookup"><span data-stu-id="eeb14-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="eeb14-116">Definieren einer Anbieter Klasse, die direkt von der [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="eeb14-116">Defining a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span>

## <a name="example"></a><span data-ttu-id="eeb14-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eeb14-117">Example</span></span>

<span data-ttu-id="eeb14-118">Dieses Beispiel zeigt, wie Sie eine Anbieter Klasse definieren und das `CmdletProvider`-Attribut deklarieren.</span><span class="sxs-lookup"><span data-stu-id="eeb14-118">This sample shows how to define a provider class and how to declare the `CmdletProvider` attribute.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Providers
{
  using System.Management.Automation;
  using System.Management.Automation.Provider;

  /// <summary>
  /// This sample shows how to declare a provider class and how to
  /// declare the CmdletProvider attribute.
  /// </summary>
  [CmdletProvider("AccessDB", ProviderCapabilities.None)]
  public class AccessDBProvider : CmdletProvider
  {
    // Add provider logic here.
  }
}
```

## <a name="see-also"></a><span data-ttu-id="eeb14-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eeb14-119">See Also</span></span>

[<span data-ttu-id="eeb14-120">System. Management. Automation. Provider. itemcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="eeb14-120">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="eeb14-121">System. Management. Automation. Provider. containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="eeb14-121">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="eeb14-122">System. Management. Automation. Provider. navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="eeb14-122">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="eeb14-123">Entwerfen Ihres Windows PowerShell-Anbieters</span><span class="sxs-lookup"><span data-stu-id="eeb14-123">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)