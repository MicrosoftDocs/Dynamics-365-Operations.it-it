---
title: Panoramica dei processi di fatturazione automatizzati dei fornitori
description: In questo argomento viene descritta l'automatizzazione dell'elaborazione delle fatture fornitore e i vantaggi inerenti all'utilizzo di un processo automatizzato.
author: abruer
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: c409b460df4c6a8b2f7811083e8c13c8fdfc186c09f859ecb91e2f3cc0b8b59f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749128"
---
# <a name="automated-vendor-invoicing-processes-overview"></a>Panoramica dei processi di fatturazione automatizzati dei fornitori

[!include [banner](../includes/banner.md)]

In questo argomento viene descritta l'automatizzazione dell'elaborazione delle fatture fornitore e i vantaggi inerenti all'utilizzo di un processo automatizzato. Questa soluzione è costituita da funzionalità attivate in Gestione funzionalità. Tali funzionalità si applicano solo alle fatture fornitore, non alle fatture elaborate tramite la pagina **Giornale di registrazione fatture** o **Giornale di registrazione del registro fatture**.

In molti casi, le organizzazioni si avvalgono di terzi parti per elaborare fatture cartacee utilizzando un provider di servizi OCR di terze parti. Il fornitore di servizi restituisce metadati di fatture leggibili da una macchina. Per facilitare l'automazione, le funzionalità di automazione della contabilità fornitori ti consentono di utilizzare questi artefatti in Contabilità fornitori.

Puoi automatizzare alcuni processi di fatturazione della contabilità fornitori. Questi processi includono l'invio di fatture fornitore importate al sistema del flusso di lavoro e l'abbinamento delle righe di entrata prodotti registrate alle righe di fattura fornitore in sospeso. Il processo automatizzato mostra le informazioni sullo stato di avanzamento di una fattura fornitore durante ognuno dei processi. Questa soluzione può aiutare gli impiegati e i responsabili della contabilità fornitori a elaborare fatture fornitori in modo più efficiente. Aiuta anche a ridurre gli errori e le inefficienze che possono verificarsi quando le informazioni vengono inserite ed elaborate manualmente.

I processi di automazione possono essere utilizzati per eseguire queste attività:

- Inviare automaticamente fatture importate al sistema del flusso di lavoro.
- Abbinare entrate prodotti alle righe di fattura fornitore in sospeso.
- Simulare la registrazione prima della registrazione di una fattura fornitore.
- Visualizzare lo storico automazione e flusso di lavoro in modo rapido ed efficiente.
- Visualizzare e analizzare i risultati dell'automazione dell'elaborazione delle fatture fornitori.
- Riprendi l'elaborazione automatizzata per più fatture.

## <a name="submit-imported-vendor-invoices-to-the-workflow-system"></a>Inviare fatture fornitore importate al sistema del flusso di lavoro

Come parte di un processo di fatturazione della contabilità fornitori senza contatto, puoi fare in modo che il sistema invii automaticamente una fattura importata al sistema del flusso di lavoro. Il processo verrà eseguito in background, alla frequenza da te specificata (oraria o giornaliera). Per inviare automaticamente fatture importate al sistema del flusso di lavoro, è necessario che il processo inizi con una fattura importata. Per garantire che la fattura possa essere elaborata dall'inizio alla fine senza intervento manuale, devi includere un'attività di registrazione automatizzata nella configurazione del flusso di lavoro.


Le fatture correlate agli ordini fornitore e le fatture che contengono una categoria di approvvigionamento non ordine fornitore e righe non a magazzino possono essere inviate automaticamente al sistema del flusso di lavoro. Le fatture immesse manualmente e le fatture create tramite l'area di lavoro **Fatturazione di collaborazione fornitore** devono essere inviate manualmente al sistema del flusso di lavoro. L'elaborazione della richiesta di pagamento anticipato deve essere eseguita manualmente per le fatture importate. È possibile applicare manualmente i pagamenti anticipati prima o dopo la registrazione della fattura importata. È possibile applicare manualmente i pagamenti anticipati a fatture standard non registrate utilizzando la pagina **Fatture fornitore**. Dopo la registrazione, il pagamento anticipato regolato sarà disponibile per essere applicato manualmente ad altre fatture di questo fornitore nella pagina **Fornitori** (**Contabilità fornitori \> Comune \> Fornitori \> Tutti i fornitori \> Scheda Fattura\> Applica**).

La funzionalità di automazione fornisce un framework flessibile che consente di definire regole specifiche dell'azienda per l'invio di fatture fornitore importate al sistema del flusso di lavoro e l'abbinamento delle righe di entrata prodotti registrate alle righe di fattura fornitore in sospeso.

## <a name="match-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Abbinare entrate prodotti a righe di fattura che hanno criteri di abbinamento a tre elementi di verifica

