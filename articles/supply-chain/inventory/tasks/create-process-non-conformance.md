---
title: Creare ed elaborare non conformità
description: In questo argomento viene descritto come eseguire la gestione di non conformità, in base a un ordine di controllo qualità esistente.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 06a56a694f7a80d65cb46d08744e78d8361cee3b
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956208"
---
# <a name="create-and-process-nonconformances"></a><span data-ttu-id="27540-103">Creare ed elaborare non conformità</span><span class="sxs-lookup"><span data-stu-id="27540-103">Create and process nonconformances</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="27540-104">In questo argomento viene descritto come eseguire la gestione di non conformità, in base a un ordine di controllo qualità esistente.</span><span class="sxs-lookup"><span data-stu-id="27540-104">This topic describes how to perform nonconformance management based on an existing quality order.</span></span> <span data-ttu-id="27540-105">In genere, la gestione della non conformità viene eseguita da un addetto alla qualità.</span><span class="sxs-lookup"><span data-stu-id="27540-105">Typically, nonconformance management is done by a quality clerk.</span></span> <span data-ttu-id="27540-106">Come prerequisito, è necessario disporre di un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="27540-106">As a prerequisite, you must have a quality order available.</span></span> <span data-ttu-id="27540-107">(Per informazioni su come creare un ordine di controllo qualità, vedere [Verificare la qualità delle merci](inspect-quality-goods.md).)</span><span class="sxs-lookup"><span data-stu-id="27540-107">(For information about how to create a quality order, see [Inspect the quality of goods](inspect-quality-goods.md).)</span></span>

<span data-ttu-id="27540-108">Prima che un utente possa elaborare l'approvazione di una non conformità, è necessario che gli venga assegnato un lavoratore nel campo **Persona** della pagina **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="27540-108">Before a user can process the approval of a nonconformance, a worker must be assigned to them in the **Person** field on the **Users** page.</span></span> <span data-ttu-id="27540-109">Inoltre, prima che l'utente possa utilizzare le note del documento, l'opzione **Attiva gestione documenti** deve essere impostata su *Sì* nelle relative opzioni utente.</span><span class="sxs-lookup"><span data-stu-id="27540-109">Additionally, before the user can use the document notes, the **Enable document handling** option must be set to *Yes* in their user options.</span></span>

## <a name="create-a-nonconformance"></a><span data-ttu-id="27540-110">Creare una non conformità</span><span class="sxs-lookup"><span data-stu-id="27540-110">Create a nonconformance</span></span>

<span data-ttu-id="27540-111">Per creare una non conformità, eseguire i passaggi indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="27540-111">To create a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="27540-112">Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.</span><span class="sxs-lookup"><span data-stu-id="27540-112">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="27540-113">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="27540-113">On the Action pane, select **New**.</span></span>
1. <span data-ttu-id="27540-114">Nella finestra di dialogo **Crea non conformità**, nel campo **Tipo di problema** selezionare il tipo di problema riscontrato durante il processo di ispezione.</span><span class="sxs-lookup"><span data-stu-id="27540-114">In the **Create non conformance** dialog box, in **Problem type** field, select the type of problem that was found during the inspection process.</span></span>
1. <span data-ttu-id="27540-115">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="27540-115">Select **OK**.</span></span>

## <a name="approve-or-reject-a-nonconformance"></a><span data-ttu-id="27540-116">Approvare o respingere una non conformità</span><span class="sxs-lookup"><span data-stu-id="27540-116">Approve or reject a nonconformance</span></span>

