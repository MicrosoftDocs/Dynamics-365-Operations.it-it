---
title: Prenotare lo stesso batch per un ordine cliente
description: Questo articolo illustra come impostare un prodotto per consentire la prenotazione di scorte rispetto un unico batch di magazzino.
author: Henrikan
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d4f3ee5d99648155e663c9ad0849b0b9ae3f80e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576618"
---
# <a name="reserve-the-same-batch-for-a-sales-order"></a>Prenotare lo stesso batch per un ordine cliente

[!include [banner](../includes/banner.md)]

Questo articolo illustra come impostare un prodotto per consentire la prenotazione di scorte rispetto un unico batch di magazzino.

La prenotazione dello stesso batch consente di prenotare le scorte per una riga di ordine cliente da un unico lotto di magazzino. Ad esempio, un cliente che ordina carta da parati può richiedere che l'intero ordine venga coperto dallo stesso batch o lotto per evitare di ricevere rotoli non omogenei tra loro. Per impostare un prodotto per l'utilizzo della prenotazione dello stesso batch, è necessario che siano attive le seguenti impostazioni nei gruppi di modelli di articoli, nel gruppo di dimensioni di tracciabilità e nel gruppo di dimensioni di immagazzinamento:

- **Gruppi di modelli di articoli**: il gruppo di modelli di articoli deve avere i campi **Selezione stesso batch** e **Fabbisogno consolidato** selezionati nel gruppo di campi **Prenotazione** dei criteri di inventario.
- **Gruppi di dimensioni di tracciabilità**: il gruppo di dimensioni di tracciabilità deve avere il campo **Piano di copertura per dimensione** selezionato per numero batch.
- **Gruppi di dimensioni di immagazzinamento**: il gruppo di dimensioni di immagazzinamento deve avere il campo **Piano di copertura per dimensione** selezionato per **Sito** e **Magazzino**.

Quando si prenotano scorte di un prodotto in una riga ordine cliente impostata per la selezione stesso batch, il sistema tenta la prenotazione della quantità ordinata da un unico batch di magazzino. Vengono inoltre considerati eventuali requisiti specifici di attributi batch. Se la quantità non può essere coperta da un unico batch, viene visualizzata la pagina **Conflitto di stessa prenotazione batch**. In questa pagina vengono descritte le problematiche e anche le azioni che è possibile intraprendere per continuare con la prenotazione. Le seguenti condizioni possono impedire la prenotazione del batch:

- Il codice smaltimento batch presenta la voce **Blocca prenotazione** per le vendite contrassegnata come **Bloccata**.
- Il batch è scaduto in base alla data di scadenza e ai giorni di vendita del cliente eventualmente applicabili. L'articolo può comunque essere idoneo alla prenotazione se il gruppo di modelli di articoli per l'articolo è controllato in base alla data FEFO (First Expired, First Out) e se il campo della data di consumo consigliata è selezionato come criterio di prelievo.
- I giorni di durata a scaffale rimanenti per il batch sono insufficienti in base alla data di scadenza e alla data di consumo consigliata, più gli eventuali giorni di vendita del cliente.

Per gli articoli associati a un gruppo di dimensioni di immagazzinamento con **Usa processi di gestione magazzino** abilitato, è possibile prenotare specifici numeri di lotto utilizzando una gerarchia di prenotazione dove la dimensione di inventario del numero di lotto è definita sopra la dimensione della posizione. Questo tipo di gerarchia di prenotazione è anche noto come *Batch-above \[location\]*. La pagina **Prenotazione batch** per le righe ordine cliente e trasferimento consente inoltre di selezionare e prenotare più righe in base ai numeri di batch disponibili. Per ulteriori informazioni sulle operazioni da eseguire se si utilizza una gerarchia di prenotazione con la dimensione del numero di batch al di sotto della posizione (*Batch-below \[location\]*), vedi [Criteri flessibili di prenotazione delle dimensioni a livello di magazzino](../warehousing/flexible-warehouse-level-dimension-reservation.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
