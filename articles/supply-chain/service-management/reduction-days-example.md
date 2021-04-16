---
title: Esempio di giorni di riduzione
description: Esempio di giorni di riduzione.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 90a2efff0add508ddb3d750bb3ca27ea35bf113a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836064"
---
# <a name="reduction-days-example"></a><span data-ttu-id="2d65e-103">Esempio di giorni di riduzione</span><span class="sxs-lookup"><span data-stu-id="2d65e-103">Reduction days example</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="2d65e-104">È stata creata una transazione di sottoscrizione per la sottoscrizione di manutenzione di un cliente come descritto nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="2d65e-104">You have created a subscription transaction for a customer's maintenance subscription, as described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2d65e-105">Dal</span><span class="sxs-lookup"><span data-stu-id="2d65e-105">From date</span></span></p></th>
<th><p><span data-ttu-id="2d65e-106">Al</span><span class="sxs-lookup"><span data-stu-id="2d65e-106">To date</span></span></p></th>
<th><p><span data-ttu-id="2d65e-107">Sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="2d65e-107">Subscription</span></span></p></th>
<th><p><span data-ttu-id="2d65e-108">Tipo di sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="2d65e-108">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="2d65e-109">Progetto</span><span class="sxs-lookup"><span data-stu-id="2d65e-109">Project</span></span></p></th>
<th><p><span data-ttu-id="2d65e-110">Categoria</span><span class="sxs-lookup"><span data-stu-id="2d65e-110">Category</span></span></p></th>
<th><p><span data-ttu-id="2d65e-111">Valuta di vendita</span><span class="sxs-lookup"><span data-stu-id="2d65e-111">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="2d65e-112">Prezzo di vendita</span><span class="sxs-lookup"><span data-stu-id="2d65e-112">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d65e-113">01 marzo 2011</span><span class="sxs-lookup"><span data-stu-id="2d65e-113">March 01, 2011</span></span></p></td>
<td><p><span data-ttu-id="2d65e-114">31 marzo 2011</span><span class="sxs-lookup"><span data-stu-id="2d65e-114">March 31, 2011</span></span></p></td>
<td><p><span data-ttu-id="2d65e-115">NR-2</span><span class="sxs-lookup"><span data-stu-id="2d65e-115">NR-2</span></span></p></td>
<td><p><span data-ttu-id="2d65e-116"><strong>Regolare</strong></span><span class="sxs-lookup"><span data-stu-id="2d65e-116"><strong>Regular</strong></span></span></p></td>
<td><p><span data-ttu-id="2d65e-117">9013</span><span class="sxs-lookup"><span data-stu-id="2d65e-117">9013</span></span></p></td>
<td><p><span data-ttu-id="2d65e-118">SubCat2</span><span class="sxs-lookup"><span data-stu-id="2d65e-118">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="2d65e-119">EUR</span><span class="sxs-lookup"><span data-stu-id="2d65e-119">EUR</span></span></p></td>
<td><p><span data-ttu-id="2d65e-120">200,00</span><span class="sxs-lookup"><span data-stu-id="2d65e-120">200.00</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2d65e-121">Il cliente segnala che la copertura del servizio non è necessaria per due giorni (10 marzo e 11 marzo).</span><span class="sxs-lookup"><span data-stu-id="2d65e-121">The customer reports that it does not need service coverage for two days (March 10 and March 11).</span></span> <span data-ttu-id="2d65e-122">Si concorda quindi di applicare una riduzione della sottoscrizione per i due giorni citati.</span><span class="sxs-lookup"><span data-stu-id="2d65e-122">You agree to reduce the subscription by these two days.</span></span>

<span data-ttu-id="2d65e-123">Viene quindi creata una nuova transazione di tipo **Giorni riduzione** come descritto nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="2d65e-123">You create a new transaction of the **Reduction days** type, as described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2d65e-124">Dal</span><span class="sxs-lookup"><span data-stu-id="2d65e-124">From date</span></span></p></th>
<th><p><span data-ttu-id="2d65e-125">Al</span><span class="sxs-lookup"><span data-stu-id="2d65e-125">To date</span></span></p></th>
<th><p><span data-ttu-id="2d65e-126">Sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="2d65e-126">Subscription</span></span></p></th>
<th><p><span data-ttu-id="2d65e-127">Tipo di sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="2d65e-127">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="2d65e-128">Progetto</span><span class="sxs-lookup"><span data-stu-id="2d65e-128">Project</span></span></p></th>
<th><p><span data-ttu-id="2d65e-129">Categoria</span><span class="sxs-lookup"><span data-stu-id="2d65e-129">Category</span></span></p></th>
<th><p><span data-ttu-id="2d65e-130">Valuta di vendita</span><span class="sxs-lookup"><span data-stu-id="2d65e-130">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="2d65e-131">Prezzo di vendita</span><span class="sxs-lookup"><span data-stu-id="2d65e-131">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d65e-132">10 marzo 2011</span><span class="sxs-lookup"><span data-stu-id="2d65e-132">March 10, 2011</span></span></p></td>
<td><p><span data-ttu-id="2d65e-133">11 marzo 2011</span><span class="sxs-lookup"><span data-stu-id="2d65e-133">March 11, 2011</span></span></p></td>
<td><p><span data-ttu-id="2d65e-134">NR-2</span><span class="sxs-lookup"><span data-stu-id="2d65e-134">NR-2</span></span></p></td>
<td><p><span data-ttu-id="2d65e-135"><strong>Giorni riduzione</strong></span><span class="sxs-lookup"><span data-stu-id="2d65e-135"><strong>Reduction days</strong></span></span></p></td>
<td><p><span data-ttu-id="2d65e-136">9013</span><span class="sxs-lookup"><span data-stu-id="2d65e-136">9013</span></span></p></td>
<td><p><span data-ttu-id="2d65e-137">SubCat2</span><span class="sxs-lookup"><span data-stu-id="2d65e-137">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="2d65e-138">EUR</span><span class="sxs-lookup"><span data-stu-id="2d65e-138">EUR</span></span></p></td>
<td><p><span data-ttu-id="2d65e-139">-12,90</span><span class="sxs-lookup"><span data-stu-id="2d65e-139">-12.90</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2d65e-140">Quando le transazioni per marzo 2011 vengono fatturate, il prezzo di vendita di EUR 200 viene ridotto a EUR 12,90.</span><span class="sxs-lookup"><span data-stu-id="2d65e-140">When the transactions for March 2011 are invoiced, the sales price of EUR 200 is reduced by EUR 12.90.</span></span> <span data-ttu-id="2d65e-141">L'importo addebitabile per la transazione di sottoscrizione è pertanto EUR 187,10 e vengono fatturate due transazioni per un totale di EUR 187,10.</span><span class="sxs-lookup"><span data-stu-id="2d65e-141">The chargeable amount for the subscription transaction is therefore EUR 187.10, and two transactions are invoiced at a total of EUR 187.10.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d65e-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d65e-142">See also</span></span>

[<span data-ttu-id="2d65e-143">Ridurre i giorni delle commissioni di sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="2d65e-143">Reduce the days on subscription fees</span></span>](reduce-the-days-on-subscription-fees.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]