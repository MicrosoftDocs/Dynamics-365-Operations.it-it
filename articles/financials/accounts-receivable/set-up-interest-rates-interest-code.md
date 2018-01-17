---
title: Impostare tassi d'interesse per un codice interessi
description: I codici interessi contengono le impostazioni che determinano quando gli interessi vengono addebitati e come vengono calcolati nei conti scaduti.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Interest
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 0279050dc8303e9c0cc3d7339c0ce072dd803707
ms.contentlocale: it-it
ms.lasthandoff: 01/17/2018

---

# <a name="set-up-interest-rates-for-an-interest-code"></a><span data-ttu-id="f27a3-103">Impostare tassi d'interesse per un codice interessi</span><span class="sxs-lookup"><span data-stu-id="f27a3-103">Set up interest rates for an interest code</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f27a3-104">I codici interessi contengono le impostazioni che determinano quando gli interessi vengono addebitati e come vengono calcolati nei conti scaduti.</span><span class="sxs-lookup"><span data-stu-id="f27a3-104">Interest codes contain settings that determine when interest is charged and how it is calculated on overdue accounts.</span></span>

<span data-ttu-id="f27a3-105">È possibile impostare un singolo codice interessi e applicarlo a più profili di registrazione cliente, codici di fatturazione o righe specifiche della fattura.</span><span class="sxs-lookup"><span data-stu-id="f27a3-105">You can set up a single interest code and apply it to multiple customer posting profiles, billing codes, or to specific invoice lines.</span></span> <span data-ttu-id="f27a3-106">Quando i dettagli del codice interessi vengono modificati, tutte le funzionalità che utilizzano il codice implementeranno automaticamente le modifiche nelle nuove transazioni.</span><span class="sxs-lookup"><span data-stu-id="f27a3-106">When the interest code details are changed, all features that use the code will automatically implement the changes on new transactions.</span></span> <span data-ttu-id="f27a3-107">Per ogni codice interessi, è possibile impostare due tipi di tassi:</span><span class="sxs-lookup"><span data-stu-id="f27a3-107">For each interest code, you can set up two types of rates:</span></span>
-   <span data-ttu-id="f27a3-108">Tassi per gli interessi attivi - Rappresentano i ricavi ottenuti tramite l'addebito di interessi sulle fatture o sulle note d'interesse.</span><span class="sxs-lookup"><span data-stu-id="f27a3-108">Rates for interest earnings − These represent revenue that is earned by charging interest on invoices or interest notes.</span></span>
-   <span data-ttu-id="f27a3-109">Tassi per gli interessi passivi - Rappresentano un costo pagato per l'interesse sulle note di accredito.</span><span class="sxs-lookup"><span data-stu-id="f27a3-109">Rates for interest payments − These represent a cost that is paid for interest on credit notes.</span></span>

<span data-ttu-id="f27a3-110">Questi tipi di tassi possono essere utilizzati contemporaneamente e nello stesso codice interessi.</span><span class="sxs-lookup"><span data-stu-id="f27a3-110">Both of these rate types can exist at the same time and in the same interest code.</span></span> <span data-ttu-id="f27a3-111">I tassi d'interesse possono essere basati su tre tipi di calcolo:</span><span class="sxs-lookup"><span data-stu-id="f27a3-111">Interest rates can be based on three calculation types:</span></span>
-   <span data-ttu-id="f27a3-112">Interesse in base a percentuale.</span><span class="sxs-lookup"><span data-stu-id="f27a3-112">Interest by percentage.</span></span>
-   <span data-ttu-id="f27a3-113">Interesse in base a importo.</span><span class="sxs-lookup"><span data-stu-id="f27a3-113">Interest by amount.</span></span>
-   <span data-ttu-id="f27a3-114">Interesse in base a intervallo, che determina una singola percentuale o un singolo importo.</span><span class="sxs-lookup"><span data-stu-id="f27a3-114">Interest by range, which results in a single percentage or amount.</span></span>

