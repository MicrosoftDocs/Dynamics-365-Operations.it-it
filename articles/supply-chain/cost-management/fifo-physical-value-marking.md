---
title: Informazioni su FIFO con valore fisico e contrassegno
description: FIFO (First In, First Out) è un modello inventariale secondo il quale gli articoli acquistati per primi sono i primi a uscire dal magazzino. Le uscite da magazzino aggiornate finanziariamente vengono compensate a fronte delle prime entrate in magazzino aggiornate finanziariamente in base alla data finanziaria della transazione di magazzino.
author: AndersGirke
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 54682
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5280498a23df26873dda1f380f686796f5e1055f
ms.sourcegitcommit: fefe93f3f44d8aa0b7e6d54cc4a3e5eca6e64feb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092142"
---
# <a name="fifo-with-physical-value-and-marking"></a>Informazioni su FIFO con valore fisico e contrassegno

[!include [banner](../includes/banner.md)]


First in, first out (FIFO) è un metodo di gestione e valutazione dell'inventario in cui l'inventario prodotto o acquisito per primo viene venduto, utilizzato o smaltito per primo. Durante il processo di chiusura dell'inventario in Microsoft Dynamics 365 Supply Chain Management, il sistema creerà liquidazioni in cui la prima ricevuta viene abbinata alla prima emissione e così via.

Il principio di abbinamento e le liquidazioni si basano sulla data finanziaria delle transazioni di magazzino. Una valutazione preliminare delle liquidazioni e delle rettifiche può essere eseguita eseguendo il processo di ricalcolo dell'inventario.

Puoi ignorare il principio FIFO contrassegnando le transazioni di magazzino in modo da liquidare un'entrata di articoli specifica a fronte di un'uscita specifica. È necessaria una chiusura periodica dell'inventario quando si utilizza il modello di inventario FIFO per creare liquidazioni e adeguare il valore delle emissioni secondo il principio FIFO. Fino a quando non esegui il processo di chiusura dell'inventario, le transazioni in uscita vengono valutate alla media corrente al momento dell'aggiornamento fisico e finanziario. A meno che tu non utilizzi la marcatura, la media corrente viene calcolata quando viene eseguito l'aggiornamento fisico o finanziario. Negli esempi riportati di seguito viene mostrato l'effetto prodotto dall'utilizzo del modello FIFO con tre configurazioni:

- FIFO senza l'opzione **Includi valore fisico**
- FIFO con l'opzione **Includi valore fisico**
- FIFO con contrassegno

## <a name="fifo-without-the-include-physical-value-option"></a>FIFO senza l'opzione Includi valore fisico

In questo esempio, la casella di controllo **Includi valore fisico** è deselezionata nel gruppo di modelli di articoli per il prodotto rilasciato. La figura di seguito mostra le transazioni:

- 1a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
- 1b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
- 2a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
- 2b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 22,00 EUR.
- 3a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 16,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 3b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo di 16,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 4a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 25,00 EUR.
- 5a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 5b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 6a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 23,00 EUR (media corrente delle transazioni registrate finanziariamente)
- 7\. Viene eseguita la chiusura inventario. In base al metodo FIFO, la prima uscita aggiornata finanziariamente verrà compensata con la prima entrata aggiornata finanziariamente e così via. In questo esempio, viene creata una liquidazione tra 1b e 3b. Verrà effettuata una rettifica di USD –6,00 a 3b e il costo finale ottenuto sarà USD 10.00.

Il nuovo prezzo di costo medio corrente riflette la media delle transazioni aggiornate finanziariamente. Le seguenti illustrazioni mostrano gli effetti del modello inventariale FIFO in questa serie di transazioni quando non viene utilizzata l'opzione **Includi valore fisico**.

