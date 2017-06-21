---
title: Data LIFO con valore fisico e contrassegno
description: "Data LIFO (Last In, First Out) è un modello inventariale basato sul principio LIFO. Le uscite da magazzino vengono liquidate a fronte delle ultime entrate in magazzino in base alla data della transazione di magazzino. Mediante questo modello inventariale, in assenza di entrate antecedenti all'uscita, quest'ultima viene liquidata a fronte delle entrate successive alla data dell'uscita. In caso di più uscite con la stessa data, la liquidazione può essere effettuata in base all'ordine ultima uscita, ultima entrata."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 51592
ms.assetid: d9f13274-3268-444f-85c8-b686fd39286d
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 96089fed3e8b522fb3a8646ffd87fadff8fe1f3e
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="lifo-date-with-physical-value-and-marking"></a>Data LIFO con valore fisico e contrassegno

[!include[banner](../includes/banner.md)]


Data LIFO (Last In, First Out) è un modello inventariale basato sul principio LIFO. Le uscite da magazzino vengono liquidate a fronte delle ultime entrate in magazzino in base alla data della transazione di magazzino. Mediante questo modello inventariale, in assenza di entrate antecedenti all'uscita, quest'ultima viene liquidata a fronte delle entrate successive alla data dell'uscita. In caso di più uscite con la stessa data, la liquidazione può essere effettuata in base all'ordine ultima uscita, ultima entrata. 

Quando si usa il modello inventariale LIFO (Last In, First Out), in assenza di entrate antecedenti all'uscita, quest'ultima viene liquidata a fronte delle entrate successive alla data dell'uscita. In caso di più uscite con la stessa data, la liquidazione può essere effettuata in base all'ordine ultima uscita, ultima entrata. Quando si utilizza il modello inventariale Data LIFO, non è necessario utilizzare la regola Data LIFO. È possibile invece contrassegnare le transazioni di magazzino in modo da liquidare un'entrata di articoli specifica a fronte di un'uscita specifica. 

Si consiglia di eseguire una chiusura periodica dell'inventario quando viene applicato questo modello inventariale. 

Negli esempi riportati di seguito viene mostrato l'effetto prodotto dall'utilizzo del modello Data LIFO con tre configurazioni:

-   Data LIFO senza opzione **Includi valore fisico**
-   Data LIFO con opzione**Includi valore fisico**
-   Data LIFO con contrassegno

## <a name="lifo-date-without-the-include-physical-value-option"></a>Data LIFO senza opzione Includi valore fisico
In questo esempio, il gruppo di modelli di articoli non è contrassegnato per includere il valore fisico. La figura di seguito mostra le transazioni:

-   1a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
-   1b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
-   2a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
-   2b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
-   3a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 25,00 EUR.
-   4a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 15,00 EUR (media corrente delle transazioni aggiornate finanziariamente).
-   4b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo di 15,00 EUR (media corrente delle transazioni aggiornate finanziariamente).
-   5a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
-   5b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
-   6. Viene eseguita la chiusura inventario. In base al metodo Data LIFO, l'ultima uscita aggiornata finanziariamente verrà compensata dall'ultima entrata aggiornata finanziariamente in base alla data. Per la transazione in uscita verrà effettuata una rettifica di 5,00 EUR. Tali transazioni si compenseranno l'una con l'altra.

Il nuovo prezzo di costo medio corrente riflette la media delle transazioni aggiornate finanziariamente a 15,00 EUR. 

La seguente illustrazione mostra gli effetti del modello inventariale Data LIFO quando non viene utilizzata l'opzione **Includi valore fisico**. ![Data LIFO con Includi valore fisico](./media/lifodatewithoutincludephysicalvalue.gif) 

**Informazioni sul diagramma**

-   Le operazioni di magazzino sono rappresentate da frecce verticali.
-   Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
-   Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
-   Al di sopra o al di sotto di ciascuna freccia verticale, il valore dell'operazione di magazzino è specificato nel formato Quantity@Unitprice.
-   Un valore di transazione di magazzino racchiuso tra parentesi indica che l'operazione è stata registrata fisicamente in magazzino.
-   Un valore di transazione di magazzino non racchiuso tra parentesi indica che l'operazione è stata registrata finanziariamente in magazzino.
-   Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
-   Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
-   Le chiusure inventario sono rappresentate da una linea tratteggiata verticale di colore rosso e dall'etichetta *Chiusura inventario*.
-   Le liquidazioni eseguite tramite la chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

## <a name="lifo-date-with-the-include-physical-value-option"></a>Data LIFO con opzione Includi valore fisico
È possibile selezionare la casella di controllo **Includi valore fisico** per un articolo nella pagina **Gruppi di modelli di articoli**. In questo caso verranno utilizzate le transazioni in entrata sia fisiche che finanziarie per calcolare il prezzo di costo medio corrente. Dove applicabile, alla transazione in uscita aggiornata fisicamente verranno anche apportate dal sistema le rettifiche necessarie. Se la casella di controllo **Includi valore fisico** è deselezionata, la chiusura dell'inventario con il modello inventariale Data LIFO consentirà di effettuare le liquidazioni solo per le transazioni aggiornate finanziariamente. 

In questo esempio di modello il gruppo di modelli di articoli è contrassegnato per includere il valore fisico. 

La figura di seguito mostra le transazioni:

-   1a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
-   1b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
-   2a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
-   2b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
-   3a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 25,00 EUR.
-   4a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo unitario di 18,33 EUR (media corrente delle transazioni aggiornate finanziariamente).
-   4b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo unitario di 18,33 EUR (media corrente delle transazioni aggiornate finanziariamente).
-   5a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
-   5b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
-   6. Viene eseguita la chiusura inventario. In base al metodo Data LIFO, l'ultima uscita aggiornata verrà rettificata o liquidata a fronte dell'ultima entrata aggiornata in base alla data. Tali transazioni si liquideranno l'una con l'altra perché la transazione finanziaria in entrata viene rettificata in base a una transazione di aggiornamento fisica. Verrà in realtà effettuata solo una rettifica di 6,67 EUR per la transazione in uscita.

