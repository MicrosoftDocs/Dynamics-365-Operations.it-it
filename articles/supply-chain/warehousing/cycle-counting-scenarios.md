---
title: Scenari di esempio di conteggio ciclo
description: Questo argomento fornisce una raccolta di scenari che spiegano le funzionalità di conteggio dei cicli di Microsoft Dynamics 365 Supply Chain Management.
author: GalynaFedorova
ms.date: 06/08/2021
ms.topic: article
ms.search.form: WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSCycleCountThreshold, WHSWorkTableListPage, SalesShipmentDeviation, WHSRFMenuItemCycleCount, WHSWorkLineCycleCount
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 828954402d223c62f52d7a13fcc9efab84630c80
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261785"
---
# <a name="cycle-counting-example-scenarios"></a>Scenari di esempio di conteggio ciclo

[!include [banner](../includes/banner.md)]

Questo argomento fornisce una raccolta di scenari che spiegano le funzionalità di conteggio dei cicli di Microsoft Dynamics 365 Supply Chain Management. Descrive innanzitutto i requisiti per l'ambiente esistente di Supply Chain Management. Spiega quindi come configurare il conteggio ciclo e descrive tutte le fasi del conteggio ciclo. Quando hai finito, dovresti avere una buona conoscenza del conteggio dei cicli, incluso il conteggio dei cicli guidato, il conteggio dei cicli forzato, il conteggio dei cicli a campione, le soglie del conteggio dei cicli e i piani di conteggio dei cicli.

## <a name="prerequisites"></a>Prerequisiti

### <a name="make-demo-data-available"></a>Rendi disponibili i dati dimostrativi

Ogni scenario di questo argomento fa riferimento a valori e record inclusi nei dati dimostrativi standard forniti per Supply Chain Management. Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica (società) su **USMF** prima di iniziare.

### <a name="turn-on-support-for-the-warehouse-management-mobile-app"></a>Attivare il supporto per l'app per dispositivi mobili Warehouse Management

Prima di poter utilizzare la nuova app per dispositivi mobili Warehouse Management, è necessario aggiungere il supporto nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione magazzino*
- **Nome funzionalità:** *Impostazioni utente, icone e titoli dei passaggi per la nuova app di magazzino*

### <a name="prepare-demo-data-for-the-scenarios"></a><a name= "prepare-demo-data"></a>Preparare i dati demo per gli scenari

Segui questi passaggi per verificare che tutti i dati demo richiesti per gli scenari siano disponibili nella società USMF nel tuo sistema. Crea eventuali record o valori mancanti.

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoratore**.
1. Nel riquadro dell'elenco, seleziona **Julia Funderburk**.
1. Nella scheda dettaglio **Utenti** seleziona la riga con i seguenti valori. Se nessuna riga esistente ha questi valori, creala.

    - **ID utente:** *61*
    - **Nome utente:** *WH61*
    - **Magazzino predefinito:** *61*
    - **Nome menu:** *Principale*

1. Nella scheda dettaglio **Lavoro** imposta i seguenti valori per l'utente *61* se non sono già impostati:

    - **Supervisore conteggio ciclo:** *No*
    - **Limite percentuale massima:** *0*
    - **Limite quantità massima:** *0*
    - **Limite valore massimo:** *0*

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Pool di lavoro**.
1. I pool di lavoro vengono usati per separare il lavoro del magazzino, in base al tipo di lavoro (in questo caso, lavoro di conteggio ciclo). Assicurati che esista un record con le seguenti impostazioni:

    - **ID pool di lavoro:** *CycleCount*
    - **Descrizione:** *Conteggio ciclo*

1. Passa a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel riquadro dell'elenco, seleziona il record denominato *Conteggio ciclo*. Se nessun record esistente ha questo nome, crealo. Conferma o imposta i seguenti valori per il record:

    - **Nome voce di menu:** *Conteggio ciclo*
    - **Titolo:** *Conteggio ciclo guidato*
    - **Modalità:** *Lavoro*
    - **Utilizza lavoro esistente:** *Sì*
    - **Diretto da:** *Sistema diretto* (Questo valore indica che Supply Chain Management assegnerà un ID lavoro di conteggio ciclo al lavoratore.)
    - **Visualizza stato inventario:** *Sì*

