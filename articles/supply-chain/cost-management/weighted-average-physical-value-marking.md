---
title: Media ponderata con valore fisico e contrassegno
description: Media ponderata è un modello inventariale basato sul principio della media ponderata, secondo il quale le uscite dal magazzino vengono valutate in base al valore medio degli articoli ricevuti in magazzino durante il periodo di chiusura inventario, più le eventuali scorte disponibili del periodo precedente.
author: JennySong-SH
ms.date: 02/21/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 65501
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41c80dcdc08432bb68478827c8763735e644aa4a
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675265"
---
# <a name="weighted-average-with-physical-value-and-marking"></a>Media ponderata con valore fisico e contrassegno

[!include [banner](../includes/banner.md)]

La media ponderata è un modello di inventario basato su una media che risulta dalla moltiplicazione di ogni componente (transazione articolo) per un fattore (prezzo di costo) che riflette la sua importanza (quantità). Un altro modo per dirlo è che la media ponderata è un modello di inventario che assegna il costo delle transazioni di emissione in base al valore medio di tutto l'inventario ricevuto durante il periodo, più qualsiasi inventario disponibile del periodo precedente.

Quando si esegue una chiusura dell'inventario utilizzando il modello dell'inventario della media ponderata, è possibile creare una liquidazione in due modi. In genere, tutte le entrate vengono liquidate a fronte di un'uscita virtuale, che comprende la quantità e il valore totale ricevuti. A questa uscita virtuale corrisponde un'entrata virtuale dalla quale vengono compensate le uscite. In questo modo, a tutte le uscite viene assegnato lo stesso costo medio. L'uscita e l'entrata virtuali possono essere considerate come un trasferimento virtuale, denominato *trasferimento di chiusura inventario media ponderata*. Questo metodo di liquidazione è chiamato *compensazione riepilogativa media ponderata*. Se è presente una sola entrata, tutte le uscite possono essere compensate da questa entrata senza che venga creato il trasferimento virtuale. Questo metodo di liquidazione è denominato *liquidazione diretta*. Qualsiasi inventario disponibile dopo l'esecuzione della chiusura dell'inventario viene valutato in base alla media ponderata del periodo precedente e incluso nel calcolo della media ponderata nel periodo successivo.

Puoi ignorare il principio della media ponderata contrassegnando le transazioni di magazzino in modo da liquidare un'entrata di articoli specifica a fronte di un'uscita specifica. È necessaria una chiusura periodica dell'inventario quando si utilizza il modello di inventario della media ponderata per creare liquidazioni e adeguare il valore delle emissioni secondo il principio della media ponderata. Fino a quando non esegui il processo di chiusura dell'inventario, le transazioni in uscita vengono valutate alla media corrente al momento dell'aggiornamento fisico e finanziario. A meno che tu non utilizzi la marcatura, la media corrente viene calcolata quando viene eseguito l'aggiornamento fisico o finanziario.

Il metodo di determinazione costi magazzino con media ponderata viene calcolato con la seguente formula:

- Media ponderata = (\[Q1 × P1\] + \[Q2 × P2\] + \[Q *n* × P *n*\]) ÷ (Q1 + Q2 + Q *n*)

Q = quantità della transazione  
P = prezzo della transazione

Le liquidazioni sono registrazioni di chiusura inventario che rettificano le uscite in base alla media ponderata corretta, calcolata alla data di chiusura. Negli esempi riportati di seguito è illustrato l'effetto dell'uso della media ponderata con cinque diverse configurazioni:

- Compensazione diretta media ponderata senza l'opzione **Includi valore fisico**
- Compensazione riepilogativa media ponderata senza l'opzione **Includi valore fisico**
- Compensazione diretta media ponderata con l'opzione **Includi valore fisico**
- Compensazione riepilogativa media ponderata con l'opzione **Includi valore fisico**
- Media ponderata con contrassegno

## <a name="weighted-average-direct-settlement-without-include-physical-value"></a>Compensazione diretta media ponderata senza l'opzione Includi valore fisico

Il principio della liquidazione diretta crea liquidazioni direttamente tra le entrate e le uscite senza creare ulteriori transazioni di magazzino. Questo principio di compensazione diretta viene utilizzato nelle situazioni seguenti:

- Nel periodo sono state registrate un'entrata e una o più uscite.
- Nel periodo sono state registrate solo uscite e l'inventario contiene le scorte di articoli disponibili da una precedente chiusura.

In questo esempio, la casella di controllo **Includi valore fisico** è deselezionata nel **gruppo di modelli di articoli** per il prodotto rilasciato. La figura di seguito mostra le transazioni:

- 1a. Entrata fisica in magazzino per una quantità pari a 10 al costo unitario di 10,00 EUR.
- 1b. Entrata finanziaria in magazzino per una quantità pari a 10 al costo unitario di 10,00 EUR.
- 2a. Entrata fisica in magazzino per una quantità pari a 10 al costo unitario di 20,00 EUR.
- 3a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 10,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 3b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo di 10,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 4a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 10,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 4b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo di 10,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 5a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 10,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 6\. Viene eseguita la chiusura inventario. Sulla base del metodo della media ponderata, il sistema utilizza il metodo della compensazione diretta poiché nel periodo viene aggiornato finanziariamente un solo incasso. In questo esempio, viene creata una compensazione tra 1b e 3b e un'altra tra 1b e 4b. Non viene effettuato alcun aggiustamento perché la media corrente è la stessa della media ponderata.

Nel diagramma riportato di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale media ponderata e del principio di compensazione diretta senza l'opzione **Includi valore fisico**.

