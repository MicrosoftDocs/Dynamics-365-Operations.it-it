---
title: Notifiche di esecuzione ciclo
description: Questo argomento descrive le notifiche di esecuzione ciclo e spiega come configurarle.
author: mirzaab
ms.date: 04/03/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WhsWaveNotificationPolicy, WHSParameters, WHSWaveTemplateTable, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2022-04-01
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 0a61aff10234f40f14d603852be30fec3ba83647
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838084"
---
# <a name="wave-execution-notifications"></a><span data-ttu-id="dee15-103">Notifiche di esecuzione ciclo</span><span class="sxs-lookup"><span data-stu-id="dee15-103">Wave execution notifications</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="dee15-104">La funzionalità *Notifiche di esecuzione ciclo* utilizza eventi aziendali e il Centro azioni per inviare notifiche relative all'esecuzione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="dee15-104">The *Wave execution notifications* feature uses business events and the Action center to deliver notifications that are related to wave execution.</span></span> <span data-ttu-id="dee15-105">Consente di specificare i tipi di eventi che generano notifiche, i magazzini che li generano e gli utenti che li ricevono.</span><span class="sxs-lookup"><span data-stu-id="dee15-105">It lets you specify the types of events that generate notifications, the warehouses that generate them, and the users who receive them.</span></span>

<span data-ttu-id="dee15-106">Il pulsante **Mostra messaggi** (simbolo della campana) sul lato destro della barra di spostamento indica quando un messaggio del centro azioni è disponibile per l'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="dee15-106">The **Show messages** button (bell symbol) on the right side of the navigation bar indicates when an Action center message is available for the current user.</span></span> <span data-ttu-id="dee15-107">L'utente può selezionare il pulsante **Mostra messaggi** per aprire il Centro azioni e rivedere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="dee15-107">The user can select the **Show messages** button to open the Action center and review the messages.</span></span>

<span data-ttu-id="dee15-108">Gli eventi aziendali si verificano quando vengono eseguiti i processi aziendali.</span><span class="sxs-lookup"><span data-stu-id="dee15-108">Business events occur when business processes are run.</span></span> <span data-ttu-id="dee15-109">I processi aziendali sono costituiti da attività.</span><span class="sxs-lookup"><span data-stu-id="dee15-109">Business processes are made up of tasks.</span></span> <span data-ttu-id="dee15-110">Durante un processo aziendale, gli utenti che vi partecipano eseguono azioni aziendali per completare tali attività.</span><span class="sxs-lookup"><span data-stu-id="dee15-110">During a business process, the users who participate in it perform business actions to complete those tasks.</span></span> <span data-ttu-id="dee15-111">Gli eventi aziendali forniscono un meccanismo che consente ai sistemi esterni di ricevere notifiche dalle applicazioni Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dee15-111">Business events provide a mechanism that lets external systems receive notifications from Finance and Operations applications.</span></span> <span data-ttu-id="dee15-112">In questo modo, i sistemi possono eseguire azioni aziendali in risposta agli eventi aziendali.</span><span class="sxs-lookup"><span data-stu-id="dee15-112">In this way, the systems can perform business actions in response to the business events.</span></span> <span data-ttu-id="dee15-113">Per ulteriori informazioni, vedi [Panoramica eventi aziendali](../../fin-ops-core/dev-itpro/business-events/home-page.md).</span><span class="sxs-lookup"><span data-stu-id="dee15-113">For more information, see [Business events overview](../../fin-ops-core/dev-itpro/business-events/home-page.md).</span></span>

## <a name="turn-on-the-wave-execution-notifications-feature"></a><span data-ttu-id="dee15-114">Attivare la funzione di notifiche di esecuzione ciclo</span><span class="sxs-lookup"><span data-stu-id="dee15-114">Turn on the Wave execution notifications feature</span></span>

<span data-ttu-id="dee15-115">Prima di poter utilizzare la funzionalità *Notifiche di esecuzione ciclo*, deve essere attivata nel sistema.</span><span class="sxs-lookup"><span data-stu-id="dee15-115">Before you can use the *Wave execution notifications* feature, it must be turned on in your system.</span></span> <span data-ttu-id="dee15-116">Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario.</span><span class="sxs-lookup"><span data-stu-id="dee15-116">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="dee15-117">Nell'area di lavoro, la funzionalità è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="dee15-117">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="dee15-118">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="dee15-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="dee15-119">**Nome funzionalità:** *Notifiche di esecuzione ciclo*</span><span class="sxs-lookup"><span data-stu-id="dee15-119">**Feature name:** *Wave execution notifications*</span></span>

