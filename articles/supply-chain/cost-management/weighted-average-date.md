---
title: Data media ponderata con Includi valore fisico e contrassegno
description: La data media ponderata costituisce un modello inventariale basato sul principio della media ponderata, in base al quale le uscite da magazzino vengono valutate al valore medio degli articoli ricevuti in magazzino per ogni giorno distinto nel periodo di chiusura inventario.
author: AndersGirke
ms.date: 03/04/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28991
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3cf2206863d891eceb9c65ff879da3f9f72032b1
ms.sourcegitcommit: fcded93fc6c27768a24a3d3dc5cc35e1b4eff22b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2022
ms.locfileid: "8392003"
---
# <a name="weighted-average-date-with-include-physical-value-and-marking"></a>Data media ponderata con Includi valore fisico e contrassegno

[!include [banner](../includes/banner.md)]

*Data media ponderata* è un modello di inventario basato su una media calcolata moltiplicando ciascun componente (transazione articolo) per un fattore (prezzo di costo) che riflette la sua importanza (quantità) ciascun giorno del periodo. In altre parole, questo modello assegna il costo di transazioni relative al problema in base al valore medio di tutto l'inventario ricevuto ciascun giorno, più qualsiasi inventario disponibile per il giorno precedente.

Quando si esegue una chiusura dell'inventario utilizzando il modello dell'inventario della data media, è possibile creare una liquidazione in due modi. In genere, tutte le entrate vengono liquidate a fronte di un'uscita virtuale, che comprende la quantità e il valore totale ricevuti. A questa uscita virtuale corrisponde un'entrata virtuale dalla quale vengono compensate le uscite. In questo modo, a tutte le uscite viene assegnato lo stesso costo medio ogni giorno. L'uscita e la ricezione virtuali possono essere considerate come un trasferimento virtuale. Il trasferimento virtuale viene denominato *trasferimento di chiusura inventario media ponderata*. Pertanto, questo metodo di liquidazione è chiamato *compensazione riepilogativa media ponderata*. Se è presente una sola entrata, tutte le uscite possono essere compensate da questa entrata senza che venga creato il trasferimento virtuale. Questo metodo di liquidazione è denominato *liquidazione diretta*. Qualsiasi inventario disponibile dopo l'esecuzione della chiusura dell'inventario viene valutato in base alla media ponderata dell'ultimo giorno del periodo precedente e incluso nel calcolo della data della media ponderata nel periodo successivo.

Puoi ignorare il principio della data della media ponderata contrassegnando le transazioni di magazzino in modo da liquidare un'entrata di articoli specifica a fronte di un'uscita specifica. È necessaria una chiusura periodica dell'inventario quando si utilizza il modello di inventario della data della media ponderata per creare liquidazioni e adeguare il valore delle emissioni secondo il principio data della media ponderata. Fino a quando non esegui la chiusura dell'inventario, le transazioni in uscita vengono valutate alla media corrente al momento dell'aggiornamento fisico e finanziario. A meno che tu non utilizzi la marcatura, la media corrente viene calcolata quando viene eseguito l'aggiornamento fisico o finanziario.

Il metodo di determinazione costi magazzino con data della media ponderata viene calcolato usando la seguente formula ogni giorno:

