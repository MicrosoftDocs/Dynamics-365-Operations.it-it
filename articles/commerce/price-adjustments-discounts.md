---
title: Rettifiche prezzi e sconti
description: Questo articolo fornisce le informazioni sulle rettifiche prezzo e sugli sconti in Dynamics 365 Commerce.
author: josaw1
ms.date: 06/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.industry: Retail
ms.search.form: RetailParameters, RetailPeriodicDiscount
ms.openlocfilehash: ff90df814d6930b5cf92772e430625943e0ae983
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279091"
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

> [!NOTE]
> Lo sconto gamma e lo sconto di soglia hanno proprietà denominate rispettivamente "Conteggio prodotti non scontati" e "Conteggio prodotti non scontati verso la soglia". Se queste proprietà sono abilitate, un articolo che non è idoneo per alcuno sconto può comunque contribuire a qualificare una transazione per lo sconto, ma l'articolo non idoneo non riceverà lo sconto. 
> 
> Ad esempio, se si crea uno sconto di gamma con due righe, A e B, in cui un cliente dovrebbe ottenere uno sconto del 10% su entrambi gli articoli, ma l'articolo A ha la configurazione "Impedisci tutti gli sconti" selezionata, in genere ciò impedirà all'articolo A di essere incluso nello sconto. Tuttavia, se la proprietà "Conteggio prodotti non scontati" è abilitata, l'articolo A può essere utilizzato per l'idoneità per lo sconto di gamma, ma lo sconto del 10% verrà applicato solo all'articolo B. Una logica simile si applica allo sconto di soglia. 
>
> Tuttavia, la proprietà "Conteggio prodotti non scontati verso la soglia" ha una funzionalità aggiuntiva rispetto alla proprietà "Conteggio prodotti non scontati" degli sconti di gamma. Se lo sconto di soglia è abilitato e c'è un articolo che ha uno sconto esistente che impedirebbe all'articolo di ottenere altri sconti, il prezzo pagato per questo articolo sarà idoneo per il raggiungimento della soglia, ma questo articolo non riceverà l'ulteriore sconto.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
