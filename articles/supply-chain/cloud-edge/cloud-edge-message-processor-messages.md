---
title: Messaggi dell'elaboratore messaggi
description: In questo articolo vengono fornite informazioni sulla funzionalità dei messaggi dell'elaboratore messaggi per i carichi di lavoro per unità di scala.
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
ms.openlocfilehash: a5f8d48ba697df389150f70ac159e690156de33b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893615"
---
# <a name="message-processor-messages"></a>Messaggi dell'elaboratore messaggi

[!include [banner](../includes/banner.md)]

I messaggi dell'elaboratore messaggi vengono utilizzati durante l'esecuzione di unità di scala per cloud e rete perimetrale per [carichi di lavoro di produzione](cloud-edge-workload-manufacturing.md) e [carichi di lavoro di gestione del magazzino](cloud-edge-workload-warehousing.md).

L'hub e gli ambienti di distribuzione delle unità di scala scambiano una grande quantità di dati per rimanere sincronizzati. Alcuni di questi dati scambiati attiveranno la logica aggiuntiva nell'*elaboratore messaggi*. È possibile visualizzare i messaggi elaborati dall'elaboratore messaggi andando a **Amministrazione di sistema > Elaboratore messaggi > Messaggi elaboratore messaggi**.

## <a name="message-grid-columns-and-filters"></a>Colonne e filtri della griglia dei messaggi

Puoi utilizzare i campi nella parte superiore della pagina **Messaggi elaboratore messaggi** per trovare i messaggi specifici che stai cercando. La maggior parte di questi filtri corrisponde alle intestazioni delle colonne nella griglia dei messaggi. I seguenti filtri e intestazioni di colonna sono disponibili:

- **Tipo di messaggio** - Specifica il tipo di messaggio.
- **Coda di messaggi** - Specifica il nome della coda in cui il messaggio deve essere elaborato. Vengono fornite le seguenti code:
  - *Unità di scala a hub*
  - *Hub per unità di scala esecuzione magazzino*
  - *Hub per unità di scala esecuzione produzione*
- **Stato messaggio** - Specifica lo stato del messaggio. Sono possibili i seguenti stati:
  - *In coda* - Il messaggio è pronto per essere elaborato dall'elaboratore messaggi.
  - *Elaborato* - Il messaggio è stato elaborato correttamente dall'elaboratore messaggi.
  - *Annullato* - Il messaggio è stato elaborato, ma l'elaborazione non è riuscita.
- **Contenuto messaggio** - questo filtro esegue una ricerca full-text del contenuto del messaggio. Il contenuto del messaggio non appare nella griglia. Il filtro tratta la maggior parte dei simboli speciali (ad esempio "-") come spazi e tratta tutti i caratteri di spazio come operatori booleani OR. Ad esempio, questo significa che se si cerca uno specifico valore `journalid` uguale a "USMF-123456", il sistema troverà tutti i messaggi che contengono "USMF" o "123456", che probabilmente sarà un lungo elenco. Pertanto, sarebbe meglio inserire solo "123456" perché restituirà risultati più specifici.

## <a name="example-message-type-request-inventory-adjustment-financial-update"></a>Tipo di messaggio di esempio: Richiedi aggiornamento finanziario per rettifica magazzino

Ad esempio, il **Tipo di messaggio** *Richiedi aggiornamento finanziario per rettifica magazzino* viene utilizzato per creare e registrare un giornale di registrazione di conteggio sull'hub quando un lavoratore utilizza l'app di magazzino per [registrare una rettifica magazzino](cloud-edge-warehouse-inventory-adjustment.md) in un carico di lavoro di gestione del magazzino per unità di scala. Poiché questo processo specifico ha origine da un'unità di scala, il campo **Coda de messaggi** mostrerà il valore *Unità di scala a hub*.

Per questo tipo di messaggio, un carico di lavoro per unità di scala registra il messaggio come parte di un'operazione di rettifica magazzino dell'app di magazzino. I dati del messaggio vengono quindi trasferiti all'hub come parte dello stesso processo utilizzato per l'[architettura di Commerce Data Exchange](../../commerce/commerce-architecture.md). Il messaggio verrà aggiornato per mostrare **Stato messaggio** *In coda*. L'elaboratore messaggi tenta quindi di elaborare il messaggio e aggiorna **Stato messaggio** in *Elaborato* in caso di successo, o *Annullato* in caso di esito negativo.

## <a name="view-the-message-log-message-content-and-details"></a>Visualizzare il registro dei messaggi, il contenuto del messaggio e i dettagli

È possibile trovare informazioni dettagliate su un messaggio selezionandolo nella griglia e quindi aprendo le schede **Registro** o **Contenuto messaggio** sotto la griglia dei messaggi, dove viene mostrato ogni evento di elaborazione.

**Contenuto messaggio** dipende da **Tipo di messaggio** e avrà quindi lunghezza del testo diversa. Il testo del contenuto di un messaggio tipico inizierà con **{** e termina con **}** e in mezzo ci sono nomi di campo come `journalId` seguito da **:** e un valore come *USMF-123456*.

