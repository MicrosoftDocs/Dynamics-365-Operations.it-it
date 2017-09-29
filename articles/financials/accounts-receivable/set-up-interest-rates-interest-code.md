---
title: Impostare tassi d'interesse per un codice interessi
description: I codici interessi contengono le impostazioni che determinano quando gli interessi vengono addebitati e come vengono calcolati nei conti scaduti.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 59acfaa93b1352f2be6d750dea6bdd740bac0312
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---

# <a name="set-up-interest-rates-for-an-interest-code"></a><span data-ttu-id="cd457-103">Impostare tassi d'interesse per un codice interessi</span><span class="sxs-lookup"><span data-stu-id="cd457-103">Set up interest rates for an interest code</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="cd457-104">I codici interessi contengono le impostazioni che determinano quando gli interessi vengono addebitati e come vengono calcolati nei conti scaduti.</span><span class="sxs-lookup"><span data-stu-id="cd457-104">Interest codes contain settings that determine when interest is charged and how it is calculated on overdue accounts.</span></span>

<span data-ttu-id="cd457-105">È possibile impostare un singolo codice interessi e applicarlo a più profili di registrazione cliente, codici di fatturazione o righe specifiche della fattura.</span><span class="sxs-lookup"><span data-stu-id="cd457-105">You can set up a single interest code and apply it to multiple customer posting profiles, billing codes, or to specific invoice lines.</span></span> <span data-ttu-id="cd457-106">Quando i dettagli del codice interessi vengono modificati, tutte le funzionalità che utilizzano il codice implementeranno automaticamente le modifiche nelle nuove transazioni.</span><span class="sxs-lookup"><span data-stu-id="cd457-106">When the interest code details are changed, all features that use the code will automatically implement the changes on new transactions.</span></span> <span data-ttu-id="cd457-107">Per ogni codice interessi, è possibile impostare due tipi di tassi:</span><span class="sxs-lookup"><span data-stu-id="cd457-107">For each interest code, you can set up two types of rates:</span></span>
-   <span data-ttu-id="cd457-108">Tassi per gli interessi attivi - Rappresentano i ricavi ottenuti tramite l'addebito di interessi sulle fatture o sulle note d'interesse.</span><span class="sxs-lookup"><span data-stu-id="cd457-108">Rates for interest earnings − These represent revenue that is earned by charging interest on invoices or interest notes.</span></span>
-   <span data-ttu-id="cd457-109">Tassi per gli interessi passivi - Rappresentano un costo pagato per l'interesse sulle note di accredito.</span><span class="sxs-lookup"><span data-stu-id="cd457-109">Rates for interest payments − These represent a cost that is paid for interest on credit notes.</span></span>

<span data-ttu-id="cd457-110">Questi tipi di tassi possono essere utilizzati contemporaneamente e nello stesso codice interessi.</span><span class="sxs-lookup"><span data-stu-id="cd457-110">Both of these rate types can exist at the same time and in the same interest code.</span></span> <span data-ttu-id="cd457-111">I tassi d'interesse possono essere basati su tre tipi di calcolo:</span><span class="sxs-lookup"><span data-stu-id="cd457-111">Interest rates can be based on three calculation types:</span></span>
-   <span data-ttu-id="cd457-112">Interesse in base a percentuale.</span><span class="sxs-lookup"><span data-stu-id="cd457-112">Interest by percentage.</span></span>
-   <span data-ttu-id="cd457-113">Interesse in base a importo.</span><span class="sxs-lookup"><span data-stu-id="cd457-113">Interest by amount.</span></span>
-   <span data-ttu-id="cd457-114">Interesse in base a intervallo, che determina una singola percentuale o un singolo importo.</span><span class="sxs-lookup"><span data-stu-id="cd457-114">Interest by range, which results in a single percentage or amount.</span></span>

