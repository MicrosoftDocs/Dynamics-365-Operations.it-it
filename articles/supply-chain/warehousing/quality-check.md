---
title: Controllo qualità
description: In questo argomento vengono fornite informazioni sulla funzionalità di controllo di qualità. Questa funzionalità consente ai magazzinieri di effettuare rapidi controlli a campione sulla qualità mentre ricevono articoli nell'area della banchina di entrata.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSQualityCheckTemplate, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSQualityCheckResult
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 585ca933726cb932290f8abf8504aeb13848a0e5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996253"
---
# <a name="quality-check"></a><span data-ttu-id="7632a-104">Controllo qualità</span><span class="sxs-lookup"><span data-stu-id="7632a-104">Quality check</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7632a-105">La funzionalità *Controllo qualità* consente ai magazzinieri di effettuare rapidi controlli a campione sulla qualità mentre ricevono articoli nell'area della banchina di entrata.</span><span class="sxs-lookup"><span data-stu-id="7632a-105">The *Quality check* feature lets warehouse workers do quick spot checks for quality while they receive items to the inbound dock area.</span></span> <span data-ttu-id="7632a-106">Questi controlli a campione sono utili quando gli operatori ispezionano l'imballaggio o altre parti facilmente riconoscibili di un articolo.</span><span class="sxs-lookup"><span data-stu-id="7632a-106">These spot checks are beneficial when workers inspect packaging or other easily recognizable parts of an item.</span></span> <span data-ttu-id="7632a-107">La funzionalità guida gli operatori durante un il rapido esame per vedere se qualcosa è chiaramente difettoso o danneggiato prima di immagazzinare le scorte nell'ubicazione di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="7632a-107">The feature guides workers to take a quick look to see whether anything is obviously faulty or damaged before they stock the inventory in its putaway location.</span></span>

<span data-ttu-id="7632a-108">Questa funzionalità è un'alternativa al processo di controllo di qualità standard.</span><span class="sxs-lookup"><span data-stu-id="7632a-108">This feature is an alternative to the standard quality check process.</span></span> <span data-ttu-id="7632a-109">Offre maggiore flessibilità e elaborazione più rapida.</span><span class="sxs-lookup"><span data-stu-id="7632a-109">It offers more flexibility and faster processing.</span></span>

<span data-ttu-id="7632a-110">Quando si utilizza questa funzione, l'arrivo e il controllo di qualità si svolgono nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="7632a-110">When you use this feature, the arrival and quality check occur in the following way:</span></span>

1. <span data-ttu-id="7632a-111">Quando arriva una spedizione, un addetto al magazzino registra l'arrivo.</span><span class="sxs-lookup"><span data-stu-id="7632a-111">When a shipment arrives, a warehouse worker registers the arrival.</span></span> <span data-ttu-id="7632a-112">Lo stesso addetto esegue inoltre la scansione di una targa per registrare l'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="7632a-112">The worker also scans a license plate to register the location.</span></span>
1. <span data-ttu-id="7632a-113">L'operatore effettua un rapido controllo di qualità e registra il risultato (positivo o negativo) per quella targa.</span><span class="sxs-lookup"><span data-stu-id="7632a-113">The worker does a quick quality check and records the result (pass or fail) for that license plate.</span></span>
1. <span data-ttu-id="7632a-114">Si verifica una delle seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="7632a-114">One of the following actions occurs:</span></span>

    - <span data-ttu-id="7632a-115">Se il controllo di qualità viene superato, la targa viene accettata e indirizzata normalmente verso un'ubicazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="7632a-115">If the quality check is passed, the license plate is accepted and guided to a receiving location, as usual.</span></span>
    - <span data-ttu-id="7632a-116">Se il controllo di qualità non viene superato, la targa viene rifiutata e il lavoro di stoccaggio esistente per la stessa viene reindirizzato verso un'ubicazione alternativa per un'ulteriore ispezione.</span><span class="sxs-lookup"><span data-stu-id="7632a-116">If the quality check is failed, the license plate is rejected, and existing putaway work for it is redirected to an alternate location for further inspection.</span></span> <span data-ttu-id="7632a-117">Viene creato un nuovo ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="7632a-117">A new quality order is created.</span></span> <span data-ttu-id="7632a-118">Per visualizzare l'ordine di controllo qualità creato dal controllo di qualità non superato, andare a **Gestione inventario \> Attività periodiche \> Gestione della qualità \> Ordini di controllo qualità**.</span><span class="sxs-lookup"><span data-stu-id="7632a-118">To view the quality order that is created from the failed quality check, go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>

<span data-ttu-id="7632a-119">Questo processo può anche essere configurato in modo tale che tutte le targhe acquisite vengano immediatamente trasferite nell'ubicazione di controllo della qualità.</span><span class="sxs-lookup"><span data-stu-id="7632a-119">This process can also be set up so that all scanned license plates are immediately diverted to the quality check location.</span></span>

## <a name="turn-on-the-quality-check-feature"></a><span data-ttu-id="7632a-120">Attivare la funzionalità Controllo qualità</span><span class="sxs-lookup"><span data-stu-id="7632a-120">Turn on the Quality check feature</span></span>

<span data-ttu-id="7632a-121">Prima di poter utilizzare la funzionalità *Controllo qualità*, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="7632a-121">Before you can use the *Quality check* feature, it must be turned on in your system.</span></span> <span data-ttu-id="7632a-122">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla.</span><span class="sxs-lookup"><span data-stu-id="7632a-122">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="7632a-123">Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="7632a-123">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="7632a-124">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="7632a-124">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="7632a-125">**Nome funzionalità:** *Controllo qualità*</span><span class="sxs-lookup"><span data-stu-id="7632a-125">**Feature name:** *Quality check*</span></span>

## <a name="set-up-the-feature-for-the-example-scenario"></a><span data-ttu-id="7632a-126">Configurare la funzionalità per lo scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="7632a-126">Set up the feature for the example scenario</span></span>

<span data-ttu-id="7632a-127">Questa sezione fornisce linee guida e un esempio che mostra come configurare la funzionalità *Controllo qualità* e preparare i dati di esempio per lo scenario di esempio illustrato più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7632a-127">This section provides guidelines and an example that shows how to set up the *Quality check* feature and prepare sample data for the example scenario that is provided later in this topic.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="7632a-128">Rendi disponibili i dati di esempio</span><span class="sxs-lookup"><span data-stu-id="7632a-128">Make sample data available</span></span>