## <a name="scenario-send-wave-batch-execution-notifications-to-the-action-center"></a><span data-ttu-id="dee15-120">Scenario: inviare notifiche di esecuzione batch ciclo al centro azioni</span><span class="sxs-lookup"><span data-stu-id="dee15-120">Scenario: Send wave batch execution notifications to the Action center</span></span>

<span data-ttu-id="dee15-121">Questo scenario mostra il flusso end-to-end per l'invio di notifiche sugli errori di esecuzione del batch ciclo a un ruolo specifico tramite il centro azioni.</span><span class="sxs-lookup"><span data-stu-id="dee15-121">This scenario shows the end-to-end flow for sending notifications about wave batch execution errors to a specific role via the Action center.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="dee15-122">Rendi disponibili i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="dee15-122">Make demo data available</span></span>

<span data-ttu-id="dee15-123">Per eseguire questo scenario, i dati dimostrativi devono essere installati ed è necessario selezionare la persona giuridica **USMF**.</span><span class="sxs-lookup"><span data-stu-id="dee15-123">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-waves-are-run-in-batch-mode"></a><span data-ttu-id="dee15-124">Assicurarsi che i cicli vengano eseguiti in modalità batch</span><span class="sxs-lookup"><span data-stu-id="dee15-124">Make sure that waves are run in batch mode</span></span>

1. <span data-ttu-id="dee15-125">Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.</span><span class="sxs-lookup"><span data-stu-id="dee15-125">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="dee15-126">Nella Scheda dettaglio **Elaborazione ciclo**, imposta l'opzione **Elabora cicli in batch** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="dee15-126">On the **Wave processing** FastTab, set the **Process waves in batch** option to *Yes*.</span></span>

> [!NOTE]
> <span data-ttu-id="dee15-127">Se desideri disabilitare le notifiche di esecuzione del batch ciclo, imposta l'opzione **Disabilita notifiche batch di elaborazione ciclo** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="dee15-127">If you want to disable wave batch execution notifications, set the **Disable wave processing batch notifications** option to *Yes*.</span></span>

### <a name="configure-a-wave-notification-policy"></a><span data-ttu-id="dee15-128">Configurare un criterio di notifica ciclo</span><span class="sxs-lookup"><span data-stu-id="dee15-128">Configure a wave notification policy</span></span>

<span data-ttu-id="dee15-129">I criteri di notifica ciclo definiscono i tipi di notifiche che vengono inviate e gli utenti a cui viene inviata la notifica.</span><span class="sxs-lookup"><span data-stu-id="dee15-129">Wave notification policies define the types of notifications that are sent and the users who are notified.</span></span>

1. <span data-ttu-id="dee15-130">Vai a **Gestione magazzino \> Impostazione \> Cicli \> Criteri di notifica ciclo**.</span><span class="sxs-lookup"><span data-stu-id="dee15-130">Go to **Warehouse management \> Setup \> Waves \> Wave notification policies**.</span></span>
1. <span data-ttu-id="dee15-131">Crea un record con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="dee15-131">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="dee15-132">**Criterio di notifica ciclo:** *24BatchError*</span><span class="sxs-lookup"><span data-stu-id="dee15-132">**Wave notification policy:** *24BatchError*</span></span>
    - <span data-ttu-id="dee15-133">**Descrizione:** *Errore batch ciclo magazzino 24*</span><span class="sxs-lookup"><span data-stu-id="dee15-133">**Description:** *Warehouse 24 wave batch error*</span></span>
    - <span data-ttu-id="dee15-134">**Invia notifica su:** *Solo errore*</span><span class="sxs-lookup"><span data-stu-id="dee15-134">**Send notification on:** *Error only*</span></span>
    - <span data-ttu-id="dee15-135">**A ruolo:** *Amministratore di sistema*</span><span class="sxs-lookup"><span data-stu-id="dee15-135">**To role:** *System administrator*</span></span>

        > [!NOTE]
        > <span data-ttu-id="dee15-136">Poiché questo scenario utilizza dati demo, il ruolo *Amministratore di sistema* è selezionato per motivi di semplicità.</span><span class="sxs-lookup"><span data-stu-id="dee15-136">Because this scenario uses demo data, the *System administrator* role is selected for the sake of simplicity.</span></span> <span data-ttu-id="dee15-137">Pertanto, poiché hai effettuato l'accesso come utente amministratore di sistema, riceverai le notifiche.</span><span class="sxs-lookup"><span data-stu-id="dee15-137">Therefore, because you're signed in as a system administrator user, you will receive the notifications.</span></span> <span data-ttu-id="dee15-138">Tuttavia, in pratica, dovresti solitamente selezionare un ruolo più specifico per notificare gli errori di esecuzione del batch ciclo, come *Responsabile del magazzino*.</span><span class="sxs-lookup"><span data-stu-id="dee15-138">However, in practice, you should usually select a more specific role to notify about wave batch execution errors, such as *Warehouse manager*.</span></span>

