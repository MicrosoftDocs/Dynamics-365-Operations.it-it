---
title: Metodi di calcolo IVA nel campo Origine
description: Questo articolo illustra le opzioni nel campo Origine nella pagina Codici IVA e spiega come viene calcolata l'IVA in base all'opzione selezionata per un codice IVA.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e57e97847c6aa7a775b0f2639dff93f1e3a9e7a2
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189375"
---
# <a name="sales-tax-calculation-methods-in-the-origin-field"></a><span data-ttu-id="0db3d-103">Metodi di calcolo IVA nel campo Origine</span><span class="sxs-lookup"><span data-stu-id="0db3d-103">Sales tax calculation methods in the Origin field</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0db3d-104">Questo articolo illustra le opzioni nel campo Origine nella pagina Codici IVA e spiega come viene calcolata l'IVA in base all'opzione selezionata per un codice IVA.</span><span class="sxs-lookup"><span data-stu-id="0db3d-104">This article explains the options in the Origin field on the sales tax codes page and how sales tax is calculated based on the selected option for a sales tax code.</span></span>

<span data-ttu-id="0db3d-105">Per ogni codice IVA creato nella pagina Codici IVA è necessario selezionare il metodo di calcolo da applicare all'importo imponibile nel campo Origine.</span><span class="sxs-lookup"><span data-stu-id="0db3d-105">For each sales tax code that you create in the Sales tax codes page, you must select the method of calculation to apply to the tax base amount in the Origin field.</span></span>

## <a name="percentage-of-net-amount"></a><span data-ttu-id="0db3d-106">Percentuale dell'importo netto</span><span class="sxs-lookup"><span data-stu-id="0db3d-106">Percentage of net amount</span></span>
<span data-ttu-id="0db3d-107">Il metodo di calcolo Percentuale dell'importo netto è il valore predefinito nel campo Origine.</span><span class="sxs-lookup"><span data-stu-id="0db3d-107">The Percentage of net amount calculation method is the default value in the Origin field.</span></span> <span data-ttu-id="0db3d-108">L'IVA viene calcolata come percentuale dell'importo di acquisto o di vendita, esclusi gli altri importi IVA.</span><span class="sxs-lookup"><span data-stu-id="0db3d-108">The sales tax is calculated as a percentage of the purchase or sales amount, excluding any other sales taxes.</span></span>
### <a name="example"></a><span data-ttu-id="0db3d-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="0db3d-109">Example</span></span>

<span data-ttu-id="0db3d-110">L'aliquota IVA è 25%.</span><span class="sxs-lookup"><span data-stu-id="0db3d-110">The tax rate is 25%.</span></span> <span data-ttu-id="0db3d-111">Si supponga che nella riga della fattura sia indicata una quantità pari a 10 articoli al prezzo di 1,00 ciascuno e che al cliente venga concesso uno sconto riga del 10%.</span><span class="sxs-lookup"><span data-stu-id="0db3d-111">The invoice line shows a quantity of 10 items at 1.00 each, and the customer is allowed a 10% line discount.</span></span> <span data-ttu-id="0db3d-112">Importo netto: (10 x 1,00) -10% = 9,00 IVA: 9,00 x 25% = 2,25 Importo totale: 9,00 + 2,25 = 11,25</span><span class="sxs-lookup"><span data-stu-id="0db3d-112">Net amount: (10 x 1.00) -10% = 9.00 Sales tax: 9.00 x 25% = 2.25 Total amount: 9.00 + 2.25 = 11.25</span></span>

## <a name="percentage-of-gross-amount"></a><span data-ttu-id="0db3d-113"> Percentuale dell'importo lordo</span><span class="sxs-lookup"><span data-stu-id="0db3d-113">Percentage of gross amount</span></span>
<span data-ttu-id="0db3d-114">Se si seleziona il metodo Percentuale dell'importo lordo, l'IVA viene calcolata come percentuale dell'importo di vendita lordo.</span><span class="sxs-lookup"><span data-stu-id="0db3d-114">If you select the Percentage of gross amount method, the sales tax is calculated as a percentage of the gross sales amount.</span></span> <span data-ttu-id="0db3d-115">L'importo lordo è l'importo netto della riga più eventuali imposte e commissioni per la riga tranne l'imposta con Origine = Percentuale dell'importo lordo.</span><span class="sxs-lookup"><span data-stu-id="0db3d-115">The gross amount is the line net amount plus all taxes and fees for the line except the one tax with Origin = Percentage of gross amount.</span></span>
### <a name="example"></a><span data-ttu-id="0db3d-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="0db3d-116">Example</span></span>

