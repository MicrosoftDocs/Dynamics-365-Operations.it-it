---
title: Ordini cliente ibridi
description: "Ordine ibrido cliente è un singolo ordine, contenente i prodotti che possono essere eseguiti punto vendita per cliente nonché prodotti che verrà intrapresa o verranno spediti secondo momento."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 1ddfc050cef94f4a31f5858b84c89eadfa726b95
ms.lasthandoff: 03/31/2017


---

# <a name="hybrid-customer-orders"></a>Ordini cliente ibridi

Ordine ibrido cliente è un singolo ordine, contenente i prodotti che possono essere eseguiti punto vendita per cliente nonché prodotti che verrà intrapresa o verranno spediti secondo momento.

In Microsoft Dynamics 365 per le operazioni al dettaglio, è possibile selezionare si esegue tutti i prodotti o si effettuano i prodotti selezionati per un ordine cliente. Le righe di prodotti contrassegnate come effettuano fatturate automaticamente dopo che l'ordine è stato creato, contea) in modo analogo le stesse per un ordine che deve essere selezionato l'articolo prodotto dopo che l'ordine viene creato. Importo dovuto sugli ordini ibridi viene determinato sommando la percentuale di deposito nelle righe di prodotti di spedizione e di prelievo con l'importo totale delle righe di pagamento. Per gli ordini ibridi, vengono attivati alternativamente la modalità di ordine cliente e la modalità di carry cash e nel seguente modo:

-   Se tutti i prodotti nel carrello vengono impostati su ** eseguire la consegna **, l'ordine verrà trattato come transazione di carry cash and.
-   Se una di queste righe nel carrello verranno impostati su o ** prelievo ** o ** consegna della spedizione **, l'ordine verrà trattato come transazione degli ordini cliente.

Se una riga del carrello è selezionata e ** prelievo selezionato, ** ** la spedizione è selezionata, ** o ** Carry out ** selezionato è selezionato, nella riga specifica del carrello viene impostata con il metodo di consegna. In tal caso, il flusso downstream di un'operazione continua normalmente. Tuttavia, se ** il prelievo è selezionata, ** ** la spedizione è selezionata, ** o ** Carry out ** selezionato è selezionato senza una riga del carrello selezionata, una nuova pagina verrà aperto con l'elenco di tutte le righe carrello. In tale schermo, è possibile selezionare più righe contemporaneamente per l'impostazione del metodo di consegna. Quando si utilizza il metodo per selezionare le righe, un metodo precedente di consegna assegnato alla riga verrà ignorato.

<a name="see-also"></a>Vedere anche
--------

[Cliente ordina la panoramica customer-orders-overview.md] ()


