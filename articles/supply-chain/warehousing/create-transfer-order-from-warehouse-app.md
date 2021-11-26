---
title: Creare ordini di trasferimento nell'app di magazzino
description: In questo argomento viene descritto come creare ed elaborare ordini di trasferimento nell'app per dispositivi mobili Gestione magazzino
author: perlynne
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 4ceedd8b42383dc1334f472ba754ac3e18261b9d
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/09/2021
ms.locfileid: "7777817"
---
# <a name="create-transfer-orders-from-the-warehouse-app"></a>Creare ordini di trasferimento dall'app di magazzino

[!include [banner](../includes/banner.md)]

Questa funzionalità consente agli addetti al magazzino di creare ed elaborare ordini di trasferimento direttamente nell'app per dispositivi mobili Gestione magazzino. Gli addetti iniziano selezionando il magazzino di destinazione e possono quindi eseguire la scansione di una o più targhe utilizzando l'app per aggiungere le targhe all'ordine di trasferimento. Quando l'addetto al magazzino seleziona **Completa ordine**, un processo batch creerà l'ordine di trasferimento richiesto e le righe dell'ordine in base alle scorte disponibili registrate per tali targhe.

## <a name="enable-the-create-transfer-orders-from-the-warehouse-app-feature"></a><a name="enable-create-transfer-order-from-warehouse-app"></a>Abilitare la funzionalità Crea ordini di trasferimento nell'app di magazzino

