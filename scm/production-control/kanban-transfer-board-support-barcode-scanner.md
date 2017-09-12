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
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1dc40de2b77be5c5c2399fd55c3c3bd15a9f24ec
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---

# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="b9692-103">Supporto della bacheca di trasferimento kanban per i lettori di codici a barre</span><span class="sxs-lookup"><span data-stu-id="b9692-103">Kanban transfer board support for barcode scanners</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="b9692-104">La scheda di trasferimento kanban supporta l'input da uno scanner di codici a barre widget per selezionare, iniziare, completare e svuotare un processo kanban.</span><span class="sxs-lookup"><span data-stu-id="b9692-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="b9692-105">Modalità di registrazione</span><span class="sxs-lookup"><span data-stu-id="b9692-105">Registration modes</span></span>
------------------

<span data-ttu-id="b9692-106">Nella scheda dettaglio **Registrazione scanner** è possibile selezionare la modalità di registrazione, che controlla l'azione quando si digitalizza un numero di scheda kanban o si digita manualmente il numero nel campo del numero della scheda kanban.</span><span class="sxs-lookup"><span data-stu-id="b9692-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>
| <span data-ttu-id="b9692-107">Imposta modalità di registrazione</span><span class="sxs-lookup"><span data-stu-id="b9692-107">Set registration mode</span></span> | <span data-ttu-id="b9692-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9692-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b9692-109">Inizia</span><span class="sxs-lookup"><span data-stu-id="b9692-109">Start</span></span>                 | <span data-ttu-id="b9692-110">Registra un processo di trasferimento kanban come in corso.</span><span class="sxs-lookup"><span data-stu-id="b9692-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="b9692-111">Completata</span><span class="sxs-lookup"><span data-stu-id="b9692-111">Complete</span></span>              | <span data-ttu-id="b9692-112">Registra un processo di trasferimento kanban come completato.</span><span class="sxs-lookup"><span data-stu-id="b9692-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="b9692-113">Vuoto</span><span class="sxs-lookup"><span data-stu-id="b9692-113">Empty</span></span>                 | <span data-ttu-id="b9692-114">Registra l'unità movimentazione materiali a cui fa riferimento una scheda kanban come vuota.</span><span class="sxs-lookup"><span data-stu-id="b9692-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="b9692-115">Seleziona</span><span class="sxs-lookup"><span data-stu-id="b9692-115">Select</span></span>                | <span data-ttu-id="b9692-116">Registra un numero di scheda kanban e seleziona automaticamente il processo di riferimento nell'elenco di processi kanban.</span><span class="sxs-lookup"><span data-stu-id="b9692-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<a name="registration-mode-select"></a><span data-ttu-id="b9692-117">Modalità di registrazione Seleziona</span><span class="sxs-lookup"><span data-stu-id="b9692-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="b9692-118">Quando si utilizza un lettore di codice a barre per selezionare un processo, la modalità di visualizzazione della bacheca kanban cambia.</span><span class="sxs-lookup"><span data-stu-id="b9692-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="b9692-119">In questo modo, sono valide le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="b9692-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="b9692-120">Viene visualizzato solo il processo kanban sottoposto a scansione.</span><span class="sxs-lookup"><span data-stu-id="b9692-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="b9692-121">I dettagli del processo selezionato vengono visualizzati nella scheda dettaglio **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="b9692-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="b9692-122">Nella scheda dettaglio **Messaggi** vengono visualizzati i messaggi solo per il processo selezionato.</span><span class="sxs-lookup"><span data-stu-id="b9692-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="b9692-123">È possibile modificare lo stato del processo con le funzioni disponibili nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="b9692-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="b9692-124">La bacheca di trasferimento kanban continua a visualizzare solo un singolo processo durante questo intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="b9692-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="b9692-125">È possibile aggiornare le informazioni nell'elenco di processi manualmente facendo clic su **Aggiorna** (MAIUSC + F5) nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="b9692-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="b9692-126">Dopo aver aggiornato le informazioni, i risultati completi per il filtro del processo vengono nuovamente visualizzati.</span><span class="sxs-lookup"><span data-stu-id="b9692-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="b9692-127">Stato del processo e azioni possibili</span><span class="sxs-lookup"><span data-stu-id="b9692-127">Job status and possible actions</span></span>
<span data-ttu-id="b9692-128">Lo stato del processo selezionato e lo stato di tutti i processi sottoposti a pegging per i kanban evento stabiliscono se è possibile elaborare il processo ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="b9692-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="b9692-129">Nella seguente tabella vengono visualizzate le informazioni sugli stati e le attività:</span><span class="sxs-lookup"><span data-stu-id="b9692-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="b9692-130">Gli stati disponibili per i processi, o per unità movimentazione a cui i processi fanno riferimento.</span><span class="sxs-lookup"><span data-stu-id="b9692-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="b9692-131">Ogni attività che è possibile eseguire per il processo.</span><span class="sxs-lookup"><span data-stu-id="b9692-131">Each task that you can perform for the job.</span></span>

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
<th><span data-ttu-id="b9692-132">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="b9692-132">Job type</span></span></th>
<th><span data-ttu-id="b9692-133">Stato del processo o stato dell'unità movimentazione</span><span class="sxs-lookup"><span data-stu-id="b9692-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="b9692-134">Aggiorna distinta di prelievo</span><span class="sxs-lookup"><span data-stu-id="b9692-134">Update picking list</span></span></th>
<th><span data-ttu-id="b9692-135">Inizia</span><span class="sxs-lookup"><span data-stu-id="b9692-135">Start</span></span></th>
<th><span data-ttu-id="b9692-136">Aggiorna registrazione</span><span class="sxs-lookup"><span data-stu-id="b9692-136">Update registration</span></span></th>
<th><span data-ttu-id="b9692-137">Completata</span><span class="sxs-lookup"><span data-stu-id="b9692-137">Complete</span></span></th>
<th><span data-ttu-id="b9692-138">Vuoto</span><span class="sxs-lookup"><span data-stu-id="b9692-138">Empty</span></span></th>
<th><span data-ttu-id="b9692-139">Crea kanban evento</span><span class="sxs-lookup"><span data-stu-id="b9692-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b9692-140">Trasferito</span><span class="sxs-lookup"><span data-stu-id="b9692-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="b9692-141">Non pianificato</span><span class="sxs-lookup"><span data-stu-id="b9692-141">Not planned</span></span></li>
<li><span data-ttu-id="b9692-142">Non esistono processi sottoposti a pegging o i processi sottoposti a pegging sono Completati</span><span class="sxs-lookup"><span data-stu-id="b9692-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="b9692-143">Sì</span><span class="sxs-lookup"><span data-stu-id="b9692-143">Yes</span></span></td>
<td><span data-ttu-id="b9692-144">Sì</span><span class="sxs-lookup"><span data-stu-id="b9692-144">Yes</span></span></td>
<td><span data-ttu-id="b9692-145">Sì</span><span class="sxs-lookup"><span data-stu-id="b9692-145">Yes</span></span></td>
<td><span data-ttu-id="b9692-146">Sì</span><span class="sxs-lookup"><span data-stu-id="b9692-146">Yes</span></span></td>
<td><span data-ttu-id="b9692-147">No</span><span class="sxs-lookup"><span data-stu-id="b9692-147">No</span></span></td>
<td><span data-ttu-id="b9692-148">Sì</span><span class="sxs-lookup"><span data-stu-id="b9692-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b9692-149">Trasferito</span><span class="sxs-lookup"><span data-stu-id="b9692-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="b9692-150">Non pianificato</span><span class="sxs-lookup"><span data-stu-id="b9692-150">Not planned</span></span></li>
<li><span data-ttu-id="b9692-151">Il processo sottoposto a pegging non è Completato</span><span class="sxs-lookup"><span data-stu-id="b9692-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="b9692-152">Sì</span><span class="sxs-lookup"><span data-stu-id="b9692-152">Yes</span></span></td>
<td><span data-ttu-id="b9692-153">No</span><span class="sxs-lookup"><span data-stu-id="b9692-153">No</span></span></td>
<td><span data-ttu-id="b9692-154">Sì</span><span class="sxs-lookup"><span data-stu-id="b9692-154">Yes</span></span></td>
<td><span data-ttu-id="b9692-155">No</span><span class="sxs-lookup"><span data-stu-id="b9692-155">No</span></span></td>
<td><span data-ttu-id="b9692-156">No</span><span class="sxs-lookup"><span data-stu-id="b9692-156">No</span></span></td>
<td><span data-ttu-id="b9692-157">No</span><span class="sxs-lookup"><span data-stu-id="b9692-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b9692-158">Trasferito</span><span class="sxs-lookup"><span data-stu-id="b9692-158">Transfer</span></span></td>
<td><span data-ttu-id="b9692-159">In corso</span><span class="sxs-lookup"><span data-stu-id="b9692-159">In progress</span></span></td>
<td><span data-ttu-id="b9692-160">Sì</span><span class="sxs-lookup"><span data-stu-id="b9692-160">Yes</span></span></td>
<td><span data-ttu-id="b9692-161">No</span><span class="sxs-lookup"><span data-stu-id="b9692-161">No</span></span></td>
<td><span data-ttu-id="b9692-162">Sì</span><span class="sxs-lookup"><span data-stu-id="b9692-162">Yes</span></span></td>
<td><span data-ttu-id="b9692-163">Sì</span><span class="sxs-lookup"><span data-stu-id="b9692-163">Yes</span></span></td>
<td><span data-ttu-id="b9692-164">No</span><span class="sxs-lookup"><span data-stu-id="b9692-164">No</span></span></td>
<td><span data-ttu-id="b9692-165">No</span><span class="sxs-lookup"><span data-stu-id="b9692-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b9692-166">Trasferito</span><span class="sxs-lookup"><span data-stu-id="b9692-166">Transfer</span></span></td>
<td><span data-ttu-id="b9692-167">Completato</span><span class="sxs-lookup"><span data-stu-id="b9692-167">Completed</span></span></td>
<td><span data-ttu-id="b9692-168">No</span><span class="sxs-lookup"><span data-stu-id="b9692-168">No</span></span></td>
<td><span data-ttu-id="b9692-169">No</span><span class="sxs-lookup"><span data-stu-id="b9692-169">No</span></span></td>
<td><span data-ttu-id="b9692-170">No</span><span class="sxs-lookup"><span data-stu-id="b9692-170">No</span></span></td>
<td><span data-ttu-id="b9692-171">No</span><span class="sxs-lookup"><span data-stu-id="b9692-171">No</span></span></td>
<td><span data-ttu-id="b9692-172">Sì</span><span class="sxs-lookup"><span data-stu-id="b9692-172">Yes</span></span></td>
<td><span data-ttu-id="b9692-173">No</span><span class="sxs-lookup"><span data-stu-id="b9692-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b9692-174">Trasferimento o processo</span><span class="sxs-lookup"><span data-stu-id="b9692-174">Transfer or process</span></span></td>
<td><span data-ttu-id="b9692-175">Vuoto</span><span class="sxs-lookup"><span data-stu-id="b9692-175">Empty</span></span></td>
<td><span data-ttu-id="b9692-176">No</span><span class="sxs-lookup"><span data-stu-id="b9692-176">No</span></span></td>
<td><span data-ttu-id="b9692-177">No</span><span class="sxs-lookup"><span data-stu-id="b9692-177">No</span></span></td>
<td><span data-ttu-id="b9692-178">No</span><span class="sxs-lookup"><span data-stu-id="b9692-178">No</span></span></td>
<td><span data-ttu-id="b9692-179">No</span><span class="sxs-lookup"><span data-stu-id="b9692-179">No</span></span></td>
<td><span data-ttu-id="b9692-180">No</span><span class="sxs-lookup"><span data-stu-id="b9692-180">No</span></span></td>
<td><span data-ttu-id="b9692-181">No</span><span class="sxs-lookup"><span data-stu-id="b9692-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b9692-182">Trasferimento o processo</span><span class="sxs-lookup"><span data-stu-id="b9692-182">Transfer or process</span></span></td>
<td><span data-ttu-id="b9692-183">Non è stata rilevata una scheda kanban</span><span class="sxs-lookup"><span data-stu-id="b9692-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="b9692-184">Nessuna</span><span class="sxs-lookup"><span data-stu-id="b9692-184">No</span></span></td>
<td><span data-ttu-id="b9692-185">Nessuna</span><span class="sxs-lookup"><span data-stu-id="b9692-185">No</span></span></td>
<td><span data-ttu-id="b9692-186">Nessuna</span><span class="sxs-lookup"><span data-stu-id="b9692-186">No</span></span></td>
<td><span data-ttu-id="b9692-187">Nessuna</span><span class="sxs-lookup"><span data-stu-id="b9692-187">No</span></span></td>
<td><span data-ttu-id="b9692-188">Nessuna</span><span class="sxs-lookup"><span data-stu-id="b9692-188">No</span></span></td>
<td><span data-ttu-id="b9692-189">Nessuna</span><span class="sxs-lookup"><span data-stu-id="b9692-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b9692-190">Trasferimento o processo</span><span class="sxs-lookup"><span data-stu-id="b9692-190">Transfer or process</span></span></td>
<td><span data-ttu-id="b9692-191">È stata rilevata una scheda kanban, ma non è stata assegnata a un kanban</span><span class="sxs-lookup"><span data-stu-id="b9692-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="b9692-192">No</span><span class="sxs-lookup"><span data-stu-id="b9692-192">No</span></span></td>
<td><span data-ttu-id="b9692-193">No</span><span class="sxs-lookup"><span data-stu-id="b9692-193">No</span></span></td>
<td><span data-ttu-id="b9692-194">No</span><span class="sxs-lookup"><span data-stu-id="b9692-194">No</span></span></td>
<td><span data-ttu-id="b9692-195">No</span><span class="sxs-lookup"><span data-stu-id="b9692-195">No</span></span></td>
<td><span data-ttu-id="b9692-196">No</span><span class="sxs-lookup"><span data-stu-id="b9692-196">No</span></span></td>
<td><span data-ttu-id="b9692-197">No</span><span class="sxs-lookup"><span data-stu-id="b9692-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b9692-198">Elaborazione</span><span class="sxs-lookup"><span data-stu-id="b9692-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="b9692-199">Non pianificato</span><span class="sxs-lookup"><span data-stu-id="b9692-199">Not planned</span></span></li>
<li><span data-ttu-id="b9692-200">Preparato</span><span class="sxs-lookup"><span data-stu-id="b9692-200">Prepared</span></span></li>
<li><span data-ttu-id="b9692-201">In corso</span><span class="sxs-lookup"><span data-stu-id="b9692-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="b9692-202">No</span><span class="sxs-lookup"><span data-stu-id="b9692-202">No</span></span></td>
<td><span data-ttu-id="b9692-203">No</span><span class="sxs-lookup"><span data-stu-id="b9692-203">No</span></span></td>
<td><span data-ttu-id="b9692-204">No</span><span class="sxs-lookup"><span data-stu-id="b9692-204">No</span></span></td>
<td><span data-ttu-id="b9692-205">No</span><span class="sxs-lookup"><span data-stu-id="b9692-205">No</span></span></td>
<td><span data-ttu-id="b9692-206">No</span><span class="sxs-lookup"><span data-stu-id="b9692-206">No</span></span></td>
<td><span data-ttu-id="b9692-207">No</span><span class="sxs-lookup"><span data-stu-id="b9692-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b9692-208">Elaborazione</span><span class="sxs-lookup"><span data-stu-id="b9692-208">Process</span></span></td>
<td><span data-ttu-id="b9692-209">Completato</span><span class="sxs-lookup"><span data-stu-id="b9692-209">Completed</span></span></td>
<td><span data-ttu-id="b9692-210">No</span><span class="sxs-lookup"><span data-stu-id="b9692-210">No</span></span></td>
<td><span data-ttu-id="b9692-211">No</span><span class="sxs-lookup"><span data-stu-id="b9692-211">No</span></span></td>
<td><span data-ttu-id="b9692-212">No</span><span class="sxs-lookup"><span data-stu-id="b9692-212">No</span></span></td>
<td><span data-ttu-id="b9692-213">No</span><span class="sxs-lookup"><span data-stu-id="b9692-213">No</span></span></td>
<td><span data-ttu-id="b9692-214">No</span><span class="sxs-lookup"><span data-stu-id="b9692-214">No</span></span></td>
<td><span data-ttu-id="b9692-215">No</span><span class="sxs-lookup"><span data-stu-id="b9692-215">No</span></span></td>
</tr>
</tbody>
</table>






