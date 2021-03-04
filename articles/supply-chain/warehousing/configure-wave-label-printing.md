---
title: Configurare e utilizzare la stampa di etichette ondata
description: Questo argomento descrive la stampa di etichette ondata e spiega come configurarla.
author: GarmMSFT
manager: PJacobse
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSDocumentRouting, WHSWaveTableListPage, WHSPostMethod, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelType, WHSWaveLabelTemplateGroup, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: PJacobse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 6314fd25d8d8a0013984d484f57a832c26f82b5a
ms.sourcegitcommit: a26e4963d40796da21ce6581cfb2f4d9db4f6776
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "4431589"
---
# <a name="set-up-and-use-wave-label-printing"></a>Configurare e utilizzare la stampa di etichette ondata

[!include [banner](../includes/banner.md)]

La stampa di etichette ondata offre un approccio alternativo alla stampa di etichette introducendo un nuovo metodo di passaggio ondata che consente di creare e stampare etichette direttamente dal modello di ondata durante l'esecuzione dell'ondata. Pertanto, le etichette saranno già disponibili prima che i lavoratori eseguano l'ordine di lavoro su un dispositivo mobile. I lavoratori possono quindi associare le etichette necessarie durante il prelievo anziché dopo il prelievo.

La stampa di etichette ondata utilizza Zebra Programming Language (ZPL) per creare layout di etichette. Un layout di etichetta è diviso in tre sezioni (intestazione, corpo e piè di pagina) per consentire etichette con struttura ripetuta. I modelli di etichette ondata indicano al sistema quale layout di etichetta utilizzare. Gli utenti possono specificare quale stampante viene utilizzata. Possono anche stampare etichette su più stampanti contemporaneamente, come necessario. La pagina **Storico etichette ondata** mostra un record di tutte le etichette che sono state create utilizzando questa configurazione.

È possibile stampare e fascicolare etichette in base alle intestazioni di lavoro, stampare etichette di interruzione per intestazione di lavoro e stampare etichette di contenuto di contenitore, etichette di cassa e altre etichette simili.

> [!NOTE]
> Questa funzionalità non sostituisce la funzionalità di stampa di etichette esistente basata sulla distribuzione dei documenti.

La stampa di etichette ondata offre i seguenti miglioramenti:

- Stampa di etichette in base al numero di cartoni su una singola riga di lavoro, senza utilizzare la containerizzazione (un "cartone" è un'unità designata su righe di gruppi di sequenze di unità).
- Stampa di diverse sequenze di etichette (ad esempio etichette di cartoni e pallet).
- Inclusione dell'enumerazione di etichette (ad esempio, 1/124, 2/124, ... 124/124) e definizione dell'intervallo di enumerazione (ad esempio, riga di lavoro, riga di carico o spedizione).
- Creazione e stampa di un ID polizza di carico sulle etichette prima che venga generata la polizza di carico.
- Creazione di un codice SSCC univoco per ciascun cartone e inclusione in ciascuna etichetta.
- Creazione di sequenze numeriche conformi a GS1 per ID polizza di carico e SSCC.
- Ristampa di etichette da dispositivi mobili e dal rich client.
- Annullamento delle etichette (ad esempio, in scenari di prelievo in difetto) e ristampa delle stesse.
- Pulire lo storico delle etichette ondata.
- I miglioramenti ai layout di distribuzione dei documenti sono condivisi tra i layout di distribuzione dei documenti e quelli delle etichette ondata (per ulteriori informazioni, vedere [Layout di distribuzione dei documenti per le targhe](../warehousing/document-routing-layout-for-license-plates.md)).

Questi miglioramenti rendono più efficiente l'etichettatura dei cartoni prima della pallettizzazione. Sono particolarmente utili per le aziende che spediscono a grandi rivenditori che confermano automaticamente la ricezione degli ordini sottoponendo a scansione ciascun cartone separatamente.

> [!NOTE]
> È possibile implementare gli scenari di configurazione descritti in questo argomento separatamente o in combinazione, a seconda delle esigenze aziendali. È possibile progettare diversi modelli di etichette ondata che funzionano in sequenza (come illustrato nello scenario 3). Ad esempio, è possibile utilizzare lo scenario 1 per stampare etichette di cartoni e lo scenario 2 per stampare etichette di pallet (se i pallet in stock variano quanto a dimensioni e composizione).

## <a name="turn-on-the-wave-label-printing-feature"></a>Attivare la funzionalità di stampa di etichette ondata

Per poter utilizzare la funzionalità *Stampa di etichette ondata*, è necessario attivarla nel sistema. Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Stampa di etichette ondata*

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a>Scenario 1: stampa di etichette ondata in cui viene generata una singola etichetta ondata

Questo scenario mostra come un'azienda può stampare etichette indirizzo per un grande rivenditore che conferma automaticamente la ricezione degli ordini sottoponendo a scansione ogni cartone separatamente.

Questo scenario mostra il flusso end-to-end.

### <a name="make-demo-data-available"></a>Rendi disponibili i dati dimostrativi

Per eseguire questo scenario, i dati dimostrativi devono essere installati ed è necessario selezionare la persona giuridica **USMF**.

### <a name="make-sure-that-the-wave-label-method-is-available"></a>Assicurarsi che il metodo di etichetta ondata sia disponibile

Potrebbe essere necessario rigenerare i metodi di elaborazione ondata per rendere disponibile il metodo di stampa di etichette ondata.

1. Andare a **Gestione magazzino \> Impostazione \> Ondate \> Metodi di elaborazione ondata**.
1. Verificare che **waveLabelPrinting** sia nell'elenco. Se non lo è, selezionare **Rigenera metodi** nel riquadro azioni per aggiungerlo.

### <a name="configure-a-wave-template"></a>Configurare un modello di ondata

I modelli di ondata consentono di collegare istanze specifiche dei metodi di ondata a un modello di etichetta ondata corrispondente.

1. Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.
1. Selezionare un modello, ad esempio **62 Spedizione predefinita**.
1. Nella Scheda dettaglio **Metodi**, spostare il metodo **Stampa di etichette ondata** nella colonna **Metodi selezionati**.
1. Nella colonna **Metodi selezionati**, seleziona il metodo **Stampa di etichette ondata** e impostare il relativo campo **Codice passaggio ondata** su *PrintLabel*. Per ulteriori informazioni sui codici del passaggio ondata, vedere [Codici del passaggio ondata](wave-step-codes.md).

### <a name="create-a-wave-label-layout"></a>Creare un layout di etichetta ondata

Il layout di etichetta controlla quali informazioni sono stampate sull'etichetta e come sono disposte. Nel layout si inserisce il codice ZPL inviato alla stampante.

1. Andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Layout etichette ondata**.
1. Crea un record con le seguenti impostazioni:

    - **ID layout etichetta:** *Cartone*
    - **Descrizione:** *Cartone (SSCC)*

1. Nel riquadro azioni selezionare **Salva**.
1. Nel riquadro azioni selezionare **Impostazioni di riga delle etichette ondata**.

    Viene visualizzata la pagina **Impostazioni di riga delle etichette ondata**. Qui è possibile configurare la parte dinamica dell'etichetta.

1. Aggiungere una riga con le seguenti impostazioni:

    - **ID riga:** *WaveLabel*
    - **Nome tabella di righe:** *WHSWaveLabel*
    - **Posizione di inizio riga:** *0*

        Questo campo definisce la posizione verticale iniziale della riga sull'etichetta.

    - **Altezza riga:** *0*

        Questo campo definisce l'altezza di ogni riga (in punti), secondo lo standard ZPL. L'altezza della riga è positiva per le etichette orizzontali e negativa per le etichette verticali. Poiché in questo esempio c'è una sola riga, è possibile impostare il valore su *0* (zero).

    - **Righe per pagina:** *1*

        Questo campo definisce il numero di righe che è possibile stampare su ciascuna etichetta.

        > [!NOTE]
        > Questa impostazione causerà la stampa di un'etichetta ZPL separata per ciascun record nella tabella delle etichette ondata.

1. Chiudere la pagina.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungere una riga con le seguenti impostazioni:

    - **Tabella:** *Righe di lavoro*
    - **Tabella derivata:** *Righe di lavoro*
    - **Campo:** *Tipo di lavoro*
    - **Criteri:** *Prelievo*

    Questa query garantisce che sull'etichetta vengano stampate solo le righe di lavoro di tipo prelievo, non le righe di lavoro di tipo stoccaggio.

1. Se si desidera poter stampare l'ID polizza di carico, nella scheda **Join**, selezionare la tabella **Righe lavoro** e unirvi la tabella **Spedizioni**.
1. Chiudere la finestra di dialogo dell'editor di query.
1. La Scheda dettaglio **Layout testo stampante** ha tre sezioni in cui è possibile scrivere il codice della stampante: **Sezione di intestazione**, **Sezione del corpo** e **Sezione piè di pagina**. Nella sezione **Sezione di intestazione**, nel campo **Intestazione etichetta**, immettere il codice per l'intestazione necessaria. Ad esempio, se si utilizzano stampanti Zebra, è possibile utilizzare il codice seguente.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. Nella sezione **Sezione del corpo**, nel campo **Corpo etichetta**, immettere il codice ZPL per il corpo necessario. Ecco un esempio.

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. Nella sezione **Sezione del corpo**, nel campo **Piè di pagina etichetta**, immettere il codice ZPL per il piè di pagina necessario. Ecco un esempio.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Questa configurazione stamperà una copia di ciascuna etichetta. Se sono necessarie più copie (ad esempio una copia per ciascun lato del pallet), impostare il valore **n** per la sezione **\^PQn** nel piè di pagina sul numero di copie necessarie. Ad esempio, per stampare quattro copie di ciascuna etichetta, specificare **\^PQ4**.

L'etichetta è ora pronta per l'uso.

### <a name="create-a-wave-label-type"></a>Creare un tipo di etichetta ondata

I tipi di etichetta ondata vengono utilizzati per collegare modelli di etichette ondata a un'unità su righe di gruppi di sequenze unità.

1. Andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Tipi di etichette ondata**.
1. Aggiungere un tipo di etichetta ondata con le seguenti impostazioni:

    - **Tipo di etichetta:** *Cartone*
    - **Descrizione:** *Cartone*

### <a name="set-up-unit-sequence-groups"></a>Imposta gruppi di sequenze unità

Quindi, impostare il gruppo di sequenze di unità per il tipo di etichetta ondata.

1. Fare clic su **Gestione magazzino \> Impostazione \> Magazzino \> Gruppi di sequenze unità**.
1. Selezionare il gruppo **unità scatola pallet**.
1. Per la riga **Scatola**, impostare il campo **Tipo di livello ondata** su *Scatola*.

### <a name="create-a-wave-label-template"></a>Creare un modello di etichetta ondata

Ora si creerà il modello di etichetta ondata per il tipo di etichetta ondata.

1. Andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Modelli di etichette ondata**.
1. Aggiungere un modello di livello ondata e impostare i seguenti valori nell'intestazione:

    - **Nome modello etichetta:** *Etichette cartoni*
    - **Descrizione:** *Etichette cartoni*
    - **Codice passaggio ondata:** *PrintLabel*
    - **Magazzino:** *62*

1. Nella Scheda dettaglio **Generale**, impostare il campo **Tipo di etichetta ondata** su *Cartone*.
1. Nella Scheda dettaglio **Dettagli modello di etichette ondata**, aggiungere una nuova riga con le seguenti impostazioni:

    - **ID layout etichetta:** *Cartone*
    - **Nome stampante:** selezionare una stampante ZPL appropriata.
    - **Esegui query:** *Sì* (questa impostazione è facoltativa, ma è consigliata per prestazioni ottimali).

1. Nel riquadro azioni selezionare **Salva**.
1. Facoltativo: se si sta progettando un'etichetta specifica per il cliente, è necessario creare una query per trovare il conto del cliente. Nella scheda dettaglio **Dettagli modello di etichette ondata**, selezionare **Modifica query**. Quindi, nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungere una riga con le seguenti impostazioni:

    - **Tabella:** *Spedizioni*
    - **Tabella derivata:** *Spedizioni*
    - **Campo:** *Numero di conto*
    - **Criteri:** Immettere il numero di conto cliente pertinente.

    Al termine, selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.

1. Nel riquadro azioni, selezionare **Modifica query** per aprire la finestra di dialogo dell'editor di query per l'intero modello di etichetta.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Ordinamento**, aggiungere una riga con le seguenti impostazioni:

    - **Tabella:** *Righe di lavoro*
    - **Tabella derivata:** *Righe di lavoro*
    - **Campo:** *ID riga di carico di riferimento (ID record)*
    - **Direzione di ricerca:** *Crescente*

1. Selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.
1. Viene visualizzato un messaggio che richiede di confermare l'operazione di ripristino del raggruppamento. Selezionare **Sì** per continuare.
1. Nel riquadro azioni selezionare **Gruppo di modelli di etichette ondata**.
1. Nella finestra di dialogo **Gruppo di modelli di etichette ondata**, selezionare la riga in cui il campo **Nome campo di riferimento** è impostato su *ID riga di carico di riferimento*, quindi selezionare la casella di controllo **ID build etichetta** per questa riga.

    > [!NOTE]
    > Questa configurazione creerà una sequenza di etichette ("Cartone 1 di X") per riga di carico in tutta l'ondata, indipendentemente dall'impostazione del raggruppamento di lavoro. Questa sequenza di etichette può essere stampata sul layout di etichetta.

### <a name="configure-number-sequence-extensions"></a>Configurare le estensioni di sequenza numerica

Le estensioni di sequenza numerica controllano la conformità GS1 delle sequenze numeriche specifiche. Questa configurazione è facoltativa per lo scenario corrente. Per ulteriori informazioni e istruzioni sulla configurazione, vedere [Configurare le estensioni di sequenza numerica](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Creare un ordine cliente e rilasciarlo nel magazzino

1. Andare a **Vendite e marketing \> Ordine cliente \> Tutti gli ordini cliente**.
1. Crea un ordine cliente con le seguenti impostazioni:

    - **Conto cliente:** *US-001*
    - **Magazzino:** *62*

1. Aggiungere due righe di ordine cliente con le seguenti impostazioni:

    - Riga ordine cliente 1:

        - **Numero articolo:** *A0001*
        - **Quantità:** *9024*
        - **Unità:** *unità* (9024 unità = 376 scatole = 47 pallet)

    - Riga ordine cliente 2:

        - **Numero articolo:** *A0002*
        - **Quantità:** *9016*
        - **Unità:** *unità* (9016 unità = 322 scatole = 46 pallet)

    > [!NOTE]
    > Gli articoli e le quantità forniti qui sono solo esempi. Devono utilizzare il gruppo di sequenze di unità definito in precedenza, conversioni di unità appropriate da *unità* a *scatola* a *pallet* devono essere definite per gli stessi e devono avere stock nel magazzino *62*. Per ulteriori informazioni, vedere [Unità di misura e politiche di stoccaggio](unit-measure-stocking-policies.md).

1. Selezionare la riga ordine cliente 1. Nella sezione **Riga ordine cliente**, nel menu **Scorte**, selezionare **Prenotazioni**.
1. Nella pagina **Prenotazione** del riquadro azioni, selezionare **Prenota lotto** e chiudere la pagina.
1. Ripetere i passaggi 4 e 5 per la riga ordine cliente 2.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.

    Si verificano gli eventi seguenti:

    - Il sistema elabora la spedizione creata utilizzando il modello che include il passaggio di stampa dell'etichetta. Il layout di etichetta verrà utilizzato per definire il formato dell'etichetta e il risultato sarà un'etichetta stampata sulla stampante selezionata nel modello di etichetta.
    - Le etichette ondata vengono generate e stampate. Il numero di etichette sarà uguale al numero di cartoni (in questo esempio, 376 etichette per scatole per la riga 1 e 322 etichette per scatole per la riga 2).
    - Viene generato un nuovo ID polizza di carico per le spedizioni. Se sono state configurate le estensioni della sequenza numerica, gli ID etichetta ondata avranno il formato numerico **SSCC-18**. 

È possibile visualizzare e ristampare le etichette ondata dalle seguenti pagine. Nel riquadro azioni di ogni pagina della scheda **Spedizioni** nel gruppo **Informazioni correlate**, selezionare **Etichette ondata**.

- Tutte le spedizioni \> Dettagli spedizione
- Tutti i carichi \> Dettagli carico
- Tutte le ondate
- Etichette ondata
- Storico etichette ondata

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a>Scenario 2: stampa di etichette ondata per containerizzazione (senza record di etichette ondata)

Questo scenario consente di stampare etichette ondata quando si utilizza la containerizzazione per suddividere automaticamente gli articoli in cartoni e quindi non è necessario un record di etichette ondata. In questo caso, l'ID contenitore funge da segnaposto per SSCC.

Di seguito sono riportate le principali differenze tra questo scenario e lo scenario 1:

- **Modelli di etichette ondata:** non si selezionerà un tipo di etichetta ondata nel modello di etichetta ondata e non sarà necessario un raggruppamento di build di etichetta. Altrimenti, si configurerà il modello di etichetta ondata e si eseguirà il collegamento al modello di ondata nello stesso modo descritto nello scenario 1. È necessario lasciare vuoto il tipo di etichetta ondata per impedire la generazione di etichette ondata.
- **Layout etichette ondata:** si configureranno le impostazioni delle righe del layout di etichetta ondata per le righe di lavoro anziché i record di etichetta ondata. È necessario configurare l'impostazione della riga per il layout di etichetta utilizzando la tabella **WHSWorkLine** anziché la tabella **WHSWaveLabel**. L'impostazione **Righe per pagina** controlla il numero di righe che avrà la sezione del corpo. 

Questa configurazione è adatta anche per scenari aziendali in cui più articoli diversi sono imballati in una scatola etichettata o in un pallet e questo processo di imballaggio può essere definito dalla creazione di lavoro (ad esempio, lavoro raggruppato per spedizione).

Questo scenario mostra il flusso end-to-end.

### <a name="make-demo-data-available"></a>Rendi disponibili i dati dimostrativi

Per eseguire questo scenario, i dati dimostrativi devono essere installati ed è necessario selezionare la persona giuridica **USMF**.

### <a name="make-sure-that-the-wave-label-method-is-available"></a>Assicurarsi che il metodo di etichetta ondata sia disponibile

Potrebbe essere necessario rigenerare i metodi di elaborazione ondata per rendere disponibile il metodo di stampa di etichette ondata.

1. Andare a **Gestione magazzino \> Impostazione \> Ondate \> Metodi di elaborazione ondata**.
1. Verificare che **waveLabelPrinting** sia nell'elenco. Se non lo è, selezionare **Rigenera metodi** nel riquadro azioni per aggiungerlo.

### <a name="set-up-a-wave-template"></a>Impostare un modello di ondata

I modelli di ondata consentono di collegare istanze specifiche dei metodi di ondata a un modello di etichetta ondata corrispondente.

1. Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.
1. Selezionare un modello, ad esempio **Contaneirizzazione 63**.
1. Nella Scheda dettaglio **Metodi**, spostare il metodo **Stampa di etichette ondata** nella colonna **Metodi selezionati**.
1. Nella colonna **Metodi selezionati**, seleziona il metodo **Stampa di etichette ondata** e impostare il relativo campo **Codice passaggio ondata** su *PrintLabel*. Per ulteriori informazioni sui codici del passaggio ondata, vedere [Codici del passaggio ondata](wave-step-codes.md).

### <a name="create-a-wave-label-layout"></a>Creare un layout di etichetta ondata

1. Andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Layout etichette ondata**.
1. Crea un record con le seguenti impostazioni:

    - **ID layout etichetta:** *Cartone*
    - **Descrizione:** *Cartone (SSCC)*

1. Nel riquadro azioni selezionare **Salva**.
1. Nel riquadro azioni selezionare **Impostazioni di riga delle etichette ondata**.

    Viene visualizzata la pagina **Impostazioni di riga delle etichette ondata**. Qui è possibile configurare la parte dinamica dell'etichetta.

1. Aggiungere una riga con le seguenti impostazioni:

    - **ID riga:** *WorkLine*
    - **Nome tabella di righe:** *WHSWorkLine*
    - **Posizione di inizio riga:** *500*

        Questo campo definisce la posizione verticale iniziale della riga sull'etichetta.

    - **Altezza riga:** *-50*

        Questo campo definisce l'altezza di ogni riga. L'altezza della riga è positiva per le etichette orizzontali e negativa per le etichette verticali.

    - **Righe per pagina:** *5*

        Questo campo definisce il numero di righe che è possibile stampare su ciascuna etichetta.

        > [!NOTE]
        > Questa configurazione stamperà diverse etichette ZPL per lavoro, dove ogni pagina può contenere fino a cinque righe di lavoro. Ad esempio, se un'etichetta viene stampata per un contenitore che ha 12 righe, verranno stampate tre etichette. Se si desidera stampare un'etichetta separata per ogni riga di prelievo, impostare questo valore su *1*.

1. Chiudere la pagina.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungere una riga con le seguenti impostazioni:

    - **Tabella:** *Righe di lavoro*
    - **Tabella derivata:** *Righe di lavoro*
    - **Campo:** *Tipo di lavoro*
    - **Criteri:** *Prelievo*

1. Se si desidera poter stampare l'ID polizza di carico, nella scheda **Join**, selezionare la tabella **Righe lavoro** e unirvi la tabella **Spedizioni**.
1. Chiudere la finestra di dialogo dell'editor di query.
1. La Scheda dettaglio **Layout testo stampante** ha tre sezioni in cui è possibile scrivere il codice della stampante: **Sezione di intestazione**, **Sezione del corpo** e **Sezione piè di pagina**. Nella sezione **Sezione di intestazione**, nel campo **Intestazione etichetta**, immettere il codice per l'intestazione necessaria. Ad esempio, se si utilizzano stampanti Zebra, è possibile utilizzare il codice seguente.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. Nella sezione **Sezione del corpo**, nel campo **Corpo etichetta**, immettere il codice ZPL per il corpo necessario. Ecco un esempio.

    ```plaintext
    <Row name="WorkLine">
    <Heading>
    //Optional heading for section of rows
    </Heading>
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWorkLine.ItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWorkLine.QtyWork$ ^FS
    </Row>
    ```

1. Nella sezione **Sezione del corpo**, nel campo **Piè di pagina etichetta**, immettere il codice ZPL per il piè di pagina necessario. Ecco un esempio.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Questa configurazione stamperà una copia di ciascuna etichetta. Se sono necessarie più copie (ad esempio una copia per ciascun lato del pallet), impostare il valore **n** per la sezione **\^PQn** nel piè di pagina sul numero di copie necessarie. Ad esempio, per stampare quattro copie di ciascuna etichetta, specificare **\^PQ4**.

L'etichetta è ora pronta per l'uso.

### <a name="create-a-wave-label-template"></a>Creare un modello di etichetta ondata

1. Andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Modelli di etichette ondata**.
1. Aggiungere un modello di livello ondata e impostare i seguenti valori nell'intestazione:

    - **Nome modello etichetta:** *Etichette contenitori*
    - **Descrizione:** *Etichette contenitori*
    - **Codice passaggio ondata:** *PrintLabel*
    - **Magazzino:** *63*

1. Nella Scheda dettaglio **Dettagli modello di etichette ondata**, aggiungere una riga con le seguenti impostazioni:

    - **ID layout etichetta:** *Contenitore*
    - **Nome stampante:** selezionare una stampante ZPL appropriata.
    - **Esegui query:** *Sì* (questa impostazione è facoltativa, ma è consigliata per prestazioni ottimali).

1. Nel riquadro azioni selezionare **Salva**.
1. Facoltativo: se si sta progettando un'etichetta specifica per il cliente, è necessario creare una query per trovare il conto del cliente. Nella scheda dettaglio **Dettagli modello di etichette ondata**, selezionare **Modifica query**. Quindi, nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungere una riga con le seguenti impostazioni:

    - **Tabella:** *Spedizioni*
    - **Tabella derivata:** *Spedizioni*
    - **Campo:** *Numero di conto*
    - **Criteri:** Immettere il numero di conto cliente pertinente.

    Al termine, selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.

### <a name="configure-number-sequence-extensions"></a>Configurare le estensioni di sequenza numerica

Le estensioni di sequenza numerica controllano la conformità GS1 delle sequenze numeriche specifiche. Questa configurazione è facoltativa per lo scenario corrente. Per ulteriori informazioni e istruzioni sulla configurazione, vedere [Configurare le estensioni di sequenza numerica](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Creare un ordine cliente e rilasciarlo nel magazzino

1. Andare a **Vendite e marketing \> Ordine cliente \> Tutti gli ordini cliente**.
1. Crea un ordine cliente con le seguenti impostazioni:

    - **Conto cliente:** *US-001*
    - **Magazzino:** *63*

1. Aggiungere cinque righe ordine cliente:

    - Riga ordine cliente 1:

        - **Numero articolo:** *A0001*
        - **Quantità:** *10*

    - Riga ordine cliente 2:

        - **Numero articolo:** *A0002*
        - **Quantità:** *20*

    - Riga ordine cliente 3:

        - **Numero articolo:** *L0006*
        - **Quantità:** *20*

    - Riga ordine cliente 4:

        - **Numero articolo:** *L0100*
        - **Quantità:** *40*

    - Riga ordine cliente 5:

        - **Numero articolo:** *L0101*
        - **Quantità:** *50*

    > [!NOTE]
    > Gli articoli e le quantità forniti qui sono solo esempi. Devono disporre di scorte nel magazzino specificato.

1. Selezionare la riga ordine cliente 1. Nella sezione **Riga ordine cliente**, nel menu **Scorte**, selezionare **Prenotazioni**.
1. Nella pagina **Prenotazione** del riquadro azioni, selezionare **Prenota lotto** e chiudere la pagina.
1. Ripetere i passaggi 4 e 5 per ogni riga ordine cliente aggiuntiva.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.

    Si verificano gli eventi seguenti:

    - Il sistema elabora la spedizione creata utilizzando il modello che include il passaggio di stampa dell'etichetta. Il layout di etichetta verrà utilizzato per definire il formato dell'etichetta e il risultato finale sarà un'etichetta con cinque righe stampata sulla stampante selezionata nel modello di etichetta.
    - Viene generato un nuovo ID polizza di carico per le spedizioni. Se sono state configurate le estensioni della sequenza numerica, gli ID etichetta ondata avranno il formato numerico **SSCC-18**. 

È possibile ristampare queste etichette ondata selezionando **Gestione magazzino \> Richieste e rapporti \>Storico etichetta ondata**.

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a>Scenario 3: stampa di etichette ondata per etichette a più livelli

Questo scenario mostra come utilizzare la funzionalità di stampa di etichette ondata quando i processi di magazzino richiedono diversi livelli di etichette indirizzo. Ad esempio, potrebbe essere necessario stampare etichette separate per cartoni e pallet e stampare un'etichetta di interruzione per un'intera spedizione. Le etichette di interruzione sono un tipo distinto di etichetta che può essere utilizzato come divisore tra rotoli e contenitori, ad esempio etichette per l'ID spedizione e un codice a barre, di modo che le etichette possano essere facilmente ordinate dopo la stampa.

La differenza principale tra la configurazione di questo scenario e la configurazione dello scenario 1, oltre al fatto che le etichette di interruzione sono abilitate, è che più tipi di etichette ondata devono essere associati a modelli di etichette ondata e righe di gruppi di sequenze di unità. Per realizzare questa configurazione, i seguenti elementi sono stati impostati per questo scenario:

- **Metodi di elaborazione ondata:** si contrassegnerà il metodo di etichetta ondata come "ripetibile", lo si aggiungerà due (o più) volte al modello di ondata e si imposteranno diversi codici passaggio ondata.
- **Modelli di etichette ondata:** si configureranno i modelli di etichette ondata e li si collegheranno al modello di ondata. Ogni modello di etichetta ondata dispone del proprio tipo di etichetta ondata.
- **Layout di etichette ondata:** si creeranno più layout di etichette ondata. Ci sarà un layout di etichetta separato per ogni "livello" di etichette nonché un layout di etichette di interruzione.

Questo scenario mostra il flusso end-to-end.

### <a name="make-demo-data-available"></a>Rendi disponibili i dati dimostrativi

Per eseguire questo scenario, i dati dimostrativi devono essere installati ed è necessario selezionare la persona giuridica **USMF**.

### <a name="set-up-a-wave-process-method"></a>Impostare un metodo di processo ondata

1. Andare a **Gestione magazzino \> Impostazione \> Ondate \> Metodi di elaborazione ondata**.
1. Verificare che **waveLabelPrinting** sia nell'elenco. Se non lo è, selezionare **Rigenera metodi** nel riquadro azioni per aggiungerlo.
1. Per il metodo **waveLabelPrinting**, selezionare la casella di controllo **Rendi ripetibile il metodo**.

### <a name="set-up-a-wave-template"></a>Impostare un modello di ondata

1. Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.
2. Selezionare un modello, ad esempio **62 Spedizione predefinita**.
3. Nella Scheda dettaglio **Metodi**, spostare il metodo **Stampa di etichette ondata** nella colonna **Metodi selezionati**.
4. Nella colonna **Metodi selezionati**, assegnare un valore **Codice passaggio ondata**, come *Cartone*, al metodo **Stampa di etichette ondata**. Per ulteriori informazioni sui codici del passaggio ondata, vedere [Codici del passaggio ondata](wave-step-codes.md).
5. Spostare il metodo **Stampa di etichette ondata** nella colonna **Metodi selezionati** una seconda volta.
6. Nella colonna **Metodi selezionati**, assegnare un valore **Codice passaggio ondata** differente, come *Pallet*, al secondo metodo **Stampa di etichette ondata**. Per ulteriori informazioni sui codici del passaggio ondata, vedere [Codici del passaggio ondata](wave-step-codes.md).

### <a name="create-three-wave-label-layouts"></a>Creare tre layout di etichetta ondata

1. Andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Layout etichette ondata**.
1. Crea un record con le seguenti impostazioni:

    - **ID layout etichetta:** *Cartone*
    - **Descrizione:** *Cartone (SSCC)*

1. Nel riquadro azioni selezionare **Salva**.
1. Nel riquadro azioni selezionare **Impostazioni di riga delle etichette ondata**.

    Viene visualizzata la pagina **Impostazioni di riga delle etichette ondata**. Qui è possibile configurare la parte dinamica dell'etichetta.

1. Aggiungere una riga con le seguenti impostazioni:

    - **ID riga:** *WaveLabel*
    - **Nome tabella di righe:** *WHSWaveLabel*
    - **Posizione di inizio riga:** *0*

        Questo campo definisce la posizione verticale iniziale della riga sull'etichetta.

    - **Altezza riga:** *0*

        Questo campo definisce l'altezza di ogni riga (in punti), secondo lo standard ZPL. L'altezza della riga è positiva per le etichette orizzontali e negativa per le etichette verticali. Poiché in questo esempio c'è una sola riga, è possibile impostare il valore su *0* (zero).

    - **Righe per pagina:** *1*

        Questo campo definisce il numero di righe che è possibile stampare su ciascuna etichetta.

        > [!NOTE]
        > Questa impostazione causerà la stampa di un'etichetta ZPL separata per ciascun record nella tabella delle etichette ondata.

1. Chiudere la pagina.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungere una riga con le seguenti impostazioni:

    - **Tabella:** *Righe di lavoro*
    - **Tabella derivata:** *Righe di lavoro*
    - **Campo:** *Tipo di lavoro*
    - **Criteri:** *Prelievo*

    Questa query garantisce che sull'etichetta vengano stampate solo le righe di lavoro di tipo prelievo, non le righe di lavoro di tipo stoccaggio.

1. Se si desidera poter stampare l'ID polizza di carico, nella scheda **Join**, selezionare la tabella **Righe lavoro** e unirvi la tabella **Spedizioni**. 
1. Chiudere la finestra di dialogo dell'editor di query.
1. La Scheda dettaglio **Layout testo stampante** ha tre sezioni in cui è possibile scrivere il codice della stampante: **Sezione di intestazione**, **Sezione del corpo** e **Sezione piè di pagina**. Nella sezione **Sezione di intestazione**, nel campo **Intestazione etichetta**, immettere il codice per l'intestazione necessaria. Ad esempio, se si utilizzano stampanti Zebra, è possibile utilizzare il codice seguente.


    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. Nella sezione **Sezione del corpo**, nel campo **Corpo etichetta**, immettere il codice ZPL per il corpo necessario. Ecco un esempio.

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. Nella sezione **Sezione del corpo**, nel campo **Piè di pagina etichetta**, immettere il codice ZPL per il piè di pagina necessario. Ecco un esempio.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Questa configurazione stamperà una copia di ciascuna etichetta. Se sono necessarie più copie (ad esempio una copia per ciascun lato del pallet), impostare il valore **n** per la sezione **\^PQn** nel piè di pagina sul numero di copie necessarie. Ad esempio, per stampare quattro copie di ciascuna etichetta, specificare **\^PQ4**.

1. La prima etichetta è ora pronta per l'uso.
1. Crea un secondo record di layout con le seguenti impostazioni:

    - **ID layout etichetta:** *Pallet*
    - **Descrizione:** *Pallet*

1. Nel riquadro azioni selezionare **Salva**.
1. Nel riquadro azioni selezionare **Impostazioni di riga delle etichette ondata**.

    Viene visualizzata la pagina **Impostazioni di riga delle etichette ondata**. Qui è possibile configurare la parte dinamica dell'etichetta.

1. Aggiungere una riga con le seguenti impostazioni:

    - **ID riga:** *WaveLabel*
    - **Nome tabella di righe:** *WHSWaveLabel*
    - **Posizione di inizio riga:** *0*

        Questo campo definisce la posizione verticale iniziale della riga sull'etichetta.

    - **Altezza riga:** *0*

        Questo campo definisce l'altezza di ogni riga (in punti), secondo lo standard ZPL. L'altezza della riga è positiva per le etichette orizzontali e negativa per le etichette verticali. Poiché in questo esempio c'è una sola riga, è possibile impostare il valore su *0* (zero).

    - **Righe per pagina:** *1*

        Questo campo definisce il numero di righe che è possibile stampare su ciascuna etichetta.

        > [!NOTE]
        > Questa impostazione causa la stampa di un'etichetta ZPL separata per ciascun record nella tabella di etichette ondata.

1. Chiudere la pagina.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungere una riga con le seguenti impostazioni:

    - **Tabella:** *Righe di lavoro*
    - **Tabella derivata:** *Righe di lavoro*
    - **Campo:** *Tipo di lavoro*
    - **Criteri:** *Prelievo*

    Questa query garantisce che sull'etichetta vengano stampate solo le righe di lavoro di tipo prelievo, non le righe di lavoro di tipo stoccaggio.

1. Se si desidera poter stampare l'ID polizza di carico, nella scheda **Join**, selezionare la tabella **Righe lavoro** e unirvi la tabella **Spedizioni**.
1. Chiudere la finestra di dialogo dell'editor di query.
1. La Scheda dettaglio **Layout testo stampante** ha tre sezioni in cui è possibile scrivere il codice della stampante: **Sezione di intestazione**, **Sezione del corpo** e **Sezione piè di pagina**. Nella sezione **Sezione di intestazione**, nel campo **Intestazione etichetta**, immettere il codice per l'intestazione necessaria. Ad esempio, se si utilizzano stampanti Zebra, è possibile utilizzare il codice seguente.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. Nella sezione **Sezione del corpo**, nel campo **Corpo etichetta**, immettere il codice ZPL per il corpo necessario. Ecco un esempio.

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. Nella sezione **Sezione del corpo**, nel campo **Piè di pagina etichetta**, immettere il codice ZPL per il piè di pagina necessario. Ecco un esempio.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Questa configurazione stamperà una copia di ciascuna etichetta. Se sono necessarie più copie (ad esempio una copia per ciascun lato del pallet), impostare il valore **n** per la sezione **\^PQn** nel piè di pagina sul numero di copie necessarie. Ad esempio, per stampare quattro copie di ciascuna etichetta, specificare **\^PQ4**.

1. La seconda etichetta è ora pronta per l'uso.
1. Creare un terzo record di layout con le seguenti impostazioni:

    - **ID layout etichetta:** *Interruzione*
    - **Descrizione:** *Etichetta di interruzione*

1. Nel riquadro azioni selezionare **Salva**.
1. La Scheda dettaglio **Layout testo stampante** ha tre sezioni in cui è possibile scrivere il codice della stampante: **Sezione di intestazione**, **Sezione del corpo** e **Sezione piè di pagina**. Nella sezione **Sezione di intestazione**, nel campo **Intestazione etichetta**, immettere il codice ZPL per l'intestazione necessaria. Ecco un esempio.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. Questa volta, non è necessario un corpo. Pertanto, immettere il testo necessario nella sezione **Sezione piè di pagina**. Ecco un esempio.

    ```plaintext
    ^XZ
    ```

    La terza etichetta è ora pronta per l'uso.

    > [!NOTE]
    > Questa terza etichetta è un'etichetta di interruzione che verrà utilizzata come divisore tra i rotoli di etichette.

### <a name="create-two-wave-label-types"></a>Creare due tipi di etichetta ondata

1. Andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Tipi di etichette ondata**.
1. Crea un record con le seguenti impostazioni:

    - **Tipo di etichetta:** *Cartone*
    - **Descrizione:** *Cartone*

1. Crea un secondo record con le seguenti impostazioni:

    - **Tipo di etichetta:** *Pallet*
    - **Descrizione:** *Pallet*

### <a name="set-up-unit-sequence-groups"></a>Imposta gruppi di sequenze unità

1. Fare clic su **Gestione magazzino \> Impostazione \> Magazzino \> Gruppi di sequenze unità**.
1. Selezionare o creare un gruppo **unità scatola pallet**.
1. Per la riga **Scatola**, impostare il campo **Tipo di livello ondata** su *Scatola*.
1. Per la riga **PALLET**, impostare il campo **Tipo di livello ondata** su *Pallet*.

### <a name="create-wave-label-templates"></a>Creare modelli di etichetta ondata

1. Andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Modelli di etichette ondata**.
1. Creare un modello di etichetta con le seguenti impostazioni:

    - **Nome modello etichetta:** *Etichette cartoni*
    - **Descrizione:** *Etichette cartoni*
    - **Codice passaggio ondata:** *Cartone*
    - **Magazzino:** *62*

1. Nella Scheda dettaglio **Generale**, nel campo **Tipo di etichetta ondata**, selezionare un valore, ad esempio *Cartone*.
1. Nella Scheda dettaglio **Dettagli modello di etichette ondata**, aggiungere una riga con le seguenti impostazioni:

    - **ID layout etichetta:** *Cartone*
    - **Nome stampante:** selezionare una stampante ZPL appropriata.
    - **Esegui query:** *Sì* (questa impostazione è facoltativa, ma è consigliata per prestazioni ottimali).

1. Nel riquadro azioni selezionare **Salva**.
1. Facoltativo: se si sta progettando un'etichetta specifica per il cliente, è necessario creare una query per trovare il conto del cliente. Nella scheda dettaglio **Dettagli modello di etichette ondata**, selezionare **Modifica query**. Quindi, nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungere una riga con le seguenti impostazioni:

    - **Tabella:** *Spedizioni*
    - **Tabella derivata:** *Spedizioni*
    - **Campo:** *Numero di conto*
    - **Criteri:** Immettere il numero di conto cliente pertinente.

    Al termine, selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.

1. Nel riquadro azioni, selezionare **Modifica query** per aprire la finestra di dialogo dell'editor di query per l'intero modello di etichetta.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Ordinamento**, aggiungere una riga con le seguenti impostazioni:

    - **Tabella:** *Righe di lavoro*
    - **Tabella derivata:** *Righe di lavoro*
    - **Campo:** *ID riga di carico di riferimento (ID record)*
    - **Direzione di ricerca:** *Crescente*

1. Aggiungere una seconda riga con le seguenti impostazioni:

    - **Tabella:** *Righe di lavoro*
    - **Tabella derivata:** *Righe di lavoro*
    - **Campo:** *ID spedizione*
    - **Direzione di ricerca:** *Crescente*

1. Selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.
1. Viene visualizzato un messaggio che richiede di confermare l'operazione di ripristino del raggruppamento. Selezionare **Sì** per continuare.
1. Nel riquadro azioni selezionare **Gruppo di modelli di etichette ondata**.
1. Nella finestra di dialogo **Gruppo di modelli di etichette ondata**, per la riga in cui il campo **Nome campo di riferimento** è impostato su *ID spedizione*, impostare i seguenti valori:

    - **Stampa etichetta di interruzione:** selezionare questa casella di controllo.
    - **ID layout etichetta:** selezionare un'etichetta di interruzione. (ad esempio, selezionare il layout di etichetta *Interruzione* creato in precedenza in questo scenario).
    - **Nome stampante:** selezionare la stampante per l'etichetta di interruzione (in genere, per lo scopo di suddividere i rotoli di etichette, è necessario selezionare la stessa stampante selezionata nella Scheda dettagli **Dettagli modello di etichette ondata**. Sono tuttavia possibili altri scenari).

1. Per la riga in cui il campo **Nome campo di riferimento** è impostato su *ID riga di carico di riferimento*, seleziona la casella di controllo **ID build etichetta**.

    > [!NOTE]
    > Questa configurazione creerà una sequenza di etichette ("Cartone 1 di X") per riga di carico in tutta l'ondata, indipendentemente dall'impostazione del raggruppamento di lavoro. Questa sequenza di etichette può essere stampata su un layout di etichetta. Inoltre, le etichette di diverse spedizioni saranno separate dall'etichetta di interruzione selezionata.

1. Selezionare **OK** per chiudere la finestra di dialogo **Gruppo di modelli di etichette ondata**.
1. Creare un secondo modello di etichetta con le seguenti impostazioni:

    - **Nome modello etichetta:** *Etichette pallet*
    - **Descrizione:** *Etichette pallet*
    - **Codice passaggio ondata:** *Pallet*
    - **Magazzino:** *62*

1. Nella Scheda dettaglio **Generale**, nel campo **Tipo di etichetta ondata**, selezionare un valore, ad esempio *Pallet*.
1. Nella Scheda dettaglio **Dettagli modello di etichette ondata**, aggiungere una riga con le seguenti impostazioni:

    - **ID layout etichetta:** *Pallet*
    - **Nome stampante:** selezionare una stampante ZPL appropriata.
    - **Esegui query:** *Sì* (questa impostazione è facoltativa, ma è consigliata per prestazioni ottimali).

1. Nel riquadro azioni selezionare **Salva**.
1. Facoltativo: se si sta progettando un'etichetta specifica per il cliente, è necessario creare una query per trovare il conto del cliente. Nella scheda dettaglio **Dettagli modello di etichette ondata**, selezionare **Modifica query**. Quindi, nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungere una riga con le seguenti impostazioni:

    - **Tabella:** *Spedizioni*
    - **Tabella derivata:** *Spedizioni*
    - **Campo:** *Numero di conto*
    - **Criteri:** Immettere il numero di conto cliente pertinente.

    Al termine, selezionare **OK** per chiudere la finestra di dialogo dell'editor di query. 

1. Nel riquadro azioni, selezionare **Modifica query** per aprire la finestra di dialogo dell'editor di query per l'intero modello di etichetta.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Ordinamento**, aggiungere una riga con le seguenti impostazioni:

    - **Tabella:** *Righe di lavoro*
    - **Tabella derivata:** *Righe di lavoro*
    - **Campo:** *ID riga di carico di riferimento (ID record)*
    - **Direzione di ricerca:** *Crescente*

1. Aggiungere una seconda riga con le seguenti impostazioni:

    - **Tabella:** *Righe di lavoro*
    - **Tabella derivata:** *Righe di lavoro*
    - **Campo:** *ID spedizione*
    - **Direzione di ricerca:** *Crescente*

1. Selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.
1. Viene visualizzato un messaggio che richiede di confermare l'operazione di ripristino del raggruppamento. Selezionare **Sì** per continuare.
1. Nel riquadro azioni selezionare **Gruppo di modelli di etichette ondata**.
1. Nella finestra di dialogo **Gruppo di modelli di etichette ondata**, per la riga in cui il campo **Nome campo di riferimento** è impostato su *ID spedizione*, impostare i seguenti valori:

    - **Stampa etichetta di interruzione:** selezionare questa casella di controllo.
    - **ID layout etichetta:** selezionare un'etichetta di interruzione. (ad esempio, selezionare il layout di etichetta *Interruzione* creato in precedenza in questo scenario).
    - **Nome stampante:** selezionare la stampante per l'etichetta di interruzione (in genere, per lo scopo di suddividere i rotoli di etichette, è necessario selezionare la stessa stampante selezionata nella Scheda dettagli **Dettagli modello di etichette ondata**. Sono tuttavia possibili altri scenari).

1. Per la riga in cui il campo **Nome campo di riferimento** è impostato su *ID riga di carico di riferimento*, seleziona la casella di controllo **ID build etichetta**.

    > [!NOTE]
    > Questa configurazione creerà una sequenza di etichette ("Cartone 1 di X") per riga di carico in tutta l'ondata, indipendentemente dall'impostazione del raggruppamento di lavoro. Questa sequenza di etichette può essere stampata su un layout di etichetta. Inoltre, le etichette di diverse spedizioni saranno separate dall'etichetta di interruzione selezionata.

### <a name="configure-number-sequence-extensions"></a>Configurare le estensioni di sequenza numerica

Le estensioni di sequenza numerica controllano la conformità GS1 delle sequenze numeriche specifiche. Questa configurazione è facoltativa per lo scenario corrente. Per ulteriori informazioni e istruzioni sulla configurazione, vedere [Configurare le estensioni di sequenza numerica](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Creare un ordine cliente e rilasciarlo nel magazzino

1. Andare a **Vendite e marketing \> Ordine cliente \> Tutti gli ordini cliente**.
1. Crea un ordine cliente con le seguenti impostazioni:

    - **Conto cliente:** *US-001*
    - **Magazzino:** *62*

1. Aggiungere due righe ordine cliente:

    - Riga ordine cliente 1:

        - **Numero articolo:** *A0001*
        - **Quantità:** *9024*
        - **Unità:** *unità* (9024 unità = 376 scatole = 47 pallet)

    - Riga ordine cliente 2:

        - **Numero articolo:** *A0002*
        - **Quantità:** *9016*
        - **Unità:** *unità* (9016 unità = 322 scatole = 46 pallet)

    > [!NOTE]
    > Gli articoli e le quantità forniti qui sono solo esempi. Devono utilizzare il gruppo di sequenze di unità definito in precedenza, conversioni di unità appropriate da *unità* a *scatola* a *pallet* devono essere definite per gli stessi e devono avere stock nel magazzino *62*. Per ulteriori informazioni, vedere [Unità di misura e politiche di stoccaggio](unit-measure-stocking-policies.md).

1. Selezionare la riga ordine cliente 1. Nella sezione **Riga ordine cliente**, nel menu **Scorte**, selezionare **Prenotazioni**.
1. Nella pagina **Prenotazione** del riquadro azioni, selezionare **Prenota lotto** e chiudere la pagina.
1. Ripetere i passaggi 4 e 5 per la riga ordine cliente 2.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.

    Si verificano gli eventi seguenti: 

    - Il sistema elabora la spedizione creata utilizzando il modello che include il passaggio di stampa dell'etichetta. Il layout di etichetta verrà utilizzato per definire il formato dell'etichetta e il risultato sarà un'etichetta stampata sulla stampante selezionata nel modello di etichetta.
    - Le etichette ondata vengono generate e stampate. Il numero di etichette sarà uguale al numero di cartoni (in questo esempio, 376 etichette scatola per la riga 1, 322 etichette scatola per la riga 2, 47 etichette pallet per la riga 1, 47 etichette pallet per la riga 2 e due etichette di interruzione che hanno l'ID spedizione).
    - Viene generato un nuovo ID polizza di carico per le spedizioni. Se sono state configurate le estensioni della sequenza numerica, gli ID etichetta ondata avranno il formato numerico **SSCC-18**. 

È possibile visualizzare e ristampare le etichette ondata dalle seguenti pagine:

- Tutte le spedizioni \> Dettagli spedizione
- Tutti i carichi \> Dettagli carico
- Tutte le ondate
- Etichette ondata
- Storico etichette ondata

Per la maggior parte di queste pagine, è possibile trovare la funzione pertinente selezionando **Etichette ondata** nel gruppo **Informazioni correlate** della scheda **Spedizioni** del riquadro azioni.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]