---
title: Data media ponderata
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 2016-01-07 19 - 58 - 01
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 28991
ms.assetid: 945d5088-a99d-4e54-bc42-d2bd61c61e22
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d05059f1b1da12ec27bd83d43275c82ac6130590
ms.lasthandoff: 03/29/2017


---

# <a name="weighted-average-date"></a>Data media ponderata



La data media ponderata è un modello inventariale basato sul principio di media ponderate. Per tale principio, le uscite da magazzino vengono valutate al valore medio degli articoli ricevuti in magazzino per ogni giorno del periodo di chiusura inventario. Quando si esegue una chiusura inventario tramite la data media ponderata, tutte le entrate giornaliere vengono liquidate a fronte di un'uscita virtuale. Quest'ultima comprende la quantità totale ricevuta e il valore del giorno. Questa uscita virtuale è associata a un'entrata virtuale corrispondente rispetto a cui verrà liquidata. In questo modo a tutte le uscite viene assegnato lo stesso costo medio. L'uscita e l'entrata virtuali possono essere considerate come un trasferimento virtuale, denominato *trasferimento di chiusura inventario media ponderata*. Se nella data in questione o in una data precedente si è verificata una sola entrata, non è necessario valutare la media. Poiché tutte le uscite vengono liquidate da tale entrata, il trasferimento virtuale non verrà creato. Analogamente, in una data in cui si verificano solo uscite non sono presenti entrate da cui valutare la media e il trasferimento non viene creato. Quando si utilizza la data media ponderata, è possibile contrassegnare le transazioni di magazzino in modo da liquidare un'entrata di articoli specifica a fronte di un'uscita specifica. In questo caso, non si utilizza la regola della data media ponderata. In caso di utilizzo del modello inventariale della data media ponderata, è consigliabile una chiusura inventario mensile. Viene utilizzata la seguente formula per calcolare il metodo di determinazione costi media ponderata: Media ponderata = (P*n*\] euro × P2\] + \[Q*n* × P1\] + \[Q2\[Q1 ÷ Ricavi) (Q1 + Q2 +) Q*n* durante la chiusura inventario, il calcolo verrà eseguita ogni giorno con il periodo di chiusura, come illustrato nella figura seguente. ![Modello di calcolo giornaliero della data media ponderata](./media/weightedaveragedatedailycalculationmodel.gif) Le operazioni di magazzino che escono dall'inventario, inclusi gli ordini cliente, i giornali di registrazione magazzino e gli ordini di produzione avranno luogo a un prezzo di costo stimato alla data di registrazione. Tale prezzo di costo stimato è noto anche come prezzo di costo medio corrente. Nella data di chiusura inventario, il sistema analizzare le transazioni di magazzino per i periodi precedenti, i giorni precedenti e per il giorno corrente. Questa analisi viene utilizzata per stabilire quale dei seguenti principi di chiusura utilizzare:

-   Liquidazione diretta
-   Liquidazione riepilogativa

Le liquidazioni sono registrazioni di chiusura inventario che rettificano le uscite in base alla media ponderata corretta, calcolata alla data di chiusura. ** Nota: ** Per ulteriori informazioni sulle liquidazioni, vedere l'articolo della chiusura inventario. Negli esempi riportati di seguito è illustrato l'effetto dell'uso della media ponderata con cinque configurazioni:

-   Compensazione diretta con data media ponderata quando non è utilizzata l'opzione **Includi valore fisico**
-   Liquidazione riepilogativa con data media ponderata quando non è utilizzata l'opzione **Includi valore fisico**
-   Compensazione diretta con data media ponderata quando è utilizzata l'opzione **Includi valore fisico**
-   Liquidazione riepilogativa con data media ponderata quando è utilizzata l'opzione **Includi valore fisico**
-   Data media ponderata quando viene utilizzato il contrassegno

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-isnt-used"></a>Compensazione diretta con data media ponderata quando non è utilizzata l'opzione Includi valore fisico
La versione corrente utilizza lo stesso principio di compensazione diretta utilizzato per la media ponderata nelle versioni precedenti. La compensazione tra entrate e uscite verrà effettuata direttamente dal sistema. Il sistema utilizza questo principio di compensazione diretta per le situazioni specifiche:

-   Nel periodo sono state registrate un'entrata e una o più uscite.
-   Nel periodo sono state registrate solo uscite e l'inventario contiene le scorte di articoli disponibili da una precedente chiusura.

Nello scenario descritto di seguito sono state registrate un'entrata e un'uscita aggiornate finanziariamente. Durante la chiusura inventario, il sistema sistema l'entrata direttamente a fronte dell'uscita senza effettuare alcuna rettifica al prezzo di costo è necessaria per l'uscita. La figura di seguito mostra le transazioni:

-   1a. Entrata fisica in magazzino aggiornata per una quantità pari a 5 al costo unitario di 10,00 EUR.
-   1b. Entrata finanziaria in magazzino aggiornata per una quantità pari a 5 al costo unitario di 10,00 EUR.
-   2a. Uscita fisica da magazzino aggiornata per una quantità pari a 2 al costo unitario di 10,00 EUR.
-   2b. Uscita finanziaria da magazzino aggiornata per una quantità pari a 2 al costo unitario di 10,00 EUR.
-   3. La chiusura dell'inventario viene eseguita utilizzando il metodo di compensazione diretta per compensare l'entrata fisica in magazzino con l'uscita finanziaria dal magazzino.

![Compensazione diretta con data media ponderata senza opzione Includi valore fisico](./media/weightedaveragedatedirectsettlementwithoutincludephysicalvalue.gif) **Chiave per la figura:**

-   Le operazioni di magazzino sono rappresentate da frecce verticali.
-   Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
-   Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
-   Al di sopra o al di sotto di ciascuna freccia verticale, il valore della transazione di magazzino è specificato nel price* di *Unit@*Quantity* del modulo.
-   Se un valore dell'operazione di magazzino racchiuso tra parentesi, l'operazione è stata registrata fisicamente in magazzino.
-   Se un valore dell'operazione di magazzino non è racchiuso tra parentesi, l'operazione è stata registrata finanziariamente in magazzino.
-   Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
-   Each vertical arrow is labeled with a sequential identifier, such as *1a*. Gli identificatori indicano la successione delle registrazioni relative alle operazioni di magazzino nella sequenza temporale.
-   Le chiusure inventario sono rappresentate da una linea tratteggiata verticale di colore rosso e dall'etichetta *Chiusura inventario*.
-   Le liquidazioni eseguite tramite chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-isnt-used"></a>Liquidazione riepilogativa con data media ponderata quando non è utilizzata l'opzione Includi valore fisico
Media ponderata si basa sul principio secondo il quale tutte le entrate in un periodo di chiusura vengono riepilogate in una nuova transazione di trasferimento scorte. Questa transazione è denominata *Chiusura inventario media ponderata*. Tutte le entrate del giorno vengono liquidate a fronte dell'uscita della transazione di trasferimento scorte creata, mentre tutte le uscite del giorno vengono liquidate a fronte dell'entrata della nuova transazione di trasferimento scorte. Se dopo la chiusura dell'inventario le scorte disponibili risultano positive, tali scorte e il valore di inventario vengono riepilogati nella nuova ricevuta di transazione di trasferimento scorte. Se dopo la chiusura dell'inventario le scorte disponibili risultano negative, tali scorte e il valore di inventario corrispondono alla somma delle singole uscite che non sono state completamente liquidate. Nello scenario seguente sono state registrate durante il periodo diverse entrate e uscite aggiornate finanziariamente. Durante la chiusura inventario, il sistema valuta per ogni giorno di ogni giorno deve essere considerato chiudendo. La figura di seguito mostra le transazioni: **Giorno 1:**