1. <span data-ttu-id="dee15-139">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dee15-139">On the Action Pane, select **Save**.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="dee15-140">Configurare un modello di ondata</span><span class="sxs-lookup"><span data-stu-id="dee15-140">Configure a wave template</span></span>

<span data-ttu-id="dee15-141">I modelli di ciclo consentono di collegare istanze specifiche dei metodi di ciclo ai modelli di etichetta ciclo corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="dee15-141">Wave templates let you link specific instances of wave methods to corresponding wave label templates.</span></span>

1. <span data-ttu-id="dee15-142">Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.</span><span class="sxs-lookup"><span data-stu-id="dee15-142">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="dee15-143">Nel riquadro elenco, imposta il campo **Tipo di modello ciclo** su *Spedizione*, quindi seleziona il modello ciclo *Spedizione predefinita 24* per il magazzino 24.</span><span class="sxs-lookup"><span data-stu-id="dee15-143">In the list pane, set the **Wave template type** field to *Shipping*, and then select the *24 Shipping Default* wave template for warehouse 24.</span></span>
1. <span data-ttu-id="dee15-144">Nella Scheda dettaglio **Generale**, imposta il campo **Criterio di notifica ciclo** su *24BatchError*.</span><span class="sxs-lookup"><span data-stu-id="dee15-144">On the **General** FastTab, set the **Wave notification policy** field to *24BatchError*.</span></span>

### <a name="configure-a-work-template"></a><span data-ttu-id="dee15-145">Configurare un modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="dee15-145">Configure a work template</span></span>

<span data-ttu-id="dee15-146">I modelli di lavoro vengono utilizzati durante l'esecuzione del ciclo per generare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="dee15-146">Work templates are used during wave execution to generate work.</span></span> <span data-ttu-id="dee15-147">Per questo scenario, l'esecuzione del ciclo dovrebbe attivare un errore.</span><span class="sxs-lookup"><span data-stu-id="dee15-147">For this scenario, wave execution should trigger an error.</span></span> <span data-ttu-id="dee15-148">Impostando la query del modello di lavoro per utilizzare un magazzino inesistente, ti assicureri che l'esecuzione del ciclo non riesca e quindi invii una notifica.</span><span class="sxs-lookup"><span data-stu-id="dee15-148">By setting the work template query to use a nonexistent warehouse, you will ensure that wave execution fails and therefore sends a notification.</span></span>

