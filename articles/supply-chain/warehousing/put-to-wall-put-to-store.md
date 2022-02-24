---
title: Stoccaggio a parete - stoccaggio in magazzino
description: Questo argomento fornisce informazioni sulla funzionalità Stoccaggio a parete - stoccaggio in magazzino. Questa funzionalità consente di gestire scenari in cui è necessario consolidare un prodotto in un'area di gestione temporanea di preimballaggio, in base a criteri configurabili. Aiuta a ridurre i tempi di prelievo perché consente di prelevare una singola targa di destinazione singola e può utilizzare più posizioni di stoccaggio rispetto a un prelievo cluster.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationType, WHSLocationProfile, WHSLocation, WHSPackProfile, WHSWaveStepCode, WHSOutboundSortTemplate, WHSPostMethod, WHSWaveTemplateTable, WHSLocDirTable, WHSWorkClass, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 12501b90e4b31ec11e3c59784ace9fd9a8b7d934
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431483"
---
# <a name="put-to-wall---put-to-store"></a>Stoccaggio a parete - stoccaggio in magazzino

[!include [banner](../includes/banner.md)]

La funzionalità *Stoccaggio a parete - stoccaggio in magazzino* consente di gestire scenari in cui è necessario consolidare un prodotto in un'area di gestione temporanea di preimballaggio, in base a criteri configurabili. Poiché questa funzionalità consente il prelievo su una singola targa di destinazione e può utilizzare più posizioni di stoccaggio rispetto al prelievo cluster, le aziende che spediscono a punti vendita o gestiscono piccoli articoli trarranno vantaggio dalla riduzione dei tempi di prelievo.

Il flusso di lavoro per questa funzionalità indirizza il prodotto prelevato a un'ubicazione di ordinamento per la distribuzione in vari tipi di contenitori. In generale, ogni ubicazione di ordinamento include più posizioni di ordinamento. Ogni posizione di ordinamento viene assegnata in base ai criteri impostati dal processo aziendale. I criteri tipici sono la destinazione finale, la spedizione o il carico. Dopo l'arrivo di un prodotto, questo viene distribuito a ciascuna posizione di ordinamento, in base alla quantità associata all'ordine, alla destinazione, alla spedizione o al carico. Quando un container è pieno o completo, viene spostato in un'ubicazione di gestione temporanea o in un'ubicazione di spedizione per un'ulteriore gestione, a seconda del processo aziendale.

Questa funzionalità di magazzino è anche indicata con altri nomi, ad esempio "put-to-light".

## <a name="turn-on-the-outbound-sorting-feature"></a>Attivare la funzionalità Ordinamento in uscita

Prima di poter usare la funzionalità *Stoccaggio a parete - stoccaggio in magazzino*, è necessario attivare la funzionalità *Ordinamento in uscita* nel sistema. Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Ordinamento in uscita*

La funzionalità *Ordinamento in uscita* può essere utilizzata insieme alla funzionalità *Codice passaggio ondata a livello di organizzazione* se è attivata. È inoltre necessario attivare questa funzionalità se si useranno codici predefiniti impostati nei codici passaggio ondata. Nell'area di lavoro **Gestione funzionalità**, questa funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Codice passaggio ondata a livello di organizzazione*

## <a name="setup"></a>Configurazione

Per questa demo, sono utilizzati i dati e il magazzino Contoso standard *62*. Vengono inoltre utilizzate alcune aggiunte che verranno annotate in seguito.

### <a name="location-type"></a>Tipo di ubicazione

1. Andare a **Gestione magazzino \> Impostazione \> Magazzino \> Tipi di ubicazione**.
1. Nel riquadro azioni selezionare **Nuovo** per creare un tipo di ubicazione per l'ordinamento.
1. Imposta i valori seguenti:

    - **Tipo di ubicazione:** *ORDINAMENTO*
    - **Descrizione:** *Ordinamento*

1. Selezionare **Salva**.

### <a name="warehouse-management-parameters"></a>Parametri di gestione magazzino

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.
1. Nella scheda **Generale** della Scheda dettaglio **Tipi di ubicazione**, nel campo **Tipo di ubicazione di ordinamento**, immettere *ORDINAMENTO*.
1. Selezionare **Salva**.

