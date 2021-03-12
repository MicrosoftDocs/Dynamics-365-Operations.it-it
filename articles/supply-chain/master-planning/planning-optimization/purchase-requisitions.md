---
title: Richieste di acquisto
description: In questo argomento viene descritto come le richieste di acquisto sono supportate in Ottimizzazione pianificazione.
author: ChristianRytt
manager: tfehr
ms.date: 01/04/2021
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
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8075f8d7c3868c6d6012edbce17dbbb4749209ab
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992346"
---
# <a name="purchase-requisitions"></a><span data-ttu-id="9726e-103">Richieste di acquisto</span><span class="sxs-lookup"><span data-stu-id="9726e-103">Purchase requisitions</span></span>

<span data-ttu-id="9726e-104">La pianificazione generale può rifornire le richieste di acquisto approvate.</span><span class="sxs-lookup"><span data-stu-id="9726e-104">Master planning can replenish approved purchase requisitions.</span></span> <span data-ttu-id="9726e-105">Pertanto, per coprire le richieste di acquisto, gli utenti non devono utilizzare un flusso di lavoro per creare ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="9726e-105">Therefore, to cover purchase requisitions, users don't have to use a workflow to create purchase orders.</span></span> <span data-ttu-id="9726e-106">Invece, le richieste di acquisto possono essere coperte dalla pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="9726e-106">Instead, purchase requisitions can be covered by master planning.</span></span> <span data-ttu-id="9726e-107">Grazie a questa funzionalità, una richiesta di acquisto può produrre un ordine fornitore, un ordine di trasferimento o un ordine di produzione, a seconda del valore **Tipo di ordine pianificato** impostato per il prodotto correlato.</span><span class="sxs-lookup"><span data-stu-id="9726e-107">Because of this functionality, a purchase requisition can produce a purchase order, a transfer order, or a production order, depending on the **Planned order type** value that is set for the related product.</span></span>

## <a name="enable-master-plans-to-include-requisitions"></a><span data-ttu-id="9726e-108">Abilitare i piani generali per includere le richieste</span><span class="sxs-lookup"><span data-stu-id="9726e-108">Enable master plans to include requisitions</span></span>

<span data-ttu-id="9726e-109">Per includere richieste durante il calcolo della copertura per un piano generale, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="9726e-109">To include requisitions during the coverage calculation for a master plan, follow these steps.</span></span>

1. <span data-ttu-id="9726e-110">Andare a **Pianificazione generale** \> **Imposta** \> **Piani** \> **Piani generali**.</span><span class="sxs-lookup"><span data-stu-id="9726e-110">Go to **Master planning** \> **Setup** \> **Plans** \> **Master plans**.</span></span>
1. <span data-ttu-id="9726e-111">Selezionare o creare un piano generale.</span><span class="sxs-lookup"><span data-stu-id="9726e-111">Create or select a master plan.</span></span>
1. <span data-ttu-id="9726e-112">Nella Scheda dettaglio **Generale**, impostare l'opzione **Includi richieste** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="9726e-112">On the **General** FastTab, set the **Include requisitions** option to *Yes*.</span></span>
1. <span data-ttu-id="9726e-113">Ripetere i passaggi 2 e 3 per ogni piano generale aggiuntivo in cui si desidera includere le richieste.</span><span class="sxs-lookup"><span data-stu-id="9726e-113">Repeat steps 2 and 3 for each additional master plan where you want to include requisitions.</span></span>

## <a name="approved-requisitions-time-fence"></a><span data-ttu-id="9726e-114">Intervallo temporale richieste approvate</span><span class="sxs-lookup"><span data-stu-id="9726e-114">Approved requisitions time fence</span></span>

<span data-ttu-id="9726e-115">L'opzione *Intervallo temporale richieste approvate* stabilisce quanto indietro (in giorni) un piano generale includerà la domanda proveniente dalle richieste di rifornimento approvate.</span><span class="sxs-lookup"><span data-stu-id="9726e-115">The *approved requisitions time fence* establishes how far back (in days) a master plan will include demand from approved replenishment requisitions.</span></span> <span data-ttu-id="9726e-116">È possibile impostare un intervallo di tempo per le richieste approvate sia a livello di gruppo di copertura che a livello di piano generale.</span><span class="sxs-lookup"><span data-stu-id="9726e-116">You can set an approved requisitions time fence at both the coverage group level and the master plan level.</span></span>

