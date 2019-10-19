---
title: RunSpace10-Code Beispiel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5337dc40-c56e-458b-aedc-5f5d401dfd28
caps.latest.revision: 6
ms.openlocfilehash: da8455a72f6a50b8ab17650541cde8cc9c98a8fd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366469"
---
# <a name="runspace10-code-sample"></a><span data-ttu-id="32df5-102">RunSpace10-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="32df5-102">RunSpace10 Code Sample</span></span>

<span data-ttu-id="32df5-103">Im folgenden finden Sie den Quellcode für das Runspace10-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="32df5-103">Here is the source code for the Runspace10 sample.</span></span> <span data-ttu-id="32df5-104">Diese Beispielanwendung fügt [System. Management. Automation. Runspaces. runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) ein Cmdlet hinzu und verwendet dann die geänderten Konfigurationsinformationen, um den Runspace zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="32df5-104">This sample application adds a cmdlet to [System.Management.Automation.Runspaces.Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) and then uses the modified configuration information to create the runspace.</span></span>

> [!NOTE]
> <span data-ttu-id="32df5-105">Sie können die C# Quelldatei (runspace10.cs) herunterladen, indem Sie das Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0-Laufzeitkomponenten verwenden.</span><span class="sxs-lookup"><span data-stu-id="32df5-105">You can download the C# source file (runspace10.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="32df5-106">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="32df5-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="32df5-107">Die heruntergeladenen Quelldateien sind in den **\<powershell-Beispielen >** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="32df5-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="32df5-108">Code Beispiel</span><span class="sxs-lookup"><span data-stu-id="32df5-108">Code Sample</span></span>

[!code-csharp[Runspace10.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace10/Runspace10.cs#L11-L118 "Runspace10.cs")]

## <a name="see-also"></a><span data-ttu-id="32df5-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32df5-109">See Also</span></span>

[<span data-ttu-id="32df5-110">Windows PowerShell-Programmier Handbuch</span><span class="sxs-lookup"><span data-stu-id="32df5-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="32df5-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="32df5-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)