<span data-ttu-id="0db3d-117">L'ufficio tributario richiede il versamento di imposte speciali su un articolo.</span><span class="sxs-lookup"><span data-stu-id="0db3d-117">The tax authority has imposed special duties on an item.</span></span> <span data-ttu-id="0db3d-118">Gli importi delle imposte vengono aggiunti all'importo netto prima del calcolo dell'IVA.</span><span class="sxs-lookup"><span data-stu-id="0db3d-118">The duty amounts are added to the net amount before sales tax is calculated.</span></span> <span data-ttu-id="0db3d-119">Dati i codici IVA seguenti:</span><span class="sxs-lookup"><span data-stu-id="0db3d-119">Given the following sales tax codes:</span></span>
-   <span data-ttu-id="0db3d-120">IMPOSTA 1 = 10%, con il metodo di calcolo Percentuale dell'importo netto</span><span class="sxs-lookup"><span data-stu-id="0db3d-120">DUTY 1 = 10%, using the Percentage of net amount calculation method</span></span>
-   <span data-ttu-id="0db3d-121">IMPOSTA 2 = 20%, con il metodo di calcolo Percentuale dell'importo netto</span><span class="sxs-lookup"><span data-stu-id="0db3d-121">DUTY 2 = 20%, using the Percentage of net amount calculation method</span></span>
-   <span data-ttu-id="0db3d-122">IVA = 25%, con il metodo di calcolo Percentuale dell'importo lordo</span><span class="sxs-lookup"><span data-stu-id="0db3d-122">SALESTAX = 25%, using the Percentage of gross amount calculation method</span></span>

<span data-ttu-id="0db3d-123">Se l'importo netto è 10,00, IMPOSTA 1 sarà 1,00 (10,00 x 10%) e IMPOSTA 2 sarà 2,00 (10,00 x 20%).</span><span class="sxs-lookup"><span data-stu-id="0db3d-123">If the net amount is 10.00, then DUTY 1 is 1.00 (10.00 x 10%) and DUTY 2 = 2.00 (10.00 x 20%).</span></span> <span data-ttu-id="0db3d-124">Gli importi sarebbero i seguenti: Importo lordo: Importo netto + importo IMPOSTA 1 + importo IMPOSTA 2 (10,00 + 1,00 + 2,00) = 13,00 IVA = 13,00 x 25% = 3,25 Totale IMPOSTE e IVA: 1,00 + 2,00 + 3,25 = 6,25 Importo totale: 10,00 + 6,25 = 16,25</span><span class="sxs-lookup"><span data-stu-id="0db3d-124">The amounts would be as follows: Gross amount: Net amount + DUTY 1 amount + DUTY 2 amount (10.00 + 1.00 + 2.00) = 13.00 SALESTAX = 13.00 x 25% = 3.25 Total DUTIES and SALESTAX: 1.00 + 2.00 + 3.25 = 6.25 Total amount: 10.00 + 6.25 = 16.25</span></span>

| <span data-ttu-id="0db3d-125">**Nota**</span><span class="sxs-lookup"><span data-stu-id="0db3d-125">**Note**</span></span>                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="0db3d-126">Un solo codice IVA con Origine = Percentuale dell'importo lordo può essere utilizzato per una transazione.</span><span class="sxs-lookup"><span data-stu-id="0db3d-126">Only one tax code with Origin = Percentage of gross amount can be used for a transaction.</span></span> <span data-ttu-id="0db3d-127">Se più di un codice di questo tipo viene determinato per una transazione, verrà visualizzato l'errore che l'IVA non può essere calcolata.</span><span class="sxs-lookup"><span data-stu-id="0db3d-127">If more than one such tax code is determined for a transaction an error will be displayed that sales tax cannot be calculated.</span></span> |


## <a name="percentage-of-sales-tax"></a><span data-ttu-id="0db3d-128">Percentuale IVA</span><span class="sxs-lookup"><span data-stu-id="0db3d-128">Percentage of sales tax</span></span>

