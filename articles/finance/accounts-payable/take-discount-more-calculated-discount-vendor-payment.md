---
title: Applicare uno sconto maggiore dello sconto calcolato per un pagamento fornitore
description: Questo articolo illustra uno scenario in cui si applica uno sconto di cassa per un importo maggiore dello sconto disponibile originariamente nella fattura. Questo scenario potrebbe verificarsi se un'organizzazione stipula un contratto con il fornitore per pagare un importo minore per la fattura.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62f2088ff04a0ef5ffe6ffe47b85f47e6957264d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810248"
---
# <a name="take-more-than-the-calculated-discount-for-a-vendor-payment"></a><span data-ttu-id="0d1bb-104">Applicare uno sconto maggiore dello sconto calcolato per un pagamento fornitore</span><span class="sxs-lookup"><span data-stu-id="0d1bb-104">Take more than the calculated discount for a vendor payment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0d1bb-105">Questo articolo illustra uno scenario in cui si applica uno sconto di cassa per un importo maggiore dello sconto disponibile originariamente nella fattura.</span><span class="sxs-lookup"><span data-stu-id="0d1bb-105">This article walks you through a scenario where a cash discount is taken for an amount that is more than the discount that was originally available on the invoice.</span></span> <span data-ttu-id="0d1bb-106">Questo scenario potrebbe verificarsi se un'organizzazione stipula un contratto con il fornitore per pagare un importo minore per la fattura.</span><span class="sxs-lookup"><span data-stu-id="0d1bb-106">This scenario might occur if an organization comes to an agreement with the vendor to pay a smaller amount on the invoice.</span></span> 

<span data-ttu-id="0d1bb-107">Il fornitore 3051 concede a Fabrikam uno sconto di cassa del 4% se una fattura viene pagata in sette giorni.</span><span class="sxs-lookup"><span data-stu-id="0d1bb-107">Vendor 3051 gives Fabrikam a cash discount of 4 percent if an invoice is paid in seven days.</span></span> <span data-ttu-id="0d1bb-108">April immette una fattura il 29 giugno per 1.000,00.</span><span class="sxs-lookup"><span data-stu-id="0d1bb-108">On June 29, April enters an invoice for 1,000.00.</span></span> <span data-ttu-id="0d1bb-109">Il fornitore consente ad April di applicare uno sconto del 60,00 anziché lo sconto predefinito di 40,00 disponibile per la fattura.</span><span class="sxs-lookup"><span data-stu-id="0d1bb-109">The vendor lets April take a discount of 60.00 instead of the default discount of 40.00 that is available for the invoice.</span></span> <span data-ttu-id="0d1bb-110">April registra un pagamento occasionale utilizzando il giornale di registrazione pagamenti della contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="0d1bb-110">April records a one-off payment by using the Accounts payable payment journal.</span></span> <span data-ttu-id="0d1bb-111">Registra il fornitore per il pagamento e quindi apre la pagina **Liquida transazioni**.</span><span class="sxs-lookup"><span data-stu-id="0d1bb-111">She enters the vendor for the payment and then opens the **Settle transactions** page.</span></span> <span data-ttu-id="0d1bb-112">Contrassegna la fattura e modifica il valore nel campo **Importo sconto di cassa** in **60,00**.</span><span class="sxs-lookup"><span data-stu-id="0d1bb-112">She marks the invoice and changes the value in the **Cash discount amount** field to **60.00**.</span></span>

