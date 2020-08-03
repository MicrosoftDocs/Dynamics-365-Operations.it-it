---
title: Gruppi del modello di ondata
description: Il raggruppamento dei modelli di ondate consente al sistema di utilizzare le configurazioni dei modelli di ondata per determinare, in base a criteri definiti, come dividere le righe rilasciate e assegnarle a ondate nuove o esistenti. Questa funzione può essere utile nei magazzini in cui le ondate vengono create in base a criteri specifici, ma in cui i responsabili preferiscono creare le ondate automaticamente anziché manualmente.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 4dd188cbd17cfed372283ecb3389633b0c0021eb
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "3530468"
---
# <a name="wave-template-grouping"></a><span data-ttu-id="da498-104">Gruppi del modello di ondata</span><span class="sxs-lookup"><span data-stu-id="da498-104">Wave template grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="da498-105">Il raggruppamento dei modelli di ondate consente al sistema di utilizzare le configurazioni dei [modelli di ondata](tasks/configure-wave-processing.md) per determinare, in base a criteri definiti, come dividere le righe rilasciate e assegnarle a ondate nuove o esistenti.</span><span class="sxs-lookup"><span data-stu-id="da498-105">Wave template grouping enables the system to use [wave template](tasks/configure-wave-processing.md) setups to determine, based on criteria that you define, how it should split released lines and assign them to new or existing waves.</span></span> <span data-ttu-id="da498-106">Questa funzione può essere utile nei magazzini in cui le ondate vengono create in base a criteri specifici, ma in cui i responsabili preferiscono creare le ondate automaticamente anziché manualmente.</span><span class="sxs-lookup"><span data-stu-id="da498-106">This feature can be useful in warehouses where waves are created based on specific criteria, but where managers prefer to create waves automatically instead of manually.</span></span> <span data-ttu-id="da498-107">Consente al sistema di aggiungere ogni spedizione appena rilasciata alla prima ondata rilevata con valori di campo di raggruppamento corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="da498-107">It enables the system to add each newly released shipment to the first wave that it finds that has matching grouping field values.</span></span> <span data-ttu-id="da498-108">Se non viene trovata alcuna corrispondenza, il sistema crea una nuova ondata per la nuova spedizione.</span><span class="sxs-lookup"><span data-stu-id="da498-108">If no match is found, the system creates a new wave for the new shipment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da498-109">Il raggruppamento dei modelli di ondata non è supportato per i tipi di lavoro *prelievo di materie prime di produzione* o *Prelievo kanban*.</span><span class="sxs-lookup"><span data-stu-id="da498-109">Wave template grouping isn't supported for the work types *production raw material picking* or *Kanban picking*.</span></span> <span data-ttu-id="da498-110">Questo perché il raggruppamento delle ondate si basa sulle spedizioni e questi tipi di lavoro non utilizzano le spedizioni.</span><span class="sxs-lookup"><span data-stu-id="da498-110">This is because wave grouping is based on shipments and these work types don't use shipments.</span></span>

## <a name="turn-on-the-wave-template-grouping-feature"></a><span data-ttu-id="da498-111">Attivare la funzione di raggruppamento dei modelli di ondata</span><span class="sxs-lookup"><span data-stu-id="da498-111">Turn on the Wave template grouping feature</span></span>

<span data-ttu-id="da498-112">Prima di poter utilizzare la funzionalità *Raggruppamento modello ondata*, deve essere attivata nel sistema.</span><span class="sxs-lookup"><span data-stu-id="da498-112">Before you can use the *Wave template grouping* feature, it must be turned on in your system.</span></span> <span data-ttu-id="da498-113">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla.</span><span class="sxs-lookup"><span data-stu-id="da498-113">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="da498-114">Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="da498-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="da498-115">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="da498-115">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="da498-116">**Nome funzionalità:** *Raggruppamento modello ondata*</span><span class="sxs-lookup"><span data-stu-id="da498-116">**Feature name:** *Wave template grouping*</span></span>

## <a name="set-a-wave-template-to-use-wave-template-grouping"></a><a name="set-up-template"></a><span data-ttu-id="da498-117">Impostare un modello di ondata per utilizzare il raggruppamento modello ondata</span><span class="sxs-lookup"><span data-stu-id="da498-117">Set a wave template to use wave template grouping</span></span>

