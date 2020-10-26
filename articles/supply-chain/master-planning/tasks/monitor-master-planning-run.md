---
title: Monitorare un'esecuzione di pianificazione generale
description: Questo argomento spiega come il responsabile di pianificazione della produzione può vedere se è in corso un'esecuzione di pianificazione generale.
author: josaw1
manager: tfehr
ms.date: 11/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 045b82af6f65b22e1c683f8de47a6df282711e6a
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3978131"
---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="47bba-103">Monitorare un'esecuzione di pianificazione generale</span><span class="sxs-lookup"><span data-stu-id="47bba-103">Monitor a master planning run</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="use-a-gantt-chart-to-visualize-master-planning-progress"></a><span data-ttu-id="47bba-104">Utilizzare un diagramma di Gantt per visualizzare l'avanzamento della pianificazione generale</span><span class="sxs-lookup"><span data-stu-id="47bba-104">Use a Gantt chart to visualize master planning progress</span></span>

<span data-ttu-id="47bba-105">Nella pagina **Visualizza stato pianificazione generale**, è possibile visualizzare i dettagli delle esecuzioni storiche di pianificazione generale come diagramma di Gantt.</span><span class="sxs-lookup"><span data-stu-id="47bba-105">From the **View master planning progress** page, you can view details of historical master planning runs as a Gantt chart.</span></span> <span data-ttu-id="47bba-106">Questa funzionalità può aiutare a comprendere il tempo impiegato nelle varie fasi della pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="47bba-106">This functionality can help you understand the time that is spent on the various phases of master planning.</span></span> <span data-ttu-id="47bba-107">Per un lavoro di pianificazione attivo corrente, è possibile utilizzare la pagina **Visualizza stato pianificazione principale** per tenere traccia dell'avanzamento e visualizzare il tempo rimanente stimato.</span><span class="sxs-lookup"><span data-stu-id="47bba-107">For a current active planning job, the **View master planning progress** page can be used to track progress and view the estimated remaining time.</span></span>

### <a name="turn-on-and-use-the-master-plan-progress-visualization-feature"></a><span data-ttu-id="47bba-108">Attivare e utilizzare la funzione di visualizzazione dell'avanzamento del piano principale</span><span class="sxs-lookup"><span data-stu-id="47bba-108">Turn on and use the Master plan progress visualization feature</span></span>

<span data-ttu-id="47bba-109">Per utilizzare questa funzionalità, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="47bba-109">To use this functionality, follow these steps.</span></span>

1. <span data-ttu-id="47bba-110">Nell'area di lavoro **Gestione funzionalità**, scheda **Nuovo**, selezionare **Visualizzazione stato pianificazione generale** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="47bba-110">In the **Feature management** workspace, on the **New** tab, select **Master planning progress visualization** in the list.</span></span> <span data-ttu-id="47bba-111">Se la funzionalità non è presente nella scheda **Nuovo**, considerare le schede **Tutto** e **Non abilitato**.</span><span class="sxs-lookup"><span data-stu-id="47bba-111">If the feature doesn't appear on the **New** tab, look on the **Not enabled** and **All** tabs.</span></span>
1. <span data-ttu-id="47bba-112">Selezionare **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="47bba-112">Select **Enable now**.</span></span> <span data-ttu-id="47bba-113">In alternativa, selezionare **Programmazione** e quindi selezionare l'ora in cui si desidera che la funzionalità sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="47bba-113">Alternatively, select **Schedule**, and then select the time when you want the feature to be turned on.</span></span>

<span data-ttu-id="47bba-114">Nella pagina **Visualizza stato pianificazione generale** possono essere visualizzati entrambi i processi della pianificazione storica e i processi di pianificazione attivi.</span><span class="sxs-lookup"><span data-stu-id="47bba-114">The **View master planning progress** page can display both historical planning jobs and active planning jobs.</span></span> 

<span data-ttu-id="47bba-115">Per visualizzare i processi della pianificazione storica, sono disponibili due opzioni.</span><span class="sxs-lookup"><span data-stu-id="47bba-115">To view historical planning jobs, there are two options.</span></span> 

