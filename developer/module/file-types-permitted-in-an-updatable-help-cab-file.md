---
title: In einem aktualisierbaren zulässigen Dateitypen unterstützen die CAB-Datei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/22/2012
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Windows PowerShell 3.0
ms.assetid: acabdb93-c41a-4b8d-acbe-45cdab91e198
caps.latest.revision: 10
ms.openlocfilehash: 931383858c0b83f0a9a66026c215e16481b89e9e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862836"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a><span data-ttu-id="4f4a3-102">Zulässige Dateitypen in aktualisierbaren CAB-Hilfedateien</span><span class="sxs-lookup"><span data-stu-id="4f4a3-102">File Types Permitted in an Updatable Help CAB File</span></span>

<span data-ttu-id="4f4a3-103">In diesem Thema aufgelistet und beschrieben von den Anforderungen für aktualisierbare Hilfe-CAB-Dateien.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-103">This topics lists and describes the content requirements for Updatable Help CAB files.</span></span>

## <a name="updatable-help-cab-file-requirements"></a><span data-ttu-id="4f4a3-104">Anforderungen für aktualisierbare Hilfe-CAB-Datei</span><span class="sxs-lookup"><span data-stu-id="4f4a3-104">Updatable Help CAB File Requirements</span></span>

<span data-ttu-id="4f4a3-105">Nicht komprimierte Inhalt der CAB-Datei ist standardmäßig auf 1 GB beschränkt.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-105">Uncompressed CAB file content is limited to 1 GB by default.</span></span> <span data-ttu-id="4f4a3-106">Um diese Beschränkung zu umgehen, müssen Benutzer verwenden die **Force** Parameter, der die [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) und [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-106">To bypass this limit, users have to use the **Force** parameter of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>
<span data-ttu-id="4f4a3-107">Nicht komprimierte Inhalt der CAB-Datei ist standardmäßig auf 1 GB beschränkt.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-107">Uncompressed CAB file content is limited to 1 GB by default.</span></span> <span data-ttu-id="4f4a3-108">Um diese Beschränkung zu umgehen, müssen Benutzer verwenden die **Force** Parameter, der die [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) und [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-108">To bypass this limit, users have to use the **Force** parameter of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="4f4a3-109">Um die Sicherheit der Hilfedateien zu gewährleisten, die aus dem Internet heruntergeladen werden, kann eine aktualisierbare Hilfe CAB-Datei nur die unten aufgeführten Dateitypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-109">To assure the security of help files that are downloaded from the Internet, an Updatable Help CAB file can include only the file types listed below.</span></span> <span data-ttu-id="4f4a3-110">Die [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) Cmdlet überprüft, ob alle Dateien anhand der Schemas Hilfethema.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-110">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet validates all files against the help topic schemas.</span></span> <span data-ttu-id="4f4a3-111">Wenn die `Update-Help` Cmdlet auftritt, eine Datei ist ungültig, oder ist kein zulässiger Typ ist, wird die ungültige Datei wird nicht installiert, und beendet die Installation von Dateien aus der CAB-Datei auf dem Computer des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-111">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB on the user's computer.</span></span>
<span data-ttu-id="4f4a3-112">Um die Sicherheit der Hilfedateien zu gewährleisten, die aus dem Internet heruntergeladen werden, kann eine aktualisierbare Hilfe CAB-Datei nur die unten aufgeführten Dateitypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-112">To assure the security of help files that are downloaded from the Internet, an Updatable Help CAB file can include only the file types listed below.</span></span> <span data-ttu-id="4f4a3-113">Die [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) Cmdlet überprüft, ob alle Dateien anhand der Schemas Hilfethema.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-113">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet validates all files against the help topic schemas.</span></span> <span data-ttu-id="4f4a3-114">Wenn die `Update-Help` Cmdlet auftritt, eine Datei ist ungültig, oder ist kein zulässiger Typ ist, wird die ungültige Datei wird nicht installiert, und beendet die Installation von Dateien aus der CAB-Datei auf dem Computer des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-114">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB on the user's computer.</span></span>

- <span data-ttu-id="4f4a3-115">XML-basierte Hilfethemen für Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-115">XML-based help topics for cmdlets.</span></span>

- <span data-ttu-id="4f4a3-116">XML-Hilfethemen für Skripts und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-116">XML-based help topics for scripts and functions.</span></span>

- <span data-ttu-id="4f4a3-117">XML-basierte Hilfethemen für Windows PowerShell-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-117">XML-based help topics for Windows PowerShell providers.</span></span>

- <span data-ttu-id="4f4a3-118">Textbasierte Hilfethemen, z. B. über Themen.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-118">Text-based help topics, such as About topics.</span></span>

<span data-ttu-id="4f4a3-119">Die [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) überprüft den Inhalt der CAB-Datei aus, wenn sie die CAB-Datei entpackt.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-119">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifies the CAB contents when it unpacks the CAB.</span></span> <span data-ttu-id="4f4a3-120">Wenn `Update-Help` findet nicht kompatible Dateitypen in einer aktualisierbaren-CAB-Hilfekabinettdatei, generiert einen Fehler mit Abbruch und beendet den Vorgang.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-120">If `Update-Help` finds non-compliant file types in an Updatable Help CAB file, it generates a terminating error and stops the operation.</span></span> <span data-ttu-id="4f4a3-121">Hilfedateien werden aus der CAB-Datei, einschließlich der kompatiblen Dateitypen nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-121">It does not install any help files from the CAB, even those of compliant file types.</span></span>
<span data-ttu-id="4f4a3-122">Die [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) überprüft den Inhalt der CAB-Datei aus, wenn sie die CAB-Datei entpackt.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-122">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifies the CAB contents when it unpacks the CAB.</span></span> <span data-ttu-id="4f4a3-123">Wenn `Update-Help` findet nicht kompatible Dateitypen in einer aktualisierbaren-CAB-Hilfekabinettdatei, generiert einen Fehler mit Abbruch und beendet den Vorgang.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-123">If `Update-Help` finds non-compliant file types in an Updatable Help CAB file, it generates a terminating error and stops the operation.</span></span> <span data-ttu-id="4f4a3-124">Hilfedateien werden aus der CAB-Datei, einschließlich der kompatiblen Dateitypen nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="4f4a3-124">It does not install any help files from the CAB, even those of compliant file types.</span></span>