---
title: Eigenschafts Parameter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d17e0d66-42ea-4e4c-a85b-3ca09b146492
caps.latest.revision: 6
ms.openlocfilehash: cc0742b86a7a36e5712707c077fd1952691f3f4b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369579"
---
# <a name="property-parameters"></a><span data-ttu-id="ef220-102">Eigenschaftenparameter</span><span class="sxs-lookup"><span data-stu-id="ef220-102">Property Parameters</span></span>

<span data-ttu-id="ef220-103">In der folgenden Tabelle sind die empfohlenen Namen und Funktionen für Eigenschafts Parameter aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ef220-103">The following table lists the recommended names and functionality for property parameters.</span></span>

|<span data-ttu-id="ef220-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="ef220-104">Parameter</span></span>|<span data-ttu-id="ef220-105">Funktion</span><span class="sxs-lookup"><span data-stu-id="ef220-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="ef220-106">**Countdown**</span><span class="sxs-lookup"><span data-stu-id="ef220-106">**Count**</span></span><br><span data-ttu-id="ef220-107">Datentyp: Int32</span><span class="sxs-lookup"><span data-stu-id="ef220-107">Data type: Int32</span></span>|<span data-ttu-id="ef220-108">Implementieren Sie diesen Parameter, sodass der Benutzer die Anzahl der zu verarbeitenden Objekte angeben kann.</span><span class="sxs-lookup"><span data-stu-id="ef220-108">Implement this parameter so that the user can specify the number of objects to be processed.</span></span>|
|<span data-ttu-id="ef220-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ef220-109">**Description**</span></span><br><span data-ttu-id="ef220-110">Datentyp: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ef220-110">Data type: String</span></span>|<span data-ttu-id="ef220-111">Implementieren Sie diesen Parameter, sodass der Benutzer eine Beschreibung für eine Ressource angeben kann.</span><span class="sxs-lookup"><span data-stu-id="ef220-111">Implement this parameter so that the user can specify a description for a resource.</span></span>|
|<span data-ttu-id="ef220-112">**Von**</span><span class="sxs-lookup"><span data-stu-id="ef220-112">**From**</span></span><br><span data-ttu-id="ef220-113">Datentyp: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ef220-113">Data type: String</span></span>|<span data-ttu-id="ef220-114">Implementieren Sie diesen Parameter, sodass der Benutzer das Verweis Objekt angeben kann, aus dem Informationen abgeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ef220-114">Implement this parameter so that the user can specify the reference object to get information from.</span></span>|
|<span data-ttu-id="ef220-115">**Name**</span><span class="sxs-lookup"><span data-stu-id="ef220-115">**Id**</span></span><br><span data-ttu-id="ef220-116">Datentyp: Ressourcen abhängig</span><span class="sxs-lookup"><span data-stu-id="ef220-116">Data type: Resource dependent</span></span>|<span data-ttu-id="ef220-117">Implementieren Sie diesen Parameter, sodass der Benutzer den Bezeichner einer Ressource angeben kann.</span><span class="sxs-lookup"><span data-stu-id="ef220-117">Implement this parameter so that the user can specify the identifier of a resource.</span></span>|
|<span data-ttu-id="ef220-118">**Der**</span><span class="sxs-lookup"><span data-stu-id="ef220-118">**Input**</span></span><br><span data-ttu-id="ef220-119">Datentyp: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ef220-119">Data type: String</span></span>|<span data-ttu-id="ef220-120">Implementieren Sie diesen Parameter, sodass der Benutzer die Eingabedatei Spezifikation angeben kann.</span><span class="sxs-lookup"><span data-stu-id="ef220-120">Implement this parameter so that the user can specify the input file specification.</span></span>|
|<span data-ttu-id="ef220-121">**Speicherort**</span><span class="sxs-lookup"><span data-stu-id="ef220-121">**Location**</span></span><br><span data-ttu-id="ef220-122">Datentyp: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ef220-122">Data type: String</span></span>|<span data-ttu-id="ef220-123">Implementieren Sie diesen Parameter, sodass der Benutzer den Speicherort der Ressource angeben kann.</span><span class="sxs-lookup"><span data-stu-id="ef220-123">Implement this parameter so that the user can specify the location of the resource.</span></span>|
|<span data-ttu-id="ef220-124">**LogName**</span><span class="sxs-lookup"><span data-stu-id="ef220-124">**LogName**</span></span><br><span data-ttu-id="ef220-125">Datentyp: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ef220-125">Data type: String</span></span>|<span data-ttu-id="ef220-126">Implementieren Sie diesen Parameter, sodass der Benutzer den Namen der Protokolldatei angeben kann, die verarbeitet oder verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ef220-126">Implement this parameter so that the user can specify the name of the log file to process or use.</span></span>|
|<span data-ttu-id="ef220-127">**Benennen**</span><span class="sxs-lookup"><span data-stu-id="ef220-127">**Name**</span></span><br><span data-ttu-id="ef220-128">Datentyp: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ef220-128">Data type: String</span></span>|<span data-ttu-id="ef220-129">Implementieren Sie diesen Parameter, sodass der Benutzer den Namen der Ressource angeben kann.</span><span class="sxs-lookup"><span data-stu-id="ef220-129">Implement this parameter so that the user can specify the name of the resource.</span></span>|
|<span data-ttu-id="ef220-130">**Ausgeben**</span><span class="sxs-lookup"><span data-stu-id="ef220-130">**Output**</span></span><br><span data-ttu-id="ef220-131">Datentyp: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ef220-131">Data type: String</span></span>|<span data-ttu-id="ef220-132">Implementieren Sie diesen Parameter, sodass der Benutzer die Ausgabedatei angeben kann.</span><span class="sxs-lookup"><span data-stu-id="ef220-132">Implement this parameter so that the user can specify the output file.</span></span>|
|<span data-ttu-id="ef220-133">**Eigentor**</span><span class="sxs-lookup"><span data-stu-id="ef220-133">**Owner**</span></span><br><span data-ttu-id="ef220-134">Datentyp: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ef220-134">Data type: String</span></span>|<span data-ttu-id="ef220-135">Implementieren Sie diesen Parameter, sodass der Benutzer den Namen des Besitzers der Ressource angeben kann.</span><span class="sxs-lookup"><span data-stu-id="ef220-135">Implement this parameter so that the user can specify the name of the owner of the resource.</span></span>|
|<span data-ttu-id="ef220-136">**Property**</span><span class="sxs-lookup"><span data-stu-id="ef220-136">**Property**</span></span><br><span data-ttu-id="ef220-137">Datentyp: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ef220-137">Data type: String</span></span>|<span data-ttu-id="ef220-138">Implementieren Sie diesen Parameter, sodass der Benutzer den Namen oder die Namen der zu verwendenden Eigenschaften angeben kann.</span><span class="sxs-lookup"><span data-stu-id="ef220-138">Implement this parameter so that the user can specify the name or the names of the properties to use.</span></span>|
|<span data-ttu-id="ef220-139">**Weshalb**</span><span class="sxs-lookup"><span data-stu-id="ef220-139">**Reason**</span></span><br><span data-ttu-id="ef220-140">Datentyp: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ef220-140">Data type: String</span></span>|<span data-ttu-id="ef220-141">Implementieren Sie diesen Parameter, sodass der Benutzer angeben kann, warum dieses Cmdlet aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ef220-141">Implement this parameter so that the user can specify why this cmdlet is being invoked.</span></span>|
|<span data-ttu-id="ef220-142">**Regex**</span><span class="sxs-lookup"><span data-stu-id="ef220-142">**Regex**</span></span><br><span data-ttu-id="ef220-143">Datentyp: Switchparameter</span><span class="sxs-lookup"><span data-stu-id="ef220-143">Data type: SwitchParameter</span></span>|<span data-ttu-id="ef220-144">Implementieren Sie diesen Parameter, sodass reguläre Ausdrücke verwendet werden, wenn der-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ef220-144">Implement this parameter so that regular expressions are used when the parameter is specified.</span></span> <span data-ttu-id="ef220-145">Wenn dieser Parameter angegeben wird, werden Platzhalter Zeichen nicht aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="ef220-145">When this parameter is specified, wildcard characters are not resolved.</span></span>|
|<span data-ttu-id="ef220-146">**Beschleunigt**</span><span class="sxs-lookup"><span data-stu-id="ef220-146">**Speed**</span></span><br><span data-ttu-id="ef220-147">Datentyp: Int32</span><span class="sxs-lookup"><span data-stu-id="ef220-147">Data type: Int32</span></span>|<span data-ttu-id="ef220-148">Implementieren Sie diesen Parameter, sodass der Benutzer die Baudrate angeben kann.</span><span class="sxs-lookup"><span data-stu-id="ef220-148">Implement this parameter so that the user can specify the baud rate.</span></span> <span data-ttu-id="ef220-149">Der Benutzer legt diesen Parameter auf die Geschwindigkeit der Ressource fest.</span><span class="sxs-lookup"><span data-stu-id="ef220-149">The user sets this parameter to the speed of the resource.</span></span>|
|<span data-ttu-id="ef220-150">**Land**</span><span class="sxs-lookup"><span data-stu-id="ef220-150">**State**</span></span><br><span data-ttu-id="ef220-151">Datentyp: Schlüsselwort Array</span><span class="sxs-lookup"><span data-stu-id="ef220-151">Data type: Keyword array</span></span>|<span data-ttu-id="ef220-152">Implementieren Sie diesen Parameter, sodass der Benutzer die Namen von Zuständen angeben kann, z. b. KeyDown.</span><span class="sxs-lookup"><span data-stu-id="ef220-152">Implement this parameter so that the user can specify the names of states, such as KEYDOWN.</span></span>|
|<span data-ttu-id="ef220-153">**Wert**</span><span class="sxs-lookup"><span data-stu-id="ef220-153">**Value**</span></span><br><span data-ttu-id="ef220-154">Datentyp: Object</span><span class="sxs-lookup"><span data-stu-id="ef220-154">Data type: Object</span></span>|<span data-ttu-id="ef220-155">Implementieren Sie diesen Parameter, sodass der Benutzer einen Wert angeben kann, der für das Cmdlet bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ef220-155">Implement this parameter so that the user can  specify a value to provide to the cmdlet.</span></span>|
|<span data-ttu-id="ef220-156">**Version**</span><span class="sxs-lookup"><span data-stu-id="ef220-156">**Version**</span></span><br><span data-ttu-id="ef220-157">Datentyp: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ef220-157">Data type: String</span></span>|<span data-ttu-id="ef220-158">Implementieren Sie diesen Parameter, sodass der Benutzer die Version der Eigenschaft angeben kann.</span><span class="sxs-lookup"><span data-stu-id="ef220-158">Implement this parameter so that the user can specify the version of the property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="ef220-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef220-159">See Also</span></span>

[<span data-ttu-id="ef220-160">Cmdlet-Parameter</span><span class="sxs-lookup"><span data-stu-id="ef220-160">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="ef220-161">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ef220-161">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="ef220-162">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="ef220-162">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)