1. <span data-ttu-id="47bba-116">Andare a **Pianificazione generale \> Impostazione \> Piani \> Piani generali**, quindi nel riquadro azioni selezionare **Storico**.</span><span class="sxs-lookup"><span data-stu-id="47bba-116">Go to **Master planning \> Setup \> Plans \> Master plans**, and then, on the Action Pane, select **History**.</span></span> <span data-ttu-id="47bba-117">Selezionare il processo desiderato selezionato, selezionare **Richieste di informazioni**, **Visualizza avanzamento**</span><span class="sxs-lookup"><span data-stu-id="47bba-117">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>
1. <span data-ttu-id="47bba-118">Passare a **Pianificazione generale \> Aree di lavoro \> Pianificazione generale** e nel riquadro della pianificazione generale selezionare **Storico**.</span><span class="sxs-lookup"><span data-stu-id="47bba-118">Go to **Master planning \> Workspaces \> Master planning**, on the Master planning tile click **History**.</span></span> <span data-ttu-id="47bba-119">Selezionare il processo desiderato selezionato, selezionare **Richieste di informazioni**, **Visualizza avanzamento**</span><span class="sxs-lookup"><span data-stu-id="47bba-119">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>

<span data-ttu-id="47bba-120">Per visualizzare i processi della pianificazione attiva, sono disponibili due opzioni.</span><span class="sxs-lookup"><span data-stu-id="47bba-120">To view active planning jobs, there are two options.</span></span> 
1. <span data-ttu-id="47bba-121">Andare a **Pianificazione generale \> Aree di lavoro \> Pianificazione generale** e nel riquadro azioni selezionare **Processi di pianificazione non completati**.</span><span class="sxs-lookup"><span data-stu-id="47bba-121">Go to **Master planning \> Workspaces \> Master planning**, on the Action Pane, select **Unfinished planning process**.</span></span> <span data-ttu-id="47bba-122">Selezionare il processo desiderato selezionato, selezionare **Richieste di informazioni**, **Visualizza avanzamento**.</span><span class="sxs-lookup"><span data-stu-id="47bba-122">With the desired job selected, select **Inquiries**,  and then select **View progress**.</span></span>
1. <span data-ttu-id="47bba-123">Passare a **Pianificazione generale \> Aree di lavoro \> Pianificazione generale** e nel riquadro della pianificazione generale selezionare **Visualizza avanzamento**.</span><span class="sxs-lookup"><span data-stu-id="47bba-123">Go to **Master planning \> Workspaces \> Master planning**, on the Master planning tile click **View progress**.</span></span> <span data-ttu-id="47bba-124">Selezionare il processo desiderato selezionato, selezionare **Richieste di informazioni**, **Visualizza avanzamento**</span><span class="sxs-lookup"><span data-stu-id="47bba-124">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>

<span data-ttu-id="47bba-125">Notare che è possibile visualizzare i processi attivi solo quando un processo di pianificazione è in elaborazione.</span><span class="sxs-lookup"><span data-stu-id="47bba-125">Note you can view active jobs only when a planning job is processing.</span></span>

### <a name="analyze-a-master-planning-job"></a><span data-ttu-id="47bba-126">Analizzare un processo di pianificazione generale</span><span class="sxs-lookup"><span data-stu-id="47bba-126">Analyze a master planning job</span></span>

<span data-ttu-id="47bba-127">Nel diagramma di Gantt, è possibile espandere i seguenti processi di pianificazione per visualizzare ulteriori dettagli relativi al tempo impiegato:</span><span class="sxs-lookup"><span data-stu-id="47bba-127">In the Gantt chart, you can expand each of the following planning processes to view additional details about the time that is spent:</span></span>

- <span data-ttu-id="47bba-128">Inizializzazione</span><span class="sxs-lookup"><span data-stu-id="47bba-128">Initializing</span></span>
- <span data-ttu-id="47bba-129">Eliminazione e inserimento dati</span><span class="sxs-lookup"><span data-stu-id="47bba-129">Deleting and inserting data</span></span>
- <span data-ttu-id="47bba-130">Pianificazione copertura</span><span class="sxs-lookup"><span data-stu-id="47bba-130">Coverage planning</span></span>
- <span data-ttu-id="47bba-131">Ritardi</span><span class="sxs-lookup"><span data-stu-id="47bba-131">Delays</span></span>
- <span data-ttu-id="47bba-132">Messaggi d'azione</span><span class="sxs-lookup"><span data-stu-id="47bba-132">Action messages</span></span>
- <span data-ttu-id="47bba-133">Finalizzazione</span><span class="sxs-lookup"><span data-stu-id="47bba-133">Finalization</span></span>
- <span data-ttu-id="47bba-134">Stabilizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="47bba-134">Auto-firming</span></span>

<span data-ttu-id="47bba-135">Il diagramma di Gantt è uno strumento utile se si desidera visualizzare l'impatto dei messaggi di azione.</span><span class="sxs-lookup"><span data-stu-id="47bba-135">The Gantt chart is a useful tool if you want to view the impact of using action messages.</span></span>