<span data-ttu-id="cd457-115">Quando si utilizza un codice interessi per calcolare gli interessi, viene creata una nota d'interesse separata per ogni tasso d'interesse in vigore nel periodo in cui il pagamento ha superato la scadenza della transazione.</span><span class="sxs-lookup"><span data-stu-id="cd457-115">When an interest code is used to calculate interest, a separate interest note is created for each interest rate that is in effect during the time that the payment has exceeded the transaction due date.</span></span> <span data-ttu-id="cd457-116">Utilizzare la scheda **Redditi** nella pagina **Codice interessi** per impostare i tassi per l'interesse guadagnato con l'addebito di interessi.</span><span class="sxs-lookup"><span data-stu-id="cd457-116">You use the **Earnings** tab on the **Interest code** page to set up interest rates for interest that you earn by charging interest.</span></span> <span data-ttu-id="cd457-117">Per impostare i tassi per gli interessi pagati, utilizzare invece la scheda **Pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="cd457-117">Use the **Payments** tab to set up interest rates for interest that you pay.</span></span>

## <a name="interest-rates-based-on-a-percentage"></a><span data-ttu-id="cd457-118">Tassi d'interesse in base a una percentuale</span><span class="sxs-lookup"><span data-stu-id="cd457-118">Interest rates based on a percentage</span></span>
<span data-ttu-id="cd457-119">È possibile impostare tassi d'interesse che calcolano una percentuale specificata.</span><span class="sxs-lookup"><span data-stu-id="cd457-119">You can set up interest rates that calculate a specified percentage.</span></span>

-   <span data-ttu-id="cd457-120">L'importo degli interessi si applica a tutte le valute.</span><span class="sxs-lookup"><span data-stu-id="cd457-120">Interest amount applies to all currencies.</span></span>
-   <span data-ttu-id="cd457-121">È possibile immettere limiti per l'importo interessi facoltativi.</span><span class="sxs-lookup"><span data-stu-id="cd457-121">Optional interest amount limits can be entered.</span></span>
-   <span data-ttu-id="cd457-122">**Percentuale** è selezionato  nel campo **Calcola interessi in base a** nella pagina **Imposta codici interessi**.</span><span class="sxs-lookup"><span data-stu-id="cd457-122">**Percentage** is selected** **in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="cd457-123">Ad esempio, per impostare un codice interessi che valuta un interesse del 5% per ogni due mesi in cui il pagamento della fattura supera la data di scadenza della transazione, immettere 2 nel campo **Calcola interessi ogni** quindi selezionare **Mese**.</span><span class="sxs-lookup"><span data-stu-id="cd457-123">For example, to set up an interest code that assesses 5 percent interest for every two months that the invoice payment exceeds the transaction due date, you would enter 2 in the **Calculate interest every** field and select **Month**.</span></span>

## <a name="interest-rates-based-on-amounts"></a><span data-ttu-id="cd457-124">Tassi d'interesse in base agli importi</span><span class="sxs-lookup"><span data-stu-id="cd457-124">Interest rates based on amounts</span></span>
<span data-ttu-id="cd457-125">È possibile impostare tassi d'interesse che calcolano una quantità specificata per valuta.</span><span class="sxs-lookup"><span data-stu-id="cd457-125">You can set up interest rates that calculate a specified amount per currency.</span></span>
-   <span data-ttu-id="cd457-126">Un importo interessi è specificato per ciascuna valuta relativa al codice interessi.</span><span class="sxs-lookup"><span data-stu-id="cd457-126">An interest amount is specified for each currency in the interest code.</span></span>
-   <span data-ttu-id="cd457-127">È possibile immettere limiti per l'importo interessi facoltativi.</span><span class="sxs-lookup"><span data-stu-id="cd457-127">Optional interest amount limits can be entered.</span></span>
-   <span data-ttu-id="cd457-128">**Importo** è selezionato nel campo **Calcola interessi in base** a nella pagina **Imposta codici interessi**.</span><span class="sxs-lookup"><span data-stu-id="cd457-128">**Amount **is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="cd457-129">Ad esempio, per impostare un codice interessi che valuta un interesse pari a 25,00 per ogni 20 giorni in cui il pagamento della fattura supera la data di scadenza della transazione, immettere 20 nel campo **Calcola interessi ogni** e selezionare **Giorno**.</span><span class="sxs-lookup"><span data-stu-id="cd457-129">For example, to set up an interest code that assesses interest of 25.00 for every 20 days that the invoice payment exceeds the transaction due date, you would enter 20 in the **Calculate interest every** field and select **Day**.</span></span>

