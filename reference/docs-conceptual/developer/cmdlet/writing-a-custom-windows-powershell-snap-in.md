---
title: Schreiben eines benutzerdefinierten Windows PowerShell-Snap-Ins | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- snap-ins [PowerShell SDK], custom PSSnapin example
- cmdlets [PowerShell SDK], specified in snap-ins
ms.assetid: 55c8b5cb-8ee2-4080-afc4-3f09c9f20128
caps.latest.revision: 6
ms.openlocfilehash: 4d50ef4dcd75d5c0ba802fbcfe2d7d1d7c954707
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364249"
---
# <a name="writing-a-custom-windows-powershell-snap-in"></a><span data-ttu-id="79da8-102">Schreiben eines benutzerdefinierten Windows PowerShell-Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="79da8-102">Writing a Custom Windows PowerShell Snap-in</span></span>

<span data-ttu-id="79da8-103">Dieses Beispiel zeigt, wie Sie ein Windows PowerShell-Snap-in schreiben, mit dem bestimmte Cmdlets registriert werden.</span><span class="sxs-lookup"><span data-stu-id="79da8-103">This example shows how to write a Windows PowerShell snap-in that registers specific cmdlets.</span></span>

<span data-ttu-id="79da8-104">Bei dieser Art von Snap-in geben Sie an, welche Cmdlets, Anbieter, Typen oder Formate registriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="79da8-104">With this type of snap-in, you specify which cmdlets, providers, types, or formats to register.</span></span> <span data-ttu-id="79da8-105">Weitere Informationen zum Schreiben eines Snap-Ins, das alle Cmdlets und Anbieter in einer Assembly registriert, finden Sie unter [Schreiben eines Windows PowerShell-Snap-Ins](./writing-a-windows-powershell-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="79da8-105">For more information about how to write a snap-in that registers all the cmdlets and providers in an assembly, see [Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md).</span></span>

## <a name="to-write-a-windows-powershell-snap-in-that-registers-specific-cmdlets"></a><span data-ttu-id="79da8-106">Zum Schreiben eines Windows PowerShell-Snap-Ins, mit dem bestimmte Cmdlets registriert werden.</span><span class="sxs-lookup"><span data-stu-id="79da8-106">To write a Windows PowerShell Snap-in that registers specific cmdlets.</span></span>

1. <span data-ttu-id="79da8-107">Fügen Sie das RunInstallerAttribute-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="79da8-107">Add the RunInstallerAttribute attribute.</span></span>

2. <span data-ttu-id="79da8-108">Erstellen Sie eine öffentliche Klasse, die von der [System. Management. Automation. CustomPSSnapIn](/dotnet/api/System.Management.Automation.CustomPSSnapIn) -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="79da8-108">Create a public class that derives from the [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) class.</span></span>

   <span data-ttu-id="79da8-109">In diesem Beispiel lautet der Klassenname "custompssnapintest".</span><span class="sxs-lookup"><span data-stu-id="79da8-109">In this example, the class name is "CustomPSSnapinTest".</span></span>

3. <span data-ttu-id="79da8-110">Fügen Sie eine öffentliche Eigenschaft für den Namen des Snap-Ins hinzu (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="79da8-110">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="79da8-111">Verwenden Sie beim Benennen von Snap-Ins keines der folgenden Zeichen: #.</span><span class="sxs-lookup"><span data-stu-id="79da8-111">When naming snap-ins, do not use any of the following characters: # .</span></span> <span data-ttu-id="79da8-112">, () {} [] &-/\ $; : "" \< > &#124; ?</span><span class="sxs-lookup"><span data-stu-id="79da8-112">, ( ) { } [ ] & - /\ $ ; : " ' \< > &#124; ?</span></span> <span data-ttu-id="79da8-113">@ \` \*</span><span class="sxs-lookup"><span data-stu-id="79da8-113">@ \` \*</span></span>

   <span data-ttu-id="79da8-114">In diesem Beispiel lautet der Name des Snap-Ins "custompssnapintest".</span><span class="sxs-lookup"><span data-stu-id="79da8-114">In this example, the name of the snap-in is "CustomPSSnapInTest".</span></span>

4. <span data-ttu-id="79da8-115">Hinzufügen einer öffentlichen Eigenschaft für den Anbieter des Snap-Ins (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="79da8-115">Add a public property for the vendor of the snap-in (required).</span></span>

   <span data-ttu-id="79da8-116">In diesem Beispiel ist der Lieferant "Microsoft".</span><span class="sxs-lookup"><span data-stu-id="79da8-116">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="79da8-117">Fügen Sie eine öffentliche Eigenschaft für die Vendor-Ressource des Snap-Ins hinzu (optional).</span><span class="sxs-lookup"><span data-stu-id="79da8-117">Add a public property for the vendor resource of the snap-in (optional).</span></span>

   <span data-ttu-id="79da8-118">In diesem Beispiel lautet die Ressource "Vendor" "custompssnapintest, Microsoft".</span><span class="sxs-lookup"><span data-stu-id="79da8-118">In this example, the vendor resource is "CustomPSSnapInTest,Microsoft".</span></span>

6. <span data-ttu-id="79da8-119">Fügen Sie eine öffentliche Eigenschaft für die Beschreibung des Snap-Ins hinzu (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="79da8-119">Add a public property for the description of the snap-in (required).</span></span>

   <span data-ttu-id="79da8-120">In diesem Beispiel lautet die Beschreibung: "Dies ist ein benutzerdefiniertes Windows PowerShell-Snap-in, das die Cmdlets" Test-HelloWorld "und" Test-customsnapintest "enthält.</span><span class="sxs-lookup"><span data-stu-id="79da8-120">In this example, the description is: "This is a custom Windows PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets".</span></span>

7. <span data-ttu-id="79da8-121">Fügen Sie eine öffentliche Eigenschaft für die Description-Ressource des Snap-Ins hinzu (optional).</span><span class="sxs-lookup"><span data-stu-id="79da8-121">Add a public property for the description resource of the snap-in (optional).</span></span>

   <span data-ttu-id="79da8-122">In diesem Beispiel ist die Ressource "Vendor" "custompssnapintest", ein benutzerdefiniertes Windows PowerShell-Snap-in, das die Cmdlets "Test-HelloWorld" und "Test-customsnapintest" enthält.</span><span class="sxs-lookup"><span data-stu-id="79da8-122">In this example, the vendor resource is "CustomPSSnapInTest, This is a custom Windows PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets".</span></span>

8. <span data-ttu-id="79da8-123">Geben Sie die Cmdlets, die zum benutzerdefinierten Snap-in (optional) gehören, mithilfe der [System. Management. Automation. Runspaces. cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) -Klasse an.</span><span class="sxs-lookup"><span data-stu-id="79da8-123">Specify the cmdlets that belong to the custom snap-in (optional) using the [System.Management.Automation.Runspaces.Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) class.</span></span> <span data-ttu-id="79da8-124">Die hier hinzugefügten Informationen umfassen den Namen des Cmdlets, den .NET-Typ und den Namen der Cmdlet-Hilfedatei (das Format des Cmdlet-Hilfe Dateinamens sollte "Name. dll-Help. xml" lauten).</span><span class="sxs-lookup"><span data-stu-id="79da8-124">The information added here includes the name of the cmdlet, its .NET type, and the cmdlet Help file name (the format of the cmdlet Help file name should be name.dll-help.xml).</span></span>

   <span data-ttu-id="79da8-125">In diesem Beispiel werden die Cmdlets Test-HelloWorld und testcustomsnapintest hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="79da8-125">This example adds the Test-HelloWorld and TestCustomSnapinTest cmdlets.</span></span>

9. <span data-ttu-id="79da8-126">Geben Sie die Anbieter an, die zum benutzerdefinierten Snap-in gehören (optional).</span><span class="sxs-lookup"><span data-stu-id="79da8-126">Specify the providers that belong to the custom snap-in (optional).</span></span>

   <span data-ttu-id="79da8-127">In diesem Beispiel werden keine Anbieter angegeben.</span><span class="sxs-lookup"><span data-stu-id="79da8-127">This example does not specify any providers.</span></span>

10. <span data-ttu-id="79da8-128">Geben Sie die Typen an, die zum benutzerdefinierten Snap-in gehören (optional).</span><span class="sxs-lookup"><span data-stu-id="79da8-128">Specify the types that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="79da8-129">In diesem Beispiel werden keine Typen angegeben.</span><span class="sxs-lookup"><span data-stu-id="79da8-129">This example does not specify any types.</span></span>

11. <span data-ttu-id="79da8-130">Geben Sie die Formate an, die zum benutzerdefinierten Snap-in gehören (optional).</span><span class="sxs-lookup"><span data-stu-id="79da8-130">Specify the formats that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="79da8-131">In diesem Beispiel werden keine Formate angegeben.</span><span class="sxs-lookup"><span data-stu-id="79da8-131">This example does not specify any formats.</span></span>

## <a name="example"></a><span data-ttu-id="79da8-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79da8-132">Example</span></span>

<span data-ttu-id="79da8-133">Dieses Beispiel zeigt, wie Sie ein benutzerdefiniertes Windows PowerShell-Snap-in schreiben, das zum Registrieren der Cmdlets "Test-HelloWorld" und "Test-customsnapintest" verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="79da8-133">This example shows how to write a Custom Windows PowerShell snap-in that can be used to register the Test-HelloWorld and Test-CustomSnapinTest cmdlets.</span></span> <span data-ttu-id="79da8-134">Beachten Sie, dass in diesem Beispiel die vollständige Assembly andere Cmdlets und Anbieter enthalten kann, die nicht von diesem Snap-in registriert werden.</span><span class="sxs-lookup"><span data-stu-id="79da8-134">Be aware that in this example, the complete assembly could contain other cmdlets and providers that would not be registered by this snap-in.</span></span>

```csharp
[RunInstaller(true)]
public class CustomPSSnapinTest : CustomPSSnapIn
{
  /// <summary>
  /// Creates an instance of CustomPSSnapInTest class.
  /// </summary>
  public CustomPSSnapinTest()
          : base()
  {
  }

  /// <summary>
  /// Specify the name of the custom PowerShell snap-in.
  /// </summary>
  public override string Name
  {
    get
    {
      return "CustomPSSnapInTest";
    }
  }

  /// <summary>
  /// Specify the vendor for the custom PowerShell snap-in.
  /// </summary>
  public override string Vendor
  {
    get
    {
      return "Microsoft";
    }
  }

  /// <summary>
  /// Specify the localization resource information for the vendor.
  /// Use the format: resourceBaseName,resourceName.
  /// </summary>
  public override string VendorResource
  {
    get
    {
        return "CustomPSSnapInTest,Microsoft";
    }
  }

  /// <summary>
  /// Specify a description of the custom PowerShell snap-in.
  /// </summary>
  public override string Description
  {
    get
    {
      return "This is a custom PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets.";
    }
  }

  /// <summary>
  /// Specify the localization resource information for the description.
  /// Use the format: resourceBaseName,Description.
  /// </summary>
  public override string DescriptionResource
  {
    get
    {
        return "CustomPSSnapInTest,This is a custom PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets.";
    }
  }

  /// <summary>
  /// Specify the cmdlets that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<CmdletConfigurationEntry> _cmdlets;
  public override Collection<CmdletConfigurationEntry> Cmdlets
  {
    get
    {
      if (_cmdlets == null)
      {
        _cmdlets = new Collection<CmdletConfigurationEntry>();
        _cmdlets.Add(new CmdletConfigurationEntry("test-customsnapintest", typeof(TestCustomSnapinTest), "TestCmdletHelp.dll-help.xml"));
        _cmdlets.Add(new CmdletConfigurationEntry("test-helloworld", typeof(TestHelloWorld), "HelloWorldHelp.dll-help.xml"));
      }

      return _cmdlets;
    }
  }

  /// <summary>
  /// Specify the providers that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<ProviderConfigurationEntry> _providers;
  public override Collection<ProviderConfigurationEntry> Providers
  {
    get
    {
      if (_providers == null)
      {
        _providers = new Collection<ProviderConfigurationEntry>();
      }

      return _providers;
    }
  }

  /// <summary>
  /// Specify the types that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<TypeConfigurationEntry> _types;
  public override Collection<TypeConfigurationEntry> Types
  {
    get
    {
      if (_types == null)
      {
        _types = new Collection<TypeConfigurationEntry>();
      }

      return _types;
    }
  }

  /// <summary>
  /// Specify the formats that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<FormatConfigurationEntry> _formats;
  public override Collection<FormatConfigurationEntry> Formats
  {
    get
    {
      if (_formats == null)
      {
        _formats = new Collection<FormatConfigurationEntry>();
      }

      return _formats;
    }
  }
}
```

<span data-ttu-id="79da8-135">Weitere Informationen zum Registrieren von Snap-Ins finden [Sie unter Registrieren von Cmdlets, Anbietern und Host Anwendungen](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c) im [Windows PowerShell-Programmier Handbuch](../prog-guide/windows-powershell-programmer-s-guide.md).</span><span class="sxs-lookup"><span data-stu-id="79da8-135">For more information about registering snap-ins, see [How to Register Cmdlets, Providers, and Host Applications](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c) in the [Windows PowerShell Programmer's Guide](../prog-guide/windows-powershell-programmer-s-guide.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="79da8-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79da8-136">See Also</span></span>

[<span data-ttu-id="79da8-137">Registrieren von Cmdlets, Anbietern und Host Anwendungen</span><span class="sxs-lookup"><span data-stu-id="79da8-137">How to Register Cmdlets, Providers, and Host Applications</span></span>](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="79da8-138">Windows PowerShell Shell SDK</span><span class="sxs-lookup"><span data-stu-id="79da8-138">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)