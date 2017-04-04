---
title: Prenotazione dello stesso batch a un ordine cliente
description: Questo articolo illustra come impostare un prodotto per consentire la prenotazione di scorte rispetto un unico batch di magazzino.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: e9f48e6e057517bb7632e8c855f4439c446f3d30
ms.lasthandoff: 03/31/2017


---

# <a name="reserve-the-same-batch-for-a-sales-order"></a>Prenotazione dello stesso batch a un ordine cliente

Questo articolo illustra come impostare un prodotto per consentire la prenotazione di scorte rispetto un unico batch di magazzino.

La prenotazione dello stesso batch consente di prenotare le scorte per una riga di ordine cliente da un unico lotto di magazzino. Ad esempio, un cliente che ordina carta da parati può richiedere che l'intero ordine venga coperto dallo stesso batch o lotto per evitare di ricevere rotoli non omogenei tra loro. Per impostare un prodotto per l'utilizzo della prenotazione dello stesso batch, è necessario che siano attive le seguenti impostazioni nei gruppi di modelli di articoli, nel gruppo di dimensioni di tracciabilità e nel gruppo di dimensioni di immagazzinamento:

-   **Gruppi di modelli di articoli**: il gruppo di modelli di articoli deve avere i campi **Selezione stesso batch** e **Fabbisogno consolidato** selezionati nel gruppo di campi **Prenotazione** dei criteri di inventario.
-   **Gruppi di dimensioni di tracciabilità**: il gruppo di dimensioni di tracciabilità deve avere il campo **Piano di copertura per dimensione** selezionato per numero batch.
-   **Gruppi di dimensioni di immagazzinamento**: il gruppo di dimensioni di immagazzinamento deve avere il campo **Piano di copertura per dimensione** selezionato per **Sito** e **Magazzino**.

Quando si prenotano scorte di un prodotto in una riga ordine cliente impostata per la selezione stesso batch, in Microsoft Dynamics 365 for Operations viene tentata la prenotazione della quantità ordinata da un unico batch di magazzino. Vengono inoltre considerati eventuali requisiti specifici di attributi batch. Se la quantità non può essere coperta da un unico batch, viene visualizzata la pagina **Conflitto di stessa prenotazione batch**. In questa pagina vengono descritte le problematiche e anche le azioni che è possibile intraprendere per continuare con la prenotazione. Le seguenti condizioni possono impedire la prenotazione del batch:

-   Il codice smaltimento batch presenta la voce **Blocca prenotazione** per le vendite contrassegnata come **Bloccata**.
-   Il batch è scaduto in base alla data di scadenza e ai giorni di vendita del cliente eventualmente applicabili. L'articolo può comunque essere idoneo alla prenotazione se il gruppo di modelli di articoli per l'articolo è controllato in base alla data FEFO (First Expired, First Out) e se il campo della data di consumo consigliata è selezionato come criterio di prelievo.
-   I giorni di durata a scaffale rimanenti per il batch sono insufficienti in base alla data di scadenza e alla data di consumo consigliata, più gli eventuali giorni di vendita del cliente.



