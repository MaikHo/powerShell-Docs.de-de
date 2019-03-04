---
title: 'Gewusst wie: Aufrufen von Skripts in einem Cmdlet | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc0bc6ce-48a5-4d9c-927e-636bca743e9f
caps.latest.revision: 9
ms.openlocfilehash: 4b4d5645785b751eb1390e196f5b9437b4a1e13b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855836"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a><span data-ttu-id="6f034-102">Aufrufen von Skripts in einem Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6f034-102">How to Invoke Scripts Within a Cmdlet</span></span>

<span data-ttu-id="6f034-103">Dieses Beispiel zeigt, wie Sie ein Skript aufrufen, die an ein Cmdlet bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6f034-103">This example shows how to invoke a script that is supplied to a cmdlet.</span></span> <span data-ttu-id="6f034-104">Das Skript vom Cmdlet ausgeführt wird, und die Ergebnisse werden an das Cmdlet zurückgegeben, als eine Auflistung von [System.Management.Automation.Psobject](/dotnet/api/System.Management.Automation.PSObject) Objekte.</span><span class="sxs-lookup"><span data-stu-id="6f034-104">The script is executed by the cmdlet, and its results are returned to the cmdlet as a collection of [System.Management.Automation.Psobject](/dotnet/api/System.Management.Automation.PSObject) objects.</span></span>

## <a name="to-invoke-a-script-block"></a><span data-ttu-id="6f034-105">Um einen Skriptblock aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="6f034-105">To invoke a script block</span></span>

1. <span data-ttu-id="6f034-106">Der Befehl wird überprüft, dass ein Skriptblock an das Cmdlet übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="6f034-106">The command verifies that a script block was supplied to the cmdlet.</span></span> <span data-ttu-id="6f034-107">Wenn ein Skriptblock angegeben wurde, ruft den Befehl den Skriptblock der erforderliche Parameter.</span><span class="sxs-lookup"><span data-stu-id="6f034-107">If a script block was supplied, the command invokes the script block with its required parameters.</span></span>

    ```csharp
    if (script != null)
    {
      WriteDebug("Executing script block.");

      // Invoke the script block with the required arguments.
      Collection<PSObject> PSObjects =
                     script.Invoke(
                                   line,
                                   simpleMatch,
                                   caseSensitive
                                  );
    ```

2. <span data-ttu-id="6f034-108">Klicken Sie dann die zurückgegebene Auflistung von das Skript durchläuft [System.Management.Automation.Psobject](/dotnet/api/System.Management.Automation.PSObject) Objekte und die erforderlichen Vorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="6f034-108">Then, the script iterates through the returned collection of [System.Management.Automation.Psobject](/dotnet/api/System.Management.Automation.PSObject) objects and perform the necessary operations.</span></span>

    ```c
    foreach (PSObject psObject in psObjects)
    {
      if (LanguagePrimitives.IsTrue(psObject))
      {
        result = new MatchInfo();
        result.Line = line;
        result.IgnoreCase = !caseSensitive;

        break;
      }
    }

    ```

## <a name="see-also"></a><span data-ttu-id="6f034-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f034-109">See Also</span></span>

[<span data-ttu-id="6f034-110">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="6f034-110">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)