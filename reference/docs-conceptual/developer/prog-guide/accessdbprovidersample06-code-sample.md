---
title: AccessDbProviderSample06-Code Beispiel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: baab6a56-c199-48d7-a03e-a904b1bb1baa
caps.latest.revision: 7
ms.openlocfilehash: 7f75a3a3d2ab89696bb34ec2fdf7ba7a5ce0f9b1
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74416237"
---
# <a name="accessdbprovidersample06-code-sample"></a><span data-ttu-id="cfc0e-102">AccessDbProviderSample06-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="cfc0e-102">AccessDbProviderSample06 Code Sample</span></span>

<span data-ttu-id="cfc0e-103">Der folgende Code zeigt die Implementierung des Windows PowerShell-Inhalts Anbieters, der unter [Erstellen eines Windows PowerShell-Inhalts Anbieters](./creating-a-windows-powershell-content-provider.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="cfc0e-103">The following code shows the implementation of the Windows PowerShell content provider described in [Creating a Windows PowerShell Content Provider](./creating-a-windows-powershell-content-provider.md).</span></span> <span data-ttu-id="cfc0e-104">Dieser Anbieter ermöglicht dem Benutzer, den Inhalt der Elemente in einem Datenspeicher zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="cfc0e-104">This provider enables the user to manipulate the contents of the items in a data store.</span></span>

> [!NOTE]
> <span data-ttu-id="cfc0e-105">Sie können die C# Quelldatei (AccessDBSampleProvider06.cs) für diesen Anbieter herunterladen, indem Sie die Laufzeitkomponenten Microsoft Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0 verwenden.</span><span class="sxs-lookup"><span data-stu-id="cfc0e-105">You can download the C# source file (AccessDBSampleProvider06.cs) for this provider by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="cfc0e-106">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="cfc0e-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="cfc0e-107">Die heruntergeladenen Quelldateien stehen im **\<PowerShell-Beispiele >** Verzeichnis zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cfc0e-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>
>
> <span data-ttu-id="cfc0e-108">Weitere Informationen zu anderen Windows PowerShell-Anbieter Implementierungen finden [Sie unter Entwerfen des Windows PowerShell-Anbieters](./designing-your-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="cfc0e-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="cfc0e-109">Code Beispiel</span><span class="sxs-lookup"><span data-stu-id="cfc0e-109">Code Sample</span></span>

[!code-csharp[AccessDBProviderSample06.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L2399 "AccessDBProviderSample06.cs")]

## <a name="see-also"></a><span data-ttu-id="cfc0e-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfc0e-110">See Also</span></span>

[<span data-ttu-id="cfc0e-111">Windows PowerShell-Programmier Handbuch</span><span class="sxs-lookup"><span data-stu-id="cfc0e-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="cfc0e-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="cfc0e-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)