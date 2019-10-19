---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Direktes Aufrufen von DSC-Ressourcenmethoden
ms.openlocfilehash: cf237f638593706e5959e2bcc0d851b0e55baf0e
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954387"
---
# <a name="calling-dsc-resource-methods-directly"></a><span data-ttu-id="b0986-103">Direktes Aufrufen von DSC-Ressourcenmethoden</span><span class="sxs-lookup"><span data-stu-id="b0986-103">Calling DSC resource methods directly</span></span>

><span data-ttu-id="b0986-104">Gilt für: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="b0986-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="b0986-105">Sie können das Cmdlet[Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) verwenden, um die Funktionen oder Methoden einer DSC-Ressource direkt aufzurufen (die Funktionen **Get-TargetResource**, **Set-TargetResource** und **Test-TargetResource** einer MOF-basierten Ressource oder die Methoden **Get**, **Set** und **Test** einer klassenbasierten Ressource).</span><span class="sxs-lookup"><span data-stu-id="b0986-105">You can use the [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) cmdlet to directly call the functions or methods of a DSC resource (The **Get-TargetResource**, **Set-TargetResource**, and **Test-TargetResource** functions of a MOF-based resource, or the **Get**, **Set**, and **Test** methods of a class-based resource).</span></span>
<span data-ttu-id="b0986-106">Dieses kann von Drittanbietern verwendet werden, die DSC-Ressourcen verwenden möchten, oder als hilfreiches Tool bei der Entwicklung von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="b0986-106">This can be used by third-parties that want to use DSC resources, or as a helpful tool while developing resources.</span></span>

<span data-ttu-id="b0986-107">Dieses Cmdlet wird in der Regel in Kombination mit einer Metakonfigurationseigenschaft `refreshMode = 'Disabled'` verwendet, kann aber unabhängig davon verwendet werden, auf was **refreshMode** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b0986-107">This cmdlet is typically used in combination with a metaconfiguration property `refreshMode = 'Disabled'`, but it can be used no matter what **refreshMode** is set to.</span></span>

<span data-ttu-id="b0986-108">Beim Aufrufen des Cmdlets **Invoke-DscResource** geben Sie an, welche Methode oder Funktion aufgerufen werden soll, indem Sie den Parameter **Method** verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0986-108">When calling the **Invoke-DscResource** cmdlet, you specify which method or function to call by using the **Method** parameter.</span></span> <span data-ttu-id="b0986-109">Sie geben die Eigenschaften der Ressource an, indem Sie eine Hashtabelle als Wert des Parameters **Property** übergeben.</span><span class="sxs-lookup"><span data-stu-id="b0986-109">You specify the properties of the resource by passing a hashtable as the value of the **Property** parameter.</span></span>

<span data-ttu-id="b0986-110">Im Folgenden finden Sie Beispiele für das direkte Aufrufen von Ressourcenmethoden:</span><span class="sxs-lookup"><span data-stu-id="b0986-110">The following are examples of directly calling resource methods:</span></span>

## <a name="ensure-a-file-is-present"></a><span data-ttu-id="b0986-111">Sicherstellen, dass eine Datei vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="b0986-111">Ensure a file is present</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Set -Property @{
                            DestinationPath = "$env:SystemDrive\\DirectAccess.txt";
                            Contents = 'This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="test-that-a-file-is-present"></a><span data-ttu-id="b0986-112">Testen, ob eine Datei vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="b0986-112">Test that a file is present</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Test -Property @{
                            DestinationPath="$env:SystemDrive\\DirectAccess.txt";
                            Contents='This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="get-the-contents-of-file"></a><span data-ttu-id="b0986-113">Abrufen des Inhalts einer Datei</span><span class="sxs-lookup"><span data-stu-id="b0986-113">Get the contents of file</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Get -Property @{
                            DestinationPath="$env:SystemDrive\\DirectAccess.txt";
                            Contents='This file is create by Invoke-DscResource'} -Verbose
$result.ItemValue | fl
```

><span data-ttu-id="b0986-114">**Hinweis:** Das direkte Aufrufen von Methoden für zusammengesetzte Ressourcen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b0986-114">**Note:** Directly calling composite resource methods is not supported.</span></span> <span data-ttu-id="b0986-115">Rufen Sie stattdessen die Methoden der zugrunde liegenden Ressourcen auf, aus denen die zusammengesetzte Ressource besteht.</span><span class="sxs-lookup"><span data-stu-id="b0986-115">Instead, call the methods of the underlying resources that make up the composite resource.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0986-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0986-116">See Also</span></span>
- [<span data-ttu-id="b0986-117">Schreiben einer benutzerdefinierten DSC-Ressource mit MOF</span><span class="sxs-lookup"><span data-stu-id="b0986-117">Writing a custom DSC resource with MOF</span></span>](../resources/authoringResourceMOF.md)
- [<span data-ttu-id="b0986-118">Schreiben einer benutzerdefinierten DSC-Ressource mit PowerShell-Klassen</span><span class="sxs-lookup"><span data-stu-id="b0986-118">Writing a custom DSC resource with PowerShell classes</span></span>](../resources/authoringResourceClass.md)
- [<span data-ttu-id="b0986-119">Debuggen von DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b0986-119">Debugging DSC resources</span></span>](../troubleshooting/debugResource.md)