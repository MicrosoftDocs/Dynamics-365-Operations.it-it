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
ms.search.form: EcoResStorageDimensionGroup, WHSInventStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 21331
ms.assetid: b35f495f-de4f-48a0-9d09-4d06781d7650
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e96ed6d01e22ee2cbc5b3b2be8168fbb43904c89
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212712"
---
# <a name="inventory-statuses"></a>Stati inventario

[!include [banner](../includes/banner.md)]

Questo articolo descrive come utilizzare gli stati di magazzino per classificare e tenere traccia delle scorte.

È possibile utilizzare gli stati inventario per suddividere in categorie l'inventario. È quindi possibile avviare le azioni appropriate, ad esempio il rifornimento o il lavoro di stoccaggio.

Di seguito sono riportati alcuni esempi delle modalità con cui è possibile utilizzare gli stati inventario:

-   Creare gli stati inventario per le scorte disponibili e le transazioni in entrata e in uscita.
-   Specificare lo stato inventario predefinito per transazioni di magazzino.
-   Modificare uno stato inventario per gli articoli prima dell'arrivo, durante l'arrivo o quando gli articoli vengono stoccati durante i movimenti scorte.
-   Utilizzare uno stato inventario per determinare i prezzi degli articoli resi e pianificare la copertura articoli durante la pianificazione generale.

Uno stato inventario è una delle dimensioni nel gruppo di dimensioni di immagazzinamento. Gli stati inventario possono essere suddivisi in categorie come disponibili o non disponibili ed è possibile utilizzare il parametro **Blocco scorte** per bloccare gli articoli con stato inventario non disponibile. Gli articoli con uno stato bloccato vengono considerati inventario fisico e non possono essere utilizzati in un ordine di produzione, in un ordine cliente, in un ordine di trasferimento o in una transazione in uscita.

È possibile utilizzare gli articoli di magazzino con stati inventario disponibile o non disponibile per il lavoro in entrata. Ad esempio, si crea uno stato disponibile denominato **Pronto**, uno stato non disponibile denominato **Danneggiato** e uno stato bloccato denominato **Bloccato**. Quando si crea un ordine acquisto per articoli ricevuti o resi, se gli articoli sono danneggiati o rotti, è possibile modificare lo stato inventario di tali articoli in **Danneggiato** nella riga dell'ordine acquisto. Dopo la ricezione degli articoli, lo stato viene automaticamente impostato su **Bloccato**. Se si esegue la scansione degli articoli danneggiati con un dispositivo mobile, Supply Chain Management può utilizzare le direttive di ubicazione e i modelli di lavoro per mostrare le informazioni relative a un'ubicazione appropriata o a un gruppo di ubicazioni in cui è possibile stoccare tali articoli. Per i resi, viene creato un problema di tipo **Prenotazione** nella pagina **Transazioni di magazzino**.

Per il lavoro in uscita, utilizzare articoli con uno stato inventario disponibile. Se si dispone di articoli con stato **Rotto** e la pianificazione generale viene eseguita su tali articoli, questi vengono considerati mancanti e l'inventario viene automaticamente rifornito.

Dopo aver impostato gli stati inventario, è possibile impostare lo stato inventario predefinito per un sito, un articolo e un magazzino. È inoltre possibile impostare uno stato predefinito per ordini acquisto, di trasferimento e cliente. Lo stato predefinito per gli ordini cliente e l'ordine di trasferimento in uscita non possono disporre del set di opzioni **Blocco scorte** su **Sì**. Lo stato inventario che viene ereditato dalle impostazioni predefinite in un sito, magazzino, articolo, ordine acquisto, di trasferimento o cliente può essere modificato utilizzando il dispositivo mobile oppure nella riga dell'ordine acquisto, cliente o di trasferimento.

Per pianificare la copertura per articoli con uno stato inventario disponibile, selezionare l'opzione **Piano di copertura per dimensione** per una dimensione di immagazzinamento nella pagina **Gruppi di dimensioni di immagazzinamento**. Quando si apre l'**Impostazione guidata copertura articoli**, gli articoli con uno stato disponibile vengono visualizzati nella pagina **Stato**. Per creare le impostazioni di copertura per tali articoli, selezionare l'ID dello stato inventario per gli stati di inventario disponibili. In base alle impostazioni di copertura, è possibile calcolare le richieste articoli e prevedere la domanda e l'offerta di articoli disponibili durante la pianificazione generale. Non è possibile creare un'impostazione copertura articoli con uno stato inventario bloccato. In alternativa, utilizzare la pagina **Copertura articoli** per creare o modificare i parametri di copertura articoli.
