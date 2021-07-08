---
title: Tolleranza di ritardo (giorni negativi)
description: Questo argomento fornisce informazioni sul calcolo della tolleranza di ritardo e su come influisce sulla creazione degli ordini pianificati in Ottimizzazione pianificazione.
author: crytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 748e047e89747f2eabccc04a40c79bcb1e6f3dea
ms.sourcegitcommit: f21659f1c23bc2cd65bbe7fb7210910d5a8e1cb9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306465"
---
# <a name="delay-tolerance-negative-days"></a><span data-ttu-id="9ccea-103">Tolleranza di ritardo (giorni negativi)</span><span class="sxs-lookup"><span data-stu-id="9ccea-103">Delay tolerance (negative days)</span></span>

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="9ccea-104">La funzionalità di tolleranza al ritardo consente a Ottimizzazione pianificazione di considerare il valore **Giorni negativi** impostato per i gruppi di copertura.</span><span class="sxs-lookup"><span data-stu-id="9ccea-104">The delay tolerance functionality enables Planning Optimization to consider the **Negative days** value that is set for coverage groups.</span></span> <span data-ttu-id="9ccea-105">Viene utilizzata per estendere il periodo di tolleranza di ritardo applicato durante la pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="9ccea-105">It's used to extend the delay tolerance period that is applied during master planning.</span></span> <span data-ttu-id="9ccea-106">In questo modo, è possibile evitare di creare nuovi ordini di fornitura se la fornitura esistente è in grado di coprire la domanda con un breve ritardo.</span><span class="sxs-lookup"><span data-stu-id="9ccea-106">In this way, you can avoid creating new supply orders if existing supply will be able to cover the demand after a short delay.</span></span> <span data-ttu-id="9ccea-107">Lo scopo della funzionalità è determinare se ha senso creare un nuovo ordine di fornitura per una determinata domanda.</span><span class="sxs-lookup"><span data-stu-id="9ccea-107">The purpose of the functionality is to determine whether it makes sense to create a new supply order for a given demand.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="9ccea-108">Attiva la funzionalità nel tuo sistema</span><span class="sxs-lookup"><span data-stu-id="9ccea-108">Turn on the feature in your system</span></span>