### <a name="location-profile"></a>Profilo dell'ubicazione

1. Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione**.
1. Nel riquadro azioni selezionare **Nuovo** per creare un profilo di ubicazione per l'ubicazione di ordinamento.
1. Nell'intestazione, imposta i seguenti valori:

    - **ID profilo ubicazione:** *Ordinamento*
    - **Nome:** *Ordinamento*

1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Formato ubicazione** *PACK*
    - **Tipo di ubicazione:** *ORDINAMENTO*
    - **Usa rilevamento targa:** *Sì*
    - **Consenti articoli combinati:** *Sì*
    - **Consenti stati inventario combinati:** *Sì*

1. Selezionare **Salva**.

### <a name="locations"></a>Ubicazioni

1. Vai a **Gestione magazzino \> Impostazione \> Magazzino \> Ubicazioni**.
1. Deselezionare la casella di controllo **Genera cifre di controllo per ubicazione**.
1. Nel riquadro azioni, selezionare **Nuovo**, quindi impostare i seguenti valori:

    - **Magazzino:** *62*
    - **Ubicazione:** *Ordinamento*
    - **ID profilo ubicazione:** *Ordinamento*

1. Selezionare **Salva**.

### <a name="packing-profiles"></a>Profili imballaggio

1. Andare a **Gestione magazzino \> Impostazioni \> Imballaggio \> Profili imballaggio**.
1. Nel riquadro azioni, selezionare **Nuovo**, quindi impostare i seguenti valori:

    - **ID profilo imballaggio:** *Ordinamento*
    - **Descrizione:** *Ordinamento*
    - **Criteri imballaggio contenitore:** Lasciare vuoto questo campo.
    - **Modalità ID contenitore:** *Auto*
    - **Tipo di contenitore:** *PALLET 48X48*
    - **Crea automaticamente il contenitore alla chiusura:** Lasciare vuoto questo campo.

1. Selezionare **Salva**.

### <a name="wave-step-codes"></a>Codici del passaggio ondata

Se la funzionalità *Codice passaggio ondata a livello di organizzazione* è stata attivata, impostare il seguente codice.

1. Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Codici passaggio ondata**.
1. Nel riquadro azioni, selezionare **Nuovo**, quindi impostare i seguenti valori:

    - **Codice passaggio ondata:** *Ordinamento*
    - **Descrizione passaggio ondata:** *Ordinamento*
    - **Tipo di passaggio ondata:** *Modello di ordinamento*

1. Selezionare **Salva**.

### <a name="outbound-sorting-template"></a>Modello di ordinamento in uscita

Il modello di ordinamento controlla se vengono create posizioni di ordinamento, quali criteri vengono utilizzati e altri attributi del processo di ordinamento.

1. Andare a **Gestione magazzino \> Impostazioni \> Imballaggio \> Modello di ordinamento in uscita**.
1. Nel riquadro azioni selezionare **Nuovo** per creare un modello di ordinamento.
1. Nell'intestazione del nuovo modello, impostare i seguenti valori:

    - **ID modello di ordinamento in uscita:** *Ordinamento ondata*
    - **Descrizione:** *Ordinamento ondate*
    - **Tipo di modello di ordinamento:** *Domanda ondata*

        Questo campo definisce il processo per cui viene utilizzato il modello di ordinamento. Sono disponibili i valori seguenti:

        - **Domanda ondata** - Il modello di ordinamento viene utilizzato per il processo *Stoccaggio a parete*. Questo tipo di modello è utilizzato per ignorare la stazione del collo ed elaborare le scorte direttamente dall'ondata. È possibile utilizzare questo tipo solo se il metodo di elaborazione dell'ondata di **ordinamento**, è incluso nel modello di ondata.
        - **Contenitore** - Il modello di ordinamento viene utilizzato per il processo *Costruzione di pallet dopo imballaggio*. Questo tipo di modello viene utilizzato per elaborare i contenitori che sono chiusi nel centro di imballaggio e devono essere ordinati in pallet.

    - **Magazzino:** *62*
    - **Ubicazione:** *Ordinamento*

