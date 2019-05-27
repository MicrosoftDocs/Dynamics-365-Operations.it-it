---
title: Aliquote IVA basate su Imponibile marginale e Metodo di calcolo
description: In questo argomento viene illustrato come i valori nei campi Imponibile marginale e Metodo di calcolo determinano le aliquote IVA nelle transazioni di vendita e di acquisto.
author: ShylaThompson
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 7171
ms.assetid: 381fc309-b32a-4927-b5b8-fa1c31b0bd72
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0128743e608ec56bea2301ac576551065a1ff290
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1561524"
---
# <a name="sales-tax-rates-based-on-the-marginal-base-and-calculation-methods"></a><span data-ttu-id="877f1-103">Aliquote IVA basate su Imponibile marginale e Metodo di calcolo</span><span class="sxs-lookup"><span data-stu-id="877f1-103">Sales tax rates based on the Marginal base and Calculation methods</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="877f1-104">In questo argomento viene illustrato come i valori nei campi Imponibile marginale e Metodo di calcolo determinano le aliquote IVA nelle transazioni di vendita e di acquisto.</span><span class="sxs-lookup"><span data-stu-id="877f1-104">This topic explains how the values in the fields Marginal base and Calculation method determine the tax rate(s) in sales and purchase transactions.</span></span>

<span data-ttu-id="877f1-105">Il calcolo dell'imponibile marginale nella scheda dettaglio della pagina dei codici IVA determina quale importo viene utilizzato per prelevare le aliquote appropriate nella pagina dei valori del codice IVA.</span><span class="sxs-lookup"><span data-stu-id="877f1-105">The Marginal base on the Calculation FastTab on the Sales tax codes page determines which amount is used to pick the appropriate tax rate(s) from the rates in the Sales tax code values page.</span></span> <span data-ttu-id="877f1-106">Il tipo di importo nel campo Imponibile marginale congiuntamente al metodo nel campo Metodo di calcolo determina la logica per cercare le aliquote corrette per una transazione.</span><span class="sxs-lookup"><span data-stu-id="877f1-106">The amount type in the Marginal base field in combination with the method in the Calculation method field determines the logic to find the correct tax rate(s) for a transaction.</span></span> 

<span data-ttu-id="877f1-107">Le varie combinazioni dei valori di questi campi determinano l'esecuzione di calcoli dell'IVA differenti, come illustrato negli esempi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="877f1-107">Various combinations of values in these fields produce very different sales tax calculations, as shown by the following examples.</span></span> <span data-ttu-id="877f1-108">Negli esempi vengono utilizzati gli stessi valori di intervallo di imposta, che sono impostati per ogni codice IVA nella pagina dei valori del codice IVA.</span><span class="sxs-lookup"><span data-stu-id="877f1-108">The examples use the same tax interval values, which are set up for each tax code in the Sales tax codes values page.</span></span> <span data-ttu-id="877f1-109">Per aprire la pagina, fare clic su Codice IVA &gt; Valori nella pagina Codici IVA.</span><span class="sxs-lookup"><span data-stu-id="877f1-109">To open this page, click Sales tax code &gt; Values in the Sales tax codes page.</span></span>

> [!Important]                                                                                                                  
> <span data-ttu-id="877f1-110">Se l'imponibile marginale relativo a uno o più codici IVA è basato su importi riga o unità, il valore del campo Metodo di calcolo nella pagima Parametri contabilità generale deve essere impostato su Riga.</span><span class="sxs-lookup"><span data-stu-id="877f1-110">If the Marginal base on one or more of your sales tax codes is based on line amounts or units, the value of the Calculation method field in the General ledger parameters page must be set to Line.</span></span> |

## <a name="net-amount-per-line"></a><span data-ttu-id="877f1-111"> Importo netto per riga</span><span class="sxs-lookup"><span data-stu-id="877f1-111">Net amount per line</span></span>
<span data-ttu-id="877f1-112">Selezionare questa opzione per determinare le aliquote IVA in base all'importo netto delle righe di fattura, escluse eventuali altre imposte.</span><span class="sxs-lookup"><span data-stu-id="877f1-112">Select this option to determine sales tax rates based on the net amount for the invoice lines, excluding any other taxes.</span></span>

### <a name="example"></a><span data-ttu-id="877f1-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="877f1-113">Example</span></span>

