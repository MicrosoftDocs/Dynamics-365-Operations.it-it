---
title: Ammortizzare i costi costanti per un articolo prodotto
description: "I costi costanti di un articolo prodotto riflettono i tempi di impostazione delle operazioni e i componenti con una quantità o un importo di scarto costante."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcTable, BOMCalcTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 274503
ms.assetid: 535ab25d-a031-4e8c-84ec-478f2987a1ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 75c0f5bcff0aae63aa8c7dae9b0767f8c7e6a81c
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="amortize-constant-costs-for-a-manufactured-item"></a>Ammortizzare i costi costanti per un articolo prodotto

[!include [banner](../includes/banner.md)]

I costi costanti di un articolo prodotto riflettono i tempi di impostazione delle operazioni e i componenti con una quantità o un importo di scarto costante. 

Il concetto di dimensioni lotto per determinazione dei costi viene utilizzato per ammortizzare questi costi costanti nel costo calcolato di un articolo prodotto. Questo concetto può avere diversi sinonimi, tra cui dimensioni lotto per contabilità. Anche il concetto di costi costanti di ammortamento può avere diversi sinonimi, tra cui costi costanti proporzionali.

La quantità di dimensioni lotto per determinazione dei costi per un articolo prodotto viene utilizzata nel calcolo DBA. La quantità dipende dalla modalità di avvio ed esecuzione del calcolo DBA, come illustrato di seguito:

-   Quantità di calcolo predefinita nel calcolo DBA di un articolo: la quantità ordine standard di un articolo per il magazzino funge da dimensioni lotto per determinazione dei costi, ma il valore predefinito potrebbe essere di una quantità maggiore che riflette il multiplo della quantità dell'ordine dell'articolo. La quantità dell'ordine standard dell'articolo e il multiplo possono essere definiti all'interno delle impostazioni di ordine predefinite o delle impostazioni di ordine specifiche del sito.
-   Quantità di calcolo specificata nel calcolo DBA di un articolo: la quantità di calcolo specificata funge da dimensioni lotto per determinazione dei costi per l'articolo. La quantità di calcolo utilizza inizialmente la quantità ordine standard dell'articolo, ma il valore predefinito può essere sostituito manualmente. La quantità di calcolo specificata rappresenta le dimensioni lotto per determinazione dei costi per l'articolo specificato e per i componenti prodotti con un tipo di riga DBA di produzione, in quanto si presume che il componente verrà prodotto nella quantità esatta. Le dimensioni lotto per determinazione dei costi per altri componenti prodotti con un tipo di riga DBA di articolo corrisponderanno alla quantità ordine standard.
-   Quantità di calcolo Produzione su ordine specificata nel calcolo DBA di un articolo: la quantità di calcolo specificata funge da dimensioni lotto per determinazione dei costi per l'articolo e i relativi componenti prodotti quando i calcoli DBA utilizzano come modalità di esplosione Produzione su ordine. Si presume che i componenti fabbricati verranno prodotti nella quantità esatta, proprio come un componente fabbricato con un tipo di riga DBA di produzione.
-   Quantità di calcolo in un calcolo DBA specifico dell'ordine: un calcolo DBA specifico dell'ordine può essere eseguito per una voce su un ordine cliente, un'offerta di vendita o un ordine di assistenza. La quantità di calcolo specificata utilizza la quantità riportata nella voce di origine, ma la quantità predefinita può essere sovrascritta. È possibile scegliere se il calcolo DBA specifico dell'ordine debba utilizzare una modalità di esplosione Produzione su ordine o multilivello.

L'importo calcolato dei costi costanti ammortizzati di un articolo prodotto viene indicato con il termine spese.






