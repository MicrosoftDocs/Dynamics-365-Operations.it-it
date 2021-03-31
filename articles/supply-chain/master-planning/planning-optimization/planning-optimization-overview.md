---
title: Panoramica dell'ottimizzazione di pianificazione
description: Questo argomento fornisce una panoramica della funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
manager: tfehr
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: cf64c3dea6fe08c36388f5f7147795221cf85b8a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5224477"
---
# <a name="planning-optimization-overview"></a><span data-ttu-id="8e8ea-103">Panoramica dell'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="8e8ea-103">Planning Optimization overview</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8e8ea-104">Il componente aggiuntivo di ottimizzazione della pianificazione per Microsoft Dynamics 365 Supply Chain Management consente il calcolo della pianificazione principale al di fuori di Dynamics 365 Supply Chain Management e del relativo database SQL.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-104">The Planning Optimization Add-in for Microsoft Dynamics 365 Supply Chain Management enables master planning calculation to occur outside Dynamics 365 Supply Chain Management and the related SQL database.</span></span> <span data-ttu-id="8e8ea-105">I vantaggi associati alla funzionalità di ottimizzazione di pianificazione includono prestazioni migliorate e un impatto minimo sul database SQL durante le esecuzioni della pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-105">The benefits that are associated with the Planning Optimization functionality include improved performance and minimal impact on SQL database during master planning runs.</span></span> <span data-ttu-id="8e8ea-106">Le esecuzioni di pianificazione rapide possono essere eseguite anche durante le ore d'ufficio, in modo che i pianificatori possano reagire immediatamente alla modifica della domanda o dei parametri.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-106">Quick planning runs can be done even during office hours, so that planners can immediately react to demand or parameter changes.</span></span>

