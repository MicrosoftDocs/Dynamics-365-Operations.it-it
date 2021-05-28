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
# <a name="purchase-accrual-that-has-a-zero-amount-is-posted-for-a-zero-value-product-receipt"></a><span data-ttu-id="80750-103">Il rateo acquisti con importo zero viene registrato per un'entrata prodotti con valore zero</span><span class="sxs-lookup"><span data-stu-id="80750-103">Purchase accrual that has a zero amount is posted for a zero-value product receipt</span></span>

<span data-ttu-id="80750-104">Numero KB: 4612588</span><span class="sxs-lookup"><span data-stu-id="80750-104">KB number: 4612588</span></span>

## <a name="symptoms"></a><span data-ttu-id="80750-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="80750-105">Symptoms</span></span>

<span data-ttu-id="80750-106">Quando viene registrata un'entrata prodotti con valore zero, il sistema crea una registrazione per il rateo acquisti in cui l'importo è 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="80750-106">When a product receipt that has zero value is posted, the system creates a posting to purchase accrual where the amount is 0 (zero).</span></span>

## <a name="resolution"></a><span data-ttu-id="80750-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="80750-107">Resolution</span></span>

<span data-ttu-id="80750-108">Per impostazione predefinita, per le registrazioni contabili di tipo *Acquisto, rateo*, il campo `IsTransferredIndetail` è sempre impostato su *Riepilogo* nelle transazioni del giornale di registrazione secondario.</span><span class="sxs-lookup"><span data-stu-id="80750-108">By default, for ledger postings of the *Purchase, accrual* type, the `IsTransferredIndetail` field is always set to *Summary* in subledger transactions.</span></span> <span data-ttu-id="80750-109">Pertanto, il sistema crea una voce di giustificativo correlata anche se l'importo è 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="80750-109">Therefore, the system creates a related voucher entry even if the amount is 0 (zero).</span></span>

<span data-ttu-id="80750-110">Per ignorare questo tipo di registrazione quando l'importo è 0 (zero), estendi il metodo `subledgerJournalizer.markDoNotTransferEntries` in modo che includa `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="80750-110">To skip this posting type when the amount is 0 (zero), extend the `subledgerJournalizer.markDoNotTransferEntries` method so that it includes `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, as shown in the following example.</span></span>

```xpp
update_recordset existingSubledgerJournalAccountEntry
setting
    IsTransferredInDetail = TransferPolicy::DoNotTransfer
where existingSubledgerJournalAccountEntry.SubledgerJournalEntry == _subledgerJournalEntryRecId
    && (existingSubledgerJournalAccountEntry.AccountingCurrencyAmount == 0 && existingSubledgerJournalAccountEntry.ReportingCurrencyAmount == 0)
    && existingSubledgerJournalAccountEntry.PostingType == LedgerPostingType::PurchPckSlpPurchaseOffsetAccount;
```
