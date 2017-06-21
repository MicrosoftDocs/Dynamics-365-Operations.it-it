---
title: Chiusura inventario
description: "Durante il processo per liquidare le transazioni in uscita con le transazioni in entrata, è possibile scegliere di aggiornare la contabilità generale in base alle rettifiche effettuate."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventClosing
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 61973
ms.assetid: c210c882-6849-4704-b78c-a777dd6cfdb6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9ff992be8a2a4f1cc0cd3146f138d12267bb74ee
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="inventory-close"></a>Chiusura inventario

[!include[banner](../includes/banner.md)]


Durante il processo per liquidare le transazioni in uscita con le transazioni in entrata, è possibile scegliere di aggiornare la contabilità generale in base alle rettifiche effettuate.

Il processo di chiusura dell'inventario  consente di compensare le transazioni in uscita a fronte delle transazioni in entrata in base al metodo di valutazione del magazzino selezionato nel gruppo di modelli di articoli dell'articolo. Nel processo di liquidazione, è possibile specificare la necessità di aggiornare la contabilità generale, in modo che rifletta le rettifiche effettuate. Finché tuttavia non si effettuerà la chiusura o il ricalcolo dell'inventario, le transazioni in uscita vengono registrate con il prezzo di costo medio corrente calcolato. 

Dopo la chiusura dell'inventario, non è più possibile effettuare la registrazione in periodi precedenti alla data di chiusura impostata, a meno che non si decida di stornare un processo di chiusura inventario completato. Ad esempio, se la chiusura dell'inventario viene eseguita per il periodo che termina il 31 gennaio, non è possibile registrare le transazioni con una data precedente a il 31 gennaio. 

Gli articoli del magazzino vengono assegnati a uno dei due tipi di inventario seguenti: articolo o assistenza. La chiusura dell'inventario esegue le stesse funzioni per entrambi i tipi. Tuttavia, per gli articoli di tipo Assistenza, le uscite verranno comunque compensate con le entrate. 

La frequenza di esecuzione del processo di chiusura dell'inventario varia a seconda della società. Tuttavia, il volume di transazioni dovrebbe agevolare la determinazione della frequenza di esecuzione della chiusura dell'inventario. La maggior parte delle società esegue di solito la chiusura dell'inventario nell'ambito delle procedure di chiusura e riconciliazione di fine mese.

## <a name="inventory-recalculation-and-the-general-ledger"></a>Ricalcolo dell'inventario e contabilità generale
Se nel corso di un mese o di un altro periodo di magazzino sono necessarie rettifiche magazzino, sarà possibile eseguire un ricalcolo anziché una chiusura dell'inventario. Con il ricalcolo vengono effettuate le rettifiche, ma non le compensazioni per le operazioni di magazzino. 

Durante il ricalcolo dell'inventario, le scorte disponibili vengono rettificate, le operazioni di magazzino vengono rettificate e i ricalcoli e le chiusure dell'inventario vengono eseguiti. Queste attività influiscono su qualsiasi conto CoGe che è collegato all'operazione di magazzino originale. 

**Esempio** 

Quando si crea un ordine fornitore da un ordine cliente, i conti CoGe utilizzati per l'ordine cliente originale vengono aggiornati. Anche se i conti CoGe per il gruppo di articoli assegnato a questo articolo sono stati modificati dopo la registrazione dell'ordine cliente, e un ricalcolo dell'inventario ha generato un importo di rettifica, quest'ultimo continuerà ad essere registrato nei conti CoGe originali e non nei nuovi conti CoGe assegnati all'articolo. 

Al termine dell'aggiornamento, è possibile esaminare il giustificativo contabile che è stato registrato a seguito dell'esecuzione di una di queste attività.

1.  Nella pagina **Chiusura e rettifica**, della scheda **Panoramica**, selezionare l'aggiornamento per la revisione.
2.  Fare clic su **Dettagli** e selezionare **Giustificativo**.

## <a name="effects-of-the-inventory-close-process-on-the-general-ledger"></a>Effetti del processo di chiusura dell'inventario sulla contabilità generale
Alcune delle attività che possono essere eseguite nella pagina **Chiusura e rettifica** determinano un aggiornamento della contabilità generale. Ad esempio, la contabilità generale viene aggiornata quando si apportano rettifiche delle scorte disponibili e delle transazioni di magazzino, si esegue il ricalcolo e la chiusura dell'inventario. 

