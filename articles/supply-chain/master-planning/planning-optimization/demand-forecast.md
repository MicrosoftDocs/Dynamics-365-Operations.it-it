---
title: Pianificazione generale con previsioni della domanda
description: Questo argomento spiega come includere previsioni della domanda durante la pianificazione generale con l'ottimizzazione della pianificazione.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 8b47aee41494394a32ffc0ea0c42a512e5051532
ms.sourcegitcommit: b86576e1114e4125eba8c144d40c068025f670fc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4666724"
---
# <a name="master-planning-with-demand-forecasts"></a>Pianificazione generale con previsioni della domanda

[!include [banner](../../includes/banner.md)]

È possibile utilizzare una previsione della domanda insieme all'ottimizzazione della pianificazione per tenere conto della domanda prevista nella pianificazione generale. È possibile creare manualmente una previsione della domanda, importarla o generarla utilizzando la funzionalità di previsione della domanda in Microsoft Dynamics 365 Supply Chain Management. Per ulteriori informazioni sulla previsione della domanda, vedere [Panoramica previsioni della domanda](../introduction-demand-forecasting.md).

> [!NOTE]
> La pianificazione della previsione separata non è supportata con l'ottimizzazione della pianificazione. Di conseguenza, l'impostazione **Piano previsionale corrente** nella pagina **Parametri di pianificazione generale** non ha alcun effetto quando si utilizza l'ottimizzazione della pianificazione.

## <a name="set-up-a-master-plan-to-include-a-demand-forecast"></a>Impostare un piano generale per includere una previsione della domanda

Per configurare un piano generale in modo che includa una previsione della domanda, seguire questi passaggi.

1. Andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**.
1. Selezionare un piano esistente o crearne uno nuovo.
1. Nella scheda dettaglio **Generale**, impostare i seguenti campi:

    - **Modello previsionale** - Selezionare il modello previsionale da applicare. Questo modello verrà preso in considerazione quando viene generato un suggerimento di fornitura per il piano generale corrente.
    - **Includi previsione della domanda** - Impostare questa opzione su *Sì* per includere la previsione della domanda nel piano generale corrente. Se si imposta questa opzione su *No*, le transazioni di previsione della domanda non verranno incluse nel piano generale.
    - **Metodo utilizzato per ridurre i requisiti di previsione** - Selezionare il metodo da utilizzare per ridurre i requisiti di previsione. Per ulteriori informazioni, vedere la sezione [Chiavi di riduzione previsionali](#reduction-keys) più avanti in questo argomento.

1. Nella Scheda dettaglio **Intervallo temporale in giorni**, è possibile impostare i seguenti campi per specificare il periodo durante il quale la previsione della domanda è inclusa:

    - **Piano previsionale** - Impostare questa opzione su *Sì* per sostituire l'intervallo temporale del piano previsionale che ha origine dai singoli gruppi di copertura. Impostare l'opzione su *No* per utilizzare i valori dei singoli gruppi di copertura per il piano generale corrente.
    - **Periodo di tempo previsto** - Se si imposta l'opzione **Piano previsionale** su *Sì*, specificare il numero di giorni (dalla data odierna) in cui deve essere applicata la previsione della domanda.

    > [!IMPORTANT]
    > L'impostazione **Piano previsionale** non è ancora supportata con l'ottimizzazione della pianificazione.

## <a name="set-up-a-coverage-group-to-include-a-demand-forecast"></a>Impostare un gruppo di copertura per includere una previsione della domanda

Per configurare un gruppo di copertura in modo che includa una previsione della domanda, seguire questi passaggi.

1. Andare a **Pianificazione generale \> Impostazioni \> Piani \> Gruppi di copertura**.
1. Selezionare un gruppo di copertura esistente o creare un nuovo gruppo.
1. Nella Scheda dettaglio **Altro**, impostare i seguenti campi:

    - **Intervallo temporale di piano previsionale** - Immettere il numero di giorni (dalla data odierna) per i quali deve essere applicata la previsione della domanda. Questo valore può essere sostituito utilizzando l'opzione **Piano previsionale** nel piano generale, come descritto nella sezione precedente.
    - **Chiave di riduzione** - Selezionare la chiave di riduzione da applicare. Per ulteriori informazioni, vedere le sezioni [Creare e impostare una chiave di riduzione previsionale](#create-reduction-key) e [Utilizzare una chiave di riduzione](#use-reduction-key) più avanti in questo argomento.
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

Per includere una previsione in un piano generale e selezionare il metodo utilizzato per ridurre i requisiti di previsione, andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**. Selezionare un modello previsionale nel campo **Modello previsionale**. Nel campo **Metodo utilizzato per ridurre i requisiti di previsione**, selezionare un metodo. Di seguito vengono illustrate le opzioni disponibili.

- Nessuna priorità
- Percentuale - chiave di riduzione
- Transazioni - chiave di riduzione (non ancora supportata con l'ottimizzazione della pianificazione)
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

Se si seleziona **Transazioni - chiave di riduzione**, i requisiti di previsione vengono ridotti in base alle transazioni effettuate durante i periodi definiti dalla chiave di riduzione.

##### <a name="example-transactions--reduction-key"></a>Esempio: Transazioni - chiave di riduzione

In questo esempio viene illustrato come gli ordini effettivi, che si verificano durante i periodi definiti dalla chiave di riduzione, riducono i requisiti di previsione della domanda.

Per questo esempio, selezionare **Transazioni - chiave di riduzione** nel campo **Metodo utilizzato per ridurre i requisiti di previsione** nella pagina **Piani generali**.

Al 1° gennaio sono presenti gli ordini cliente che seguono.

| Mese    | Numero di pezzi ordinati |
|----------|--------------------------|
| gennaio  | 956                      |
| febbraio | 1.176                    |
| marzo    | 451                      |
| aprile    | 119                      |

Utilizzando la stessa previsione della domanda di 1.000 pezzi al mese utilizzata nell'esempio precedente, vengono trasferite al piano generale le quantità indicate di seguito.

| Mese                | Numero di pezzi richiesti |
|----------------------|---------------------------|
| gennaio              | 44                        |
| febbraio             | 0                         |
| marzo                | 549                       |
| aprile                | 881                       |
| Da maggio a dicembre | 1.000                     |

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
2. Selezionare **Nuovo** o premere **CTRL+N** per creare una chiave di riduzione.
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

    - Pianificazione generale \> Impostazioni \> Piani \> Piani previsionali
    - Pianificazione generale \> Impostazioni \> Piani \> Piani generali

4. Nella pagina **Piani previsionali** o **Piani generali**, nel campo **Metodo utilizzato per ridurre i requisiti di previsione** della Scheda dettaglio **Generale**, selezionare **Percentuale - chiave di riduzione** o **Transazioni - chiave di riduzione**.

### <a name="reduce-a-forecast-by-transactions"></a>Ridurre una previsione mediante transazioni

Quando si seleziona **Transazioni - chiave di riduzione** o **Transazioni - periodo dinamico** come metodo per ridurre i requisiti previsti, è possibile specificare le transazioni che riducono la previsione. Nella pagina **Gruppi di copertura** , nella scheda dettaglio **Altro**, nel campo **Riduci previsione per** , selezionare **Tutte le transizioni** se tutte le transazioni devono ridurre la previsione oppure **Ordini** se solo gli ordini cliente devono ridurre la previsione.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]