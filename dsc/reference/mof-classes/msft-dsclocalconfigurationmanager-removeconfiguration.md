---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: RemoveConfiguration-Methode der MSFT_DSCLocalConfigurationManager-Klasse
ms.openlocfilehash: 03555cc73da1272bdebebc3d93b26aaf8fabc18e
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: de-DE
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047340"
---
# <a name="removeconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="39b13-103">RemoveConfiguration-Methode der MSFT_DSCLocalConfigurationManager-Klasse</span><span class="sxs-lookup"><span data-stu-id="39b13-103">RemoveConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="39b13-104">Entfernt die Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="39b13-104">Removes the configuration files.</span></span>

## <a name="syntax"></a><span data-ttu-id="39b13-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="39b13-105">Syntax</span></span>

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a><span data-ttu-id="39b13-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="39b13-106">Parameters</span></span>

<span data-ttu-id="39b13-107">*Stage* \[in\] Gibt an, welches Konfigurationsdokument entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="39b13-107">*Stage* \[in\] Specifies which configuration document to remove.</span></span> <span data-ttu-id="39b13-108">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="39b13-108">The following values are valid:</span></span>

|<span data-ttu-id="39b13-109">Wert</span><span class="sxs-lookup"><span data-stu-id="39b13-109">Value</span></span> |<span data-ttu-id="39b13-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39b13-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="39b13-111">**1**</span><span class="sxs-lookup"><span data-stu-id="39b13-111">**1**</span></span> | <span data-ttu-id="39b13-112">Das **aktuelle** (Current) Konfigurationsdokument (current.mof).</span><span class="sxs-lookup"><span data-stu-id="39b13-112">The **Current** configuration document (current.mof).</span></span> |
|<span data-ttu-id="39b13-113">**2**</span><span class="sxs-lookup"><span data-stu-id="39b13-113">**2**</span></span> | <span data-ttu-id="39b13-114">Das **ausstehende** (Pending) Konfigurationsdokument (pending.mof).</span><span class="sxs-lookup"><span data-stu-id="39b13-114">The **Pending** configuration document (pending.mof).</span></span>  |
|<span data-ttu-id="39b13-115">**4**</span><span class="sxs-lookup"><span data-stu-id="39b13-115">**4**</span></span> | <span data-ttu-id="39b13-116">Das **vorherige** (Previous) Konfigurationsdokument (previous.mof).</span><span class="sxs-lookup"><span data-stu-id="39b13-116">The **Previous** configuration document (previous.mof).</span></span> |

<span data-ttu-id="39b13-117">*Force* \[in\] **true**, um das Entfernen der Konfiguration zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="39b13-117">*Force* \[in\] **true** to force the removal of the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="39b13-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="39b13-118">Return value</span></span>

<span data-ttu-id="39b13-119">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="39b13-119">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="39b13-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39b13-120">Remarks</span></span>

<span data-ttu-id="39b13-121">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="39b13-121">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="39b13-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="39b13-122">Requirements</span></span>

<span data-ttu-id="39b13-123">MOF\*\* DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="39b13-123">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="39b13-124">\*\*Namespace: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="39b13-124">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="39b13-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39b13-125">See also</span></span>

[<span data-ttu-id="39b13-126">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="39b13-126">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)