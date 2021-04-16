---
title: Risolvere i problemi relativi alle operazioni di inventario
description: Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si utilizzano le operazioni di inventario.
author: sherry-zheng
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 24e41e35b3e810c509a16b91fffd1e796ab9d134
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832060"
---
# <a name="troubleshoot-inventory-operations"></a><span data-ttu-id="897e4-103">Risolvere i problemi relativi alle operazioni di inventario</span><span class="sxs-lookup"><span data-stu-id="897e4-103">Troubleshoot inventory operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="897e4-104">Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si utilizzano le operazioni di inventario.</span><span class="sxs-lookup"><span data-stu-id="897e4-104">This topic describes how to fix issues that you might encounter while you work with inventory operations.</span></span>

## <a name="i-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a><span data-ttu-id="897e4-105">Non riesco a trovare la finestra di dialogo a discesa "Flusso di lavoro" per i giornali di registrazione magazzino.</span><span class="sxs-lookup"><span data-stu-id="897e4-105">I can't find the "Workflow" drop-down dialog box for inventory journals.</span></span>

### <a name="issue-description"></a><span data-ttu-id="897e4-106">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="897e4-106">Issue description</span></span>

<span data-ttu-id="897e4-107">Non riesci a trovare la finestra di dialogo a discesa **Flusso di lavoro** nella pagina del giornale di registrazione o le operazioni del flusso di lavoro correlate non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="897e4-107">You can't find the **Workflow** drop-down dialog box on the journal page, or related workflow operations aren't available.</span></span>

<span data-ttu-id="897e4-108">Questo problema può verificarsi per tre motivi, come descritto nelle sottosezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="897e4-108">This issue can occur for three reasons, as described in the following subsections.</span></span>

### <a name="issue-resolution-1"></a><span data-ttu-id="897e4-109">Risoluzione del problema 1</span><span class="sxs-lookup"><span data-stu-id="897e4-109">Issue resolution 1</span></span>

<span data-ttu-id="897e4-110">Se il problema si applica a tutti gli utenti, potrebbe verificarsi perché il flusso di lavoro di approvazione non è stato assegnato al nome del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="897e4-110">If the issue applies to all users, it might be occurring because the approval workflow hasn't been assigned to the journal name.</span></span> <span data-ttu-id="897e4-111">Per risolvere il problema, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="897e4-111">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="897e4-112">Andare a **Gestione inventario &gt; Imposta &gt; Nomi giornale di registrazione &gt; Inventario**.</span><span class="sxs-lookup"><span data-stu-id="897e4-112">Go to **Inventory Management &gt; Setup &gt; Journal names &gt; Inventory**.</span></span>
1. <span data-ttu-id="897e4-113">Nel riquadro dell'elenco, selezionare il nome di un giornale di registrazione per aprirne le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="897e4-113">In the list pane, select a journal name to open its settings.</span></span>
1. <span data-ttu-id="897e4-114">Nella Scheda dettaglio **Generale**, impostare l'opzione **Flusso di lavoro di approvazione** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="897e4-114">On the **General** FastTab, set the **Approval workflow** option to *Yes*.</span></span> <span data-ttu-id="897e4-115">Se viene richiesto di confermare la modifica, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="897e4-115">If you're prompted to confirm the change, select **Yes**.</span></span>
1. <span data-ttu-id="897e4-116">Nel campo **Flusso di lavoro** selezionare il flusso di lavoro che si desidera utilizzare per il nome del giornale di registrazione selezionato.</span><span class="sxs-lookup"><span data-stu-id="897e4-116">In the **Workflow** field, select the workflow that you want to use for the selected journal name.</span></span>

### <a name="issue-resolution-2"></a><span data-ttu-id="897e4-117">Risoluzione del problema 2</span><span class="sxs-lookup"><span data-stu-id="897e4-117">Issue resolution 2</span></span>