1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Ordina tipo di verifica:** selezionare *Scansione posizione*

        Questo campo definisce la verifica necessaria durante l'ordinamento. Sono disponibili i valori seguenti:

        - Nessuna priorità
        - Scansione targa
        - Scansione posizione

    - **Crea lavoro in posizione chiusa:** *Sì*

        Se questa opzione è impostata su *Sì*, quando la posizione è chiusa, verrà creato il lavoro per spostare le scorte nell'ubicazione di spedizione finale. Se è impostata su *No*, le scorte verranno immediatamente prelevate nell'ordine quando la posizione viene chiusa.

    - **Assegnazione di posizione:** *Manuale*

        Questo campo definisce il tipo di assegnazione della posizione. Sono disponibili i valori seguenti:

        - **Manuale** - L'utente deve sempre indicare in quale posizione le scorte devono essere ordinate.
        - **Automatico** - Il sistema inserisce automaticamente le scorte in una posizione quando possibile, in base alle suddivisioni del modello di ordinamento.

    - **Assegna criteri di posizione di ordinamento:** *Utilizza solo posizione vuota*

        Questo campo controlla se le scorte già presenti in posizioni di ordinamento vengono considerate durante l'assegnazione di una posizione per la domanda. Sono disponibili i valori seguenti:

        - **Utilizza solo posizione vuota** - Le posizioni che hanno già scorte associate verranno prese in considerazione
        - **Presupponi posizione vuota** - Qualsiasi scorta già presente nella posizione verrà ignorata durante l'assegnazione. Verranno utilizzate tutte le posizioni disponibili.

    - **Codice passaggio ondata:** *Ordinamento*

        Se la funzionalità *Codice passaggio ondata a livello di organizzazione* è attivata, anche il codice passaggio ondata *Ordinamento* deve essere impostato nei codici passaggio ondata.

    - **Chiudi automaticamente posizione ordinamento:** *Sì*

        Se questa opzione è impostata su *Sì*, la posizione di ordinamento verrà chiusa automaticamente quando tutto il lavoro che arriva in quella posizione risulta completato.

    - **Numero di posizioni di ordinamento:** *3*

        Questo campo definisce il numero massimo di posizioni di ordinamento che il sistema creerà.

    - **Prefisso posizione di ordinamento:** *SP-*

        Questo campo definisce il prefisso che il sistema assegna prima del numero di posizione.

    - **Imballa automaticamente posizione ordinamento:** *Sì*

        Se questa opzione è impostata su *Sì* le scorte nella posizione di ordinamento verranno imballate in un contenitore quando la posizione è chiusa.

    - **ID profilo imballaggio:** *Ordinamento*

        Questo campo definisce il profilo di imballaggio che verrà utilizzato quando la posizione di ordinamento viene imballata in un contenitore.

1. Nel riquadro azioni selezionare **Modifica query** per specificare i criteri utilizzati per questo modello di ordinamento.
1. Nella finestra di dialogo della query, nella scheda **Ordinamento**, selezionare **Nuovo** per aggiungere una riga e quindi impostare i seguenti valori:

    - **Tabella:** *Carica dettagli*
    - **Tabella derivata:** *Carica dettagli*
    - **Campo:** *ID spedizione*
    - **Direzione di ricerca:** *Crescente*

1. Selezionare **OK**.
1. È possibile che venga visualizzato il messaggio seguente: "Il raggruppamento verrà ripristinato. Continuare?". Selezionare **Sì**.

    Il pulsante **Interruzioni del modello di ordinamento in uscita** nel riquadro azioni diventa disponibile.

1. Nel riquadro azioni selezionare **Interruzioni del modello di ordinamento in uscita**.
1. Selezionare la casella di controllo **Raggruppa per campo** per raggruppare l'ID spedizione.

    Questa impostazione creerà una posizione di ordinamento per spedizione che è un contenitore nell'ondata.

1. Selezionare **OK**.

### <a name="wave-process-methods"></a>Metodi di elaborazione ondata

1. Andare a **Gestione magazzino \> Impostazione \> Ondate \> Metodi di elaborazione ondata**.
1. Nel riquadro azioni, seleziona **Rigenera metodi**.

    Il metodo **Ordinamento** viene aggiunto all'elenco dei metodi disponibili e il tipo di metodo di ondata *Spedizione* è selezionato per tale metodo.

