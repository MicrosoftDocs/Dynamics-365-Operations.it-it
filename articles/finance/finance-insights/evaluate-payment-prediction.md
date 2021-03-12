---
title: Valutare il modello di previsione di pagamento del cliente iniziale (anteprima)
description: In questo argomento vengono descritti i passaggi che è possibile eseguire per comprendere il modello di previsione del pagamento del cliente e valutarne l'efficacia.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: ef0daec6153405fc064b1185ba7067796ff5bb45
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995117"
---
# <a name="evaluate-the-initial-customer-payment-prediction-model-preview"></a>Valutare il modello di previsione di pagamento del cliente iniziale (anteprima)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo argomento spiega come valutare un modello di previsione dopo aver attivato Informazioni finanziarie dettagliate e quindi generato ed eseguito il training del primo modello. Questo argomento illustra i modelli per la previsione dei pagamenti dei clienti. In questo argomento vengono descritti i passaggi che è possibile eseguire per comprendere il modello di previsione del pagamento del cliente e valutarne l'efficacia.

## <a name="getting-details-about-the-model"></a>Ottenere dettagli sul modello

Nella pagina **Parametri di informazioni finanziarie dettagliate** in Microsoft Dynamics 365 Finance, un collegamento **Migliora la precisione del modello** viene visualizzato accanto al punteggio di precisione.

[![Collegamento Migliora la precisione del modello](./media/prediction-model.png)](./media/prediction-model.png)

Questo collegamento reindirizza ad AI Builder, dove puoi saperne di più sul modello attuale e anche adottare misure per migliorarlo. L'illustrazione seguente mostra la pagina che viene aperta.

[![AI Builder](./media/what-to-predict.png)](./media/what-to-predict.png)

La pagina che viene aperta mostra le informazioni seguenti:

