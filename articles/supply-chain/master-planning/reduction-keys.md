---
title: Chiavi di riduzione
description: "Questo articolo fornisce esempi che illustrano come impostare una chiave di riduzione. Include informazioni sulle diverse impostazioni della chiave di riduzione e sui risultati di ciascuna. È possibile utilizzare una chiave di riduzione per definire il modo in cui ridurre i requisiti di previsione."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqPlanSched
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 506ca3aac7ad271ca7472f3b74627e94d97a74ee
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="reduction-keys"></a>Chiavi di riduzione

[!INCLUDE [banner](../includes/banner.md)]

Questo articolo fornisce esempi che illustrano come impostare una chiave di riduzione. Include informazioni sulle diverse impostazioni della chiave di riduzione e sui risultati di ciascuna. È possibile utilizzare una chiave di riduzione per definire il modo in cui ridurre i requisiti di previsione.

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a>Esempio 1: Principio di riduzione previsioni di Percentuale - chiave di riduzione
---------------------------------------------------------------

In questo esempio viene illustrato come una chiave di riduzione riduce i requisiti di previsione della domanda in base alle percentuali e ai periodi definiti dalla chiave di riduzione.

1. Nella pagina **Chiavi di riduzione** impostare le seguenti righe.

   | Cambia | Unità  | Percentuale |
   |--------|-------|---------|
   |   1    | Mese |   100   |
   |   2    | Mese |   75    |
   |   3    | Mese |   50    |
   |   4    | Mese |   25    |


2. Collegare la chiave di riduzione al gruppo di copertura dell'articolo.
3. Nel campo **Principio di riduzione** della pagina **Piani generali** selezionare **Percentuale - chiave di riduzione**.
4. Creare una previsione della domanda di 1.000 pezzi al mese.

Se si esegue una programmazione previsionale il 1° gennaio, i requisiti di previsione della domanda vengono consumati in base alle percentuali definite alla pagina **Chiavi di riduzione**. Vengono trasferite al piano generale le quantità di requisiti che seguono.

| Mese                | Numero di pezzi richiesti |
|----------------------|---------------------------|
| gennaio              | 0                         |
| febbraio             | 250                       |
| marzo                | 500                       |
| aprile                | 750                       |
| Da maggio a dicembre | 1.000                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a>Esempio 2: Principio di riduzione previsioni di Transazioni - chiave di riduzione
In questo esempio viene illustrato come gli ordini effettivi, che si verificano durante i periodi definiti dalla chiave di riduzione, riducono i requisiti di previsione della domanda.

-   Nel campo **Principio di riduzione** della pagina **Piani generali** selezionare **Transazioni - chiave di riduzione**.

Al 1° gennaio sono presenti gli ordini cliente che seguono.

| Mese    | Numero di pezzi ordinati |
|----------|--------------------------|
| gennaio  | 956                      |
| febbraio | 1.176                    |
| marzo    | 451                      |
| aprile    | 119                      |

Utilizzando la stessa previsione della domanda di 1.000 pezzi al mese, vengono trasferite al piano generale le quantità indicate di seguito.

| Mese                | Numero di pezzi richiesti |
|----------------------|---------------------------|
| gennaio              | 44                        |
| febbraio             | 0                         |
| marzo                | 549                       |
| aprile                | 881                       |
| Da maggio a dicembre | 1.000                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a>Esempio 3: Principio di riduzione previsioni di Transazioni - periodo dinamico
Nella maggior parte dei casi i sistemi vengono impostati in modo che le transazioni riducano la previsione della domanda entro periodi specifici di previsione: settimane, mesi, ecc. I periodi vengono sono definiti nella chiave di riduzione. Tuttavia, il tempo trascorso tra due righe di previsione della domanda può anche *implicare* un periodo.

1. Creare una previsione della domanda per le seguenti date e quantità.

   | Data       | Previsione della domanda |
   |------------|-----------------|
   | 1 gennaio  | 1.000           |
   | 5 gennaio  | 500             |
   | 12 gennaio | 1.000           |

   Nella previsione non è presente un periodo chiaro tra le date di previsione: tra le prime e le seconde date vi è un intervallo di quattro giorni e tra la seconde e terze date vi è un intervallo di sette giorni. I vari intervalli sono i periodi dinamici.
2. Creare righe dell'ordine cliente come segue
   | Data                             | Quantità ordine cliente |
   |----------------------------------|----------------------|
   | 15 dicembre dell'anno precedente | 500                  |
   | 3 gennaio                        | 100                  |
   | 10 gennaio                       | 200                  |

La previsione verrà ridotta come segue:

-   Il primo ordine cliente non rientra in alcun periodo, pertanto non ridurrà alcuna previsione.
-   Il secondo ordine cliente è compreso tra il 1° gennaio e il 5 gennaio, pertanto ridurrà la previsione per il 1° gennaio di 100.
-   Il terzo ordine cliente è compreso tra il 5 gennaio e il 12 gennaio, pertanto ridurrà la previsione per il 5 gennaio di 200.

Il seguente ordine pianificato verrà creato per soddisfare la previsione.

| Data di previsione della domanda | Quantità ridotta |
|----------------------|------------------|
| 1 gennaio            | 900              |
| 5 gennaio            | 300              |
| 12 gennaio           | 1.000            |

Questo campo è un riepilogo della riduzione **Transazioni - periodo dinamico**:

-   I requisiti di previsione vengono ridotti in base alle transazioni di ordini effettive effettuate durante il periodo dinamico. Il periodo dinamico copre le date di previsione correnti e termina all'inizio della previsione successiva.
-   Per questo metodo non viene utilizzata o richiesta alcuna chiave di riduzione.
-   Quando questa opzione viene utilizzata, si verifica il seguente comportamento :
    -   Se la previsione viene ridotta completamente, i requisiti per la previsione corrente diventano 0 (zero).
    -   Se non vi è alcuna previsione futura, vengono ridotti i requisiti di previsione dall'ultima previsione immessa.
    -   Gli intervalli temporali vengono inclusi nel calcolo della riduzione previsionale.
    -   I giorni di positività vengono inclusi nel calcolo della riduzione previsionale.
    -   Se le transazioni di ordini effettivi superano i fabbisogni previsti, le transazioni rimanenti non vengono inoltrate al periodo previsionale successivo.


<a name="see-also"></a>Vedere anche
--------

[Piani generali](master-plans.md)




