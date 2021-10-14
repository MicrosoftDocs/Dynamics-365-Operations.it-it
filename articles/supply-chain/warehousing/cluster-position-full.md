---
title: Posizione cluster piena
description: In questo argomento vengono fornite informazioni sulla funzionalità Posizione cluster piena. Questa funzione offre un'alternativa all'applicazione più rigida delle regole di interruzione del lavoro quando viene utilizzato il prelievo del cluster perché consente un margine di errore più ampio nei vincoli volumetrici dei contenitori o dei totali.
author: Mirzaab
ms.date: 08/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: a23168b550bfa2bb6a51c8df5d0a558431c23ebb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574259"
---
# <a name="cluster-position-full"></a>Posizione cluster piena

[!include [banner](../includes/banner.md)]

La funzione *Posizione cluster piena* offre un'alternativa all'applicazione più rigida delle regole di interruzione del lavoro quando viene utilizzato il prelievo del cluster perché consente un margine di errore più ampio nei vincoli volumetrici dei contenitori o dei totali. In uno scenario comune, non tutti gli articoli di un ordine di lavoro rientrano un contenitore selezionato. I lavoratori del magazzino che effettuano il prelievo del cluster hanno poche opzioni in questo scenario: devono passare a una dimensione del contenitore più grande o collaborare con il proprio supervisore per trovare una soluzione diversa.

Questa funzione introduce la possibilità di eseguire il pulsante **Completo** su una delle unità di lavoro in un cluster. Nelle versioni precedenti, questa opzione era disponibile solo per il prelievo regolare degli ordini, non per il prelievo in gruppo. Tuttavia, questa funzionalità è diversa dal pulsante **Completo** standard in quanto annulla il lavoro rimanente. Non suggerisce all'utente di aggiungere un altro contenitore allo stesso cluster e non crea automaticamente nuovo lavoro.

## <a name="turn-on-the-cluster-position-full-feature"></a>Attivare la funzionalità Posizione cluster piena

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Posizione cluster piena*

## <a name="setup"></a>Attrezzaggio

Questa sezione fornisce le linee guida e un esempio che mostra come configurare e utilizzare la funzionalità *Posizione cluster piena*.

### <a name="make-sample-data-available"></a>Rendi disponibili i dati di esempio

