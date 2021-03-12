---
title: Configurazione dei criteri di consolidamento delle spedizioni
description: Questo argomento spiega come impostare criteri di consolidamento delle spedizioni predefiniti e personalizzati.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, TMSMode, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 0d6ab6c034a5c341432f661cf1e729dfd3e5c239
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996399"
---
# <a name="configure-shipment-consolidation-policies"></a>Configurazione dei criteri di consolidamento delle spedizioni

[!include [banner](../includes/banner.md)]

Il processo di consolidamento della spedizione che utilizza criteri di consolidamento della spedizione consente il consolidamento automatico della spedizione durante il rilascio automatico e manuale al magazzino. Dopo aver attivato questa funzionalità, è necessario configurare i criteri iniziali. Se non sono configurati criteri, ogni riga di vendita genererà una spedizione separata con una sola riga di carico.

Gli scenari presentati in questo argomento mostrano come impostare criteri di consolidamento delle spedizioni predefiniti e personalizzati.

## <a name="turn-on-the-shipment-consolidation-policies-feature"></a>Attiva la funzionalità Criteri di consolidamento spedizione

> [!IMPORTANT]
> Nel [primo scenario](#scenario-1) che è descritto in questo argomento, devi prima impostare un magazzino in modo che utilizzi la funzione di consolidamento della spedizione precedente. Renderai quindi disponibili i criteri di consolidamento della spedizione. In questo modo, puoi provare come funziona lo scenario di aggiornamento. Se prevedi di utilizzare un ambiente dati dimostrativo per conoscere il primo scenario, non attivare la funzionalità prima di eseguire lo scenario.

Prima di poter usare la funzionalità *Criteri di consolidamento spedizione*, devi attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzione:** *Consolida spedizione*

## <a name="make-demo-data-available"></a>Rendi disponibili i dati dimostrativi

Ogni scenario in questo argomento fa riferimento a valori e record inclusi nei dati demo standard forniti per Microsoft Dynamics 365 Supply Chain Management. Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica su **USMF** prima di iniziare.

## <a name="scenario-1-configure-default-shipment-consolidation-policies"></a><a name="scenario-1"></a>Scenario 1: configurare i criteri di consolidamento delle spedizioni predefiniti

Esistono due situazioni in cui è necessario configurare il numero minimo di criteri predefiniti dopo aver attivato la funzionalità *Criteri di consolidamento della spedizione*:

- Stai aggiornando un ambiente che contiene già dati.
- Stai configurando un ambiente completamente nuovo.

### <a name="upgrade-an-environment-where-warehouses-are-already-configured-for-cross-order-consolidation"></a>Aggiorna un ambiente in cui i magazzini sono già configurati per il consolidamento tra ordini

Quando avvii questa procedura, la funzionalità *Criteri di consolidamento della spedizione* deve essere disattivata per simulare un ambiente in cui è già stata utilizzata la funzionalità di consolidamento tra ordini di base. Utilizzerai quindi la gestione delle funzionalità per attivare la funzione, in modo da poter imparare come impostare i criteri di consolidamento della spedizione dopo l'aggiornamento.

Attieniti alla seguente procedura per impostare i criteri di consolidamento delle spedizioni predefiniti in un ambiente in cui i magazzini sono già stati configurati per il consolidamento tra ordini.

1. Selezionare **Gestione magazzino \> Impostazioni \> Magazzino \> Magazzini**.
1. Nell'elenco, trova e apri il record di magazzino desiderato (ad esempio, magazzino *24* nei dati dimostrativi **USMF**).
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nella Scheda dettaglio **Magazzino**, imposta l'opzione **Consolida spedizione al rilascio al magazzino** su *Sì*.
1. Ripeti i passaggi da 2 a 4 per tutti gli altri magazzini in cui è richiesto il consolidamento.
1. Chiudere la pagina.
1. Usare la [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per abilitare la funzionalità *Criteri di consolidamento della spedizione*. Nell'area di lavoro **Gestione funzionalità**, la funzione è denominata *Consolida spedizione*.
1. Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento della spedizione**. Potrebbe essere necessario aggiornare il browser per vedere la nuova voce di menu **Criteri di consolidamento della spedizione** dopo aver abilitato la funzione.
1. Nel riquadro azioni, seleziona **Crea impostazione predefinita** per creare i seguenti criteri:

    - Un criterio **CrossOrder** per il tipo di criteri *Ordini cliente* (a condizione che si disponga di almeno un magazzino impostato per utilizzare la funzionalità di consolidamento precedente)
    - Un criterio **Predefinito** per il tipo di criterio *Ordini cliente*
    - Un criterio **Predefinito** per il tipo di criterio *Uscita di trasferimento*
    - Un criterio **CrossOrder** per il tipo di criteri *Uscita di trasferimento* (a condizione che si disponga di almeno un magazzino impostato per utilizzare la funzionalità di consolidamento precedente)

    > [!NOTE]
    > - Entrambi i criteri **CrossOrder** considerano lo stesso insieme di campi della logica precedente, ad eccezione del campo per il numero dell'ordine. Questo campo viene utilizzato per consolidare le righe nelle spedizioni, in base a fattori quali magazzino, modalità di trasporto della consegna e indirizzo.
    > - Entrambi i criteri **Predefinito** considerano lo stesso insieme di campi della logica precedente, incluso il campo per il numero dell'ordine. Questo campo viene utilizzato per consolidare le righe nelle spedizioni, in base a fattori quali numero di ordine, magazzino, modalità di trasporto della consegna e indirizzo.

1. Seleziona il criterio **CrossOrder** per il tipo di criterio *Ordini cliente*, quindi, nel riquadro azioni, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor di query, notare che i magazzini in cui l'opzione **Consolida spedizione al rilascio al magazzino** è impostata su *Sì* sono elencati. Pertanto, sono inclusi nella query.

### <a name="create-default-policies-for-a-new-environment"></a>Crea criteri predefiniti per un nuovo ambiente

Segui questi passaggi per impostare i criteri di consolidamento delle spedizioni predefinite in un ambiente completamente nuovo.

1. Usare la [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per abilitare la funzionalità *Criteri di consolidamento della spedizione*, se non è stata già abilitata. Nell'area di lavoro **Gestione funzionalità**, la funzione è denominata *Consolida spedizione*.
1. Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento della spedizione**.
1. Nel riquadro azioni, seleziona **Crea impostazione predefinita** per creare i seguenti criteri:

    - Un criterio **Predefinito** per il tipo di criterio *Ordini cliente*
    - Un criterio **Predefinito** per il tipo di criterio *Uscita di trasferimento*

    > [!NOTE]
    > Entrambi i criteri **Predefinito** considerano lo stesso insieme di campi della logica precedente, incluso il campo per il numero dell'ordine. Questo campo viene utilizzato per consolidare le righe nelle spedizioni, in base a fattori quali numero di ordine, magazzino, modalità di trasporto della consegna e indirizzo.

## <a name="scenario-2-configure-custom-shipment-consolidation-policies"></a>Scenario 2: configurare i criteri di consolidamento delle spedizioni personalizzati

Questo scenario mostra come impostare criteri di consolidamento delle spedizioni personalizzati. I criteri personalizzati possono supportare requisiti aziendali complessi in cui il consolidamento della spedizione dipende da diverse condizioni. Per ciascun criterio di esempio più avanti in questo scenario, è inclusa una breve descrizione del caso aziendale. Questi criteri di esempio dovrebbero essere impostati in una sequenza che garantisca una valutazione piramidale delle query. In altre parole, i criteri che presentano il maggior numero di condizioni dovrebbero essere valutati come aventi la massima priorità.

### <a name="turn-on-the-feature-and-prepare-master-data-for-this-scenario"></a>Attiva la funzione e prepara i dati master per questo scenario

Prima di poter eseguire gli esercizi in questo scenario, è necessario attivare la funzione e preparare i dati master necessari per eseguire il filtro, come descritto nelle sottosezioni seguenti. Questi prerequisiti si applicano anche agli scenari elencati in [Scenari di esempio su come utilizzare i criteri di consolidamento della spedizione](#example-scenarios).

#### <a name="turn-on-the-feature-and-create-the-default-policies"></a>Attiva la funzione e crea i criteri predefiniti

Utilizza la gestione delle funzionalità per attivare la funzione, se non è già stata attivata e crea i criteri di consolidamento predefiniti descritti nello [scenario 1](#scenario-1).

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

1. Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento della spedizione**.
1. Imposta il campo **Tipo di criteri** su *Ordini cliente*.
1. Nel riquadro azioni, seleziona **Nuovo** per creare un criterio con le seguenti impostazioni:

    - **Nome criterio:** *CustomerMode*
    - **Descrizione criterio:** *Conto cliente e modalità di consegna*

1. Lascia l'opzione **Consolida con spedizioni aperte** impostata su *No*.
1. Nel riquadro azioni selezionare **Salva**.
1. Nella Scheda dettaglio **Campi di consolidamento**, nell'elenco **Campi rimanenti**, seleziona la riga in cui il campo **Nome campo** è impostato su *Modalità di consegna*.
1. Seleziona il pulsante **Aggiungi** ![Freccia destra](media/forward-button.png) per spostare il campo sull'elenco **Campi selezionati**.
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

1. Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento della spedizione**.
1. Imposta il campo **Tipo di criteri** su *Ordini cliente*.
1. Nel riquadro azioni, seleziona **Nuovo** per creare un criterio con le seguenti impostazioni:

    - **Nome criteri:** *Tipo di articolo*
    - **Descrizione criterio:** *Consolida lo stesso tipo di articolo tra ordini*

1. Imposta l'opzione **Consolida con spedizioni aperte** su *Sì*.
1. Nel riquadro azioni selezionare **Salva**.
1. Nella Scheda dettaglio **Campi di consolidamento**, nell'elenco **Campi rimanenti**, seleziona la riga in cui il campo **Nome campo** è impostato su *Modalità di consegna*.
1. Seleziona il pulsante **Aggiungi** ![Freccia destra](media/forward-button.png) per spostare il campo sull'elenco **Campi selezionati**.
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

1. Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento della spedizione**.
1. Imposta il campo **Tipo di criteri** su *Ordini cliente*.
1. Nel riquadro azioni, seleziona **Nuovo** per creare un criterio con le seguenti impostazioni:

    - **Nome criteri:** *CustomerOrderNo*
    - **Descrizione criterio:** *Consolida righe in base al PO cliente*

1. Imposta l'opzione **Consolida con spedizioni aperte** su *Sì*.
1. Nel riquadro azioni selezionare **Salva**.
1. Nella Scheda dettaglio **Campi di consolidamento**, nell'elenco **Campi rimanenti**, seleziona la riga in cui il campo **Nome campo** è impostato su *Richiesta di approvvigionamento cliente*.
1. Seleziona il pulsante **Aggiungi** ![Freccia destra](media/forward-button.png) per spostare il campo sull'elenco **Campi selezionati**.
1. Nell'elenco **Campi rimanenti**, seleziona la riga in cui il campo **Nome campo** è impostato su *Modalità di consegna*.
1. Seleziona il pulsante **Aggiungi** ![Freccia destra](media/forward-button.png) per spostare il campo sull'elenco **Campi selezionati**.
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

1. Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento della spedizione**.
1. Imposta il campo **Tipo di criteri** su *Ordini cliente*.
1. Nel riquadro azioni, seleziona **Nuovo** per creare un criterio con le seguenti impostazioni:

    - **Nome criterio:** *Pool di ordini*
    - **Descrizione criteri:** *Consolida tra ordini in base al pool di ordini*

1. Lascia l'opzione **Consolida con spedizioni aperte** impostata su *No*.
1. Nel riquadro azioni selezionare **Salva**.
1. Nella Scheda dettaglio **Campi di consolidamento**, nell'elenco **Campi rimanenti**, seleziona la riga in cui il campo **Nome campo** è impostato su *Modalità di consegna*.
1. Seleziona il pulsante **Aggiungi** ![Freccia destra](media/forward-button.png) per spostare il campo sull'elenco **Campi selezionati**.
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

In genere, questo caso aziendale può essere risolto utilizzando i criteri predefiniti in cui è stato creato nello [scenario 1](#scenario-1). Tuttavia, è anche possibile creare manualmente criteri simili seguendo questi passaggi.

1. Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento della spedizione**.
1. Imposta il campo **Tipo di criteri** su *Ordini cliente*.
1. Nel riquadro azioni, seleziona **Nuovo** per creare un criterio con le seguenti impostazioni:

    - **Nome criterio:** *Tra ordini*
    - **Descrizione criterio:** *Consolidamento tra ordini per magazzini specifici*

1. Lascia l'opzione **Consolida con spedizioni aperte** impostata su *No*.
1. Nel riquadro azioni selezionare **Salva**.
1. Nella Scheda dettaglio **Campi di consolidamento**, nel campo **Campi rimanenti**, seleziona la riga in cui il campo **Nome campo** è impostato su *Modalità di consegna*.
1. Seleziona il pulsante **Aggiungi** ![Freccia destra](media/forward-button.png) per spostare il campo sull'elenco **Campi selezionati**.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, trova la riga in cui il campo **Campo** è impostato su *Magazzino* e imposta il campo **Criteri** per quella riga su *61, 63*.
1. Selezionare **OK** per chiudere la finestra di dialogo.

### <a name="set-the-order"></a>Configura l'ordine

Ora che hai creato tutti i tuoi criteri, devi stabilire l'ordine in cui verranno applicati. Per utilizzare un approccio simile a una piramide, in cui i criteri che presentano il maggior numero di condizioni vengono valutati con la massima priorità, attieniti alla seguente procedura.

1. Vai a **Gestione magazzino \> Impostazione \>Rilascia in magazzino \> Criteri di consolidamento della spedizione**.
1. Imposta il campo **Tipo di criteri** su *Ordini cliente*.
1. Seleziona ciascun criterio elencato nella colonna sinistra, quindi utilizza i pulsanti **Sposta su** e **Sposta giù** nel riquadro azioni per disporre i criteri nel seguente ordine:

    1. CustomerMode
    1. Tipo di articolo
    1. CustomerOrderNo
    1. Pool di ordini
    1. Tra ordini
    1. Predefinita

## <a name="example-scenarios-of-how-to-use-shipment-consolidation-policies"></a><a name="example-scenarios"></a> Scenari di esempio su come utilizzare i criteri di consolidamento della spedizione

I seguenti scenari illustrano come è possibile utilizzare i criteri di consolidamento della spedizione create durante la lettura di questo argomento. Ogni scenario passa attraverso il processo di consolidamento della spedizione che utilizza criteri di consolidamento della spedizione durante il rilascio automatico e manuale al magazzino:

- Scenario 1: [Consolidare le spedizioni quando vengono rilasciate al magazzino utilizzando Rilascio automatico degli ordini cliente](../warehousing/consolidate-shipments-automatic.md)
- Scenario 2: [Consolidare le spedizioni quando i criteri di consolidamento delle spedizioni vengono ignorati dalla pagina Rilascia in magazzino](../warehousing/consolidate-shipments-release-to-warehouse-override.md)
- Scenario 3: [Consolidare le spedizioni utilizzando Rilascia in magazzino dal workbench di pianificazione del carico](../warehousing/consolidate-shipments-load-planning-workbench.md)
- Scenario 4: [Consolidare le spedizioni utilizzando il workbench di consolidamento delle spedizioni](../warehousing/consolidate-shipments-manual-workbench.md)
- Scenario 5: [Consolidare le spedizioni manualmente utilizzando la pagina Consolida spedizioni](../warehousing/consolidate-shipments-manual-form.md)


## <a name="additional-resources"></a>Risorse aggiuntive

- [Criteri consolidamento spedizione](about-shipment-consolidation-policies.md)