<span data-ttu-id="27540-117">Per approvare o respingere una non conformità, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="27540-117">To approve or reject a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="27540-118">Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.</span><span class="sxs-lookup"><span data-stu-id="27540-118">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="27540-119">Nell'elenco selezionare la non conformità che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="27540-119">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27540-120">È possibile aggiungere una correzione solo alle non conformità approvate.</span><span class="sxs-lookup"><span data-stu-id="27540-120">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="27540-121">Nel riquadro azioni selezionare **Funzioni \> Approva non conformità** per approvare la non conformità o **Funzioni \> Respingi non conformità** per respingerla.</span><span class="sxs-lookup"><span data-stu-id="27540-121">On the Action Pane, select **Functions \> Approve non conformance** to approve the nonconformance or **Functions \> Refuse non conformance** to reject it.</span></span> <span data-ttu-id="27540-122">È possibile associare non conformità approvate a [operazioni correlate](../quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="27540-122">You can associate approved nonconformances with [related operations](../quality-operations.md).</span></span> <span data-ttu-id="27540-123">In questo modo, è possibile registrare il lavoro svolto come parte della gestione delle non conformità e dell'elaborazione della gestione delle correzioni.</span><span class="sxs-lookup"><span data-stu-id="27540-123">In this way, you can record work that is done as part of the nonconformance handling and the processing of correction handling.</span></span>
1. <span data-ttu-id="27540-124">Ti viene chiesto di confermare la selezione.</span><span class="sxs-lookup"><span data-stu-id="27540-124">You're prompted to confirm your selection.</span></span> <span data-ttu-id="27540-125">Selezionare **Sì** per continuare.</span><span class="sxs-lookup"><span data-stu-id="27540-125">Select **Yes** to continue.</span></span>

## <a name="add-operations-and-other-details-to-nonconformances"></a><span data-ttu-id="27540-126">Aggiungere operazioni e altri dettagli alle non conformità</span><span class="sxs-lookup"><span data-stu-id="27540-126">Add operations and other details to nonconformances</span></span>

<span data-ttu-id="27540-127">Dopo aver creato una non conformità, è possibile iniziare ad aggiungere operazioni correlate e specificare ulteriori informazioni su tali operazioni.</span><span class="sxs-lookup"><span data-stu-id="27540-127">After you've created a nonconformance, you can start to add related operations and specify additional information about those operations.</span></span> <span data-ttu-id="27540-128">È possibile aggiungere operazioni correlate solo alle non conformità approvate.</span><span class="sxs-lookup"><span data-stu-id="27540-128">You can add related operations only to nonconformances that are approved.</span></span>

<span data-ttu-id="27540-129">Oltre alle informazioni di base, è possibile aggiungere i seguenti dettagli a un'operazione:</span><span class="sxs-lookup"><span data-stu-id="27540-129">Besides the basic information, you can add the following details to an operation:</span></span>

- <span data-ttu-id="27540-130">**Articoli** - È possibile creare un elenco di articoli che vengono consumati per eseguire la correzione.</span><span class="sxs-lookup"><span data-stu-id="27540-130">**Items** – You can create a list of items that are consumed to perform the correction.</span></span> <span data-ttu-id="27540-131">Ad esempio, gli articoli potrebbero essere prodotti necessari per riparare apparecchiature o ingredienti necessari per la rilavorazione di un prodotto finito.</span><span class="sxs-lookup"><span data-stu-id="27540-131">For example, the items might be products that are required to repair equipment or ingredients that are required to rework a finished product.</span></span>
- <span data-ttu-id="27540-132">**Spese gestione qualità** - È possibile creare un elenco di spese sostenute o fatturate a fonti esterne.</span><span class="sxs-lookup"><span data-stu-id="27540-132">**Quality charges** – You can create a list of charges that are incurred or billed out to external sources.</span></span>
- <span data-ttu-id="27540-133">**Foglio presenze** - È possibile creare un registro del tempo che ogni lavoratore dedica all'operazione.</span><span class="sxs-lookup"><span data-stu-id="27540-133">**Timesheet** – You can create a log of the time that each worker spends on the operation.</span></span>

<span data-ttu-id="27540-134">Le impostazioni rimanenti sono facoltative.</span><span class="sxs-lookup"><span data-stu-id="27540-134">The remaining settings are optional.</span></span> <span data-ttu-id="27540-135">Il costo di ogni articolo, le spese di gestione qualità e il foglio presenze vengono sommati e visualizzati nell'operazione.</span><span class="sxs-lookup"><span data-stu-id="27540-135">The cost for each item, quality charges, and the timesheet are summed and shown on the operation.</span></span> <span data-ttu-id="27540-136">Non puoi modificare direttamente il campo **Costo** dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="27540-136">You can't directly edit the **Cost** field on the operation.</span></span>

### <a name="create-an-operation-for-a-nonconformance"></a><span data-ttu-id="27540-137">Creare un'operazione per una non conformità</span><span class="sxs-lookup"><span data-stu-id="27540-137">Create an operation for a nonconformance</span></span>

