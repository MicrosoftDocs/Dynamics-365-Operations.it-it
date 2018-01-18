---
title: Determinare la combinazione ottimale di sconti sovrapposti
description: "Quando gli sconti si sovrappongono, è necessario determinare la combinazione di sconti sovrapposti che produrranno il totale transazione più basso o lo sconto totale più alto. Quando l'importo dello sconto dipende dal prezzo dei prodotti acquistati, come ad esempio nel comune sconto al dettaglio \"Compri 1, prendi 1 con lo sconto dell'X%\", questo processo diventa una questione di ottimizzazione combinatoria."
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailParameters, RetailPeriodicDiscount,
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations, Retail
ms.custom: 89643
ms.assetid: 09843c9a-3e19-4e4a-a8ce-80650f2095f9
ms.search.region: global
ms.search.industry: Retail
ms.author: kfend
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4b561503efa24bc4017a4c4360e0355ce39e2f56
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="determine-the-optimal-combination-of-overlapping-discounts"></a>Determinare la combinazione ottimale di sconti sovrapposti

[!include[banner](includes/banner.md)]


Quando gli sconti si sovrappongono, è necessario determinare la combinazione di sconti sovrapposti che produrranno il totale transazione più basso o lo sconto totale più alto. Quando l'importo dello sconto dipende dal prezzo dei prodotti acquistati, come ad esempio nel comune sconto al dettaglio "Compri 1, prendi 1 con lo sconto dell'X%", questo processo diventa una questione di ottimizzazione combinatoria.

Questo articolo si applica a Microsoft Dynamics AX 2012 R3 con KB 3105973 (rilasciato il 2 novembre 2015) o versioni successive e a Microsoft Dynamics 365 for Retail. Per determinare la combinazione di sconti sovrapposti da applicare con puntualità, abbiamo introdotto un metodo per l'applicazione degli sconti sovrapposti. Chiamiamo il nuovo metodo **classificazione del valore marginale**. Classificazione del valore marginale viene utilizzata quando il tempo necessario per valutare le possibili combinazioni di sconti sovrapposti supera una soglia configurabile nella pagina **Parametri di vendita al dettaglio**. Nel metodo di classificazione del valore marginale, un valore viene calcolato per ciascuno sconto sovrapposto utilizzando il valore dello sconto sui prodotti condivisi. Gli sconti sovrapposti vengono quindi applicati dal valore relativo più alto al valore relativo più basso. Per informazioni dettagliate sul nuovo metodo, vedere la sezione "Valore marginale", più avanti in questo articolo. La classificazione del valore marginale non viene utilizzata quando gli importi di sconto per un prodotto non sono influenzati da un altro prodotto nella transazione. Ad esempio, questo metodo non viene utilizzato per due sconti semplici, o per uno sconto semplice e uno sconto quantità di un prodotto singolo.

## <a name="discount-examples"></a>Esempi di sconto
È possibile creare un numero illimitato di sconti al dettaglio per un set comune di prodotti. Tuttavia, poiché non esiste un limite, problemi di prestazioni possono verificarsi quando si tenta di calcolare gli sconti da utilizzare sui vari prodotti. Gli esempi seguenti illustrano più dettagliatamente questo problema. Nell'esempio 1, cominciamo con due prodotti e due sconti sovrapposti. Quindi, nell'esempio 2, mostriamo come si evolve il problema con l'aggiunta di più prodotti.

### <a name="example-1-two-products-and-two-discounts"></a>Esempio 1: Due prodotti e due sconti

In questo esempio, due prodotti sono necessari per qualificarsi per ciascuno sconto e gli sconti non possono essere combinati. Gli sconti in questo esempio sono sconti **Prezzo migliore**. Entrambi i prodotti sono idonei a entrambi gli sconti. Di seguito vengono riportati i due sconti.
![Combinazione 01 sconti sovrapposti](./media/overlapping-discount-combo-01.jpg)

Per qualsiasi combinazione di due prodotti, il migliore dei due sconti dipende dai prezzi dei due prodotti. Se il prezzo di entrambi i prodotti è uguali o quasi uguale, lo sconto 1 è preferibile. Se il prezzo di un prodotto è molto inferiore al prezzo dell'altro prodotto, lo sconto 2 è preferibile. Ecco la regola matematica per la valutazione reciproca dei due sconti: ![Combinazione 02 di sconti sovrapposti](./media/overlapping-discount-combo-02.jpg)

