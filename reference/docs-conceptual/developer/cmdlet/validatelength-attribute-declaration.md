---
title: ValidateLength-Attribut Deklaration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateLength attribute, described
- attributes, ValidateLength
- ValidateLength attribute
ms.assetid: 82fe3a35-a94b-4bc1-ad9e-dfc5f1e788b3
caps.latest.revision: 13
ms.openlocfilehash: a25fa2410fcc6803563573596af1bc99052c3ffa
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369179"
---
# <a name="validatelength-attribute-declaration"></a><span data-ttu-id="b6e37-102">Attributdeklaration: ValidateLength</span><span class="sxs-lookup"><span data-stu-id="b6e37-102">ValidateLength Attribute Declaration</span></span>

<span data-ttu-id="b6e37-103">Das validateLength-Attribut gibt die minimale und maximale Anzahl von Zeichen für ein Cmdlet-Parameter Argument an.</span><span class="sxs-lookup"><span data-stu-id="b6e37-103">The ValidateLength attribute specifies the minimum and maximum number of characters for a cmdlet parameter argument.</span></span> <span data-ttu-id="b6e37-104">Dieses Attribut kann auch von Windows PowerShell-Funktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b6e37-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="b6e37-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6e37-105">Syntax</span></span>

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="b6e37-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b6e37-106">Parameters</span></span>

<span data-ttu-id="b6e37-107">`MinLength` ([System. Int32](/dotnet/api/System.Int32)) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b6e37-107">`MinLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="b6e37-108">Gibt die Mindestanzahl von Zeichen an, die zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="b6e37-108">Specifies the minimum number of characters allowed.</span></span>

<span data-ttu-id="b6e37-109">`MaxLength` ([System. Int32](/dotnet/api/System.Int32)) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b6e37-109">`MaxLength` ([System.Int32](/dotnet/api/System.Int32)) Required.</span></span> <span data-ttu-id="b6e37-110">Gibt die maximal zulässige Anzahl von Zeichen an.</span><span class="sxs-lookup"><span data-stu-id="b6e37-110">Specifies the maximum number of characters allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="b6e37-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b6e37-111">Remarks</span></span>

- <span data-ttu-id="b6e37-112">Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [Deklarieren von Eingabe Validierungsregeln](./how-to-validate-parameter-input.md).</span><span class="sxs-lookup"><span data-stu-id="b6e37-112">For more information about how to declare this attribute, see [How to Declare Input Validation Rules](./how-to-validate-parameter-input.md).</span></span>

- <span data-ttu-id="b6e37-113">Wenn dieses Attribut nicht verwendet wird, kann das entsprechende Parameter Argument eine beliebige Länge aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b6e37-113">When this attribute is not used, the corresponding parameter argument can be of any length.</span></span>

- <span data-ttu-id="b6e37-114">Die Windows PowerShell-Laufzeit löst unter den folgenden Bedingungen einen Fehler aus:</span><span class="sxs-lookup"><span data-stu-id="b6e37-114">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

    - <span data-ttu-id="b6e37-115">Wenn der Wert des `MaxLength`-Attribut Parameters kleiner als der Wert des Attributs "`MinLength`" ist.</span><span class="sxs-lookup"><span data-stu-id="b6e37-115">When the value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

    - <span data-ttu-id="b6e37-116">Wenn der `MaxLength`-Attribut Parameter auf 0 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b6e37-116">When the `MaxLength` attribute parameter is set to 0.</span></span>

    - <span data-ttu-id="b6e37-117">Wenn das Argument keine Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="b6e37-117">When the argument is not a string.</span></span>

- <span data-ttu-id="b6e37-118">Das validateLength-Attribut wird von der [System. Management. Automation. validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) -Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="b6e37-118">The ValidateLength attribute is defined by the [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6e37-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6e37-119">See Also</span></span>

[<span data-ttu-id="b6e37-120">System. Management. Automation. validatelengthattribute</span><span class="sxs-lookup"><span data-stu-id="b6e37-120">System.Management.Automation.Validatelengthattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[<span data-ttu-id="b6e37-121">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="b6e37-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)