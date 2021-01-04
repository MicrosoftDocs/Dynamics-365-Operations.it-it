---
title: Esempio di giorni di riduzione
description: Esempio di giorni di riduzione.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87c46cd7ee7410e1c7cb88868cd19f5075482f8c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430892"
---
# <a name="reduction-days-example"></a><span data-ttu-id="eca3b-103">Esempio di giorni di riduzione</span><span class="sxs-lookup"><span data-stu-id="eca3b-103">Reduction days example</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="eca3b-104">È stata creata una transazione di sottoscrizione per la sottoscrizione di manutenzione di un cliente come descritto nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="eca3b-104">You have created a subscription transaction for a customer's maintenance subscription, as described in the following table.</span></span>

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
<th><p><span data-ttu-id="eca3b-105">Dal</span><span class="sxs-lookup"><span data-stu-id="eca3b-105">From date</span></span></p></th>
<th><p><span data-ttu-id="eca3b-106">Al</span><span class="sxs-lookup"><span data-stu-id="eca3b-106">To date</span></span></p></th>
<th><p><span data-ttu-id="eca3b-107">Sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="eca3b-107">Subscription</span></span></p></th>
<th><p><span data-ttu-id="eca3b-108">Tipo di sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="eca3b-108">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="eca3b-109">Progetto</span><span class="sxs-lookup"><span data-stu-id="eca3b-109">Project</span></span></p></th>
<th><p><span data-ttu-id="eca3b-110">Categoria</span><span class="sxs-lookup"><span data-stu-id="eca3b-110">Category</span></span></p></th>
<th><p><span data-ttu-id="eca3b-111">Valuta di vendita</span><span class="sxs-lookup"><span data-stu-id="eca3b-111">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="eca3b-112">Prezzo di vendita</span><span class="sxs-lookup"><span data-stu-id="eca3b-112">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eca3b-113">01 marzo 2011</span><span class="sxs-lookup"><span data-stu-id="eca3b-113">March 01, 2011</span></span></p></td>
<td><p><span data-ttu-id="eca3b-114">31 marzo 2011</span><span class="sxs-lookup"><span data-stu-id="eca3b-114">March 31, 2011</span></span></p></td>
<td><p><span data-ttu-id="eca3b-115">NR-2</span><span class="sxs-lookup"><span data-stu-id="eca3b-115">NR-2</span></span></p></td>
<td><p><span data-ttu-id="eca3b-116"><strong>Regolare</strong></span><span class="sxs-lookup"><span data-stu-id="eca3b-116"><strong>Regular</strong></span></span></p></td>
<td><p><span data-ttu-id="eca3b-117">9013</span><span class="sxs-lookup"><span data-stu-id="eca3b-117">9013</span></span></p></td>
<td><p><span data-ttu-id="eca3b-118">SubCat2</span><span class="sxs-lookup"><span data-stu-id="eca3b-118">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="eca3b-119">EUR</span><span class="sxs-lookup"><span data-stu-id="eca3b-119">EUR</span></span></p></td>
<td><p><span data-ttu-id="eca3b-120">200,00</span><span class="sxs-lookup"><span data-stu-id="eca3b-120">200.00</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eca3b-121">Il cliente segnala che la copertura del servizio non è necessaria per due giorni (10 marzo e 11 marzo).</span><span class="sxs-lookup"><span data-stu-id="eca3b-121">The customer reports that it does not need service coverage for two days (March 10 and March 11).</span></span> <span data-ttu-id="eca3b-122">Si concorda quindi di applicare una riduzione della sottoscrizione per i due giorni citati.</span><span class="sxs-lookup"><span data-stu-id="eca3b-122">You agree to reduce the subscription by these two days.</span></span>

<span data-ttu-id="eca3b-123">Viene quindi creata una nuova transazione di tipo **Giorni riduzione** come descritto nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="eca3b-123">You create a new transaction of the **Reduction days** type, as described in the following table.</span></span>

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
<th><p><span data-ttu-id="eca3b-124">Dal</span><span class="sxs-lookup"><span data-stu-id="eca3b-124">From date</span></span></p></th>
<th><p><span data-ttu-id="eca3b-125">Al</span><span class="sxs-lookup"><span data-stu-id="eca3b-125">To date</span></span></p></th>
<th><p><span data-ttu-id="eca3b-126">Sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="eca3b-126">Subscription</span></span></p></th>
<th><p><span data-ttu-id="eca3b-127">Tipo di sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="eca3b-127">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="eca3b-128">Progetto</span><span class="sxs-lookup"><span data-stu-id="eca3b-128">Project</span></span></p></th>
<th><p><span data-ttu-id="eca3b-129">Categoria</span><span class="sxs-lookup"><span data-stu-id="eca3b-129">Category</span></span></p></th>
<th><p><span data-ttu-id="eca3b-130">Valuta di vendita</span><span class="sxs-lookup"><span data-stu-id="eca3b-130">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="eca3b-131">Prezzo di vendita</span><span class="sxs-lookup"><span data-stu-id="eca3b-131">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eca3b-132">10 marzo 2011</span><span class="sxs-lookup"><span data-stu-id="eca3b-132">March 10, 2011</span></span></p></td>
<td><p><span data-ttu-id="eca3b-133">11 marzo 2011</span><span class="sxs-lookup"><span data-stu-id="eca3b-133">March 11, 2011</span></span></p></td>
<td><p><span data-ttu-id="eca3b-134">NR-2</span><span class="sxs-lookup"><span data-stu-id="eca3b-134">NR-2</span></span></p></td>
<td><p><span data-ttu-id="eca3b-135"><strong>Giorni riduzione</strong></span><span class="sxs-lookup"><span data-stu-id="eca3b-135"><strong>Reduction days</strong></span></span></p></td>
<td><p><span data-ttu-id="eca3b-136">9013</span><span class="sxs-lookup"><span data-stu-id="eca3b-136">9013</span></span></p></td>
<td><p><span data-ttu-id="eca3b-137">SubCat2</span><span class="sxs-lookup"><span data-stu-id="eca3b-137">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="eca3b-138">EUR</span><span class="sxs-lookup"><span data-stu-id="eca3b-138">EUR</span></span></p></td>
<td><p><span data-ttu-id="eca3b-139">-12,90</span><span class="sxs-lookup"><span data-stu-id="eca3b-139">-12.90</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eca3b-140">Quando le transazioni per marzo 2011 vengono fatturate, il prezzo di vendita di EUR 200 viene ridotto a EUR 12,90.</span><span class="sxs-lookup"><span data-stu-id="eca3b-140">When the transactions for March 2011 are invoiced, the sales price of EUR 200 is reduced by EUR 12.90.</span></span> <span data-ttu-id="eca3b-141">L'importo addebitabile per la transazione di sottoscrizione è pertanto EUR 187,10 e vengono fatturate due transazioni per un totale di EUR 187,10.</span><span class="sxs-lookup"><span data-stu-id="eca3b-141">The chargeable amount for the subscription transaction is therefore EUR 187.10, and two transactions are invoiced at a total of EUR 187.10.</span></span>

## <a name="see-also"></a><span data-ttu-id="eca3b-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eca3b-142">See also</span></span>

[<span data-ttu-id="eca3b-143">Ridurre i giorni delle commissioni di sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="eca3b-143">Reduce the days on subscription fees</span></span>](reduce-the-days-on-subscription-fees.md)

  


