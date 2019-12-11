---
title: Erstellen eines einfachen Windows PowerShell-Anbieters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- base provider [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], base provider
ms.assetid: 11eeea41-15c8-47ad-9016-0f4b72573305
caps.latest.revision: 7
ms.openlocfilehash: e825581b96f0f33893b38f9f6499dd46a7bf38eb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360519"
---
# <a name="creating-a-basic-windows-powershell-provider"></a><span data-ttu-id="c6c3b-102">Erstellen eines Windows PowerShell-Standardanbieters</span><span class="sxs-lookup"><span data-stu-id="c6c3b-102">Creating a Basic Windows PowerShell Provider</span></span>

<span data-ttu-id="c6c3b-103">Dieses Thema stellt den Ausgangspunkt für das Erstellen eines Windows PowerShell-Anbieters dar.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-103">This topic is the starting point for learning how to create a Windows PowerShell provider.</span></span> <span data-ttu-id="c6c3b-104">Der hier beschriebene grundlegende Anbieter bietet Methoden zum Starten und Beenden des Anbieters, und obwohl dieser Anbieter keine Mittel zum Zugreifen auf einen Datenspeicher oder zum Abrufen oder Festlegen der Daten im Datenspeicher bereitstellt, stellt er die grundlegenden Funktionen bereit, die für erforderlich sind. alle Anbieter.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-104">The basic provider described here provides methods for starting and stopping the provider, and although this provider does not provide a means to access a data store or to get or set the data in the data store, it does provide the basic functionality that is required by all providers.</span></span>

<span data-ttu-id="c6c3b-105">Wie bereits erwähnt, implementiert der hier beschriebene grundlegende Anbieter Methoden zum Starten und Beenden des Anbieters.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-105">As mentioned previously, the basic provider described here implements methods for starting and stopping the provider.</span></span> <span data-ttu-id="c6c3b-106">Die Windows PowerShell-Laufzeit ruft diese Methoden auf, um den Anbieter zu initialisieren und deren Initialisierung zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-106">The Windows PowerShell runtime calls these methods to initialize and uninitialize the provider.</span></span>

> [!NOTE]
> <span data-ttu-id="c6c3b-107">Sie finden ein Beispiel dieses Anbieters in der AccessDBSampleProvider01.cs-Datei, die von Windows PowerShell bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-107">You can find a sample of this provider in the AccessDBSampleProvider01.cs file provided by Windows PowerShell.</span></span>

## <a name="defining-the-windows-powershell-provider-class"></a><span data-ttu-id="c6c3b-108">Definieren der Windows PowerShell-Anbieter Klasse</span><span class="sxs-lookup"><span data-stu-id="c6c3b-108">Defining the Windows PowerShell Provider Class</span></span>

<span data-ttu-id="c6c3b-109">Der erste Schritt beim Erstellen eines Windows PowerShell-Anbieters ist die Definition der .NET-Klasse.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-109">The first step in creating a Windows PowerShell provider is to define its .NET class.</span></span> <span data-ttu-id="c6c3b-110">Dieser grundlegende Anbieter definiert eine Klasse mit dem Namen "`AccessDBProvider`", die von der [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) -Basisklasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-110">This basic provider defines a class called `AccessDBProvider` that derives from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) base class.</span></span>

<span data-ttu-id="c6c3b-111">Es wird empfohlen, die Anbieter Klassen in einem `Providers`-Namespace ihres API-Namespace zu platzieren, z. b. xxx. PowerShell. Providers.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-111">It is recommended that you place your provider classes in a `Providers` namespace of your API namespace, for example, xxx.PowerShell.Providers.</span></span> <span data-ttu-id="c6c3b-112">Dieser Anbieter verwendet den `Microsoft.Samples.PowerShell.Provider`-Namespace, in dem alle Windows PowerShell-Anbieter Beispiele ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-112">This provider uses the `Microsoft.Samples.PowerShell.Provider` namespace, in which all Windows PowerShell provider samples run.</span></span>

> [!NOTE]
> <span data-ttu-id="c6c3b-113">Die-Klasse für einen Windows PowerShell-Anbieter muss explizit als public gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-113">The class for a Windows PowerShell provider must be explicitly marked as public.</span></span> <span data-ttu-id="c6c3b-114">Klassen, die nicht als public gekennzeichnet sind, werden standardmäßig intern verwendet und werden von der Windows PowerShell-Laufzeit nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-114">Classes not marked as public will default to internal and will not be found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="c6c3b-115">Hier ist die Klassendefinition für diesen grundlegenden Anbieter:</span><span class="sxs-lookup"><span data-stu-id="c6c3b-115">Here is the class definition for this basic provider:</span></span>