Il sistema può abbinare automaticamente le entrate prodotti registrate alle righe di fattura per cui sono definiti criteri di abbinamento a tre elementi di verifica. Il processo verrà eseguito fino a quando la quantità delle entrate prodotti abbinate non sarà uguale alla quantità della fattura. Come parte di questo processo, puoi specificare il numero massimo di tentativi del sistema di abbinare le entrate prodotti a una riga di fattura prima che il sistema consideri il processo come non riuscito. Il processo verrà eseguito in background, ogni ora o ogni giorno. Puoi eseguire il processo di abbinamento automatizzato come parte del processo di invio di fatture al sistema del flusso di lavoro. In alternativa, puoi eseguirlo come processo autonomo.

## <a name="pre-validate-vendor-invoice-posting"></a>Pre-convalidare la registrazione delle fatture fornitore

La simulazione della registrazione completa i passaggi di convalida eseguiti durante il processo di registrazione delle fatture fornitore, ma nessun conto viene aggiornato. Per eseguire il processo, puoi selezionare una singola fattura o più fatture nella pagina **Fatture fornitore in sospeso**.

## <a name="enhanced-experience-for-viewing-workflow-and-automation-historical-information-for-vendor-invoices"></a>Esperienza migliorata per la visualizzazione delle informazioni dello storico automazione e flusso di lavoro per fatture fornitore

Viene fornita una visualizzazione di facile lettura dello storico flusso di lavoro delle fatture fornitore. Puoi accedere allo storico flusso di lavoro delle fatture fornitore direttamente dalla fattura fornitore. Pertanto, sono necessari meno clic per trovare tali informazioni. Se l'organizzazione ha abilitato la possibiliyà di inviare automaticamente le fatture fornitore importate al flusso di lavoro, viene fornita la cronologia dell'automazione per le fatture importate. La cronologia dell'automazione aiuta a identificare il passaggio del processo corrente, nonché i passaggi che sono già stati completati. Quando un passaggio non viene completato, il sistema fornisce informazioni dettagliate per aiutarti a comprendere il motivo dell'errore.

## <a name="analytics-and-metrics"></a>Analisi e metriche

L'area di lavoro **Inserimento fatture fornitore** ti consente di concentrarti sulle fatture fornitore che non hanno superato il processo automatizzato. I riquadri nell'area di lavoro elencano le informazioni sulle fatture fornitore che non sono state inviate correttamente al sistema del flusso di lavoro, importate o abbinate alle entrate prodotti. Sono inoltre disponibili metriche Microsoft Power BI per fornire ai responsabili della contabilità fornitori una visione dell'efficienza dell'automazione delle fatture fornitore.


## <a name="resume-automation-processing-for-multiple-invoices"></a>Riprendere l'elaborazione automatizzata per più fatture

Quando una fattura importata non viene inviata correttamente al flusso di lavoro tramite il processo automatizzato, il sistema la rimuoverà dall'ulteriore elaborazione automatizzata. Un addetto alla contabilità fornitori può esaminare e modificare la fattura prima che il processo automatizzato la invii nuovamente al flusso di lavoro. Quando un motivo di errore può essere risolto con la stessa correzione per più fatture, puoi riavviare il processo automatizzato nella pagina **Riprendi l'elaborazione automatica delle fatture**. 

## <a name="tracking-the-invoice-received-date-value"></a>Monitoraggio del valore di Data di ricezione fattura

Il valore **Data di ricezione fattura** indica la data in cui l'azienda ha ricevuto la fattura dal fornitore. Fornisce un punto di partenza per monitorare l'avanzamento della fattura nei processi di automazione. Questo valore può essere incluso nei dati importati di una fattura fornitore. Per le fatture create manualmente, è possibile specificare la data. Se non viene immesso alcun valore, per impostazione predefinita viene utilizzata la data corrente.


## <a name="tracking-the-imported-invoice-amount-and-imported-sales-tax-amount-values"></a>Monitoraggio dei valori Importo fattura importata e Importo IVA importata

I valori **Importo fattura importata** e **Importo IVA importata** per le fatture fornitore possono essere forniti nel file di importazione delle fatture fornitore. In genere, questi valori provengono da una fattura sottoposta a scansione da un fornitore esterno e inclusa nel file di importazione. Quando la fattura viene elaborata in Contabilità fornitori, il sistema calcola i valori in base ai dati della fattura. La fattura può essere registrata solo se i valori importati corrispondono ai valori calcolati. I valori corrispondenti garantiscono che la fattura rifletta accuratamente l'importo dovuto al fornitore. Se l'organizzazione consente l'invio automatico delle fatture importate al sistema del flusso di lavoro, è possibile richiedere eventualmente che i totali importati corrispondano ai totali calcolati prima che la fattura possa essere inviata al sistema del flusso di lavoro.

## <a name="vendor-invoice-automation---resume-automation-processing-for-multiple-invoices"></a>Automazione delle fatture fornitore: riprendere l'elaborazione dell'automazione per più fatture
Quando una fattura importata non viene inviata correttamente al flusso di lavoro tramite il processo automatizzato, il sistema la rimuoverà dall'ulteriore elaborazione automatizzata. Un addetto alla contabilità fornitori può esaminare e modificare la fattura prima che il processo automatizzato la invii nuovamente al flusso di lavoro. Quando un motivo di errore può essere risolto con la stessa correzione per più fatture, puoi riavviare il processo automatizzato nella pagina **Riprendi l'elaborazione automatica delle fatture**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