**Nota:** quando il prezzo del prodotto 1 equivale a due terzi del prezzo del prodotto 2, i due sconti sono uguali. In questo esempio, la percentuale di sconto valida per lo sconto 1 varia da pochi punti percentuali (quando i prezzi dei due prodotti sono molto diversi) fino a un massimo del 25% (quando i due prodotti hanno lo stesso prezzo). La percentuale di sconto valida per lo sconto 2 è fissa. È sempre 20%. Poiché la percentuale di sconto valida per lo sconto 1 ha un intervallo che può essere superiore o inferiore allo sconto 2, il migliore sconto dipende dai prezzi dei due prodotti che devono essere scontati. In questo esempio, il calcolo viene completato rapidamente, poiché solo due sconti vengono applicati a solo due prodotti. Sono disponibili solo due possibili combinazioni: un'applicazione dello sconto 1 o una applicazione dello sconto 2. Non esistono permutazioni da calcolare. Il valore di ogni sconto viene calcolato utilizzando entrambi i prodotti e il migliore sconto viene utilizzato.

### <a name="example-2-four-products-and-two-discounts"></a>Esempio 2: quattro prodotti e due sconti

A questo punto, useremo quattro prodotti e gli stessi due sconti. Tutti e quattro i prodotti sono idonei a entrambi gli sconti. Sono disponibili dodici combinazioni possibili. Al termine, due sconti vengono applicati alla transazione in una delle seguenti tre combinazioni: due applicazioni dello sconto 1, due applicazioni dell'applicazione dello sconto, 2 o una applicazione dello sconto 1 e una applicazione dello sconto 2. Per illustrare le combinazioni possibili, esamineremo due diversi set di quattro prodotti con prezzi diversi:

-   Tutti e quattro i prodotti hanno lo stesso prezzo, $ 15,00. In questo caso, la migliore combinazione di sconto è due applicazioni dello sconto 1. Due prodotti saranno a prezzo pieno e due avranno lo sconto del 50%. Il totale scontato per la transazione è $ 45 (15 + 15 + 7,50 + 7,50), ovvero $ 15 (25%) di sconto sul totale non scontato di $ 60. Lo sconto 2 è solo $ 12 (20%).
-   Due prodotti costano $ 20 ciascuno, un prodotto $ 15 e un prodotto $ 5. In questo caso, la migliore combinazione di sconto è un'applicazione dello sconto 2 a un'applicazione dello sconto 1. Nelle tabelle seguenti vengono illustrati gli sconti.

Per leggere le tabelle, utilizzare un prodotto da una riga e un prodotto da una colonna. Ad esempio, nella tabella per lo sconto 1, quando si combinano i due prodotti da $ 20, si ottiene uno sconto di $ 10. Nella tabella per lo sconto 2, quando si combinano il prodotto $ 15 e il prodotto da $ 5, si ottiene uno sconto di $ 4.
![Combinazione 03 sconti sovrapposti](./media/overlapping-discount-combo-03.jpg)

Per prima cosa individuiamo lo sconto maggiore disponibile per qualsiasi combinazione di due prodotti utilizzando l'uno o l'altro sconto. Le due tabelle mostrano l'importo di sconto per tutte le combinazioni dei due prodotti. Le parti ombreggiate delle tabelle rappresentano casi in cui un prodotto è accoppiato con se stesso, che non è fattibile, o un abbinamento invertito di due prodotti che genera lo stesso importo di sconto e può essere ignorato. Esaminando le tabelle, si noterà che lo sconto 1 per i due articoli da $ 20 è il più grande sconti che sia disponibile per uno sconto su tutti e quattro i prodotti. Questo sconto viene evidenziato in verde nella prima tabella. Questo lascia solo il prodotto da $ 15 e il prodotto da $ 5. Esaminando le due tabelle di nuovo, si noterà che, per questi due prodotti, lo sconto 1 offre uno sconto di $ 2,50, mentre lo sconto 2 offre uno sconto di $ 4. Di conseguenza, selezioniamo lo sconto 2. Lo sconto totale è $ 14. Per semplificare la visualizzazione della discussione, ecco due tabelle aggiuntive in cui è visualizzata la percentuale di sconto valida per tutte le combinazioni possibili di due prodotti sia per lo sconto 1 che lo sconto 2. Solo metà dell'elenco di combinazioni è inclusa, poiché, per questi due sconti, l'ordine in cui i due prodotti vengono inclusi nello sconto non è rilevante. Il più alto sconto valido (25%) viene evideziato in verde e il più basso sconto valido (10%) viene evidenziato in rosso. 