Per elaborare lo [scenario di esempio](#example-scenario) utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

È inoltre possibile utilizzare questo scenario di esempio come indicazioni per l'utilizzo di questa funzionalità in un sistema di produzione. Tuttavia, in tal caso, è necessario sostituire i valori per le impostazioni descritte qui.

### <a name="cluster-profiles"></a>Profili cluster

È necessario specificare se gli ID cluster vengono generati automaticamente, quante posizioni vengono utilizzate, quando i cluster vengono interrotti e come viene sequenziato e verificato il lavoro di prelievo.

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Profili cluster**.
1. Nel riquadro elenco, selezionare il record **Crea cluster**.
1. Nella Scheda dettaglio **Generale**, verificare i seguenti valori:

    - **Genera ID cluster:** *Sì*
    - **Attiva posizioni:** *Sì*
    - **Numero di posizioni:** *2*
    - **Nome posizione:** *Numerico*
    - **Suddividi cluster a:** *Inserisci*
    - **Ordina tipo di verifica:** *Scansione posizione*

1. Nella scheda dettaglio **Ordinamento cluster**. La griglia deve essere vuota (ovvero, non deve contenere righe).

### <a name="work-templates"></a>Modelli di lavoro

È necessario definire la modalità di prelievo del lavoro per il prelievo del cluster.

1. Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.
1. Nella parte superiore della pagina, impostare il campo **Tipo di ordine di lavoro** su *Ordini cliente*.
1. Assicurarsi che siano elencati i seguenti modelli di lavoro dai dati demo. Se non sono disponibili, non è possibile completare lo scenario.

    - Fase ordine cliente 61
    - Prelievo cluster ordine cliente 61

### <a name="location-directives"></a>Direttive ubicazione

È necessario specificare da dove vengono prelevati gli articoli e dove vengono inseriti.

1. Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Nell'intestazione elenco, impostare il campo **Tipo ordine di lavoro** su *Ordini cliente*.
1. Assicurarsi che siano elencate le seguenti direttive ordine cliente dai dati demo. Se non sono disponibili, non è possibile completare lo scenario.

    - Prelievo cluster 61
    - Prelievo ordine ordine cliente 61

### <a name="mobile-device-menu-items"></a>Voci di menu del dispositivo mobile

È necessario configurare una voce di menu del dispositivo mobile per utilizzare il lavoro esistente che è diretto dal prelievo del cluster. Nella voce di menu del dispositivo mobile per il prelievo cluster, il parametro **Consenti suddivisione del lavoro** deve essere attivato e la classe di lavoro *Prelievo ordine cliente* deve essere aggiunta.

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel riquadro elenco, selezionare il record **Creazione prelievo del cluster**.
1. Nel riquadro azioni, selezionare **Modifica**.
1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Diretto da:** *Prelievo del cluster*
    - **Genera targa:** *Sì*
    - **Consenti suddivisione del lavoro:** *Sì*
    - **ID profilo cluster:** *Crea cluster*

    Accetta i valori predefiniti per tutti gli altri campi.

1. Nella scheda dettaglio **Classi di lavoro** aggiungere le seguenti due righe, come richiesto:

    - Riga 1 (normalmente presente nei dati demo):

        - **ID classe lavoro:** *Vendita* 
        - **Tipo di ordine di lavoro:** *Ordini cliente*

    - Riga 2 (probabilmente non presente nei dati demo):

        - **ID classe lavoro:** *Prelievo ordine cliente*
        - **Tipo di ordine di lavoro:** *Ordini cliente*

1. Andare a **Impostazione conferma lavoro** nel riquadro azioni.
1. Selezionare **Modifica**.
1. Immettere i seguenti valori nella riga della griglia.
    - **Tipo di lavoro** - *Prelevare*
    - **Conferma del prodotto** - *Selezionare la casella di controllo*

1. Selezionare **Salva** nel riquadro azioni e chiudere la pagina.

## <a name="create-picking-work"></a>Creare il lavoro di prelievo

Prima di poter iniziare il prelievo dei cluster, è necessario creare del lavoro in uscita. Il profilo cluster creato in precedenza specifica due posizioni cluster. Pertanto, è necessario creare almeno due ID lavoro per il prelievo degli ordini cliente. Per questo scenario, le transazioni avverranno nel magazzino *61* e useranno gli articoli *L0101* e *T0100*. I dati della demo dovrebbero avere scorte sufficienti di questi articoli. Assicurarsi di disporre di scorte sufficienti per completare le transazioni.

### <a name="create-sales-order-1"></a>Creare l'ordine cliente 1

1. Accedere a **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Selezionare **Nuovo** per creare l'ordine cliente 1.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Conto cliente:** *US-010*
    - **Magazzino:** *61*

1. Selezionare **OK**.
1. Viene aperto il nuovo ordine cliente. Nella Scheda dettaglio **Righe ordine cliente**, aggiungere una riga che abbia le seguenti impostazioni:

    - **Numero articolo:** *T0100*
    - **Quantità:** *5*

1. Nella scheda dettaglio **Dettagli riga** nella scheda **Consegna** impostare il campo **Data di consegna confermata** sulla data di oggi.
1. Nella Scheda dettaglio **Righe ordine cliente**, aggiungere una seconda riga che abbia le seguenti impostazioni:

    - **Numero articolo:** *L0101*
    - **Quantità:** *20*

1. Nella scheda dettaglio **Dettagli riga** nella scheda **Consegna** impostare il campo **Data di consegna confermata** sulla data di oggi.
1. Per ogni riga che appena aggiunta, seguire questi passaggi per prenotare le scorte:

    1. Selezionare la riga da prenotare.
    2. Nella scheda dettaglio **Righe ordine cliente**, selezionare **Scorte \> Prenotazione**.
    3. Nella pagina **Prenotazione**, quindi nel riquadro azioni, selezionare **Prenota lotto** per prenotare le scorte.
    4. Chiudi la pagina **Prenotazione**.

1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.

    Quando il rilascio è completato, verranno ricevuti messaggi informativi che mostrano l'ID ondata e l'ID carico creati.

### <a name="create-sales-order-2"></a>Creare l'ordine cliente 2

1. Accedere a **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Selezionare **Nuovo** per creare l'ordine cliente 2.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Conto cliente:** *US-011*
    - **Magazzino:** *61*

1. Selezionare **OK**.
1. Viene aperto il nuovo ordine cliente. Nella Scheda dettaglio **Righe ordine cliente**, aggiungere una riga che abbia le seguenti impostazioni:

    - **Numero articolo:** *L0101*
    - **Quantità:** *20*

1. Nella scheda dettaglio **Dettagli riga** nella scheda **Consegna** impostare il campo **Data di consegna confermata** sulla data di oggi.
1. Nella Scheda dettaglio **Righe ordine cliente**, aggiungere una seconda riga che abbia le seguenti impostazioni:

    - **Numero articolo:** *T0100*
    - **Quantità:** *2*

1. Nella scheda dettaglio **Dettagli riga** nella scheda **Consegna** impostare il campo **Data di consegna confermata** sulla data di oggi.
1. Per ogni riga che appena aggiunta, seguire questi passaggi per prenotare le scorte:

    1. Selezionare la riga da prenotare.
    2. Nella scheda dettaglio **Righe ordine cliente**, selezionare **Scorte \> Prenotazione**.
    3. Nella pagina **Prenotazione**, quindi nel riquadro azioni, selezionare **Prenota lotto** per prenotare le scorte.
    4. Chiudi la pagina **Prenotazione**.

1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.

    Quando il rilascio è completato, verranno ricevuti messaggi informativi che mostrano l'ID ondata e l'ID carico creati.

### <a name="get-work-ids-and-license-plate-numbers"></a>Ottenere gli ID lavoro e i numeri di targa

Dovrebbero essere stati creati due ID lavoro, ciascuno dei quali ha due righe di selezione. Seguire questi passaggi per trovare gli ID lavoro e le assegnazioni delle targhe.

1. Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.
1. Nella griglia **Panoramica** cercare la colonna **Numero ordine** per i due ordini cliente appena creati. Prendere nota dell'ID lavoro corrispondente per ciascun ordine cliente.
1. Selezionare la riga per ogni ordine cliente per visualizzare le informazioni correlate nella griglia **Righe**. Prendere nota della posizione da cui verrà prelevato ogni articolo.
1. Passare a **Gestione articoli \> Richieste di informazioni e report \> Scorte disponibili**.
1. Nel riquadro azioni, scegliere **Dimensioni** per aprire la finestra di dialogo **Visualizzazione dimensioni**.
1. Assicurarsi che le caselle di controllo **Targa**, **Magazzino** e **Numero articolo** siano selezionate, quindi selezionare **OK**.
1. Nel riquadro **Filtro** impostare i seguenti filtri:

    - **Numero articolo** - **è uno tra** - *L0101* e *T100*
    - **Magazzino** - **inizia con** - *61*

1. Prendere nota dei valori **Targa** visualizzati.

## <a name="example-scenario"></a><a name="example-scenario"></a>Scenario di esempio

### <a name="mobile-device-flow-execution--work-confirmation-setup-for-the-product"></a>Esecuzione del flusso del dispositivo mobile: impostazione della conferma del lavoro per il prodotto

1. Accedi all'app per dispositivi mobili Gestione magazzino come utente nel magazzino *61*.
1. Andare a **In uscita \> Creazione prelievo del cluster**.

    Viene visualizzata la pagina **ATTIVITÀ: assegnare il lavoro al cluster**.

1. Immettere l'ID lavoro per l'ordine cliente 1 per assegnarlo alla posizione cluster 1.
1. Selezionare **OK** (segno di spunta).
1. Immettere l'ID lavoro per l'ordine cliente 2 per assegnarlo alla posizione cluster 2.
1. Selezionare **OK** (segno di spunta).

    Viene visualizzata la pagina **ATTIVITÀ: Creazione prelievo del cluster: prelievo** che mostra *Articolo L0101 2 PL*.

Poiché il profilo cluster imposta il numero di posizioni su 2, il sistema indirizza automaticamente al primo prelievo consolidato: due pallet (PL) dell'articolo *L0101*.

In qualsiasi momento durante i seguenti passaggi, è possibile selezionare la scheda **Dettagli** per visualizzare ulteriori informazioni sull'attività, come la posizione di prelievo.

1. Impostare il campo **ARTICOLO** su *L0101*. Ciò conferma il numero di articolo, richiesto per questa voce di menu (è stata configurata in precedenza selezionando **Impostazione conferma lavoro** dalla pagina **Voce di menu del dispositivo mobile** quando è stata creata questa voce di menu).
1. Immettere il numero di targa associato all'articolo nella posizione da cui si sta prelevando. Verranno prelevati due pallet.
1. Impostare il campo **LP** su *LP\_PICK\_01*.
1. Selezionare **OK** (segno di spunta).

    Viene visualizzata la pagina **ATTIVITÀ: Ordinamento: Creazione prelievo del cluster**. Qui, i due pallet prelevati vengono ordinati in una posizione di prelievo. Questa posizione potrebbe essere un totalizzatore o un contenitore utilizzato per separare le scorte prelevate dall'ordine cliente.

1. Visualizzare i dettagli mostrati per l'articolo (*L0101*) e la quantità (*20* ea) che verrà ordinato nella posizione 1 (per l'ordine cliente 1).
1. Impostare il campo **NOME POSIZIONE** su *1*.
1. Selezionare **OK** (segno di spunta).
1. Visualizzare i dettagli mostrati per l'articolo (*L0101*) e la quantità (*20* ea) che verrà ordinato nella posizione 2 (per l'ordine cliente 2).
1. Impostare il campo **NOME POSIZIONE** su *2*.
1. Selezionare **OK** (segno di spunta).

    Viene visualizzata la pagina **ATTIVITÀ: Creazione prelievo del cluster: prelievo** che mostra *Articolo T0100 7 ea*.

