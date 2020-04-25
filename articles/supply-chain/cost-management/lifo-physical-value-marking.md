---
title: Informazioni su LIFO con valore fisico e contrassegno
description: LIFO (Last In, First Out) è un modello inventariale in cui le ultime entrate (le più recenti) sono le prime a uscire. Le uscite da magazzino vengono compensate a fronte delle ultime entrate in magazzino in base alla data dell'operazione di magazzino.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 55021
ms.assetid: 49c492b0-b018-44e0-928f-9671e54eee20
ms.search.region: Global
ms.search.industry: Retail
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e774b032bdcb3047f4788c97cd94e6336f20109a
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201665"
---
# <a name="lifo-with-physical-value-and-marking"></a>Informazioni su LIFO con valore fisico e contrassegno

[!include [banner](../includes/banner.md)]

LIFO (Last In, First Out) è un modello inventariale in cui le ultime entrate (le più recenti) sono le prime a uscire. Le uscite da magazzino vengono compensate a fronte delle ultime entrate in magazzino in base alla data dell'operazione di magazzino. 

LIFO (Last In, First Out) è un modello inventariale in cui le ultime entrate (le più recenti) sono le prime a uscire. Le uscite da magazzino vengono compensate a fronte delle ultime entrate in magazzino in base alla data dell'operazione di magazzino. Quando si utilizza il modello inventariale LIFO, non è necessario utilizzare la regola LIFO. È possibile invece contrassegnare le transazioni di magazzino in modo da liquidare un'entrata di articoli specifica a fronte di un'uscita specifica. Quando si utilizza il modello inventariale LIFO, si consiglia di eseguire una chiusura di inventario periodica. 

Negli esempi riportati di seguito viene mostrato l'effetto prodotto dall'utilizzo del modello LIFO con tre configurazioni:

-   LIFO senza l'opzione **Includi valore fisico**
-   LIFO con l'opzione **Includi valore fisico**
-   LIFO con contrassegno

## <a name="lifo-without-the-include-physical-value-option"></a>LIFO senza l'opzione Includi valore fisico
In questo esempio, il gruppo di modelli di articoli non è contrassegnato per includere il valore fisico. La figura di seguito mostra le transazioni:

-   1a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
-   1b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
-   2a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
-   2b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
-   3a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 25,00 EUR.
-   4a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
-   4b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
-   5a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo unitario di 20,00 EUR (media corrente delle transazioni aggiornate finanziariamente).
-   5b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo unitario di 20,00 EUR (media corrente delle transazioni aggiornate finanziariamente).
-   6. Viene eseguita la chiusura inventario. In base al metodo LIFO, l'ultima uscita aggiornata finanziariamente verrà compensata a fronte dell'ultima entrata aggiornata finanziariamente. Per la transazione in uscita verrà effettuata una rettifica di 10,00 EUR.

Il nuovo prezzo di costo medio corrente riflette la media delle transazioni aggiornate finanziariamente a 15,00 EUR. La seguente figura mostra gli effetti del modello inventariale LIFO in questa serie di transazioni quando non viene utilizzata l'opzione **Includi valore fisico**. 

![LIFO senza Includi valore fisico](./media/lifowithoutincludephysicalvalue.gif) 

**Informazioni sul diagramma**

- Le operazioni di magazzino sono rappresentate da frecce verticali.
- Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
- Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
- Al di sopra o al di sotto di ciascuna freccia verticale, il valore della transazione di magazzino è specificato nel formato Quantità/Prezzo unitario.
- Un valore di transazione di magazzino racchiuso tra parentesi indica che l'operazione è stata registrata fisicamente in magazzino.
- Un valore di transazione di magazzino non racchiuso tra parentesi indica che l'operazione è stata registrata finanziariamente in magazzino.
- Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
- Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
- Le chiusure inventario sono rappresentate da una linea tratteggiata verticale di colore rosso e dall'etichetta *Chiusura inventario*.
- Le liquidazioni eseguite tramite la chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

## <a name="lifo-with-the-include-physical-value-option"></a>LIFO con opzione Includi valore fisico
Se la casella di controllo **Includi valore fisico** è selezionata per un articolo nella pagina **Gruppi di modelli di articoli**, il sistema utilizza entrambe le transazioni di entrata fisica e finanziaria per calcolare il prezzo del costo medio corrente. Dove applicabile, alla transazione in uscita aggiornata fisicamente verranno anche apportate dal sistema le rettifiche necessarie. Se la casella di controllo **Includi valore fisico** è deselezionata, la chiusura dell'inventario con il modello inventariale LIFO consentirà di effettuare le liquidazioni solo per le transazioni aggiornate finanziariamente. 

La figura di seguito mostra le transazioni:

-   1a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
-   1b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 10,00 EUR.
-   2a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
-   2b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 20,00 EUR.
-   3a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 25,00 EUR.
-   4a. Entrata fisica in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
-   4b. Entrata finanziaria in magazzino per una quantità pari a 1 al costo unitario di 30,00 EUR.
-   5a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo unitario di 21,25 EUR (media corrente delle transazioni fisiche e finanziarie aggiornate).
-   5b. Uscita finanziaria da magazzino per una quantità pari a 1 al prezzo di costo unitario di 21,25 EUR (media corrente delle transazioni fisiche e finanziarie aggiornate).
-   6a. Uscita fisica da magazzino per una quantità pari a 1 al prezzo di costo unitario di 21,25 EUR.
-   7. Viene eseguita la chiusura inventario. In base al metodo LIFO, l'ultima transazione in uscita verrà rettificata o compensata a fronte dell'ultima entrata aggiornata.

