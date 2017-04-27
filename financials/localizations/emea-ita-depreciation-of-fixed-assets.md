---
title: Ammortamento manuale dei cespiti per l&quot;Italia
description: In questo argomento vengono fornite informazioni sull&quot;ammortamento dei cespiti per le persone giuridiche in Italia.
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile, LedgerJournalTransApprove, LedgerJournalTransAsset, LedgerJournalTransDaily, LedgerJournalTransVendInvoice, PurchTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 264294
ms.assetid: 89d8fca3-b653-4fc8-9186-b765c31f7544
ms.search.region: Italy
ms.author: v-elgolu
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 5a3bed60b3ba3b95aba7616a19485b2de3f02b77
ms.lasthandoff: 03/31/2017


---

# <a name="manual-depreciation-of-fixed-assets-for-italy"></a>Ammortamento manuale dei cespiti per l'Italia

[!include[banner](../includes/banner.md)]


In questo argomento vengono fornite informazioni sull'ammortamento dei cespiti per le persone giuridiche in Italia. 

Per le persone giuridiche in Italia, il metodo di ammortamento manuale ha una funzionalità aggiuntiva che include i seguenti campi:

-   **Base di calcolo** - ** **Questo campo presenta due opzioni: **Giorni** o **Mesi** nella pagina **Profili di ammortamento**. L'ammortamento di cespiti viene calcolato per l'anno nel seguente modo:
    -   Ammortamento in giorni = intero ammortamento \* (numero di giorni rimanenti/giorni totali nell'anno)
    -   Ammortamento in mesi = intero ammortamento \* (numero di mesi rimanenti/12)
-   **Data d'esecuzione ammortamento**: questo campo è stato aggiunto alle pagine seguenti:
    -   Giornale di registrazione generale
    -   Giornale di registrazione cespiti
    -   Giornale di approvazione fatture
    -   Giornale di registrazione fatture
    -   Ordine fornitore

La **Data d'esecuzione ammortamento** deve essere configurata al momento dell'acquisto ed essere impostata sulla data del sistema durante l'acquisto. La **Data d'esecuzione ammortamento** viene utilizzata per calcolare l'ammortamento per **Numero di giorni rimanenti** o **Numero di mesi rimanenti**, a seconda del valore di **Base di calcolo**. Se la **Data d'esecuzione ammortamento** è precedente alla metà del mese (il 15 o il 14 febbraio), il mese corrente viene incluso nel numero di mesi, in caso contrario il cespite viene considerato come acquisito nel mese successivo.