<span data-ttu-id="0db3d-129">Quando si seleziona Percentuale IVA nel campo Origine, l'IVA viene calcolata come percentuale dell'IVA selezionata nel campo IVA sull'IVA.</span><span class="sxs-lookup"><span data-stu-id="0db3d-129">When you select Percentage of sales tax in the Origin field, sales tax is calculated as a percentage of the sales tax that is selected in the Sales tax on sales tax field.</span></span> <span data-ttu-id="0db3d-130">Viene innanzitutto calcolata l'IVA selezionata nel campo IVA sull'IVA.</span><span class="sxs-lookup"><span data-stu-id="0db3d-130">The sales tax that is selected in the Sales tax on sales tax field is calculated first.</span></span> <span data-ttu-id="0db3d-131">Il secondo importo IVA viene quindi calcolato in base al primo importo.</span><span class="sxs-lookup"><span data-stu-id="0db3d-131">The second sales tax is then calculated based on the first sales tax amount.</span></span>
### <a name="example"></a><span data-ttu-id="0db3d-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="0db3d-132">Example</span></span>

<span data-ttu-id="0db3d-133">Dati i codici IVA seguenti:</span><span class="sxs-lookup"><span data-stu-id="0db3d-133">Given the following sales tax codes:</span></span>
-   <span data-ttu-id="0db3d-134">IMPOSTA 1 = 10%, con il metodo Percentuale dell'importo netto</span><span class="sxs-lookup"><span data-stu-id="0db3d-134">DUTY 1 = 10%, using the Percentage of net amount method</span></span>
-   <span data-ttu-id="0db3d-135">IMPOSTA 2 = 20%, con il metodo Percentuale del IVA, con Imposta 1 nel campo IVA sull'IVA</span><span class="sxs-lookup"><span data-stu-id="0db3d-135">DUTY 2 = 20%, using the Percentage of sales tax method, with Duty 1 in the Sales tax on sales tax field</span></span>
-   <span data-ttu-id="0db3d-136">IVA = 25%, con il metodo Percentuale dell'importo lordo</span><span class="sxs-lookup"><span data-stu-id="0db3d-136">SALESTAX = 25%, using the Percentage of gross amount method</span></span>

<span data-ttu-id="0db3d-137">Importo netto: 10,00 IMPOSTA 1: 10,00 x 10% = 1,00 IMPOSTA 2: 1,00 x 20% = 0,20 Importo lordo: 10,00 + 1,00 + 0,20 = 11.20 IVA: 11,20 x 25% = 2,80 Totale IMPOSTE e IVA: 1,00 + 0,20 + 2,80 = 4,00 Importo totale: 10,00 + 4,00 = 14,00</span><span class="sxs-lookup"><span data-stu-id="0db3d-137">Net amount: 10.00 DUTY 1: 10.00 x 10% = 1.00 DUTY 2: 1.00 x 20% = 0.20 Gross amount: 10.00 + 1.00 + 0.20 = 11.20 SALESTAX: 11.20 x 25% = 2.80 Total DUTIES and SALESTAX: 1.00 + 0.20 + 2.80 = 4.00 Total amount: 10.00 + 4.00 = 14.00</span></span>

| <span data-ttu-id="0db3d-138">**Nota**</span><span class="sxs-lookup"><span data-stu-id="0db3d-138">**Note**</span></span>                                                                                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="0db3d-139">I calcoli di imposta su imposta multilivello non sono possibili.</span><span class="sxs-lookup"><span data-stu-id="0db3d-139">Multilevel tax on tax calculations are not possible.</span></span> <span data-ttu-id="0db3d-140">Un'imposta non può essere calcolata in base a un'imposta che viene già calcolata in base a un'altra imposta.</span><span class="sxs-lookup"><span data-stu-id="0db3d-140">A tax cannot be calculated based on a tax which already is calculated based on another tax.</span></span> <span data-ttu-id="0db3d-141">Più codici imposta su imposta a livello singolo possono essere calcolati per una transazione.</span><span class="sxs-lookup"><span data-stu-id="0db3d-141">Multiple single level tax on tax codes can be calculated on a transaction.</span></span> |

