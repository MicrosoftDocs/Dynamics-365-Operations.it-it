---
title: Divisione lavoro
description: In questo argomento vengono fornite informazioni sulla funzionalità di suddivisione del lavoro. Questa funzionalità consente di suddividere gli ordini di lavoro di grandi dimensioni in diversi ordini di lavoro più piccoli che è possibile quindi assegnare a più lavoratori di magazzino. In questo modo, lo stesso lavoro può essere prelevato contemporaneamente da più magazzinieri.
author: mirzaab
ms.date: 10/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: WHSWorkTableListPage
ms.author: mirzaab
ms.search.validFrom: 2020-10-15
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: eae1e722a7c4d819cbca398eb14a2b36fa04eec5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830764"
---
# <a name="work-split"></a><span data-ttu-id="d8670-105">Divisione lavoro</span><span class="sxs-lookup"><span data-stu-id="d8670-105">Work split</span></span>

<span data-ttu-id="d8670-106">La funzionalità di suddivisione del lavoro consente di suddividere gli ID ordini di lavoro di grandi dimensioni (ossia ordini di lavoro con molte righe) in diversi ID ordini di lavoro più piccoli che è possibile quindi assegnare a più lavoratori di magazzino.</span><span class="sxs-lookup"><span data-stu-id="d8670-106">Work split functionality lets you split large work IDs (that is, work orders that have several lines) into several smaller work IDs that you can then assign to multiple warehouse workers.</span></span> <span data-ttu-id="d8670-107">In questo modo, lo stesso numero di creazione lavoro può essere prelevato contemporaneamente da più magazzinieri.</span><span class="sxs-lookup"><span data-stu-id="d8670-107">In this way, the same work creation number can be picked simultaneously by several warehouse workers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8670-108">È possibile suddividere solo gli ordini di lavoro con stato *Aperto* o *In corso*.</span><span class="sxs-lookup"><span data-stu-id="d8670-108">You can split only work orders that have a status of *Open* or *In-progress*.</span></span>

## <a name="turn-on-the-work-split-functionality"></a><span data-ttu-id="d8670-109">Attivare la funzionalità di suddivisione del lavoro</span><span class="sxs-lookup"><span data-stu-id="d8670-109">Turn on the work split functionality</span></span>

<span data-ttu-id="d8670-110">Prima di poter utilizzare la funzionalità di suddivisione del lavoro, è necessario attivare la funzionalità e la relativa funzionalità prerequisito nel sistema.</span><span class="sxs-lookup"><span data-stu-id="d8670-110">Before you can use the work split functionality, you must turn on the feature and its prerequisite feature in your system.</span></span> <span data-ttu-id="d8670-111">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato delle funzioni e se necessario abilitarle.</span><span class="sxs-lookup"><span data-stu-id="d8670-111">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the features and turn them on as required.</span></span>

<span data-ttu-id="d8670-112">Innanzitutto, attivare la funzionalità prerequisito *Blocco del lavoro a livello di organizzazione* se non è già attivata.</span><span class="sxs-lookup"><span data-stu-id="d8670-112">First, turn on the prerequisite *Organization-wide work blocking* feature if it isn't already turned on.</span></span> <span data-ttu-id="d8670-113">Nell'area di lavoro **Gestione funzionalità**, questa funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d8670-113">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="d8670-114">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="d8670-114">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="d8670-115">**Nome funzionalità:** *Blocco del lavoro a livello di organizzazione*</span><span class="sxs-lookup"><span data-stu-id="d8670-115">**Feature name:** *Organization-wide work blocking*</span></span>

> [!NOTE]
> <span data-ttu-id="d8670-116">Quando questa funzione è attivata, un aggiornamento dei dati viene applicato automaticamente dopo che la funzione è stata attivata in tutte le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="d8670-116">When this feature is activated, a data upgrade is automatically applied after the feature is turned on across all legal entities.</span></span>

<span data-ttu-id="d8670-117">Quindi, attivare la funzionalità *Suddivisione lavoro* che è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d8670-117">Next, turn on the *Work split* feature, which is listed in the following way:</span></span>

