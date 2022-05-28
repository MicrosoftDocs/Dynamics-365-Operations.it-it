---
title: Data LIFO con valore fisico e contrassegno
description: Data LIFO (Last In, First Out) è un modello inventariale basato sul principio LIFO. Le uscite da magazzino vengono liquidate a fronte delle ultime entrate in magazzino in base alla data della transazione di magazzino. Mediante questo modello inventariale, in assenza di entrate antecedenti all'uscita, quest'ultima viene liquidata a fronte delle entrate successive alla data dell'uscita. In caso di più uscite con la stessa data, la liquidazione può essere effettuata in base all'ordine ultima uscita, ultima entrata.
author: JennySong-SH
ms.date: 02/21/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 51592
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8ca344e6ca81814e787046f6ece97625d035346d
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671452"
---
# <a name="lifo-date-with-physical-value-and-marking"></a>Data LIFO con valore fisico e contrassegno

[!include [banner](../includes/banner.md)]

Last in, first out (LIFO) è un metodo di gestione e valutazione dell'inventario in cui l'inventario prodotto o acquisito per primo viene venduto, utilizzato o smaltito per primo. Durante il processo di chiusura dell'inventario in Microsoft Dynamics 365 Supply Chain Management, il sistema creerà liquidazioni in cui l'ultima entrata viene abbinata alla prima emissione per ogni data specificata a partire dalla data meno recente e così via. Quando si usa il modello inventariale LIFO (Last In, First Out), in assenza di entrate antecedenti all'uscita, quest'ultima viene liquidata a fronte delle entrate successive alla data dell'uscita. Il principio di abbinamento e le liquidazioni si basano sulla data finanziaria delle transazioni di magazzino. In caso di più uscite con la stessa data, la liquidazione può essere effettuata in base all'ordine ultima uscita, ultima entrata. Una valutazione preliminare delle liquidazioni e delle rettifiche può essere eseguita eseguendo il processo di ricalcolo dell'inventario.

Puoi ignorare il principio LIFO contrassegnando le transazioni di magazzino in modo da liquidare un'entrata di articoli specifica a fronte di un'uscita specifica. È necessaria una chiusura periodica dell'inventario quando si utilizza il modello di inventario LIFO per creare liquidazioni e adeguare il valore delle emissioni secondo il principio LIFO. Fino a quando non esegui il processo di chiusura dell'inventario, le transazioni in uscita vengono valutate alla media corrente al momento dell'aggiornamento fisico e finanziario. A meno che tu non utilizzi la marcatura, la media corrente viene calcolata quando viene eseguito l'aggiornamento fisico o finanziario.

Si consiglia di eseguire una chiusura periodica dell'inventario quando viene applicato questo modello inventariale.

Negli esempi riportati di seguito viene mostrato l'effetto prodotto dall'utilizzo del modello Data LIFO con tre configurazioni:

- Data LIFO senza opzione **Includi valore fisico**
- Data LIFO con opzione **Includi valore fisico**
- Data LIFO con Contrassegno

## <a name="lifo-date-without-the-include-physical-value-option"></a>Data LIFO senza opzione Includi valore fisico

In questo esempio, il gruppo di modelli di articoli non è contrassegnato per includere il valore fisico. La figura di seguito mostra le transazioni:

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
- 7\. Viene eseguita la chiusura inventario. In base al metodo LIFO, la prima uscita aggiornata finanziariamente verrà compensata con l'ultima entrata aggiornata finanziariamente a partire dalla prima data e così via. In questo esempio, viene creata una liquidazione tra 3b e 2b. Verrà effettuata una rettifica di USD 6,00 a 3b e il costo finale ottenuto sarà USD 22.00.

La seguente illustrazione mostra gli effetti del modello inventariale Data LIFO quando non viene utilizzata l'opzione **Includi valore fisico**.

![Data LIFO senza opzione Includi valore fisico.](media/lifo-date-without-include-physical-value.png)

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

## <a name="lifo-date-with-the-include-physical-value-option"></a>Data LIFO con opzione Includi valore fisico

Se la casella di controllo **Includi valore fisico** è selezionata per un articolo nella pagina **Gruppi di modelli di articoli**, il sistema utilizza entrambe le transazioni di entrata fisica e finanziaria per calcolare il prezzo del costo medio corrente. Dove applicabile, il sistema rettifica anche la transazione in uscita aggiornata fisicamente. Se la casella di controllo **Includi valore fisico** è deselezionata, la chiusura dell'inventario con il modello inventariale Data LIFO consentirà di effettuare le liquidazioni solo per le transazioni aggiornate finanziariamente.

