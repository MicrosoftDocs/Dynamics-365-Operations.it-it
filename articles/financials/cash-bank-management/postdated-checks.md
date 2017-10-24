---
title: Assegni postdatati
description: "Questo articolo fornisce informazioni sul supporto per gli assegni postdatati in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Gli assegni postdatati sono assegni emessi per effettuare e ricevere pagamenti in una data futura. Di conseguenza, l'assegno non può più essere incassato fino alla data specificata."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6a535b5f1192b7c27383cb8ece53f76a9c76f047
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="postdated-checks"></a><span data-ttu-id="41767-105">Assegni postdatati</span><span class="sxs-lookup"><span data-stu-id="41767-105">Postdated checks</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="41767-106">Questo articolo fornisce informazioni sul supporto per gli assegni postdatati in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="41767-106">This article provides information about support for postdated checks in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> <span data-ttu-id="41767-107">Gli assegni postdatati sono assegni emessi per effettuare e ricevere pagamenti in una data futura.</span><span class="sxs-lookup"><span data-stu-id="41767-107">Postdated checks are checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="41767-108">Di conseguenza, l'assegno non può più essere incassato fino alla data specificata.</span><span class="sxs-lookup"><span data-stu-id="41767-108">Therefore, the check can't be cashed until the specified date.</span></span>

<span data-ttu-id="41767-109">Microsoft Dynamics 365 for Finance and Operations supporta il ciclo di gestione completo per assegni postdatati sia in Contabilità clienti che in Contabilità fornitori, come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="41767-109">Microsoft Dynamics 365 for Finance and Operations supports the full management cycle for postdated checks in both Accounts receivable and Accounts payable, as shown in the following table.</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41767-110">Scenario</span><span class="sxs-lookup"><span data-stu-id="41767-110">Scenario</span></span></th>
<th><span data-ttu-id="41767-111">Dettagli</span><span class="sxs-lookup"><span data-stu-id="41767-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="41767-112">Impostare gli assegni postdatati</span><span class="sxs-lookup"><span data-stu-id="41767-112">Set up postdated checks</span></span></td>
<td><span data-ttu-id="41767-113">È necessario impostare un nuovo metodo di pagamento e specificare la procedura di pagamento per i conti di compensazione per gli assegni emessi, gli assegni ricevuti e la ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="41767-113">You must set up a new payment method, and specify the payment routine for clearing accounts for issued checks, received checks, and withholding tax.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="41767-114">Registrare un assegno postdatato per un fornitore</span><span class="sxs-lookup"><span data-stu-id="41767-114">Register and post a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="41767-115">Registrare i dettagli di un assegno postdatato da emettere a favore di un fornitore.</span><span class="sxs-lookup"><span data-stu-id="41767-115">Register the details of a postdated check that you issue to a vendor.</span></span> <span data-ttu-id="41767-116">Quando il pagamento viene registrato, la passività fornitore viene riconosciuta, ma il conto bancario non è ancora accreditato.</span><span class="sxs-lookup"><span data-stu-id="41767-116">When the payment is posted, the vendor liability is recognized, but the bank account isn’t yet credit.</span></span> <span data-ttu-id="41767-117">A questo scopo viene utilizzato invece un conto di compensazione.</span><span class="sxs-lookup"><span data-stu-id="41767-117">Instead, a clearing account is used for this purpose.</span></span> </td>
</tr>
<tr class="odd">
<td><span data-ttu-id="41767-118">Registrare un assegno postdatato di un cliente</span><span class="sxs-lookup"><span data-stu-id="41767-118">Register and post a postdated check for a customer</span></span></td>
<td><span data-ttu-id="41767-119">Registrare i dettagli di un assegno postdatato ricevuto da un cliente.</span><span class="sxs-lookup"><span data-stu-id="41767-119">Register the details of a postdated check that you receive from a customer.</span></span> <span data-ttu-id="41767-120">Quando il pagamento viene registrato, la contabilità cliente viene accreditata, ma il conto bancario non è ancora addebitato.</span><span class="sxs-lookup"><span data-stu-id="41767-120">When the payment is posted, the customer receivable is credit, but the bank account isn’t yet debit.</span></span> <span data-ttu-id="41767-121">A questo scopo viene utilizzato invece un conto di compensazione.</span><span class="sxs-lookup"><span data-stu-id="41767-121">Instead, a clearing account is used for this purpose.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="41767-122">Registrare un assegno postdatato in sostituzione per un cliente o un fornitore</span><span class="sxs-lookup"><span data-stu-id="41767-122">Register and post a replacement postdated check for a customer or a vendor</span></span></td>
<td>
<span data-ttu-id="41767-123">Se l'assegno originale per un fornitore o da un cliente viene perso o danneggiato, è possibile emettere un assegno postdatato in sostituzione.</span><span class="sxs-lookup"><span data-stu-id="41767-123">If your original check to a vendor or from a customer is lost or damaged, you can issue a replacement postdated check.</span></span> <span data-ttu-id="41767-124">Quando si registrano i dettagli dell'assegno, fornire un riferimento all'assegno originale e indicare che il nuovo assegno è in sostituzione di quello originale.</span><span class="sxs-lookup"><span data-stu-id="41767-124">When you register the check details, provide a reference to the original check, and indicate that the new check is a replacement for the original.</span></span> <span data-ttu-id="41767-125">È inoltre possibile registrare l'assegno in sostituzione.</span><span class="sxs-lookup"><span data-stu-id="41767-125">You can also post the replacement check.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="41767-126">Trasferire un assegno postdatato del cliente a un fornitore</span><span class="sxs-lookup"><span data-stu-id="41767-126">Transfer a customer postdated check to a vendor</span></span></td>
<td><span data-ttu-id="41767-127">Quando si riceve un assegno postdatato da un cliente, è possibile trasferirlo a un fornitore come pagamento.</span><span class="sxs-lookup"><span data-stu-id="41767-127">When you receive a postdated check from a customer, you can transfer that check to a vendor as a payment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="41767-128">Liquidare un assegno postdatato per un cliente o un fornitore</span><span class="sxs-lookup"><span data-stu-id="41767-128">Settle a postdated check for a customer or a vendor</span></span></td>
<td><span data-ttu-id="41767-129">Liquidare un assegno postdatato registrato in un conto provvisorio per un cliente o un fornitore nel momento in cui diventa valido.</span><span class="sxs-lookup"><span data-stu-id="41767-129">Settle a postdated check that is posted to a bridging account for a customer or a vendor when the check finally matures.</span></span> <span data-ttu-id="41767-130">Se l'assegno viene liquidato, la banca viene addebitata o accreditata in base al conto di compensazione utilizzato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="41767-130">When the check is settled, the bank is finally debit or credit against the clearing account that was used earlier.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="41767-131">Annullare un assegno postdatato per un fornitore</span><span class="sxs-lookup"><span data-stu-id="41767-131">Cancel a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="41767-132">È possibile annullare gli assegni postdatati registrati nelle seguenti situazioni: - L'assegno viene restituito dalla banca.</span><span class="sxs-lookup"><span data-stu-id="41767-132">You can cancel a posted postdated check in these situations: - The check is returned by the bank.</span></span>
<span data-ttu-id="41767-133">- L'assegno è applicato a una fattura non corretta.</span><span class="sxs-lookup"><span data-stu-id="41767-133">- The check is applied to an incorrect invoice.</span></span>
<span data-ttu-id="41767-134">- Un pagamento in contanti viene effettuato a fronte dell'assegno.</span><span class="sxs-lookup"><span data-stu-id="41767-134">- A cash payment is made against the check.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="41767-135">Bloccare il pagamento di un assegno postdatato</span><span class="sxs-lookup"><span data-stu-id="41767-135">Stop payment for a postdated check</span></span></td>
<td><span data-ttu-id="41767-136">È possibile bloccare il pagamento di un assegno postdatato emesso a un fornitore per diversi motivi quali, ad esempio, copertura insufficiente, modifica delle condizioni del contratto con il fornitore, fornitura di merci difettose da parte del fornitore o merce resa al fornitore.</span><span class="sxs-lookup"><span data-stu-id="41767-136">You can stop payment on a postdated check that was issued to a vendor, for reasons such as not sufficient funds, changes in the terms of the agreement with the vendor, supply of defective goods by the vendor, or return of goods to the vendor.</span></span> <span data-ttu-id="41767-137">È possibile bloccare il pagamento solo degli assegni che non sono stati annullati.</span><span class="sxs-lookup"><span data-stu-id="41767-137">You can stop payment only on checks that haven’t cleared.</span></span></td>
</tr>
</tbody>
</table>



