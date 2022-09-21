---
title: Configurazione dei criteri di consolidamento delle spedizioni
description: Questo articolo spiega come impostare criteri di consolidamento delle spedizioni predefiniti e personalizzati.
author: Mirzaab
ms.date: 09/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, TMSMode, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 0312d425d2ebc5311e894030423a916b90f1881a
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2022
ms.locfileid: "9427984"
---
# <a name="configure-shipment-consolidation-policies"></a>Configurazione dei criteri di consolidamento delle spedizioni

[!include [banner](../includes/banner.md)]

Il processo di consolidamento delle spedizioni che utilizza criteri di consolidamento delle spedizioni consente il consolidamento automatico delle spedizioni durante il rilascio automatico e manuale al magazzino. Dopo aver attivato questa funzionalità, è necessario configurare i criteri iniziali. Se non sono configurati criteri, ogni riga di vendita genererà una spedizione separata con una sola riga di carico.

Gli scenari presentati in questo articolo mostrano come impostare criteri di consolidamento delle spedizioni predefiniti e personalizzati.

> [!WARNING]
> Se aggiorni un sistema Microsoft Dynamics 365 Supply Chain Management in cui è stata utilizzata la funzione di consolidamento delle spedizioni legacy, il consolidamento potrebbe smettere di funzionare come previsto a meno che non si segua il consiglio fornito qui.
>
> Nelle installazioni di Supply Chain Management in cui la funzione *Criteri consolidamento spedizione* è disattivata, si abilita il consolidamento delle spedizioni utilizzando l'impostazione **Consolida spedizione al rilascio al magazzino** per ogni singolo magazzino. Questa funzionalità è obbligatoria a partire dalla versione 10.0.29. Quando è attivata, l'impostazione **Consolida spedizione al rilascio in magazzino** viene nascosta e la funzionalità viene sostituita dai *criteri di consolidamento spedizione* che sono descritti in questo articolo. Ciascun criterio stabilisce le regole di consolidamento e include una query per controllare dove si applica il criterio. Quando attivi la funzione per la prima volta, non verranno definiti criteri di consolidamento delle spedizioni nella pagina **Criteri consolidamento spedizione**. Quando non sono definiti i criteri, il sistema utilizza il comportamento legacy. Pertanto, ogni magazzino esistente continua a rispettarne l'impostazione **Consolida spedizione al rilascio in magazzino**, anche se tale impostazione è ora nascosta. Tuttavia, dopo aver creato almeno un criterio di consolidamento delle spedizioni, le impostazioni **Consolida spedizione al rilascio in magazzino** non hanno più alcun effetto e la funzionalità di consolidamento è interamente controllata dai criteri.
>
> Dopo aver definito almeno un criterio di consolidamento della spedizione, il sistema verificherà i criteri di consolidamento ogni volta che un ordine viene rilasciato al magazzino. Il sistema elabora i criteri utilizzando la classifica definita dal valore **Sequenza criteri** di ogni criterio. Applica il primo criterio in cui la query corrisponde al nuovo ordine. Se nessuna query corrisponde all'ordine, ciascuna riga ordine genera una spedizione separata con un'unica riga di carico. Pertanto, come fallback, ti consigliamo di creare un criterio predefinito che si applichi a tutti i magazzini e i gruppi in base al numero d'ordine. Dai a questo criterio di fallback il massimo valore di **Sequenza criteri**, in modo che venga elaborato per ultimo.
>
> Per riprodurre il comportamento legacy, è necessario creare un criterio che non raggruppi per numero d'ordine e che abbia criteri di query che includano tutti i magazzini pertinenti.

## <a name="turn-on-the-shipment-consolidation-policies-feature"></a>Attiva la funzionalità Criteri di consolidamento spedizioni

Per poter usare la funzionalità *Criteri di consolidamento spedizioni*, è necessario attivarla per il sistema. A partire dalla versione 10.0.29 di Supply Chain Management, la funzionalità è obbligatoria e non può essere disattivata. Se si sta eseguendo una versione precedente alla versione 10.0.29, gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Criteri di consolidamento spedizioni* nell'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-your-initial-consolidation-policies"></a><a name="initial-policies"></a>Impostare i criteri di consolidamento iniziali

Se stai lavorando con un nuovo sistema o un sistema in cui hai appena attivato la funzionalità *Criteri consolidamento spedizione* per la prima volta, attieniti alla seguente procedura per impostare i criteri di consolidamento delle spedizioni iniziali.

1. Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento spedizioni**.
1. Nel riquadro azioni, seleziona **Crea impostazione predefinita** per creare i seguenti criteri:

    - Un criterio denominato *Predefinito* per il tipo di criterio *Ordini cliente*.
    - Un criterio denominato *Predefinito* per il tipo di criterio *Uscita di trasferimento*.
    - Un criterio denominato *CrossOrder* per il tipo di criterio *Uscita di trasferimento*. Questo criterio viene creato solo se disponi di almeno un magazzino in cui l'impostazione legacy **Consolida spedizione al rilascio in magazzino** è stata abilitata.
    - Un criterio denominato *CrossOrder* per il tipo di criterio *Ordini cliente*. Questo criterio viene creato solo se disponi di almeno un magazzino in cui l'impostazione legacy **Consolida spedizione al rilascio in magazzino** è stata abilitata.

    > [!NOTE]
    > - Entrambi i criteri *CrossOrder* considerano lo stesso insieme di campi della logica precedente. Tuttavia, considerano anche il campo del numero d'ordine. Questo campo viene utilizzato per consolidare le righe nelle spedizioni, in base a fattori quali magazzino, modalità di trasporto della consegna e indirizzo.
    > - Entrambi i criteri *Predefinito* considerano lo stesso insieme di campi della logica precedente. Tuttavia, considerano anche il campo del numero d'ordine. Questo campo viene utilizzato per consolidare le righe nelle spedizioni, in base a fattori quali numero di ordine, magazzino, modalità di trasporto della consegna e indirizzo.

1. Se il sistema ha generato un criterio *CrossOrder* per il tipo di criterio *Ordini cliente*, selezionalo, e nel riquadro azioni, seleziona **Modifica query**. Nell'editor di query, puoi vedere per quale dei tuoi magazzini l'impostazione **Consolida spedizione al rilascio in magazzino** era precedentemente abilitata. Pertanto, questo criterio riproduce le impostazioni precedenti per questi magazzini.
1. Personalizza i nuovi criteri predefiniti come richiesto aggiungendo o rimuovendo campi e/o modificando le query. Puoi anche aggiungere tutti i nuovi criteri di cui hai bisogno. Per esempi che mostrano come personalizzare e configurare i criteri, vedi lo scenario di esempio più avanti in questo articolo.

## <a name="scenario-configure-custom-shipment-consolidation-policies"></a>Scenario: configurare criteri di consolidamento delle spedizioni personalizzati

Questo scenario fornisce un esempio che mostra come impostare criteri di consolidamento delle spedizioni personalizzati e quindi testarli utilizzando dati demo. I criteri personalizzati possono supportare requisiti aziendali complessi in cui il consolidamento della spedizione dipende da diverse condizioni. Per ciascun criterio di esempio più avanti in questo scenario, è inclusa una breve descrizione del caso aziendale. Questi criteri di esempio dovrebbero essere impostati in una sequenza che garantisca una valutazione piramidale delle query. In altre parole, i criteri che presentano il maggior numero di condizioni dovrebbero essere valutati come aventi la massima priorità.

### <a name="make-demo-data-available"></a>Rendi disponibili i dati dimostrativi