-   1a. Entrata fisica in magazzino aggiornata per una quantità pari a 3 al costo unitario di 15,00 EUR.
-   1b. Entrata finanziaria in magazzino aggiornata per una quantità pari a 3 al costo unitario di 15,00 EUR.
-   2a. Uscita fisica da magazzino per una quantità pari a 1 al costo medio corrente di 15,00 EUR.
-   2b. Uscita finanziaria da magazzino per una quantità pari a 1 al costo medio corrente di 15,00 EUR.

Nel sistema verrà utilizzato l'approccio con compensazione diretta per il giorno 1. ** Giorno 2: **

-   3a. Uscita fisica da magazzino per una quantità pari a 1 al costo medio corrente di 15,00 EUR.
-   3b. Uscita finanziaria da magazzino di una quantità pari a 1 al costo medio corrente di EUR 15,00

Nel sistema verrà utilizzato l'approccio con compensazione diretta per il giorno 2. ** Giorno 3: **

-   4a. Uscita fisica da magazzino per una quantità pari a 1 al costo medio corrente di 15,00 EUR.
-   4b. Uscita finanziaria da magazzino di una quantità pari a 1 al costo medio corrente di EUR 15,00
-   5a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 17,00 EUR.
-   5b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 17,00 EUR.

Viene eseguita la chiusura inventario. È necessario utilizzare la compensazione diretta perché sono presenti più entrate che si estendono su diversi giorni.

-   7a. Creazione entrata finanziaria per transazione di chiusura inventario media ponderata per una quantità pari a 2 a 32,00 EUR per riepilogare le liquidazioni di tutte le entrate finanziarie in magazzino alla data corrente che non sono state chiuse.
-   7b. Creazione entrata finanziaria per transazione di chiusura inventario media ponderata come contropartita al punto 7a.

Il sistema genera e registra la transazione di trasferimento scorte riepilogativa. Inoltre, il sistema sistema tutte le entrate del giorno e le scorte disponibili dei giorni precedenti a fronte della transazione in uscita di trasferimento scorte riepilogativa. Tutte le uscite del giorno vengono compensate a fronte della transazione in entrata per il trasferimento scorte riepilogativa. Il prezzo di costo medio ponderato viene calcolato con valore pari a 16,00 EUR. All'uscita verrà apportata una rettifica pari a 1,00 EUR in base al costo medio ponderato. Il nuovo prezzo di costo medio corrente è 16,00 EUR. Nella figura riportata di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale media ponderata e del principio di compensazione riepilogativo senza l'opzione **Includi valore fisico**. ![Liquidazione riepilogativa con data media ponderata senza opzione Includi valore fisico](./media/weightedaveragedatesummarizedsettlementwithoutincludephysicalvalue.gif) **Chiave per la figura**

-   Le operazioni di magazzino sono rappresentate da frecce verticali.
-   Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
-   Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
-   Al di sopra o al di sotto di ciascuna freccia verticale, il valore della transazione di magazzino è specificato nel price* di *Unit@*Quantity* del modulo.
-   Se un valore dell'operazione di magazzino racchiuso tra parentesi, l'operazione è stata registrata fisicamente in magazzino.
-   Se un valore dell'operazione di magazzino non è racchiuso tra parentesi, l'operazione è stata registrata finanziariamente in magazzino.
-   Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
-   Each vertical arrow is labeled with a sequential identifier, such as *1a*. Gli identificatori indicano la successione delle registrazioni relative alle operazioni di magazzino nella sequenza temporale.
-   Le chiusure inventario sono rappresentate da una linea tratteggiata verticale di colore rosso e dall'etichetta *Chiusura inventario*.
-   Le liquidazioni eseguite tramite chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.
-   Le frecce piene diagonali rosse indicano le transazioni in entrata compensate a fronte della transazione in uscita creata dal sistema.
-   La freccia piena diagonale verde rappresenta la transazione in entrata di contropartita generata dal sistema a fronte della quale viene compensata la transazione in uscita originariamente registrata.

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-is-used"></a>Compensazione diretta con data media ponderata quando è utilizzata l'opzione Includi valore fisico
La versione corrente utilizza lo stesso principio di compensazione diretta per la data media ponderata utilizzata nelle versioni precedenti. La compensazione tra entrate e uscite verrà effettuata direttamente dal sistema. Il sistema utilizza questo principio di compensazione diretta per le situazioni specifiche:

-   Nel periodo sono state registrate un'entrata e una o più uscite.
-   Nel periodo sono state registrate solo uscite e l'inventario contiene le scorte disponibili da una precedente chiusura.

Se si seleziona ** Includi valore fisico ** la casella di controllo per un articolo ** gruppo di modelli di articoli ** nella pagina, verrà utilizzato le entrate aggiornate fisicamente durante il calcolo del prezzo di costo stimato, o della media corrente. Le uscite vengono registrate in base a tale prezzo di costo stimato durante il periodo. Durante la chiusura dell'inventario, solo le entrate aggiornate finanziariamente verranno considerate nel calcolo della media ponderata.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-is-used"></a>Liquidazione riepilogativa con data media ponderata quando è utilizzata l'opzione Includi valore fisico
Se si seleziona ** Includi valore fisico ** la casella di controllo per un articolo ** gruppo di modelli di articoli ** nella pagina, verrà utilizzato le entrate aggiornate fisicamente durante il calcolo del prezzo di costo stimato, o della media corrente. Le uscite vengono registrate in base a tale prezzo di costo stimato durante il periodo. Durante la chiusura dell'inventario, solo le entrate aggiornate finanziariamente verranno considerate nel calcolo della media ponderata. La liquidazione media ponderata si basa sul principio secondo il quale tutte le entrate comprese in un periodo di chiusura vengono riepilogate in una nuova transazione di trasferimento scorte denominata *chiusura inventario media ponderata*. Tutte le entrate del giorno vengono liquidate a fronte dell'uscita della transazione di trasferimento scorte creata, mentre tutte le uscite del giorno vengono liquidate a fronte dell'entrata della nuova transazione di trasferimento scorte. Se dopo la chiusura dell'inventario le scorte disponibili risultano positive, tali scorte e il valore di inventario vengono riepilogati nella nuova transazione di trasferimento scorte (entrata). Se dopo la chiusura dell'inventario le scorte disponibili risultano negative, tali scorte e il valore di inventario corrispondono alla somma delle singole uscite che non sono state completamente liquidate.

## <a name="weighted-average-date-when-marking-is-used"></a>Data media ponderata quando viene utilizzato il contrassegno
Il contrassegno è un processo che consente di collegare una transazione in uscita a una transazione in entrata. Questo processo può essere eseguito prima o dopo la registrazione di una transazione. È possibile utilizzare il contrassegno per essere certi del costo esatto dell'inventario quando viene registrata la transazione o viene eseguita la chiusura dell'inventario. Si supponga ad esempio che il reparto Servizio clienti di un'azienda abbia accettato un ordine urgente da parte di un cliente importante. Trattandosi di un'urgenza, sarà necessario pagare un prezzo più elevato per l'articolo in modo da soddisfare la richiesta del cliente. Di conseguenza, è necessario accertarsi che il costo dell'articolo di magazzino venga considerato nel margine, ovvero nel costo del venduto (COGS), della fattura relativa a questo ordine cliente. Quando l'ordine fornitore viene registrato, l'articolo di magazzino viene ricevuto al costo di 120,00 EUR. Il documento dell'ordine cliente viene contrassegnato nell'ordine fornitore prima della registrazione del documento di trasporto o della fattura, il valore COGS sarà uguale a 120,00 EUR anziché al costo medio corrente dell'articolo. Se la registrazione del documento di trasporto ordine cliente o della fattura avviene prima del contrassegno, il costo del venduto verrà registrato con il prezzo di costo medio corrente. Prima di eseguire la chiusura dell'inventario, è ancora possibile collegare queste due transazioni. Quando una transazione in entrata viene contrassegnata come corrispondente a una transazione in uscita, il metodo di valutazione definito nel gruppo di modelli dell'articolo viene ignorato. In tal caso, il sistema sistema le transazioni l'una con. Per collegare una transazione in uscita a un'entrata prima che la transazione venga registrata, È possibile effettuare questa operazione da una riga dell'ordine vendita nella pagina **Dettagli ordini cliente**. È possibile visualizzare le transazioni di entrata aperte nella pagina **Contrassegno**. Per collegare una transazione in uscita a un'entrata dopo che la transazione è stata registrata, è possibile abbinare o contrassegnare una transazione in uscita a una transazione in entrata aperta per un articolo inventariato da un giornale di registrazione di rettifica magazzino registrato. La figura di seguito mostra le transazioni:

-   1a. Entrata fisica in magazzino per una quantità pari a 1 al prezzo di costo unitario di 10,00 EUR.
-   1b. Entrata finanziaria in magazzino per una quantità pari a 1 al prezzo di costo unitario di 10,00 EUR.
-   2a. Entrata fisica in magazzino per una quantità pari a 1 al prezzo di costo unitario di 20,00 EUR.
-   2b. Entrata finanziaria in magazzino per una quantità pari a 1 al prezzo di costo unitario di 20,00 EUR.
-   3a. Entrata fisica in magazzino per una quantità pari a 1 al prezzo di costo unitario di 25,00 EUR.
-   4a. Entrata fisica in magazzino per una quantità pari a 1 al prezzo di costo unitario di 30,00 EUR.
-   4b. Entrata finanziaria in magazzino per una quantità pari a 1 al prezzo di costo unitario di 30,00 EUR.
-   5a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 21,25 EUR (media corrente delle transazioni fisiche e finanziarie aggiornate).
-   5b. Uscita finanziaria da magazzino per una quantità pari a 1 contrassegnata all'entrata in magazzino 2b prima della registrazione della transazione. Questa transazione viene registrata a un prezzo di costo di 20,00 EUR.
-   6a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 21,25 EUR.
-   7. Viene eseguita la chiusura inventario. Poiché la transazione aggiornata finanziariamente è contrassegnata a un'entrata esistente, queste transazioni vengono liquidate reciprocamente senza effettuare alcuna rettifica.

Il nuovo prezzo di costo medio corrente riflette la media delle transazioni aggiornate fisicamente e finanziariamente a 27,50 EUR. Nella figura riportata di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale data media ponderata con contrassegno. ![Data media ponderata con contrassegno](./media/weightedaveragedatewithmarking.gif) **Chiave per la figura:**

-   Le operazioni di magazzino sono rappresentate da frecce verticali.
-   Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
-   Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
-   Al di sopra o al di sotto di ciascuna freccia verticale, il valore della transazione di magazzino è specificato nel price* di *Unit@*Quantity* del modulo.
-   Se un valore dell'operazione di magazzino racchiuso tra parentesi, l'operazione è stata registrata fisicamente in magazzino.
-   Se un valore dell'operazione di magazzino non è racchiuso tra parentesi, l'operazione è stata registrata finanziariamente in magazzino.
-   Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
-   Each vertical arrow is labeled with a sequential identifier, such as *1a*. Gli identificatori indicano la successione delle registrazioni relative alle operazioni di magazzino nella sequenza temporale.
-   Le chiusure inventario sono rappresentate da una linea tratteggiata verticale di colore rosso e dall'etichetta *Chiusura inventario*.
-   Le liquidazioni eseguite tramite chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.



