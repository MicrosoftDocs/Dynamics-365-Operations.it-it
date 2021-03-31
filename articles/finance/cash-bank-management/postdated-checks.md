---
title: Assegni postdatati
description: Questo articolo fornisce informazioni sul supporto per gli assegni postdatati in Microsoft Dynamics 365 Finance. Gli assegni postdatati sono assegni emessi per effettuare e ricevere pagamenti in una data futura. Di conseguenza, l'assegno non può più essere incassato fino alla data specificata.
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPostDatedChecks, CustPostDatedChecks
audience: Application User
ms.reviewer: roschlom
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7562999a09e0036a7ea765c0cb0954412bbbda69
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228865"
---
# <a name="postdated-checks"></a><span data-ttu-id="b856c-105">Assegni postdatati</span><span class="sxs-lookup"><span data-stu-id="b856c-105">Postdated checks</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b856c-106">Questo articolo fornisce informazioni sul supporto per gli assegni postdatati.</span><span class="sxs-lookup"><span data-stu-id="b856c-106">This article provides information about support for postdated checks.</span></span> <span data-ttu-id="b856c-107">Gli assegni postdatati sono assegni emessi per effettuare e ricevere pagamenti in una data futura.</span><span class="sxs-lookup"><span data-stu-id="b856c-107">Postdated checks are checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="b856c-108">Di conseguenza, l'assegno non può più essere incassato fino alla data specificata.</span><span class="sxs-lookup"><span data-stu-id="b856c-108">Therefore, the check can't be cashed until the specified date.</span></span>