<span data-ttu-id="877f1-114">Vengono impostati i seguenti intervalli per le aliquote IVA:</span><span class="sxs-lookup"><span data-stu-id="877f1-114">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="877f1-115">Intervallo importi</span><span class="sxs-lookup"><span data-stu-id="877f1-115">Amount interval</span></span>    | <span data-ttu-id="877f1-116">Aliquota imposta</span><span class="sxs-lookup"><span data-stu-id="877f1-116">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="877f1-117">0 - 50</span><span class="sxs-lookup"><span data-stu-id="877f1-117">0 - 50</span></span>             | <span data-ttu-id="877f1-118">30%</span><span class="sxs-lookup"><span data-stu-id="877f1-118">30%</span></span>      |
| <span data-ttu-id="877f1-119">50 - 100</span><span class="sxs-lookup"><span data-stu-id="877f1-119">50 - 100</span></span>           | <span data-ttu-id="877f1-120">20%</span><span class="sxs-lookup"><span data-stu-id="877f1-120">20%</span></span>      |
| <span data-ttu-id="877f1-121">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="877f1-121">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="877f1-122">10%</span><span class="sxs-lookup"><span data-stu-id="877f1-122">10%</span></span>      |

> [!NOTE]                                                                                                             
> <span data-ttu-id="877f1-123">Il limite superiore 0 (zero) nell'ultimo intervallo indica che sono inclusi tutti gli importi maggiori di 100.</span><span class="sxs-lookup"><span data-stu-id="877f1-123">The upper limit of zero (0) in the last interval means that all amounts that exceed 100 are included in the interval.</span></span>

<span data-ttu-id="877f1-124">Imponibile marginale: **Importo netto per riga**</span><span class="sxs-lookup"><span data-stu-id="877f1-124">Marginal base: **Net amount per line**</span></span> 

<span data-ttu-id="877f1-125">Metodo di calcolo: **Intervallo**</span><span class="sxs-lookup"><span data-stu-id="877f1-125">Calculation method: **Interval**</span></span> 

<span data-ttu-id="877f1-126">Si acquistano 8 lampade al costo di 25,00 l'una.</span><span class="sxs-lookup"><span data-stu-id="877f1-126">You buy 8 lamps that cost 25.00 each.</span></span> 

<span data-ttu-id="877f1-127">L'importo netto della riga di fattura è pari a EUR 200.</span><span class="sxs-lookup"><span data-stu-id="877f1-127">The net amount for the invoice line is 200.00.</span></span> 

<span data-ttu-id="877f1-128">L'IVA viene calcolata nel seguente modo:</span><span class="sxs-lookup"><span data-stu-id="877f1-128">The tax is calculated as follows:</span></span> 

<span data-ttu-id="877f1-129">IVA totale = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = EUR 35,00</span><span class="sxs-lookup"><span data-stu-id="877f1-129">Total sales tax = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = 35.00</span></span> 

<span data-ttu-id="877f1-130">Importo fattura totale = 200,00 + 35,00 = EUR 235,00</span><span class="sxs-lookup"><span data-stu-id="877f1-130">Total invoice amount = 200.00 + 35.00 = 235.00</span></span> 

<span data-ttu-id="877f1-131">**Variazione**</span><span class="sxs-lookup"><span data-stu-id="877f1-131">**Variation**</span></span> 

<span data-ttu-id="877f1-132">Se la fattura ha due righe con 4 articoli ciascuna, l'importo netto per ogni riga sarà pari a 100,00 e l'IVA verrà calcolata nel seguente modo:</span><span class="sxs-lookup"><span data-stu-id="877f1-132">If the invoice has two lines with four items on each line, the net amount on each line is 100.00 and the sales tax is calculated as follows:</span></span> 

<span data-ttu-id="877f1-133">IVA riga 1 = 50 x 30% + 50 x 20% = 15 + 10 = EUR 25,00</span><span class="sxs-lookup"><span data-stu-id="877f1-133">Sales tax line 1 = 50 x 30% + 50 x 20% = 15 + 10 = 25.00</span></span> 

<span data-ttu-id="877f1-134">IVA riga 2 = 50 x 30% + 50 x 20% = 15 + 10 = EUR 25,00</span><span class="sxs-lookup"><span data-stu-id="877f1-134">Sales tax line 2 = 50 x 30% + 50 x 20% = 15 + 10 = 25.00</span></span> 

