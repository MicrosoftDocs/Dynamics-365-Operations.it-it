---
title: Prezzi di vendita sottoscrizione
description: Quando si crea una sottoscrizione, il prezzo di vendita deriva dall'impostazione del prezzo di vendita creata nel modulo Sottoscrizione prezzo di vendita.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b4b02af0a535e67818751c437482c3663524474
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817415"
---
# <a name="subscription-sales-prices"></a><span data-ttu-id="7aaa4-103">Prezzi di vendita sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="7aaa4-103">Subscription sales prices</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="7aaa4-104">Quando si crea una sottoscrizione, il prezzo di vendita deriva dall'impostazione del prezzo di vendita creata nel modulo **Sottoscrizione prezzo di vendita**.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-104">When you create a subscription, the sales price is derived from the sales price setup that was created in the **Sales price (subscription)** form.</span></span>

<span data-ttu-id="7aaa4-105">Nel modulo **Sottoscrizione prezzo di vendita** è possibile creare prezzi di vendita per una sottoscrizione specifica o prezzi di vendita da applicare su più larga scala.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-105">In the **Sales price (subscription)** form, you can create sales prices for a specific subscription or you can create sales prices that apply more broadly.</span></span> <span data-ttu-id="7aaa4-106">Per applicare un prezzo di vendita a una sottoscrizione, il codice periodo e la valuta della sottoscrizione e del prezzo di vendita devono essere identici.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-106">For a sales price to be applied to a subscription, the period code and the currency of the subscription must be identical to the period code and the currency of the sales price.</span></span>

<span data-ttu-id="7aaa4-107">Se il codice periodo e la valuta sono identici per la sottoscrizione e per il prezzo di vendita, i prezzi di vendita di sottoscrizione verranno selezionati sulla base delle priorità elencate nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-107">If the period code and currency are identical for the subscription and the sales price, subscription sales prices are selected on the basis of the priorities listed in the following table.</span></span> <span data-ttu-id="7aaa4-108">Una cella vuota nella tabella indica un campo vuoto e la X indica un valore uguale al valore nella sottoscrizione da cui viene generata la transazione.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-108">A blank cell in the table indicates an empty field and an X indicates a value that is equal to the value in the subscription from which the transaction is generated.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7aaa4-109">Priorità </span><span class="sxs-lookup"><span data-stu-id="7aaa4-109">Priority</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-110"><strong>Categoria</strong></span><span class="sxs-lookup"><span data-stu-id="7aaa4-110"><strong>Category</strong></span></span></p></th>
<th><p><span data-ttu-id="7aaa4-111"><strong>ID progetto</strong></span><span class="sxs-lookup"><span data-stu-id="7aaa4-111"><strong>Project ID</strong></span></span></p></th>
<th><p><span data-ttu-id="7aaa4-112"><strong>Sottoscrizione</strong></span><span class="sxs-lookup"><span data-stu-id="7aaa4-112"><strong>Subscription</strong></span></span></p></th>
<th><p><span data-ttu-id="7aaa4-113"><strong>Valuta di vendita</strong></span><span class="sxs-lookup"><span data-stu-id="7aaa4-113"><strong>Sales currency</strong></span></span></p></th>
<th><p><span data-ttu-id="7aaa4-114"><strong>Codice periodo</strong></span><span class="sxs-lookup"><span data-stu-id="7aaa4-114"><strong>Period code</strong></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aaa4-115">1</span><span class="sxs-lookup"><span data-stu-id="7aaa4-115">1</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-116">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-116">X</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-117">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-117">X</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-118">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-118">X</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-119">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-119">X</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-120">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-120">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aaa4-121">2</span><span class="sxs-lookup"><span data-stu-id="7aaa4-121">2</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="7aaa4-122">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-122">X</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-123">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-123">X</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-124">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-124">X</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-125">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-125">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aaa4-126">3</span><span class="sxs-lookup"><span data-stu-id="7aaa4-126">3</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-127">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-127">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="7aaa4-128">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-128">X</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-129">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-129">X</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-130">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-130">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aaa4-131">4</span><span class="sxs-lookup"><span data-stu-id="7aaa4-131">4</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="7aaa4-132">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-132">X</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-133">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-133">X</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-134">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-134">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aaa4-135">5</span><span class="sxs-lookup"><span data-stu-id="7aaa4-135">5</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-136">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-136">X</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-137">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-137">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="7aaa4-138">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-138">X</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-139">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-139">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aaa4-140">6</span><span class="sxs-lookup"><span data-stu-id="7aaa4-140">6</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="7aaa4-141">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-141">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="7aaa4-142">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-142">X</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-143">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-143">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aaa4-144">7</span><span class="sxs-lookup"><span data-stu-id="7aaa4-144">7</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-145">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-145">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="7aaa4-146">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-146">X</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-147">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-147">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aaa4-148">8</span><span class="sxs-lookup"><span data-stu-id="7aaa4-148">8</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="7aaa4-149">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-149">X</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-150">X</span><span class="sxs-lookup"><span data-stu-id="7aaa4-150">X</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7aaa4-151">Quando viene creata una commissione di sottoscrizione, viene selezionato come prezzo di vendita di sottoscrizione il prezzo di vendita con il livello massimo di dettagli, come indicato nella tabella sopra riportata.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-151">When a subscription fee is created, the sales price with the greatest level of detail, as noted in the table above, is selected as the subscription sales price.</span></span>

