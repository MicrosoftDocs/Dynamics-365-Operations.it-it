---
title: Supporto della bacheca di trasferimento kanban per i lettori di codici a barre
description: La scheda di trasferimento kanban supporta l'input da uno scanner di codici a barre widget per selezionare, iniziare, completare e svuotare un processo kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: e63a33af63144b78d0c375022b9802e11c255598
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="407d6-103">Supporto della bacheca di trasferimento kanban per i lettori di codici a barre</span><span class="sxs-lookup"><span data-stu-id="407d6-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="407d6-104">La scheda di trasferimento kanban supporta l'input da uno scanner di codici a barre widget per selezionare, iniziare, completare e svuotare un processo kanban.</span><span class="sxs-lookup"><span data-stu-id="407d6-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="407d6-105">Modalità di registrazione</span><span class="sxs-lookup"><span data-stu-id="407d6-105">Registration modes</span></span>
------------------

<span data-ttu-id="407d6-106">Nella scheda dettaglio **Registrazione scanner** è possibile selezionare la modalità di registrazione, che controlla l'azione quando si digitalizza un numero di scheda kanban o si digita manualmente il numero nel campo del numero della scheda kanban.</span><span class="sxs-lookup"><span data-stu-id="407d6-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="407d6-107">Imposta modalità di registrazione</span><span class="sxs-lookup"><span data-stu-id="407d6-107">Set registration mode</span></span> | <span data-ttu-id="407d6-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="407d6-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="407d6-109">Inizia</span><span class="sxs-lookup"><span data-stu-id="407d6-109">Start</span></span>                 | <span data-ttu-id="407d6-110">Registra un processo di trasferimento kanban come in corso.</span><span class="sxs-lookup"><span data-stu-id="407d6-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="407d6-111">Completata</span><span class="sxs-lookup"><span data-stu-id="407d6-111">Complete</span></span>              | <span data-ttu-id="407d6-112">Registra un processo di trasferimento kanban come completato.</span><span class="sxs-lookup"><span data-stu-id="407d6-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="407d6-113">Vuoto</span><span class="sxs-lookup"><span data-stu-id="407d6-113">Empty</span></span>                 | <span data-ttu-id="407d6-114">Registra l'unità movimentazione materiali a cui fa riferimento una scheda kanban come vuota.</span><span class="sxs-lookup"><span data-stu-id="407d6-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="407d6-115">Seleziona</span><span class="sxs-lookup"><span data-stu-id="407d6-115">Select</span></span>                | <span data-ttu-id="407d6-116">Registra un numero di scheda kanban e seleziona automaticamente il processo di riferimento nell'elenco di processi kanban.</span><span class="sxs-lookup"><span data-stu-id="407d6-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<a name="registration-mode-select"></a><span data-ttu-id="407d6-117">Modalità di registrazione Seleziona</span><span class="sxs-lookup"><span data-stu-id="407d6-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="407d6-118">Quando si utilizza un lettore di codice a barre per selezionare un processo, la modalità di visualizzazione della bacheca kanban cambia.</span><span class="sxs-lookup"><span data-stu-id="407d6-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="407d6-119">In questo modo, sono valide le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="407d6-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="407d6-120">Viene visualizzato solo il processo kanban sottoposto a scansione.</span><span class="sxs-lookup"><span data-stu-id="407d6-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="407d6-121">I dettagli del processo selezionato vengono visualizzati nella scheda dettaglio **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="407d6-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="407d6-122">Nella scheda dettaglio **Messaggi** vengono visualizzati i messaggi solo per il processo selezionato.</span><span class="sxs-lookup"><span data-stu-id="407d6-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="407d6-123">È possibile modificare lo stato del processo con le funzioni disponibili nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="407d6-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="407d6-124">La bacheca di trasferimento kanban continua a visualizzare solo un singolo processo durante questo intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="407d6-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="407d6-125">È possibile aggiornare le informazioni nell'elenco di processi manualmente facendo clic su **Aggiorna** (MAIUSC + F5) nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="407d6-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="407d6-126">Dopo aver aggiornato le informazioni, i risultati completi per il filtro del processo vengono nuovamente visualizzati.</span><span class="sxs-lookup"><span data-stu-id="407d6-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="407d6-127">Stato del processo e azioni possibili</span><span class="sxs-lookup"><span data-stu-id="407d6-127">Job status and possible actions</span></span>
<span data-ttu-id="407d6-128">Lo stato del processo selezionato e lo stato di tutti i processi sottoposti a pegging per i kanban evento stabiliscono se è possibile elaborare il processo ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="407d6-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="407d6-129">Nella seguente tabella vengono visualizzate le informazioni sugli stati e le attività:</span><span class="sxs-lookup"><span data-stu-id="407d6-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="407d6-130">Gli stati disponibili per i processi, o per unità movimentazione a cui i processi fanno riferimento.</span><span class="sxs-lookup"><span data-stu-id="407d6-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="407d6-131">Ogni attività che è possibile eseguire per il processo.</span><span class="sxs-lookup"><span data-stu-id="407d6-131">Each task that you can perform for the job.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="407d6-132">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="407d6-132">Job type</span></span></th>
<th><span data-ttu-id="407d6-133">Stato del processo o stato dell'unità movimentazione</span><span class="sxs-lookup"><span data-stu-id="407d6-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="407d6-134">Aggiorna distinta di prelievo</span><span class="sxs-lookup"><span data-stu-id="407d6-134">Update picking list</span></span></th>
<th><span data-ttu-id="407d6-135">Inizia</span><span class="sxs-lookup"><span data-stu-id="407d6-135">Start</span></span></th>
<th><span data-ttu-id="407d6-136">Aggiorna registrazione</span><span class="sxs-lookup"><span data-stu-id="407d6-136">Update registration</span></span></th>
<th><span data-ttu-id="407d6-137">Completata</span><span class="sxs-lookup"><span data-stu-id="407d6-137">Complete</span></span></th>
<th><span data-ttu-id="407d6-138">Vuoto</span><span class="sxs-lookup"><span data-stu-id="407d6-138">Empty</span></span></th>
<th><span data-ttu-id="407d6-139">Crea kanban evento</span><span class="sxs-lookup"><span data-stu-id="407d6-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="407d6-140">Trasferito</span><span class="sxs-lookup"><span data-stu-id="407d6-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="407d6-141">Non pianificato</span><span class="sxs-lookup"><span data-stu-id="407d6-141">Not planned</span></span></li>
<li><span data-ttu-id="407d6-142">Non esistono processi sottoposti a pegging o i processi sottoposti a pegging sono Completati</span><span class="sxs-lookup"><span data-stu-id="407d6-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="407d6-143">Sì</span><span class="sxs-lookup"><span data-stu-id="407d6-143">Yes</span></span></td>
<td><span data-ttu-id="407d6-144">Sì</span><span class="sxs-lookup"><span data-stu-id="407d6-144">Yes</span></span></td>
<td><span data-ttu-id="407d6-145">Sì</span><span class="sxs-lookup"><span data-stu-id="407d6-145">Yes</span></span></td>
<td><span data-ttu-id="407d6-146">Sì</span><span class="sxs-lookup"><span data-stu-id="407d6-146">Yes</span></span></td>
<td><span data-ttu-id="407d6-147">No</span><span class="sxs-lookup"><span data-stu-id="407d6-147">No</span></span></td>
<td><span data-ttu-id="407d6-148">Sì</span><span class="sxs-lookup"><span data-stu-id="407d6-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="407d6-149">Trasferito</span><span class="sxs-lookup"><span data-stu-id="407d6-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="407d6-150">Non pianificato</span><span class="sxs-lookup"><span data-stu-id="407d6-150">Not planned</span></span></li>
<li><span data-ttu-id="407d6-151">Il processo sottoposto a pegging non è Completato</span><span class="sxs-lookup"><span data-stu-id="407d6-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="407d6-152">Sì</span><span class="sxs-lookup"><span data-stu-id="407d6-152">Yes</span></span></td>
<td><span data-ttu-id="407d6-153">No</span><span class="sxs-lookup"><span data-stu-id="407d6-153">No</span></span></td>
<td><span data-ttu-id="407d6-154">Sì</span><span class="sxs-lookup"><span data-stu-id="407d6-154">Yes</span></span></td>
<td><span data-ttu-id="407d6-155">No</span><span class="sxs-lookup"><span data-stu-id="407d6-155">No</span></span></td>
<td><span data-ttu-id="407d6-156">No</span><span class="sxs-lookup"><span data-stu-id="407d6-156">No</span></span></td>
<td><span data-ttu-id="407d6-157">No</span><span class="sxs-lookup"><span data-stu-id="407d6-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="407d6-158">Trasferito</span><span class="sxs-lookup"><span data-stu-id="407d6-158">Transfer</span></span></td>
<td><span data-ttu-id="407d6-159">In corso</span><span class="sxs-lookup"><span data-stu-id="407d6-159">In progress</span></span></td>
<td><span data-ttu-id="407d6-160">Sì</span><span class="sxs-lookup"><span data-stu-id="407d6-160">Yes</span></span></td>
<td><span data-ttu-id="407d6-161">No</span><span class="sxs-lookup"><span data-stu-id="407d6-161">No</span></span></td>
<td><span data-ttu-id="407d6-162">Sì</span><span class="sxs-lookup"><span data-stu-id="407d6-162">Yes</span></span></td>
<td><span data-ttu-id="407d6-163">Sì</span><span class="sxs-lookup"><span data-stu-id="407d6-163">Yes</span></span></td>
<td><span data-ttu-id="407d6-164">No</span><span class="sxs-lookup"><span data-stu-id="407d6-164">No</span></span></td>
<td><span data-ttu-id="407d6-165">No</span><span class="sxs-lookup"><span data-stu-id="407d6-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="407d6-166">Trasferito</span><span class="sxs-lookup"><span data-stu-id="407d6-166">Transfer</span></span></td>
<td><span data-ttu-id="407d6-167">Completato</span><span class="sxs-lookup"><span data-stu-id="407d6-167">Completed</span></span></td>
<td><span data-ttu-id="407d6-168">No</span><span class="sxs-lookup"><span data-stu-id="407d6-168">No</span></span></td>
<td><span data-ttu-id="407d6-169">No</span><span class="sxs-lookup"><span data-stu-id="407d6-169">No</span></span></td>
<td><span data-ttu-id="407d6-170">No</span><span class="sxs-lookup"><span data-stu-id="407d6-170">No</span></span></td>
<td><span data-ttu-id="407d6-171">No</span><span class="sxs-lookup"><span data-stu-id="407d6-171">No</span></span></td>
<td><span data-ttu-id="407d6-172">Sì</span><span class="sxs-lookup"><span data-stu-id="407d6-172">Yes</span></span></td>
<td><span data-ttu-id="407d6-173">No</span><span class="sxs-lookup"><span data-stu-id="407d6-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="407d6-174">Trasferimento o processo</span><span class="sxs-lookup"><span data-stu-id="407d6-174">Transfer or process</span></span></td>
<td><span data-ttu-id="407d6-175">Vuoto</span><span class="sxs-lookup"><span data-stu-id="407d6-175">Empty</span></span></td>
<td><span data-ttu-id="407d6-176">No</span><span class="sxs-lookup"><span data-stu-id="407d6-176">No</span></span></td>
<td><span data-ttu-id="407d6-177">No</span><span class="sxs-lookup"><span data-stu-id="407d6-177">No</span></span></td>
<td><span data-ttu-id="407d6-178">No</span><span class="sxs-lookup"><span data-stu-id="407d6-178">No</span></span></td>
<td><span data-ttu-id="407d6-179">No</span><span class="sxs-lookup"><span data-stu-id="407d6-179">No</span></span></td>
<td><span data-ttu-id="407d6-180">No</span><span class="sxs-lookup"><span data-stu-id="407d6-180">No</span></span></td>
<td><span data-ttu-id="407d6-181">No</span><span class="sxs-lookup"><span data-stu-id="407d6-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="407d6-182">Trasferimento o processo</span><span class="sxs-lookup"><span data-stu-id="407d6-182">Transfer or process</span></span></td>
<td><span data-ttu-id="407d6-183">Non è stata rilevata una scheda kanban</span><span class="sxs-lookup"><span data-stu-id="407d6-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="407d6-184">Nessuna</span><span class="sxs-lookup"><span data-stu-id="407d6-184">No</span></span></td>
<td><span data-ttu-id="407d6-185">Nessuna</span><span class="sxs-lookup"><span data-stu-id="407d6-185">No</span></span></td>
<td><span data-ttu-id="407d6-186">Nessuna</span><span class="sxs-lookup"><span data-stu-id="407d6-186">No</span></span></td>
<td><span data-ttu-id="407d6-187">Nessuna</span><span class="sxs-lookup"><span data-stu-id="407d6-187">No</span></span></td>
<td><span data-ttu-id="407d6-188">Nessuna</span><span class="sxs-lookup"><span data-stu-id="407d6-188">No</span></span></td>
<td><span data-ttu-id="407d6-189">Nessuna</span><span class="sxs-lookup"><span data-stu-id="407d6-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="407d6-190">Trasferimento o processo</span><span class="sxs-lookup"><span data-stu-id="407d6-190">Transfer or process</span></span></td>
<td><span data-ttu-id="407d6-191">È stata rilevata una scheda kanban, ma non è stata assegnata a un kanban</span><span class="sxs-lookup"><span data-stu-id="407d6-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="407d6-192">No</span><span class="sxs-lookup"><span data-stu-id="407d6-192">No</span></span></td>
<td><span data-ttu-id="407d6-193">No</span><span class="sxs-lookup"><span data-stu-id="407d6-193">No</span></span></td>
<td><span data-ttu-id="407d6-194">No</span><span class="sxs-lookup"><span data-stu-id="407d6-194">No</span></span></td>
<td><span data-ttu-id="407d6-195">No</span><span class="sxs-lookup"><span data-stu-id="407d6-195">No</span></span></td>
<td><span data-ttu-id="407d6-196">No</span><span class="sxs-lookup"><span data-stu-id="407d6-196">No</span></span></td>
<td><span data-ttu-id="407d6-197">No</span><span class="sxs-lookup"><span data-stu-id="407d6-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="407d6-198">Elaborazione</span><span class="sxs-lookup"><span data-stu-id="407d6-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="407d6-199">Non pianificato</span><span class="sxs-lookup"><span data-stu-id="407d6-199">Not planned</span></span></li>
<li><span data-ttu-id="407d6-200">Preparato</span><span class="sxs-lookup"><span data-stu-id="407d6-200">Prepared</span></span></li>
<li><span data-ttu-id="407d6-201">In corso</span><span class="sxs-lookup"><span data-stu-id="407d6-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="407d6-202">No</span><span class="sxs-lookup"><span data-stu-id="407d6-202">No</span></span></td>
<td><span data-ttu-id="407d6-203">No</span><span class="sxs-lookup"><span data-stu-id="407d6-203">No</span></span></td>
<td><span data-ttu-id="407d6-204">No</span><span class="sxs-lookup"><span data-stu-id="407d6-204">No</span></span></td>
<td><span data-ttu-id="407d6-205">No</span><span class="sxs-lookup"><span data-stu-id="407d6-205">No</span></span></td>
<td><span data-ttu-id="407d6-206">No</span><span class="sxs-lookup"><span data-stu-id="407d6-206">No</span></span></td>
<td><span data-ttu-id="407d6-207">No</span><span class="sxs-lookup"><span data-stu-id="407d6-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="407d6-208">Elaborazione</span><span class="sxs-lookup"><span data-stu-id="407d6-208">Process</span></span></td>
<td><span data-ttu-id="407d6-209">Completato</span><span class="sxs-lookup"><span data-stu-id="407d6-209">Completed</span></span></td>
<td><span data-ttu-id="407d6-210">No</span><span class="sxs-lookup"><span data-stu-id="407d6-210">No</span></span></td>
<td><span data-ttu-id="407d6-211">No</span><span class="sxs-lookup"><span data-stu-id="407d6-211">No</span></span></td>
<td><span data-ttu-id="407d6-212">No</span><span class="sxs-lookup"><span data-stu-id="407d6-212">No</span></span></td>
<td><span data-ttu-id="407d6-213">No</span><span class="sxs-lookup"><span data-stu-id="407d6-213">No</span></span></td>
<td><span data-ttu-id="407d6-214">No</span><span class="sxs-lookup"><span data-stu-id="407d6-214">No</span></span></td>
<td><span data-ttu-id="407d6-215">No</span><span class="sxs-lookup"><span data-stu-id="407d6-215">No</span></span></td>
</tr>
</tbody>
</table>