<span data-ttu-id="877f1-135">Totale IVA = 25 + 25 = 50,00</span><span class="sxs-lookup"><span data-stu-id="877f1-135">Total sales tax = 25.00 + 25.00 = 50.00</span></span> 

<span data-ttu-id="877f1-136">Importo fattura totale = 200,00 + 50,00 = EUR 250,00</span><span class="sxs-lookup"><span data-stu-id="877f1-136">Total invoice amount = 200.00 + 50.00 = 250.00</span></span>

## <a name="net-amount-per-unit"></a><span data-ttu-id="877f1-137"> Importo netto unitario</span><span class="sxs-lookup"><span data-stu-id="877f1-137">Net amount per unit</span></span>
<span data-ttu-id="877f1-138">Selezionare questa opzione per determinare l'aliquota IVA in base al valore di ogni unità, escluse eventuali altre imposte.</span><span class="sxs-lookup"><span data-stu-id="877f1-138">Select this option to determine sales tax rates based on the value of each unit, excluding any other taxes.</span></span> <span data-ttu-id="877f1-139">Quando un Imponibile marginale basato su unità viene selezionato, anche un'unità deve essere specificata per il codice IVA.</span><span class="sxs-lookup"><span data-stu-id="877f1-139">When a unit based Marginal base is selected then also a Unit has to be specified for the Sales tax code.</span></span>

### <a name="example"></a><span data-ttu-id="877f1-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="877f1-140">Example</span></span>

<span data-ttu-id="877f1-141">Vengono impostati i seguenti intervalli per le aliquote IVA:</span><span class="sxs-lookup"><span data-stu-id="877f1-141">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="877f1-142">Importo</span><span class="sxs-lookup"><span data-stu-id="877f1-142">Amount</span></span>             | <span data-ttu-id="877f1-143">Aliquota imposta</span><span class="sxs-lookup"><span data-stu-id="877f1-143">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="877f1-144">0 - 50</span><span class="sxs-lookup"><span data-stu-id="877f1-144">0 - 50</span></span>             | <span data-ttu-id="877f1-145">30%</span><span class="sxs-lookup"><span data-stu-id="877f1-145">30%</span></span>      |
| <span data-ttu-id="877f1-146">50 - 100</span><span class="sxs-lookup"><span data-stu-id="877f1-146">50 - 100</span></span>           | <span data-ttu-id="877f1-147">20%</span><span class="sxs-lookup"><span data-stu-id="877f1-147">20%</span></span>      |
| <span data-ttu-id="877f1-148">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="877f1-148">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="877f1-149">10%</span><span class="sxs-lookup"><span data-stu-id="877f1-149">10%</span></span>      |

<span data-ttu-id="877f1-150">Imponibile marginale: **Importo netto per unità**</span><span class="sxs-lookup"><span data-stu-id="877f1-150">Marginal base: **Net amount per unit**</span></span> 

<span data-ttu-id="877f1-151">Metodo di calcolo  **Importo totale:**</span><span class="sxs-lookup"><span data-stu-id="877f1-151">Calculation method: **Whole amount**</span></span> 

<span data-ttu-id="877f1-152">Si acquistano 8 lampade al costo di 25,00 l'una.</span><span class="sxs-lookup"><span data-stu-id="877f1-152">You buy 8 lamps that cost 25.00 each.</span></span> 

<span data-ttu-id="877f1-153">L'importo netto della riga di fattura è pari a EUR 200.</span><span class="sxs-lookup"><span data-stu-id="877f1-153">The net amount for the invoice line is 200.00.</span></span> 

<span data-ttu-id="877f1-154">L'IVA viene calcolata nel seguente modo: IVA per unità = 25,00 x 30% = 7,50 IVA totale = 7,50 x 8 unità = 60,00 Importo della fattura totale = 200,00 + 60,00 = 260,00</span><span class="sxs-lookup"><span data-stu-id="877f1-154">The tax is calculated as follows: Sales tax per unit = 25.00 x 30% = 7.50 Total sales tax = 7.50 x 8 units = 60.00 Total invoice amount = 200.00 + 60.00 = 260.00</span></span>