## <a name="update-and-index-subscription-sales-prices"></a><span data-ttu-id="7aaa4-152">Aggiornare e indicizzare i prezzi di vendita di sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="7aaa4-152">Update and index subscription sales prices</span></span>

<span data-ttu-id="7aaa4-153">È possibile aggiornare il prezzo di vendita di sottoscrizione aggiornando l'indice o il prezzo di base.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-153">You can update the subscription sales price by updating the base price or the index.</span></span> <span data-ttu-id="7aaa4-154">L'aggiornamento può essere eseguito in base a un valore percentuale o a un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-154">You can update by a percentage or to a new value.</span></span>

## <a name="subscription-fee-sales-prices"></a><span data-ttu-id="7aaa4-155">Prezzi di vendita di commissioni di sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="7aaa4-155">Subscription fee sales prices</span></span>

<span data-ttu-id="7aaa4-156">Quando si crea una commissione di sottoscrizione, il prezzo di vendita è basato sull'impostazione del prezzo di vendita della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-156">When you create a subscription fee, the sales price is based on the sales price setup of the subscription.</span></span> <span data-ttu-id="7aaa4-157">È possibile utilizzare il prezzo di base dell'impostazione del prezzo di sottoscrizione oppure creare prezzi di vendita indicizzati.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-157">You can either use the base price from the subscription price setup or create indexed sales prices.</span></span>

## <a name="example"></a><span data-ttu-id="7aaa4-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="7aaa4-158">Example</span></span>

<span data-ttu-id="7aaa4-159">Si desidera impostare prezzi di vendita di sottoscrizione di 500 EUR per un nuovo progetto 9030.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-159">You want to set up subscription sales prices of EUR 500 for a new project 9030.</span></span> <span data-ttu-id="7aaa4-160">Nel modulo **Sottoscrizione prezzo di vendita** creare una riga del prezzo di vendita di sottoscrizione come indicato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="7aaa4-160">In the **Sales price (subscription)** form, you create a subscription sales price line as indicated in the following table.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7aaa4-161">Valido dal</span><span class="sxs-lookup"><span data-stu-id="7aaa4-161">Valid from</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-162">Categoria</span><span class="sxs-lookup"><span data-stu-id="7aaa4-162">Category</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-163">Progetto</span><span class="sxs-lookup"><span data-stu-id="7aaa4-163">Project</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-164">Sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="7aaa4-164">Subscription</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-165">Codice periodo</span><span class="sxs-lookup"><span data-stu-id="7aaa4-165">Period code</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-166">Valuta di vendita</span><span class="sxs-lookup"><span data-stu-id="7aaa4-166">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-167">Prezzo di vendita</span><span class="sxs-lookup"><span data-stu-id="7aaa4-167">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aaa4-168">28/08/2006</span><span class="sxs-lookup"><span data-stu-id="7aaa4-168">28-08-2006</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7aaa4-169">9030</span><span class="sxs-lookup"><span data-stu-id="7aaa4-169">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7aaa4-170">Mese</span><span class="sxs-lookup"><span data-stu-id="7aaa4-170">Month</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-171">EUR</span><span class="sxs-lookup"><span data-stu-id="7aaa4-171">EUR</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-172">500</span><span class="sxs-lookup"><span data-stu-id="7aaa4-172">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7aaa4-173">Si noti che i campi **Categoria** e **Sottoscrizione** sono vuoti.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-173">Note that the **Category** and **Subscription** fields are empty.</span></span>