| <span data-ttu-id="0d1bb-113">Contrassegna</span><span class="sxs-lookup"><span data-stu-id="0d1bb-113">Mark</span></span>     | <span data-ttu-id="0d1bb-114">Utilizzare lo sconto di cassa</span><span class="sxs-lookup"><span data-stu-id="0d1bb-114">Use cash discount</span></span> | <span data-ttu-id="0d1bb-115">Giustificativo</span><span class="sxs-lookup"><span data-stu-id="0d1bb-115">Voucher</span></span>   | <span data-ttu-id="0d1bb-116">Conto</span><span class="sxs-lookup"><span data-stu-id="0d1bb-116">Account</span></span> | <span data-ttu-id="0d1bb-117">Data</span><span class="sxs-lookup"><span data-stu-id="0d1bb-117">Date</span></span>      | <span data-ttu-id="0d1bb-118">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="0d1bb-118">Due date</span></span>  | <span data-ttu-id="0d1bb-119">Fattura</span><span class="sxs-lookup"><span data-stu-id="0d1bb-119">Invoice</span></span> | <span data-ttu-id="0d1bb-120">Importo nella valuta della transazione</span><span class="sxs-lookup"><span data-stu-id="0d1bb-120">Amount in transaction currency</span></span> | <span data-ttu-id="0d1bb-121">Valuta</span><span class="sxs-lookup"><span data-stu-id="0d1bb-121">Currency</span></span> | <span data-ttu-id="0d1bb-122">Importo da liquidare</span><span class="sxs-lookup"><span data-stu-id="0d1bb-122">Amount to settle</span></span> |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| <span data-ttu-id="0d1bb-123">Selezionata</span><span class="sxs-lookup"><span data-stu-id="0d1bb-123">Selected</span></span> | <span data-ttu-id="0d1bb-124">Normale</span><span class="sxs-lookup"><span data-stu-id="0d1bb-124">Normal</span></span>            | <span data-ttu-id="0d1bb-125">Inv-10040</span><span class="sxs-lookup"><span data-stu-id="0d1bb-125">Inv-10040</span></span> | <span data-ttu-id="0d1bb-126">3051</span><span class="sxs-lookup"><span data-stu-id="0d1bb-126">3051</span></span>    | <span data-ttu-id="0d1bb-127">29/6/2015</span><span class="sxs-lookup"><span data-stu-id="0d1bb-127">6/29/2015</span></span> | <span data-ttu-id="0d1bb-128">29/7/2015</span><span class="sxs-lookup"><span data-stu-id="0d1bb-128">7/29/2015</span></span> | <span data-ttu-id="0d1bb-129">10040</span><span class="sxs-lookup"><span data-stu-id="0d1bb-129">10040</span></span>   | <span data-ttu-id="0d1bb-130">1.000,00</span><span class="sxs-lookup"><span data-stu-id="0d1bb-130">1,000.00</span></span>                       | <span data-ttu-id="0d1bb-131">GBP</span><span class="sxs-lookup"><span data-stu-id="0d1bb-131">USD</span></span>      | <span data-ttu-id="0d1bb-132">940,00</span><span class="sxs-lookup"><span data-stu-id="0d1bb-132">940.00</span></span>           |

<span data-ttu-id="0d1bb-133">Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni**.</span><span class="sxs-lookup"><span data-stu-id="0d1bb-133">Discount information appears at the bottom of the **Settle transactions** page.</span></span>

| <span data-ttu-id="0d1bb-134">Campo</span><span class="sxs-lookup"><span data-stu-id="0d1bb-134">Field</span></span>                        | <span data-ttu-id="0d1bb-135">Valore</span><span class="sxs-lookup"><span data-stu-id="0d1bb-135">Value</span></span>     |
|------------------------------|-----------|
| <span data-ttu-id="0d1bb-136">Data sconto di cassa</span><span class="sxs-lookup"><span data-stu-id="0d1bb-136">Cash discount date</span></span>           | <span data-ttu-id="0d1bb-137">12/7/2015</span><span class="sxs-lookup"><span data-stu-id="0d1bb-137">7/12/2015</span></span> |
| <span data-ttu-id="0d1bb-138">Importo sconto di cassa</span><span class="sxs-lookup"><span data-stu-id="0d1bb-138">Cash discount amount</span></span>         | <span data-ttu-id="0d1bb-139">60.00</span><span class="sxs-lookup"><span data-stu-id="0d1bb-139">60.00</span></span>     |
| <span data-ttu-id="0d1bb-140">Utilizzare lo sconto di cassa</span><span class="sxs-lookup"><span data-stu-id="0d1bb-140">Use cash discount</span></span>            | <span data-ttu-id="0d1bb-141">Normale</span><span class="sxs-lookup"><span data-stu-id="0d1bb-141">Normal</span></span>    |
| <span data-ttu-id="0d1bb-142">Sconto di cassa applicato</span><span class="sxs-lookup"><span data-stu-id="0d1bb-142">Cash discount taken</span></span>          | <span data-ttu-id="0d1bb-143">0,00</span><span class="sxs-lookup"><span data-stu-id="0d1bb-143">0.00</span></span>      |
| <span data-ttu-id="0d1bb-144">Importo sconto di cassa da applicare</span><span class="sxs-lookup"><span data-stu-id="0d1bb-144">Cash discount amount to take</span></span> | <span data-ttu-id="0d1bb-145">60,00</span><span class="sxs-lookup"><span data-stu-id="0d1bb-145">60.00</span></span>     |

<span data-ttu-id="0d1bb-146">April registra il giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="0d1bb-146">April posts the payment journal.</span></span> <span data-ttu-id="0d1bb-147">La fattura è completamente liquidata con un pagamento di 940,00 e uno sconto di 60,00.</span><span class="sxs-lookup"><span data-stu-id="0d1bb-147">The invoice is fully settled by using a payment of 940.00 and a discount of 60.00.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]