### <a name="set-the-approved-requisitions-time-fence-for-a-coverage-group"></a><span data-ttu-id="9726e-117">Impostare l'intervallo di tempo per le richieste approvate per un gruppo di copertura</span><span class="sxs-lookup"><span data-stu-id="9726e-117">Set the approved requisitions time fence for a coverage group</span></span>

1. <span data-ttu-id="9726e-118">Andare a **Pianificazione generale** \> **Imposta** \> **Copertura** \> **Gruppi di copertura**.</span><span class="sxs-lookup"><span data-stu-id="9726e-118">Go to **Master planning** \> **Setup** \> **Coverage** \> **Coverage group**.</span></span>
1. <span data-ttu-id="9726e-119">Creare o selezionare un gruppo di copertura.</span><span class="sxs-lookup"><span data-stu-id="9726e-119">Create or select a coverage group.</span></span>
1. <span data-ttu-id="9726e-120">Nella Scheda dettaglio **Altro**, impostare il campo **Intervallo temporale richieste approvate (giorni)** sul numero di giorni da includere nell'intervallo temporale.</span><span class="sxs-lookup"><span data-stu-id="9726e-120">On the **Other** FastTab, set the **Approved requisitions time fence (days)** field to the number of days to include in the time fence.</span></span>
1. <span data-ttu-id="9726e-121">Ripetere i passaggi 2 e 3 per ogni gruppo di copertura aggiuntivo in cui si desidera impostare un intervallo di tempo per le richieste approvate.</span><span class="sxs-lookup"><span data-stu-id="9726e-121">Repeat steps 2 and 3 for each additional coverage group where you want to set an approved requisitions time fence.</span></span>

### <a name="set-the-approved-requisitions-time-fence-for-individual-master-plans"></a><span data-ttu-id="9726e-122">Impostare l'intervallo di tempo per le richieste approvate per i singoli piani generali</span><span class="sxs-lookup"><span data-stu-id="9726e-122">Set the approved requisitions time fence for individual master plans</span></span>

<span data-ttu-id="9726e-123">Quando si imposta un intervallo temporale per le richieste approvate per un singolo piano generale, l'impostazione sostituisce l'impostazione dell'intervallo temporale per qualsiasi gruppo di copertura applicabile.</span><span class="sxs-lookup"><span data-stu-id="9726e-123">When you set an approved requisitions time fence for an individual master plan, the setting overrides the time fence setting for any applicable coverage group.</span></span>

1. <span data-ttu-id="9726e-124">Andare a **Pianificazione generale** \> **Imposta** \> **Piani** \> **Piani generali**.</span><span class="sxs-lookup"><span data-stu-id="9726e-124">Go to **Master planning** \> **Setup** \> **Plans** \> **Master plans**.</span></span>
1. <span data-ttu-id="9726e-125">Selezionare o creare un piano generale.</span><span class="sxs-lookup"><span data-stu-id="9726e-125">Create or select a master plan.</span></span>
1. <span data-ttu-id="9726e-126">Nella Scheda dettaglio **Intervalli temporali in giorni**, impostare il campo **Intervallo temporale richieste approvate (giorni)** sul numero di giorni da includere nell'intervallo temporale.</span><span class="sxs-lookup"><span data-stu-id="9726e-126">On the **TIme fences in days** FastTab, set the **Approved requisitions time fence (days)** field to the number of days to include in the time fence.</span></span>
1. <span data-ttu-id="9726e-127">Ripetere i passaggi 2 e 3 per ogni piano generale aggiuntivo in cui si desidera impostare un intervallo di tempo per le richieste approvate.</span><span class="sxs-lookup"><span data-stu-id="9726e-127">Repeat steps 2 and 3 for each additional master plan where you want to set an approved requisitions time fence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9726e-128">**Presto disponibili:** gli intervalli temporali delle richieste approvate non sono ancora supportati per l'ottimizzazione della pianificazione.</span><span class="sxs-lookup"><span data-stu-id="9726e-128">**Coming soon:** Approved requisitions time fences aren't yet supported for Planning Optimization.</span></span> <span data-ttu-id="9726e-129">Fino a quando non sono supportati, tutti i valori immessi nel campo **Intervallo temporale per le richieste approvate (giorni)** verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="9726e-129">Until they are supported, all values that you enter in the **Approved requisitions time fence (days)** field will be ignored.</span></span>

