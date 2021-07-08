---
title: Messaggi dell'elaboratore messaggi
description: In questo argomento vengono fornite informazioni sulla funzionalità dei messaggi dell'elaboratore messaggi per i carichi di lavoro per unità di scala.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysMessageProcessorMessage, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 86f15831f11dc9fdcada9639858fd3b18cdc7503
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271103"
---
# <a name="message-processor-messages"></a><span data-ttu-id="5fc14-103">Messaggi dell'elaboratore messaggi</span><span class="sxs-lookup"><span data-stu-id="5fc14-103">Message processor messages</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5fc14-104">I messaggi dell'elaboratore messaggi vengono utilizzati durante l'esecuzione di unità di scala per cloud e rete perimetrale per [carichi di lavoro di produzione](cloud-edge-workload-manufacturing.md) e [carichi di lavoro di gestione del magazzino](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="5fc14-104">Message processor messages are used when running cloud and edge scale units for [manufacturing workloads](cloud-edge-workload-manufacturing.md) and [warehouse management workloads](cloud-edge-workload-warehousing.md).</span></span>

<span data-ttu-id="5fc14-105">Una grande quantità di dati viene scambiata tra l'hub e gli ambienti di distribuzione delle unità di scala per mantenerli sincronizzati, ma solo alcuni di questi scambi di dati verranno elaborati dal *elaboratore messaggi*.</span><span class="sxs-lookup"><span data-stu-id="5fc14-105">A large amount of data is exchanged between the hub and scale unit deployment environments to keep them in sync, but only a few of these data exchanges will be processed by the *message processor*.</span></span> <span data-ttu-id="5fc14-106">È possibile visualizzare i messaggi elaborati dall'elaboratore messaggi andando a **Amministrazione di sistema > Elaboratore messaggi > Messaggi elaboratore messaggi**.</span><span class="sxs-lookup"><span data-stu-id="5fc14-106">You can view the messages processed by the message processor by going to **System administration > Message processor > Message processor messages**.</span></span>

## <a name="message-grid-columns-and-filters"></a><span data-ttu-id="5fc14-107">Colonne e filtri della griglia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="5fc14-107">Message grid columns and filters</span></span>

<span data-ttu-id="5fc14-108">Puoi utilizzare i campi nella parte superiore della pagina **Messaggi elaboratore messaggi** per trovare i messaggi specifici che stai cercando.</span><span class="sxs-lookup"><span data-stu-id="5fc14-108">You can use the fields at the top of the **Message processor messages** page to help find any particular messages you are looking for.</span></span> <span data-ttu-id="5fc14-109">La maggior parte di questi filtri corrisponde alle intestazioni delle colonne nella griglia dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="5fc14-109">Most of these filters match the column headings in the message grid.</span></span> <span data-ttu-id="5fc14-110">I seguenti filtri e intestazioni di colonna sono disponibili:</span><span class="sxs-lookup"><span data-stu-id="5fc14-110">The following filters and column headings are available:</span></span>

- <span data-ttu-id="5fc14-111">**Tipo di messaggio** - Specifica il tipo di messaggio.</span><span class="sxs-lookup"><span data-stu-id="5fc14-111">**Message type** – Specifies the type of message.</span></span>
- <span data-ttu-id="5fc14-112">**Coda di messaggi** - Specifica il nome della coda in cui il messaggio deve essere elaborato.</span><span class="sxs-lookup"><span data-stu-id="5fc14-112">**Message queue** – Specifies the name of the queue in which the message is to be processed.</span></span> <span data-ttu-id="5fc14-113">Vengono fornite le seguenti code:</span><span class="sxs-lookup"><span data-stu-id="5fc14-113">The following queues are provided:</span></span>
  - <span data-ttu-id="5fc14-114">*Unità di scala a hub*</span><span class="sxs-lookup"><span data-stu-id="5fc14-114">*Scale unit to hub*</span></span>
  - <span data-ttu-id="5fc14-115">*Hub per unità di scala esecuzione magazzino*</span><span class="sxs-lookup"><span data-stu-id="5fc14-115">*Hub to warehouse execution scale unit*</span></span>
  - <span data-ttu-id="5fc14-116">*Hub per unità di scala esecuzione produzione*</span><span class="sxs-lookup"><span data-stu-id="5fc14-116">*Hub to manufacturing execution scale unit*</span></span>
