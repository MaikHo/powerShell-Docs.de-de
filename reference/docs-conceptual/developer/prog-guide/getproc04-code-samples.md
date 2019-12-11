---
title: GetProc04-Code Beispiele | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c00afd46-758a-4aec-b865-2c9d8f6a17ad
caps.latest.revision: 5
ms.openlocfilehash: 8326d1f47ce07698f09ade9ba97154ecc358465a
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417460"
---
# <a name="getproc04-code-samples"></a><span data-ttu-id="72145-102">GetProc04-Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="72145-102">GetProc04 Code Samples</span></span>

<span data-ttu-id="72145-103">Im folgenden finden Sie die Codebeispiele für das Cmdlet "GetProc04 Sample".</span><span class="sxs-lookup"><span data-stu-id="72145-103">Here are the code samples for the GetProc04 sample cmdlet.</span></span> <span data-ttu-id="72145-104">Dies ist das `Get-Process` Cmdlet-Beispiel, das unter [Hinzufügen von Fehlern bei der nicht abschließenden Fehlerberichterstattung zum Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="72145-104">This is the `Get-Process` cmdlet sample described in [Adding Nonterminating Error Reporting to Your Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span></span> <span data-ttu-id="72145-105">Dieses `Get-Process`-Cmdlet ruft die [System. Management. Automation. Cmdlet. Write error](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) -Methode auf, wenn beim Abrufen der Prozessinformationen eine Ausnahme vom Typ "Ungültiger Vorgang" ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="72145-105">This `Get-Process` cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method whenever an invalid operation exception is thrown while retrieving process information.</span></span>

> [!NOTE]
> <span data-ttu-id="72145-106">Sie können die C# Quelldatei (getprov04.cs) für dieses Get-proc-Cmdlet mit dem Microsoft Windows Software Development Kit für Windows Vista und .NET Framework 3,0-Laufzeitkomponenten herunterladen.</span><span class="sxs-lookup"><span data-stu-id="72145-106">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="72145-107">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="72145-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="72145-108">Die heruntergeladenen Quelldateien stehen im **\<PowerShell-Beispiele >** Verzeichnis zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="72145-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="72145-109">Einen umfassenden Beispielcode finden Sie in den folgenden Themen.</span><span class="sxs-lookup"><span data-stu-id="72145-109">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="72145-110">Sprache</span><span class="sxs-lookup"><span data-stu-id="72145-110">Language</span></span>|<span data-ttu-id="72145-111">Thema</span><span class="sxs-lookup"><span data-stu-id="72145-111">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="72145-112">C#</span><span class="sxs-lookup"><span data-stu-id="72145-112">C#</span></span>|[<span data-ttu-id="72145-113">GetProc04 (C#)-Beispiel Code</span><span class="sxs-lookup"><span data-stu-id="72145-113">GetProc04 (C#) Sample Code</span></span>](./getproc04-csharp-sample-code.md)|
|<span data-ttu-id="72145-114">VB.NET</span><span class="sxs-lookup"><span data-stu-id="72145-114">VB.NET</span></span>|[<span data-ttu-id="72145-115">GetProc04 (VB.net)-Beispiel Code</span><span class="sxs-lookup"><span data-stu-id="72145-115">GetProc04 (VB.NET) Sample Code</span></span>](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="72145-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72145-116">See Also</span></span>

[<span data-ttu-id="72145-117">Windows PowerShell-Programmier Handbuch</span><span class="sxs-lookup"><span data-stu-id="72145-117">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="72145-118">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="72145-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)