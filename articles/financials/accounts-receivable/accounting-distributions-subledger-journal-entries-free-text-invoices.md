---
title: Distribuzioni contabili e sugli inserimenti nel giornale di registrazione secondario per le fatture a testo libero
description: Le distribuzioni contabili vengono utilizzate per definire il modo in cui importo verrà conteggiato, ad esempio i ricavi, le tasse o le spese vengono conteggiate in una fattura a testo libero. Ogni importo che deve essere conteggiato quando la fattura a testo libero viene immessa nel giornale di registrazione avrà una o più distribuzioni contabili.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5d1546e8537110daec5d6655f68d3328a58ca1cb
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "334866"
---
# <a name="accounting-distributions-and-subledger-journal-entries-for-free-text-invoices"></a><span data-ttu-id="d807d-104">Distribuzioni contabili e sugli inserimenti nel giornale di registrazione secondario per le fatture a testo libero</span><span class="sxs-lookup"><span data-stu-id="d807d-104">Accounting distributions and subledger journal entries for free text invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d807d-105">Le distribuzioni contabili vengono utilizzate per definire il modo in cui importo verrà conteggiato, ad esempio i ricavi, le tasse o le spese vengono conteggiate in una fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="d807d-105">Accounting distributions are used to define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span> <span data-ttu-id="d807d-106">Ogni importo che deve essere conteggiato quando la fattura a testo libero viene immessa nel giornale di registrazione avrà una o più distribuzioni contabili.</span><span class="sxs-lookup"><span data-stu-id="d807d-106">Every amount that must be accounted for when the free text invoice is journalized will have one or more accounting distributions.</span></span>

<a name="accounting-distributions"></a><span data-ttu-id="d807d-107">Distribuzioni contabili</span><span class="sxs-lookup"><span data-stu-id="d807d-107">Accounting distributions</span></span>
------------------------

<span data-ttu-id="d807d-108">È possibile utilizzare i pulsanti riportati di seguito nella pagina Fattura testo libero per visualizzare ed eventualmente modificare le distribuzioni contabili per ogni importo nella fattura testo libero.</span><span class="sxs-lookup"><span data-stu-id="d807d-108">You can use the following buttons in the Free text invoice page to view, and possibly change, the accounting distributions for each amount on the free text invoice.</span></span>

-   <span data-ttu-id="d807d-109">**Distribuisci importi**: consente di visualizzare e modificare le distribuzioni contabili per una singola riga e tutte le righe figlio, ad esempio imposte o spese.</span><span class="sxs-lookup"><span data-stu-id="d807d-109">**Distribute amounts**—View and change the accounting distributions for an individual line and any child lines, such as taxes or charges.</span></span> <span data-ttu-id="d807d-110">È inoltre possibile visualizzare e modificare le distribuzioni contabili per la riga figlio direttamente dalla pagina Transazioni VAT o Transazioni spese.</span><span class="sxs-lookup"><span data-stu-id="d807d-110">You can also view and change the accounting distributions for the child line directly from the Sales tax transactions page or the Charges transactions page.</span></span>
    -   <span data-ttu-id="d807d-111">Modificare gli importi intestazione della fattura a testo libero, ad esempio le spese o gli importi di arrotondamento valuta.</span><span class="sxs-lookup"><span data-stu-id="d807d-111">Change free text invoice header amounts, such as charges or currency rounding amounts.</span></span>
    -   <span data-ttu-id="d807d-112">Modificare importi riga fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="d807d-112">Change free text invoice line amounts.</span></span>
-   <span data-ttu-id="d807d-113">**Visualizza distribuzioni**: visualizza le distribuzioni contabili per tutte le righe del documento.</span><span class="sxs-lookup"><span data-stu-id="d807d-113">**View distributions**—View the accounting distributions for all lines on the document.</span></span> <span data-ttu-id="d807d-114">Non è possibile modificare le distribuzioni contabili da questa visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="d807d-114">You can't change the accounting distributions from this view.</span></span>
    -   <span data-ttu-id="d807d-115">Visualizzare importi di riga e intestazione.</span><span class="sxs-lookup"><span data-stu-id="d807d-115">View header and line amounts.</span></span>

