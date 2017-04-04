---
title: Rettificare i valori di costo delle scorte disponibili
description: "Utilizzare la pagina Rettifica delle scorte disponibili per rettificare il valore di costo delle quantità di scorte disponibili dopo l&quot;esecuzione di un processo di chiusura di inventario."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d1ef775c9783b975fd0f852dc7112506d3897605
ms.lasthandoff: 03/31/2017


---

# <a name="adjust-on-hand-inventory-cost-values"></a>Rettificare i valori di costo delle scorte disponibili

Utilizzare la pagina Rettifica delle scorte disponibili per rettificare il valore di costo delle quantità di scorte disponibili dopo l'esecuzione di un processo di chiusura di inventario.

È possibile utilizzare la pagina **Rettifica delle scorte disponibili** per rettificare il valore di costo delle quantità di scorte disponibili dopo l'esecuzione di un processo di chiusura di inventario. ** Nota: ** Aprire ** rettifica delle scorte disponibili ** la pagina, ** chiusura e rettifica ** nella pagina, selezionare il record di un processo di chiusura inventario completato e fare clic su ** rettifica ** &gt; ** disponibili **. **Esempio:** nel mese di febbraio sono state registrate le seguenti transazioni:

-   1° febbraio: entrata finanziaria in magazzino per una quantità pari a 2 al costo di 10,00 EUR
-   5 febbraio: entrata finanziaria in magazzino per una quantità pari a 1 al costo di 13,00 EUR
-   19 febbraio: uscita finanziaria da magazzino di una quantità pari a 1 al costo medio corrente di 11,00 EUR

L'articolo è stato impostato con il modello inventariale FIFO e la chiusura dell'inventario è stata eseguita il 28 febbraio. La transazione di uscita finanziaria di USD 11.00 verrà compensata a fronte dell'entrata finanziaria in del 1° febbraio e una rettifica di 1.00 EUR per. Le seguenti entrate in magazzino conterranno quindi quantità in magazzino aperte:

-   1 febbraio: quantità pari a 1 al costo di 10,00 EUR
-   5 febbraio: quantità pari a 1 al costo di 13,00 EUR

Per impostare il costo di questi due articoli a EUR 15,00, utilizzare l'opzione di rettifica delle disponibilità per aprire le quantità disponibili aperte all'ultimo periodo di chiusura dell'inventario. **Nota:** la data di registrazione della transazione di rettifica delle disponibilità sarà la data dell'ultima chiusura dell'inventario. Non è possibile modificare questa data.