- <span data-ttu-id="d8670-118">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="d8670-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="d8670-119">**Nome funzionalità:** *Suddivisione lavoro*</span><span class="sxs-lookup"><span data-stu-id="d8670-119">**Feature name:** *Work split*</span></span>

## <a name="enhancements-to-the-work-details-and-all-work-pages"></a><span data-ttu-id="d8670-120">Miglioramenti ai dettagli del lavoro e a tutte le pagine di lavoro</span><span class="sxs-lookup"><span data-stu-id="d8670-120">Enhancements to the Work details and All work pages</span></span>

<span data-ttu-id="d8670-121">La funzionalità *Suddivisione lavoro* aggiunge i seguenti due pulsanti alla scheda **Lavoro** nel riquadro azioni delle pagine **Dettagli lavoro** e **Tutto il lavoro**:</span><span class="sxs-lookup"><span data-stu-id="d8670-121">The *Work split* feature adds the following two buttons to the **Work** tab on the Action Pane of the **Work details** and **All work** pages:</span></span>

- <span data-ttu-id="d8670-122">**Suddivisione lavoro** – Dividere l'ID lavoro corrente in più ID lavoro di dimensioni minori che possono essere elaborati da lavoratori separati.</span><span class="sxs-lookup"><span data-stu-id="d8670-122">**Split work** – Split the current work ID into multiple smaller work IDs that can be processed by separate workers.</span></span>
- <span data-ttu-id="d8670-123">**Annulla sessione di suddivisione lavoro** - Annullare la sessione di suddivisione del lavoro e rendere il lavoro disponibile per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="d8670-123">**Cancel work split session** – Cancel the work split session, and make the work available for processing.</span></span>

<span data-ttu-id="d8670-124">![Pulsanti Suddivisione lavoro e Annulla sessione di suddivisione lavoro](media/Work_split_buttons.png "Pulsanti Suddivisione lavoro e Annulla sessione di suddivisione lavoro")</span><span class="sxs-lookup"><span data-stu-id="d8670-124">![Split work and Cancel work split session buttons](media/Work_split_buttons.png "Split work and Cancel work split session buttons")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8670-125">Il pulsante **Suddivisione lavoro** non sarà disponibile se viene soddisfatta una delle seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="d8670-125">The **Split work** button won't be available if any of the following conditions are met:</span></span>
>
> - <span data-ttu-id="d8670-126">Lo stato del lavoro è diverso da *Aperto* o *In corso*.</span><span class="sxs-lookup"><span data-stu-id="d8670-126">The work status is something other than *Open* or *In progress*.</span></span>
> - <span data-ttu-id="d8670-127">Un ID contenitore è associato all'ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8670-127">A container ID is associated with the work ID.</span></span> <span data-ttu-id="d8670-128">Un contenitore non può essere suddiviso sistematicamente, perché richiede azioni fisiche.</span><span class="sxs-lookup"><span data-stu-id="d8670-128">(A container can't be systematically split, because it requires physical actions.)</span></span>
> - <span data-ttu-id="d8670-129">Il lavoro è associato a un cluster.</span><span class="sxs-lookup"><span data-stu-id="d8670-129">The work is associated with a cluster.</span></span>
> - <span data-ttu-id="d8670-130">Il tipo di ordine di lavoro è diverso da uno dei seguenti tipi:</span><span class="sxs-lookup"><span data-stu-id="d8670-130">The work order type is something other than one of the following types:</span></span>
>
>    - <span data-ttu-id="d8670-131">Gestione ordini cliente</span><span class="sxs-lookup"><span data-stu-id="d8670-131">Sales orders</span></span>
>    - <span data-ttu-id="d8670-132">Prelievo materie prime</span><span class="sxs-lookup"><span data-stu-id="d8670-132">Raw material picking</span></span>
>    - <span data-ttu-id="d8670-133">Uscita di trasferimento</span><span class="sxs-lookup"><span data-stu-id="d8670-133">Transfer issue</span></span>
>
> - <span data-ttu-id="d8670-134">Il lavoro è attualmente suddiviso da un altro utente.</span><span class="sxs-lookup"><span data-stu-id="d8670-134">The work is currently being split by another user.</span></span> <span data-ttu-id="d8670-135">Se si tenta di aprire la pagina di suddivisione per il lavoro già suddiviso da un altro utente, viene visualizzato il seguente messaggio di errore: "Il lavoro con ID \#\#\#\# è attualmente suddiviso.</span><span class="sxs-lookup"><span data-stu-id="d8670-135">If you try to open the splitting page for work that is already being split by another user, you receive the following error message: "The work with ID \#\#\#\# is currently being split.</span></span> <span data-ttu-id="d8670-136">Riprovare tra qualche minuto.</span><span class="sxs-lookup"><span data-stu-id="d8670-136">Retry in a few minutes.</span></span> <span data-ttu-id="d8670-137">Se si continua a ricevere questo messaggio, contattare un supervisore."</span><span class="sxs-lookup"><span data-stu-id="d8670-137">If you continue to receive this message, contact a supervisor."</span></span>