#### <a name="navigation-in-the-gantt-chart"></a><span data-ttu-id="47bba-136">Navigazione nel diagramma di Gantt</span><span class="sxs-lookup"><span data-stu-id="47bba-136">Navigation in the Gantt chart</span></span>

- <span data-ttu-id="47bba-137">Per espandere il gruppo selezionato e visualizzare i dettagli, selezionare il segno più (**+**) nella visualizzazione ad albero.</span><span class="sxs-lookup"><span data-stu-id="47bba-137">To expand the selected group and show the details, select the plus sign (**+**) in the tree view.</span></span>
- <span data-ttu-id="47bba-138">Per comprimere il gruppo selezionato, selezionare il segno meno (**–**) nella visualizzazione ad albero.</span><span class="sxs-lookup"><span data-stu-id="47bba-138">To collapse the selected group, select the minus sign (**–**) in the tree view.</span></span>
- <span data-ttu-id="47bba-139">È possibile utilizzare la tastiera per la navigazione.</span><span class="sxs-lookup"><span data-stu-id="47bba-139">You can use your keyboard for navigation.</span></span> <span data-ttu-id="47bba-140">Utilizzare i tasti **freccia su** e **freccia giù** per spostare tra le righe.</span><span class="sxs-lookup"><span data-stu-id="47bba-140">Use the **Up arrow** and **Down arrow** keys to move between rows.</span></span> <span data-ttu-id="47bba-141">Utilizzare i tasti **freccia a sinistra** e **freccia a destra** per espandere e comprimere gruppi.</span><span class="sxs-lookup"><span data-stu-id="47bba-141">Use the **Right arrow** and **Left arrow** keys to expand and collapse groups.</span></span>
- <span data-ttu-id="47bba-142">Per aprire o chiudere tutti i livelli nel diagramma di Gantt, selezionare **Espandi tutto** o **Comprimi tutto**.</span><span class="sxs-lookup"><span data-stu-id="47bba-142">To open or close all levels in the Gantt chart, select **Expand all** or **Collapse all**.</span></span>
- <span data-ttu-id="47bba-143">Per visualizzare il tempo di esecuzione correlato, passare il mouse su un'attività.</span><span class="sxs-lookup"><span data-stu-id="47bba-143">To view the related processing time, hover over a task.</span></span> <span data-ttu-id="47bba-144">Le attività sono il livello più basso nel diagramma di Gantt.</span><span class="sxs-lookup"><span data-stu-id="47bba-144">(Tasks are the lowest level in the Gantt chart.)</span></span>

#### <a name="view-an-additional-master-planning-run-to-compare-jobs"></a><span data-ttu-id="47bba-145">Visualizzare un'altra esecuzione della pianificazione generale per confrontare i processi</span><span class="sxs-lookup"><span data-stu-id="47bba-145">View an additional master planning run to compare jobs</span></span>

<span data-ttu-id="47bba-146">Se si seleziona il processo di pianificazione generale nel campo **Mostra esecuzione della pianificazione generale aggiuntiva**, è possibile visualizzare l'esecuzione di una pianificazione generale aggiuntiva nel diagramma di Gantt e confrontare i due processi.</span><span class="sxs-lookup"><span data-stu-id="47bba-146">By selecting a master planning job on field **Show additional master planning run**, you can view an additional master planning run in the Gantt chart and compare the two jobs.</span></span>

#### <a name="bom-level-display"></a><span data-ttu-id="47bba-147">Visualizzazione dei livelli DBA</span><span class="sxs-lookup"><span data-stu-id="47bba-147">BOM-level display</span></span>

<span data-ttu-id="47bba-148">I livelli della distinta base (DBA) vengono visualizzati in modo diverso per pianificazione di copertura, ritardi, azioni e stabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="47bba-148">Bill of materials (BOM) levels are shown differently for coverage planning, delays, actions, and firming.</span></span>

- <span data-ttu-id="47bba-149">**Pianificazione copertura** - I livelli DBA vengono visualizzati come previsto.</span><span class="sxs-lookup"><span data-stu-id="47bba-149">**Coverage planning** – BOM levels are shown as expected.</span></span> <span data-ttu-id="47bba-150">Vengono calcolati dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="47bba-150">They are calculated from the top down.</span></span>

    <span data-ttu-id="47bba-151">**Esempio:** livello DBA 0, 1, 2</span><span class="sxs-lookup"><span data-stu-id="47bba-151">**Example:** BOM level 0, 1, 2</span></span>

