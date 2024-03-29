---
title: Ammortamento manuale dei cespiti per l'Italia
description: In questo articolo vengono fornite informazioni sull'ammortamento dei cespiti per le persone giuridiche in Italia.
author: AdamTrukawka
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: atrukawk
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 264294
ms.search.form: AssetDepreciationProfile, LedgerJournalTransApprove, LedgerJournalTransAsset, LedgerJournalTransDaily, LedgerJournalTransVendInvoice, PurchTable
ms.openlocfilehash: a1ec22e9bf9c4a567aee142492de8e93d458701b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281215"
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