<span data-ttu-id="27540-138">Per creare un'operazione per una non conformità, eseguire i passaggi indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="27540-138">To create an operation for a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="27540-139">Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.</span><span class="sxs-lookup"><span data-stu-id="27540-139">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="27540-140">Nell'elenco selezionare la non conformità che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="27540-140">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27540-141">È possibile aggiungere o aggiornare operazioni solo per le non conformità approvate.</span><span class="sxs-lookup"><span data-stu-id="27540-141">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="27540-142">Nel riquadro azioni, seleziona **Operazioni correlate**.</span><span class="sxs-lookup"><span data-stu-id="27540-142">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="27540-143">Nella pagina **Operazioni correlate**, nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="27540-143">On the **Related operations** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="27540-144">Quindi imposta i seguenti campi per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="27540-144">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="27540-145">**Operazione** - Selezionare il codice dell'operazione che verrà eseguita per la non conformità.</span><span class="sxs-lookup"><span data-stu-id="27540-145">**Operation** – Select the code of the operation that will be performed for the nonconformance.</span></span>
    - <span data-ttu-id="27540-146">**Motivo** - Immettere una descrizione dettagliata che spieghi perché l'operazione è richiesta.</span><span class="sxs-lookup"><span data-stu-id="27540-146">**Reason** – Enter a detailed description that explains why the operation is required.</span></span>
    - <span data-ttu-id="27540-147">**Ordine cliente** - Se il codice operazione selezionato è correlato al tipo di ordine cliente, selezionare l'ordine cliente a cui si sta collegando l'operazione.</span><span class="sxs-lookup"><span data-stu-id="27540-147">**Sales order** – If the selected operation code is related to the sales order type, select the sales order that you're linking the operation to.</span></span>
    - <span data-ttu-id="27540-148">**Ordine fornitore** - Se il codice operazione selezionato è correlato al tipo di ordine fornitore, selezionare l'ordine fornitore a cui si sta collegando l'operazione.</span><span class="sxs-lookup"><span data-stu-id="27540-148">**Purchase order** – If the selected operation code is related to the purchase order type, select the purchase order that you're linking the operation to.</span></span>

1. <span data-ttu-id="27540-149">Chiudere le pagine.</span><span class="sxs-lookup"><span data-stu-id="27540-149">Close the pages.</span></span>

### <a name="add-items-to-an-operation"></a><span data-ttu-id="27540-150">Aggiungere articoli a un'operazione</span><span class="sxs-lookup"><span data-stu-id="27540-150">Add items to an operation</span></span>

<span data-ttu-id="27540-151">Per aggiungere articoli a un'operazione, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="27540-151">To add items to an operation, follow these steps.</span></span>

1. <span data-ttu-id="27540-152">Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.</span><span class="sxs-lookup"><span data-stu-id="27540-152">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="27540-153">Nell'elenco selezionare la non conformità che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="27540-153">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27540-154">È possibile aggiungere o aggiornare operazioni solo per le non conformità approvate.</span><span class="sxs-lookup"><span data-stu-id="27540-154">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="27540-155">Nel riquadro azioni, seleziona **Operazioni correlate**.</span><span class="sxs-lookup"><span data-stu-id="27540-155">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="27540-156">Nella pagina **Operazioni correlate** selezionare l'operazione a cui si desidera aggiungere articoli.</span><span class="sxs-lookup"><span data-stu-id="27540-156">On the **Related operations** page, select the operation that you want to add items to.</span></span>
1. <span data-ttu-id="27540-157">Nel riquadro azioni seleziona **Articoli**.</span><span class="sxs-lookup"><span data-stu-id="27540-157">On the Action Pane, select **Items**.</span></span>
1. <span data-ttu-id="27540-158">Nella pagina **Operazioni correlate**, nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="27540-158">On the **Related operations** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="27540-159">Quindi imposta i seguenti campi per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="27540-159">Then set the following fields for new row:</span></span>

    - <span data-ttu-id="27540-160">**Numero articolo** - Seleziona il prodotto che verrà consumato come parte dell'operazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="27540-160">**Item number** – Select the product that will be consumed as part of the selected operation.</span></span>
    - <span data-ttu-id="27540-161">**Quantità** - Immettere il numero di articoli che verranno consumati.</span><span class="sxs-lookup"><span data-stu-id="27540-161">**Quantity** – Enter the number of items that will be consumed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27540-162">È possibile visualizzare il costo dell'articolo nel campo **Costo** della scheda **Generale**. Il costo che vi viene mostrato deriva dal costo che è impostato nella pagina **Prodotto rilasciato**.</span><span class="sxs-lookup"><span data-stu-id="27540-162">You can view the cost for the item in the **Cost** field on the **General** tab. The cost that is shown there comes from the cost that is set up on the **Released product** page.</span></span> <span data-ttu-id="27540-163">Il costo non può essere aggiornato direttamente nella pagina **Elementi operazioni correlate**.</span><span class="sxs-lookup"><span data-stu-id="27540-163">The cost can't be updated directly on the **Related operation item** page.</span></span> <span data-ttu-id="27540-164">Il costo di tutti gli articoli aggiunti alla pagina **Elementi operazioni correlate** viene automaticamente aggiunto al campo **Costo** nella pagina **Operazioni correlate**.</span><span class="sxs-lookup"><span data-stu-id="27540-164">The cost of all items that are added on the **Related operation items** page is automatically added to the **Cost** field on the **Related operations** page.</span></span>

