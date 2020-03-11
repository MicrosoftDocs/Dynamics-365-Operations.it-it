---
title: Pianificazione con quantità disponibili negative
description: Questo argomento spiega come vengono gestite le quantità disponibili negative quando si utilizza l'ottimizzazione della pianificazione.
author: ChristianRytt
manager: AnnBe
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: ca12d13f7318f649cb1dbc0f7c3cf56502c9d3ea
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "3077486"
---
# <a name="planning-with-negative-on-hand-quantities"></a><span data-ttu-id="77362-103">Pianificazione con quantità disponibili negative</span><span class="sxs-lookup"><span data-stu-id="77362-103">Planning with negative on-hand quantities</span></span>

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="77362-104">Se il sistema mostra una quantità aggregata disponibile negativa, il motore di pianificazione considera la quantità come 0 (zero) per evitare un eccesso di offerta.</span><span class="sxs-lookup"><span data-stu-id="77362-104">If the system shows a negative aggregate on-hand quantity, the planning engine treats the quantity as 0 (zero) to help avoid over-supply.</span></span> <span data-ttu-id="77362-105">Ecco come funziona questa funzionalità:</span><span class="sxs-lookup"><span data-stu-id="77362-105">Here is how this functionality works:</span></span>

1. <span data-ttu-id="77362-106">La funzione di ottimizzazione della pianificazione aggrega le quantità disponibile al livello più basso delle dimensioni di copertura.</span><span class="sxs-lookup"><span data-stu-id="77362-106">The planning optimization feature aggregates on-hand quantities at the lowest level of coverage dimensions.</span></span> <span data-ttu-id="77362-107">(Ad esempio, se *Ubicazione* non è una dimensione di copertura, la pianificazione dell'ottimizzazione aggrega le quantità disponibile a livello di *magazzino*.)</span><span class="sxs-lookup"><span data-stu-id="77362-107">(For example, if *location* isn't a coverage dimension, planning optimization aggregates on-hand quantities at the *warehouse* level.)</span></span>
1. <span data-ttu-id="77362-108">Se la quantità disponibile aggregata al livello più basso delle dimensioni di copertura è negativa, il sistema presuppone che la quantità disponibile sia effettivamente 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="77362-108">If the aggregate on-hand quantity at the lowest level of coverage dimensions is negative, the system assumes that the on-hand quantity is really 0 (zero).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77362-109">Il sistema di pianificazione può essere preciso solo parimenti ai dati di input.</span><span class="sxs-lookup"><span data-stu-id="77362-109">The planning system can be only as precise as the input data.</span></span> <span data-ttu-id="77362-110">Se i dati di input non sono accurati, i record con quantità disponibili negative indicano che le informazioni sulle scorte in Microsoft Dynamics 365 Supply Chain Management non sono sincronizzate con il mondo reale.</span><span class="sxs-lookup"><span data-stu-id="77362-110">If the input data is inaccurate, negative on-hand records will indicate that the inventory information in Microsoft Dynamics 365 Supply Chain Management is out of sync with the real world.</span></span> <span data-ttu-id="77362-111">Pertanto, il risultato della pianificazione sarà imperfetto.</span><span class="sxs-lookup"><span data-stu-id="77362-111">Therefore, the planning result will be flawed.</span></span> <span data-ttu-id="77362-112">Per ottenere un risultato di pianificazione preciso, è necessario ridurre al minimo il numero di record che mostrano una quantità disponibile negativa.</span><span class="sxs-lookup"><span data-stu-id="77362-112">To get a precise planning result, you should minimize the number of records that show a negative on-hand quantity.</span></span>

## <a name="example-1"></a><span data-ttu-id="77362-113">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="77362-113">Example 1</span></span>

<span data-ttu-id="77362-114">Il magazzino 13 è configurato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="77362-114">Warehouse 13 is configured in the following manner:</span></span>

- <span data-ttu-id="77362-115">**Codice di copertura:** Min/Max</span><span class="sxs-lookup"><span data-stu-id="77362-115">**Coverage code:** Min./Max.</span></span>
- <span data-ttu-id="77362-116">**Minimo:** 15 pezzi (pz.)</span><span class="sxs-lookup"><span data-stu-id="77362-116">**Minimum:** 15 pieces (pcs.)</span></span>
- <span data-ttu-id="77362-117">**Massimo:** 25 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-117">**Maximum:** 25 pcs.</span></span>

<span data-ttu-id="77362-118">Il livello più basso di dimensioni di copertura è *magazzino* e le seguenti quantità disponibili sono registrate presso il livello *ubicazione*:</span><span class="sxs-lookup"><span data-stu-id="77362-118">The lowest level of coverage dimensions is *warehouse*, and the following on-hand quantities are recorded at the *location* level:</span></span>

- <span data-ttu-id="77362-119">**Sito 1, magazzino 13, ubicazione 1:** 20 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-119">**Site 1, warehouse 13, location 1:** 20 pcs.</span></span>
- <span data-ttu-id="77362-120">**Sito 1, magazzino 13, ubicazione 2:** &minus;8 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-120">**Site 1 warehouse 13, location 2:** &minus;8 pcs.</span></span>