### <a name="wave-templates"></a>Modelli ondata

Modificare il modello di ondata utilizzato per l'ordinamento della domanda ondata.

1. Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.
1. Nel campo **Tipo di modello ondata** selezionare *Spedizione*.
1. Selezionare il modello **62 Spedizione predefinita**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella Scheda dettaglio **Generale**, apportare le seguenti modifiche:

    - Impostare l'opzione **Elabora ondata al rilascio in magazzino** su *No*.
    - Impostare l'opzione **Assegna a ondate aperte** su *Sì*.

1. Nella scheda dettaglio **Metodi** impostare il metodo **ordinamento**.

    1. Nella griglia **Metodi rimanenti**, selezionare **ordinamento**.
    2. Selezionare il pulsante freccia DESTRA per spostare **ordinamento** nella griglia **Metodi selezionati**.
    3. Nella griglia **Metodi selezionati**, selezionare **ordinamento**.
    4. Impostare il campo **Codice passaggio ondata** su *Ordinamento*.

1. Selezionare **Salva**.

### <a name="mobile-device-menu-items"></a>Voci di menu del dispositivo mobile

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'intestazione, imposta i seguenti valori:

    - **Nome voce di menu** *Ordina*
    - **Titolo:** *Ordina*
    - **Modalità:** *Indiretta*
    - **Utilizza lavoro esistente:** *No*

1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Codice attività:** *Ordinamento in uscita*
    - **Usa guida al processo:** *Sì* (valore predefinito)
    - **ID modello di ordinamento in uscita:** *Ordinamento ondata*

1. Selezionare **Salva**.

### <a name="mobile-device-menu"></a>Menu del dispositivo mobile

1. Accedere a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.
1. Nell'elenco dei menu, selezionare **In uscita**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella griglia **Menu e voci di menu disponibili**, trovare e selezionare la voce di menu **Ordina** appena creata.
1. Selezionare il pulsante freccia DESTRA per spostare **Ordina** nell'elenco **Struttura menu**. In questo modo, si aggiunge la voce di menu al menu **In uscita**.
1. Selezionare **Salva**.

### <a name="location-directives"></a>Direttive ubicazione

È necessario creare direttive sull'ubicazione per guidare il lavoro creato dopo il completamento dell'ordinamento.

1. Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Nel campo **Tipo ordine di lavoro** selezionare *Prelievo scorte ordinate*.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'intestazione, imposta i seguenti valori:

    - **Sequenza:** *1*
    - **Nome:** *Stoccaggio in Portellone*

1. Nella Scheda dettaglio **Direttive ubicazione**, impostare i seguenti valori:

    - **Tipo di lavoro:** *Inserire*
    - **Sito:** *6*
    - **Magazzino:** *62*
    - **Codice direttiva:** lascia vuoto questo campo.
    - **Più SKU:** *No*

1. Seleziona **Salva** per rendere la Scheda dettaglio **Righe** disponibile.
1. Nella Scheda dettaglio **Righe**, selezionare **Nuovo**, quindi impostare i seguenti valori. Accettare i valori predefiniti per tutti gli altri campi.

    - **Numero progressivo:** *1*
    - **Da quantità:** *0*
    - **A quantità:** *1000000*

1. Seleziona **Salva** per rendere la Scheda dettaglio **Azioni direttiva ubicazione** disponibile.
1. Nella Scheda dettaglio **Azioni direttiva ubicazione**, selezionare **Nuovo**, quindi impostare i seguenti valori. Accettare i valori predefiniti per tutti gli altri campi.

    - **Numero progressivo:** *1*
    - **Nome:** *Portellone*

1. Selezionare **Salva** per rendere disponibile il pulsante **Modifica query** nella barra degli strumenti **Azioni direttiva ubicazione**.
1. Nella scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Modifica query**.
1. Nella finestra di dialogo della query, nella scheda **Intervallo**, trovare la riga in cui il campo **Campo** è impostato su *Ubicazione*. Impostare il campo **Criteri** per questa riga su *Portellone*.
1. Selezionare **OK** per confermare la modifica.

