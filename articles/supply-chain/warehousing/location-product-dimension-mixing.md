---
title: Combinazione dimensioni prodotto ubicazione
description: Questo argomento fornisce informazioni sulla combinazione di dimensioni del prodotti di ubicazione. Questa funzionalità del profilo di ubicazione consente di migliorare la gestione dell'ubicazione quando vengono utilizzate varianti di prodotto o prodotti con dimensioni, ad esempio nel settore della moda. Consente di decidere se configurazioni, colori, stili e dimensioni possono essere combinati per un profilo di ubicazione specifico o se solo una di queste dimensioni o una combinazione di esse può essere collocata nella stessa ubicazione.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 73519f3fe79d3d7d917d3044255f735640b8ccfd
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431471"
---
# <a name="location-product-dimension-mixing"></a>Combinazione dimensioni prodotto ubicazione

[!include [banner](../includes/banner.md)]

La combinazione delle dimensioni del prodotto di ubicazione è una funzionalità del profilo di ubicazione che consente di migliorare la gestione dell'ubicazione quando vengono utilizzate varianti di prodotto o prodotti con dimensioni, ad esempio nel settore della moda. Consente di decidere se configurazioni, colori, stili e dimensioni possono essere combinati per un profilo di ubicazione specifico o se solo una di queste dimensioni o una combinazione di esse può essere collocata nella stessa ubicazione.

## <a name="turn-on-the-location-product-dimension-mixing-feature"></a>Attivare la funzionalità di combinazione delle dimensioni del prodotto di ubicazione

Prima di poter utilizzare la combinazione delle dimensioni del prodotto di ubicazione, tale funzionalità deve essere attivata nel sistema. Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Combinazione dimensioni prodotto ubicazione*

## <a name="setup"></a>Attrezzaggio

Ogni ubicazione del magazzino deve disporre di un profilo che descrive le proprietà dell'ubicazione. Pertanto, tutte le ubicazioni che utilizzano lo stesso profilo ubicazione saranno in grado di consentire la combinazione delle dimensioni del prodotto dopo che è stato impostato.

### <a name="configure-location-profiles-to-allow-product-dimension-mixing"></a>Configurare i profili di ubicazione per consentire la combinazione delle dimensioni

1. Vai a **Gestione magazzino \> Impostazioni \> Magazzino \> Profili ubicazione**.
1. Nell'elenco dei profili di ubicazione, seleziona **BULK**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella Scheda dettaglio **Generale**, imposta l'opzione **Abilita combinazione specifica dimensioni prodotto di ubicazione** su *Sì*.

    > [!NOTE]
    > È possibile impostare questa opzione su *Sì* solo se l'opzione **Consenti articoli combinati** è impostata su *No*.

1. Nella Scheda dettaglio **Combinazione dimensioni prodotto consentita**, imposta l'opzione **Dimensione** su *Sì*. Nello scenario descritto in questo argomento, la combinazione può essere eseguita solo per prodotti che hanno valori diversi per **Dimensione**. Tuttavia, sono disponibili anche altre opzioni.
1. Selezionare **Salva**.

### <a name="create-a-new-product-master-and-product-variants"></a>Creare una nuova rappresentazione generale prodotto e varianti di prodotto

1. Vai a **Gestione informazioni sul prodotto \> Prodotti \> Rappresentazioni generali prodotto**.
1. Nel riquadro azioni seleziona **Nuova** per creare una rappresentazione generale prodotto.
1. Nella finestra di dialogo **Nuovo prodotto**, imposta i seguenti valori:

    - **Tipo di prodotto:** *Articolo*
    - **Sottotipo di prodotto:** *Rappresentazione generale prodotto*
    - **Numero prodotto:** *B0001*
    - **Nome prodotto:** *Dimensione B0001*
    - **Gruppo di dimensioni prodotto:** *Dimensione*
    - **Tecnologia di configurazione:** *Varianti predefinite*

1. Selezionare **OK**.
1. Nella pagina **Dettagli prodotto**, nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Genera varianti automaticamente:** *Sì*
    - **Gruppo di dimensioni:** *CASUALDHIR*

1. Per visualizzare le varianti predefinite, nel riquadro azioni seleziona **Varianti prodotto**.

    La pagina **Varianti prodotto** viene visualizzata e mostra un elenco di varianti dalla configurazione del gruppo di dimensioni.

### <a name="release-products-to-the-usmf-company"></a>Rilasciare i prodotti a società USMF

1. Nel riquadro azioni seleziona **Rilascia prodotti**.
1. Nella pagina **Seleziona prodotti da rilasciare**, Verifica che il numero di prodotto *B0001* sia nell'elenco, quindi seleziona **Avanti**.
1. Seleziona **Avanti** per confermare le varianti del prodotto da rilasciare.
1. Nella pagina **Seleziona aziende a cui rilasciare**, seleziona *USMF*, quindi seleziona **Avanti** per confermare la selezione.
1. Nella pagina **Conferma selezione**, seleziona **Fine** per completare il rilascio.

    Ricevi un messaggio di tipo "Operazione completata".

