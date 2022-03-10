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
ms.openlocfilehash: 304609e065389d4f56913ae3f2f7fc562de2eadc9f0885ddbe2c8f4747081c66
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722177"
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