### <a name="work-classes"></a>Classi lavoro

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Classi di lavoro**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'intestazione, imposta i seguenti valori:

    - **ID classe lavoro:** *Ordinamento*
    - **Descrizione** *Ordinamento*
    - **Tipo ordine di lavoro:** *Prelievo scorte ordinate*

1. Selezionare **Salva**.

### <a name="work-templates"></a>Modelli di lavoro

1. Andare a **Gestione magazzino \> Lavoro \> Modelli di lavoro**.
1. Nel campo **Tipo ordine di lavoro** selezionare *Ordini cliente*.
1. Nella griglia, selezionare il modello di lavoro **62 Prelievo da imballare**.
1. Nel riquadro azioni, selezionare **Suddivisioni intestazione lavoro**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella riga in cui il campo **Nome campo** è impostato su *ID spedizione*, deselezionare la casella di controllo **Raggruppa per questo campo**.
1. Selezionare **Salva** e quindi chiudere la finestra di dialogo **Suddivisioni intestazione lavoro**.
1. Nel campo **Tipo ordine di lavoro** selezionare *Prelievo scorte ordinate*.
1. Selezionare **Nuovo** per creare un modello di lavoro.
1. Nella sezione **Panoramica**, impostare i seguenti valori. Accettare i valori predefiniti per tutti gli altri campi.

    - **Modello di lavoro:** *Prelievo ordinato*
    - **Descrizione modello di lavoro:** *Prelievo ordinato*

1. Selezionare **Salva** per rendere disponibile la Scheda dettaglio **Dettagli modello di lavoro** .
1. Nella sezione **Dettagli modello di lavoro**, si creeranno due righe. Selezionare **Nuovo**, quindi impostare i seguenti valori per la riga 1:

    - **Tipo di lavoro:** *Prelevare*
    - **Obbligatorio:** Selezionato (= *Sì*)
    - **ID classe lavoro:** *Ordinamento*

1. Selezionare di nuovo **Nuovo**, quindi impostare i seguenti valori per la riga 2:

    - **Tipo di lavoro:** *Inserire*
    - **Obbligatorio:** Selezionato (= *Sì*)
    - **ID classe lavoro:** *Ordinamento*

1. Selezionare **Salva**.

## <a name="example-scenario"></a>Scenario di esempio

Questo scenario simula una situazione in cui nel magazzino sono stoccati piccoli articoli in ubicazioni e devono essere imballarli in scatole prima di essere spediti e dove la funzionalità centro di imballaggio non è veramente appropriata. I lavoratori prelevano contemporaneamente ordini per più clienti e indirizzi diversi per aumentare la velocità di prelievo. Dopo che il prelievo è stato completato, i lavoratori arrivano all'ubicazione di ordinamento, dove gli articoli prelevati possono essere ordinati nella scatola corretta, in base ai criteri richiesti. In questo esempio, l'ID spedizione verrà utilizzato per determinare la scatola corretta, poiché ogni spedizione ha un indirizzo diverso. Dopo che tutti gli articoli del carico vengono imballati e ordinati per spedizione, le scatole verranno spostate nell'area di gestione temporanea e infine caricate su un camion.

Prima di iniziare lo scenario, assicurarsi che tutte le funzionalità standard del magazzino siano impostate correttamente per il proprio magazzino. Il magazzino Contoso standard *62* è usato per questo scopo. Le configurazioni standard non sono state modificate, oltre a quanto descritto nell'impostazione.

### <a name="create-demand"></a>Creare domanda

Prima di poter dimostrare la funzionalità, è necessario creare una domanda. Per questo scenario, verranno creati tre ordini cliente per tre diversi clienti per simulare indirizzi di consegna diversi. In questo modo, si creeranno tre spedizioni distinte.

Prima di creare ordini cliente e spedizioni, verificare che le ubicazioni di prelievo dispongano di scorte sufficienti per tutti gli articoli degli ordini. Rivedere le impostazioni della direttiva di ubicazione per confermare le ubicazioni di prelievo utilizzate per il prelievo degli ordini cliente. Se è necessario regolare le scorte, puoi creare movimenti manuali, utilizza il rifornimento o utilizza qualsiasi altro flusso, come richiesto. Quindi prenotare le scorte.

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Selezionare **Nuovo** per creare un ordine cliente per ordine 1.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Cliente:** *US-001*
    - **Magazzino:** *62*