<span data-ttu-id="f27a3-115">Quando si utilizza un codice interessi per calcolare gli interessi, viene creata una nota d'interesse separata per ogni tasso d'interesse in vigore nel periodo in cui il pagamento ha superato la scadenza della transazione.</span><span class="sxs-lookup"><span data-stu-id="f27a3-115">When an interest code is used to calculate interest, a separate interest note is created for each interest rate that is in effect during the time that the payment has exceeded the transaction due date.</span></span> <span data-ttu-id="f27a3-116">Utilizzare la scheda **Redditi** nella pagina **Codice interessi** per impostare i tassi per l'interesse guadagnato con l'addebito di interessi.</span><span class="sxs-lookup"><span data-stu-id="f27a3-116">You use the **Earnings** tab on the **Interest code** page to set up interest rates for interest that you earn by charging interest.</span></span> <span data-ttu-id="f27a3-117">Per impostare i tassi per gli interessi pagati, utilizzare invece la scheda **Pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="f27a3-117">Use the **Payments** tab to set up interest rates for interest that you pay.</span></span>

## <a name="interest-rates-based-on-a-percentage"></a><span data-ttu-id="f27a3-118">Tassi d'interesse in base a una percentuale</span><span class="sxs-lookup"><span data-stu-id="f27a3-118">Interest rates based on a percentage</span></span>
<span data-ttu-id="f27a3-119">È possibile impostare tassi d'interesse che calcolano una percentuale specificata.</span><span class="sxs-lookup"><span data-stu-id="f27a3-119">You can set up interest rates that calculate a specified percentage.</span></span>

-   <span data-ttu-id="f27a3-120">L'importo degli interessi si applica a tutte le valute.</span><span class="sxs-lookup"><span data-stu-id="f27a3-120">Interest amount applies to all currencies.</span></span>
-   <span data-ttu-id="f27a3-121">È possibile immettere limiti per l'importo interessi facoltativi.</span><span class="sxs-lookup"><span data-stu-id="f27a3-121">Optional interest amount limits can be entered.</span></span>
-   <span data-ttu-id="f27a3-122">**Percentuale** è selezionato  nel campo **Calcola interessi in base a** nella pagina **Imposta codici interessi**.</span><span class="sxs-lookup"><span data-stu-id="f27a3-122">**Percentage** is selected** **in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="f27a3-123">Ad esempio, per impostare un codice interessi che valuta un interesse del 5% per ogni due mesi in cui il pagamento della fattura supera la data di scadenza della transazione, immettere 2 nel campo **Calcola interessi ogni** quindi selezionare **Mese**.</span><span class="sxs-lookup"><span data-stu-id="f27a3-123">For example, to set up an interest code that assesses 5 percent interest for every two months that the invoice payment exceeds the transaction due date, you would enter 2 in the **Calculate interest every** field and select **Month**.</span></span>

## <a name="interest-rates-based-on-amounts"></a><span data-ttu-id="f27a3-124">Tassi d'interesse in base agli importi</span><span class="sxs-lookup"><span data-stu-id="f27a3-124">Interest rates based on amounts</span></span>
<span data-ttu-id="f27a3-125">È possibile impostare tassi d'interesse che calcolano una quantità specificata per valuta.</span><span class="sxs-lookup"><span data-stu-id="f27a3-125">You can set up interest rates that calculate a specified amount per currency.</span></span>
-   <span data-ttu-id="f27a3-126">Un importo interessi è specificato per ciascuna valuta relativa al codice interessi.</span><span class="sxs-lookup"><span data-stu-id="f27a3-126">An interest amount is specified for each currency in the interest code.</span></span>
-   <span data-ttu-id="f27a3-127">È possibile immettere limiti per l'importo interessi facoltativi.</span><span class="sxs-lookup"><span data-stu-id="f27a3-127">Optional interest amount limits can be entered.</span></span>
-   <span data-ttu-id="f27a3-128">**Importo** è selezionato nel campo **Calcola interessi in base** a nella pagina **Imposta codici interessi**.</span><span class="sxs-lookup"><span data-stu-id="f27a3-128">**Amount **is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="f27a3-129">Ad esempio, per impostare un codice interessi che valuta un interesse pari a 25,00 per ogni 20 giorni in cui il pagamento della fattura supera la data di scadenza della transazione, immettere 20 nel campo **Calcola interessi ogni** e selezionare **Giorno**.</span><span class="sxs-lookup"><span data-stu-id="f27a3-129">For example, to set up an interest code that assesses interest of 25.00 for every 20 days that the invoice payment exceeds the transaction due date, you would enter 20 in the **Calculate interest every** field and select **Day**.</span></span>

