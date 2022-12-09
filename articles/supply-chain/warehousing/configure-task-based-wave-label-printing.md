---
title: Pianifica la stampa dell'etichetta ciclo durante il ciclo
description: Questo articolo descrive come impostare e utilizzare la funzionalità per la stampa di etichette ciclo basata su attività.
author: perlynne
ms.date: 12/02/2022
ms.topic: article
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: e788e5a9206e46ada6490d4a0196c7ea8ca6af15
ms.sourcegitcommit: 04e42c495d018e457fb3b038cadc4fe75ecbba12
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2022
ms.locfileid: "9822364"
---
# <a name="schedule-wave-label-printing-during-wave"></a>Pianifica la stampa dell'etichetta ciclo durante il ciclo

[!include [banner](../../includes/banner.md)]

Usa la funzionalità *Stampa di etichette ciclo basata su attività* come parte del processo di ciclo per aiutare a migliorare l'efficienza e per fare in modo che il sistema crei etichette ciclo e lavori in attività separate.

Il processo di configurazione della stampa di etichette ciclo è complesso e si basa su una configurazione accurata e su dati master. Non è raro che la generazione di record di etichette ciclo non riesca e, quando ciò accade, viene eseguito il rollback dell'intera elaborazione ciclo. La funzionalità *Stampa etichette ciclo basata su attività* ti aiuta a evitare di dover ricreare il lavoro e le righe di lavoro ogni volta che un'etichetta ciclo viene stampata in modo errato.

Quando usi la funzionalità *Stampa etichette ciclo basata su attività* il sistema crea prima il lavoro e le righe di lavoro. Quindi crea e stampa le etichette ciclo. Infine, se le etichette ciclo sono create correttamente, rilascia il lavoro e il ciclo per il prelievo.

## <a name="turn-on-the-task-based-wave-label-printing-feature-in-feature-management"></a>Attivare la funzione di stampa etichette ciclo basata su attività nella gestione delle funzionalità

Per utilizzare le funzionalità descritte in questo articolo, è necessario attivarle per il sistema. Usa l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivare le funzionalità nel seguente ordine:

1. *Blocco del lavoro a livello di organizzazione* - Questa funzione è necessaria per la configurazione sia manuale che automatica della creazione del lavoro programmato. (A partire dalla versione 10.0.21 di Supply Chain Management, questa funzionalità è obbligatoria, quindi è attivata per impostazione predefinita e non può essere disattivata di nuovo.)
1. *Stampa etichette ciclo basata su attività* – Questa funzione è necessaria per suddividere la stampa di etichette ciclo in un ambito di transazione separato.

## <a name="manually-enable-the-new-wave-step-method"></a>Abilitare manualmente il nuovo metodo di passaggio ciclo

Devi prima creare il nuovo metodo di passaggio ciclo e abilitarlo per l'elaborazione parallela di attività asincrone.

1. Andare a **Gestione magazzino \> Impostazione \> Ondate \> Metodi di elaborazione ondata**.
1. Nel riquadro azioni, seleziona **Rigenera metodo**. Nota che *waveLabelPrinting* viene aggiunto all'elenco dei metodi di processo ciclo che è possibile utilizzare nei modelli ciclo di spedizione.
1. Seleziona il record in cui il campo **Nome metodo** è impostato su *waveLabelPrinting*, quindi, nel riquadro azioni, seleziona **Configurazione attività**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Magazzino** - Seleziona il magazzino che utilizzerai per l'elaborazione di Pianifica creazione lavoro. Se stai utilizzando dati demo a scopo di test, puoi selezionare il magazzino *24*.
    - **Numero massimo di attività batch**: specifica un numero massimo di attività batch. Nella maggior parte dei casi, il valore dovrebbe essere compreso tra *8* e *16*. Tuttavia, ti consigliamo di sperimentare per trovare l'impostazione ottimale per i tuoi scenari.
    - **Gruppo batch elaborazione ondata**: selezionare un gruppo batch di elaborazione ondata dedicato per ottimizzare l'elaborazione della coda batch.

