---
title: App Visibilità inventario
description: Questo articolo descrive come utilizzare l'applicazione Visibilità inventario.
author: yufeihuang
ms.date: 09/15/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 0a4e436cc1af6b71049f75fb66bdfb89ca38df9f
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831776"
---
# <a name="use-the-inventory-visibility-app"></a>Utilizzare l'app Visibilità inventario

[!include [banner](../includes/banner.md)]

Questo articolo descrive come utilizzare l'applicazione Visibilità inventario.

Visibilità inventario fornisce un'applicazione guidata dal modello per la visualizzazione. L'applicazione contiene tre pagine: **Configurazione**, **Visibilità operativa** e **Riepilogo inventario**. Ha le seguenti caratteristiche:

- Fornisce un'interfaccia utente (UI) per la configurazione on-hand e la configurazione soft reservation.
- Supporta le interrogazioni in tempo reale dell'inventario su varie combinazioni di dimensioni.
- Fornisce un'interfaccia utente per pubblicare le richieste di prenotazione.
- Fornisce una visualizzazione dell'inventario a disposizione dei prodotti insieme a tutte le dimensioni.
- Fornisce una visualizzazione delle scorte disponibili dei prodotti insieme a tutte le dimensioni predefinite. La visualizzazione dell'elenco delle disponibilità può essere un riepilogo completo o un risultato precaricato di una query delle disponibilità.

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, installare e configurare il componente aggiuntivo Visibilità inventario come descritto in [Installare e configurare Visibilità inventario](inventory-visibility-setup.md).

## <a name="open-and-authenticate-the-inventory-visibility-app"></a><a name="open-authenticate"></a>Apri e autentica l'app Visibilità inventario

Per aprire e autenticare l'app Visibilità inventario, segui questi passaggi.

1. Accedi al tuo ambiente Power Apps.
1. Apri l'app **Visibilità inventario**.
1. Apri la pagina **Visibilità operativa** dal riquadro di sinistra.
1. Selezionare il pulsante **Impostazioni** (simbolo dell'ingranaggio) nella parte superiore della pagina.
1. Nella finestra di dialogo **Impostazioni**, immetti i valori **ID client**, **ID tenant** e **Segreto client** che hai annotato quando hai [installato e configurato Visibilità inventario](inventory-visibility-setup.md).
1. Seleziona il pulsante **Aggiorna** accanto al campo **Token di connessione**. Il sistema genera un nuovo token di connessione, in base alle informazioni che hai inserito.

    ![Impostazioni della query di disponibilità.](media/inventory-visibility-query-settings.png "Impostazioni della query a portata di mano")

1. Quando ricevi un token di connessione, chiudi la finestra di dialogo. Il token di connessione scadrà dopo qualche tempo. Pertanto, è necessario aggiornarlo occasionalmente quando è necessario aggiornare la configurazione, registrare dati o eseguire query sui dati.

## <a name="configure-the-inventory-visibility-app"></a><a name="configuration"></a>Configurare l'app Visibilità magazzino

La pagina **Configurazione** dell'app Visibilità inventario aiuta a configurare la configurazione di gestione dei dati generali e la configurazione delle funzionalità. Dopo l'installazione del componente aggiuntivo, la configurazione predefinita include un'impostazione predefinita per Microsoft Dynamics 365 Supply Chain Management (l'origine dati `fno`). Potete rivedere l'impostazione predefinita. In seguito, in base alle esigenze aziendali e ai requisiti di registrazione dell'inventario del sistema esterno, è possibile modificare la configurazione per standardizzare il modo in cui le modifiche all'inventario possono essere registrate, organizzate e interrogate su più sistemi.

Per i dettagli completi su come configurare la soluzione, vedere [Configurare Visibilità inventario](inventory-visibility-configuration.md).

## <a name="operational-visibility"></a>Visibilità operativa

La pagina di **Visibilità operativa** fornisce i risultati di una query sulle scorte disponibili in tempo reale, la registrazione della prenotazione e l'allocazione basata su varie combinazioni di dimensioni. Quando la funzione *OnHandReservation* è [attivata](inventory-visibility-configuration.md), puoi anche inviare richieste di prenotazione dalla pagina **Visibilità operativa**.

### <a name="on-hand-query"></a>Interrogazione a portata di mano

