---
title: Pianificazione generale con previsioni della domanda
description: Questo articolo spiega come includere previsioni della domanda durante la pianificazione generale.
author: t-benebo
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqPlanSched, ReqGroup, ReqReduceKey, ForecastModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 79a25d6fc5c809947b5b92a32cc00c9a3cc73202
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739785"
---
# <a name="master-planning-with-demand-forecasts"></a>Pianificazione generale con previsioni della domanda

[!include [banner](../../includes/banner.md)]

È possibile utilizzare una previsione della domanda per tenere conto della domanda prevista nella pianificazione generale. È possibile creare manualmente una previsione della domanda, importarla o generarla utilizzando la funzionalità di previsione della domanda in Microsoft Dynamics 365 Supply Chain Management. Per ulteriori informazioni sulla previsione della domanda, vedere [Panoramica previsioni della domanda](../introduction-demand-forecasting.md).

> [!NOTE]
> La pianificazione della previsione separata non è supportata con l'ottimizzazione della pianificazione. Di conseguenza, l'impostazione **Piano previsionale corrente** nella pagina **Parametri di pianificazione generale** non ha alcun effetto quando si utilizza l'ottimizzazione della pianificazione.

## <a name="set-up-a-master-plan-to-include-a-demand-forecast"></a>Impostare un piano generale per includere una previsione della domanda

Per configurare un piano generale in modo che includa una previsione della domanda, seguire questi passaggi.

1. Andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**.
1. Selezionare un piano esistente o crearne uno nuovo.
1. Nella scheda dettaglio **Generale**, impostare i seguenti campi:

    - **Modello previsionale** - Selezionare il modello previsionale da applicare. Questo modello verrà preso in considerazione quando viene generato un suggerimento di fornitura per il piano generale corrente.
    - **Includi previsione della domanda** - Impostare questa opzione su *Sì* per includere la previsione della domanda nel piano generale corrente. Se si imposta questa opzione su *No*, le transazioni di previsione della domanda non verranno incluse nel piano generale.
    - **Metodo utilizzato per ridurre i requisiti di previsione** - Selezionare il metodo da utilizzare per ridurre i requisiti di previsione. Per ulteriori informazioni, vedi la sezione [Chiavi di riduzione previsionali](#reduction-keys) più avanti in questo articolo.

1. Nella Scheda dettaglio **Intervallo temporale in giorni**, è possibile impostare i seguenti campi per specificare il periodo durante il quale la previsione della domanda è inclusa:

    - **Piano previsionale** - Impostare questa opzione su *Sì* per sostituire l'intervallo temporale del piano previsionale che ha origine dai singoli gruppi di copertura. Impostare l'opzione su *No* per utilizzare i valori dei singoli gruppi di copertura per il piano generale corrente.
    - **Periodo di tempo previsto** - Se si imposta l'opzione **Piano previsionale** su *Sì*, specificare il numero di giorni (dalla data odierna) in cui deve essere applicata la previsione della domanda.

    > [!IMPORTANT]
    > L'impostazione **Piano previsionale** non è supportata con l'ottimizzazione della pianificazione.

## <a name="set-up-a-coverage-group-to-include-a-demand-forecast"></a>Impostare un gruppo di copertura per includere una previsione della domanda

Per configurare un gruppo di copertura in modo che includa una previsione della domanda, seguire questi passaggi.

1. Andare a **Pianificazione generale \> Impostazioni \> Piani \> Gruppi di copertura**.
1. Selezionare un gruppo di copertura esistente o creare un nuovo gruppo.
1. Nella Scheda dettaglio **Altro**, impostare i seguenti campi:

    - **Intervallo temporale di piano previsionale** - Immettere il numero di giorni (dalla data odierna) per i quali deve essere applicata la previsione della domanda. Questo valore può essere sostituito utilizzando l'opzione **Piano previsionale** nel piano generale, come descritto nella sezione precedente.
    - **Chiave di riduzione** - Selezionare la chiave di riduzione da applicare. Per ulteriori informazioni, vedi le sezioni [Creare e impostare una chiave di riduzione previsionale](#create-reduction-key) e [Utilizzare una chiave di riduzione](#use-reduction-key) più avanti in questo articolo.
    - **Riduci previsione per** - Per i piani generali in cui il campo **Metodo utilizzato per ridurre i requisiti di previsione** è impostato su *Transazioni - chiave di riduzione* o *Transazioni - periodo dinamico*, specificare quali transazioni devono ridurre la previsione. Selezionare uno dei seguenti valori:

        - **Tutte le transazioni** - Tutte le transazioni devono ridurre la previsione.
        - **Ordini** - Solo gli ordini cliente devono ridurre la previsione.

        > [!NOTE]
        > Se si seleziona *Tutte le transazioni*, le transazioni che hanno domanda e offerta nelle stesse dimensioni inventariali sono considerate neutre e vengono ignorate durante la riduzione della previsione. Ad esempio, se la dimensione di pianificazione è impostata solo su sito e non su magazzino, un ordine di trasferimento tra il sito 1, magazzino 11 e sito 1, magazzino 13, verrà ignorato e non ridurrà la previsione della domanda rimanente.

    - **Includi ordini interaziendali** - Impostare questa opzione su *Sì* se gli ordini interaziendali devono essere inclusi quando la previsione viene ridotta. Altrimenti, impostare l'opzione su *No*.
    - **Includi previsione del cliente nella previsione della domanda** - Specificare se una previsione del cliente deve essere inclusa nella previsione generale. Questa opzione determina in che modo la domanda effettiva riduce la domanda prevista. L'utilizzo di questa opzione consente di assicurarsi che la pianificazione generale copra la fornitura di articoli acquistati da clienti specifici.

        - Impostare questa opzione su *Sì* per includere una previsione del cliente nella previsione generale. In questo caso, la domanda effettiva del cliente riduce sia la previsione del cliente che la previsione complessiva. La pianificazione generale genera ordini pianificati per coprire solo la quantità di previsione globale.
        - Impostare questa opzione su *No* se non si desidera includere una previsione del cliente nella previsione generale. In questo caso, la domanda effettiva del cliente riduce solo la previsione del cliente. La pianificazione generale genera ordini pianificati per coprire sia la quantità di previsione globale che la previsione per la quantità di ciascun cliente.

## <a name="forecast-reduction-keys"></a><a name="reduction-keys"></a>Chiavi di riduzione previsionali

Questa sezione fornisce informazioni sui differenti metodi utilizzati per ridurre i requisiti di previsione. Include esempi dei risultati di ogni metodo. Descrive inoltre come creare, impostare e utilizzare una chiave di riduzione previsionale. Alcuni metodi utilizzano una chiave di riduzione previsionale per ridurre requisiti di previsione.

### <a name="methods-that-are-used-to-reduce-forecast-requirements"></a>Metodi utilizzati per ridurre i requisiti di previsione

Quando si include una previsione in un piano generale, è possibile selezionare il modo in cui ridurre i requisiti di previsione quando viene inclusa la domanda effettiva. Si noti che la pianificazione generale esclude i requisiti di previsione passati, il che significa tutti i requisiti di previsione prima della data odierna.

Per includere una previsione in un piano generale e selezionare il metodo utilizzato per ridurre i requisiti di previsione, andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**. Selezionare un modello previsionale nel campo **Modello previsionale**. Nel campo **Metodo utilizzato per ridurre i requisiti di previsione**, selezionare un metodo. Sono disponibili le opzioni seguenti:

- Nessuno
- Percentuale - chiave di riduzione
- Transazioni - chiave di riduzione
- Transazioni - periodo dinamico

Nelle sezioni seguenti vengono fornite altre informazioni sui ogni opzione.

#### <a name="none"></a>Nessuno

Se si sceglie **Nessuno**, i requisiti di previsione non vengono ridotti durante la programmazione generale. In questo caso, la pianificazione generale crea ordini pianificati per fornire la domanda prevista (requisiti di previsione). Questi ordini pianificati mantengono la quantità suggerita, indipendentemente da altri tipi di domande. Ad esempio, se vengono effettuati ordini cliente, la pianificazione generale crea ulteriori ordini pianificati per fornire ordini cliente. La quantità dei requisiti di previsione non viene ridotta.

#### <a name="percent--reduction-key"></a>Percentuale - chiave di riduzione

Se si seleziona **Percentuale - chiave di riduzione**, i requisiti di previsione sono ridotti in base alle percentuali e ai periodi definiti dalla chiave di riduzione. In questo caso, la pianificazione generale crea ordini pianificati in cui la quantità viene calcolata come Quantità prevista × chiave di riduzione in ogni periodo. Se sono presenti altri tipi di domande, la pianificazione generale crea anche ordini pianificati per fornire la domanda.

##### <a name="example-percent--reduction-key"></a>Esempio: Percentuale - chiave di riduzione

In questo esempio viene illustrato come una chiave di riduzione riduce i requisiti di previsione della domanda in base alle percentuali e ai periodi definiti dalla chiave di riduzione.

Per questo esempio, includere la seguente previsione della domanda in un piano generale.

| Mese    | Previsione della domanda |
|----------|-----------------|
| gennaio  | 1.000           |
| febbraio | 1.000           |
| marzo    | 1.000           |
| aprile    | 1.000           |

Nella pagina **Chiavi di riduzione** impostare le seguenti righe.

| Modifica | Unità  | Percentuale |
|--------|-------|---------|
| 1      | Mese | 100     |
| 2      | Mese | 75      |
| 3      | Mese | 50      |
| 4      | Mese | 25      |

La chiave di riduzione viene assegnata al gruppo di copertura dell'articolo. Quindi, nella pagina **Piani generali**, nel campo **Metodo utilizzato per ridurre i requisiti di previsione**, selezionare **Percentuale - chiave di riduzione**.

In questo caso, se si esegue una programmazione previsionale il 1° gennaio, i requisiti di previsione della domanda vengono consumati in base alle percentuali definite nella pagina **Chiavi di riduzione**. Vengono trasferite al piano generale le quantità di requisiti che seguono.

| Mese                | Quantità dell'ordine pianificato | Calcolo    |
|----------------------|------------------------|----------------|
| gennaio              | 0                      | = 0% × 1.000   |
| febbraio             | 250                    | = 25% × 1.000  |
| marzo                | 500                    | = 50% × 1.000  |
| aprile                | 750                    | = 75% × 1.000  |
| Da maggio a dicembre | 1.000                  | = 100% × 1.000 |

#### <a name="transactions--reduction-key"></a>Transazioni - chiave di riduzione

Se si imposta il campo **Metodo utilizzato per ridurre i requisiti di previsione** in *Transazioni - chiave di riduzione*, i requisiti previsti vengono ridotti dalle transazioni della domanda qualificata che si verificano durante i periodi definiti dalla chiave di riduzione.

La domanda qualificata è definita dal campo **Riduci previsione per** sulla pagina **Gruppi di copertura**. Se si imposta il campo **Riduci previsione per** su *Ordini*, solo le transazioni dell'ordine cliente sono considerate domanda qualificata. Se si lo imposta su *Tutte le transazioni*, qualsiasi transazione di inventario in uscita non interaziendale è considerata domanda qualificata. Se anche gli ordini cliente interaziendali devono essere considerati domanda qualificata, impostare l'opzione **Includi ordini interaziendali** su *Sì*.

La riduzione della previsione inizia con il primo record di previsione della domanda (meno recente) nel periodo della chiave di riduzione. Se la quantità di transazioni di inventario qualificate è maggiore della quantità di righe di previsione della domanda nello stesso periodo della chiave di riduzione, il saldo della quantità delle transazioni di inventario verrà utilizzato per ridurre la quantità di previsione della domanda nel periodo precedente (se è presente una previsione non consumata).

Se non rimane alcuna previsione non consumata nel precedente periodo della chiave di riduzione, il saldo della quantità delle transazioni di inventario verrà utilizzato per ridurre la quantità prevista nel mese successivo (se è presente una previsione non consumata).

Il valore del campo **Percentuale** sulle righe della chiave di riduzione non viene utilizzato quando il campo **Metodo utilizzato per ridurre i requisiti di previsione** è impostato su *Transazioni - chiave di riduzione*. Solo le date vengono utilizzate per definire il periodo della chiave di riduzione.

> [!NOTE]
> Qualsiasi previsione registrata entro la data odierna verrà ignorata e non verrà utilizzata per creare ordini pianificati. Ad esempio, se la previsione della domanda per il mese viene generata il 1° gennaio e si esegue una pianificazione generale che include la previsione della domanda il 2 gennaio, il calcolo ignorerà la riga della previsione della domanda datata 1° gennaio.

##### <a name="example-transactions--reduction-key"></a>Esempio: Transazioni - chiave di riduzione

In questo esempio viene illustrato come gli ordini effettivi, che si verificano durante i periodi definiti dalla chiave di riduzione, riducono i requisiti di previsione della domanda.

[![Ordini effettivi e previsione precedenti all'esecuzione della pianificazione generale.](media/forecast-reduction-keys-1-small.png)](media/forecast-reduction-keys-1.png)

Per questo esempio, selezionare *Transazioni - chiave di riduzione* nel campo **Metodo utilizzato per ridurre i requisiti di previsione** nella pagina **Piani generali**.

Le seguenti righe della previsione della domanda esistono il 1° aprile.

| Data     | Numero di pezzi previsti |
|----------|-----------------------------|
| 5 aprile  | 100                         |
| 12 aprile | 100                         |
| 19 aprile | 100                         |
| 26 aprile | 100                         |
| 3° maggio    | 100                         |
| 10° maggio   | 100                         |
| 17° maggio   | 100                         |

Le seguenti righe dell'ordine cliente esistono ad aprile.

| Data     | Numero di pezzi richiesti |
|----------|----------------------------|
| 27 aprile | 240                        |

[![Fornitura pianificata generata in base agli ordini di aprile.](media/forecast-reduction-keys-2-small.png)](media/forecast-reduction-keys-2.png)

Le seguenti quantità di requisiti vengono trasferite al piano generale quando la pianificazione generale viene eseguita il 1° aprile. Come si nota, le transazioni di previsione di aprile sono state ridotte della quantità della domanda di 240 in sequenza, a partire dalla prima di tali transazioni.

| Data     | Numero di pezzi richiesti |
|----------|---------------------------|
| 5 aprile  | 0                         |
| 12 aprile | 0                         |
| 19 aprile | 60                        |
| 26 aprile | 100                       |
| 27 aprile | 240                       |
| 3° maggio    | 100                       |
| 10° maggio   | 100                       |
| 17° maggio   | 100                       |

Ora, supponiamo che siano stati importati nuovi ordini per il periodo di maggio.

Le seguenti righe dell'ordine cliente esistono a maggio.

| Data   | Numero di pezzi richiesti |
|--------|----------------------------|
| 4° maggio  | 80                         |
| 11° maggio | 130                        |

[![Fornitura pianificata generata in base agli ordini di aprile e maggio.](media/forecast-reduction-keys-3-small.png)](media/forecast-reduction-keys-3.png)

Le seguenti quantità di requisiti vengono trasferite al piano generale quando la pianificazione generale viene eseguita il 1° aprile. Come si nota, le transazioni di previsione di aprile sono state ridotte della quantità della domanda di 240 in sequenza, a partire dalla prima di tali transazioni. Tuttavia, le transazioni di previsione di maggio sono state ridotte di un totale di 210, a partire dalla prima transazione di previsione della domanda di maggio. Tuttavia, vengono mantenuti i totali per periodo (400 ad aprile e 300 a maggio).

| Data     | Numero di pezzi richiesti |
|----------|---------------------------|
| 5 aprile  | 0                         |
| 12 aprile | 0                         |
| 19 aprile | 60                        |
| 26 aprile | 100                       |
| 27 aprile | 240                       |
| 3° maggio    | 0                         |
| 4° maggio    | 80                        |
| 10° maggio   | 0                         |
| 11° maggio   | 130                       |
| 17° maggio   | 90                        |

#### <a name="transactions--dynamic-period"></a>Transazioni - periodo dinamico

Se si seleziona **Transazioni - periodo dinamico**, i requisiti di previsione vengono ridotti in base alle transazioni di ordine effettive effettuate durante il periodo dinamico. Il periodo dinamico copre le date di previsione correnti e termina all'inizio della previsione successiva. In questo caso, la pianificazione generale crea ordini pianificati per fornire la domanda prevista (requisiti di previsione). Tuttavia, quando si eseguono transazioni di ordini, i requisiti di previsione vengono ridotti. Le transazioni effettive consumano parte dei requisiti previsti.

Quando questa opzione viene utilizzata, si verifica il seguente comportamento :

- Le chiavi di riduzione non sono richieste o utilizzate. 
- Se la previsione viene ridotta completamente, i requisiti per la previsione corrente diventano 0 (zero).
- Se non vi è alcuna previsione futura, vengono ridotti i requisiti di previsione dall'ultima previsione immessa.
- Gli intervalli temporali vengono inclusi nel calcolo della riduzione previsionale.
- I giorni di positività vengono inclusi nel calcolo della riduzione previsionale.
- Se le transazioni di ordini effettivi superano i requisiti previsti, le transazioni rimanenti non vengono inoltrate al periodo previsionale successivo.

##### <a name="example-1-transactions--dynamic-period"></a>Esempio 1: Transazioni - periodo dinamico

Di seguito viene riportato un esempio semplice che mostra il funzionamento del metodo **Transazioni - periodo dinamico**.

Per questo esempio, includere la seguente previsione della domanda in un piano generale.

| Data       | Previsione della domanda |
|------------|-----------------|
| 1 gennaio  | 1.000           |
| 1 febbraio | 1.000             |

Si creano inoltre i seguenti ordini cliente.

| Data        | Quantità ordine cliente |
|-------------|----------------------|
| 15 gennaio  | 200                  |
| 15 febbraio | 400                  |

In questo caso, vengono creati i seguenti ordini pianificati.

| Data di previsione della domanda | Quantità | Spiegazione                           |
|--------------------- |----------|---------------------------------------|
| 1 gennaio            | 800      | Requisiti di previsione (= 1.000 – 200) |
| 15 gennaio           | 200      | Requisiti ordini cliente             |
| 1 febbraio           | 600      | Requisiti di previsione (= 1.000 – 400) |
| 15 febbraio          | 400      | Requisiti ordine cliente             |

##### <a name="example-2-transactions--dynamic-period"></a>Esempio 2: Transazioni - periodo dinamico

Nella maggior parte dei casi i sistemi vengono impostati in modo che le transazioni riducano la previsione della domanda nei periodi specifici di previsione: settimane, mesi, ecc. I periodi vengono sono definiti nella chiave di riduzione. Tuttavia, il tempo trascorso tra due righe di previsione della domanda può anche *implicare* un periodo.

Per questo esempio, si crea una previsione della domanda per le seguenti date e quantità.

| Data       | Previsione della domanda |
|------------|-----------------|
| 1 gennaio  | 1.000           |
| 5 gennaio  | 500             |
| 12 gennaio | 1.000           |

Si noti che, nella previsione, non è presente un periodo chiaro tra le date di previsione. Tra le prima data e la seconda vi è un intervallo di quattro giorni e tra la seconda data e la terza vi è un intervallo di sette giorni. Questi intervalli sono i periodi dinamici.

Si creano inoltre le seguenti righe ordine cliente.

| Data                             | Quantità ordine cliente |
|----------------------------------|----------------------|
| 15 dicembre dell'anno precedente | 500                  |
| 3 gennaio                        | 100                  |
| 10 gennaio                       | 200                  |

In questo caso, la previsione viene ridotta nel seguente modo:

- Poiché il primo ordine cliente non rientra in alcun periodo, non riduce alcuna previsione.
- Poiché il secondo ordine cliente è compreso tra il 1° gennaio e il 5 gennaio, riduce la previsione per il 1° gennaio di 100.
- Poiché il terzo ordine cliente è compreso tra il 5° gennaio e il 12 gennaio, riduce la previsione per il 5° gennaio di 200.

Di conseguenza, vengono creati i seguenti ordini pianificati.

| Data di previsione della domanda             | Quantità | Spiegazione                                                         |
|----------------------------------|----------|---------------------------------------------------------------------|
| 15 dicembre dell'anno precedente | 500      | Requisiti ordine cliente                                            |
| 1 gennaio                        | 900      | Requisiti di previsione nel periodo dal 1° gennaio al 5 gennaio = (1.000 - 100) |
| 3 gennaio                        | 100      | Requisiti ordine cliente                                            |
| 5 gennaio                        | 300      | Requisiti di previsione nel periodo dal 5° gennaio al 10 gennaio = (500 - 200)  |
| 12 gennaio                       | 1.000    | Requisiti di previsione nel periodo dal 12 gennaio alla fine                      |

### <a name="create-and-set-up-a-forecast-reduction-key"></a><a name="create-reduction-key"></a>Creare e impostare una chiave di riduzione previsionale

Una chiave di riduzione previsionale viene utilizzata nei metodi **Transazioni - chiave di riduzione** e **Percentuale - chiave di riduzione** per ridurre i requisiti di previsione. Attenersi alla procedura seguente per creare e impostare una chiave di riduzione.

1. Andare a **Pianificazione generale \> Impostazione \> Copertura \> Chiavi di riduzione**.
2. Selezionare **Nuovo** per creare una chiave di riduzione.
3. Nel campo **Chiave di riduzione**, immettere un identificatore univoco per la chiave di riduzione previsionale. Quindi, nel campo **Nome** immettere un nome. 
4. Definire i periodi e la percentuale della chiave di riduzione in ciascun periodo:

    - Il campo **Data di validità** indica la data in cui ha inizio la creazione dei periodi. Quando l'opzione **Utilizza la data di validità** è impostata su **Sì**, i periodi iniziano a partire dalla data di validità. Quando è impostata su **No**, i periodi iniziano a partire dalla data in cui la pianificazione generale viene eseguita.
    - Definire i periodi in cui deve avvenire la riduzione previsionale.
    - Per un periodo specifico, specificare le percentuali di riduzione dei requisiti di previsione. È possibile immettere valori positivi per ridurre i requisiti o valori negativi per aumentarli.

### <a name="use-a-reduction-key"></a><a name="use-reduction-key"></a>Utilizzare una chiave di riduzione

Una chiave di riduzione previsionale deve essere assegnata al gruppo di copertura dell'articolo. Attenersi alla procedura seguente per assegnare una chiave di riduzione al gruppo di copertura di un articolo.

1. Andare a **Pianificazione generale \> Impostazioni \> Copertura \> Gruppi di copertura**.
2. Nella Scheda dettaglio **Altro**, nel campo **Chiave di riduzione**, selezionare la chiave di riduzione da assegnare al gruppo di copertura. La chiave di riduzione viene quindi applicata a tutti articoli appartenenti al gruppo di copertura.
3. Per calcolare la riduzione previsionale durante la programmazione generale utilizzando una chiave di riduzione, è necessario definire questa impostazione nella configurazione del piano previsionale o del piano generale. Passare a una delle pagine seguenti:

    - **Pianificazione generale \> Impostazioni \> Piani \> Piani previsionali**
    - **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**

4. Nella pagina **Piani previsionali** o **Piani generali**, nel campo **Metodo utilizzato per ridurre i requisiti di previsione** della Scheda dettaglio **Generale**, selezionare **Percentuale - chiave di riduzione** o **Transazioni - chiave di riduzione**.

### <a name="reduce-a-forecast-by-transactions"></a>Ridurre una previsione mediante transazioni

Quando si seleziona **Transazioni - chiave di riduzione** o **Transazioni - periodo dinamico** come metodo per ridurre i requisiti previsti, è possibile specificare le transazioni che riducono la previsione. Nella pagina **Gruppi di copertura** , nella scheda dettaglio **Altro**, nel campo **Riduci previsione per** , selezionare **Tutte le transizioni** se tutte le transazioni devono ridurre la previsione oppure **Ordini** se solo gli ordini cliente devono ridurre la previsione.

## <a name="forecast-models-and-submodels"></a>Modelli e sottomodelli previsionali

Questa sezione descrive come creare modelli previsionali e come combinare più modelli previsionali impostando sottomodelli.

Un *modello previsionale* denomina e identifica una previsione specifica. Dopo aver creato il modello di previsione, è possibile aggiungervi righe di previsione. Per aggiungere righe di previsione per più articoli, utilizzare la pagina **Righe di previsione della domanda**. Per aggiungere righe di previsione per uno specifico articolo selezionato, utilizzare la pagina **Prodotti rilasciati**.

Un modello previsionale può includere previsioni di altri modelli previsionali. Per ottenere questo risultato, si aggiungono altri modelli previsionali come *sottomodelli* di un modello previsionale padre. È necessario creare ogni modello pertinente prima di poterlo aggiungere come sottomodello di un modello previsionale padre.

La struttura risultante offre un modo potente per controllare le previsioni, poiché consente di combinare (aggregare) l'input di più previsioni individuali. Pertanto, dal punto di vista della pianificazione, è facile combinare previsioni per simulazioni. Ad esempio, si potrebbe impostare una simulazione basata sulla combinazione di una previsione regolare con la previsione per una promozione primaverile.

### <a name="submodel-levels"></a>Livelli di sottomodelli

Non vi è alcun limite al numero di sottomodelli che possono essere aggiunti a un modello previsionale padre. Tuttavia, la struttura può comportare un solo livello. In altre parole, un modello previsionale che è un sottomodello di un altro modello previsionale non può avere sottomodelli. Quando si aggiungono sottomodelli a un modello previsionale, il sistema verifica se tale modello previsionale è già un sottomodello di un altro modello previsionale.

Se la pianificazione generale rileva un sottomodello che ha dei sottomodelli, viene visualizzato un messaggio di errore.

#### <a name="submodel-levels-example"></a>Esempio di livelli di sottomodelli

Il modello previsionale A ha il modello previsionale B come sottomodello. Pertanto, il modello previsionale B non può avere sottomodelli. Se si tenta di aggiungere un sottomodello al modello previsionale B, viene visualizzato il seguente messaggio di errore: "Il modello previsionale B è un sottomodello per il modello A."

### <a name="aggregating-forecasts-across-forecast-models"></a>Aggregazione di previsioni tra modelli previsionali

Le righe di previsione che si verificano lo stesso giorno verranno aggregate nel rispettivo modello previsionale e nei relativi sottomodelli.

#### <a name="aggregation-example"></a>Esempio di aggregazione

Il modello previsionale A ha i modelli previsionali B e C come sottomodelli.

- Il modello previsionale A include una previsione della domanda per 2 pezzi (pz) il 15 giugno.
- Il modello previsionale B include una previsione della domanda per 3 pz il 15 giugno.
- Il modello previsionale C include una previsione della domanda per 4 pz il 15 giugno.

La previsione della domanda risultante sarà una singola domanda per 9 pezzi (2 + 3 + 4) il 15 giugno.

> [!NOTE]
> Ogni sottomodello utilizza parametri propri, non quelli del modello previsionale padre.

### <a name="create-a-forecast-model"></a>Creare un modello previsionale

Per creare un modello previsionale, attenersi alla procedura seguente.

1. Selezionare **Pianificazione generale \> Impostazioni \> Previsione della domanda \> Modelli previsionali**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Impostare i seguenti campi per il nuovo modello previsionale:

    - **Modello** - Immettere un identificatore univoco per il modello.
    - **Nome** – Immettere un nome descrittivo per il modello.
    - **Interrotto** - Di solito, questa opzione deve essere impostata su *No*. Impostarla su *Sì* solo se si desidera impedire la modifica di tutte le righe di previsione assegnate al modello.

    > [!NOTE]
    > Il campo **Includi in previsioni di cassa** e i campi nella Scheda dettaglio **Progetto** non sono correlati alla pianificazione generale. Pertanto, puoi ignorarli in questo contesto. È necessario considerarli solo quando si lavora con le previsioni per il modulo **Gestione progetti e contabilità**.

### <a name="assign-submodels-to-a-forecast-model"></a>Assegnare sottomodelli a un modello previsionale

Per assegnare sottomodelli a un modello previsionale, attenersi alla procedura seguente.

1. Selezionare **Gestione articoli \> Impostazioni \> Previsione \> Modelli previsionali**.
1. Nel riquadro elenco, selezionare il modello previsionale per il quale impostare un sottomodello.
1. Nella Scheda dettaglio **Sottomodello**, selezionare **Aggiungi** per aggiungere una riga alla griglia.
1. Nella nuova riga, impostare i seguenti campi.

    - **Sottomodello** - Selezionare il modello previsionale da aggiungere come sottomodello. Questo modello previsionale deve già esistere e non deve avere sottomodelli.
    - **Nome** – Immettere un nome descrittivo per il sottomodello. Ad esempio, questo nome potrebbe indicare la relazione del sottomodello con il modello previsionale padre.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

