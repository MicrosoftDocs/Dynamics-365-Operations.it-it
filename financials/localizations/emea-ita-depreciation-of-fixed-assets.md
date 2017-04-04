---
title: Ammortamento manuale dei cespiti per l&quot;Italia
description: In questo argomento vengono fornite informazioni sull&quot;ammortamento dei cespiti per le persone giuridiche italiane.
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

In questo argomento vengono fornite informazioni sull'ammortamento dei cespiti per le persone giuridiche italiane. 

Per le persone giuridiche italiane, il metodo di ammortamento manuale ha funzionalità aggiuntive in cui sono inclusi i seguenti campi:

-   ** Base di calcolo ** - ** ** questo campo sono disponibili due opzioni: ** ** Giorni o mesi ** ** su ** profili di ammortamento ** pagina. L'ammortamento di cespiti viene calcolato per l'anno nel seguente modo:
    -   Ammortamento di giorni = intera ammortamento \* (numero di anni delle rimanenze/totale di giorni di giorni nell'anno)
    -   Mesi di ammortamento = intera ammortamento \* (numero di mesi remaining/12 di anni)
-   ** Data d'esecuzione ammortamento ** il campo è stato aggiunto alle pagine seguenti:
    -   Giornale di registrazione generale
    -   Giornale di registrazione cespiti
    -   Giornale di approvazione fatture
    -   Giornale di registrazione fatture
    -   Ordine fornitore

** Data d'esecuzione ammortamento ** deve essere impostato al momento di acquisizione e viene impostata sulla data di sistema dell'acquisizione. ** Data d'esecuzione ammortamento ** viene utilizzato per calcolare l'ammortamento per ** numero di giorni rimanenti ** o ** numero di mesi ** rimanente, a seconda ** base di calcolo ** il valore. ** Se la data di esecuzione dell'** è precedente del secondo nome del mese (il giorno o quattordicesimo per febbraio), il mese corrente viene incluso la quantità mesi, il cespite verrà considerato come acquistato il mese successivo.


