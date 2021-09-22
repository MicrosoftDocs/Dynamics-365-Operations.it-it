---
title: Criteri flessibili di prenotazione delle dimensioni a livello di magazzino
description: In questo argomento vengono descritti i criteri di prenotazione di inventario che consentono alle aziende che vendono prodotti tracciati in batch ed eseguono la propria logistica come operazioni abilitate WMS di prenotare batch specifici per gli ordini cliente, anche se la gerarchia di prenotazioni associata ai prodotti impedisce la prenotazione di specifici batch.
author: perlynne
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSReservationHierarchy, WHSWorkTrans, WHSWorkInventTrans, WHSInventTableReservationHierarchy, WHSReservationHierarchyCreate, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 0fe4b377ec80601f616f81f71222129256dfd448
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474942"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a>Criteri flessibili di prenotazione delle dimensioni a livello di magazzino

[!include [banner](../includes/banner.md)]

Quando una gerarchia di prenotazioni di inventario di tipo *Batch-below\[location\]* è associata ai prodotti, le aziende che vendono prodotti tracciati in batch ed eseguono la propria logistica come operazioni abilitate per il sistema di gestione del magazzino (Warehouse Management System, WMS) di Microsoft Dynamics 365 non possono prenotare specifici batch di tali prodotti per gli ordini cliente.

Allo stesso modo, le targhe specifiche non possono essere prenotate per i prodotti negli ordini cliente quando tali prodotti sono associati alla gerarchia di prenotazione predefinita.

Questo argomento descrive i criteri di prenotazione delle scorte che consentono a queste aziende di prenotare specifici batch o targhe, anche quando i prodotti sono associati ad una gerarchia di prenotazioni *Batch-below\[location\]*.

## <a name="inventory-reservation-hierarchy"></a>Gerarchia di prenotazioni di inventario

Questa sezione riassume la gerarchia di prenotazioni di inventario esistente.

La gerarchia di prenotazione dell'inventario stabilisce che, per quanto riguarda le dimensioni di immagazzinamento, l'ordine di domanda specifica le dimensioni obbligatorie di sito, magazzino e stato dell'inventario. In altre parole, le dimensioni obbligatorie sono tutte le dimensioni sopra la dimensione dell'ubicazione nella gerarchia di prenotazione, mentre la logica del magazzino è responsabile dell'assegnazione di un'ubicazione alle quantità richieste e della prenotazione dell'ubicazione. Nelle interazioni tra l'ordine con domanda e le operazioni di magazzino, l'ordine di domanda dovrebbe indicare da dove deve essere spedito l'ordine (ovvero, quale sito e magazzino). Il magazzino si affida quindi alla relativa logica per trovare la quantità richiesta nei locali del magazzino.

Tuttavia, per riflettere il modello operativo dell'azienda, le dimensioni di tracciabilità (numeri di batch e di serie) sono soggette a maggiore flessibilità. Una gerarchia di prenotazioni di inventario può rivelarsi appropriata per gli scenari in cui si applicano le seguenti condizioni:

- L'azienda si affida alle proprie operazioni di magazzino per gestire il prelievo di quantità che hanno numeri di batch o di serie *dopo* che le quantità vengono trovate nello spazio di stoccaggio del magazzino. Questo modello viene spesso definito come *Batch-below\[location\]* o *Serial-below\[location\]*. Viene in genere utilizzato quando l'identificazione del numero di batch o di serie di un prodotto non è importante per i clienti che inoltrano la domanda alla società venditrice.
- L'azienda si affida alle proprie operazioni di magazzino per gestire il prelievo di quantità che hanno numeri di batch o di serie *prima* che le quantità vengono trovate nello spazio di stoccaggio del magazzino. Se i numeri di batch o di serie fanno parte di una specifica per ordini di un cliente, vengono registrati nell'ordine con domanda e le operazioni di magazzino che trovano le quantità nel magazzino non possono modificarle. Questo modello viene spesso definito come *Batch-above\[location\]* o *Serial-above\[location\]*. Poiché le dimensioni sopra l'ubicazione sono i requisiti specifici per le domande che devono essere soddisfatte, la logica del magazzino non le allocherà. Queste dimensioni **devono** essere sempre specificate nell'ordine di richiesta o nelle relative prenotazioni.

In questi scenari, la difficoltà risiede nel fatto che una sola gerarchia di prenotazioni di inventario può essere assegnata a ogni prodotto rilasciato. Pertanto, affinché WMS gestisca gli articoli tracciati, dopo che l'assegnazione della gerarchia determina quando il numero di batch o di serie deve essere prenotato (quando viene preso l'ordine con domanda o durante il lavoro di prelievo in magazzino), questa tempistica non può essere modificata su una base ad-hoc.

## <a name="flexible-reservation-for-batch-tracked-items"></a>Prenotazione flessibile per articoli tracciati in batch

### <a name="business-scenario"></a>Scenario aziendale

In questo scenario, una società utilizza una strategia di inventario in cui i prodotti finiti vengono tracciati mediante numeri di batch. Questa società utilizza anche il carico di lavoro WMS. Poiché questo carico di lavoro ha una logica adeguata per la pianificazione e l'esecuzione delle operazioni di prelievo e spedizione in magazzino per articoli abilitati per batch, la maggior parte degli articoli finiti è associata a una gerarchia di prenotazioni di inventario *Batch-below\[location\]*. Il vantaggio di questo tipo di impostazione operativa è che le decisioni (che sono in realtà decisioni di prenotazione) relative a quali batch prelevare e dove stoccarli nel magazzino vengono rinviate fino all'inizio delle operazioni di prelievo in magazzino. Non vengono effettuate quando l'ordine del cliente viene eseguito.

Sebbene la gerarchia di prenotazioni *Batch-below\[location\]* soddisfi pienamente gli obiettivi di business della società, molti dei clienti usuali dell'azienda richiedono lo stesso batch che avevano acquistato in precedenza quando riordinano i prodotti. Pertanto, la società necessita di flessibilità nel modo in cui vengono gestite le regole di prenotazione di batch, di modo che, a seconda della domanda dei clienti per lo stesso articolo, si verifichino i seguenti comportamenti:

- Un numero di batch può essere registrato e prenotato quando l'ordine viene preso dall'addetto alle vendite e non può essere modificato durante le operazioni di magazzino e/o preso da altre domande. Questo comportamento garantisce che il numero di batch ordinato sia spedito al cliente.
- Se il numero di batch non è importante per il cliente, le operazioni di magazzino possono determinare un numero di batch durante il lavoro di prelievo, dopo l'esecuzione della registrazione e della prenotazione dell'ordine cliente.

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a>Consentire la prenotazione di un batch specifico nell'ordine cliente

Per consentire la flessibilità desiderata nel comportamento di prenotazione di batch per gli articoli associati a una gerarchia di prenotazioni di inventario *Batch-below\[location\]*, i responsabili delle scorte devono selezionare la casella di controllo **Consenti prenotazione su ordine con domanda** per il livello **Numero batch** nella pagina **Gerarchie prenotazioni inventario**.

![Rendere flessibile la gerarchia di prenotazioni di inventario.](media/Flexible-inventory-reservation-hierarchy.png)

Quando il livello **Numero batch** nella gerarchia è selezionato, tutte le dimensioni al di sopra di quel livello e fino al livello **Ubicazione** verranno selezionate automaticamente. (per impostazione predefinita, tutte le dimensioni sopra il livello **Ubicazione** sono preselezionate). Questo comportamento riflette la logica in cui tutte le dimensioni nell'intervallo tra il numero di batch e l'ubicazione vengono automaticamente prenotate dopo la prenotazione di un numero di batch specifico nella riga ordine.

> [!NOTE]
> La casella di controllo **Consenti prenotazione su ordine con domanda** si applica solo ai livelli di gerarchia di prenotazioni al di sotto della dimensione di ubicazione magazzino.
>
> **Numero batch** e **Targa** sono gli unici livelli nella gerarchia che sono aperti per i criteri di prenotazione flessibili. In altre parole, non è possibile selezionare la casella di controllo **Consenti prenotazione su ordine con domanda** per il livello **Ubicazione** o **Numero di serie**.
>
> Se la gerarchia di prenotazioni include la dimensione numero di serie (che deve essere sempre inferiore al livello **Numero batch**) e la prenotazione specifica al batch per il numero di batch, il sistema continuerà a gestire le operazioni di prenotazione e prelievo di numeri di serie, in base alle regole che si applicano ai criteri di prenotazione *Serial-below\[location\]*.

