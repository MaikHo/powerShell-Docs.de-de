---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: wmf,powershell,setup
title: Verbesserungen an der PowerShell-Engine in WMF 5.1
ms.openlocfilehash: cccfcf8872ac60e0902669bcc797d0ed250317ba
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808936"
---
# <a name="powershell-engine-improvements"></a><span data-ttu-id="d151f-103">Verbesserungen an der PowerShell-Engine</span><span class="sxs-lookup"><span data-stu-id="d151f-103">PowerShell Engine Improvements</span></span>

<span data-ttu-id="d151f-104">Die folgenden Verbesserungen an der PowerShell-Kern-Engine wurden in WMF 5.1 implementiert:</span><span class="sxs-lookup"><span data-stu-id="d151f-104">The following improvements to the core PowerShell engine have been implemented in WMF 5.1:</span></span>

## <a name="performance"></a><span data-ttu-id="d151f-105">Leistung</span><span class="sxs-lookup"><span data-stu-id="d151f-105">Performance</span></span>

<span data-ttu-id="d151f-106">In einigen wichtigen Bereichen wurde die Leistung verbessert:</span><span class="sxs-lookup"><span data-stu-id="d151f-106">Performance has improved in some important areas:</span></span>

- <span data-ttu-id="d151f-107">Start</span><span class="sxs-lookup"><span data-stu-id="d151f-107">Startup</span></span>
- <span data-ttu-id="d151f-108">Das Pipelining bei Cmdlets wie `ForEach-Object` und `Where-Object` erfolgt etwa 50 % schneller.</span><span class="sxs-lookup"><span data-stu-id="d151f-108">Pipelining to cmdlets like `ForEach-Object` and `Where-Object` is approximately 50% faster</span></span>

<span data-ttu-id="d151f-109">Einige Beispiele für Verbesserungen (die Ergebnisse variieren je nach Hardware):</span><span class="sxs-lookup"><span data-stu-id="d151f-109">Some example improvements (your results may vary depending on your hardware):</span></span>

| <span data-ttu-id="d151f-110">Szenario</span><span class="sxs-lookup"><span data-stu-id="d151f-110">Scenario</span></span> | <span data-ttu-id="d151f-111">Zeit (ms) in 5.0</span><span class="sxs-lookup"><span data-stu-id="d151f-111">5.0 Time (ms)</span></span> | <span data-ttu-id="d151f-112">Zeit (ms) in 5.1</span><span class="sxs-lookup"><span data-stu-id="d151f-112">5.1 Time (ms)</span></span> |
| -------- | :---------------: | :---------------: |
| `powershell -command "echo 1"` | <span data-ttu-id="d151f-113">900</span><span class="sxs-lookup"><span data-stu-id="d151f-113">900</span></span> | <span data-ttu-id="d151f-114">250</span><span class="sxs-lookup"><span data-stu-id="d151f-114">250</span></span> |
| <span data-ttu-id="d151f-115">Erste Ausführung von PowerShell überhaupt: `powershell -command "Unknown-Command"`</span><span class="sxs-lookup"><span data-stu-id="d151f-115">First ever PowerShell run: `powershell -command "Unknown-Command"`</span></span> | <span data-ttu-id="d151f-116">30.000</span><span class="sxs-lookup"><span data-stu-id="d151f-116">30000</span></span> | <span data-ttu-id="d151f-117">13.000</span><span class="sxs-lookup"><span data-stu-id="d151f-117">13000</span></span> |
| <span data-ttu-id="d151f-118">Erstellung des Caches für die Befehlsanalyse: `powershell -command "Unknown-Command"`</span><span class="sxs-lookup"><span data-stu-id="d151f-118">Command analysis cache built: `powershell -command "Unknown-Command"`</span></span> | <span data-ttu-id="d151f-119">7000</span><span class="sxs-lookup"><span data-stu-id="d151f-119">7000</span></span> | <span data-ttu-id="d151f-120">520</span><span class="sxs-lookup"><span data-stu-id="d151f-120">520</span></span> |
| <code>1..1000000 &#124; % { }</code> | <span data-ttu-id="d151f-121">1400</span><span class="sxs-lookup"><span data-stu-id="d151f-121">1400</span></span> | <span data-ttu-id="d151f-122">750</span><span class="sxs-lookup"><span data-stu-id="d151f-122">750</span></span> |

> [!NOTE]
> <span data-ttu-id="d151f-123">Eine Änderung im Zusammenhang mit dem Start kann sich möglicherweise auf einige (nicht unterstützte) Szenarien auswirken.</span><span class="sxs-lookup"><span data-stu-id="d151f-123">One change related to startup might impact some unsupported scenarios.</span></span> <span data-ttu-id="d151f-124">PowerShell liest nicht mehr die Dateien des Typs `$pshome\*.ps1xml`. Diese Dateien wurden in C# konvertiert, um den Datei- und CPU-Overhead beim Verarbeiten der XML-Dateien zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="d151f-124">PowerShell no longer reads the files `$pshome\*.ps1xml` -- these files have been converted to C# to avoid some file and CPU overhead of processing the XML files.</span></span> <span data-ttu-id="d151f-125">Die Dateien sind zur Unterstützung der parallelen Verwendung von Version 2 noch vorhanden. Wenn Sie also den Inhalt der Dateien ändern, hat dies keine Auswirkung auf Version 5, sondern nur auf Version 2.</span><span class="sxs-lookup"><span data-stu-id="d151f-125">The files still exist to support V2 side-by-side, so if you change the file contents, it will not have any effect to V5, only V2.</span></span> <span data-ttu-id="d151f-126">Beachten Sie, dass das Ändern dieser Dateien zu keiner Zeit ein unterstütztes Szenario war.</span><span class="sxs-lookup"><span data-stu-id="d151f-126">Note that changing the contents of these files was never a supported scenario.</span></span>

<span data-ttu-id="d151f-127">Eine andere sichtbare Änderung ist, wie PowerShell die exportierten Befehle und andere Informationen für Module zwischenspeichert, die auf einem System installiert sind.</span><span class="sxs-lookup"><span data-stu-id="d151f-127">Another visible change is how PowerShell caches the exported commands and other information for modules that are installed on a system.</span></span> <span data-ttu-id="d151f-128">Zuvor wurde dieser Cache im Verzeichnis `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d151f-128">Previously, this cache was stored in the directory `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis`.</span></span> <span data-ttu-id="d151f-129">In WMF 5.1 befindet sich der Cache ausschließlich in der Datei `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span><span class="sxs-lookup"><span data-stu-id="d151f-129">In WMF 5.1, the cache is a single file `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span> <span data-ttu-id="d151f-130">Unter [Die Datei „ModuleAnalysisCache“](release-notes.md#module-analysis-cache) finden Sie weitere Details.</span><span class="sxs-lookup"><span data-stu-id="d151f-130">See [Module Analysis Cache](release-notes.md#module-analysis-cache) for more details.</span></span>