<span data-ttu-id="d8670-138">Un nuovo motivo di blocco del lavoro, *Suddivisione lavoro*, indica quando l'ID lavoro è suddiviso.</span><span class="sxs-lookup"><span data-stu-id="d8670-138">A new work blocking reason, *Split work*, indicates when the work ID is in the process of being split.</span></span> <span data-ttu-id="d8670-139">È mostrato nella pagina **Suddivisione lavoro** e nell'app per dispositivi mobili Gestione magazzino se un utente tenta di eseguire il lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8670-139">It's shown both on the **Split work** page and in the Warehouse Management mobile app if a user tries to run the work.</span></span> <span data-ttu-id="d8670-140">Quando vengono utilizzati motivi di blocco, il nome del campo **Ciclo bloccato** dell'ID lavoro viene modificato in **Bloccato**.</span><span class="sxs-lookup"><span data-stu-id="d8670-140">When blocking reasons are used, the name of the **Blocked wave** field from the work ID is changed to **Blocked**.</span></span>

## <a name="initiate-a-work-split"></a><span data-ttu-id="d8670-141">Iniziare una suddivisione del lavoro</span><span class="sxs-lookup"><span data-stu-id="d8670-141">Initiate a work split</span></span>

<span data-ttu-id="d8670-142">La funzione aggiunge una nuova pagina **Suddivisione lavoro** che consente agli utenti di suddividere le righe di lavoro dell'ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8670-142">The feature adds a new **Split work** page that lets users split work lines from the work ID.</span></span> <span data-ttu-id="d8670-143">Quando la pagina viene aperta per la prima volta, mostra le righe che hanno uno stato di lavoro di *Aperto* e che sono disponibili per essere suddivise.</span><span class="sxs-lookup"><span data-stu-id="d8670-143">When the page is first opened, it shows lines that have a work status of *Open* and that are available to be split.</span></span> <span data-ttu-id="d8670-144">Nel riquadro azioni selezionare **Suddivisione lavoro** per elaborare il lavoro selezionato.</span><span class="sxs-lookup"><span data-stu-id="d8670-144">On the Action Pane, select **Split work** to process the selected work.</span></span>

<span data-ttu-id="d8670-145">Per suddividere il lavoro, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="d8670-145">To split work, follow these steps.</span></span>

1. <span data-ttu-id="d8670-146">Aprire una delle pagine di lavoro seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8670-146">Open one of the following work pages:</span></span>

    - <span data-ttu-id="d8670-147">**Dettagli lavoro** (**Gestione magazzino \> Lavoro \> Dettagli lavoro**)</span><span class="sxs-lookup"><span data-stu-id="d8670-147">**Work details** (**Warehouse management \> Work \> Work details**)</span></span>
    - <span data-ttu-id="d8670-148">**Tutti i lavori** (**Gestione magazzino \> Lavoro \> Tutti i lavori**)</span><span class="sxs-lookup"><span data-stu-id="d8670-148">**All work** (**Warehouse management \> Work \> All work**)</span></span>

