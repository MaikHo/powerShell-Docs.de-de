---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: ResourceTest-Methode
ms.openlocfilehash: ff06fd645a94055e79aa0f8d20f2f06e16483720
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954947"
---
# <a name="resourcetest-method"></a><span data-ttu-id="81de2-103">ResourceTest-Methode</span><span class="sxs-lookup"><span data-stu-id="81de2-103">ResourceTest method</span></span>

<span data-ttu-id="81de2-104">Ruft direkt die **Test**-Methode einer DSC-Ressource auf.</span><span class="sxs-lookup"><span data-stu-id="81de2-104">Directly calls the **Test** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="81de2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="81de2-105">Syntax</span></span>

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

## <a name="parameters"></a><span data-ttu-id="81de2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="81de2-106">Parameters</span></span>

<span data-ttu-id="81de2-107">*ResourceType* \[in\] Der Name der aufzurufenden Ressource.</span><span class="sxs-lookup"><span data-stu-id="81de2-107">*ResourceType* \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="81de2-108">*ModuleName* \[in\] Der Name des Moduls, das die aufzurufende Ressource enthält.</span><span class="sxs-lookup"><span data-stu-id="81de2-108">*ModuleName* \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="81de2-109">*resourceProperty* \[in\] Gibt den Namen der Ressourceneigenschaft und deren Wert in einer Hashtabelle als Schlüssel und Wert an.</span><span class="sxs-lookup"><span data-stu-id="81de2-109">*resourceProperty* \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="81de2-110">Verwenden Sie das Cmdlet [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) zum Ermitteln von Ressourceneigenschaften und deren Typen.</span><span class="sxs-lookup"><span data-stu-id="81de2-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="81de2-111">*InDesiredState* \[out\] Bei der Rückgabe wird diese Eigenschaft auf **true** festgelegt, wenn sich der Zielknoten im gewünschten Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="81de2-111">*InDesiredState* \[out\] On return, this property is set to **true** if the target node is in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="81de2-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="81de2-112">Return value</span></span>

<span data-ttu-id="81de2-113">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="81de2-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="81de2-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="81de2-114">Remarks</span></span>

<span data-ttu-id="81de2-115">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="81de2-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="81de2-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="81de2-116">Requirements</span></span>

<span data-ttu-id="81de2-117">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="81de2-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="81de2-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="81de2-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="81de2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81de2-119">See also</span></span>

[<span data-ttu-id="81de2-120">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="81de2-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)