## <a name="interest-rates-based-on-ranges"></a><span data-ttu-id="cd457-130">Tassi d'interesse in base agli intervalli</span><span class="sxs-lookup"><span data-stu-id="cd457-130">Interest rates based on ranges</span></span>
<span data-ttu-id="cd457-131">È possibile impostare tassi d'interesse che variano a seconda dell'importo scaduto e del numero di giorni o mesi accumulati dalla scadenza della fattura.</span><span class="sxs-lookup"><span data-stu-id="cd457-131">You can set up interest rates that vary depending on the overdue amount, the number of days that the amount is late, or the number of months that the amount is late.</span></span>
-   <span data-ttu-id="cd457-132">È possibile utilizzare la scheda **Utili per valuta** per definire le impostazioni specifiche degli interessi per ciascuna valuta.</span><span class="sxs-lookup"><span data-stu-id="cd457-132">You can use the **Earnings by Currency** tab to define specific interest settings for each currency.</span></span> <span data-ttu-id="cd457-133">Qui è inoltre possibile definire l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="cd457-133">This is also where you will define the range.</span></span>
-   <span data-ttu-id="cd457-134">Utilizzare il pulsante **Intervalli** per aggiungere righe che rappresentano gli intervalli che si desidera impostare.</span><span class="sxs-lookup"><span data-stu-id="cd457-134">Use the **Ranges** button to add lines that represent the ranges that you want to set up.</span></span> <span data-ttu-id="cd457-135">Il valore **Da** rappresenta l'inizio dell'intervallo e il numero in **Valore d'interesse** rappresenta una percentuale o un importo, a seconda della selezione nel campo **Calcola interessi in base a** nella pagina **Imposta codici interessi**.</span><span class="sxs-lookup"><span data-stu-id="cd457-135">The **From** value represents the beginning of the range and the **Interest value** number represents either a percentage or an amount, depending on the selection in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

## <a name="example-1-interest-by-range--amount"></a><span data-ttu-id="cd457-136">Esempio 1: Interessi in base a intervallo = Importo</span><span class="sxs-lookup"><span data-stu-id="cd457-136">Example 1: Interest by range = Amount</span></span>
<span data-ttu-id="cd457-137">Si imposta un codice interessi che valuta gli interessi una volta per ogni tre mesi in cui il pagamento della fattura supera la data di scadenza della transazione.</span><span class="sxs-lookup"><span data-stu-id="cd457-137">You set up an interest code that assesses interest one time for every three months that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="cd457-138">Si desidera basare il calcolo su un valore di interesse percentuale, in base a intervalli di importi graduali.</span><span class="sxs-lookup"><span data-stu-id="cd457-138">You want to base the calculation on a percentage interest value, according to stepped amount intervals.</span></span> <span data-ttu-id="cd457-139">Il valore degli interessi corrisponderà all'1% per gli importi della fattura fino a 1.000,00, al 2% per gli importi da 1.001,00 a 5.000,00 e al 3% per gli importi superiori a 5.000,00.</span><span class="sxs-lookup"><span data-stu-id="cd457-139">The interest value will be 1 percent for invoice amounts up to 1,000.00, 2 percent for amounts from 1,001.00 to 5,000.00, and 3 percent for amounts larger than 5,000.00.</span></span> <span data-ttu-id="cd457-140">I valori del campo del codice interessi vengono impostati nel modo indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="cd457-140">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="cd457-141">**Nome campo**</span><span class="sxs-lookup"><span data-stu-id="cd457-141">**Field name**</span></span>                  | <span data-ttu-id="cd457-142">**Valore campo**</span><span class="sxs-lookup"><span data-stu-id="cd457-142">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="cd457-143">**Codice interessi**</span><span class="sxs-lookup"><span data-stu-id="cd457-143">**Interest code**</span></span>               | <span data-ttu-id="cd457-144">3M%ByAmt</span><span class="sxs-lookup"><span data-stu-id="cd457-144">3M%ByAmt</span></span>        |
| <span data-ttu-id="cd457-145">**Calcola interessi ogni**</span><span class="sxs-lookup"><span data-stu-id="cd457-145">**Calculate interest every**</span></span>    | <span data-ttu-id="cd457-146">3/Mese</span><span class="sxs-lookup"><span data-stu-id="cd457-146">3/Month</span></span>         |
| <span data-ttu-id="cd457-147">**Interessi in base a intervallo**</span><span class="sxs-lookup"><span data-stu-id="cd457-147">**Interest by range**</span></span>           | <span data-ttu-id="cd457-148">Importo</span><span class="sxs-lookup"><span data-stu-id="cd457-148">Amount</span></span>          |
| <span data-ttu-id="cd457-149">**Calcola interessi in base a**</span><span class="sxs-lookup"><span data-stu-id="cd457-149">**Calculate interest based on**</span></span> | <span data-ttu-id="cd457-150">Percentuale</span><span class="sxs-lookup"><span data-stu-id="cd457-150">Percentage</span></span>      |

