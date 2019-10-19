---
title: RunSpace06-Code Beispiel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d71f86d5-eb62-4b16-aa95-5fd3f314ffd3
caps.latest.revision: 6
ms.openlocfilehash: f0197e6ca3535b72f843ba52e97381c0f2531598
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366489"
---
# <a name="runspace06-code-sample"></a><span data-ttu-id="ed52d-102">RunSpace06-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="ed52d-102">RunSpace06 Code Sample</span></span>

<span data-ttu-id="ed52d-103">Im folgenden finden Sie den Quellcode für das Runspace06-Beispiel, das unter [Konfigurieren eines Runspace mithilfe eines Windows PowerShell-Snap-Ins](https://msdn.microsoft.com/en-us/a7289ee8-9732-49ee-91c7-d533e9538b83)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="ed52d-103">Here is the source code for the Runspace06 sample described in [Configuring a Runspace Using a Windows PowerShell Snap-in](https://msdn.microsoft.com/en-us/a7289ee8-9732-49ee-91c7-d533e9538b83).</span></span> <span data-ttu-id="ed52d-104">Diese Beispielanwendung erstellt einen Runspace auf Grundlage eines Windows PowerShell-Snap-Ins, das dann verwendet wird, um eine Pipeline mit einem einzigen Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ed52d-104">This sample application creates a runspace based on a Windows PowerShell snap-in, which is then used to run a pipeline with a single command.</span></span> <span data-ttu-id="ed52d-105">Zu diesem Zweck erstellt die Anwendung die Runspace-Konfigurationsinformationen, erstellt einen Runspace, erstellt eine Pipeline mit einem einzigen Befehl und führt dann die Pipeline aus.</span><span class="sxs-lookup"><span data-stu-id="ed52d-105">To do this, the application creates the runspace configuration information, creates a runspace, creates a pipeline with a single command, and then executes the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="ed52d-106">Sie können die C# Quelldatei (runspace06.cs) herunterladen, indem Sie das Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0-Laufzeitkomponenten verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed52d-106">You can download the C# source file (runspace06.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="ed52d-107">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="ed52d-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="ed52d-108">Die heruntergeladenen Quelldateien sind in den **\<powershell-Beispielen >** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ed52d-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="ed52d-109">Code Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed52d-109">Code Sample</span></span>

[!code-csharp[Runspace06.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs#L11-L85 "Runspace06.cs")]

## <a name="see-also"></a><span data-ttu-id="ed52d-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed52d-110">See Also</span></span>

[<span data-ttu-id="ed52d-111">Windows PowerShell-Programmier Handbuch</span><span class="sxs-lookup"><span data-stu-id="ed52d-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="ed52d-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="ed52d-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)