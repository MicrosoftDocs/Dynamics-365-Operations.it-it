---
title: Tenere traccia del costo medio corrente per dimensione inventariale
description: "A ogni articolo di magazzino è assegnato un gruppo di dimensioni inventariali. Pertanto, il prezzo di costo medio corrente di un articolo viene quindi calcolato sulla base della selezione di dimensioni inventariali di cui viene tenuta traccia da un punto di vista finanziario."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventOnhandItem
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: d9d92f436ce2e0757ce69f0dd5e11234e30c2df8
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="tracking-running-average-cost-per-inventory-dimension"></a>Tenere traccia del costo medio corrente per dimensione inventariale

[!include[banner](../includes/banner.md)]


A ogni articolo di magazzino è assegnato un gruppo di dimensioni inventariali. Pertanto, il prezzo di costo medio corrente di un articolo viene quindi calcolato sulla base della selezione di dimensioni inventariali di cui viene tenuta traccia da un punto di vista finanziario.

Sono disponibili tre tipi di dimensioni inventariali: prodotto, immagazzinamento e tracciabilità. Le dimensioni prodotto includono la configurazione, le dimensioni e il colore e ne viene sempre tenuta traccia finanziariamente. Le dimensioni di tracciabilità e di immagazzinamento includono il sito, il magazzino, la posizione, lo stato inventario, la targa, il numero batch e il numero di serie L'utente può scegliere di quali di esse tenere traccia finanziariamente. 

**Esempio 1** 

Se del gruppo di dimensione di immagazzinamento associato all'articolo viene tenuta traccia finanziariamente per magazzino, il prezzo di costo medio corrente verrà calcolato per ogni magazzino. Sono stati fatturati i seguenti ordini fornitore:

-   È stato fatturato un ordine acquisto per una quantità 2 a un prezzo di costo di 10,00 EUR per il magazzino GW.
-   È stato fatturato un ordine acquisto per una quantità 3 a un prezzo di costo di 12,00 EUR per il magazzino GW.
-   È stato fatturato un ordine acquisto per una quantità 5 a un prezzo di costo di 15,00 EUR per il magazzino MW.

Il prezzo di costo medio corrente per il magazzino GW è EUR 11,20 e il prezzo di costo medio corrente per il magazzino MW è 15,00 EUR. Se viene registrata una fattura ordine cliente per il magazzino GW, il valore delle scorte e il costo del venduto (prima della chiusura dell'inventario senza contrassegni) è di 11,20 EUR. Se viene registrato un altro ordine cliente per il magazzino MW, il valore delle scorte e il costo del venduto (prima della chiusura dell'inventario senza contrassegni) è di 15,00 EUR. 

**Esempio 2** Se del gruppo di dimensioni di immagazzinamento collegato all'articolo viene tenuta traccia finanziariamente dal magazzino e del gruppo di dimensioni di tracciabilità viene tenuta traccia finanziariamente per numero batch, il prezzo di costo medio corrente verrà calcolato per ogni batch. 

**Nota:** è consigliabile visualizzare sempre il prezzo di costo con tutte le dimensioni finanziarie di cui viene tenuta traccia. Sono stati fatturati i seguenti ordini fornitore:

-   È stato fatturato un ordine fornitore per una quantità 2 a un prezzo di costo di 10,00 EUR per il magazzino GW e il batch AAA.
-   È stato fatturato un ordine fornitore per una quantità 3 a un prezzo di costo di 12,00 EUR per il magazzino GW e il batch AAA.
-   È stato fatturato un ordine fornitore per una quantità 2 a un prezzo di costo di 15,00 EUR per il magazzino GW e il batch BBB.

Il prezzo di costo medio corrente per il magazzino GW e il batch AAA è EUR 11,20 e il prezzo di costo medio corrente per il magazzino GW e il batch BBB è 15,00 EUR.