1. Selezionare **OK**.
1. Una nuova riga viene aggiunta alla Scheda dettaglio **Righe ordine cliente**. Imposta i valori seguenti:

    - **Numero articolo:** *A0001*
    - **Quantità:** *5*

1. Seleziona **Aggiungi riga** per aggiungere una seconda riga, quindi imposta i seguenti valori:

    - **Numero articolo:** *A0002*
    - **Quantità:** *10*

1. Ripetere i passaggi seguenti per ciascuna riga di vendita nell'ordine per prenotare le relative scorte:

    1. Nella scheda dettaglio **Righe ordine cliente**, nel menu **Scorte**, seleziona **Prenotazione**.
    1. Nella pagina **Prenotazione** selezionare **Prenota lotto** e chiudere la pagina.
    1. Selezionare **Salva**.

1. Selezionare **Nuovo** per creare un ordine cliente per ordine 2.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Cliente:** *US-004*
    - **Magazzino:** *62*

1. Selezionare **OK**.
1. Una nuova riga viene aggiunta alla Scheda dettaglio **Righe ordine cliente**. Imposta i valori seguenti:

    - **Numero articolo:** *A0001*
    - **Quantità:** *7*

1. Seleziona **Aggiungi riga** per aggiungere una seconda riga, quindi imposta i seguenti valori:

    - **Numero articolo:** *A0002*
    - **Quantità:** *3*

1. Ripetere i passaggi seguenti per ciascuna riga di vendita nell'ordine per prenotare le relative scorte:

    1. Nella scheda dettaglio **Righe ordine cliente**, nel menu **Scorte**, seleziona **Prenotazione**.
    1. Nella pagina **Prenotazione** selezionare **Prenota lotto** e chiudere la pagina.
    1. Selezionare **Salva**.

1. Selezionare **Nuovo** per creare un ordine cliente per ordine 3.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Cliente:** *US-007*
    - **Magazzino:** *62*

1. Selezionare **OK**.
1. Una nuova riga viene aggiunta alla Scheda dettaglio **Righe ordine cliente**. Imposta i valori seguenti:

    - **Numero articolo:** *A0001*
    - **Quantità:** *8*

1. Per prenotare le scorte per la riga di vendita, attenersi alla procedura riportata di seguito.

    1. Nella scheda dettaglio **Righe ordine cliente**, nel menu **Scorte**, seleziona **Prenotazione**.
    1. Nella pagina **Prenotazione** selezionare **Prenota lotto** e chiudere la pagina.
    1. Selezionare **Salva**.

Completare la seguente procedura per rilasciare ogni ordine cliente al magazzino. Verranno create tre spedizioni diverse. Quindi si aggiungeranno tutte e tre le spedizioni a una nuova ondata.

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Nella griglia, selezionare il primo ordine cliente creato.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.

    Viene visualizzato un messaggio informativo che mostra l'ID ondata e l'ID spedizione creati.

1. Ripetere i passaggi precedenti per rilasciare gli ordini cliente 2 e 3 al magazzino. Si noti che il messaggio informativo visualizzato indica che è stata aggiunta una spedizione all'ondata creata al momento del rilascio dell'ordine cliente 1.
1. Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.
1. Selezionare l'ID ondata creato dal rilascio degli ordini cliente per aprire la pagina **Ondate**. Questa pagina mostra i dettagli dell'ondata. La Scheda dettaglio **Righe ondata** mostra le spedizioni create.

    È ora necessario creare lavoro per portare gli articoli dalle ubicazioni di prelievo all'ubicazione di ordinamento.

1. Nel riquadro azioni selezionare **Elabora**.

    Durante l'elaborazione delle ondate, il metodo di ordinamento utilizzerà il modello di ordinamento per assegnare le scorte alle posizioni di ordinamento. Al termine dell'elaborazione dell'ondata viene visualizzato un messaggio informativo che indica che l'ondata è stata pubblicata e che il lavoro è stato creato.