## <a name="amount-per-unit"></a><span data-ttu-id="0db3d-142"> Importo unitario</span><span class="sxs-lookup"><span data-stu-id="0db3d-142">Amount per unit</span></span>
<span data-ttu-id="0db3d-143">Quando si seleziona Importo unitario nel campo Origine, l'IVA viene calcolata come importo fisso per unità moltiplicato per la quantità immessa nella riga del documento.</span><span class="sxs-lookup"><span data-stu-id="0db3d-143">When you select Amount per unit in the Origin field, sales tax is calculated as a fixed amount per unit multiplied with the quantity entered on the document line.</span></span> <span data-ttu-id="0db3d-144">Un'unità deve essere selezionata nel campo Unità.</span><span class="sxs-lookup"><span data-stu-id="0db3d-144">A unit has to be selected in the Unit field.</span></span> <span data-ttu-id="0db3d-145">L'importo unitario è specificato nella pagina Valori codice IVA.</span><span class="sxs-lookup"><span data-stu-id="0db3d-145">The amount per unit is specified in the Sales tax code values page.</span></span>
### <a name="example"></a><span data-ttu-id="0db3d-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="0db3d-146">Example</span></span>

<span data-ttu-id="0db3d-147">Il codice IVA è impostato come: 1,20 USD per unità = scatola In una riga di fattura di vendita 25 scatole di un articolo sono vendute L'IVA è calcolata come 25 x 1,20 = 30,00</span><span class="sxs-lookup"><span data-stu-id="0db3d-147">Sales tax code is set up as: USD 1.20 per unit = box On a sales invoice line 25 boxes of an item are sold Sales tax is calculated as 25 x 1.20 = 30.00</span></span>

| <span data-ttu-id="0db3d-148">**Nota**</span><span class="sxs-lookup"><span data-stu-id="0db3d-148">**Note**</span></span>                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="0db3d-149">Se la transazione è stata immessa in un'unità diversa dall'unità specificata nel codice IVA, viene convertita automaticamente in base alle conversioni unità impostate nella pagina Conversioni unità.</span><span class="sxs-lookup"><span data-stu-id="0db3d-149">If the transaction is entered in different unit than the unit specified on the sales tax code, it is converted automatically based on the unit conversions that are set up in the Unit conversions page.</span></span> |

###  <a name="amount-per-unit-additional-option"></a><span data-ttu-id="0db3d-150"> Importo unitario con opzioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0db3d-150">Amount per unit, additional option</span></span>

<span data-ttu-id="0db3d-151">Nella scheda Calcolo, è possibile scegliere se l'IVA per un importo unitario viene calcolata prima di altri codici imposta e viene aggiunta all'importo netto prima che altri codici con Origine = Percentuale dell'importo netto vengano calcolati.</span><span class="sxs-lookup"><span data-stu-id="0db3d-151">On the Calculation tab, you can select whether an amount per unit calculated tax is calculated before other tax codes and added to the net amount before other tax codes with Origin = Percentage of net amount are calculated.</span></span>

### <a name="examples"></a><span data-ttu-id="0db3d-152">Esempi</span><span class="sxs-lookup"><span data-stu-id="0db3d-152">Examples</span></span>

<span data-ttu-id="0db3d-153">Si presupponga il calcolo di 2 codici IVA per una transazione:</span><span class="sxs-lookup"><span data-stu-id="0db3d-153">Assume we calculate 2 tax codes on a transaction:</span></span>

-   <span data-ttu-id="0db3d-154">IMPOSTA: Origine = Importo unitario e IVA, il valore viene impostato su 5,00 per unità = pz</span><span class="sxs-lookup"><span data-stu-id="0db3d-154">DUTY: Origin = Amount per unit and a sales tax, the value is set to 5.00 per unit = pcs</span></span>
-   <span data-ttu-id="0db3d-155">IVA: Origine = come illustrato negli esempi successivi, il valore viene impostata su 25%</span><span class="sxs-lookup"><span data-stu-id="0db3d-155">SALESTAX: Origin = as shown in the examples below, the value is set to 25%</span></span>

<span data-ttu-id="0db3d-156">Vendiamo 1 pezzo di un articolo al prezzo unitario di 10,00</span><span class="sxs-lookup"><span data-stu-id="0db3d-156">We sell 1 piece of an item at a unit price of 10.00</span></span>
#### <a name="example-1"></a><span data-ttu-id="0db3d-157">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="0db3d-157">Example 1</span></span>

