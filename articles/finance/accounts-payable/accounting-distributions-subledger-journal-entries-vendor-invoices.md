---
title: Distribuzioni contabili e scritture contabili per le fatture fornitore
description: Le distribuzioni contabili vengono utilizzate per definire il modo in cui un importo verrà conteggiato, ad esempio le spese e le tasse vengono conteggiate in una fattura fornitore. Ogni importo che deve essere conteggiato quando la fattura fornitore viene immessa nel giornale di registrazione avrà una o più distribuzioni contabili.
author: abruer
ms.date: 08/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 953069dfd39843d39cc92d99318f02819dc31ed0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820986"
---
# <a name="accounting-distributions-and-journal-entries-for-vendor-invoices"></a><span data-ttu-id="d55fe-104">Distribuzioni contabili e scritture contabili per le fatture fornitore</span><span class="sxs-lookup"><span data-stu-id="d55fe-104">Accounting distributions and journal entries for vendor invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d55fe-105">Le distribuzioni contabili vengono utilizzate per definire il modo in cui un importo verrà conteggiato, ad esempio le spese e le tasse vengono conteggiate in una fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-105">Accounting distributions are used to define how an amount will be accounted for, such as how the expense, tax, or charges will be accounted for on a vendor invoice.</span></span> <span data-ttu-id="d55fe-106">Ogni importo che deve essere conteggiato quando la fattura fornitore viene immessa nel giornale di registrazione avrà una o più distribuzioni contabili.</span><span class="sxs-lookup"><span data-stu-id="d55fe-106">Every amount that must be accounted for when the vendor invoice is journalized will have one or more accounting distributions.</span></span> 

<a name="accounting-distributions"></a><span data-ttu-id="d55fe-107">Distribuzioni contabili</span><span class="sxs-lookup"><span data-stu-id="d55fe-107">Accounting distributions</span></span> 
-------------------------

<span data-ttu-id="d55fe-108">È possibile utilizzare i pulsanti riportati di seguito nella pagina Fattura fornitore per visualizzare ed eventualmente modificare le distribuzioni contabili per ogni importo nella fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-108">You can use the following buttons in the Vendor invoice page to view, and possibly modify, the accounting distributions for each amount on the vendor invoice.</span></span>
-   <span data-ttu-id="d55fe-109">**Distribuisci importi**: consente di visualizzare e modificare le distribuzioni contabili per una singola riga e tutte le righe figlio, ad esempio imposte o spese.</span><span class="sxs-lookup"><span data-stu-id="d55fe-109">**Distribute amounts** – View and modify the accounting distributions for an individual line and any child lines, such as taxes or charges.</span></span> <span data-ttu-id="d55fe-110">È inoltre possibile visualizzare e modificare le distribuzioni contabili per la riga figlio direttamente dalla pagina Transazioni VAT o Transazioni spese.</span><span class="sxs-lookup"><span data-stu-id="d55fe-110">You can also view and modify the accounting distributions for the child line directly from the Sales tax transactions page or the Charges transactions page.</span></span>
    -   <span data-ttu-id="d55fe-111">Modificare gli importi intestazione della fattura fornitore, ad esempio le spese o gli importi di arrotondamento valuta.</span><span class="sxs-lookup"><span data-stu-id="d55fe-111">Modify vendor invoice header amounts, such as charges or currency rounding amounts.</span></span>
    -   <span data-ttu-id="d55fe-112">Modificare gli importi delle righe della fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-112">Modify vendor invoice line amounts.</span></span>
-   <span data-ttu-id="d55fe-113">**Visualizza distribuzioni**: visualizza le distribuzioni contabili per tutte le righe del documento.</span><span class="sxs-lookup"><span data-stu-id="d55fe-113">**View distributions** – View the accounting distributions for all lines on the document.</span></span> <span data-ttu-id="d55fe-114">Non è possibile modificare le distribuzioni contabili da questa visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="d55fe-114">You cannot modify the accounting distributions from this view.</span></span>
    -   <span data-ttu-id="d55fe-115">Visualizzare importi di riga e intestazione.</span><span class="sxs-lookup"><span data-stu-id="d55fe-115">View header and line amounts.</span></span>

