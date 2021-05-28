---
title: Il rateo acquisti con importo zero viene registrato per un'entrata prodotti con valore zero
description: Quando viene registrata un'entrata prodotti con valore zero, il sistema crea una registrazione per il rateo acquisti in cui l'importo è 0 (zero).
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f8d9d857590dc788d16b01edf77600d8fd8c8444
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026659"
---
# <a name="purchase-accrual-that-has-a-zero-amount-is-posted-for-a-zero-value-product-receipt"></a>Il rateo acquisti con importo zero viene registrato per un'entrata prodotti con valore zero

Numero KB: 4612588

## <a name="symptoms"></a>Sintomi

Quando viene registrata un'entrata prodotti con valore zero, il sistema crea una registrazione per il rateo acquisti in cui l'importo è 0 (zero).

## <a name="resolution"></a>Risoluzione

Per impostazione predefinita, per le registrazioni contabili di tipo *Acquisto, rateo*, il campo `IsTransferredIndetail` è sempre impostato su *Riepilogo* nelle transazioni del giornale di registrazione secondario. Pertanto, il sistema crea una voce di giustificativo correlata anche se l'importo è 0 (zero).

Per ignorare questo tipo di registrazione quando l'importo è 0 (zero), estendi il metodo `subledgerJournalizer.markDoNotTransferEntries` in modo che includa `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, come mostrato nell'esempio seguente.

```xpp
update_recordset existingSubledgerJournalAccountEntry
setting
    IsTransferredInDetail = TransferPolicy::DoNotTransfer
where existingSubledgerJournalAccountEntry.SubledgerJournalEntry == _subledgerJournalEntryRecId
    && (existingSubledgerJournalAccountEntry.AccountingCurrencyAmount == 0 && existingSubledgerJournalAccountEntry.ReportingCurrencyAmount == 0)
    && existingSubledgerJournalAccountEntry.PostingType == LedgerPostingType::PurchPckSlpPurchaseOffsetAccount;
```
