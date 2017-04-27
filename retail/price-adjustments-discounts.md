---
title: Rettifiche prezzi e sconti
description: Questo articolo fornisce le informazioni sulle rettifiche prezzo e sugli sconti in Vendita al dettaglio e commercio in Microsoft Dynamics 365 for Operations.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 01f249cbdabc6febf23dcd7103d4587cecdaad08
ms.lasthandoff: 03/31/2017


---

# <a name="price-adjustments-and-discounts"></a>Rettifiche prezzi e sconti

[!include[banner](includes/banner.md)]


Questo articolo fornisce le informazioni sulle rettifiche prezzo e sugli sconti in Vendita al dettaglio e commercio in Microsoft Dynamics 365 for Operations.

In Dynamics 365 for Operations - Retail, è possibile apportare rettifiche prezzo a prodotti e è inoltre possibile impostare gli sconti applicabili a una voce o a una transazione nel POS, in un ordine cliente del call center, o in un ordine online. Sia le rettifiche prezzo che gli sconti sono collegati a gruppi di prezzi. Per entrambe le rettifiche prezzo e sconti, è possibile specificare una singola data di inizio e la data di fine o un periodo di riproduzione, un codice di sconto e alcuni attributi aggiuntivi. Le rettifiche prezzo e gli sconti possono essere applicati ai prodotti, alle varianti o alle categorie. Se più di uno sconto viene applicato a un prodotto, un cliente può ricevere uno degli sconti o uno sconto combinato, a seconda della configurazione dello sconto. In Dynamics 365 for Operations viene automaticamente applicato lo sconto o la combinazione di sconti che forniscono il migliore prezzo al cliente. Quando si imposta una rettifica di prezzo o uno sconto, assicurarsi di confermare che i gruppi di prezzi vengono assegnati ai canali, ai cataloghi, le affiliazioni, o i programmi corretti di fedeltà che si desidera lo sconto da applicare. Inoltre, se si desidera generare automaticamente l'ID dello sconto, è possibile impostare le sequenze numeriche nel modulo **Parametri vendita al dettaglio** prima di definire un nuovo sconto o una rettifica prezzo o sconto. **Nota:** è possibile eliminare una rettifica prezzo o uno sconto. Tuttavia, le informazioni statistiche vengono perse.

### <a name="types-of-discounts"></a>Tipi di sconti

Sono ora disponibili quattro tipi di sconti vendita al dettaglio:

-   **Sconto semplice**: una singola percentuale o importo.
-   **Sconto la quantità** Uno sconto applicato quando due o più prodotti vengono acquistati.
-   **Sconto gamma** - Viene applicato uno sconto quando si acquista una combinazione specifica di prodotti.
-   **Sconto della soglia** - Uno sconto applicato quando il totale della transazione è più della quantità specificata.

Sia le rettifiche prezzo che gli sconti sono collegati a gruppi di prezzi. I gruppi di prezzi possono quindi essere associati ai canali, i cataloghi, le affiliazioni e piani di fedeltà.