La transazione 6a verrà rettificata secondo la transazione in entrata 4b. Il sistema non compenserà tali transazioni perché l'entrata viene aggiornata solo fisicamente e non finanziariamente. Verrà in realtà effettuata solo una rettifica di 8,75 EUR per la transazione in uscita fisica. La transazione 5b verrà rettificata secondo la transazione in entrata fisica 3a. Il sistema non compenserà tali transazioni perché non sono state entrambe aggiornate finanziariamente. Verrà in realtà effettuata solo una rettifica di -3,75 EUR per la transazione in uscita. Il nuovo prezzo di costo medio corrente riflette la media delle transazioni aggiornate fisicamente e finanziariamente a 20,00 EUR. 

La seguente illustrazione mostra gli effetti del modello inventariale LIFO in questa serie di transazioni quando viene utilizzata l'opzione **Includi valore fisico**. 

![LIFO con Includi valore fisico](./media/lifowithincludephysicalvalue.gif) 

**Informazioni sul diagramma**

- Le operazioni di magazzino sono rappresentate da frecce verticali.
- Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
- Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
- Al di sopra o al di sotto di ciascuna freccia verticale, il valore della transazione di magazzino è specificato nel formato Quantità/Prezzo unitario.
- Un valore di transazione di magazzino racchiuso tra parentesi indica che l'operazione è stata registrata fisicamente in magazzino.
- Un valore di transazione di magazzino non racchiuso tra parentesi indica che l'operazione è stata registrata finanziariamente in magazzino.
- Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
- Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
- Le chiusure inventario sono rappresentate da una linea tratteggiata verticale di colore rosso e dall'etichetta *Chiusura inventario*.
- Le liquidazioni eseguite tramite la chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

## <a name="lifo-with-marking"></a>LIFO con contrassegno
Il contrassegno è un processo che consente di collegare, o contrassegnare, una transazione in uscita a una transazione in entrata. Questo processo può essere eseguito prima o dopo la registrazione di una transazione. È possibile utilizzare il contrassegno per essere certi del costo esatto di magazzino quando viene registrata la transazione o viene eseguita la chiusura dell'inventario. Si supponga, ad esempio, che il reparto Servizio clienti di un'azienda abbia accettato un ordine urgente da parte di un cliente importante. Trattandosi di un'urgenza, sarà necessario pagare un prezzo più elevato per l'articolo per soddisfare la richiesta del cliente. 

È necessario accertarsi che il costo dell'articolo di magazzino venga considerato nel margine, ovvero nel costo del venduto (COGS), della fattura relativa a questo ordine cliente. Quando l'ordine fornitore viene registrato, l'articolo di magazzino viene ricevuto al costo di 120,00 EUR. Se il documento dell'ordine cliente viene contrassegnato nell'ordine fornitore prima della registrazione del documento di trasporto o della fattura, il costo del venduto sarà uguale a 120,00 EUR anziché al costo medio corrente dell'articolo. Se la registrazione del documento di trasporto ordine cliente o della fattura avviene prima del contrassegno, il costo del venduto verrà registrato con il prezzo di costo medio corrente. 

Prima di eseguire la chiusura dell'inventario, è ancora possibile collegare queste due transazioni. 

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
-   7. Viene eseguita la chiusura inventario. Poiché la transazione FIFO aggiornata finanziariamente è contrassegnata rispetto a un'entrata esistente, queste transazioni vengono liquidate reciprocamente senza effettuare alcuna rettifica.

Il nuovo prezzo di costo medio corrente riflette la media delle transazioni aggiornate fisicamente e finanziariamente a 27,50 EUR. 

Nella seguente illustrazione vengono mostrati gli effetti del modello inventariale LIFO su questa serie di transazioni quando viene utilizzato il contrassegno tra entrate e uscite. 

![LIFO con Contrassegno](./media/lifowithmarking.gif) 

**Informazioni sul diagramma**

- Le operazioni di magazzino sono rappresentate da frecce verticali.
- Le entrate in magazzino sono rappresentate da frecce verticali al di sopra della sequenza temporale.
- Le uscite da magazzino sono rappresentate da frecce verticali al di sotto della sequenza temporale.
- Al di sopra o al di sotto di ciascuna freccia verticale, il valore della transazione di magazzino è specificato nel formato Quantità/Prezzo unitario.
- Un valore di transazione di magazzino racchiuso tra parentesi indica che l'operazione è stata registrata fisicamente in magazzino.
- Un valore di transazione di magazzino non racchiuso tra parentesi indica che l'operazione è stata registrata finanziariamente in magazzino.
- Ogni nuova transazione in entrata o in uscita è indicata con una nuova etichetta.
- Ogni freccia verticale è contrassegnata con un identificatore sequenziale, ad esempio *1a*. Gli identificatori indicano l'ordine delle registrazioni relative alle transazioni di magazzino nella sequenza temporale.
- Le chiusure inventario sono rappresentate da una linea tratteggiata verticale di colore rosso e dall'etichetta *Chiusura inventario*.
- Le liquidazioni eseguite tramite la chiusura inventario sono rappresentate da frecce rosse tratteggiate che uniscono in diagonale un'entrata a un'uscita.

