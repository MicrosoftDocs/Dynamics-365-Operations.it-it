---
title: Stati inventario
description: Questo articolo descrive come utilizzare gli stati di magazzino per classificare e tenere traccia delle scorte.
author: yufeihuang
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, WHSInventStatus, WHSWarehouseStatusChange
audience: Application User
ms.reviewer: kamaybac
ms.custom: 21331
ms.assetid: b35f495f-de4f-48a0-9d09-4d06781d7650
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: db15ad94355823c699e83c9e3f47660f813e1c9a
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103465"
---
# <a name="inventory-statuses"></a>Stati inventario

[!include [banner](../includes/banner.md)]

Questo articolo descrive come utilizzare gli stati di magazzino per classificare e tenere traccia delle scorte.

## <a name="set-up-and-use-inventory-statuses"></a>Impostare e utilizzare gli stati dell'inventario

È possibile utilizzare gli stati inventario per suddividere in categorie l'inventario. È quindi possibile avviare le azioni appropriate, ad esempio il rifornimento o il lavoro di stoccaggio.

Di seguito sono riportati alcuni esempi delle modalità con cui è possibile utilizzare gli stati inventario:

- Creare gli stati inventario per le scorte disponibili e le transazioni in entrata e in uscita.
- Specificare lo stato inventario predefinito per transazioni di magazzino.
- Modificare uno stato inventario per gli articoli prima dell'arrivo, durante l'arrivo o quando gli articoli vengono stoccati durante i movimenti scorte.
- Utilizzare uno stato inventario per determinare i prezzi degli articoli resi e pianificare la copertura articoli durante la pianificazione generale.

Uno stato inventario è una delle dimensioni nel gruppo di dimensioni di immagazzinamento. Gli stati inventario possono essere suddivisi in categorie come disponibili o non disponibili ed è possibile utilizzare il parametro **Blocco scorte** per bloccare gli articoli con stato inventario non disponibile. Gli articoli con uno stato bloccato vengono considerati inventario fisico e non possono essere utilizzati in un ordine di produzione, in un ordine cliente, in un ordine di trasferimento o in una transazione in uscita.

È possibile utilizzare gli articoli di magazzino con stati inventario disponibile o non disponibile per il lavoro in entrata. Ad esempio, si crea uno stato disponibile denominato *Pronto*, uno stato non disponibile denominato *Danneggiato* e uno stato bloccato denominato *Bloccato*. Quando si crea un ordine acquisto per articoli ricevuti o resi, se gli articoli sono danneggiati o rotti, è possibile modificare lo stato inventario di tali articoli in *Danneggiato* nella riga dell'ordine acquisto. Dopo la ricezione degli articoli, lo stato viene automaticamente impostato su *Bloccato*. Se si esegue la scansione degli articoli danneggiati con un dispositivo mobile, Supply Chain Management può utilizzare le direttive di ubicazione e i modelli di lavoro per mostrare le informazioni relative a un'ubicazione appropriata o a un gruppo di ubicazioni in cui è possibile stoccare tali articoli. Per i resi, viene creato un problema di tipo *Prenotazione* nella pagina **Transazioni di magazzino**.

Puoi specificare quali stati di magazzino sono stati di blocco tramite le caselle di controllo **Blocco scorte** nella pagina **Stati inventario**. Non è possibile utilizzare gli stati di magazzino come stati di blocco per ordini cliente, ordini di trasferimento o integrazioni di progetto.

Per il lavoro in uscita, puoi utilizzare diversi stati di inventario non di blocco per controllare per quale inventario prenotare. Se hai articoli con stato *Blocco* e la pianificazione generale viene eseguita su tali articoli, questi vengono considerati mancanti e l'inventario viene automaticamente rifornito. Inoltre, per gli ordini di controllo qualità associati al lavoro in uscita, non è possibile aggiornare lo **Stato dell'inventario** come parte della convalida dell'ordine di controllo qualità.

