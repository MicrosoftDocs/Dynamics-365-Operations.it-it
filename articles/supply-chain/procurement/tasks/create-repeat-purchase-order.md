---
title: Creare un ordine fornitore ripetuto
description: In questo argomento viene illustrato come creare un ordine fornitore (PO) ripetuto copiando le righe da documento di ordine fornitore precedente in un nuovo PO o un PO esistente.
author: RichardLuan
manager: tfehr
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, PurchCopying
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 65eb801fb363ce2484dcce4d086d1b2b5ad3388f
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017344"
---
# <a name="create-a-repeat-purchase-order"></a>Creare un ordine fornitore ripetuto

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come creare un ordine fornitore (PO) ripetuto copiando le righe da documento di ordine fornitore precedente in un nuovo PO o un PO esistente. Ci sono due metodi per creare gli ordini ripetuti. Potete usare le azioni disponibili al livello del documento dal riquadro azioni, o potete usare le azioni dei dettagli riga. Le azioni a livello del documento principalmente sono intese per creare un nuovo ordine fornitore aggiungendo le righe e le informazioni di intestazione da un altro ordine, mentre l'azione dei dettagli righe è principalmente per l'aggiunta delle righe ad un ordine esistente. L'esempio indicato in questa guida può essere utilizzato nella società di dati dimostrativi USMF. In genere questa attività viene svolta da un addetto acquisti.


## <a name="create-a-new-repeat-purchase-order"></a>Creare un nuovo ordine fornitore ripetuto
1. Passare ad **pannello di navigazione > Moduli > Approvvigionamento > Ordini fornitore > Tutti gli ordini fornitore**. In primo luogo proveremo l'opzione per copiare le informazioni in un nuovo ordine.  
2. Selezionare **Nuovo**.
3. Nel campo **Conto fornitore** immettere `US-101`.
4. Selezionare **OK**.
5. Nel riquadro azioni, selezionare **Ordine fornitore**.
6. Selezionare **Da tutto**. Questa è la pagina da cui potete copiare dagli ordini attuali al vostro ordine. Ci sono opzioni differenti per come le righe sono copiate e generi differenti di documenti da cui potete copiare. Esamineremo le opzioni per come le righe sono copiate in primo luogo. 
7. Espandere la sezione **Parametri**.

    - Il campo **Fattore quantitativo** è utile se dovete usare una quantità che è differente che quella che è sull'ordine da cui state copiando. Per esempio, se volete ordinare due volte la quantità che è nelle righe da cui state copiando, dovreste scrivere "2" in questo campo e poi il sistema aggiungerà le righe dove la quantità originale è stata raddoppiata.  
    - Anche il campo **Inverti segno** supporta la modifica della quantità ordinata cambiando il segno della quantità per le righe di ordine che si aggiungono. Ciò può essere utile se dovete invertire una transazione, creando le righe di ordine che negano la transazione. Questa opzione è selezionata automaticamente quando la pagina viene aperta dall'azione **Crea nota di accredito**.  
    - L'opzione **Copia spese** permette di copiare le spese nel nuovo ordine dal documento da cui si stanno copiando le righe di ordine.  
    - L'opzione **Ricalcola il prezzo** usa i prezzi e gli sconti correnti piuttosto che copiarli dal documento da cui si stanno copiando altre informazioni.  
    - L'opzione **Copia esattamente** crea una copia esatta dei valori in tutti i campi sull'intestazione e sulle righe del documento di ordine. Se questa opzione non è selezionata, i valori predefiniti sono usati per molti dei campi relativi a fornitore e prodotti come se steste creando manualmente il nuovo ordine. Per esempio, se l'ordine da cui si sta copiando sostituisce il conto fattura predefinito del fornitore, lo stesso conto fattura viene copiato nell'ordine. Se non si seleziona l'opzione **Copia esattamente**, il conto fattura predefinito per il fornitore viene usato nell'ordine.  
    - L'opzione **Elimina righe acquisti** elimina tutte le righe dell'ordine fornitore che già esistono nell'ordine fornitore in cui si copia, prima dell'applicazione delle nuove righe. Usare con prudenza questa opzione, perché elimina tutte le linee righe esistenti senza ulteriore avvertimento.  
    - Se si usa l'opzione **Copia intestazione ordine**, non è necessario creare manualmente le informazioni dell'intestazione sul nuovo ordine. Si noti che questa opzione provocherà l'uso di valori predefiniti per i campi associati al fornitore. Se il documento da cui si sta copiando contiene valori non predefiniti da copiare, usare l'opzione **Copia esattamente**.   
    - Ci sono origini documenti differenti da cui potete copiare e ciascuna ha una sezione separata in questa pagina. Per esempio, la sezione **Ordini fornitore** permette che copiate dagli ordini fornitore esistenti.  

8. Nella sezione **Ordini fornitore**, selezionare le righe da copiare negli Appunti. È inoltre possibile selezionare righe supplementari da altri ordini fornitore e copiarle nell'ordine. È inoltre possibile aggiungere righe da altri tipi di documenti di acquisto. I prossimi passaggi esaminano le opzioni differenti.  
9. Espandere la sezione **Conferma**. Qui potete selezionare le conferme di ordine fornitore da cui copiare. Le conferme di ordine fornitore sono identificate tramite l'ID giornale di registrazione acquisti associato o l'ID ordine fornitore.  
10. Espandere la sezione **Entrate prodotti**. Qui potete selezionare i giornali di registrazione entrata prodotti da cui copiare. I giornali di registrazione entrata prodotti sono identificati tramite il giustificativo di entrata prodotti o l'ID ordine fornitore.   
11. Espandere la sezione **Fatture**. Qui potete selezionare le fatture fornitore da cui copiare. Le fatture sono identificate tramite il giustificativo della fattura o l'ID ordine fornitore.   
12. Espandere la sezione **Righe o intestazioni selezionate da copiare**. Questa visualizzazione mostra un riepilogo di tutti i documenti e le righe che sono state selezionate per essere copiate nel vostro ordine.   
13. Selezionare **OK**. Le righe selezionate sono state copiate nel nuovo ordine fornitore.   

## <a name="copy-lines-to-an-existing-purchase-order"></a>Copiare righe in un ordine fornitore esistente  

Invece di copiare un ordine intero, è più comune creare un nuovo PO e completare le informazioni sull'intestazione del PO e poi copiare le singole righe da ordini esistenti.  

1. Selezionare **Riga ordine fornitore**.
2. Selezionare **Da tutto**. La pagina che si apre è identica a quella indicata prima, ma opzioni differenti sono selezionate quando viene aperta dalla visualizzazione righe ordine. Esaminare i parametri.   
3. Espandere la sezione **Parametri**.

    - L'opzione **Elimina riga acquisti** non è selezionata. Ciò significa che potete copiare le nuove righe nel vostro ordine senza rimuovere le righe esistenti.   
    - Anche l'opzione **Copia intestazione ordine** non è selezionata, poiché si stanno solo aggiungendo righe supplementari all'ordine.   
    - Per questo esempio, si copiano le righe da un ordine fornitore esistente.   

4. Selezionare la riga per l'ordine fornitore desiderato. Notare che la singola riga ordine presente in questo PO è anche selezionata.  
5. Selezionare **OK**. La riga supplementare di ordine è stata aggiunta al vostro ordine fornitore.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]