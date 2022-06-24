---
title: Ammortamento manuale dei cespiti per l'Italia
description: In questo articolo vengono fornite informazioni sull'ammortamento dei cespiti per le persone giuridiche in Italia.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile, LedgerJournalTransApprove, LedgerJournalTransAsset, LedgerJournalTransDaily, LedgerJournalTransVendInvoice, PurchTable
audience: Application User
ms.reviewer: kfend
ms.custom: 264294
ms.search.region: Italy
ms.author: kfend
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 9a443dd1f427dae9fd7e03ad0a49b2176043603e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872368"
---
# <a name="manual-depreciation-of-fixed-assets-for-italy"></a>Ammortamento manuale dei cespiti per l'Italia

[!include [banner](../includes/banner.md)]

In questo articolo vengono fornite informazioni sull'ammortamento dei cespiti per le persone giuridiche in Italia. 

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





[!INCLUDE[footer-include](../../includes/footer-banner.md)]