## <a name="independent-supply-regardless-of-coverage-code"></a><span data-ttu-id="9726e-130">Fornitura indipendente, indipendentemente dal codice di copertura</span><span class="sxs-lookup"><span data-stu-id="9726e-130">Independent supply, regardless of coverage code</span></span>

<span data-ttu-id="9726e-131">Le richieste di acquisto sono sempre coperte da ordini pianificati indipendenti, indipendentemente dal codice di copertura.</span><span class="sxs-lookup"><span data-stu-id="9726e-131">Purchase requisitions are always covered by independent planned orders, regardless of the coverage code.</span></span> <span data-ttu-id="9726e-132">Questo comportamento garantisce una chiara tracciabilità e flussi di lavoro tra le richieste di acquisto e gli ordini di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="9726e-132">This behavior ensures clear traceability and workflows between purchase requisitions and replenishment orders.</span></span>

### <a name="example-1"></a><span data-ttu-id="9726e-133">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="9726e-133">Example 1</span></span>

<span data-ttu-id="9726e-134">Un prodotto è impostato in modo che abbia un valore **Codice di copertura** pari a *Min/max* . Presenta i seguenti stati di inventario e richiesta:</span><span class="sxs-lookup"><span data-stu-id="9726e-134">A product is set up so that it has a **Coverage code** value of *Min/max*. It has the following inventory and requisition statuses:</span></span>

- <span data-ttu-id="9726e-135">Quantità scorte disponibili = 10.</span><span class="sxs-lookup"><span data-stu-id="9726e-135">Inventory on-hand quantity = 10.</span></span>
- <span data-ttu-id="9726e-136">Quantità minima in magazzino = 15.</span><span class="sxs-lookup"><span data-stu-id="9726e-136">Minimum inventory quantity = 15.</span></span>
- <span data-ttu-id="9726e-137">Quantità massima in magazzino = 20.</span><span class="sxs-lookup"><span data-stu-id="9726e-137">Maximum inventory quantity = 20.</span></span>
- <span data-ttu-id="9726e-138">Esiste una richiesta di acquisto per un pezzo.</span><span class="sxs-lookup"><span data-stu-id="9726e-138">A purchase requisition for one piece exists.</span></span> <span data-ttu-id="9726e-139">Ha una data richiesta di oggi.</span><span class="sxs-lookup"><span data-stu-id="9726e-139">It has a requested date of today.</span></span>

<span data-ttu-id="9726e-140">Quando viene eseguita la pianificazione generale, vengono creati due ordini pianificati: uno per 10 pezzi per rifornire le scorte alla quantità massima e uno per un pezzo per rifornire la richiesta di acquisto.</span><span class="sxs-lookup"><span data-stu-id="9726e-140">When master planning runs, two planned orders are created: one for 10 pieces to replenish inventory to the maximum quantity, and one for one piece to replenish the purchase requisition.</span></span>

### <a name="example-2"></a><span data-ttu-id="9726e-141">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="9726e-141">Example 2</span></span>

<span data-ttu-id="9726e-142">Un prodotto è impostato in modo che abbia un valore **Codice di copertura** pari a *Min/max* . Presenta i seguenti stati di inventario e richiesta:</span><span class="sxs-lookup"><span data-stu-id="9726e-142">A product is set up so that it has a **Coverage code** value of *Min/max*. It has the following inventory and requisition statuses:</span></span>