1. <span data-ttu-id="d8670-149">Nella griglia, selezionare un ID lavoro da suddividere.</span><span class="sxs-lookup"><span data-stu-id="d8670-149">In the grid, select a work ID to split.</span></span> <span data-ttu-id="d8670-150">Il campo **Tipo di ordine di lavoro** deve essere impostato su uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d8670-150">The **Work order type** field must be set to one of the following values:</span></span>

    - <span data-ttu-id="d8670-151">Gestione ordini cliente</span><span class="sxs-lookup"><span data-stu-id="d8670-151">Sales orders</span></span>
    - <span data-ttu-id="d8670-152">Prelievo materie prime</span><span class="sxs-lookup"><span data-stu-id="d8670-152">Raw material picking</span></span>
    - <span data-ttu-id="d8670-153">Uscita di trasferimento</span><span class="sxs-lookup"><span data-stu-id="d8670-153">Transfer issue</span></span>

1. <span data-ttu-id="d8670-154">Nella scheda **Lavoro** del riquadro azioni, nel gruppo **Lavoro**, selezionare **Suddivisione lavoro**.</span><span class="sxs-lookup"><span data-stu-id="d8670-154">On the Action Pane, on the **Work** tab, in the **Work** group, select **Split work**.</span></span>

    <span data-ttu-id="d8670-155">La pagina **Suddivisione lavoro** viene visualizzata che mostra le righe di lavoro aperte e disponibili per la suddivisione.</span><span class="sxs-lookup"><span data-stu-id="d8670-155">The **Split work** page appears and shows the work lines that are open and available to be split.</span></span> <span data-ttu-id="d8670-156">Per impostazione predefinita, vengono visualizzate solo le righe di lavoro disponibili.</span><span class="sxs-lookup"><span data-stu-id="d8670-156">By default, only available work lines are shown.</span></span> <span data-ttu-id="d8670-157">Per visualizzare tutte le righe per l'ID lavoro (ad esempio, le righe che hanno un tipo di lavoro *Stoccaggio*), selezionare la casella di controllo **Mostra tutte le righe** sopra la griglia.</span><span class="sxs-lookup"><span data-stu-id="d8670-157">To view all lines for the work ID (for example, lines that have a work type of *Put*), select the **Show all lines** check box above the grid.</span></span>

    <span data-ttu-id="d8670-158">Viene visualizzato il seguente messaggio: "Gli utenti non possono elaborare le righe del lavoro finché non si termina la suddivisione e si chiude questa pagina".</span><span class="sxs-lookup"><span data-stu-id="d8670-158">The following message is shown: "Users can't process lines of the work until you finish splitting and close this page."</span></span>

    <span data-ttu-id="d8670-159">Il campo **Motivo del blocco di lavoro** per il lavoro corrente sarà impostato su *Suddivisione lavoro* e il lavoro verrà bloccato.</span><span class="sxs-lookup"><span data-stu-id="d8670-159">The **Work blocking reason** field for the current work will be set to *Split work*, and the work will be blocked.</span></span>

    <span data-ttu-id="d8670-160">![Motivo del blocco](media/Blocking_reason.png "Motivo del blocco")</span><span class="sxs-lookup"><span data-stu-id="d8670-160">![Blocking reason](media/Blocking_reason.png "Blocking reason")</span></span>