<span data-ttu-id="7632a-129">Per elaborare lo [scenario di esempio](#example-scenario) utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard.</span><span class="sxs-lookup"><span data-stu-id="7632a-129">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="7632a-130">È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="7632a-130">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="quality-check-template"></a><a name="quality-template"></a><span data-ttu-id="7632a-131">Modello di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="7632a-131">Quality check template</span></span>

<span data-ttu-id="7632a-132">Il modello di controllo della qualità definisce le regole per eseguire controlli a campion rapidi per la qualità al momento della ricezione.</span><span class="sxs-lookup"><span data-stu-id="7632a-132">The quality check template defines the rules for doing quick spot checks for quality at the time of receiving.</span></span>

1. <span data-ttu-id="7632a-133">Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modello di controllo di qualità**.</span><span class="sxs-lookup"><span data-stu-id="7632a-133">Go to **Warehouse management \> Setup \> Work \> Quality check template**.</span></span>
1. <span data-ttu-id="7632a-134">Seleziona **Nuovo** per aggiungere un modello alla griglia.</span><span class="sxs-lookup"><span data-stu-id="7632a-134">Select **New** to add a template to the grid.</span></span>
1. <span data-ttu-id="7632a-135">Definire il nuovo modello impostando i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="7632a-135">Set the following values to define the new template:</span></span>

    - <span data-ttu-id="7632a-136">**Nome modello di controllo qualità:** *Controllo banchina*</span><span class="sxs-lookup"><span data-stu-id="7632a-136">**Quality check template name:** *Dock check*</span></span>

        <span data-ttu-id="7632a-137">Immettere un nome che identifichi i criteri applicati per questo modello.</span><span class="sxs-lookup"><span data-stu-id="7632a-137">Enter a name that identifies the policies applied for this template.</span></span>

    - <span data-ttu-id="7632a-138">**Criteri di accettazione:** *Richiedi conferma all'utente*</span><span class="sxs-lookup"><span data-stu-id="7632a-138">**Acceptance policy:** *Prompt user*</span></span>

        <span data-ttu-id="7632a-139">Specificare se agli utenti deve essere richiesto di accettare o rifiutare la qualità dell'inventario mentre elaborano il lavoro o se la qualità deve essere automaticamente rifiutata.</span><span class="sxs-lookup"><span data-stu-id="7632a-139">Specify whether users should be prompted to accept or reject the quality of the inventory while they process the work, or whether the quality should automatically be rejected.</span></span> <span data-ttu-id="7632a-140">Le opzioni disponibili sono *Rifiuto automatico* e *Richiedi conferma all'utente*.</span><span class="sxs-lookup"><span data-stu-id="7632a-140">The available options are *Auto reject* and *Prompt user*.</span></span>

    - <span data-ttu-id="7632a-141">**Criteri di elaborazione controllo qualità:** *Crea ordine di controllo qualità*</span><span class="sxs-lookup"><span data-stu-id="7632a-141">**Quality processing policy:** *Create quality order*</span></span>

        <span data-ttu-id="7632a-142">Selezionare i criteri da utilizzare quando la qualità dell'inventario viene rifiutata.</span><span class="sxs-lookup"><span data-stu-id="7632a-142">Select the policy that should be used when the quality of the inventory is rejected.</span></span> <span data-ttu-id="7632a-143">Di seguito vengono illustrate le opzioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="7632a-143">The following options are available:</span></span>

        - <span data-ttu-id="7632a-144">*Crea solo lavoro*: creare il lavoro solo per facilitare la movimentazione delle scorte.</span><span class="sxs-lookup"><span data-stu-id="7632a-144">*Create work only* – Just create work to facilitate inventory movement.</span></span>
        - <span data-ttu-id="7632a-145">*Crea ordine di controllo qualità*: creare un ordine di controllo qualità per facilitare i test di qualità.</span><span class="sxs-lookup"><span data-stu-id="7632a-145">*Create quality order* – Create a quality order to facilitate quality tests.</span></span>

    - <span data-ttu-id="7632a-146">**Gruppo di test:** *Sistemi di chiusura*</span><span class="sxs-lookup"><span data-stu-id="7632a-146">**Test group:** *Enclosure*</span></span>

        <span data-ttu-id="7632a-147">Specificare il gruppo di test che deve essere utilizzato nell'ordine di controllo qualità creato.</span><span class="sxs-lookup"><span data-stu-id="7632a-147">Specify the test group that should be used in the quality order that is created.</span></span> <span data-ttu-id="7632a-148">I gruppi di test vengono configurati nel modulo **Gestione inventario**.</span><span class="sxs-lookup"><span data-stu-id="7632a-148">Test groups are set up in the **Inventory management** module.</span></span>

        <span data-ttu-id="7632a-149">Lasciare l'opzione **Test distruttivo** disattivata per il gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="7632a-149">Leave the **Destructive text** option turned off for the test group.</span></span> <span data-ttu-id="7632a-150">Questa opzione definisce se il campione verrà distrutto come parte dei test del gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="7632a-150">This option defines whether the sample will be destroyed as part of the tests in the test group.</span></span> <span data-ttu-id="7632a-151">Se viene utilizzato un test distruttivo, il sistema genera una transazione di magazzino quando un ordine di controllo qualità viene creato per un articolo.</span><span class="sxs-lookup"><span data-stu-id="7632a-151">If a destructive test is used, the system generates an inventory transaction when a quality order is created for an item.</span></span> <span data-ttu-id="7632a-152">La nuova operazione di magazzino stima la riduzione delle scorte per la quantità da testare.</span><span class="sxs-lookup"><span data-stu-id="7632a-152">The new inventory transaction predicts the inventory reduction for the test quantity.</span></span> <span data-ttu-id="7632a-153">La riduzione delle scorte si verifica quanto l'ordine di controllo qualità viene completato attraverso la fase di convalida.</span><span class="sxs-lookup"><span data-stu-id="7632a-153">The inventory reduction occurs when the quality order is completed through the validation step.</span></span> <span data-ttu-id="7632a-154">L'operazione di magazzino viene identificata come un ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="7632a-154">The inventory transaction is identified as a quality order.</span></span>

### <a name="work-class--quality-check"></a><a name="work-class"></a><span data-ttu-id="7632a-155">Classe di lavoro: controllo di qualità</span><span class="sxs-lookup"><span data-stu-id="7632a-155">Work class – Quality check</span></span>

<span data-ttu-id="7632a-156">Le classi di lavoro vengono utilizzate per indirizzare e/o limitare il tipo di righe ordine di lavoro che gli addetti al magazzino possono elaborare in un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="7632a-156">Work classes are used to direct and/or limit the type of work order lines that warehouse workers can process on a mobile device.</span></span>

1. <span data-ttu-id="7632a-157">Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Classi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="7632a-157">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="7632a-158">Selezionare **Nuovo** per creare una classe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7632a-158">Select **New** to create a work class.</span></span>
1. <span data-ttu-id="7632a-159">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="7632a-159">In the header, set the following values:</span></span>

    - <span data-ttu-id="7632a-160">**ID classe lavoro:** *Controllo di qualità*</span><span class="sxs-lookup"><span data-stu-id="7632a-160">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="7632a-161">Immettere un nome che identifichi la classe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7632a-161">Enter a name that identifies the work class.</span></span>

    - <span data-ttu-id="7632a-162">**Descrizione:** *Controllo di qualità*</span><span class="sxs-lookup"><span data-stu-id="7632a-162">**Description:** *QC Check*</span></span>

        <span data-ttu-id="7632a-163">Immettere una breve descrizione che indichi a cosa serve la classe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7632a-163">Enter a short description that indicates what the work class is used for.</span></span>

    - <span data-ttu-id="7632a-164">**Tipo di ordine di lavoro:** *Qualità nel controllo qualità*</span><span class="sxs-lookup"><span data-stu-id="7632a-164">**Work order type:** *Quality in quality check*</span></span>

        <span data-ttu-id="7632a-165">Selezionare il tipo di ordine di lavoro creato dalla classe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7632a-165">Select the type of work order that is created by the work class.</span></span> <span data-ttu-id="7632a-166">Quando si imposta il lavoro di controllo qualità, selezionare sempre *Qualità nel controllo qualità*.</span><span class="sxs-lookup"><span data-stu-id="7632a-166">When you set up quality control work, always select *Quality in quality check*.</span></span>

1. <span data-ttu-id="7632a-167">Nella Scheda dettaglio **Tipi di ubicazione inseriti validi**, lasciare vuoto il campo **Tipo di ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="7632a-167">On the **Valid put location types** FastTab, leave the **Location type** field blank.</span></span>

    <span data-ttu-id="7632a-168">Se si seleziona un tipo di ubicazione, si limitano le ubicazioni in cui gli articoli possono essere stoccati dopo che sono stati prelevati.</span><span class="sxs-lookup"><span data-stu-id="7632a-168">If you select a location type, you limit the locations where items can be put after they are picked.</span></span> <span data-ttu-id="7632a-169">Questo campo viene utilizzato quando una direttiva ubicazione prova a risolvere l'ubicazione o quando un addetto al magazzino specifica manualmente l'ubicazione per la voce di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="7632a-169">This field is used when a location directive tries to resolve the location, or when a warehouse worker manually specifies the location for the mobile device menu item.</span></span>

<span data-ttu-id="7632a-170">Per altre informazioni sulle classi di lavoro e su come crearle, vedere [Creare una classe di lavoro](tasks/create-work-class.md).</span><span class="sxs-lookup"><span data-stu-id="7632a-170">For more information about work classes and how to create them, see [Create a work class](tasks/create-work-class.md).</span></span>

### <a name="work-template"></a><span data-ttu-id="7632a-171">Modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="7632a-171">Work template</span></span>

<span data-ttu-id="7632a-172">Modelli di lavoro consente di definire le operazioni di lavoro che devono essere eseguite nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="7632a-172">Work templates let you define the work operations that must be performed in the warehouse.</span></span> <span data-ttu-id="7632a-173">In genere, le operazioni di lavoro sono costituite da una coppia di azioni: un lavoratore di magazzino preleva le scorte disponibili da un'ubicazione quindi colloca le scorte prelevate in un'altra ubicazione.</span><span class="sxs-lookup"><span data-stu-id="7632a-173">Typically, warehouse work operations consist of a pair of actions: a warehouse worker picks on-hand inventory up in one location and then puts the picked inventory down in another location.</span></span> <span data-ttu-id="7632a-174">Un modello di lavoro per il controllo di qualità definisce le operazioni di lavoro per l'esecuzione dei controlli di qualità.</span><span class="sxs-lookup"><span data-stu-id="7632a-174">A work template for quality control defines the work operations for doing quality checks.</span></span>

#### <a name="purchase-orders"></a><span data-ttu-id="7632a-175">Ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="7632a-175">Purchase orders</span></span>

1. <span data-ttu-id="7632a-176">Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="7632a-176">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="7632a-177">Nell'intestazione, Impostare il campo **Tipo ordine di lavoro** su *Ordini fornitore*.</span><span class="sxs-lookup"><span data-stu-id="7632a-177">In the header, set the **Work order type** field to *Purchase orders*.</span></span>
1. <span data-ttu-id="7632a-178">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="7632a-178">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="7632a-179">Selezionare un modello di lavoro che dovrebbe includere una fase di controllo della qualità.</span><span class="sxs-lookup"><span data-stu-id="7632a-179">Select a work template that should include a quality check step.</span></span> <span data-ttu-id="7632a-180">Nella sezione **Panoramica**, nel campo **Modello di lavoro**, selezionare *Ricevuta ordine d'acquisto 51*.</span><span class="sxs-lookup"><span data-stu-id="7632a-180">In the **Overview** section, in the **Work template** field, select *51 PO Receipt*.</span></span>
1. <span data-ttu-id="7632a-181">Nella sezione **Dettagli del modello di lavoro**, notare che la griglia ha due righe esistenti: una per *Preleva* e una per *Inserisci*.</span><span class="sxs-lookup"><span data-stu-id="7632a-181">In the **Work template details** section, notice that the grid has two existing lines: one for *Pick* and one for *Put*.</span></span>
1. <span data-ttu-id="7632a-182">Nella sezione **Dettagli del modello di lavoro**, selezionare **Nuovo** per aggiungere una riga per il controllo di qualità alla griglia.</span><span class="sxs-lookup"><span data-stu-id="7632a-182">In the **Work template details** section, select **New** to add a row for quality control to the grid.</span></span> <span data-ttu-id="7632a-183">Si noti che il campo **Numero di riga** per la nuova riga è impostato su *3*.</span><span class="sxs-lookup"><span data-stu-id="7632a-183">Notice that the **Line number** field for the new line is set to *3*.</span></span>
1. <span data-ttu-id="7632a-184">Nella nuova riga, imposta i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="7632a-184">On the new line, set the following values.</span></span> <span data-ttu-id="7632a-185">Accettare i valori predefiniti per i campi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="7632a-185">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="7632a-186">**Tipo di lavoro:** *Controllo qualità*</span><span class="sxs-lookup"><span data-stu-id="7632a-186">**Work type:** *Quality check*</span></span>
    - <span data-ttu-id="7632a-187">**ID classe lavoro:** *Acquisto*</span><span class="sxs-lookup"><span data-stu-id="7632a-187">**Work class ID:** *Purchase*</span></span>
    - <span data-ttu-id="7632a-188">**Nome modello di controllo qualità:** *Controllo banchina*</span><span class="sxs-lookup"><span data-stu-id="7632a-188">**Quality check template name:** *Dock check*</span></span>

        <span data-ttu-id="7632a-189">Selezionare l'ID univoco per la classe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7632a-189">Select the unique ID for the work class.</span></span> <span data-ttu-id="7632a-190">Utilizzare questo valore per configurare le voci di menu nel dispositivo mobile e i tipi di lavoro che le voci di menu possono elaborare.</span><span class="sxs-lookup"><span data-stu-id="7632a-190">You use this value to configure the menu items on the mobile device and the types of work that those menu items can process.</span></span>

1. <span data-ttu-id="7632a-191">Nel riquadro azioni selezionare **Salva** per salvare il lavoro eseguito finora.</span><span class="sxs-lookup"><span data-stu-id="7632a-191">On the Action Pane, select **Save** to save your work so far.</span></span>

    <span data-ttu-id="7632a-192">Si riceverà un messaggio informativo che indica "Non valido: Il controllo di qualità deve essere eseguito direttamente dopo un prelievo".</span><span class="sxs-lookup"><span data-stu-id="7632a-192">You receive an informational message that states, "Invalid - Quality check must come directly after a pick."</span></span> <span data-ttu-id="7632a-193">Pertanto, è necessario modificare il valore **Numero di riga** per la riga appena aggiunta.</span><span class="sxs-lookup"><span data-stu-id="7632a-193">Therefore, you must change the **Line number** value for the line that you just added.</span></span>

1. <span data-ttu-id="7632a-194">Seguire questi passaggi per modificare il valore di **Numero di riga** per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="7632a-194">Follow these steps to change the **Line number** value for the new line:</span></span>

    1. <span data-ttu-id="7632a-195">Nella sezione **Dettagli del modello di lavoro**, selezionare la riga in cui il campo **Tipo di lavoro** è impostato su *Controllo qualità*.</span><span class="sxs-lookup"><span data-stu-id="7632a-195">In the **Work template details** section, select the line where the **Work type** field is set to *Quality check*.</span></span>
    2. <span data-ttu-id="7632a-196">Selezionare il pulsante **Sposta su** o **Sposta giù** per spostare la riga *Controllo qualità* in modo che sia dopo la riga *Preleva*.</span><span class="sxs-lookup"><span data-stu-id="7632a-196">Select the **Move up** or **Move down** button to move the *Quality check* line so that it's after the *Pick* line.</span></span>

1. <span data-ttu-id="7632a-197">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7632a-197">On the Action Pane, select **Save**.</span></span>

#### <a name="quality-in-quality-check"></a><span data-ttu-id="7632a-198">Qualità nel controllo qualità</span><span class="sxs-lookup"><span data-stu-id="7632a-198">Quality in quality check</span></span>

<span data-ttu-id="7632a-199">Quindi, creare un modello di lavoro per il controllo di qualità.</span><span class="sxs-lookup"><span data-stu-id="7632a-199">Next, create a work template for the quality check.</span></span>

1. <span data-ttu-id="7632a-200">Nell'intestazione della pagina **Modelli di lavoro**, modifica il valore del campo **Tipo di ordine di lavoro** su *Qualità nel controllo qualità*.</span><span class="sxs-lookup"><span data-stu-id="7632a-200">In the header of the **Work templates** page, change the value of the **Work order type** field to *Quality in quality check*.</span></span>
1. <span data-ttu-id="7632a-201">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia nella sezione **Panoramica**.</span><span class="sxs-lookup"><span data-stu-id="7632a-201">On the Action Pane, select **New** to add a row to the grid in the **Overview** section.</span></span>
1. <span data-ttu-id="7632a-202">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="7632a-202">In the new row, set the following values:</span></span>

    - <span data-ttu-id="7632a-203">**Modello di lavoro:** *Controllo qualità 51*</span><span class="sxs-lookup"><span data-stu-id="7632a-203">**Work template:** *51 Quality Check*</span></span>

        <span data-ttu-id="7632a-204">Immettere un nome per il modello.</span><span class="sxs-lookup"><span data-stu-id="7632a-204">Enter a name for the template.</span></span>

    - <span data-ttu-id="7632a-205">**Descrizione modello di lavoro:** *Controllo qualità 51*</span><span class="sxs-lookup"><span data-stu-id="7632a-205">**Work template description:** *51 Quality Check*</span></span>

1. <span data-ttu-id="7632a-206">Nel riquadro azioni, selezionare **Salva** per rendere disponibile la sezione **Dettagli modello di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="7632a-206">On the Action Pane, select **Save** to make the **Work template details** section available.</span></span>
1. <span data-ttu-id="7632a-207">Mentre il nuovo modello è ancora selezionato nella sezione **Panoramica**, selezionare **Nuovo** nella sezione **Dettagli del modello di lavoro** per aggiungere una riga alla griglia in quel punto.</span><span class="sxs-lookup"><span data-stu-id="7632a-207">While the new template is still selected in the **Overview** section, select **New** in the **Work template details** section to add a row to the grid there.</span></span>
1. <span data-ttu-id="7632a-208">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="7632a-208">In the new row, set the following values:</span></span>

    - <span data-ttu-id="7632a-209">**Tipo di lavoro:** *Prelevare*</span><span class="sxs-lookup"><span data-stu-id="7632a-209">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="7632a-210">**ID classe lavoro:** *Controllo di qualità*</span><span class="sxs-lookup"><span data-stu-id="7632a-210">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="7632a-211">Selezionare il nome della [classe di lavoro](#work-class) creata in precedenza per il lavoro di controllo della qualità.</span><span class="sxs-lookup"><span data-stu-id="7632a-211">Select the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

1. <span data-ttu-id="7632a-212">Nella sezione **Dettagli del modello di lavoro**, selezionare ancora **Nuovo** per aggiungere un'altra riga.</span><span class="sxs-lookup"><span data-stu-id="7632a-212">In the **Work template details** section, select **New** again to add another row.</span></span>
1. <span data-ttu-id="7632a-213">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="7632a-213">In the new row, set the following values:</span></span>

    - <span data-ttu-id="7632a-214">**Tipo di lavoro:** *Inserire*</span><span class="sxs-lookup"><span data-stu-id="7632a-214">**Work type:** *Put*</span></span>
    - <span data-ttu-id="7632a-215">**ID classe lavoro:** *Controllo di qualità*</span><span class="sxs-lookup"><span data-stu-id="7632a-215">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="7632a-216">Selezionare il nome della [classe di lavoro](#work-class) creata in precedenza per il lavoro di controllo della qualità.</span><span class="sxs-lookup"><span data-stu-id="7632a-216">Select the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

1. <span data-ttu-id="7632a-217">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7632a-217">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="7632a-218">Per ulteriori informazioni sui modelli di lavoro, vedere [Controllo del lavoro di magazzino con modelli di lavoro e direttive di ubicazione](control-warehouse-location-directives.md).</span><span class="sxs-lookup"><span data-stu-id="7632a-218">For more information about work templates, see [Control warehouse work by using work templates and location directives](control-warehouse-location-directives.md)</span></span>

### <a name="location-directive--quality-failures"></a><span data-ttu-id="7632a-219">Direttiva ubicazione: errori di qualità</span><span class="sxs-lookup"><span data-stu-id="7632a-219">Location directive – Quality failures</span></span>

<span data-ttu-id="7632a-220">Le direttive ubicazione sono regole che aiutano a identificare le ubicazioni di prelievo e stoccaggio per il movimento scorte.</span><span class="sxs-lookup"><span data-stu-id="7632a-220">Location directives are rules that help identify pick and put locations for inventory movement.</span></span> <span data-ttu-id="7632a-221">Ad esempio, in una transazione dell'ordine cliente, la direttiva ubicazione determina il punto di prelievo e il punto di stoccaggio degli articoli.</span><span class="sxs-lookup"><span data-stu-id="7632a-221">For example, in a sales order transaction, a location directive determines where the items will be picked and where the picked items will be put.</span></span> <span data-ttu-id="7632a-222">È necessario configurare una regola della direttiva ubicazione per definire come verranno gestiti i controlli di qualità non superati.</span><span class="sxs-lookup"><span data-stu-id="7632a-222">You must configure a location directive rule to define how failed quality checks will be handled.</span></span>

1. <span data-ttu-id="7632a-223">Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="7632a-223">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="7632a-224">Nel riquadro sinistro, impostare il campo **Tipo di ordine di lavoro** su *Ordini di acquisto* per lavorare con le direttive ubicazioni di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="7632a-224">In the left pane, set the **Work order type** field to *Purchase orders* to work with location directives of that type.</span></span>
1. <span data-ttu-id="7632a-225">Nel riquadro azioni selezionare **Nuovo** per creare una direttiva ubicazione per i controlli di qualità.</span><span class="sxs-lookup"><span data-stu-id="7632a-225">On the Action Pane, select **New** to create a location directive for quality checks.</span></span>
1. <span data-ttu-id="7632a-226">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="7632a-226">In the header, set the following values:</span></span>

    - <span data-ttu-id="7632a-227">**Numero sequenza:** accetta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="7632a-227">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="7632a-228">**Nome:** *51 a qualità*</span><span class="sxs-lookup"><span data-stu-id="7632a-228">**Name:** *51 To Quality*</span></span>

1. <span data-ttu-id="7632a-229">Nella Scheda dettaglio **Direttive ubicazione**, imposta i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="7632a-229">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="7632a-230">Accettare i valori predefiniti per i campi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="7632a-230">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="7632a-231">**Tipo di lavoro:** *Inserire*</span><span class="sxs-lookup"><span data-stu-id="7632a-231">**Work type:** *Put*</span></span>
    - <span data-ttu-id="7632a-232">**Sito:** *5*</span><span class="sxs-lookup"><span data-stu-id="7632a-232">**Site:** *5*</span></span>
    - <span data-ttu-id="7632a-233">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="7632a-233">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="7632a-234">Nel riquadro azioni, selezionare **Salva** per salvare la direttiva e rendere disponibile la Scheda dettaglio **Righe**.</span><span class="sxs-lookup"><span data-stu-id="7632a-234">On the Action Pane select **Save** to save your directive and make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="7632a-235">Nella Scheda dettaglio **Righe**, seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="7632a-235">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="7632a-236">Nella nuova riga, imposta i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="7632a-236">On the new line, set the following values.</span></span> <span data-ttu-id="7632a-237">Accettare i valori predefiniti per i campi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="7632a-237">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="7632a-238">**Da quantità:** *1*</span><span class="sxs-lookup"><span data-stu-id="7632a-238">**From quantity:** *1*</span></span>
    - <span data-ttu-id="7632a-239">**A quantità:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="7632a-239">**To quantity:** *1000000*</span></span>

1. <span data-ttu-id="7632a-240">Nel riquadro azioni, selezionare **Salva** per salvare la nuova riga e rendere disponibile la Scheda dettaglio **Azioni direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="7632a-240">On the Action Pane, select **Save** to save the new line and make the **Location directive actions** FastTab available.</span></span>
1. <span data-ttu-id="7632a-241">Mentre la nuova riga è ancora selezionata nella Scheda dettaglio **Righe**, selezionare **Nuova** nella Scheda dettaglio **Azioni direttiva ubicazione** per aggiungere una riga alla griglia in quel punto, in modo da poter configurare un'azione per la riga.</span><span class="sxs-lookup"><span data-stu-id="7632a-241">While the new line is still selected on the **Lines** FastTab, select **New** on the **Location directive actions** FastTab to add a row to the grid there, so that you can set up an action for the line.</span></span>
1. <span data-ttu-id="7632a-242">Nella nuova riga, impostare il campo **Nome** su *Qualità*.</span><span class="sxs-lookup"><span data-stu-id="7632a-242">In the new row, set the **Name** field to *Quality*.</span></span> <span data-ttu-id="7632a-243">Accettare i valori predefiniti per i campi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="7632a-243">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="7632a-244">Nel riquadro azioni, selezionare **Salva** per rendere disponibile il pulsante **Modifica query** nella Scheda dettaglio **Azioni direttiva ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="7632a-244">On the Action Pane, select **Save** to make the **Edit query** button on the **Location directive actions** FastTab available.</span></span>
1. <span data-ttu-id="7632a-245">Mentre la riga appena aggiunta è ancora selezionata nella Scheda dettaglio **Azioni direttiva ubicazione**, selezionare **Modifica query** per aprire una finestra di dialogo in cui è possibile modificare la query per l'azione.</span><span class="sxs-lookup"><span data-stu-id="7632a-245">While the line that you just added is still selected on the **Location directive actions** FastTab, select **Edit query** to open a dialog box where you can edit the query for the action.</span></span>
1. <span data-ttu-id="7632a-246">Nella scheda **Intervallo**, selezionare **Aggiungi** per aggiungere una riga alla query.</span><span class="sxs-lookup"><span data-stu-id="7632a-246">On the **Range** tab, select **Add** to add a row to the query.</span></span>
1. <span data-ttu-id="7632a-247">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="7632a-247">In the new row, set the following values:</span></span>

    - <span data-ttu-id="7632a-248">**Tabella:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="7632a-248">**Table:** *Locations*</span></span>
    - <span data-ttu-id="7632a-249">**Tabella derivata:** *Ubicazioni*</span><span class="sxs-lookup"><span data-stu-id="7632a-249">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="7632a-250">**Campo:** *Ubicazione*</span><span class="sxs-lookup"><span data-stu-id="7632a-250">**Field:** *Location*</span></span>
    - <span data-ttu-id="7632a-251">**Criteri:** *QMS*</span><span class="sxs-lookup"><span data-stu-id="7632a-251">**Criteria:** *QMS*</span></span>

    <span data-ttu-id="7632a-252">L'ubicazione *QMS* è un'ubicazione di magazzino per la qualità.</span><span class="sxs-lookup"><span data-stu-id="7632a-252">The *QMS* location is a warehouse location for quality.</span></span>

1. <span data-ttu-id="7632a-253">Selezionare **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="7632a-253">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="7632a-254">Ora è necessario modificare la sequenza delle direttive di ubicazione dell'ordine fornitore per il magazzino *51*.</span><span class="sxs-lookup"><span data-stu-id="7632a-254">You must now change the sequence of purchase order location directives for warehouse *51*.</span></span> <span data-ttu-id="7632a-255">Salvare la nuova direttiva ubicazione *51 alla qualità*, aggiornare la pagina e selezionare la direttiva ubicazione nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7632a-255">Save the new *51 To Quality* location directive, refresh the page, and select the location directive in the list.</span></span> <span data-ttu-id="7632a-256">Quindi utilizzare i pulsanti **Sposta su** e **Sposta giù** nel riquadro azioni per inserire la direttiva ubicazione per il magazzino *51* nel seguente ordine.</span><span class="sxs-lookup"><span data-stu-id="7632a-256">Then use the **Move up** and **Move down** buttons on the Action Pane to put the location directive for warehouse *51* in the following order.</span></span> <span data-ttu-id="7632a-257">(Prima di selezionare **Sposta su** o **Sposta giù**, è necessario selezionare una direttiva ubicazione nell'elenco).</span><span class="sxs-lookup"><span data-stu-id="7632a-257">(Before you select **Move up** or **Move down**, you must select a location directive in the list.)</span></span>

    1. <span data-ttu-id="7632a-258">Da 51 a qualità</span><span class="sxs-lookup"><span data-stu-id="7632a-258">51 To Quality</span></span>
    2. <span data-ttu-id="7632a-259">51 PO Diretto</span><span class="sxs-lookup"><span data-stu-id="7632a-259">51 PO Direct</span></span>
    3. <span data-ttu-id="7632a-260">51 QMS</span><span class="sxs-lookup"><span data-stu-id="7632a-260">51 QMS</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="7632a-261">Voci di menu del dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="7632a-261">Mobile device menu items</span></span>

<span data-ttu-id="7632a-262">Configurare una voce di menu in modo che i dispositivi mobili possano eseguire la funzione **Controllo qualità**.</span><span class="sxs-lookup"><span data-stu-id="7632a-262">Configure a menu item so that mobile devices can perform the **Quality Check** function.</span></span>

#### <a name="purchase-putaway"></a><span data-ttu-id="7632a-263">Stoccaggio di acquisto</span><span class="sxs-lookup"><span data-stu-id="7632a-263">Purchase putaway</span></span>

1. <span data-ttu-id="7632a-264">Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="7632a-264">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="7632a-265">Nell'elenco, selezionare la voce d menu **Stoccaggio acquisto**.</span><span class="sxs-lookup"><span data-stu-id="7632a-265">In the list, select the **Purchase put-away** menu item.</span></span>
1. <span data-ttu-id="7632a-266">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="7632a-266">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="7632a-267">Nella sezione **Classi di lavoro**, selezionare **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="7632a-267">In the **Work classes** section, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="7632a-268">Nella nuova riga, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="7632a-268">In the new row, set the following values:</span></span>

    - <span data-ttu-id="7632a-269">**ID classe lavoro:** *Controllo di qualità*</span><span class="sxs-lookup"><span data-stu-id="7632a-269">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="7632a-270">Immettere il nome della [classe di lavoro](#work-class) creata in precedenza per il lavoro di controllo della qualità.</span><span class="sxs-lookup"><span data-stu-id="7632a-270">Enter the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

    - <span data-ttu-id="7632a-271">**Tipo di ordine di lavoro:** *Qualità nel controllo qualità*</span><span class="sxs-lookup"><span data-stu-id="7632a-271">**Work order type:** *Quality in quality check*</span></span>

1. <span data-ttu-id="7632a-272">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7632a-272">On the Action Pane, select **Save**.</span></span>

#### <a name="purchase-order-line-receiving"></a><span data-ttu-id="7632a-273">Ricevimento riga ordine acquisto</span><span class="sxs-lookup"><span data-stu-id="7632a-273">Purchase order line receiving</span></span>

1. <span data-ttu-id="7632a-274">Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="7632a-274">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="7632a-275">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7632a-275">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="7632a-276">Nell'intestazione, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="7632a-276">In the header, set the following values:</span></span>

    - <span data-ttu-id="7632a-277">**Nome voce di menu:** *Ricezione riga PO*</span><span class="sxs-lookup"><span data-stu-id="7632a-277">**Menu item name:** *PO line receiving*</span></span>
    - <span data-ttu-id="7632a-278">**Titolo:** *Ricezione riga PO*</span><span class="sxs-lookup"><span data-stu-id="7632a-278">**Title:** *PO line receiving*</span></span>
    - <span data-ttu-id="7632a-279">**Modalità:** *Lavoro*</span><span class="sxs-lookup"><span data-stu-id="7632a-279">**Mode:** *Work*</span></span>
    - <span data-ttu-id="7632a-280">**Utilizza lavoro esistente:** *No*</span><span class="sxs-lookup"><span data-stu-id="7632a-280">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="7632a-281">Nella Scheda dettaglio **Generale**, impostare i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="7632a-281">On the **General** FastTab, set the following values.</span></span> <span data-ttu-id="7632a-282">Accettare i valori predefiniti per i campi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="7632a-282">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="7632a-283">**Processo di creazione lavoro:** *Ricevimento e stoccaggio riga ordine acquisto*</span><span class="sxs-lookup"><span data-stu-id="7632a-283">**Work creation process:** *Purchase order line receiving and put away*</span></span>
    - <span data-ttu-id="7632a-284">**Genera targa:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="7632a-284">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="7632a-285">**Modello di lavoro:** *51 PO ricevuta*</span><span class="sxs-lookup"><span data-stu-id="7632a-285">**Work template:** *51 PO Receipt*</span></span>

1. <span data-ttu-id="7632a-286">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7632a-286">On the Action Pane, select **Save**.</span></span>

#### <a name="add-the-menu-item-to-a-mobile-device-menu"></a><span data-ttu-id="7632a-287">Aggiungere la voce di menu a un menu per dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="7632a-287">Add the menu item to a mobile device menu</span></span>

1. <span data-ttu-id="7632a-288">Accedere a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="7632a-288">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="7632a-289">Nel riquadro sinistro, selezionare il menu **In entrata**.</span><span class="sxs-lookup"><span data-stu-id="7632a-289">In the left pane, select the **Inbound** menu.</span></span>
1. <span data-ttu-id="7632a-290">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="7632a-290">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="7632a-291">Nella colonna **Menu e voci di menu disponibili**, selezionare la nuova voce di menu **Ricezione riga PO**.</span><span class="sxs-lookup"><span data-stu-id="7632a-291">In the **Available menus and menu items** column, select the new **PO line receiving** menu item.</span></span>
1. <span data-ttu-id="7632a-292">Selezionare il pulsante freccia DESTRA per spostare **Ricezione riga PO** nella colonna **Struttura menu**.</span><span class="sxs-lookup"><span data-stu-id="7632a-292">Select the right arrow button to move **PO line receiving** to the **Menu structure** column.</span></span>
1. <span data-ttu-id="7632a-293">Nella colonna **Struttura menu**, selezionare **Ricezione riga PO**, quindi selezionare il pulsante freccia SU o freccia GIÙ per spostare la voce di menu nella posizione desiderata nel menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="7632a-293">In the **Menu structure** column, select **PO line receiving**, and then select the up arrow or down arrow button to move the menu item to the desired position on the mobile device menu.</span></span>
1. <span data-ttu-id="7632a-294">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7632a-294">On the Action Pane, select **Save**.</span></span>

## <a name="example-scenario"></a><a name="example-scenario"></a><span data-ttu-id="7632a-295">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="7632a-295">Example scenario</span></span>

<span data-ttu-id="7632a-296">Dopo aver reso disponibili tutti i dati di esempio precedentemente descritti e averli configurati, è possibile utilizzare questo scenario per provare la funzionalità *Controllo qualità*.</span><span class="sxs-lookup"><span data-stu-id="7632a-296">After you've made all the previously described sample data available and set it up, you can work through this scenario to try out the *Quality check* feature.</span></span> <span data-ttu-id="7632a-297">I valori mostrati in questo scenario presuppongono che si stia lavorando con i dati dimostrativi standard, che sia stata selezionata la persona giuridica **USMF** e che sono stati preparati i record di esempio descritti in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7632a-297">The values that are shown in this scenario assume that you're working with the standard demo data, that you selected the **USMF** legal entity, and that you prepared the sample records that are described earlier in this topic.</span></span> <span data-ttu-id="7632a-298">Questo scenario serve anche come esempio che mostra come la funzionalità può essere utilizzata in uno scenario di produzione.</span><span class="sxs-lookup"><span data-stu-id="7632a-298">This scenario also serves as an example that shows how the feature can be used in a production setting.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="7632a-299">Creare un ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="7632a-299">Create a purchase order</span></span>

1. <span data-ttu-id="7632a-300">Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.</span><span class="sxs-lookup"><span data-stu-id="7632a-300">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="7632a-301">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7632a-301">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="7632a-302">Nella finestra di dialogo **Crea ordine fornitore**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="7632a-302">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="7632a-303">**Conto fornitore:** *104*</span><span class="sxs-lookup"><span data-stu-id="7632a-303">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="7632a-304">**Magazzino:** *51*</span><span class="sxs-lookup"><span data-stu-id="7632a-304">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="7632a-305">Scegliere **OK** per chiudere la finestra di dialogo e aprire il nuovo ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="7632a-305">Select **OK** to close the dialog box and open the new purchase order.</span></span>
1. <span data-ttu-id="7632a-306">Nella Scheda dettaglio **Righe ordine fornitore**, la griglia contiene una nuova riga vuota.</span><span class="sxs-lookup"><span data-stu-id="7632a-306">On the **Purchase order lines** FastTab, the grid contains a new, blank line.</span></span> <span data-ttu-id="7632a-307">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="7632a-307">On this line, set the following values:</span></span>

    - <span data-ttu-id="7632a-308">**Numero articolo:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="7632a-308">**Item number:** *M9203*</span></span>
    - <span data-ttu-id="7632a-309">**Quantità:** *3*</span><span class="sxs-lookup"><span data-stu-id="7632a-309">**Quantity:** *3*</span></span>
    - <span data-ttu-id="7632a-310">**Unità:** *PALLET*</span><span class="sxs-lookup"><span data-stu-id="7632a-310">**Unit:** *PL*</span></span>

1. <span data-ttu-id="7632a-311">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7632a-311">On the Action Pane, select **Save**.</span></span>

### <a name="process-quality-check-receiving"></a><span data-ttu-id="7632a-312">Elaborare la ricezione del controllo di qualità</span><span class="sxs-lookup"><span data-stu-id="7632a-312">Process quality check receiving</span></span>

<span data-ttu-id="7632a-313">Dopo che l'ordine fornitore è stato creato, può essere ricevuto utilizzando la voce di menu **Ricezione riga PO** e la funzionalità di *Controllo di qualità*.</span><span class="sxs-lookup"><span data-stu-id="7632a-313">After the purchase order has been created, it can be received by using the **PO line receiving** menu item and the functionality of the *Quality check* feature.</span></span>

#### <a name="receive-pallet-1"></a><span data-ttu-id="7632a-314">Ricevere il pallet 1</span><span class="sxs-lookup"><span data-stu-id="7632a-314">Receive pallet 1</span></span>

1. <span data-ttu-id="7632a-315">Accedere all'app di magazzino come utente nel magazzino *51*.</span><span class="sxs-lookup"><span data-stu-id="7632a-315">Sign in to the warehouse app as a user for warehouse *51*.</span></span> <span data-ttu-id="7632a-316">(Immettere *51* come ID utente e *1* come password).</span><span class="sxs-lookup"><span data-stu-id="7632a-316">(Enter *51* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="7632a-317">Passare a **In entrata \> Ricezione riga PO**.</span><span class="sxs-lookup"><span data-stu-id="7632a-317">Go to **Inbound \> PO line receiving**.</span></span>
1. <span data-ttu-id="7632a-318">Nel campo **PONUM**, immettere il numero dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="7632a-318">In the **PONUM** field, enter the purchase order number.</span></span>
1. <span data-ttu-id="7632a-319">Confermare il numero dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="7632a-319">Confirm the purchase order number.</span></span>
1. <span data-ttu-id="7632a-320">Nel campo **LINENUM**, immettere il numero della riga dell'ordine fornitore che viene ricevuta.</span><span class="sxs-lookup"><span data-stu-id="7632a-320">In the **LINENUM** field, enter the number of the purchase order line that is being received.</span></span> <span data-ttu-id="7632a-321">Poiché l'ordine include solo una riga in questo scenario, sarà necessario immettere *1* nel campo **LINENUM** per ogni passaggio di ricezione.</span><span class="sxs-lookup"><span data-stu-id="7632a-321">Because the order has only one line in this scenario, you will enter *1* in the **LINENUM** field for each receiving step.</span></span>
1. <span data-ttu-id="7632a-322">Confermare il numero della riga.</span><span class="sxs-lookup"><span data-stu-id="7632a-322">Confirm the line number.</span></span>
1. <span data-ttu-id="7632a-323">Nel campo **QUANTITÀ** immettere la quantità da ricevere.</span><span class="sxs-lookup"><span data-stu-id="7632a-323">In the **QTY** field, enter the quantity to receive.</span></span> <span data-ttu-id="7632a-324">Poiché l'ordine fornutore è per tre pallet (*PL*) in questo scenario e sono presenti tre passaggi di ricezione, sarà necessario immettere *1* nel campo **QUANTITÀ** per ogni passaggio di ricezione.</span><span class="sxs-lookup"><span data-stu-id="7632a-324">Because the purchase order is for three pallets (*PL*) in this scenario, and there are three receiving steps, you will enter *1* in the **QTY** field for each receiving step.</span></span>
1. <span data-ttu-id="7632a-325">Confermare la quantità.</span><span class="sxs-lookup"><span data-stu-id="7632a-325">Confirm the quantity.</span></span>

    <span data-ttu-id="7632a-326">La pagina **Controllo qualità** visualizzata non ha campi di immissione.</span><span class="sxs-lookup"><span data-stu-id="7632a-326">The **Quality check** page that appears has no entry fields.</span></span> <span data-ttu-id="7632a-327">Ha solo il pulsante di conferma (segno di spunta) in basso e il pulsante Menu (**≡**) in cima.</span><span class="sxs-lookup"><span data-stu-id="7632a-327">It has only the confirmation (check mark) button at the bottom and the Menu button (**≡**) at the top.</span></span> <span data-ttu-id="7632a-328">(Il pulsante Menu viene talvolta definito hamburger o pulsante hamburger). Per accelerare il processo di controllo qualità, quando il pallet supera il controllo qualità, l'utente conferma la pagina **Controllo qualità**.</span><span class="sxs-lookup"><span data-stu-id="7632a-328">(The Menu button is sometimes referred to as the hamburger or the hamburger button.) To expedite the quality check process, when the pallet passes the quality check, the user just confirms the **Quality check** page.</span></span>

    <span data-ttu-id="7632a-329">![Pagina Controllo qualità](media/quality-check.png "Pagina Controllo qualità")</span><span class="sxs-lookup"><span data-stu-id="7632a-329">![Quality check page](media/quality-check.png "Quality check page")</span></span>

1. <span data-ttu-id="7632a-330">Selezionare il pulsante di conferma per superare il controllo di qualità per il pallet 1 dalla riga 1.</span><span class="sxs-lookup"><span data-stu-id="7632a-330">Select the confirmation button to pass the quality check for pallet 1 from line 1.</span></span>

    <span data-ttu-id="7632a-331">La pagina **Ordini fornitore: inserimento** che appare mostra i dettagli del lavoro di inserimento:</span><span class="sxs-lookup"><span data-stu-id="7632a-331">The **Purchase orders: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="7632a-332">**UBICAZIONE:** l'ubicazione determinata dal sistema</span><span class="sxs-lookup"><span data-stu-id="7632a-332">**LOC:** The system determined location</span></span>

        <span data-ttu-id="7632a-333">Questa ubicazione è l'ubicazione di stoccaggio designata per la ricezione dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="7632a-333">This location is the designated putaway location for purchase order receiving.</span></span>

    - <span data-ttu-id="7632a-334">**TARGA:** l'ID targa generato dal sistema</span><span class="sxs-lookup"><span data-stu-id="7632a-334">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="7632a-335">**Articolo:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="7632a-335">**Item:** *M9203*</span></span>
    - <span data-ttu-id="7632a-336">**Quantità:** *1 PL: 100 ea*</span><span class="sxs-lookup"><span data-stu-id="7632a-336">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="7632a-337">Viene anche mostrata la descrizione dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="7632a-337">The item description is also shown.</span></span>

1. <span data-ttu-id="7632a-338">Confermare il lavoro di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="7632a-338">Confirm the putaway work.</span></span>

    <span data-ttu-id="7632a-339">Nella pagina **Attività** per la ricezione della riga ordine fornitore, viene visualizzato il messaggio "Lavoro completato".</span><span class="sxs-lookup"><span data-stu-id="7632a-339">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="7632a-340">Il campo **LINENUM** è disponibile in modo da poter iniziare a ricevere il pallet successivo.</span><span class="sxs-lookup"><span data-stu-id="7632a-340">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

#### <a name="receive-pallet-2"></a><span data-ttu-id="7632a-341">Ricevere il pallet 2</span><span class="sxs-lookup"><span data-stu-id="7632a-341">Receive pallet 2</span></span>

<span data-ttu-id="7632a-342">Per questo scenario, il pallet 2 verrà rifiutato.</span><span class="sxs-lookup"><span data-stu-id="7632a-342">For this scenario, pallet 2 will be rejected.</span></span>

1. <span data-ttu-id="7632a-343">Nel campo **LINENUM**, immettere *1* e confermare il numero di riga.</span><span class="sxs-lookup"><span data-stu-id="7632a-343">In the **LINENUM** field, enter *1*, and confirm the line number.</span></span>
1. <span data-ttu-id="7632a-344">Il campo **QUANTITÀ** è ora disponibile.</span><span class="sxs-lookup"><span data-stu-id="7632a-344">The **QTY** field is now available.</span></span> <span data-ttu-id="7632a-345">Immettere *1* e confermare la quantità.</span><span class="sxs-lookup"><span data-stu-id="7632a-345">Enter *1*, and confirm the quantity.</span></span>

    <span data-ttu-id="7632a-346">Viene visualizzata la pagina **Controllo qualità**.</span><span class="sxs-lookup"><span data-stu-id="7632a-346">The **Quality check** page appears.</span></span> <span data-ttu-id="7632a-347">Per questa ricezione, il pallet verrà rifiutato per la qualità e verrà inserito nell'ubicazione di qualità *QMS*.</span><span class="sxs-lookup"><span data-stu-id="7632a-347">For this receipt, the pallet will be rejected for quality, and it will be put into the *QMS* quality location.</span></span>

1. <span data-ttu-id="7632a-348">Selezionare il pulsante Menu (**≡**) nella parte superiore della pagina, quindi dal menu selezionare **Rifiuta**.</span><span class="sxs-lookup"><span data-stu-id="7632a-348">Select the Menu button (**≡**) at the top of the page, and then, on the menu, select **Reject**.</span></span>
1. <span data-ttu-id="7632a-349">Nella pagina **Attività** che appare, immettere **QMS** come ubicazione *Inserisci* a cui inviare il pallet per ulteriori ispezioni.</span><span class="sxs-lookup"><span data-stu-id="7632a-349">On the **Task** page that appears, enter **QMS** as the *Put* location to send the pallet to for further inspection.</span></span>

    <span data-ttu-id="7632a-350">La pagina **Qualità nel controllo qualità: inserimento** che appare mostra i dettagli del lavoro di inserimento:</span><span class="sxs-lookup"><span data-stu-id="7632a-350">The **Quality in quality check: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="7632a-351">**UBICAZIONE:** *QMS*</span><span class="sxs-lookup"><span data-stu-id="7632a-351">**LOC:** *QMS*</span></span>

        <span data-ttu-id="7632a-352">Questa ubicazione è l'ubicazione di stoccaggio designata per la ricezione della qualità rifiutata.</span><span class="sxs-lookup"><span data-stu-id="7632a-352">This location is the designated putaway location for rejected quality receiving.</span></span>

    - <span data-ttu-id="7632a-353">**TARGA:** l'ID targa generato dal sistema</span><span class="sxs-lookup"><span data-stu-id="7632a-353">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="7632a-354">**Articolo:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="7632a-354">**Item:** *M9203*</span></span>
    - <span data-ttu-id="7632a-355">**Quantità:** *1 PL: 100 ea*</span><span class="sxs-lookup"><span data-stu-id="7632a-355">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="7632a-356">Viene anche mostrata la descrizione dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="7632a-356">The item description is also shown.</span></span>

1. <span data-ttu-id="7632a-357">Confermare il lavoro di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="7632a-357">Confirm the putaway work.</span></span>

    <span data-ttu-id="7632a-358">Nella pagina **Attività** per la ricezione della riga ordine fornitore, viene visualizzato il messaggio "Lavoro completato".</span><span class="sxs-lookup"><span data-stu-id="7632a-358">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="7632a-359">Il campo **LINENUM** è disponibile in modo da poter iniziare a ricevere il pallet successivo.</span><span class="sxs-lookup"><span data-stu-id="7632a-359">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

<span data-ttu-id="7632a-360">Le operazioni di controllo di qualità e creazione di un ordine di controllo qualità per il pallet rifiutato sono state completate.</span><span class="sxs-lookup"><span data-stu-id="7632a-360">You've now completed the quality check and created a quality order for the rejected pallet.</span></span> <span data-ttu-id="7632a-361">Per visualizzare l'ordine di controllo qualità creato, andare a **Gestione inventario \> Attività periodiche \> Gestione della qualità \> Ordini di controllo qualità**.</span><span class="sxs-lookup"><span data-stu-id="7632a-361">To view the order that was created, go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>

<span data-ttu-id="7632a-362">Ora è possibile elaborare il test dell'ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="7632a-362">Quality order testing can now be processed.</span></span> <span data-ttu-id="7632a-363">Il test di qualità non viene illustrato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7632a-363">Quality testing isn't covered in this topic.</span></span>

<span data-ttu-id="7632a-364">Per ulteriori informazioni sulla gestione della qualità, vedere [Panoramica della gestione della qualità](../inventory/enable-quality-management.md).</span><span class="sxs-lookup"><span data-stu-id="7632a-364">For more information about quality management, see [Quality management overview](../inventory/enable-quality-management.md)</span></span>

#### <a name="receive-pallet-3"></a><span data-ttu-id="7632a-365">Ricevere il pallet 3</span><span class="sxs-lookup"><span data-stu-id="7632a-365">Receive pallet 3</span></span>

<span data-ttu-id="7632a-366">Per questo scenario, il pallet 3 verrà accettato.</span><span class="sxs-lookup"><span data-stu-id="7632a-366">For this scenario, pallet 3 will be accepted.</span></span>

1. <span data-ttu-id="7632a-367">Nel campo **LINENUM**, immettere *1* e confermare il numero di riga.</span><span class="sxs-lookup"><span data-stu-id="7632a-367">In the **LINENUM** field, enter *1*, and confirm the line number.</span></span>
1. <span data-ttu-id="7632a-368">Il campo **QUANTITÀ** è ora disponibile.</span><span class="sxs-lookup"><span data-stu-id="7632a-368">The **QTY** field is now available.</span></span> <span data-ttu-id="7632a-369">Immettere *1* e confermare la quantità.</span><span class="sxs-lookup"><span data-stu-id="7632a-369">Enter *1*, and confirm the quantity.</span></span>

    <span data-ttu-id="7632a-370">Viene visualizzata la pagina **Controllo qualità**.</span><span class="sxs-lookup"><span data-stu-id="7632a-370">The **Quality check** page appears.</span></span> <span data-ttu-id="7632a-371">Per questa ricezione, il pallet verrà accettato per la qualità e verrà inserito in un'ubicazione di stoccaggio in blocco.</span><span class="sxs-lookup"><span data-stu-id="7632a-371">For this receipt, the pallet will be accepted for quality, and it will be put into a bulk putaway location.</span></span>

1. <span data-ttu-id="7632a-372">Selezionare il pulsante di conferma per superare il controllo di qualità.</span><span class="sxs-lookup"><span data-stu-id="7632a-372">Select the confirmation button to pass the quality check.</span></span>

    <span data-ttu-id="7632a-373">La pagina **Ordini fornitore: inserimento** che appare mostra i dettagli del lavoro di inserimento:</span><span class="sxs-lookup"><span data-stu-id="7632a-373">The **Purchase orders: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="7632a-374">**UBICAZIONE:** l'ubicazione determinata dal sistema</span><span class="sxs-lookup"><span data-stu-id="7632a-374">**LOC:** The system determined location</span></span>

        <span data-ttu-id="7632a-375">Questa ubicazione è l'ubicazione di stoccaggio designata per la ricezione dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="7632a-375">This location is the designated putaway location for purchase order receiving.</span></span>

    - <span data-ttu-id="7632a-376">**TARGA:** l'ID targa generato dal sistema</span><span class="sxs-lookup"><span data-stu-id="7632a-376">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="7632a-377">**Articolo:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="7632a-377">**Item:** *M9203*</span></span>
    - <span data-ttu-id="7632a-378">**Quantità:** *1 PL: 100 ea*</span><span class="sxs-lookup"><span data-stu-id="7632a-378">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="7632a-379">Viene anche mostrata la descrizione dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="7632a-379">The item description is also shown.</span></span>

1. <span data-ttu-id="7632a-380">Confermare il lavoro di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="7632a-380">Confirm the putaway work.</span></span>

    <span data-ttu-id="7632a-381">Nella pagina **Attività** per la ricezione della riga ordine fornitore, viene visualizzato il messaggio "Lavoro completato".</span><span class="sxs-lookup"><span data-stu-id="7632a-381">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="7632a-382">Il campo **LINENUM** è disponibile in modo da poter iniziare a ricevere il pallet successivo.</span><span class="sxs-lookup"><span data-stu-id="7632a-382">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

1. <span data-ttu-id="7632a-383">Selezionare il pulsante Menu (**≡**) nella parte superiore della pagina, quindi dal menu selezionare **Annulla** per tornare al menu.</span><span class="sxs-lookup"><span data-stu-id="7632a-383">Select the Menu button (**≡**) at the top of the page, and then, on the menu, select **Cancel** to return to the menu.</span></span>

<span data-ttu-id="7632a-384">Ora è possibile chiudere l'app per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="7632a-384">You can now close the mobile app.</span></span>