## <a name="distributing-amounts"></a><span data-ttu-id="d807d-116">Distribuzione degli importi</span><span class="sxs-lookup"><span data-stu-id="d807d-116">Distributing amounts</span></span>
<span data-ttu-id="d807d-117">Quando si immette una fattura a testo libero, ogni importo viene distribuito come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d807d-117">When you enter a free text invoice, each amount will be distributed as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d807d-118">Tipo di importo monetario</span><span class="sxs-lookup"><span data-stu-id="d807d-118">Type of monetary amount</span></span></th>
<th><span data-ttu-id="d807d-119">Determina da dove viene visualizzato il conto principale</span><span class="sxs-lookup"><span data-stu-id="d807d-119">Where the main account is displayed from</span></span></th>
<th><span data-ttu-id="d807d-120">Ordine di priorità che determina la dimensione finanziaria predefinita visualizzata</span><span class="sxs-lookup"><span data-stu-id="d807d-120">Order of priority that determines which default financial dimension is displayed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d807d-121">Riga fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="d807d-121">Free text invoice line</span></span></td>
<td><span data-ttu-id="d807d-122">Conto CoGe nella riga della fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="d807d-122">The ledger account on the free text invoice line.</span></span></td>
<td><ol>
<li><span data-ttu-id="d807d-123">Se il conto principale è un conto di allocazione, utilizzare il valore predefinito dalla definizione del conto di allocazione.</span><span class="sxs-lookup"><span data-stu-id="d807d-123">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="d807d-124">Se il conto principale non è un conto allocazione, utilizzare il modello predefinito delle dimensioni finanziarie nella riga fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="d807d-124">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d807d-125">Utilizzare i valori di dimensione finanziaria predefiniti nella riga fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="d807d-125">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d807d-126">Utilizzare i valori di dimensione finanziaria predefiniti del conto CoGe nella pagina Piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="d807d-126">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d807d-127">Riga fattura a testo libero per una combinazione di modello di valore e numero cespite</span><span class="sxs-lookup"><span data-stu-id="d807d-127">Free text invoice line for a fixed asset number and value model combination</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><span data-ttu-id="d807d-128"><strong>Nota </strong></span><span class="sxs-lookup"><span data-stu-id="d807d-128"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d807d-129">Il conto principale nella riga fattura a testo libero sarà il conto di dismissione cespiti.</span><span class="sxs-lookup"><span data-stu-id="d807d-129">The main account on the free text invoice line will be the fixed asset disposal account.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
<td><span data-ttu-id="d807d-130">Conto CoGe nella riga della fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="d807d-130">The ledger account on the free text invoice line.</span></span></td>
<td><ol>
<li><span data-ttu-id="d807d-131">Utilizzare i valori di dimensione finanziaria predefiniti nella riga fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="d807d-131">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d807d-132">Utilizzare i valori di dimensione finanziaria predefiniti del conto CoGe nella pagina Piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="d807d-132">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d807d-133">Importo dello sconto fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="d807d-133">Free text invoice discount amount</span></span></td>
<td><span data-ttu-id="d807d-134">Il campo Conto principale per sconti cliente nella pagina Sconti di cassa.</span><span class="sxs-lookup"><span data-stu-id="d807d-134">The Main account for customer discounts field in the Cash discounts page.</span></span></td>
<td><ol>
<li><span data-ttu-id="d807d-135">Se il conto principale è un conto di allocazione, utilizzare il valore predefinito dalla definizione del conto di allocazione.</span><span class="sxs-lookup"><span data-stu-id="d807d-135">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="d807d-136">Se il conto principale non è un conto allocazione, utilizzare il modello predefinito delle dimensioni finanziarie nella riga fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="d807d-136">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d807d-137">Utilizzare i valori di dimensione finanziaria predefiniti nella riga fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="d807d-137">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d807d-138">Utilizzare i valori di dimensione finanziaria predefiniti del conto CoGe nella pagina Piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="d807d-138">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d807d-139">Importo IVA della fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="d807d-139">Free text invoice sales tax amount</span></span></td>
<td><span data-ttu-id="d807d-140">Il campo IVA a debito nella pagina dei gruppi di registrazione contabile.</span><span class="sxs-lookup"><span data-stu-id="d807d-140">The Sales tax payable field in the Ledger posting groups page.</span></span></td>
<td><ol>
<li><span data-ttu-id="d807d-141">Utilizzare le dimensioni finanziarie definite nell'importo della riga fattura a testo libero o le distribuzioni per l'importo della riga addebito.</span><span class="sxs-lookup"><span data-stu-id="d807d-141">Use the financial dimensions that are defined on the free text invoice line amount or the distributions for the charge line amount.</span></span></li>
<li><span data-ttu-id="d807d-142">Utilizzare i valori di dimensione finanziaria predefiniti nella riga fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="d807d-142">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d807d-143">Utilizzare i valori di dimensione finanziaria predefiniti del conto CoGe nella pagina Piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="d807d-143">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d807d-144">Importo della riga addebito fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="d807d-144">Free text invoice charge line amount</span></span></td>
<td><span data-ttu-id="d807d-145">Il campo Conto in avere nella pagina Codice spese.</span><span class="sxs-lookup"><span data-stu-id="d807d-145">The Credit account field in the Charges code page.</span></span></td>
<td><ol>
<li><span data-ttu-id="d807d-146">Se il conto principale è un conto di allocazione, utilizzare il valore predefinito dalla definizione del conto di allocazione.</span><span class="sxs-lookup"><span data-stu-id="d807d-146">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="d807d-147">Se il conto principale non è un conto allocazione, utilizzare il modello predefinito delle dimensioni finanziarie nella riga fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="d807d-147">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d807d-148">Utilizzare i valori di dimensione finanziaria predefiniti nella riga fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="d807d-148">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d807d-149">Utilizzare i valori di dimensione finanziaria predefiniti del conto CoGe nella pagina Piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="d807d-149">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a><span data-ttu-id="d807d-150">Distribuzione di imposte</span><span class="sxs-lookup"><span data-stu-id="d807d-150">Distributing taxes</span></span>
<span data-ttu-id="d807d-151">impossibile creare distribuzioni contabili per imposte fino a quando queste ultime non verranno calcolate.</span><span class="sxs-lookup"><span data-stu-id="d807d-151">Accounting distributions for taxes cannot be created until taxes are calculated.</span></span> <span data-ttu-id="d807d-152">Per calcolare l'IVA, è necessario completare una delle seguenti attività nel modulo Fattura testo libero:</span><span class="sxs-lookup"><span data-stu-id="d807d-152">To calculate sales taxes, you must complete one of the following tasks in the Free text invoice form:</span></span>
-   <span data-ttu-id="d807d-153">Visualizzare l'IVA.</span><span class="sxs-lookup"><span data-stu-id="d807d-153">View the sales tax.</span></span>
-   <span data-ttu-id="d807d-154">Visualizzare il totale fattura.</span><span class="sxs-lookup"><span data-stu-id="d807d-154">View the invoice total.</span></span>
-   <span data-ttu-id="d807d-155">Visualizzare il flusso di cassa.</span><span class="sxs-lookup"><span data-stu-id="d807d-155">View the cash flow.</span></span>
-   <span data-ttu-id="d807d-156">Visualizzare le distribuzioni contabili per l'intera fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="d807d-156">View accounting distributions for the whole free text invoice.</span></span>
-   <span data-ttu-id="d807d-157">Visualizzare il giornale di registrazione secondario.</span><span class="sxs-lookup"><span data-stu-id="d807d-157">View the subledger journal.</span></span>