<span data-ttu-id="da498-118">Per rendere disponibile il raggruppamento modello ondata, attieniti alla seguente procedura per configurare il [modello di ondata](tasks/configure-wave-processing.md).</span><span class="sxs-lookup"><span data-stu-id="da498-118">To make wave template grouping available, follow these steps to set up your [wave template](tasks/configure-wave-processing.md).</span></span>

1. <span data-ttu-id="da498-119">Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.</span><span class="sxs-lookup"><span data-stu-id="da498-119">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="da498-120">Nel riquadro sinistro, seleziona il modello di ondata da configurare.</span><span class="sxs-lookup"><span data-stu-id="da498-120">In the left pane, select the wave template to set up.</span></span> <span data-ttu-id="da498-121">Se ti stai preparando a lavorare sullo scenario più avanti in questo argomento usando i dati demo, seleziona il modello **62 Spedizione predefinita**.</span><span class="sxs-lookup"><span data-stu-id="da498-121">If you're preparing to work through the scenario later in this topic by using demo data, select the **62 Shipping default** template.</span></span>
1. <span data-ttu-id="da498-122">Seleziona **Modifica** per mettere la pagina in modalità modifica.</span><span class="sxs-lookup"><span data-stu-id="da498-122">Select **Edit** to put the page into edit mode.</span></span>
1. <span data-ttu-id="da498-123">Nella Scheda dettaglio **Generale**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="da498-123">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="da498-124">**Automatizza creazione ondata:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="da498-124">**Automate wave creation:** *Yes*</span></span>
    - <span data-ttu-id="da498-125">**Assegna a ondate aperte:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="da498-125">**Assign to open waves:** *Yes*</span></span>
    - <span data-ttu-id="da498-126">**Elabora ondata al rilascio in magazzino:** *No*</span><span class="sxs-lookup"><span data-stu-id="da498-126">**Process wave at release to warehouse:** *No*</span></span>

1. <span data-ttu-id="da498-127">Nel riquadro azioni, seleziona **Modifica query** per aprire la finestra di dialogo dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="da498-127">On the Action Pane, select **Edit query** to open the query dialog box.</span></span>
1. <span data-ttu-id="da498-128">Nella finestra di dialogo della query, nella scheda **Ordinamento**, rivedi i criteri di ordinamento e assicurati che esista una regola che includa il campo che vuoi utilizzare per raggruppare le ondate.</span><span class="sxs-lookup"><span data-stu-id="da498-128">In the query dialog box, on the **Sorting** tab, review the sorting criteria, and make sure that there is a rule that includes the field that you want to use to group your waves.</span></span>

    <span data-ttu-id="da498-129">Se ti stai preparando a utilizzare lo scenario utilizzando i dati demo, aggiungi una riga con i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="da498-129">If you're preparing to work through the scenario by using demo data, add a row that has the following values:</span></span>

    - <span data-ttu-id="da498-130">**Tabella:** *Spedizioni*</span><span class="sxs-lookup"><span data-stu-id="da498-130">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="da498-131">**Tabella derivata:** *Spedizioni*</span><span class="sxs-lookup"><span data-stu-id="da498-131">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="da498-132">**Campo:** *Servizio trasporto*</span><span class="sxs-lookup"><span data-stu-id="da498-132">**Field:** *Carrier service*</span></span>

        > [!NOTE]
        > <span data-ttu-id="da498-133">Dopo aver selezionato questo valore, è possibile che venga visualizzato il messaggio seguente: "Il servizio di trasporto non è un campo indice.</span><span class="sxs-lookup"><span data-stu-id="da498-133">After you select this value, you might receive the following message: "Field Carrier service is not an index field.</span></span> <span data-ttu-id="da498-134">Vuoi aggiungere l'ordinamento su questo? "</span><span class="sxs-lookup"><span data-stu-id="da498-134">Do you want to add sorting on this?"</span></span> <span data-ttu-id="da498-135">Seleziona **Sì** per aggiungere l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="da498-135">Select **Yes** to add sorting.</span></span>

    - <span data-ttu-id="da498-136">**Direzione di ricerca:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="da498-136">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="da498-137">Seleziona **OK** per salvare le modifiche e chiudere la finestra di dialogo della query.</span><span class="sxs-lookup"><span data-stu-id="da498-137">Select **OK** to save your changes and close the query dialog box.</span></span>