[!code-csharp[AccessDBProviderSample01.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs#L23-L24 "AccessDBProviderSample01.cs")]

<span data-ttu-id="c6c3b-116">Direkt vor der Klassendefinition müssen Sie das [System. Management. Automation. Provider. cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) -Attribut mit der Syntax [cmdletprovider ()] deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-116">Right before the class definition, you must declare the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute, with the syntax [CmdletProvider()].</span></span>

<span data-ttu-id="c6c3b-117">Sie können Attribut Schlüsselwörter festlegen, um die Klasse bei Bedarf weiter zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-117">You can set attribute keywords to further declare the class if necessary.</span></span> <span data-ttu-id="c6c3b-118">Beachten Sie, dass das [System. Management. Automation. Provider. cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) -Attribut, das hier deklariert ist, zwei Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-118">Notice that the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute declared here includes two parameters.</span></span> <span data-ttu-id="c6c3b-119">Der erste Attribut Parameter gibt den standardmäßigen anzeigen Amen für den Anbieter an, der vom Benutzer später geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-119">The first attribute parameter specifies the default-friendly name for the provider, which the user can modify later.</span></span> <span data-ttu-id="c6c3b-120">Der zweite Parameter gibt die Windows PowerShell-definierten Funktionen an, die der Anbieter während der Befehls Verarbeitung für die Windows PowerShell-Laufzeit verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-120">The second parameter specifies the Windows PowerShell-defined capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span> <span data-ttu-id="c6c3b-121">Die möglichen Werte für die Anbieter Funktionen werden von der [System. Management. Automation. Provider. providerfunktionalitäten](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) -Enumeration definiert.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-121">The possible values for the provider capabilities are defined by the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="c6c3b-122">Da es sich hierbei um einen Basis Anbieter handelt, werden keine Funktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-122">Because this is a base provider, it supports no capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="c6c3b-123">Der voll qualifizierte Name des Windows PowerShell-Anbieters schließt den Assemblynamen und andere Attribute ein, die von Windows PowerShell bei der Registrierung des Anbieters festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-123">The fully qualified name of the Windows PowerShell provider includes the assembly name and other attributes determined by Windows PowerShell upon registration of the provider.</span></span>

## <a name="defining-provider-specific-state-information"></a><span data-ttu-id="c6c3b-124">Definieren Anbieter spezifischer Zustandsinformationen</span><span class="sxs-lookup"><span data-stu-id="c6c3b-124">Defining Provider-Specific State Information</span></span>

<span data-ttu-id="c6c3b-125">Die [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) -Basisklasse und alle abgeleiteten Klassen werden als zustandslos angesehen, weil die Windows PowerShell-Laufzeit nur dann Anbieter Instanzen erstellt, wenn dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-125">The [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) base class and all derived classes are considered stateless because the Windows PowerShell runtime creates provider instances only as required.</span></span> <span data-ttu-id="c6c3b-126">Wenn Ihr Anbieter eine vollständige Kontrolle und Zustands Verwaltung für anbieterspezifische Daten erfordert, muss daher eine Klasse von der [System. Management. Automation. ProviderInfo](/dotnet/api/System.Management.Automation.ProviderInfo) -Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-126">Therefore, if your provider requires full control and state maintenance for provider-specific data, it must derive a class from the [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) class.</span></span> <span data-ttu-id="c6c3b-127">Ihre abgeleitete Klasse sollte die für die Beibehaltung des Zustands erforderlichen Elemente definieren, damit auf die anbieterspezifischen Daten zugegriffen werden kann, wenn die Windows PowerShell-Laufzeit die [System. Management. Automation. Provider. cmdletprovider. Start \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) -Methode aufruft. Initialisieren Sie den Anbieter.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-127">Your derived class should define the members necessary to maintain the state so that the provider-specific data can be accessed when the Windows PowerShell runtime calls the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method to initialize the provider.</span></span>

<span data-ttu-id="c6c3b-128">Ein Windows PowerShell-Anbieter kann auch den verbindungsbasierten Status beibehalten.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-128">A Windows PowerShell provider can also maintain connection-based state.</span></span> <span data-ttu-id="c6c3b-129">Weitere Informationen zum Beibehalten des Verbindungsstatus finden Sie unter [Erstellen eines PowerShell-Laufwerks Anbieters](./creating-a-windows-powershell-drive-provider.md).</span><span class="sxs-lookup"><span data-stu-id="c6c3b-129">For more information about maintaining connection state, see [Creating a PowerShell Drive Provider](./creating-a-windows-powershell-drive-provider.md).</span></span>

## <a name="initializing-the-provider"></a><span data-ttu-id="c6c3b-130">Initialisieren des Anbieters</span><span class="sxs-lookup"><span data-stu-id="c6c3b-130">Initializing the Provider</span></span>

<span data-ttu-id="c6c3b-131">Um den Anbieter zu initialisieren, ruft die Windows PowerShell-Runtime die [System. Management. Automation. Provider. cmdletprovider. Start \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) -Methode auf, wenn Windows PowerShell gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-131">To initialize the provider, the Windows PowerShell runtime calls the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method when Windows PowerShell is started.</span></span> <span data-ttu-id="c6c3b-132">Der Anbieter kann zum größten Teil die Standard Implementierung dieser Methode verwenden, die einfach das [System. Management. Automation. ProviderInfo](/dotnet/api/System.Management.Automation.ProviderInfo) -Objekt zurückgibt, das Ihren Anbieter beschreibt.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-132">For the most part, your provider can use the default implementation of this method, which simply returns the [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) object that describes your provider.</span></span> <span data-ttu-id="c6c3b-133">Wenn Sie jedoch zusätzliche Initialisierungs Informationen hinzufügen möchten, sollten Sie eine eigene [System. Management. Automation. Provider. cmdletprovider. Start \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) -Methode implementieren, die eine geänderte Version von [zurückgibt. System. Management. Automation. ProviderInfo](/dotnet/api/System.Management.Automation.ProviderInfo) -Objekt, das an Ihren Anbieter übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-133">However, in the case where you want to add additional initialization information, you should implement your own [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method that returns a modified version of the [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) object that is passed to your provider.</span></span> <span data-ttu-id="c6c3b-134">Im Allgemeinen sollte diese Methode das bereitgestellte [System. Management. Automation. ProviderInfo](/dotnet/api/System.Management.Automation.ProviderInfo) -Objekt zurückgeben, das an Sie übermittelt wurde, oder ein geändertes [System. Management. Automation. ProviderInfo](/dotnet/api/System.Management.Automation.ProviderInfo) -Objekt, das weitere Initialisierungs Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-134">In general, this method should return the provided [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) object passed to it or a modified [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) object that contains other initialization information.</span></span>

<span data-ttu-id="c6c3b-135">Dieser grundlegende Anbieter überschreibt diese Methode nicht.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-135">This basic provider does not override this method.</span></span> <span data-ttu-id="c6c3b-136">Der folgende Code zeigt jedoch die Standard Implementierung dieser Methode:</span><span class="sxs-lookup"><span data-stu-id="c6c3b-136">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStart](Msh_samplesaccessdbprov01#accessdbprov01ProviderStart)]  -->

<span data-ttu-id="c6c3b-137">Der Anbieter kann den Zustand der anbieterspezifischen Informationen wie unter [Definieren des anbieterspezifischen Daten Zustands](#defining-provider-specific-state-information)beschrieben beibehalten.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-137">The provider can maintain the state of provider-specific information as described in [Defining Provider-specific Data State](#defining-provider-specific-state-information).</span></span> <span data-ttu-id="c6c3b-138">In diesem Fall muss Ihre Implementierung die [System. Management. Automation. Provider. cmdletprovider. Start \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) -Methode überschreiben, um eine Instanz der abgeleiteten Klasse zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-138">In this case, your implementation must override the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method to return an instance of the derived class.</span></span>

## <a name="start-dynamic-parameters"></a><span data-ttu-id="c6c3b-139">Dynamische Parameter starten</span><span class="sxs-lookup"><span data-stu-id="c6c3b-139">Start Dynamic Parameters</span></span>

<span data-ttu-id="c6c3b-140">Die Anbieter Implementierung der [System. Management. Automation. Provider. cmdletprovider. Start \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) -Methode erfordert möglicherweise zusätzliche Parameter.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-140">Your provider implementation of the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method might require additional parameters.</span></span> <span data-ttu-id="c6c3b-141">In diesem Fall sollte der Anbieter die [System. Management. Automation. Provider. cmdletprovider. startdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.StartDynamicParameters) -Methode außer Kraft setzen und ein Objekt zurückgeben, das über Eigenschaften und Felder mit ähnlichen Attributen wie einer Cmdlet-Klasse oder einen [ System. Management. Automation. runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-141">In this case, the provider should override the [System.Management.Automation.Provider.Cmdletprovider.Startdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.StartDynamicParameters) method and return an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span>

<span data-ttu-id="c6c3b-142">Dieser grundlegende Anbieter überschreibt diese Methode nicht.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-142">This basic provider does not override this method.</span></span> <span data-ttu-id="c6c3b-143">Der folgende Code zeigt jedoch die Standard Implementierung dieser Methode:</span><span class="sxs-lookup"><span data-stu-id="c6c3b-143">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters](Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters)]  -->

## <a name="uninitializing-the-provider"></a><span data-ttu-id="c6c3b-144">Aufheben der Initialisierung des Anbieters</span><span class="sxs-lookup"><span data-stu-id="c6c3b-144">Uninitializing the Provider</span></span>

<span data-ttu-id="c6c3b-145">Zum Freigeben von Ressourcen, die der Windows PowerShell-Anbieter verwendet, sollte Ihr Anbieter seine eigene [System. Management. Automation. Provider. cmdletprovider. Break \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Stop) -Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-145">To free resources that the Windows PowerShell provider uses, your provider should implement its own [System.Management.Automation.Provider.Cmdletprovider.Stop\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Stop) method.</span></span> <span data-ttu-id="c6c3b-146">Diese Methode wird von der Windows PowerShell-Laufzeit aufgerufen, um die Initialisierung des Anbieters bei der Sitzung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-146">This method is called by the Windows PowerShell runtime to uninitialize the provider at the close of a session.</span></span>

<span data-ttu-id="c6c3b-147">Dieser grundlegende Anbieter überschreibt diese Methode nicht.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-147">This basic provider does not override this method.</span></span> <span data-ttu-id="c6c3b-148">Der folgende Code zeigt jedoch die Standard Implementierung dieser Methode:</span><span class="sxs-lookup"><span data-stu-id="c6c3b-148">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStop](Msh_samplesaccessdbprov01#accessdbprov01ProviderStop)]  -->

## <a name="code-sample"></a><span data-ttu-id="c6c3b-149">Code Beispiel</span><span class="sxs-lookup"><span data-stu-id="c6c3b-149">Code Sample</span></span>

<span data-ttu-id="c6c3b-150">Einen umfassenden Beispielcode finden Sie unter [AccessDbProviderSample01-Codebeispiel](./accessdbprovidersample01-code-sample.md).</span><span class="sxs-lookup"><span data-stu-id="c6c3b-150">For complete sample code, see [AccessDbProviderSample01 Code Sample](./accessdbprovidersample01-code-sample.md).</span></span>

## <a name="testing-the-windows-powershell-provider"></a><span data-ttu-id="c6c3b-151">Testen des Windows PowerShell-Anbieters</span><span class="sxs-lookup"><span data-stu-id="c6c3b-151">Testing the Windows PowerShell Provider</span></span>

<span data-ttu-id="c6c3b-152">Nachdem der Windows PowerShell-Anbieter bei Windows PowerShell registriert wurde, können Sie ihn testen, indem Sie die unterstützten Cmdlets in der Befehlszeile ausführen.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-152">Once your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line.</span></span> <span data-ttu-id="c6c3b-153">Führen Sie für diesen grundlegenden Anbieter die neue Shell aus, und verwenden Sie das Cmdlet "`Get-PSProvider`", um die Liste der Anbieter abzurufen und sicherzustellen, dass der accessdb-Anbieter vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c6c3b-153">For this basic provider, run the new shell and use the `Get-PSProvider` cmdlet to retrieve the list of providers and ensure that the AccessDb provider is present.</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="c6c3b-154">Die folgende Ausgabe wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c6c3b-154">The following output appears:</span></span>

```output
Name                 Capabilities                  Drives
----                 ------------                  ------
AccessDb             None                          {}
Alias                ShouldProcess                 {Alias}
Environment          ShouldProcess                 {Env}
FileSystem           Filter, ShouldProcess         {C, Z}
Function             ShouldProcess                 {function}
Registry             ShouldProcess                 {HKLM, HKCU}
```

## <a name="see-also"></a><span data-ttu-id="c6c3b-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6c3b-155">See Also</span></span>

[<span data-ttu-id="c6c3b-156">Erstellen von Windows PowerShell-Anbietern</span><span class="sxs-lookup"><span data-stu-id="c6c3b-156">Creating Windows PowerShell Providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="c6c3b-157">Entwerfen Ihres Windows PowerShell-Anbieters</span><span class="sxs-lookup"><span data-stu-id="c6c3b-157">Designing Your Windows PowerShell Provider</span></span>](./designing-your-windows-powershell-provider.md)