- <span data-ttu-id="5fc14-117">**Stato messaggio** - Specifica lo stato del messaggio.</span><span class="sxs-lookup"><span data-stu-id="5fc14-117">**Message state** – Specifies the state of the message.</span></span> <span data-ttu-id="5fc14-118">Sono possibili i seguenti stati:</span><span class="sxs-lookup"><span data-stu-id="5fc14-118">The following states exists:</span></span>
  - <span data-ttu-id="5fc14-119">*In coda* - Il messaggio è pronto per essere elaborato dall'elaboratore messaggi.</span><span class="sxs-lookup"><span data-stu-id="5fc14-119">*Queued* – The message is ready to be processed by the message processor.</span></span>
  - <span data-ttu-id="5fc14-120">*Elaborato* - Il messaggio è stato elaborato correttamente dall'elaboratore messaggi.</span><span class="sxs-lookup"><span data-stu-id="5fc14-120">*Processed* – The message was successfully processed by the message processor.</span></span>
  - <span data-ttu-id="5fc14-121">*Annullato* - Il messaggio è stato elaborato, ma l'elaborazione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="5fc14-121">*Canceled* – The message was processed, but processing failed.</span></span>
- <span data-ttu-id="5fc14-122">**Contenuto messaggio** - questo filtro esegue una ricerca full-text del contenuto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="5fc14-122">**Message content** – This filter does a full-text search of message content.</span></span> <span data-ttu-id="5fc14-123">Il contenuto del messaggio non appare nella griglia. Il filtro tratta la maggior parte dei simboli speciali (ad esempio "-") come spazi e tratta tutti i caratteri di spazio come operatori booleani OR.</span><span class="sxs-lookup"><span data-stu-id="5fc14-123">(Message content is not shown in the grid.) The filter treats most special symbols (such as "-") as spaces, and treats all space characters as Boolean OR operators.</span></span> <span data-ttu-id="5fc14-124">T = Ad esempio, questo significa che se cerchi uno specifico valore `journalid` uguale a "USMF-123456", il sistema troverà tutti i messaggi che contengono "USMF" o "123456", che probabilmente sarà un lungo elenco.</span><span class="sxs-lookup"><span data-stu-id="5fc14-124">T=For example, this means if you search for a specific `journalid` value equal "USMF-123456", the system will find all messages that contain "USMF" or "123456", which is likely to be a long list.</span></span> <span data-ttu-id="5fc14-125">Pertanto, sarebbe meglio inserire solo "123456" perché restituirà risultati più specifici.</span><span class="sxs-lookup"><span data-stu-id="5fc14-125">Therefore, it would be better to enter just "123456" alone because that will return more specific results.</span></span>

## <a name="example-message-type-request-inventory-adjustment-financial-update"></a><span data-ttu-id="5fc14-126">Tipo di messaggio di esempio: Richiedi aggiornamento finanziario per rettifica magazzino</span><span class="sxs-lookup"><span data-stu-id="5fc14-126">Example message type: Request inventory adjustment financial update</span></span>

<span data-ttu-id="5fc14-127">Ad esempio, il **Tipo di messaggio** *Richiedi aggiornamento finanziario per rettifica magazzino* viene utilizzato per creare e registrare un giornale di registrazione di conteggio sull'hub quando un lavoratore utilizza l'app di magazzino per [registrare una rettifica magazzino](cloud-edge-warehouse-inventory-adjustment.md) in un carico di lavoro di gestione del magazzino per unità di scala.</span><span class="sxs-lookup"><span data-stu-id="5fc14-127">For example, the **Message type** *Request inventory adjustment financial update* is used to create and post a counting journal on the hub when a worker uses the warehouse app to [register an inventory adjustment](cloud-edge-warehouse-inventory-adjustment.md) on a scale unit warehouse management workload.</span></span> <span data-ttu-id="5fc14-128">Poiché questo processo specifico ha origine da un'unità di scala, il campo **Coda de messaggi** mostrerà il valore *Unità di scala a hub*.</span><span class="sxs-lookup"><span data-stu-id="5fc14-128">Because this specific process originates from a scale unit, the **Message queue** field will show the value *Scale unit to hub*.</span></span>

