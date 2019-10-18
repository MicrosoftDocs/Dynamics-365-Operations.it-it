---
title: Applicare uno sconto maggiore dello sconto calcolato per un pagamento fornitore
description: Questo articolo illustra uno scenario in cui si applica uno sconto di cassa per un importo maggiore dello sconto disponibile originariamente nella fattura. Questo scenario potrebbe verificarsi se un'organizzazione stipula un contratto con il fornitore per pagare un importo minore per la fattura.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b84b3d6ef1a86d8174823345a5ee9181c701c151
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178536"
---
# <a name="take-a-discount-that-is-more-than-the-calculated-discount-for-a-vendor-payment"></a><span data-ttu-id="264fa-104">Applicare uno sconto maggiore dello sconto calcolato per un pagamento fornitore</span><span class="sxs-lookup"><span data-stu-id="264fa-104">Take a discount that is more than the calculated discount for a vendor payment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="264fa-105">Questo articolo illustra uno scenario in cui si applica uno sconto di cassa per un importo maggiore dello sconto disponibile originariamente nella fattura.</span><span class="sxs-lookup"><span data-stu-id="264fa-105">This article walks you through a scenario where a cash discount is taken for an amount that is more than the discount that was originally available on the invoice.</span></span> <span data-ttu-id="264fa-106">Questo scenario potrebbe verificarsi se un'organizzazione stipula un contratto con il fornitore per pagare un importo minore per la fattura.</span><span class="sxs-lookup"><span data-stu-id="264fa-106">This scenario might occur if an organization comes to an agreement with the vendor to pay a smaller amount on the invoice.</span></span> 

<span data-ttu-id="264fa-107">Il fornitore 3051 concede a Fabrikam uno sconto di cassa del 4% se una fattura viene pagata in sette giorni.</span><span class="sxs-lookup"><span data-stu-id="264fa-107">Vendor 3051 gives Fabrikam a cash discount of 4 percent if an invoice is paid in seven days.</span></span> <span data-ttu-id="264fa-108">April immette una fattura il 29 giugno per 1.000,00.</span><span class="sxs-lookup"><span data-stu-id="264fa-108">On June 29, April enters an invoice for 1,000.00.</span></span> <span data-ttu-id="264fa-109">Il fornitore consente ad April di applicare uno sconto del 60,00 anziché lo sconto predefinito di 40,00 disponibile per la fattura.</span><span class="sxs-lookup"><span data-stu-id="264fa-109">The vendor lets April take a discount of 60.00 instead of the default discount of 40.00 that is available for the invoice.</span></span> <span data-ttu-id="264fa-110">April registra un pagamento occasionale utilizzando il giornale di registrazione pagamenti della contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="264fa-110">April records a one-off payment by using the Accounts payable payment journal.</span></span> <span data-ttu-id="264fa-111">Registra il fornitore per il pagamento e quindi apre la pagina **Liquida transazioni**.</span><span class="sxs-lookup"><span data-stu-id="264fa-111">She enters the vendor for the payment and then opens the **Settle transactions** page.</span></span> <span data-ttu-id="264fa-112">Contrassegna la fattura e modifica il valore nel campo **Importo sconto di cassa** in **60,00**.</span><span class="sxs-lookup"><span data-stu-id="264fa-112">She marks the invoice and changes the value in the **Cash discount amount** field to **60.00**.</span></span>