La barra degli strumenti nella scheda **Registro** include i seguenti pulsanti:

- **Registro** - Visualizza i risultati dell'elaborazione. Ciò è particolarmente utile per comprendere i motivi di un errore di elaborazione dei messaggi con **Risultato dell'elaborazione** *Non riuscito*.
- **Aggregazione** - È possibile eseguire più operazioni di elaborazione dei messaggi come parte dello stesso processo batch. Seleziona questo pulsante per visualizzare questi dati dettagliati. Ad esempio, è possibile vedere se esistono dipendenze che richiedono al sistema di elaborare determinati messaggi in una sequenza specifica.

## <a name="message-processor-batch-job"></a>Processo batch dell'elaboratore messaggi

Quando si esegue una topologia ibrida distribuita con unità di scala, il processo batch *Elaboratore messaggi* verrà richiamato automaticamente quando viene creato un nuovo messaggio per l'elaborazione, quindi non dovrebbe essere necessario pianificare questo lavoro manualmente.

Se necessario, puoi accedere al processo batch andando su **Amministrazione di sistema > Elaboratore messaggi > Elaboratore messaggi**.

## <a name="manually-process-or-cancel-a-message"></a>Elaborare o annullare manualmente un messaggio

Se necessario, è possibile elaborare o annullare manualmente un messaggio, a seconda del suo stato corrente. A tale scopo, selezionare il messaggio nella griglia e quindi selezionare **Elabora** o **Annulla** nel riquadro azioni

## <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a>Impostare eventi aziendali per fornire avvisi per risultati di elaborazione non riusciti

Oltre a filtrare in base al valore di **Stato messaggio** *Annullato* per richiedere informazioni sui messaggi non riusciti, è possibile impostare [Eventi aziendali](../../fin-ops-core/dev-itpro/business-events/home-page.md) sull'hub per avvisarti dei risultati di elaborazioni non riuscite. A tale scopo, attiva l'evento aziendale denominato *Messaggio elaboratore messaggi elaborato* nella pagina **Catalogo eventi aziendali** (**Amministrazione di sistema > Imposta > Eventi aziendali > Catalogo eventi aziendali**).

Come parte del processo di attivazione, sarai guidato a specificare se l'evento è specifico per una o tutte le persone giuridiche e fornire un **Nome di endpoint**, che deve essere definito per primo.

>[!NOTE]
> Se **Quando si verifica un evento aziendale** è impostato su *Microsoft Power Automate* (piuttosto che su *HTTPS*, ad esempio), **Nome di endpoint** verrà creato automaticamente in Supply Chain Management in base all'impostazione *Microsoft Power Automate*.

### <a name="microsoft-power-automate-example"></a>Esempio Microsoft Power Automate

In questo esempio, l'uso di **Quando si verifica un evento aziendale** con *Microsoft Power Automate* invia e-mail contenenti messaggi InfoLog e collegamenti ipertestuali per aprire la pagina **Messaggi elaboratore messaggi** per un messaggio di errore specifico nella distribuzione hub. Se necessario, è possibile aggiungere ulteriore logica per inviare le notifiche in parallelo utilizzando diversi canali e controllare i destinatari in base ai dati dell'evento.

1. In [Power Automate](https://preview.flow.microsoft.com), crea un nuovo flusso cloud automatizzato per il trigger di flusso **Quando si verifica un evento aziendale - App Fin & Ops (Dynamics 365)** seguito dai passaggi **Analizza JSON** e **Invia un'e-mail**, come mostrato nell'illustrazione seguente.

    :::image type="content" source="./media/cloud-edge-power-automate-example1.png" alt-text="Flusso cloud automatizzato di Power Automate.":::

1. Nel passaggio **Quando si verifica un evento aziendale** puoi cercare o inserire l'**Istanza** hub seguendo la **Categoria** e poi l'**Evento aziendale** *Messaggio elaboratore messaggi elaborato*, come mostrato nell'illustrazione seguente.

    :::image type="content" source="./media/cloud-edge-power-automate-example2.png" alt-text="Passaggio Power Automate Quando si verifica un evento aziendale.":::

1. Per il passaggio **Analizza JSON**, immettere uno **Schema** che definisce i campi estesi. Puoi usare l'opzione *Scarica schema* nella pagina **Catalogo eventi aziendali** in Supply Chain Management o iniziare incollando il testo dello schema di esempio. Questo testo di esempio viene fornito dopo la seguente illustrazione.

    :::image type="content" source="./media/cloud-edge-power-automate-example3.png" alt-text="Passaggio Power Automate Analizza JSON.":::

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

1. Nel passaggio **Invia e-mail**, è possibile selezionare i singoli campi o iniziare incollando l'esempio del corpo dell'email nel campo **Corpo**. Questo esempio viene fornito dopo la seguente illustrazione.

    :::image type="content" source="./media/cloud-edge-power-automate-example4.png" alt-text="Passaggio Power Automate Invia e-mail.":::

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

1. Quando salvi l'evento aziendale, verrà automaticamente attivato e pronto per essere utilizzato come parte di Supply Chain Management.