In questo esempio di modello il gruppo di modelli di articoli è contrassegnato per includere il valore fisico. 

La figura di seguito mostra le transazioni:

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
- 7\. Viene eseguita la chiusura inventario. In base al metodo LIFO, la prima uscita aggiornata finanziariamente verrà compensata con l'ultima entrata aggiornata finanziariamente per ciascuna data a partire dalla prima data e così via. In questo esempio, viene creata una liquidazione tra 2b e 3b. Verrà effettuata una rettifica di USD 6,00 a 3b e il costo finale ottenuto sarà USD 22.00. Inoltre, la transazione 6a verrà rettificata secondo il costo della transazione in entrata di 5b. Il sistema non compenserà tali transazioni perché l'entrata viene aggiornata solo fisicamente e non finanziariamente. Al contrario, nella transazione di emissione fisica verrà registrata solo una rettifica di -6,33 USD e il costo rettificato ottenuto sarà USD 30.00.

La seguente illustrazione mostra gli effetti del modello inventariale LIFO quando viene utilizzata l'opzione **Includi valore fisico**.

![Data LIFO con opzione Includi valore fisico.](media/lifo-date-with-include-physical-value.png)

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

## <a name="lifo-date-with-marking"></a>Data LIFO con Contrassegno

Il contrassegno è un processo che consente di collegare, o contrassegnare, una transazione in uscita a una transazione in entrata. Questo processo può essere eseguito prima o dopo la registrazione di una transazione. È possibile utilizzare il contrassegno per essere certi del costo esatto di magazzino quando viene registrata la transazione o viene eseguita la chiusura dell'inventario. Si supponga, ad esempio, che il reparto Servizio clienti di un'azienda abbia accettato un ordine urgente da parte di un cliente importante. Trattandosi di un'urgenza, sarà necessario pagare un prezzo più elevato per l'articolo per soddisfare la richiesta del cliente.

È necessario accertarsi che il costo dell'articolo di magazzino venga considerato nel margine, ovvero nel costo del venduto (COGS), della fattura relativa a questo ordine cliente. Quando l'ordine fornitore viene registrato, l'articolo di magazzino viene ricevuto al costo di 120,00 EUR. Se il documento dell'ordine cliente viene contrassegnato nell'ordine fornitore prima della registrazione del documento di trasporto o della fattura, il costo del venduto sarà uguale a 120,00 EUR anziché al costo medio corrente dell'articolo. Se la registrazione del documento di trasporto ordine cliente o della fattura avviene prima del contrassegno, il costo del venduto verrà registrato con il prezzo di costo medio corrente.

Prima di eseguire la chiusura dell'inventario, è ancora possibile collegare queste due transazioni.

Per collegare una transazione in uscita a un'entrata prima che la transazione venga registrata, È possibile contrassegnare da una riga dell'ordine cliente nella pagina **Dettagli ordini cliente** selezionando **Inventario\> Contrassegno** nella Scheda dettaglio **Righe ordine cliente**. È possibile visualizzare le transazioni di entrata aperte nella pagina **Contrassegno**.

Per collegare una transazione in uscita a un'entrata dopo che la transazione è stata registrata, è possibile abbinare o contrassegnare una transazione in uscita a una transazione in entrata aperta per un articolo inventariato da un giornale di registrazione di rettifica magazzino registrato.

La figura di seguito mostra le transazioni:

- 1a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
- 1b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
- 2a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
- 2b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 22,00 EUR.
- 3a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 16,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 3b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo di 16,00 EUR (media corrente delle transazioni registrate finanziariamente).
- 3c. L'emissione finanziaria di inventario per 3b è contrassegnata per l'emissione finanziaria di inventario per 1b.
- 4a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 25,00 EUR.
- 5a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 5b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
- 6a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo di 23,00 EUR (media corrente delle transazioni registrate finanziariamente)
- 7\. Viene eseguita la chiusura inventario. Sulla base del principio del contrassegno che utilizza il metodo LIFO, le transazioni contrassegnate sono compensate l'una contro l'altra. In questo esempio, 3b viene liquidata rispetto a 1b e una rettifica per USD -6.00 viene inviata a 3b per portare il valore a USD 10.00. In questo esempio, non vengono effettuate liquidazioni aggiuntive, poiché la chiusura crea liquidazioni solo per transazioni aggiornate finanziariamente.

Nella seguente illustrazione vengono illustrati gli effetti legati alla scelta del modello inventariale LIFO con contrassegno tra entrate e uscite. 

![Data LIFO con Contrassegno.](media/lifo-date-with-marking.png)

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
- Le liquidazioni e i contrassegni eseguiti tramite chiusura inventario sono rappresentati da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
