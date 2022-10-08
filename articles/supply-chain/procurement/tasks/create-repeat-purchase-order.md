---
title: Creare un ordine fornitore ripetuto
description: In questo articolo viene illustrato come creare un ordine fornitore (PO) ripetuto copiando le righe da documento di ordine fornitore precedente in un nuovo PO o un PO esistente.
author: GalynaFedorova
ms.date: 09/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, PurchCopying
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 335461d60fa0bc92e9711806c6e42643a3f75d02
ms.sourcegitcommit: 073604c07116e0a87f78ab2c76cb89ae83ebba3c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9608113"
---
# <a name="create-a-repeat-purchase-order"></a>Creare un ordine fornitore ripetuto

[!include [banner](../../includes/banner.md)]

In questo articolo viene illustrato come creare un ordine fornitore (PO) ripetuto copiando le righe da documento di ordine fornitore precedente in un nuovo PO o un PO esistente. Ci sono due metodi per creare gli ordini ripetuti. Potete usare le azioni disponibili al livello del documento dal riquadro azioni, o potete usare le azioni dei dettagli riga. Le azioni a livello del documento sono intese per creare un nuovo ordine fornitore aggiungendo le righe e le informazioni di intestazione da un altro ordine, mentre l'azione dei dettagli righe è principalmente per l'aggiunta delle righe ad un ordine esistente. L'esempio indicato in questa guida può essere utilizzato nella società di dati dimostrativi USMF. In genere questa attività viene svolta da un addetto acquisti.

## <a name="create-a-new-repeat-purchase-order"></a>Creare un nuovo ordine fornitore ripetuto

1. Nel riquadro di spostamento, vai a **Moduli \> Approvvigionamento \> Ordine fornitore \> Tutti gli ordini fornitore**. In primo luogo proveremo l'opzione per copiare le informazioni in un nuovo ordine.  
1. Selezionare **Nuovo**.
1. Nel campo **Conto fornitore** immettere `US-101`.
1. Selezionare **OK**.
1. Nel riquadro azioni, apri la scheda **Ordine d'acquisto** e, nel gruppo **Copia**, seleziona **Da tutto**. Viene visualizzata la finestra di dialogo **Copia da altri documenti**. Da qui, puoi copiare dagli ordini esistenti nel tuo ordine. Ci sono opzioni differenti per come le righe sono copiate e generi differenti di documenti da cui potete copiare. Esamineremo le opzioni per come le righe sono copiate in primo luogo.
1. Espandi la Scheda dettaglio **Parametri**.

    - Il campo **Fattore quantitativo** è utile se dovete usare una quantità che è differente che quella che è sull'ordine da cui state copiando. Per esempio, se volete ordinare due volte la quantità che è nelle righe da cui state copiando, dovreste scrivere "2" in questo campo e poi il sistema aggiungerà le righe dove la quantità originale è stata raddoppiata.  
    - Anche il campo **Inverti segno** supporta la modifica della quantità ordinata cambiando il segno della quantità per le righe di ordine che si aggiungono. Ciò può essere utile se dovete invertire una transazione, creando le righe di ordine che negano la transazione. Questa opzione è selezionata automaticamente quando la pagina viene aperta dall'azione **Crea nota di accredito**.  
    - L'opzione **Copia spese** permette di copiare le spese nel nuovo ordine dal documento da cui si stanno copiando le righe di ordine.  
    - L'opzione **Ricalcola il prezzo** usa i prezzi e gli sconti correnti piuttosto che copiarli dal documento da cui si stanno copiando altre informazioni.  
    - L'opzione **Copia esattamente** crea copie dei valori di tutti i campi sull'intestazione e sulle righe dell'ordine. Se questa opzione non è selezionata, i valori predefiniti verranno usati per molti dei campi relativi a fornitore e prodotti come se steste creando manualmente il nuovo ordine. Se imposti, ad esempio, **Copia esattamente** su *Sì* e copi un ordine che sovrascrive il conto di fatturazione predefinito per il fornitore, allora lo stesso conto di fatturazione verrà copiato nel tuo nuovo ordine. Se imposti **Copia esattamente** su *No*, il conto di fatturazione predefinito per il fornitore verrà utilizzato nel nuovo ordine. I valori per i seguenti campi vengono copiati quando **Copia esattamente** è impostata su *Sì*:
        - Lingua
        - Termini di pagamento
        - Metodo di pagamento
        - Specifiche pagamento
        - Gruppo di sequenze numeriche
        - Sconto di cassa
        - Percentuale sconto
        - Valuta
        - Termini di consegna
        - Modalità di consegna
        - Dimensione
        - Fascia IVA
        - Sostituisci IVA
        - Prezzi IVA inclusa
        - Trasporto
        - Porto
        - Procedura statistiche
        - ID modello
        - Nome consegna
        - Indirizzo postale
        - Riferimento
        - ID tabella riferimenti
    - L'opzione **Elimina righe acquisti** elimina tutte le righe dell'ordine fornitore che già esistono nell'ordine fornitore in cui si copia, prima dell'applicazione delle nuove righe. Usare con prudenza questa opzione, perché elimina tutte le linee righe esistenti senza ulteriore avvertimento.  
    - Se si usa l'opzione **Copia intestazione ordine**, non è necessario creare manualmente le informazioni dell'intestazione sul nuovo ordine. Questa opzione provocherà l'uso di valori predefiniti per i campi associati al fornitore. Se il documento da cui si sta copiando contiene valori non predefiniti da copiare, usare l'opzione **Copia esattamente**.
    - Ci sono origini documenti differenti da cui potete copiare e ciascuna ha una sezione separata in questa pagina. Per esempio, la sezione **Ordini fornitore** permette che copiate dagli ordini fornitore esistenti.  