### <a name="update-a-released-product-in-the-usmf-company"></a>Aggiornare un prodotto rilasciato nella società USMF

1. Assicurati di aver effettuato l'accesso all'azienda **USMF**.
1. Vai a **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati** per terminare la creazione del prodotto rilasciato.
1. Trova e seleziona il numero dell'articolo *B0001* per aprire la pagina **Dettagli prodotto rilasciato**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella Scheda dettaglio **Generale**, verifica che **Gruppo di modelli di articoli** sia impostato su *FIFO*.
1. Nel riquadro azioni, nella scheda **Prodotto**, nel gruppo **Imposta**, seleziona **Gruppi di dimensioni**.
1. Imposta i valori seguenti:

    - **Gruppo di dimensioni di immagazzinamento:** *Ondata*
    - **Gruppo di dimensioni di tracciabilità:** *Nessuno*

1. Selezionare **OK**.
1. Nel riquadro azioni, nella scheda **Prodotto**, nel gruppo **Imposta**, seleziona **Gerarchia prenotazioni**.
1. Imposta il campo **Gerarchia prenotazioni** su *Predefinito*, quindi seleziona **OK**.
1. Nella Scheda dettaglio **Generale**, nella sezione **Amministrazione**, nota che le tue selezioni sono state aggiornate.
1. Nella Scheda dettaglio **Acquisto**, nel campo **Prezzo**, immetti *10*.
1. Nella Scheda dettaglio **Gestisci costi** seleziona il gruppo *Audio* nel campo **Gruppo di articoli**.
1. Nella Scheda dettaglio **Acquisto**, nel campo **Prezzo**, immetti *10*.
1. Nell Scheda dettaglio **Magazzino**, nel campo **ID gruppo di sequenze unità**, immetti *ea*.
1. Selezionare **Salva**.

### <a name="create-a-location-directive"></a>Creare una direttiva ubicazione

1. Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Nel riquadro sinistro, nel campo **Tipo di ordine di lavoro**, seleziona *Ordini fornitore*.
1. Nell'elenco, seleziona la direttiva di ubicazione denominata *24 PO diretto*.
1. Nella Scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Numero progressivo:** *1*

        La nuova riga dovrebbe trovarsi davanti alla riga precedentemente esistente. Per apportare la modifica, utilizza i pulsanti **Sposta su** e **Sposta giù** sulla barra degli strumenti o modificare il valore **Numero progressivo** della riga esistente su *2*.

    - **Nome:** *Inserisci su profilo di ubicazione BULK*
    - **Utilizzo ubicazioni fisse:** *Ubicazioni fisse e non fisse*
    - **Consenti inventario negativo:** *Deseleziona questa casella di controllo (=No)*
    - **Lotto abilitato:** *Deseleziona questa casella di controllo (=No)*
    - **Strategia:** *Nessuna*

1. Con la nuova riga ancora selezionata, seleziona **Modifica query** sopra la griglia.
1. Nella finestra di dialogo della query, nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tabella:** *Ubicazioni*
    - **Tabella derivata:** *Ubicazioni*
    - **Campo:** *ID profilo ubicazione*
    - **Criteri:** *BULK*

1. Selezionare **OK**.
1. Nella pagina **Direttive ubicazione**, nel riquadro azioni, seleziona **Salva**.

> [!NOTE]
> Nella Scheda dettaglio **Azioni direttiva ubicazione** nel campo **Strategia**, se utilizzi la strategia di ubicazione *Consolida*, la configurazione della Scheda dettaglio **Combinazione dimensioni prodotto consentita** in **Profili ubicazione** verrà sovrascritta e gli elementi verranno collocati nella stessa ubicazione anche se questo comportamento non è consentito dalla configurazione.

### <a name="create-a-mobile-device-menu-item"></a>Creare una voce di menu per dispositivo mobile

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel riquadro azioni seleziona **Nuovo** per creare una voce di menu da utilizzare per l'ordinamento.
1. Nell'intestazione, imposta i seguenti valori:

    - **Nome voce di menu:** *Ricezione riga PO*
    - **Titolo:** *Ricezione riga PO*
    - **Modalità:** *Lavoro*
    - **Utilizza lavoro esistente:** *No*

1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Processo di creazione lavoro:** *Ricevimento e stoccaggio riga ordine acquisto*
    - **Genera targa:** *Sì*

1. Selezionare **Salva**.

### <a name="configure-the-mobile-device-menu"></a>Configurare i menu dei dispositivi mobili

1. Accedere a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.
1. Nell'elenco dei menu, seleziona **In entrata**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nell'elenco **Menu e voci di menu disponibili**, trova e seleziona la voce di menu **Ricezione riga PO**.
1. Seleziona il pulsante freccia destra per spostare la voce di menu **Ricezione riga PO** sull'elenco **Struttura menu**. In questo modo, aggiungi la nuova voce di menu al menu selezionato.
1. Selezionare **Salva**.

## <a name="scenario"></a>Scenario

Questo scenario dimostrativo mostra come due diverse varianti di prodotto possono essere messe nella stessa ubicazione quando il profilo di ubicazione non consente articoli combinati, ma la funzionalità *Combinazione dimensioni prodotto ubicazione*. In questo caso, utilizzerai la variante **Dimensione** come criterio.