1. Nel riquadro azioni, seleziona **Conteggio ciclo**.
1. Nella finestra di dialogo **Conteggio ciclo dispositivo mobile** conferma o imposta i seguenti valori:

    - **Visualizza numero articolo:** *Sì*
    - **Visualizza targa:** *Sì*
    - **Numero di tentativi:** *1*

1. Selezionare **OK** per chiudere la finestra di dialogo.
1. Nel riquadro dell'elenco, seleziona il record denominato *Conteggio ciclo forzato*. Se nessun record esistente ha questo nome, crealo. Conferma o imposta i seguenti valori per il record:

    - **Nome voce di menu:** *Conteggio ciclo forzato*
    - **Titolo:** *Conteggio ciclo forzato*
    - **Modalità:** *Lavoro*
    - **Utilizza lavoro esistente:** *Sì*
    - **Diretto da:** *Raggruppamento conteggio ciclo* (Questo valore indica che il lavoratore può raggruppare degli ID di lavoro di conteggio ciclo che sono specifici di un'ubicazione, una zona o un pool di lavoro).

1. Nel riquadro azioni, seleziona **Conteggio ciclo**.
1. Nella finestra di dialogo **Conteggio ciclo dispositivo mobile** conferma o imposta i seguenti valori:

    - **Visualizza numero articolo:** *No*
    - **Visualizza targa:** *No*
    - **Numero di tentativi:** *0*

1. Selezionare **OK** per chiudere la finestra di dialogo.
1. Nel riquadro dell'elenco, seleziona il record denominato *Conteggio a campione*. Se nessun record esistente ha questo nome, crealo. Conferma o imposta i seguenti valori per il record:

    - **Nome voce di menu:** *Conteggio a campione*
    - **Titolo:** *Conteggio a campione*
    - **Modalità:** *Lavoro*
    - **Utilizza lavoro esistente:** *No*
    - **Processo di creazione lavoro:** *Conteggio ciclo a campione* (Questo valore indica che il lavoratore può contare gli articoli in un'ubicazione magazzino in qualsiasi momento, senza creare un lavoro di conteggio ciclo). Per eseguire il conteggio ciclo a campione in un'ubicazione, il lavoratore immette l'ID ubicazione.

1. Accedi a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.
1. Nel riquadro dell'elenco, seleziona il record denominato *Inventario*. Se nessun record esistente ha questo nome, crealo. Conferma che le seguenti voci del menu di conteggio ciclo appaiano nella colonna **Struttura menu**:

    - Conteggio ciclo
    - Conteggio ciclo forzato
    - Conteggio ciclo a campione

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.
1. Nella scheda **Conteggio ciclo**, impostare i seguenti valori:

    - **Tipo di rettifica conteggio ciclo predefinito:** *Conteggio ciclo* (Questo campo specifica il tipo di giornale che viene registrato quando viene eseguito il conteggio ciclo.)
    - **ID classe di lavoro conteggio ciclo predefinito:** *Conteggio* (Questo campo specifica la classe di lavoro utilizzata per il conteggio ciclo.)
    - **Priorità lavoro conteggio ciclo predefinito:** *50* Questo campo imposta la priorità del lavoro di conteggio ciclo rispetto ad altri tipi di lavoro nel magazzino. Se si inserisce un numero inferiore a quello di altri tipi di lavoro, la priorità di lavoro di conteggio ciclo aumenta.

1. Seleziona **Warehouse Management \> Impostazione \> Scorte \> Tipi di rettifica**.
1. La pagina **Tipi di rettifica** consente di creare codici per le diverse rettifiche in entrata e in uscita che potrebbero verificarsi. Verifica che esista un record con le seguenti impostazioni:

    - **Tipo di rettifica magazzino:** *Conteggio ciclo*
    - **Descrizione:** *Conteggio ciclo*
    - **Nome:** *ICnt*

1. Selezionare **Warehouse Management \> Impostazioni \> Impostazione magazzino \> Magazzini**.
1. Nell'elenco dell'elenco, seleziona il magazzino *61*. Se nessun record esistente ha questo nome, crealo.
1. Nella scheda dettaglio **Magazzino**, imposta i seguenti valori:

    - **Usa processi di Warehouse Management:** *Sì* (Questo valore abilita il magazzino per i processi di gestione del magazzino.)
    - **Consenti movimenti targa durante conteggio ciclo:** *Sì* (Questo valore consente ai lavoratori di spostare le targhe durante un conteggio ciclo.)

## <a name="scenario-1-guided-cycle-counting"></a>Scenario 1: Conteggio ciclo guidato

Prima di poter eseguire il conteggio ciclo guidato, è necessario creare un lavoro. Questo lavoro guiderà la persona assegnata attraverso il magazzino, da un luogo all'altro, per completare i conteggi impostati nel lavoro.

### <a name="create-cycle-counting-work-for-scenario-1"></a>Creare un lavoro di conteggio ciclo per lo scenario 1

Segui questi passaggi per creare un lavoro di conteggio ciclo per la posizione dell'articolo *01A02R2S2B* (BULK-06) nel magazzino *61*.

1. Vai a **Warehouse Management \> Conteggio ciclo \> Lavoro conteggio ciclo per ubicazione**.
1. Nella finestra di dialogo **Crea lavoro conteggio ciclo per ubicazione** imposta il campo **ID pool di lavoro** su *CycleCount*.
1. Nella scheda dettaglio **Record da includere**, selezionare **Filtro**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo** segui questi passaggi:

    - Per la riga in cui il campo **Campo** è impostato su *Magazzino*, imposta il campo **Criteri** su *61*.
    - Per la riga in cui il campo **Campo** è impostato su *Ubicazione*, imposta il campo **Criteri** su *01A02R2S2B*.

1. Selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.
1. Seleziona **OK** per chiudere la finestra di dialogo **Crea lavoro conteggio ciclo per ubicazione**.

    Al termine del processo di creazione del lavoro, viene visualizzato un messaggio nel Centro azioni.

1. Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.
1. Trova il lavoro appena creato impostando un filtro sulla colonna **ID pool di lavoro** per trovare i record che hanno il valore *CycleCount*.

### <a name="do-cycle-counting-work-for-scenario-1"></a>Effettuare un lavoro di conteggio ciclo per lo scenario 1

Una volta creato il lavoro di conteggio ciclo, è possibile eseguire il lavoro contando gli articoli in un'ubicazione magazzino e utilizzando un dispositivo mobile per inserire i risultati in Supply Chain Management. Segui questi passaggi per eseguire il conteggio ciclo nell'app per dispositivi mobili Warehouse Management.

1. Accedi all'app per dispositivi mobili Warehouse Management come utente di lavoro che hai impostato nella sezione precedente [Preparare i dati demo per gli scenari](#prepare-demo-data) in questo argomento. Per l'esempio in questo argomento, l'utente è denominato *Julia Funderburk* ed è impostato per magazzino *61*. I dati demo USMF ti consentono di accedere come utente di lavoro inserendo *61* come ID utente e *1* come password.
1. Nel menu principale, selezionare **Inventario**.
1. Nel menu **Inventario** seleziona **Conteggio ciclo guidato**.
1. Seleziona il campo **Qtà** inserisci *9* utilizzando il tastierino numerico, quindi seleziona **OK** (il pulsante del segno di spunta).
1. Il sistema si aspettava che tu inserissi un conteggio di 10 pezzi per questo articolo, posizione e targa. Pertanto, ti viene chiesto di ricontare. Seleziona il campo **Qtà** inserisci di nuovo *9* utilizzando il tastierino numerico, quindi seleziona **OK** (il pulsante del segno di spunta). Al secondo tentativo, il tuo conteggio sarà accettato.

    > [!NOTE]
    > Quando il sistema ha rilevato una differenza tra la quantità prevista in giacenza e la quantità che hai inserito, ti ha chiesto di contare una seconda volta perché il campo **Numero di tentativi** è impostato su *1* per la voce di menu del dispositivo mobile **Conteggio ciclo guidato**. Sei stato guidato a un numero di articolo specifico e numero di targa perché l'opzione **Visualizza numero articolo** e l'opzione **Visualizza targa** sono impostate su *Sì* per la voce di menu del dispositivo mobile.

1. Selezionare **OK** (il simbolo del segno di spunta).

### <a name="review-the-cycle-counting-differences-for-scenario-1"></a>Rivedere le differenze di conteggio ciclo per lo scenario 1

Seguire questi passaggi per rivedere le differenze di conteggio ciclo.

1. Torna a Supply Chain Management.
1. Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.
1. Trova e seleziona il lavoro di conteggio ciclo che hai esaminato in precedenza. (Ad esempio, imposta un filtro sulla colonna **ID pool di lavoro** per trovare i record che hanno un valore di *CycleCount*.) Nota che il campo **Stato lavoro** per questo lavoro è ora impostato su *Revisione in sospeso*.

    > [!NOTE]
    > Per l'account utente di lavoro che hai utilizzato per eseguire il lavoro di conteggio, l'opzione **Supervisore conteggio ciclo** è impostata su *No*, e i campi **Limite percentuale massimo**, **Limite quantità massima**, e **Limite valore massimo** sono tutti impostati su *0* (zero). Pertanto, tutte le differenze di conteggio che questo utente segnala devono essere approvate manualmente e il campo **Stato lavoro** per il lavoro correlato è impostato su *Revisione in sospeso*. Se il valore conteggiato rientrava nei limiti di deviazione (come specificato nei campi **Limite percentuale massimo** o **Limite quantità massima** della pagina **Utenti lavoro**), o se l'opzione **Supervisore conteggio ciclo** era impostata su *Sì* per l'utente, il lavoro sarebbe stato automaticamente chiuso.

1. Nel riquadro Azioni, nella scheda **Lavoro**, seleziona **Conteggio ciclo**.
1. Nel riquadro azioni, seleziona **Accetta conteggio**.

    La differenza viene registrata utilizzando il giornale di registrazione di conteggio standard e viene creato un nuovo ordine di lavoro.

1. Nella pagina **Transazioni conteggio ciclo**, nel riquadro azioni, seleziona **Lavoro derivato** per trovare il lavoro creato per la differenza approvata.

## <a name="scenario-2-blind-cycle-counting"></a>Scenario 2: Conteggio ciclo forzato

Questo scenario richiede che lo scenario 1 sia già completato nel sistema.

### <a name="create-cycle-counting-work-for-scenario-2"></a>Creare un lavoro di conteggio ciclo per lo scenario 2

Prima di poter eseguire il conteggio ciclo forzato, è necessario creare un lavoro. Segui questi passaggi per creare un lavoro di conteggio ciclo per la posizione dell'articolo *01A02R2S2B* (BULK-06) nel magazzino *61*.

1. Vai a **Warehouse Management \> Conteggio ciclo \> Lavoro conteggio ciclo per articolo**.
1. Nella finestra di dialogo **Crea lavoro conteggio ciclo per articolo** imposta il campo **ID pool di lavoro** su *CycleCount*.
1. Nella scheda dettaglio **Record da includere**, selezionare **Filtro**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungi tre righe con le seguenti impostazioni:

    - Riga 1:

        - **Tabella:** *Articoli*
        - **Campo:** *Numero articolo*
        - **Criteri:** *L0101*

    - Riga 2:

        - **Tabella:** *Dimensioni inventariali*
        - **Campo:** *Magazzino*
        - **Criteri:** *61*

    - Riga 3:

        - **Tabella:** *Dimensioni inventariali*
        - **Campo:** *Ubicazione*
        - **Criteri:** *01A02R2S2B*

1. Selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.
1. Seleziona **OK** per chiudere la finestra di dialogo **Crea lavoro conteggio ciclo per articolo**.

    Quando il processo di creazione del lavoro è completato, ricevi un messaggio informativo.

### <a name="do-cycle-counting-work-for-scenario-2"></a>Effettuare un lavoro di conteggio ciclo per lo scenario 2

Dopo aver creato il lavoro di conteggio ciclo, segui questi passaggi per eseguire il lavoro nell'app per dispositivi mobili Warehouse Management.

1. Accedi all'app per dispositivi mobili Warehouse Management come utente di lavoro che hai impostato nella sezione precedente [Preparare i dati demo per gli scenari](#prepare-demo-data) in questo argomento. Per l'esempio in questo argomento, l'utente è denominato *Julia Funderburk* ed è impostato per magazzino *61*. I dati demo USMF ti consentono di accedere come utente di lavoro inserendo *61* come ID utente e *1* come password.
1. Nel menu principale, selezionare **Inventario**.
1. Nel menu **Inventario** seleziona **Conteggio ciclo forzato**.
1. Seleziona il campo **ID zona** immetti *BULK06*, quindi seleziona **OK** (il pulsante con il segno di spunta).
1. Seleziona il campo **Articolo** immetti *L0101*, quindi seleziona **OK** (il pulsante con il segno di spunta).
1. Seleziona il campo **Targa** immetti *LP\_BULK\_06\_01*, quindi seleziona **OK** (il pulsante con il segno di spunta).
1. Seleziona il campo **Qtà** immetti *10*, quindi seleziona **OK** (il pulsante con il segno di spunta).

    > [!NOTE]
    > Anche se il sistema ha rilevato una differenza tra la quantità prevista in giacenza e la quantità che hai inserito, non ti ha chiesto di contare una seconda volta perché il campo **Numero di tentativi** è impostato su *0* (zero) per la voce di menu del dispositivo mobile **Conteggio ciclo forzato**. Ti è stato richiesto di digitalizzare il numero di articolo e il numero di targa perché l'opzione **Visualizza numero articolo** e l'opzione **Visualizza targa** sono impostate su *No* per la voce di menu del dispositivo mobile.

1. Selezionare **OK** (il simbolo del segno di spunta).

### <a name="review-the-cycle-counting-differences-for-scenario-2"></a>Rivedere le differenze di conteggio ciclo per lo scenario 2

Seguire questi passaggi per rivedere le differenze di conteggio ciclo.

1. Torna a Supply Chain Management.
1. Vai a **Warehouse Management \> Comune \> Lavoro \> Lavoro conteggio ciclo con revisione in sospeso**.
1. Nel riquadro Azioni, nella scheda **Lavoro**, seleziona **Conteggio ciclo**.
1. Nel riquadro azioni, seleziona **Rifiuta conteggio**.

    Poiché la differenza di conteggio è stata rifiutata, il lavoro è chiuso.

## <a name="scenario-3-spot-cycle-counting"></a>Scenario 3: Conteggio ciclo a campione

Il record delle scorte indica che è presente una quantità di articolo disponibile *L0101* nell'ubicazione *01A02R2S2B*. L'addetto al magazzino è all'ubicazione *01A02R2S1B*. Anche se questa ubicazione dovrebbe essere vuota, è piena. Pertanto, l'addetto al magazzino esegue immediatamente un conteggio a campione di questa ubicazione.

### <a name="do-cycle-counting-work-for-scenario-3"></a>Effettuare un lavoro di conteggio ciclo per lo scenario 3

Segui questi passaggi per eseguire il conteggio ciclo nell'app per dispositivi mobili Warehouse Management.

1. Accedi all'app per dispositivi mobili Warehouse Management come utente di lavoro che hai impostato nella sezione precedente [Preparare i dati demo per gli scenari](#prepare-demo-data) in questo argomento. Per l'esempio in questo argomento, l'utente è denominato *Julia Funderburk* ed è impostato per magazzino *61*. I dati demo USMF ti consentono di accedere come utente di lavoro inserendo *61* come ID utente e *1* come password.
1. Nel menu principale, selezionare **Inventario**.
1. Nel menu **Inventario** seleziona **Conteggio a campione**.
1. Seleziona il campo **Ubicazione** immetti *01A02R2S1B*, quindi seleziona **OK** (il pulsante con il segno di spunta).

    Il sistema rileva che l'ubicazione è vuota in Supply Chain Management.

1. Seleziona **Aggiungi targa o oggetto**.
1. Seleziona il campo **Articolo** immetti *L0101*, quindi seleziona **OK** (il pulsante con il segno di spunta).
1. Seleziona il campo **Targa** immetti *LP\_BULK\_06\_01*, quindi seleziona **OK** (il pulsante con il segno di spunta).
1. Seleziona il campo **Qtà** immetti *9*, quindi seleziona **OK** (il pulsante con il segno di spunta).

    Poiché il sistema rileva che la targa specificata è già disponibile in un'altra ubicazione in Supply Chain Management, quella targa verrà spostata nell'ubicazione corrente. Pertanto, il sistema chiede di confermare il movimento.

1. Selezionare **OK** (il simbolo del segno di spunta).

### <a name="review-the-cycle-counting-differences-for-scenario-3"></a>Rivedere le differenze di conteggio ciclo per lo scenario 3

Seguire questi passaggi per rivedere i risultati del conteggio.

1. Torna a Supply Chain Management.
1. Vai a **Warehouse Management \> Comune \> Dettagli lavoro**.
1. Seleziona la casella di controllo **Mostra chiuso** nella parte superiore della griglia.
1. Imposta il filtro per la colonna **Tipo di ordine di lavoro** su *Movimento scorte*.

    Il sistema ha rilevato automaticamente questo conteggio come un movimento scorte. Questo movimento è consentito perché l'opzione **Consenti movimenti targa durante conteggio ciclo** è impostata su *Sì* per il magazzino *61* nella pagina **Magazzini**.

## <a name="scenario-4-define-cycle-count-thresholds"></a>Scenario 4: definire le soglie di conteggio ciclo

Un modo per creare un lavoro di conteggio ciclo consiste nell'utilizzare le soglie. Una soglia di conteggio ciclo indica la quantità o il limite di percentuale degli articoli di magazzino. Il lavoro del conteggio ciclo viene automaticamente creato quando viene raggiunta la soglia.

Ad esempio, sono presenti 60 articoli in una ubicazione con una soglia di conteggio ciclo di 40. Durante la transazione di ordini cliente, 25 articoli vengono prelevati dalla ubicazione e collocati in una ubicazione temporanea. Poiché il nuovo conteggio articoli di 35 è inferiore alla quantità soglia, il lavoro di conteggio ciclo viene creato automaticamente per l'ubicazione.

Segui questi passaggi per impostare le soglie di conteggio ciclo.

1. Vai a **Warehouse management \> Impostazioni \> Conteggio ciclo \> Soglie conteggio ciclo**.
1. Nel riquadro azioni seleziona **Nuovo** per creare una soglia e impostarne i seguenti valori:

    - **ID soglia conteggio ciclo:** *L0101*
    - **Descrizione:** *Soglia L0101*
    - **Quantità di soglia:** *2*
    - **Unità:** *unità*
    - **Soglia capacità basata su percentuale:** *0,00*
    - **Tipo di soglia conteggio ciclo:** *Quantità*
    - **Elabora conteggio ciclo immediatamente:** *Sì*
    - **Giorni tra conteggio ciclo:** *1*
    - **ID pool di lavoro:** *CycleCount*

1. Nel riquadro azioni seleziona **Seleziona articoli**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, trovare la riga in cui il campo **Campo** è impostato su *Numero articolo*. Imposta il campo **Criteri** per questa riga su *L0101*.
1. Selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.

    Ora hai definito una soglia di conteggio ciclo per l'articolo *L0101*.

Il conteggio ciclo verrà ora creato per l'articolo *L0101* in qualsiasi ubicazione se la quantità disponibile è inferiore a 2 e se la data dell'ultimo conteggio ciclo per l'ubicazione è diversa da quella corrente.

## <a name="scenario-5-define-cycle-count-plans"></a>Scenario 5: definire i piani di conteggio ciclo

I piani di conteggio ciclo consentono di automatizzare la creazione del lavoro di conteggio ciclo. È possibile impostare ogni piano di conteggio ciclo con query di posizione e articoli specifici. Quando il processo batch viene eseguito, crea un lavoro di conteggio ciclo per tutte le ubicazioni che corrispondono ai criteri dell'articolo e dell'ubicazione (fino al numero massimo di conteggi specificato per il piano). Quando viene creato un lavoro di conteggio ciclo, la riga di lavoro di conteggio include informazioni sull'ubicazione da conteggiare. Le scorte disponibili associate a quella ubicazione non sono bloccate. Pertanto, è disponibile per la prenotazione e l'elaborazione in uscita, anche se esiste un lavoro di conteggio aperto.

Segui questi passaggi per impostare un piano di conteggio ciclo.

1. Vai a **Warehouse management \> Impostazioni \> Conteggio ciclo \> Piani di conteggio ciclo**.
1. Nel riquadro azioni seleziona **Nuovo** per aggiungere una riga alla griglia e imposta i seguenti campi:

    - **ID piano di conteggio ciclo:** *BULK06*
    - **Descrizione:** *conteggio dell'ubicazione per BULK06*
    - **ID pool di lavoro:** *CycleCount*
    - **Numero massimo di conteggi ciclo:** *10*
    - **Giorni tra conteggio ciclo:** *10*
    - **Ubicazioni vuote:** *Escludi vuoto*
    - **Modello di lavoro**: lasciare vuoto questo campo.

1. Nel riquadro azioni seleziona **Seleziona ubicazioni**.
1. Viene visualizzata la finestra di dialogo dell'editor di query standard. Nella scheda **Intervallo**, aggiungi una riga e imposta i seguenti valori:

    - **Tabella:** *Ubicazioni*
    - **Campo:** *ID zona*
    - **Criteri:** *BULK06*

1. Selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.
1. Nel riquadro azioni, seleziona **Elabora piano di conteggio ciclo**.
1. Nella finestra di dialogo **Piani di conteggio ciclo**, nella Scheda dettaglio **Esegui in background**, imposta l'opzione **Elaborazione in batch** su *Sì*.
1. Seleziona **Ricorrenza**.
1. Nella finestra di dialogo **Definisci ricorrenza** imposta il processo batch in modo che inizi immediatamente e venga eseguito una volta al minuto, senza una data di fine.
1. Seleziona **OK** per chiudere la finestra di dialogo **Definisci ricorrenza**.
1. Seleziona **OK** per chiudere la finestra di dialogo **Piani di conteggio ciclo**.

    Un messaggio informa che il lavoro è stato aggiunto alla coda batch.

1. Vai a **Warehouse management \> Comune \> Programmazione conteggio ciclo**. Il piano inizia immediatamente e crea lavoro di conteggio. Poiché il lavoro di conteggio non è stato completato, il campo **Stato** è impostato su *In corso*. Dopo un minuto, il valore nella colonna **Conteggi ciclo totali** cambia in *1*.

    > [!NOTE]
    > Il lavoro di conteggio ciclo non verrà creato se il numero di giorni dall'ultimo conteggio ciclo è inferiore al valore impostato per il campo **Giorni tra conteggi ciclo** per il piano di conteggio ciclo. Ad esempio, se il valore specificato nel campo **Giorni tra conteggio ciclo** è impostato su *5*, il lavoro del conteggio ciclo verrà creato ogni cinque giorni. Tuttavia, se il lavoro di conteggio ciclo viene elaborato il terzo giorno, il lavoro di conteggio ciclo successivo verrà creato cinque giorni dopo l'elaborazione dell'ultimo conteggio ciclo, l'ottavo giorno.

1. Nel riquadro azioni, seleziona **Lavoro** per visualizzare il lavoro di conteggio creato.