<span data-ttu-id="897e4-118">Se il flusso di lavoro utilizza codice personalizzato, potrebbero verificarsi problemi dopo l'aggiornamento del sistema.</span><span class="sxs-lookup"><span data-stu-id="897e4-118">If your workflow uses customized code, issues might occur after you upgrade the system.</span></span> <span data-ttu-id="897e4-119">Ad esempio, nel flusso di lavoro del giornale di registrazione, il pulsante **Invia** potrebbe essere disattivato, quindi non puoi selezionarlo per approvare un invio.</span><span class="sxs-lookup"><span data-stu-id="897e4-119">For example, in the journal workflow, the **Submit** button might be grayed out so you can't select it to approve a submission.</span></span>

<span data-ttu-id="897e4-120">Se il pulsante **Invia** è disattivato, il flusso di lavoro potrebbe essere stato personalizzato, il che significa che il metodo del flusso di lavoro, `canSubmitToWorkflow()` in `FormDataUtil`, è stato esteso.</span><span class="sxs-lookup"><span data-stu-id="897e4-120">If the **Submit** button is grayed out, your workflow might have been customized, which means the method of the workflow, `canSubmitToWorkflow()` in `FormDataUtil`, has been extended.</span></span> <span data-ttu-id="897e4-121">Per risolvere questo problema, modifica il modo in cui estendi il metodo `canSubmitToWorkflow()` per utilizzare la struttura nel seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="897e4-121">To fix this issue, change the way that you extend the method of the `canSubmitToWorkflow()` to use the structure in the following example.</span></span>

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

### <a name="issue-resolution-3"></a><span data-ttu-id="897e4-122">Risoluzione del problema 3</span><span class="sxs-lookup"><span data-stu-id="897e4-122">Issue resolution 3</span></span>

<span data-ttu-id="897e4-123">Se il problema si applica solo a pochi utenti specifici, tali utenti potrebbero non disporre dei privilegi di sicurezza obbligatori per eseguire le operazioni del flusso di lavoro sui giornali di registrazione magazzino.</span><span class="sxs-lookup"><span data-stu-id="897e4-123">If the issue applies only to a few specific users, those users might not have the security privileges that are required to run workflow operations on inventory journals.</span></span> <span data-ttu-id="897e4-124">Verifica che ogni utente interessato disponga del privilegio di sicurezza *Mantieni il flusso di lavoro del giornale di registrazione magazzino*.</span><span class="sxs-lookup"><span data-stu-id="897e4-124">Verify that each affected user has the *Maintain inventory journal workflow* security privilege.</span></span> <span data-ttu-id="897e4-125">Per impostazione predefinita, questo privilegio viene assegnato a un compito con lo stesso nome e tale compito viene applicato ai ruoli *Addetto magazzino* e *Responsabile magazzino*.</span><span class="sxs-lookup"><span data-stu-id="897e4-125">By default, this privilege is assigned to a duty that has same name, and that duty is applied to the *Warehouse worker* and *Warehouse manager* roles.</span></span>

## <a name="my-inventory-journal-remains-in-system-locked-status-and-the-workflow-batch-job-doesnt-work"></a><span data-ttu-id="897e4-126">Il mio giornale di registrazione magazzino rimane nello stato di bloccato dal sistema e il processo batch del flusso di lavoro non funziona.</span><span class="sxs-lookup"><span data-stu-id="897e4-126">My inventory journal remains in system-locked status, and the workflow batch job doesn't work.</span></span>

### <a name="issue-description"></a><span data-ttu-id="897e4-127">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="897e4-127">Issue description</span></span>

