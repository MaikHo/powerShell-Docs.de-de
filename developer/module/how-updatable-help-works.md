---
title: Funktionsweise von aktualisierbaren Hilfe Works | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7674636e-a0f2-4587-bfc5-dd3e6ce5489e
caps.latest.revision: 6
ms.openlocfilehash: 8874cc18416937c4d3cb30d801f2714410304c8c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860876"
---
# <a name="how-updatable-help-works"></a><span data-ttu-id="1cfd2-102">Funktionsweise der aktualisierbaren Hilfe</span><span class="sxs-lookup"><span data-stu-id="1cfd2-102">How Updatable Help Works</span></span>

<span data-ttu-id="1cfd2-103">In diesem Thema wird erläutert, wie der aktualisierbaren Hilfe Prozesse die HelpInfo XML-Datei und die CAB-Dateien für jedes Modul, und installiert die Hilfe für Benutzer aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-103">This topic explains how Updatable Help processes the HelpInfo XML file and CAB files for each module, and installs updated help for users.</span></span>

## <a name="the-update-help-process"></a><span data-ttu-id="1cfd2-104">Der Update-Help-Prozess</span><span class="sxs-lookup"><span data-stu-id="1cfd2-104">The Update-Help Process</span></span>

<span data-ttu-id="1cfd2-105">Die folgende Liste beschreibt die Aktionen der [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) Cmdlet aus, wenn ein Benutzer einen Befehl zum Aktualisieren der Hilfedateien für ein Modul in einer bestimmten UI-Kultur ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-105">The following list describes the actions of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet when a user runs a command to update the help files for a module in a particular UI culture.</span></span>
<span data-ttu-id="1cfd2-106">Die folgende Liste beschreibt die Aktionen der [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) Cmdlet aus, wenn ein Benutzer einen Befehl zum Aktualisieren der Hilfedateien für ein Modul in einer bestimmten UI-Kultur ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-106">The following list describes the actions of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet when a user runs a command to update the help files for a module in a particular UI culture.</span></span>

1. <span data-ttu-id="1cfd2-107">`Update-Help` Ruft die HelpInfo XML-Remotedatei an der durch den Wert der angegebenen Position der **HelpInfoURI** im modulmanifest Schlüssel und die Datei anhand des Schemas überprüft.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-107">`Update-Help` gets the remote HelpInfo XML file from the location specified by the value of the **HelpInfoURI** key in the module manifest and validates the file against the schema.</span></span> <span data-ttu-id="1cfd2-108">(Um das Schema anzuzeigen, finden Sie unter [HelpInfo-XML-Schema](./helpinfo-xml-schema.md).) Klicken Sie dann `Update-Help` sucht nach einer lokalen HelpInfo XML-Datei für das Modul in das Modulverzeichnis auf dem Computer des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-108">(To view the schema, see [HelpInfo XML Schema](./helpinfo-xml-schema.md).) Then `Update-Help` looks for a local HelpInfo XML file for the module in the module directory on the user's computer.</span></span>

2. <span data-ttu-id="1cfd2-109">`Update-Help` Vergleicht die Versionsnummer der Hilfedateien für die angegebene Benutzeroberflächenkultur in den lokalen und remote HelpInfo XML-Dateien für das Modul an.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-109">`Update-Help` compares the version number of the help files for the specified UI culture in the remote and local HelpInfo XML files for the module.</span></span> <span data-ttu-id="1cfd2-110">Wenn die Versionsnummer für die remote-Datei größer als die Versionsnummer für die lokale Datei ist oder wenn es keine lokale HelpInfo XML-Datei für das Modul gibt `Update-Help` bereitet, neue Hilfedateien herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-110">If the version number on the remote file is greater than version number on the local file, or if the there is no local HelpInfo XML file for the module, `Update-Help` prepares to download new help files.</span></span>

3. <span data-ttu-id="1cfd2-111">`Update-Help` Wählt die CAB-Datei für das Modul aus dem Speicherort, die gemäß der **HelpContentUri** Element in der remote HelpInfo-XML-Datendatei.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-111">`Update-Help` selects the CAB file for the module from the location specified by the **HelpContentUri** element in the remote HelpInfo XML file.</span></span> <span data-ttu-id="1cfd2-112">Es verwendet die Modulnamen, die Modul-GUID und die UI-Kultur, um die CAB-Datei zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-112">It uses the module name, module GUID, and UI culture to identify the CAB file.</span></span>

4. <span data-ttu-id="1cfd2-113">`Update-Help` Lädt die CAB-Datei herunter, entpackt sie, überprüft die Hilfe Inhaltsdateien und speichert die Hilfe Inhaltsdateien in die sprachspezifischen Unterverzeichnis des Modulverzeichnisses auf dem Computer des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-113">`Update-Help` downloads the CAB file, unpacks it, validates the help content files, and saves the help content files in the language-specific subdirectory of the module directory on the user's computer.</span></span>

