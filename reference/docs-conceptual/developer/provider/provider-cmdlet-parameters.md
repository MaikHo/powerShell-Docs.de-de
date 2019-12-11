---
title: Anbieter-Cmdlet-Parameter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3d09eaa-924f-4e2b-adfb-14bb729090dd
caps.latest.revision: 8
ms.openlocfilehash: ad7f9737c646dd5cea5abb14b828236e40feac5a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366309"
---
# <a name="provider-cmdlet-parameters"></a><span data-ttu-id="adffd-102">Anbieter-Cmdlet-Parameter</span><span class="sxs-lookup"><span data-stu-id="adffd-102">Provider cmdlet parameters</span></span>

<span data-ttu-id="adffd-103">Anbieter-Cmdlets verfügen über einen Satz statischer Parameter, die für alle Anbieter verfügbar sind, die das Cmdlet unterstützen, sowie dynamische Parameter, die hinzugefügt werden, wenn der Benutzer einen bestimmten Wert für bestimmte statische Parameter des Provider-Cmdlets angibt.</span><span class="sxs-lookup"><span data-stu-id="adffd-103">Provider cmdlets come with a set of static parameters that are available to all providers that support the cmdlet, as well as dynamic parameters that are added when the user specifies a certain value for certain static parameters of the provider cmdlet.</span></span>

## <a name="provider-cmdlet-static-parameters"></a><span data-ttu-id="adffd-104">Statische Cmdlet-Parameter des Anbieters</span><span class="sxs-lookup"><span data-stu-id="adffd-104">Provider Cmdlet Static Parameters</span></span>

<span data-ttu-id="adffd-105">Statische Parameter werden von Windows PowerShell definiert.</span><span class="sxs-lookup"><span data-stu-id="adffd-105">Static parameters are defined by Windows PowerShell.</span></span> <span data-ttu-id="adffd-106">Eine große Menge dieser Parameter wird von Windows PowerShell implementiert, um Konsistenz für alle Anbieter bereitzustellen und eine einfachere Entwicklungsfunktion bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="adffd-106">A large set of these parameters is implemented by Windows PowerShell to provide consistency across all the providers and to provide a simpler development experience.</span></span> <span data-ttu-id="adffd-107">Beispiele für diese Parameter sind die Parameter "`literalPath`", "`exclude`" und "`include`" des `Get-Item`-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="adffd-107">Examples of these parameters include the `literalPath`, `exclude`, and `include` parameters of the `Get-Item` cmdlet.</span></span> <span data-ttu-id="adffd-108">Ein kleinerer Satz dieser Parameter kann überschrieben werden, um Aktionen bereitzustellen, die für Ihren Anbieter spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="adffd-108">A smaller set of these parameters can be overwritten to provide actions that are specific to your provider.</span></span> <span data-ttu-id="adffd-109">Beispiele für diese Parameter sind der `Path`-und `Value`-Parameter des Cmdlets `Set-Item`.</span><span class="sxs-lookup"><span data-stu-id="adffd-109">Examples of these parameters include the `Path` and `Value` parameter of the `Set-Item` cmdlet.</span></span> <span data-ttu-id="adffd-110">Im folgenden finden Sie eine Liste der Parameter, die für die Anbieter-Cmdlets überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="adffd-110">Here is a list of the parameters that can be overwritten for the provider cmdlets.</span></span>

<span data-ttu-id="adffd-111">`Clear-Content`-Cmdlet können Sie definieren, wie der Anbieter die Werte verwendet, die an den `Path`-Parameter des `Clear-Content`-Cmdlets übergeben werden, indem Sie die [System. Management. Automation. Provider. icontentcmdletprovider. ClearContent \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) -Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="adffd-111">`Clear-Content` cmdlet You can define how your provider will use the values passed to the `Path` parameter of the `Clear-Content` cmdlet by implementing the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method.</span></span>

<span data-ttu-id="adffd-112">mit dem Cmdlet "`Clear-Item`" können Sie definieren, wie der Anbieter die Werte verwendet, die an den `Path`-Parameter des Cmdlets "`Clear-Item`" übergeben werden, indem Sie die [System. Management. Automation. Provider. itemcmdletprovider. ClearItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) -Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="adffd-112">`Clear-Item` cmdlet You can define how your provider will use the values passed to the `Path` parameter of the `Clear-Item` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Clearitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) method.</span></span>

