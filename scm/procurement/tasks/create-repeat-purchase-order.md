--- 
title: Creare un ordine fornitore ripetuto
description: Questa procedura vi mostra come creare un ordine fornitore (PO) ripetuto copiando le righe da documento di ordine fornitore precedente in un nuovo PO o un PO esistente.
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 406a59ffdbca4e7a5de54b4cb283a9a46c977ed1
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-repeat-purchase-order"></a>Creare un ordine fornitore ripetuto

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa procedura vi mostra come creare un ordine fornitore (PO) ripetuto copiando le righe da documento di ordine fornitore precedente in un nuovo PO o un PO esistente. Ci sono due metodi per creare gli ordini ripetuti. Potete usare le azioni disponibili al livello del documento dal riquadro azioni, o potete usare le azioni dei dettagli riga. Le azioni a livello del documento principalmente sono intese per creare un nuovo ordine fornitore aggiungendo le righe e le informazioni di intestazione da un altro ordine, mentre l'azione dei dettagli righe è principalmente per l'aggiunta delle righe ad un ordine esistente. L'esempio indicato in questa guida può essere utilizzato nella società di dati dimostrativi USMF. In genere questa attività viene svolta da un addetto acquisti.


## <a name="create-a-new-repeat-purchase-order"></a>Creare un nuovo ordine fornitore ripetuto
1. Andare ad Approvvigionamento > Ordini fornitore> Tutti gli ordini fornitore.
    * In primo luogo proveremo l'opzione per copiare le informazioni in un nuovo ordine.  
2. Fare clic su Nuovo.
3. Digitare US-101 nel campo Conto fornitore.
4. Fare clic su OK.
5. Nel riquadro azioni, fare clic su Ordine fornitore.
6. Fare clic su Da tutto.
    * Questa è la pagina da cui potete copiare dagli ordini attuali al vostro ordine. Ci sono opzioni differenti per come le righe sono copiate e generi differenti di documenti da cui potete copiare. Esamineremo le opzioni per come le righe sono copiate in primo luogo.   
7. Espandere la sezione Parametri.
    * Il campo Fattore quantitativo è utile se dovete usare una quantità che è differente che quella che è sull'ordine da cui state copiando. Per esempio, se volete ordinare due volte la quantità che è nelle righe da cui state copiando, dovreste scrivere '2' in questo campo e poi il sistema aggiungerà le righe dove la quantità originale è stata raddoppiata.  
    * Anche il campo Inverti segno supporta la modifica della quantità ordinata cambiando il segno della quantità per le righe di ordine che si aggiungono. Ciò può essere utile se dovete invertire una transazione, creando le righe di ordine che negano la transazione. Questa opzione è selezionata automaticamente quando la pagina viene aperta dall'azione Crea nota di accredito.  
    * L'opzione Copia spese permette che copiate le spese al vostro nuovo ordine dal documento da cui state copiando le righe di ordine.  
    * L'opzione Ricalcola il prezzo usa i prezzi e gli sconti correnti piuttosto che copiarli dal documento da cui state copiando altre informazioni.  
    * L'opzione Copia esattamente crea una copia esatta dei valori in tutti i campi sull'intestazione e sulle righe del documento di ordine. Se questa opzione non è selezionata, i valori predefiniti sono usati per molti dei campi relativi a fornitore e prodotti come se steste creando manualmente il nuovo ordine. Per esempio, se l'ordine da cui state copiando avesse sostituito il Conto fattura predefinito del fornitore, lo stesso Conto fattura verrebbe copiato nel vostro ordine. Se non selezionaste l'opzione Copia esattamente, il conto fattura predefinito per il fornitore verrebbe invece usato nel vostro ordine.  
    * L'opzione Elimina righe acquisti elimina tutte le righe dell'ordine fornitore che già esistono nell'ordine fornitore in cui state copiando, prima dell'applicazione delle nuove righe. Usare con prudenza questa opzione, perché elimina tutte le linee righe esistenti senza ulteriore avvertimento.  
    * Se usate l'opzione Copia intestazione ordine, non dovete creare manualmente le informazioni dell'intestazione sul vostro nuovo ordine. Si noti che questa opzione provocherà l'uso di valori predefiniti per i campi associati al fornitore. Se il documento da cui state copiando ha valori non predefiniti che volete copiare, usate anche l'opzione Copia esattamente.  