Ora puoi aggiornare un modello ciclo esistente in modo che utilizzi il metodo di elaborazione ciclo *Stampa etichette ciclo*. In alternativa, puoi creare un nuovo modello ciclo che lo utilizzi.

1. Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Nel riquadro dell'elenco, seleziona il modello ciclo da aggiornare. Se stai utilizzando dati demo a scopo di test, puoi selezionare il magazzino *24 Spedizione predefinita*.
1. Nella Scheda dettaglio **Metodi**, nella colonna **Metodi rimanenti**, seleziona la riga in cui il campo **Nome** è impostato su *waveLabelPrinting*.
1. Seleziona il pulsante **Aggiungi** (pulsante freccia destra) per spostare la riga selezionata nella colonna **Metodi selezionati**.
1. Nel campo **Codice passaggio ciclo** immetti un codice di passaggio ciclo che verrà utilizzato per collegare il modello ciclo a un modello etichetta ciclo.

## <a name="set-wave-task-processing-threshold-data"></a>Impostare i dati della soglia di elaborazione dell'attività di ondata

La prima volta che un processo ciclo viene eseguito utilizzando un'elaborazione basata su attività, il sistema crea dati di soglia di elaborazione dell'attività ciclo predefiniti. I dati vengono utilizzati per controllare quando l'elaborazione ciclo verrà eseguita in modo asincrono e sarà basata su attività, il che consente di elaborare e creare le etichette ciclo in parallelo.

I dati predefiniti utilizzano inizialmente un valore di soglia di *1* per il numero minimo di ID lavoro (`MinimumWorkThresholdForLabelPrinting`). Pertanto, quando il sistema elabora un ciclo che ha più di un ID lavoro, utilizzerà l'elaborazione basata su attività delle etichette ciclo in una transazione separata. Puoi inserire o aggiornare manualmente questi dati nella tabella `WHSWaveTaskProcessingThresholdParameters` negli ambienti di test. Per modificare questa impostazione in un ambiente di produzione, devi contattare il supporto Microsoft per richiedere l'aggiornamento.

## <a name="changes-to-the-wave-processing-logic-when-task-based-wave-label-printing-is-used"></a>Modifiche alla logica di elaborazione ciclo quando viene utilizzata la stampa di etichette ciclo basata su attività

Se l'elaborazione dell'etichetta ciclo supera la soglia di elaborazione dell'attività ciclo, viene avviata l'elaborazione basata sull'attività. Nella successiva elaborazione ciclo che si adatta al modello ciclo, la stampa di etichette ciclo verrà eseguita in una transazione *ttsbegin*/*ttscommit* autonoma subito dopo la creazione del lavoro. Se il rilascio del lavoro (sblocco) è configurato sul modello ciclo per l'esecuzione automatica, si verifica solo dopo che il processo di stampa dell'etichetta ciclo è stato completato.

Se la generazione dell'etichetta ciclo non riesce (ad esempio, se la conversione della quantità di lavoro nella quantità dell'etichetta ciclo ha esito negativo e genera un errore), solo la transazione appropriata ha esito negativo. Il lavoro creato in precedenza rimane congelato. Per correggere gli errori e stampare le etichette ciclo, segui questi passaggi.

1. Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.
1. Seleziona il relativo ciclo nella griglia.
1. Nel riquadro azioni, scheda **Ondata**, gruppo **Stampa**, selezionare **Etichette ondata**.
1. Segui le istruzioni sullo schermo per inviare le etichette per la stampa.
1. Nel riquadro azioni, nella scheda **Ciclo**, nel gruppo **Ciclo** seleziona **Rilascia** per rilasciare manualmente il lavoro per il ciclo selezionato.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Stampa di etichette ciclo](configure-wave-label-printing.md)
- [Programmare la creazione del lavoro durante il ciclo](configure-wave-schedule-work-creation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
