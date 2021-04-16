---
title: Ordini cliente ibridi
description: Un ordine cliente ibrido è un ordine singolo che contiene prodotti che possono essere ritirati nel punto vendita dal cliente e prodotti che verranno ritirati o spediti in un secondo momento.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6357c034059523f83ba05a1da53cae691ef74758
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798939"
---
# <a name="hybrid-customer-orders"></a>Ordini cliente ibridi

[!include [banner](includes/banner.md)]

Un ordine cliente ibrido è un ordine singolo che contiene prodotti che possono essere ritirati nel punto vendita dal cliente e prodotti che verranno ritirati o spediti in un secondo momento.

In Commefce, è possibile selezionare o trasportare tutti i prodotti o trasportare prodotti selezionati per un ordine cliente. Le righe di prodotti contrassegnate come trasporto vengono fatturate automaticamente dopo la creazione dell'ordine, in modo analogo è lo stesso per un ordine che deve essere selezionato dopo che l'ordine è stato creato. L'importo dovuto sugli ordini ibridi viene determinato sommando la percentuale di deposito nelle righe prelievo e spedizione di prodotti con l'importo totale delle righe di trasporto. Per gli ordini ibridi, il sistema passa tra la modalità ordine cliente e la modalità cash-and-carry nel seguente modo:

- Se tutti i prodotti nel carrello vengono impostati sull'**esecuzione consegna**, l'ordine verrà trattato come transazione cash-and-carry.
- Se una o tutte le righe nel carrello vengono impostate su **Prelievo** o **spedizione consegna**, l'ordine verrà gestito come transazione ordine cliente.

Se è selezionata una riga del carrello ed è selezionata l'opzione **Preleva selezionati**, **Spedizione selezionata** o **Esecuzione selezionata**, solo la riga del carrello specifica verrà impostata con quel metodo di consegna. In tal caso, il flusso downstream dell'operazione continua normalmente. Se invece l'opzione **Preleva selezionati**, **Spedizione selezionata** o **Esecuzione selezionata** è selezionata ma non è selezionata alcune riga del carrello, verrà visualizzata una nuova pagina con l'elenco di tutte le righe del carrello. In questa schermata è possibile selezionare più righe contemporaneamente per l'impostazione del metodo di consegna. Quando si utilizza tale metodo per selezionare le righe, qualsiasi metodo di consegna precedente assegnato alla riga verrà ignorato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Ordini cliente in Modern POS (MPOS)](customer-orders-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]