<span data-ttu-id="77362-121">Pertanto, la quantità disponibile aggregata per il magazzino 13 è di 12 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-121">Therefore, the aggregate on-hand quantity for warehouse 13 is 12 pcs.</span></span> <span data-ttu-id="77362-122">(= 20 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-122">(= 20 pcs.</span></span> <span data-ttu-id="77362-123">&minus; 8 pz.).</span><span class="sxs-lookup"><span data-stu-id="77362-123">&minus; 8 pcs.).</span></span>

<span data-ttu-id="77362-124">In questo caso, il motore di pianificazione utilizza una quantità disponibile aggregata di 12 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-124">In this case, the planning engine uses an aggregate on-hand quantity of 12 pcs.</span></span> <span data-ttu-id="77362-125">per il magazzino 13.</span><span class="sxs-lookup"><span data-stu-id="77362-125">for warehouse 13.</span></span>

<span data-ttu-id="77362-126">Il risultato è un ordine pianificato di 13 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-126">The result is a planned order of 13 pcs.</span></span> <span data-ttu-id="77362-127">(= 25 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-127">(= 25 pcs.</span></span> <span data-ttu-id="77362-128">&minus; 12 pz.) per ricaricare il magazzino 13 da 12 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-128">&minus; 12 pcs.) to refill warehouse 13 from 12 pcs.</span></span> <span data-ttu-id="77362-129">a 25 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-129">to 25 pcs.</span></span>

## <a name="example-2"></a><span data-ttu-id="77362-130">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="77362-130">Example 2</span></span>

<span data-ttu-id="77362-131">Il magazzino 13 è configurato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="77362-131">Warehouse 13 is configured in the following manner:</span></span>

- <span data-ttu-id="77362-132">**Codice di copertura:** Min/Max</span><span class="sxs-lookup"><span data-stu-id="77362-132">**Coverage code:** Min./Max.</span></span>
- <span data-ttu-id="77362-133">**Minimo:** 15 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-133">**Minimum:** 15 pcs.</span></span>
- <span data-ttu-id="77362-134">**Massimo:** 25 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-134">**Maximum:** 25 pcs.</span></span>

<span data-ttu-id="77362-135">Il livello più basso di dimensioni di copertura è *magazzino* e le seguenti quantità disponibili sono registrate presso il livello *ubicazione*:</span><span class="sxs-lookup"><span data-stu-id="77362-135">The lowest level of coverage dimensions is *warehouse*, and the following on-hand quantities are recorded at the *location* level:</span></span>

- <span data-ttu-id="77362-136">**Sito 1, magazzino 13, ubicazione 1:** 4 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-136">**Site 1, warehouse 13, location 1:** 4 pcs.</span></span>
- <span data-ttu-id="77362-137">**Sito 1, magazzino 13, ubicazione 2:** &minus;8 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-137">**Site 1 warehouse 13, location 2:** &minus;8 pcs.</span></span>

<span data-ttu-id="77362-138">Pertanto, la quantità disponibile aggregata per il magazzino 13 è di &minus;4 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-138">Therefore, the aggregate on-hand quantity for warehouse 13 is &minus;4 pcs.</span></span> <span data-ttu-id="77362-139">(= 4 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-139">(= 4 pcs.</span></span> <span data-ttu-id="77362-140">&minus; 8 pz.).</span><span class="sxs-lookup"><span data-stu-id="77362-140">&minus; 8 pcs.).</span></span> <span data-ttu-id="77362-141">In altre parole, è inferiore a 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="77362-141">In other words, it's less than 0 (zero).</span></span>

<span data-ttu-id="77362-142">In questo caso, il motore di pianificazione presuppone che la quantità disponibile per il magazzino 13 sia 0 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-142">In this case, the planning engine assumes that the on-hand quantity for warehouse 13 is 0 pcs.</span></span> <span data-ttu-id="77362-143">anziché &minus;4 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-143">instead of &minus;4 pcs.</span></span>

<span data-ttu-id="77362-144">Il risultato è un ordine pianificato di 25 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-144">The result is a planned order of 25 pcs.</span></span> <span data-ttu-id="77362-145">(= 25 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-145">(= 25 pcs.</span></span> <span data-ttu-id="77362-146">&minus; 0 pz.) per ricaricare il magazzino 13 da 0 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-146">&minus; 0 pcs.) to refill warehouse 13 from 0 pcs.</span></span> <span data-ttu-id="77362-147">a 25 pz.</span><span class="sxs-lookup"><span data-stu-id="77362-147">to 25 pcs.</span></span>

## <a name="related-resources"></a><span data-ttu-id="77362-148">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="77362-148">Related resources</span></span>

[<span data-ttu-id="77362-149">Panoramica sull'ottimizzazione della pianificazione</span><span class="sxs-lookup"><span data-stu-id="77362-149">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="77362-150">Introduzione all'ottimizzazione della pianificazione</span><span class="sxs-lookup"><span data-stu-id="77362-150">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="77362-151">Analisi di adeguatezza dell'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="77362-151">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="77362-152">Visualizzare la cronologia del piano e i log di pianificazione</span><span class="sxs-lookup"><span data-stu-id="77362-152">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="77362-153">Annullare un processo di pianificazione</span><span class="sxs-lookup"><span data-stu-id="77362-153">Cancel a planning job</span></span>](cancel-planning-job.md)