## <a name="net-amount-of-invoice-balance"></a><span data-ttu-id="877f1-155"> Importo netto del saldo fattura</span><span class="sxs-lookup"><span data-stu-id="877f1-155">Net amount of invoice balance</span></span>

<span data-ttu-id="877f1-156">Selezionare questa opzione per determinare l'aliquota IVA in base all'importo totale delle righe di fattura, escluse eventuali altre imposte.</span><span class="sxs-lookup"><span data-stu-id="877f1-156">Select this option to determine sales tax rates based on the total value for the invoice, excluding any other taxes.</span></span>

### <a name="example"></a><span data-ttu-id="877f1-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="877f1-157">Example</span></span>

<span data-ttu-id="877f1-158">Vengono impostati i seguenti intervalli per le aliquote IVA:</span><span class="sxs-lookup"><span data-stu-id="877f1-158">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="877f1-159">Importo</span><span class="sxs-lookup"><span data-stu-id="877f1-159">Amount</span></span>            | <span data-ttu-id="877f1-160">Aliquota imposta</span><span class="sxs-lookup"><span data-stu-id="877f1-160">Tax rate</span></span> |
|-------------------|----------|
| <span data-ttu-id="877f1-161">0 - 50</span><span class="sxs-lookup"><span data-stu-id="877f1-161">0 - 50</span></span>            | <span data-ttu-id="877f1-162">30%</span><span class="sxs-lookup"><span data-stu-id="877f1-162">30%</span></span>      |
| <span data-ttu-id="877f1-163">50 - 100</span><span class="sxs-lookup"><span data-stu-id="877f1-163">50 - 100</span></span>          | <span data-ttu-id="877f1-164">20%</span><span class="sxs-lookup"><span data-stu-id="877f1-164">20%</span></span>      |
| <span data-ttu-id="877f1-165">100 -0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="877f1-165">100 -0 (&gt; 100)</span></span> | <span data-ttu-id="877f1-166">10%</span><span class="sxs-lookup"><span data-stu-id="877f1-166">10%</span></span>      |

<span data-ttu-id="877f1-167">Imponibile marginale: **Importo netto del saldo fattura**</span><span class="sxs-lookup"><span data-stu-id="877f1-167">Marginal base: **Net amount of invoice balance**</span></span> 

<span data-ttu-id="877f1-168">Metodo di calcolo: **Intervallo** Una fattura di vendita ha 2 righe con 4 lampade per ogni riga per 25,00 ciascuna.</span><span class="sxs-lookup"><span data-stu-id="877f1-168">Calculation method: **Interval** A sales invoice has 2 lines with 4 lamps on each lines for 25.00 each.</span></span> <span data-ttu-id="877f1-169">L'importo del saldo netto della fattura è 4 x 25,00 + 4 x 25,00 = 200,00.</span><span class="sxs-lookup"><span data-stu-id="877f1-169">The net amount of invoice balance is 4 x 25.00 + 4 x 25.00 = 200.00.</span></span> <span data-ttu-id="877f1-170">L'IVA viene calcolata nel seguente modo: IVA totale = 50 x 0,30 + 50 x 0,20 + 100 x 0,10 = 15 + 10 + 10 = 35,00 Importo della fattura totale = 200,00 + 35,00 = 235,00</span><span class="sxs-lookup"><span data-stu-id="877f1-170">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 100 x 0.10 = 15 + 10 + 10 = 35.00 Total invoice amount = 200.00 + 35.00 = 235.00</span></span>

## <a name="gross-amount-per-line"></a><span data-ttu-id="877f1-171"> Importo lordo per riga</span><span class="sxs-lookup"><span data-stu-id="877f1-171">Gross amount per line</span></span>

<span data-ttu-id="877f1-172">Selezionare questa opzione per determinare l'aliquota IVA in base al valore della riga incluse tutte le altre imposte per tale riga.</span><span class="sxs-lookup"><span data-stu-id="877f1-172">Select this option to determine sales tax rates based on the value of the line including all other taxes for that line.</span></span>

> [!NOTE]
> <span data-ttu-id="877f1-173">In una fascia IVA può essere presente un solo codice IVA con questo valore selezionato nel campo Imponibile marginale.</span><span class="sxs-lookup"><span data-stu-id="877f1-173">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field.</span></span>

### <a name="example"></a><span data-ttu-id="877f1-174">Esempio</span><span class="sxs-lookup"><span data-stu-id="877f1-174">Example</span></span>