<span data-ttu-id="cd457-151">Le informazioni sull'intervallo vengono impostate nel modo indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="cd457-151">You set up the range information as follows.</span></span>

| <span data-ttu-id="cd457-152">**Dal valore**</span><span class="sxs-lookup"><span data-stu-id="cd457-152">**From value**</span></span> | <span data-ttu-id="cd457-153">**Valore interessi**</span><span class="sxs-lookup"><span data-stu-id="cd457-153">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="cd457-154">0</span><span class="sxs-lookup"><span data-stu-id="cd457-154">0</span></span>              | <span data-ttu-id="cd457-155">1</span><span class="sxs-lookup"><span data-stu-id="cd457-155">1</span></span>                  |
| <span data-ttu-id="cd457-156">1,001</span><span class="sxs-lookup"><span data-stu-id="cd457-156">1,001</span></span>          | <span data-ttu-id="cd457-157">2</span><span class="sxs-lookup"><span data-stu-id="cd457-157">2</span></span>                  |
| <span data-ttu-id="cd457-158">5,001</span><span class="sxs-lookup"><span data-stu-id="cd457-158">5,001</span></span>          | <span data-ttu-id="cd457-159">3</span><span class="sxs-lookup"><span data-stu-id="cd457-159">3</span></span>                  |

 
## <a name="example-2-interest-by-range--days"></a><span data-ttu-id="cd457-160">Esempio 2: Interessi in base a intervallo = Giorni</span><span class="sxs-lookup"><span data-stu-id="cd457-160">Example 2: Interest by range = Days</span></span>
--------------------------------------------------

<span data-ttu-id="cd457-161">Si imposta un codice interessi che valuta gli interessi una volta per ogni 15 giorni in cui il pagamento della fattura supera la data di scadenza della transazione.</span><span class="sxs-lookup"><span data-stu-id="cd457-161">You set up an interest code that assesses interest one time for every 15 days that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="cd457-162">Si desidera basare il calcolo su un valore di interesse importo, in base a intervalli di giorni graduali.</span><span class="sxs-lookup"><span data-stu-id="cd457-162">You want to base the calculation on an amount interest value, according to stepped day intervals.</span></span> <span data-ttu-id="cd457-163">Il valore degli interessi sarà pari a 10,00 per 15 giorni durante i primi 60 giorni, 15,00 per 15 giorni durante l'intervallo di giorni da 61 a 90 e 20,00 per 15 giorni dal giorno 91 in poi.</span><span class="sxs-lookup"><span data-stu-id="cd457-163">The interest value will be 10.00 per 15 days during the first 60 days, 15.00 per 15 days during days 61 to 90, and 20.00 per 15 days from day 91 and after.</span></span> <span data-ttu-id="cd457-164">I valori del campo del codice interessi vengono impostati nel modo indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="cd457-164">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="cd457-165">**Nome campo**</span><span class="sxs-lookup"><span data-stu-id="cd457-165">**Field name**</span></span>                  | <span data-ttu-id="cd457-166">**Valore campo**</span><span class="sxs-lookup"><span data-stu-id="cd457-166">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="cd457-167">**Codice interessi**</span><span class="sxs-lookup"><span data-stu-id="cd457-167">**Interest code**</span></span>               | <span data-ttu-id="cd457-168">15DAmtXDay</span><span class="sxs-lookup"><span data-stu-id="cd457-168">15DAmtXDay</span></span>      |
| <span data-ttu-id="cd457-169">**Calcola interessi ogni**</span><span class="sxs-lookup"><span data-stu-id="cd457-169">**Calculate interest every**</span></span>    | <span data-ttu-id="cd457-170">15/Giorno</span><span class="sxs-lookup"><span data-stu-id="cd457-170">15/Day</span></span>          |
| <span data-ttu-id="cd457-171">**Interessi in base a intervallo**</span><span class="sxs-lookup"><span data-stu-id="cd457-171">**Interest by range**</span></span>           | <span data-ttu-id="cd457-172">Giorni</span><span class="sxs-lookup"><span data-stu-id="cd457-172">Days</span></span>            |
| <span data-ttu-id="cd457-173">**Calcola interessi in base a**</span><span class="sxs-lookup"><span data-stu-id="cd457-173">**Calculate interest based on**</span></span> | <span data-ttu-id="cd457-174">Importo</span><span class="sxs-lookup"><span data-stu-id="cd457-174">Amount</span></span>          |