In qualsiasi momento, è possibile consentire la prenotazione specifica al batch per una gerarchia di prenotazioni *Batch-below\[location\]* esistente nella distribuzione. Questa modifica non avrà alcun effetto sulle prenotazioni e i lavori di magazzino aperti creati prima della modifica. Tuttavia, la casella di controllo **Consenti prenotazione su ordine con domanda** non può essere deselezionata se esistono operazioni di magazzino problematiche di tipo **Ordinato prenotato**, **Fisico prenotato** o **Ordinato** per uno o più articoli associati a quella gerarchia di prenotazioni.

> [!NOTE]
> Se la gerarchia di prenotazioni esistente di un articolo non consente la specifica del batch nell'ordine, è possibile riassegnarlo a una gerarchia di prenotazioni che consente la specifica del batch, a condizione che la struttura a livello di gerarchia sia la stessa in entrambe le gerarchie. Utilizzare la funzione **Modifica gerarchia prenotazioni per articoli** per eseguire la riassegnazione. Questa modifica potrebbe essere pertinente quando si desidera impedire la prenotazione flessibile di batch per un sottoinsieme di articoli tracciati in batch ma consentirla per il resto del portafoglio prodotti.

Indipendentemente dalla selezione o meno della casella di controllo **Consenti prenotazione su ordine con domanda**, se non si desidera prenotare uno specifico numero di batch per l'articolo in una riga ordine, la logica delle operazioni di magazzino predefinita che è valida per una gerarchia di prenotazioni *Batch-below\[location\]* verrà comunque applicata.

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a>Prenotare un numero di batch specifico per un ordine cliente

Dopo l'impostazione di una gerarchia di prenotazioni di inventario *Batch-below\[location\]* di un articolo tracciato in batch per consentire la prenotazione di specifici numeri di batch negli ordini cliente, gli addetti agli ordini cliente possono prendere gli ordini dei clienti per lo stesso articolo in uno dei seguenti modi, a seconda della richiesta del cliente:

- **Immettere i dettagli dell'ordine senza specificare un numero di batch** - Questo approccio deve essere utilizzato quando la specifica del batch del prodotto non è importante per il cliente. Tutti i processi esistenti associati alla gestione di un ordine di questo tipo nel sistema rimangono invariati. Non sono richieste ulteriori considerazioni da parte degli utenti.
- **Immettere i dettagli dell'ordine e prenotare un numero di batch specifico** - Questo approccio deve essere utilizzato quando il cliente richiede un batch specifico. In genere, i clienti richiedono un batch specifico quando riordinano un prodotto che hanno acquistato in precedenza. Questo tipo di prenotazione specifica al batch è denominato *prenotazione impegnata nell'ordine*.

Il seguente set di regole è valido quando le quantità vengono elaborate e un numero di batch viene impegnato in un ordine specifico:

- Per consentire la prenotazione di un numero di batch specifico per un articolo secondo i criteri di prenotazione *Batch-below\[location\]*, il sistema deve prenotare tutte le dimensioni fino all'ubicazione. Questo intervallo include in genere la dimensione della targa.
- Le direttive sull'ubicazione non vengono utilizzate quando si crea il lavoro di prelievo per una riga di vendita che utilizza la prenotazione di batch impegnata nell'ordine.
- Durante l'elaborazione in magazzino del lavoro per i batch impegnati nell'ordine, né l'utente né il sistema possono modificare il numero di batch. (questa elaborazione include la gestione delle eccezioni).

L'esempio seguente mostra il flusso end-to-end.

## <a name="example-scenario-batch-number-allocation"></a>Scenario di esempio: allocazione del numero di batch

Per questo esempio, i dati dimostrativi devono essere installati ed è necessario utilizzare la società di dati dimostrativi **USMF**.

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a><a name="Example-batch-allocation"></a>Impostare una gerarchia di prenotazioni di inventario per consentire la prenotazione specifica al batch

1. Selezionare **Gestione magazzino** \> **Impostazione** \> **Scorte \> Gerarchia prenotazioni**.
2. Selezionare **Nuovo**.
3. Nel campo **Nome**, immettere un nome (ad esempio **BatchFles**).
4. Nel campo **Descrizione**, immettere una descrizione (ad esempio, **Batch below flessibile**).
5. Nel campo **Selezionato**, selezionare **Numero di serie** e **Proprietario**, quindi selezionare il pulsante freccia sinistra per spostarli nel campo **Disponibile**.
6. Selezionare **OK**.
7. Nella riga per il livello di dimensione **Numero batch**, selezionare la casella di controllo **Consenti prenotazione su ordine con domanda**. I livelli **Targa** e **Ubicazione** vengono selezionati automaticamente e non è possibile deselezionare le caselle di controllo corrispondenti.
8. Selezionare **Salva**.

### <a name="create-a-new-released-product"></a>Creare un nuovo prodotto rilasciato

1. Impostare i tre parametri di dati master del prodotto utilizzando questi valori:

    - Nel campo **Gruppo di dimensioni di immagazzinamento**, selezionare **Magaz**.
    - Nel campo **Gruppo di dimensioni di tracciabilità**, selezionare **Batch-Fis**.
    - Nel campo **Gerarchia prenotazioni** selezionare **BatchFles**.

2. Creare due numeri di batch ad esempio **B11** e **B22**.
3. Aggiungere quantità di articoli allo scorte disponibili utilizzando i seguenti valori.

    | Magazzino | Numero batch | Ubicazione | Targa | Quantità |
    |-----------|--------------|----------|---------------|----------|
    | 24        | B11          | BULK-001 | Nessuna          | 10       |
    | 24        | B11          | FL-001   | LP11          | 10       |
    | 24        | B22          | FL-002   | LP22          | 10       |

### <a name="enter-sales-order-details"></a><a name="sales-order-details"></a>Immettere i dettagli degli ordini cliente

1. Andare a **Vendite e marketing** \> **Ordini cliente** \> **Tutti gli ordini cliente**.
2. Selezionare **Nuovo**.
3. Nell'intestazione dell'ordine cliente, nel campo **Conto cliente**, immettere **US-003**.
4. Aggiungere una riga per il nuovo articolo e immettere **10** come quantità. Assicurarsi che il campo **Magazzino** sia impostato su **24**.
5. Nella scheda dettaglio **Righe ordine cliente** selezionare **Scorte** e quindi nel gruppo **Gestisci**, selezionare **Prenotazione batch**. La pagina **Prenotazione batch** mostra un elenco di batch disponibili per la prenotazione per la riga ordine. Per questo esempio, mostra una quantità **20** per il numero di batch **B11** e una quantità **10** per il numero di batch **B22**. Si noti che non è possibile accedere alla pagina **Prenotazione batch** da una riga se l'articolo in quella riga è associato alla gerarchia di prenotazioni *Batch-below\[location\]* a meno che non sia impostata per consentire la prenotazione specifica al batch.

    > [!NOTE]
    > Per prenotare un batch specifico per un ordine cliente, è necessario utilizzare la pagina **Prenotazione batch**.
    >
    > Se si inserisce il numero di batch direttamente nella riga ordine cliente, il sistema si comporterà come se si fosse immesso un valore di batch specifico per un articolo che è soggetto ai criteri di prenotazione *Batch-below\[location\]*. Quando si salva la riga, viene visualizzato un messaggio di avviso. Se si conferma che il numero di batch deve essere specificato direttamente nella riga ordine, la riga non verrà gestita dalla logica di gestione del magazzino normale.
    >
    > Se si prenota la quantità nella pagina **Prenotazione**, non verrà prenotato alcun batch specifico e l'esecuzione delle operazioni di magazzino per la riga seguirà le regole applicabili in base ai criteri di prenotazione *Batch-below\[location\]*.

    In genere, questa pagina funziona e interagisce nello stesso modo in cui funziona e interagisce con gli articoli a cui è associata una gerarchia di prenotazioni di tipo *Batch-above\[location\]*. Tuttavia, si applicano le seguenti eccezioni:

    - La scheda dettaglio **Numeri di batch impegnati nella riga di origine** mostra i numeri di batch prenotati per la riga ordine. I valori batch nella griglia verranno visualizzati durante l'intero ciclo di evasione della riga ordine, comprese le fasi di elaborazione del magazzino. Invece, nella scheda dettaglio **Panoramica**, la prenotazione normale nella riga ordine (ovvero la prenotazione effettuata per le dimensioni superiori al livello **Ubicazione**) viene visualizzata nella griglia fino al momento in cui viene creato il lavoro di magazzino. L'entità di lavoro gestisce quindi la prenotazione nella riga e questa non viene più visualizzata nella pagina. La scheda dettaglio **Numeri batch impegnati nella riga di origine** consente al gestore degli ordini cliente di visualizzare i numeri di batch che sono stati impegnati nell'ordine del cliente in qualsiasi momento durante il relativo ciclo di vita, fino alla fatturazione.
    - Oltre a prenotare un batch specifico, un utente può selezionare manualmente la targa e l'ubicazione specifiche del batch anziché lasciare al sistema il compito di selezionarli automaticamente. Questa funzionalità è correlata alla progettazione del meccanismo di prenotazione di batch impegnati nell'ordine. Come menzionato precedentemente, quando un numero di batch specifico viene prenotato per un articolo secondo i criteri di prenotazione *Batch-below\[location\]*, il sistema deve prenotare tutte le dimensioni fino all'ubicazione. Pertanto, il lavoro di magazzino avrà le stesse dimensioni di immagazzinamento prenotate dagli utenti che hanno lavorato sugli ordini e a volte potrebbe non rappresentare la posizione di stoccaggio degli articoli più conveniente o addirittura possibile per le operazioni di prelievo. Se i gestori degli ordini sono consapevoli dei vincoli inerenti al magazzino, potrebbero voler selezionare manualmente le targhe e le ubicazioni quando prenotano un batch. In questo caso, l'utente deve utilizzare la funzionalità **Visualizza dimensioni** nell'intestazione della pagina e deve aggiungere l'ubicazione e la targa nella griglia della scheda dettaglio **Panoramica**.