<span data-ttu-id="7aaa4-174">Creare a questo punto le seguenti sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-174">You then create the following subscriptions.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7aaa4-175">Sottoscrizione assistenza</span><span class="sxs-lookup"><span data-stu-id="7aaa4-175">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-176">Progetto</span><span class="sxs-lookup"><span data-stu-id="7aaa4-176">Project</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-177">Gruppo di sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="7aaa4-177">Subscription group</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-178">Categoria</span><span class="sxs-lookup"><span data-stu-id="7aaa4-178">Category</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-179">Valuta</span><span class="sxs-lookup"><span data-stu-id="7aaa4-179">Currency</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-180">Codice periodo</span><span class="sxs-lookup"><span data-stu-id="7aaa4-180">Period code</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aaa4-181">00020_135</span><span class="sxs-lookup"><span data-stu-id="7aaa4-181">00020_135</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-182">9030</span><span class="sxs-lookup"><span data-stu-id="7aaa4-182">9030</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-183">Sub1</span><span class="sxs-lookup"><span data-stu-id="7aaa4-183">Sub1</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-184">SubCat1</span><span class="sxs-lookup"><span data-stu-id="7aaa4-184">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-185">EUR</span><span class="sxs-lookup"><span data-stu-id="7aaa4-185">EUR</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-186">Mensile</span><span class="sxs-lookup"><span data-stu-id="7aaa4-186">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aaa4-187">00021_135</span><span class="sxs-lookup"><span data-stu-id="7aaa4-187">00021_135</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-188">9030</span><span class="sxs-lookup"><span data-stu-id="7aaa4-188">9030</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-189">Sub1</span><span class="sxs-lookup"><span data-stu-id="7aaa4-189">Sub1</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-190">SubCat2</span><span class="sxs-lookup"><span data-stu-id="7aaa4-190">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-191">EUR</span><span class="sxs-lookup"><span data-stu-id="7aaa4-191">EUR</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-192">Mensile</span><span class="sxs-lookup"><span data-stu-id="7aaa4-192">Monthly</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7aaa4-193">Creare ora commissioni di sottoscrizione per entrambe le sottoscrizioni del gruppo di sottoscrizioni Sub1:</span><span class="sxs-lookup"><span data-stu-id="7aaa4-193">Now you create subscription fees for both subscriptions in the subscription group Sub1:</span></span>

1.  <span data-ttu-id="7aaa4-194">Fare clic su **Gestione assistenza** \> **Impostazione** \> **Sottoscrizioni assistenza** \> **Gruppo di sottoscrizioni**.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-194">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

2.  <span data-ttu-id="7aaa4-195">Nel modulo **Gruppi di sottoscrizioni**, fare clic su **Funzione** \> **Crea commissione sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-195">In the **Subscription groups** form, click **Function** \> **Create subscription fee**.</span></span>

