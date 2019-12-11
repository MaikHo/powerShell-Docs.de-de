---
title: Beispiele für die Windows PowerShell-API | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82df2cde-ba12-46d2-b6ec-da5455fd9b57
caps.latest.revision: 8
ms.openlocfilehash: a472f07cb24b0de8e5dcdfcaddd2802575318d7a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360839"
---
# <a name="windows-powershell-api-samples"></a><span data-ttu-id="2d3bd-102">Beispiele für Windows PowerShell-APIs</span><span class="sxs-lookup"><span data-stu-id="2d3bd-102">Windows PowerShell API Samples</span></span>

<span data-ttu-id="2d3bd-103">Dieser Abschnitt enthält Beispielcode, der zeigt, wie Sie Runspaces erstellen, die die Funktionalität einschränken, und wie Sie Befehle asynchron ausführen, indem Sie einen Runspace-Pool verwenden, um die Runspaces bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2d3bd-103">This section includes sample code that shows how to create runspaces that restrict functionality, and how to asynchronously run commands by using a runspace pool to supply the runspaces.</span></span> <span data-ttu-id="2d3bd-104">Mit Microsoft Visual Studio können Sie eine Konsolenanwendung erstellen und dann den Code aus den Themen in diesem Abschnitt in die Host Anwendung kopieren.</span><span class="sxs-lookup"><span data-stu-id="2d3bd-104">You can use Microsoft Visual Studio to create a console application and then copy the code from the topics in this section into your host application.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2d3bd-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2d3bd-105">In This Section</span></span>

<span data-ttu-id="2d3bd-106">[PowerShell01-Beispiel](./windows-powershell01-sample.md) In diesem Beispiel wird gezeigt, wie ein [System. Management. Automation. Runspaces. initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) -Objekt verwendet wird, um die Funktionalität eines Runspace einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="2d3bd-106">[PowerShell01 Sample](./windows-powershell01-sample.md) This sample shows how to use an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to limit the functionality of a runspace.</span></span> <span data-ttu-id="2d3bd-107">In der Ausgabe dieses Beispiels wird veranschaulicht, wie der Sprachmodus des Runspace eingeschränkt wird, wie ein Cmdlet als privat markiert wird, wie Cmdlets und Anbieter hinzugefügt und entfernt werden, wie ein Proxy Befehl hinzugefügt wird und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="2d3bd-107">The output of this sample demonstrates how to restrict the language mode of the runspace, how to mark a cmdlet as private, how to add and remove cmdlets and providers, how to add a proxy command, and more.</span></span>

<span data-ttu-id="2d3bd-108">[PowerShell02-Beispiel](./windows-powershell02-sample.md) In diesem Beispiel wird gezeigt, wie Befehle asynchron mit den Runspaces eines Runspace-Pools ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2d3bd-108">[PowerShell02 Sample](./windows-powershell02-sample.md) This sample shows how to run commands asynchronously by using the runspaces of a runspace pool.</span></span> <span data-ttu-id="2d3bd-109">Das Beispiel generiert eine Liste mit Befehlen und führt diese Befehle aus, während die Windows PowerShell-Engine einen Runspace aus dem Pool öffnet, wenn Sie benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="2d3bd-109">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>