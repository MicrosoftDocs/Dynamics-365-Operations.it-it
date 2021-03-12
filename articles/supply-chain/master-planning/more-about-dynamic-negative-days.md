---
title: Giorni negativi e giorni negativi dinamici
description: In questo argomento vengono fornite informazioni sui giorni negativi e sui giorni negativi dinamici nonché su come utilizzarli per la propria azienda.
author: t-benebo
manager: tfehr
ms.date: 06/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2019-06-07
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c098c04e8804187f5111fd10cb858a0c63289e3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983621"
---
# <a name="negative-days-and-dynamic-negative-days"></a>Giorni negativi e giorni negativi dinamici

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite informazioni sui giorni negativi e sui giorni negativi dinamici nonché su come utilizzarli per la propria azienda. L'*intervallo temporale dei giorni negativi* rappresenta il numero di giorni che si è disposti ad attendere prima di ordinare un nuovo rifornimento in caso di scorte negative.

In questo argomento viene descritto quanto segue:

- Il modo in cui gli ordini pianificati sono creati
- La correlazione tra l'intervallo temporale dei giorni negativi e il lead time dell'articolo
- Il modo in cui l'intervallo temporale dei giorni negativi dinamici viene calcolato e come il lead time dell'articolo viene preso in considerazione nel calcolo
- Il modo in cui interpretare i [suggerimenti per il miglioramento del tempo di esecuzione per la pianificazione dei fabbisogni materiali (MRP) (pianificazione generale)](https://blogs.msdn.com/b/axmfg/archive/2015/01/02/checklist-for-improving-mrp-performance-part-2-how-to-setup-planning-parameters.aspx) sono correlati ai giorni negativi

In questo argomento vengono utilizzati tre scenari ipotetici che consentono di comprendere tali informazioni. La differenza tra gli scenari è il punto in cui si riceve la richiesta: prima, durante o dopo il lead time dell'articolo.

## <a name="scenario-1-you-get-demand-before-the-items-lead-time-period"></a>Scenario 1: si riceve la richiesta prima del lead time dell'articolo

È possibile che si riceva la richiesta abbastanza presto nel lead time dell'articolo o appena prima dell'inizio del lead time. Di seguito è riportato un esempio di questo scenario:

- L'articolo DemoProduct presenta un lead time di acquisto di sei giorni.
- Il giorno zero (1° gennaio), il livello delle scorte per l'articolo DemoProduct è 0 (zero).
- Il giorno zero (1° gennaio), si riceve un ordine cliente per una quantità di 10 articoli DemoProduct.
- Il giorno sette (7 gennaio), si ha un ordine fornitore esistente per una quantità di 10 articoli DemoProduct.

La figura seguente illustra una visualizzazione grafica di questo scenario.

![Visualizzazione grafica dello scenario 1](./media/negative-days-1.jpg)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Caso A: i giorni negativi sono inferiori al lead time dell'articolo

Se si impostano i giorni negativi su un numero inferiore al lead time dell'articolo, MRP cerca le entrate dell'articolo DemoProduct all'interno dell'intervallo temporale dei giorni negativi. Poiché non viene trovata alcuna entrata, MRP crea un nuovo ordine fornitore pianificato. Questo ordine pianificato viene immediatamente ritardato di sei giorni (il lead time). Di conseguenza, arriverà il 7 gennaio. L'ordine fornitore esistente riceve un messaggio d'azione **Annulla**, in quanto la creazione del nuovo ordine fornitore pianificato lo ha reso ridondante.

La figura seguente illustra una schermata di questo tipo.

![Schermata del caso A per lo scenario 1](./media/negative-days-2.png)

La figura seguente illustra una visualizzazione grafica di ciò che avviene in questo caso.

![Visualizzazione grafica del caso A per lo scenario 1](./media/negative-days-3.png)

Se si considerano le prestazioni MRP e si prevede una certa instabilità, questo caso non risulterà appropriato. MRP deve creare un nuovo ordine pianificato e deve calcolare ritardi e azioni. Queste attività richiedono molto tempo. Questo caso inoltre aggiunge due nuove transazioni al piano. D'altra parte, l'ordine cliente viene ritardato di sei giorni, non sette.

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Caso B: i giorni negativi sono maggiori del lead time dell'articolo

Per migliorare le prestazioni MRP, è possibile impostare i giorni negativi su un numero maggiore del lead time dell'articolo. Poiché non è possibile ottenere la fornitura all'interno del lead time in questo scenario, è possibile cercare le entrate purché tale ricerca abbia una logica. Sebbene il tempo di esecuzione per MRP sarà più breve, è necessario fare attenzione ai ritardi degli ordini.

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Casa C: correlare automaticamente il lead time dell'articolo all'intervallo temporale dei giorni negativi

Per correlare automaticamente il lead time dell'articolo all'intervallo temporale dei giorni negativi, utilizzare i giorni negativi dinamici. Per utilizzare i giorni negativi dinamici, andare a **Pianificazione generale \> Impostazioni \> Parametri di pianificazione generale**, quindi nella scheda **Generale**, nella sezione **Copertura**, impostare l'opzione **Utilizza giorni negativi dinamici** su **Sì**. MRP cerca quindi tutte le entrate all'interno dell'intervallo temporale relativo dei giorni negativi dinamici. Questo intervallo temporale viene calcolato mediante la seguente formula:

Intervallo temporale dei giorni negativi dinamici = Lead time di acquisto + Intervallo temporale dei giorni negativi+ (Data corrente - Data fabbisogno)

(se il tipo di ordine predefinito dell'articolo DemoProduct è **Produzione** o **Trasferimento**, il lead time è il lead time **scorte**).

Quando si utilizzano i giorni negativi dinamici, l'intervallo temporale che MRP prende in considerazione per le entrate è 6 + 2 + 0 = 8 giorni. MRP trova l'ordine fornitore esistente e lo utilizza per eseguire il pegging dell'ordine cliente. Non vengono creati nuovi ordini pianificati. Di conseguenza, il tempo di esecuzione per MRP è più breve. Nell'illustrazione seguente vengono mostrati i fabbisogni netti per l'articolo DemoProduct.

![Fabbisogni netti per il caso C per lo scenario 1](./media/negative-days-4.png)

La figura seguente illustra una visualizzazione grafica di ciò che avviene in questo caso.

![Visualizzazione grafica del caso C per lo scenario 1](./media/negative-days-5.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Caso D: utilizzare solo giorni negativi dinamici

Se si impostano i giorni negativi su **0** (zero) e si utilizza solo l'intervallo temporale dei giorni negativi dinamici, l'intervallo temporale dei giorni negativi dinamici è 6 + 0 + 0 = 6 giorni. In questo caso, il risultato è uguale al risultato del caso A per questo scenario. MRP deve creare un nuovo ordine pianificato e deve calcolare ritardi e azioni. Queste attività richiedono molto tempo e possono anche essere scoraggianti. Si hanno inoltre due ulteriori transazioni da elaborare. Poiché la richiesta non può essere soddisfatta in tempo affinché l'articolo arrivi, questo caso aggiunge complicazioni inutili al piano.

La figura seguente illustra una schermata di questo caso.

![Schermata del caso D per lo scenario 1](./media/negative-days-6.png)

La figura seguente illustra una visualizzazione grafica di ciò che avviene in questo caso.

![Visualizzazione grafica del caso D per lo scenario 1](./media/negative-days-7.png)

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Caso E: utilizzare i giorni negativi maggiori del lead time dell'articolo e l'intervallo temporale dei giorni negativi dinamici

Se invece si impostano i giorni negativi su un numero maggiore del lead time dell'articolo e si utilizza anche l'intervallo temporale dei giorni negativi dinamici, l'intervallo temporale dei giorni negativi dinamici è 6 + 6 + 0 = 12 giorni. Questo approccio potrebbe produrre un intervallo temporale molto lungo in cui MRP deve cercare i risultati. Per informazioni su come il caso E è correlato a una situazione in cui invece si impostano i giorni negativi su un intervallo temporale lungo, vedere la sezione [Conclusione](#conclusion) di questo argomento.

## <a name="scenario-2-you-get-demand-during-the-items-lead-time-period"></a>Scenario 2: si riceve la richiesta durante il lead time dell'articolo

È possibile che si riceva la richiesta durante il lead time dell'articolo. Di seguito è riportato un esempio di questo scenario:

- L'articolo DemoProduct presenta un lead time di acquisto di sei giorni. 
- Il giorno zero (1° gennaio), il livello delle scorte per l'articolo DemoProduct è 0 (zero).
- Il giorno quattro (5 gennaio), all'interno del lead time dell'articolo, si riceve un ordine cliente per una quantità di 10 articoli DemoProduct.
- Il giorno sette (8 gennaio), si ha un ordine fornitore per una quantità di 10 articoli DemoProduct.

La figura seguente illustra una visualizzazione grafica di questo scenario.

![Visualizzazione grafica dello scenario 1](./media/negative-days-8.png)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Caso A: i giorni negativi sono inferiori al lead time dell'articolo

Se si impostano i giorni negativi su un numero inferiore al lead time dell'articolo, MRP cerca le entrate dell'articolo DemoProduct all'interno dell'intervallo temporale dei giorni negativi. Poiché non trova alcuna entrata, MRP crea un nuovo ordine fornitore pianificato che utilizza la data corrente come data dell'ordine. Questo ordine pianificato viene immediatamente ritardato di sei giorni (il lead time). Di conseguenza, arriverà il 7 gennaio. L'ordine fornitore esistente riceve un messaggio d'azione **Annulla**, in quanto la creazione del nuovo ordine fornitore pianificato lo ha reso ridondante.

La figura seguente illustra una schermata di questo caso.

![Schermata del caso A per lo scenario 2](./media/negative-days-9.png)

La figura seguente illustra una visualizzazione grafica di ciò che avviene in questo caso.

![Visualizzazione grafica del caso A per lo scenario 2](./media/negative-days-10.png)

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Caso B: i giorni negativi sono maggiori del lead time dell'articolo

Questo caso è simile al caso B per lo scenario 1. Se si impostano i giorni negativi su un numero maggiore del lead time dell'articolo, non si riceve un nuovo ordine pianificato. L'ordine cliente è associato all'ordine fornitore esistente.

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Casa C: correlare automaticamente il lead time dell'articolo all'intervallo temporale dei giorni negativi

Questo caso è simile al caso C per lo scenario 1, poiché i giorni negativi dinamici funzionano altrettanto bene che in quel caso. L'intervallo temporale dei giorni negativi dinamici è ora di 6 + 2 - 4 = 4 giorni. Se si utilizza questo approccio, MRP trova l'ordine fornitore esistente e vi associa l'ordine cliente. Poiché non vengono creati nuovi ordini pianificati, il tempo di esecuzione per MRP è più breve.

La figura seguente illustra una schermata di questo tipo.

![Schermata del caso C per lo scenario 2](./media/negative-days-11.png)

La figura seguente illustra una visualizzazione grafica di ciò che avviene in questo caso.

![Visualizzazione grafica del caso C per lo scenario 2](./media/negative-days-12.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Caso D: utilizzare solo giorni negativi dinamici

Se si impostano i giorni negativi su **0** (zero) e si utilizza solo l'intervallo temporale dei giorni negativi dinamici, l'intervallo temporale dei giorni negativi dinamici è 6 + 0 - 4 = 2 giorni. In questo caso, il risultato è uguale al risultato del caso A per questo scenario. Per una visualizzazione grafica di ciò che avviene, vedere il caso A per questo scenario.

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Caso E: utilizzare i giorni negativi maggiori del lead time dell'articolo e l'intervallo temporale dei giorni negativi dinamici

Se si impostano i giorni negativi su un numero maggiore del lead time dell'articolo e si utilizza anche l'intervallo temporale dei giorni negativi dinamici, questo intervallo è pari a 6 + 6 - 4 = 8 giorni. Questo approccio potrebbe produrre un intervallo temporale molto lungo in cui MRP deve cercare i risultati. Per informazioni su come il caso E è correlato a una situazione in cui invece si impostano i giorni negativi su un intervallo temporale lungo, vedere la sezione [Conclusione](#conclusion) di questo argomento.

## <a name="scenario-3-you-get-demand-after-the-items-lead-time-period"></a>Scenario 3: si riceve la richiesta dopo il lead time dell'articolo

È possibile che si riceva la richiesta dopo il lead time dell'articolo. Di seguito è riportato un esempio di questo scenario:

- L'articolo DemoProduct presenta un lead time di acquisto di sei giorni.
- Il giorno zero (1° gennaio), il livello delle scorte per l'articolo DemoProduct è 0 (zero).
- Il giorno sette (8 gennaio), all'esterno del lead time dell'articolo, si riceve un ordine cliente per una quantità di 10 articoli DemoProduct.
- Il giorno 10 (11 gennaio), si ha un ordine fornitore per una quantità di 10 articoli DemoProduct.

La figura seguente illustra una visualizzazione grafica di questo scenario.

![Visualizzazione grafica dello scenario 3](./media/negative-days-13.png)

### <a name="case-a-negative-days-are-less-than-the-items-lead-time"></a>Caso A: i giorni negativi sono inferiori al lead time dell'articolo

Se si impostano i giorni negativi su un numero inferiore al lead time dell'articolo, MRP effettua la ricerca due giorni prima della data fabbisogno dell'ordine cliente. Poiché non trova nulla, MRP crea un nuovo ordine fornitore pianificato il 2 gennaio. Questo ordine fornitore pianificato verrà spedito in tempo per soddisfare la richiesta dell'ordine cliente. L'ordine fornitore esistente riceve un messaggio d'azione **Annulla** in quanto non è obbligatorio.

La figura seguente illustra una schermata di questo tipo.

![Schermata del caso A per lo scenario 3](./media/negative-days-14.png)

La figura seguente illustra una visualizzazione grafica di ciò che avviene in questo caso.

![Visualizzazione grafica del caso A per lo scenario 3](./media/negative-days-15.png)

> [!NOTE]
> Nella schermata precedente, la data fabbisogno dell'ordine fornitore è il 12 gennaio. Poiché tale schermata è stato acquisita nel 2015, quando l'11 gennaio era una domenica, MRP ha spostato la data fabbisogno al giorno lavorativo successivo, ovvero lunedì 12 gennaio. Cionondimeno, la data di consegna dell'ordine fornitore è l'11 gennaio.

### <a name="case-b-negative-days-are-more-than-the-items-lead-time"></a>Caso B: i giorni negativi sono maggiori del lead time dell'articolo

Se si impostano i giorni negativi su un numero maggiore del lead time dell'articolo, non si riceve un nuovo ordine pianificato. L'ordine cliente viene sottoposto a pegging in base all'ordine fornitore esistente. Di conseguenza, l'ordine cliente viene ritardato. Se si crea un ordine pianificato, è possibile spedire l'ordine cliente in tempo.

La figura seguente illustra una schermata di questo tipo.

![Schermata del caso B per lo scenario 3](./media/negative-days-16.png)

La figura seguente illustra una visualizzazione grafica di ciò che avviene in questo caso.

![Visualizzazione grafica del caso B per lo scenario 3](./media/negative-days-17.png)

### <a name="case-c-automatically-correlate-the-items-lead-time-to-the-negative-days-time-fence"></a>Casa C: correlare automaticamente il lead time dell'articolo all'intervallo temporale dei giorni negativi

Questo caso è simile al caso C per lo scenario 1, poiché i giorni negativi dinamici funzionano altrettanto bene, se non meglio, che nel caso B di questo scenario.

L'intervallo temporale dei giorni negativi dinamici è 6 + 2 - 7 = 1 giorno. Tuttavia, in questo caso, il sistema prende ancora in considerazione il lead time dei giorni negativi (2), in quanto MRP considera il valore massimo tra il lead time dei giorni negativi e quello dei giorni negativi dinamici. Di conseguenza, il risultato in questo caso è lo stesso del caso A per questo scenario.

La figura seguente illustra una visualizzazione grafica di ciò che avviene in questo caso.

![Visualizzazione grafica del caso C per lo scenario 3](./media/negative-days-18.png)

### <a name="case-d-use-only-dynamic-negative-days"></a>Caso D: utilizzare solo giorni negativi dinamici

Se si impostano i giorni negativi su **0** (zero) e si utilizza solo l'intervallo temporale dei giorni negativi dinamici, questo intervallo temporale è 6 + 0 - 7 = -1 giorno. In questo caso, il sistema prende ancora in considerazione il lead time dei giorni negativi (2). Di conseguenza, il risultato in questo caso è lo stesso del caso A per questo scenario e presenta gli stessi inconvenienti. Per una visualizzazione grafica di ciò che avviene, vedere il caso A per lo scenario 2.

### <a name="case-e-use-both-negative-days-that-are-more-than-the-items-lead-time-and-the-dynamic-negative-days-time-fence"></a>Caso E: utilizzare i giorni negativi maggiori del lead time dell'articolo e l'intervallo temporale dei giorni negativi dinamici

Questo caso è uguale al caso E per gli scenari 1 e 2. In pratica presenta gli stessi vantaggi e inconvenienti.

## <a name="conclusion"></a>Conclusioni

Come mostrano i tre scenari in questo argomento, è consigliabile impostare i giorni negativi su un numero maggiore del lead time degli articoli del gruppo di copertura. È inoltre consigliabile utilizzare solo i giorni negativi dinamici e impostare i giorni negativi sul numero di giorni che si è disposti ad attendere prima di ordinare un nuovo rifornimento in caso di scorte negative (in altre parole, il numero di giorni che si è disposti a ritardare ulteriormente la richiesta). Inoltre, gli articoli nello stesso gruppo di copertura deve avere lead time simili.

Se si impostano i giorni negativi su **0** (zero) e non si utilizzano i giorni negativi dinamici, MRP crea sempre un nuovo ordine pianificato per soddisfare la richiesta. In questa situazione, è importante utilizzare i messaggi d'azione per assicurarsi di non accumulare le scorte.

È possibile che si intenda impostare i giorni negativi su un intervallo temporale lungo e quindi utilizzare i messaggi d'azione. Questo approccio produce ottimi risultati di pianificazione, ma è anche un po' più lento. Potrebbe inoltre risultare più difficile da analizzare, poiché è necessario analizzare e applicare i messaggi d'azione. Ecco un esempio:

- L'articolo DemoProduct presenta un lead time di acquisto di sei giorni.
- Il giorno zero (1° gennaio), il livello delle scorte per l'articolo DemoProduct è 0 (zero).
- Il giorno zero (1° gennaio), si riceve un ordine cliente per una quantità di 10 articoli DemoProduct.
- Il giorno 10 (10 gennaio), si riceve un ordine cliente per una quantità di 10 articoli DemoProduct.
- Il giorno 12 (12 gennaio), si ha un ordine fornitore per una quantità di 10 articoli DemoProduct.
- I giorni negativi sono impostati su **20**, che è molto di più del lead time dell'articolo.

La figura seguente illustra una visualizzazione grafica di ciò che avviene.

![Visualizzazione grafica dell'esempio](./media/negative-days-19.png)

MRP genera i risultati descritti di seguito.

![Risultati](./media/negative-days-20.png)

Nella schermata precedente, la data fabbisogno dell'ordine cliente è il 9 gennaio anziché il 10 gennaio. Poiché tale schermata è stato acquisita nel 2015, quando il 10 gennaio era un sabato, la data fabbisogno dell'ordine dovrebbe essere il giorno lavorativo precedente, ovvero venerdì 9 gennaio.

MRP crea un ordine fornitore pianificato per soddisfare la domanda richiesta dal primo ordine cliente, ma quindi consiglia di annullare l'ordine pianificato in quanto è possibile anticipare l'ordine fornitore esistente e aumentare la quantità sullo stesso.

I risultati non sono errati, ma il tempo di esecuzione per MRP potrebbe risultare più lungo, in quanto MRP deve creare tutti i ritardi e i suggerimenti. Inoltre,l'addetto alla pianificazione potrebbe richiedere più tempo per comprendere i risultati di MRP. Cosa più importante, in questo caso, è essenziale che l'addetto alla pianificazione comprenda e utilizzi i messaggi d'azione.

Se si riducono i giorni negativi a un numero maggiore che è più prossimo al lead time dell'articolo e si utilizzano i giorni negativi dinamici, MRP genera i risultati esposti di seguito.

![Risultati](./media/negative-days-21.png)

MRP crea un ordine pianificato associato al primo ordine cliente. Quindi, come previsto, il secondo ordine cliente viene sottoposto a pegging a fronte dell'ordine fornitore esistente, in base all'impostazione dei giorni negativi. Anche questo risultato di pianificazione è corretto e il tempo di esecuzione per MRP potrebbe risultare più breve. In questo caso, non è essenziale comprendere e sapere come utilizzare i messaggi d'azione.

Per garantire l'immissione dei valori corretti per la propria società, è necessario pensare in termini di funzionalità e tempo di esecuzione di MRP. Di conseguenza, è possibile che siano necessari alcuni tentativi per determinare i valori ottimali.

## <a name="see-also"></a>Vedere anche

Per ulteriori informazioni, vedere il post del blog [Altre informazioni sui giorni negativi (dinamici)](https://blogs.msdn.microsoft.com/axmfg/2015/02/19/more-about-dynamic-negative-days/).