| <span data-ttu-id="264fa-113">Contrassegna</span><span class="sxs-lookup"><span data-stu-id="264fa-113">Mark</span></span>     | <span data-ttu-id="264fa-114">Utilizzare lo sconto di cassa</span><span class="sxs-lookup"><span data-stu-id="264fa-114">Use cash discount</span></span> | <span data-ttu-id="264fa-115">Giustificativo</span><span class="sxs-lookup"><span data-stu-id="264fa-115">Voucher</span></span>   | <span data-ttu-id="264fa-116">Conto</span><span class="sxs-lookup"><span data-stu-id="264fa-116">Account</span></span> | <span data-ttu-id="264fa-117">Data</span><span class="sxs-lookup"><span data-stu-id="264fa-117">Date</span></span>      | <span data-ttu-id="264fa-118">Data di scadenza</span><span class="sxs-lookup"><span data-stu-id="264fa-118">Due date</span></span>  | <span data-ttu-id="264fa-119">Fattura</span><span class="sxs-lookup"><span data-stu-id="264fa-119">Invoice</span></span> | <span data-ttu-id="264fa-120">Importo nella valuta della transazione</span><span class="sxs-lookup"><span data-stu-id="264fa-120">Amount in transaction currency</span></span> | <span data-ttu-id="264fa-121">Valuta</span><span class="sxs-lookup"><span data-stu-id="264fa-121">Currency</span></span> | <span data-ttu-id="264fa-122">Importo da liquidare</span><span class="sxs-lookup"><span data-stu-id="264fa-122">Amount to settle</span></span> |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| <span data-ttu-id="264fa-123">Selezionata</span><span class="sxs-lookup"><span data-stu-id="264fa-123">Selected</span></span> | <span data-ttu-id="264fa-124">Normale</span><span class="sxs-lookup"><span data-stu-id="264fa-124">Normal</span></span>            | <span data-ttu-id="264fa-125">Inv-10040</span><span class="sxs-lookup"><span data-stu-id="264fa-125">Inv-10040</span></span> | <span data-ttu-id="264fa-126">3051</span><span class="sxs-lookup"><span data-stu-id="264fa-126">3051</span></span>    | <span data-ttu-id="264fa-127">29/6/2015</span><span class="sxs-lookup"><span data-stu-id="264fa-127">6/29/2015</span></span> | <span data-ttu-id="264fa-128">29/7/2015</span><span class="sxs-lookup"><span data-stu-id="264fa-128">7/29/2015</span></span> | <span data-ttu-id="264fa-129">10040</span><span class="sxs-lookup"><span data-stu-id="264fa-129">10040</span></span>   | <span data-ttu-id="264fa-130">1.000,00</span><span class="sxs-lookup"><span data-stu-id="264fa-130">1,000.00</span></span>                       | <span data-ttu-id="264fa-131">GBP</span><span class="sxs-lookup"><span data-stu-id="264fa-131">USD</span></span>      | <span data-ttu-id="264fa-132">940,00</span><span class="sxs-lookup"><span data-stu-id="264fa-132">940.00</span></span>           |

<span data-ttu-id="264fa-133">Le informazioni di sconto vengono visualizzate nella parte inferiore della pagina **Liquida transazioni**.</span><span class="sxs-lookup"><span data-stu-id="264fa-133">Discount information appears at the bottom of the **Settle transactions** page.</span></span>

|                              |           |
|------------------------------|-----------|
| <span data-ttu-id="264fa-134">Data sconto di cassa</span><span class="sxs-lookup"><span data-stu-id="264fa-134">Cash discount date</span></span>           | <span data-ttu-id="264fa-135">12/7/2015</span><span class="sxs-lookup"><span data-stu-id="264fa-135">7/12/2015</span></span> |
| <span data-ttu-id="264fa-136">Importo sconto di cassa</span><span class="sxs-lookup"><span data-stu-id="264fa-136">Cash discount amount</span></span>         | <span data-ttu-id="264fa-137">60,00</span><span class="sxs-lookup"><span data-stu-id="264fa-137">60.00</span></span>     |
| <span data-ttu-id="264fa-138">Utilizzare lo sconto di cassa</span><span class="sxs-lookup"><span data-stu-id="264fa-138">Use cash discount</span></span>            | <span data-ttu-id="264fa-139">Normale</span><span class="sxs-lookup"><span data-stu-id="264fa-139">Normal</span></span>    |
| <span data-ttu-id="264fa-140">Sconto di cassa applicato</span><span class="sxs-lookup"><span data-stu-id="264fa-140">Cash discount taken</span></span>          | <span data-ttu-id="264fa-141">0,00</span><span class="sxs-lookup"><span data-stu-id="264fa-141">0.00</span></span>      |
| <span data-ttu-id="264fa-142">Importo sconto di cassa da applicare</span><span class="sxs-lookup"><span data-stu-id="264fa-142">Cash discount amount to take</span></span> | <span data-ttu-id="264fa-143">60,00</span><span class="sxs-lookup"><span data-stu-id="264fa-143">60.00</span></span>     |

<span data-ttu-id="264fa-144">April registra il giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="264fa-144">April posts the payment journal.</span></span> <span data-ttu-id="264fa-145">La fattura è completamente liquidata con un pagamento di 940,00 e uno sconto di 60,00.</span><span class="sxs-lookup"><span data-stu-id="264fa-145">The invoice is fully settled by using a payment of 940.00 and a discount of 60.00.</span></span>