Prima di iniziare, assicurati che ci siano ubicazioni vuote nel magazzino *24* che usano il profilo di ubicazione *BULK*.

### <a name="create-a-purchase-order"></a>Creare un ordine fornitore

Creerai un ordine fornitore che ha tre righe: due righe per lo stesso numero di prodotto ma diverse varianti **Dimensione** e una terza riga per un prodotto diverso che non ha varianti.

1. Vai a **Contabilità fornitori \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine fornitore**, imposta i seguenti valori:

    - **Conto fornitore:** *1001*
    - **Magazzino:** *24*

1. Selezionare **OK**.
1. L'ordine fornitore viene creato e una nuova riga viene aggiunta sulla Scheda dettaglio **Righe ordine fornitore**. Prendere nota del numero di ordine fornitore.
1. Nella nuova riga, imposta i seguenti valori:

    - **Numero articolo:** *B0001*
    - **Dimensione** *L*
    - **Quantità:** *2*

1. Seleziona **Aggiungi riga** sopra la griglia per aggiungere un secondo ordine fornitore, quindi imposta i seguenti valori:

    - **Numero articolo:** *B0001*
    - **Dimensione** *XL*
    - **Quantità:** *2*

1. Seleziona **Aggiungi riga** per aggiungere una terza riga ordine fornitore, quindi imposta i seguenti valori:

    - **Numero articolo:** *A0001*
    - **Quantità:** *1*

1.Seleziona **Salva**.

### <a name="receive-purchase-order-lines-in-the-warehouse-app"></a>Ricevere le righe ordine fornitore nell'app del magazzino

1. Accedi all'app del magazzino come utente abilitato per il magazzino *24*.
1. Seleziona il menu **In uscita**.
1. Seleziona **Ricezione riga PO**.
1. Seleziona il campo **PONUM**, quindi inserisci il numero dell'ordine fornitore.
1. Conferma l'immissione selezionando il pulsante di conferma (✔) nella parte inferiore della pagina.
1. Immetti il numero di riga dall'ordine fornitore che viene ricevuto. Seleziona il campo **LINENUM**, quindi utilizza il tastierino numerico per immettere *1*.
1. Conferma l'inserimento.
1. Immetti la quantità da ricevere. Seleziona il segno più (**+**) due volte per aumentare il valore nel campo **Qtà** su *2*.
1. Registra l'inserimento selezionando il pulsante (✔) nella parte inferiore della pagina, quindi conferma l'inserimento selezionando nuovamente il pulsante (✔).
1. Visualizza le informazioni nella pagina **Ordini fornitore: Inserisci**. Questa pagina mostra il lavoro che è stato creato per lo sttoccaggio (Lavoro 1).

    Viene visualizzata l'ubicazione di stoccaggio dell'articolo ricevuto, la targa, l'articolo, le dimensioni e la quantità dell'attività **Ricezione riga PO** appena completata.

1. Conferma il lavoro di stoccaggio.
1. Ripeti i passaggi da 4 a 11 per la riga ordine fornitore 2. Tuttavia, al passaggio 8, specifica una quantità di *1*.

    Il nuovo lavoro di stoccaggio (Lavoro 2) viene creato nella stessa ubicazione del Lavoro 1.

1. Ripeti i passaggi da 4 a 11 per la riga ordine fornitore 2. Al passaggio 8, specifica la quantità rimanente di *1*.

    Il nuovo lavoro di stoccaggio (Lavoro 3) viene creato nella stessa ubicazione del Lavoro 1 e Lavoro 2. Questo comportamento si verifica perché viene utilizzata la strategia della direttiva di ubicazione *Consolida* e la Scheda dettaglio **Combinazione dimensioni prodotto consentita** nella configurazione *Massa* **Profili di ubicazione** consente la combinazione della variante **Dimensione** in un'ubicazione.

1. Ripeti i passaggi da 4 a 11 per la riga ordine fornitore 3. Nel passaggio 8, specifica una quantità di *1* per il numero articolo *A0001*.

    Il nuovo lavoro di stoccaggio (Lavoro 4) viene creato per una diversa ubicazione da quella utilizzata per le righe ordine fornitore 1 e 2. Questo comportamento si verifica perché il profilo di ubicazione non consente prodotti combinati, ma consente dimensioni combinate della stessa rappresentazione generale prodotto.

1. Seleziona il pulsante Menu nella parte superiore della pagina (a volte indicato come hamburger o pulsante hamburger), quindi seleziona **Annulla** per uscire da **Ricezione riga PO**.

> [!TIP]
> Puoi ripetere questo scenario, ma questa volta, imposta **Dimensione** - *No* nella Scheda dettaglio **Consenti combinazione dimensioni prodotto** sul *BULK* **Profili di ubicazione**, in modo che nessuna delle dimensioni del prodotto possa essere combinata. In questo caso, quando si riceve l'ordine fornitore, ciascuna variante di prodotto verrà inserita in una nuova ubicazione.