---
title: Supporto della bacheca di trasferimento kanban per i lettori di codici a barre
description: La scheda di trasferimento kanban supporta l'input da uno scanner di codici a barre widget per selezionare, iniziare, completare e svuotare un processo kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
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
ms.openlocfilehash: e63a33af63144b78d0c375022b9802e11c255598
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569219"
---
# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="2cc1e-103">Supporto della bacheca di trasferimento kanban per i lettori di codici a barre</span><span class="sxs-lookup"><span data-stu-id="2cc1e-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2cc1e-104">La scheda di trasferimento kanban supporta l'input da uno scanner di codici a barre widget per selezionare, iniziare, completare e svuotare un processo kanban.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="2cc1e-105">Modalità di registrazione</span><span class="sxs-lookup"><span data-stu-id="2cc1e-105">Registration modes</span></span>
------------------

<span data-ttu-id="2cc1e-106">Nella scheda dettaglio **Registrazione scanner** è possibile selezionare la modalità di registrazione, che controlla l'azione quando si digitalizza un numero di scheda kanban o si digita manualmente il numero nel campo del numero della scheda kanban.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="2cc1e-107">Imposta modalità di registrazione</span><span class="sxs-lookup"><span data-stu-id="2cc1e-107">Set registration mode</span></span> | <span data-ttu-id="2cc1e-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2cc1e-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2cc1e-109">Inizia</span><span class="sxs-lookup"><span data-stu-id="2cc1e-109">Start</span></span>                 | <span data-ttu-id="2cc1e-110">Registra un processo di trasferimento kanban come in corso.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="2cc1e-111">Completata</span><span class="sxs-lookup"><span data-stu-id="2cc1e-111">Complete</span></span>              | <span data-ttu-id="2cc1e-112">Registra un processo di trasferimento kanban come completato.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="2cc1e-113">Vuoto</span><span class="sxs-lookup"><span data-stu-id="2cc1e-113">Empty</span></span>                 | <span data-ttu-id="2cc1e-114">Registra l'unità movimentazione materiali a cui fa riferimento una scheda kanban come vuota.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="2cc1e-115">Seleziona</span><span class="sxs-lookup"><span data-stu-id="2cc1e-115">Select</span></span>                | <span data-ttu-id="2cc1e-116">Registra un numero di scheda kanban e seleziona automaticamente il processo di riferimento nell'elenco di processi kanban.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<span data-ttu-id="2cc1e-117">Modalità di registrazione Seleziona</span><span class="sxs-lookup"><span data-stu-id="2cc1e-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="2cc1e-118">Quando si utilizza un lettore di codice a barre per selezionare un processo, la modalità di visualizzazione della bacheca kanban cambia.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span><span data-ttu-id="2cc1e-119"> In questo modo, sono valide le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="2cc1e-119"> In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="2cc1e-120">Viene visualizzato solo il processo kanban sottoposto a scansione.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="2cc1e-121">I dettagli del processo selezionato vengono visualizzati nella scheda dettaglio **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="2cc1e-122">Nella scheda dettaglio **Messaggi** vengono visualizzati i messaggi solo per il processo selezionato.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="2cc1e-123">È possibile modificare lo stato del processo con le funzioni disponibili nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="2cc1e-124">La bacheca di trasferimento kanban continua a visualizzare solo un singolo processo durante questo intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="2cc1e-125">È possibile aggiornare le informazioni nell'elenco di processi manualmente facendo clic su **Aggiorna** (MAIUSC + F5) nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="2cc1e-126">Dopo aver aggiornato le informazioni, i risultati completi per il filtro del processo vengono nuovamente visualizzati.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="2cc1e-127">Stato del processo e azioni possibili</span><span class="sxs-lookup"><span data-stu-id="2cc1e-127">Job status and possible actions</span></span>
<span data-ttu-id="2cc1e-128">Lo stato del processo selezionato e lo stato di tutti i processi sottoposti a pegging per i kanban evento stabiliscono se è possibile elaborare il processo ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="2cc1e-129">Nella seguente tabella vengono visualizzate le informazioni sugli stati e le attività:</span><span class="sxs-lookup"><span data-stu-id="2cc1e-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="2cc1e-130">Gli stati disponibili per i processi, o per unità movimentazione a cui i processi fanno riferimento.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="2cc1e-131">Ogni attività che è possibile eseguire per il processo.</span><span class="sxs-lookup"><span data-stu-id="2cc1e-131">Each task that you can perform for the job.</span></span>

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
<th><span data-ttu-id="2cc1e-132">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="2cc1e-132">Job type</span></span></th>
<th><span data-ttu-id="2cc1e-133">Stato del processo o stato dell'unità movimentazione</span><span class="sxs-lookup"><span data-stu-id="2cc1e-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="2cc1e-134">Aggiorna distinta di prelievo</span><span class="sxs-lookup"><span data-stu-id="2cc1e-134">Update picking list</span></span></th>
<th><span data-ttu-id="2cc1e-135">Inizia</span><span class="sxs-lookup"><span data-stu-id="2cc1e-135">Start</span></span></th>
<th><span data-ttu-id="2cc1e-136">Aggiorna registrazione</span><span class="sxs-lookup"><span data-stu-id="2cc1e-136">Update registration</span></span></th>
<th><span data-ttu-id="2cc1e-137">Completata</span><span class="sxs-lookup"><span data-stu-id="2cc1e-137">Complete</span></span></th>
<th><span data-ttu-id="2cc1e-138">Vuoto</span><span class="sxs-lookup"><span data-stu-id="2cc1e-138">Empty</span></span></th>
<th><span data-ttu-id="2cc1e-139">Crea kanban evento</span><span class="sxs-lookup"><span data-stu-id="2cc1e-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="2cc1e-140">Trasferito</span><span class="sxs-lookup"><span data-stu-id="2cc1e-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="2cc1e-141">Non pianificato</span><span class="sxs-lookup"><span data-stu-id="2cc1e-141">Not planned</span></span></li>
<li><span data-ttu-id="2cc1e-142">Non esistono processi sottoposti a pegging o i processi sottoposti a pegging sono Completati</span><span class="sxs-lookup"><span data-stu-id="2cc1e-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="2cc1e-143">Sì</span><span class="sxs-lookup"><span data-stu-id="2cc1e-143">Yes</span></span></td>
<td><span data-ttu-id="2cc1e-144">Sì</span><span class="sxs-lookup"><span data-stu-id="2cc1e-144">Yes</span></span></td>
<td><span data-ttu-id="2cc1e-145">Sì</span><span class="sxs-lookup"><span data-stu-id="2cc1e-145">Yes</span></span></td>
<td><span data-ttu-id="2cc1e-146">Sì</span><span class="sxs-lookup"><span data-stu-id="2cc1e-146">Yes</span></span></td>
<td><span data-ttu-id="2cc1e-147">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-147">No</span></span></td>
<td><span data-ttu-id="2cc1e-148">Sì</span><span class="sxs-lookup"><span data-stu-id="2cc1e-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2cc1e-149">Trasferito</span><span class="sxs-lookup"><span data-stu-id="2cc1e-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="2cc1e-150">Non pianificato</span><span class="sxs-lookup"><span data-stu-id="2cc1e-150">Not planned</span></span></li>
<li><span data-ttu-id="2cc1e-151">Il processo sottoposto a pegging non è Completato</span><span class="sxs-lookup"><span data-stu-id="2cc1e-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="2cc1e-152">Sì</span><span class="sxs-lookup"><span data-stu-id="2cc1e-152">Yes</span></span></td>
<td><span data-ttu-id="2cc1e-153">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-153">No</span></span></td>
<td><span data-ttu-id="2cc1e-154">Sì</span><span class="sxs-lookup"><span data-stu-id="2cc1e-154">Yes</span></span></td>
<td><span data-ttu-id="2cc1e-155">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-155">No</span></span></td>
<td><span data-ttu-id="2cc1e-156">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-156">No</span></span></td>
<td><span data-ttu-id="2cc1e-157">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2cc1e-158">Trasferito</span><span class="sxs-lookup"><span data-stu-id="2cc1e-158">Transfer</span></span></td>
<td><span data-ttu-id="2cc1e-159">In corso</span><span class="sxs-lookup"><span data-stu-id="2cc1e-159">In progress</span></span></td>
<td><span data-ttu-id="2cc1e-160">Sì</span><span class="sxs-lookup"><span data-stu-id="2cc1e-160">Yes</span></span></td>
<td><span data-ttu-id="2cc1e-161">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-161">No</span></span></td>
<td><span data-ttu-id="2cc1e-162">Sì</span><span class="sxs-lookup"><span data-stu-id="2cc1e-162">Yes</span></span></td>
<td><span data-ttu-id="2cc1e-163">Sì</span><span class="sxs-lookup"><span data-stu-id="2cc1e-163">Yes</span></span></td>
<td><span data-ttu-id="2cc1e-164">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-164">No</span></span></td>
<td><span data-ttu-id="2cc1e-165">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2cc1e-166">Trasferito</span><span class="sxs-lookup"><span data-stu-id="2cc1e-166">Transfer</span></span></td>
<td><span data-ttu-id="2cc1e-167">Completato</span><span class="sxs-lookup"><span data-stu-id="2cc1e-167">Completed</span></span></td>
<td><span data-ttu-id="2cc1e-168">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-168">No</span></span></td>
<td><span data-ttu-id="2cc1e-169">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-169">No</span></span></td>
<td><span data-ttu-id="2cc1e-170">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-170">No</span></span></td>
<td><span data-ttu-id="2cc1e-171">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-171">No</span></span></td>
<td><span data-ttu-id="2cc1e-172">Sì</span><span class="sxs-lookup"><span data-stu-id="2cc1e-172">Yes</span></span></td>
<td><span data-ttu-id="2cc1e-173">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2cc1e-174">Trasferimento o processo</span><span class="sxs-lookup"><span data-stu-id="2cc1e-174">Transfer or process</span></span></td>
<td><span data-ttu-id="2cc1e-175">Vuoto</span><span class="sxs-lookup"><span data-stu-id="2cc1e-175">Empty</span></span></td>
<td><span data-ttu-id="2cc1e-176">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-176">No</span></span></td>
<td><span data-ttu-id="2cc1e-177">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-177">No</span></span></td>
<td><span data-ttu-id="2cc1e-178">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-178">No</span></span></td>
<td><span data-ttu-id="2cc1e-179">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-179">No</span></span></td>
<td><span data-ttu-id="2cc1e-180">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-180">No</span></span></td>
<td><span data-ttu-id="2cc1e-181">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2cc1e-182">Trasferimento o processo</span><span class="sxs-lookup"><span data-stu-id="2cc1e-182">Transfer or process</span></span></td>
<td><span data-ttu-id="2cc1e-183">Non è stata rilevata una scheda kanban</span><span class="sxs-lookup"><span data-stu-id="2cc1e-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="2cc1e-184">Nessuna</span><span class="sxs-lookup"><span data-stu-id="2cc1e-184">No</span></span></td>
<td><span data-ttu-id="2cc1e-185">Nessuna</span><span class="sxs-lookup"><span data-stu-id="2cc1e-185">No</span></span></td>
<td><span data-ttu-id="2cc1e-186">Nessuna</span><span class="sxs-lookup"><span data-stu-id="2cc1e-186">No</span></span></td>
<td><span data-ttu-id="2cc1e-187">Nessuna</span><span class="sxs-lookup"><span data-stu-id="2cc1e-187">No</span></span></td>
<td><span data-ttu-id="2cc1e-188">Nessuna</span><span class="sxs-lookup"><span data-stu-id="2cc1e-188">No</span></span></td>
<td><span data-ttu-id="2cc1e-189">Nessuna</span><span class="sxs-lookup"><span data-stu-id="2cc1e-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2cc1e-190">Trasferimento o processo</span><span class="sxs-lookup"><span data-stu-id="2cc1e-190">Transfer or process</span></span></td>
<td><span data-ttu-id="2cc1e-191">È stata rilevata una scheda kanban, ma non è stata assegnata a un kanban</span><span class="sxs-lookup"><span data-stu-id="2cc1e-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="2cc1e-192">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-192">No</span></span></td>
<td><span data-ttu-id="2cc1e-193">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-193">No</span></span></td>
<td><span data-ttu-id="2cc1e-194">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-194">No</span></span></td>
<td><span data-ttu-id="2cc1e-195">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-195">No</span></span></td>
<td><span data-ttu-id="2cc1e-196">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-196">No</span></span></td>
<td><span data-ttu-id="2cc1e-197">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2cc1e-198">Elaborazione</span><span class="sxs-lookup"><span data-stu-id="2cc1e-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="2cc1e-199">Non pianificato</span><span class="sxs-lookup"><span data-stu-id="2cc1e-199">Not planned</span></span></li>
<li><span data-ttu-id="2cc1e-200">Preparato</span><span class="sxs-lookup"><span data-stu-id="2cc1e-200">Prepared</span></span></li>
<li><span data-ttu-id="2cc1e-201">In corso</span><span class="sxs-lookup"><span data-stu-id="2cc1e-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="2cc1e-202">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-202">No</span></span></td>
<td><span data-ttu-id="2cc1e-203">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-203">No</span></span></td>
<td><span data-ttu-id="2cc1e-204">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-204">No</span></span></td>
<td><span data-ttu-id="2cc1e-205">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-205">No</span></span></td>
<td><span data-ttu-id="2cc1e-206">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-206">No</span></span></td>
<td><span data-ttu-id="2cc1e-207">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2cc1e-208">Elaborazione</span><span class="sxs-lookup"><span data-stu-id="2cc1e-208">Process</span></span></td>
<td><span data-ttu-id="2cc1e-209">Completato</span><span class="sxs-lookup"><span data-stu-id="2cc1e-209">Completed</span></span></td>
<td><span data-ttu-id="2cc1e-210">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-210">No</span></span></td>
<td><span data-ttu-id="2cc1e-211">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-211">No</span></span></td>
<td><span data-ttu-id="2cc1e-212">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-212">No</span></span></td>
<td><span data-ttu-id="2cc1e-213">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-213">No</span></span></td>
<td><span data-ttu-id="2cc1e-214">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-214">No</span></span></td>
<td><span data-ttu-id="2cc1e-215">No</span><span class="sxs-lookup"><span data-stu-id="2cc1e-215">No</span></span></td>
</tr>
</tbody>
</table>