3.  <span data-ttu-id="7aaa4-196">Nel modulo **Crea commissione sottoscrizione**, immettere le informazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-196">In the **Create subscription fee** form, enter the appropriate information.</span></span> <span data-ttu-id="7aaa4-197">Per ulteriori informazioni, vedere [Creare transazioni di commissione di sottoscrizione](create-subscription-fee-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="7aaa4-197">For more information, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="7aaa4-198">Verranno create commissioni di sottoscrizione con prezzo di vendita di 500 EUR per entrambe le sottoscrizioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-198">Subscription fees that have a sales price of EUR 500 are created for both subscriptions, as shown in the following table.</span></span>

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
<th><p><span data-ttu-id="7aaa4-199">Data progetto</span><span class="sxs-lookup"><span data-stu-id="7aaa4-199">Project date</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-200">Sottoscrizione assistenza</span><span class="sxs-lookup"><span data-stu-id="7aaa4-200">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-201">Progetto</span><span class="sxs-lookup"><span data-stu-id="7aaa4-201">Project</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-202">Categoria</span><span class="sxs-lookup"><span data-stu-id="7aaa4-202">Category</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-203">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="7aaa4-203">Start date</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-204">Data di fine</span><span class="sxs-lookup"><span data-stu-id="7aaa4-204">End date</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-205">Valuta di vendita</span><span class="sxs-lookup"><span data-stu-id="7aaa4-205">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-206">Prezzo di vendita</span><span class="sxs-lookup"><span data-stu-id="7aaa4-206">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aaa4-207">28/08/2006</span><span class="sxs-lookup"><span data-stu-id="7aaa4-207">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-208">00020_135</span><span class="sxs-lookup"><span data-stu-id="7aaa4-208">00020_135</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-209">9030</span><span class="sxs-lookup"><span data-stu-id="7aaa4-209">9030</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-210">SubCat1</span><span class="sxs-lookup"><span data-stu-id="7aaa4-210">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-211">01/01/2007</span><span class="sxs-lookup"><span data-stu-id="7aaa4-211">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-212">31/03/2007</span><span class="sxs-lookup"><span data-stu-id="7aaa4-212">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-213">EUR</span><span class="sxs-lookup"><span data-stu-id="7aaa4-213">EUR</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-214">500</span><span class="sxs-lookup"><span data-stu-id="7aaa4-214">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aaa4-215">28/08/2006</span><span class="sxs-lookup"><span data-stu-id="7aaa4-215">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-216">00021_135</span><span class="sxs-lookup"><span data-stu-id="7aaa4-216">00021_135</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-217">9030</span><span class="sxs-lookup"><span data-stu-id="7aaa4-217">9030</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-218">SubCat2</span><span class="sxs-lookup"><span data-stu-id="7aaa4-218">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-219">01/01/2007</span><span class="sxs-lookup"><span data-stu-id="7aaa4-219">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-220">31/03/2007</span><span class="sxs-lookup"><span data-stu-id="7aaa4-220">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-221">EUR</span><span class="sxs-lookup"><span data-stu-id="7aaa4-221">EUR</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-222">500</span><span class="sxs-lookup"><span data-stu-id="7aaa4-222">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7aaa4-223">Si decide successivamente che si desidera specificare i prezzi di vendita per la categoria SubCat1 del progetto 9030.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-223">Later, you decide that you want to specify sales prices for the category SubCat1 for project 9030.</span></span> <span data-ttu-id="7aaa4-224">Viene creata pertanto una nuova riga con prezzo di vendita di 550 EUR per la combinazione del progetto 9030 e della categoria di commissione SubCat1.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-224">Therefore, you create a new sales price line that has a sales price of EUR 550 for the combination of project 9030 and fee category SubCat1.</span></span> <span data-ttu-id="7aaa4-225">Per il progetto 9030 ora sono presenti due righe di prezzo di vendita di sottoscrizione, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-225">There are now two subscription sales price lines for project 9030, as shown in the following table.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7aaa4-226">Valido dal</span><span class="sxs-lookup"><span data-stu-id="7aaa4-226">Valid from</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-227">Categoria</span><span class="sxs-lookup"><span data-stu-id="7aaa4-227">Category</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-228">Progetto</span><span class="sxs-lookup"><span data-stu-id="7aaa4-228">Project</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-229">Sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="7aaa4-229">Subscription</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-230">Codice periodo</span><span class="sxs-lookup"><span data-stu-id="7aaa4-230">Period code</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-231">Valuta</span><span class="sxs-lookup"><span data-stu-id="7aaa4-231">Currency</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-232">Prezzo di vendita</span><span class="sxs-lookup"><span data-stu-id="7aaa4-232">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aaa4-233">28/08/2007</span><span class="sxs-lookup"><span data-stu-id="7aaa4-233">28-08-2007</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7aaa4-234">9030</span><span class="sxs-lookup"><span data-stu-id="7aaa4-234">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7aaa4-235">Mese</span><span class="sxs-lookup"><span data-stu-id="7aaa4-235">Month</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-236">EUR</span><span class="sxs-lookup"><span data-stu-id="7aaa4-236">EUR</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-237">500</span><span class="sxs-lookup"><span data-stu-id="7aaa4-237">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aaa4-238">28/08/2007</span><span class="sxs-lookup"><span data-stu-id="7aaa4-238">28-08-2007</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-239">SubCat1</span><span class="sxs-lookup"><span data-stu-id="7aaa4-239">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-240">9030</span><span class="sxs-lookup"><span data-stu-id="7aaa4-240">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7aaa4-241">Mese</span><span class="sxs-lookup"><span data-stu-id="7aaa4-241">Month</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-242">EUR</span><span class="sxs-lookup"><span data-stu-id="7aaa4-242">EUR</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-243">550</span><span class="sxs-lookup"><span data-stu-id="7aaa4-243">550</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7aaa4-244">Ripetere la procedura sopra descritta per creare commissioni di sottoscrizione per entrambe le sottoscrizioni del gruppo di sottoscrizioni Sub1.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-244">You repeat the procedure described above to create subscription fees for both subscriptions in the subscription group Sub1.</span></span> <span data-ttu-id="7aaa4-245">Nella tabella seguente vengono illustrate le transazioni create per ogni sottoscrizione collegata al gruppo di sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-245">The following table shows the transactions that are created for each subscription that is attached to the subscription group.</span></span>

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
<th><p><span data-ttu-id="7aaa4-246">Data progetto</span><span class="sxs-lookup"><span data-stu-id="7aaa4-246">Project date</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-247">Sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="7aaa4-247">Subscription</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-248">Progetto</span><span class="sxs-lookup"><span data-stu-id="7aaa4-248">Project</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-249">Categoria</span><span class="sxs-lookup"><span data-stu-id="7aaa4-249">Category</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-250">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="7aaa4-250">Start date</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-251">Data di fine</span><span class="sxs-lookup"><span data-stu-id="7aaa4-251">End date</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-252">Valuta di vendita</span><span class="sxs-lookup"><span data-stu-id="7aaa4-252">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="7aaa4-253">Prezzo di vendita</span><span class="sxs-lookup"><span data-stu-id="7aaa4-253">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aaa4-254">28/07/2007</span><span class="sxs-lookup"><span data-stu-id="7aaa4-254">28-07-2007</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-255">00020_135</span><span class="sxs-lookup"><span data-stu-id="7aaa4-255">00020_135</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-256">9030</span><span class="sxs-lookup"><span data-stu-id="7aaa4-256">9030</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-257">SubCat1</span><span class="sxs-lookup"><span data-stu-id="7aaa4-257">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-258">01/01/2008</span><span class="sxs-lookup"><span data-stu-id="7aaa4-258">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-259">31/03/2008</span><span class="sxs-lookup"><span data-stu-id="7aaa4-259">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-260">EUR</span><span class="sxs-lookup"><span data-stu-id="7aaa4-260">EUR</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-261">550</span><span class="sxs-lookup"><span data-stu-id="7aaa4-261">550</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aaa4-262">28/07/2008</span><span class="sxs-lookup"><span data-stu-id="7aaa4-262">28-07-2008</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-263">00021_135</span><span class="sxs-lookup"><span data-stu-id="7aaa4-263">00021_135</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-264">9030</span><span class="sxs-lookup"><span data-stu-id="7aaa4-264">9030</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-265">SubCat2</span><span class="sxs-lookup"><span data-stu-id="7aaa4-265">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-266">01/01/2008</span><span class="sxs-lookup"><span data-stu-id="7aaa4-266">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-267">31/03/2008</span><span class="sxs-lookup"><span data-stu-id="7aaa4-267">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-268">EUR</span><span class="sxs-lookup"><span data-stu-id="7aaa4-268">EUR</span></span></p></td>
<td><p><span data-ttu-id="7aaa4-269">500</span><span class="sxs-lookup"><span data-stu-id="7aaa4-269">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7aaa4-270">Nella prima transazione della sottoscrizione 00020\_135 il prezzo di vendita di 550 EUR deriva dal prezzo di vendita di sottoscrizione impostato per la combinazione di progetto e categoria specifici.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-270">In the first transaction for subscription 00020\_135, the sales price of EUR 550 derives from the subscription sales price that is set up for the combination of the specific project and category.</span></span> <span data-ttu-id="7aaa4-271">Nella seconda transazione della sottoscrizione 00021\_135 il prezzo di vendita di 500 EUR viene utilizzato come prezzo di vendita di sottoscrizione del progetto, poiché per la combinazione del progetto 9030 e della categoria SubCat2 non è impostato alcun prezzo.</span><span class="sxs-lookup"><span data-stu-id="7aaa4-271">In the second transaction for subscription 00021\_135, the sales price of EUR 500 is used as the project subscription sales price because there is no price set up for the combination of project 9030 and category SubCat2.</span></span>

## <a name="see-also"></a><span data-ttu-id="7aaa4-272">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7aaa4-272">See also</span></span>

[<span data-ttu-id="7aaa4-273">Aggiornare e indicizzare i prezzi di vendita di sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="7aaa4-273">Update and index subscription sales prices</span></span>](update-and-index-subscription-sales-prices.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]