![Compensazione diretta media ponderata senza l'opzione Includi valore fisico.](media/weighted-average-direct-settlement-without-include-physical-value.png)

**Informazioni sul diagramma**

- Le operazioni di magazzino sono rappresentate da frecce verticali.
- Le transazioni fisiche sono rappresentate da frecce grigio chiaro più corte.
- Le transazioni finanziarie sono rappresentate da frecce nere più lunghe.
- Le entrate in magazzino sono rappresentate da frecce verticali al di sopra dell'asse.
- Le uscite da magazzino sono rappresentate da frecce verticali al di sotto dell'asse.
- Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
- Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
- Ciascuna data nel diagramma è separata da una sottile linea verticale nera. La data è annotata in fondo al diagramma.
- Le chiusure inventario sono rappresentate da una linea verticale tratteggiata di colore rosso.
- Le liquidazioni eseguite tramite chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

## <a name="weighted-average-summarized-settlement-without-the-include-physical-value-option"></a>Compensazione riepilogativa media ponderata senza l'opzione Includi valore fisico

Quando in un periodo ci sono più entrate, la media ponderata utilizza il principio di compensazione riepilogato secondo il quale tutte le entrate comprese in un periodo di chiusura vengono riepilogate in una transazione denominata *chiusura inventario media ponderata*. Tutte le entrate del periodo verranno compensate a fronte dell'uscita della transazione scorte creata, mentre tutte le uscite del periodo verranno compensate a fronte dell'entrata della nuova transazione di scorte. Se dopo la chiusura dell'inventario rimane un valore di scorte disponibili, tale valore di scorte disponibili viene incluso nella transazione in entrata delle transazioni di chiusura inventario con media ponderata.

Nel grafico riportato di seguito sono illustrate le seguenti transazioni:

- 1a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
- 1b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
- 2a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
- 2b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 22,00 EUR.
- 3a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 16,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 3b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo di 16,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 4a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 25,00 EUR.
- 5a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 5b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 6a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 23,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 7\. Viene eseguita la chiusura inventario.
- 7a. Viene creata un'uscita finanziaria transazione di chiusura inventario media ponderata per sommare le compensazioni di tutte le entrate finanziarie in magazzino.
  - La transazione 1b è compensata per una quantità pari a 1 con un importo regolato di USD 10.00.
  - La transazione 2b è compensata per una quantità pari a 1 con un importo regolato di USD 22.00.
  - La transazione 5b è compensata per una quantità pari a 1 con un importo regolato di USD 30.00.
  - La transazione 7a. è creata per una quantità pari a 3 con un importo regolato di USD 62.00. Questa transazione compensa la somma delle tre transazioni di entrata aggiornate finanziariamente nel periodo.
- 7b. Creazione entrata finanziaria per transazione di chiusura inventario media ponderata come contropartita alle uscite registrate finanziariamente.
  - La transazione 3b è compensata per una quantità pari a 1 con un importo regolato di USD 20.67. Questa transazione viene rettificata da USD 4.67 per portare il valore originale di USD 16.00 a 20,67, che è la media ponderata delle transazioni registrate finanziariamente per il periodo.
  - La transazione 7b. è creata per una quantità pari a 1 con un importo regolato di USD 20.67 per compensare 3b. Questa transazione compensa la somma di una transazione di uscita aggiornata finanziariamente nel periodo.

Nel diagramma riportato di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale media ponderata e del principio di compensazione riepilogativo senza l'opzione **Includi valore fisico**.

![Compensazione riepilogativa media ponderata senza l'opzione Includi valore fisico.](media/weighted-average-summarized-settlement-without-include-physical-value.png)

**Informazioni sul diagramma**

- Le operazioni di magazzino sono rappresentate da frecce verticali.
- Le transazioni fisiche sono rappresentate da frecce grigio chiaro più corte.
- Le transazioni finanziarie sono rappresentate da frecce nere più lunghe.
- Le entrate in magazzino sono rappresentate da frecce verticali al di sopra dell'asse.
- Le uscite da magazzino sono rappresentate da frecce verticali al di sotto dell'asse.
- Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
- Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
- Ciascuna data nel diagramma è separata da una sottile linea verticale nera. La data è annotata in fondo al diagramma.
- Le chiusure inventario sono rappresentate da una linea verticale tratteggiata di colore rosso.
- Le liquidazioni eseguite tramite chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

## <a name="weighted-average-direct-settlement-with-the-include-physical-value-option"></a>Compensazione diretta media ponderata con l'opzione Includi valore fisico

Il funzionamento del parametro **Includi valore fisico** con il modello inventariale media ponderata è diverso rispetto alle versioni precedenti del prodotto. Quando selezioni l'opzione **Includi valore fisico** per un articolo nel modulo **Gruppo di modelli di articoli**, il sistema utilizza le entrate aggiornate fisicamente quando calcola il prezzo stimato o la media corrente. Le uscite verranno registrate in base a tale prezzo di costo stimato durante il periodo. Durante la chiusura dell'inventario, le entrate aggiornate finanziariamente verranno considerate solo nel calcolo della media ponderata.

Nel grafico riportato di seguito sono illustrate le seguenti transazioni:

- 1a. Entrata fisica in magazzino per una quantità pari a 10 al costo unitario di 10,00 EUR.
- 1b. Entrata finanziaria in magazzino per una quantità pari a 10 al costo unitario di 10,00 EUR.
- 2a. Entrata fisica in magazzino per una quantità pari a 10 al costo unitario di 20,00 EUR.
- 3a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 15,00 EUR (media corrente delle transazioni fisiche e finanziarie registrate).
- 3b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo di 15,00 EUR (media corrente delle transazioni fisiche e finanziarie registrate).
- 4a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 15,00 EUR (media corrente delle transazioni fisiche e finanziarie registrate).
- 4b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo di 15,00 EUR (media corrente delle transazioni fisiche e finanziarie registrate).
- 5a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 15,00 EUR (media corrente delle transazioni fisiche e finanziarie registrate).
- 6\. Viene eseguita la chiusura inventario. Sulla base del metodo della media ponderata, il sistema utilizza il metodo della compensazione diretta poiché nel periodo viene aggiornato finanziariamente un solo incasso. In questo esempio, viene creata una compensazione tra 1b e 3b e un'altra tra 1b e 4b. Le transazioni 3b e 4b vengono rettificate ciascuna di USD -5,00 per portare il valore a USD 10.00.

Nel diagramma riportato di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale media ponderata e del principio di compensazione diretta con l'opzione **Includi valore fisico**.

![Compensazione diretta media ponderata con l'opzione Includi valore fisico.](media/weighted-average-direct-settlement-with-include-physical-value.png)

**Informazioni sul diagramma**

- Le operazioni di magazzino sono rappresentate da frecce verticali.
- Le transazioni fisiche sono rappresentate da frecce grigio chiaro più corte.
- Le transazioni finanziarie sono rappresentate da frecce nere più lunghe.
- Le entrate in magazzino sono rappresentate da frecce verticali al di sopra dell'asse.
- Le uscite da magazzino sono rappresentate da frecce verticali al di sotto dell'asse.
- Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
- Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
- Ciascuna data nel diagramma è separata da una sottile linea verticale nera. La data è annotata in fondo al diagramma.
- Le chiusure inventario sono rappresentate da una linea verticale tratteggiata di colore rosso.
- Le liquidazioni eseguite tramite chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

## <a name="weighted-average-summarized-settlement-with-the-include-physical-value-option"></a>Compensazione riepilogativa media ponderata con l'opzione Includi valore fisico

Il funzionamento del parametro **Includi valore fisico** con la media ponderata è diverso rispetto alle versioni precedenti del programma. Selezionare la casella di controllo **Includi valore fisico** per un articolo nella pagina **Gruppi di modelli di articoli**. Verranno utilizzate le entrate aggiornate fisicamente durante il calcolo del prezzo di costo stimato o della media corrente. Le uscite verranno registrate in base a tale prezzo di costo stimato durante il periodo. Durante la chiusura dell'inventario, le entrate aggiornate finanziariamente verranno considerate solo nel calcolo della media ponderata. Quando si utilizza il modello inventariale media ponderata, si consiglia di eseguire una chiusura inventario ogni mese. In questo esempio di compensazione riepilogativa media ponderata il modello inventariale è contrassegnato in modo da includere il valore fisico.

Nel grafico riportato di seguito sono illustrate le seguenti transazioni:

- 1a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
- 1b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
- 2a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
- 2b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 22,00 EUR.
- 3a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 16,00 EUR (media corrente delle transazioni fisiche e finanziarie registrate).
- 3b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo di 16,00 EUR (media corrente delle transazioni fisiche e finanziarie registrate).
- 4a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 25,00 EUR.
- 5a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 5b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 6a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 23,67 EUR (media corrente delle transazioni fisiche e finanziarie registrate).
- 7\. Viene eseguita la chiusura inventario.
- 7a. Viene creata un'uscita finanziaria transazione di chiusura inventario media ponderata per sommare le compensazioni di tutte le entrate finanziarie in magazzino.
  - La transazione 1b è compensata per una quantità pari a 1 con un importo regolato di USD 10.00.
  - La transazione 2b è compensata per una quantità pari a 1 con un importo regolato di USD 22.00.
  - La transazione 5b è compensata per una quantità pari a 1 con un importo regolato di USD 30.00.
  - La transazione 7a. è creata per una quantità pari a 3 con un importo regolato di USD 62.00.  
- 7b. Creazione entrata finanziaria per transazione di chiusura inventario media ponderata come contropartita alle transazioni di uscita registrate finanziariamente.
  - La transazione 3b è compensata per una quantità pari a 1 con un importo regolato di USD 20.67. Questa transazione viene rettificata da USD 4.67 per portare il valore originale di USD 16.00 a 20,67, che è la media ponderata delle transazioni registrate finanziariamente per il periodo.
  - La transazione 7b. è creata per una quantità pari a 1 con un importo regolato di USD 20.67 per compensare 3b.

Nel diagramma riportato di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale media ponderata e del principio di compensazione riepilogativo senza l'opzione **Includi valore fisico**.

![Compensazione riepilogativa media ponderata con l'opzione Includi valore fisico.](media/weighted-average-summarized-settlement-with-include-physical-value.png)

**Informazioni sul diagramma**

- Le operazioni di magazzino sono rappresentate da frecce verticali.
- Le transazioni fisiche sono rappresentate da frecce grigio chiaro più corte.
- Le transazioni finanziarie sono rappresentate da frecce nere più lunghe.
- Le entrate in magazzino sono rappresentate da frecce verticali al di sopra dell'asse.
- Le uscite da magazzino sono rappresentate da frecce verticali al di sotto dell'asse.
- Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
- Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
- Ciascuna data nel diagramma è separata da una sottile linea verticale nera. La data è annotata in fondo al diagramma.
- Le chiusure inventario sono rappresentate da una linea verticale tratteggiata di colore rosso.
- Le liquidazioni eseguite tramite chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

## <a name="weighted-average-with-marking"></a>Media ponderata con contrassegno

Il contrassegno è un processo che consente di collegare, o contrassegnare, una transazione in uscita a una transazione in entrata. Questo processo può essere eseguito prima o dopo la registrazione di una transazione. È possibile utilizzare il contrassegno per essere certi del costo esatto dell'inventario quando viene registrata la transazione o viene eseguita la chiusura dell'inventario.

Si supponga ad esempio che il reparto Servizio clienti di un'azienda abbia accettato un ordine urgente da parte di un cliente importante. Trattandosi di un'urgenza, sarà necessario pagare un prezzo più elevato per l'articolo in modo da poter soddisfare la richiesta del cliente. Di conseguenza, è necessario accertarsi che il costo dell'articolo di magazzino venga considerato nel margine, ovvero nel costo del venduto (COGS), della fattura relativa a questo ordine cliente.

Quando l'ordine fornitore viene registrato, l'articolo di magazzino viene ricevuto al costo di 120,00 EUR. Se ad esempio il documento dell'ordine cliente viene contrassegnato nell'ordine fornitore prima della registrazione del documento di trasporto o della fattura, il costo del venduto sarà uguale a 120,00 EUR anziché al costo medio corrente dell'articolo. Se la registrazione del documento di trasporto ordine cliente o della fattura avviene prima del contrassegno, il costo del venduto verrà registrato con il prezzo di costo medio corrente.

Prima di eseguire la chiusura dell'inventario, è ancora possibile collegare queste due transazioni.

Quando una transazione in entrata viene collegata a una transazione in uscita tramite contrassegno, il metodo di valutazione selezionato per il gruppo di modelli di articoli dell'articolo verrà ignorato e le transazioni verranno compensate l'una con l'altra.

Per collegare una transazione in uscita a un'entrata prima che la transazione venga registrata, È possibile effettuare questa operazione da una riga dell'ordine vendita nella pagina **Dettagli ordini cliente**. Le transazioni di entrata aperte sono mostrate nella pagina **Contrassegno**.

Per collegare una transazione in uscita a un'entrata dopo che la transazione è stata registrata, è possibile abbinare o contrassegnare una transazione in uscita a una transazione in entrata aperta per un articolo inventariato da un giornale di registrazione di rettifica magazzino registrato.

Nel grafico riportato di seguito sono illustrate le seguenti transazioni:

- 1a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
- 1b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
- 2a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
- 2b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 22,00 EUR.
- 3a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 16,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 3b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo di 16,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 3c. L'emissione finanziaria di inventario per 3b è contrassegnata per l'emissione finanziaria di inventario per 2b.
- 4a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 25,00 EUR.
- 5a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 5b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 6a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 23,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 7\. Viene eseguita la chiusura inventario. Sulla base del principio del contrassegno che utilizza il metodo della media ponderata, le transazioni contrassegnate sono compensate l'una contro l'altra. In questo esempio, 3b viene liquidata rispetto a 2b e una rettifica per USD 6.00 viene inviata a 3b per portare il valore a USD 22.00. In questo esempio, non vengono effettuate liquidazioni aggiuntive, poiché la chiusura crea liquidazioni solo per transazioni aggiornate finanziariamente.

Nel diagramma riportato di seguito viene illustrata questa serie di transazioni con gli effetti derivanti dalla scelta del modello inventariale media ponderata con contrassegno.

![Media ponderata con contrassegno.](media/weighted-average-with-marking.png)

**Informazioni sul diagramma**

- Le operazioni di magazzino sono rappresentate da frecce verticali.
- Le transazioni fisiche sono rappresentate da frecce grigio chiaro più corte.
- Le transazioni finanziarie sono rappresentate da frecce nere più lunghe.
- Le entrate in magazzino sono rappresentate da frecce verticali al di sopra dell'asse.
- Le uscite da magazzino sono rappresentate da frecce verticali al di sotto dell'asse.
- Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
- Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
- Ciascuna data nel diagramma è separata da una sottile linea verticale nera. La data è annotata in fondo al diagramma.
- Le chiusure inventario sono rappresentate da una linea verticale tratteggiata di colore rosso.
- Le liquidazioni eseguite tramite chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
