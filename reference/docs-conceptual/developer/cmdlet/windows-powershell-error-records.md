---
title: Windows PowerShell-Fehler Datensätze | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error category [PowerShell SDK]
- error identifier [PowerShell SDK]
- error records [PowerShell SDK]
- error category string [PowerShell SDK]
ms.assetid: bdd66fea-eb63-4bb6-9cbe-9a799e5e0db5
caps.latest.revision: 9
ms.openlocfilehash: 5412d88b690a1f5f1ef387416e3bf9da3a32c95d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369109"
---
# <a name="windows-powershell-error-records"></a><span data-ttu-id="5cac6-102">Windows PowerShell-Fehlerdatensätze</span><span class="sxs-lookup"><span data-stu-id="5cac6-102">Windows PowerShell Error Records</span></span>

<span data-ttu-id="5cac6-103">Cmdlets müssen ein [System. Management. Automation. ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) -Objekt übergeben, das die Fehlerbedingung für das Beenden und das Abbrechen von Fehlern angibt, die nicht abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="5cac6-103">Cmdlets must pass an [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) object that identifies the error condition for terminating and non-terminating errors.</span></span>

<span data-ttu-id="5cac6-104">Das [System. Management. Automation. ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) -Objekt enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="5cac6-104">The [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) object contains the following information:</span></span>

- <span data-ttu-id="5cac6-105">Die Ausnahme, die den Fehler beschreibt.</span><span class="sxs-lookup"><span data-stu-id="5cac6-105">The exception that describes the error.</span></span> <span data-ttu-id="5cac6-106">Häufig handelt es sich hierbei um eine Ausnahme, die vom Cmdlet abgefangen und in einen Fehler Daten Satz konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5cac6-106">Often, this is an exception that the cmdlet caught and converted into an error record.</span></span> <span data-ttu-id="5cac6-107">Jeder Fehler Daten Satz muss eine Ausnahme enthalten.</span><span class="sxs-lookup"><span data-stu-id="5cac6-107">Every error record must contain an exception.</span></span>

<span data-ttu-id="5cac6-108">Wenn das Cmdlet eine Ausnahme nicht abfängt, muss eine neue Ausnahme erstellt und die Ausnahme Klasse ausgewählt werden, die die Fehlerbedingung am besten beschreibt.</span><span class="sxs-lookup"><span data-stu-id="5cac6-108">If the cmdlet did not catch an exception, it must create a new exception and choose the exception class that best describes the error condition.</span></span> <span data-ttu-id="5cac6-109">Sie müssen die Ausnahme jedoch nicht auslösen, da Sie über die [System. Management. Automation. ErrorRecord. Exception](/dotnet/api/System.Management.Automation.ErrorRecord.Exception) -Eigenschaft des [System. Management. Automation. ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) -Objekts aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="5cac6-109">However, you do not need to throw the exception because it can be accessed through the [System.Management.Automation.ErrorRecord.Exception](/dotnet/api/System.Management.Automation.ErrorRecord.Exception) property of the [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) object.</span></span>

- <span data-ttu-id="5cac6-110">Ein Fehler Bezeichner, der einen Ziel Kenn Zeichner bereitstellt, der zu Diagnose Zwecken und von Windows PowerShell-Skripts verwendet werden kann, um bestimmte Fehlerbedingungen mit bestimmten Fehler Handlern zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5cac6-110">An error identifier that provides a targeted designator that can be used for diagnostic purposes and by Windows PowerShell scripts to handle specific error conditions with specific error handlers.</span></span> <span data-ttu-id="5cac6-111">Jeder Fehler Daten Satz muss einen Fehler Bezeichner enthalten (siehe Fehler Bezeichner).</span><span class="sxs-lookup"><span data-stu-id="5cac6-111">Every error record must contain an error identifier (see Error Identifier).</span></span>