<span data-ttu-id="d55fe-116">Se la fattura fornitore fa riferimento a un ordine fornitore, è possibile dividere e modificare le distribuzioni contabili per le righe contenenti un articolo non stoccato.</span><span class="sxs-lookup"><span data-stu-id="d55fe-116">If the vendor invoice references a purchase order, you can split and modify the accounting distributions for lines that contain an item that is not stocked.</span></span> <span data-ttu-id="d55fe-117">Se la riga della fattura fornitore non fa riferimento a una riga dell'ordine fornitore, è possibile anche eliminare una distribuzione contabile.</span><span class="sxs-lookup"><span data-stu-id="d55fe-117">If the vendor invoice line does not reference a purchase order line, you can also delete an accounting distribution.</span></span> <span data-ttu-id="d55fe-118">Non è possibile dividere o eliminare le righe per spese, imposte e sconti riga.</span><span class="sxs-lookup"><span data-stu-id="d55fe-118">You cannot split or delete lines for charges, taxes, and line discounts.</span></span> <span data-ttu-id="d55fe-119">È possibile modificare il conto CoGe, ma non è consentita la modifica di importi o percentuali.</span><span class="sxs-lookup"><span data-stu-id="d55fe-119">You can modify the ledger account, but you cannot change the amounts or percentages.</span></span>
> [!NOTE]                                                                                                                                 
> <span data-ttu-id="d55fe-120">Se la riga padre contiene un articolo non stoccato e le distribuzioni contabili vengono suddivise, la riga figlio verrà automaticamente suddivisa per corrispondere alle dimensioni finanziarie della riga padre.</span><span class="sxs-lookup"><span data-stu-id="d55fe-120">If the parent line contains an item that is not stocked and the accounting distributions are split, the child line will be split automatically to match the financial dimensions of the parent line.</span></span> <span data-ttu-id="d55fe-121">Le distribuzioni contabili per la riga figlio non possono inoltre essere suddivise o eliminate, ma in base all'impostazione della riga figlio potrebbe essere possibile modificare il conto CoGe per le distribuzioni contabili della riga figlio.</span><span class="sxs-lookup"><span data-stu-id="d55fe-121">The accounting distributions for the child line cannot be additionally split or deleted, but depending on the setup of the child line, you might be able to modify the ledger account for the accounting distributions of the child line.</span></span>

