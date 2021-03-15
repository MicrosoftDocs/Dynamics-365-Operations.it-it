---
title: Stati inventario
description: Questo articolo descrive come utilizzare gli stati di magazzino per classificare e tenere traccia delle scorte.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, WHSInventStatus, WHSWarehouseStatusChange
audience: Application User
ms.reviewer: kamaybac
ms.custom: 21331
ms.assetid: b35f495f-de4f-48a0-9d09-4d06781d7650
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0c4cad56389c7a8fd6d37591c1ff335fff715707
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001826"
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

Per il lavoro in uscita, utilizzare articoli con uno stato inventario disponibile. Se si dispone di articoli con stato *Rotto* e la pianificazione generale viene eseguita su tali articoli, questi vengono considerati mancanti e l'inventario viene automaticamente rifornito.

Dopo aver impostato gli stati inventario, è possibile impostare lo stato inventario predefinito per un sito, un articolo e un magazzino. È inoltre possibile impostare uno stato predefinito per ordini acquisto, di trasferimento e cliente. Lo stato predefinito per gli ordini cliente e l'ordine di trasferimento in uscita non possono disporre del set di opzioni **Blocco scorte** su *Sì*. Lo stato inventario che viene ereditato dalle impostazioni predefinite in un sito, magazzino, articolo, ordine acquisto, di trasferimento o cliente può essere modificato utilizzando il dispositivo mobile oppure nella riga dell'ordine acquisto, cliente o di trasferimento.

Per pianificare la copertura per articoli con uno stato inventario disponibile, selezionare l'opzione **Piano di copertura per dimensione** per una dimensione di immagazzinamento nella pagina **Gruppi di dimensioni di immagazzinamento**. Quando si apre l'**Impostazione guidata copertura articoli**, gli articoli con uno stato disponibile vengono visualizzati nella pagina **Stato**. Per creare le impostazioni di copertura per tali articoli, selezionare l'ID dello stato inventario per gli stati di inventario disponibili. In base alle impostazioni di copertura, è possibile calcolare le richieste articoli e prevedere la domanda e l'offerta di articoli disponibili durante la pianificazione generale. Non è possibile creare un'impostazione copertura articoli con uno stato inventario bloccato. In alternativa, utilizzare la pagina **Copertura articoli** per creare o modificare i parametri di copertura articoli.

## <a name="change-inventory-statuses"></a>Cambiare gli stati dell'inventario

Puoi modificare gli stati dell'inventario utilizzando la pagina **Disponibili per ubicazione** o utilizzando l'attività periodica *Modifica stato inventario*.

- Quando si utilizza l'attività periodica *Modifica stato inventario* è possibile selezionare quali record includere e impostare l'attività da eseguire nel batch all'intervallo desiderato.
- Per modificare lo stato dell'inventario come processo ad hoc, andare alla pagina **Disponibili per ubicazione**, selezionare i record pertinenti, quindi selezionare il pulsante **Modifica stato inventario**.

> [!NOTE]
> La funzionalità *Modifica stato inventario degli articoli controllati dalle dimensioni di tracciabilità* consente di modificare lo stato dell'inventario degli articoli controllati dalle dimensioni di tracciabilità, inclusa la possibilità di aggiornare solo i record selezionati. Usare la [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per abilitare la funzione secondo necessità. Quando la funzione è abilitata, è possibile effettuare quanto segue:
>
> - Nella pagina **Disponibili per ubicazione** è possibile raggruppare le righe in base alle dimensioni visualizzate utilizzando il pulsante **Visualizza dimensioni** e modificare lo stato delle righe selezionate.
> - Nella pagina **Disponibili per ubicazione** è possibile selezionare più record e quindi utilizzare il pulsante **Modifica stato inventario** per cambiarli tutti contemporaneamente.
> - Nell'attività periodica **Modifica stato inventario** sarà possibile filtrare tenendo traccia delle dimensioni.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]