- <span data-ttu-id="5cac6-112">Eine Fehler Kategorie, die einen allgemeinen Kenn Zeichner bereitstellt, der zu Diagnose Zwecken verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5cac6-112">An error category that provides a general designator that can be used for diagnostic purposes.</span></span> <span data-ttu-id="5cac6-113">Jeder Fehler Daten Satz muss eine Fehler Kategorie angeben (siehe Fehler Kategorie).</span><span class="sxs-lookup"><span data-stu-id="5cac6-113">Every error record must specify an error category (see Error Category).</span></span>

- <span data-ttu-id="5cac6-114">Eine optionale Ersatz Fehlermeldung und eine empfohlene Aktion (siehe Ersatz Fehlermeldung).</span><span class="sxs-lookup"><span data-stu-id="5cac6-114">An optional replacement error message and a recommended action (see Replacement Error Message).</span></span>

- <span data-ttu-id="5cac6-115">Optionale Aufruf Informationen über das Cmdlet, das den Fehler ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="5cac6-115">Optional invocation information about the cmdlet that threw the error.</span></span> <span data-ttu-id="5cac6-116">Diese Informationen werden von Windows PowerShell angegeben (siehe Aufruf Nachricht).</span><span class="sxs-lookup"><span data-stu-id="5cac6-116">This information is specified by Windows PowerShell (see Invocation Message).</span></span>

- <span data-ttu-id="5cac6-117">Das Zielobjekt, das beim Auftreten des Fehlers verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="5cac6-117">The target object that was being processed when the error occurred.</span></span> <span data-ttu-id="5cac6-118">Dies kann das Eingabe Objekt sein, oder es kann ein anderes Objekt sein, das das Cmdlet verarbeitet hat.</span><span class="sxs-lookup"><span data-stu-id="5cac6-118">This might be the input object, or it might be another object that your cmdlet was processing.</span></span> <span data-ttu-id="5cac6-119">Beispielsweise kann für den Befehl `remove-item -recurse c:\somedirectory` der Fehler eine Instanz eines FileInfo-Objekts für "c:\somedirectory\lockedfile" sein.</span><span class="sxs-lookup"><span data-stu-id="5cac6-119">For example, for the command `remove-item -recurse c:\somedirectory`, the error might be an instance of a FileInfo object for "c:\somedirectory\lockedfile".</span></span> <span data-ttu-id="5cac6-120">Die Zielobjekt Informationen sind optional.</span><span class="sxs-lookup"><span data-stu-id="5cac6-120">The target object information is optional.</span></span>

## <a name="error-identifier"></a><span data-ttu-id="5cac6-121">Fehler Bezeichner</span><span class="sxs-lookup"><span data-stu-id="5cac6-121">Error Identifier</span></span>

<span data-ttu-id="5cac6-122">Wenn Sie einen Fehler Daten Satz erstellen, geben Sie einen Bezeichner an, der die Fehlerbedingung innerhalb des Cmdlets festlegt.</span><span class="sxs-lookup"><span data-stu-id="5cac6-122">When you create an error record, specify an identifier that designates the error condition within your cmdlet.</span></span> <span data-ttu-id="5cac6-123">Windows PowerShell kombiniert den Ziel Bezeichner mit dem Namen des Cmdlets, um einen voll qualifizierten Fehler Bezeichner zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5cac6-123">Windows PowerShell combines the targeted identifier with the name of your cmdlet to create a fully qualified error identifier.</span></span> <span data-ttu-id="5cac6-124">Der Zugriff auf den voll qualifizierten Fehler Bezeichner kann über die [System. Management. Automation. ErrorRecord. fullyqualifiederrorid-](/dotnet/api/System.Management.Automation.ErrorRecord.FullyQualifiedErrorId) Eigenschaft des [System. Management. Automation. ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) -Objekts erfolgen.</span><span class="sxs-lookup"><span data-stu-id="5cac6-124">The fully qualified error identifier can be accessed through the [System.Management.Automation.ErrorRecord.FullyQualifiedErrorId](/dotnet/api/System.Management.Automation.ErrorRecord.FullyQualifiedErrorId) property of the [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord) object.</span></span> <span data-ttu-id="5cac6-125">Der Fehler Bezeichner ist allein nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5cac6-125">The error identifier is not available by itself.</span></span> <span data-ttu-id="5cac6-126">Sie ist nur als Teil des voll qualifizierten Fehler Bezeichners verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5cac6-126">It is available only as part of the fully qualified error identifier.</span></span>