1. Nella sezione **Ordini fornitore**, selezionare le righe da copiare negli Appunti. È inoltre possibile selezionare righe supplementari da altri ordini fornitore e copiarle nell'ordine. È inoltre possibile aggiungere righe da altri tipi di documenti di acquisto. I prossimi passaggi esaminano le opzioni differenti.  
1. Espandere la sezione **Conferma**. Qui potete selezionare le conferme di ordine fornitore da cui copiare. Le conferme di ordine fornitore sono identificate tramite l'ID giornale di registrazione acquisti associato o l'ID ordine fornitore.  
1. Espandere la sezione **Entrate prodotti**. Qui potete selezionare i giornali di registrazione entrata prodotti da cui copiare. I giornali di registrazione entrata prodotti sono identificati tramite il giustificativo di entrata prodotti o l'ID ordine fornitore.
1. Espandere la sezione **Fatture**. Qui potete selezionare le fatture fornitore da cui copiare. Le fatture sono identificate tramite il giustificativo della fattura o l'ID ordine fornitore.
1. Espandere la sezione **Righe o intestazioni selezionate da copiare**. Questa visualizzazione mostra un riepilogo di tutti i documenti e le righe che sono state selezionate per essere copiate nel vostro ordine.
1. Selezionare **OK**. Le righe selezionate sono state copiate nel nuovo ordine fornitore.

## <a name="copy-lines-to-an-existing-purchase-order"></a>Copiare righe in un ordine fornitore esistente  

Invece di copiare un ordine intero, è più comune creare un nuovo PO e completare le informazioni sull'intestazione del PO e poi copiare le singole righe da ordini esistenti.  

1. Selezionare **Riga ordine fornitore**.
1. Selezionare **Da tutto**. La pagina che si apre è identica a quella indicata prima, ma opzioni differenti sono selezionate quando viene aperta dalla visualizzazione righe ordine. Esaminare i parametri.
1. Espandere la sezione **Parametri**.

    - L'opzione **Elimina riga acquisti** non è selezionata. Ciò significa che potete copiare le nuove righe nel vostro ordine senza rimuovere le righe esistenti.
    - Anche l'opzione **Copia intestazione ordine** non è selezionata, poiché si stanno solo aggiungendo righe supplementari all'ordine.
    - Per questo esempio, si copiano le righe da un ordine fornitore esistente.

1. Selezionare la riga per l'ordine fornitore desiderato. Notare che la singola riga ordine presente in questo PO è anche selezionata.  
1. Selezionare **OK**. La riga supplementare di ordine è stata aggiunta al vostro ordine fornitore.  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]