<span data-ttu-id="0db3d-158">IVA: Origine = Metodo Percentuale dell'importo lordo L'opzione Calcola prima dell'IVA non ha effetto, poiché IVA viene calcolata come percentuale dell'importo lordo.</span><span class="sxs-lookup"><span data-stu-id="0db3d-158">SALESTAX: Origin = Percentage of gross amount method The Calculate before sales tax option has no effect, because SALESTAX is calculated as a percentage of the gross amount.</span></span> <span data-ttu-id="0db3d-159">IMPOSTA: 1 x 5,00 = 5,00 Importo lordo: 10,00 + 5,00 = 15,00 IVA: 15,00 x 25% = 3,75 Totale IVA: 5,00 + 3,75 = 8,75 Importo totale: 10,00 + 8,75 = 18,75</span><span class="sxs-lookup"><span data-stu-id="0db3d-159">DUTY: 1 x 5.00 = 5.00 Gross amount: 10.00 + 5.00 = 15.00 SALESTAX: 15.00 x 25% = 3.75 Total sales tax: 5.00 + 3.75 = 8.75 Total amount: 10.00 + 8.75 = 18.75</span></span>

#### <a name="example-2"></a><span data-ttu-id="0db3d-160">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="0db3d-160">Example 2</span></span>

<span data-ttu-id="0db3d-161">IVA: Origine = Percentuale dell'importo netto L'opzione Calcola prima dell'IVA non è selezionata per il calcolo di IMPOSTA.</span><span class="sxs-lookup"><span data-stu-id="0db3d-161">SALESTAX: Origin = Percentage of net amount The Calculate before sales tax option is not selected for the DUTY calculation.</span></span> <span data-ttu-id="0db3d-162">Importo netto: 10,00 IMPOSTA: 1 x 5,00 = 5,00 IVA: 10,00 x 25% = 2,50: Totale IVA: 5,00 + 2,50 = 7,50 Importo totale: 10,00 + 7,50 = 17,50</span><span class="sxs-lookup"><span data-stu-id="0db3d-162">Net amount: 10.00 DUTY: 1 x 5.00 = 5.00 SALESTAX: 10.00 x 25% = 2.50 Total sales tax: 5.00 + 2.50 = 7.50 Total amount: 10.00 + 7.50 = 17.50</span></span>

#### <a name="example-3"></a><span data-ttu-id="0db3d-163">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="0db3d-163">Example 3</span></span>

<span data-ttu-id="0db3d-164">IVA: Origine = Percentuale dell'importo netto L'opzione Calcola prima dell'IVA è selezionata per il calcolo di IMPOSTA.</span><span class="sxs-lookup"><span data-stu-id="0db3d-164">SALESTAX: Origin = Percentage of net amount The Calculate before sales tax option is selected for the DUTY calculation.</span></span> <span data-ttu-id="0db3d-165">Importo netto: 10,00 IMPOSTA: 1 x 5,00 = 5,00 IVA: (10,00 + 5,00) x 25% = 3,75: Totale IVA: 5,00 + 3,75 = 8,75 Importo totale: 10,00 + 8,75 = 18,75</span><span class="sxs-lookup"><span data-stu-id="0db3d-165">Net amount: 10.00 DUTY: 1 x 5.00 = 5.00 SALESTAX: (10.00 + 5.00) x 25% = 3.75 Total sales tax: 5.00 + 3.75 = 8.75 Total amount: 10.00 + 8.75 = 18.75</span></span>

#### <a name="example-4"></a><span data-ttu-id="0db3d-166">Esempio 4</span><span class="sxs-lookup"><span data-stu-id="0db3d-166">Example 4</span></span>

<span data-ttu-id="0db3d-167">Il risultato degli esempi 3 e 1 è lo stesso in quanto è presente una sola imposta.</span><span class="sxs-lookup"><span data-stu-id="0db3d-167">The result of Example 3 and Example 1 is the same, because there is only one duty.</span></span> <span data-ttu-id="0db3d-168">Si supponga di avere due IMPOSTE e una sola di esse viene inclusa nell'importo netto per il calcolo dell'IVA: IMPOSTA 1: 5,00, con il metodo Importo unitario e l'opzione Calcola prima dell'IVA selezionata IMPOSTA 2: 2,50, con il metodo Importo unitario e l'opzione Calcola prima dell'IVA non selezionata IVA: 25%, con il metofo Percentuale dell'importo netto Importo netto: 10,00 IMPOSTA 1: 1 x 5,00 = 5,00 IMPOSTA 2: 1 x 2,50 = 2,50 Importo netto soggetto a IVA: 10,00 + 5,00 = 15,00 IVA: 15,00 x 25% = 3,75 Totali IVA, incluse imposte: 5,00 + 2,50 + 3,75 = 11,25 Importo totale: 10,00 + 11,25 = 21,25 Il 25% di IVA è calcolato per la somma dell'importo netto (10,00) + IMPOSTA 1 (5,00) = 15,00.</span><span class="sxs-lookup"><span data-stu-id="0db3d-168">Assume that you have two DUTIES, and only one of them is included in the net amount for the sales tax calculation: DUTY 1: 5.00, using the Amount per unit method, and the Calculate before sales tax option is selected DUTY 2: 2.50, using the Amount per unit method, and the Calculate before sales tax option is not selected Sales tax: 25%, using the Percentage of net amount method Net amount: 10.00 DUTY 1: 1 x 5.00 = 5.00 DUTY 2: 1 x 2.50 = 2.50 Net amount subject to sales tax: 10.00 + 5.00 = 15.00 SALESTAX: 15.00 x 25% = 3.75 Total sales taxes, including duties: 5.00 + 2.50 + 3.75 = 11.25 Total amount: 10.00 + 11.25 = 21.25 The 25% SALESTAX is calculated for the sum of the net amount (10.00) + DUTY 1 (5.00) = 15.00.</span></span> <span data-ttu-id="0db3d-169">Dopo il calcolo dell'IVA, all'importo IVA viene aggiunto l'importo di IMPOSTA 2.</span><span class="sxs-lookup"><span data-stu-id="0db3d-169">DUTY 2 is added to the tax amount after the sales tax is calculated.</span></span>