1. <span data-ttu-id="27540-165">Ripeti il passaggio precedente per ogni articolo aggiuntivo che devi aggiungere.</span><span class="sxs-lookup"><span data-stu-id="27540-165">Repeat the previous step for each additional item that you must add.</span></span>
1. <span data-ttu-id="27540-166">Chiudere le pagine.</span><span class="sxs-lookup"><span data-stu-id="27540-166">Close the pages.</span></span>

### <a name="add-quality-charges-to-an-operation"></a><span data-ttu-id="27540-167">Aggiungere spese di gestione qualità a un'operazione</span><span class="sxs-lookup"><span data-stu-id="27540-167">Add quality charges to an operation</span></span>

<span data-ttu-id="27540-168">Per aggiungere spese di gestione qualità a un'operazione, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="27540-168">To add quality charges to an operation, follow these steps.</span></span>

1. <span data-ttu-id="27540-169">Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.</span><span class="sxs-lookup"><span data-stu-id="27540-169">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="27540-170">Nell'elenco selezionare la non conformità che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="27540-170">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27540-171">È possibile aggiungere o aggiornare operazioni solo per le non conformità approvate.</span><span class="sxs-lookup"><span data-stu-id="27540-171">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="27540-172">Nel riquadro azioni, seleziona **Operazioni correlate**.</span><span class="sxs-lookup"><span data-stu-id="27540-172">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="27540-173">Nella pagina **Operazioni correlate** selezionare l'operazione a cui si desidera aggiungere le spese di gestione qualità.</span><span class="sxs-lookup"><span data-stu-id="27540-173">On the **Related operations** page, select the operation that you want to add quality charges to.</span></span>
1. <span data-ttu-id="27540-174">Nel riquadro azioni, seleziona **Spese gestione qualità**.</span><span class="sxs-lookup"><span data-stu-id="27540-174">On the Action Pane, select **Quality charges**.</span></span>
1. <span data-ttu-id="27540-175">Nella pagina **Spese operazioni correlate**, nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="27540-175">On the **Related operation charges** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="27540-176">Quindi imposta i seguenti campi per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="27540-176">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="27540-177">**Codice spese** - Seleziona le spese di gestione qualità che desideri aggiungere.</span><span class="sxs-lookup"><span data-stu-id="27540-177">**Charges code** – Select the quality charge that you want to add.</span></span>
    - <span data-ttu-id="27540-178">**Descrizione** - Immettere una descrizione dettagliata delle spese.</span><span class="sxs-lookup"><span data-stu-id="27540-178">**Description** – Enter a detailed description of the charge.</span></span>
    - <span data-ttu-id="27540-179">**Valore spese** – Immettere l'importo delle spese.</span><span class="sxs-lookup"><span data-stu-id="27540-179">**Charges value** – Enter the amount of the charge.</span></span>

