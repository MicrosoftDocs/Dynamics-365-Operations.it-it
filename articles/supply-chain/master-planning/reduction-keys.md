---
title: Chiavi di riduzione previsionali
description: Questo argomento fornisce esempi che illustrano come impostare una chiave di riduzione. Include informazioni sulle diverse impostazioni della chiave di riduzione e sui risultati di ciascuna. È possibile utilizzare una chiave di riduzione per definire il modo in cui ridurre i requisiti di previsione.
author: roxanadiaconu
manager: tfehr
ms.date: 04/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqPlanSched, ReqReduceKeyDefaultDataWizard, ReqReduceKey
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1fc2b63bfdec1c663027cb4e551589a705c2164e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431020"
---
# <a name="forecast-reduction-keys"></a>Chiavi di riduzione previsionali

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni sui differenti metodi utilizzati per ridurre i requisiti di previsione. Include esempi dei risultati di ogni metodo. Descrive inoltre come creare, impostare e utilizzare una chiave di riduzione previsionale. Alcuni metodi utilizzano una chiave di riduzione previsionale per ridurre requisiti di previsione.

## <a name="methods-that-are-used-to-reduce-forecast-requirements"></a>Metodi utilizzati per ridurre i requisiti di previsione

Quando si include una previsione in un piano generale, è possibile selezionare il modo in cui ridurre i requisiti di previsione quando viene inclusa la domanda effettiva. Si noti che la pianificazione generale esclude i requisiti di previsione passati, il che significa tutti i requisiti di previsione prima della data odierna.

Per includere una previsione in un piano generale e selezionare il metodo utilizzato per ridurre i requisiti di previsione, andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**. Selezionare un modello previsionale nel campo **Modello previsionale**. Nel campo **Metodo utilizzato per ridurre i requisiti di previsione**, selezionare un metodo. Sono disponibili le opzioni seguenti:

- Nessuno
- Percentuale - chiave di riduzione
- Transazioni - chiave di riduzione
- Transazioni - periodo dinamico

Nelle sezioni seguenti vengono fornite altre informazioni sui ogni opzione.

### <a name="none"></a>Nessuno

Se si sceglie **Nessuno**, i requisiti di previsione non vengono ridotti durante la programmazione generale. In questo caso, la pianificazione generale crea ordini pianificati per fornire la domanda prevista (requisiti di previsione). Questi ordini pianificati mantengono la quantità suggerita, indipendentemente da altri tipi di domande. Ad esempio, se vengono effettuati ordini cliente, la pianificazione generale crea ulteriori ordini pianificati per fornire ordini cliente. La quantità dei requisiti di previsione non viene ridotta.

### <a name="percent--reduction-key"></a>Percentuale - chiave di riduzione

Se si seleziona **Percentuale - chiave di riduzione**, i requisiti di previsione sono ridotti in base alle percentuali e ai periodi definiti dalla chiave di riduzione. In questo caso, la pianificazione generale crea ordini pianificati in cui la quantità viene calcolata come Quantità prevista × chiave di riduzione in ogni periodo. Se sono presenti altri tipi di domande, la pianificazione generale crea anche ordini pianificati per fornire la domanda.

#### <a name="example-percent--reduction-key"></a>Esempio: Percentuale - chiave di riduzione

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

### <a name="transactions--reduction-key"></a>Transazioni - chiave di riduzione

Se si seleziona **Transazioni - chiave di riduzione**, i requisiti di previsione vengono ridotti in base alle transazioni effettuate durante i periodi definiti dalla chiave di riduzione.

#### <a name="example-transactions--reduction-key"></a>Esempio: Transazioni - chiave di riduzione

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

### <a name="transactions--dynamic-period"></a>Transazioni - periodo dinamico

Se si seleziona **Transazioni - periodo dinamico**, i requisiti di previsione vengono ridotti in base alle transazioni di ordine effettive effettuate durante il periodo dinamico. Il periodo dinamico copre le date di previsione correnti e termina all'inizio della previsione successiva. In questo caso, la pianificazione generale crea ordini pianificati per fornire la domanda prevista (requisiti di previsione). Tuttavia, quando si eseguono transazioni di ordini, i requisiti di previsione vengono ridotti. Le transazioni effettive consumano parte dei requisiti previsti.