## <a name="distributing-amounts"></a><span data-ttu-id="d55fe-122">Distribuzione degli importi</span><span class="sxs-lookup"><span data-stu-id="d55fe-122">Distributing amounts</span></span>
<span data-ttu-id="d55fe-123">Quando si immette una fattura fornitore, ogni importo viene distribuito come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d55fe-123">When you enter a vendor invoice, each amount will be distributed as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d55fe-124">Tipo di riga della fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="d55fe-124">Type of vendor invoice line</span></span></th>
<th><span data-ttu-id="d55fe-125">Ordine di priorità che determina da dove viene visualizzato il conto principale</span><span class="sxs-lookup"><span data-stu-id="d55fe-125">Order of priority that determines where the main account is displayed from</span></span></th>
<th><span data-ttu-id="d55fe-126">Ordine di priorità che determina la dimensione finanziaria predefinita visualizzata</span><span class="sxs-lookup"><span data-stu-id="d55fe-126">Order of priority that determines which default financial dimension is displayed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d55fe-127">Prodotto stoccato</span><span class="sxs-lookup"><span data-stu-id="d55fe-127">Stocked product</span></span></td>
<td><ol>
<li><span data-ttu-id="d55fe-128">La distribuzione contabile per la riga dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-128">The accounting distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-129">Campo Conto principale se la spesa di acquisto per il prodotto è selezionata nella pagina di registrazione.</span><span class="sxs-lookup"><span data-stu-id="d55fe-129">The Main account field when Purchase expenditure for product is selected in the Posting page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="d55fe-130">Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-130">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-131">Utilizzare i valori di dimensione finanziaria predefiniti nella fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-131">Use the default financial dimension values on the vendor invoice.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d55fe-132">Una categoria di approvvigionamento o un prodotto non stoccato</span><span class="sxs-lookup"><span data-stu-id="d55fe-132">A procurement category or a product that is not stocked</span></span></td>
<td><ol>
<li><span data-ttu-id="d55fe-133">Se la riga della fattura fornitore fa riferimento a una riga ordine fornitore, la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-133">The accounting distribution for the purchase order line, if the vendor invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-134">Campo Conto principale se la spesa di acquisto per la spesa è selezionata nella pagina di registrazione.</span><span class="sxs-lookup"><span data-stu-id="d55fe-134">The Main account field when Purchase expenditure for expense is selected in the Posting page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="d55fe-135">Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-135">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-136">Se il conto principale è un conto di allocazione, utilizzare il valore predefinito dalla definizione del conto di allocazione.</span><span class="sxs-lookup"><span data-stu-id="d55fe-136">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="d55fe-137">Utilizzare i valori di dimensione finanziaria predefiniti nella fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-137">Use the default financial dimension values on the vendor invoice.</span></span></li>
<li><span data-ttu-id="d55fe-138">Utilizzare i valori di dimensione finanziaria della riga fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-138">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="d55fe-139">Utilizzare i valori di dimensione finanziaria predefiniti del conto principale nella pagina Piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="d55fe-139">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d55fe-140">Cespite</span><span class="sxs-lookup"><span data-stu-id="d55fe-140">Fixed asset</span></span></td>
<td><ol>
<li><span data-ttu-id="d55fe-141">Se la riga della fattura fornitore fa riferimento a una riga ordine fornitore, la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-141">The accounting distribution for the purchase order line, if the vendor invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-142">Se l'opzione Acquisizione è selezionata nel campo Tipo di transazione nel modulo Fatture fornitore, il campo Conto principale quando l'acquisizione è selezionata nella pagina Profili registrazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="d55fe-142">If Acquisition is selected in the Transaction type field in the Vendor invoice form, the Main account field when Acquisition is selected in the Fixed asset posting profiles page.</span></span></li>
<li><span data-ttu-id="d55fe-143">Se l'opzione Rettifica acquisizione è selezionata nel campo Tipo di transazione nel modulo Fatture fornitore, il campo Conto principale quando la rettifica acquisizione è selezionata nella pagina Profili registrazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="d55fe-143">If Acquisition adjustment is selected in the Transaction type field, the Main account field when Acquisition adjustment is selected in the Fixed asset posting profiles page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="d55fe-144">Se la riga della fattura fa riferimento a una riga ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-144">Use the account distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-145">Utilizzare i valori di dimensione finanziaria della riga fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-145">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="d55fe-146">Utilizzare i valori di dimensione finanziaria predefiniti del conto principale nella pagina Piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="d55fe-146">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d55fe-147">Progetto definito nella riga fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="d55fe-147">Project defined on the vendor invoice line</span></span></td>
<td><ol>
<li><span data-ttu-id="d55fe-148">Se la riga della fattura fa riferimento a una riga ordine fornitore, la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-148">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-149">Se il saldo è selezionato nel campo Registra costi - Articolo nella pagina gruppi di progetti, il campo Conto principale quando il costo è selezionato nella pagina Impostazioni registrazione contabile.</span><span class="sxs-lookup"><span data-stu-id="d55fe-149">If Balance is selected in the Post costs - item field in the Project groups page, the Main account field when Cost is selected in the Ledger posting setup page.</span></span></li>
<li><span data-ttu-id="d55fe-150">Se l'opzione Profitti e perdite è selezionata nel campo Registra costi - Articolo nella pagina Gruppi di progetti, il campo Conto principale quando l'opzione Costo - Articolo è selezionata nella pagina Impostazioni registrazione contabile.</span><span class="sxs-lookup"><span data-stu-id="d55fe-150">If Profit and loss is selected in the Post costs - item field in the Project groups page, the Main account field when Cost - item is selected in the Ledger posting setup page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="d55fe-151">Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-151">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d55fe-152">Sconto riga</span><span class="sxs-lookup"><span data-stu-id="d55fe-152">Line discount</span></span></td>
<td><ol>
<li><span data-ttu-id="d55fe-153">Se la riga della fattura fa riferimento a una riga ordine fornitore, la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-153">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-154">Il campo Conto principale quando lo sconto viene selezionato nella pagina di registrazione.</span><span class="sxs-lookup"><span data-stu-id="d55fe-154">The Main account field when Discount is selected in the Posting page.</span></span></li>
<li><span data-ttu-id="d55fe-155">Se nel profilo registrazione non è definito un conto principale per uno sconto, la distribuzione contabile del prezzo esteso nella riga ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-155">If a main account for a discount is not defined on the posting profile, the accounting distribution of the extended price on the purchase order line.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="d55fe-156">Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-156">If the invoice line references a purchase order line, use the accounting distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-157">Utilizzare le dimensioni finanziarie delle distribuzioni contabili per il prezzo esteso nella riga fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-157">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="d55fe-158">Utilizzare i valori di dimensione finanziaria per la riga fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-158">Use the financial dimension values for the vendor invoice line.</span></span></li>
<li><span data-ttu-id="d55fe-159">Utilizzare i valori di dimensione finanziaria predefiniti del conto principale nella pagina Piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="d55fe-159">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d55fe-160">Spese di acquisto, immesse nella scheda Prezzo e sconto della riga ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="d55fe-160">Purchase charge, which is entered on the Price and discount tab of the purchase order line</span></span></td>
<td><ol>
<li><span data-ttu-id="d55fe-161">Se la riga della fattura fa riferimento a una riga ordine fornitore, la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-161">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-162">La distribuzione contabile del prezzo esteso nella riga ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-162">The accounting distribution of the extended price on the purchase order line.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="d55fe-163">Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-163">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-164">Utilizzare le dimensioni finanziarie delle distribuzioni contabili per il prezzo esteso nella riga fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-164">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d55fe-165">Spese riga</span><span class="sxs-lookup"><span data-stu-id="d55fe-165">Line charge</span></span></td>
<td><ol>
<li><span data-ttu-id="d55fe-166">Se la riga della fattura fa riferimento a una riga ordine fornitore, la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-166">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-167">Se il conto CoGe è selezionato nel campo del tipo di addebito nel modulo Codice spese, il campo Conto in Dare nella pagina Codice spese.</span><span class="sxs-lookup"><span data-stu-id="d55fe-167">If Ledger account is selected in the debit Type field in the Charges code form, the debit Account field in the Charges code page.</span></span></li>
<li><span data-ttu-id="d55fe-168">Se l'articolo è selezionato nel campo del tipo di addebito del modulo Codice spese, la distribuzione contabile per il prezzo esteso nella riga ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-168">If Item is selected in the debit Type field in the Charges code form, the accounting distribution for the extended price on the purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-169">Se l'opzione Cliente/Fornitore è selezionata nel campo del tipo di addebito nel modulo Codice spese, il campo Conto in Avere nella pagina Codice spese.</span><span class="sxs-lookup"><span data-stu-id="d55fe-169">If Customer/Vendor is selected in the debit Type field in the Charges code form, the credit Account field in the Charges code page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="d55fe-170">Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-170">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-171">Utilizzare le dimensioni finanziarie delle distribuzioni contabili per il prezzo esteso nella riga fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-171">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="d55fe-172">Utilizzare i valori di dimensione finanziaria della riga fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-172">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="d55fe-173">Utilizzare i valori di dimensione finanziaria predefiniti del conto principale nella pagina Piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="d55fe-173">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d55fe-174">Imposta, con la seguente condizione:</span><span class="sxs-lookup"><span data-stu-id="d55fe-174">Tax, with the following condition:</span></span>
<ul>
<li><span data-ttu-id="d55fe-175">L'opzione Applica regole di tassazione statunitensi è selezionata nella pagina Parametri di contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="d55fe-175">The Apply U.S. taxation rules option is selected in the General ledger parameters page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="d55fe-176">Se la riga della fattura fa riferimento a una riga ordine fornitore, la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-176">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-177">La distribuzione contabile della spesa o del prezzo esteso.</span><span class="sxs-lookup"><span data-stu-id="d55fe-177">The accounting distribution of the extended price or charge.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="d55fe-178">Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-178">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-179">Utilizzare le dimensioni finanziarie delle distribuzioni contabili per il prezzo esteso nella riga fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-179">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="d55fe-180">Utilizzare i valori di dimensione finanziaria della riga fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-180">Use the financial dimension values from the vendor invoice line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d55fe-181">Imposta, con le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="d55fe-181">Tax, with the following conditions:</span></span>
<ul>
<li><span data-ttu-id="d55fe-182">L'opzione Applica regole di tassazione statunitensi è deselezionata nella pagina Parametri di contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="d55fe-182">The Apply U.S. taxation rules option is cleared in the General ledger parameters page.</span></span></li>
<li><span data-ttu-id="d55fe-183">Il campo IVA intracomunitaria per la fascia IVA è deselezionata nella pagina Fasce IVA.</span><span class="sxs-lookup"><span data-stu-id="d55fe-183">The Use tax field for the sales tax group is cleared in the Sales tax groups page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="d55fe-184">Se l'importo IVA è recuperabile, il campo IVA a credito nella pagina Gruppi registrazione contabile.</span><span class="sxs-lookup"><span data-stu-id="d55fe-184">If the tax amount is recoverable, the Sales tax receivable field in the Ledger posting groups page.</span></span></li>
<li><span data-ttu-id="d55fe-185">Se l'importo delle imposte non è recuperabile, il prezzo esteso o la distribuzione contabile per la spesa.</span><span class="sxs-lookup"><span data-stu-id="d55fe-185">If the tax amount is not recoverable, the extended price or the accounting distribution for the charge.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="d55fe-186">Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-186">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-187">Utilizzare le dimensioni finanziarie del prezzo esteso o delle distribuzioni contabili per la spesa nella riga fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-187">Use the financial dimensions from the extended price or the accounting distributions for the charge on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="d55fe-188">Utilizzare i valori di dimensione finanziaria della riga fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-188">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="d55fe-189">Utilizzare i valori di dimensione finanziaria predefiniti del conto principale nella pagina Piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="d55fe-189">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d55fe-190">Imposta, con le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="d55fe-190">Tax, with the following conditions:</span></span>
<ul>
<li><span data-ttu-id="d55fe-191">L'opzione Applica regole di tassazione statunitensi è deselezionata nella pagina Parametri di contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="d55fe-191">The Apply U.S. taxation rules option is cleared in the General ledger parameters page.</span></span></li>
<li><span data-ttu-id="d55fe-192">Il campo IVA intracomunitaria per la fascia IVA è selezionata nella pagina Fasce IVA.</span><span class="sxs-lookup"><span data-stu-id="d55fe-192">The Use tax field for the sales tax group is selected in the Sales tax groups page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="d55fe-193">Se l'importo IVA è recuperabile, il campo IVA a credito nella pagina Gruppi registrazione contabile.</span><span class="sxs-lookup"><span data-stu-id="d55fe-193">If the tax amount is recoverable, the Sales tax receivable field in the Ledger posting groups page.</span></span></li>
<li><span data-ttu-id="d55fe-194">Se l'importo IVA non è recuperabile, il campo Importo IVA intracomunitaria nella pagina Gruppi registrazione contabile.</span><span class="sxs-lookup"><span data-stu-id="d55fe-194">If the tax amount is not recoverable, the Use tax expense field in the Ledger posting groups page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="d55fe-195">Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-195">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-196">Utilizzare le dimensioni finanziarie del prezzo esteso o delle distribuzioni contabili per la spesa nella riga fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-196">Use the financial dimensions from the extended price or the accounting distributions for the charge on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="d55fe-197">Utilizzare i valori di dimensione finanziaria della riga fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-197">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="d55fe-198">Utilizzare i valori di dimensione finanziaria predefiniti del conto principale nella pagina Piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="d55fe-198">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d55fe-199">Spesa intestazione</span><span class="sxs-lookup"><span data-stu-id="d55fe-199">Header charge</span></span></td>
<td><ol>
<li><span data-ttu-id="d55fe-200">Se il conto CoGe è selezionato nel campo del tipo di addebito nel modulo Codice spese, il campo Conto in Dare nella pagina Codice spese.</span><span class="sxs-lookup"><span data-stu-id="d55fe-200">If Ledger account is selected in the debit Type field in the Charges code form, the debit Account field in the Charges code page.</span></span></li>
<li><span data-ttu-id="d55fe-201">Se l'opzione Cliente/Fornitore è selezionata nel campo del tipo di addebito nel modulo Codice spese, il campo Conto in Avere nella pagina Codice spese.</span><span class="sxs-lookup"><span data-stu-id="d55fe-201">If Customer/Vendor is selected in the debit Type field in the Charges code form, the credit Account field in the Charges code page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="d55fe-202">Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-202">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-203">Se il conto principale è un conto di allocazione, utilizzare il valore predefinito dalla definizione del conto di allocazione.</span><span class="sxs-lookup"><span data-stu-id="d55fe-203">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="d55fe-204">Utilizzare i valori del modello predefinito di dimensione finanziaria dell'intestazione della fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-204">Use the financial dimension default template values from the vendor invoice header.</span></span></li>
<li><span data-ttu-id="d55fe-205">Utilizzare i valori di dimensione finanziaria della riga fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-205">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="d55fe-206">Utilizzare i valori di dimensione finanziaria predefiniti del conto principale nella pagina Piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="d55fe-206">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d55fe-207">Sconto intestazione</span><span class="sxs-lookup"><span data-stu-id="d55fe-207">Header discount</span></span></td>
<td><ol>
<li><span data-ttu-id="d55fe-208">Il campo Conto principale per il tipo di registrazione dello sconto fatture fornitore nella pagina Conti per transazioni automatiche.</span><span class="sxs-lookup"><span data-stu-id="d55fe-208">The Main account field for the Vendor invoice discount posting type in the Accounts for automatic transactions page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="d55fe-209">Se la riga della fattura fa riferimento a una riga dell'ordine fornitore, utilizzare la distribuzione contabile per quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d55fe-209">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="d55fe-210">Utilizzare le dimensioni finanziarie delle distribuzioni contabili per il prezzo esteso nella riga fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-210">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="d55fe-211">Utilizzare i valori di dimensione finanziaria della riga fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-211">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="d55fe-212">Utilizzare i valori di dimensione finanziaria predefiniti del conto principale nella pagina Piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="d55fe-212">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
</tbody>
</table>


