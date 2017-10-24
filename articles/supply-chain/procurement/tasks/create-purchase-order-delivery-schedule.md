--- 
title: Creare un ordine fornitore con una programmazione consegna
description: Questa procedura dimostra come creare una programmazione consegna per un ordine foritore.
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1e4a0204d74c8966cd90b52ae13c88e222ebc3ef
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-order-with-a-delivery-schedule"></a>Creare un ordine fornitore con una programmazione consegna

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa procedura dimostra come creare una programmazione consegna per un ordine foritore. Una programmazione consegna viene utilizzata quando si richiede che una quantità di un ordine o su un giornale di registrazione venga consegnata in più spedizioni. L'esempio indicato in questa guida può essere utilizzato nella società di dati dimostrativi USMF. Questa procedura viene in genere eseguita da un addetto agli acquisti.


## <a name="create-a-delivery-schedule"></a>Creare una programmazione consegna
1. Andare ad Approvvigionamento > Ordini fornitore> Tutti gli ordini fornitore.
2. Fare clic su Nuovo.
3. Digitare US-101 nel campo Conto fornitore.
4. Fare clic su OK.
5. Nel campo Numero articolo immettere M0001.
6. Nel campo Quantità immettere 10.
7. Fare clic su Riga ordine fornitore.
8. Fare clic su Programmazione consegna.
    * La pagina Programmazione consegna è il luogo in cui è possibile specificare il numero di spedizioni in cui la quantità totale della riga ordine verrà consegnata dal fornitore.  
    * Per impostazione predefinita, il sistema copia la quantità totale e altri dettagli di consegna della riga di acquisto originale nella prima riga di programmazione consegna. In questo esempio creeremo una programmazione per due spedizioni, con uno scostamento della data della seconda spedizione di una settimana rispetto alla prima.  
9. Nel campo Quantità modificare la quantità in 4.
10. Fare clic su Nuovo.
11. Nel campo Quantità immettere 6 come quantità rimanente.
    * Nel campo della data di consegna, selezionare una data che è di una settimana successiva alla prima riga di consegna.  
    * È possibile tenere traccia della quantità totale che viene allocata alle righe di programmazione consegna guardando i campi Totale e Rimanente. Se la quantità rimanente da zero, la quantità totale della riga originale è stata allocata alla programmazione.  
12. Espandere la sezione Conversione spese.
    * Le opzioni qui permettono di determinare la distribuzione delle spese tra le righe della programmazione consegna. Se si seleziona Copia importi lordi, lo stesso importo di spesa della riga ordine originale viene copiato in ciascuna riga di consegna. L'opzione Assegna a righe consegna divide le spese dalla riga originale secondo la quantità su ogni riga di consegna.  
13. Comprimere la sezione Conversione spese.
14. Fare clic su OK.
    * La programmazione consegna ora è stata applicata all'ordine.  
    * La riga ordine originale, ora denominata riga commerciale, è stata convertita in riga ordine con più consegne. È contrassegnata con un'icona distinta e funge da intestazione delle righe consegna.  
15. Selezionare la seconda riga ordine, che è la prima delle due righe di consegna.
    * Le due nuove righe, denominate righe consegna, costituiscono una programmazione consegna. L'ordine verrà elaborato rispetto a queste righe e non alla riga originale. Se i documenti come conferme, giornali di registrazione entrata prodotti o fatture vengono stampati, verranno visualizzate solo le righe consegna.  

## <a name="change-the-delivery-schedule"></a>Modificare la programmazione consegna
    * È possibile modificare la quantità nelle righe consegna. In questo caso, la riga commerciale viene aggiornata automaticamente in base alla quantità totale delle righe di consegna.  
1. Nel campo Quantità della riga della prima consegna cambiare la quantità da 4 a 5.
2. Selezionare la prima riga di ordine (la riga commerciale).
    * La quantità della linea commerciale è stata cambiata in 11.  

## <a name="process-product-receipt-using-delivery-schedules"></a>Elaborare l'entrata prodotti facendo uso delle programmazioni consegna
    * L'ordine fornitore deve essere confermato prima che l'entrata prodotti possa essere elaborata. In questo esempio, l'entrata è registrata direttamente nell'ordine fornitore. L'entrata potrebbe anche essere stata registrata quando le merci sono arrivate nel magazzino.  
1. Nel riquadro azioni fare clic su Acquisti.
2. Fare clic su Conferma.
3. Nel riquadro azioni fare clic su Ricevimento.
4. Fare clic su Entrata prodotti.
5. Digitare un valore nel campo Entrata prodotti.
    * Questo campo è usato per immettere un riferimento che sarà usato come giustificativo per il giornale di registrazione entrata prodotti.  
    * Nel campo Quantità, selezionare ‘Quantità ordinata’. Questa opzione significa che l'entrata verrà elaborata per la quantità con cui sono state create le righe ordine.  
    * Assicurarsi che il campo Stampa entrata prodotti sia impostato su No. La stampa non è necessaria in questo esempio.  
6. Espandere la sezione Righe.
    * Notare come l'entrata prodotti è creata per le due righe di consegna e non riga ordine originale. Se l'entrata fosse stata registrata nel magazzino, sarebbe stata registrata anche nelle righe di programmazione consegna.  
7. Comprimere la sezione Righe.
8. Fare clic su OK per registrare l'entrata.