- Nella sezione **Prestazioni**, il grado di prestazione del modello fornisce una prospettiva sulla qualità del modello. Per ulteriori informazioni su questo grado, vedi [Prestazioni del modello di previsione](https://docs.microsoft.com/ai-builder/prediction-performance) nella documentazione di AI Builder.
- La sezione **Dati più influenti** mostra l'importanza dei diversi tipi di input di dati per il modello. Puoi valutare questo elenco e le percentuali corrispondenti per determinare se le informazioni sono coerenti con ciò che sai della tua azienda e del tuo mercato.

    [![Sezioni Prestazioni e Dati più influenti per il modello di previsione](./media/models.png)](./media/models.png)

- Nella sezione **Prestazioni**, seleziona **Visualizza dettagli** per saperne di più sul grado e altre considerazioni. Nella figura seguente, i dettagli mostrano che il modello utilizza meno informazioni di quelle consigliate. Pertanto, il sistema ha generato un messaggio di avviso.

    [![Avvisi sulle prestazioni del modello](./media/details.png)](./media/details.png)

## <a name="digging-deeper"></a>Eseguire un'analisi più approfondita

Sebbene la precisione sia un buon punto di partenza per la valutazione di un modello e il grado di prestazione fornisca una prospettiva, AI Builder fornisce metriche più dettagliate che puoi utilizzare per la tua valutazione. Per scaricare i dettagli, nella sezione **Prestazioni**, seleziona il pulsante con i puntini di sospensione (**...**) accanto al pulsante **Utilizza modello** e quindi seleziona **Scarica metriche dettagliate**.

[![Comando Scarica metriche dettagliate](./media/performance.png)](./media/performance.png)

La figura seguente mostra il formato in cui è possibile scaricare i dati.

[![Formato dei dati scaricati](./media/data-format.png)](./media/data-format.png)

Per un'analisi più approfondita dei risultati, un buon punto di partenza è la revisione della metrica "Matrice di confusione". Ad esempio, ecco i dati mostrati per questa metrica nell'illustrazione precedente.

`{"name": "Confusion Matrix", "value": {"schema_type": "confusion_matrix", "schema_version": "1.0.0", "data": {"class_labels": ["0", "1", "2"], "matrix": [[71, 9, 21], [5, 0, 27], [2, 0, 45]]}}, "type": "dictionaryNumericalList", "isGlobalScore": false}`

Puoi espandere questi dati nel modo seguente.

|                          | Previsto in tempo | Previsto in ritardo | Previsto molto in ritardo |
|--------------------------|-------------------|----------------|---------------------|
| Pagamento puntuale effettivo   | **71**            | 0              | 21                  |
| Pagamento in ritardo effettivo      | 5                 | **0**          | 27                  |
| Pagamento molto in ritardo effettivo | 2                 | 0              | **45**              |

La matrice di confusione mostra i risultati di un set di dati di test selezionato casualmente dal processo di training. Poiché queste fatture chiuse non sono state utilizzate per il training del modello, costituiscono test case ottimali per il modello. Inoltre, poiché è noto lo stato effettivo della fattura, è possibile visualizzare anche le prestazioni del modello.

La prima cosa da cercare è il valore effettivo più comune. Sebbene questo valore possa non essere perfettamente in linea con il set di dati complessivo, è un'approssimazione ragionevole. In questo caso, **Pagamento puntuale effettivo** si verifica per 92 delle 171 fatture totali ed è il valore effettivo più comune. Pertanto, è una buona base per il tuo modello. Se avessi ipotizzato che tutte le fatture sarebbero state puntuali, avresti avuto ragione 92 volte su 171 (ovvero il 54% delle volte).

È importante che tu capisca quanto sia bilanciato il tuo set di dati. In questo caso, 92 fatture su 171 sono state pagate in tempo, 32 sono state pagate in ritardo e 47 sono state pagate molto in ritardo. Questi valori indicano un set di dati ragionevolmente bilanciato, perché ci sono risultati non banali in ogni classificazione. Una situazione in cui uno degli stati ha pochissimi risultati può essere difficile per un modello di apprendimento automatico.

La precisione del modello indica il numero di previsioni corrette per il set di dati di test. Queste previsioni corrette sono i valori mostrati in grassetto nell'esempio precedente. In questo caso, i valori producono una precisione calcolata del 67,8 percento (= \[71 + 0 + 45\] ÷ 171). Questo valore rappresenta un miglioramento del 14% rispetto all'ipotesi di base del 54% ed è un indicatore della qualità del modello.

Se osservi più da vicino la matrice di confusione, noterai che il modello fa un buon lavoro nel prevedere i pagamenti delle fatture puntuali e molto in ritardo. Tuttavia, è sbagliato su tutte le 32 fatture che sono state effettivamente pagate in ritardo (ma non molto in ritardo). Questo risultato suggerisce che sono necessarie ulteriori esplorazioni e miglioramenti del modello.

Un numero che rappresenta le prestazioni del modello meglio della precisione è il punteggio Macro F1. Questo punteggio considera i risultati di ogni stato di classificazione (puntuale, in ritardo e molto in ritardo). Ad esempio, ecco i dati mostrati per la metrica "F1 Macro" nell'illustrazione precedente.

`{"name": "F1 Macro", "value": 0.4927170868347339, "type": "percentage", "isGlobalScore": false}`

In questo caso, il punteggio F1 Macro di circa il 49,3% indica che il modello non fornisce previsioni efficaci in ogni stato, nonostante un punteggio di accuratezza complessivo che sembra ragionevolmente alto.

## <a name="improving-the-model"></a>Miglioramento del modello

Dopo aver compreso meglio i risultati del primo modello, è consigliabile migliorare il modello aggiungendo o rimuovendo le colonne delle funzionalità oppure filtrando le parti del set di dati che non supportano previsioni accurate. Chiudi AI Builder, quindi usa il collegamento **Migliora il modello** in Dynamics 365 Finance per riavviare il processo AI Builder. Puoi sperimentare caratteristiche diverse senza alcun impatto sul modello pubblicato. Il modello pubblicato è interessato solo quando selezioni **Pubblica**. Ricorda che per la tua istanza di Dynamics 365 Finance viene utilizzato un unico modello. Pertanto, è necessario esaminare attentamente qualsiasi nuovo modello prima di pubblicarlo.

## <a name="for-more-information"></a>Ulteriori informazioni

Per ulteriori informazioni su come valutare i modelli di previsione, vedi [Risultati dei modelli di apprendimento automatico](/confusion-matrix.md)

#### <a name="privacy-notice"></a>Informativa sulla privacy
Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.