Questo scenario fa riferimento a valori e record inclusi nei [dati dimostrativi](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard forniti per Supply Chain Management. Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica su *USMF* prima di iniziare.

### <a name="prepare-master-data-for-this-scenario"></a>Preparare i dati master per questo scenario

Prima di poter eseguire gli esercizi in questo scenario, è necessario preparare i dati master necessari per eseguire il filtro, come descritto nelle sottosezioni seguenti. Questi prerequisiti si applicano anche agli scenari elencati nella sezione [Scenari di esempio su come utilizzare i criteri di consolidamento delle spedizioni](#example-scenarios).

#### <a name="create-two-new-product-filter-codes"></a>Crea due nuovi codici filtro prodotto

1. Vai a **Gestione magazzino \> Impostazione \> Filtri prodotto \> Filtri prodotto** e aggiungi due filtri prodotto:

    - Filtro prodotti 1:

        - **Codice filtro:** *Infiammabile*
        - **Titolo filtro:** *Codice 4*

    - Filtro prodotti 2:

        - **Codice filtro:** *Esplosivo*
        - **Titolo filtro:** *Codice 4*

1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Apri il prodotto con numero articolo *M9200*. Il prodotto selezionato deve essere abilitato per i processi del magazzino avanzato \[WMS\] e questo prodotto è pre-abilitato per i processi WMS nei dati dimostrativi **USMF**.
1. Nella Scheda dettaglio **Magazzino**, imposta il campo **Codice 4** su *Infiammabile*.
1. Chiudere la pagina.
1. Apri il prodotto con numero articolo *M9201*. Questo prodotto è pre-abilitato anche per i processi WMS nei dati dimostrativi **USMF**.
1. Nella Scheda dettaglio **Magazzino**, imposta il campo **Codice 4** su *Esplosivo*.
1. Chiudere la pagina.

#### <a name="create-a-new-transportation-mode-of-delivery"></a>Crea una nuova modalità di trasporto della consegna

1. Vai a **Gestione trasporto \> Impostazioni \> Vettori \> Modalità**.
1. Crea una modalità di trasporto che verrà utilizzata nelle query di consolidamento e chiamala *Airways*.
1. Vai a **Gestione trasporto \> Impostazioni \> Vettori \> Vettori spedizione**.
1. Crea un vettore con le seguenti impostazioni:

    - **Vettore spedizione:** *Airways*
    - **Nome:** *Airways*
    - **Modalità:** *Airways*

1. Nella Scheda dettaglio **Servizi** per il nuovo vettore, aggiungi una riga con le seguenti impostazioni:

    - **Servizio trasporto:** *Air*
    - **Metodo di trasporto:** *Air*

1. Nel riquadro azioni selezionare **Salva**.

    > [!NOTE]
    > Quando salvi il nuovo vettore, il campo **Modalità di consegna** per la nuova riga nella griglia **Servizi** viene automaticamente impostato su *Airwa-Air*. Quando si utilizza la modalità di consegna *Airwa-Air* per un ordine cliente, la modalità di trasporto *Airways* verrà utilizzata per le spedizioni correlate.

#### <a name="create-an-order-pool"></a>Crea pool di ordini

1. Vai a **Vendite e marketing \> Impostazioni \> Ordini cliente \> Pool di ordini**.
1. Crea un pool di ordini che verrà utilizzato per la query di consolidamento. Questo pool di ordini dovrebbe avere le seguenti impostazioni:

    - **Pool:** immettere un numero intero che non sia già utilizzato da nessun altro pool.
    - **Nome:** *ShipCons*

1. Vai a **Vendite e marketing \> Clienti \> Tutti i clienti**.
1. Apri il cliente con il numero di conto *US-003*.
1. Nella Scheda dettaglio **Impostazioni predefinite ordine cliente**, imposta il campo **Pool ordini cliente** al pool degli ordini che hai appena creato.
1. Chiudi la pagina, quindi ripeti i passaggi 4 e 5 per il cliente che ha il numero di conto *US-004*.

### <a name="create-example-policy-1"></a>Crea un criterio di esempio 1

In questo esempio, creerai un criterio *Cliente + Modalità* che può essere utilizzato per il seguente caso aziendale:

- Il criterio chiederà un conto cliente specifico (*US-001*) e una modalità di consegna specifica (*Airwa-Air*).
- Il consolidamento con spedizioni aperte è disattivato.
- Il consolidamento viene eseguito per ID ordine. In altre parole, ci saranno spedizioni separate per ordine, magazzino e così via.

Attieniti alla seguente procedura per creare i criteri di consolidamento della spedizione per questo caso aziendale.

1. Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento spedizioni**.
1. Imposta il campo **Tipo di criteri** su *Ordini cliente*.
1. Nel riquadro azioni, seleziona **Nuovo** per creare un criterio con le seguenti impostazioni:

    - **Nome criterio:** *CustomerMode*
    - **Descrizione criterio:** *Conto cliente e modalità di consegna*

1. Lascia l'opzione **Consolida con spedizioni aperte** impostata su *No*.
1. Nel riquadro azioni selezionare **Salva**.
1. Nella Scheda dettaglio **Campi di consolidamento**, nell'elenco **Campi rimanenti**, seleziona la riga in cui il campo **Nome campo** è impostato su *Modalità di consegna*.
1. Selezionare il pulsante **Aggiungi** ![Freccia DESTRA.](media/forward-button.png) per spostare il campo nell'elenco **Campi selezionati**.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, nella griglia, trova la riga in cui il campo **Campo** è impostato su *Conto cliente* e imposta il campo **Criteri** per quella riga su *US-001*.
1. Seleziona **Aggiungi** per aggiungere una riga con le seguenti impostazioni alla griglia:

    - **Tabella:** *Righe ordine*
    - **Tabella derivata:** *Righe ordine*
    - **Campo:** *Modalità di consegna*
    - **Criteri:** *Airwa-Air*

1. Selezionare **OK** per chiudere la finestra di dialogo.

> [!NOTE]
> Per questo caso aziendale, le righe degli ordini per il cliente *US-001* che usa la modalità di consegna *Airwa-Air* non saranno consolidate tra gli ordini. Questi criteri devono essere utilizzati prima in una sequenza, nei casi in cui le spedizioni per tutte le altre modalità di consegna sono consolidate per questo cliente.

### <a name="create-example-policy-2"></a>Crea un criterio di esempio 2

In questo esempio, creerai un criterio *Merce pericolosa* che può essere utilizzato per il seguente caso aziendale:

- Il criterio chiederà un codice filtro specifico (*pericoloso*) e una modalità di consegna specifica (*Airwa-Air*).
- Il consolidamento con spedizioni aperte è attivato.
- Il consolidamento viene eseguito tra gli ordini. In altre parole, ci saranno spedizioni separate per conto, magazzino e così via, ma solo all'interno del gruppo di articoli specificato nella query.

Attieniti alla seguente procedura per creare i criteri di consolidamento della spedizione per questo caso aziendale.

1. Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento spedizioni**.
1. Imposta il campo **Tipo di criteri** su *Ordini cliente*.
1. Nel riquadro azioni, seleziona **Nuovo** per creare un criterio con le seguenti impostazioni:

    - **Nome criteri:** *Tipo di articolo*
    - **Descrizione criterio:** *Consolida lo stesso tipo di articolo tra ordini*

1. Imposta l'opzione **Consolida con spedizioni aperte** su *Sì*.
1. Nel riquadro azioni selezionare **Salva**.
1. Nella Scheda dettaglio **Campi di consolidamento**, nell'elenco **Campi rimanenti**, seleziona la riga in cui il campo **Nome campo** è impostato su *Modalità di consegna*.
1. Selezionare il pulsante **Aggiungi** ![Freccia DESTRA.](media/forward-button.png) per spostare il campo nell'elenco **Campi selezionati**.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Join**, espandi e seleziona **Tabelle \> Carica dettagli** nell'albero.
1. Seleziona **Aggiungi tabella join**.
1. Nella griglia di relazioni che appare, trova e seleziona la riga in cui il campo **Relazione** è impostato su *Numero articolo magazzino (Numero articolo)*, quindi seleziona **Seleziona**. 
1. Nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga che ha le seguenti impostazioni alla griglia:

    - **Tabella:** *Numero articolo magazzino*
    - **Tabella derivata:** *Numero articolo magazzino*
    - **Campo:** *Codice 4*
    - **Criteri:** *Infiammabile*

1. Selezionare **OK** per chiudere la finestra di dialogo.

> [!NOTE]
> Per questo caso aziendale, tutte le righe ordine in cui gli articoli hanno un codice filtro specifico (ovvero il codice filtro in cui il campo **Codice 4** è impostato su *Infiammabile*) verrà consolidato con altri articoli dello stesso tipo tra gli ordini. Se esiste una spedizione aperta per lo stesso conto, magazzino e gruppo di articoli, le nuove righe verranno allegate ad esso.

### <a name="create-example-policy-3"></a>Crea un criterio di esempio 3

In questo esempio, creerai un criterio *Requisiti cliente* che può essere utilizzato per il seguente caso aziendale:

- Il criterio richiederà un account cliente specifico.
- Il consolidamento con spedizioni aperte è attivato.
- Il consolidamento viene eseguito tra gli ordini ma si basa sulle richieste di approvvigionamento del cliente. In altre parole, più ordini verranno raggruppati in spedizioni, in base allo stesso numero di richiesta di approvvigionamento del cliente e magazzino.

Attieniti alla seguente procedura per creare i criteri di consolidamento della spedizione per questo caso aziendale.

1. Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento spedizioni**.
1. Imposta il campo **Tipo di criteri** su *Ordini cliente*.
1. Nel riquadro azioni, seleziona **Nuovo** per creare un criterio con le seguenti impostazioni:

    - **Nome criteri:** *CustomerOrderNo*
    - **Descrizione criterio:** *Consolida righe in base al PO cliente*

1. Imposta l'opzione **Consolida con spedizioni aperte** su *Sì*.
1. Nel riquadro azioni selezionare **Salva**.
1. Nella Scheda dettaglio **Campi di consolidamento**, nell'elenco **Campi rimanenti**, seleziona la riga in cui il campo **Nome campo** è impostato su *Richiesta di approvvigionamento cliente*.
1. Selezionare il pulsante **Aggiungi** ![Freccia DESTRA.](media/forward-button.png) per spostare il campo nell'elenco **Campi selezionati**.
1. Nell'elenco **Campi rimanenti**, seleziona la riga in cui il campo **Nome campo** è impostato su *Modalità di consegna*.
1. Selezionare il pulsante **Aggiungi** ![Freccia DESTRA.](media/forward-button.png) per spostare il campo nell'elenco **Campi selezionati**.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, trova la riga in cui il campo **Campo** è impostato su *Conto cliente* e imposta il campo **Criteri** per quella riga su *US-001*.
1. Selezionare **OK** per chiudere la finestra di dialogo.

> [!NOTE]
> Per questo caso aziendale, tutte le righe degli ordini in cui gli ordini cliente hanno lo stesso numero di richiesta cliente verranno consolidate in una spedizione, indipendentemente dal numero dell'ordine cliente. Il numero di richiesta del cliente viene utilizzato come numero di \[PO\] ordine fornitore del cliente. Se esiste una spedizione aperta per lo stesso conto, magazzino e richiesta di approvvigionamento del cliente, le nuove righe verranno allegate ad esso. Questo criterio può essere utilizzato se il cliente invia più righe ordine con lo stesso numero PO più volte durante il giorno e desidera raggruppare tutte le righe in un'unica spedizione. In altre parole, ci sarà una polizza di carico e un documento di trasporto.

### <a name="create-example-policy-4"></a>Crea un criterio di esempio 4

In questo esempio, creerai un criterio *Clienti che consentono il consolidamento* che può essere utilizzato per il seguente caso aziendale:

- Il criterio richiederà uno specifico pool di ordini per identificare i clienti che accettano spedizioni consolidate.
- Il consolidamento con spedizioni aperte è disattivato.
- Il consolidamento viene effettuato tra gli ordini utilizzando i campi selezionati dai criteri CrossOrder predefiniti (per replicare la casella di controllo **Consolida spedizione al rilascio al magazzino** precedente).

- Puoi sovrascrivere la regola su un ordine cliente selezionando un pool di ordini diverso.

Attieniti alla seguente procedura per creare i criteri di consolidamento della spedizione per questo caso aziendale.

1. Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento spedizioni**.
1. Imposta il campo **Tipo di criteri** su *Ordini cliente*.
1. Nel riquadro azioni, seleziona **Nuovo** per creare un criterio con le seguenti impostazioni:

    - **Nome criterio:** *Pool di ordini*
    - **Descrizione criteri:** *Consolida tra ordini in base al pool di ordini*

1. Lascia l'opzione **Consolida con spedizioni aperte** impostata su *No*.
1. Nel riquadro azioni selezionare **Salva**.
1. Nella Scheda dettaglio **Campi di consolidamento**, nell'elenco **Campi rimanenti**, seleziona la riga in cui il campo **Nome campo** è impostato su *Modalità di consegna*.
1. Selezionare il pulsante **Aggiungi** ![Freccia DESTRA.](media/forward-button.png) per spostare il campo nell'elenco **Campi selezionati**.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor delle query, nella scheda **Intervallo**, seleziona **Aggiungi** per aggiungere una riga che ha le seguenti impostazioni alla griglia:

    - **Tabella:** *Ordini cliente*
    - **Tabella derivata:** *Ordini cliente*
    - **Campo:** *Pool*
    - **Criteri:** *ShipCons*

1. Selezionare **OK** per chiudere la finestra di dialogo.

> [!NOTE]
> Per questo caso aziendale, tutte le righe ordine in cui gli ordini cliente appartengono allo stesso pool di ordini verranno consolidate in un'unica spedizione tra ordini cliente per lo stesso conto, magazzino e modalità di trasporto della consegna. In alternativa al pool di ordini, puoi utilizzare qualsiasi altro campo per distinguere un gruppo di clienti e utilizzare l'intestazione dell'ordine cliente per impostazione predefinita. Puoi utilizzare questo approccio se il cliente, non il magazzino, sta guidando la necessità di consolidamento. Nella precedente logica di consolidamento, il magazzino ha guidato la necessità di consolidamento.

### <a name="create-example-policy-5"></a>Crea un criterio di esempio 5

In questo esempio, creerai un criterio *Magazzini che consentono il consolidamento* che può essere utilizzato per il seguente caso aziendale:

- Il criterio richiederà uno specifico pool di ordini per identificare i magazzini che possono consolidare spedizioni.
- Il consolidamento con spedizioni aperte è disattivato.
- Il consolidamento viene effettuato tra gli ordini utilizzando i campi selezionati dai criteri CrossOrder predefiniti (per replicare la casella di controllo **Consolida spedizione al rilascio al magazzino** precedente).

In genere, questo caso aziendale può essere risolto utilizzando i criteri predefiniti in cui è stato creato in [Impostare i criteri di consolidamento iniziali](#initial-policies). Tuttavia, è anche possibile creare manualmente criteri simili seguendo questi passaggi.

1. Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento spedizioni**.
1. Imposta il campo **Tipo di criteri** su *Ordini cliente*.
1. Nel riquadro azioni, seleziona **Nuovo** per creare un criterio con le seguenti impostazioni:

    - **Nome criterio:** *Tra ordini*
    - **Descrizione criterio:** *Consolidamento tra ordini per magazzini specifici*

1. Lascia l'opzione **Consolida con spedizioni aperte** impostata su *No*.
1. Nel riquadro azioni selezionare **Salva**.
1. Nella Scheda dettaglio **Campi di consolidamento**, nel campo **Campi rimanenti**, seleziona la riga in cui il campo **Nome campo** è impostato su *Modalità di consegna*.
1. Selezionare il pulsante **Aggiungi** ![Freccia DESTRA.](media/forward-button.png) per spostare il campo nell'elenco **Campi selezionati**.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, trova la riga in cui il campo **Campo** è impostato su *Magazzino* e imposta il campo **Criteri** per quella riga su *61, 63*.
1. Selezionare **OK** per chiudere la finestra di dialogo.

### <a name="set-the-order"></a>Configura l'ordine

Ora che hai creato tutti i tuoi criteri, devi stabilire l'ordine in cui verranno applicati. Per utilizzare un approccio simile a una piramide, in cui i criteri che presentano il maggior numero di condizioni vengono valutati con la massima priorità, attieniti alla seguente procedura.

1. Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento spedizioni**.
1. Imposta il campo **Tipo di criteri** su *Ordini cliente*.
1. Seleziona ciascun criterio elencato nella colonna sinistra, quindi utilizza i pulsanti **Sposta su** e **Sposta giù** nel riquadro azioni per disporre i criteri nel seguente ordine:

    1. CustomerMode
    1. Tipo di articolo
    1. CustomerOrderNo
    1. Pool di ordini
    1. Tra ordini
    1. Predefinita

## <a name="example-scenarios-of-how-to-use-shipment-consolidation-policies"></a><a name="example-scenarios"></a> Scenari di esempio su come utilizzare i criteri di consolidamento delle spedizioni

I seguenti scenari illustrano come è possibile utilizzare i criteri di consolidamento delle spedizioni create durante la lettura di questo articolo. Ogni scenario passa attraverso il processo di consolidamento della spedizione che utilizza criteri di consolidamento delle spedizioni durante il rilascio automatico e manuale al magazzino:

- Scenario 1: [Consolidare le spedizioni quando vengono rilasciate al magazzino utilizzando Rilascio automatico degli ordini cliente](../warehousing/consolidate-shipments-automatic.md)
- Scenario 2: [Consolidare le spedizioni quando i criteri di consolidamento delle spedizioni vengono ignorati dalla pagina Rilascia in magazzino](../warehousing/consolidate-shipments-release-to-warehouse-override.md)
- Scenario 3: [Consolidare le spedizioni utilizzando Rilascia in magazzino dal workbench di pianificazione del carico](../warehousing/consolidate-shipments-load-planning-workbench.md)
- Scenario 4: [Consolidare le spedizioni utilizzando il workbench di consolidamento delle spedizioni](../warehousing/consolidate-shipments-manual-workbench.md)
- Scenario 5: [Consolidare le spedizioni manualmente utilizzando la pagina Consolida spedizioni](../warehousing/consolidate-shipments-manual-form.md)


## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica dei criteri di consolidamento delle spedizioni](about-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