<span data-ttu-id="adffd-113">mit dem Cmdlet "`Clear-ItemProperty`" können Sie definieren, wie der Anbieter die Werte verwendet, die an die Parameter "`Path`" und "`Name`" des `Clear-ItemProperty`-Cmdlets übergeben werden, indem Sie die [System. Management. Automation. Provider. ipropertycmdletprovider. clearproperty \*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) -Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="adffd-113">`Clear-ItemProperty` cmdlet You can define how your provider will use the values passed to the `Path` and `Name` parameters of the `Clear-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty\*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) method.</span></span>

<span data-ttu-id="adffd-114">`Copy-Item`-Cmdlet können Sie definieren, wie der Anbieter die Werte verwendet, die an die Parameter "`Path`", "`Destination`" und "`Recurse`" des `Copy-Item`-Cmdlets übergeben werden, indem Sie " [System. Management. Automation. Provider. containercmdletprovider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) " implementieren. anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="adffd-114">`Copy-Item` cmdlet You can define how your provider will use the values passed to the `Path`, `Destination`, and `Recurse` parameters of the `Copy-Item` cmdlet by implementing the [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) method.</span></span>

<span data-ttu-id="adffd-115">Cmdlet "Get-ChildItems" können Sie definieren, wie der Anbieter die Werte verwendet, die an die Parameter "`Path`" und "`Recurse`" des `Get-ChildItem`-Cmdlets übergeben werden, indem Sie " [System. Management. Automation. Provider. containercmdletprovider. getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) " implementieren. und [System. Management. Automation. Provider. containercmdletprovider. getchildnames \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) -Methoden.</span><span class="sxs-lookup"><span data-stu-id="adffd-115">Get-ChildItems cmdlet You can define how your provider will use the values passed to the `Path` and `Recurse` parameters of the `Get-ChildItem` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) and [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) methods.</span></span>

<span data-ttu-id="adffd-116">`Get-Content`-Cmdlet können Sie definieren, wie der Anbieter die Werte verwendet, die an den `Path`-Parameter des `Get-Content`-Cmdlets übergeben werden, indem Sie die [System. Management. Automation. Provider. icontentcmdletprovider. getcontentreader \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) -Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="adffd-116">`Get-Content` cmdlet You can define how your provider will use the values passed to the `Path` parameter of the `Get-Content` cmdlet by implementing the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) method.</span></span>

<span data-ttu-id="adffd-117">mit dem Cmdlet "`Get-Item`" können Sie definieren, wie der Anbieter die Werte verwendet, die an den `Path`-Parameter des Cmdlets "`Get-Item`" übergeben werden, indem Sie die [System. Management. Automation. Provider. itemcmdletprovider. GetItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) -Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="adffd-117">`Get-Item` cmdlet You can define how your provider will use the values passed to the `Path` parameter of the `Get-Item` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) method.</span></span>

<span data-ttu-id="adffd-118">mit dem Cmdlet "`Get-ItemProperty`" können Sie definieren, wie der Anbieter die Werte verwendet, die an die Parameter "`Path`" und "`Name`" des `Get-ItemProperty`-Cmdlets übergeben werden, indem Sie die [System. Management. Automation. Provider. ipropertycmdletprovider. GetProperty \*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) -Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="adffd-118">`Get-ItemProperty` cmdlet You can define how your provider will use the values passed to the `Path` and `Name` parameters of the `Get-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty\*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) method.</span></span>

<span data-ttu-id="adffd-119">`Invoke-Item`-Cmdlet können Sie definieren, wie der Anbieter die Werte verwendet, die an den `Path`-Parameter des `Invoke-Item`-Cmdlets übergeben werden, indem Sie die [System. Management. Automation. Provider. itemcmdletprovider. invokedefaultaction \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) -Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="adffd-119">`Invoke-Item` cmdlet You can define how your provider will use the values passed to the `Path` parameter of the `Invoke-Item` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) method.</span></span>

<span data-ttu-id="adffd-120">mit dem Cmdlet "`Move-Item`" können Sie definieren, wie der Anbieter die Werte verwendet, die an die Parameter "`Path`" und "`Destination`" des `Move-Item`-Cmdlets übergeben werden, indem Sie die [System. Management. Automation. Provider. navigationcmdletprovider. muveitem \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) -Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="adffd-120">`Move-Item` cmdlet You can define how your provider will use the values passed to the `Path` and `Destination` parameters of the `Move-Item` cmdlet by implementing the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method.</span></span>