<span data-ttu-id="5cac6-127">Verwenden Sie die folgenden Richtlinien, um beim Erstellen von Fehler Datensätzen Fehler Bezeichner zu generieren:</span><span class="sxs-lookup"><span data-stu-id="5cac6-127">Use the following guidelines to generate error identifiers when you create error records:</span></span>

- <span data-ttu-id="5cac6-128">Machen Sie Fehler Bezeichner für einen Fehlerzustand spezifisch.</span><span class="sxs-lookup"><span data-stu-id="5cac6-128">Make error identifiers specific to an error condition.</span></span> <span data-ttu-id="5cac6-129">Ziel der Fehler Bezeichner für Diagnosezwecke und für Skripts, die bestimmte Fehlerbedingungen mit bestimmten Fehler Handlern verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5cac6-129">Target the error identifiers for diagnostic purposes and for scripts that handle specific error conditions with specific error handlers.</span></span> <span data-ttu-id="5cac6-130">Ein Benutzer sollte die Fehlerkennung verwenden können, um den Fehler und dessen Quelle zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5cac6-130">A user should be able to use the error identifier to identify the error and its source.</span></span> <span data-ttu-id="5cac6-131">Fehler Bezeichner ermöglichen auch die Berichterstellung für bestimmte Fehlerbedingungen aus vorhandenen Ausnahmen, sodass keine neuen Ausnahme Unterklassen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5cac6-131">Error identifiers also enable reporting for specific error conditions from existing exceptions so that new exception subclasses are not required.</span></span>

- <span data-ttu-id="5cac6-132">Weisen Sie unterschiedliche Fehler Bezeichner unterschiedlichen Codepfade zu.</span><span class="sxs-lookup"><span data-stu-id="5cac6-132">In general, assign different error identifiers to different code paths.</span></span> <span data-ttu-id="5cac6-133">Der Endbenutzer profitiert von bestimmten bezeichlern.</span><span class="sxs-lookup"><span data-stu-id="5cac6-133">The end-user benefits from specific identifiers.</span></span> <span data-ttu-id="5cac6-134">Häufig hat jeder Codepfad, der " [System. Management. Automation. Cmdlet. Write-error](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) " oder " [System. Management. Automation. Cmdlet. ThrowTerminatingError \*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) " aufruft, einen eigenen Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="5cac6-134">Often, each code path that calls [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) or [System.Management.Automation.Cmdlet.Throwterminatingerror\*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) has its own identifier.</span></span> <span data-ttu-id="5cac6-135">Definieren Sie als Regel einen neuen Bezeichner, wenn Sie eine neue Vorlagen Zeichenfolge für die Fehlermeldung definieren und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="5cac6-135">As a rule, define a new identifier when you define a new template string for the error message, and vice-versa.</span></span> <span data-ttu-id="5cac6-136">Verwenden Sie die Fehlermeldung nicht als Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="5cac6-136">Do not use the error message as an identifier.</span></span>

- <span data-ttu-id="5cac6-137">Wenn Sie Code mithilfe eines bestimmten Fehler Bezeichners veröffentlichen, legen Sie die Semantik von Fehlern mit diesem Bezeichner für den gesamten Lebenszyklus des Produkt Supports fest.</span><span class="sxs-lookup"><span data-stu-id="5cac6-137">When you publish code using a particular error identifier, you establish the semantics of errors with that identifier for your complete product support lifecycle.</span></span> <span data-ttu-id="5cac6-138">Verwenden Sie Sie nicht in einem Kontext, der semantisch vom ursprünglichen Kontext abweicht.</span><span class="sxs-lookup"><span data-stu-id="5cac6-138">Do not reuse it in a context that is semantically different from the original context.</span></span> <span data-ttu-id="5cac6-139">Wenn sich die Semantik dieses Fehlers ändert, erstellen Sie einen neuen Bezeichner, und verwenden Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="5cac6-139">If the semantics of this error change, create and then use a new identifier.</span></span>