Prima di utilizzare questa funzionalità, devi abilitarla nel sistema insieme ai relativi prerequisiti. Gli amministratori possono utilizzare la pagina [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla se necessario.

1. Abilita prima la funzionalità [Elabora eventi dell'app di magazzino](warehouse-app-events.md), elencata in [ Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) come segue:
    - **Modulo**: Gestione magazzino
    - **Nome funzionalità**: Elabora eventi dell'app di magazzino
1. Quindi abilita la funzionalità *Crea ordini di trasferimento nell'app di magazzino*, elencata come segue:
    - **Modulo**: Gestione magazzino
    - **Nome funzionalità** - Crea ed elabora ordini di trasferimento nell'app di magazzino
1. Per automatizzare l'elaborazione delle spedizioni in uscita, devi abilitare anche la funzionalità [Conferma spedizioni in uscita in processi batch](confirm-outbound-shipments-from-batch-jobs.md). A partire dalla versione 10.0.21 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. Gli amministratori possono utilizzare la pagina [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla o disabilitarla se necessario. La funzione viene elencata come:
    - **Modulo**: Gestione magazzino
    - **Nome funzionalità** - Conferma spedizioni in uscita in processi batch

## <a name="set-up-a-mobile-device-menu-item-to-create-transfer-orders"></a><a name="setup-warehouse-app-menu"></a>Impostare una voce di menu di dispositivo mobile per creare ordini di trasferimento

Di seguito sono riportate le linee guida generali per l'impostazione di una voce di menu di dispositivo mobile per la creazione di un ordine di trasferimento. A seconda dei requisiti aziendali per il livello di automazione da impostare quando gli utenti creano ordini di trasferimento nella linea di produzione, verranno abilitate configurazioni differenti. Lo scenario in questo documento descriverà una di queste configurazioni.

1. Passa a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Seleziona **Nuovo** per aggiungere una nuova voce di menu. Quindi effettua le seguenti impostazioni per iniziare:

    - **Nome voce di menu** - Assegna il nome che deve essere visualizzato in Supply Chain Management.
    - **Titolo** - Assegna al menu il nome che sarà visibile ai lavoratori nell'app per dispositivi mobili Gestione magazzino.
    - **Modalità** - Imposta *Indiretta* (questa voce di menu non creerà lavoro).
    - **Codice attività** - Imposta su *Crea ordine di trasferimento da targhe* per consentire agli addetti al magazzino di creare un ordine di trasferimento basato su una o più targhe sottoposte a scansione.

1. Utilizza l'impostazione **Criteri di creazione di righe dell'ordine di trasferimento** per controllare il modo in cui verranno create le righe dell'ordine di trasferimento mediante questa voce di menu. Le righe verranno create/aggiornate in base alle scorte disponibili registrate per le targhe scansionate. Scegli uno dei seguenti valori:

    - **Nessuna prenotazione** - Le righe dell'ordine di trasferimento non saranno prenotate.
    - **Targa guidata con prenotazione riga** - Le righe dell'ordine di trasferimento verranno prenotate e utilizzeranno l'opzione della strategia Targa guidata, che memorizza gli ID targa pertinenti associati alle righe ordine. I valori di ID targa individuata possono pertanto essere utilizzati come parte del processo di creazione del lavoro per le righe dell'ordine di trasferimento.

1. Utilizza l'impostazione **Criteri di spedizione in uscita** per aggiungere più automazione al processo di spedizione dell'ordine di trasferimento in uscita, come necessario. Quando un lavoratore seleziona il pulsante **Completa ordine**, l'app crea l'evento dell'app di magazzino *Completa ordine* che salverà il valore scelto qui nel campo **Criteri di spedizione in uscita** per ogni riga nell'ordine di trasferimento corrente. Successivamente, quando la coda degli eventi viene elaborata da un processo batch per creare l'ordine di trasferimento, il valore memorizzato in questo campo può essere letto dal processo batch e può quindi controllare il modo in cui quel processo elabora ciascuna riga. Sono disponibili le seguenti opzioni:

    - **Nessuna** - Non viene eseguita alcuna elaborazione automatizzata.
    - **Rilascia in magazzino** - Automatizza il processo di rilascio in magazzino.
    - **Conferma spedizione** - Automatizza il processo di conferma della spedizione.
    - **Rilascio e conferma spedizione** - Automatizza i processi di rilascio in magazzino e di conferma della spedizione..

## <a name="add-the-mobile-device-menu-item-to-a-menu"></a>Aggiungere la voce di menu di dispositivo mobile a un menu

1. Accedi a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**
1. Selezionare **Modifica**.
1. Seleziona un menu esistente dopo aver selezionato la nuova voce di menu in **Menu e voci di menu disponibili**. Aggiungi la voce di menu selezionando il pulsante freccia destra.

## <a name="create-a-transfer-order-based-on-license-plates"></a>Creare un ordine di trasferimento basato su targhe

L'app per dispositivi mobili Gestione magazzino include un semplice processo per creare ordini di trasferimento basati su targhe. A tale scopo, il lavoratore esegue quanto segue utilizzando l'app per dispositivi mobili Gestione magazzino:

1. Crea l'ordine di trasferimento e identifica il magazzino di destinazione.
1. Identifica ogni targa da spedire.
1. Seleziona **Completa ordine**.

>[!NOTE]
> È possibile per più lavoratori assegnare targhe destinate allo stesso ordine di trasferimento utilizzando il pulsante **Seleziona ordine di trasferimento** per selezionare un numero di ordine di trasferimento esistente non elaborato nella coda degli eventi dell'app di magazzino. Per informazioni su come trovare i numeri degli ordini di trasferimento, vedi [Richiedere informazioni su eventi dell'app di magazzino](#inquire-the-warehouse-app-events).

## <a name="example-scenario"></a>Scenario di esempio

Questo scenario fornisce una panoramica del processo per ottenere ordini di trasferimento creati ed elaborati automaticamente in base alle scorte disponibili registrate nelle targhe selezionate.

Per eseguire questo scenario utilizzando i valori suggeriti, devi lavorare su un sistema con dati demo installati e selezionare la persona giuridica *USMF* prima di iniziare.

Questo scenario presuppone che siano già state abilitate le funzionalità [Crea ed elabora ordini di trasferimento nell'app di magazzino](#enable-create-transfer-order-from-warehouse-app), e [Elaborazione di eventi dell'app di magazzino](warehouse-app-events.md).

Oltre a impostare la creazione dell'ordine di trasferimento nelle voci di menu di dispositivo mobile, devono essere impostati e abilitati anche modelli aggiuntivi, direttive di ubicazione e processi batch.

### <a name="example-scenario-blueprint"></a>Progetto di uno scenario di esempio

Sei un rivenditore e disponi di più targhe, ciascuna contenente un mix di articoli che si trovano in un'ubicazione specifica in uno dei tuoi magazzini (*Magazzino 51*). Vorresti abilitare il processo che consente ai lavoratori di creare un ordine di trasferimento in un altro magazzino (*Magazzino 61*) per una raccolta di targhe sottoposte a scansione. Spedirai e aggiornerai automaticamente l'ordine di trasferimento non appena sarà stata identificata l'ultima targa dell'ordine.

![Esempio di elaborazione automatizzata dell'ordine di trasferimento.](media/create-transfer-order-from-app-example.png "Esempio di elaborazione automatizzata dell'ordine di trasferimento")

### <a name="create-a-mobile-device-menu-item-for-creating-transfer-orders"></a>Creare una voce di menu di dispositivo mobile per creare ordini di trasferimento

In questa sezione viene descritto come creare una nuova voce di menu di dispositivo mobile per la creazione di ordini di trasferimento. Imposta **Modalità** su *Indiretta* e **Codice attività** su *Crea ordine di trasferimento da targhe*.

1. Passa a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Selezionare **Nuovo**.
1. Nel campo **Nome voce di menu**, immetti il nome *Crea OT*.
1. Nel campo **Titolo**, inserisci la descrizione *Crea OT*.
1. Nel campo **Modalità**, seleziona *Indiretta*.
1. In **Codice attività**, seleziona *Crea ordine di trasferimento da targhe*.
1. In **Criteri di creazione di righe dell'ordine di trasferimento**, seleziona *Targa guidata con prenotazione riga*.
1. In **Criteri di spedizione in uscita**, seleziona *Rilascio e conferma spedizione*.
1. Accedi a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.
1. Seleziona **Modifica**.
1. Seleziona il menu **Scorte** esistente, quindi seleziona la nuova voce di menu in **Menu e voci di menu disponibili**. Aggiungi la voce di menu nel menu **Scorte** selezionando il pulsante freccia destra.

### <a name="set-up-work-templates-to-auto-process-and-break-work-by-located-license-plate"></a>Impostare modelli di lavoro per elaborare automaticamente e suddividere il lavoro per targa individuata

In questa sezione viene descritto come abilitare un modello di lavoro per elaborare automaticamente il lavoro creato dal modello quando viene rilasciato un ciclo.

1. Accedi a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.
1. Nel campo **Tipo ordine di lavoro** seleziona *Uscita di trasferimento*.
1. Seleziona **Nuovo** per creare un nuovo modello di lavoro.
1. Nel campo **Modello di lavoro** immetti *Targa processo automatico 51*.
1. Nel campo **Descrizione modello di lavoro**, inserisci *Targa processo automatico 51*.
1. Seleziona la casella di controllo **Elabora automaticamente**. Questa selezione è necessaria per qualsiasi passaggio di automazione da elaborare.
1. Nei dati demo esiste già un modello di lavoro *Trasferimento 51*, modifica il campo **Numero progressivo** di modo che il nuovo modello di lavoro abbia un numero progressivo inferiore rispetto al modello di lavoro esistente *Trasferimento 51*.
1. Seleziona **Salva** nella barra degli strumenti per abilitare la Scheda dettaglio **Dettagli modello di lavoro**.
1. Nella Scheda dettaglio **Dettagli modello di lavoro**, seleziona **Nuovo** nella barra degli strumenti. Aggiungerai due righe.
1. Nel campo **Tipo di lavoro**, seleziona *Preleva*.
1. Nel campo **ID classe lavoro** seleziona *TransfOut*.
1. Nella barra degli strumenti **Dettagli modello di lavoro**, seleziona **Nuovo**.
1. Nel campo **Tipo di lavoro** seleziona *Inserisci*.
1. Nel campo **ID classe lavoro** seleziona *TransfOut*.
1. Seleziona **Salva** per abilitare il campo **Codice direttiva**.
1. Nella riga **Tipo di lavoro** *Inserisci*, seleziona **Codice direttiva** *Baydoor*. Assicurati che questo nuovo modello di lavoro ottenga il **numero progressivo** più basso.
1. Nella barra degli strumenti, seleziona **Modifica query** per aprire l'editor di query.
1. Nella scheda **Intervallo** seleziona **Aggiungi**.
1. Nella riga aggiunta, in **Campo** seleziona *Magazzino*.
1. Nel campo **Criteri**, seleziona *51*.
1. Seleziona la scheda **Ordinamento**.
1. Seleziona **Aggiungi** e imposta **Campo** su *ID targa individuata*. Selezionando questo campo abiliterai il pulsante della barra degli strumenti **Interruzioni intestazione lavoro**.
1. Seleziona **OK** seguito da **Sì** per ripristinare il raggruppamento e tornare alla pagina **Modelli di lavoro**.
1. Seleziona **Interruzioni intestazione lavoro** e abilita **Raggruppa per questo campo** in **ID targa individuata**, quindi chiudi.

> [!NOTE]
> Non tutte le impostazioni possono essere elaborate automaticamente, ad esempio, gli articoli a peso variabile e l'uso di dimensioni di tracciabilità miste.

### <a name="set-up-location-directives-for-the-license-plate-guided-strategy"></a>Impostare le direttive di ubicazione per la strategia di targa guidata

In questa sezione viene descritto come impostare un processo di prelievo per direttiva di ubicazione per utilizzare la strategia **Targa guidata**.

1. Vai a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Seleziona **Modifica**.
1. Nell'intestazione dell'elenco di navigazione, seleziona **Tipo di ordine di lavoro** *Uscita di trasferimento*.
1. Nell'elenco di navigazione, seleziona la direttiva ubicazione esistente **Prelievo OT 51**.
1. Nella Scheda dettaglio **Righe**, seleziona la casella di controllo **Consenti divisione**.
1. Nella Scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Nuova** per aggiungere una nuova riga di azione.
1. Nel campo **Nome** immetti *Targa guidata*.
1. Nel campo **Strategia** seleziona *Targa guidata*. Questa azione richiede il numero progressivo più basso.
1. Seleziona **Salva** nella barra degli strumenti.
1. Seleziona l'icona di pagina **Aggiorna** nella barra degli strumenti.
1. Nella Scheda dettaglio **Azioni direttiva ubicazione**, seleziona la riga *Prelievo OT*.
1. Nella barra di strumenti **Azioni direttiva ubicazione**, seleziona **Sposta giù** per modificare il numero progressivo di modo che sia maggiore del numero progressivo per l'azione *Targa guidata* appena creata.

> [!NOTE]
> La strategia Targa guidata tenterà di prenotare e creare lavori di prelievo nelle ubicazioni contenenti le targhe richieste che sono state associate alle righe dell'ordine di trasferimento. Ma se ciò non è possibile e desideri comunque creare un lavoro di prelievo, devi eseguire il fallback per un'altra strategia di azione della direttiva di ubicazione e forse anche cercare le scorte in un'altra area del magazzino, a seconda delle esigenze del processo.

### <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Configurare un processo batch per elaborare eventi dell'app di magazzino

In questa sezione viene descritto come impostare un processo batch pianificato per elaborare eventi dell'app di magazzino.

1. Vai a **Gestione magazzino \> Attività periodiche \> Elabora eventi dell'app di magazzino**.
2. Nella finestra di dialogo, abilita **Elaborazione batch** sotto la sezione **Esegui in background**.
3. Seleziona **Ricorrenza** e imposta il processo batch da elaborare in base all'intervallo necessario.
4. Seleziona **OK** per tornare alla finestra di dialogo principale.
5. Seleziona **OK** nella finestra di dialogo principale per aggiungere il processo alla coda batch.

### <a name="set-up-a-batch-job-to-release-transfer-orders-automatically"></a>Impostare un processo batch per rilasciare automaticamente ordini di trasferimento

In questa sezione viene descritto come impostare un processo batch pianificato per rilasciare gli ordini di trasferimento che sono stati contrassegnati come "pronti per il rilascio".

1. Vai a **Gestione magazzino \> Rilascio in magazzino \> Rilascio automatico degli ordini di trasferimento**.
1. Nella finestra di dialogo, espandi la sezione **Record da includere**.
1. Sotto la sezione **Record da includere**, seleziona **Filtra**.
1. Nella pagina della query **WHSTransferAutoRTWQuery**, nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una nuova riga alla query.
1. Nel campo **Tabella** della nuova riga, seleziona il menu a discesa e seleziona la tabella **Rilascio riga di trasferimento in magazzino**.
1. Nel menu a discesa **Campo**, seleziona **Criteri di spedizione in uscita**.
1. Nel campo **Criteri** seleziona **Rilascio e conferma spedizione**.
1. Nella riga dove **Campo** è impostato su *Magazzino origine*, nel campo **Criteri**, seleziona *51*.
1. Seleziona **OK** per tornare alla finestra di dialogo principale.
1. Espandi la sezione **Esegui in background** per configurare l'elaborazione batch.
1. Abilita **Elaborazione batch** sotto la sezione **Esegui in background**.
1. Seleziona **Ricorrenza** e imposta il processo batch da elaborare in base all'intervallo necessario.
1. Seleziona **OK** per tornare alla finestra di dialogo principale.
1. Seleziona **OK** nella finestra di dialogo principale per aggiungere il processo batch alla coda batch.

### <a name="set-up-the-process-outbound-shipment-batch-job"></a>Impostare il processo batch "Elabora spedizioni in uscita"

In questa sezione viene descritto come impostare un processo batch pianificato per eseguire la conferma della spedizione in uscita per i carichi pronti per la spedizione correlati alle righe dell'ordine di trasferimento che sono "pronte per la spedizione".

1. Vai a **Gestione magazzino \> Attività periodiche \> Elaborazione spedizioni in uscita**.
1. Espandi la sezione **Record da includere**.
1. Seleziona **Filtro**.
1. Nella query **WHSLoadShipConfirm**, seleziona la scheda **Join**.
1. Espandi la gerarchia della tabella di modo che **Carichi** e **Dettagli carico** siano stati espansi.
1. Seleziona la scheda **Dettagli carico**.
1. Seleziona il pulsante **Aggiungi tabella join**.
1. Nell'elenco delle relazioni di tabella, filtra o cerca nella colonna **Relazione** per *Righe ordine di trasferimento (riferimento)*.
1. Concentrati sulla relazione di tabella nell'elenco, quindi premi il tasto **Seleziona**.
1. Seleziona la tabella **Righe ordine di trasferimento**.
1. Seleziona il pulsante **Aggiungi tabella join**.
1. Nell'elenco delle relazioni di tabella, nella colonna **Relazione** filtra o cerca *Campi aggiuntivi trasferimento scorte (ID record)*.
1. Concentrati sulla relazione di tabella nell'elenco, quindi premi il tasto **Seleziona**.
1. Seleziona la scheda **Intervallo**.
1. Nelle tabelle di query **Intervallo**, imposterai tre intervalli di criteri di query. Seleziona il pulsante **Aggiungi** per aggiungere una riga.
1. Aggiungi un intervallo per la tabella **Carichi**. Imposta **Campo** su *Stato carico* e imposta **Criteri** su *Caricato*.
1. Aggiungi un altro intervallo per la tabella **Campi aggiuntivi trasferimento scorte**. Imposta **Campo** su *Criteri di spedizione in uscita* e imposta **Criteri** su *Rilascio e conferma spedizione*.
1. Aggiungi un altro intervallo per la tabella **Dettagli carico**. Imposta **Campo** su *Riferimento* e imposta **Criteri** su *Spedizione ordine di trasferimento*.
1. Seleziona **OK** per tornare alla finestra di dialogo principale.
1. Espandi la sezione **Esecuzione in background**.
1. Abilita **Elaborazione batch**.
1. Seleziona **Ricorrenza** e imposta il processo batch da elaborare in base all'intervallo necessario.
1. Seleziona **OK** per tornare alla finestra di dialogo principale.
1. Seleziona **OK** nella finestra di dialogo principale per aggiungere il processo batch alla coda batch.

> [!NOTE]
> Per ulteriori informazioni, vedi [Confermare spedizioni in uscita in processi batch](confirm-outbound-shipments-from-batch-jobs.md).

## <a name="processing-the-example-for-create-transfer-order-from-the-warehouse-app"></a>Elaborazione dell'esempio per "Crea ordine di trasferimento dall'app di magazzino"

### <a name="add-on-hand-on-a-license-plate"></a>Aggiungere scorte disponibili in una targa

Come punto di partenza per questo scenario, dovrai avere una targa contenente scorte fisiche disponibili.

| Articolo | Magazzino | Stato inventario | Posizione | Targa | Quantità |
| --- | --- | --- | --- | --- | --- |
| A0001 | 51 | Disponibile | LP-010 | LP10 | 1 |
| A0002 | 51 | Disponibile | LP-010 | LP10 | 2 |

Aggiungi quantità di scorte fisiche disponibili utilizzando i seguenti valori:

> [!NOTE]
> Dovrai creare la targa e utilizzare ubicazioni che ti consentano di trasportare articoli misti, come LP-010.

### <a name="create-and-process-transfer-orders-from-the-warehouse-app"></a>Creare ed elaborare ordini di trasferimento dall'app di magazzino

1. Apri l'app e accedi come utente *51*. L'attuale magazzino utente sarà 51.
1. Seleziona la voce di menu **Crea OT** nella posizione a cui è stata aggiunta durante la configurazione.
1. Avvia la creazione di un ordine di trasferimento inserendo *61* per il magazzino di destinazione (Magazzino destinazione) nel campo **Magazzino**. Il nuovo ordine di trasferimento passerà dal magazzino attuale 51 (Magazzino origine) al magazzino di destinazione *61*.
1. Seleziona **OK**.
1. Esegui la scansiona di una ID targa nel campo **Targa**. Inserisci la targa delle scorte aggiunte in un passaggio precedente, *LP10*.
1. Seleziona **OK**.
1. Seleziona il pulsante del menu, quindi seleziona **Completa ordine** per finalizzare la creazione dell'ordine di trasferimento dell'app di magazzino.

Per l'esempio citato, sono utilizzati due **eventi dell'app di magazzino** (*Crea ordine di trasferimento* e *Completa ordine di trasferimento*).

### <a name="inquire-the-warehouse-app-events"></a><a name="#inquire-the-warehouse-app-events"></a>Richiedere informazioni su eventi dell'app di magazzino

Puoi visualizzare la coda degli eventi e i messaggi di eventi generati dall'app per dispositivi mobili Gestione magazzino selezionando **Gestione magazzino \> Richieste di informazioni e report \> Log dispositivo mobile \> Eventi dell'app di magazzino**.

I messaggi dell'evento *Crea ordine di trasferimento* avranno lo stato *In attesa*, il che significa che il processo batch **Elabora eventi dell'app di magazzino** non preleverà ed elaborerà i messaggi di evento. Non appena lo stato del messaggio dell'evento diventa *In coda*, il processo batch elaborerà gli eventi. Ciò avverrà contemporaneamente alla creazione dell'evento *Completa ordine di trasferimento* (quando un lavoratore seleziona il pulsante **Completa ordine** nell'app per dispositivi mobili Gestione magazzino). Dopo che i messaggi dell'evento *Crea ordine di trasferimento* sono stati elaborati, lo stato diventa *Completato* o *Non riuscito*. Quando lo stato di *Completa ordine di trasferimento* diventa *Completato*, tutti gli eventi correlati vengono eliminati dalla coda.

Poiché gli **eventi dell'app di magazzino** per la creazione dei dati dell'ordine di trasferimento non verranno elaborati dal processo batch prima che lo stato dei messaggi diventi *In coda*, dovrai cercare i numeri dell'ordine di trasferimento richiesti nel campo **Identificatore**. Il campo **Identificatore** si trova nell'intestazione della pagina **Eventi dell'app di magazzino**.

Come parte dell'elaborazione degli eventi di magazzino, la creazione della riga dell'ordine di trasferimento potrebbe non riuscire. In tal caso, lo stato del messaggio di evento diventa *Non riuscito* e puoi utilizzare le informazioni in **Registro del processo batch** per conoscere il motivo dell'errore e agire per correggere eventuali problemi.

I problemi tipici possono essere correlati a una configurazione mancante per il processo, come un magazzino di transito mancante per l'evento *Crea ordine di trasferimento*. In un esempio simile, aggiungeresti un magazzino di transito al magazzino di spedizione e useresti l'opzione **Ripristina** per modificare lo stato di tutti i messaggi di evento dell'app di magazzino da *Non riuscito* a *In coda*, il che significa che il processo batch elaborerà nuovamente i messaggi di evento dopo la correzione dei dati di configurazione.

Negli ambienti di produzione, le eccezioni sarebbero più correlate al processo, ad esempio avere una targa richiesta, che al momento dell'elaborazione del processo batch è vuota e quindi non vengono create righe dell'ordine di trasferimento. Questo messaggio di evento non riuscito può essere rimosso utilizzando l'opzione **Elimina** oppure puoi aggiungere la disponibilità fisica nella targa e utilizzare l'opzione **Ripristina** per tutti i messaggi di evento correlati.

Per ulteriori informazioni, vedi [Elaborazione di eventi dell'app di magazzino](warehouse-app-events.md).

### <a name="follow-up-on-the-example-scenario-processing"></a>Informazioni sull'elaborazione dello scenario di esempio

Nel corso di questo scenario, si è verificato quanto segue:

1. Utilizzando l'app per dispositivi mobili Gestione magazzino, hai selezionato una voce di menu che utilizza il codice attività **Crea ordine di trasferimento da targhe**.
1. L'app ti richiede di selezionare il magazzino di destinazione per l'ordine di trasferimento. Il magazzino di origine è sempre quello a cui hai attualmente accesso come Lavoratore.
1. Nella selezione del magazzino di destinazione, il sistema ha riservato un numero ID per l'ordine di trasferimento imminente (in base alla sequenza numerica dell'ordine di trasferimento definita nel sistema) ma non ha ancora creato l'ordine di trasferimento.
1. Quando hai eseguito la scansione della targa *LP10* contenente le scorte disponibili che devono essere spostate nel nuovo magazzino, un **evento dell'app di magazzino** è stato aggiunto alla coda degli eventi per essere elaborato in seguito. L'evento di magazzino conteneva i dettagli del messaggio sulla scansione, incluso il numero dell'ordine di trasferimento previsto.
1. Nell'app per dispositivi mobili Gestione magazzino quando il pulsante **Completa ordine** è selezionato, un nuovo evento dell'app di magazzino, **Completa ordine di trasferimento**, viene creato e lo stato dell'evento esistente correlato, **Crea ordine di trasferimento**, diventa **In coda**.
1. Nel back-end, il **processo batch Elabora eventi dell'app di magazzino** ha prelevato l'evento **In coda** e raccolto le scorte disponibili correlate alla targa sottoposta a scansione. In base alle disponibilità, sono stati creati il record dell'ordine di trasferimento effettivo e le righe associate. Il processo ha anche popolato il campo **Criteri di spedizione in uscita** per l'ordine di trasferimento in base al valore configurato di *Rilascio e conferma spedizione* e collegato la targa alle righe per la strategia **Targa guidata**.
1. In base al valore del campo **Criteri di spedizione in uscita** della riga dell'ordine di trasferimento, la query **Processo batch Rilascio automatico degli ordini di trasferimento** ha generato il rilascio dell'ordine di trasferimento al magazzino di spedizione. Inoltre, per via della configurazione dei campi **Modello ondata**, **Modello di lavoro** e **Direttive ubicazione** utilizzati, per il lavoro sono stati generati processi automatici a seguito dei quali lo **stato del carico** è diventato *Caricato*.
1. Il **processo batch Elabora spedizioni in uscita** viene eseguito per il carico, determinando la spedizione dell'ordine di trasferimento e la generazione di un avviso ASN (Advance Shipment Notice).
1. La tempistica di tutti questi eventi dipende dalle impostazioni di **Ricorrenza** per i processi batch creati.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="mobile-device-menu-item-setup"></a>Configurazione di una voce di menu di dispositivo mobile

#### <a name="why-cant-i-see-create-transfer-order-from-license-plate-in-the-menu-item-work-activity-drop-down-list"></a>Perché non riesco a visualizzare "Crea ordine di trasferimento da targhe" nell'elenco a discesa delle attività di lavoro della voce di menu?

La funzionalità *Crea ed elabora ordini di trasferimento nell'app di magazzino* deve essere abilitata. Per ulteriori informazioni, vedi [Abilitare la funzionalità Crea ordini di trasferimento nell'app di magazzino](#enable-create-transfer-order-from-warehouse-app).

### <a name="warehouse-management-mobile-app-processes"></a>Processi dell'app per dispositivi mobili Gestione magazzino

#### <a name="why-cant-i-see-the-menu-button-complete-order"></a>Perché il pulsante di menu "Completa ordine"?

Devi avere almeno una targa assegnata all'ordine di trasferimento.

#### <a name="can-several-warehouse-management-mobile-app-users-add-license-plates-to-the-same-transfer-order-at-the-same-time"></a>Più utenti dell'app per dispositivi mobili Gestione magazzino possono aggiungere contemporaneamente targhe allo stesso ordine di trasferimento?

Sì, più addetti al magazzino possono eseguire la scansione di targhe nello stesso ordine di trasferimento.

#### <a name="can-the-same-license-plate-be-added-to-different-transfer-orders"></a>È possibile aggiungere la stessa targa a ordini di trasferimento differenti?

No, una targa può essere aggiunta solo a un ordine di trasferimento alla volta.

#### <a name="after-having-selected-the-complete-order-button-can-i-then-add-more-license-plates-for-that-transfer-order"></a>Dopo aver selezionato il pulsante "Completa ordine", posso aggiungere più targhe per quell'ordine di trasferimento?

No, non puoi aggiungere più targhe a un ordine di trasferimento con un evento di app di magazzino **Completa ordine di trasferimento**.

#### <a name="how-can-i-find-existing-transfer-orders-to-be-used-via-the-select-transfer-order-button-in-the-warehouse-management-mobile-app-if-the-order-has-not-yet-been-created-in-the-backend-system"></a>Come posso trovare ordini di trasferimento esistenti da utilizzare mediante il pulsante "Seleziona ordine di trasferimento" nell'app per dispositivi mobili Gestione magazzino se l'ordine non è stato ancora creato nel sistema back-end?

Al momento non puoi cercare ordini di trasferimento nell'app, ma puoi trovare i numeri degli ordini di trasferimento nella pagina **Eventi dell'app di magazzino**. Per ulteriori informazioni, vedi [Richiedere informazioni su eventi dell'app di magazzino](#inquire-the-warehouse-app-events).

#### <a name="can-i-manually-select-the-transfer-order-number-to-be-used-from-the-warehouse-management-mobile-app"></a>Posso selezionare manualmente il numero dell'ordine di trasferimento da utilizzare nell'app per dispositivi mobili Gestione magazzino?

Sono supportati solo i numeri di ordine di trasferimento generati automaticamente tramite sequenze numeriche.

### <a name="background-processing"></a>Elaborazione in background

#### <a name="how-should-i-clean-up-records-in-my-warehouse-app-events-queue-message-tables"></a>Come devo pulire i record nelle tabelle dei messaggi della coda degli eventi dell'app di magazzino?

Puoi visualizzarli nella pagina **Eventi dell'app di magazzino** e quindi eseguire l'operazione di pulizia. Per ulteriori informazioni, vedi [Richiedere informazioni su eventi dell'app di magazzino](#inquire-the-warehouse-app-events).

#### <a name="why-is-the-transfer-order-receipt-date-not-updated-according-to-my-delivery-date-control-setup"></a>Perché la "Data di ricevimento" dell'ordine di trasferimento non viene aggiornata in base all'impostazione "Controllo data di consegna"?

Gli ordini di trasferimento vengono creati senza utilizzare **Controllo data di consegna**.

#### <a name="can-i-use-a-license-plate-having-physical-negative-inventory-on-hand"></a>Posso usare una targa con scorte fisiche disponibili negative?

La funzionalità supporta solo quantità fisiche disponibili positive a livello di targa, ma è possibile avere quantità disponibili fisiche negative a livello di magazzino e inventario superiori quando si assegnano le targhe agli ordini di trasferimento.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]