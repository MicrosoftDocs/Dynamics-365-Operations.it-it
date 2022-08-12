---
title: Notifiche di esecuzione ciclo
description: Questo articolo descrive le notifiche di esecuzione ciclo e spiega come configurarle.
author: Mirzaab
ms.date: 04/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WhsWaveNotificationPolicy, WHSParameters, WHSWaveTemplateTable, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 5c8fa259e51f024d19c1f2f7e84ed7edd0ddb7e1
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9069030"
---
# <a name="wave-execution-notifications"></a>Notifiche di esecuzione ciclo

[!include [banner](../includes/banner.md)]

La funzionalità *Notifiche di esecuzione ciclo* utilizza eventi aziendali e il Centro azioni per inviare notifiche relative all'esecuzione del ciclo. Consente di specificare i tipi di eventi che generano notifiche, i magazzini che li generano e gli utenti che li ricevono.

Il pulsante **Mostra messaggi** (simbolo della campana) sul lato destro della barra di spostamento indica quando un messaggio del centro azioni è disponibile per l'utente corrente. L'utente può selezionare il pulsante **Mostra messaggi** per aprire il Centro azioni e rivedere i messaggi.

Gli eventi aziendali si verificano quando vengono eseguiti i processi aziendali. I processi aziendali sono costituiti da attività. Durante un processo aziendale, gli utenti che vi partecipano eseguono azioni aziendali per completare tali attività. Gli eventi aziendali forniscono un meccanismo che consente ai sistemi esterni di ricevere notifiche dalle app per la finanza e le operazioni. In questo modo, i sistemi possono eseguire azioni aziendali in risposta agli eventi aziendali. Per ulteriori informazioni, vedi [Panoramica eventi aziendali](../../fin-ops-core/dev-itpro/business-events/home-page.md).

## <a name="turn-the-wave-execution-notifications-feature-on-or-off"></a>Attivare o disattivare la funzionalità Notifiche di esecuzione ciclo

A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. Gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Notifiche di esecuzione ciclo* nell'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="scenario-send-wave-batch-execution-notifications-to-the-action-center"></a>Scenario: inviare notifiche di esecuzione batch ciclo al centro azioni

Questo scenario mostra il flusso end-to-end per l'invio di notifiche sugli errori di esecuzione del batch ciclo a un ruolo specifico tramite il centro azioni.

### <a name="make-demo-data-available"></a>Rendi disponibili i dati dimostrativi

Per eseguire questo scenario, i dati dimostrativi devono essere installati ed è necessario selezionare la persona giuridica **USMF**.

### <a name="make-sure-that-waves-are-run-in-batch-mode"></a>Assicurarsi che i cicli vengano eseguiti in modalità batch

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.
1. Nella Scheda dettaglio **Elaborazione ciclo**, imposta l'opzione **Elabora cicli in batch** su *Sì*.

> [!NOTE]
> Se desideri disabilitare le notifiche di esecuzione del batch ciclo, imposta l'opzione **Disabilita notifiche batch di elaborazione ciclo** su *Sì*.

### <a name="configure-a-wave-notification-policy"></a>Configurare un criterio di notifica ciclo

I criteri di notifica ciclo definiscono i tipi di notifiche che vengono inviate e gli utenti a cui viene inviata la notifica.

1. Vai a **Gestione magazzino \> Impostazione \> Cicli \> Criteri di notifica ciclo**.
1. Crea un record con le seguenti impostazioni:

    - **Criterio di notifica ciclo:** *24BatchError*
    - **Descrizione:** *Errore batch ciclo magazzino 24*
    - **Invia notifica su:** *Solo errore*
    - **A ruolo:** *Amministratore di sistema*

        > [!NOTE]
        > Poiché questo scenario utilizza dati demo, il ruolo *Amministratore di sistema* è selezionato per motivi di semplicità. Pertanto, poiché hai effettuato l'accesso come utente amministratore di sistema, riceverai le notifiche. Tuttavia, in pratica, dovresti solitamente selezionare un ruolo più specifico per notificare gli errori di esecuzione del batch ciclo, come *Responsabile del magazzino*.

1. Nel riquadro azioni selezionare **Salva**.

### <a name="configure-a-wave-template"></a>Configurare un modello di ondata

I modelli di ciclo consentono di collegare istanze specifiche dei metodi di ciclo ai modelli di etichetta ciclo corrispondenti.

1. Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.
1. Nel riquadro elenco, imposta il campo **Tipo di modello ciclo** su *Spedizione*, quindi seleziona il modello ciclo *Spedizione predefinita 24* per il magazzino 24.
1. Nella Scheda dettaglio **Generale**, imposta il campo **Criterio di notifica ciclo** su *24BatchError*.

### <a name="configure-a-work-template"></a>Configurare un modello di lavoro

I modelli di lavoro vengono utilizzati durante l'esecuzione del ciclo per generare il lavoro. Per questo scenario, l'esecuzione del ciclo dovrebbe attivare un errore. Impostando la query del modello di lavoro per utilizzare un magazzino inesistente, ti assicureri che l'esecuzione del ciclo non riesca e quindi invii una notifica.

1. Accedi a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.
1. Nel riquadro elenco, imposta il campo **Tipo di modello lavoro** su *Ordini cliente*, quindi seleziona il modello di lavoro *Fase ordine cliente 24* per il magazzino 24.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo** modifica la seguente riga (o aggiungila se non esiste):

    - **Tabella:** *Transazioni lavoro temporanee*
    - **Tabella derivata:** *Transazioni lavoro temporanee*
    - **Campo:** *Magazzino*
    - **Criteri:** Modifica il valore da *24* in *Errore*.

1. Seleziona **OK** e conferma la modifica.

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Creare un ordine cliente e rilasciarlo nel magazzino

1. Andare a **Vendite e marketing \> Ordine cliente \> Tutti gli ordini cliente**.
1. Crea un ordine cliente con le seguenti impostazioni:

    - **Conto cliente:** *US-001*
    - **Magazzino:** *24*

1. Nella Scheda dettaglio **Righe ordine cliente**, aggiungi una riga ordine cliente che abbia le seguenti impostazioni:

    - **Numero articolo:** *A0001*
    - **Quantità:** *10*

    > [!NOTE]
    > Questi articoli e quantità sono solo esempi. Il magazzino specificato deve contenere scorte sufficienti.

1. Mentre la nuova riga ordine è ancora selezionata nella Scheda dettaglio **Righe ordine cliente**, seleziona **Inventario \> Prenotazione** nella barra degli strumenti.
1. Nella pagina **Prenotazione**, nel riquadro azioni, seleziona **Prenota lotto**. Quindi, chiudere la pagina.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.

### <a name="notifications-from-wave-batch-job-execution"></a>Notifiche dell'esecuzione di lavori batch ciclo

A seconda della configurazione dei tuoi eventi aziendali, alla fine riceverai una notifica sull'errore di esecuzione del ciclo. Il messaggio del centro azioni sarà simile al seguente esempio e includerà un collegamento al ciclo che ha avuto esito negativo.

> **Errore durante l'esecuzione del ciclo**  
> Si è verificato un errore durante l'esecuzione del ciclo USMF-000000001.  
> Ultimi messaggi: Nessun lavoro è stato creato per il ciclo USMF-000000001.
>
> **STATO**  
> Attive
>
> Apri dettagli ciclo

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