## <a name="interest-rates-based-on-ranges"></a><span data-ttu-id="f27a3-130">Tassi d'interesse in base agli intervalli</span><span class="sxs-lookup"><span data-stu-id="f27a3-130">Interest rates based on ranges</span></span>
<span data-ttu-id="f27a3-131">È possibile impostare tassi d'interesse che variano a seconda dell'importo scaduto e del numero di giorni o mesi accumulati dalla scadenza della fattura.</span><span class="sxs-lookup"><span data-stu-id="f27a3-131">You can set up interest rates that vary depending on the overdue amount, the number of days that the amount is late, or the number of months that the amount is late.</span></span>
-   <span data-ttu-id="f27a3-132">È possibile utilizzare la scheda **Utili per valuta** per definire le impostazioni specifiche degli interessi per ciascuna valuta.</span><span class="sxs-lookup"><span data-stu-id="f27a3-132">You can use the **Earnings by Currency** tab to define specific interest settings for each currency.</span></span> <span data-ttu-id="f27a3-133">Qui è inoltre possibile definire l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="f27a3-133">This is also where you will define the range.</span></span>
-   <span data-ttu-id="f27a3-134">Utilizzare il pulsante **Intervalli** per aggiungere righe che rappresentano gli intervalli che si desidera impostare.</span><span class="sxs-lookup"><span data-stu-id="f27a3-134">Use the **Ranges** button to add lines that represent the ranges that you want to set up.</span></span> <span data-ttu-id="f27a3-135">Il valore **Da** rappresenta l'inizio dell'intervallo e il numero in **Valore d'interesse** rappresenta una percentuale o un importo, a seconda della selezione nel campo **Calcola interessi in base a** nella pagina **Imposta codici interessi**.</span><span class="sxs-lookup"><span data-stu-id="f27a3-135">The **From** value represents the beginning of the range and the **Interest value** number represents either a percentage or an amount, depending on the selection in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

## <a name="example-1-interest-by-range--amount"></a><span data-ttu-id="f27a3-136">Esempio 1: Interessi in base a intervallo = Importo</span><span class="sxs-lookup"><span data-stu-id="f27a3-136">Example 1: Interest by range = Amount</span></span>
<span data-ttu-id="f27a3-137">Si imposta un codice interessi che valuta gli interessi una volta per ogni tre mesi in cui il pagamento della fattura supera la data di scadenza della transazione.</span><span class="sxs-lookup"><span data-stu-id="f27a3-137">You set up an interest code that assesses interest one time for every three months that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="f27a3-138">Si desidera basare il calcolo su un valore di interesse percentuale, in base a intervalli di importi graduali.</span><span class="sxs-lookup"><span data-stu-id="f27a3-138">You want to base the calculation on a percentage interest value, according to stepped amount intervals.</span></span> <span data-ttu-id="f27a3-139">Il valore degli interessi corrisponderà all'1% per gli importi della fattura fino a 1.000,00, al 2% per gli importi da 1.001,00 a 5.000,00 e al 3% per gli importi superiori a 5.000,00.</span><span class="sxs-lookup"><span data-stu-id="f27a3-139">The interest value will be 1 percent for invoice amounts up to 1,000.00, 2 percent for amounts from 1,001.00 to 5,000.00, and 3 percent for amounts larger than 5,000.00.</span></span> <span data-ttu-id="f27a3-140">I valori del campo del codice interessi vengono impostati nel modo indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f27a3-140">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="f27a3-141">**Nome campo**</span><span class="sxs-lookup"><span data-stu-id="f27a3-141">**Field name**</span></span>                  | <span data-ttu-id="f27a3-142">**Valore campo**</span><span class="sxs-lookup"><span data-stu-id="f27a3-142">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="f27a3-143">**Codice interessi**</span><span class="sxs-lookup"><span data-stu-id="f27a3-143">**Interest code**</span></span>               | <span data-ttu-id="f27a3-144">3M%ByAmt</span><span class="sxs-lookup"><span data-stu-id="f27a3-144">3M%ByAmt</span></span>        |
| <span data-ttu-id="f27a3-145">**Calcola interessi ogni**</span><span class="sxs-lookup"><span data-stu-id="f27a3-145">**Calculate interest every**</span></span>    | <span data-ttu-id="f27a3-146">3/Mese</span><span class="sxs-lookup"><span data-stu-id="f27a3-146">3/Month</span></span>         |
| <span data-ttu-id="f27a3-147">**Interessi in base a intervallo**</span><span class="sxs-lookup"><span data-stu-id="f27a3-147">**Interest by range**</span></span>           | <span data-ttu-id="f27a3-148">Importo</span><span class="sxs-lookup"><span data-stu-id="f27a3-148">Amount</span></span>          |
| <span data-ttu-id="f27a3-149">**Calcola interessi in base a**</span><span class="sxs-lookup"><span data-stu-id="f27a3-149">**Calculate interest based on**</span></span> | <span data-ttu-id="f27a3-150">Percentuale</span><span class="sxs-lookup"><span data-stu-id="f27a3-150">Percentage</span></span>      |

