---
title: Festlegen der helpinfo-XML-Versionsnummern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a00463-af58-41c8-b088-450909fa1d05
caps.latest.revision: 6
ms.openlocfilehash: b98e6879bbfe0e3ec1a9ab37496dde44caf523a4
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360679"
---
# <a name="how-to-set-helpinfo-xml-version-numbers"></a><span data-ttu-id="8fb64-102">Festlegen von XML-Versionsnummern für HelpInfo</span><span class="sxs-lookup"><span data-stu-id="8fb64-102">How to Set HelpInfo XML Version Numbers</span></span>

<span data-ttu-id="8fb64-103">In diesem Thema wird erläutert, wie die Versionsnummern in einer aktualisierbaren Hilfe Informationsdatei festgelegt und erhöht werden, die häufig als "helpinfo-XML-Datei" bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="8fb64-103">This topic explains how to set and increase the version numbers in an Updatable Help Information file, commonly known as a "HelpInfo XML file."</span></span>

## <a name="how-to-set-helpinfo-xml-version-numbers"></a><span data-ttu-id="8fb64-104">Festlegen von XML-Versionsnummern für HelpInfo</span><span class="sxs-lookup"><span data-stu-id="8fb64-104">How to Set HelpInfo XML Version Numbers</span></span>

<span data-ttu-id="8fb64-105">Die Versionsnummern in einer helpinfo-XML-Datei sind wichtig für den Vorgang der aktualisierbaren Hilfe.</span><span class="sxs-lookup"><span data-stu-id="8fb64-105">The version numbers in a HelpInfo XML file are critical to the operation of Updatable Help.</span></span>
<span data-ttu-id="8fb64-106">Mit den Cmdlets " [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) " und " [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) " werden neue Hilfedateien nur heruntergeladen, wenn die Versionsnummer für eine Benutzeroberflächen Kultur in der XML-Datei "Remote helpinfo" größer ist als die Versionsnummer für diese Benutzeroberflächen Kultur im lokalen helpinfo-XML, oder es gibt keine lokalen helpinfo. XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="8fb64-106">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets download new help files only when the version number for a UI culture in the remote HelpInfo XML file is greater than the version number for that UI culture in the local HelpInfo XML, or there is no local HelpInfo XML file.</span></span>

<span data-ttu-id="8fb64-107">Die helpinfo-XML-Datei verwendet die 4-teilige Versionsnummer, die in der **System. Version** -Klasse des Microsoft .NET Frameworks definiert ist.</span><span class="sxs-lookup"><span data-stu-id="8fb64-107">The HelpInfo XML file uses the 4-part version number that is defined in the **System.Version** class of the Microsoft .NET Framework.</span></span> <span data-ttu-id="8fb64-108">Das Format ist `N1.N2.N3.N4`.</span><span class="sxs-lookup"><span data-stu-id="8fb64-108">The format is `N1.N2.N3.N4`.</span></span> <span data-ttu-id="8fb64-109">Modul Autoren können ein beliebiges Versionsnummern Schema verwenden, das von der **System. Version** -Klasse zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="8fb64-109">Module authors can use any version numbering scheme that is permitted by the **System.Version** class.</span></span> <span data-ttu-id="8fb64-110">Die aktualisierbare Hilfe erfordert nur, dass die Versionsnummer für eine Benutzeroberflächen Kultur zunimmt, wenn eine neue Version der CAB-Datei für die Benutzeroberflächen Kultur an den Speicherort hochgeladen wird, der durch das **helpcontenturi** -Element in der helpinfo-XML-Datei angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8fb64-110">Updatable Help requires only that the version number for a UI culture increase when a new version of the CAB file for that UI culture is uploaded to the location that is specified by the **HelpContentURI** element in the HelpInfo XML file.</span></span>

<span data-ttu-id="8fb64-111">Das folgende Beispiel zeigt die Elemente der helpinfo-XML-Datei für die deutsche Benutzeroberflächen Kultur (de-de), wenn die Version 2.15.0.10 ist.</span><span class="sxs-lookup"><span data-stu-id="8fb64-111">The following example shows the elements of the HelpInfo XML file for the German (de-DE) UI culture when the version is 2.15.0.10.</span></span>

```xml

<UICulture>
  <UICultureName>de-DE</UICultureName>
  <UICultureVersion>2.15.0.10</UICultureVersion>
</UICulture>
```

<span data-ttu-id="8fb64-112">Die Versionsnummer für eine Benutzeroberflächen Kultur spiegelt die Version der CAB-Datei für die Benutzeroberflächen Kultur wider.</span><span class="sxs-lookup"><span data-stu-id="8fb64-112">The version number for a UI culture reflects the version of the CAB file for that UI culture.</span></span> <span data-ttu-id="8fb64-113">Die Versionsnummer gilt für die gesamte CAB-Datei.</span><span class="sxs-lookup"><span data-stu-id="8fb64-113">The version number applies to the entire CAB file.</span></span> <span data-ttu-id="8fb64-114">In der CAB-Datei können keine anderen Versionsnummern für verschiedene Dateien festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="8fb64-114">You cannot set different version numbers for different files in the CAB file.</span></span> <span data-ttu-id="8fb64-115">Die Versionsnummer für jede Benutzeroberflächen Kultur wird unabhängig ausgewertet und muss nicht mit den Versionsnummern für andere Benutzeroberflächen Kulturen verknüpft sein, die das Modul unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8fb64-115">The version number for each UI culture is evaluated independently and need not be related to the version numbers for other UI cultures that the module supports.</span></span>