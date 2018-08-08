--- 
title: Registrare l'entrata di merci sull'ordine fornitore
description: Questa procedura mostra come registrare l'entrata delle merci direttamente su un ordine fornitore.
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9b2300a593c9e153ee598fa72e29907c82f2b79e
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>Registrare l'entrata di merci sull'ordine fornitore

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come registrare l'entrata delle merci direttamente su un ordine fornitore. È inoltre possibile registrare l'entrata prodotti nel magazzino e poi registrarla successivamente sull'ordine fornitore. Quest'attività viene eseguita tipicamente da un addetto acquisti o un coordinatore contabilità fornitori. L'esempio indicato in questa guida può essere utilizzato nella società di dati dimostrativi USMF. L'esempio comprende i passaggi per creare un ordine fornitore semplice in modo da poter eseguire la procedura come guida attività. Se si seguisse la procedura utilizzando i propri dati, si dovrebbe iniziare con la sottoattività Registrare l'entrata dei prodotti.


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a>Preparare un nuovo ordine fornitore per l'entrata delle merci
1. Andare ad Approvvigionamento > Ordini fornitore> Tutti gli ordini fornitore.
2. Fare clic su Nuovo.
3. Digitare US-101 nel campo Conto fornitore.
4. Fare clic su OK.
5. Nel campo Numero articolo immettere M0001.
6. Nel campo Quantità immettere 5.
7. Nel riquadro azioni fare clic su Acquisti.
8. Fare clic su Conferma.

## <a name="record-receipt-of-goods"></a>Registrare l'entrata dei prodotti
1. Nel riquadro azioni fare clic su Ricevimento.
2. Fare clic su Entrata prodotti.
    * Il campo Quantità permette di selezionare opzioni differenti per la quantità che volete ricevere. Ad esempio, se una quantità precedentemente è stata registrata nel magazzino, potete selezionare Quantità registrata.  Per questo esempio, usare il valore Quantità ordinata.   
3. Digitare un valore nel campo Entrata prodotti.
    * Questo campo è usato per immettere un riferimento che sarà usato come giustificativo per il giornale di registrazione entrata prodotti.  
4. Espandere la sezione Righe.
5. Impostare la quantità su "4".
    * Qui potete specificare manualmente la quantità che si sta ricevendo per ogni riga sull'ordine.  
6. Comprimere la sezione Righe.
7. Fare clic su OK.
    * Le merci ora sono state registrate come ricevute sull'ordine fornitore e un giornale di registrazione entrata prodotti è stato creato come documento per riflettere questo. Potete usare l'azione Entrata prodotti per esaminare i giornali di registrazione creati con l'ordine fornitore e vedere che cosa è stato ricevuto e quando.  