1. <span data-ttu-id="d8670-161">Selezionare le righe da rimuovere dall'ID lavoro corrente e aggiungerle a un nuovo ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8670-161">Select the lines to remove from the current work ID and add to a new work ID.</span></span> <span data-ttu-id="d8670-162">Si verificano gli eventi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8670-162">The following events occur:</span></span>

    - <span data-ttu-id="d8670-163">Quando si suddivide il lavoro, la riga o le righe selezionate dall'ID lavoro originale vengono annullate e quindi copiate in un nuovo ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8670-163">When you split the work, the selected line or lines from the original work ID are canceled and then copied to a new work ID.</span></span>
    - <span data-ttu-id="d8670-164">La struttura del modello di lavoro esistente e la posizione dello stoccaggio (e anche le future coppie prelievo/stoccaggio) vengono preservate.</span><span class="sxs-lookup"><span data-stu-id="d8670-164">The existing work template structure and the location of the put (and also future pick/put pairs) are preserved.</span></span> <span data-ttu-id="d8670-165">I valori per i seguenti campi ID lavoro vengono copiati dal lavoro originale al nuovo lavoro:</span><span class="sxs-lookup"><span data-stu-id="d8670-165">Values for the following work ID fields are copied from the original work to the new work:</span></span>

        - <span data-ttu-id="d8670-166">ID carico</span><span class="sxs-lookup"><span data-stu-id="d8670-166">Load ID</span></span>
        - <span data-ttu-id="d8670-167">ID spedizione</span><span class="sxs-lookup"><span data-stu-id="d8670-167">Shipment ID</span></span>
        - <span data-ttu-id="d8670-168">Tipo ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="d8670-168">Work order type</span></span>
        - <span data-ttu-id="d8670-169">Numero ordine</span><span class="sxs-lookup"><span data-stu-id="d8670-169">Order number</span></span>
        - <span data-ttu-id="d8670-170">Sito</span><span class="sxs-lookup"><span data-stu-id="d8670-170">Site</span></span>
        - <span data-ttu-id="d8670-171">Magazzino</span><span class="sxs-lookup"><span data-stu-id="d8670-171">Warehouse</span></span>
        - <span data-ttu-id="d8670-172">Priorità lavoro</span><span class="sxs-lookup"><span data-stu-id="d8670-172">Work priority</span></span>
        - <span data-ttu-id="d8670-173">ID pool lavoro</span><span class="sxs-lookup"><span data-stu-id="d8670-173">Work pool ID</span></span>
        - <span data-ttu-id="d8670-174">ID ondata</span><span class="sxs-lookup"><span data-stu-id="d8670-174">Wave ID</span></span>
        - <span data-ttu-id="d8670-175">Numero creazione lavoro</span><span class="sxs-lookup"><span data-stu-id="d8670-175">Work creation number</span></span>

    - <span data-ttu-id="d8670-176">I seguenti campi non vengono copiati nel nuovo ID lavoro:</span><span class="sxs-lookup"><span data-stu-id="d8670-176">The following fields aren't copied to the new work ID:</span></span>

        - <span data-ttu-id="d8670-177">**ID lavoro** - Viene generato un nuovo ID lavoro dalla sequenza numerica appropriata.</span><span class="sxs-lookup"><span data-stu-id="d8670-177">**Work ID** – A new work ID is generated from the appropriate number sequence.</span></span>
        - <span data-ttu-id="d8670-178">**Stato lavoro** - Questo campo è impostato su *Aperto*.</span><span class="sxs-lookup"><span data-stu-id="d8670-178">**Work status** – This field is set to *Open*.</span></span>
        - <span data-ttu-id="d8670-179">**Bloccato da** - Questo campo è inizialmente impostato su vuoto.</span><span class="sxs-lookup"><span data-stu-id="d8670-179">**Locked by** – This field is initially set to blank.</span></span>
        - <span data-ttu-id="d8670-180">**ID targa di destinazione** - Questo campo è lasciato vuoto.</span><span class="sxs-lookup"><span data-stu-id="d8670-180">**Target license plate ID** – This field is left blank.</span></span>
        - <span data-ttu-id="d8670-181">**Data e ora di creazione** - Questo campo è impostato sulla data e l'ora correnti.</span><span class="sxs-lookup"><span data-stu-id="d8670-181">**Created date and time** – This field is set to the current date and time.</span></span>
        - <span data-ttu-id="d8670-182">**Ciclo bloccato/Congelato** - Questo campo viene ricalcolato per l'ID lavoro originale e il nuovo ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8670-182">**Blocked wave/frozen** – This field is recomputed for the original work ID and the new work ID.</span></span>

1. <span data-ttu-id="d8670-183">Nel riquadro azioni, selezionare **Suddivisione lavoro**.</span><span class="sxs-lookup"><span data-stu-id="d8670-183">On the Action Pane, select **Split work**.</span></span>

<span data-ttu-id="d8670-184">Durante la suddivisione del lavoro, viene visualizzato il seguente messaggio: "Operazione di elaborazione - Suddivisione lavoro".</span><span class="sxs-lookup"><span data-stu-id="d8670-184">While the work is being split, the following message is shown: "Processing operation - Split work".</span></span> <span data-ttu-id="d8670-185">Mentre questo messaggio è visibile, è possibile annullare l'operazione selezionando **Annulla** nella finestra del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d8670-185">While this message is visible, you can cancel the operation by selecting **Cancel** in the message box.</span></span>