- <span data-ttu-id="5cac6-140">Sie sollten im Allgemeinen nur für Ausnahmen eines bestimmten CLR-Typs einen bestimmten Fehler Bezeichner verwenden.</span><span class="sxs-lookup"><span data-stu-id="5cac6-140">You should generally use a particular error identifier only for exceptions of a particular CLR type.</span></span> <span data-ttu-id="5cac6-141">Wenn sich der Typ der Ausnahme oder der Typ des Zielobjekts ändert, erstellen Sie, und verwenden Sie dann einen neuen Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="5cac6-141">If the type of the exception or the type of the target object changes, create and then use a new identifier.</span></span>

- <span data-ttu-id="5cac6-142">Wählen Sie Text für die Fehler-ID aus, die dem von Ihnen Bericht Erstellungs Fehler entspricht.</span><span class="sxs-lookup"><span data-stu-id="5cac6-142">Choose text for your error identifier that concisely corresponds to the error that you are reporting.</span></span> <span data-ttu-id="5cac6-143">Verwenden Sie .NET Framework Benennungs-und Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="5cac6-143">Use standard .NET Framework naming and capitalization conventions.</span></span> <span data-ttu-id="5cac6-144">Verwenden Sie keine Leerzeichen oder Interpunktions Zeichen.</span><span class="sxs-lookup"><span data-stu-id="5cac6-144">Do not use white space or punctuation.</span></span> <span data-ttu-id="5cac6-145">Die Fehler Bezeichner können nicht lokalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="5cac6-145">Do not localize error identifiers.</span></span>

- <span data-ttu-id="5cac6-146">Generieren Sie Fehler Bezeichner nicht dynamisch auf nicht reproduzierbare Weise.</span><span class="sxs-lookup"><span data-stu-id="5cac6-146">Do not dynamically generate error identifiers in a non-reproducible way.</span></span> <span data-ttu-id="5cac6-147">Binden Sie z. b. keine Fehlerinformationen ein, z. b. eine Prozess-ID.</span><span class="sxs-lookup"><span data-stu-id="5cac6-147">For example, do not incorporate error information such as a process ID.</span></span> <span data-ttu-id="5cac6-148">Fehler Bezeichner sind nur hilfreich, wenn Sie den Fehler bezeichmern entsprechen, die von anderen Benutzern erkannt werden, die dieselbe Fehlerbedingung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="5cac6-148">Error identifiers are useful only if they correspond to the error identifiers seen by other users who are experiencing the same error condition.</span></span>

## <a name="error-category"></a><span data-ttu-id="5cac6-149">Fehler Kategorie</span><span class="sxs-lookup"><span data-stu-id="5cac6-149">Error Category</span></span>

<span data-ttu-id="5cac6-150">Wenn Sie einen Fehler Daten Satz erstellen, geben Sie die Kategorie des Fehlers mithilfe einer der Konstanten an, die von der [System. Management. Automation. ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory?view=pscore-6.2.0) -Enumeration definiert werden.</span><span class="sxs-lookup"><span data-stu-id="5cac6-150">When you create an error record, specify the category of the error using one of the constants defined by the [System.Management.Automation.ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory?view=pscore-6.2.0) enumeration.</span></span> <span data-ttu-id="5cac6-151">Windows PowerShell verwendet die Fehler Kategorie, um Fehlerinformationen anzuzeigen, wenn Benutzer die `$ErrorView`-Variable auf `"CategoryView"` festlegen.</span><span class="sxs-lookup"><span data-stu-id="5cac6-151">Windows PowerShell uses the error category to display error information when users set the `$ErrorView` variable to `"CategoryView"`.</span></span>