<span data-ttu-id="9ccea-109">Per rendere disponibile la funzionalità di tolleranza di ritardo nel sistema, andare a [Gestione funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e attiva la funzionalità *Giorni negativi per l'ottimizzazione della pianificazione*.</span><span class="sxs-lookup"><span data-stu-id="9ccea-109">To make the delay tolerance functionality available in your system, go to [Feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Negative days for Planning Optimization* feature.</span></span>

## <a name="delay-tolerance-in-planning-optimization"></a><span data-ttu-id="9ccea-110">Tolleranza di ritardo nell'ottimizzazione della pianificazione</span><span class="sxs-lookup"><span data-stu-id="9ccea-110">Delay tolerance in Planning Optimization</span></span>

<span data-ttu-id="9ccea-111">La tolleranza di ritardo rappresenta il numero di giorni oltre il lead time che si è disposti ad aspettare prima di ordinare un nuovo rifornimento quando la fornitura esistente è già pianificata.</span><span class="sxs-lookup"><span data-stu-id="9ccea-111">Delay tolerance represents the number of days beyond the lead time that you're willing to wait before you order new replenishment when existing supply is already planned.</span></span> <span data-ttu-id="9ccea-112">La tolleranza al ritardo viene definita utilizzando i giorni di calendario, non i giorni lavorativi.</span><span class="sxs-lookup"><span data-stu-id="9ccea-112">Delay tolerance is defined by using calendar days, not business days.</span></span>

<span data-ttu-id="9ccea-113">Al momento della pianificazione generale, quando il sistema calcola la tolleranza di ritardo, considera l'impostazione **Giorni negativi**.</span><span class="sxs-lookup"><span data-stu-id="9ccea-113">At the time of master planning, when the system calculates the delay tolerance, it considers the **Negative days** setting.</span></span> <span data-ttu-id="9ccea-114">È possibile impostare il valore **Giorni negativi** nella pagina **Gruppi di copertura** o nella pagina **Copertura articoli**.</span><span class="sxs-lookup"><span data-stu-id="9ccea-114">You can set the **Negative days** value on either the **Coverage groups** page or the **Item coverage** page.</span></span>

<span data-ttu-id="9ccea-115">Il sistema collega il calcolo della tolleranza di ritardo alla *prima data di rifornimento*, che equivale alla data corrente più il lead time.</span><span class="sxs-lookup"><span data-stu-id="9ccea-115">The system links the delay tolerance calculation to the *earliest replenishment date*, which equals today's date plus the lead time.</span></span> <span data-ttu-id="9ccea-116">La tolleranza di ritardo viene calcolata utilizzando la seguente formula, dove *max()* trova il maggiore tra due valori:</span><span class="sxs-lookup"><span data-stu-id="9ccea-116">The delay tolerance is calculated by using following formula, where *max()* finds the larger of two values:</span></span>

<span data-ttu-id="9ccea-117">*max(prima data di rifornimento, data di scadenza della domanda)* – *Data di scadenza della domanda* + *Giorni negativi*</span><span class="sxs-lookup"><span data-stu-id="9ccea-117">*max(Earliest replenishment date, Demand due date)* – *Demand due date* + *Negative days*</span></span>

<span data-ttu-id="9ccea-118">Questa formula garantisce che la pianificazione generale non crei nuovi ordini di fornitura quando esiste una fornitura sufficiente durante il lead time del prodotto.</span><span class="sxs-lookup"><span data-stu-id="9ccea-118">This formula ensures that master planning doesn't create new supply orders when enough supply exists during the product lead time.</span></span>

> [!NOTE]
> <span data-ttu-id="9ccea-119">Il calcolo della tolleranza di ritardo in Ottimizzazione pianificazione utilizza sempre il calcolo dinamico dei giorni negativi dalla pianificazione generale incorporata.</span><span class="sxs-lookup"><span data-stu-id="9ccea-119">The delay tolerance calculation in Planning Optimization always uses the dynamic negative days calculation from built-in master planning.</span></span> <span data-ttu-id="9ccea-120">L'impostazione **Usa giorni negativi dinamici** nella pagina **Parametri di pianificazione generale** non ha alcun effetto su questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="9ccea-120">The **Use dynamic negative days** setting on the **Master planning parameters** page has no effect on this behavior.</span></span>

<span data-ttu-id="9ccea-121">Se la fornitura esistente implica un ritardo della domanda inferiore o uguale alla tolleranza di ritardo calcolata, l'ottimizzazione della pianificazione associa la fornitura esistente alla domanda.</span><span class="sxs-lookup"><span data-stu-id="9ccea-121">If the existing supply implies a demand delay that is less than or equal to the calculated delay tolerance, Planning Optimization pegs existing supply with the demand.</span></span> <span data-ttu-id="9ccea-122">In alcuni casi, è meglio ritardare la domanda piuttosto che finire con un eccesso di offerta.</span><span class="sxs-lookup"><span data-stu-id="9ccea-122">In some cases, it's better to delay the demand than to end up with oversupply.</span></span>

<span data-ttu-id="9ccea-123">Le seguenti sottosezioni forniscono esempi che mostrano come la tolleranza di ritardo influisca sulla creazione di ordini pianificati in Ottimizzazione pianificazione.</span><span class="sxs-lookup"><span data-stu-id="9ccea-123">The following subsections provide examples that show how delay tolerance affects the creation of planned orders in Planning Optimization.</span></span>

### <a name="example-1"></a><span data-ttu-id="9ccea-124">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="9ccea-124">Example 1</span></span>

<span data-ttu-id="9ccea-125">Un prodotto ha la seguente configurazione:</span><span class="sxs-lookup"><span data-stu-id="9ccea-125">A product has the following configuration:</span></span>

- <span data-ttu-id="9ccea-126">**Lead time:** *10*</span><span class="sxs-lookup"><span data-stu-id="9ccea-126">**Lead time:** *10*</span></span>
- <span data-ttu-id="9ccea-127">**Giorni negativi:** *2*</span><span class="sxs-lookup"><span data-stu-id="9ccea-127">**Negative days:** *2*</span></span>

<span data-ttu-id="9ccea-128">Per il prodotto esistono la domanda e l'offerta seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ccea-128">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="9ccea-129">**Domanda per oggi:** Un ordine di vendita per una quantità di 10</span><span class="sxs-lookup"><span data-stu-id="9ccea-129">**Demand for today:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="9ccea-130">**Fornitura in 12 giorni:** Un ordine di acquisto per una quantità di 10</span><span class="sxs-lookup"><span data-stu-id="9ccea-130">**Supply in 12 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="9ccea-131">La fornitura esistente può coprire la domanda entro 12 giorni e tale periodo equivale alla tolleranza di ritardo.</span><span class="sxs-lookup"><span data-stu-id="9ccea-131">Existing supply can cover the demand within 12 days, and that period equals the delay tolerance.</span></span> <span data-ttu-id="9ccea-132">Pertanto, quando viene eseguita la pianificazione generale, non vengono creati ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="9ccea-132">Therefore, when master planning runs, no planned orders are created.</span></span>

### <a name="example-2"></a><span data-ttu-id="9ccea-133">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="9ccea-133">Example 2</span></span>

<span data-ttu-id="9ccea-134">Un prodotto ha la seguente configurazione:</span><span class="sxs-lookup"><span data-stu-id="9ccea-134">A product has the following configuration:</span></span>

- <span data-ttu-id="9ccea-135">**Lead time:** *10*</span><span class="sxs-lookup"><span data-stu-id="9ccea-135">**Lead time:** *10*</span></span>
- <span data-ttu-id="9ccea-136">**Giorni negativi:** *0*</span><span class="sxs-lookup"><span data-stu-id="9ccea-136">**Negative days:** *0*</span></span>

<span data-ttu-id="9ccea-137">Per il prodotto esistono la domanda e l'offerta seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ccea-137">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="9ccea-138">**Domanda per oggi:** Un ordine di vendita per una quantità di 10</span><span class="sxs-lookup"><span data-stu-id="9ccea-138">**Demand for today:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="9ccea-139">**Fornitura in 12 giorni:** Un ordine di acquisto per una quantità di 10</span><span class="sxs-lookup"><span data-stu-id="9ccea-139">**Supply in 12 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="9ccea-140">L'offerta esistente può coprire la domanda solo dopo 12 giorni.</span><span class="sxs-lookup"><span data-stu-id="9ccea-140">Existing supply can cover the demand only after 12 days.</span></span> <span data-ttu-id="9ccea-141">Tuttavia, la tolleranza di ritardo è di 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="9ccea-141">However, the delay tolerance is 10 days.</span></span> <span data-ttu-id="9ccea-142">Pertanto, quando viene eseguita la pianificazione generale, viene creato un ordine pianificato per una quantità pari a 10.</span><span class="sxs-lookup"><span data-stu-id="9ccea-142">Therefore, when master planning runs, a planned order for a quantity of 10 is created.</span></span>

### <a name="example-3"></a><span data-ttu-id="9ccea-143">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="9ccea-143">Example 3</span></span>

<span data-ttu-id="9ccea-144">Un prodotto ha la seguente configurazione:</span><span class="sxs-lookup"><span data-stu-id="9ccea-144">A product has the following configuration:</span></span>

- <span data-ttu-id="9ccea-145">**Lead time:** *10*</span><span class="sxs-lookup"><span data-stu-id="9ccea-145">**Lead time:** *10*</span></span>
- <span data-ttu-id="9ccea-146">**Giorni negativi:** *2*</span><span class="sxs-lookup"><span data-stu-id="9ccea-146">**Negative days:** *2*</span></span>

<span data-ttu-id="9ccea-147">Per il prodotto esistono la domanda e l'offerta seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ccea-147">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="9ccea-148">**Domanda tra 11 giorni oggi:** Un ordine di vendita per una quantità di 10</span><span class="sxs-lookup"><span data-stu-id="9ccea-148">**Demand in 11 days:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="9ccea-149">**Fornitura in 14 giorni:** Un ordine di acquisto per una quantità di 10</span><span class="sxs-lookup"><span data-stu-id="9ccea-149">**Supply in 14 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="9ccea-150">L'offerta esistente può coprire la domanda solo dopo tre giorni.</span><span class="sxs-lookup"><span data-stu-id="9ccea-150">Existing supply can cover the demand only after three days.</span></span> <span data-ttu-id="9ccea-151">Tuttavia, la tolleranza di ritardo è di due giorni.</span><span class="sxs-lookup"><span data-stu-id="9ccea-151">However, the delay tolerance is two days.</span></span> <span data-ttu-id="9ccea-152">In questo caso, la tolleranza di ritardo include solo i due giorni negativi.</span><span class="sxs-lookup"><span data-stu-id="9ccea-152">(In this case, the delay tolerance includes only the two negative days.</span></span> <span data-ttu-id="9ccea-153">La data della domanda non è inclusa perché è successiva al lead time del prodotto. Pertanto, quando viene eseguita la pianificazione generale, viene creato un ordine pianificato per una quantità pari a 10.</span><span class="sxs-lookup"><span data-stu-id="9ccea-153">The demand date isn't included because it's after the product lead time.) Therefore, when master planning runs, a planned order for a quantity of 10 is created.</span></span>
