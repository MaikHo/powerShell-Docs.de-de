---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: GetConfigurationResultOutput-Methode
ms.openlocfilehash: 480e710ce1a208253f0e664474c3e9bab296066a
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953417"
---
# <a name="getconfigurationresultoutput-method"></a><span data-ttu-id="255c9-103">GetConfigurationResultOutput-Methode</span><span class="sxs-lookup"><span data-stu-id="255c9-103">GetConfigurationResultOutput method</span></span>

<span data-ttu-id="255c9-104">Ruft die Konfigurations-Agent-Ausgabe im Zusammenhang mit einem bestimmten Auftrag ab.</span><span class="sxs-lookup"><span data-stu-id="255c9-104">Gets the Configuration Agent output associated with a specific job.</span></span>

## <a name="syntax"></a><span data-ttu-id="255c9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="255c9-105">Syntax</span></span>

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

## <a name="parameters"></a><span data-ttu-id="255c9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="255c9-106">Parameters</span></span>

<span data-ttu-id="255c9-107">*jobId* \[in\] Die ID des Auftrags, für den Ausgabedaten abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="255c9-107">*jobId* \[in\] The ID of the job for which to get output data.</span></span>

<span data-ttu-id="255c9-108">*resumeOutputBookmark* \[in\] Gibt an, dass die Ausgabe eine Fortsetzung eines vorherigen Lesezeichens sein soll.</span><span class="sxs-lookup"><span data-stu-id="255c9-108">*resumeOutputBookmark* \[in\] Specifies that the output should be a continuation from a previous bookmark.</span></span>

<span data-ttu-id="255c9-109">*output* \[out\] Die Ausgabe für den angegebenen Auftrag.</span><span class="sxs-lookup"><span data-stu-id="255c9-109">*output* \[out\] The output for the specified job.</span></span>

## <a name="return-value"></a><span data-ttu-id="255c9-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="255c9-110">Return value</span></span>

<span data-ttu-id="255c9-111">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="255c9-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="255c9-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="255c9-112">Remarks</span></span>

<span data-ttu-id="255c9-113">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="255c9-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="255c9-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="255c9-114">Requirements</span></span>

<span data-ttu-id="255c9-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="255c9-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="255c9-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="255c9-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="255c9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="255c9-117">See also</span></span>

[<span data-ttu-id="255c9-118">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="255c9-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)