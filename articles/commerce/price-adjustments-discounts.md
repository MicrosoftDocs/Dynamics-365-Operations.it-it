---
title: Rettifiche prezzi e sconti
description: Questo articolo fornisce le informazioni sulle rettifiche prezzo e sugli sconti in Dynamics 365 Commerce.
author: scott-tucker
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 2d3e8025c5ab28296713634094694156f9addf62
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802793"
---
# <a name="price-adjustments-and-discounts"></a>Rettifiche prezzi e sconti

[!include [banner](includes/banner.md)]

Questo articolo fornisce le informazioni sulle rettifiche prezzo e sugli sconti in Dynamics 365 Commerce.

In Commerce, è possibile apportare rettifiche prezzo a prodotti e è inoltre possibile impostare gli sconti applicabili a una voce o a una transazione nel POS, in un ordine cliente del call center, o in un ordine online. Sia le rettifiche prezzo che gli sconti sono collegati a gruppi di prezzi. Per entrambe le rettifiche prezzo e sconti, è possibile specificare una singola data di inizio e la data di fine o un periodo di riproduzione, un codice di sconto e alcuni attributi aggiuntivi. 

Le rettifiche prezzo e gli sconti possono essere applicati ai prodotti, alle varianti o alle categorie. Se più di uno sconto viene applicato a un prodotto, un cliente può ricevere uno degli sconti o uno sconto combinato, a seconda della configurazione dello sconto. In Commerce viene automaticamente applicato lo sconto o la combinazione di sconti che forniscono il migliore prezzo al cliente. Quando si imposta una rettifica di prezzo o uno sconto, assicurarsi di confermare che i gruppi di prezzi vengono assegnati ai canali, ai cataloghi, le affiliazioni, o i programmi corretti di fedeltà che si desidera lo sconto da applicare. Inoltre, se si desidera generare automaticamente l'ID dello sconto, è possibile impostare le sequenze numeriche nel modulo **Parametri di commercio** prima di definire un nuovo sconto o una rettifica prezzo o sconto.

> [!NOTE]
> È possibile eliminare una rettifica prezzo o uno sconto. Tuttavia, le informazioni statistiche vengono perse.

## <a name="types-of-discounts"></a>Tipi di sconti

Sono ora disponibili molti tipi di sconti:

- **Sconto semplice**: una singola percentuale o importo.
- **Sconto la quantità** Uno sconto applicato quando due o più prodotti vengono acquistati.
- **Sconto gamma** - Viene applicato uno sconto quando si acquista una combinazione specifica di prodotti.
- **Sconto della soglia** - Uno sconto applicato quando il totale della transazione è più della quantità specificata.
- **Sconti basati sui metodi di pagamento** - Uno sconto che viene applicato quando il totale della transazione è superiore a un importo specificato e per il pagamento viene utilizzato un tipo di pagamento specifico (ad esempio, contanti, carta di credito o di debito).
- **Sconto sulla spedizione** - Uno sconto che viene applicato quando il totale della transazione è superiore a un importo specificato e una modalità di consegna specifica (ad esempio, spedizione in due giorni o spedizione notturna) viene utilizzata per l'ordine.

Sia le rettifiche prezzo che gli sconti sono collegati a gruppi di prezzi. I gruppi di prezzi possono quindi essere associati ai canali, i cataloghi, le affiliazioni e piani di fedeltà.


[!INCLUDE[footer-include](../includes/footer-banner.md)]