<span data-ttu-id="877f1-175">Vengono impostati i seguenti intervalli per le aliquote IVA:</span><span class="sxs-lookup"><span data-stu-id="877f1-175">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="877f1-176">Importo</span><span class="sxs-lookup"><span data-stu-id="877f1-176">Amount</span></span>             | <span data-ttu-id="877f1-177">Aliquota imposta</span><span class="sxs-lookup"><span data-stu-id="877f1-177">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="877f1-178">0 - 50</span><span class="sxs-lookup"><span data-stu-id="877f1-178">0 - 50</span></span>             | <span data-ttu-id="877f1-179">30%</span><span class="sxs-lookup"><span data-stu-id="877f1-179">30%</span></span>      |
| <span data-ttu-id="877f1-180">50 - 100</span><span class="sxs-lookup"><span data-stu-id="877f1-180">50 - 100</span></span>           | <span data-ttu-id="877f1-181">20%</span><span class="sxs-lookup"><span data-stu-id="877f1-181">20%</span></span>      |
| <span data-ttu-id="877f1-182">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="877f1-182">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="877f1-183">10%</span><span class="sxs-lookup"><span data-stu-id="877f1-183">10%</span></span>      |

<span data-ttu-id="877f1-184">Imponibile marginale: **Importo lordo per riga** Metodo di calcolo: **Intervallo** È inoltre presente un altro codice IVA calcolato per un diritto speciale di 5,00 in ciascuna lampada.</span><span class="sxs-lookup"><span data-stu-id="877f1-184">Marginal base: **Gross amount per line** Calculation method: **Interval** Additionally there is another tax code calculated for a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="877f1-185">Gli importi delle imposte vengono aggiunti all'importo netto prima del calcolo dell'IVA.</span><span class="sxs-lookup"><span data-stu-id="877f1-185">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="877f1-186">Si acquistano 8 lampade al costo di 25,00 l'una.</span><span class="sxs-lookup"><span data-stu-id="877f1-186">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="877f1-187">L'importo netto della riga di fattura è pari a EUR 200.</span><span class="sxs-lookup"><span data-stu-id="877f1-187">The net amount for the invoice line is 200.00.</span></span> <span data-ttu-id="877f1-188">L'importo lordo della riga di fattura è pari a 8 x 25,00 + 8 x 5,00 = 240,00.</span><span class="sxs-lookup"><span data-stu-id="877f1-188">The gross amount for the invoice line is 8 x 25.00 + 8 x 5.00 = 240.00.</span></span> <span data-ttu-id="877f1-189">L'IVA viene calcolata nel seguente modo: IVA totale = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 20 + 14 = 39,00 = 5,00 x 8 = 40,00 Importi della fattura totale = 200,00 + 39,00 + 40,00 = 279,00</span><span class="sxs-lookup"><span data-stu-id="877f1-189">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 140 x 0.10 = 15 + 20 + 14 = 39.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 39.00 + 40.00 = 279.00</span></span>

<span data-ttu-id="877f1-190">**Variazione**</span><span class="sxs-lookup"><span data-stu-id="877f1-190">**Variation**</span></span> 

<span data-ttu-id="877f1-191">Se la fattura viene creata utilizzando due righe con 4 articoli ciascuna, l'importo netto per riga di fattura sarà pari a 100,00.</span><span class="sxs-lookup"><span data-stu-id="877f1-191">If the invoice is created by using 2 invoice lines with 4 items on each line, the net amount per invoice line is 100.00.</span></span> <span data-ttu-id="877f1-192">Importo lordo (imposta incluso di 4 x 5,00) di per riga di fattura sarà 120,00 e l'vat verrà creato come segue: Riga fattura 2 = di VAT riga fattura 1 = 50 VAT x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 totale VAT 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 imposta totale = 27,00 + 27,00 = 54,00 = 5,00 x 8 = 40,00 importi della fattura totale = 200,00 + 54,00 + 40,00 = 294,00</span><span class="sxs-lookup"><span data-stu-id="877f1-192">The gross amount (including the duty of 4 x 5.00) per invoice line would be 120.00, and the sales tax is created as follows: Sales tax invoice line 1 = 50 x 0.30 + 50 x 0.20 + 20 x 0.10 = 15 + 10 + 2 = 27.00 Sales tax invoice line 2 = 50 x 0.30 + 50 x 0.20 + 20 x 0.10 = 15 + 10 + 2 = 27.00 Total sales tax = 27.00 + 27.00 = 54.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 54.00 + 40.00 = 294.00</span></span>