<span data-ttu-id="d8670-186">Se la casella di controllo **Mostra tutte le righe** è deselezionata, la riga che era stata suddivisa e annullata non apparirà più nella griglia.</span><span class="sxs-lookup"><span data-stu-id="d8670-186">If the **Show all lines** check box is cleared, the line that was split off and canceled will no longer appear in the grid.</span></span> <span data-ttu-id="d8670-187">Se la casella di controllo è selezionata, il valore del campo **Stato lavoro** per quella riga cambia in *Annullato*.</span><span class="sxs-lookup"><span data-stu-id="d8670-187">If the check box is selected, you should see that the value of the **Work status** field for that line has changed to *Canceled*.</span></span>

<span data-ttu-id="d8670-188">Viene visualizzata la seguente notifica per indicare che il nuovo ID lavoro è stato creato: "Il lavoro \#\#\#\# è stato creato con la suddivisione dal lavoro originale \#\#\#\#."</span><span class="sxs-lookup"><span data-stu-id="d8670-188">The following notification is shown to indicate that the new work ID has been created: "Work \#\#\#\# has been created by splitting off from original work \#\#\#\#."</span></span>

<span data-ttu-id="d8670-189">Altre righe di lavoro dell'ID lavoro originale (come righe di *stoccaggio*) saranno regolate come richiesto per riflettere le righe di lavoro che sono state annullate.</span><span class="sxs-lookup"><span data-stu-id="d8670-189">Other work lines from the original work ID (such as *Put* lines) will be adjusted as required to reflect the lines of work that have been canceled.</span></span> <span data-ttu-id="d8670-190">Ad esempio, se l'ID lavoro originale aveva una riga di *stoccaggio* per una quantità di 15 e le righe di *prelievo* che hanno una quantità totale di 10 sono state annullate, la nuova quantità di *prelievo* dell'ID lavoro originale sarà ora 5.</span><span class="sxs-lookup"><span data-stu-id="d8670-190">For example, if the original work ID had a *Put* line for a quantity of 15, and *Pick* lines that have a total quantity of 10 were canceled, the new *Put* quantity on the original work ID will now be 5.</span></span>

<span data-ttu-id="d8670-191">Il nuovo lavoro non verrà assegnato immediatamente a nessun utente.</span><span class="sxs-lookup"><span data-stu-id="d8670-191">The new work won't immediately be assigned to any user.</span></span> <span data-ttu-id="d8670-192">Tuttavia, è possibile assegnarlo a un utente ora, come richiesto, utilizzando la funzionalità standard della pagina **Dettagli lavoro**.</span><span class="sxs-lookup"><span data-stu-id="d8670-192">However, you can assign it to a user now, as required, by using the standard functionality of the **Work details** page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8670-193">È possibile suddividere solo gli ID lavoro che contengono due o più righe di lavoro disponibili.</span><span class="sxs-lookup"><span data-stu-id="d8670-193">You can split only work IDs that contain two or more available work lines.</span></span> <span data-ttu-id="d8670-194">Se si seleziona **Suddivisione lavoro** quando è presente una sola riga di lavoro, verrà visualizzato il seguente messaggio di errore: "Almeno una riga di lavoro deve rimanere sul lavoro iniziale".</span><span class="sxs-lookup"><span data-stu-id="d8670-194">If you select **Split work** when there is only one work line, you will receive the following error message: "At least one work line must remain on initial work."</span></span> <span data-ttu-id="d8670-195">In questo caso, non si verificherà alcuna suddivisione.</span><span class="sxs-lookup"><span data-stu-id="d8670-195">In this case, no splitting will occur.</span></span>

## <a name="finish-a-work-split"></a><span data-ttu-id="d8670-196">Finire una suddivisione del lavoro</span><span class="sxs-lookup"><span data-stu-id="d8670-196">Finish a work split</span></span>

<span data-ttu-id="d8670-197">Per finire la suddivisione del lavoro, il motivo di blocco *Suddivisione lavoro* deve essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="d8670-197">To finish splitting work, the *Split work* blocking reason must be removed.</span></span> <span data-ttu-id="d8670-198">Sono disponibili due modi per eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="d8670-198">There are two ways to complete this step:</span></span>

