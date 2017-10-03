---
title: Media pesata con valore fisico e contrassegno
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 65501
ms.assetid: 25041ff0-bafe-484d-a94a-e1772ad43204
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: cdbca6d9c71c901a1f4e7a8e5a2f9be1d3efb355
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017

---

# <a name="weighted-average-with-physical-value-and-marking"></a>Media pesata con valore fisico e contrassegno

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]



Quando si esegue una chiusura inventario, tutte le entrate vengono liquidate a fronte di un'uscita virtuale, che comprende la quantità e il valore totale ricevuti. A questa uscita virtuale corrisponde un'entrata virtuale dalla quale vengono compensate le uscite. In questo modo, a tutte le uscite viene assegnato lo stesso costo medio. L'uscita e l'entrata virtuali possono essere considerate come un trasferimento virtuale, denominato trasferimento di chiusura inventario media ponderata.

Se è presente una sola entrata, tutte le uscite possono essere compensate da questa entrata senza che venga creato il trasferimento virtuale. 

Quando si utilizza la media ponderata, è possibile contrassegnare le operazioni di magazzino in modo che un'entrata articoli specifica venga compensata a fronte di un'uscita specifica anziché utilizzando la regola della media ponderata. 

Quando si utilizza il modello inventariale media ponderata, è consigliabile eseguire una chiusura inventario ogni mese. 

Il metodo di determinazione costi magazzino con media ponderata viene calcolato con la seguente formula:
-   Media ponderata = (Q1\*P1 + Q2\*P2 + Qn\*Pn) / (Q1 + Q2 + Qn)

Le operazioni di magazzino che non interessano le uscite da magazzino, inclusi gli ordini cliente, i giornali di registrazione magazzino e gli ordini di produzione, verranno eseguite a un prezzo di costo stimato alla data di registrazione. Il prezzo di costo stimato viene indicato anche come media corrente. Al momento della chiusura inventario, nel sistema verranno analizzate le operazioni di magazzino dei periodi precedenti e corrente per determinare quale tra i seguenti principi di chiusura utilizzare:
-   Compensazione diretta
-   Compensazione riepilogativa

Le compensazioni sono registrazioni di chiusura inventario che rettificano le uscite in base alla media ponderata corretta, calcolata alla data di chiusura. Negli esempi riportati di seguito è illustrato l'effetto dell'uso della media ponderata con cinque diverse configurazioni:
-   Compensazione diretta media ponderata senza l'opzione Includi valore fisico
-   Compensazione riepilogativa media ponderata senza l'opzione Includi valore fisico
-   Compensazione diretta media ponderata con l'opzione Includi valore fisico
-   Compensazione riepilogativa media ponderata con l'opzione Includi valore fisico
-   Media ponderata con contrassegno

## <a name="weighted-average-direct-settlement-without-include-physical-value"></a>Compensazione diretta media ponderata senza l'opzione Includi valore fisico
Il principio di compensazione diretta è lo stesso utilizzato per la media ponderata nelle versioni precedenti. La compensazione tra entrate e uscite verrà effettuata direttamente dal sistema. Questo principio di compensazione diretta viene utilizzato in alcune situazioni specifiche:
-   Nel periodo sono state registrate un'entrata e una o più uscite.
-   Nel periodo sono state registrate solo uscite e l'inventario contiene le scorte di articoli disponibili da una precedente chiusura.

Nello scenario descritto nelle sezioni seguenti sono state registrate un'entrata e un'uscita aggiornate finanziariamente. Durante la chiusura dell'inventario, l'entrata verrà compensata direttamente a fronte dell'uscita e non sarà quindi necessario rettificare il prezzo di costo al momento dell'uscita. Nel grafico riportato di seguito sono illustrate le seguenti transazioni.
-   1a. Entrata fisica in magazzino aggiornata per una quantità pari a 5 al costo unitario di 10,00 EUR
-   1b. Entrata finanziaria in magazzino aggiornata per una quantità pari a 5 al costo unitario di 10,00 EUR
-   2a. Uscita fisica da magazzino aggiornata per una quantità pari a 2 al costo unitario di 10,00 EUR
-   2b. Uscita finanziaria da magazzino aggiornata per una quantità pari a 2 al costo unitario di 10,00 EUR
-   3. La chiusura dell'inventario viene eseguita utilizzando il metodo di compensazione diretta per compensare l'entrata finanziaria in magazzino con l'uscita finanziaria dal magazzino.

