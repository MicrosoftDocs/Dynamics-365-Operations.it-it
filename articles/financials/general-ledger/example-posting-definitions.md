---
title: Definizioni di registrazione
description: L'articolo offre alcuni esempi che mostrano come utilizzare le definizioni di registrazione per gli impegni di spesa di ordini fornitore e le ripartizioni di budget.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15772
ms.assetid: 3864e4da-853f-403d-b906-79631d80b363
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 004f3f24ec410d9f0e7d1e7264ec2730b9467410
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="posting-definition-examples"></a><span data-ttu-id="bd961-103">Esempi di definizioni di registrazione</span><span class="sxs-lookup"><span data-stu-id="bd961-103">Posting definition examples</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="bd961-104">L'articolo offre alcuni esempi che mostrano come utilizzare le definizioni di registrazione per gli impegni di spesa di ordini fornitore e le ripartizioni di budget.</span><span class="sxs-lookup"><span data-stu-id="bd961-104">This article provides examples that show how posting definitions are used for purchase order encumbrances and budget appropriations.</span></span>

<span data-ttu-id="bd961-105">Prima di leggere questo argomento, è consigliabile acquisire familiarità con le definizioni di registrazione e le definizioni di registrazione della transazione.</span><span class="sxs-lookup"><span data-stu-id="bd961-105">Before you read this topic, you should be familiar with posting definitions and transaction posting definitions.</span></span> <span data-ttu-id="bd961-106">Per ulteriori informazioni, vedere [Definizioni di registrazione](posting-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="bd961-106">For information, see [Posting definitions](posting-definitions.md).</span></span> <span data-ttu-id="bd961-107">Gli esempi seguenti possono essere impostati nella pagina **Definizioni di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="bd961-107">The following examples can be set up on the **Posting definitions** page.</span></span> <span data-ttu-id="bd961-108">Ogni esempio contiene queste sezioni:</span><span class="sxs-lookup"><span data-stu-id="bd961-108">Each example contains these sections:</span></span>

-   <span data-ttu-id="bd961-109">Definizione di registrazione – criteri di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="bd961-109">Posting definition – Match criteria</span></span>
-   <span data-ttu-id="bd961-110">Definizione di registrazione – voci generate</span><span class="sxs-lookup"><span data-stu-id="bd961-110">Posting definition – Generated entries</span></span>
-   <span data-ttu-id="bd961-111">Transazioni con i conti, i valori di dimensione e gli importi</span><span class="sxs-lookup"><span data-stu-id="bd961-111">Transactions with the accounts, dimension values, and amounts</span></span>
-   <span data-ttu-id="bd961-112">Voci di contabilità generale generate dalla definizione di registrazione</span><span class="sxs-lookup"><span data-stu-id="bd961-112">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="bd961-113">In caso di corrispondenza tra i conti e i valori di dimensione nel riquadro **Associa criteri** per la definizione di registrazione e i conti e i valori di dimensione sulla transazione, vengono generate voci di contabilità generale basate sul riquadro **Voci generate** per la definizione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="bd961-113">When a match occurs between the accounts and dimension values in the **Match criteria** pane for the posting definition and the accounts and dimension values on the transaction, ledger entries are generated based on the **Generated entries** pane for the posting definition.</span></span> 
> [!NOTE]
> <span data-ttu-id="bd961-114">Per associare una definizione di registrazione a uno specifico tipo di transazione, utilizzare la pagina **Definizioni di registrazione transazioni**.</span><span class="sxs-lookup"><span data-stu-id="bd961-114">To associate a posting definition with a specific transaction type, use the **Transaction posting definitions** page.</span></span> <span data-ttu-id="bd961-115">Dopo aver associato una definizione di registrazione a un tipo di transazione e selezionato **Usa definizioni di registrazione** nella pagina **Parametri di contabilità generale**, tutte le transazioni del tipo selezionato devono utilizzare definizioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="bd961-115">After you associate a posting definition with a transaction type and select **Use posting definitions** on the **General ledger parameters** page, all transactions of the selected transaction type must use posting definitions.</span></span>

## <a name="example-purchase-order-encumbrances"></a><span data-ttu-id="bd961-116">Esempio: impegni di spesa ordini fornitore</span><span class="sxs-lookup"><span data-stu-id="bd961-116">Example: Purchase order encumbrances</span></span>
<span data-ttu-id="bd961-117">Quando si abilita l'elaborazione degli impegni di spesa selezionando **Abilita processo di impegno di spesa** nella pagina **Parametri di contabilità generale**, è necessario utilizzare le definizioni di registrazione per registrare gli impegni di spesa nella contabilità generale per tutti i conti che devono essere prenotati.</span><span class="sxs-lookup"><span data-stu-id="bd961-117">When you enable encumbrance processing by selecting **Enable encumbrance process** on the **General ledger parameters** page, posting definitions must be used to record encumbrances to the general ledger for any accounts that should be reserved.</span></span> <span data-ttu-id="bd961-118">Nella maggior parte dei casi, tutti i conti spese vengono prenotati sullo stato patrimoniale.</span><span class="sxs-lookup"><span data-stu-id="bd961-118">In most cases, all expense accounts are reserved on the balance sheet.</span></span> 

<span data-ttu-id="bd961-119">Le definizioni di registrazione per gli impegni di spesa vengono impostati per il modulo **Acquisto** nella pagina **Definizioni di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="bd961-119">Posting definitions for encumbrances are set up for the **Purchasing** module on the **Posting definitions** page.</span></span> <span data-ttu-id="bd961-120">Quindi, nell'area **Acquisto** della pagina **Definizioni di registrazione transazione**, è possibile selezionare il tipo di transazione **Ordine acquisto** per associare la definizione di registrazione agli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="bd961-120">Then, in the **Purchasing** area of the **Transaction posting definitions** page, you can select the **Purchase order** transaction type to associate the posting definition with purchase orders.</span></span> 

<span data-ttu-id="bd961-121">Tutte le transazioni giustificativo per gli impegni di spesa degli ordini fornitore devono compensarsi (i debiti devono essere pari ai crediti) in ciascuna dimensione univoca su un giustificativo.</span><span class="sxs-lookup"><span data-stu-id="bd961-121">All voucher transactions for purchase order encumbrances must balance (that is, debits must equal credits) in each unique dimension on a voucher.</span></span>

### <a name="posting-definition--match-criteria"></a><span data-ttu-id="bd961-122">Definizione di registrazione – criteri di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="bd961-122">Posting definition – Match criteria</span></span>

| <span data-ttu-id="bd961-123">Struttura dei conti</span><span class="sxs-lookup"><span data-stu-id="bd961-123">Account structure</span></span>       | <span data-ttu-id="bd961-124">Associa numero di conto</span><span class="sxs-lookup"><span data-stu-id="bd961-124">Match account number</span></span> | <span data-ttu-id="bd961-125">Priorità</span><span class="sxs-lookup"><span data-stu-id="bd961-125">Priority</span></span> |
|-------------------------|----------------------|----------|
| <span data-ttu-id="bd961-126">Struttura dei conti - profitti e perdite</span><span class="sxs-lookup"><span data-stu-id="bd961-126">Account Structure - P&L</span></span> | \*                   | <span data-ttu-id="bd961-127">1</span><span class="sxs-lookup"><span data-stu-id="bd961-127">1</span></span>        |

<span data-ttu-id="bd961-128">*Un valore vuoto nel campo **Numero di conto** da associare implica che tutti i conti corrispondenti nella struttura dei conti definita faranno parte della regola di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="bd961-128">*A blank value in the **Match account number** field means that all matching accounts in the defined account structure are part of the matching rule.</span></span>

### <a name="posting-definition--generated-entries"></a><span data-ttu-id="bd961-129">Definizione di registrazione – voci generate</span><span class="sxs-lookup"><span data-stu-id="bd961-129">Posting definition – Generated entries</span></span>

| <span data-ttu-id="bd961-130">Struttura dei conti</span><span class="sxs-lookup"><span data-stu-id="bd961-130">Account structure</span></span> | <span data-ttu-id="bd961-131">Numero di conto generato</span><span class="sxs-lookup"><span data-stu-id="bd961-131">Generated account number</span></span>                    | <span data-ttu-id="bd961-132">Dare/Avere generato</span><span class="sxs-lookup"><span data-stu-id="bd961-132">Generated debit/credit</span></span> |
|-------------------|---------------------------------------------|------------------------|
| <span data-ttu-id="bd961-133">Saldo</span><span class="sxs-lookup"><span data-stu-id="bd961-133">Balance</span></span>           | <span data-ttu-id="bd961-134">300143 - -(conto impegno di spesa)</span><span class="sxs-lookup"><span data-stu-id="bd961-134">300143 - -(Encumbrance account)</span></span>             | <span data-ttu-id="bd961-135">Uguali</span><span class="sxs-lookup"><span data-stu-id="bd961-135">Same</span></span>                   |
| <span data-ttu-id="bd961-136">Saldo</span><span class="sxs-lookup"><span data-stu-id="bd961-136">Balance</span></span>           | <span data-ttu-id="bd961-137">300144 - -(prenotazione conto impegno di spesa)</span><span class="sxs-lookup"><span data-stu-id="bd961-137">300144 - -(Reserve for encumbrance account)</span></span> | <span data-ttu-id="bd961-138">Stare in equilibrio</span><span class="sxs-lookup"><span data-stu-id="bd961-138">Balancing</span></span>              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a><span data-ttu-id="bd961-139">Transazioni con i conti, i valori di dimensione e gli importi</span><span class="sxs-lookup"><span data-stu-id="bd961-139">Transactions with the accounts, dimension values, and amounts</span></span>

<span data-ttu-id="bd961-140">I conti e i valori di dimensione derivano dalle distribuzioni contabili immesse per una riga dell'ordine fornitore oppure derivano dai conti e dalle dimensioni generati automaticamente in base alle impostazioni predefinite per fornitori, articoli, categorie e modelli di dimensione.</span><span class="sxs-lookup"><span data-stu-id="bd961-140">The accounts and dimension values come either from the accounting distributions that you enter for a purchase order line, or from the accounts and dimensions that are automatically generated based on the default settings for vendors, items, categories, and dimension templates.</span></span>

| <span data-ttu-id="bd961-141">Conto + dimensioni</span><span class="sxs-lookup"><span data-stu-id="bd961-141">Account + dimensions</span></span>           | <span data-ttu-id="bd961-142">Dare</span><span class="sxs-lookup"><span data-stu-id="bd961-142">Debit</span></span>  | <span data-ttu-id="bd961-143">Avere</span><span class="sxs-lookup"><span data-stu-id="bd961-143">Credit</span></span> | <span data-ttu-id="bd961-144">Commento</span><span class="sxs-lookup"><span data-stu-id="bd961-144">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="bd961-145">606400-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="bd961-145">606400-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="bd961-146">250,00</span><span class="sxs-lookup"><span data-stu-id="bd961-146">250.00</span></span> |        |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a><span data-ttu-id="bd961-147">Voci di contabilità generale generate dalla definizione di registrazione</span><span class="sxs-lookup"><span data-stu-id="bd961-147">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="bd961-148">Le voci di contabilità generale generate vengono create per registrare gli impegni di spesa.</span><span class="sxs-lookup"><span data-stu-id="bd961-148">Generated ledger entries are created to record the encumbrances.</span></span>

| <span data-ttu-id="bd961-149">Conto + dimensioni</span><span class="sxs-lookup"><span data-stu-id="bd961-149">Account + dimensions</span></span>           | <span data-ttu-id="bd961-150">Dare</span><span class="sxs-lookup"><span data-stu-id="bd961-150">Debit</span></span>  | <span data-ttu-id="bd961-151">Avere</span><span class="sxs-lookup"><span data-stu-id="bd961-151">Credit</span></span> | <span data-ttu-id="bd961-152">Commento</span><span class="sxs-lookup"><span data-stu-id="bd961-152">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="bd961-153">300143-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="bd961-153">300143-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="bd961-154">250,00</span><span class="sxs-lookup"><span data-stu-id="bd961-154">250.00</span></span> |        |         |
| <span data-ttu-id="bd961-155">300144-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="bd961-155">300144-OU\_1-OU\_3566-Training</span></span> |        | <span data-ttu-id="bd961-156">250,00</span><span class="sxs-lookup"><span data-stu-id="bd961-156">250.00</span></span> |         |

<span data-ttu-id="bd961-157">In questo esempio, qualsiasi conto fa parte di Struttura conti - profitti e perdite corrispondono ai criteri delle definizioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="bd961-157">In this example, any account that is part of Account Structure - P&L matches the posting definition criteria.</span></span> <span data-ttu-id="bd961-158">Pertanto, quando viene valutato 606500-OU\_1-OU\_3566-Training, le voci generate vengono create per i conti definiti nel riquadro **Voci generate** per la definizione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="bd961-158">Therefore, when 606500-OU\_1-OU\_3566-Training is evaluated, generated entries are created for the accounts that are defined in the **Generated entries** pane for the posting definition.</span></span>

## <a name="example-budget-appropriations"></a><span data-ttu-id="bd961-159">Esempio: Ripartizioni di budget</span><span class="sxs-lookup"><span data-stu-id="bd961-159">Example: Budget appropriations</span></span>
<span data-ttu-id="bd961-160">Quando si abilita la ripartizione di budget selezionando **Abilita ripartizione budget** nella pagina **Parametri contabilità generale**, le definizioni di registrazione devono essere utilizzate per registrare le voci del registro di budget nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="bd961-160">When you enable budget appropriation by selecting **Enable budget appropriation** on the **General ledger parameters** page, posting definitions must be used to record budget register entries to the general ledger.</span></span> <span data-ttu-id="bd961-161">Quando una configurazione del controllo del budget è attiva e abilitata, le definizioni di registrazione e le definizioni di registrazione delle transazioni possono essere utilizzate per sostenere la registrazione delle voci di ripartizione, revisione, trasferimento, progetto, cespite, e di previsione della domanda e dell'offerta nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="bd961-161">When a budget control configuration is active and is turned on, posting definitions and transaction posting definitions can be used to support the recording of entries for appropriations, revisions, transfers, projects, fixed assets, and supply and demand forecasts to the general ledger.</span></span> 

<span data-ttu-id="bd961-162">Una definizione di registrazione per voci del registro di budget del tipo di budget **Budget originale** e che ha abilitate le ripartizioni, può essere impostata selezionando il modulo **Budget** nella pagina **Definizioni di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="bd961-162">To set up a posting definition for budget register entries that has a budget type of **Original budget**, and that has appropriations enabled, select the **Budget** module on the **Posting definitions** page.</span></span> <span data-ttu-id="bd961-163">Quindi, nell'area **Budget** della pagina **Definizioni di registrazione transazioni**, è possibile utilizzare i codici budget per associare la definizione di registrazione a voci del registro di budget del tipo di budget **Budget originale**.</span><span class="sxs-lookup"><span data-stu-id="bd961-163">Then, in the **Budget** area of the **Transaction posting definitions** page, you can use budget codes to associate the posting definition with budget register entries that have a budget type of **Original budget**.</span></span> 

<span data-ttu-id="bd961-164">Se sono abilitate le ripartizioni di budget e le definizioni di registrazione, le voci del registro di budget vengono registrate per il controllo del budget e nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="bd961-164">When budget appropriations and posting definitions are enabled, the budget register entries are recorded for budget control and in the general ledger.</span></span>

### <a name="posting-definition--match-criteria"></a><span data-ttu-id="bd961-165">Definizione di registrazione – criteri di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="bd961-165">Posting definition – Match criteria</span></span>

| <span data-ttu-id="bd961-166">Struttura dei conti</span><span class="sxs-lookup"><span data-stu-id="bd961-166">Account structure</span></span>       | <span data-ttu-id="bd961-167">Associa numero di conto</span><span class="sxs-lookup"><span data-stu-id="bd961-167">Match account number</span></span> | <span data-ttu-id="bd961-168">Priorità</span><span class="sxs-lookup"><span data-stu-id="bd961-168">Priority</span></span> |
|-------------------------|----------------------|----------|
| <span data-ttu-id="bd961-169">Struttura dei conti - profitti e perdite</span><span class="sxs-lookup"><span data-stu-id="bd961-169">Account Structure - P&L</span></span> | \*                   | <span data-ttu-id="bd961-170">1</span><span class="sxs-lookup"><span data-stu-id="bd961-170">1</span></span>        |

<span data-ttu-id="bd961-171">*Un valore vuoto nel campo **Numero di conto** da associare implica che tutti i conti corrispondenti nella struttura dei conti definita faranno parte della regola di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="bd961-171">*A blank value in the **Match account number** field means that all matching accounts in the defined account structure are part of the matching rule.</span></span>

### <a name="posting-definition--generated-entries"></a><span data-ttu-id="bd961-172">Definizione di registrazione – voci generate</span><span class="sxs-lookup"><span data-stu-id="bd961-172">Posting definition – Generated entries</span></span>

| <span data-ttu-id="bd961-173">Struttura dei conti</span><span class="sxs-lookup"><span data-stu-id="bd961-173">Account structure</span></span> | <span data-ttu-id="bd961-174">Numero di conto generato</span><span class="sxs-lookup"><span data-stu-id="bd961-174">Generated account number</span></span>              | <span data-ttu-id="bd961-175">Dare/Avere generato</span><span class="sxs-lookup"><span data-stu-id="bd961-175">Generated debit/credit</span></span> |
|-------------------|---------------------------------------|------------------------|
| <span data-ttu-id="bd961-176">Struttura dei conti</span><span class="sxs-lookup"><span data-stu-id="bd961-176">Account structure</span></span> | <span data-ttu-id="bd961-177">300145 - -(Conto ricavi stimati)</span><span class="sxs-lookup"><span data-stu-id="bd961-177">300145 - -(Estimated revenue account)</span></span> | <span data-ttu-id="bd961-178">Uguali</span><span class="sxs-lookup"><span data-stu-id="bd961-178">Same</span></span>                   |
| <span data-ttu-id="bd961-179">Struttura dei conti</span><span class="sxs-lookup"><span data-stu-id="bd961-179">Account structure</span></span> | <span data-ttu-id="bd961-180">300146 - -(Conto ripartizioni)</span><span class="sxs-lookup"><span data-stu-id="bd961-180">300146 - -(Appropriation account)</span></span>     | <span data-ttu-id="bd961-181">Stare in equilibrio</span><span class="sxs-lookup"><span data-stu-id="bd961-181">Balancing</span></span>              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a><span data-ttu-id="bd961-182">Transazioni con i conti, i valori di dimensione e gli importi</span><span class="sxs-lookup"><span data-stu-id="bd961-182">Transactions with the accounts, dimension values, and amounts</span></span>

<span data-ttu-id="bd961-183">Nella pagina **Voce di registro budget** si immettono i conti, i valori di dimensione e gli importi per la voce contabile del budget.</span><span class="sxs-lookup"><span data-stu-id="bd961-183">You enter the accounts, dimension values, and amounts for the budget account entry on the **Budget register entry** page.</span></span>

| <span data-ttu-id="bd961-184">Conto + dimensioni</span><span class="sxs-lookup"><span data-stu-id="bd961-184">Account + dimensions</span></span>           | <span data-ttu-id="bd961-185">Dare</span><span class="sxs-lookup"><span data-stu-id="bd961-185">Debit</span></span> | <span data-ttu-id="bd961-186">Avere</span><span class="sxs-lookup"><span data-stu-id="bd961-186">Credit</span></span> | <span data-ttu-id="bd961-187">Commento</span><span class="sxs-lookup"><span data-stu-id="bd961-187">Comment</span></span> |
|--------------------------------|-------|--------|---------|
| <span data-ttu-id="bd961-188">606400-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="bd961-188">606400-OU\_1-OU\_3566-Training</span></span> |       | <span data-ttu-id="bd961-189">250,00</span><span class="sxs-lookup"><span data-stu-id="bd961-189">250.00</span></span> |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a><span data-ttu-id="bd961-190">Voci di contabilità generale generate dalla definizione di registrazione</span><span class="sxs-lookup"><span data-stu-id="bd961-190">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="bd961-191">Le voci di contabilità generale generate vengono create per registrare il budget originale in ciascuna dimensione.</span><span class="sxs-lookup"><span data-stu-id="bd961-191">Generated ledger entries are created to record the original budget in each dimension.</span></span>

| <span data-ttu-id="bd961-192">Conto + dimensioni</span><span class="sxs-lookup"><span data-stu-id="bd961-192">Account + dimensions</span></span>           | <span data-ttu-id="bd961-193">Dare</span><span class="sxs-lookup"><span data-stu-id="bd961-193">Debit</span></span>  | <span data-ttu-id="bd961-194">Avere</span><span class="sxs-lookup"><span data-stu-id="bd961-194">Credit</span></span> | <span data-ttu-id="bd961-195">Commento</span><span class="sxs-lookup"><span data-stu-id="bd961-195">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="bd961-196">300145-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="bd961-196">300145-OU\_1-OU\_3566-Training</span></span> |        | <span data-ttu-id="bd961-197">250,00</span><span class="sxs-lookup"><span data-stu-id="bd961-197">250.00</span></span> |         |
| <span data-ttu-id="bd961-198">300146-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="bd961-198">300146-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="bd961-199">250,00</span><span class="sxs-lookup"><span data-stu-id="bd961-199">250.00</span></span> |        |         |

<span data-ttu-id="bd961-200">In questo esempio, qualsiasi conto fa parte di Struttura conti - profitti e perdite corrispondono ai criteri delle definizioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="bd961-200">In this example, any account that is part of Account Structure - P&L matches the posting definition criteria.</span></span> <span data-ttu-id="bd961-201">Pertanto, quando viene valutato 606400-OU\_1-OU\_3566-Training, vengono create le voci della contabilità generale generate.</span><span class="sxs-lookup"><span data-stu-id="bd961-201">Therefore, when 606400-OU\_1-OU\_3566-Training is evaluated, the generated ledger entries are created.</span></span>