<span data-ttu-id="f27a3-151">Le informazioni sull'intervallo vengono impostate nel modo indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f27a3-151">You set up the range information as follows.</span></span>

| <span data-ttu-id="f27a3-152">**Dal valore**</span><span class="sxs-lookup"><span data-stu-id="f27a3-152">**From value**</span></span> | <span data-ttu-id="f27a3-153">**Valore interessi**</span><span class="sxs-lookup"><span data-stu-id="f27a3-153">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="f27a3-154">0</span><span class="sxs-lookup"><span data-stu-id="f27a3-154">0</span></span>              | <span data-ttu-id="f27a3-155">1</span><span class="sxs-lookup"><span data-stu-id="f27a3-155">1</span></span>                  |
| <span data-ttu-id="f27a3-156">1,001</span><span class="sxs-lookup"><span data-stu-id="f27a3-156">1,001</span></span>          | <span data-ttu-id="f27a3-157">2</span><span class="sxs-lookup"><span data-stu-id="f27a3-157">2</span></span>                  |
| <span data-ttu-id="f27a3-158">5,001</span><span class="sxs-lookup"><span data-stu-id="f27a3-158">5,001</span></span>          | <span data-ttu-id="f27a3-159">3</span><span class="sxs-lookup"><span data-stu-id="f27a3-159">3</span></span>                  |

 
## <a name="example-2-interest-by-range--days"></a><span data-ttu-id="f27a3-160">Esempio 2: Interessi in base a intervallo = Giorni</span><span class="sxs-lookup"><span data-stu-id="f27a3-160">Example 2: Interest by range = Days</span></span>
--------------------------------------------------

<span data-ttu-id="f27a3-161">Si imposta un codice interessi che valuta gli interessi una volta per ogni 15 giorni in cui il pagamento della fattura supera la data di scadenza della transazione.</span><span class="sxs-lookup"><span data-stu-id="f27a3-161">You set up an interest code that assesses interest one time for every 15 days that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="f27a3-162">Si desidera basare il calcolo su un valore di interesse importo, in base a intervalli di giorni graduali.</span><span class="sxs-lookup"><span data-stu-id="f27a3-162">You want to base the calculation on an amount interest value, according to stepped day intervals.</span></span> <span data-ttu-id="f27a3-163">Il valore degli interessi sarà pari a 10,00 per 15 giorni durante i primi 60 giorni, 15,00 per 15 giorni durante l'intervallo di giorni da 61 a 90 e 20,00 per 15 giorni dal giorno 91 in poi.</span><span class="sxs-lookup"><span data-stu-id="f27a3-163">The interest value will be 10.00 per 15 days during the first 60 days, 15.00 per 15 days during days 61 to 90, and 20.00 per 15 days from day 91 and after.</span></span> <span data-ttu-id="f27a3-164">I valori del campo del codice interessi vengono impostati nel modo indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f27a3-164">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="f27a3-165">**Nome campo**</span><span class="sxs-lookup"><span data-stu-id="f27a3-165">**Field name**</span></span>                  | <span data-ttu-id="f27a3-166">**Valore campo**</span><span class="sxs-lookup"><span data-stu-id="f27a3-166">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="f27a3-167">**Codice interessi**</span><span class="sxs-lookup"><span data-stu-id="f27a3-167">**Interest code**</span></span>               | <span data-ttu-id="f27a3-168">15DAmtXDay</span><span class="sxs-lookup"><span data-stu-id="f27a3-168">15DAmtXDay</span></span>      |
| <span data-ttu-id="f27a3-169">**Calcola interessi ogni**</span><span class="sxs-lookup"><span data-stu-id="f27a3-169">**Calculate interest every**</span></span>    | <span data-ttu-id="f27a3-170">15/Giorno</span><span class="sxs-lookup"><span data-stu-id="f27a3-170">15/Day</span></span>          |
| <span data-ttu-id="f27a3-171">**Interessi in base a intervallo**</span><span class="sxs-lookup"><span data-stu-id="f27a3-171">**Interest by range**</span></span>           | <span data-ttu-id="f27a3-172">Giorni</span><span class="sxs-lookup"><span data-stu-id="f27a3-172">Days</span></span>            |
| <span data-ttu-id="f27a3-173">**Calcola interessi in base a**</span><span class="sxs-lookup"><span data-stu-id="f27a3-173">**Calculate interest based on**</span></span> | <span data-ttu-id="f27a3-174">Importo</span><span class="sxs-lookup"><span data-stu-id="f27a3-174">Amount</span></span>          |

