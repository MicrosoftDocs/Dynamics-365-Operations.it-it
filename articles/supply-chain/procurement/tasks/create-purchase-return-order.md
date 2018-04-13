--- 
title: Creare un ordine di reso acquisti
description: Questa procedura vi mostra come creare un ordine di reso acquisti usando l'azione Nota di accredito per copiare le righe da un documento di fattura fornitore ad un nuovo PO.
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
ms.openlocfilehash: b9124100f84afb13acc2ac9dda7b9483afb01754
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-return-order"></a>Creare un ordine di reso acquisti

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura vi mostra come creare un ordine di reso acquisti usando l'azione Nota di accredito per copiare le righe da un documento di fattura fornitore ad un nuovo PO. Mostra inoltre come confermare l'ordine ed elaborare la spedizione di restituzione delle merci al fornitore. L'esempio indicato in questa procedura può essere utilizzato nella società di dati dimostrativi USMF. In genere questa attività viene svolta da un addetto acquisti.


## <a name="create-a-new-purchase-return-order"></a>Creare un nuovo ordine di reso acquisti
1. Andare ad Approvvigionamento > Ordini fornitore> Tutti gli ordini fornitore.
    * Il primo passaggio è di creare un nuovo ordine fornitore da usare come ordine di reso acquisti.  
2. Fare clic su Nuovo.
3. Digitare US-102 nel campo Conto fornitore.
4. Fare clic su OK.
5. Nel riquadro azioni fare clic su Acquisti.
6. Fare clic su Nota di accredito.
    * Questa è la pagina da cui potete copiare da una fattura fornitore esistente al vostro ordine di reso. Questa è la stessa pagina che è usata per altre azioni di copia. Ma perché la abbiamo aperta dall'azione Nota di accredito, la pagina è configurata per supportare la creazione di un ordine di reso per la contropartita delle fatture fornitore.  
7. Espandere la sezione Parametri.
    * L'opzione Inverti segno è selezionata automaticamente e non può essere cambiata. Ciò assicura che il segno sia cambiato per le quantità e che le righe di ordine che si aggiungono faranno da contropartita alla fattura fornitore.  
    * L'opzione Copia spese è selezionata automaticamente e non può essere cambiata. Ciò significa che le spese dalla fattura fornitore si aggiungono all'ordine di reso acquisti come contropartita della spesa originale. È possibile modificare le spese nell'intestazione e nelle righe ordine successivamente.  
    * L'opzione Copia esattamente è selezionata automaticamente e non può essere cambiata. Ciò assicura che una copia esatta sia fatta dei valori in tutti i campi dell'intestazione e delle righe della fattura fornitore. Ciò significa che un ordine di reso acquisti è creato con i valori che corrispondono a tutti i termini usati con il documento della fattura fornitore.  
    * L'opzione Elimina righe acquisti elimina tutte le righe dell'ordine fornitore che già esistono nell'ordine fornitore prima di aggiungere le nuove righe. In questo esempio ancora non abbiamo aggiunto righe all'ordine reso acquisti, così non ci sarebbe alcun effetto. Usare con prudenza questa opzione, perché elimina tutte le linee righe esistenti senza ulteriore avvertimento.  
    * L'opzione Copia intestazione ordine è selezionata automaticamente e non può essere cambiata. Ciò assicura che le informazioni siano copiate dalla fattura fornitore e applicate all'intestazione di ordine di reso acquisti. Ciò è utile perché contribuisce ad assicurare che l'ordine di reso acquisti funga da contropartita della fattura usando simili termini.  
8. Comprimere la sezione Parametri.
9. Espandere la sezione Fatture.
    * La pagina è stata aperta dall'azione Nota di accredito, quindi la sola opzione disponibile è copiare le informazioni dalle fatture fornitore. Questa scheda mostra tutte le fatture disponibili per il conto fornitore specificato sull'ordine di reso acquisti che avete creato prima.   Le fatture sono identificate tramite il giustificativo della fattura o gli ID ordine fornitore.  
10. Individuare la fattura fornitore identificata dal numero di fattura AP-0006 ed evidenziare quella riga facendo clic su qualsiasi campo in quella riga.
11. Selezionare la riga facendo clic sulla relativa casella di controllo. 
    * Notare che le righe disponibili sulla fattura fornitore sono selezionate automaticamente insieme all'ordine. Questa fattura fornitore particolare ha 2 righe di ordine. Per questo esempio, restituiremo parte della quantità dalla seconda riga.  
12. Evidenziare la seconda riga (quella con l'articolo M0006) facendo clic su qualsiasi campo in quella riga.
13. Nel campo Quantità modificare la quantità in 10. Questa è la quantità che restituiremo al fornitore. 
14. Evidenziare la prima riga (quella con l'articolo M0005) facendo clic su qualsiasi campo in quella riga.
15. Deselezionare la casella di controllo della riga.
    * Soltanto le righe selezionate saranno copiate nel vostro ordine.  
16. Comprimere la sezione Fatture.
17. Espandere la sezione Righe o intestazioni selezionate da copiare.
    * Questa visualizzazione mostra un riepilogo di tutti i documenti e le righe che sono state selezionate per essere copiate nel vostro ordine.  
18. Comprimere la sezione Righe o intestazioni selezionate da copiare.
19. Fare clic su OK.
    * La riga selezionata è stata ora copiata nell'ordine di reso acquisti. Il campo Quantità mostra -10.   
20. Fare clic su Scorte.
21. Fare clic su Contrassegno.
    * La riga di ordine che è stata creata è contrassegnata a fronte della transazione di magazzino dalla fattura fornitore. Ciò assicura che l'inventario che è restituito al fornitore sia lo stesso dell'inventario che è stato ricevuto prima. Ci sono alcune situazioni dove il contrassegno non viene posto, per esempio, se l'inventario già è stato contrassegnato come consumato, o se il prodotto è uno che non usa il contrassegno.  
22. Fare clic su OK.

## <a name="confirm-and-record-the-shipment-of-goods"></a>Confermare e registrare la spedizione delle merci
1. Fare clic su Conferma.
2. Nel riquadro azioni fare clic su Ricevimento.
3. Fare clic su Entrata prodotti.
    * Questa pagina è usata per registrare l'entrata prodotti per gli ordini fornitore ed anche per elaborare il reso delle merci al fornitore. Le righe di ordine con una quantità negativa significano che le merci devono essere restituite al fornitore ed il documento che può essere generato da questa pagina può essere usato come documento di trasporto per questo uso.   
    * Nel campo Quantità, selezionare Quantità ordinata per questo esempio.   Ciò assicura che la spedizione sia elaborata per la quantità ordinata completa con cui le righe di ordine erano state create.   
4. Digitare un valore nel campo Entrata prodotti.
    * Questo campo è usato per immettere un riferimento che sarà usato come giustificativo per il giornale di registrazione entrata prodotti.  
5. Fare clic su OK.
    * Le merci ora sono state registrate come spedite sull'ordine di reso acquisti e un giornale di registrazione entrata prodotti è stato creato. Potete usare l'azione Entrata prodotti per esaminare i giornali di registrazione creati con l'ordine fornitore e vedere che cosa è stato ricevuto o restituito e quando.  