1. Nel riquadro azioni, nella scheda **Ondata**, nel gruppo **Informazioni correlate**, selezionare **Lavoro** per visualizzare il lavoro creato. Prendere nota dell'ID lavoro.
1. Selezionare **Gestione magazzino \> Imballaggio e containerizzazione \> Assegnazioni di posizioni di ordinamento in uscita**.
1. Nella colonna di sinistra è possibile visualizzare la posizione di ordinamento in uscita creata per ciascuna spedizione.
1. Nella Scheda dettaglio **Criteri di posizione di ordinamento**, è possibile visualizzare l'ID spedizione per quella posizione.

Un ID lavoro è stato creato per portare le scorte dalle ubicazioni di prelievo all'ubicazione di ordinamento. Per completare il lavoro, sarà necessario l'ID lavoro creato durante l'elaborazione dell'ondata.

### <a name="sales-order-picking-to-the-sorting-location"></a>Prelievo dell'ordine cliente nell'ubicazione di ordinamento

1. Accedere all'app per dispositivi mobili come lavoratore nel magazzino *62*.
1. Nel menu principale, selezionare **In uscita**.
1. Nel menu **In uscita**, selezionare **Prelievo vendite**.
1. Selezionare il campo **ID**, quindi immettere l'ID lavoro dall'elaborazione dell'ondata.
1. Conferma l'inserimento.

    Successivamente, viene richiesto di immettere una targa di destinazione. Si noti che la riga 1 dell'ordine di vendita 1 è ciò che deve essere prelevato e aggiunto alla targa di destinazione. Vengono visualizzati il numero, la quantità, la descrizione e l'ubicazione di prelievo dell'articolo.

1. Nel campo **Targa destinazione**, immettere il numero di targa di destinazione.

    Si preleveranno tutte le righe create dall'ondata elaborata sulla stessa targa di destinazione.

1. Conferma l'inserimento.

    L'app per dispositivi mobili ora presenta una serie di pagine **Prelievo** che indicano l'ubicazione di prelievo e l'articolo e la quantità che devono essere prelevati. Dopo che l'elemento prelevato è stato aggiunto alla targa, si confermerà il lavoro di prelievo. L'ultima pagina sarà il lavoro per stoccare gli articoli prelevati nell'ubicazione di ordinamento.

1. Confermare il primo lavoro di prelievo.
1. Viene visualizzato il lavoro di prelievo successivo. Confermare il prelievo.
1. Continuare a confermare il lavoro di prelievo rimanente.
1. L'ultimo passaggio consiste nel completare il lavoro di stoccaggio. Confermare lo stoccaggio nell'ubicazione di ordinamento.

    Viene visualizzato il messaggio "Lavoro completato".

1. Chiudere **Prelievo vendite** nell'app per dispositivi mobili.

### <a name="sortingput-to-wall"></a>Ordinamento/Stoccaggio a parete

Ora che tutte le scorte sono state stoccate nella posizione di ordinamento, devono essere ordinate nell'ubicazione di ordinamento corretta.

1. Accedere all'app per dispositivi mobili.
1. Nel menu principale, selezionare **In uscita**.
1. Nel menu **In uscita**, selezionare **Ordina** per iniziare a ordinare gli articoli.
1. Nel campo **TARGA/CON**, immettere la targa di destinazione del lavoro dell'ordine cliente prelevato.
1. Conferma l'inserimento.
1. Immettere il numero di articolo da ordinare per primo.
1. Il sistema determina la prima posizione di ordinamento che deve essere visualizzata. Confermare la posizione di ordinamento.
1. Viene richiesto di assegnare una targa alla posizione di ordinamento. Selezionare il campo **TARGA**, immettere un numero di targa, quindi confermare l'immissione.

    Poiché la posizione di ordinamento è correlata all'ID spedizione, si ordineranno gli articoli prelevati in una targa specifica per la spedizione in uscita e l'ordine cliente.

    La pagina successiva mostra l'ID articolo, la quantità, l'ID posizione di ordinamento e gli ID targa "da" (prelievo) e "a" (ordinamento). Le informazioni contenute in questa pagina indicano di ordinare l'articolo e le quantità specificati dalla targa di prelievo nella targa di ordinamento.