*Costo* = \[(*Q*<sub>*b*</sub> × *P*<sub>*b*</sub>) + &#x2211;<sub>*n*</sub>(*Q*<sub>*n*</sub> × *P*<sub>*n*</sub>)\] ÷ (*Q*<sub>*b*</sub> + &#x2211;<sub>*n*</sub>*Q*<sub>*n*</sub>)

- *Q* = quantità della transazione
- *P* = prezzo della transazione

In altre parole, il costo medio ponderato equivale alla quantità iniziale per il prezzo iniziale, più la somma di ciascuna volta di quantità ricevuta per il prezzo di ricezione, tutto diviso per la quantità iniziale più la somma delle quantità delle entrate.

Durante la chiusura inventario, il calcolo verrà eseguito ogni giorno per la durata del periodo di chiusura.

> [!NOTE]
> Per ulteriori informazioni sulle dichiarazioni, vedi [Chiusura inventario](inventory-close.md).

Negli esempi riportati di seguito è illustrato l'effetto dell'uso della data della media ponderata con cinque configurazioni:

- Compensazione diretta con data media ponderata quando non è utilizzata l'opzione **Includi valore fisico**
- Liquidazione riepilogativa con data media ponderata quando non è utilizzata l'opzione **Includi valore fisico**
- Compensazione diretta con data media ponderata quando è utilizzata l'opzione **Includi valore fisico**
- Liquidazione riepilogativa con data media ponderata quando è utilizzata l'opzione **Includi valore fisico**
- Data media ponderata quando viene utilizzato il contrassegno

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-isnt-used"></a>Compensazione diretta con data media ponderata quando non è utilizzata l'opzione Includi valore fisico

Il principio della liquidazione diretta crea liquidazioni direttamente tra le entrate e le uscite senza creare ulteriori transazioni di magazzino. Questo principio di compensazione diretta viene utilizzato nelle situazioni seguenti:

- Nel periodo sono state registrate un'entrata e una o più uscite.
- Nel periodo sono state registrate solo uscite e l'inventario contiene le scorte di articoli disponibili da una precedente chiusura.

In questo esempio, la casella di controllo **Includi valore fisico** è deselezionata nella pagina **Gruppo di modelli di articoli** per il prodotto rilasciato. La figura di seguito mostra le transazioni:

**Giorno 1:**

- 1a. Entrata fisica in magazzino per una quantità pari a 10 al costo unitario di 10,00 EUR.
- 1b. Entrata finanziaria in magazzino per una quantità pari a 10 al costo unitario di 10,00 EUR.
- 2a. Entrata fisica in magazzino per una quantità pari a 10 al costo unitario di 20,00 EUR.
- 3a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 10,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 3b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo di 10,00 EUR (media corrente delle transazioni registrate finanziariamente).

**Giorno 2:**

- 4a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 25,00 EUR.
- 5a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 5b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 6a. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo di 20,00 EUR (media corrente delle transazioni registrate finanziariamente).

**Giorno 3:**

- 7\. Viene eseguita la chiusura inventario. Sulla base del metodo della data della media ponderata, il sistema utilizza il metodo della compensazione diretta per il 30 dicembre (30/12) poiché nel periodo viene aggiornato finanziariamente un solo incasso in data 30/12. In questo esempio, viene creata una liquidazione tra le transazioni 1b e 3b. Una rettifica di 10 USD viene effettuata per portare il valore della transazione 3b fino a 20. Nessuna rettifica o dichiarazione viene effettuata in data 31 dicembre (31/12) perché non ci sono problemi di aggiornamento finanziario in data 31/12.

Nel diagramma riportato di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale media ponderata e del principio di compensazione diretta senza l'opzione **Includi valore fisico**.

![Compensazione diretta con data media ponderata senza opzione Includi valore fisico.](media/weighted-average-date-direct-settlement-without-include-physical-value.png)

**Informazioni sul diagramma:**

- Le operazioni di magazzino sono rappresentate da frecce verticali.
- Le transazioni fisiche sono rappresentate da frecce grigio chiaro più corte.
- Le transazioni finanziarie sono rappresentate da frecce nere più lunghe.
- Le entrate in magazzino sono rappresentate da frecce verticali al di sopra dell'asse.
- Le uscite da magazzino sono rappresentate da frecce verticali al di sotto dell'asse.
- Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
- Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
- Le date sono separate da linee verticali nere. Le date sono annotate in fondo al diagramma.
- Le chiusure inventario sono rappresentate da linee verticali tratteggiate di colore rosso.
- Le liquidazioni eseguite tramite chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-isnt-used"></a>Liquidazione riepilogativa con data media ponderata quando non è utilizzata l'opzione Includi valore fisico

Quando in un periodo ci sono più entrate, la data della media ponderata utilizza il principio di compensazione riepilogato secondo il quale tutte le entrate in un singolo giorno vengono riepilogate in una transazione denominata *chiusura inventario media ponderata*. Tutte le entrate del giorno verranno compensate a fronte dell'uscita della transazione scorte creata, mentre tutte le uscite del giorno verranno compensate a fronte dell'entrata della nuova transazione di scorte. Se dopo la chiusura dell'inventario rimane un valore di scorte disponibili, tale valore di scorte disponibili viene incluso nella transazione in entrata delle transazioni di chiusura inventario con media ponderata.

La figura di seguito mostra le transazioni:

**Giorno 1:**

- 1a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
- 1b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
- 2a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
- 2b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 22,00 EUR.
- 3a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 16,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 3b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo di 16,00 EUR (media corrente delle transazioni registrate finanziariamente).

**Giorno 2:**

- 4a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 25,00 EUR.
- 5a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 5b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 6a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 23,00 EUR (media corrente delle transazioni registrate finanziariamente).

**Giorno 3:**

- 7\. Viene eseguita la chiusura inventario.
- 7a. Viene creata un'uscita finanziaria transazione di chiusura inventario media ponderata per sommare le compensazioni di tutte le entrate finanziarie in magazzino.

    - La transazione 1b è compensata per una quantità pari a 1 con un importo regolato di 10 USD.
    - La transazione 2b è compensata per una quantità pari a 1 con un importo regolato di 22 USD.
    - La transazione 7a è creata per una quantità pari a 2 con un importo regolato di 32 USD. Questa transazione compensa la somma delle due transazioni di entrata aggiornate finanziariamente nel periodo.

- 7b. Creazione entrata finanziaria per transazione di chiusura inventario media ponderata come contropartita per le uscite registrate finanziariamente.

    - La transazione 3b è compensata per una quantità pari a 1 con un importo regolato di 16 USD. Questa transazione non viene rettificata perché è la media ponderata delle transazioni registrate finanziariamente in data 1 dicembre (1/12).
    - La transazione 7b viene creata per una quantità di 2 con un importo finanziario di 32 USD e un importo regolato di 16 USD per l'offset della transazione 3b. Questa transazione compensa la somma di una transazione di uscita aggiornata finanziariamente nel periodo. La transazione rimane aperta perché ne esiste ancora una.

Nella figura riportata di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale media ponderata e del principio di compensazione riepilogativo senza l'opzione **Includi valore fisico**.

![Liquidazione riepilogativa con data media ponderata senza opzione Includi valore fisico.](media/weighted-average-date-summarized-settlement-without-include-physical-value.png)

**Informazioni sul diagramma:**

- Le operazioni di magazzino sono rappresentate da frecce verticali.
- Le transazioni fisiche sono rappresentate da frecce grigio chiaro più corte.
- Le transazioni finanziarie sono rappresentate da frecce nere più lunghe.
- Le entrate in magazzino sono rappresentate da frecce verticali al di sopra dell'asse.
- Le uscite da magazzino sono rappresentate da frecce verticali al di sotto dell'asse.
- Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
- Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
- Le date sono separate da linee verticali nere. Le date sono annotate in fondo al diagramma.
- Le chiusure inventario sono rappresentate da linee verticali tratteggiate di colore rosso.
- Le liquidazioni eseguite tramite chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-is-used"></a>Compensazione diretta con data media ponderata quando è utilizzata l'opzione Includi valore fisico

Nella versione corrente del prodotto, l'opzione **Includi valore fisico** con il modello inventariale della data della media ponderata è diverso rispetto alle versioni precedenti. Quando selezioni la casella di controllo **Includi valore fisico** per un articolo nella pagina **Gruppo di modelli di articoli**, il sistema utilizzerà le entrate aggiornate fisicamente quando calcola il prezzo di costo stimato o la media corrente. Le uscite verranno registrate in base a tale prezzo di costo stimato durante il periodo. Durante la chiusura dell'inventario, solo le entrate aggiornate finanziariamente verranno considerate nel calcolo della media ponderata.

La figura di seguito mostra le transazioni:

**Giorno 1:**

- 1a. Entrata fisica in magazzino per una quantità pari a 10 al costo unitario di 10,00 EUR.
- 1b. Entrata finanziaria in magazzino per una quantità pari a 10 al costo unitario di 10,00 EUR.
- 2a. Entrata fisica in magazzino per una quantità pari a 10 al costo unitario di 20,00 EUR.
- 3a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 15,00 EUR (media corrente delle transazioni fisiche e finanziarie registrate).
- 3b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo di 15,00 EUR (media corrente delle transazioni fisiche e finanziarie registrate).

**Giorno 2:**

- 4a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 25,00 EUR.
- 5a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 5b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 6a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 21,25 EUR (media corrente delle transazioni fisiche e finanziarie registrate).

**Giorno 3:**

- 7\. Viene eseguita la chiusura inventario. Sulla base del metodo della data della media ponderata, il sistema utilizza il metodo della compensazione diretta per il 30 dicembre (30/12) poiché nel periodo viene aggiornato finanziariamente un solo incasso in data 30/12. In questo esempio, viene creata una liquidazione tra le transazioni 1b e 3b. Non viene effettuata nessuna rettifica al problema in data 30/12. Inoltre, nessuna rettifica o dichiarazione viene effettuata in data 31 dicembre (31/12) perché non ci sono problemi di aggiornamento finanziario in data 31/12.

Nel diagramma riportato di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale media ponderata e del principio di compensazione diretta con l'opzione **Includi valore fisico**.

![Compensazione diretta media ponderata con l'opzione Includi valore fisico.](media/weighted-average-date-direct-settlement-with-include-physical-value.png)

**Informazioni sul diagramma:**

- Le operazioni di magazzino sono rappresentate da frecce verticali.
- Le transazioni fisiche sono rappresentate da frecce grigio chiaro più corte.
- Le transazioni finanziarie sono rappresentate da frecce nere più lunghe.
- Le entrate in magazzino sono rappresentate da frecce verticali al di sopra dell'asse.
- Le uscite da magazzino sono rappresentate da frecce verticali al di sotto dell'asse.
- Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
- Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
- Le date sono separate da linee verticali nere. Le date sono annotate in fondo al diagramma.
- Le chiusure inventario sono rappresentate da linee verticali tratteggiate di colore rosso.
- Le liquidazioni eseguite tramite chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-is-used"></a>Liquidazione riepilogativa con data media ponderata quando è utilizzata l'opzione Includi valore fisico

Nella versione corrente del prodotto, l'opzione **Includi valore fisico** con la media ponderata è diversa rispetto alle versioni precedenti. Quando selezioni la casella di controllo **Includi valore fisico** per un articolo nella pagina **Gruppo di modelli di articoli**, il sistema utilizzerà le entrate aggiornate fisicamente quando calcola il prezzo di costo o la media corrente. Le uscite verranno registrate in base a tale prezzo di costo stimato durante il periodo. Durante la chiusura dell'inventario, solo le entrate aggiornate finanziariamente verranno considerate nel calcolo della media ponderata. Quando si utilizza il modello inventariale media ponderata, si consiglia di eseguire una chiusura inventario ogni mese. In questo esempio di compensazione riepilogativa di data di media ponderata il modello inventariale è contrassegnato in modo da includere il valore fisico.

La figura di seguito mostra le transazioni:

**Giorno 1:**

- 1a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
- 1b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
- 2a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
- 2b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 22,00 EUR.
- 3a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 16,00 EUR (media corrente delle transazioni fisiche e finanziarie registrate).
- 3b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo di 16,00 EUR (media corrente delle transazioni fisiche e finanziarie registrate).

**Giorno 2:**

- 4a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 25,00 EUR.
- 5a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 5b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 6a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 23,67 EUR (media corrente delle transazioni fisiche e finanziarie registrate).

**Giorno 3:**

- 7\. Viene eseguita la chiusura inventario.
- 7a. Viene creata un'uscita finanziaria transazione di chiusura inventario media ponderata per sommare le compensazioni di tutte le entrate finanziarie in magazzino.

    - La transazione 1b è compensata per una quantità pari a 1 con un importo regolato di 10 USD.
    - La transazione 2b è compensata per una quantità pari a 1 con un importo regolato di 22 USD.
    - La transazione 7a è creata per una quantità pari a 2 con un importo regolato di 32 USD. Questa transazione compensa la somma delle due transazioni di entrata aggiornate finanziariamente nel periodo.

- 7b. Creazione entrata finanziaria per transazione di chiusura inventario media ponderata come contropartita per le uscite registrate finanziariamente.

    - La transazione 3b è compensata per una quantità pari a 1 con un importo regolato di 16 USD. Questa transazione non viene rettificata perché è la media ponderata delle transazioni registrate finanziariamente in data 1 dicembre (1/12).
    - La transazione 7b viene creata per una quantità di 2 con un importo finanziario di 32 USD e un importo regolato di 16 USD per l'offset della transazione 3b. Questa transazione compensa la somma di una transazione di uscita aggiornata finanziariamente nel periodo. La transazione rimane aperta perché ne esiste ancora una.

Nel diagramma riportato di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale media ponderata e del principio di compensazione riepilogata senza l'opzione **Includi valore fisico**.

![Compensazione riepilogata media ponderata con l'opzione Includi valore fisico.](media/weighted-average-date-summarized-settlement-with-include-physical-value.png)

**Informazioni sul diagramma:**

- Le operazioni di magazzino sono rappresentate da frecce verticali.
- Le transazioni fisiche sono rappresentate da frecce grigio chiaro più corte.
- Le transazioni finanziarie sono rappresentate da frecce nere più lunghe.
- Le entrate in magazzino sono rappresentate da frecce verticali al di sopra dell'asse.
- Le uscite da magazzino sono rappresentate da frecce verticali al di sotto dell'asse.
- Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
- Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
- Le date sono separate da linee verticali nere. Le date sono annotate in fondo al diagramma.
- Le chiusure inventario sono rappresentate da linee verticali tratteggiate di colore rosso.
- Le liquidazioni eseguite tramite chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

## <a name="weighted-average-date-when-marking-is-used"></a>Data media ponderata quando viene utilizzato il contrassegno

Il contrassegno è un processo che consente di collegare, o contrassegnare, una transazione in uscita a una transazione in entrata. Questo processo può essere eseguito prima o dopo la registrazione di una transazione. È possibile utilizzare il contrassegno per essere certi del costo esatto dell'inventario quando viene registrata la transazione o quando viene eseguita la chiusura dell'inventario.

Si supponga ad esempio che il reparto Servizio clienti di un'azienda abbia accettato un ordine urgente da parte di un cliente importante. Trattandosi di un'urgenza, sarà necessario pagare un prezzo più elevato per l'articolo in modo da poter soddisfare la richiesta del cliente. È necessario accertarsi che il costo dell'articolo di magazzino venga considerato nel margine, ovvero nel costo del venduto (COGS), della fattura relativa a questo ordine cliente.

Quando l'ordine fornitore viene registrato, l'articolo di magazzino viene ricevuto al costo di 120,00 EUR. Se il documento dell'ordine cliente viene contrassegnato nell'ordine fornitore prima della registrazione del documento di trasporto o della fattura, il costo del venduto sarà uguale a 120,00 EUR anziché al costo medio corrente dell'articolo. Se la registrazione del documento di trasporto ordine cliente o della fattura avviene prima del contrassegno, il costo del venduto verrà registrato con il prezzo di costo medio corrente.

Prima di eseguire la chiusura dell'inventario, è ancora possibile collegare queste due transazioni.

Se una transazione in entrata viene contrassegnata su una transazione in uscita, il metodo di valutazione selezionato per l'articolo nel gruppo di modelli inventariali dell'articolo verrà ignorato e il sistema compensa le transazioni l'una con l'altra.

Per collegare una transazione in uscita a un'entrata prima che la transazione venga registrata, È possibile effettuare questa operazione contrassegnando una riga dell'ordine vendita nella pagina **Dettagli ordini cliente**. Le transazioni di entrata aperte sono mostrate nella pagina **Contrassegno**.

Per collegare una transazione in uscita a un'entrata dopo che la transazione è stata registrata, è possibile abbinare o contrassegnare una transazione in uscita a una transazione in entrata aperta per un articolo inventariato da un giornale di registrazione di rettifica magazzino registrato.

La figura di seguito mostra le transazioni:

**Giorno 1:**

- 1a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
- 1b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
- 2a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
- 2b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 22,00 EUR.
- 3a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 16,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 3b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo di 16,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 3c. L'emissione finanziaria di inventario per la transazione 3b è contrassegnata per l'emissione finanziaria di inventario per la transazione 2b.

**Giorno 2:**

- 4a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 25,00 EUR.
- 5a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 5b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 6a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 23,00 EUR (media corrente delle transazioni registrate finanziariamente).

**Giorno 3:**

- 7\. Viene eseguita la chiusura inventario. Sulla base del principio del contrassegno che utilizza il metodo della media ponderata, le transazioni contrassegnate sono compensate l'una contro l'altra. In questo esempio, la transazione 3b viene liquidata rispetto ala transazione 2b e una rettifica per 6 USD viene inviata alla transazione 3b per portare il valore a 22 USD. In questo esempio, non vengono effettuate liquidazioni aggiuntive, poiché la chiusura crea liquidazioni solo per transazioni aggiornate finanziariamente.

Nella figura riportata di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale data media ponderata con contrassegno.

![Media ponderata con contrassegno.](media/weighted-average-date-with-marking.png)

**Informazioni sul diagramma:**

- Le operazioni di magazzino sono rappresentate da frecce verticali.
- Le transazioni fisiche sono rappresentate da frecce grigio chiaro più corte.
- Le transazioni finanziarie sono rappresentate da frecce nere più lunghe.
- Le entrate in magazzino sono rappresentate da frecce verticali al di sopra dell'asse.
- Le uscite da magazzino sono rappresentate da frecce verticali al di sotto dell'asse.
- Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
- Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
- Le date sono separate da linee verticali nere. Le date sono annotate in fondo al diagramma.
- Le chiusure inventario sono rappresentate da linee verticali tratteggiate di colore rosso.
- Le liquidazioni eseguite tramite chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