<span data-ttu-id="cd457-175">Le informazioni sull'intervallo vengono impostate nel modo indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="cd457-175">You set up the range information as follows.</span></span>

| <span data-ttu-id="cd457-176">**Dal valore**</span><span class="sxs-lookup"><span data-stu-id="cd457-176">**From value**</span></span> | <span data-ttu-id="cd457-177">**Valore interessi**</span><span class="sxs-lookup"><span data-stu-id="cd457-177">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="cd457-178">0</span><span class="sxs-lookup"><span data-stu-id="cd457-178">0</span></span>              | <span data-ttu-id="cd457-179">10</span><span class="sxs-lookup"><span data-stu-id="cd457-179">10</span></span>                 |
| <span data-ttu-id="cd457-180">61</span><span class="sxs-lookup"><span data-stu-id="cd457-180">61</span></span>             | <span data-ttu-id="cd457-181">15</span><span class="sxs-lookup"><span data-stu-id="cd457-181">15</span></span>                 |
| <span data-ttu-id="cd457-182">91</span><span class="sxs-lookup"><span data-stu-id="cd457-182">91</span></span>             | <span data-ttu-id="cd457-183">20</span><span class="sxs-lookup"><span data-stu-id="cd457-183">20</span></span>                 |

 
## <a name="example-3-interest-by-range--months"></a><span data-ttu-id="cd457-184">Esempio 3: Interessi in base a intervallo = Mesi</span><span class="sxs-lookup"><span data-stu-id="cd457-184">Example 3: Interest by range = Months</span></span>
----------------------------------------------------