![Combinazione 04 sconti sovrapposti](./media/overlapping-discount-combo-04.jpg)

**Nota:** se i prezzi variano e due o più sconti sono in concorrenza, l'unico modo per garantire la migliore combinazione di sconti è di valutare entrambi gli sconti e di confrontarli.

## <a name="total-possible-combinations"></a>Combinazioni possibili totali
In questa sezione continua l'esempio della sezione precedente. Aggiungeremo più prodotti e un altro sconto e vedremo quante combinazioni devono essere calcolate e confrontate. Nella seguente tabella è riportato il numero delle possibili combinazioni di sconto man mano che la quantità di prodotti aumenta. La tabella mostra cosa accade quando sono presenti due sconti sovrapposti, come nell'esempio precedente, e quando sono presenti tre sconti sovrapposti. Il numero delle possibili combinazioni di sconto che devono essere valutate supera anche quanto un computer veloce può calcolare e confrontare abbastanza rapidamente da essere accettabile per le transazioni di vendita al dettaglio.

![Combinazione 05 sconti sovrapposti](./media/overlapping-discount-combo-05.jpg)

Quando quantità anche maggiori o più sconti sovrapposti vengono applicati, il numero totale delle possibili combinazioni di sconto raggiunge rapidamente l'ordine dei milioni e il tempo necessario per valutare rapidamente e selezionare la combinazione migliore possibile diventa significativo. Alcune ottimizzazioni sono state effettuate nel motore del prezzo di vendita al dettaglio per ridurre il numero totale di combinazioni che devono essere valutate. Tuttavia, poiché il numero di sconti sovrapposti e le quantità in una transazione non sono limitati, un numero elevato di combinazioni sempre dovrà essere valutato ogni volta che si sovrappongono gli sconti. Questa situazione è il problema affrontato dal metodo della classificazione del valore marginale.

## <a name="marginal-value-method"></a>Metodo del valore marginale
Per risolvere il problema di un numero che cresce in modo esponenziale delle combinazioni che devono essere valutate, esiste un'ottimizzazione che calcola il valore per prodotto condiviso di ogni sconto nel set di prodotti a cui due o più sconti sono applicabili. Si fa riferimento a questo valore come al **valore marginale** dello sconto per i prodotti condivisi. Il valore marginale è la media per incremento di prodotto nell'importo di sconto totale quando i prodotti condivisi vengono inclusi in ogni sconto. Il valore marginale viene calcolato prendendo l'importo di sconto totale (DTotal), sottraendo l'importo dello sconto senza i prodotti condivisi (DMinus\\ Shared) e dividendo la differenza per il numero di prodotti condivisi (ProductsShared). 
![Combinazione 06 sconti sovrapposti](./media/overlapping-discount-combo-06.jpg)

Dopo che il valore marginale di ciascuno sconto in un set di prodotti condivisi viene calcolato, gli sconti vengono applicati ai prodotti condivisi nell'ordine, esaustivamente, dal valore marginale più elevato al valore marginale più basso. Per questo metodo, tutte le possibilità di sconto rimanenti non vengono confrontate ogni volta dopo che una singola istanza di uno sconto viene applicata. Invece, gli scontisovrapposti vengono confrontati una volta e quindi applicati nell'ordine. Nessun confronto aggiuntivo viene eseguito. È possibile configurare la soglia per passare al metodo del valore marginale nella scheda **Sconto** della pagina **Parametri di vendita al dettaglio**. Il tempo accettabile di calcolo dello sconto totale varia nei settori di vendita al dettaglio. Tuttavia, questo tempo rientra in genere nell'intervallo compreso tra decine di millisecondi e un secondo.




