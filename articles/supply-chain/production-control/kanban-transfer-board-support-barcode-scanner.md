---
title: Supporto della bacheca di trasferimento kanban per i lettori di codici a barre
description: La scheda di trasferimento kanban supporta l'input da uno scanner di codici a barre widget per selezionare, iniziare, completare e svuotare un processo kanban.
author: ChristianRytt
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b6d65430d09c293fd5bca032b8b0e88c971d5a9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246095"
---
# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="57940-103">Supporto della bacheca di trasferimento kanban per i lettori di codici a barre</span><span class="sxs-lookup"><span data-stu-id="57940-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57940-104">La scheda di trasferimento kanban supporta l'input da uno scanner di codici a barre widget per selezionare, iniziare, completare e svuotare un processo kanban.</span><span class="sxs-lookup"><span data-stu-id="57940-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="57940-105">Modalità di registrazione</span><span class="sxs-lookup"><span data-stu-id="57940-105">Registration modes</span></span>
------------------

<span data-ttu-id="57940-106">Nella scheda dettaglio **Registrazione scanner** è possibile selezionare la modalità di registrazione, che controlla l'azione quando si digitalizza un numero di scheda kanban o si digita manualmente il numero nel campo del numero della scheda kanban.</span><span class="sxs-lookup"><span data-stu-id="57940-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="57940-107">Imposta modalità di registrazione</span><span class="sxs-lookup"><span data-stu-id="57940-107">Set registration mode</span></span> | <span data-ttu-id="57940-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57940-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="57940-109">Inizia</span><span class="sxs-lookup"><span data-stu-id="57940-109">Start</span></span>                 | <span data-ttu-id="57940-110">Registra un processo di trasferimento kanban come in corso.</span><span class="sxs-lookup"><span data-stu-id="57940-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="57940-111">Completata</span><span class="sxs-lookup"><span data-stu-id="57940-111">Complete</span></span>              | <span data-ttu-id="57940-112">Registra un processo di trasferimento kanban come completato.</span><span class="sxs-lookup"><span data-stu-id="57940-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="57940-113">Vuoto</span><span class="sxs-lookup"><span data-stu-id="57940-113">Empty</span></span>                 | <span data-ttu-id="57940-114">Registra l'unità movimentazione materiali a cui fa riferimento una scheda kanban come vuota.</span><span class="sxs-lookup"><span data-stu-id="57940-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="57940-115">Seleziona</span><span class="sxs-lookup"><span data-stu-id="57940-115">Select</span></span>                | <span data-ttu-id="57940-116">Registra un numero di scheda kanban e seleziona automaticamente il processo di riferimento nell'elenco di processi kanban.</span><span class="sxs-lookup"><span data-stu-id="57940-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<a name="registration-mode-select"></a><span data-ttu-id="57940-117">Modalità di registrazione Seleziona</span><span class="sxs-lookup"><span data-stu-id="57940-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="57940-118">Quando si utilizza un lettore di codice a barre per selezionare un processo, la modalità di visualizzazione della bacheca kanban cambia.</span><span class="sxs-lookup"><span data-stu-id="57940-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="57940-119">In questa modalità, sono valide le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="57940-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="57940-120">Viene visualizzato solo il processo kanban sottoposto a scansione.</span><span class="sxs-lookup"><span data-stu-id="57940-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="57940-121">I dettagli del processo selezionato vengono visualizzati nella scheda dettaglio **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="57940-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="57940-122">Nella scheda dettaglio **Messaggi** vengono visualizzati i messaggi solo per il processo selezionato.</span><span class="sxs-lookup"><span data-stu-id="57940-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="57940-123">È possibile modificare lo stato del processo con le funzioni disponibili nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="57940-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="57940-124">La bacheca di trasferimento kanban continua a visualizzare solo un singolo processo durante questo intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="57940-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="57940-125">È possibile aggiornare le informazioni nell'elenco di processi manualmente facendo clic su **Aggiorna** (MAIUSC + F5) nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="57940-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="57940-126">Dopo aver aggiornato le informazioni, i risultati completi per il filtro del processo vengono nuovamente visualizzati.</span><span class="sxs-lookup"><span data-stu-id="57940-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="57940-127">Stato del processo e azioni possibili</span><span class="sxs-lookup"><span data-stu-id="57940-127">Job status and possible actions</span></span>
<span data-ttu-id="57940-128">Lo stato del processo selezionato e lo stato di tutti i processi sottoposti a pegging per i kanban evento stabiliscono se è possibile elaborare il processo ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="57940-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="57940-129">Nella seguente tabella vengono visualizzate le informazioni sugli stati e le attività:</span><span class="sxs-lookup"><span data-stu-id="57940-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="57940-130">Gli stati disponibili per i processi, o per unità movimentazione a cui i processi fanno riferimento.</span><span class="sxs-lookup"><span data-stu-id="57940-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="57940-131">Ogni attività che è possibile eseguire per il processo.</span><span class="sxs-lookup"><span data-stu-id="57940-131">Each task that you can perform for the job.</span></span>

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
<th><span data-ttu-id="57940-132">Tipo di processo</span><span class="sxs-lookup"><span data-stu-id="57940-132">Job type</span></span></th>
<th><span data-ttu-id="57940-133">Stato del processo o stato dell'unità movimentazione</span><span class="sxs-lookup"><span data-stu-id="57940-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="57940-134">Aggiorna distinta di prelievo</span><span class="sxs-lookup"><span data-stu-id="57940-134">Update picking list</span></span></th>
<th><span data-ttu-id="57940-135">Inizia</span><span class="sxs-lookup"><span data-stu-id="57940-135">Start</span></span></th>
<th><span data-ttu-id="57940-136">Aggiorna registrazione</span><span class="sxs-lookup"><span data-stu-id="57940-136">Update registration</span></span></th>
<th><span data-ttu-id="57940-137">Completata</span><span class="sxs-lookup"><span data-stu-id="57940-137">Complete</span></span></th>
<th><span data-ttu-id="57940-138">Vuoto</span><span class="sxs-lookup"><span data-stu-id="57940-138">Empty</span></span></th>
<th><span data-ttu-id="57940-139">Crea kanban evento</span><span class="sxs-lookup"><span data-stu-id="57940-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="57940-140">Trasferito</span><span class="sxs-lookup"><span data-stu-id="57940-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="57940-141">Non pianificato</span><span class="sxs-lookup"><span data-stu-id="57940-141">Not planned</span></span></li>
<li><span data-ttu-id="57940-142">Non esistono processi sottoposti a pegging o i processi sottoposti a pegging sono Completati</span><span class="sxs-lookup"><span data-stu-id="57940-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="57940-143">Sì</span><span class="sxs-lookup"><span data-stu-id="57940-143">Yes</span></span></td>
<td><span data-ttu-id="57940-144">Sì</span><span class="sxs-lookup"><span data-stu-id="57940-144">Yes</span></span></td>
<td><span data-ttu-id="57940-145">Sì</span><span class="sxs-lookup"><span data-stu-id="57940-145">Yes</span></span></td>
<td><span data-ttu-id="57940-146">Sì</span><span class="sxs-lookup"><span data-stu-id="57940-146">Yes</span></span></td>
<td><span data-ttu-id="57940-147">No</span><span class="sxs-lookup"><span data-stu-id="57940-147">No</span></span></td>
<td><span data-ttu-id="57940-148">Sì</span><span class="sxs-lookup"><span data-stu-id="57940-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="57940-149">Trasferito</span><span class="sxs-lookup"><span data-stu-id="57940-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="57940-150">Non pianificato</span><span class="sxs-lookup"><span data-stu-id="57940-150">Not planned</span></span></li>
<li><span data-ttu-id="57940-151">Il processo sottoposto a pegging non è Completato</span><span class="sxs-lookup"><span data-stu-id="57940-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="57940-152">Sì</span><span class="sxs-lookup"><span data-stu-id="57940-152">Yes</span></span></td>
<td><span data-ttu-id="57940-153">No</span><span class="sxs-lookup"><span data-stu-id="57940-153">No</span></span></td>
<td><span data-ttu-id="57940-154">Sì</span><span class="sxs-lookup"><span data-stu-id="57940-154">Yes</span></span></td>
<td><span data-ttu-id="57940-155">No</span><span class="sxs-lookup"><span data-stu-id="57940-155">No</span></span></td>
<td><span data-ttu-id="57940-156">No</span><span class="sxs-lookup"><span data-stu-id="57940-156">No</span></span></td>
<td><span data-ttu-id="57940-157">No</span><span class="sxs-lookup"><span data-stu-id="57940-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="57940-158">Trasferito</span><span class="sxs-lookup"><span data-stu-id="57940-158">Transfer</span></span></td>
<td><span data-ttu-id="57940-159">In corso</span><span class="sxs-lookup"><span data-stu-id="57940-159">In progress</span></span></td>
<td><span data-ttu-id="57940-160">Sì</span><span class="sxs-lookup"><span data-stu-id="57940-160">Yes</span></span></td>
<td><span data-ttu-id="57940-161">No</span><span class="sxs-lookup"><span data-stu-id="57940-161">No</span></span></td>
<td><span data-ttu-id="57940-162">Sì</span><span class="sxs-lookup"><span data-stu-id="57940-162">Yes</span></span></td>
<td><span data-ttu-id="57940-163">Sì</span><span class="sxs-lookup"><span data-stu-id="57940-163">Yes</span></span></td>
<td><span data-ttu-id="57940-164">No</span><span class="sxs-lookup"><span data-stu-id="57940-164">No</span></span></td>
<td><span data-ttu-id="57940-165">No</span><span class="sxs-lookup"><span data-stu-id="57940-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="57940-166">Trasferito</span><span class="sxs-lookup"><span data-stu-id="57940-166">Transfer</span></span></td>
<td><span data-ttu-id="57940-167">Completato</span><span class="sxs-lookup"><span data-stu-id="57940-167">Completed</span></span></td>
<td><span data-ttu-id="57940-168">No</span><span class="sxs-lookup"><span data-stu-id="57940-168">No</span></span></td>
<td><span data-ttu-id="57940-169">No</span><span class="sxs-lookup"><span data-stu-id="57940-169">No</span></span></td>
<td><span data-ttu-id="57940-170">No</span><span class="sxs-lookup"><span data-stu-id="57940-170">No</span></span></td>
<td><span data-ttu-id="57940-171">No</span><span class="sxs-lookup"><span data-stu-id="57940-171">No</span></span></td>
<td><span data-ttu-id="57940-172">Sì</span><span class="sxs-lookup"><span data-stu-id="57940-172">Yes</span></span></td>
<td><span data-ttu-id="57940-173">No</span><span class="sxs-lookup"><span data-stu-id="57940-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="57940-174">Trasferimento o processo</span><span class="sxs-lookup"><span data-stu-id="57940-174">Transfer or process</span></span></td>
<td><span data-ttu-id="57940-175">Vuoto</span><span class="sxs-lookup"><span data-stu-id="57940-175">Empty</span></span></td>
<td><span data-ttu-id="57940-176">No</span><span class="sxs-lookup"><span data-stu-id="57940-176">No</span></span></td>
<td><span data-ttu-id="57940-177">No</span><span class="sxs-lookup"><span data-stu-id="57940-177">No</span></span></td>
<td><span data-ttu-id="57940-178">No</span><span class="sxs-lookup"><span data-stu-id="57940-178">No</span></span></td>
<td><span data-ttu-id="57940-179">No</span><span class="sxs-lookup"><span data-stu-id="57940-179">No</span></span></td>
<td><span data-ttu-id="57940-180">No</span><span class="sxs-lookup"><span data-stu-id="57940-180">No</span></span></td>
<td><span data-ttu-id="57940-181">No</span><span class="sxs-lookup"><span data-stu-id="57940-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="57940-182">Trasferimento o processo</span><span class="sxs-lookup"><span data-stu-id="57940-182">Transfer or process</span></span></td>
<td><span data-ttu-id="57940-183">Non è stata rilevata una scheda kanban</span><span class="sxs-lookup"><span data-stu-id="57940-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="57940-184">Nessuna</span><span class="sxs-lookup"><span data-stu-id="57940-184">No</span></span></td>
<td><span data-ttu-id="57940-185">Nessuna</span><span class="sxs-lookup"><span data-stu-id="57940-185">No</span></span></td>
<td><span data-ttu-id="57940-186">Nessuna</span><span class="sxs-lookup"><span data-stu-id="57940-186">No</span></span></td>
<td><span data-ttu-id="57940-187">Nessuna</span><span class="sxs-lookup"><span data-stu-id="57940-187">No</span></span></td>
<td><span data-ttu-id="57940-188">Nessuna</span><span class="sxs-lookup"><span data-stu-id="57940-188">No</span></span></td>
<td><span data-ttu-id="57940-189">Nessuna</span><span class="sxs-lookup"><span data-stu-id="57940-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="57940-190">Trasferimento o processo</span><span class="sxs-lookup"><span data-stu-id="57940-190">Transfer or process</span></span></td>
<td><span data-ttu-id="57940-191">È stata rilevata una scheda kanban, ma non è stata assegnata a un kanban</span><span class="sxs-lookup"><span data-stu-id="57940-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="57940-192">No</span><span class="sxs-lookup"><span data-stu-id="57940-192">No</span></span></td>
<td><span data-ttu-id="57940-193">No</span><span class="sxs-lookup"><span data-stu-id="57940-193">No</span></span></td>
<td><span data-ttu-id="57940-194">No</span><span class="sxs-lookup"><span data-stu-id="57940-194">No</span></span></td>
<td><span data-ttu-id="57940-195">No</span><span class="sxs-lookup"><span data-stu-id="57940-195">No</span></span></td>
<td><span data-ttu-id="57940-196">No</span><span class="sxs-lookup"><span data-stu-id="57940-196">No</span></span></td>
<td><span data-ttu-id="57940-197">No</span><span class="sxs-lookup"><span data-stu-id="57940-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="57940-198">Elaborazione</span><span class="sxs-lookup"><span data-stu-id="57940-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="57940-199">Non pianificato</span><span class="sxs-lookup"><span data-stu-id="57940-199">Not planned</span></span></li>
<li><span data-ttu-id="57940-200">Preparato</span><span class="sxs-lookup"><span data-stu-id="57940-200">Prepared</span></span></li>
<li><span data-ttu-id="57940-201">In corso</span><span class="sxs-lookup"><span data-stu-id="57940-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="57940-202">No</span><span class="sxs-lookup"><span data-stu-id="57940-202">No</span></span></td>
<td><span data-ttu-id="57940-203">No</span><span class="sxs-lookup"><span data-stu-id="57940-203">No</span></span></td>
<td><span data-ttu-id="57940-204">No</span><span class="sxs-lookup"><span data-stu-id="57940-204">No</span></span></td>
<td><span data-ttu-id="57940-205">No</span><span class="sxs-lookup"><span data-stu-id="57940-205">No</span></span></td>
<td><span data-ttu-id="57940-206">No</span><span class="sxs-lookup"><span data-stu-id="57940-206">No</span></span></td>
<td><span data-ttu-id="57940-207">No</span><span class="sxs-lookup"><span data-stu-id="57940-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="57940-208">Elaborazione</span><span class="sxs-lookup"><span data-stu-id="57940-208">Process</span></span></td>
<td><span data-ttu-id="57940-209">Completato</span><span class="sxs-lookup"><span data-stu-id="57940-209">Completed</span></span></td>
<td><span data-ttu-id="57940-210">No</span><span class="sxs-lookup"><span data-stu-id="57940-210">No</span></span></td>
<td><span data-ttu-id="57940-211">No</span><span class="sxs-lookup"><span data-stu-id="57940-211">No</span></span></td>
<td><span data-ttu-id="57940-212">No</span><span class="sxs-lookup"><span data-stu-id="57940-212">No</span></span></td>
<td><span data-ttu-id="57940-213">No</span><span class="sxs-lookup"><span data-stu-id="57940-213">No</span></span></td>
<td><span data-ttu-id="57940-214">No</span><span class="sxs-lookup"><span data-stu-id="57940-214">No</span></span></td>
<td><span data-ttu-id="57940-215">No</span><span class="sxs-lookup"><span data-stu-id="57940-215">No</span></span></td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]