<span data-ttu-id="897e4-128">Uno dei tuoi giornali di registrazione magazzino è bloccato da un'operazione e non viene rilasciato.</span><span class="sxs-lookup"><span data-stu-id="897e4-128">One of your inventory journals is locked by some operation and isn't being released.</span></span> <span data-ttu-id="897e4-129">Ad esempio, se si verifica un errore sconosciuto durante la registrazione (che è un'operazione di blocco del sistema), il giornale di registrazione potrebbe rimanere nello stato di blocco del sistema.</span><span class="sxs-lookup"><span data-stu-id="897e4-129">For example, if an unknown error occurs during posting (which is a system lock operation), the journal might remain in system-locked status.</span></span> <span data-ttu-id="897e4-130">In questo caso, il gestore dell'elemento di lavoro del flusso di lavoro genererà un errore mentre blocca la convalida.</span><span class="sxs-lookup"><span data-stu-id="897e4-130">In this case, the workflow work item handler will throw an error while it does lock validation.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="897e4-131">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="897e4-131">Issue resolution</span></span>

<span data-ttu-id="897e4-132">Accedi all'istanza di SQL Server per Supply Chain Management e verifica se **InventJournalTable.SystemBlocked** è impostato su *1*.</span><span class="sxs-lookup"><span data-stu-id="897e4-132">Sign in to the SQL Server instance for Supply Chain Management, and check whether **InventJournalTable.SystemBlocked** is set to *1*.</span></span> <span data-ttu-id="897e4-133">In tal caso, accertati che il giornale di registrazione non sia in stato bloccato e quindi reimposta **InventJournalTable.SystemBlocked** su *0*.</span><span class="sxs-lookup"><span data-stu-id="897e4-133">If it is, make sure that the journal should not be in locked status, and then reset **InventJournalTable.SystemBlocked** to *0*.</span></span>

## <a name="my-inventory-journal-workflow-is-never-completed-and-the-journal-cant-be-edited-or-posted"></a><span data-ttu-id="897e4-134">Il mio flusso di lavoro del giornale di registrazione magazzino non viene mai completato e il giornale di registrazione non può essere modificato o registrato.</span><span class="sxs-lookup"><span data-stu-id="897e4-134">My inventory journal workflow is never completed, and the journal can't be edited or posted.</span></span>

### <a name="issue-description"></a><span data-ttu-id="897e4-135">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="897e4-135">Issue description</span></span>

<span data-ttu-id="897e4-136">Dopo aver inviato un flusso di lavoro di approvazione del giornale di registrazione, l'elaborazione del flusso di lavoro smette di rispondere e non è possibile modificare o elaborare i giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="897e4-136">After you submit a journal approval workflow, workflow processing stops responding, and you can't edit or process your journals.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="897e4-137">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="897e4-137">Issue resolution</span></span>

<span data-ttu-id="897e4-138">Esistono diversi motivi per cui l'elaborazione del flusso di lavoro potrebbe non essere completata.</span><span class="sxs-lookup"><span data-stu-id="897e4-138">There are several reasons why workflow processing might not be completed.</span></span> <span data-ttu-id="897e4-139">Verifica i seguenti problemi:</span><span class="sxs-lookup"><span data-stu-id="897e4-139">Check for the following issues:</span></span>

- <span data-ttu-id="897e4-140">Vai a **Gestione inventario &gt; Imposta &gt; Flussi di lavoro gestione articoli** e rivedi la configurazione del flusso di lavoro interessato.</span><span class="sxs-lookup"><span data-stu-id="897e4-140">Go to **Inventory management &gt; Setup &gt; Inventory management workflows**, and review the configuration of the affected workflow.</span></span> <span data-ttu-id="897e4-141">Per ulteriori informazioni, vedere [Flussi di lavoro di approvazione del giornale di registrazione magazzino](inventory-journal-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="897e4-141">For more information, see [Inventory journal approval workflows](inventory-journal-workflow.md).</span></span>
- <span data-ttu-id="897e4-142">Il flusso di lavoro potrebbe riscontrare un'eccezione o un errore.</span><span class="sxs-lookup"><span data-stu-id="897e4-142">The workflow might be encountering an exception or error.</span></span> <span data-ttu-id="897e4-143">Rivedi la cronologia degli elementi di lavoro del flusso di lavoro interessato per vedere se include un errore dell'applicazione che termina il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="897e4-143">Review the work item history of the affected workflow to see whether it includes an application error that terminates the workflow.</span></span>
- <span data-ttu-id="897e4-144">Il giornale di registrazione inventario può essere aggiornato o modificato solo se approvato.</span><span class="sxs-lookup"><span data-stu-id="897e4-144">The inventory journal can be updated or edited only if it's approved.</span></span> <span data-ttu-id="897e4-145">Se il richiamo è attivo, puoi provare a richiamare il giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="897e4-145">If recall is active, you can try to recall the journal.</span></span> <span data-ttu-id="897e4-146">L'esecuzione del processo batch del flusso di lavoro potrebbe essere sospesa per diversi motivi.</span><span class="sxs-lookup"><span data-stu-id="897e4-146">Execution of the workflow batch job might be suspended for multiple reasons.</span></span> <span data-ttu-id="897e4-147">Alcuni di questi motivi potrebbero essere causati dal problema del framework del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="897e4-147">Some of these reasons might be caused by the workflow framework issue.</span></span>

## <a name="inventory-journal-workflow-conditions-apply-only-at-the-journal-level-not-at-the-line-level"></a><span data-ttu-id="897e4-148">Le condizioni del flusso di lavoro del giornale di registrazione magazzino si applicano solo a livello di giornale di registrazione, non a livello di riga</span><span class="sxs-lookup"><span data-stu-id="897e4-148">Inventory journal workflow conditions apply only at the journal level, not at the line level</span></span>

### <a name="issue-description"></a><span data-ttu-id="897e4-149">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="897e4-149">Issue description</span></span>

<span data-ttu-id="897e4-150">È possibile che si verifichi questo problema se, ad esempio, si tenta di configurare una condizione del flusso di lavoro del giornale di registrazione magazzini sull'importo del costo.</span><span class="sxs-lookup"><span data-stu-id="897e4-150">You might experience this issue if, for example, you try to set up an inventory journal workflow condition on the cost amount.</span></span> <span data-ttu-id="897e4-151">Si configura la condizione in modo che il passaggio 1 venga eseguito solo quando l'importo del costo è inferiore a 100.</span><span class="sxs-lookup"><span data-stu-id="897e4-151">You set up the condition so that step 1 is run only when the cost amount is less than 100.</span></span> <span data-ttu-id="897e4-152">Quindi si configura un'altra condizione in modo che il passaggio 2 venga eseguito solo quando l'importo del costo è maggiore o uguale a 100.</span><span class="sxs-lookup"><span data-stu-id="897e4-152">You then set up another condition so that step 2 is run only when the cost amount is more than or equal to 100.</span></span> <span data-ttu-id="897e4-153">Quindi, quando viene eseguito il flusso di lavoro, la cronologia del flusso di lavoro mostra solo una riga e la prima condizione viene sempre valutata come *vero*, indipendentemente dal valore inviato.</span><span class="sxs-lookup"><span data-stu-id="897e4-153">Then, when the workflow is run, the workflow history shows only one line, and the first condition is always evaluated as *true*, regardless of the value that is submitted.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="897e4-154">Soluzione del problema</span><span class="sxs-lookup"><span data-stu-id="897e4-154">Issue workaround</span></span>

<span data-ttu-id="897e4-155">Nella versione attuale, le condizioni del flusso di lavoro del giornale di registrazione magazzino si applicano solo a livello di giornale di registrazione, non a livello di riga.</span><span class="sxs-lookup"><span data-stu-id="897e4-155">In the current release, inventory workflow conditions apply only at the journal level, not at the line level.</span></span> <span data-ttu-id="897e4-156">Questo comportamento è predefinito.</span><span class="sxs-lookup"><span data-stu-id="897e4-156">This behavior is by design.</span></span> <span data-ttu-id="897e4-157">È consigliabile impostare i criteri della condizione solo sugli attributi a livello di giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="897e4-157">We recommend that you set your condition criteria only on journal-level attributes.</span></span>

## <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-filter-results-as-i-expect"></a><span data-ttu-id="897e4-158">Il riquadro dei filtri nella pagina elenco Elenco scorte disponibili non filtra i risultati come previsto.</span><span class="sxs-lookup"><span data-stu-id="897e4-158">The filter pane on the On-hand list page doesn't filter results as I expect.</span></span>

### <a name="issue-description"></a><span data-ttu-id="897e4-159">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="897e4-159">Issue description</span></span>

<span data-ttu-id="897e4-160">I filtri nel riquadro dei filtri nella pagina **Elenco scorte disponibili**  non filtra i risultati come previsto.</span><span class="sxs-lookup"><span data-stu-id="897e4-160">The filters in the filter pane on the **On-hand list** page don't filter results as you expect.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="897e4-161">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="897e4-161">Issue resolution</span></span>

<span data-ttu-id="897e4-162">Questo comportamento è predefinito.</span><span class="sxs-lookup"><span data-stu-id="897e4-162">This behavior is by design.</span></span>

<span data-ttu-id="897e4-163">La pagina  **Elenco scorte disponibili**  è assemblata da una tabella dettagliata di scorte disponibili che include tutte le dimensioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="897e4-163">The **On-hand list** page is assembled from a detailed on-hand inventory table that includes all available dimensions.</span></span> <span data-ttu-id="897e4-164">Tuttavia, l'elenco in questa pagina è un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="897e4-164">However, the list on this page is a summary.</span></span> <span data-ttu-id="897e4-165">Pertanto, potrebbe combinare le righe dalla tabella di origine aggregando i valori in base alle dimensioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="897e4-165">Therefore, it might combine rows from the source table by aggregating values according to the dimensions that are shown.</span></span>

<span data-ttu-id="897e4-166">I filtri configurati nel riquadro dei filtri si applicano alla tabella di origine, non all'elenco aggregato.</span><span class="sxs-lookup"><span data-stu-id="897e4-166">Filters that are set up in the filter pane apply to the source table, not to the aggregated list.</span></span> <span data-ttu-id="897e4-167">Questo comportamento a volte può produrre risultati imprevisti, come mostrato in [questi esempi](inventory-on-hand-list.md#examples).</span><span class="sxs-lookup"><span data-stu-id="897e4-167">This behavior can sometimes produce unexpected results, as shown in [these examples](inventory-on-hand-list.md#examples).</span></span>

<span data-ttu-id="897e4-168">Tuttavia, i  [filtri forniti nella griglia](inventory-on-hand-list.md#grid-filters)  *si applicano*  all'elenco aggregato.</span><span class="sxs-lookup"><span data-stu-id="897e4-168">However, the [filters that are provided in the grid](inventory-on-hand-list.md#grid-filters) *do* apply to the aggregated list.</span></span> <span data-ttu-id="897e4-169">Questi filtri includono sia un filtro rapido nella parte superiore della griglia sia il filtro per ciascuna intestazione di colonna.</span><span class="sxs-lookup"><span data-stu-id="897e4-169">These filters include both the QuickFilter at the top of the grid and the filter for each column heading.</span></span>

## <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a><span data-ttu-id="897e4-170">L'unità e la quantità unitaria non funzionano correttamente nel giornale di registrazione magazzino.</span><span class="sxs-lookup"><span data-stu-id="897e4-170">The unit and unit quantity aren't working correctly in the inventory journal.</span></span>

### <a name="issue-description"></a><span data-ttu-id="897e4-171">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="897e4-171">Issue description</span></span>

<span data-ttu-id="897e4-172">Potresti riscontrare uno o entrambi i seguenti problemi quando lavori con unità e quantità in un giornale di registrazione magazzino:</span><span class="sxs-lookup"><span data-stu-id="897e4-172">You might encounter one or both of the following issues when you work with units and quantities in an inventory journal:</span></span>

- <span data-ttu-id="897e4-173">Non vengono visualizzate le unità o le quantità unitarie nel giornale di registrazione magazzino mentre è impostata un'unità di conversione per il prodotto rilasciato e non è possibile modificare l'unità nel giornale di registrazione magazzino.</span><span class="sxs-lookup"><span data-stu-id="897e4-173">You don't see units or unit quantities in the inventory journal while a unit of conversion is set up for the released product, and you can't change the unit in the inventory journal.</span></span>
- <span data-ttu-id="897e4-174">Vedi i campi **Quantità** e **Unità** nel giornale di registrazione magazzino, ma non vedi il campo **Quantità unitaria**.</span><span class="sxs-lookup"><span data-stu-id="897e4-174">You see the **Quantity** and **Unit** fields in the inventory journal, but you don't see the **Unit quantity** field.</span></span> <span data-ttu-id="897e4-175">Se modifichi l'unità, immetti una quantità e registri il giornale di registrazione, il giornale di registrazione mostra ancora l'unità di misura originale per quella quantità.</span><span class="sxs-lookup"><span data-stu-id="897e4-175">If you change the unit, enter a quantity, and post the journal, the journal still shows the original unit of measurement for that quantity.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="897e4-176">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="897e4-176">Issue resolution</span></span>

<span data-ttu-id="897e4-177">Per risolvere questo problema, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="897e4-177">To fix this issue, follow these steps.</span></span>

1. <span data-ttu-id="897e4-178">Nell'area di lavoro **Gestione funzionalità**, assicurati che la funzionalità *Utilizzo di unità di misura e quantità unitaria nei giornali di registrazione magazzino* sia attivata.</span><span class="sxs-lookup"><span data-stu-id="897e4-178">In the **Feature management** workspace, make sure that the *Using unit of measure and unit quantity in inventory journals* feature is turned on.</span></span> <span data-ttu-id="897e4-179">Questa funzionalità aggiunge i campi **Unità** e **Quantità unitaria** al giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="897e4-179">This feature adds the **Unit** and **Unit quantity** fields to the journal.</span></span>
1. <span data-ttu-id="897e4-180">Dopo che la funzionalità è stata attivata, utilizza i campi **Quantità**, **Quantità unitaria** e **Unità** nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="897e4-180">After the feature is turned on, use the **Quantity**, **Unit quantity**, and **Unit** fields in the following way:</span></span>

    - <span data-ttu-id="897e4-181">**Quantità**: specifica la quantità utilizzando l'unità predefinita definita per il prodotto rilasciato.</span><span class="sxs-lookup"><span data-stu-id="897e4-181">**Quantity** – Specify the quantity by using the default unit that is defined for the released product.</span></span> <span data-ttu-id="897e4-182">Tuttavia, l'unità predefinita stessa non viene mostrata qui.</span><span class="sxs-lookup"><span data-stu-id="897e4-182">However, the default unit itself isn't shown here.</span></span> <span data-ttu-id="897e4-183">Se viene configurata una conversione tra l'unità predefinita e l'unità selezionata nel campo **Unità**, il campo **Quantità** viene aggiornato automaticamente, in base alle selezioni nei campi **Quantità unitaria** e **Unità**.</span><span class="sxs-lookup"><span data-stu-id="897e4-183">If a conversion is set up between the default unit and the unit that is selected in the **Unit** field, the **Quantity** field is automatically updated, based on the selections in the **Unit quantity** and **Unit** fields.</span></span>
    - <span data-ttu-id="897e4-184">**Quantità unitaria**: specificare la quantità utilizzando l'unità selezionata nel campo **Unità**.</span><span class="sxs-lookup"><span data-stu-id="897e4-184">**Unit quantity** – Specify the quantity by using the unit that is selected in the **Unit** field.</span></span>
    - <span data-ttu-id="897e4-185">**Unità**: selezionare l'unità da applicare al valore nel campo **Quantità unitaria**.</span><span class="sxs-lookup"><span data-stu-id="897e4-185">**Unit** – Select the unit to apply to the value in the **Unit quantity** field.</span></span>

## <a name="i-receive-the-following-error-message-maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a><span data-ttu-id="897e4-186">Ricevo il seguente messaggio di errore: "Il numero massimo di decimali per l'unità di stockkeeping è 0."</span><span class="sxs-lookup"><span data-stu-id="897e4-186">I receive the following error message: "Maximum number of decimals for the stock keeping unit is 0."</span></span>

### <a name="issue-description"></a><span data-ttu-id="897e4-187">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="897e4-187">Issue description</span></span>

<span data-ttu-id="897e4-188">Quando si tenta di registrare una transazione di magazzino o una prenotazione di magazzino, viene visualizzato il seguente messaggio di errore: "Il numero massimo di decimali per l'unità di stockkeeping è 0."</span><span class="sxs-lookup"><span data-stu-id="897e4-188">When you try to post an inventory transaction or an inventory reservation, you receive the following error message: "Maximum number of decimals for the stock keeping unit is 0."</span></span>

<span data-ttu-id="897e4-189">Questo problema si verifica quando la quantità della transazione di magazzino viene specificata come valore decimale inferiore al livello di precisione supportato dal campo.</span><span class="sxs-lookup"><span data-stu-id="897e4-189">This issue occurs when the inventory transaction quantity is specified as a decimal value that is below the level of precision that the field supports.</span></span> <span data-ttu-id="897e4-190">Ad esempio, una quantità di *0,5* è stata specificato per una transazione di magazzino, ma sono supportate solo quantità intere.</span><span class="sxs-lookup"><span data-stu-id="897e4-190">For example, a quantity of *0.5* has been specified for an inventory transaction, but only integer quantities are supported.</span></span> <span data-ttu-id="897e4-191">Pertanto, il valore dovrebbe essere *1* invece di *0,5*.</span><span class="sxs-lookup"><span data-stu-id="897e4-191">Therefore, the value should be *1* instead of *0.5*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="897e4-192">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="897e4-192">Issue resolution</span></span>

1. <span data-ttu-id="897e4-193">Esegui il seguente script sull'istanza di SQL Server per arrotondare le quantità nelle transazioni di magazzino.</span><span class="sxs-lookup"><span data-stu-id="897e4-193">Run the following script on your SQL Server instance to round quantities in the inventory transactions.</span></span> <span data-ttu-id="897e4-194">Questo script correggerà i valori nella tabella **inventTrans**.</span><span class="sxs-lookup"><span data-stu-id="897e4-194">This script will correct values in the **inventTrans** table.</span></span>

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. <span data-ttu-id="897e4-195">Esegui un controllo di coerenza delle scorte disponibili dove l'opzione **correggi l'errore** è attivata.</span><span class="sxs-lookup"><span data-stu-id="897e4-195">Run an on-hand consistency check where the **fix error** option is turned on.</span></span> <span data-ttu-id="897e4-196">Questo controllo correggerà i valori nella tabella **inventSum**.</span><span class="sxs-lookup"><span data-stu-id="897e4-196">This check will correct values in the **inventSum** table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="897e4-197">Si consiglia vivamente di modificare con attenzione lo script come richiesto per il proprio ambiente, di testarlo in un ambiente di test e quindi di controllare i dati ottenuti prima di eseguire lo script in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="897e4-197">We strongly recommend that you carefully edit the script as required for your environment, test it in a test environment, and then check the resulting data before you run the script in a production environment.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]