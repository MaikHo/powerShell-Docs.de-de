---
title: GetProc01 (C#)-Beispiel Code | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65094bb7-1972-44b3-b8b0-5f639860b58c
caps.latest.revision: 5
ms.openlocfilehash: 06a24266eb8fda6e4f138f1f77ae702f7454e525
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366799"
---
# <a name="getproc01-c-sample-code"></a><span data-ttu-id="9356f-102">GetProc01-Codebeispiel (C#)</span><span class="sxs-lookup"><span data-stu-id="9356f-102">GetProc01 (C#) Sample Code</span></span>

<span data-ttu-id="9356f-103">Der folgende Code zeigt die Implementierung des GetProc01-Beispiel-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="9356f-103">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="9356f-104">Beachten Sie, dass das Cmdlet vereinfacht wird, indem Sie die tatsächliche Prozess Abruf Funktion an die [System. Diagnostics. Process. GetProcesses \*](/dotnet/api/System.Diagnostics.Process.GetProcesses) -Methode überlassen.</span><span class="sxs-lookup"><span data-stu-id="9356f-104">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="9356f-105">Sie können die C# Quelldatei (getproc01.cs) für dieses Get-proc-Cmdlet mit dem Microsoft Windows Software Development Kit für Windows Vista und .NET Framework 3,0-Laufzeitkomponenten herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9356f-105">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="9356f-106">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="9356f-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="9356f-107">Die heruntergeladenen Quelldateien sind in den **\<powershell-Beispielen >** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9356f-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="9356f-108">Code Beispiel</span><span class="sxs-lookup"><span data-stu-id="9356f-108">Code Sample</span></span>

[!code-csharp[GetProcessSample01.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs#L11-L126 "GetProcessSample01.cs")]

## <a name="see-also"></a><span data-ttu-id="9356f-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9356f-109">See Also</span></span>

[<span data-ttu-id="9356f-110">Windows PowerShell-Programmier Handbuch</span><span class="sxs-lookup"><span data-stu-id="9356f-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="9356f-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="9356f-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)