<span data-ttu-id="f27a3-175">Le informazioni sull'intervallo vengono impostate nel modo indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f27a3-175">You set up the range information as follows.</span></span>

| <span data-ttu-id="f27a3-176">**Dal valore**</span><span class="sxs-lookup"><span data-stu-id="f27a3-176">**From value**</span></span> | <span data-ttu-id="f27a3-177">**Valore interessi**</span><span class="sxs-lookup"><span data-stu-id="f27a3-177">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="f27a3-178">0</span><span class="sxs-lookup"><span data-stu-id="f27a3-178">0</span></span>              | <span data-ttu-id="f27a3-179">10</span><span class="sxs-lookup"><span data-stu-id="f27a3-179">10</span></span>                 |
| <span data-ttu-id="f27a3-180">61</span><span class="sxs-lookup"><span data-stu-id="f27a3-180">61</span></span>             | <span data-ttu-id="f27a3-181">15</span><span class="sxs-lookup"><span data-stu-id="f27a3-181">15</span></span>                 |
| <span data-ttu-id="f27a3-182">91</span><span class="sxs-lookup"><span data-stu-id="f27a3-182">91</span></span>             | <span data-ttu-id="f27a3-183">20</span><span class="sxs-lookup"><span data-stu-id="f27a3-183">20</span></span>                 |

 
## <a name="example-3-interest-by-range--months"></a><span data-ttu-id="f27a3-184">Esempio 3: Interessi in base a intervallo = Mesi</span><span class="sxs-lookup"><span data-stu-id="f27a3-184">Example 3: Interest by range = Months</span></span>
----------------------------------------------------