1. <span data-ttu-id="27540-180">Ripeti il passaggio precedente per ogni spese aggiuntiva che devi aggiungere.</span><span class="sxs-lookup"><span data-stu-id="27540-180">Repeat the previous step for each additional charge that you must add.</span></span>
1. <span data-ttu-id="27540-181">Chiudere le pagine.</span><span class="sxs-lookup"><span data-stu-id="27540-181">Close the pages.</span></span>

> [!NOTE]
> <span data-ttu-id="27540-182">L'importo nel campo **Valore spese** viene automaticamente sommato per tutti le spese di gestione qualità e aggiunto a qualsiasi altro importo nel campo **Costo** della pagina **Operazioni correlate**.</span><span class="sxs-lookup"><span data-stu-id="27540-182">The amount in the **Charges value** field is automatically summed for all quality charges and added to any other amounts in the **Cost** field on the **Related operations** page.</span></span>

### <a name="create-a-timesheet-on-an-operation"></a><span data-ttu-id="27540-183">Creare un foglio presenze su un'operazione</span><span class="sxs-lookup"><span data-stu-id="27540-183">Create a timesheet on an operation</span></span>

<span data-ttu-id="27540-184">Per aggiungere un foglio presenze a un'operazione, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="27540-184">To add a timesheet to an operation, follow these steps.</span></span>

1. <span data-ttu-id="27540-185">Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.</span><span class="sxs-lookup"><span data-stu-id="27540-185">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="27540-186">Nell'elenco selezionare la non conformità che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="27540-186">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27540-187">È possibile aggiungere o aggiornare operazioni solo per le non conformità approvate.</span><span class="sxs-lookup"><span data-stu-id="27540-187">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="27540-188">Nel riquadro azioni, seleziona **Operazioni correlate**.</span><span class="sxs-lookup"><span data-stu-id="27540-188">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="27540-189">Nella pagina **Operazioni correlate** selezionare l'operazione a cui si desidera aggiungere un foglio presenze.</span><span class="sxs-lookup"><span data-stu-id="27540-189">On the **Related operations** page, select the operation that you want to add a timesheet to.</span></span>
1. <span data-ttu-id="27540-190">Nel riquadro azioni selezionare **Foglio presenze**.</span><span class="sxs-lookup"><span data-stu-id="27540-190">On the Action Pane, select **Timesheet**.</span></span>
1. <span data-ttu-id="27540-191">Nella pagina **Fogli presenze operazioni correlate**, nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="27540-191">On the **Related operation time sheets** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="27540-192">Quindi imposta i seguenti campi per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="27540-192">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="27540-193">**Data** - Specificare la data in cui è stato svolto il lavoro.</span><span class="sxs-lookup"><span data-stu-id="27540-193">**Date** – Specify the date when work was done.</span></span> <span data-ttu-id="27540-194">Per impostazione predefinita, il campo è impostato sulla corrente.</span><span class="sxs-lookup"><span data-stu-id="27540-194">By default, this field is set to the current date.</span></span>
    - <span data-ttu-id="27540-195">**Lavoratore** – Selezionare il lavoratore che ha svolto il lavoro.</span><span class="sxs-lookup"><span data-stu-id="27540-195">**Worker** – Select the worker who did the work.</span></span> <span data-ttu-id="27540-196">Per impostazione predefinita, questo campo è impostato sul lavoratore assegnato all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="27540-196">By default, this field is set to the worker that is assigned to the current user.</span></span>
    - <span data-ttu-id="27540-197">**Ore operazione** - Immettere il numero di ore lavorate nell'operazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="27540-197">**Operation hours** – Enter the number of hours that were worked on the selected operation.</span></span>
    - <span data-ttu-id="27540-198">**Fatturato** - Selezionare questa casella di controllo se il tempo è stato addebitato a un cliente o fornitore su una fattura.</span><span class="sxs-lookup"><span data-stu-id="27540-198">**Invoiced** – Select this check box if the time has been charged to a customer or vendor on an invoice.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27540-199">Puoi visualizzare il costo nel campo **Costo** della scheda **Generale**. Il costo viene calcolato utilizzando la tariffa definita nella pagina **Parametri di Gestione articoli**.</span><span class="sxs-lookup"><span data-stu-id="27540-199">You can view the cost in the **Cost** field on the **General** tab. The cost is calculated by using the rate that you define on the **Inventory management parameters** page.</span></span>