<span data-ttu-id="5cac6-152">Vermeiden Sie die Verwendung der [System. Management. Automation. ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory?view=pscore-6.2.0) **NotSet** -Konstante.</span><span class="sxs-lookup"><span data-stu-id="5cac6-152">Avoid using the [System.Management.Automation.ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory?view=pscore-6.2.0) **NotSpecified** constant.</span></span> <span data-ttu-id="5cac6-153">Wenn Sie Informationen über den Fehler oder den Vorgang haben, der den Fehler verursacht hat, wählen Sie die Kategorie aus, die den Fehler oder den Vorgang am besten beschreibt, auch wenn die Kategorie nicht perfekt geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="5cac6-153">If you have any information about the error or about the operation that caused the error, choose the category that best describes the error or the operation, even if the category is not a perfect match.</span></span>

<span data-ttu-id="5cac6-154">Die von Windows PowerShell angezeigten Informationen werden als Zeichenfolge für die Kategorieansicht bezeichnet und aus den Eigenschaften der [System. Management. Automation. errorcategoryinfo](/dotnet/api/System.Management.Automation.ErrorCategoryInfo) -Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="5cac6-154">The information displayed by Windows PowerShell is referred to as the category-view string and is built from the properties of the [System.Management.Automation.Errorcategoryinfo](/dotnet/api/System.Management.Automation.ErrorCategoryInfo) class.</span></span> <span data-ttu-id="5cac6-155">(Auf diese Klasse wird durch die Error [System. Management. Automation. ErrorRecord. categoryinfo](/dotnet/api/System.Management.Automation.ErrorRecord.CategoryInfo) -Eigenschaft zugegriffen.)</span><span class="sxs-lookup"><span data-stu-id="5cac6-155">(This class is accessed through the error [System.Management.Automation.ErrorRecord.CategoryInfo](/dotnet/api/System.Management.Automation.ErrorRecord.CategoryInfo) property.)</span></span>

```
{Category}: ({TargetName}:{TargetType}):[{Activity}], {Reason}
```

<span data-ttu-id="5cac6-156">In der folgenden Liste werden die angezeigten Informationen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="5cac6-156">The following list describes the information displayed:</span></span>

- <span data-ttu-id="5cac6-157">Kategorie: eine Windows PowerShell-definierte [System. Management. Automation. ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory?view=pscore-6.2.0) -Konstante.</span><span class="sxs-lookup"><span data-stu-id="5cac6-157">Category: A Windows PowerShell-defined [System.Management.Automation.ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory?view=pscore-6.2.0) constant.</span></span>

- <span data-ttu-id="5cac6-158">TargetName: standardmäßig der Name des Objekts, das das Cmdlet verarbeitet hat, als der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="5cac6-158">TargetName: By default, the name of the object the cmdlet was processing when the error occurred.</span></span> <span data-ttu-id="5cac6-159">Oder eine andere Cmdlet-definierte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5cac6-159">Or, another cmdlet-defined string.</span></span>

- <span data-ttu-id="5cac6-160">TargetType: standardmäßig der Typ des Zielobjekts.</span><span class="sxs-lookup"><span data-stu-id="5cac6-160">TargetType: By default, the type of the target object.</span></span> <span data-ttu-id="5cac6-161">Oder eine andere Cmdlet-definierte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5cac6-161">Or, another cmdlet-defined string.</span></span>

- <span data-ttu-id="5cac6-162">Aktivität: standardmäßig der Name des Cmdlets, von dem der Fehler Daten Satz erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5cac6-162">Activity: By default, the name of the cmdlet that created the error record.</span></span> <span data-ttu-id="5cac6-163">Oder eine andere Cmdlet-definierte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5cac6-163">Or, some other cmdlet-defined string.</span></span>

- <span data-ttu-id="5cac6-164">Ursache: der Ausnahmetyp ist standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="5cac6-164">Reason: By default, the exception type.</span></span> <span data-ttu-id="5cac6-165">Oder eine andere Cmdlet-definierte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5cac6-165">Or, another cmdlet-defined string.</span></span>