<span data-ttu-id="41767-138">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="41767-138">For more information, see the following topics:</span></span>

[<span data-ttu-id="41767-139">Impostare gli assegni postdatati</span><span class="sxs-lookup"><span data-stu-id="41767-139">Set up postdated checks</span></span>](tasks/set-up-postdated-checks.md)

[<span data-ttu-id="41767-140">Registrare un assegno postdatato per un cliente</span><span class="sxs-lookup"><span data-stu-id="41767-140">Register and post a postdated check for a customer</span></span>](tasks/register-post-postdated-check-customer.md)

[<span data-ttu-id="41767-141">Liquidare un assegno postdatato di un cliente</span><span class="sxs-lookup"><span data-stu-id="41767-141">Settle a postdated check from a customer</span></span>](tasks/settle-postdated-check-customer.md)

[<span data-ttu-id="41767-142">Registrare un assegno postdatato per un fornitore</span><span class="sxs-lookup"><span data-stu-id="41767-142">Register and post a postdated check for a vendor</span></span>](tasks/register-post-postdated-check-vendor.md) 

[<span data-ttu-id="41767-143">Liquidare un assegno postdatato per un fornitore</span><span class="sxs-lookup"><span data-stu-id="41767-143">Settle a postdated check for a vendor</span></span>](tasks/settle-postdated-check-vendor.md)