1. <span data-ttu-id="27540-200">Ripeti il passaggio precedente per ogni foglio presenze aggiuntiva che devi aggiungere.</span><span class="sxs-lookup"><span data-stu-id="27540-200">Repeat the previous step for each additional timesheet line that you must add.</span></span>
1. <span data-ttu-id="27540-201">Chiudere le pagine.</span><span class="sxs-lookup"><span data-stu-id="27540-201">Close the pages.</span></span>

> [!NOTE]
> <span data-ttu-id="27540-202">L'importo nel campo **Costo** viene automaticamente sommato per tutte le righe del foglio presenze e aggiunto a qualsiasi altro importo nel campo **Costo** della pagina **Operazioni correlate**.</span><span class="sxs-lookup"><span data-stu-id="27540-202">The amount in the **Cost** field is summed for all timesheet lines and added to any other amounts in the **Cost** field on the **Related operations** page.</span></span>

## <a name="add-a-correction-to-a-nonconformance"></a><span data-ttu-id="27540-203">Aggiungere una correzione a una non conformità</span><span class="sxs-lookup"><span data-stu-id="27540-203">Add a correction to a nonconformance</span></span>

<span data-ttu-id="27540-204">Per aggiungere una correzione a una non conformità, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="27540-204">To add a correction to a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="27540-205">Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.</span><span class="sxs-lookup"><span data-stu-id="27540-205">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="27540-206">Nell'elenco selezionare la non conformità che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="27540-206">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27540-207">È possibile aggiungere una correzione solo alle non conformità approvate.</span><span class="sxs-lookup"><span data-stu-id="27540-207">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="27540-208">Nel riquadro azioni, seleziona **Correzioni**.</span><span class="sxs-lookup"><span data-stu-id="27540-208">On the Action Pane, select **Corrections**.</span></span>
1. <span data-ttu-id="27540-209">Nella pagina **Correzioni**, nel riquadro azioni seleziona **Nuovo** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="27540-209">On the **Corrections** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="27540-210">Quindi imposta i seguenti campi per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="27540-210">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="27540-211">**Diagnostica** - Seleziona il tipo di diagnostica che identifica il tipo di correzione che stai creando.</span><span class="sxs-lookup"><span data-stu-id="27540-211">**Diagnostic** – Select the diagnostic type that identifies the type of correction that you're creating.</span></span>
    - <span data-ttu-id="27540-212">**Lavoratore** – Seleziona la persona responsabile della correzione.</span><span class="sxs-lookup"><span data-stu-id="27540-212">**Worker** – Select the person who is responsible for the correction.</span></span>
    - <span data-ttu-id="27540-213">**Priorità di correzione** - Selezionare un'opzione per indicare come assegnare la priorità alla correzione (*Bassa*, *Normale* o *Alta*).</span><span class="sxs-lookup"><span data-stu-id="27540-213">**Correction priority** – Select an option to indicate how the correction should be prioritized (*Low*, *Normal*, or *High*).</span></span>
    - <span data-ttu-id="27540-214">**Data richiesta** - Immettere la data in cui è stata richiesta l'azione correttiva.</span><span class="sxs-lookup"><span data-stu-id="27540-214">**Requested date** – Enter the date when the corrective action was requested.</span></span>
    - <span data-ttu-id="27540-215">**Data pianificata** - Immettere la data in cui si prevede di completare la correzione.</span><span class="sxs-lookup"><span data-stu-id="27540-215">**Planned date** – Enter the date when the correction is expected to be completed.</span></span>
    - <span data-ttu-id="27540-216">**Soluzione a breve termine** - Selezionare questa casella di controllo se l'azione correttiva corregge la non conformità solo per un breve periodo.</span><span class="sxs-lookup"><span data-stu-id="27540-216">**Short term solution** – Select this check box if the corrective action corrects the nonconformance only for a short time.</span></span>

1. <span data-ttu-id="27540-217">Chiudere le pagine.</span><span class="sxs-lookup"><span data-stu-id="27540-217">Close the pages.</span></span>

## <a name="mark-a-correction-as-completed"></a><span data-ttu-id="27540-218">Contrassegnare una correzione come completata</span><span class="sxs-lookup"><span data-stu-id="27540-218">Mark a correction as completed</span></span>