1. <span data-ttu-id="da498-138">Nel riquadro azioni seleziona **Raggruppamento modello ondata**.</span><span class="sxs-lookup"><span data-stu-id="da498-138">On the Action Pane, select **Wave template grouping**.</span></span>
1. <span data-ttu-id="da498-139">Nella pagina **Raggruppamento modello ondata**, seleziona la casella di controllo **Raggruppa per** per ogni riga che si desidera utilizzare per raggruppare le righe dell'ordine in ondate, come richiesto.</span><span class="sxs-lookup"><span data-stu-id="da498-139">On the **Wave template grouping** page, select the **Group by** check box for each row that you want to use to group your order lines into waves, as required.</span></span> <span data-ttu-id="da498-140">Se ti stai preparando a elaborare lo scenario utilizzando i dati demo, seleziona la casella di controllo **Raggruppa per** controllo per la riga *Servizio trasporto*.</span><span class="sxs-lookup"><span data-stu-id="da498-140">If you're preparing to work through the scenario by using demo data, select the **Group by** check box for the *Carrier service* row.</span></span>
1. <span data-ttu-id="da498-141">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="da498-141">Select **Save**.</span></span>
1. <span data-ttu-id="da498-142">Chiudi la pagina **Raggruppamento modello ondata**.</span><span class="sxs-lookup"><span data-stu-id="da498-142">Close the **Wave template grouping** page.</span></span>
1. <span data-ttu-id="da498-143">Seleziona **Salva** per salvare il modello.</span><span class="sxs-lookup"><span data-stu-id="da498-143">Select **Save** to save your template.</span></span>

## <a name="scenario"></a><span data-ttu-id="da498-144">Scenario</span><span class="sxs-lookup"><span data-stu-id="da498-144">Scenario</span></span>

<span data-ttu-id="da498-145">Questa sezione fornisce uno script che è possibile elaborare per apprendere cosa fa questa funzionalità e come utilizzarla.</span><span class="sxs-lookup"><span data-stu-id="da498-145">This section provides a script that you can work through to learn what this feature does and how to work with it.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="da498-146">Rendi disponibili i dati di esempio</span><span class="sxs-lookup"><span data-stu-id="da498-146">Make sample data available</span></span>

<span data-ttu-id="da498-147">Per elaborare lo scenario utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard.</span><span class="sxs-lookup"><span data-stu-id="da498-147">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="da498-148">È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="da498-148">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="da498-149">È inoltre possibile utilizzare questo scenario come indicazioni per l'utilizzo di questa funzionalità quando si lavora su un sistema di produzione.</span><span class="sxs-lookup"><span data-stu-id="da498-149">You can also use this scenario as guidance for using the feature when you work on a production system.</span></span> <span data-ttu-id="da498-150">Tuttavia, in questo caso, è necessario sostituire i propri valori e potrebbero mancare alcuni tipi di record richiesti forniti dai dati demo standard.</span><span class="sxs-lookup"><span data-stu-id="da498-150">However, in that case, you must substitute your own values, and you might be missing some types of required records that the standard demo data provides.</span></span>

### <a name="scenario-wave-template-grouping"></a><span data-ttu-id="da498-151">Scenario: raggruppamento modello ondata</span><span class="sxs-lookup"><span data-stu-id="da498-151">Scenario: Wave template grouping</span></span>

<span data-ttu-id="da498-152">Questo scenario mostra come utilizzare il raggruppamento dei modelli di ondata per creare automaticamente più ondate, in base a criteri di raggruppamento definiti in un modello di ondata.</span><span class="sxs-lookup"><span data-stu-id="da498-152">This scenario shows how to use wave template grouping to automatically create multiple waves, based on grouping criteria that are defined in a wave template.</span></span> <span data-ttu-id="da498-153">In questo scenario, il modello di ondata è impostato nel sistema per creare un'ondata per servizio di trasporto.</span><span class="sxs-lookup"><span data-stu-id="da498-153">In this scenario, the wave template is set up in the system to create one wave per carrier service.</span></span>