<a name="distributing-taxes"></a><span data-ttu-id="d55fe-213">Distribuzione di imposte</span><span class="sxs-lookup"><span data-stu-id="d55fe-213">Distributing taxes</span></span>
------------------

<span data-ttu-id="d55fe-214">impossibile creare distribuzioni contabili per imposte fino a quando queste ultime non verranno calcolate.</span><span class="sxs-lookup"><span data-stu-id="d55fe-214">Accounting distributions for taxes cannot be created until taxes are calculated.</span></span> <span data-ttu-id="d55fe-215">Per calcolare l'IVA, è necessario completare una delle seguenti attività nella pagina Fattura fornitore:</span><span class="sxs-lookup"><span data-stu-id="d55fe-215">To calculate sales taxes, you must complete one of the following tasks in the Vendor invoice page:</span></span>
-   <span data-ttu-id="d55fe-216">Visualizzare il totale fattura.</span><span class="sxs-lookup"><span data-stu-id="d55fe-216">View the invoice total.</span></span>
-   <span data-ttu-id="d55fe-217">Visualizzare l'IVA.</span><span class="sxs-lookup"><span data-stu-id="d55fe-217">View the sales tax.</span></span>
-   <span data-ttu-id="d55fe-218">Visualizzare il giornale di registrazione secondario.</span><span class="sxs-lookup"><span data-stu-id="d55fe-218">View the subledger journal.</span></span>
-   <span data-ttu-id="d55fe-219">Visualizzare le distribuzioni contabili per la fattura fornitore completa.</span><span class="sxs-lookup"><span data-stu-id="d55fe-219">View accounting distributions for the complete vendor invoice.</span></span>
-   <span data-ttu-id="d55fe-220">Mettere in attesa la fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="d55fe-220">Place the vendor invoice on hold.</span></span>
-   <span data-ttu-id="d55fe-221">Registrare la fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-221">Post the vendor invoice.</span></span>