> [!NOTE]
> Non è possibile modificare lo stato dell'inventario nelle ubicazioni in cui esistono lavori aperti. Ad esempio, se si è effettuata l'entrata acquisto per un articolo, ma non lo stoccaggio, esisterebbe del lavoro aperto per l'ubicazione di ricezione e verrebbe visualizzato un errore se si tenta di modificare lo stato dell'inventario in quell'ubicazione. Il completamento o l'annullamento del lavoro correlato consentirebbe di modificare lo stato.
>
> Di solito, lo stato delle scorte disponibili relative al lavoro di magazzino aperto viene modificato solo dai lavoratori che utilizzano l'app per dispositivi mobili Gestione magazzino, ad esempio durante l'esecuzione di un processo di movimento.

Dopo aver impostato gli stati inventario, è possibile impostare lo stato inventario predefinito per un sito, un articolo e un magazzino. È inoltre possibile impostare uno stato predefinito per ordini acquisto, di trasferimento e cliente. Lo stato predefinito per gli ordini cliente e l'ordine di trasferimento in uscita non possono disporre del set di opzioni **Blocco scorte** su *Sì*. Lo stato inventario che viene ereditato dalle impostazioni predefinite in un sito, magazzino, articolo, ordine acquisto, di trasferimento o cliente può essere modificato utilizzando il dispositivo mobile oppure nella riga dell'ordine acquisto, cliente o di trasferimento.

Per pianificare la copertura per articoli con uno stato inventario disponibile, selezionare l'opzione **Piano di copertura per dimensione** per una dimensione di immagazzinamento nella pagina **Gruppi di dimensioni di immagazzinamento**. Quando si apre l'**Impostazione guidata copertura articoli**, gli articoli con uno stato disponibile vengono visualizzati nella pagina **Stato**. Per creare le impostazioni di copertura per tali articoli, selezionare l'ID dello stato inventario per gli stati di inventario disponibili. In base alle impostazioni di copertura, è possibile calcolare le richieste articoli e prevedere la domanda e l'offerta di articoli disponibili durante la pianificazione generale. Non è possibile creare un'impostazione copertura articoli con uno stato inventario bloccato. In alternativa, utilizzare la pagina **Copertura articoli** per creare o modificare i parametri di copertura articoli.

## <a name="change-inventory-statuses"></a>Cambiare gli stati dell'inventario

Puoi modificare gli stati dell'inventario utilizzando la pagina **Disponibili per ubicazione** o utilizzando l'attività periodica *Modifica stato inventario*.

- Quando si utilizza l'attività periodica *Modifica stato inventario* è possibile selezionare quali record includere e impostare l'attività da eseguire nel batch all'intervallo desiderato.
- Per modificare lo stato dell'inventario come processo ad hoc, andare alla pagina **Disponibili per ubicazione**, selezionare i record pertinenti, quindi selezionare il pulsante **Modifica stato inventario**.

> [!NOTE]
> La funzionalità *Modifica stato inventario degli articoli controllati dalle dimensioni di tracciabilità* consente di modificare lo stato dell'inventario degli articoli controllati dalle dimensioni di tracciabilità, inclusa la possibilità di aggiornare solo i record selezionati. A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria e non può essere disattivata. Se si sta eseguendo una versione precedente alla versione 10.0.25, gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Modifica lo stato di magazzino degli articoli controllati dalle dimensioni di tracciabilità* nell'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Se la funzionalità è abilitata, è possibile effettuare quanto segue:
>
> - Nella pagina **Disponibili per ubicazione** è possibile raggruppare le righe in base alle dimensioni visualizzate utilizzando il pulsante **Visualizza dimensioni** e modificare lo stato delle righe selezionate.
> - Nella pagina **Disponibili per ubicazione** è possibile selezionare più record e quindi utilizzare il pulsante **Modifica stato inventario** per cambiarli tutti contemporaneamente.
> - Nell'attività periodica **Modifica stato inventario** sarà possibile filtrare tenendo traccia delle dimensioni.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