1. <span data-ttu-id="dee15-149">Accedi a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="dee15-149">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="dee15-150">Nel riquadro elenco, imposta il campo **Tipo di modello lavoro** su *Ordini cliente*, quindi seleziona il modello di lavoro *Fase ordine cliente 24* per il magazzino 24.</span><span class="sxs-lookup"><span data-stu-id="dee15-150">In the list pane, set the **Work template type** field to *Sales orders* and then select the *24 SO Stage* work template for warehouse 24.</span></span>
1. <span data-ttu-id="dee15-151">Nel riquadro azioni, seleziona **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="dee15-151">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="dee15-152">Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo** modifica la seguente riga (o aggiungila se non esiste):</span><span class="sxs-lookup"><span data-stu-id="dee15-152">In the query editor dialog box, on the **Range** tab, edit the following row (or add it if it doesn't exist):</span></span>

    - <span data-ttu-id="dee15-153">**Tabella:** *Transazioni lavoro temporanee*</span><span class="sxs-lookup"><span data-stu-id="dee15-153">**Table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="dee15-154">**Tabella derivata:** *Transazioni lavoro temporanee*</span><span class="sxs-lookup"><span data-stu-id="dee15-154">**Derived table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="dee15-155">**Campo:** *Magazzino*</span><span class="sxs-lookup"><span data-stu-id="dee15-155">**Field:** *Warehouse*</span></span>
    - <span data-ttu-id="dee15-156">**Criteri:** Modifica il valore da *24* in *Errore*.</span><span class="sxs-lookup"><span data-stu-id="dee15-156">**Criteria:** Change the value from *24* to *Error*.</span></span>

1. <span data-ttu-id="dee15-157">Seleziona **OK** e conferma la modifica.</span><span class="sxs-lookup"><span data-stu-id="dee15-157">Select **OK**, and confirm the change.</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="dee15-158">Creare un ordine cliente e rilasciarlo nel magazzino</span><span class="sxs-lookup"><span data-stu-id="dee15-158">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="dee15-159">Andare a **Vendite e marketing \> Ordine cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="dee15-159">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="dee15-160">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="dee15-160">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="dee15-161">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="dee15-161">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="dee15-162">**Magazzino:** *24*</span><span class="sxs-lookup"><span data-stu-id="dee15-162">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="dee15-163">Nella Scheda dettaglio **Righe ordine cliente**, aggiungi una riga ordine cliente che abbia le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="dee15-163">On the **Sales order lines** FastTab, add a sales order line that has the following settings:</span></span>

    - <span data-ttu-id="dee15-164">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="dee15-164">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="dee15-165">**Quantità:** *10*</span><span class="sxs-lookup"><span data-stu-id="dee15-165">**Quantity:** *10*</span></span>

    > [!NOTE]
    > <span data-ttu-id="dee15-166">Questi articoli e quantità sono solo esempi.</span><span class="sxs-lookup"><span data-stu-id="dee15-166">These items and quantities are only examples.</span></span> <span data-ttu-id="dee15-167">Il magazzino specificato deve contenere scorte sufficienti.</span><span class="sxs-lookup"><span data-stu-id="dee15-167">The specified warehouse must contain enough stock.</span></span>

1. <span data-ttu-id="dee15-168">Mentre la nuova riga ordine è ancora selezionata nella Scheda dettaglio **Righe ordine cliente**, seleziona **Inventario \> Prenotazione** nella barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="dee15-168">While the new line is still selected on the **Sales order lines** FastTab, select **Inventory \> Reservation** on the toolbar.</span></span>
1. <span data-ttu-id="dee15-169">Nella pagina **Prenotazione**, nel riquadro azioni, seleziona **Prenota lotto**.</span><span class="sxs-lookup"><span data-stu-id="dee15-169">On the **Reservation** page, on the Action Pane, select **Reserve lot**.</span></span> <span data-ttu-id="dee15-170">Quindi, chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="dee15-170">Then close the page.</span></span>
1. <span data-ttu-id="dee15-171">Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="dee15-171">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

### <a name="notifications-from-wave-batch-job-execution"></a><span data-ttu-id="dee15-172">Notifiche dell'esecuzione di lavori batch ciclo</span><span class="sxs-lookup"><span data-stu-id="dee15-172">Notifications from wave batch job execution</span></span>

<span data-ttu-id="dee15-173">A seconda della configurazione dei tuoi eventi aziendali, alla fine riceverai una notifica sull'errore di esecuzione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="dee15-173">Depending on the setup of your business events, you will eventually receive a notification about wave execution failure.</span></span> <span data-ttu-id="dee15-174">Il messaggio del centro azioni sarà simile al seguente esempio e includerà un collegamento al ciclo che ha avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="dee15-174">The Action center message will resemble the following example and will include a link to the wave that failed.</span></span>

> <span data-ttu-id="dee15-175">**Errore durante l'esecuzione del ciclo**</span><span class="sxs-lookup"><span data-stu-id="dee15-175">**Error during wave execution**</span></span>  
> <span data-ttu-id="dee15-176">Si è verificato un errore durante l'esecuzione del ciclo USMF-000000001.</span><span class="sxs-lookup"><span data-stu-id="dee15-176">An error occurred while executing wave USMF-000000001.</span></span>  
> <span data-ttu-id="dee15-177">Ultimi messaggi: Nessun lavoro è stato creato per il ciclo USMF-000000001.</span><span class="sxs-lookup"><span data-stu-id="dee15-177">Last messages: No Work was created for Wave USMF-000000001.</span></span>
>
> <span data-ttu-id="dee15-178">**STATO**</span><span class="sxs-lookup"><span data-stu-id="dee15-178">**STATUS**</span></span>  
> <span data-ttu-id="dee15-179">Attive</span><span class="sxs-lookup"><span data-stu-id="dee15-179">Active</span></span>
>
> <span data-ttu-id="dee15-180">Apri dettagli ciclo</span><span class="sxs-lookup"><span data-stu-id="dee15-180">Open wave details</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