## <a name="replacement-error-message"></a><span data-ttu-id="5cac6-166">Ersetzungs Fehlermeldung</span><span class="sxs-lookup"><span data-stu-id="5cac6-166">Replacement Error Message</span></span>

<span data-ttu-id="5cac6-167">Wenn Sie einen Fehler Daten Satz für ein Cmdlet entwickeln, wird die Standard Fehlermeldung für den Fehler aus dem Standard Meldungs Text in der [System. Exception. Message](/dotnet/api/System.Exception.Message) -Eigenschaft ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="5cac6-167">When you develop an error record for a cmdlet, the default error message for the error comes from the default message text in the [System.Exception.Message](/dotnet/api/System.Exception.Message) property.</span></span> <span data-ttu-id="5cac6-168">Dabei handelt es sich um eine schreibgeschützte Eigenschaft, deren Meldungs Text nur für Debuggingzwecke vorgesehen ist (gemäß den .NET Framework Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="5cac6-168">This is a read-only property whose message text is intended only for debugging purposes (according to the .NET Framework guidelines).</span></span> <span data-ttu-id="5cac6-169">Es wird empfohlen, dass Sie eine Fehlermeldung erstellen, die den Standard Nachrichtentext ersetzt oder erweitert.</span><span class="sxs-lookup"><span data-stu-id="5cac6-169">We recommend that you create an error message that replaces or augments the default message text.</span></span> <span data-ttu-id="5cac6-170">Machen Sie die Nachricht benutzerfreundlicher und spezifischere für das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5cac6-170">Make the message more user-friendly and more specific to the cmdlet.</span></span>

<span data-ttu-id="5cac6-171">Die Ersetzungs Meldung wird von einem [System. Management. Automation. errorDetails](/dotnet/api/System.Management.Automation.ErrorDetails) -Objekt bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5cac6-171">The replacement message is provided by an [System.Management.Automation.ErrorDetails](/dotnet/api/System.Management.Automation.ErrorDetails) object.</span></span> <span data-ttu-id="5cac6-172">Verwenden Sie einen der folgenden Konstruktoren dieses Objekts, da Sie zusätzliche Lokalisierungs Informationen bereitstellen, die von Windows PowerShell verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5cac6-172">Use one of the following constructors of this object because they provide additional localization information that can be used by Windows PowerShell.</span></span>

- <span data-ttu-id="5cac6-173">[ErrorDetails (Cmdlet, String, String, Object [])](/dotnet/api/system.management.automation.errordetails.-ctor?view=pscore-6.2.0#System_Management_Automation_ErrorDetails__ctor_System_Management_Automation_Cmdlet_System_String_System_String_System_Object___): Verwenden Sie diesen Konstruktor, wenn die Vorlagen Zeichenfolge eine Ressourcen Zeichenfolge in derselben Assembly ist, in der das Cmdlet implementiert ist, oder wenn Sie die Vorlagen Zeichenfolge über eine außer Kraft setzung des [ System. Management. Automation. Cmdlet. GetResourceString](/dotnet/api/System.Management.Automation.Cmdlet.GetResourceString) -Methode.</span><span class="sxs-lookup"><span data-stu-id="5cac6-173">[ErrorDetails(Cmdlet, String, String, Object[])](/dotnet/api/system.management.automation.errordetails.-ctor?view=pscore-6.2.0#System_Management_Automation_ErrorDetails__ctor_System_Management_Automation_Cmdlet_System_String_System_String_System_Object___): Use this constructor if your template string is a resource string in the same assembly in which the cmdlet is implemented or if you want to load the template string through an override of the  [System.Management.Automation.Cmdlet.GetResourceString](/dotnet/api/System.Management.Automation.Cmdlet.GetResourceString) method.</span></span>

- <span data-ttu-id="5cac6-174">[ErrorDetails (Assembly, String, String, Object [])](/dotnet/api/system.management.automation.errordetails.-ctor?view=pscore-6.2.0#System_Management_Automation_ErrorDetails__ctor_System_Reflection_Assembly_System_String_System_String_System_Object___): Verwenden Sie diesen Konstruktor, wenn sich die Vorlagen Zeichenfolge in einer anderen Assembly befindet, und Sie Sie nicht durch eine außer Kraft Setzung von [System. Management. Automation. Cmdlet. GetResourceString](/dotnet/api/System.Management.Automation.Cmdlet.GetResourceString)laden.</span><span class="sxs-lookup"><span data-stu-id="5cac6-174">[ErrorDetails(Assembly, String, String, Object[])](/dotnet/api/system.management.automation.errordetails.-ctor?view=pscore-6.2.0#System_Management_Automation_ErrorDetails__ctor_System_Reflection_Assembly_System_String_System_String_System_Object___): Use this constructor if the template string is in another assembly and you do not load it through an override of [System.Management.Automation.Cmdlet.GetResourceString](/dotnet/api/System.Management.Automation.Cmdlet.GetResourceString).</span></span>

<span data-ttu-id="5cac6-175">Die Ersetzungs Nachricht muss den .NET Framework Entwurfs Richtlinien entsprechen, um Ausnahme Meldungen mit geringem Unterschied zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="5cac6-175">The replacement message should conform to the .NET Framework design guidelines for writing exception messages with a small difference.</span></span> <span data-ttu-id="5cac6-176">Die Richtlinien geben an, dass Ausnahme Meldungen für Entwickler geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5cac6-176">The guidelines state that exception messages should be written for developers.</span></span> <span data-ttu-id="5cac6-177">Diese Ersetzungs Nachrichten sollten für den Cmdlet-Benutzer geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="5cac6-177">These replacement messages should be written for the cmdlet user.</span></span>

<span data-ttu-id="5cac6-178">Die Ersetzungs Fehlermeldung muss hinzugefügt werden, bevor die Methoden " [System. Management. Automation. Cmdlet. Write-error](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) " oder " [System. Management. Automation. Cmdlet. ThrowTerminatingError \*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) " aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5cac6-178">The replacement error message must be added before the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) or [System.Management.Automation.Cmdlet.Throwterminatingerror\*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) methods are called.</span></span> <span data-ttu-id="5cac6-179">Zum Hinzufügen einer Ersatz Meldung legen Sie die [System. Management. Automation. ErrorRecord. errorDetails](/dotnet/api/System.Management.Automation.ErrorRecord.ErrorDetails) -Eigenschaft des Fehler Datensatzes fest.</span><span class="sxs-lookup"><span data-stu-id="5cac6-179">To add a replacement message, set the [System.Management.Automation.ErrorRecord.ErrorDetails](/dotnet/api/System.Management.Automation.ErrorRecord.ErrorDetails) property of the error record.</span></span> <span data-ttu-id="5cac6-180">Wenn diese Eigenschaft festgelegt ist, zeigt Windows PowerShell die [System. Management. Automation. errorDetails. Message \*](/dotnet/api/System.Management.Automation.ErrorDetails.Message) -Eigenschaft anstelle des Standard Nachrichten Texts an.</span><span class="sxs-lookup"><span data-stu-id="5cac6-180">When this property is set, Windows PowerShell displays the [System.Management.Automation.ErrorDetails.Message\*](/dotnet/api/System.Management.Automation.ErrorDetails.Message) property instead of the default message text.</span></span>

## <a name="recommended-action-information"></a><span data-ttu-id="5cac6-181">Empfohlene Aktions Informationen</span><span class="sxs-lookup"><span data-stu-id="5cac6-181">Recommended Action Information</span></span>

<span data-ttu-id="5cac6-182">Das [System. Management. Automation. errorDetails](/dotnet/api/System.Management.Automation.ErrorDetails) -Objekt kann auch Informationen darüber bereitstellen, welche Aktionen bei Auftreten des Fehlers empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="5cac6-182">The [System.Management.Automation.ErrorDetails](/dotnet/api/System.Management.Automation.ErrorDetails) object can also provide information about what actions are recommended when the error occurs.</span></span>

## <a name="invocation-information"></a><span data-ttu-id="5cac6-183">Aufruf Informationen</span><span class="sxs-lookup"><span data-stu-id="5cac6-183">Invocation information</span></span>

<span data-ttu-id="5cac6-184">Wenn ein Cmdlet " [System. Management. Automation. Cmdlet. Write-error](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) " oder " [System. Management. Automation. Cmdlet. ThrowTerminatingError \*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) " verwendet, um einen Fehler Daten Satz zu melden, werden von Windows PowerShell automatisch Informationen hinzugefügt, die die der Befehl, der aufgerufen wurde, als der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="5cac6-184">When a cmdlet uses [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) or [System.Management.Automation.Cmdlet.Throwterminatingerror\*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) to report an error record, Windows PowerShell automatically adds information that describes the command that was invoked when the error occurred.</span></span> <span data-ttu-id="5cac6-185">Diese Informationen werden von einem [System. Management. Automation. invocationinfo](/dotnet/api/System.Management.Automation.InvocationInfo) -Objekt bereitgestellt, das den Namen des Cmdlets enthält, das vom Befehl aufgerufen wurde, dem Befehl selbst und Informationen zur Pipeline oder dem Skript.</span><span class="sxs-lookup"><span data-stu-id="5cac6-185">This information is provided by a [System.Management.Automation.Invocationinfo](/dotnet/api/System.Management.Automation.InvocationInfo) object that contains the name of the cmdlet that was invoked by the command, the command itself, and information about the pipeline or script.</span></span> <span data-ttu-id="5cac6-186">Diese Eigenschaft ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="5cac6-186">This property is read-only.</span></span>

## <a name="see-also"></a><span data-ttu-id="5cac6-187">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5cac6-187">See Also</span></span>

[<span data-ttu-id="5cac6-188">System. Management. Automation. Cmdlet. Write error</span><span class="sxs-lookup"><span data-stu-id="5cac6-188">System.Management.Automation.Cmdlet.WriteError</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="5cac6-189">System. Management. Automation. Cmdlet. ThrowTerminatingError \*</span><span class="sxs-lookup"><span data-stu-id="5cac6-189">System.Management.Automation.Cmdlet.Throwterminatingerror\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[<span data-ttu-id="5cac6-190">System. Management. Automation. ErrorCategory</span><span class="sxs-lookup"><span data-stu-id="5cac6-190">System.Management.Automation.ErrorCategory</span></span>](/dotnet/api/System.Management.Automation.ErrorCategory?view=pscore-6.2.0)

[<span data-ttu-id="5cac6-191">System. Management. Automation. errorcategoryinfo</span><span class="sxs-lookup"><span data-stu-id="5cac6-191">System.Management.Automation.Errorcategoryinfo</span></span>](/dotnet/api/System.Management.Automation.ErrorCategoryInfo)

[<span data-ttu-id="5cac6-192">System. Management. Automation. ErrorRecord</span><span class="sxs-lookup"><span data-stu-id="5cac6-192">System.Management.Automation.ErrorRecord</span></span>](/dotnet/api/System.Management.Automation.ErrorRecord)

[<span data-ttu-id="5cac6-193">System. Management. Automation. errorDetails</span><span class="sxs-lookup"><span data-stu-id="5cac6-193">System.Management.Automation.ErrorDetails</span></span>](/dotnet/api/System.Management.Automation.ErrorDetails)

[<span data-ttu-id="5cac6-194">System. Management. Automation. invocationinfo</span><span class="sxs-lookup"><span data-stu-id="5cac6-194">System.Management.Automation.Invocationinfo</span></span>](/dotnet/api/System.Management.Automation.InvocationInfo)

[<span data-ttu-id="5cac6-195">Windows PowerShell-Fehlerberichterstattung</span><span class="sxs-lookup"><span data-stu-id="5cac6-195">Windows PowerShell Error Reporting</span></span>](./error-reporting-concepts.md)

[<span data-ttu-id="5cac6-196">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5cac6-196">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)