<span data-ttu-id="adffd-121">`New-Item`-Cmdlet können Sie definieren, wie der Anbieter die Werte verwendet, die an die Parameter "`Path`", "`ItemType`" und "`Value`" des `New-Item`-Cmdlets übergeben werden, indem Sie " [System. Management. Automation. Provider. containercmdletprovider. nwitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) " implementieren. anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="adffd-121">`New-Item` cmdlet You can define how your provider will use the values passed to the `Path`, `ItemType`, and `Value` parameters of the `New-Item` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method.</span></span>

<span data-ttu-id="adffd-122">`New-ItemProperty`-Cmdlet Sie können definieren, wie der Anbieter die Werte verwendet, die an die Parameter "`Path`", "`Name`", "`PropertyType`" und "`Value`" des `New-ItemProperty`-Cmdlets übergeben werden, indem [Microsoft. PowerShell. Commands. registryprovider. newproperty \*](/dotnet/api/Microsoft.PowerShell.Commands.RegistryProvider.NewProperty) implementiert wird. anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="adffd-122">`New-ItemProperty` cmdlet You can define how your provider will use the values passed to the `Path`, `Name`, `PropertyType`, and `Value` parameters of the `New-ItemProperty` cmdlet by implementing the [Microsoft.PowerShell.Commands.Registryprovider.Newproperty\*](/dotnet/api/Microsoft.PowerShell.Commands.RegistryProvider.NewProperty) method.</span></span>

<span data-ttu-id="adffd-123">`Remove-Item` Sie können definieren, wie der Anbieter die Werte verwendet, die an die Parameter "`Path`" und "`Recurse`" des `Remove-Item`-Cmdlets übergeben werden, indem Sie die [System. Management. Automation. Provider. containercmdletprovider. RemoveItem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) -Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="adffd-123">`Remove-Item` You can define how your provider will use the values passed to the `Path` and `Recurse` parameters of the `Remove-Item` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) method.</span></span>

<span data-ttu-id="adffd-124">`Remove-ItemProperty` Sie können definieren, wie der Anbieter die Werte verwendet, die an die Parameter "`Path`" und "`Name`" des `Remove-ItemProperty`-Cmdlets übergeben werden, indem Sie " [System. Management. Automation. Provider. idynamicpropertycmdletprovider. RemoveProperty \*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) " implementieren. anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="adffd-124">`Remove-ItemProperty` You can define how your provider will use the values passed to the `Path` and `Name` parameters of the `Remove-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removeproperty\*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) method.</span></span>

<span data-ttu-id="adffd-125">mit dem Cmdlet "`Rename-Item`" können Sie definieren, wie der Anbieter die Werte verwendet, die an die Parameter "`Path`" und "`NewName`" des `Rename-Item`-Cmdlets übergeben werden, indem Sie die [System. Management. Automation. Provider. containercmdletprovider. RenameItem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) -Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="adffd-125">`Rename-Item` cmdlet You can define how your provider will use the values passed to the `Path` and `NewName` parameters of the `Rename-Item` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Renameitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) method.</span></span>

<span data-ttu-id="adffd-126">`Rename-ItemProperty` Sie können definieren, wie der Anbieter die Werte verwendet, die an die Parameter `Path`, `NewName` und `Name` des `Rename-ItemProperty`-Cmdlets übergeben werden, indem Sie die [System. Management. Automation. Provider. idynamicpropertycmdletprovider. renameproperty \* implementieren. ](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty)-Methode.</span><span class="sxs-lookup"><span data-stu-id="adffd-126">`Rename-ItemProperty` You can define how your provider will use the values passed to the `Path`, `NewName`, and `Name` parameters of the `Rename-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renameproperty\*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty) method.</span></span>

<span data-ttu-id="adffd-127">mit dem Cmdlet "`Set-Content`" können Sie definieren, wie der Anbieter die Werte verwendet, die an den `Path`-Parameter des Cmdlets "`Set-Content`" übergeben werden, indem Sie die [System. Management. Automation. Provider. icontentcmdletprovider. getcontentwriter \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) -Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="adffd-127">`Set-Content` cmdlet You can define how your provider will use the values passed to the `Path` parameter of the `Set-Content` cmdlet by implementing the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) method.</span></span>