<span data-ttu-id="27540-219">Per contrassegnare la correzione a una non conformità come completata, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="27540-219">To mark a nonconformance correction as completed, follow these steps.</span></span>

1. <span data-ttu-id="27540-220">Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.</span><span class="sxs-lookup"><span data-stu-id="27540-220">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="27540-221">Nell'elenco selezionare la non conformità che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="27540-221">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27540-222">È possibile aggiungere una correzione solo alle non conformità approvate.</span><span class="sxs-lookup"><span data-stu-id="27540-222">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="27540-223">Nel riquadro azioni, seleziona **Correzioni**.</span><span class="sxs-lookup"><span data-stu-id="27540-223">On the Action Pane, select **Corrections**.</span></span>
1. <span data-ttu-id="27540-224">Nella pagina **Correzioni**, nella griglia selezionare la correzione che si desidera contrassegnare come completata.</span><span class="sxs-lookup"><span data-stu-id="27540-224">On the **Corrections** page, in the grid, select the correction that you want to mark as completed.</span></span>
1. <span data-ttu-id="27540-225">Nel riquadro azioni fare clic su **Contrassegna come completata**.</span><span class="sxs-lookup"><span data-stu-id="27540-225">On the Action Pane, select **Mark complete**.</span></span>
1. <span data-ttu-id="27540-226">Ti viene chiesto di confermare la selezione.</span><span class="sxs-lookup"><span data-stu-id="27540-226">You're prompted to confirm your selection.</span></span> <span data-ttu-id="27540-227">Selezionare **OK** per continuare.</span><span class="sxs-lookup"><span data-stu-id="27540-227">Select **OK** to continue.</span></span> <span data-ttu-id="27540-228">Il campo **Data e ora di completamento** è impostato sulla data e l'ora correnti e la casella di controllo **Completato** è selezionata.</span><span class="sxs-lookup"><span data-stu-id="27540-228">The **Completion date and time** field is set to the current date and time, and the **Completed** check box is selected.</span></span>
1. <span data-ttu-id="27540-229">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="27540-229">Close the page.</span></span>

## <a name="reopen-a-completed-correction"></a><span data-ttu-id="27540-230">Riaprire una correzione completata</span><span class="sxs-lookup"><span data-stu-id="27540-230">Reopen a completed correction</span></span>

<span data-ttu-id="27540-231">Per riaprire una correzione completata, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="27540-231">To reopen a completed correction, follow these steps.</span></span>

1. <span data-ttu-id="27540-232">Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Non conformità**.</span><span class="sxs-lookup"><span data-stu-id="27540-232">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="27540-233">Nell'elenco selezionare la non conformità che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="27540-233">In the list, select the nonconformance that you want to update.</span></span>
1. <span data-ttu-id="27540-234">Nel riquadro azioni, seleziona **Correzioni**.</span><span class="sxs-lookup"><span data-stu-id="27540-234">On the Action pane, select **Corrections**.</span></span>
1. <span data-ttu-id="27540-235">Nella pagina **Correzioni**, nella griglia selezionare la correzione che si desidera riaprire.</span><span class="sxs-lookup"><span data-stu-id="27540-235">On the **Corrections** page, in the grid, select the correction that you want to reopen.</span></span>
1. <span data-ttu-id="27540-236">Nel riquadro azioni fare clic su **Riapri**.</span><span class="sxs-lookup"><span data-stu-id="27540-236">On the Action Pane, select **Reopen**.</span></span>
1. <span data-ttu-id="27540-237">Ti viene chiesto di confermare la selezione.</span><span class="sxs-lookup"><span data-stu-id="27540-237">You're prompted to confirm your selection.</span></span> <span data-ttu-id="27540-238">Selezionare **OK** per continuare.</span><span class="sxs-lookup"><span data-stu-id="27540-238">Select **OK** to continue.</span></span> <span data-ttu-id="27540-239">Il valore viene cancellato dal campo **Data e ora di completamento** e la casella di controllo **Completato** viene deselezionata.</span><span class="sxs-lookup"><span data-stu-id="27540-239">The value is cleared from the **Completion date and time** field, and the **Completed** check box is cleared.</span></span>
1. <span data-ttu-id="27540-240">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="27540-240">Close the page.</span></span>