La scheda **Query disponibilità** della pagina **Visibilità operativa** consente di eseguire query sulla disponibilità di scorte in tempo reale. Segui questi passaggi per configurare ed eseguire una query.

1. Apri l'app **Visibilità inventario**.
1. Apri la pagina **Visibilità operativa** dal riquadro di sinistra.
1. Nella scheda **Query disponibilità**, immetti i valori **ID organizzazione**, **ID sito** e **ID posizione** su cui vuoi eseguire query.
1. Nel campo **ID prodotto**, inserisci uno o più ID prodotto per ottenere una corrispondenza esatta per la tua query. Se lasci vuoto il campo **ID prodotto**, i risultati includeranno tutti i prodotti nel sito e nella posizione specificati.
1. Per ottenere un risultato più granulare (ad esempio, una visualizzazione per valori di dimensione come colore e dimensione), seleziona il raggruppamento per dimensioni nel campo **Raggruppa risultati per**.
1. Per trovare gli elementi che hanno un valore di dimensione specifico (come colore = rosso), seleziona la dimensione nel campo **Dimensioni filtro** e quindi immetti un valore di dimensione.
1. Seleziona **Query**. Riceverai un messaggio di operazione completata (verde) o non riuscita (rosso). Se la query ha esito negativo, controlla i criteri della query e assicurati che il tuo [token di connessione](#open-authenticate) non sia scaduto.

Un altro modo per effettuare una query sulle scorte disponibili consiste nell'effettuare richieste API dirette. Puoi usare entrambi `/api/environment/{environmentId}/onhand/indexquery` o `/api/environment/{environmentId}/onhand`. Per maggiori informazioni, vedi [API pubbliche di Visibilità inventario](inventory-visibility-api.md).

### <a name="reservation-posting"></a>Prenotazione

Usa la scheda **Prenotazione** della pagina **Visibilità operativa** per pubblicare una richiesta di prenotazione. Prima di poter pubblicare una richiesta di prenotazione, devi attivare la funzione *OnHandReservation* . Per ulteriori informazioni su questa funzione e come attivarla, vedi [Prenotazioni di Visibilità inventario](inventory-visibility-reservations.md).

> [!NOTE]
> La possibilità di effettuare una prenotazione temporanea tramite l'interfaccia utente ha lo scopo di consentire il test della funzionalità. Ogni richiesta di prenotazione temporanea deve essere associata a una modifica della riga dell'ordine di transazione (creazione, modifica, eliminazione e così via). Pertanto, è consigliabile effettuare solo prenotazioni temporanee collegate a un ordine back-end. Per maggiori informazioni, vedere [Prenotazioni di Visibilità inventario](inventory-visibility-reservations.md).

Segui questi passaggi per inviare una richiesta di prenotazione temporanea utilizzando l'interfaccia utente.

1. Apri l'app **Visibilità inventario**.
1. Apri la pagina **Visibilità operativa** dal riquadro di sinistra.
1. Nella scheda **Prenotazione**, nel campo **Quantità**, specifica la quantità che vuoi prenotare.
1. Seleziona la casella di controllo **Attiva l'inventario negativo per supportare l'overselling** per evitare che lo stock venga venduto in eccesso o prenotato in eccesso.
1. Nel campo **Operatore** seleziona l'origine dati e la misura fisica che si applicano alla quantità con prenotazione temporanea.
1. Immetti i valori **ID organizzazione**, **ID sito**, **ID posizione** e **ID prodotto** su cui vuoi eseguire query.
1. Per ottenere un risultato più granulare, seleziona un'origine dati, le dimensioni e i valori delle dimensioni.

Un altro modo per registrare una prenotazione temporanea consiste nell'effettuare richieste API dirette. Usate il modello che è descritto in [Creare un evento di prenotazione](inventory-visibility-api.md#create-one-reservation-event). Poi seleziona **Registra**. Per visualizzare i dettagli della risposta alla richiesta, selezionare **Mostra dettagli**. È possibile anche ottenere il valore `reservationId` dai dettagli della risposta.

### <a name="allocation"></a>Allocazione

Per informazioni su come gestire le allocazioni dall'interfaccia utente e dalle API, vedere [Allocazione delle scorte in Visibilità inventario](inventory-visibility-allocation.md).

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Riepilogo dell'inventario

La pagina **Riepilogo inventario** fornisce un riepilogo dell'inventario per i prodotti insieme a tutte le dimensioni. Il riepilogo è una vista personalizzata per l'entità *Somma inventario disponibile*. I dati del riepilogo dell'inventario vengono sincronizzati periodicamente da Visibilità inventario.

Per abilitare la pagina **Riepilogo inventario** e impostare la frequenza di sincronizzazione, procedi come segue:

1. Aprire la pagina di **configurazione** .
1. Apri la scheda **Gestione funzionalità e impostazioni**.
1. Imposta l'interruttore della funzionalità *OnHandMostSpecificBackgroundService* su *Sì*.
1. Quando la funzionalità è abilitata, la sezione **Configurazione servizio** diventa disponibile e include una riga per la configurazione della funzionalità **OnHandMostSpecificBackgroundService**. Questa impostazione ti consente di scegliere la frequenza con cui i dati del riepilogo dell'inventario vengono sincronizzati. Utilizza i pulsanti **Su** e **Giù** nella colonna **Valore** per modificare l'intervallo di tempo tra le sincronizzazioni (che può arrivare fino a 5 minuti). Quindi selezionare **Salva**.

    ![Impostazione OnHandMostSpecificBackgroundService](media/inventory-visibility-ohms-freq.png "Impostazione OnHandMostSpecificBackgroundService")

1. Seleziona **Aggiorna configurazione** per salvare tutte le modifiche.

> [!NOTE]
> La funzionalità *OnHandMostSpecificBackgroundService* tiene traccia solo delle modifiche delle scorte disponibili che si sono verificate dopo l'attivazione della funzione. I dati per i prodotti che non sono cambiati da quando hai attivato la funzione non verranno sincronizzati dalla cache del servizio di inventario nell'ambiente Dataverse. Se la pagina **Riepilogo inventario** non mostra tutte le informazioni disponibili che ti aspetti, apri Supply Chain Management, vai a **Gestione inventario > Attività periodiche > Integrazione Visibilità inventario**, disabilita il processo batch e riattivalo. Questo eseguirà il push iniziale e tutti i dati verranno sincronizzati con l'entità *Somma scorte disponibili* nei prossimi 15 minuti. Se desideri utilizzare la funzione *OnHandMostSpecificBackgroundService*, ti consigliamo di attivarla prima di creare eventuali modifiche alle scorte disponibili e di abilitare il processo batch **Integrazione Visibilità inventario**.

## <a name="preload-a-streamlined-on-hand-query"></a><a name="preload-streamlined-onhand-query"></a>Precaricare una query di scorte disponibili ottimizzata

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: Preview until further notice -->

Supply Chain Management memorizza una grande quantità di informazioni sulle attuali scorte disponibili e le rende disponibili per un'ampia varietà di scopi. Tuttavia, molte operazioni quotidiane e integrazioni di terze parti richiedono solo un piccolo sottoinsieme di questi dettagli e la query del sistema per tutte le informazioni può comportare set di dati di grandi dimensioni che richiedono tempo per l'assemblaggio e il trasferimento. Pertanto, il servizio di visibilità dell'inventario può recuperare e archiviare periodicamente un set semplificato di dati di scorte disponibili per rendere continuamente disponibili tali informazioni ottimizzate. I dettagli delle scorte disponibili archiviati vengono filtrati in base a criteri aziendali configurabili per garantire che siano incluse solo le informazioni più rilevanti. Poiché gli elenchi di scorte disponibili filtrati sono archiviati localmente nel servizio di visibilità inventario e vengono aggiornati regolarmente, supportano l'accesso rapido, l'esportazione dei dati su richiesta e l'integrazione semplificata con i sistemi esterni.

La pagina **Precarica il riepilogo di visibilità inventario** fornisce una vista per l'entità *Risultati di precaricamento delle query sull'indice di disponibilità*. Diversamente dall'entità *Riepilogo inventario*, l'entità *Risultati di precaricamento delle query sull'indice di disponibilità* fornisce un elenco di scorte disponibili per i prodotti insieme alle dimensioni selezionate. La visibilità inventario sincronizza i dati di riepilogo precaricati ogni 15 minuti.

Per visualizzare i dati nella scheda **Precarica il riepilogo di visibilità inventario**, devi attivare e configurare la funzionalità *OnHandIndexQueryPreloadBackgroundService*. Vedi [Attivare e configurare le query sulle scorte precaricate](inventory-visibility-configuration.md#query-preload-configuration) per le istruzioni.

> [!NOTE]
> Come con la funzione *OnHandMostSpecificBackgroundService*, la funzione *OnHandIndexQueryPreloadBackgroundService* tiene traccia solo delle modifiche all'inventario disponibili che si sono verificate dopo l'attivazione della funzione. I dati per i prodotti che non sono cambiati da quando hai attivato la funzione non verranno sincronizzati dalla cache del servizio di inventario nell'ambiente Dataverse. Se la pagina **Riepilogo inventario** non mostra tutte le informazioni disponibili che ti aspetti, vai a **Gestione inventario > Attività periodiche > Integrazione Visibilità inventario**, disabilita il processo batch e riattivalo. Questo eseguirà il push iniziale e tutti i dati verranno sincronizzati con l'entità *Risultati di precaricamento delle query sull'indice di disponibilità* nei prossimi 15 minuti. Se desideri utilizzare questa funzione, ti consigliamo di attivarla prima di creare eventuali modifiche alle scorte disponibili e di abilitare il processo batch **Integrazione Visibilità inventario**.

## <a name="filter-and-browse-the-inventory-summaries"></a><a name="additional-tip-for-viewing-data"></a>Filtrare e sfogliare i riepiloghi dell'inventario

Utilizzando il **filtro avanzato** che Dataverse fornisce, è possibile creare una vista personale che mostra le righe importanti per l'utente. Le opzioni di filtro avanzate ti permettono di creare una vasta gamma di visualizzazioni, dalle più semplici alle più complesse. Permettono anche di aggiungere condizioni raggruppate e annidate ai filtri. Per ulteriori informazioni su come utilizzare il filtro avanzato, vedi [Modificare o creare viste personali usando i filtri avanzati della griglia](/powerapps/user/grid-filters-advanced).

La pagina **Riepilogo inventario** fornisce tre campi sopra la griglia (**Dimensione predefinita**, **Dimensione personalizzata**, e **Misura**) che puoi utilizzare per controllare quali colonne sono visibili. Puoi anche selezionare l'intestazione della colonna per filtrare o ordinare il risultato corrente in base a quella colonna. La schermata seguente evidenzia i campi dimensione, filtro, conteggio risultati e "carica altro" disponibili sulla pagina **Riepilogo inventario**.

![Pagina riepilogo inventario.](media/inventory-visibility-onhand-list.png "Pagina riepilogo inventario")

Poiché avrai predefinito le dimensioni utilizzate per il caricamento dei dati di riepilogo, la pagina **Precarica il riepilogo di visibilità inventario** visualizza le colonne relative alle dimensioni. *Le dimensioni non sono personalizzabili: il sistema supporta solo le dimensioni del sito e dell'ubicazione per gli elenchi di scorte disponibili precaricati.* La pagina **Precarica il riepilogo di visibilità inventario** fornisce filtri simili a quelli della pagina **Riepilogo inventario** tranne per il fatto che le dimensioni sono già selezionate. La schermata seguente evidenzia i campi di filtro disponibili nella pagina **Precarica il riepilogo di visibilità inventario**.

![Pagina Precarica il riepilogo di visibilità inventario.](media/inventory-visibility-preload-onhand-list.png "Pagina Precarica il riepilogo di visibilità inventario")

In fondo alle pagine **Precarica il riepilogo di visibilità inventario** e **Riepilogo inventario** troverai informazioni come "50 record (29 selezionati)" o "50 record". Questa informazione si riferisce ai record attualmente caricati dal risultato del **filtro avanzato**. Il testo "29 selezionati" si riferisce al numero di record che sono stati selezionati utilizzando il filtro di intestazione della colonna per i record caricati. C'è anche un pulsante **Ulteriori informazioni** che puoi usare per caricare altri record da Dataverse. Il numero predefinito di record caricati è 50. Quando si seleziona **Carica altro**, i prossimi 1.000 record disponibili vengono caricati nella vista. Il numero sul pulsante **Carica altro** indica i record attualmente caricati e il numero totale di record per il risultato del **filtro avanzato**.