- <span data-ttu-id="47bba-152">**Ritardi** - I livelli DBA vengono visualizzati come i livelli DBA della pianificazione copertura moltiplicati per -1.</span><span class="sxs-lookup"><span data-stu-id="47bba-152">**Delays** – BOM levels are shown as the coverage planning BOM levels multiplied by –1.</span></span> <span data-ttu-id="47bba-153">In altre parole con segno negativo.</span><span class="sxs-lookup"><span data-stu-id="47bba-153">(In other words, they have a negative sign.)</span></span>

    <span data-ttu-id="47bba-154">**Esempio:** livello DBA -2, -1, 0</span><span class="sxs-lookup"><span data-stu-id="47bba-154">**Example:** BOM level –2, –1, 0</span></span>

- <span data-ttu-id="47bba-155">**Messaggio d'azione** - I livelli DBA vengono visualizzati come previsto.</span><span class="sxs-lookup"><span data-stu-id="47bba-155">**Action message** – BOM levels are shown as expected.</span></span> <span data-ttu-id="47bba-156">Vengono calcolati dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="47bba-156">They are calculated from the top down.</span></span>

    <span data-ttu-id="47bba-157">**Esempio:** livello DBA 0, 1, 2</span><span class="sxs-lookup"><span data-stu-id="47bba-157">**Example:** BOM level 0, 1, 2</span></span>

- <span data-ttu-id="47bba-158">**Stabilizzazione automatica** - I livelli DBA vengono visualizzati come 999 meno il livello DBA della pianificazione di copertura.</span><span class="sxs-lookup"><span data-stu-id="47bba-158">**Auto-firming** – BOM levels are shown as 999 minus the coverage planning BOM level.</span></span>

    <span data-ttu-id="47bba-159">**Esempio:** livello DBA 999, 998, 997</span><span class="sxs-lookup"><span data-stu-id="47bba-159">**Example:** BOM level 999, 998, 997</span></span>

<span data-ttu-id="47bba-160">Nella seguente tabella viene illustrato il comportamento.</span><span class="sxs-lookup"><span data-stu-id="47bba-160">The following table summarizes the behavior.</span></span>

| <span data-ttu-id="47bba-161">Livello DBA mostrato</span><span class="sxs-lookup"><span data-stu-id="47bba-161">BOM level that is shown</span></span> | <span data-ttu-id="47bba-162">Prodotto finito</span><span class="sxs-lookup"><span data-stu-id="47bba-162">End item</span></span> | <span data-ttu-id="47bba-163">Sottocomponente</span><span class="sxs-lookup"><span data-stu-id="47bba-163">Subcomponent</span></span> | <span data-ttu-id="47bba-164">Materie prime</span><span class="sxs-lookup"><span data-stu-id="47bba-164">Raw material</span></span> |
|---|---|---|---|
| <span data-ttu-id="47bba-165">Pianificazione copertura</span><span class="sxs-lookup"><span data-stu-id="47bba-165">Coverage planning</span></span> | <span data-ttu-id="47bba-166">0</span><span class="sxs-lookup"><span data-stu-id="47bba-166">0</span></span> | <span data-ttu-id="47bba-167">1</span><span class="sxs-lookup"><span data-stu-id="47bba-167">1</span></span> | <span data-ttu-id="47bba-168">2</span><span class="sxs-lookup"><span data-stu-id="47bba-168">2</span></span> |
| <span data-ttu-id="47bba-169">Ritardi</span><span class="sxs-lookup"><span data-stu-id="47bba-169">Delays</span></span> | <span data-ttu-id="47bba-170">0</span><span class="sxs-lookup"><span data-stu-id="47bba-170">0</span></span> | <span data-ttu-id="47bba-171">–1</span><span class="sxs-lookup"><span data-stu-id="47bba-171">–1</span></span> | <span data-ttu-id="47bba-172">–2</span><span class="sxs-lookup"><span data-stu-id="47bba-172">–2</span></span> |
| <span data-ttu-id="47bba-173">Messaggio d'azione</span><span class="sxs-lookup"><span data-stu-id="47bba-173">Action message</span></span> | <span data-ttu-id="47bba-174">0</span><span class="sxs-lookup"><span data-stu-id="47bba-174">0</span></span> | <span data-ttu-id="47bba-175">1</span><span class="sxs-lookup"><span data-stu-id="47bba-175">1</span></span> | <span data-ttu-id="47bba-176">2</span><span class="sxs-lookup"><span data-stu-id="47bba-176">2</span></span> |
| <span data-ttu-id="47bba-177">Stabilizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="47bba-177">Auto-firming</span></span> | <span data-ttu-id="47bba-178">999</span><span class="sxs-lookup"><span data-stu-id="47bba-178">999</span></span> | <span data-ttu-id="47bba-179">998</span><span class="sxs-lookup"><span data-stu-id="47bba-179">998</span></span> | <span data-ttu-id="47bba-180">997</span><span class="sxs-lookup"><span data-stu-id="47bba-180">997</span></span> |

