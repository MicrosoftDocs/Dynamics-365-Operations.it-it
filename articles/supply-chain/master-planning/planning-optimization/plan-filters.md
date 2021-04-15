---
title: Applicare i filtri a un piano
description: In questo argomento viene descritto come usare i filtri in un piano quando è utilizzata la funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 7b605f9826d2116f6f52a4b880f4fb5bd24cfdd0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813053"
---
# <a name="apply-filters-to-a-plan"></a><span data-ttu-id="dfed8-103">Applicare i filtri a un piano</span><span class="sxs-lookup"><span data-stu-id="dfed8-103">Apply filters to a plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dfed8-104">Quando la funzionalità di ottimizzazione di pianificazione viene utilizzata, è possibile applicare un filtro a un piano.</span><span class="sxs-lookup"><span data-stu-id="dfed8-104">When the Planning Optimization functionality is used, you can apply a filter to a plan.</span></span> <span data-ttu-id="dfed8-105">Il **filtro del piano** viene sempre applicato durante un'esecuzione di pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="dfed8-105">The **Plan filter** will always be applied during a master planning run.</span></span> <span data-ttu-id="dfed8-106">Un **filtro del piano** è utile quando si desidera limitare un piano a un gruppo specifico di articoli e assicurarsi che nessun altro elemento sia incluso come parte della pianificazione generale risultante.</span><span class="sxs-lookup"><span data-stu-id="dfed8-106">A **Plan filter** is useful when you want to limit a plan to a specific group of items and make sure that no other items are included as part of the resulting master planning.</span></span>

<span data-ttu-id="dfed8-107">Se viene applicato un **filtro del piano** e viene applicato anche un filtro del runtime durante l'esecuzione della pianificazione generale, nell'esecuzione della pianificazione viene inclusa solo l'intersezione dei due filtri.</span><span class="sxs-lookup"><span data-stu-id="dfed8-107">If a **Plan filter** is applied, and a runtime filter is also applied during the master planning run, only the intersection of the two filters is included in the planning run.</span></span>

<span data-ttu-id="dfed8-108">Il **filtro di piano** è accessibile da **Piani generali** quando viene utilizzata l'ottimizzazione della pianificazione.</span><span class="sxs-lookup"><span data-stu-id="dfed8-108">The **Plan filter** can be accessed from **Master plans** when Planning Optimization is used.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="dfed8-109">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="dfed8-109">Example scenario</span></span>

<span data-ttu-id="dfed8-110">Viene impostato un filtro del piano che include gli articoli A, B e C. Le esecuzioni della pianificazione principale vengono quindi eseguite per lo stesso piano, ma vengono applicati diversi filtri del runtime:</span><span class="sxs-lookup"><span data-stu-id="dfed8-110">A plan filter is set up that includes items A, B, and C. Master planning runs are then run for the same plan, but different runtime filters are applied:</span></span>

- <span data-ttu-id="dfed8-111">**Filtro del runtime che include l'articolo D:** Non sono previsti articoli, poiché non esiste intersezione tra il filtro del piano e il filtro del runtime.</span><span class="sxs-lookup"><span data-stu-id="dfed8-111">**Runtime filter that includes item D:** No items are planned, because there is no intersection between the plan filter and the runtime filter.</span></span>
- <span data-ttu-id="dfed8-112">**Filtro del runtime che include l'articolo A e D:** Nell'esecuzione della pianificazione è incluso solo l'articolo A, poiché l'articolo D non fa parte del filtro del piano.</span><span class="sxs-lookup"><span data-stu-id="dfed8-112">**Runtime filter that includes item A and D:** Only item A is included in the planning run, because item D isn't part of the plan filter.</span></span>
- <span data-ttu-id="dfed8-113">**Filtro del runtime che include l'articolo B:** Nell'esecuzione della pianificazione è incluso solo l'articolo B e viene mantenuto l'output di pianificazione precedente per l'articolo A.</span><span class="sxs-lookup"><span data-stu-id="dfed8-113">**Runtime filter that includes item B:** Only item B is included in the planning run, and the previous planning output for item A is kept.</span></span>
- <span data-ttu-id="dfed8-114">**Filtro del runtime che include tutti gli articoli (filtro vuoto):** Gli articoli A, B e C sono inclusi nell'esecuzione della pianificazione e l'output di pianificazione precedente per gli articoli A e B viene sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="dfed8-114">**Runtime filter that includes all items (blank filter):** Items A, B, and C are included in the planning run, and the previous planning output for items A and B is overwritten.</span></span>

> [!NOTE]
> <span data-ttu-id="dfed8-115">È necessario evitare di impostare un filtro del piano sul piano selezionato come **Piano generale dinamico corrente** nella pagina **Parametri di pianificazione generale**.</span><span class="sxs-lookup"><span data-stu-id="dfed8-115">You should avoid setting a plan filter on the plan that is selected as **Current dynamic master plan** on the **Master planning parameters** page.</span></span> <span data-ttu-id="dfed8-116">In caso contrario, la funzionalità del piano principale dinamico è limitata agli articoli filtrati.</span><span class="sxs-lookup"><span data-stu-id="dfed8-116">Otherwise, the dynamic master plan functionality will be limited to the filtered items.</span></span> <span data-ttu-id="dfed8-117">Ad esempio, se i requisiti netti vengono aggiornati per un articolo che non fa parte del filtro del piano, non verrà generato alcun risultato.</span><span class="sxs-lookup"><span data-stu-id="dfed8-117">For example, if the net requirements are updated for an item that isn't part of the plan filter, no result will be generated.</span></span>

## <a name="related-resources"></a><span data-ttu-id="dfed8-118">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="dfed8-118">Related resources</span></span>

[<span data-ttu-id="dfed8-119">Panoramica dell'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="dfed8-119">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="dfed8-120">Introduzione all'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="dfed8-120">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="dfed8-121">Analisi di adeguatezza dell'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="dfed8-121">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="dfed8-122">Visualizzare la cronologia del piano e i log di pianificazione</span><span class="sxs-lookup"><span data-stu-id="dfed8-122">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="dfed8-123">Annullare un processo di pianificazione</span><span class="sxs-lookup"><span data-stu-id="dfed8-123">Cancel a planning job</span></span>](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]