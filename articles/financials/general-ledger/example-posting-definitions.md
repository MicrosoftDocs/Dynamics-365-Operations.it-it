---
title: Definizioni di registrazione
description: L'articolo offre alcuni esempi che mostrano come utilizzare le definizioni di registrazione per gli impegni di spesa di ordini fornitore e le ripartizioni di budget.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15772
ms.assetid: 3864e4da-853f-403d-b906-79631d80b363
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 09b78a40d3bac5794a66d0ea743f11a27cfacf4e
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839331"
---
# <a name="posting-definition-examples"></a><span data-ttu-id="39761-103">Esempi di definizioni di registrazione</span><span class="sxs-lookup"><span data-stu-id="39761-103">Posting definition examples</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39761-104">L'articolo offre alcuni esempi che mostrano come utilizzare le definizioni di registrazione per gli impegni di spesa di ordini fornitore e le ripartizioni di budget.</span><span class="sxs-lookup"><span data-stu-id="39761-104">This article provides examples that show how posting definitions are used for purchase order encumbrances and budget appropriations.</span></span>

<span data-ttu-id="39761-105">Prima di leggere questo argomento, è consigliabile acquisire familiarità con le definizioni di registrazione e le definizioni di registrazione della transazione.</span><span class="sxs-lookup"><span data-stu-id="39761-105">Before you read this topic, you should be familiar with posting definitions and transaction posting definitions.</span></span> <span data-ttu-id="39761-106">Per ulteriori informazioni, vedere [Definizioni di registrazione](posting-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="39761-106">For information, see [Posting definitions](posting-definitions.md).</span></span> <span data-ttu-id="39761-107">Gli esempi seguenti possono essere impostati nella pagina **Definizioni di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="39761-107">The following examples can be set up on the **Posting definitions** page.</span></span> <span data-ttu-id="39761-108">Ogni esempio contiene queste sezioni:</span><span class="sxs-lookup"><span data-stu-id="39761-108">Each example contains these sections:</span></span>

-   <span data-ttu-id="39761-109">Definizione di registrazione – criteri di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="39761-109">Posting definition – Match criteria</span></span>
-   <span data-ttu-id="39761-110">Definizione di registrazione – voci generate</span><span class="sxs-lookup"><span data-stu-id="39761-110">Posting definition – Generated entries</span></span>
-   <span data-ttu-id="39761-111">Transazioni con i conti, i valori di dimensione e gli importi</span><span class="sxs-lookup"><span data-stu-id="39761-111">Transactions with the accounts, dimension values, and amounts</span></span>
-   <span data-ttu-id="39761-112">Voci di contabilità generale generate dalla definizione di registrazione</span><span class="sxs-lookup"><span data-stu-id="39761-112">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="39761-113">In caso di corrispondenza tra i conti e i valori di dimensione nel riquadro **Associa criteri** per la definizione di registrazione e i conti e i valori di dimensione sulla transazione, vengono generate voci di contabilità generale basate sul riquadro **Voci generate** per la definizione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="39761-113">When a match occurs between the accounts and dimension values in the **Match criteria** pane for the posting definition and the accounts and dimension values on the transaction, ledger entries are generated based on the **Generated entries** pane for the posting definition.</span></span> 
> [!NOTE]
> <span data-ttu-id="39761-114">Per associare una definizione di registrazione a uno specifico tipo di transazione, utilizzare la pagina **Definizioni di registrazione transazioni**.</span><span class="sxs-lookup"><span data-stu-id="39761-114">To associate a posting definition with a specific transaction type, use the **Transaction posting definitions** page.</span></span> <span data-ttu-id="39761-115">Dopo aver associato una definizione di registrazione a un tipo di transazione e selezionato **Usa definizioni di registrazione** nella pagina **Parametri di contabilità generale**, tutte le transazioni del tipo selezionato devono utilizzare definizioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="39761-115">After you associate a posting definition with a transaction type and select **Use posting definitions** on the **General ledger parameters** page, all transactions of the selected transaction type must use posting definitions.</span></span>

## <a name="example-purchase-order-encumbrances"></a><span data-ttu-id="39761-116">Esempio: impegni di spesa ordini fornitore</span><span class="sxs-lookup"><span data-stu-id="39761-116">Example: Purchase order encumbrances</span></span>
<span data-ttu-id="39761-117">Quando si abilita l'elaborazione degli impegni di spesa selezionando **Abilita processo di impegno di spesa** nella pagina **Parametri di contabilità generale**, è necessario utilizzare le definizioni di registrazione per registrare gli impegni di spesa nella contabilità generale per tutti i conti che devono essere prenotati.</span><span class="sxs-lookup"><span data-stu-id="39761-117">When you enable encumbrance processing by selecting **Enable encumbrance process** on the **General ledger parameters** page, posting definitions must be used to record encumbrances to the general ledger for any accounts that should be reserved.</span></span> <span data-ttu-id="39761-118">Nella maggior parte dei casi, tutti i conti spese vengono prenotati sullo stato patrimoniale.</span><span class="sxs-lookup"><span data-stu-id="39761-118">In most cases, all expense accounts are reserved on the balance sheet.</span></span> 

<span data-ttu-id="39761-119">Le definizioni di registrazione per gli impegni di spesa vengono impostati per il modulo **Acquisto** nella pagina **Definizioni di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="39761-119">Posting definitions for encumbrances are set up for the **Purchasing** module on the **Posting definitions** page.</span></span> <span data-ttu-id="39761-120">Quindi, nell'area **Acquisto** della pagina **Definizioni di registrazione transazione**, è possibile selezionare il tipo di transazione **Ordine acquisto** per associare la definizione di registrazione agli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="39761-120">Then, in the **Purchasing** area of the **Transaction posting definitions** page, you can select the **Purchase order** transaction type to associate the posting definition with purchase orders.</span></span> 

<span data-ttu-id="39761-121">Tutte le transazioni giustificativo per gli impegni di spesa degli ordini fornitore devono compensarsi (i debiti devono essere pari ai crediti) in ciascuna dimensione univoca su un giustificativo.</span><span class="sxs-lookup"><span data-stu-id="39761-121">All voucher transactions for purchase order encumbrances must balance (that is, debits must equal credits) in each unique dimension on a voucher.</span></span>

### <a name="posting-definition--match-criteria"></a><span data-ttu-id="39761-122">Definizione di registrazione – criteri di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="39761-122">Posting definition – Match criteria</span></span>

| <span data-ttu-id="39761-123">Struttura dei conti</span><span class="sxs-lookup"><span data-stu-id="39761-123">Account structure</span></span>       | <span data-ttu-id="39761-124">Associa numero di conto</span><span class="sxs-lookup"><span data-stu-id="39761-124">Match account number</span></span> | <span data-ttu-id="39761-125">Priorità </span><span class="sxs-lookup"><span data-stu-id="39761-125">Priority</span></span> |
|-------------------------|----------------------|----------|
| <span data-ttu-id="39761-126">Struttura dei conti - profitti e perdite</span><span class="sxs-lookup"><span data-stu-id="39761-126">Account Structure - P&L</span></span> | \*                   | <span data-ttu-id="39761-127">1</span><span class="sxs-lookup"><span data-stu-id="39761-127">1</span></span>        |

<span data-ttu-id="39761-128"><em>Un valore vuoto nel campo \**Numero di conto da associare</em>* implica che tutti i conti corrispondenti nella struttura dei conti definita faranno parte della regola di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="39761-128"><em>A blank value in the \**Match account number</em>* field means that all matching accounts in the defined account structure are part of the matching rule.</span></span>

### <a name="posting-definition--generated-entries"></a><span data-ttu-id="39761-129">Definizione di registrazione – voci generate</span><span class="sxs-lookup"><span data-stu-id="39761-129">Posting definition – Generated entries</span></span>

| <span data-ttu-id="39761-130">Struttura dei conti</span><span class="sxs-lookup"><span data-stu-id="39761-130">Account structure</span></span> | <span data-ttu-id="39761-131">Numero di conto generato</span><span class="sxs-lookup"><span data-stu-id="39761-131">Generated account number</span></span>                    | <span data-ttu-id="39761-132">Dare/Avere generato</span><span class="sxs-lookup"><span data-stu-id="39761-132">Generated debit/credit</span></span> |
|-------------------|---------------------------------------------|------------------------|
| <span data-ttu-id="39761-133">Saldo</span><span class="sxs-lookup"><span data-stu-id="39761-133">Balance</span></span>           | <span data-ttu-id="39761-134">300143 - -(conto impegno di spesa)</span><span class="sxs-lookup"><span data-stu-id="39761-134">300143 - -(Encumbrance account)</span></span>             | <span data-ttu-id="39761-135">Uguali</span><span class="sxs-lookup"><span data-stu-id="39761-135">Same</span></span>                   |
| <span data-ttu-id="39761-136">Saldo</span><span class="sxs-lookup"><span data-stu-id="39761-136">Balance</span></span>           | <span data-ttu-id="39761-137">300144 - -(prenotazione conto impegno di spesa)</span><span class="sxs-lookup"><span data-stu-id="39761-137">300144 - -(Reserve for encumbrance account)</span></span> | <span data-ttu-id="39761-138">Stare in equilibrio</span><span class="sxs-lookup"><span data-stu-id="39761-138">Balancing</span></span>              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a><span data-ttu-id="39761-139">Transazioni con i conti, i valori di dimensione e gli importi</span><span class="sxs-lookup"><span data-stu-id="39761-139">Transactions with the accounts, dimension values, and amounts</span></span>

<span data-ttu-id="39761-140">I conti e i valori di dimensione derivano dalle distribuzioni contabili immesse per una riga dell'ordine fornitore oppure derivano dai conti e dalle dimensioni generati automaticamente in base alle impostazioni predefinite per fornitori, articoli, categorie e modelli di dimensione.</span><span class="sxs-lookup"><span data-stu-id="39761-140">The accounts and dimension values come either from the accounting distributions that you enter for a purchase order line, or from the accounts and dimensions that are automatically generated based on the default settings for vendors, items, categories, and dimension templates.</span></span>

| <span data-ttu-id="39761-141">Conto + dimensioni</span><span class="sxs-lookup"><span data-stu-id="39761-141">Account + dimensions</span></span>           | <span data-ttu-id="39761-142">Dare</span><span class="sxs-lookup"><span data-stu-id="39761-142">Debit</span></span>  | <span data-ttu-id="39761-143">Avere</span><span class="sxs-lookup"><span data-stu-id="39761-143">Credit</span></span> | <span data-ttu-id="39761-144">Commento</span><span class="sxs-lookup"><span data-stu-id="39761-144">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="39761-145">606400-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="39761-145">606400-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="39761-146">250,00</span><span class="sxs-lookup"><span data-stu-id="39761-146">250.00</span></span> |        |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a><span data-ttu-id="39761-147">Voci di contabilità generale generate dalla definizione di registrazione</span><span class="sxs-lookup"><span data-stu-id="39761-147">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="39761-148">Le voci di contabilità generale generate vengono create per registrare gli impegni di spesa.</span><span class="sxs-lookup"><span data-stu-id="39761-148">Generated ledger entries are created to record the encumbrances.</span></span>

| <span data-ttu-id="39761-149">Conto + dimensioni</span><span class="sxs-lookup"><span data-stu-id="39761-149">Account + dimensions</span></span>           | <span data-ttu-id="39761-150">Dare</span><span class="sxs-lookup"><span data-stu-id="39761-150">Debit</span></span>  | <span data-ttu-id="39761-151">Avere</span><span class="sxs-lookup"><span data-stu-id="39761-151">Credit</span></span> | <span data-ttu-id="39761-152">Commento</span><span class="sxs-lookup"><span data-stu-id="39761-152">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="39761-153">300143-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="39761-153">300143-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="39761-154">250,00</span><span class="sxs-lookup"><span data-stu-id="39761-154">250.00</span></span> |        |         |
| <span data-ttu-id="39761-155">300144-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="39761-155">300144-OU\_1-OU\_3566-Training</span></span> |        | <span data-ttu-id="39761-156">250,00</span><span class="sxs-lookup"><span data-stu-id="39761-156">250.00</span></span> |         |

<span data-ttu-id="39761-157">In questo esempio, qualsiasi conto fa parte di Struttura conti - profitti e perdite corrispondono ai criteri delle definizioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="39761-157">In this example, any account that is part of Account Structure - P&L matches the posting definition criteria.</span></span> <span data-ttu-id="39761-158">Pertanto, quando viene valutato 606500-OU\_1-OU\_3566-Training, le voci generate vengono create per i conti definiti nel riquadro **Voci generate** per la definizione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="39761-158">Therefore, when 606500-OU\_1-OU\_3566-Training is evaluated, generated entries are created for the accounts that are defined in the **Generated entries** pane for the posting definition.</span></span>

## <a name="example-budget-appropriations"></a><span data-ttu-id="39761-159">Esempio: Ripartizioni di budget</span><span class="sxs-lookup"><span data-stu-id="39761-159">Example: Budget appropriations</span></span>
<span data-ttu-id="39761-160">Quando si abilita la ripartizione di budget selezionando **Abilita ripartizione budget** nella pagina **Parametri contabilità generale**, le definizioni di registrazione devono essere utilizzate per registrare le voci del registro di budget nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="39761-160">When you enable budget appropriation by selecting **Enable budget appropriation** on the **General ledger parameters** page, posting definitions must be used to record budget register entries to the general ledger.</span></span> <span data-ttu-id="39761-161">Quando una configurazione del controllo del budget è attiva e abilitata, le definizioni di registrazione e le definizioni di registrazione delle transazioni possono essere utilizzate per sostenere la registrazione delle voci di ripartizione, revisione, trasferimento, progetto, cespite, e di previsione della domanda e dell'offerta nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="39761-161">When a budget control configuration is active and is turned on, posting definitions and transaction posting definitions can be used to support the recording of entries for appropriations, revisions, transfers, projects, fixed assets, and supply and demand forecasts to the general ledger.</span></span> 

<span data-ttu-id="39761-162">Una definizione di registrazione per voci del registro di budget del tipo di budget **Budget originale** e che ha abilitate le ripartizioni, può essere impostata selezionando il modulo **Budget** nella pagina **Definizioni di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="39761-162">To set up a posting definition for budget register entries that has a budget type of **Original budget**, and that has appropriations enabled, select the **Budget** module on the **Posting definitions** page.</span></span> <span data-ttu-id="39761-163">Quindi, nell'area **Budget** della pagina **Definizioni di registrazione transazioni**, è possibile utilizzare i codici budget per associare la definizione di registrazione a voci del registro di budget del tipo di budget **Budget originale**.</span><span class="sxs-lookup"><span data-stu-id="39761-163">Then, in the **Budget** area of the **Transaction posting definitions** page, you can use budget codes to associate the posting definition with budget register entries that have a budget type of **Original budget**.</span></span> 

<span data-ttu-id="39761-164">Se sono abilitate le ripartizioni di budget e le definizioni di registrazione, le voci del registro di budget vengono registrate per il controllo del budget e nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="39761-164">When budget appropriations and posting definitions are enabled, the budget register entries are recorded for budget control and in the general ledger.</span></span>

### <a name="posting-definition--match-criteria"></a><span data-ttu-id="39761-165">Definizione di registrazione – criteri di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="39761-165">Posting definition – Match criteria</span></span>

| <span data-ttu-id="39761-166">Struttura dei conti</span><span class="sxs-lookup"><span data-stu-id="39761-166">Account structure</span></span>       | <span data-ttu-id="39761-167">Associa numero di conto</span><span class="sxs-lookup"><span data-stu-id="39761-167">Match account number</span></span> | <span data-ttu-id="39761-168">Priorità </span><span class="sxs-lookup"><span data-stu-id="39761-168">Priority</span></span> |
|-------------------------|----------------------|----------|
| <span data-ttu-id="39761-169">Struttura dei conti - profitti e perdite</span><span class="sxs-lookup"><span data-stu-id="39761-169">Account Structure - P&L</span></span> | \*                   | <span data-ttu-id="39761-170">1</span><span class="sxs-lookup"><span data-stu-id="39761-170">1</span></span>        |

<span data-ttu-id="39761-171"><em>Un valore vuoto nel campo \**Numero di conto da associare</em>* implica che tutti i conti corrispondenti nella struttura dei conti definita faranno parte della regola di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="39761-171"><em>A blank value in the \**Match account number</em>* field means that all matching accounts in the defined account structure are part of the matching rule.</span></span>

### <a name="posting-definition--generated-entries"></a><span data-ttu-id="39761-172">Definizione di registrazione – voci generate</span><span class="sxs-lookup"><span data-stu-id="39761-172">Posting definition – Generated entries</span></span>

| <span data-ttu-id="39761-173">Struttura dei conti</span><span class="sxs-lookup"><span data-stu-id="39761-173">Account structure</span></span> | <span data-ttu-id="39761-174">Numero di conto generato</span><span class="sxs-lookup"><span data-stu-id="39761-174">Generated account number</span></span>              | <span data-ttu-id="39761-175">Dare/Avere generato</span><span class="sxs-lookup"><span data-stu-id="39761-175">Generated debit/credit</span></span> |
|-------------------|---------------------------------------|------------------------|
| <span data-ttu-id="39761-176">Struttura dei conti</span><span class="sxs-lookup"><span data-stu-id="39761-176">Account structure</span></span> | <span data-ttu-id="39761-177">300145 - -(Conto ricavi stimati)</span><span class="sxs-lookup"><span data-stu-id="39761-177">300145 - -(Estimated revenue account)</span></span> | <span data-ttu-id="39761-178">Uguali</span><span class="sxs-lookup"><span data-stu-id="39761-178">Same</span></span>                   |
| <span data-ttu-id="39761-179">Struttura dei conti</span><span class="sxs-lookup"><span data-stu-id="39761-179">Account structure</span></span> | <span data-ttu-id="39761-180">300146 - -(Conto ripartizioni)</span><span class="sxs-lookup"><span data-stu-id="39761-180">300146 - -(Appropriation account)</span></span>     | <span data-ttu-id="39761-181">Stare in equilibrio</span><span class="sxs-lookup"><span data-stu-id="39761-181">Balancing</span></span>              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a><span data-ttu-id="39761-182">Transazioni con i conti, i valori di dimensione e gli importi</span><span class="sxs-lookup"><span data-stu-id="39761-182">Transactions with the accounts, dimension values, and amounts</span></span>

<span data-ttu-id="39761-183">Nella pagina **Voce di registro budget** si immettono i conti, i valori di dimensione e gli importi per la voce contabile del budget.</span><span class="sxs-lookup"><span data-stu-id="39761-183">You enter the accounts, dimension values, and amounts for the budget account entry on the **Budget register entry** page.</span></span>

| <span data-ttu-id="39761-184">Conto + dimensioni</span><span class="sxs-lookup"><span data-stu-id="39761-184">Account + dimensions</span></span>           | <span data-ttu-id="39761-185">Dare</span><span class="sxs-lookup"><span data-stu-id="39761-185">Debit</span></span> | <span data-ttu-id="39761-186">Avere</span><span class="sxs-lookup"><span data-stu-id="39761-186">Credit</span></span> | <span data-ttu-id="39761-187">Commento</span><span class="sxs-lookup"><span data-stu-id="39761-187">Comment</span></span> |
|--------------------------------|-------|--------|---------|
| <span data-ttu-id="39761-188">606400-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="39761-188">606400-OU\_1-OU\_3566-Training</span></span> |       | <span data-ttu-id="39761-189">250,00</span><span class="sxs-lookup"><span data-stu-id="39761-189">250.00</span></span> |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a><span data-ttu-id="39761-190">Voci di contabilità generale generate dalla definizione di registrazione</span><span class="sxs-lookup"><span data-stu-id="39761-190">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="39761-191">Le voci di contabilità generale generate vengono create per registrare il budget originale in ciascuna dimensione.</span><span class="sxs-lookup"><span data-stu-id="39761-191">Generated ledger entries are created to record the original budget in each dimension.</span></span>

| <span data-ttu-id="39761-192">Conto + dimensioni</span><span class="sxs-lookup"><span data-stu-id="39761-192">Account + dimensions</span></span>           | <span data-ttu-id="39761-193">Dare</span><span class="sxs-lookup"><span data-stu-id="39761-193">Debit</span></span>  | <span data-ttu-id="39761-194">Avere</span><span class="sxs-lookup"><span data-stu-id="39761-194">Credit</span></span> | <span data-ttu-id="39761-195">Commento</span><span class="sxs-lookup"><span data-stu-id="39761-195">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="39761-196">300145-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="39761-196">300145-OU\_1-OU\_3566-Training</span></span> |        | <span data-ttu-id="39761-197">250,00</span><span class="sxs-lookup"><span data-stu-id="39761-197">250.00</span></span> |         |
| <span data-ttu-id="39761-198">300146-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="39761-198">300146-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="39761-199">250,00</span><span class="sxs-lookup"><span data-stu-id="39761-199">250.00</span></span> |        |         |

<span data-ttu-id="39761-200">In questo esempio, qualsiasi conto fa parte di Struttura conti - profitti e perdite corrispondono ai criteri delle definizioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="39761-200">In this example, any account that is part of Account Structure - P&L matches the posting definition criteria.</span></span> <span data-ttu-id="39761-201">Pertanto, quando viene valutato 606400-OU\_1-OU\_3566-Training, vengono create le voci della contabilità generale generate.</span><span class="sxs-lookup"><span data-stu-id="39761-201">Therefore, when 606400-OU\_1-OU\_3566-Training is evaluated, the generated ledger entries are created.</span></span>