<span data-ttu-id="da498-154">Prima di iniziare, prepara il modello di ondata come descritto in precedenza nella sezione [Impostare un modello di ondata per utilizzare il raggruppamento modello ondata](#set-up-template) in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="da498-154">Before you begin, prepare your wave template as described in the [Set a wave template to use wave template grouping](#set-up-template) section earlier in this topic.</span></span> <span data-ttu-id="da498-155">Se lavorerai con i dati dimostrativi per questo scenario, assicurati di usare i valori dei dati dimostrativi suggeriti in quella procedura.</span><span class="sxs-lookup"><span data-stu-id="da498-155">If you will be working with demo data for this scenario, be sure to use the demo data values that are suggested in that procedure.</span></span> <span data-ttu-id="da498-156">Questa configurazione raggrupperà le ondate in base al servizio di trasporto impostato per ciascun ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-156">This setup will group your waves according to the carrier service that is set for each sales order.</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="da498-157">Creare l'ordine cliente 1</span><span class="sxs-lookup"><span data-stu-id="da498-157">Create sales order 1</span></span>

1. <span data-ttu-id="da498-158">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="da498-158">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="da498-159">Selezionare **Nuovo** per creare un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-159">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="da498-160">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="da498-160">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="da498-161">Nella Scheda dettaglio **Cliente**, imposta il campo **Conto cliente** su *US-004*.</span><span class="sxs-lookup"><span data-stu-id="da498-161">On the **Customer** FastTab, set the **Customer account** field to *US-004*.</span></span>
    - <span data-ttu-id="da498-162">Nel campo **Magazzino** della Scheda dettaglio **Generale**, seleziona *62*.</span><span class="sxs-lookup"><span data-stu-id="da498-162">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="da498-163">Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo **Crea ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="da498-163">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="da498-164">Il nuovo ordine cliente viene aperto nella visualizzazione **Righe**.</span><span class="sxs-lookup"><span data-stu-id="da498-164">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="da498-165">Prendi nota del numero di ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-165">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="da498-166">Passa alla visualizzazione **Intestazione**.</span><span class="sxs-lookup"><span data-stu-id="da498-166">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="da498-167">Nella Scheda dettaglio **Consegna**, nella sezione **Trasporti**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="da498-167">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="da498-168">**Vettore spedizione:** *Air cargo*</span><span class="sxs-lookup"><span data-stu-id="da498-168">**Shipping carrier:** *Air cargo*</span></span>
    - <span data-ttu-id="da498-169">**Servizio trasporto:** *Air*</span><span class="sxs-lookup"><span data-stu-id="da498-169">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="da498-170">Torna alla visualizzazione **Righe**.</span><span class="sxs-lookup"><span data-stu-id="da498-170">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="da498-171">Nella sezione **Righe ordine cliente**, seleziona **Aggiungi riga** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="da498-171">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="da498-172">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="da498-172">On the new line, set the following values:</span></span>

    - <span data-ttu-id="da498-173">**Numero articolo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="da498-173">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="da498-174">**Quantità:** *2*</span><span class="sxs-lookup"><span data-stu-id="da498-174">**Quantity:** *2*</span></span>

1. <span data-ttu-id="da498-175">Seleziona la nuova riga ordine, quindi sul menu **Scorte** sopra la griglia, seleziona **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="da498-175">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="da498-176">Nella pagina **Prenotazione**, nel riquadro azioni, seleziona **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="da498-176">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="da498-177">Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-177">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="da498-178">Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="da498-178">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="da498-179">Riceverai un messaggio informativo che mostra la spedizione e l'ondata per questo ordine.</span><span class="sxs-lookup"><span data-stu-id="da498-179">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="da498-180">Prendi nota del numero ID ondata e i numeri ID spedizione.</span><span class="sxs-lookup"><span data-stu-id="da498-180">Make a note of the wave ID number and the shipment ID numbers.</span></span>

#### <a name="view-the-wave-that-was-created-from-sales-order-1"></a><span data-ttu-id="da498-181">Visualizzare l'ondata creata dall'ordine cliente 1</span><span class="sxs-lookup"><span data-stu-id="da498-181">View the wave that was created from sales order 1</span></span>

1. <span data-ttu-id="da498-182">Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.</span><span class="sxs-lookup"><span data-stu-id="da498-182">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="da498-183">Seleziona l'ID ondata creato dall'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-183">Select the wave ID that was created from the sales order.</span></span>
1. <span data-ttu-id="da498-184">Seleziona il collegamento ID ondata per aprire la pagina Dettagli ondata.</span><span class="sxs-lookup"><span data-stu-id="da498-184">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="da498-185">Nota che la spedizione è stata aggiunta alla Scheda dettaglio **Righe ondata**.</span><span class="sxs-lookup"><span data-stu-id="da498-185">Notice that the shipment has been added to the **Wave lines** FastTab.</span></span>

#### <a name="create-sales-order-2"></a><span data-ttu-id="da498-186">Creare l'ordine cliente 2</span><span class="sxs-lookup"><span data-stu-id="da498-186">Create sales order 2</span></span>

1. <span data-ttu-id="da498-187">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="da498-187">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="da498-188">Selezionare **Nuovo** per creare un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-188">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="da498-189">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="da498-189">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="da498-190">Nella Scheda dettaglio **Cliente**, imposta il campo **Conto cliente** su *US-005*.</span><span class="sxs-lookup"><span data-stu-id="da498-190">On the **Customer** FastTab, set the **Customer account** field to *US-005*.</span></span>
    - <span data-ttu-id="da498-191">Nel campo **Magazzino** della Scheda dettaglio **Generale**, seleziona *62*.</span><span class="sxs-lookup"><span data-stu-id="da498-191">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="da498-192">Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo **Crea ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="da498-192">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="da498-193">Il nuovo ordine cliente viene aperto nella visualizzazione **Righe**.</span><span class="sxs-lookup"><span data-stu-id="da498-193">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="da498-194">Prendi nota del numero di ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-194">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="da498-195">Passa alla visualizzazione **Intestazione**.</span><span class="sxs-lookup"><span data-stu-id="da498-195">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="da498-196">Nella Scheda dettaglio **Consegna**, nella sezione **Trasporti**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="da498-196">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="da498-197">**Vettore spedizione:** *Flower moving*</span><span class="sxs-lookup"><span data-stu-id="da498-197">**Shipping carrier:** *Flower moving*</span></span>
    - <span data-ttu-id="da498-198">**Servizio trasporto:** *Std*</span><span class="sxs-lookup"><span data-stu-id="da498-198">**Carrier service:** *Std*</span></span>

1. <span data-ttu-id="da498-199">Torna alla visualizzazione **Righe**.</span><span class="sxs-lookup"><span data-stu-id="da498-199">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="da498-200">Nella sezione **Righe ordine cliente**, seleziona **Aggiungi riga** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="da498-200">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="da498-201">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="da498-201">On the new line, set the following values:</span></span>

    - <span data-ttu-id="da498-202">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="da498-202">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="da498-203">**Quantità:** *1*</span><span class="sxs-lookup"><span data-stu-id="da498-203">**Quantity:** *1*</span></span>

1. <span data-ttu-id="da498-204">Seleziona la nuova riga ordine, quindi sul menu **Scorte** sopra la griglia, seleziona **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="da498-204">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="da498-205">Nella pagina **Prenotazione**, nel riquadro azioni, seleziona **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="da498-205">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="da498-206">Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-206">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="da498-207">Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="da498-207">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="da498-208">Riceverai un messaggio informativo che mostra la spedizione e l'ondata per questo ordine.</span><span class="sxs-lookup"><span data-stu-id="da498-208">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="da498-209">Prendi nota del numero ID ondata e i numeri ID spedizione.</span><span class="sxs-lookup"><span data-stu-id="da498-209">Make a note of the wave ID number and the shipment ID numbers.</span></span> <span data-ttu-id="da498-210">Nota l'ID ondata differisce dall'ID ondata del primo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-210">Notice that the wave ID differs from the wave ID of the first sales order.</span></span>

#### <a name="view-the-wave-that-was-created-from-sales-order-2"></a><span data-ttu-id="da498-211">Visualizzare l'ondata creata dall'ordine cliente 2</span><span class="sxs-lookup"><span data-stu-id="da498-211">View the wave that was created from sales order 2</span></span>

1. <span data-ttu-id="da498-212">Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.</span><span class="sxs-lookup"><span data-stu-id="da498-212">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="da498-213">Seleziona l'ID ondata creato dal secondo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-213">Select the wave ID that was created from the second sales order.</span></span>
1. <span data-ttu-id="da498-214">Seleziona il collegamento ID ondata per aprire la pagina Dettagli ondata.</span><span class="sxs-lookup"><span data-stu-id="da498-214">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="da498-215">Nota che la spedizione è stata aggiunta alla Scheda dettaglio **Righe ondata**.</span><span class="sxs-lookup"><span data-stu-id="da498-215">Notice that the shipment has been added to the **Wave lines** FastTab.</span></span>

<span data-ttu-id="da498-216">È stata creata una nuova ondata per questa spedizione, poiché utilizza un servizio di trasporto diverso dal primo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-216">A new wave was created for this shipment, because it uses a different carrier service than the first sales order.</span></span>

#### <a name="create-sales-order-3"></a><span data-ttu-id="da498-217">Creare l'ordine cliente 3</span><span class="sxs-lookup"><span data-stu-id="da498-217">Create sales order 3</span></span>

1. <span data-ttu-id="da498-218">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="da498-218">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="da498-219">Selezionare **Nuovo** per creare un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-219">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="da498-220">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="da498-220">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="da498-221">Nella Scheda dettaglio **Cliente**, imposta il campo **Conto cliente** su *US-006*.</span><span class="sxs-lookup"><span data-stu-id="da498-221">On the **Customer** FastTab, set the **Customer account** field to *US-006*.</span></span>
    - <span data-ttu-id="da498-222">Nel campo **Magazzino** della Scheda dettaglio **Generale**, seleziona *62*.</span><span class="sxs-lookup"><span data-stu-id="da498-222">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="da498-223">Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo **Crea ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="da498-223">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="da498-224">Il nuovo ordine cliente viene aperto nella visualizzazione **Righe**.</span><span class="sxs-lookup"><span data-stu-id="da498-224">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="da498-225">Prendi nota del numero di ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-225">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="da498-226">Passa alla visualizzazione **Intestazione**.</span><span class="sxs-lookup"><span data-stu-id="da498-226">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="da498-227">Nella Scheda dettaglio **Consegna**, nella sezione **Trasporti**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="da498-227">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="da498-228">**Vettore spedizione:** *Air Cargo*</span><span class="sxs-lookup"><span data-stu-id="da498-228">**Shipping carrier:** *Air Cargo*</span></span>
    - <span data-ttu-id="da498-229">**Servizio trasporto:** *Air*</span><span class="sxs-lookup"><span data-stu-id="da498-229">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="da498-230">Torna alla visualizzazione **Righe**.</span><span class="sxs-lookup"><span data-stu-id="da498-230">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="da498-231">Nella sezione **Righe ordine cliente**, seleziona **Aggiungi riga** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="da498-231">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="da498-232">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="da498-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="da498-233">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="da498-233">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="da498-234">**Quantità:** *1*</span><span class="sxs-lookup"><span data-stu-id="da498-234">**Quantity:** *1*</span></span>

1. <span data-ttu-id="da498-235">Seleziona la nuova riga ordine, quindi sul menu **Scorte** sopra la griglia, seleziona **Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="da498-235">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="da498-236">Nella pagina **Prenotazione**, nel riquadro azioni, seleziona **Prenota lotto** per prenotare l'intera quantità della riga selezionata nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="da498-236">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="da498-237">Chiudi la pagina **Prenotazione** per tornare all'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-237">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="da498-238">Nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="da498-238">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="da498-239">Riceverai un messaggio informativo che mostra la spedizione e l'ondata per questo ordine.</span><span class="sxs-lookup"><span data-stu-id="da498-239">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="da498-240">Prendi nota del numero ID ondata e i numeri ID spedizione.</span><span class="sxs-lookup"><span data-stu-id="da498-240">Make a note of the wave ID number and the shipment ID numbers.</span></span> <span data-ttu-id="da498-241">La spedizione è stata assegnata all'ondata esistente dal primo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-241">The shipment has been assigned to the existing wave from the first sales order.</span></span>

#### <a name="view-the-wave-for-sales-orders-1-and-3"></a><span data-ttu-id="da498-242">Visualizzare l'ondata per gli ordini cliente 1 e 3</span><span class="sxs-lookup"><span data-stu-id="da498-242">View the wave for sales orders 1 and 3</span></span>

1. <span data-ttu-id="da498-243">Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.</span><span class="sxs-lookup"><span data-stu-id="da498-243">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="da498-244">Seleziona l'ID ondata creato dal terzo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-244">Select the wave ID that was created from the third sales order.</span></span>
1. <span data-ttu-id="da498-245">Seleziona il collegamento ID ondata per aprire la pagina Dettagli ondata.</span><span class="sxs-lookup"><span data-stu-id="da498-245">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="da498-246">Nota che la spedizione è stata aggiunta alla Scheda dettaglio **Righe ondata**, insieme alla spedizione per il primo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="da498-246">Notice that the shipment has been added to the **Wave lines** FastTab, together with the shipment for the first sales order.</span></span>