#### <a name="visualize-progress"></a><span data-ttu-id="47bba-181">Visualizzare l'avanzamento</span><span class="sxs-lookup"><span data-stu-id="47bba-181">Visualize progress</span></span>

<span data-ttu-id="47bba-182">Se si visualizza un processo di pianificazione generale attualmente in esecuzione, l'avanzamento è indicato tramite i colori nel diagramma di Gantt.</span><span class="sxs-lookup"><span data-stu-id="47bba-182">If you view a master planning job that is currently running, progress is shown through colors in the Gantt chart.</span></span> <span data-ttu-id="47bba-183">I seguenti colori si applicano al tema blu.</span><span class="sxs-lookup"><span data-stu-id="47bba-183">The following colors apply to the blue theme.</span></span> <span data-ttu-id="47bba-184">Per altri temi i colori sono diversi.</span><span class="sxs-lookup"><span data-stu-id="47bba-184">For other color themes, the colors will differ.</span></span>

- <span data-ttu-id="47bba-185">**Blu scuro** - Attività di pianificazione completate.</span><span class="sxs-lookup"><span data-stu-id="47bba-185">**Dark blue** – Completed planning tasks.</span></span>
- <span data-ttu-id="47bba-186">**Arancione** L'attività che è attualmente in corso.</span><span class="sxs-lookup"><span data-stu-id="47bba-186">**Orange** – The task that is currently in progress.</span></span>
- <span data-ttu-id="47bba-187">**Blu chiaro** - La stima delle attività rimanenti.</span><span class="sxs-lookup"><span data-stu-id="47bba-187">**Light blue** – The estimate for remaining tasks.</span></span>

<span data-ttu-id="47bba-188">Il colore viene visualizzato solo sul livello più basso nel diagramma di Gantt.</span><span class="sxs-lookup"><span data-stu-id="47bba-188">The color is shown only on the lowest level in the Gantt chart.</span></span> <span data-ttu-id="47bba-189">Selezionare **Espandi tutto** per visualizzare tutte le attività nel processo di pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="47bba-189">Select **Expand all** to view all tasks in the master planning job.</span></span> <span data-ttu-id="47bba-190">La stima delle attività rimanenti si basa sui processi storici della pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="47bba-190">The estimate of remaining tasks is based on historical master planning jobs.</span></span>

## <a name="run-master-planning-and-track-processing-time"></a><span data-ttu-id="47bba-191">Eseguire la pianificazione generale e tracciare il tempo di elaborazione</span><span class="sxs-lookup"><span data-stu-id="47bba-191">Run master planning and track processing time</span></span>

1. <span data-ttu-id="47bba-192">Nel dashboard predefinito, selezionare **Pianificazione generale**.</span><span class="sxs-lookup"><span data-stu-id="47bba-192">On the default dashboard, select **Master planning**.</span></span>
1. <span data-ttu-id="47bba-193">Nel campo **Piano** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="47bba-193">In the **Plan** field, enter or select a value.</span></span>
1. <span data-ttu-id="47bba-194">Selezionare **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="47bba-194">Select **Run**.</span></span>
1. <span data-ttu-id="47bba-195">Impostare l'opzione **Traccia ora di elaborazione** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="47bba-195">Set the **Track processing time** option to **Yes**.</span></span>
1. <span data-ttu-id="47bba-196">Nel campo **Numero di thread** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="47bba-196">In the **Number of threads** field, enter a number.</span></span>
1. <span data-ttu-id="47bba-197">Nella scheda dettaglio **Record da includere**, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="47bba-197">On the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="47bba-198">Nella griglia, selezionare la riga in cui il campo **Campo** è impostato su **Numero articolo**.</span><span class="sxs-lookup"><span data-stu-id="47bba-198">In the grid, select the row where the **Field** field is set to **Item number**.</span></span>
1. <span data-ttu-id="47bba-199">Nel campo **Criteri** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="47bba-199">In the **Criteria** field, enter a value.</span></span>
1. <span data-ttu-id="47bba-200">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="47bba-200">Select **OK**.</span></span>