<span data-ttu-id="8e8ea-107">Per utilizzare l'ottimizzazione di pianificazione, è necessario installare il componente aggiuntivo di ottimizzazione della pianificazione dal progetto in Microsoft Dynamics Lifecycle Services (LCS) e attivare la funzionalità di ottimizzazione di pianificazione in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-107">To use Planning Optimization, you must install the Planning Optimization Add-in from your project in Microsoft Dynamics Lifecycle Services (LCS) and turn on the Planning Optimization functionality in Supply Chain Management.</span></span> <span data-ttu-id="8e8ea-108">Per ulteriori informazioni, vedere [Introduzione all'ottimizzazione di pianificazione](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="8e8ea-108">For more information, see [Get started with Planning Optimization](get-started.md).</span></span>

<span data-ttu-id="8e8ea-109">La seguente illustrazione mostra il vantaggio di eseguire l'ottimizzazione di pianificazione durante l'orario di ufficio.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-109">The following illustration shows the advantage of running Planning Optimization during office hours.</span></span>

![Vantaggio dell'esecuzione dell'ottimizzazione di pianificazione durante l'orario di ufficio](media/PlanningOptimization1.png)

## <a name="improved-performance"></a><span data-ttu-id="8e8ea-111">Prestazioni migliorate</span><span class="sxs-lookup"><span data-stu-id="8e8ea-111">Improved performance</span></span>

<span data-ttu-id="8e8ea-112">L'ottimizzazione di pianificazione può essere utilizzata negli scenari che includono i piani generali a esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-112">Planning Optimization can be used in scenarios that involve long-running master plans.</span></span> <span data-ttu-id="8e8ea-113">È specificamente progettata per calcoli molto veloci che coinvolgono volumi di dati molto grandi.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-113">It's specifically designed for very fast calculations that involve very large volumes of data.</span></span> <span data-ttu-id="8e8ea-114">Poiché è concepita come un servizio multi-tenant iperscalabile, più istanze possono lavorare contemporaneamente per calcolare il piano.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-114">Because it's built as a hyper-scalable multitenant service, multiple instances can work together simultaneously to calculate the plan.</span></span> <span data-ttu-id="8e8ea-115">Inoltre, il servizio di pianificazione rimuove il carico della pianificazione generale dal sistema e funziona con un flusso di dati che riduce al minimo il carico del server.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-115">Additionally, the planning service removes the load of master planning from your system and works with a data stream that minimizes the server load.</span></span>

<span data-ttu-id="8e8ea-116">L'ottimizzazione di pianificazione consente di raggiungere i seguenti obiettivi:</span><span class="sxs-lookup"><span data-stu-id="8e8ea-116">Planning Optimization can help you achieve the following goals:</span></span>

- <span data-ttu-id="8e8ea-117">Migliorare le prestazioni di pianificazione con un tempo di esecuzione più breve.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-117">Improve planning performance through a shorter runtime.</span></span>
- <span data-ttu-id="8e8ea-118">Ridurre l'impatto su altri processi durante l'esecuzione della pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-118">Reduce the impact on other processes during the master planning run.</span></span>
- <span data-ttu-id="8e8ea-119">Avviare esecuzioni di pianificazione più frequenti.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-119">Do more frequent planning runs.</span></span> <span data-ttu-id="8e8ea-120">Non c'è limite alle esecuzioni giornaliere.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-120">(You aren't limited to daily runs.)</span></span>
- <span data-ttu-id="8e8ea-121">Essere sicuri che la crescita futura dell'azienda non sovraccaricherà il sistema di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-121">Be confident that future business growth won't overload the planning system.</span></span>

## <a name="architecture-and-data-flow"></a><span data-ttu-id="8e8ea-122">Architettura e flusso di dati</span><span class="sxs-lookup"><span data-stu-id="8e8ea-122">Architecture and data flow</span></span>

<span data-ttu-id="8e8ea-123">Quando il componente aggiuntivo di ottimizzazione di pianificazione viene installato da LCS, viene stabilita una connessione sicura al servizio di ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-123">When the Planning Optimization Add-in is installed from LCS, a secure connection to the Planning Optimization service is established.</span></span> <span data-ttu-id="8e8ea-124">Il servizio si trova nello stesso paese del data center dell'istanza di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-124">The service is located in the same data center country or region as the related Supply Chain Management instance.</span></span> <span data-ttu-id="8e8ea-125">Dopo aver impostato l'ottimizzazione di pianificazione, quando viene eseguita la pianificazione generale, i dati principali e i dati transazionali vengono inviati da Supply Chain Management al servizio di ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-125">After Planning Optimization is set up, when master planning is run, master data and transactional data are sent from Supply Chain Management to the Planning Optimization service.</span></span>

<span data-ttu-id="8e8ea-126">Se il componente aggiuntivo ottimizzazione di pianificazione viene disinstallato, tutti i dati correlati nel servizio ottimizzazione di pianificazione vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-126">If the Planning Optimization Add-in is uninstalled, all related data in the Planning Optimization service is removed.</span></span>

### <a name="high-level-data-flow-for-regeneration-runs"></a><span data-ttu-id="8e8ea-127">Flusso di dati di alto livello per le esecuzioni di rigenerazione</span><span class="sxs-lookup"><span data-stu-id="8e8ea-127">High-level data flow for regeneration runs</span></span>

1. <span data-ttu-id="8e8ea-128">Il client di Supply Chain Management invia un segnale per richiedere l'esecuzione di una pianificazione dall'ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-128">The Supply Chain Management client sends a signal to request a planning run from Planning Optimization.</span></span>
2. <span data-ttu-id="8e8ea-129">L'ottimizzazione di pianificazione richiede i dati necessari tramite il connettore integrato.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-129">Planning Optimization requests the required data via the integrated connector.</span></span>
3. <span data-ttu-id="8e8ea-130">Il database SQL invia le informazioni richieste sui dati di installazione, master e transazionali all'ottimizzazione di pianificazione tramite il connettore.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-130">The SQL database sends the requested information about setup, master, and transactional data to Planning Optimization via the connector.</span></span> <span data-ttu-id="8e8ea-131">Il connettore traduce le informazioni tra Supply Chain Management e il servizio di ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-131">The connector translates information between Supply Chain Management and the Planning Optimization service.</span></span>
4. <span data-ttu-id="8e8ea-132">Il servizio di ottimizzazione di pianificazione conserva in memoria i dati relativi alla pianificazione ed esegue i calcoli richiesti.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-132">The Planning Optimization service holds planning-related data in memory and does the required calculations.</span></span>
5. <span data-ttu-id="8e8ea-133">Il risultato della pianificazione viene inviato al database di Supply Chain Management tramite il connettore.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-133">The planning result is sent to the Supply Chain Management database via the connector.</span></span> <span data-ttu-id="8e8ea-134">I risultati includono informazioni come ordini pianificati e informazioni di pegging.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-134">The results include information such as planned orders and pegging information.</span></span> <span data-ttu-id="8e8ea-135">L'ottimizzazione di pianificazione invia un segnale a Supply Chain Management per indicare che l'esecuzione di pianificazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-135">Planning Optimization sends a signal to Supply Chain Management to indicate that the planning run has been completed.</span></span> <span data-ttu-id="8e8ea-136">Invia inoltre eventuali messaggi e avvisi pertinenti.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-136">It also sends any relevant messages and warnings.</span></span>

<span data-ttu-id="8e8ea-137">L'illustrazione seguente mostra il flusso dei dati.</span><span class="sxs-lookup"><span data-stu-id="8e8ea-137">The following illustration shows the data flow.</span></span>

![Flusso di dati per le esecuzioni di rigenerazione](media/PlanningOptimization2.png)

## <a name="related-resources"></a><span data-ttu-id="8e8ea-139">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="8e8ea-139">Related resources</span></span>

[<span data-ttu-id="8e8ea-140">Introduzione all'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="8e8ea-140">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="8e8ea-141">Analisi di adeguatezza dell'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="8e8ea-141">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="8e8ea-142">Visualizzare la cronologia del piano e i log di pianificazione</span><span class="sxs-lookup"><span data-stu-id="8e8ea-142">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="8e8ea-143">Applicare i filtri a un piano</span><span class="sxs-lookup"><span data-stu-id="8e8ea-143">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="8e8ea-144">Annullare un processo di pianificazione</span><span class="sxs-lookup"><span data-stu-id="8e8ea-144">Cancel a planning job</span></span>](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]