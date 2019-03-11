---
title: Ammortamento manuale dei cespiti per l'Italia
description: In questo argomento vengono fornite informazioni sull'ammortamento dei cespiti per le persone giuridiche in Italia.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile, LedgerJournalTransApprove, LedgerJournalTransAsset, LedgerJournalTransDaily, LedgerJournalTransVendInvoice, PurchTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264294
ms.search.region: Italy
ms.author: v-elgolu
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 80b0fdd86785f1c503045afe9e8e03a2e0641f9b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "370935"
---
# <a name="manual-depreciation-of-fixed-assets-for-italy"></a>Ammortamento manuale dei cespiti per l'Italia

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite informazioni sull'ammortamento dei cespiti per le persone giuridiche in Italia. 

Per le persone giuridiche in Italia, il metodo di ammortamento manuale ha una funzionalità aggiuntiva che include i seguenti campi:

- <strong>Base di calcolo</strong> -** <strong>Questo campo contiene due opzioni: **Giorni</strong> o <strong>Mesi</strong> nella pagina <strong>Profili di ammortamento</strong>. L'ammortamento di cespiti viene calcolato per l'anno nel seguente modo:
  -   Ammortamento in giorni = intero ammortamento \* (numero di giorni rimanenti/giorni totali nell'anno)
  -   Ammortamento in mesi = intero ammortamento \* (numero di mesi rimanenti/12)
- **Data d'esecuzione ammortamento**: questo campo è stato aggiunto alle pagine seguenti:
  -   Giornale di registrazione generale
  -   Giornale di registrazione cespiti
  -   Giornale di approvazione fatture
  -   Giornale di registrazione fatture
  -   Ordine fornitore

La **Data d'esecuzione ammortamento** deve essere configurata al momento dell'acquisto ed essere impostata sulla data del sistema durante l'acquisto. La **Data d'esecuzione ammortamento** viene utilizzata per calcolare l'ammortamento per **Numero di giorni rimanenti** o **Numero di mesi rimanenti**, a seconda del valore di **Base di calcolo**. Se la **Data d'esecuzione ammortamento** è precedente alla metà del mese (il 15 o il 14 febbraio), il mese corrente viene incluso nel numero di mesi, in caso contrario il cespite viene considerato come acquisito nel mese successivo.