5. <span data-ttu-id="1cfd2-114">`Update-Help` erstellt eine lokale HelpInfo XML-Datei durch Kopieren der remote HelpInfo XML-Datei an.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-114">`Update-Help` creates a local HelpInfo XML file by copying the remote HelpInfo XML file.</span></span> <span data-ttu-id="1cfd2-115">Die lokale HelpInfo XML-Datei bearbeitet, damit sie Elemente nur für die CAB-Datei enthält, die es installiert.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-115">It edits the local HelpInfo XML file so that it includes elements only for the CAB file that it installed.</span></span> <span data-ttu-id="1cfd2-116">Anschließend speichert die lokale HelpInfo XML-Datei im Modulverzeichnis gespeichert und wird abgeschlossen, das Update.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-116">Then it saves the local HelpInfo XML file in the module directory and concludes the update.</span></span>

## <a name="the-save-help-process"></a><span data-ttu-id="1cfd2-117">Der Save-Help-Prozess</span><span class="sxs-lookup"><span data-stu-id="1cfd2-117">The Save-Help Process</span></span>

<span data-ttu-id="1cfd2-118">Die folgende Liste beschreibt die Aktionen der [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) und [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) Cmdlets, wenn ein Benutzer führt die Befehle zum Aktualisieren der Hilfedateien in einer Dateifreigabe, und klicken Sie dann diese Dateien beim Aktualisieren der Hilfedateien auf den Computer des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-118">The following list describes the actions of the [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) and [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlets when a user runs commands to update the help files in a file share, and then use those files to update the help files on the user's computer.</span></span>
<span data-ttu-id="1cfd2-119">Die folgende Liste beschreibt die Aktionen der [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) und [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) Cmdlets, wenn ein Benutzer führt die Befehle zum Aktualisieren der Hilfedateien in einer Dateifreigabe, und klicken Sie dann diese Dateien beim Aktualisieren der Hilfedateien auf den Computer des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-119">The following list describes the actions of the [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) and [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlets when a user runs commands to update the help files in a file share, and then use those files to update the help files on the user's computer.</span></span>

<span data-ttu-id="1cfd2-120">Die `Save-Help` -Cmdlet führt die folgenden Aktionen als Reaktion auf einen Befehl aus, um die Hilfedateien für ein Modul in eine Dateifreigabe zu speichern, die angegeben wird die **DestinationPath** Parameter.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-120">The `Save-Help` cmdlet performs the following actions in response to a command to save the help files for a module in a file share that is specified by the **DestinationPath** parameter.</span></span>

1. <span data-ttu-id="1cfd2-121">`Save-Help` Ruft die HelpInfo XML-Remotedatei an der durch den Wert der angegebenen Position der **HelpInfoURI** im modulmanifest Schlüssel und die Datei anhand des Schemas überprüft.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-121">`Save-Help` gets  the remote HelpInfo XML file from the location specified by the value of the **HelpInfoURI** key in the module manifest and validates the file against the schema.</span></span> <span data-ttu-id="1cfd2-122">(Um das Schema anzuzeigen, finden Sie unter [HelpInfo-XML-Schema](./helpinfo-xml-schema.md).) Klicken Sie dann `Save-Help` sucht nach einer lokalen HelpInfo XML-Datei im Verzeichnis, das angegeben wird die **DestinationPath** Parameter in der `Save-Help` Befehl.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-122">(To view the schema, see [HelpInfo XML Schema](./helpinfo-xml-schema.md).) Then `Save-Help` looks for a local HelpInfo XML file in the directory that is specified by the **DestinationPath** parameter in the `Save-Help` command.</span></span>

2. <span data-ttu-id="1cfd2-123">`Save-Help` Vergleicht die Versionsnummer der Hilfedateien für die angegebene Benutzeroberflächenkultur in den lokalen und remote HelpInfo XML-Dateien für das Modul an.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-123">`Save-Help` compares the version number of the help files for the specified UI culture in the remote and local HelpInfo XML files for the module.</span></span> <span data-ttu-id="1cfd2-124">Wenn die Versionsnummer für die remote-Datei größer als die Versionsnummer für die lokale Datei ist oder wenn es keine lokale HelpInfo XML-Datei für das Modul gibt der **DestinationPath** Verzeichnis `Save-Help` bereitet, neue Hilfedateien herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-124">If the version number on the remote file is greater than version number on the local file, or if the there is no local HelpInfo XML file for the module in the **DestinationPath** directory, `Save-Help` prepares to download new help files.</span></span>

3. <span data-ttu-id="1cfd2-125">`Save-Help` Wählt die CAB-Datei für das Modul aus dem Speicherort, die gemäß der **HelpContentUri** Element in der remote HelpInfo-XML-Datendatei.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-125">`Save-Help` selects the CAB file for the module from the location specified by the **HelpContentUri** element in the remote HelpInfo XML file.</span></span> <span data-ttu-id="1cfd2-126">Es verwendet die Modulnamen, die Modul-GUID und die UI-Kultur, um die CAB-Datei zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-126">It uses the module name, module GUID, and UI culture to identify the CAB file.</span></span>