## <a name="subledger-journals-for-free-text-invoices"></a><span data-ttu-id="d807d-158">Giornali di registrazione secondari per fatture a testo libero.</span><span class="sxs-lookup"><span data-stu-id="d807d-158">Subledger journals for free text invoices</span></span>
<span data-ttu-id="d807d-159">Prima di registrare una fattura a testo libero, è possibile visualizzare l'intera voce contabile della fattura, che include i debiti e gli accrediti, per verificare che la fattura venga registrata nei conti corretti.</span><span class="sxs-lookup"><span data-stu-id="d807d-159">Before you post a free text invoice, you can view the full accounting entry of the invoice, which includes debits and credits, to verify that the invoice is being posted to the correct accounts.</span></span> <span data-ttu-id="d807d-160">Questa visualizzazione della voce contabile completa viene chiamata giornale di registrazione secondario.</span><span class="sxs-lookup"><span data-stu-id="d807d-160">This view of the full accounting entry is called a subledger journal.</span></span> <span data-ttu-id="d807d-161">L'inserimento nel giornale di registrazione secondario non può essere modificato se non è corretto quando lo si visualizza in anteprima prima di inserire nel giornale di registrazione la fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="d807d-161">If the subledger journal entry is incorrect when you preview it before you journalize the free text invoice, you can't change the subledger journal entry.</span></span> <span data-ttu-id="d807d-162">È invece necessario modificare le distribuzioni contabili o il profilo registrazione.</span><span class="sxs-lookup"><span data-stu-id="d807d-162">Instead, you must change the accounting distributions or the posting profile.</span></span> <span data-ttu-id="d807d-163">Le distribuzioni contabili vengono utilizzate per definire un lato della voce contabile, dare o avere.</span><span class="sxs-lookup"><span data-stu-id="d807d-163">The accounting distributions are used to define one side of the accounting entry, the debit or the credit.</span></span> <span data-ttu-id="d807d-164">La voce contabile giornale di registrazione secondario in contropartita viene creata dai profili registrazione, ad esempio il conto client o le imposte.</span><span class="sxs-lookup"><span data-stu-id="d807d-164">The offsetting subledger journal account entry is created from the posting profiles, such as from the customer account or the tax.</span></span>