<span data-ttu-id="adffd-128">mit dem Cmdlet "`Set-Item`" können Sie definieren, wie der Anbieter die Werte verwendet, die an die Parameter "`Path`" und "`Value`" des `Set-Item`-Cmdlets übergeben werden, indem Sie die [System. Management. Automation. Provider. itemcmdletprovider. SetItem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) -Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="adffd-128">`Set-Item` cmdlet You can define how your provider will use the values passed to the `Path` and `Value` parameters of the `Set-Item` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) method.</span></span>

<span data-ttu-id="adffd-129">mit dem Cmdlet "`Set-ItemProperty`" können Sie definieren, wie der Anbieter die Werte verwendet, die an die Parameter "`Path`" und "`Value`" des `Set-Item`-Cmdlets übergeben werden, indem Sie die [System. Management. Automation. Provider. ipropertycmdletprovider. SetProperty \*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) -Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="adffd-129">`Set-ItemProperty` cmdlet You can define how your provider will use the values passed to the `Path` and `Value` parameters of the `Set-Item` cmdlet by implementing the [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty\*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) method.</span></span>

<span data-ttu-id="adffd-130">`Test-Path`-Cmdlet können Sie definieren, wie der Anbieter die Werte verwendet, die an den `Path`-Parameter des `Test-Path`-Cmdlets übergeben werden, indem Sie die [System. Management. Automation. Provider. itemcmdletprovider. invokedefaultaction \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) -Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="adffd-130">`Test-Path` cmdlet You can define how your provider will use the values passed to the `Path` parameter of the `Test-Path` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) method.</span></span>

<span data-ttu-id="adffd-131">Außerdem können Sie die Merkmale dieser Parameter nicht angeben, z. b. ob Sie optional oder erforderlich sind, und Sie können diesen Parametern auch keinen Alias geben oder die Validierungs Attribute angeben.</span><span class="sxs-lookup"><span data-stu-id="adffd-131">In addition, you cannot specify the characteristics of these parameters, such as whether they are optional or required, nor can you give these parameters an alias or specify any of the validation attributes.</span></span> <span data-ttu-id="adffd-132">Im Gegensatz dazu können Sie Parameter Merkmale in eigenständigen Cmdlets mithilfe von Attributen wie dem `Parameters`-Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="adffd-132">In contrast, you can specify parameter characteristics in stand-alone cmdlets by using attributes such as the `Parameters` attribute.</span></span>

## <a name="provider-cmdlet-dynamic-parameters"></a><span data-ttu-id="adffd-133">Dynamische Parameter des Anbieter-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="adffd-133">Provider Cmdlet Dynamic Parameters</span></span>

<span data-ttu-id="adffd-134">Dynamische Parameter für Cmdlet-Anbieter ähneln dynamischen Anbietern für eigenständige Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="adffd-134">Dynamic parameters for cmdlet providers are similar to dynamic providers for stand-alone cmdlets.</span></span> <span data-ttu-id="adffd-135">In beiden Fällen werden die Parameter zum Cmdlet hinzugefügt, wenn der Benutzer einen bestimmten Wert für einen der Standardparameter angibt, z. b. den `path`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="adffd-135">In both cases, the parameters are added to the cmdlet when the user specifies a certain value for one of the default parameters, such as the `path` parameter.</span></span> <span data-ttu-id="adffd-136">Es können jedoch nicht alle statischen Parameter verwendet werden, um das Hinzufügen dynamischer Parameter zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="adffd-136">However, not all of the static parameters can be used to trigger the addition of dynamic parameters.</span></span> <span data-ttu-id="adffd-137">Weitere Informationen zu dynamischen Parametern finden [Sie unter Anbieter-Cmdlet-Parameter](./provider-cmdlet-dynamic-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="adffd-137">For more information about dynamic parameters, see [Provider Cmdlet Dynamic Parameters](./provider-cmdlet-dynamic-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="adffd-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="adffd-138">See Also</span></span>

[<span data-ttu-id="adffd-139">Dynamische Parameter des Anbieter-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="adffd-139">Provider Cmdlet Dynamic Parameters</span></span>](./provider-cmdlet-dynamic-parameters.md)

[<span data-ttu-id="adffd-140">Schreiben eines Windows PowerShell-Anbieters</span><span class="sxs-lookup"><span data-stu-id="adffd-140">Writing a Windows PowerShell Provider</span></span>](./writing-a-windows-powershell-provider.md)