4. <span data-ttu-id="1cfd2-127">`Save-Help` die CAB-Datei lädt und speichert sie in der **DestinationPath** Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-127">`Save-Help` downloads the CAB file and saves it in the **DestinationPath** directory.</span></span> <span data-ttu-id="1cfd2-128">(Es wird keine sprachspezifischen Unterverzeichnisse erstellt.)</span><span class="sxs-lookup"><span data-stu-id="1cfd2-128">(It does not create any language-specific subdirectories.)</span></span>

5. <span data-ttu-id="1cfd2-129">`Save-Help` erstellt eine lokale HelpInfo XML-Datei durch Kopieren der remote HelpInfo XML-Datei an.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-129">`Save-Help` creates a local HelpInfo XML file by copying the remote HelpInfo XML file.</span></span> <span data-ttu-id="1cfd2-130">Die lokale HelpInfo XML-Datei bearbeitet, damit sie Elemente nur für die CAB-Datei enthält, die sie gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-130">It edits the local HelpInfo XML file so that it includes elements only for the CAB file that it saved.</span></span> <span data-ttu-id="1cfd2-131">Dann die lokale HelpInfo XML-Datei in speichert die **DestinationPath** Verzeichnis und schließt das Update.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-131">Then it saves the local HelpInfo XML file in the  **DestinationPath** directory and concludes the update.</span></span>

   <span data-ttu-id="1cfd2-132">Die `Update-Help` -Cmdlet führt die folgenden Aktionen als Reaktion auf einen Befehl aus, um die Hilfedateien auf dem Computer eines Benutzers aus den Dateien in einer Dateifreigabe aktualisieren, die angegeben wird die **SourcePath** Parameter.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-132">The `Update-Help` cmdlet performs the following actions in response to a command to update the help files on a user's computer from the files in a file share that is specified by the **SourcePath** parameter.</span></span>

1. <span data-ttu-id="1cfd2-133">`Update-Help` Ruft ab, der remote HelpInfo XML-Datei aus dem **SourcePath** Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-133">`Update-Help` gets the remote HelpInfo XML file from the **SourcePath** directory.</span></span> <span data-ttu-id="1cfd2-134">Klicken Sie dann nach einer lokalen HelpInfo XML-Datei im Modulverzeichnis auf dem Computer des Benutzers gesucht.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-134">Then it looks for a local HelpInfo XML file in the module directory on the user's computer.</span></span>

2. <span data-ttu-id="1cfd2-135">`Update-Help` Vergleicht die Versionsnummer der Hilfedateien für die angegebene Benutzeroberflächenkultur in den lokalen und remote HelpInfo XML-Dateien für das Modul an.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-135">`Update-Help` compares the version number of the help files for the specified UI culture in the remote and local HelpInfo XML files for the module.</span></span> <span data-ttu-id="1cfd2-136">Wenn die Versionsnummer für die remote-Datei größer als die Versionsnummer für die lokale Datei ist oder wenn es keine lokale HelpInfo XML-Datei gibt `Update-Help` bereitet, neue Hilfedateien zu installieren.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-136">If the version number on the remote file is greater than version number on the local file, or if the there is no local HelpInfo XML file, `Update-Help` prepares to install new help files.</span></span>

3. <span data-ttu-id="1cfd2-137">`Update-Help` Wählt die CAB-Datei für das Modul aus **SourcePath** Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-137">`Update-Help` selects the CAB file for the module from **SourcePath** directory.</span></span> <span data-ttu-id="1cfd2-138">Es verwendet die Modulnamen, die Modul-GUID und die UI-Kultur, um die CAB-Datei zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-138">It uses the module name, module GUID, and UI culture to identify the CAB file.</span></span>

4. <span data-ttu-id="1cfd2-139">`Update-Help` die CAB-Datei entpackt, überprüft die Hilfe Inhaltsdateien und speichert die Hilfe Inhaltsdateien in die sprachspezifischen Unterverzeichnis des Modulverzeichnisses auf dem Computer des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-139">`Update-Help` unpacks the CAB file, validates the help content files, and saves the help content files in the language-specific subdirectory of the module directory on the user's computer.</span></span>

5. <span data-ttu-id="1cfd2-140">`Update-Help` erstellt eine lokale HelpInfo XML-Datei durch Kopieren der remote HelpInfo XML-Datei an.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-140">`Update-Help` creates a local HelpInfo XML file by copying the remote HelpInfo XML file.</span></span> <span data-ttu-id="1cfd2-141">Die lokale HelpInfo XML-Datei bearbeitet, damit sie Elemente nur für die CAB-Datei enthält, die es installiert.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-141">It edits the local HelpInfo XML file so that it includes elements only for the CAB file that it installed.</span></span> <span data-ttu-id="1cfd2-142">Anschließend speichert die lokale HelpInfo XML-Datei im Modulverzeichnis gespeichert und wird abgeschlossen, das Update.</span><span class="sxs-lookup"><span data-stu-id="1cfd2-142">Then it saves the local HelpInfo XML file in the module directory and concludes the update.</span></span>