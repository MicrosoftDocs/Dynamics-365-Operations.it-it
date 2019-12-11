---
title: Analisi di adeguatezza dell'ottimizzazione di pianificazione
description: Questo argomento spiega come verificare la configurazione e i dati correnti rispetto alle funzionalità della funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
manager: AnnBe
ms.date: 1030/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 26b067f8526df16474c0ab52d0abf816170ff5cb
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773990"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="planning-optimization-fit-analysis"></a><span data-ttu-id="dff52-103">Analisi di adeguatezza dell'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="dff52-103">Planning Optimization fit analysis</span></span>

<span data-ttu-id="dff52-104">Per visualizzare la compatibilità dell'impostazione e dei dati correnti rispetto alla funzionalità di ottimizzazione di pianificazione, passare a **Pianificazione generale** \> **Impostazione** \> **Analisi di adeguatezza dell'ottimizzazione di pianificazione** e selezionare **Esegui analisi**.</span><span class="sxs-lookup"><span data-stu-id="dff52-104">To see how compatible your current setup and data are with the Planning Optimization functionality, go to **Master planning** \> **Setup** \> **Planning Optimization fit analysis**, and then select **Run analysis**.</span></span> <span data-ttu-id="dff52-105">Se l'analisi rileva delle incoerenze, vengono elencate nella stessa pagina.</span><span class="sxs-lookup"><span data-stu-id="dff52-105">If the analysis finds any inconsistencies, they are listed on the same page.</span></span> <span data-ttu-id="dff52-106">L'esecuzione dell'analisi può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="dff52-106">(The analysis can take a few minutes to run.)</span></span>

> [!NOTE]
> <span data-ttu-id="dff52-107">In caso di incongruenze, sarà comunque possibile utilizzare l'ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="dff52-107">If inconsistencies are found, you can still use Planning Optimization.</span></span> <span data-ttu-id="dff52-108">I risultati dell'analisi di adeguatezza indicano le posizioni in cui il servizio di pianificazione non onorerà la configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="dff52-108">The results of the fit analysis just show places where the planning service won't honor your current setup.</span></span> <span data-ttu-id="dff52-109">Ciò significa che indicano le posizioni in cui i processi potrebbero essere ignorati o non essere supportati.</span><span class="sxs-lookup"><span data-stu-id="dff52-109">In other words, they show places where some processes might be ignored or might not be supported.</span></span>

## <a name="analysis-results-example-1"></a><span data-ttu-id="dff52-110">Risultati dell'analisi: Esempio 1</span><span class="sxs-lookup"><span data-stu-id="dff52-110">Analysis results: Example 1</span></span>

- <span data-ttu-id="dff52-111">**Funzionalità:** Produzione</span><span class="sxs-lookup"><span data-stu-id="dff52-111">**Feature:** Production</span></span>
- <span data-ttu-id="dff52-112">**Problema:** Articoli con livello DBA maggiore di zero: 56</span><span class="sxs-lookup"><span data-stu-id="dff52-112">**Issue:** Items with BOM level greater than zero: 56</span></span>
- <span data-ttu-id="dff52-113">**Descrizione:** L'analisi di adeguatezza ha rilevato 56 articoli con una distinta base (DBA) impostata per la produzione.</span><span class="sxs-lookup"><span data-stu-id="dff52-113">**Explanation:** The fit analysis found 56 items that have a bill of materials (BOM) setup for production.</span></span> <span data-ttu-id="dff52-114">Poiché l'attuale versione di ottimizzazione di pianificazione non supporta la produzione, ottimizzazione di pianificazione genera ordini fornitore pianificati anziché ordini di produzione pianificati.</span><span class="sxs-lookup"><span data-stu-id="dff52-114">Because the current version of Planning Optimization doesn't support production, Planning Optimization will generate planned purchase orders instead of planned production orders.</span></span> <span data-ttu-id="dff52-115">Mostra anche un avviso che elenca gli articoli interessati.</span><span class="sxs-lookup"><span data-stu-id="dff52-115">It will also show a warning that lists the affected items.</span></span>

### <a name="analysis-results-example-2"></a><span data-ttu-id="dff52-116">Risultati dell'analisi: Esempio 2</span><span class="sxs-lookup"><span data-stu-id="dff52-116">Analysis results: Example 2</span></span>

- <span data-ttu-id="dff52-117">**Funzionalità:** Azioni</span><span class="sxs-lookup"><span data-stu-id="dff52-117">**Feature:** Actions</span></span>
- <span data-ttu-id="dff52-118">**Problema:** Gruppi di copertura con calcolo delle azioni abilitato: 6</span><span class="sxs-lookup"><span data-stu-id="dff52-118">**Issue:** Coverage groups with actions calculation enabled: 6</span></span>
- <span data-ttu-id="dff52-119">**Descrizione:** L'analisi di adeguatezza ha rilevato sei gruppi di copertura in cui il calcolo dell'azione è abilitato.</span><span class="sxs-lookup"><span data-stu-id="dff52-119">**Explanation:** The fit analysis found six coverage groups where action calculation is turned on.</span></span> <span data-ttu-id="dff52-120">Poiché la versione corrente dell'ottimizzazione di pianificazione non supporta le azioni, non viene generata alcuna azione durante la pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="dff52-120">Because the current version of Planning Optimization doesn't support actions, no actions will be generated during master planning.</span></span>

## <a name="related-resources"></a><span data-ttu-id="dff52-121">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="dff52-121">Related resources</span></span>

[<span data-ttu-id="dff52-122">Panoramica dell'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="dff52-122">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="dff52-123">Introduzione all'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="dff52-123">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="dff52-124">Visualizzare la cronologia del piano e i log di pianificazione</span><span class="sxs-lookup"><span data-stu-id="dff52-124">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="dff52-125">Applicare i filtri a un piano</span><span class="sxs-lookup"><span data-stu-id="dff52-125">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="dff52-126">Annullare un processo di pianificazione</span><span class="sxs-lookup"><span data-stu-id="dff52-126">Cancel a planning job</span></span>](cancel-planning-job.md)