Quando questa opzione viene utilizzata, si verifica il seguente comportamento :

- Le chiavi di riduzione non sono richieste o utilizzate. 
- Se la previsione viene ridotta completamente, i requisiti per la previsione corrente diventano 0 (zero).
- Se non vi è alcuna previsione futura, vengono ridotti i requisiti di previsione dall'ultima previsione immessa.
- Gli intervalli temporali vengono inclusi nel calcolo della riduzione previsionale.
- I giorni di positività vengono inclusi nel calcolo della riduzione previsionale.
- Se le transazioni di ordini effettivi superano i requisiti previsti, le transazioni rimanenti non vengono inoltrate al periodo previsionale successivo.

#### <a name="example-1-transactions--dynamic-period"></a>Esempio 1: Transazioni - periodo dinamico

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

#### <a name="example-2-transactions--dynamic-period"></a>Esempio 2: Transazioni - periodo dinamico

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

## <a name="create-and-set-up-a-forecast-reduction-key"></a>Creare e impostare una chiave di riduzione previsionale

Una chiave di riduzione previsionale viene utilizzata nei metodi **Transazioni - chiave di riduzione** e **Percentuale - chiave di riduzione** per ridurre i requisiti di previsione. Attenersi alla procedura seguente per creare e impostare una chiave di riduzione.

1. Andare a **Pianificazione generale \> Impostazione \> Copertura \> Chiavi di riduzione**.
2. Selezionare **Nuovo** o premere **CTRL+N** per creare una chiave di riduzione.
3. Nel campo **Chiave di riduzione**, immettere un identificatore univoco per la chiave di riduzione previsionale. Quindi, nel campo **Nome** immettere un nome. 
4. Definire i periodi e la percentuale della chiave di riduzione in ciascun periodo:

    - Il campo **Data di validità** indica la data in cui ha inizio la creazione dei periodi. Quando l'opzione **Utilizza la data di validità** è impostata su **Sì**, i periodi iniziano a partire dalla data di validità. Quando è impostata su **No**, i periodi iniziano a partire dalla data in cui la pianificazione generale viene eseguita.
    - Definire i periodi in cui deve avvenire la riduzione previsionale.
    - Per un periodo specifico, specificare le percentuali di riduzione dei requisiti di previsione. È possibile immettere valori positivi per ridurre i requisiti o valori negativi per aumentarli.

## <a name="use-a-reduction-key"></a>Utilizzare una chiave di riduzione

Una chiave di riduzione previsionale deve essere assegnata al gruppo di copertura dell'articolo. Attenersi alla procedura seguente per assegnare una chiave di riduzione al gruppo di copertura di un articolo.

1. Andare a **Pianificazione generale \> Impostazioni \> Copertura \> Gruppi di copertura**.
2. Nella Scheda dettaglio **Altro**, nel campo **Chiave di riduzione**, selezionare la chiave di riduzione da assegnare al gruppo di copertura. La chiave di riduzione viene quindi applicata a tutti articoli appartenenti al gruppo di copertura.
3. Per calcolare la riduzione previsionale durante la programmazione generale utilizzando una chiave di riduzione, è necessario definire questa impostazione nella configurazione del piano previsionale o del piano generale. Passare a una delle pagine seguenti:

    - Pianificazione generale \> Impostazioni \> Piani \> Piani previsionali
    - Pianificazione generale \> Impostazioni \> Piani \> Piani generali

4. Nella pagina **Piani previsionali** o **Piani generali**, nel campo **Metodo utilizzato per ridurre i requisiti di previsione** della Scheda dettaglio **Generale**, selezionare **Percentuale - chiave di riduzione** o **Transazioni - chiave di riduzione**.

## <a name="reduce-a-forecast-by-transactions"></a>Ridurre una previsione mediante transazioni

Quando si seleziona **Transazioni - chiave di riduzione** o **Transazioni - periodo dinamico** come metodo per ridurre i requisiti previsti, è possibile specificare le transazioni che riducono la previsione. Nella pagina **Gruppi di copertura** , nella scheda dettaglio **Altro**, nel campo **Riduci previsione per** , selezionare **Tutte le transizioni** se tutte le transazioni devono ridurre la previsione oppure **Ordini** se solo gli ordini cliente devono ridurre la previsione.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica piani generali](master-plans.md)