- <span data-ttu-id="d8670-199">L'utente che sta suddividendo il lavoro chiude la pagina **Suddivisione lavoro** selezionando il pulsante **Chiudi** (**X**) nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="d8670-199">The user who is splitting the work closes the **Split work** page by selecting the **Close** button (**X**) in the upper-right corner.</span></span> <span data-ttu-id="d8670-200">Quando la pagina è chiusa, il motivo del blocco *Suddivisione lavoro* verrà rimosso.</span><span class="sxs-lookup"><span data-stu-id="d8670-200">When the page is closed, the *Split Work* blocking reason will be removed.</span></span> <span data-ttu-id="d8670-201">Lo stato *Bloccato* di questo lavoro verrà ricalcolato e, se non ci sono motivi di blocco rimanenti per questo lavoro, il lavoro verrà sbloccato.</span><span class="sxs-lookup"><span data-stu-id="d8670-201">The *Blocked* state of this work will be recomputed and, if there are no remaining blocking reasons for this work, the work will be unblocked.</span></span>
- <span data-ttu-id="d8670-202">Un utente apre l'ID lavoro e seleziona il pulsante **Annulla sessione di suddivisione lavoro** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="d8670-202">Any user opens the work ID and selects the **Cancel work split session** button on the Action Pane.</span></span> <span data-ttu-id="d8670-203">Il motivo di blocco *Suddivisione lavoro* verrà rimosso e lo stato *Bloccato* di questo lavoro verrà ricalcolato, proprio come quando la pagina **Suddivisione lavoro** viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="d8670-203">The *Split work* blocking reason will be removed, and the *Blocked* state of this work will be recomputed, just as when the **Split work** page is closed.</span></span>

<span data-ttu-id="d8670-204">Dopo che il motivo di blocco *Suddivisione lavoro* viene rimosso, il lavoro può essere eseguito sul dispositivo mobile, a condizione che lo stato **Bloccato** è impostato su *No* sull'ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8670-204">After the *Split work* blocking reason is removed, the work can be run on the mobile device, provided that the **Blocked** state is set to *No* on the work ID.</span></span>

## <a name="user-blocking-on-the-warehouse-management-mobile-app"></a><span data-ttu-id="d8670-205">Blocco dell'utente nell'app per dispositivi mobili Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="d8670-205">User blocking on the Warehouse Management mobile app</span></span>

<span data-ttu-id="d8670-206">Se tenti di usare l'app per dispositivi mobili Gestione magazzino per eseguire un lavoro di prelievo per un ID lavoro suddiviso, viene visualizzato il seguente messaggio di errore: "Il lavoro con ID \#\#\#\# è attualmente suddiviso."</span><span class="sxs-lookup"><span data-stu-id="d8670-206">If you try to use the Warehouse Management mobile app to run picking work against a work ID that is being split, you will receive the following error message: "The work with ID \#\#\#\# is currently being split."</span></span> <span data-ttu-id="d8670-207">Se viene visualizzato questo messaggio di errore, selezionare **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="d8670-207">If you receive this message, select **Cancel**.</span></span> <span data-ttu-id="d8670-208">È quindi possibile continuare a elaborare altri lavori.</span><span class="sxs-lookup"><span data-stu-id="d8670-208">You can then continue to process other work.</span></span>

## <a name="other-blocked-operations"></a><span data-ttu-id="d8670-209">Altre operazioni bloccate</span><span class="sxs-lookup"><span data-stu-id="d8670-209">Other blocked operations</span></span>

<span data-ttu-id="d8670-210">Tutte le operazioni che modificano le righe di lavoro, le transazioni di inventario del lavoro o i collegamenti di rifornimento correlati al lavoro che viene suddiviso non avranno esito positivo e verrà visualizzato il seguente messaggio di errore: "Il lavoro con ID \#\#\#\# è attualmente suddiviso."</span><span class="sxs-lookup"><span data-stu-id="d8670-210">Any operations that modify work lines, work inventory transactions, or replenishment links that are related to work that is being split will fail, and the following error message will be shown: "The work with ID \#\#\#\# is currently being split."</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]