## <a name="gross-amount-per-unit"></a><span data-ttu-id="877f1-193"> Importo lordo unitario</span><span class="sxs-lookup"><span data-stu-id="877f1-193">Gross amount per unit</span></span>

<span data-ttu-id="877f1-194">Selezionare questa opzione per determinare l'aliquota IVA in base al valore di ogni unità, incluse eventuali altre imposte.</span><span class="sxs-lookup"><span data-stu-id="877f1-194">Select this option to determine sales tax rates based on the value of the unit including any other taxes.</span></span>

> [!NOTE]
> <span data-ttu-id="877f1-195">In una fascia IVA può essere presente un solo codice IVA con questo valore selezionato nel campo Imponibile marginale.</span><span class="sxs-lookup"><span data-stu-id="877f1-195">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field.</span></span>

### <a name="example"></a><span data-ttu-id="877f1-196">Esempio</span><span class="sxs-lookup"><span data-stu-id="877f1-196">Example</span></span>

<span data-ttu-id="877f1-197">Vengono impostati i seguenti intervalli per le aliquote IVA:</span><span class="sxs-lookup"><span data-stu-id="877f1-197">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="877f1-198">Importo</span><span class="sxs-lookup"><span data-stu-id="877f1-198">Amount</span></span>             | <span data-ttu-id="877f1-199">Aliquota imposta</span><span class="sxs-lookup"><span data-stu-id="877f1-199">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="877f1-200">0 - 50</span><span class="sxs-lookup"><span data-stu-id="877f1-200">0 - 50</span></span>             | <span data-ttu-id="877f1-201">30%</span><span class="sxs-lookup"><span data-stu-id="877f1-201">30%</span></span>      |
| <span data-ttu-id="877f1-202">50 - 100</span><span class="sxs-lookup"><span data-stu-id="877f1-202">50 - 100</span></span>           | <span data-ttu-id="877f1-203">20%</span><span class="sxs-lookup"><span data-stu-id="877f1-203">20%</span></span>      |
| <span data-ttu-id="877f1-204">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="877f1-204">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="877f1-205">10%</span><span class="sxs-lookup"><span data-stu-id="877f1-205">10%</span></span>      |

<span data-ttu-id="877f1-206">Imponibile marginale: **Importo lordo unitario** È presente un diritto speciale di 5,00 in ciascuna lampada.</span><span class="sxs-lookup"><span data-stu-id="877f1-206">Marginal base: **Gross amount per unit** There is a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="877f1-207">Gli importi delle imposte vengono aggiunti all'importo netto prima del calcolo dell'IVA.</span><span class="sxs-lookup"><span data-stu-id="877f1-207">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="877f1-208">Si acquistano 8 lampade al costo di 25,00 l'una.</span><span class="sxs-lookup"><span data-stu-id="877f1-208">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="877f1-209">L'importo lordo unitario è pari a EUR 30,00.</span><span class="sxs-lookup"><span data-stu-id="877f1-209">The gross amount per unit is 30.00.</span></span> <span data-ttu-id="877f1-210">L'IVA viene calcolata nel seguente modo: IVA per unità = 30 x 30% = 9,00 Iva totale = 9,00 x 8 = 72,00 Diritto totale = 5.00 x 8 = 40.00 Importo della fattura totale = 200,00 + 72,00 + 40,00 = 312,00</span><span class="sxs-lookup"><span data-stu-id="877f1-210">The tax is calculated as follows: Sales tax per unit = 30 x 30% = 9.00 Total sales tax = 9.00 x 8 = 72.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 72.00 + 40.00 = 312.00</span></span>

## <a name="invoice-total-incl-other-sales-tax-amounts"></a><span data-ttu-id="877f1-211"> Totale fattura inclusi altri importi IVA</span><span class="sxs-lookup"><span data-stu-id="877f1-211">Invoice total incl. other sales tax amounts</span></span>