## <a name="subledger-journals-for-vendor-invoices"></a><span data-ttu-id="d55fe-222">Giornali di registrazione secondari per le fatture fornitore</span><span class="sxs-lookup"><span data-stu-id="d55fe-222">Subledger journals for vendor invoices</span></span>
<span data-ttu-id="d55fe-223">Prima di registrare una fattura fornitore, è possibile visualizzare l'intera voce contabile della fattura, che include i debiti e gli accrediti, per verificare che venga registrata nei conti corretti.</span><span class="sxs-lookup"><span data-stu-id="d55fe-223">Before you post a vendor invoice, you can view the full accounting entry of the invoice, which includes debits and credits, to verify that the invoice is being posted to the correct accounts.</span></span> <span data-ttu-id="d55fe-224">Questa visualizzazione della voce contabile completa viene chiamata giornale di registrazione secondario.</span><span class="sxs-lookup"><span data-stu-id="d55fe-224">This view of the full accounting entry is called a subledger journal.</span></span> 

<span data-ttu-id="d55fe-225">L'inserimento nel giornale di registrazione secondario non può essere modificato se non è corretto quando lo si visualizza in anteprima prima di inserire nel giornale la fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d55fe-225">If the subledger journal entry is incorrect when you preview it before you journalize the vendor invoice, you cannot modify the subledger journal entry.</span></span> <span data-ttu-id="d55fe-226">È invece necessario modificare le distribuzioni contabili o il profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="d55fe-226">Instead, you must modify the accounting distributions or the posting profile.</span></span> <span data-ttu-id="d55fe-227">Le distribuzioni contabili vengono utilizzate per definire un lato della voce contabile, dare o avere.</span><span class="sxs-lookup"><span data-stu-id="d55fe-227">The accounting distributions are used to define one side of the accounting entry, the debit or the credit.</span></span> <span data-ttu-id="d55fe-228">La voce contabile giornale di registrazione secondario in contropartita viene creata utilizzando i profili registrazione, ad esempio il conto fornitore o le imposte.</span><span class="sxs-lookup"><span data-stu-id="d55fe-228">The offsetting subledger journal account entry is created by using the posting profiles, such as from the vendor account or tax.</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]