<span data-ttu-id="b856c-109">Dynamics 365 Finance supporta il ciclo di gestione completo per assegni postdatati sia in Contabilità clienti che in Contabilità fornitori, come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="b856c-109">Dynamics 365 Finance supports the full management cycle for postdated checks in both Accounts receivable and Accounts payable, as shown in the following table.</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b856c-110">Scenario</span><span class="sxs-lookup"><span data-stu-id="b856c-110">Scenario</span></span></th>
<th><span data-ttu-id="b856c-111">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b856c-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b856c-112">Impostare gli assegni postdatati</span><span class="sxs-lookup"><span data-stu-id="b856c-112">Set up postdated checks</span></span></td>
<td><span data-ttu-id="b856c-113">È necessario impostare un nuovo metodo di pagamento e specificare la procedura di pagamento per i conti di compensazione per gli assegni emessi, gli assegni ricevuti e la ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="b856c-113">You must set up a new payment method, and specify the payment routine for clearing accounts for issued checks, received checks, and withholding tax.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b856c-114">Registrare un assegno postdatato per un fornitore</span><span class="sxs-lookup"><span data-stu-id="b856c-114">Register and post a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="b856c-115">Registrare i dettagli di un assegno postdatato da emettere a favore di un fornitore.</span><span class="sxs-lookup"><span data-stu-id="b856c-115">Register the details of a postdated check that you issue to a vendor.</span></span> <span data-ttu-id="b856c-116">Quando il pagamento viene registrato, la passività fornitore viene riconosciuta, ma il conto bancario non è ancora accreditato.</span><span class="sxs-lookup"><span data-stu-id="b856c-116">When the payment is posted, the vendor liability is recognized, but the bank account isn’t yet credit.</span></span> <span data-ttu-id="b856c-117">A questo scopo viene utilizzato invece un conto di compensazione.</span><span class="sxs-lookup"><span data-stu-id="b856c-117">Instead, a clearing account is used for this purpose.</span></span> </td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b856c-118">Registrare un assegno postdatato di un cliente</span><span class="sxs-lookup"><span data-stu-id="b856c-118">Register and post a postdated check for a customer</span></span></td>
<td><span data-ttu-id="b856c-119">Registrare i dettagli di un assegno postdatato ricevuto da un cliente.</span><span class="sxs-lookup"><span data-stu-id="b856c-119">Register the details of a postdated check that you receive from a customer.</span></span> <span data-ttu-id="b856c-120">Quando il pagamento viene registrato, la contabilità cliente viene accreditata, ma il conto bancario non è ancora addebitato.</span><span class="sxs-lookup"><span data-stu-id="b856c-120">When the payment is posted, the customer receivable is credit, but the bank account isn’t yet debit.</span></span> <span data-ttu-id="b856c-121">A questo scopo viene utilizzato invece un conto di compensazione.</span><span class="sxs-lookup"><span data-stu-id="b856c-121">Instead, a clearing account is used for this purpose.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b856c-122">Registrare un assegno postdatato in sostituzione per un cliente o un fornitore</span><span class="sxs-lookup"><span data-stu-id="b856c-122">Register and post a replacement postdated check for a customer or a vendor</span></span></td>
<td>
<span data-ttu-id="b856c-123">Se l'assegno originale per un fornitore o da un cliente viene perso o danneggiato, è possibile emettere un assegno postdatato in sostituzione.</span><span class="sxs-lookup"><span data-stu-id="b856c-123">If your original check to a vendor or from a customer is lost or damaged, you can issue a replacement postdated check.</span></span> <span data-ttu-id="b856c-124">Quando si registrano i dettagli dell'assegno, fornire un riferimento all'assegno originale e indicare che il nuovo assegno è in sostituzione di quello originale.</span><span class="sxs-lookup"><span data-stu-id="b856c-124">When you register the check details, provide a reference to the original check, and indicate that the new check is a replacement for the original.</span></span> <span data-ttu-id="b856c-125">È inoltre possibile registrare l'assegno in sostituzione.</span><span class="sxs-lookup"><span data-stu-id="b856c-125">You can also post the replacement check.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b856c-126">Trasferire un assegno postdatato del cliente a un fornitore</span><span class="sxs-lookup"><span data-stu-id="b856c-126">Transfer a customer postdated check to a vendor</span></span></td>
<td><span data-ttu-id="b856c-127">Quando si riceve un assegno postdatato da un cliente, è possibile trasferirlo a un fornitore come pagamento.</span><span class="sxs-lookup"><span data-stu-id="b856c-127">When you receive a postdated check from a customer, you can transfer that check to a vendor as a payment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b856c-128">Liquidare un assegno postdatato per un cliente o un fornitore</span><span class="sxs-lookup"><span data-stu-id="b856c-128">Settle a postdated check for a customer or a vendor</span></span></td>
<td><span data-ttu-id="b856c-129">Liquidare un assegno postdatato registrato in un conto provvisorio per un cliente o un fornitore nel momento in cui diventa valido.</span><span class="sxs-lookup"><span data-stu-id="b856c-129">Settle a postdated check that is posted to a bridging account for a customer or a vendor when the check finally matures.</span></span> <span data-ttu-id="b856c-130">Se l'assegno viene liquidato, la banca viene addebitata o accreditata in base al conto di compensazione utilizzato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b856c-130">When the check is settled, the bank is finally debit or credit against the clearing account that was used earlier.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b856c-131">Annullare un assegno postdatato per un fornitore</span><span class="sxs-lookup"><span data-stu-id="b856c-131">Cancel a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="b856c-132">È possibile annullare gli assegni postdatati registrati nelle seguenti situazioni: - L'assegno viene restituito dalla banca.</span><span class="sxs-lookup"><span data-stu-id="b856c-132">You can cancel a posted postdated check in these situations: - The check is returned by the bank.</span></span>
<span data-ttu-id="b856c-133">- L'assegno è applicato a una fattura non corretta.</span><span class="sxs-lookup"><span data-stu-id="b856c-133">- The check is applied to an incorrect invoice.</span></span>
<span data-ttu-id="b856c-134">- Un pagamento in contanti viene effettuato a fronte dell'assegno.</span><span class="sxs-lookup"><span data-stu-id="b856c-134">- A cash payment is made against the check.</span></span>
  </td>
  </tr>
  <tr class="even">
  <td><span data-ttu-id="b856c-135">Bloccare il pagamento di un assegno postdatato</span><span class="sxs-lookup"><span data-stu-id="b856c-135">Stop payment for a postdated check</span></span></td>
  <td><span data-ttu-id="b856c-136">È possibile bloccare il pagamento di un assegno postdatato emesso a un fornitore per diversi motivi quali, ad esempio, copertura insufficiente, modifica delle condizioni del contratto con il fornitore, fornitura di merci difettose da parte del fornitore o merce resa al fornitore.</span><span class="sxs-lookup"><span data-stu-id="b856c-136">You can stop payment on a postdated check that was issued to a vendor, for reasons such as not sufficient funds, changes in the terms of the agreement with the vendor, supply of defective goods by the vendor, or return of goods to the vendor.</span></span> <span data-ttu-id="b856c-137">È possibile bloccare il pagamento solo degli assegni che non sono stati annullati.</span><span class="sxs-lookup"><span data-stu-id="b856c-137">You can stop payment only on checks that haven’t cleared.</span></span></td>
  </tr>
  </tbody>
  </table>



<span data-ttu-id="b856c-138">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="b856c-138">For more information, see the following topics:</span></span>

[<span data-ttu-id="b856c-139">Impostare gli assegni postdatati</span><span class="sxs-lookup"><span data-stu-id="b856c-139">Set up postdated checks</span></span>](tasks/set-up-postdated-checks.md)

[<span data-ttu-id="b856c-140">Registrare un assegno postdatato per un cliente</span><span class="sxs-lookup"><span data-stu-id="b856c-140">Register and post a postdated check for a customer</span></span>](tasks/register-post-postdated-check-customer.md)

[<span data-ttu-id="b856c-141">Liquidare un assegno postdatato di un cliente</span><span class="sxs-lookup"><span data-stu-id="b856c-141">Settle a postdated check from a customer</span></span>](tasks/settle-postdated-check-customer.md)

[<span data-ttu-id="b856c-142">Registrare un assegno postdatato per un fornitore</span><span class="sxs-lookup"><span data-stu-id="b856c-142">Register and post a postdated check for a vendor</span></span>](tasks/register-post-postdated-check-vendor.md) 

[<span data-ttu-id="b856c-143">Liquidare un assegno postdatato per un fornitore</span><span class="sxs-lookup"><span data-stu-id="b856c-143">Settle a postdated check for a vendor</span></span>](tasks/settle-postdated-check-vendor.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]