## <a name="calculated-percentage-of-net-amount"></a><span data-ttu-id="0db3d-170"> Percentuale calcolata dell'importo netto</span><span class="sxs-lookup"><span data-stu-id="0db3d-170">Calculated percentage of net amount</span></span>
<span data-ttu-id="0db3d-171">La Percentuale calcolata dell'importo netto gestisce il calcolo dell'IVA in modo diverso a seconda dell'impostazione del parametro Importo IVA inclusa del documento o del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="0db3d-171">The Calculated percentage of net amount handles tax calculation differently depending on the setting of the Amounts include sales tax parameter for the document or journal.</span></span>
### <a name="example-1"></a><span data-ttu-id="0db3d-172">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="0db3d-172">Example 1</span></span>

<span data-ttu-id="0db3d-173">Il documento/giornale di registrazione è impostato su Importo IVA inclusa =Sì Importo riga di transazione: 10,00 Aliquota IVA: 25%: IVA: Importo riga di transazione x aliquota IVA (10,00 x 25%) = 2,50 Importo imponibile (importo origine): Importo riga di transazione - IVA (10,00 - 2,50) = 7,50</span><span class="sxs-lookup"><span data-stu-id="0db3d-173">Document / journal is set to Amounts include sales tax = Yes Transaction line amount: 10.00 Tax rate: 25% Sales tax: Transaction line amount x tax rate (10.00 x 25%) = 2.50 Tax base amount (origin amount): Transaction line amount - Sales tax (10.00 - 2.50) = 7.50</span></span>

### <a name="example-2"></a><span data-ttu-id="0db3d-174">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="0db3d-174">Example 2</span></span>

<span data-ttu-id="0db3d-175">Il documento/giornale di registrazione è impostato su Importo IVA inclusa =No Importo riga di transazione: 10,00 Aliquota IVA: 25%: IVA: (Importo riga di transazione x aliquota IVA) / (100 - aliquota IVA) (10,00 x 25%) / (100% - 25%) = 3,33 Importo imponibile (importo origine): Importo riga di transazione = 10,00</span><span class="sxs-lookup"><span data-stu-id="0db3d-175">Document / journal is set to Amounts include sales tax = No Transaction line amount: 10.00 Tax rate: 25% Sales tax: (Transaction line amount x tax rate) / (100 - tax rate) (10.00 x 25%) / (100% - 25%) = 3.33 Tax base amount (origin amount): Transaction line amount = 10.00</span></span>



## <a name="additional-resources"></a><span data-ttu-id="0db3d-176">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0db3d-176">Additional resources</span></span>

[<span data-ttu-id="0db3d-177">Aliquote IVA basate su Imponibile marginale e Metodo di calcolo</span><span class="sxs-lookup"><span data-stu-id="0db3d-177">Sales tax rates based on the Marginal base and Calculation methods</span></span>](marginal-base-field.md)

[<span data-ttu-id="0db3d-178">Opzioni importo totale e intervallo per i codici IVA</span><span class="sxs-lookup"><span data-stu-id="0db3d-178">Whole amount and Interval calculation options for sales tax codes</span></span>](whole-amount-interval-options-sales-tax-codes.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]