1. Confermare la posizione di ordinamento.
1. Ordinare gli articoli nella prima posizione di ordinamento. Al termine, il sistema indirizza alla posizione di ordinamento successiva.
1. Ripetere questo processo per tutte le righe prelevate nell'ordine di lavoro. È necessario usare questo processo anche quando vi sono più righe di prelievo che hanno lo stesso numero di articolo.

    Quando si ripete questo processo per tutti gli articoli, il sistema valuta i criteri dall'articolo sottoposto a scansione successivo (riga di lavoro) e determina in quale posizione di ordinamento deve essere stoccato. L'articolo viene automaticamente stoccato nella posizione di ordinamento corretta. A seconda della configurazione di conferma, viene anche richiesto di confermare questa azione immettendo il numero di posizione o l'ID targa.

    > [!NOTE]
    > Se l'ordinamento automatico è attivato, la sostituzione manuale non è disponibile.

1. Al termine, in Microsoft Dynamics 365 Supply Chain Management, aprire la pagina **Assegnazioni di posizioni di ordinamento in uscita** per esaminare lo stato delle posizioni.

    - Se le posizioni vengono chiuse automaticamente, selezionare **Mostra chiuse** per mostrare le posizioni chiuse.
    - Si noti che le transazioni delle posizioni di ordinamento sono visualizzate. L'articolo e la quantità elaborati tramite la posizione sono visualizzati.

    Quando si configura il modello di ordinamento in uscita, si imposta l'opzione **Chiudi automaticamente posizione ordinamento** su *Sì*. Pertanto, la posizione viene automaticamente chiusa dopo lo stoccaggio nella stessa delle ultime scorte previste. Lo stato delle posizioni di ordinamento è **Chiusa** ed è stato creato lavoro per spostare le scorte ordinate nell'ubicazione *Portellone*.

1. Completare il lavoro di prelievo delle scorte ordinate per spostare le scorte nell'ubicazione di spedizione. Quando le scorte sono pronte, confermarne la spedizione.

> [!NOTE]
> Affinché il lavoro di prelievo delle scorte ordinate venga elaborato correttamente, una voce di menu del dispositivo mobile con un ID classe di lavoro dove il campo **Tipo ordine di lavoro** è impostato su *Prelievo scorte ordinate* deve essere usato per il movimento e il processo di caricamento.

### <a name="manually-close-a-position-optional"></a>Chiudere manualmente una posizione (facoltativo)

Se le posizioni di ordinamento devono essere chiuse manualmente, l'opzione **Chiudi automaticamente posizione ordinamento** per il modello di ordinamento in uscita deve essere impostata su *No* e la chiusura deve essere eseguita prima che le scorte possano essere spostate nell'area Portellone. Le posizioni possono essere chiuse in vari modi:

- Via l'app di magazzino:

    - L'utente può eseguire la scansione di uno degli articoli già presenti nella posizione e quindi selezionare **Chiudi** per chiudere la posizione.
    - Se l'utente esegue la scansione di un contenitore che è già stato ordinato, viene visualizzato un messaggio di errore. Tuttavia, l'utente può comunque continuare a chiudere la posizione.

- Nella pagina **Assegnazioni di posizioni di ordinamento in uscita** di Microsoft Dynamics 365 Supply Chain Management:

    - L'utente può selezionare il record della posizione di ordinamento in uscita e quindi selezionare **Chiudi posizione** nel riquadro azioni.

## <a name="tips"></a>Suggerimenti

- Gli articoli non possono essere spostati tra le posizioni dopo che sono stati assegnati a una di queste. Il sistema valuta la quantità di ogni articolo da assegnare a una specifica posizione.
- Il modello di ordinamento può essere configurato per creare automaticamente contenitori quando le posizioni sono chiuse. Questo approccio creerà una struttura ID contenitore standard basata sul profilo di imballaggio specificato.

> [!IMPORTANT]
> Dopo che il lavoro di movimento è stato creato dall'ubicazione di ordinamento, non è necessario annullare il lavoro. In caso contrario, la posizione e i relativi contenitori verranno eliminati dal sistema e non saranno disponibili per ulteriori elaborazioni. Anche le scorte verranno rimosse.