In questo scenario, la posizione 1 non può accettare l'intera quantità di articoli che devono essere prelevati per evadere l'ordine cliente 1. Una posizione deve essere contrassegnata come piena. In questo scenario, si esegue un prelievo parziale del secondo articolo. Il secondo articolo verrà prelevato parzialmente per la posizione 1 e verrà creato un nuovo lavoro per prelevare la quantità rimanente per evadere l'ordine.

1. Selezionare il pulsante Menu (a volte indicato come hamburger o pulsante hamburger), quindi selezionare **Posizione piena**.
1. Identificare la posizione piena e selezionare *1*.
1. Selezionare **OK** (segno di spunta).
1. Immettere la quantità di prelievo che può ancora essere prelevata nella posizione 1. Il sistema può determinare quale numero di articolo viene prelevato.
1. Immetti *2*.
1. Selezionare **OK** (segno di spunta).
1. Confermare il numero di articolo per completare il prelievo dell'articolo rimanente nella posizione 2.
1. Impostare il campo **ARTICOLO** su *T0100*.
1. Selezionare **OK** (segno di spunta).
1. Immettere la targa da cui viene prelevato l'articolo impostando il campo **LP** su *LPREPL04*.
1. Selezionare **OK** (segno di spunta).
1. Visualizzare i dettagli mostrati per l'articolo (*T0100*) e la quantità (*2* ea) che verrà ordinato nella posizione 2 (per l'ordine cliente 2).
1. Impostare il campo **NOME POSIZIONE** su *2*.
1. Selezionare **OK** (segno di spunta).
1. Visualizzare i dettagli mostrati per l'articolo (*T0100*) e la quantità (*2* ea) che verrà ordinato nella posizione 1 (per l'ordine cliente 1).
1. Impostare il campo **NOME POSIZIONE** su *1*.
1. Selezionare **OK** (segno di spunta).

    Viene visualizzata la pagina **ATTIVITÀ: Creazione prelievo del cluster: Inserimento**.

In questo scenario, il prelievo del cluster è stato completato e all'utente viene chiesto di riporre gli articoli prelevati dalla posizione 1 e dalla posizione 2 nella posizione di gestione temporanea *STAGE01*.

1. Esaminare le informazioni nella pagina. Mostra che una quantità totale di *44* sarà messa nella posizione di gestione temporanea.
1. Selezionare **OK** (segno di spunta).

    Viene ricevuto un messaggio di tipo "Cluster completato".

Ora è possibile usare la voce di menu **Prelievo vendite** per prelevare la quantità rimanente. È quindi possibile utilizzare la voce di menu **Caricamento vendite** per spostare gli articoli dalla posizione di gestione temporanea alla banchina di carico.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]