8. Comprimere la sezione Parametri.
    * Ci sono origini documenti differenti da cui potete copiare e ciascuna ha una sezione separata in questa pagina. Per esempio, la sezione Ordini fornitore permette che copiate dagli ordini fornitore esistenti.  
9. Fare clic sulla riga dell'ordine fornitore con ID 00015. 
10. Selezionare la riga facendo clic sulla casella di controllo.
11. Deselezionare la casella di controllo della riga in modo da non copiarla nel vostro ordine.
    * Ora 4 righe sono state selezionate per essere copiate nell'ordine fornitore. È inoltre possibile selezionare righe supplementari da altri ordini fornitore e copiarle nel vostro ordine. È inoltre possibile aggiungere righe da altri generi di documenti dell'acquisto. I prossimi passaggi esaminano le opzioni differenti.  
12. Comprimere la sezione Ordini fornitore.
13. Espandere la sezione Conferma.
    * Qui potete selezionare le conferme di ordine fornitore da cui copiare. Le conferme di ordine fornitore sono identificate tramite l'ID giornale di registrazione acquisti associato o l'ID ordine fornitore.  
14. Comprimere la sezione Conferma.
15. Espandere la sezione Entrate prodotti.
    * Qui potete selezionare i giornali di registrazione entrata prodotti da cui copiare. I giornali di registrazione entrata prodotti sono identificati tramite il giustificativo di entrata prodotti o l'ID ordine fornitore.   
16. Comprimere la sezione Entrate prodotti.
17. Espandere la sezione Fatture.
    * Qui potete selezionare le fatture fornitore da cui copiare. Le fatture sono identificate tramite il giustificativo della fattura o l'ID ordine fornitore.   
18. Comprimere la sezione Fatture.
19. Espandere la sezione Righe o intestazioni selezionate da copiare.
    * Questa visualizzazione mostra un riepilogo di tutti i documenti e le righe che sono state selezionate per essere copiate nel vostro ordine.   
20. Comprimere la sezione Righe o intestazioni selezionate da copiare.
21. Fare clic su OK.
    * Le 4 righe selezionate sono state copiate nel nuovo ordine fornitore.   

## <a name="copy-lines-to-an-existing-purchase-order"></a>Copiare righe in un ordine fornitore esistente
    * Invece di copiare un ordine intero, è più comune creare un nuovo PO e completare le informazioni sull'intestazione del PO e poi copiare le singole righe da ordini esistenti.  
1. Fare clic su Riga ordine fornitore.
2. Fare clic su Da tutto.
    * La pagina che si apre è identica a quella indicata prima, ma opzioni differenti sono selezionate quando viene aperta dalla visualizzazione righe ordine. Esaminiamo i parametri.   
3. Espandere la sezione Parametri.
    * L'opzione Elimina riga acquisti non è selezionata. Ciò significa che potete copiare le nuove righe nel vostro ordine senza rimuovere le righe esistenti.   
    * Anche l'opzione Copia intestazione ordine non è selezionata, poichè stiamo solo aggiungendo righe supplementari all'ordine.   
4. Comprimere la sezione Parametri.
    * Per questo esempio, copieremo le righe da un ordine fornitore esistente.   
5. Fare clic sulla riga dell'ordine fornitore con ID 00034. 
6. Selezionare la riga facendo clic sulla casella di controllo.
    * Notare che la singola riga ordine che è su questo PO è anche selezionata.  
7. Fare clic su OK.
    * La riga supplementare di ordine è stata aggiunta al vostro ordine fornitore.  