<span data-ttu-id="cd457-185">Si imposta un codice interessi che valuta gli interessi una volta per ogni mese in cui il pagamento della fattura supera la data di scadenza della transazione.</span><span class="sxs-lookup"><span data-stu-id="cd457-185">You set up an interest code that assesses interest one time for every month that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="cd457-186">Si desidera basare il calcolo su un valore di interesse percentuale, in base a intervalli di mesi graduali.</span><span class="sxs-lookup"><span data-stu-id="cd457-186">You want to base the calculation on a percentage interest value, according to stepped month intervals.</span></span> <span data-ttu-id="cd457-187">Il valore degli interessi sarà dell'1,5% al mese per i primi tre mesi di ritardo, del 2,0% al mese per i tre mesi successivi e del 2,5% al mese per ogni mese successivo ai primi sei.</span><span class="sxs-lookup"><span data-stu-id="cd457-187">The interest value will be 1.5 percent per month for the first three overdue months, 2.0 percent per month for the second three months, and 2.5 percent per month for each month beyond the first six months.</span></span> <span data-ttu-id="cd457-188">I valori del campo del codice interessi vengono impostati nel modo indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="cd457-188">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="cd457-189">**Nome campo**</span><span class="sxs-lookup"><span data-stu-id="cd457-189">**Field name**</span></span>                  | <span data-ttu-id="cd457-190">**Valore campo**</span><span class="sxs-lookup"><span data-stu-id="cd457-190">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="cd457-191">**Codice interessi**</span><span class="sxs-lookup"><span data-stu-id="cd457-191">**Interest code**</span></span>               | <span data-ttu-id="cd457-192">1M%ByMth</span><span class="sxs-lookup"><span data-stu-id="cd457-192">1M%ByMth</span></span>        |
| <span data-ttu-id="cd457-193">**Calcola interessi ogni**</span><span class="sxs-lookup"><span data-stu-id="cd457-193">**Calculate interest every**</span></span>    | <span data-ttu-id="cd457-194">1/Mese</span><span class="sxs-lookup"><span data-stu-id="cd457-194">1/Month</span></span>         |
| <span data-ttu-id="cd457-195">**Interessi in base a intervallo**</span><span class="sxs-lookup"><span data-stu-id="cd457-195">**Interest by range**</span></span>           | <span data-ttu-id="cd457-196">Mesi</span><span class="sxs-lookup"><span data-stu-id="cd457-196">Months</span></span>          |
| <span data-ttu-id="cd457-197">**Calcola interessi in base a**</span><span class="sxs-lookup"><span data-stu-id="cd457-197">**Calculate interest based on**</span></span> | <span data-ttu-id="cd457-198">Percentuale</span><span class="sxs-lookup"><span data-stu-id="cd457-198">Percentage</span></span>      |

<span data-ttu-id="cd457-199">Le informazioni sull'intervallo vengono impostate nel modo indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="cd457-199">You set up the range information as follows.</span></span>

| <span data-ttu-id="cd457-200">**Dal valore**</span><span class="sxs-lookup"><span data-stu-id="cd457-200">**From value**</span></span> | <span data-ttu-id="cd457-201">**Valore interessi**</span><span class="sxs-lookup"><span data-stu-id="cd457-201">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="cd457-202">0</span><span class="sxs-lookup"><span data-stu-id="cd457-202">0</span></span>              | <span data-ttu-id="cd457-203">1.5</span><span class="sxs-lookup"><span data-stu-id="cd457-203">1.5</span></span>                |
| <span data-ttu-id="cd457-204">4</span><span class="sxs-lookup"><span data-stu-id="cd457-204">4</span></span>              | <span data-ttu-id="cd457-205">2</span><span class="sxs-lookup"><span data-stu-id="cd457-205">2</span></span>                  |
| <span data-ttu-id="cd457-206">7</span><span class="sxs-lookup"><span data-stu-id="cd457-206">7</span></span>              | <span data-ttu-id="cd457-207">2,5</span><span class="sxs-lookup"><span data-stu-id="cd457-207">2.5</span></span>                |

## <a name="new-versions"></a><span data-ttu-id="cd457-208">Nuove versioni</span><span class="sxs-lookup"><span data-stu-id="cd457-208">New versions</span></span>
<span data-ttu-id="cd457-209">I codici interessi contengono una data valida.</span><span class="sxs-lookup"><span data-stu-id="cd457-209">Interest codes are date effective.</span></span> <span data-ttu-id="cd457-210">Se si desidera modificare il tasso d'interesse, è possibile creare una **nuova versione** valida a partire da una data futura.</span><span class="sxs-lookup"><span data-stu-id="cd457-210">If you want to modify the interest rate, you can create a **new version** that is effective as of a future date.</span></span>

<span data-ttu-id="cd457-211">Per visualizzare versioni diverse, è possibile utilizzare l'opzione di menu **In data** per selezionare la data limite.</span><span class="sxs-lookup"><span data-stu-id="cd457-211">To view different versions, you can use the **As of Date** menu choice to select the cutoff date.</span></span> <span data-ttu-id="cd457-212">È inoltre possibile selezionare **Visualizza tutti i record** per visualizzare tutti i codici interessi nella pagina.</span><span class="sxs-lookup"><span data-stu-id="cd457-212">You can also select the **Display all records** to view all interest codes in the page.</span></span>




