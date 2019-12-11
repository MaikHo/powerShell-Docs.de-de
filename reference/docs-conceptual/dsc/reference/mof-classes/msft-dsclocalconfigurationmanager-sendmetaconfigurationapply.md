---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: SendMetaConfigurationApply-Methode
ms.openlocfilehash: b2e420bafb8ea22aea43800f6e429d3ed785d1e8
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "71954877"
---
# <a name="sendmetaconfigurationapply-method"></a><span data-ttu-id="3ef8c-103">SendMetaConfigurationApply-Methode</span><span class="sxs-lookup"><span data-stu-id="3ef8c-103">SendMetaConfigurationApply method</span></span>

<span data-ttu-id="3ef8c-104">Legt die Einstellungen des lokalen Konfigurations-Managers fest, die zur Steuerung des Konfigurations-Agents verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3ef8c-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="3ef8c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ef8c-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="3ef8c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ef8c-106">Parameters</span></span>

<span data-ttu-id="3ef8c-107">*ConfigurationData* \[in\] Die Umgebungsdaten für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="3ef8c-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="3ef8c-108">*force* \[in\] **true**, um das Beenden der Konfiguration zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="3ef8c-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="3ef8c-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3ef8c-109">Return value</span></span>

<span data-ttu-id="3ef8c-110">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="3ef8c-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="3ef8c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ef8c-111">Remarks</span></span>

<span data-ttu-id="3ef8c-112">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="3ef8c-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3ef8c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ef8c-113">Requirements</span></span>

<span data-ttu-id="3ef8c-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="3ef8c-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="3ef8c-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="3ef8c-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="3ef8c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ef8c-116">See also</span></span>

[<span data-ttu-id="3ef8c-117">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="3ef8c-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)