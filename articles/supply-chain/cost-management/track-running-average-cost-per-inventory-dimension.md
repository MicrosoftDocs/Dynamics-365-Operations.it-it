---
title: Tenere traccia del costo medio corrente per dimensione inventariale
description: A ogni articolo di magazzino è assegnato un gruppo di dimensioni inventariali. Pertanto, il prezzo di costo medio corrente di un articolo viene quindi calcolato sulla base della selezione di dimensioni inventariali di cui viene tenuta traccia da un punto di vista finanziario.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f8ade2981056e9e4f49726a8c01c45f77b8e151b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563091"
---
# <a name="track-running-average-cost-per-inventory-dimension"></a>Tenere traccia del costo medio corrente per dimensione inventariale

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

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