- <span data-ttu-id="9726e-143">Quantità scorte disponibili = 17.</span><span class="sxs-lookup"><span data-stu-id="9726e-143">Inventory on-hand quantity = 17.</span></span>
- <span data-ttu-id="9726e-144">Quantità minima in magazzino = 15.</span><span class="sxs-lookup"><span data-stu-id="9726e-144">Minimum inventory quantity = 15.</span></span>
- <span data-ttu-id="9726e-145">Quantità massima in magazzino = 20.</span><span class="sxs-lookup"><span data-stu-id="9726e-145">Maximum inventory quantity = 20.</span></span>
- <span data-ttu-id="9726e-146">Esiste una richiesta di acquisto per un pezzo.</span><span class="sxs-lookup"><span data-stu-id="9726e-146">A purchase requisition for one piece exists.</span></span> <span data-ttu-id="9726e-147">Ha una data richiesta di oggi.</span><span class="sxs-lookup"><span data-stu-id="9726e-147">It has a requested date of today.</span></span>

<span data-ttu-id="9726e-148">Quando viene eseguita la pianificazione generale, viene creato un ordine pianificato per un pezzo per rifornire la richiesta di acquisto.</span><span class="sxs-lookup"><span data-stu-id="9726e-148">When master planning runs, one planned order for one piece is created to replenish the purchase requisition.</span></span>

### <a name="example-3"></a><span data-ttu-id="9726e-149">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="9726e-149">Example 3</span></span>

<span data-ttu-id="9726e-150">Un prodotto è impostato in modo che abbia un valore di **Codice di copertura** di *Periodo* e un periodo di sette giorni.</span><span class="sxs-lookup"><span data-stu-id="9726e-150">A product is set up so that it has a **Coverage code** value of *Period* and a period length of seven days.</span></span> <span data-ttu-id="9726e-151">Presenta i seguenti stati di inventario, ordine cliente e richiesta:</span><span class="sxs-lookup"><span data-stu-id="9726e-151">It has the following inventory, sales order, and requisition statuses:</span></span>

- <span data-ttu-id="9726e-152">Quantità scorte disponibili = 0.</span><span class="sxs-lookup"><span data-stu-id="9726e-152">Inventory on-hand quantity = 0.</span></span>
- <span data-ttu-id="9726e-153">Esiste un ordine cliente per cinque pezzi.</span><span class="sxs-lookup"><span data-stu-id="9726e-153">A sales order for five pieces exists.</span></span> <span data-ttu-id="9726e-154">Ha una data di spedizione prevista per oggi più un giorno.</span><span class="sxs-lookup"><span data-stu-id="9726e-154">It has an expected ship date of today plus one day.</span></span>
- <span data-ttu-id="9726e-155">Esiste una richiesta di acquisto per tre pezzi.</span><span class="sxs-lookup"><span data-stu-id="9726e-155">A purchase requisition for three pieces exists.</span></span> <span data-ttu-id="9726e-156">Ha una data richiesta di oggi più tre giorni.</span><span class="sxs-lookup"><span data-stu-id="9726e-156">It has a requested date of today plus three days.</span></span>

<span data-ttu-id="9726e-157">Quando viene eseguita la pianificazione generale, vengono creati due ordini pianificati: uno per tre pezzi per rifornire la richiesta di acquisto e uno per cinque pezzi per rifornire la domanda dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="9726e-157">When master planning runs, two planned orders are created: one for three pieces to replenish the purchase requisition and one for five pieces to replenish sales order demand.</span></span>

> [!NOTE]
> <span data-ttu-id="9726e-158">Dopo che un ordine pianificato con pegging a una richiesta di acquisto è stato stabilizzato, il motore di pianificazione mantiene il pegging alla richiesta di acquisto.</span><span class="sxs-lookup"><span data-stu-id="9726e-158">After a planned order that is pegged to a purchase requisition is firmed, the planning engine keeps the pegging to the purchase requisition.</span></span> <span data-ttu-id="9726e-159">Se in seguito si scopre che nell'ordine stabilizzato manca una quantità necessaria per soddisfare la richiesta di acquisto, il sistema creerà un nuovo ordine pianificato per la differenza.</span><span class="sxs-lookup"><span data-stu-id="9726e-159">If the firmed order is later found to be missing some quantity that is required to fulfill the purchase requisition, the system will create a new planned order for the difference.</span></span>

<span data-ttu-id="9726e-160">Per ulteriori informazioni sulle richieste di acquisto, vedere [Panoramica della richiesta di acquisto](../../procurement/purchase-requisitions-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9726e-160">For more information about purchase requisitions, see [Purchase requisition overview](../../procurement/purchase-requisitions-overview.md).</span></span>