6. Nella pagina **Prenotazione batch**, selezionare la riga per il batch **B11**, quindi selezionare **Prenota riga**. Non esiste una logica designata per l'assegnazione di ubicazioni e targhe durante la prenotazione automatica. È possibile inserire manualmente la quantità nel campo **Prenotazione**. Si noti che nella scheda dettaglio **Numeri batch impegnati nella riga di origine** il batch **B11** è visualizzato come **Impegnato**.

    ![Impegnare un numero di batch specifico in una riga ordine cliente nella pagina Prenotazione batch.](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > La prenotazione della quantità in una riga ordine cliente può essere effettuata su più batch. Allo stesso modo, la prenotazione dello stesso batch può essere effettuata in più ubicazioni e targhe (se le targhe sono abilitate per le ubicazioni).
    >
    > La prenotazione di un batch specifico per la quantità in una riga ordine cliente può anche essere parziale. Ad esempio, la quantità totale di 100 unità può essere prenotata in modo che un batch specifico venga impegnato per 20 unità, mentre 80 unità sono prenotate a livello di sito e magazzino per qualsiasi batch disponibile. In questo caso, WMS gestirà le operazioni di prelievo utilizzando due righe lavoro distinte.

7. Selezionare **Gestione informazioni sul prodotto** \> **Prodotti** \> **Prodotti rilasciati**. Selezionare l'articolo, quindi selezionare **Gestione articoli** \> **Visualizza** \> **Transazioni**.

    ![Prenotazione impegnata dall'ordine come tipo di operazione di magazzino.](media/Inventory-transactions-for-order-committed-reservation.png)

8. Esaminare le operazioni di magazzino dell'articolo correlate alla prenotazione nella riga ordine cliente.

    - Una transazione in cui il campo **Riferimento** è impostato su **Ordine cliente** e il campo **Problema** è impostato su **Fisico prenotato** rappresenta la prenotazione nella riga ordine per le dimensioni inventariali sopra il livello **Ubicazione**. Secondo la gerarchia di prenotazioni di inventario dell'articolo, tali dimensioni sono sito, magazzino e stato dell'inventario.
    - Una transazione in cui il campo **Riferimento** è impostato su **Prenotazione impegnata nell'ordine** e il campo **Problema** è impostato su **Fisico prenotato** rappresenta la prenotazione nella riga ordine per il batch specifico e tutte le dimensioni inventariali superiori. Secondo la gerarchia di prenotazioni di inventario dell'articolo, tali dimensioni sono numero batch e ubicazione. In questo esempio, l'ubicazione è **Bulk-001**.

9. Nell'intestazione dell'ordine cliente, selezionare **Magazzino** \> **Azioni** \> **Rilascio in magazzino**. La riga ordine è ora in ondata e vengono creati un carico e un lavoro.

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a>Esaminare ed elaborare il lavoro di magazzino che ha numeri di batch impegnati nell'ordine

1. Nella scheda dettaglio **Righe ordine cliente**, selezionare **Magazzino** \> **Dettagli lavoro**.

    Il lavoro che gestisce l'operazione di prelievo per le quantità batch impegnate nella riga ordine cliente presenta le seguenti caratteristiche:

    - Per creare lavoro, il sistema utilizza modelli di lavoro ma non direttive sull'ubicazione. Tutte le impostazioni standard definite per i modelli di lavoro, come un numero massimo di righe di prelievo o un'unità di misura specifica, verranno applicate per determinare quando è necessario creare un nuovo lavoro. Tuttavia, le regole associate alle direttive sull'ubicazione per l'identificazione delle ubicazioni di prelievo non vengono prese in considerazione poiché la prenotazione impegnata nell'ordine specifica già tutte le dimensioni inventariali. Tali dimensioni inventariali includono le dimensioni a livello di stoccaggio in magazzino. Pertanto, il lavoro eredita tali dimensioni senza dover consultare le direttive sull'ubicazione.
    - Il numero di batch non viene visualizzato nella riga di prelievo (come nel caso della riga di lavoro creata per un articolo a cui è associata la gerarchia di prenotazioni *Batch-below\[location\]*). Invece, il numero di batch "da" e tutte le altre dimensioni di immagazzinamento vengono visualizzati nell'operazione di magazzino della riga lavoro a cui si fa riferimento dalle operazioni di magazzino associate.

        ![Transazione di magazzino per lavori originati da una prenotazione impegnata dall'ordine.](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - Dopo aver creato il lavoro, l'operazione di magazzino dove il campo **Riferimento** è impostato su **Prenotazione impegnata nell'ordine** viene rimossa. L'operazione di magazzino in cui il campo **Riferimento** è impostato su **Lavoro** ora detiene la prenotazione fisica in tutte le dimensioni inventariali della quantità.

        Le operazioni di magazzino possono procedere alla gestione dell'esecuzione del lavoro nel modo consueto. Tuttavia, le istruzioni sul dispositivo mobile indicheranno al lavoratore di prelevare un numero di batch specifico. In ambienti di magazzino in cui le ubicazioni sono controllate dalla targa, dopo che un lavoratore ha raggiunto un'ubicazione in cui lo stesso batch si trova in più targhe, può prelevare da qualsiasi targa non ancora prenotata (ad esempio, da un'altra prenotazione impegnata nell'ordine o dal lavoro originato da una prenotazione di quel tipo).

        Se risulta poco pratico prelevare dall'ubicazione specificata nella riga lavoro, gli operatori di magazzino possono utilizzare una delle seguenti azioni per reindirizzare il prelievo del batch specifico da un'ubicazione più conveniente:

        - L'azione standard **Ignora ubicazione** su un dispositivo mobile (a condizione che l'impostazione **Consenti override ubicazione prelievo** dell'addetto al magazzino sia abilitata)
        - L'azione **Modifica ubicazione** nella pagina **Dettagli elenco di lavoro**. 

2. Sul dispositivo mobile, terminare il prelievo e lo stoccaggio del lavoro.

    La quantità **10** per il numero di batch **B11** viene ora prelevata per la riga ordine cliente e inserita nell'ubicazione **Baydoor**. A questo punto, è pronta per essere caricata sul camion e spedita all'indirizzo del cliente.

## <a name="flexible-license-plate-reservation"></a>Prenotazione flessibile della targa

### <a name="business-scenario"></a>Scenario aziendale

In questo scenario, un'azienda utilizza la gestione del magazzino e l'elaborazione del lavoro e gestisce la pianificazione del carico a livello di singoli pallet/contenitori al di fuori di Supply Chain Management prima della creazione del lavoro. Questi contenitori sono rappresentati da targhe nelle dimensioni inventariali. Pertanto, per questo approccio, le targhe specifiche devono essere pre-assegnate alle righe degli ordini cliente prima che venga effettuato il lavoro di prelievo. L'azienda è alla ricerca di flessibilità nel modo in cui vengono gestite le regole di prenotazione della targa, in modo che si verifichino i seguenti comportamenti:

- Una targa può essere registrata e prenotata quando l'ordine viene preso dall'addetto alle vendite e non può essere preso da altre domande. Questo comportamento garantisce che la targa pianificata sia spedita al cliente.
- Se la targa non è già assegnata a una riga ordine cliente, il personale del magazzino può selezionare una targa durante il lavoro di prelievo, dopo che la registrazione e la prenotazione dell'ordine cliente sono state completate.

### <a name="turn-on-flexible-license-plate-reservation"></a>Attivare la prenotazione flessibile della targa

Prima di poter utilizzare la prenotazione flessibile della targa, due funzionalità devono essere attivate nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato delle funzionalità e attivarle se sono obbligatorie. È necessario attivare le funzionalità nel seguente ordine:

1. **Nome funzionalità:** *Prenotazione flessibile delle dimensioni a livello di magazzino*
1. **Nome funzionalità:** *Prenotazione flessibile della targa impegnata nell'ordine*

### <a name="reserve-a-specific-license-plate-on-the-sales-order"></a>Prenotare una targa specifica sull'ordine cliente

Per abilitare la prenotazione della targa su un ordine, è necessario selezionare la casella di controllo **Consenti prenotazione su ordine con domanda** per il livello **Targa** nella pagina **Gerarchie prenotazioni inventario** per la gerarchia associata all'articolo pertinente.

![Pagina delle gerarchie di prenotazione dell'inventario per una gerarchia di prenotazione targa flessibile.](media/Flexible-LP-reservation-hierarchy.png)

È possibile abilitare la prenotazione della targa sull'ordine in qualsiasi fase della distribuzione. Questa modifica non avrà alcun effetto sulle prenotazioni o i lavori di magazzino aperti creati prima della modifica. Tuttavia, non è possibile deselezionare la casella di controllo **Consenti prenotazione su ordine con domanda** se esistono operazioni di magazzino con stato di uscita del tipo *Ordinato prenotato*, *Fisico prenotato* o *Ordinato* per uno o più articoli associati a quella gerarchia di prenotazioni.

Anche se la casella di controllo **Consenti prenotazione su ordine con domanda** è selezionata per il livello **Targa**, è comunque possibile *non* prenotare una targa specifica sull'ordine. In questo caso, si applica la logica delle operazioni di magazzino predefinita valida per la gerarchia di prenotazione.

Per prenotare una targa specifica, è necessario utilizzare un processo [Open Data Protocol (OData)](../../fin-ops-core/dev-itpro/data-entities/odata.md). Nell'applicazione puoi effettuare questa prenotazione direttamente da un ordine cliente utilizzando l'opzione **Prenotazioni impegnate su ordine per targa** del comando **Apri in Excel**. Nei dati dell'entità aperti nel componente aggiuntivo di Excel, è necessario inserire i seguenti dati relativi alla prenotazione e quindi selezionare **Pubblica** per inviare nuovamente i dati a Supply Chain Management:

- Riferimento (solo il valore *Ordine cliente* è supportato).
- Numero ordine (il valore può essere derivato dal lotto).
- ID lotto
- Targa
- Quantità

Se è necessario prenotare una targa specifica per un articolo tracciato in lotti, utilizzare la pagina **Prenotazione in lotti**, come descritto nella sezione [Immettere i dettagli dell'ordine cliente](#sales-order-details).

Quando la riga dell'ordine cliente che utilizza una prenotazione della targa impegnata nell'ordine viene elaborata dalle operazioni di magazzino, le direttive di ubicazione non vengono utilizzate.

Se un articolo di lavoro di magazzino è costituito da righe uguali a un pallet completo e include quantità impegnate nella targa, è possibile ottimizzare il processo di prelievo utilizzando una voce di menu del dispositivo mobile in cui l'opzione **Gestisci per targa** è impostata su *Sì*. Un addetto al magazzino può quindi eseguire la scansione di una targa per completare un prelievo invece di eseguire la scansione degli articoli dal lavoro uno per uno.

![Voce di menu del dispositivo mobile in cui l'opzione Gestisci per targa è impostata su Sì.](media/Handle-by-LP-menu-item.png)

Poiché la funzionalità **Gestisci per targa** non supporta il lavoro che copre più pallet, è meglio avere un elemento di lavoro separato per diverse targhe. Per utilizzare questo approccio, aggiungere il campo **ID targa impegnata dall'ordine** come interruzione di intestazione di lavoro della pagina **Modello di lavoro**.

> [!NOTE]
> Per il processo di creazione del lavoro impegnato nell'ordine, alle righe del lavoro di prelievo verrà assegnato un valore "dimensione inventariale impegnata nell'ordine" e non sarà possibile visualizzare direttamente il valore di targa. Solo il processo *Diretto dall'utente* è supportato durante la configurazione di una voce di menu del dispositivo mobile.

## <a name="example-scenario-set-up-and-process-an-order-committed-license-plate-reservation"></a>Scenario di esempio: configurare ed elaborare una prenotazione della targa impegnata da un ordine

Questo scenario mostra come configurare ed elaborare una prenotazione della targa impegnata da un ordine.

### <a name="make-demo-data-available"></a>Rendi disponibili i dati dimostrativi

Questo scenario fa riferimento a valori e record inclusi nei dati dimostrativi standard forniti per Supply Chain Management. Se si desidera elaborarlo utilizzando i valori specificati qui, assicurarsi di utilizzare un ambiente in cui sono installati i dati dimostrativi. Inoltre, impostare la persona giuridica su **USMF** prima di iniziare.

### <a name="create-an-inventory-reservation-hierarchy-that-allows-for-license-plate-reservation"></a>Creare una gerarchia di prenotazione di inventario che consenta la prenotazione della targa

1. Passare a **Gestione magazzino \> Impostazione \> Scorte \> Gerarchia prenotazioni**.
1. Selezionare **Nuovo**.
1. Nel campo **Nome**, immettere un valore (ad esempio *FlexibleLP*).
1. Nel campo **Descrizione**, immettere un valore (ad esempio, *Prenotazione targa flessibile*).
1. Nell'elenco **Selezionato**, selezionare **Numero di lotto**, **Numero di serie** e **Proprietario**.
1. Selezionare il pulsante **Rimuovi** ![Freccia INDIETRO](media/backward-button.png) per spostare i record selezionati nell'elenco **Disponibili**.
1. Selezionare **OK**.
1. Nella riga per il livello di dimensione **Targa**, selezionare la casella di controllo **Consenti prenotazione su ordine con domanda**. Il livello **Targa** viene selezionato automaticamente e non è possibile deselezionare la casella di controllo corrispondente.
1. Selezionare **Salva**.

### <a name="create-two-released-products"></a>Creare due prodotti rilasciati

1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Nuovo prodotto rilasciato**, imposta i seguenti valori:

    - **Numero di prodotto:** *Item1*
    - **Numero articolo:** *Item1*
    - **Gruppo di modelli di articoli:** *FIFO*
    - **Gruppo di articoli:** *Audio*
    - **Gruppo di dimensioni di immagazzinamento:** *Ondata*
    - **Gruppo di dimensioni di tracciabilità:** *Nessuno*
    - **Gerarchia di prenotazione:** *FlexibleLP*

1. Selezionare **OK** per creare il prodotto e chiudere la finestra di dialogo.
1. Il nuovo prodotto è aperto. Nella Scheda dettaglio **Magazzino**, impostare il campo **ID gruppo di sequenze unità** su *ea*.
1. Ripetere i passaggi precedenti per creare un secondo prodotto con le stesse impostazioni, ma impostare i campi **Numero prodotto** e **Numero articolo** su *Item2*.
1. Nel riquadro azioni della scheda **Gestione articoli**, nel gruppo **Visualizza**, selezionare **Scorte disponibili**. Quindi selezionare **Rettifica quantità**.
1. Regola le scorte disponibili dei nuovi articoli come specificato nella tabella seguente.

    | Articolo  | Magazzino | Posizione | Targa | Quantità |
    |-------|-----------|----------|---------------|----------|
    | Item1 | 24        | FL-010   | LP01          | 10       |
    | Item1 | 24        | FL-011   | LP02          | 10       |
    | Item2 | 24        | FL-010   | LP01          | 5        |
    | Item2 | 24        | FL-011   | LP02          | 5        |

    > [!NOTE]
    > È necessario creare le due targhe e utilizzare ubicazioni che consentano articoli misti, ad esempio *FL-010* e *FL-011*.

### <a name="create-a-sales-order-and-reserve-a-specific-license-plate"></a>Creare un ordine cliente e prenotare una targa specifica

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Conto cliente:** *US-001*
    - **Magazzino:** *24*

1. Selezionare **OK** per chiudere la finestra di dialogo **Crea ordine cliente** e aprire il nuovo ordine cliente.
1. Nella Scheda dettaglio **Righe ordine cliente**, aggiungere una riga che abbia le seguenti impostazioni:

    - **Numero articolo:** *Item1*
    - **Quantità:** *10*

1. Aggiungere una seconda riga ordine cliente con le seguenti impostazioni:

    - **Numero articolo:** *Item2*
    - **Quantità:** *5*

1. Selezionare **Salva**.
1. Nella Scheda dettaglio **Dettagli riga**, nella scheda **Imposta**, prendere nota del valore di **ID lotto** per ogni riga. Questi valori saranno richiesti durante la prenotazione di targhe specifiche.

    > [!NOTE]
    > Per prenotare una targa specifica, è necessario utilizzare l'entità di dati **Prenotazioni impegnate su ordine per targa**. Per prenotare un articolo tracciato in lotti su una targa specifica, è possibile anche utilizzare la pagina **Prenotazione in lotti**, come descritto nella sezione [Immettere i dettagli dell'ordine cliente](#sales-order-details).
    >
    > Se si immette la targa direttamente nella riga dell'ordine cliente e la si conferma nel sistema, l'elaborazione della gestione del magazzino non verrà utilizzata per la riga.

1. Selezionare **Apri in Microsoft Office**, selezionare **Prenotazioni impegnate su ordine per targa** e scaricare il file.
1. Aprire il file scaricato in Excel e selezionare **Abilita modifica** per attivare il componente aggiuntivo di Excel da eseguire.
1. Se si esegue per la prima volta il componente aggiuntivo di Excel, selezionare **Considera attendibile questo componente aggiuntivo**.
1. Se viene richiesto di accedere, selezionare **Accedi**, quindi accedere utilizzando le stesse credenziali usate per l'accesso a Supply Chain Management.
1. Per prenotare un articolo su una targa specifica, nel componente aggiuntivo di Excel, selezionare **Nuovo** per aggiungere una riga di prenotazione e quindi impostare i seguenti valori:

    - **ID lotto:** immettere il valore **ID lotto** trovato per la riga ordine cliente per *item1*.
    - **Targa:** *LP02*
    - **ReservedInventoryQuantity:** *10*

1. Seleziona **Nuova** per aggiungere un'altra riga di prenotazione, quindi impostare i seguenti valori:

    - **ID lotto:** immettere il valore **ID lotto** trovato per la riga ordine cliente per *item2*.
    - **Targa:** *LP02*
    - **ReservedInventoryQuantity:** *5*

1. Nel componente aggiuntivo di Excel, selezionare **Pubblica** per inviare nuovamente i dati a Supply Chain Management.

    > [!NOTE]
    > La riga di prenotazione apparirà nel sistema solo se la pubblicazione viene completata senza errori.

1. Tornare a Supply Chain Management. 
1. Per rivedere la prenotazione dell'articolo, nella Scheda dettaglio **Righe ordine cliente**, nel menu **Inventario**, selezionare **Gestisci \> Prenotazione**. Tenere presente che, per la riga ordine cliente per *Item1*, vengono prenotate scorte dell'ordine di *10*, mentre per la riga ordine cliente per *Item2*, vengono prenotate scorte pari a *5*.
1. Per rivedere le transazioni di magazzino correlate alla prenotazione della riga ordine cliente, nella Scheda dettaglio **Righe ordine cliente**, nel menu **Inventario**, selezionare **Visualizza \> Transazioni**. Si noti che esistono due transazioni correlate alla prenotazione: una in cui il campo **Riferimento** è impostato su *Ordine cliente* e una dove il campo **Riferimento** è impostato su *Prenotazione impegnata dall'ordine*.

    > [!NOTE]
    > Una transazione in cui il campo **Riferimento** è impostato su *Ordine cliente* rappresenta la prenotazione nella riga ordine per le dimensioni inventariali superiori al livello **Ubicazione** (sito, magazzino e stato inventario). Una transazione in cui il campo **Riferimento** è impostato su *Prenotazione impegnata dall'ordine* rappresenta la prenotazione della riga ordine per la targa e l'ubicazione specifiche.

1. Per rilasciare l'ordine cliente, nel riquadro azioni, nella scheda **Magazzino**, nel gruppo **Azioni**, selezionare **Rilascia in magazzino**.

### <a name="review-and-process-warehouse-work-with-order-committed-license-plates-assigned"></a>Rivedere ed elaborare il lavoro di magazzino con le targhe impegnate dagli ordini assegnate

1. Nella scheda dettaglio **Righe ordine cliente**, nel menu **Magazzino**, seleziona **Dettagli lavoro**.

    Come quando viene effettuata la prenotazione per un batch specifico, il sistema non utilizza le direttive di ubicazione quando crea il lavoro per l'ordine cliente vendita che utilizza la prenotazione della targa. Poiché la prenotazione impegnata nell'ordine specifica tutte le dimensioni inventariali, inclusa l'ubicazione, non è necessario utilizzare le direttive di ubicazione, poiché tali dimensioni inventariali vengono solo inserite nel lavoro. Vengono mostrate nella sezione **Dalle dimensioni inventariali** della pagina **Transazioni di inventario lavoro**.

    > [!NOTE]
    > Dopo aver creato il lavoro, l'operazione di magazzino dove il campo **Riferimento** è impostato su *Prenotazione impegnata nell'ordine* viene rimossa. L'operazione di magazzino in cui il campo **Riferimento** è impostato su *Lavoro* ora detiene la prenotazione fisica in tutte le dimensioni inventariali della quantità.

1. Sul dispositivo mobile, completa il prelievo e l'inserimento del lavoro utilizzando una voce di menu in cui la casella di controllo **Gestisci per targa** è selezionata.

    > [!NOTE]
    > La funzionalità **Gestisci per targa** consente di elaborare l'intera targa. Se è necessario elaborare parte della targa, non è possibile utilizzare questa funzionalità.
    >
    > Si consiglia di generare un lavoro separato per ciascuna targa. Per ottenere questo risultato, utilizzare la funzionalità **Suddivisioni intestazione lavoro** della pagina **Modello di lavoro**.

    La targa *LP02* viene ora selezionata per le righe ordine cliente e inserita nell'ubicazione *Baydoor*. A questo punto, è pronta per essere caricata e spedita al cliente.

## <a name="exception-handling-of-warehouse-work-that-has-order-committed-batch-numbers"></a>Gestione delle eccezioni per lavoro di magazzino che ha numeri batch impegnati nell'ordine

Il lavoro di magazzino per il prelievo di numeri batch impegnati nell'ordine è soggetto alle stesse azioni e gestione standard delle eccezioni di magazzino del lavoro normale. In generale, il lavoro o la riga lavoro aperto può essere annullato, interrotto perché l'ubicazione di un utente è piena, prelevato in modo insufficiente e aggiornato a causa di un movimento. Allo stesso modo, la quantità di lavoro prelevata che è già stata completata può essere ridotta oppure il lavoro può essere stornato.

La seguente regola chiave viene applicata a tutte queste azioni di gestione delle eccezioni: il numero di batch prenotato per il cliente non può mai essere sostituito con un numero di batch differente, ma le relative dimensioni di immagazzinamento (ubicazione e targa) possono essere modificate mediante un aggiornamento manuale effettuato dall'utente o un aggiornamento automatico eseguito dal sistema. L'aggiornamento automatico si basa sulla stessa assegnazione casuale delle dimensioni di immagazzinamento che è stata applicata quando un batch specifico è stato prenotato automaticamente ma non sono state specificate dimensioni di immagazzinamento.

### <a name="example-scenario"></a>Scenario di esempio

Un esempio di questo scenario è una situazione in cui il prelievo di un lavoro precedentemente completato viene annullato utilizzando la funzione **Riduci quantità prelevata**. Questo esempio presuppone che siano già completati i passaggi descritti in [Scenario di esempio: allocazione del numero di batch](#Example-batch-allocation). Continua da quell'esempio.

1. Selezionare **Gestione magazzino** \> **Carichi** \> **Carichi attivi**.
2. Seleziona il carico che è stato creato in relazione alla spedizione dell'ordine cliente.
3. Nella scheda dettaglio **Carica righe ordine**, selezionare **Riduci quantità prelevata**.
4. Nella pagina **Riduce quantità prelevata**, nel campo **Sposta nell'ubicazione**, seleziona **FL-001**.
5. Nel campo **Passa a targa** selezionare **LP33**.
6. Nella griglia, nel campo **Quantità inventario per annullamento prelievo**, immettere **10**.
7. Selezionare **OK**.

Di seguito sono riportati i risultati dell'azione di annullamento del prelievo:

- Lo stato del lavoro chiuso precedentemente diventa **Annullato**.
- Un nuovo lavoro di tipo **Movimenti scorte** viene creato per la quantità **10** non prelevata per il numero di batch **B11**. Questo lavoro rappresenta il movimento dall'ubicazione **Baydoor** alla targa **LP33** nell'ubicazione **FL-001**. Lo stato diventa **Chiuso**.
- Il sistema prenota nuovamente il numero di batch originariamente ordinato e assegna gli ID ubicazione e targa (questo processo equivale all'esecuzione della funzione **Prenota riga** per la riga ordine per un determinato numero di batch). Di conseguenza, il batch **B11** viene visualizzato come impegnato nella scheda **Numeri batch impegnati nella riga di origine** della pagina **Prenotazione batch** e il campo **Prenotazione** contiene la quantità **10** per il numero di batch **B11**. Inoltre, il campo **Ubicazione** è impostato su **FL-001** e il campo **Targa** è impostato su **LP11** (è possibile aggiungere questi campi alla griglia se non sono visibili).

Le tabelle seguenti forniscono una panoramica che mostra come il sistema gestisce la prenotazione di batch impegnati nell'ordine per specifiche azioni di magazzino. Per interpretare il contenuto delle tabelle, è necessario supporre che ogni azione di magazzino venga eseguita nel contesto di un lavoro di magazzino esistente originato da una prenotazione batch impegnata nell'ordine o che l'esecuzione di ogni azione di magazzino influisce sul lavoro di quel tipo.

> [!NOTE]
> In queste tabelle, la colonna "Quantità batch disponibile" indica se è disponibile una quantità batch oltre alla quantità già prenotata per le prenotazioni impegnate nell'ordine correnti o già prenotata dal lavoro di magazzino originato da prenotazioni di quel tipo.

#### <a name="override-the-pick-location-on-the-open-work"></a>Override dell'ubicazione di prelievo nel lavoro aperto

<table>
<thead>
<tr>
<th>Parametro di impostazione chiave</th>
<th>Quantità batch disponibile</th>
<th>Passaggi utente chiave</th>
<th>Lavoro di magazzino</th>
<th>Prenotazione batch impegnata dall'ordine</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>L'opzione <strong>Consenti override ubicazione prelievo</strong> è abilitata per il lavoratore.</td>
<td>Sì</td>
<td>
<ol>
<li>Seleziona la voce di menu <strong>Ignora ubicazione</strong> nell'app per dispositivi mobili Gestione magazzino quando inizi il lavoro di prelievo.</li>
<li>Selezionare <strong>Suggerisci</strong>.</li>
<li>Confermare la nuova ubicazione suggerita in base alla disponibilità della quantità batch.</li>
</ol>
</td>
<td>Nel lavoro corrente, si verificano le seguenti azioni:
<ul>
<li>L'ubicazione nella riga di prelievo viene aggiornata alla nuova ubicazione (se l'ubicazione è controllata dalla targa, una targa casuale viene assegnata all'operazione di magazzino e il lavoratore può prelevare da qualsiasi targa che abbia la quantità disponibile).</li>
<li>Se la quantità viene trovata in più targhe nella nuova ubicazione, la riga di prelievo originale viene suddivisa in più righe per corrispondere a ciascuna targa.</li>
</ul>
</td>
<td>Non applicabile</td>
</tr>
<tr>
<td>Nessuno</td>
<td>
<ol>
<li>Seleziona la voce di menu <strong>Ignora ubicazione</strong> nell'app per dispositivi mobili Gestione magazzino quando inizi il lavoro di prelievo.</li>
<li>Immettere un'ubicazione manualmente.</li>
</ol>
</td>
<td>L'azione <strong>Ignora ubicazione</strong> non è possibile. Non viene eseguita correttamente e viene generato un errore.</td>
<td>Non applicabile</td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a>Pulsante Completo - Suddividere una riga lavoro a causa dell'overflow nell'ubicazione dell'utente

<table>
<thead>
<tr>
<th>Parametro di impostazione chiave</th>
<th>Quantità batch disponibile</th>
<th>Passaggi utente chiave</th>
<th>Lavoro di magazzino</th>
<th>Prenotazione batch impegnata dall'ordine</th>
</tr>
</thead>
<tbody>
<tr>
<td>L'opzione <strong>Consenti suddivisione del lavoro</strong> è abilitata nella voce di menu sul dispositivo mobile.</td>
<td>Non applicabile</td>
<td>
<ol>
<li>Seleziona la voce di menu <strong>Completo</strong> nell'app per dispositivi mobili Gestione magazzino quando elabori il lavoro di prelievo.</li>
<li>Nel campo <strong>Qtà prelievo</strong>, immettere una quantità parziale del prelievo necessario per indicare la piena capacità.</li>
</ol>
</td>
<td>
<ul>
<li>Nel lavoro corrente, la quantità viene aggiornata alla quantità rimanente che deve essere prelevata.</li>
<li>Il nuovo lavoro per la quantità prelevata viene creato e chiuso.</li>
</ul></td>
<td>Non applicabile</td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a>Ridurre la quantità prelevato del lavoro completato (da un carico)

<table>
<thead>
<tr>
<th>Parametro di impostazione chiave</th>
<th>Quantità batch disponibile</th>
<th>Passaggi utente chiave</th>
<th>Lavoro di magazzino</th>
<th>Prenotazione batch impegnata dall'ordine</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>Non applicabile</td>
<td>Sì</td>
<td>
<ol>
<li>Aprire la pagina <strong>Riduci quantità prelevata</strong> dalla riga di carico.</li>
<li>Immettere la quantità completa per la quale annullare il prelievo.</li>
<li>Selezionare un'ubicazione/targa "sposta in".</li>
</ol>
</td>
<td>
<ul> 
<li>Il lavoro associato alla riga di carico viene annullato.</li>
<li>Il nuovo lavoro per il movimento scorte viene creato e chiuso.</li>
</ul>
</td>
<td>La quantità viene prenotata nuovamente per lo stesso batch. Il sistema assegna a caso un'ubicazione e una targa (se l'ubicazione è controllata dalla targa) in cui la quantità è disponibile.</td>
</tr>
<tr>
<td>Nessuno</td>
<td>Vedere la riga precedente.</td>
<td>Vedere la riga precedente.</td>
<td>La quantità viene prenotata nuovamente per lo stesso batch e per le stesse ubicazione e targa (se l'ubicazione è controllata dalla targa) immesse durante l'annullamento del prelievo.</td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a>Spostare un articolo in un magazzino

> [!NOTE]
> Questa azione di magazzino è applicabile solo a un movimento di tipo **Processo di creazione lavoro**, non al movimento per modello.

<table>
<thead>
<tr>
<th>Parametro di impostazione chiave</th>
<th>Quantità batch disponibile</th>
<th>Passaggi utente chiave</th>
<th>Lavoro di magazzino</th>
<th>Prenotazione batch impegnata dall'ordine</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>L'opzione <strong>Consenti movimento di magazzino e lavoro associato</strong> è abilitata per il lavoratore.</td>
<td>Sì</td>
<td>
<ol>
<li>Inizia un movimento nell'app per dispositivi mobili Gestione magazzino.</li>
<li>Immettere le ubicazioni "da" e "a".</li>
</ol></td>
<td>
<ul>
<li>Per tutto il lavoro esistente interessato dallo spostamento, l'ubicazione di prelievo viene aggiornata alla nuova ubicazione "a".</li>
<li>Il nuovo lavoro per il movimento scorte viene creato e chiuso.</li>
</ul>
</td>
<td>Tutte le prenotazioni esistenti interessate dal movimento di quantità dall'ubicazione specificata vengono ripetute per lo stesso batch. Il sistema assegna a caso un'ubicazione e una targa (se l'ubicazione è controllata dalla targa) in cui la quantità è disponibile.</td>
</tr>
<tr>
<td>Nessuno</td>
<td>Vedere la riga precedente.</td>
<td>Vedere la riga precedente.</td>
<td>Tutte le prenotazioni esistenti interessate dal movimento di quantità dall'ubicazione indicata vengono ripetute per lo stesso batch e per la nuova targa e ubicazione "a" (se l'ubicazione è controllata dalla targa).</td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a>Stornare la quantità prelevata di lavoro completato (da un carico o un'ondata)

<table>
<thead>
<tr>
<th>Parametro di impostazione chiave</th>
<th>Quantità batch disponibile</th>
<th>Passaggi utente chiave</th>
<th>Lavoro di magazzino</th>
<th>Prenotazione batch impegnata dall'ordine</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'>Non applicabile</td>
<td>Sì</td>
<td>
<ol>
<li>Aprire la pagina <strong>Storna lavoro</strong>.</li>
<li>Nella pagina della richiesta, selezionare l'opzione <strong>Lascia articoli nell'ubicazione corrente</strong>.</li>
</ol>
</td>
<td>Tutto il lavoro associato al carico viene annullato.</td>
<td>La quantità viene prenotata nuovamente per lo stesso batch. Il sistema assegna a caso un'ubicazione e una targa (se l'ubicazione è controllata dalla targa) in cui la quantità è disponibile.</td>
</tr>
<tr>
<td>Nessuno</td>
<td>Vedere la riga precedente.</td>
<td>Vedere la riga precedente.</td>
<td>La quantità viene prenotata nuovamente per lo stesso batch e per l'ubicazione e la targa in cui la quantità è stata lasciata al momento dello storno.</td>
</tr>
<tr>
<td>Sì</td>
<td>
<ol>
<li>Aprire la pagina <strong>Storna lavoro</strong>.</li>
<li>Nella pagina della richiesta, selezionare l'opzione <strong>Assegna articoli a questa ubicazione</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>Il lavoro corrente viene annullato.</li>
<li>Il nuovo lavoro per il movimento scorte viene creato e chiuso.</li>
</ul>
</td>
<td>La quantità viene prenotata nuovamente per lo stesso batch. Il sistema assegna a caso un'ubicazione e una targa (se l'ubicazione è controllata dalla targa) in cui la quantità è disponibile.</td>
</tr>
<tr>
<td>Nessuno</td>
<td>Vedere la riga precedente.</td>
<td>Vedere la riga precedente.</td>
<td>La quantità viene prenotata nuovamente per lo stesso batch e per l'ubicazione e la targa a cui la quantità è stata assegnata al momento dello storno.</td>
</tr>
<tr>
<td>Sì/No</td>
<td>
<ol>
<li>Aprire la pagina <strong>Storna lavoro</strong>.</li>
<li>Nella pagina della richiesta, selezionare l'opzione <strong>Sposta articoli a questa ubicazione</strong>.</li>
</ol>
</td>
<td>Lo storno non è supportato.</td>
<td>Non applicabile</td>
</tr>
<tr>
<td>Sì/No</td>
<td>
<ol>
<li>Aprire la pagina <strong>Storna lavoro</strong>.</li>
<li>Nella pagina della richiesta, selezionare l'opzione <strong>Sposta articoli in base alle direttive ubicazione</strong>.</li>
</ol>
</td>
<td>Lo storno non è supportato. </td>
<td>Non applicabile</td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a>Prelevare in difetto una quantità - Registrare la quantità come fisicamente non trovata nell'ubicazione/targa durante il lavoro di prelievo

<table>
<thead>
<tr>
<th>Parametro di impostazione chiave</th>
<th>Quantità batch disponibile</th>
<th>Passaggi utente chiave</th>
<th>Lavoro di magazzino</th>
<th>Prenotazione batch impegnata dall'ordine</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>Un'eccezione lavoro di tipo <strong>Prelievo in difetto</strong> è impostata, dove <strong>Riallocazione articolo</strong> = <strong>Nessuna</strong>, <strong>Correggi magazzino</strong> = <strong>Sì</strong> e <strong>Rimuovi prenotazioni</strong> = <strong>No</strong>.</td>
<td>Sì</td>
<td>
<ol>
<li>Seleziona la voce di menu <strong>Prelievo in difetto</strong> nell'app per dispositivi mobili Gestione magazzino quando esegui il lavoro di prelievo.</li>
<li>Nel campo <strong>Quantità prelievo</strong> immettere <strong>0</strong> (zero).</li>
<li>Nel campo <strong>Motivo</strong>, immettere <strong>Nessuna riallocazione</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>Il lavoro corrente viene chiuso e la quantità prelevata è 0 (zero).</li>
<li>Un'operazione di magazzino di tipo <strong>Conteggio</strong> e il tipo di problema <strong>Venduto</strong> vengono creati per rappresentare la rettifica.</li>
</ul>
</td>
<td>La quantità viene prenotata nuovamente per lo stesso batch. Il sistema assegna a caso un'ubicazione e una targa (se l'ubicazione è controllata dalla targa) in cui la quantità è disponibile.</td>
</tr>
<tr>
<td>Nessuno</td>
<td>Vedere la riga precedente.</td>
<td>
<ul>
<li>L'azione di prelievo in difetto non riesce e viene generato un errore.</li>
<li>Il lavoro corrente rimane aperto.</li>
</ul>
</td>
<td>Non applicabile</td>
</tr>
<tr>
<td rowspan='2'>Un'eccezione lavoro di tipo <strong>Prelievo in difetto</strong> è impostata, dove <strong>Riallocazione articolo</strong> = <strong>Nessuna</strong>, <strong>Correggi magazzino</strong> = <strong>Sì</strong> e <strong>Rimuovi prenotazioni</strong> = <strong>Sì</strong>.</td>
<td>Sì</td>
<td>
<ol>
<li>Seleziona la voce di menu <strong>Prelievo in difetto</strong> nell'app per dispositivi mobili Gestione magazzino quando esegui il lavoro di prelievo.</li>
<li>Nel campo <strong>Quantità prelievo</strong> immettere <strong>0</strong> (zero).</li>
<li>Nel campo <strong>Motivo</strong>, immettere <strong>Nessuna riallocazione</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>Il lavoro corrente viene chiuso e la quantità prelevata è 0 (zero).</li>
<li>Un'operazione di magazzino di tipo <strong>Conteggio</strong> e il tipo di problema <strong>Venduto</strong> vengono creati per rappresentare la rettifica.</li>
</ul>
</td>
<td>Tutte le prenotazioni esistenti interessate dalla rettifica della quantità nell'ubicazione del prelievo in difetto vengono ripetute per lo stesso batch. Il sistema assegna a caso un'ubicazione e una targa (se l'ubicazione è controllata dalla targa) in cui la quantità è disponibile.</td>
</tr>
<tr>
<td>Nessuno</td>
<td>Vedere la riga precedente.</td>
<td>Vedere la riga precedente.</td>
<td>Tutte le prenotazioni esistenti interessate dalla rettifica della quantità nell'ubicazione del prelievo in difetto vengono rimosse per lo stesso batch.</td>
</tr>
<tr>
<td>Un'eccezione lavoro di tipo <strong>Prelievo in difetto</strong> è impostata, dove <strong>Riallocazione articolo</strong> = <strong>Manuale</strong>, <strong>Correggi magazzino</strong> = <strong>Sì</strong> e <strong>Rimuovi prenotazioni</strong> = <strong>Sì</strong>. Inoltre, l'opzione <strong>Consenti riallocazione manuale articolo</strong> è abilitata per il lavoratore.</td>
<td>Sì</td>
<td>
<ol>
<li>Seleziona la voce di menu <strong>Prelievo in difetto</strong> nell'app per dispositivi mobili Gestione magazzino quando esegui il lavoro di prelievo.</li>
<li>Nel campo <strong>Quantità prelievo in difetto</strong> immettere <strong>0</strong> (zero).</li>
<li>Nel campo <strong>Motivo</strong>, selezionare <strong>Prelievo in difetto con riallocazione manuale</strong>.</li>
<li>Selezionare l'ubicazione/targa nell'elenco.</li>
</ol>
</td>
<td>
<ul>
<li>Nel lavoro corrente, si verificano le seguenti azioni:
<ul>
<li>La riga di prelievo viene chiusa e la quantità prelevata è 0 (zero).</li>
<li>La riga di stoccaggio viene cancellata.</li>
<li>Viene creata una nuova riga di prelievo. che utilizza l'ubicazione/la targa che l'utente ha selezionato.</li>
<li>Viene creata una nuova riga di stoccaggio.</li>
</ul>
</li>
<li>Un'operazione di magazzino di tipo <strong>Conteggio</strong> e il tipo di problema <strong>Venduto</strong> vengono creati per rappresentare la rettifica.</li>
</ul>
</td>
<td>Non applicabile</td>
</tr>
<tr>
<td>Un'eccezione lavoro di tipo <strong>Prelievo in difetto</strong> è impostata, dove <strong>Riallocazione articolo</strong> = <strong>Manuale</strong>, <strong>Correggi magazzino</strong> = <strong>Sì</strong> e <strong>Rimuovi prenotazioni</strong> = <strong>No</strong>. Inoltre, l'opzione <strong>Consenti riallocazione manuale articolo</strong> è abilitata per il lavoratore.</td>
<td>Nessuno</td>
<td>
<ol>
<li>Seleziona la voce di menu <strong>Prelievo in difetto</strong> nell'app per dispositivi mobili Gestione magazzino quando esegui il lavoro di prelievo.</li>
<li>Nel campo <strong>Quantità prelievo in difetto</strong> immettere <strong>0</strong> (zero).</li>
<li>Nel campo <strong>Motivo</strong>, selezionare <strong>Prelievo in difetto con riallocazione manuale</strong>.</li>
</ol>
</td>
<td>L'azione di prelievo in difetto non riesce e viene generato un errore.</td>
<td>Non applicabile</td>
</tr>
<tr>
<td>Un'eccezione lavoro di tipo <strong>Prelievo in difetto</strong> è impostata, dove <strong>Riallocazione articolo</strong> = <strong>Manuale</strong>, <strong>Correggi magazzino</strong> = <strong>Sì</strong> e <strong>Rimuovi prenotazioni</strong> = <strong>Sì</strong>. Inoltre, l'opzione <strong>Consenti riallocazione manuale articolo</strong> è abilitata per il lavoratore.</td>
<td>Nessuno</td>
<td>
<ol>
<li>Seleziona la voce di menu <strong>Prelievo in difetto</strong> nell'app per dispositivi mobili Gestione magazzino quando esegui il lavoro di prelievo.</li>
<li>Nel campo <strong>Quantità prelievo in difetto</strong> immettere <strong>0</strong> (zero).</li>
<li>Nel campo <strong>Motivo</strong>, selezionare <strong>Prelievo in difetto con riallocazione manuale</strong>.</li>
<li>Selezionare l'ubicazione/targa nell'elenco.</li>
</ol>
</td>
<td>
<ul>
<li>Nel lavoro corrente, si verificano le seguenti azioni:
<ul>
<li>La riga di prelievo viene chiusa e la quantità prelevata è 0 (zero).</li>
<li>La riga di stoccaggio viene cancellata.</li>
</ul>
</li>
<li>Un'operazione di magazzino di tipo <strong>Conteggio</strong> e il tipo di problema <strong>Venduto</strong> vengono creati per rappresentare la rettifica.</li>
</ul>
</td>
<td>Tutte le prenotazioni esistenti interessate dalla rettifica della quantità nell'ubicazione/targa del prelievo in difetto vengono rimosse per lo stesso batch.</td>
</tr>
<tr>
<td>Un'eccezione lavoro di tipo <strong>Prelievo in difetto</strong> è impostata, dove <strong>Riallocazione articolo</strong> = <strong>Automatica</strong>, <strong>Correggi magazzino</strong> = <strong>Sì/No</strong> e <strong>Rimuovi prenotazioni</strong> = <strong>Sì/No</strong>.</td>
<td>Non applicabile</td>
<td>
<ol>
<li>Seleziona la voce di menu <strong>Prelievo in difetto</strong> nell'app per dispositivi mobili Gestione magazzino quando esegui il lavoro di prelievo.</li>
<li>Nel campo <strong>Quantità prelievo in difetto</strong> immettere <strong>0</strong> (zero).</li>
<li>Nel campo <strong>Motivo</strong>, selezionare <strong>Prelievo in difetto con riallocazione automatica</strong>.</li>
</ol>
</td>
<td>Il prelievo in difetto che comporta la riallocazione automatica non è supportato.</td>
<td>Il prelievo in difetto che comporta la riallocazione automatica non è supportato.</td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a>Cambia lo stato magazzino

> [!NOTE]
> Questa azione di magazzino può essere eseguita da più punti di ingresso. L'esempio che viene mostrato qui utilizza l'azione **Modifica stato inventario** nella pagina **Disponibili per ubicazione**.

<table>
<thead>
<tr>
<th>Parametro di impostazione chiave</th>
<th>Quantità batch disponibile</th>
<th>Passaggi utente chiave</th>
<th>Lavoro di magazzino</th>
<th>Prenotazione batch impegnata dall'ordine</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>Nella scheda <strong>Magazzino</strong>, nel record <strong>Magazzino</strong>, il campo <strong>Rimuovi prenotazioni e contrassegni</strong> è impostato su <strong>Prenotazioni</strong> o <strong>Contrassegni e prenotazioni</strong>.</td>
<td>Sì</td>
<td>
<ol>
<li>Selezionare un'ubicazione specifica.</li>
<li>Selezionare una riga con un articolo, un'ubicazione e una targa specifici (se l'ubicazione è controllata dalla targa).</li>
<li>Selezionare <strong>Modifica stato inventario</strong>.</li>
<li>Impostare il campo <strong>Stato inventario</strong> su <strong>Blocco</strong>.</li>
</ol>
</td>
<td>Le modifiche allo stato dell'inventario non sono consentite per le quantità prenotate per il lavoro.</td>
<td>
<ul>
<li>La quantità viene prenotata nuovamente per lo stesso batch. Il sistema assegna a caso un'ubicazione e una targa (se l'ubicazione è controllata dalla targa) in cui la quantità è disponibile.</li>
<li>Due operazioni di magazzino di tipo <strong>Modifica stato inventario</strong> vengono create per rappresentare la modifica nella dimensione stato inventario.</li>
<li>Un'operazione di magazzino di tipo <strong>Blocco scorte</strong> e il tipo di problema <strong>Fisico prenotato</strong> vengono creati per rappresentare la prenotazione della quantità bloccata.</li>
</ul>
</td>
</tr>
<tr>
<td>Nessuno</td>
<td>Vedere la riga precedente.</td>
<td>Le modifiche allo stato dell'inventario non sono consentite per le quantità prenotate per il lavoro.</td>
<td>
<ul>
<li>La prenotazione viene rimossa.</li>
<li>Due operazioni di magazzino di tipo <strong>Modifica stato inventario</strong> vengono create per rappresentare la modifica nella dimensione stato inventario.</li>
<li>Un'operazione di magazzino di tipo <strong>Blocco scorte</strong> e il tipo di problema <strong>Fisico prenotato</strong> vengono creati per rappresentare la prenotazione della quantità bloccata.</li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'>Nella scheda <strong>Magazzino</strong>, nel record <strong>Magazzino</strong>, il campo <strong>Rimuovi prenotazioni e contrassegni</strong> è impostato su <strong>Nssuno</strong>.</td>
<td>Sì</td>
<td>
<ol>
<li>Selezionare un'ubicazione specifica.</li>
<li>Selezionare una riga con un articolo, un'ubicazione e una targa specifici (se l'ubicazione è controllata dalla targa).</li>
<li>Selezionare <strong>Modifica stato inventario</strong>.</li>
<li>Impostare il campo <strong>Stato inventario</strong> su <strong>Blocco</strong>.</li>
</ol>
</td>
<td>Le modifiche allo stato dell'inventario non sono consentite per le quantità prenotate per il lavoro.</td>
<td>La quantità viene prenotata nuovamente per lo stesso batch. Il sistema assegna a caso un'ubicazione e una targa (se l'ubicazione è controllata dalla targa) in cui la quantità è disponibile.</td>
</tr>
<tr>
<td>Nessuno</td>
<td>Vedere la riga precedente.</td>
<td>Le modifiche allo stato dell'inventario non sono consentite per le quantità prenotate per il lavoro.</td>
<td>Le modifiche allo stato dell'inventario non sono consentite.</td>
</tr>
</tbody>
</table>

## <a name="limitations"></a>Limiti

- I criteri flessibili di prenotazione delle dimensioni a livello di magazzino non supportano le seguenti funzionalità:

    - Gestione del peso variabile
    - Scorte fisiche negative
    - Prenotazione contro fornitura ordinata
    - Ordini di trasferimento e prelievo di materie prime

- La regola di consolidamento dei contenitori per l'imballaggio per unità direttiva presenta dei limiti. Per le prenotazioni impegnate in ordini, si consiglia di non utilizzare modelli di build contenitore dove il campo **Imballa per unità direttiva** è abilitato. Nella progettazione attuale, le direttive di ubicazione non vengono utilizzate durante la creazione di lavoro di magazzino. Pertanto, solo l'unità più bassa nel gruppo di sequenze unità (l'unità di magazzino) viene applicata durante il passaggio ondata di containerizzazione.

## <a name="see-also"></a>Vedere anche

- [Numeri batch in Gestione magazzino](/dynamicsax-2012/appuser-itpro/batch-numbers-in-warehouse-management)
- [Prenotare lo stesso lotto per un ordine cliente](../sales-marketing/reserve-same-batch-sales-order.md)
- [Prelevare il batch meno recente su un dispositivo mobile](pick-oldest-batch.md)
- [Conferma batch e targa](batch-and-license-plate-confirmation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]