Il nuovo prezzo di costo medio corrente riflette la media delle transazioni aggiornate finanziariamente a 20,00 EUR. 

La seguente illustrazione mostra gli effetti del modello inventariale LIFO quando viene utilizzata l'opzione **Includi valore fisico**. ![Data LIFO con Includi valore fisico](./media/lifodatewithincludephysicalvalue.gif) 

**Informazioni sul diagramma**

-   Le operazioni di magazzino sono rappresentate da frecce verticali.
-   Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
-   Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
-   Al di sopra o al di sotto di ciascuna freccia verticale, il valore dell'operazione di magazzino è specificato nel formato Quantity@Unitprice.
-   Un valore di transazione di magazzino racchiuso tra parentesi indica che l'operazione è stata registrata fisicamente in magazzino.
-   Un valore di transazione di magazzino non racchiuso tra parentesi indica che l'operazione è stata registrata finanziariamente in magazzino.
-   Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
-   Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
-   Le chiusure inventario sono rappresentate da una linea tratteggiata verticale di colore rosso e dall'etichetta *Chiusura inventario*.
-   Le liquidazioni eseguite tramite la chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

## <a name="lifo-date-with-marking"></a>Data LIFO con contrassegno
Il contrassegno è un processo che consente di collegare, o contrassegnare, una transazione in uscita a una transazione in entrata. Questo processo può essere eseguito prima o dopo la registrazione di una transazione. È possibile utilizzare il contrassegno per essere certi del costo esatto di magazzino quando viene registrata la transazione o viene eseguita la chiusura dell'inventario. 

Si supponga, ad esempio, che il reparto Servizio clienti di un'azienda abbia accettato un ordine urgente da parte di un cliente importante. Trattandosi di un ordine urgente, sarà necessario pagare un prezzo più elevato per l'articolo in modo da poter soddisfare la richiesta del cliente. È necessario accertarsi che il costo dell'articolo di magazzino venga considerato nel margine, ovvero nel costo del venduto (COGS), della fattura relativa a questo ordine cliente. 

Quando l'ordine fornitore viene registrato, l'articolo di magazzino viene ricevuto al costo di 120,00 EUR. Se il documento dell'ordine cliente viene contrassegnato nell'ordine fornitore prima della registrazione del documento di trasporto o della fattura, il costo del venduto sarà uguale a 120,00 EUR anziché al costo medio corrente dell'articolo. Se la registrazione del documento di trasporto ordine cliente o della fattura avviene prima del contrassegno, il costo del venduto verrà registrato con il prezzo di costo medio corrente. 

Prima di eseguire la chiusura dell'inventario, è ancora possibile collegare queste due transazioni. 

Ad esempio, una transazione in entrata viene contrassegnata per una transazione in uscita. In questo caso, il metodo di valutazione definito nel gruppo di modelli di articoli dell'articolo verrà ignorato e le transazioni verranno liquidate l'una con l'altra. 

Per collegare una transazione in uscita a un'entrata prima che la transazione venga registrata, È possibile effettuare questa operazione da una riga dell'ordine vendita nella pagina **Dettagli ordini cliente**. È possibile visualizzare le transazioni di entrata aperte nella pagina **Contrassegno**. 

Per collegare una transazione in uscita a un'entrata dopo che la transazione è stata registrata, è possibile abbinare o contrassegnare una transazione in uscita a una transazione in entrata aperta per un articolo inventariato da un giornale di registrazione di rettifica magazzino registrato. 

La figura di seguito mostra le transazioni:

-   1a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
-   1b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
-   2a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
-   2b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
-   3a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 25,00 EUR.
-   4a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
-   4b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
-   5a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo unitario di 21,25 EUR (media corrente delle transazioni fisiche e finanziarie aggiornate).
-   5b. Uscita finanziaria da magazzino per una quantità pari a 1 contrassegnata all'entrata in magazzino 2b prima della registrazione della transazione. Questa transazione viene registrata con un prezzo di costo unitario di 20,00 EUR.
-   6a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo unitario di 21,25 EUR.
-   7. Viene eseguita la chiusura inventario. Poiché la transazione FIFO aggiornata finanziariamente è contrassegnata a un'entrata esistente, queste transazioni vengono liquidate reciprocamente senza effettuare alcuna rettifica.

Il nuovo prezzo di costo medio corrente riflette la media delle transazioni aggiornate fisicamente e finanziariamente a 27,50 EUR. 

Nella seguente illustrazione vengono illustrati gli effetti legati alla scelta del modello inventariale LIFO con contrassegno tra entrate e uscite. ![Data LIFO con Contrassegno](./media/lifodatewithmarking.gif) 

**Informazioni sul diagramma**

-   Le operazioni di magazzino sono rappresentate da frecce verticali.
-   Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
-   Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
-   Al di sopra o al di sotto di ciascuna freccia verticale, il valore dell'operazione di magazzino è specificato nel formato Quantity@Unitprice.
-   Un valore di transazione di magazzino racchiuso tra parentesi indica che l'operazione è stata registrata fisicamente in magazzino.
-   Un valore di transazione di magazzino non racchiuso tra parentesi indica che l'operazione è stata registrata finanziariamente in magazzino.
-   Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
-   Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
-   Le chiusure inventario sono rappresentate da una linea tratteggiata verticale di colore rosso e dall'etichetta *Chiusura inventario*.
-   Le liquidazioni eseguite tramite la chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.