<span data-ttu-id="877f1-212">Selezionare questa opzione per determinare l'aliquota IVA in base all'importo totale delle righe di fattura, incluse eventuali altre imposte.</span><span class="sxs-lookup"><span data-stu-id="877f1-212">Select this option to determine sales tax rates based on the total value for the invoice including any other taxes.</span></span>
> [!NOTE]
> <span data-ttu-id="877f1-213">In una fascia IVA può essere presente un solo codice IVA con questo valore selezionato nel campo Imponibile marginale.</span><span class="sxs-lookup"><span data-stu-id="877f1-213">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field</span></span>

### <a name="example"></a><span data-ttu-id="877f1-214">Esempio</span><span class="sxs-lookup"><span data-stu-id="877f1-214">Example</span></span>

<span data-ttu-id="877f1-215">Vengono impostati i seguenti intervalli per le aliquote IVA:</span><span class="sxs-lookup"><span data-stu-id="877f1-215">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="877f1-216">Importo</span><span class="sxs-lookup"><span data-stu-id="877f1-216">Amount</span></span>             | <span data-ttu-id="877f1-217">Aliquota imposta</span><span class="sxs-lookup"><span data-stu-id="877f1-217">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="877f1-218">0 - 50</span><span class="sxs-lookup"><span data-stu-id="877f1-218">0 - 50</span></span>             | <span data-ttu-id="877f1-219">30%</span><span class="sxs-lookup"><span data-stu-id="877f1-219">30%</span></span>      |
| <span data-ttu-id="877f1-220">50 - 100</span><span class="sxs-lookup"><span data-stu-id="877f1-220">50 - 100</span></span>           | <span data-ttu-id="877f1-221">20%</span><span class="sxs-lookup"><span data-stu-id="877f1-221">20%</span></span>      |
| <span data-ttu-id="877f1-222">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="877f1-222">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="877f1-223">10%</span><span class="sxs-lookup"><span data-stu-id="877f1-223">10%</span></span>      |

<span data-ttu-id="877f1-224">Imponibile marginale: **Totale fattura inclusi altri importi IVA** Metodo di calcolo: **Intervallo** </span><span class="sxs-lookup"><span data-stu-id="877f1-224">Marginal base: **Invoice total incl. other sales tax amounts** Calculation method: **Interval** </span></span>  
<span data-ttu-id="877f1-225">Su ciascuna lampada viene applicata un'imposta speciale di EUR 5,00.</span><span class="sxs-lookup"><span data-stu-id="877f1-225">There is a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="877f1-226">Gli importi delle imposte vengono aggiunti all'importo netto prima del calcolo dell'IVA.</span><span class="sxs-lookup"><span data-stu-id="877f1-226">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="877f1-227">Si acquistano 8 lampade al costo di 25,00 l'una.</span><span class="sxs-lookup"><span data-stu-id="877f1-227">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="877f1-228">L'importo netto della fattura è pari a EUR 200.</span><span class="sxs-lookup"><span data-stu-id="877f1-228">The net amount for the invoice is 200.00.</span></span> <span data-ttu-id="877f1-229">L'importo lordo della fattura è pari a EUR 200 + (8 x 5,00) = EUR 240,00.</span><span class="sxs-lookup"><span data-stu-id="877f1-229">The gross amount for the invoice is 200.00 + (8 x 5.00) = 240.00.</span></span> <span data-ttu-id="877f1-230">L'IVA viene calcolata nel seguente modo: IVA totale = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 10 + 14 = 39,00 = 5,00 x 8 = 40,00 Importi della fattura totale = 200,00 + 39,00 + 40,00 = 279,00</span><span class="sxs-lookup"><span data-stu-id="877f1-230">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 140 x 0.10 = 15 + 10 + 14 = 39.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 39.00 + 40.00 = 279.00</span></span>

<span data-ttu-id="877f1-231">Per ulteriori informazioni, vedere [Opzioni Importo totale e Intervallo per i codici IVA](whole-amount-interval-options-sales-tax-codes.md) e [Metodi di calcolo IVA nel campo Origine](sales-tax-calculation-methods-origin-field.md)</span><span class="sxs-lookup"><span data-stu-id="877f1-231">For more information, see [Whole amount and Interval calculation options for sales tax codes](whole-amount-interval-options-sales-tax-codes.md) and [Sales tax calculation methods in the Origin field](sales-tax-calculation-methods-origin-field.md).</span></span>