<span data-ttu-id="5fc14-129">Per questo tipo di messaggio, un carico di lavoro per unità di scala registra il messaggio come parte di un'operazione di rettifica magazzino dell'app di magazzino.</span><span class="sxs-lookup"><span data-stu-id="5fc14-129">For this message type, a scale unit workload records the message as part of a warehouse app inventory adjustment operation.</span></span> <span data-ttu-id="5fc14-130">I dati del messaggio vengono quindi trasferiti all'hub come parte dello stesso processo utilizzato per l'[architettura di Commerce Data Exchange](../../commerce/commerce-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="5fc14-130">The message data is then transferred to the hub as part of the same process used for the [Commerce data exchange architecture](../../commerce/commerce-architecture.md).</span></span> <span data-ttu-id="5fc14-131">Il messaggio verrà aggiornato per mostrare **Stato messaggio** *In coda*.</span><span class="sxs-lookup"><span data-stu-id="5fc14-131">The message will be updated to show **Message state** as *Queued*.</span></span> <span data-ttu-id="5fc14-132">L'elaboratore messaggi tenta quindi di elaborare il messaggio e aggiorna **Stato messaggio** in *Elaborato* in caso di successo, o *Annullato* in caso di esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5fc14-132">The message processor then attempts to process the message and updates the **Message state** to *Processed* on success, or *Canceled* on failure.</span></span>

## <a name="view-the-message-log-message-content-and-details"></a><span data-ttu-id="5fc14-133">Visualizzare il registro dei messaggi, il contenuto del messaggio e i dettagli</span><span class="sxs-lookup"><span data-stu-id="5fc14-133">View the message log, message content, and details</span></span>

<span data-ttu-id="5fc14-134">È possibile trovare informazioni dettagliate su un messaggio selezionandolo nella griglia e quindi aprendo le schede **Registro** o **Contenuto messaggio** sotto la griglia dei messaggi, dove viene mostrato ogni evento di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="5fc14-134">You can find detailed information about a message by selecting it in the grid and then opening the **Log** or **Message content** tabs under the message grid, where each processing event is shown.</span></span>

<span data-ttu-id="5fc14-135">**Contenuto messaggio** dipende da **Tipo di messaggio** e avrà quindi lunghezza del testo diversa.</span><span class="sxs-lookup"><span data-stu-id="5fc14-135">The **Message content** depends on the **Message type** and will therefore have different text length.</span></span> <span data-ttu-id="5fc14-136">Il testo del contenuto di un messaggio tipico inizierà con **{** e termina con **}** e in mezzo ci sono nomi di campo come `journalId` seguito da **:** e un valore come *USMF-123456*.</span><span class="sxs-lookup"><span data-stu-id="5fc14-136">A typical message content text will start with a **{** and end with a **}** and in between have field names such as `journalId` followed by a **:** and a value such as *USMF-123456*.</span></span>

<span data-ttu-id="5fc14-137">La barra degli strumenti nella scheda **Registro** include i seguenti pulsanti:</span><span class="sxs-lookup"><span data-stu-id="5fc14-137">The toolbar on the **Log** tab includes the following buttons:</span></span>

- <span data-ttu-id="5fc14-138">**Registro** - Visualizza i risultati dell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="5fc14-138">**Log** – Displays the processing results.</span></span> <span data-ttu-id="5fc14-139">Ciò è particolarmente utile per comprendere i motivi di un errore di elaborazione dei messaggi con **Risultato dell'elaborazione** *Non riuscito*.</span><span class="sxs-lookup"><span data-stu-id="5fc14-139">This is especially helpful for understanding the reasons for a processing failure for messages having a **Processing result** of *Failed*.</span></span>
- <span data-ttu-id="5fc14-140">**Aggregazione** - È possibile eseguire più operazioni di elaborazione dei messaggi come parte dello stesso processo batch.</span><span class="sxs-lookup"><span data-stu-id="5fc14-140">**Bundle** – Multiple message processing operations can run as part of the same batch process.</span></span> <span data-ttu-id="5fc14-141">Seleziona questo pulsante per visualizzare questi dati dettagliati.</span><span class="sxs-lookup"><span data-stu-id="5fc14-141">Select this button to view this detailed data.</span></span> <span data-ttu-id="5fc14-142">Ad esempio, è possibile vedere se esistono dipendenze che richiedono al sistema di elaborare determinati messaggi in una sequenza specifica.</span><span class="sxs-lookup"><span data-stu-id="5fc14-142">For example, you can see whether dependencies exist that require the system to process certain messages in a specific sequence.</span></span>

## <a name="message-processor-batch-job"></a><span data-ttu-id="5fc14-143">Processo batch dell'elaboratore messaggi</span><span class="sxs-lookup"><span data-stu-id="5fc14-143">Message processor batch job</span></span>

<span data-ttu-id="5fc14-144">Quando si esegue una distribuzione su cloud e rete perimetrale, il processo batch *Elaboratore messaggi* verrà richiamato automaticamente quando viene creato un nuovo messaggio per l'elaborazione, quindi non dovrebbe essere necessario pianificare questo lavoro manualmente.</span><span class="sxs-lookup"><span data-stu-id="5fc14-144">When running a cloud and edge deployment, the *Message processor* batch job will automatically be evoked when a new message is created for processing, so you should not need to schedule this job manually.</span></span>

<span data-ttu-id="5fc14-145">Se necessario, puoi accedere al processo batch andando su **Amministrazione di sistema > Elaboratore messaggi > Elaboratore messaggi**.</span><span class="sxs-lookup"><span data-stu-id="5fc14-145">If necessary, you can access the batch job by going to **System administration > Message  processor > Message processor**.</span></span>

## <a name="manually-process-or-cancel-a-message"></a><span data-ttu-id="5fc14-146">Elaborare o annullare manualmente un messaggio</span><span class="sxs-lookup"><span data-stu-id="5fc14-146">Manually process or cancel a message</span></span>

<span data-ttu-id="5fc14-147">Se necessario, è possibile elaborare o annullare manualmente un messaggio, a seconda del suo stato corrente.</span><span class="sxs-lookup"><span data-stu-id="5fc14-147">If needed, you can manually process or cancel a message, depending on its current state.</span></span> <span data-ttu-id="5fc14-148">A tale scopo, selezionare il messaggio nella griglia e quindi selezionare **Elabora** o **Annulla** nel riquadro azioni</span><span class="sxs-lookup"><span data-stu-id="5fc14-148">To do so, select the message in the grid and then select **Process** or **Cancel** on the Action Pane</span></span>

## <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a><span data-ttu-id="5fc14-149">Impostare eventi aziendali per fornire avvisi per risultati di elaborazione non riusciti</span><span class="sxs-lookup"><span data-stu-id="5fc14-149">Set up business events to deliver alerts for failed processing results</span></span>

<span data-ttu-id="5fc14-150">Oltre a filtrare in base al valore di **Stato messaggio** *Annullato* per richiedere informazioni sui messaggi non riusciti, è possibile impostare [Eventi aziendali](../../fin-ops-core/dev-itpro/business-events/home-page.md) sull'hub per avvisarti dei risultati di elaborazioni non riuscite.</span><span class="sxs-lookup"><span data-stu-id="5fc14-150">In addition to filtering on the **Message state** value *Canceled* to inquire for failed messages, you can set up [Business events](../../fin-ops-core/dev-itpro/business-events/home-page.md) on the hub to alert you to failed processing results.</span></span> <span data-ttu-id="5fc14-151">A tale scopo, attiva l'evento aziendale denominato *Messaggio elaboratore messaggi elaborato* nella pagina **Catalogo eventi aziendali** (**Amministrazione di sistema > Imposta > Eventi aziendali > Catalogo eventi aziendali**).</span><span class="sxs-lookup"><span data-stu-id="5fc14-151">To do so, activate the business event named *Message processor message processed*  on the **Business events catalog** page (**System administration > Setup > Business events > Business events catalog**).</span></span>

<span data-ttu-id="5fc14-152">Come parte del processo di attivazione, sarai guidato a specificare se l'evento è specifico per una o tutte le persone giuridiche e fornire un **Nome di endpoint**, che deve essere definito per primo.</span><span class="sxs-lookup"><span data-stu-id="5fc14-152">As part of the activation process, you will be guided to specify whether the event is specific to one or all legal entities and provide an **Endpoint name**, which must be defined first.</span></span>

>[!NOTE]
> <span data-ttu-id="5fc14-153">Se **Quando si verifica un evento aziendale** è impostato su *Microsoft Power Automate* (piuttosto che su *HTTPS*, ad esempio), **Nome di endpoint** verrà creato automaticamente in Supply Chain Management in base all'impostazione *Microsoft Power Automate*.</span><span class="sxs-lookup"><span data-stu-id="5fc14-153">If **When a Business Event occurs** is set to *Microsoft Power Automate* (rather than *HTTPS*, for example), the **Endpoint name** will automatically be created in Supply Chain Management based on the *Microsoft Power Automate* setup.</span></span>

### <a name="microsoft-power-automate-example"></a><span data-ttu-id="5fc14-154">Esempio Microsoft Power Automate</span><span class="sxs-lookup"><span data-stu-id="5fc14-154">Microsoft Power Automate example</span></span>

<span data-ttu-id="5fc14-155">In questo esempio, l'uso di **Quando si verifica un evento aziendale** con *Microsoft Power Automate* invia e-mail contenenti messaggi InfoLog e collegamenti ipertestuali per aprire la pagina **Messaggi elaboratore messaggi** per un messaggio di errore specifico nella distribuzione hub.</span><span class="sxs-lookup"><span data-stu-id="5fc14-155">In this example, use **When a Business Event occurs** with *Microsoft Power Automate* sends emails containing InfoLog messages and hyperlinks to open the **Message processor messages** page for a specific failed message on the hub deployment.</span></span> <span data-ttu-id="5fc14-156">Se necessario, è possibile aggiungere ulteriore logica per inviare le notifiche in parallelo utilizzando diversi canali e controllare i destinatari in base ai dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="5fc14-156">If needed, you can add extra logic to send the notifications in parallel using different channels and control the recipients based on the event data.</span></span>

1. <span data-ttu-id="5fc14-157">In [Power Automate](https://preview.flow.microsoft.com), crea un nuovo flusso cloud automatizzato per il trigger di flusso **Quando si verifica un evento aziendale - App Fin & Ops (Dynamics 365)** seguito dai passaggi **Analizza JSON** e **Invia un'e-mail**, come mostrato nell'illustrazione seguente.</span><span class="sxs-lookup"><span data-stu-id="5fc14-157">In [Power Automate](https://preview.flow.microsoft.com), create a new automated cloud flow for the flow trigger **When a Business Event occurs - Fin & Ops App (Dynamics 365)** followed by the **Parse JSON** and **Send an email** steps, as shown in the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example1.png" alt-text="Flusso cloud automatizzato di Power Automate":::

1. <span data-ttu-id="5fc14-159">Nel passaggio **Quando si verifica un evento aziendale** puoi cercare o inserire l'**Istanza** hub seguendo la **Categoria** e poi l'**Evento aziendale** *Messaggio elaboratore messaggi elaborato*, come mostrato nell'illustrazione seguente.</span><span class="sxs-lookup"><span data-stu-id="5fc14-159">In the **When a Business Event occurs** step, you can look up or enter the hub **Instance** following the **Category** and then the **Business event** *Message processor message processed*, as shown in the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example2.png" alt-text="Passaggio Power Automate Quando si verifica un evento aziendale":::

1. <span data-ttu-id="5fc14-161">Per il passaggio **Analizza JSON**, immettere uno **Schema** che definisce i campi estesi.</span><span class="sxs-lookup"><span data-stu-id="5fc14-161">For the **Parse JSON** step, enter a **Schema** that defines the extended fields.</span></span> <span data-ttu-id="5fc14-162">Puoi usare l'opzione *Scarica schema* nella pagina **Catalogo eventi aziendali** in Supply Chain Management o iniziare incollando il testo dello schema di esempio.</span><span class="sxs-lookup"><span data-stu-id="5fc14-162">You can use the *Download schema* option on the **Business events catalog** page in Supply Chain Management or start by pasting in the example schema text.</span></span> <span data-ttu-id="5fc14-163">Questo testo di esempio viene fornito dopo la seguente illustrazione.</span><span class="sxs-lookup"><span data-stu-id="5fc14-163">This example text is provided after the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example3.png" alt-text="Passaggio Power Automate Analizza JSON":::

    ```json
    {
        "properties": {
            "BusinessEventId": {
                "type": "string"
            },
            "ControlNumber": {
                "type": "integer"
            },
            "EventId": {
                "type": "string"
            },
            "EventTime": {
                "type": "string"
            },
            "MajorVersion": {
                "type": "integer"
            },
            "MessageContent": {
                "type": "string"
            },
            "MessageDestinationCompanyId": {
                "type": "string"
            },
            "MessageDestinationOperationalSiteId": {
                "type": "string"
            },
            "MessageDestinationWarehouseId": {
                "type": "string"
            },
            "MessageDestinationWorkloadName": {
                "type": "string"
            },
            "MessageInfolog": {
                "type": "string"
            },
            "MessageProcessingResult": {
                "type": "string"
            },
            "MessageProcessingResultLabel": {
                "type": "string"
            },
            "MessageProcessorMessagePageUrl": {
                "type": "string"
            },
            "MessageQueue": {
                "type": "string"
            },
            "MessageQueueLabel": {
                "type": "string"
            },
            "MessageSourceCompanyId": {
                "type": "string"
            },
            "MessageSourceOperationalSiteId": {
                "type": "string"
            },
            "MessageSourceWarehouseId": {
                "type": "string"
            },
            "MessageSourceWorkloadName": {
                "type": "string"
            },
            "MessageState": {
                "type": "string"
            },
            "MessageStateLabel": {
                "type": "string"
            },
            "MessageType": {
                "type": "string"
            },
            "MessageTypeLabel": {
                "type": "string"
            },
            "MinorVersion": {
                "type": "integer"
            }
        },
        "type": "object"
    }
    ```

1. <span data-ttu-id="5fc14-165">Nel passaggio **Invia e-mail**, è possibile selezionare i singoli campi o iniziare incollando l'esempio del corpo dell'email nel campo **Corpo**.</span><span class="sxs-lookup"><span data-stu-id="5fc14-165">In the **Send an email** step, you can select the individual fields or start by pasting the email body example into the **Body** field.</span></span> <span data-ttu-id="5fc14-166">Questo esempio viene fornito dopo la seguente illustrazione.</span><span class="sxs-lookup"><span data-stu-id="5fc14-166">This example is provided after the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example4.png" alt-text="Passaggio Power Automate Invia e-mail":::

    ```plaintext
    Message queue: @{body('Parse_JSON')?['MessageQueue']}
    Message queue label: @{body('Parse_JSON')?['MessageQueueLabel']}
    Message type: @{body('Parse_JSON')?['MessageQueueType']}
    Message type label: @{body('Parse_JSON')?['MessageQueueTypeLabel']}
    Message content: @{body('Parse_JSON')?['MessageContent']}
    Message state: @{body('Parse_JSON')?['MessageState']}
    Message state label: @{body('Parse_JSON')?['MessageStateLabel']}
    Message processing result: @{body('Parse_JSON')?['MessageProcessingResult']}
    Message processing result label: @{body('Parse_JSON')?['MessageProcessingResultLabel']}
    Message infolog: @{body('Parse_JSON')?['MessageInfolog']}
    Message source company ID: @{body('Parse_JSON')?['MessageSourceCompanyId']}
    Message source workload name: @{body('Parse_JSON')?['MessageSourceWorkloadName']}
    Message source site ID: @{body('Parse_JSON')?['MessageSourceOperationalSiteId']}
    Message source warehouse ID: @{body('Parse_JSON')?['MessageSourceWarehouseId']}
    Message destination company ID: @{body('Parse_JSON')?['MessageDestinationCompanyId']}
    Message destination workload name: @{body('Parse_JSON')?['MessageDestinationWorkloadName']}
    Message destination site ID: @{body('Parse_JSON')?['MessageDestinationOperationalSiteId']}
    Message destination warehouse ID: @{body('Parse_JSON')?['MessageDestinationWarehouseId']}
    Message processor message page URL: @{body('Parse_JSON')?['MessageProcessorMessagePageUrl']}
    ```

1. <span data-ttu-id="5fc14-168">Quando salvi l'evento aziendale, verrà automaticamente attivato e pronto per essere utilizzato come parte di Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5fc14-168">When you save the business event, it will automatically be activated and ready to use as part of Supply Chain Management.</span></span>