<span data-ttu-id="f27a3-185">Si imposta un codice interessi che valuta gli interessi una volta per ogni mese in cui il pagamento della fattura supera la data di scadenza della transazione.</span><span class="sxs-lookup"><span data-stu-id="f27a3-185">You set up an interest code that assesses interest one time for every month that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="f27a3-186">Si desidera basare il calcolo su un valore di interesse percentuale, in base a intervalli di mesi graduali.</span><span class="sxs-lookup"><span data-stu-id="f27a3-186">You want to base the calculation on a percentage interest value, according to stepped month intervals.</span></span> <span data-ttu-id="f27a3-187">Il valore degli interessi sarà dell'1,5% al mese per i primi tre mesi di ritardo, del 2,0% al mese per i tre mesi successivi e del 2,5% al mese per ogni mese successivo ai primi sei.</span><span class="sxs-lookup"><span data-stu-id="f27a3-187">The interest value will be 1.5 percent per month for the first three overdue months, 2.0 percent per month for the second three months, and 2.5 percent per month for each month beyond the first six months.</span></span> <span data-ttu-id="f27a3-188">I valori del campo del codice interessi vengono impostati nel modo indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f27a3-188">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="f27a3-189">**Nome campo**</span><span class="sxs-lookup"><span data-stu-id="f27a3-189">**Field name**</span></span>                  | <span data-ttu-id="f27a3-190">**Valore campo**</span><span class="sxs-lookup"><span data-stu-id="f27a3-190">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="f27a3-191">**Codice interessi**</span><span class="sxs-lookup"><span data-stu-id="f27a3-191">**Interest code**</span></span>               | <span data-ttu-id="f27a3-192">1M%ByMth</span><span class="sxs-lookup"><span data-stu-id="f27a3-192">1M%ByMth</span></span>        |
| <span data-ttu-id="f27a3-193">**Calcola interessi ogni**</span><span class="sxs-lookup"><span data-stu-id="f27a3-193">**Calculate interest every**</span></span>    | <span data-ttu-id="f27a3-194">1/Mese</span><span class="sxs-lookup"><span data-stu-id="f27a3-194">1/Month</span></span>         |
| <span data-ttu-id="f27a3-195">**Interessi in base a intervallo**</span><span class="sxs-lookup"><span data-stu-id="f27a3-195">**Interest by range**</span></span>           | <span data-ttu-id="f27a3-196">Mesi</span><span class="sxs-lookup"><span data-stu-id="f27a3-196">Months</span></span>          |
| <span data-ttu-id="f27a3-197">**Calcola interessi in base a**</span><span class="sxs-lookup"><span data-stu-id="f27a3-197">**Calculate interest based on**</span></span> | <span data-ttu-id="f27a3-198">Percentuale</span><span class="sxs-lookup"><span data-stu-id="f27a3-198">Percentage</span></span>      |

<span data-ttu-id="f27a3-199">Le informazioni sull'intervallo vengono impostate nel modo indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f27a3-199">You set up the range information as follows.</span></span>

| <span data-ttu-id="f27a3-200">**Dal valore**</span><span class="sxs-lookup"><span data-stu-id="f27a3-200">**From value**</span></span> | <span data-ttu-id="f27a3-201">**Valore interessi**</span><span class="sxs-lookup"><span data-stu-id="f27a3-201">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="f27a3-202">0</span><span class="sxs-lookup"><span data-stu-id="f27a3-202">0</span></span>              | <span data-ttu-id="f27a3-203">1.5</span><span class="sxs-lookup"><span data-stu-id="f27a3-203">1.5</span></span>                |
| <span data-ttu-id="f27a3-204">4</span><span class="sxs-lookup"><span data-stu-id="f27a3-204">4</span></span>              | <span data-ttu-id="f27a3-205">2</span><span class="sxs-lookup"><span data-stu-id="f27a3-205">2</span></span>                  |
| <span data-ttu-id="f27a3-206">7</span><span class="sxs-lookup"><span data-stu-id="f27a3-206">7</span></span>              | <span data-ttu-id="f27a3-207">2,5</span><span class="sxs-lookup"><span data-stu-id="f27a3-207">2.5</span></span>                |

## <a name="new-versions"></a><span data-ttu-id="f27a3-208">Nuove versioni</span><span class="sxs-lookup"><span data-stu-id="f27a3-208">New versions</span></span>
<span data-ttu-id="f27a3-209">I codici interessi contengono una data valida.</span><span class="sxs-lookup"><span data-stu-id="f27a3-209">Interest codes are date effective.</span></span> <span data-ttu-id="f27a3-210">Se si desidera modificare il tasso d'interesse, è possibile creare una **nuova versione** valida a partire da una data futura.</span><span class="sxs-lookup"><span data-stu-id="f27a3-210">If you want to modify the interest rate, you can create a **new version** that is effective as of a future date.</span></span>

<span data-ttu-id="f27a3-211">Per visualizzare versioni diverse, è possibile utilizzare l'opzione di menu **In data** per selezionare la data limite.</span><span class="sxs-lookup"><span data-stu-id="f27a3-211">To view different versions, you can use the **As of Date** menu choice to select the cutoff date.</span></span> <span data-ttu-id="f27a3-212">È inoltre possibile selezionare **Visualizza tutti i record** per visualizzare tutti i codici interessi nella pagina.</span><span class="sxs-lookup"><span data-stu-id="f27a3-212">You can also select the **Display all records** to view all interest codes in the page.</span></span>