<span data-ttu-id="27540-241">È ora possibile apportare ulteriori modifiche o aggiornamenti alla correzione.</span><span class="sxs-lookup"><span data-stu-id="27540-241">You can now make additional edits or updates to the correction.</span></span> <span data-ttu-id="27540-242">Quando hai finito, puoi contrassegnare di nuovo la correzione come completata.</span><span class="sxs-lookup"><span data-stu-id="27540-242">When you've finished, you can mark the correction as completed again.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="27540-243">Chiudere una non conformità</span><span class="sxs-lookup"><span data-stu-id="27540-243">Close a nonconformance</span></span>

<span data-ttu-id="27540-244">Per chiudere una non conformità, eseguire i passaggi indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="27540-244">To close a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="27540-245">Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Ordini di controllo qualità**.</span><span class="sxs-lookup"><span data-stu-id="27540-245">Go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>
1. <span data-ttu-id="27540-246">Seleziona un ordine di controllo qualità nella griglia.</span><span class="sxs-lookup"><span data-stu-id="27540-246">Select a quality order in the grid.</span></span>
1. <span data-ttu-id="27540-247">Nel riquadro azioni seleziona **Richieste di informazioni \> Non conformità**.</span><span class="sxs-lookup"><span data-stu-id="27540-247">On the Action Pane, select **Inquiries \> Non conformances**.</span></span>
1. <span data-ttu-id="27540-248">Nella pagina **Non conformità**, selezionare la non conformità di destinazione nella griglia.</span><span class="sxs-lookup"><span data-stu-id="27540-248">On the **Non conformances** page, select the target nonconformance in the grid.</span></span>
1. <span data-ttu-id="27540-249">Nel riquadro azioni seleziona **Funzioni \> Chiudi non conformità**.</span><span class="sxs-lookup"><span data-stu-id="27540-249">On the Action Pane, select **Functions \> Close non conformance**.</span></span>
1. <span data-ttu-id="27540-250">Ti viene chiesto di confermare la selezione.</span><span class="sxs-lookup"><span data-stu-id="27540-250">You're prompted to confirm your selection.</span></span> <span data-ttu-id="27540-251">Selezionare **Sì** per continuare.</span><span class="sxs-lookup"><span data-stu-id="27540-251">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="27540-252">Chiudere le pagine.</span><span class="sxs-lookup"><span data-stu-id="27540-252">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="27540-253">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="27540-253">Additional resources</span></span>

- [<span data-ttu-id="27540-254">Panoramica gestione qualità</span><span class="sxs-lookup"><span data-stu-id="27540-254">Quality management overview</span></span>](../quality-management-processes.md)
- [<span data-ttu-id="27540-255">Abilitare la gestione della qualità e della non conformità</span><span class="sxs-lookup"><span data-stu-id="27540-255">Enable quality and nonconformance management</span></span>](../enable-quality-management.md)
- [<span data-ttu-id="27540-256">Lavoratori responsabili dell'approvazione delle non conformità</span><span class="sxs-lookup"><span data-stu-id="27540-256">Workers responsible for approving nonconformances</span></span>](../quality-responsible-workers.md)
- [<span data-ttu-id="27540-257">Aree di quarantena per non conformità</span><span class="sxs-lookup"><span data-stu-id="27540-257">Quarantine zones for nonconformances</span></span>](../quality-quarantine-zones.md)
- [<span data-ttu-id="27540-258">Tipi di diagnostica per non conformità</span><span class="sxs-lookup"><span data-stu-id="27540-258">Diagnostic types for nonconformances</span></span>](../quality-diagnostic-types.md)
- [<span data-ttu-id="27540-259">Spese di gestione qualità per non conformità</span><span class="sxs-lookup"><span data-stu-id="27540-259">Quality charges for nonconformances</span></span>](../quality-charges.md)
- [<span data-ttu-id="27540-260">Operazioni per non conformità</span><span class="sxs-lookup"><span data-stu-id="27540-260">Operations for nonconformances</span></span>](../quality-operations.md)
- [<span data-ttu-id="27540-261">Gestione qualità per i processi di magazzino</span><span class="sxs-lookup"><span data-stu-id="27540-261">Quality management for warehouse processes</span></span>](../quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