Nel diagramma riportato di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale media ponderata e del principio di compensazione diretta senza l'opzione Includi valore fisico. 

![Compensazione diretta media ponderata senza l'opzione Includi valore fisico](./media/weightedaveragedirectsettlementwithoutincludephysicalvalue.gif) 

**Informazioni sul diagramma**
-   Le operazioni di magazzino sono rappresentate da frecce verticali.
-   Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
-   Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
-   Al di sopra o al di sotto di ciascuna freccia verticale, il valore dell'operazione di magazzino è specificato nel formato Quantity@Unitprice.
-   Un valore dell'operazione di magazzino racchiuso tra parentesi indica che l'operazione è stata registrata fisicamente in magazzino.
-   Un valore dell'operazione di magazzino non racchiuso tra parentesi indica che l'operazione è stata registrata finanziariamente in magazzino.
-   Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
-   Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano la successione delle registrazioni relative alle operazioni di magazzino nella sequenza temporale.
-   Le chiusure inventario sono rappresentate da una linea verticale tratteggiata di colore rosso e dall'etichetta Chiusura inventario.
-   Le compensazioni eseguite tramite chiusura inventario sono rappresentate da frecce puntate di colore rosso che uniscono in diagonale un'entrata a un'uscita.

## <a name="weighted-average-summarized-settlement-without-the-include-physical-value-option"></a>Compensazione riepilogativa media ponderata senza l'opzione Includi valore fisico
La media ponderata utilizza il principio di compensazione secondo il quale tutte le entrate comprese in un periodo di chiusura vengono riepilogate in una transazione denominata chiusura inventario media ponderata. Tutte le entrate del periodo verranno compensate a fronte dell'uscita della transazione di trasferimento scorte creata, mentre tutte le uscite del periodo verranno compensate a fronte dell'entrata della nuova transazione di trasferimento scorte. Se dopo la chiusura dell'inventario le scorte disponibili risultano positive, tali scorte e il valore di inventario vengono riepilogati nella nuova transazione di trasferimento scorte (entrata). Se dopo la chiusura dell'inventario le scorte disponibili risultano negative, tali scorte e il valore di inventario corrispondono alla somma delle singole uscite che non sono state completamente compensate. Nello scenario descritto di seguito sono state registrate un'uscita e alcune entrate aggiornate finanziariamente. 

Durante la chiusura dell'inventario, verrà generata e registrata la transazione di trasferimento scorte riepilogativa e verranno compensate tutte le entrate del periodo a fronte della transazione in uscita di trasferimento scorte riepilogativa. Tutte le uscite registrate per il periodo verranno compensate a fronte della transazione in entrata di trasferimento scorte riepilogativa. La media ponderata viene calcolata in 15,00 EUR. Poiché l'uscita è stata registrata in origine con un prezzo di costo stimato di 14,67 EUR, verrà creata e registrata per l'uscita una rettifica di un valore negativo di 0,33 EUR. Per quanto riguarda la data di chiusura dell'inventario, le scorte disponibili sono 3 pezzi con un valore di 45,00 EUR. 

Nel grafico riportato di seguito sono illustrate le seguenti transazioni:
-   1a. Entrata fisica in magazzino aggiornata per una quantità pari a 2 al costo unitario di 11,00 EUR.
-   1b. Entrata finanziaria in magazzino aggiornata per una quantità pari a 2 al costo unitario di 14,00 EUR.
-   2a. Entrata fisica in magazzino aggiornata per una quantità pari a 1 al costo unitario di 12,00 EUR.
-   2b. Entrata finanziaria in magazzino aggiornata per una quantità pari a 1 al costo unitario di 16,00 EUR.
-   3a. Uscita fisica da magazzino aggiornata per una quantità pari a 1 al costo unitario di 14,67 EUR (media corrente).
-   3b. Uscita finanziaria da magazzino aggiornata per una quantità pari a 1 al costo unitario di 14,67 EUR (media corrente).
-   4a. Entrata fisica in magazzino aggiornata per una quantità pari a 1 al costo unitario di 14,00 EUR.
-   4b. Entrata finanziaria in magazzino aggiornata per una quantità pari a 1 al costo unitario di 16,00 EUR.
-   5. Viene eseguita la chiusura inventario.
-   6a. Viene creata un'uscita finanziaria "transazione di chiusura inventario media ponderata" per sommare le compensazioni di tutte le entrate finanziarie in magazzino.
-   6b. Viene creata un'entrata finanziaria "transazione di chiusura inventario media ponderata" come contropartita per la transazione 5a.

Nel diagramma riportato di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale media ponderata e del principio di compensazione riepilogativo senza l'opzione Includi valore fisico. 

![Compensazione riepilogativa media ponderata senza l'opzione Includi valore fisico](./media/weightedaveragesummarizedsettlementwithoutincludephysicalvalue.gif) 

**Informazioni sul diagramma**
-   Le operazioni di magazzino sono rappresentate da frecce verticali.
-   Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
-   Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
-   Al di sopra o al di sotto di ciascuna freccia verticale, il valore dell'operazione di magazzino è specificato nel formato Quantity@Unitprice.
-   Un valore dell'operazione di magazzino racchiuso tra parentesi indica che l'operazione è stata registrata fisicamente in magazzino.
-   Un valore dell'operazione di magazzino non racchiuso tra parentesi indica che l'operazione è stata registrata finanziariamente in magazzino.
-   Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
-   Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano la successione delle registrazioni relative alle operazioni di magazzino nella sequenza temporale.
-   Le chiusure inventario sono rappresentate da una linea verticale tratteggiata di colore rosso e dall'etichetta Chiusura inventario.
-   Le compensazioni eseguite tramite chiusura inventario sono rappresentate da frecce puntate di colore rosso che uniscono in diagonale un'entrata a un'uscita.
-   Le frecce rosse indicano le transazioni in entrata compensate a fronte della transazione in uscita creata dal sistema.
-   La freccia verde rappresenta la transazione in entrata di contropartita generata dal sistema a fronte della quale viene compensata la transazione in uscita originariamente registrata.

## <a name="weighted-average-direct-settlement-with-the-include-physical-value-option"></a>Compensazione diretta media ponderata con l'opzione Includi valore fisico
Il funzionamento del parametro Includi valore fisico con il modello inventariale media ponderata è diverso rispetto alle versioni precedenti del prodotto. Selezionare la casella di controllo Includi valore fisico per un articolo nella pagina Gruppi di modelli di articoli. Verranno utilizzate le entrate aggiornate fisicamente durante il calcolo del prezzo di costo stimato o della media corrente. Le uscite verranno registrate in base a tale prezzo di costo stimato durante il periodo. Durante la chiusura dell'inventario, le entrate aggiornate finanziariamente verranno considerate solo nel calcolo della media ponderata. Quando si utilizza il modello inventariale media ponderata, si consiglia di eseguire una chiusura inventario ogni mese. In questo esempio di compensazione diretta media ponderata il gruppo di modelli di articoli è contrassegnato in modo da includere il valore fisico. 

Nel grafico riportato di seguito sono illustrate le seguenti transazioni:
-   1a. Entrata fisica in magazzino aggiornata per una quantità pari a 1 al costo unitario di 11,00 EUR.
-   1b. Entrata finanziaria in magazzino aggiornata per una quantità pari a 1 al costo unitario di 10,00 EUR.
-   2a. Entrata fisica in magazzino aggiornata per una quantità pari a 1 al costo unitario di 15,00 EUR.
-   3a. Uscita fisica da magazzino aggiornata per una quantità pari a 1 al costo unitario di 12,50 EUR (costo medio corrente, poiché viene preso in considerazione il valore dell'entrata fisica).
-   3b. Uscita finanziaria da magazzino aggiornata per una quantità pari a 1 al costo unitario di 12,50 EUR (costo medio corrente, poiché viene preso in considerazione il valore dell'entrata fisica).
-   4. Viene eseguita la chiusura inventario. Durante la chiusura dell'inventario, verranno ignorate tutte le operazioni di magazzino che sono state aggiornate solo fisicamente. Verrà utilizzato invece il principio di compensazione diretta poiché è presente solo un'entrata finanziaria. Verrà registrata una rettifica di 2,50 EUR nell'operazione di magazzino in uscita finanziaria alla data di chiusura dell'inventario. Dopo la chiusura dell'inventario, le scorte disponibili saranno una quantità pari a 1 con prezzo di costo medio corrente di 15,00 EUR.

Nel diagramma riportato di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale media ponderata e del principio di compensazione diretta con l'opzione Includi valore fisico. 

![Compensazione diretta media ponderata con l'opzione Includi valore fisico](./media/weightedaveragedirectsettlementwithincludephysicalvalue.gif) 

**Informazioni sul diagramma**
-   Le operazioni di magazzino sono rappresentate da frecce verticali.
-   Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
-   Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
-   Al di sopra o al di sotto di ciascuna freccia verticale, il valore dell'operazione di magazzino è specificato nel formato Quantity@Unitprice.
-   Un valore dell'operazione di magazzino racchiuso tra parentesi indica che l'operazione è stata registrata fisicamente in magazzino.
-   Un valore dell'operazione di magazzino non racchiuso tra parentesi indica che l'operazione è stata registrata finanziariamente in magazzino.
-   Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
-   Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano la successione delle registrazioni relative alle operazioni di magazzino nella sequenza temporale.
-   Le chiusure inventario sono rappresentate da una linea verticale tratteggiata di colore rosso e dall'etichetta Chiusura inventario.
-   Le compensazioni eseguite tramite chiusura inventario sono rappresentate da frecce puntate di colore rosso che uniscono in diagonale un'entrata a un'uscita.

## <a name="weighted-average-summarized-settlement-with-the-include-physical-value-option"></a>Compensazione riepilogativa media ponderata con l'opzione Includi valore fisico
Il funzionamento del parametro Includi valore fisico con la media ponderata è diverso rispetto alle versioni precedenti del programma. Selezionare la casella di controllo Includi valore fisico per un articolo nella pagina Gruppi di modelli di articoli. Verranno utilizzate le entrate aggiornate fisicamente durante il calcolo del prezzo di costo stimato o della media corrente. Le uscite verranno registrate in base al prezzo di costo stimato durante il periodo. Durante la chiusura dell'inventario, le entrate aggiornate finanziariamente verranno considerate solo nel calcolo della media ponderata. Quando si utilizza il modello inventariale media ponderata, si consiglia di eseguire una chiusura inventario ogni mese. In questo esempio di compensazione riepilogativa media ponderata il modello inventariale è contrassegnato in modo da includere il valore fisico. 

Nel grafico riportato di seguito sono illustrate le seguenti transazioni:
-   1a. Entrata fisica in magazzino aggiornata per una quantità pari a 2 al costo unitario di 11,00 EUR.
-   1b. Entrata finanziaria in magazzino aggiornata per una quantità pari a 2 al costo unitario di 14,00 EUR.
-   2. Entrata fisica in magazzino aggiornata per una quantità pari a 1 al costo unitario di 10,00 EUR.
-   3a. Entrata fisica in magazzino aggiornata per una quantità pari a 1 al costo unitario di 12,00 EUR.
-   3b. Entrata finanziaria in magazzino aggiornata per una quantità pari a 1 al costo unitario di 16,00 EUR.
-   4a. Uscita fisica da magazzino aggiornata per una quantità pari a 1 al costo unitario di 13,50 EUR (costo medio corrente, poiché viene preso in considerazione il valore dell'entrata fisica).
-   4b. Uscita finanziaria da magazzino aggiornata per una quantità pari a 1 al costo unitario di 13,50 EUR (costo medio corrente, poiché viene preso in considerazione il valore dell'entrata fisica).
-   5a. Entrata fisica in magazzino aggiornata per una quantità pari a 1 al costo unitario di 14,00 EUR.
-   5b. Entrata finanziaria in magazzino aggiornata per una quantità pari a 1 al costo unitario di 16,00 EUR.
-   6. Viene eseguita la chiusura inventario. Durante la chiusura dell'inventario, verranno ignorate tutte le operazioni di magazzino aggiornate solo fisicamente. Verrà utilizzato il principio di compensazione riepilogativa poiché è presente solo un'entrata finanziaria. Verrà registrata una rettifica di 1,50 EUR nell'operazione di magazzino in uscita finanziaria alla data di chiusura dell'inventario. Dopo la chiusura dell'inventario, le scorte disponibili saranno una quantità pari a 3 con prezzo di costo medio corrente di 15,00 EUR.
-   7a. Viene creata un'uscita finanziaria "transazione di chiusura inventario media ponderata" per sommare le compensazioni di tutte le entrate finanziarie in magazzino.
-   7b. Viene creata un'entrata finanziaria "transazione di chiusura inventario media ponderata" come contropartita per la transazione 5a.

Nel diagramma riportato di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale media ponderata e del principio di compensazione riepilogativo senza l'opzione Includi valore fisico. 

![Compensazione riepilogativa media ponderata con l'opzione Includi valore fisico](./media/weightedaveragesummarizedsettlementwithincludephysicalvalue.gif) 

**Informazioni sul diagramma**
-   Le operazioni di magazzino sono rappresentate da frecce verticali.
-   Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
-   Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
-   Al di sopra o al di sotto di ciascuna freccia verticale, il valore dell'operazione di magazzino è specificato nel formato Quantity@Unitprice.
-   Un valore dell'operazione di magazzino racchiuso tra parentesi indica che l'operazione è stata registrata fisicamente in magazzino.
-   Un valore dell'operazione di magazzino non racchiuso tra parentesi indica che l'operazione è stata registrata finanziariamente in magazzino.
-   Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
-   Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio 1a. Gli identificatori indicano la successione delle registrazioni relative alle operazioni di magazzino nella sequenza temporale.
-   Le chiusure inventario sono rappresentate da una linea verticale tratteggiata di colore rosso e dall'etichetta Chiusura inventario.
-   Le compensazioni eseguite tramite chiusura inventario sono rappresentate da frecce puntate di colore rosso che uniscono in diagonale un'entrata a un'uscita.
-   Le frecce rosse indicano le transazioni in entrata compensate a fronte della transazione in uscita creata dal sistema.
-   La freccia verde rappresenta la transazione in entrata di contropartita generata dal sistema a fronte della quale viene compensata la transazione in uscita originariamente registrata.

## <a name="weighted-average-with-marking"></a>Media ponderata con contrassegno
Il contrassegno è un processo che consente di collegare, o contrassegnare, una transazione in uscita a una transazione in entrata. Questo processo può essere eseguito prima o dopo la registrazione di una transazione. È possibile utilizzare il contrassegno per essere certi del costo esatto dell'inventario quando viene registrata la transazione o viene eseguita la chiusura dell'inventario. 

Si supponga ad esempio che il reparto Servizio clienti di un'azienda abbia accettato un ordine urgente da parte di un cliente importante. Trattandosi di un'urgenza, sarà necessario pagare un prezzo più elevato per l'articolo in modo da poter soddisfare la richiesta del cliente. Di conseguenza, è necessario accertarsi che il costo dell'articolo di magazzino venga considerato nel margine, ovvero nel costo del venduto (COGS), della fattura relativa a questo ordine cliente. 

Quando l'ordine fornitore viene registrato, l'articolo di magazzino viene ricevuto al costo di 120,00 EUR. Se ad esempio il documento dell'ordine cliente viene contrassegnato nell'ordine fornitore prima della registrazione del documento di trasporto o della fattura, il costo del venduto sarà uguale a 120,00 EUR anziché al costo medio corrente dell'articolo. Se la registrazione del documento di trasporto ordine cliente o della fattura avviene prima del contrassegno, il costo del venduto verrà registrato con il prezzo di costo medio corrente. 

Prima di eseguire la chiusura dell'inventario, è ancora possibile collegare queste due transazioni. 

Quando una transazione in entrata viene collegata a una transazione in uscita tramite contrassegno, il metodo di valutazione selezionato per il gruppo di modelli di articoli dell'articolo verrà ignorato e le transazioni verranno compensate l'una con l'altra. 

Per collegare una transazione in uscita a un'entrata prima che la transazione venga registrata, È possibile effettuare questa operazione da una riga dell'ordine cliente nella pagina Dettagli ordini cliente. Le transazioni di entrata aperte sono visualizzate nella pagina Contrassegno. 

Per collegare una transazione in uscita a un'entrata dopo che la transazione è stata registrata, È possibile abbinare o contrassegnare una transazione in uscita a una transazione in entrata aperta per un articolo inventariato da un giornale di registrazione di rettifica magazzino registrato. 

Nel grafico riportato di seguito sono illustrate le seguenti transazioni:
-   1a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
-   1b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
-   2a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
-   2b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
-   3a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 25,00 EUR.
-   4a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
-   4b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
-   5a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 21,25 EUR (media corrente delle transazioni fisiche e finanziarie aggiornate).
-   5b. Uscita finanziaria da magazzino per una quantità pari a 1 collegata tramite contrassegno all'entrata in magazzino 2b prima della registrazione della transazione. Questa transazione viene registrata con un prezzo di costo di 20,00 EUR.
-   6a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo unitario di 21,25 EUR.
-   7. Viene eseguita la chiusura dell'inventario. Poiché la transazione aggiornata finanziariamente è collegata tramite contrassegno a un'entrata esistente, queste transazioni vengono compensate reciprocamente senza effettuare alcuna rettifica.

Il nuovo prezzo di costo medio corrente riflette la media delle transazioni aggiornate fisicamente e finanziariamente a 27,50 EUR. 

Nel diagramma riportato di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale media ponderata con contrassegno. 

![Media ponderata con contrassegno](./media/weightedaveragewithmarking.gif) 

**Informazioni sul diagramma**
-   Le operazioni di magazzino sono rappresentate da frecce verticali.
-   Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
-   Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
-   Al di sopra o al di sotto di ciascuna freccia verticale, il valore dell'operazione di magazzino è specificato nel formato Quantity@Unitprice.
-   Un valore dell'operazione di magazzino racchiuso tra parentesi indica che l'operazione è stata registrata fisicamente in magazzino.
-   Un valore dell'operazione di magazzino non racchiuso tra parentesi indica che l'operazione è stata registrata finanziariamente in magazzino.
-   Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
-   Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano la successione delle registrazioni relative alle operazioni di magazzino nella sequenza temporale.
-   Le chiusure inventario sono rappresentate da una linea verticale tratteggiata di colore rosso e dall'etichetta Chiusura inventario.
-   Le compensazioni eseguite tramite chiusura inventario sono rappresentate da frecce puntate di colore rosso che uniscono in diagonale un'entrata a un'uscita.