Queste attività influiscono sui conti CoGe collegati all'operazione di magazzino originale. Se ad esempio un ordine cliente viene compensato con un ordine fornitore, i conti CoGe utilizzati per l'ordine cliente originale vengono rettificati. Ciò si verifica anche qualora i conti CoGe per il gruppo di articoli assegnato all'articolo sono stati modificati in seguito alla registrazione dell'ordine cliente. Dopo la creazione di un importo di compensazione da parte di una chiusura dell'inventario, tale importo verrà comunque registrato nei conti CoGe originali e non nei nuovi conti CoGe assegnati all'articolo. La contabilità generale può inoltre essere aggiornata se si storna una chiusura dell'inventario. 

**Note:**

-   La chiusura dell'inventario non è necessaria se si utilizza il metodo di valutazione Costo standard.
-   Prima di eseguire la procedura di chiusura, è possibile visualizzare un elenco di articoli che non possono essere liquidati durante l'aggiornamento.
-   È consigliabile eseguire la chiusura dell'inventario in fasce orarie non di punta, per distribuire più equamente le risorse di elaborazione.

## <a name="the-inventory-close-log"></a>Registro di chiusura inventario
Al termine del processo di chiusura dell'inventario, è possibile che un messaggio nel centro messaggi indichi che un prezzo di costo unitario potrebbe essere errato perché non è stato possibile liquidare completamente una transazione. 

Prima che venga visualizzato questo messaggio, il sistema segnala il numero di articolo e la transazione interessata. Nel messaggio viene comunicato che l'importo di costo utilizzato per questa transazione non è stato aggiornato a causa della chiusura dell'inventario. Il messaggio viene visualizzato quando non è possibile liquidare una transazione in uscita. 

Durante il processo di chiusura dell'inventario, il sistema verifica ogni dimensione finanziaria per determinare se vi sono più uscite che entrate fino a una data di chiusura specifica. Questo tipo di squilibrio può verificarsi se una transazione di magazzino da un ordine fornitore non è completamente registrata finanziariamente perché non è stata ancora ricevuta la fattura fornitore o un componente della distinta base (DBA) incluso in una produzione a un livello superiore non è registrato finanziariamente, ovvero non è stato calcolato il costo della produzione secondaria. In questo caso, la successiva chiusura non rettifica tutte le uscite in base al prezzo di costo corretto, in quanto non sono disponibili sufficienti informazioni relative alle entrate. 

Per ogni esecuzione della procedura di chiusura, il sistema indica se viene archiviato un registro che contiene avvisi e se tale registro può essere visualizzato. 

Se si ricevono numerosi avvisi nel messaggio, è consigliabile effettuare le seguenti operazioni:

-   Aggiornare finanziariamente le entrate.
-   Posticipare la data di chiusura.
-   Rivalutare le procedure aziendali.

In alcune circostanze, non è possibile risolvere in alcun modo i problemi segnalati dagli avvisi. Se i contrassegni, ad esempio, vengono utilizzati quando l'ordine fornitore contrassegnato è associato a una data finanziaria successiva alla data di chiusura, la data di chiusura non può essere modificata.

## <a name="reversing-a-completed-inventory-close"></a>Annullamento di una chiusura dell'inventario completata
Talvolta potrebbe essere necessario stornare una chiusura dell'inventario completata per riportare le liquidazioni allo stato in cui erano prima che venissero effettuate le rettifiche. Quando si storna una chiusura inventario completata, l'inventario viene riaperto per consentire la registrazione nel periodo coperto dalla chiusura inventario. È inoltre possibile apportare modifiche correlate nella contabilità generale. Una volta terminate le rettifiche, è possibile eseguire nuovamente la chiusura inventario per il periodo che si sta utilizzando. 

**Nota:** è possibile riaprire solo l'ultimo periodo di magazzino che è stato chiuso. Per stornare una chiusura dell'inventario precedente, è necessario stornare singolarmente ogni successiva chiusura dell'inventario, a partire dalla chiusura più recente.