![FIFO senza l'opzione Includi valore fisico.](./media/fifo-without-include-physical-value.png)

**Informazioni sul diagramma**

- Le operazioni di magazzino sono rappresentate da frecce verticali.
- Le transazioni fisiche sono rappresentate da frecce grigio chiaro più corte.
- Le transazioni finanziarie sono rappresentate da frecce nere più lunghe.
- Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
- Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
- Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
- Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
- Ciascuna data nel diagramma è separata da una sottile linea verticale nera. La data è annotata in fondo al diagramma.
- Le chiusure inventario sono rappresentate da una linea verticale tratteggiata di colore rosso.
- Le liquidazioni eseguite tramite chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

## <a name="fifo-with-the-include-physical-value-option"></a>FIFO con l'opzione Includi valore fisico

Se la casella di controllo **Includi valore fisico** è selezionata per un articolo nella pagina **Gruppo di modelli di articoli**, il sistema utilizza entrambe le transazioni di entrata fisica e finanziaria per calcolare il prezzo del costo medio corrente. Dove applicabile, il sistema rettifica anche la transazione in uscita aggiornata fisicamente. La chisura dell'inventario che utlizza il modello inventariale FIFO effettua compensazioni solo per le transazioni aggiornate finanziariamente. La figura di seguito mostra le transazioni:

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
- 7\. Viene eseguita la chiusura inventario. In base al metodo FIFO, la prima uscita aggiornata finanziariamente verrà compensata con la prima entrata aggiornata finanziariamente e così via. In questo esempio, viene creata una liquidazione tra 1b e 3b. Verrà effettuata una rettifica di USD –6,00 a 3b e il costo finale ottenuto sarà USD 10.00. Inoltre, la transazione 6a verrà rettificata secondo il costo della transazione in entrata di 2b. Il sistema non compenserà tali transazioni perché l'entrata viene aggiornata solo fisicamente e non finanziariamente. Al contrario, nella transazione di emissione fisica verrà registrata solo una rettifica di -1,67 USD e il costo rettificato ottenuto sarà USD 22.00.

![FIFO con l'opzione Includi valore fisico.](./media/fifo-with-include-physical-value.png)

Si noti che il risultato dell'esecuzione del processo di chiusura dell'inventario è lo stesso, indipendentemente dal fatto che si selezioni l'opzione **Includi valore fisico** nella pagina **Gruppo di modelli di articoli**. L'opzione **Includi valore fisico** influisce solo sulla media corrente.

**Informazioni sul diagramma**

- Le operazioni di magazzino sono rappresentate da frecce verticali.
- Le transazioni fisiche sono rappresentate da frecce grigio chiaro più corte.
- Le transazioni finanziarie sono rappresentate da frecce nere più lunghe.
- Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
- Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
- Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
- Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
- Ciascuna data nel diagramma è separata da una sottile linea verticale nera. La data è annotata in fondo al diagramma.
- Le chiusure inventario sono rappresentate da una linea verticale tratteggiata di colore rosso.
- Le liquidazioni eseguite tramite chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

## <a name="fifo-with-marking"></a>FIFO con contrassegno

Il contrassegno è un processo che consente di collegare, o contrassegnare, una transazione in uscita a una transazione in entrata. Questo processo può essere eseguito prima o dopo la registrazione di una transazione. È possibile utilizzare il contrassegno per essere certi del costo esatto di magazzino quando viene registrata la transazione o viene eseguita la chiusura dell'inventario.

Si supponga, ad esempio, che il reparto Servizio clienti di un'azienda abbia accettato un ordine urgente da parte di un cliente importante. Trattandosi di un'urgenza, sarà necessario pagare un prezzo più elevato per l'articolo per soddisfare la richiesta del cliente. È necessario accertarsi che il costo dell'articolo di magazzino venga considerato nel margine, ovvero nel costo del venduto (COGS), della fattura relativa a questo ordine cliente. Quando l'ordine fornitore viene registrato, l'articolo di magazzino viene ricevuto al costo di 120,00 EUR. Se il documento dell'ordine cliente viene contrassegnato nell'ordine fornitore prima della registrazione del documento di trasporto o della fattura, il costo del venduto sarà uguale a 120,00 EUR anziché al costo medio corrente dell'articolo. Se la registrazione del documento di trasporto ordine cliente o della fattura avviene prima del contrassegno, il costo del venduto verrà registrato con il prezzo di costo medio corrente. Prima di eseguire la chiusura dell'inventario, è ancora possibile collegare queste due transazioni.

Quando una transazione in entrata viene contrassegnate su una transazione in uscita, il metodo di valutazione definito nel gruppo di modelli inventariali dell'articolo viene ignorato e il sistema compensa le transazioni l'una con l'altra. È possibile contrassegnare manualmente una transazione a fronte di una riga dell'ordine cliente nella pagina **Dettagli ordini cliente** selezionando **Inventario\> Contrassegno** nella Scheda dettaglio **Righe ordine cliente**. È possibile visualizzare le transazioni di entrata aperte nella pagina **Contrassegno**. È possibile abbinare o contrassegnare una transazione in uscita a una transazione in entrata aperta per un articolo inventariato da un giornale di registrazione di rettifica magazzino registrato. La figura di seguito mostra le transazioni:

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
- 6a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 23,00 EUR (media corrente delle transazioni registrate finanziariamente)
- 7\. Viene eseguita la chiusura inventario. Sulla base del principio del contrassegno che utilizza il metodo FIFO, le transazioni contrassegnate sono compensate l'una contro l'altra. In questo esempio, 3b viene liquidata rispetto a 2b e una rettifica per USD 6.00 viene inviata a 3b per portare il valore a USD 22.00. In questo esempio, non vengono effettuate liquidazioni aggiuntive, poiché la chiusura crea liquidazioni solo per transazioni aggiornate finanziariamente.

Nella seguente illustrazione vengono mostrati gli effetti del modello inventariale FIFO su questa serie di transazioni quando viene utilizzato il contrassegno tra entrate e uscite.

![FIFO con contrassegno.](./media/fifo-with-marking.png)

**Informazioni sul diagramma**

- Le operazioni di magazzino sono rappresentate da frecce verticali.
- Le transazioni fisiche sono rappresentate da frecce grigio chiaro più corte.
- Le transazioni finanziarie sono rappresentate da frecce nere più lunghe.
- Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
- Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
- Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
- Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
- Ciascuna data nel diagramma è separata da una sottile linea verticale nera. La data è annotata in fondo al diagramma.
- Le chiusure inventario sono rappresentate da una linea verticale tratteggiata di colore rosso.
- Le liquidazioni e i contrassegni eseguiti tramite chiusura inventario sono rappresentati da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
