---
title: Doppio reporting
description: In questo argomento viene illustrato un esempio che mostra come soddisfare i requisiti sia per la creazione di report International Financial Reporting Standard (IFRS) sia per il reporting statutario nel leasing di cespiti.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d6daa43178625316a40427728e7e4186691cc13c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229552"
---
# <a name="dual-reporting"></a><span data-ttu-id="44f5d-103">Doppio reporting</span><span class="sxs-lookup"><span data-stu-id="44f5d-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="44f5d-104">In questo argomento viene illustrato un esempio che mostra come soddisfare i requisiti sia per la creazione di report International Financial Reporting Standard (IFRS) sia per il reporting statutario nel leasing di cespiti.</span><span class="sxs-lookup"><span data-stu-id="44f5d-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="44f5d-105">La conoscenza dei livelli di registrazione in Microsoft Dynamics 365 Finance è obbligatoria e renderà l'esempio più facile da capire.</span><span class="sxs-lookup"><span data-stu-id="44f5d-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="44f5d-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="44f5d-106">Example</span></span>

<span data-ttu-id="44f5d-107">Il seguente esempio utilizza un leasing ai sensi del reporting statutario italiano utilizzando sia il metodo di cassa sia i metodi di reporting IFRS.</span><span class="sxs-lookup"><span data-stu-id="44f5d-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="44f5d-108">L'azienda deve stabilire tre libri contabili per tenere conto sia dei requisiti legali italiani che dei requisiti IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="44f5d-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="44f5d-109">Un libro è richiesto per l'IFRS 16, un libro è richiesto per i requisiti legali e un libro è richiesto per stornare automaticamente le registrazioni statutarie.</span><span class="sxs-lookup"><span data-stu-id="44f5d-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="44f5d-110">I libri sono configurati come mostrato nelle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="44f5d-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="44f5d-111">**Libro IFRS 16**</span><span class="sxs-lookup"><span data-stu-id="44f5d-111">**IFRS 16 book**</span></span>

<span data-ttu-id="44f5d-112">Il libro IFRS 16 è configurato in modo da essere conforme al principio contabile IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="44f5d-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="44f5d-113">Tutte le voci registrate in questo libro verranno registrate su un livello personalizzato.</span><span class="sxs-lookup"><span data-stu-id="44f5d-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="44f5d-114">Nome</span><span class="sxs-lookup"><span data-stu-id="44f5d-114">Name</span></span>                                    | <span data-ttu-id="44f5d-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44f5d-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="44f5d-116">Tipo libro</span><span class="sxs-lookup"><span data-stu-id="44f5d-116">Book type</span></span>                               | <span data-ttu-id="44f5d-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="44f5d-117">IFRS 16</span></span>        |
| <span data-ttu-id="44f5d-118">Descrizione del libro</span><span class="sxs-lookup"><span data-stu-id="44f5d-118">Book description</span></span>                        | <span data-ttu-id="44f5d-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="44f5d-119">IFRS 16</span></span>        |
| <span data-ttu-id="44f5d-120">Livello di registrazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-120">Posting Layer</span></span>                           | <span data-ttu-id="44f5d-121">Livello personalizzato 1</span><span class="sxs-lookup"><span data-stu-id="44f5d-121">Custom layer 1</span></span> |
| <span data-ttu-id="44f5d-122">Tipo di leasing</span><span class="sxs-lookup"><span data-stu-id="44f5d-122">Lease Type</span></span>                              | <span data-ttu-id="44f5d-123">Finance</span><span class="sxs-lookup"><span data-stu-id="44f5d-123">Finance</span></span>        |
| <span data-ttu-id="44f5d-124">Framework di contabilità</span><span class="sxs-lookup"><span data-stu-id="44f5d-124">Accounting Framework</span></span>                    | <span data-ttu-id="44f5d-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="44f5d-125">IFRS 16</span></span>        |
| <span data-ttu-id="44f5d-126">Configurazione termine del leasing/vita utile</span><span class="sxs-lookup"><span data-stu-id="44f5d-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="44f5d-127">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-127">0.00</span></span>           |
| <span data-ttu-id="44f5d-128">Configurazione valore corrente/valore equo cespite</span><span class="sxs-lookup"><span data-stu-id="44f5d-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="44f5d-129">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-129">0.00</span></span>           |
| <span data-ttu-id="44f5d-130">Soglia a breve termine</span><span class="sxs-lookup"><span data-stu-id="44f5d-130">Short-term threshold</span></span>                    | <span data-ttu-id="44f5d-131">12</span><span class="sxs-lookup"><span data-stu-id="44f5d-131">12</span></span>             |
| <span data-ttu-id="44f5d-132">Soglia valore basso</span><span class="sxs-lookup"><span data-stu-id="44f5d-132">Low Value Threshold</span></span>                     | <span data-ttu-id="44f5d-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-133">5,000.00</span></span>       |
| <span data-ttu-id="44f5d-134">Pagamento al fornitore</span><span class="sxs-lookup"><span data-stu-id="44f5d-134">Pay to Vendor</span></span>                           | <span data-ttu-id="44f5d-135">Nessuno</span><span class="sxs-lookup"><span data-stu-id="44f5d-135">No</span></span>             |

<span data-ttu-id="44f5d-136">**Libro statutario**</span><span class="sxs-lookup"><span data-stu-id="44f5d-136">**Statutory book**</span></span>

<span data-ttu-id="44f5d-137">Il libro statutario è un libro di cassa in cui la società contabilizzerà le spese di leasing come l'importo in contanti che viene pagato ogni mese per l'affitto.</span><span class="sxs-lookup"><span data-stu-id="44f5d-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="44f5d-138">Questo libro non produrrà un Asset Right of use un'obbligazione sul leasing.</span><span class="sxs-lookup"><span data-stu-id="44f5d-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="44f5d-139">Nome</span><span class="sxs-lookup"><span data-stu-id="44f5d-139">Name</span></span>                                    | <span data-ttu-id="44f5d-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44f5d-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="44f5d-141">Tipo libro</span><span class="sxs-lookup"><span data-stu-id="44f5d-141">Book type</span></span>                               | <span data-ttu-id="44f5d-142">Statutario</span><span class="sxs-lookup"><span data-stu-id="44f5d-142">Statutory</span></span>   |
| <span data-ttu-id="44f5d-143">Descrizione del libro</span><span class="sxs-lookup"><span data-stu-id="44f5d-143">Book description</span></span>                        | <span data-ttu-id="44f5d-144">GAAP locale</span><span class="sxs-lookup"><span data-stu-id="44f5d-144">Local GAAP</span></span>  |
| <span data-ttu-id="44f5d-145">Livello di registrazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-145">Posting Layer</span></span>                           | <span data-ttu-id="44f5d-146">Correnti</span><span class="sxs-lookup"><span data-stu-id="44f5d-146">Current</span></span>     |
| <span data-ttu-id="44f5d-147">Tipo di leasing</span><span class="sxs-lookup"><span data-stu-id="44f5d-147">Lease Type</span></span>                              | <span data-ttu-id="44f5d-148">Automatica</span><span class="sxs-lookup"><span data-stu-id="44f5d-148">Automatic</span></span>   |
| <span data-ttu-id="44f5d-149">Framework di contabilità</span><span class="sxs-lookup"><span data-stu-id="44f5d-149">Accounting Framework</span></span>                    | <span data-ttu-id="44f5d-150">Cassa</span><span class="sxs-lookup"><span data-stu-id="44f5d-150">Cash basis</span></span>  |
| <span data-ttu-id="44f5d-151">Configurazione termine del leasing/vita utile</span><span class="sxs-lookup"><span data-stu-id="44f5d-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="44f5d-152">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-152">0.00</span></span>        |
| <span data-ttu-id="44f5d-153">Configurazione valore corrente/valore equo cespite</span><span class="sxs-lookup"><span data-stu-id="44f5d-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="44f5d-154">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-154">0.00</span></span>        |
| <span data-ttu-id="44f5d-155">Soglia a breve termine</span><span class="sxs-lookup"><span data-stu-id="44f5d-155">Short-term threshold</span></span>                    | <span data-ttu-id="44f5d-156">0</span><span class="sxs-lookup"><span data-stu-id="44f5d-156">0</span></span>           |
| <span data-ttu-id="44f5d-157">Soglia valore basso</span><span class="sxs-lookup"><span data-stu-id="44f5d-157">Low Value Threshold</span></span>                     | <span data-ttu-id="44f5d-158">0</span><span class="sxs-lookup"><span data-stu-id="44f5d-158">0</span></span>           |
| <span data-ttu-id="44f5d-159">Pagamento al fornitore</span><span class="sxs-lookup"><span data-stu-id="44f5d-159">Pay to Vendor</span></span>                           | <span data-ttu-id="44f5d-160">Nessuno</span><span class="sxs-lookup"><span data-stu-id="44f5d-160">No</span></span>          |

<span data-ttu-id="44f5d-161">**Libro storno statutario**</span><span class="sxs-lookup"><span data-stu-id="44f5d-161">**Statutory reversal book**</span></span>

<span data-ttu-id="44f5d-162">Il libro di storno statutario è configurato allo stesso modo del libro statutario.</span><span class="sxs-lookup"><span data-stu-id="44f5d-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="44f5d-163">Nome</span><span class="sxs-lookup"><span data-stu-id="44f5d-163">Name</span></span>                                    | <span data-ttu-id="44f5d-164">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44f5d-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="44f5d-165">Tipo libro</span><span class="sxs-lookup"><span data-stu-id="44f5d-165">Book type</span></span>                               | <span data-ttu-id="44f5d-166">Statutario - Storno</span><span class="sxs-lookup"><span data-stu-id="44f5d-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="44f5d-167">Descrizione del libro</span><span class="sxs-lookup"><span data-stu-id="44f5d-167">Book description</span></span>                        | <span data-ttu-id="44f5d-168">Libro per stornare libro statutario</span><span class="sxs-lookup"><span data-stu-id="44f5d-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="44f5d-169">Livello di registrazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-169">Posting Layer</span></span>                           | <span data-ttu-id="44f5d-170">Livello personalizzato 1</span><span class="sxs-lookup"><span data-stu-id="44f5d-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="44f5d-171">Tipo di leasing</span><span class="sxs-lookup"><span data-stu-id="44f5d-171">Lease Type</span></span>                              | <span data-ttu-id="44f5d-172">Automatica</span><span class="sxs-lookup"><span data-stu-id="44f5d-172">Automatic</span></span>                      |
| <span data-ttu-id="44f5d-173">Framework di contabilità</span><span class="sxs-lookup"><span data-stu-id="44f5d-173">Accounting Framework</span></span>                    | <span data-ttu-id="44f5d-174">Cassa</span><span class="sxs-lookup"><span data-stu-id="44f5d-174">Cash basis</span></span>                     |
| <span data-ttu-id="44f5d-175">Configurazione termine del leasing/vita utile</span><span class="sxs-lookup"><span data-stu-id="44f5d-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="44f5d-176">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-176">0.00</span></span>                           |
| <span data-ttu-id="44f5d-177">Configurazione valore corrente/valore equo cespite</span><span class="sxs-lookup"><span data-stu-id="44f5d-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="44f5d-178">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-178">0.00</span></span>                           |
| <span data-ttu-id="44f5d-179">Soglia a breve termine</span><span class="sxs-lookup"><span data-stu-id="44f5d-179">Short-term threshold</span></span>                    | <span data-ttu-id="44f5d-180">0</span><span class="sxs-lookup"><span data-stu-id="44f5d-180">0</span></span>                              |
| <span data-ttu-id="44f5d-181">Soglia valore basso</span><span class="sxs-lookup"><span data-stu-id="44f5d-181">Low Value Threshold</span></span>                     | <span data-ttu-id="44f5d-182">0</span><span class="sxs-lookup"><span data-stu-id="44f5d-182">0</span></span>                              |
| <span data-ttu-id="44f5d-183">Pagamento al fornitore</span><span class="sxs-lookup"><span data-stu-id="44f5d-183">Pay to Vendor</span></span>                           | <span data-ttu-id="44f5d-184">Nessuno</span><span class="sxs-lookup"><span data-stu-id="44f5d-184">No</span></span>                             |

<span data-ttu-id="44f5d-185">Per questo esempio, è stato creato un contratto di leasing con le seguenti impostazioni nelle schede **Generale** e **Righe scadenzario pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="44f5d-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="44f5d-186">**Scheda Generale**</span><span class="sxs-lookup"><span data-stu-id="44f5d-186">**General tab**</span></span>

| <span data-ttu-id="44f5d-187">Campo</span><span class="sxs-lookup"><span data-stu-id="44f5d-187">Field</span></span>                      | <span data-ttu-id="44f5d-188">Valore</span><span class="sxs-lookup"><span data-stu-id="44f5d-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="44f5d-189">Tasso incrementale di prestito</span><span class="sxs-lookup"><span data-stu-id="44f5d-189">Incremental borrowing rate</span></span> | <span data-ttu-id="44f5d-190">5%</span><span class="sxs-lookup"><span data-stu-id="44f5d-190">5%</span></span>               |
| <span data-ttu-id="44f5d-191">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="44f5d-191">Commencement date</span></span>          | <span data-ttu-id="44f5d-192">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="44f5d-192">1/1/2020</span></span>         |
| <span data-ttu-id="44f5d-193">Gruppo di leasing</span><span class="sxs-lookup"><span data-stu-id="44f5d-193">Lease group</span></span>                | <span data-ttu-id="44f5d-194">Edifici</span><span class="sxs-lookup"><span data-stu-id="44f5d-194">Buildings</span></span>        |
| <span data-ttu-id="44f5d-195">Fornitore</span><span class="sxs-lookup"><span data-stu-id="44f5d-195">Vendor</span></span>                     | <span data-ttu-id="44f5d-196">1001</span><span class="sxs-lookup"><span data-stu-id="44f5d-196">1001</span></span>             |
| <span data-ttu-id="44f5d-197">Valore equo del cespite</span><span class="sxs-lookup"><span data-stu-id="44f5d-197">Fair value of the asset</span></span>    | <span data-ttu-id="44f5d-198">245,000</span><span class="sxs-lookup"><span data-stu-id="44f5d-198">245,000</span></span>          |
| <span data-ttu-id="44f5d-199">Vita utile del cespite</span><span class="sxs-lookup"><span data-stu-id="44f5d-199">Asset useful life</span></span>          | <span data-ttu-id="44f5d-200">120</span><span class="sxs-lookup"><span data-stu-id="44f5d-200">120</span></span>              |
| <span data-ttu-id="44f5d-201">Tipo di rendita finanziaria</span><span class="sxs-lookup"><span data-stu-id="44f5d-201">Annuity type</span></span>               | <span data-ttu-id="44f5d-202">Rendita finanziaria posticipata</span><span class="sxs-lookup"><span data-stu-id="44f5d-202">Ordinary annuity</span></span> |
| <span data-ttu-id="44f5d-203">Intervallo interessi composti</span><span class="sxs-lookup"><span data-stu-id="44f5d-203">Compounding interval</span></span>       | <span data-ttu-id="44f5d-204">Ogni mese</span><span class="sxs-lookup"><span data-stu-id="44f5d-204">Monthly</span></span>          |

<span data-ttu-id="44f5d-205">**Scheda Righe scadenzario pagamenti**</span><span class="sxs-lookup"><span data-stu-id="44f5d-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="44f5d-206">Campo</span><span class="sxs-lookup"><span data-stu-id="44f5d-206">Field</span></span>             | <span data-ttu-id="44f5d-207">Valore</span><span class="sxs-lookup"><span data-stu-id="44f5d-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="44f5d-208">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="44f5d-208">Start date</span></span>        | <span data-ttu-id="44f5d-209">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="44f5d-209">1/1/2020</span></span>   |
| <span data-ttu-id="44f5d-210">Intervallo periodico</span><span class="sxs-lookup"><span data-stu-id="44f5d-210">Period interval</span></span>   | <span data-ttu-id="44f5d-211">Mesi</span><span class="sxs-lookup"><span data-stu-id="44f5d-211">Months</span></span>     |
| <span data-ttu-id="44f5d-212">Periodi</span><span class="sxs-lookup"><span data-stu-id="44f5d-212">Periods</span></span>           | <span data-ttu-id="44f5d-213">24</span><span class="sxs-lookup"><span data-stu-id="44f5d-213">24</span></span>         |
| <span data-ttu-id="44f5d-214">Data di fine</span><span class="sxs-lookup"><span data-stu-id="44f5d-214">End date</span></span>          | <span data-ttu-id="44f5d-215">31/12/2020</span><span class="sxs-lookup"><span data-stu-id="44f5d-215">12/31/2020</span></span> |
| <span data-ttu-id="44f5d-216">Frequenza pagamenti</span><span class="sxs-lookup"><span data-stu-id="44f5d-216">Payment frequency</span></span> | <span data-ttu-id="44f5d-217">Ogni mese</span><span class="sxs-lookup"><span data-stu-id="44f5d-217">Monthly</span></span>    |
| <span data-ttu-id="44f5d-218">Importo pagamento</span><span class="sxs-lookup"><span data-stu-id="44f5d-218">Payment amount</span></span>    | <span data-ttu-id="44f5d-219">1.000</span><span class="sxs-lookup"><span data-stu-id="44f5d-219">1,000</span></span>      |

<span data-ttu-id="44f5d-220">Per contabilizzare questo leasing in due framework, utilizza un livello di registrazione corrente e un livello di registrazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="44f5d-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="44f5d-221">La tabella seguente mostra un esempio di ogni registrazione a giornale il cui obbligo era di rappresentare equamente i dati finanziari in ogni standard di reporting.</span><span class="sxs-lookup"><span data-stu-id="44f5d-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="44f5d-222">Successivamente viene fornita una descrizione dettagliata di ciascuna registrazione a giornale per il primo mese del contratto di leasing.</span><span class="sxs-lookup"><span data-stu-id="44f5d-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="44f5d-223">Numero conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="44f5d-224">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44f5d-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="44f5d-225">Libro statutario (livello attuale)</span><span class="sxs-lookup"><span data-stu-id="44f5d-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="44f5d-226">Totale livello corrente</span><span class="sxs-lookup"><span data-stu-id="44f5d-226">Current layer total</span></span></th>
<th><span data-ttu-id="44f5d-227">Libro di storno (livello personalizzato)</span><span class="sxs-lookup"><span data-stu-id="44f5d-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="44f5d-228">Libro IFRS 16 (livello personalizzato)</span><span class="sxs-lookup"><span data-stu-id="44f5d-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="44f5d-229">Totale livello corrente + livello personalizzato</span><span class="sxs-lookup"><span data-stu-id="44f5d-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="44f5d-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="44f5d-230">JE-100</span></span></th>
<th><span data-ttu-id="44f5d-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="44f5d-231">JE-110</span></span></th>
<th><span data-ttu-id="44f5d-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="44f5d-232">JE-120</span></span></th>
<th><span data-ttu-id="44f5d-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="44f5d-233">JE-130</span></span></th>
<th><span data-ttu-id="44f5d-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="44f5d-234">JE-140</span></span></th>
<th><span data-ttu-id="44f5d-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="44f5d-235">JE-150</span></span></th>
<th><span data-ttu-id="44f5d-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="44f5d-236">JE-160</span></span></th>
<th><span data-ttu-id="44f5d-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="44f5d-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="44f5d-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="44f5d-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="44f5d-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="44f5d-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="44f5d-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="44f5d-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="44f5d-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="44f5d-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="44f5d-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="44f5d-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="44f5d-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="44f5d-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="44f5d-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="44f5d-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="44f5d-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="44f5d-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="44f5d-246">1</span><span class="sxs-lookup"><span data-stu-id="44f5d-246">1</span></span></td>
<td><span data-ttu-id="44f5d-247">Spesa di leasing</span><span class="sxs-lookup"><span data-stu-id="44f5d-247">Lease expense</span></span></td>
<td><span data-ttu-id="44f5d-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-249">1,000.00</span></span></td>
<td><span data-ttu-id="44f5d-250">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-251">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-252">2</span><span class="sxs-lookup"><span data-stu-id="44f5d-252">2</span></span></td>
<td><span data-ttu-id="44f5d-253">Commissione bancaria</span><span class="sxs-lookup"><span data-stu-id="44f5d-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-254">3.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-255">3.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-256">3.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-257">3</span><span class="sxs-lookup"><span data-stu-id="44f5d-257">3</span></span></td>
<td><span data-ttu-id="44f5d-258">Spesa IVA</span><span class="sxs-lookup"><span data-stu-id="44f5d-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-259">5.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-260">5.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-261">5.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-262">4</span><span class="sxs-lookup"><span data-stu-id="44f5d-262">4</span></span></td>
<td><span data-ttu-id="44f5d-263">Conto di compensazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-263">Clearing account</span></span></td>
<td><span data-ttu-id="44f5d-264">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-264">-1,000.00</span></span></td>
<td><span data-ttu-id="44f5d-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-266">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-266">0.00</span></span></td>
<td><span data-ttu-id="44f5d-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-268">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-269">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-270">5</span><span class="sxs-lookup"><span data-stu-id="44f5d-270">5</span></span></td>
<td><span data-ttu-id="44f5d-271">Contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="44f5d-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-272">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-272">-1,008.00</span></span></td>
<td><span data-ttu-id="44f5d-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-273">1,008.00</span></span></td>
<td><span data-ttu-id="44f5d-274">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-275">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-276">6</span><span class="sxs-lookup"><span data-stu-id="44f5d-276">6</span></span></td>
<td><span data-ttu-id="44f5d-277">Asset ROU</span><span class="sxs-lookup"><span data-stu-id="44f5d-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-278">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="44f5d-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-281">7</span><span class="sxs-lookup"><span data-stu-id="44f5d-281">7</span></span></td>
<td><span data-ttu-id="44f5d-282">Obbligo di leasing finanziario</span><span class="sxs-lookup"><span data-stu-id="44f5d-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-283">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-284">-22.794,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-284">-22,794.00</span></span></td>
<td><span data-ttu-id="44f5d-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-285">1,000.00</span></span></td>
<td><span data-ttu-id="44f5d-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="44f5d-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-287">-21.888,87</span><span class="sxs-lookup"><span data-stu-id="44f5d-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-288">8</span><span class="sxs-lookup"><span data-stu-id="44f5d-288">8</span></span></td>
<td><span data-ttu-id="44f5d-289">Interessi passivi</span><span class="sxs-lookup"><span data-stu-id="44f5d-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-290">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-291">94.97</span><span class="sxs-lookup"><span data-stu-id="44f5d-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-292">94.97</span><span class="sxs-lookup"><span data-stu-id="44f5d-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-293">9</span><span class="sxs-lookup"><span data-stu-id="44f5d-293">9</span></span></td>
<td><span data-ttu-id="44f5d-294">Cassa</span><span class="sxs-lookup"><span data-stu-id="44f5d-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-295">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-295">-1,008.00</span></span></td>
<td><span data-ttu-id="44f5d-296">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-297">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-298">10</span><span class="sxs-lookup"><span data-stu-id="44f5d-298">10</span></span></td>
<td><span data-ttu-id="44f5d-299">Spesa di ammortamento</span><span class="sxs-lookup"><span data-stu-id="44f5d-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-300">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-301">949.75</span><span class="sxs-lookup"><span data-stu-id="44f5d-301">949.75</span></span></td>
<td><span data-ttu-id="44f5d-302">949.75</span><span class="sxs-lookup"><span data-stu-id="44f5d-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-303">11</span><span class="sxs-lookup"><span data-stu-id="44f5d-303">11</span></span></td>
<td><span data-ttu-id="44f5d-304">Fondo di ammortamento</span><span class="sxs-lookup"><span data-stu-id="44f5d-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-305">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="44f5d-306">-949.75</span></span></td>
<td><span data-ttu-id="44f5d-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="44f5d-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="44f5d-308">Come mostra la tabella precedente, sono obbligatori tre libri per la rendicontazione ai sensi sia del reporting statutario che del reporting IFRS.</span><span class="sxs-lookup"><span data-stu-id="44f5d-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="44f5d-309">Il libro legale registra il canone di leasing secondo le regole per la contabilità di cassa nel livello corrente.</span><span class="sxs-lookup"><span data-stu-id="44f5d-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="44f5d-310">Il libro di storno statutario storna le registrazioni di scrittura contabile.</span><span class="sxs-lookup"><span data-stu-id="44f5d-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="44f5d-311">Il libro IFRS 16 crea le registrazioni di scrittura contabile obbligatorie ai sensi di IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="44f5d-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="44f5d-312">Devi inserire un leasing solo una volta.</span><span class="sxs-lookup"><span data-stu-id="44f5d-312">You must enter a lease only one time.</span></span> <span data-ttu-id="44f5d-313">È quindi possibile aprire la pagina **Libri** per vedere tutti i libri associati al leasing.</span><span class="sxs-lookup"><span data-stu-id="44f5d-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="44f5d-314">Quando crei i libri, tutti e tre devono essere associati allo stesso record di leasing.</span><span class="sxs-lookup"><span data-stu-id="44f5d-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="44f5d-315">La prima registrazione a giornale registra le spese di leasing nel libro statutario.</span><span class="sxs-lookup"><span data-stu-id="44f5d-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="44f5d-316">È possibile creare i pagamenti in batch o selezionando lo scadenzario pagamenti nel libro statutario.</span><span class="sxs-lookup"><span data-stu-id="44f5d-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="44f5d-317">Per questo esempio, la seguente scrittura contabile viene prodotta per il libro legale dallo scadenzario pagamenti.</span><span class="sxs-lookup"><span data-stu-id="44f5d-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="44f5d-318">Canone di leasing - 31/01/2020 - JE 100</span><span class="sxs-lookup"><span data-stu-id="44f5d-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="44f5d-319">Tipo di account</span><span class="sxs-lookup"><span data-stu-id="44f5d-319">Account type</span></span> | <span data-ttu-id="44f5d-320">Numero conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-320">Account number</span></span> | <span data-ttu-id="44f5d-321">Livello</span><span class="sxs-lookup"><span data-stu-id="44f5d-321">Layer</span></span>   | <span data-ttu-id="44f5d-322">Descrizione conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-322">Account description</span></span> | <span data-ttu-id="44f5d-323">Dare</span><span class="sxs-lookup"><span data-stu-id="44f5d-323">Debit</span></span>    | <span data-ttu-id="44f5d-324">Avere</span><span class="sxs-lookup"><span data-stu-id="44f5d-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="44f5d-325">Ledger</span><span class="sxs-lookup"><span data-stu-id="44f5d-325">Ledger</span></span>       | <span data-ttu-id="44f5d-326">1</span><span class="sxs-lookup"><span data-stu-id="44f5d-326">1</span></span>              | <span data-ttu-id="44f5d-327">Correnti</span><span class="sxs-lookup"><span data-stu-id="44f5d-327">Current</span></span> | <span data-ttu-id="44f5d-328">Spesa di leasing</span><span class="sxs-lookup"><span data-stu-id="44f5d-328">Lease expense</span></span>       | <span data-ttu-id="44f5d-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-329">1,000.00</span></span> |          |
| <span data-ttu-id="44f5d-330">Ledger</span><span class="sxs-lookup"><span data-stu-id="44f5d-330">Ledger</span></span>       | <span data-ttu-id="44f5d-331">4</span><span class="sxs-lookup"><span data-stu-id="44f5d-331">4</span></span>              | <span data-ttu-id="44f5d-332">Correnti</span><span class="sxs-lookup"><span data-stu-id="44f5d-332">Current</span></span> | <span data-ttu-id="44f5d-333">Conto di compensazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-333">Clearing account</span></span>    |          | <span data-ttu-id="44f5d-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-334">1,000.00</span></span> |

<span data-ttu-id="44f5d-335">Un addetto alla contabilità fornitori utilizza la funzionalità standard di Dynamics 365 per creare una fattura per pagare il leasing al di fuori del leasing di cespiti.</span><span class="sxs-lookup"><span data-stu-id="44f5d-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="44f5d-336">Tuttavia, invece di selezionare **Spese di leasing** come conto in Dare, l'addetto alla contabilità fornitori seleziona un conto di compensazione per generare la seguente voce.</span><span class="sxs-lookup"><span data-stu-id="44f5d-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="44f5d-337">Processo contabilità fornitori - 31/1/2020 - JE 110</span><span class="sxs-lookup"><span data-stu-id="44f5d-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="44f5d-338">Tipo di account</span><span class="sxs-lookup"><span data-stu-id="44f5d-338">Account type</span></span> | <span data-ttu-id="44f5d-339">Numero conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-339">Account number</span></span> | <span data-ttu-id="44f5d-340">Livello</span><span class="sxs-lookup"><span data-stu-id="44f5d-340">Layer</span></span>   | <span data-ttu-id="44f5d-341">Descrizione conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-341">Account description</span></span> | <span data-ttu-id="44f5d-342">Dare</span><span class="sxs-lookup"><span data-stu-id="44f5d-342">Debit</span></span>    | <span data-ttu-id="44f5d-343">Avere</span><span class="sxs-lookup"><span data-stu-id="44f5d-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="44f5d-344">Ledger</span><span class="sxs-lookup"><span data-stu-id="44f5d-344">Ledger</span></span>       | <span data-ttu-id="44f5d-345">4</span><span class="sxs-lookup"><span data-stu-id="44f5d-345">4</span></span>              | <span data-ttu-id="44f5d-346">Correnti</span><span class="sxs-lookup"><span data-stu-id="44f5d-346">Current</span></span> | <span data-ttu-id="44f5d-347">Conto di compensazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-347">Clearing account</span></span>    | <span data-ttu-id="44f5d-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-348">1,000.00</span></span> |          |
| <span data-ttu-id="44f5d-349">Ledger</span><span class="sxs-lookup"><span data-stu-id="44f5d-349">Ledger</span></span>       | <span data-ttu-id="44f5d-350">2</span><span class="sxs-lookup"><span data-stu-id="44f5d-350">2</span></span>              | <span data-ttu-id="44f5d-351">Correnti</span><span class="sxs-lookup"><span data-stu-id="44f5d-351">Current</span></span> | <span data-ttu-id="44f5d-352">Commissione bancaria</span><span class="sxs-lookup"><span data-stu-id="44f5d-352">Bank fee</span></span>            | <span data-ttu-id="44f5d-353">3.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-353">3.00</span></span>     |          |
| <span data-ttu-id="44f5d-354">Ledger</span><span class="sxs-lookup"><span data-stu-id="44f5d-354">Ledger</span></span>       | <span data-ttu-id="44f5d-355">3</span><span class="sxs-lookup"><span data-stu-id="44f5d-355">3</span></span>              | <span data-ttu-id="44f5d-356">Correnti</span><span class="sxs-lookup"><span data-stu-id="44f5d-356">Current</span></span> | <span data-ttu-id="44f5d-357">Spesa IVA</span><span class="sxs-lookup"><span data-stu-id="44f5d-357">VAT expense</span></span>         | <span data-ttu-id="44f5d-358">5.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-358">5.00</span></span>     |          |
| <span data-ttu-id="44f5d-359">Fornitore</span><span class="sxs-lookup"><span data-stu-id="44f5d-359">Vendor</span></span>       | <span data-ttu-id="44f5d-360">5</span><span class="sxs-lookup"><span data-stu-id="44f5d-360">5</span></span>              | <span data-ttu-id="44f5d-361">Correnti</span><span class="sxs-lookup"><span data-stu-id="44f5d-361">Current</span></span> | <span data-ttu-id="44f5d-362">Contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="44f5d-362">Accounts payable</span></span>    |          | <span data-ttu-id="44f5d-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-363">1,008.00</span></span> |

<span data-ttu-id="44f5d-364">Quando la dichiarazione viene rilasciata al fornitore, segui il normale processo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="44f5d-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="44f5d-365">Durante questo processo, viene generata la seguente scrittura contabile.</span><span class="sxs-lookup"><span data-stu-id="44f5d-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="44f5d-366">Pagamento in contanti - 31/01/2020 - JE 120</span><span class="sxs-lookup"><span data-stu-id="44f5d-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="44f5d-367">Tipo di account</span><span class="sxs-lookup"><span data-stu-id="44f5d-367">Account type</span></span> | <span data-ttu-id="44f5d-368">Numero conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-368">Account number</span></span> | <span data-ttu-id="44f5d-369">Livello</span><span class="sxs-lookup"><span data-stu-id="44f5d-369">Layer</span></span>   | <span data-ttu-id="44f5d-370">Descrizione conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-370">Account description</span></span> | <span data-ttu-id="44f5d-371">Dare</span><span class="sxs-lookup"><span data-stu-id="44f5d-371">Debit</span></span>    | <span data-ttu-id="44f5d-372">Avere</span><span class="sxs-lookup"><span data-stu-id="44f5d-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="44f5d-373">Fornitore</span><span class="sxs-lookup"><span data-stu-id="44f5d-373">Vendor</span></span>       | <span data-ttu-id="44f5d-374">5</span><span class="sxs-lookup"><span data-stu-id="44f5d-374">5</span></span>              | <span data-ttu-id="44f5d-375">Correnti</span><span class="sxs-lookup"><span data-stu-id="44f5d-375">Current</span></span> | <span data-ttu-id="44f5d-376">Contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="44f5d-376">Accounts Payable</span></span>    | <span data-ttu-id="44f5d-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-377">1,008.00</span></span> |          |
| <span data-ttu-id="44f5d-378">Banca</span><span class="sxs-lookup"><span data-stu-id="44f5d-378">Bank</span></span>         | <span data-ttu-id="44f5d-379">9</span><span class="sxs-lookup"><span data-stu-id="44f5d-379">9</span></span>              | <span data-ttu-id="44f5d-380">Correnti</span><span class="sxs-lookup"><span data-stu-id="44f5d-380">Current</span></span> | <span data-ttu-id="44f5d-381">Cassa</span><span class="sxs-lookup"><span data-stu-id="44f5d-381">Cash</span></span>                |          | <span data-ttu-id="44f5d-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-382">1,008.00</span></span> |

<span data-ttu-id="44f5d-383">A questo punto, hai contabilizzato completamente questo leasing in base ai requisiti di reporting legali e puoi generare un bilancio di verifica utilizzando il livello corrente.</span><span class="sxs-lookup"><span data-stu-id="44f5d-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="44f5d-384">Il sistema restituisce un bilancio di verifica con le seguenti cifre.</span><span class="sxs-lookup"><span data-stu-id="44f5d-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="44f5d-385">Numero conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="44f5d-386">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44f5d-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="44f5d-387">Libro statutario (livello attuale)</span><span class="sxs-lookup"><span data-stu-id="44f5d-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="44f5d-388">Totale livello corrente</span><span class="sxs-lookup"><span data-stu-id="44f5d-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="44f5d-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="44f5d-389">JE-100</span></span></th>
<th><span data-ttu-id="44f5d-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="44f5d-390">JE-110</span></span></th>
<th><span data-ttu-id="44f5d-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="44f5d-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="44f5d-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="44f5d-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="44f5d-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="44f5d-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="44f5d-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="44f5d-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="44f5d-395">1</span><span class="sxs-lookup"><span data-stu-id="44f5d-395">1</span></span></td>
<td><span data-ttu-id="44f5d-396">Spesa di leasing</span><span class="sxs-lookup"><span data-stu-id="44f5d-396">Lease expense</span></span></td>
<td><span data-ttu-id="44f5d-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-399">2</span><span class="sxs-lookup"><span data-stu-id="44f5d-399">2</span></span></td>
<td><span data-ttu-id="44f5d-400">Commissione bancaria</span><span class="sxs-lookup"><span data-stu-id="44f5d-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-401">3.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-402">3.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-403">3</span><span class="sxs-lookup"><span data-stu-id="44f5d-403">3</span></span></td>
<td><span data-ttu-id="44f5d-404">Spesa IVA</span><span class="sxs-lookup"><span data-stu-id="44f5d-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-405">5.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-406">5.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-407">4</span><span class="sxs-lookup"><span data-stu-id="44f5d-407">4</span></span></td>
<td><span data-ttu-id="44f5d-408">Conto di compensazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-408">Clearing account</span></span></td>
<td><span data-ttu-id="44f5d-409">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-409">-1,000.00</span></span></td>
<td><span data-ttu-id="44f5d-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-411">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-412">5</span><span class="sxs-lookup"><span data-stu-id="44f5d-412">5</span></span></td>
<td><span data-ttu-id="44f5d-413">Contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="44f5d-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="44f5d-414">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-414">-1,008.00</span></span></td>
<td><span data-ttu-id="44f5d-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-415">1,008.00</span></span></td>
<td><span data-ttu-id="44f5d-416">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-417">6</span><span class="sxs-lookup"><span data-stu-id="44f5d-417">6</span></span></td>
<td><span data-ttu-id="44f5d-418">Asset ROU</span><span class="sxs-lookup"><span data-stu-id="44f5d-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-419">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-420">7</span><span class="sxs-lookup"><span data-stu-id="44f5d-420">7</span></span></td>
<td><span data-ttu-id="44f5d-421">Obbligo di leasing finanziario</span><span class="sxs-lookup"><span data-stu-id="44f5d-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-422">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-423">8</span><span class="sxs-lookup"><span data-stu-id="44f5d-423">8</span></span></td>
<td><span data-ttu-id="44f5d-424">Interessi passivi</span><span class="sxs-lookup"><span data-stu-id="44f5d-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-425">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-426">9</span><span class="sxs-lookup"><span data-stu-id="44f5d-426">9</span></span></td>
<td><span data-ttu-id="44f5d-427">Cassa</span><span class="sxs-lookup"><span data-stu-id="44f5d-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-428">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-428">-1,008.00</span></span></td>
<td><span data-ttu-id="44f5d-429">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-430">10</span><span class="sxs-lookup"><span data-stu-id="44f5d-430">10</span></span></td>
<td><span data-ttu-id="44f5d-431">Spesa di ammortamento</span><span class="sxs-lookup"><span data-stu-id="44f5d-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-432">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="44f5d-433">11</span><span class="sxs-lookup"><span data-stu-id="44f5d-433">11</span></span></td>
<td><span data-ttu-id="44f5d-434">Fondo di ammortamento</span><span class="sxs-lookup"><span data-stu-id="44f5d-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="44f5d-435">0,00</span><span class="sxs-lookup"><span data-stu-id="44f5d-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="44f5d-436">Se vuoi utilizzare i dati IFRS 16 per eseguire lo stesso bilancio di verifica, le registrazioni a giornale contabili legali devono essere stornate e le registrazioni contabili IFRS 16 devono essere registrate.</span><span class="sxs-lookup"><span data-stu-id="44f5d-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="44f5d-437">Per stornare le registrazioni a giornale legali, questo esempio include un libro di storno legale che ha la stessa configurazione del libro legale ma un profilo di registrazione opposto.</span><span class="sxs-lookup"><span data-stu-id="44f5d-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="44f5d-438">Ad esempio, il libro statutario ha *addebitato* un conto spese di leasing, ma il libro di storno *accredita* questo account.</span><span class="sxs-lookup"><span data-stu-id="44f5d-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="44f5d-439">Queste relazioni sono facilmente definibili nei conti di registrazione del leasing di asset nella pagina **Parametri del leasing di cespiti** (**Leasing di cespiti\> Imposta \> Parametri del leasing di cespiti**).</span><span class="sxs-lookup"><span data-stu-id="44f5d-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="44f5d-440">Quando lo stesso processo utilizzato per il libro legale viene utilizzato per il libro di storno, viene prodotta la seguente registrazione a giornale.</span><span class="sxs-lookup"><span data-stu-id="44f5d-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="44f5d-441">La differenza è che il libro di storno registra le registrazioni di storno dal libro statutario.</span><span class="sxs-lookup"><span data-stu-id="44f5d-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="44f5d-442">Le voci di storno vengono apportate anche al livello personalizzato.</span><span class="sxs-lookup"><span data-stu-id="44f5d-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="44f5d-443">Quando un bilancio di verifica viene eseguito al livello corrente, le registrazioni a giornale di storno non vengono incluse.</span><span class="sxs-lookup"><span data-stu-id="44f5d-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="44f5d-444">Canone di leasing - 31/01/2020 - JE 130</span><span class="sxs-lookup"><span data-stu-id="44f5d-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="44f5d-445">Tipo di account</span><span class="sxs-lookup"><span data-stu-id="44f5d-445">Account type</span></span> | <span data-ttu-id="44f5d-446">Numero conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-446">Account number</span></span> | <span data-ttu-id="44f5d-447">Livello</span><span class="sxs-lookup"><span data-stu-id="44f5d-447">Layer</span></span>  | <span data-ttu-id="44f5d-448">Descrizione conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-448">Account description</span></span> | <span data-ttu-id="44f5d-449">Dare</span><span class="sxs-lookup"><span data-stu-id="44f5d-449">Debit</span></span>    | <span data-ttu-id="44f5d-450">Avere</span><span class="sxs-lookup"><span data-stu-id="44f5d-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="44f5d-451">Ledger</span><span class="sxs-lookup"><span data-stu-id="44f5d-451">Ledger</span></span>       | <span data-ttu-id="44f5d-452">4</span><span class="sxs-lookup"><span data-stu-id="44f5d-452">4</span></span>              | <span data-ttu-id="44f5d-453">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-453">Custom</span></span> | <span data-ttu-id="44f5d-454">Conto di compensazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-454">Clearing account</span></span>    | <span data-ttu-id="44f5d-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-455">1,000.00</span></span> |          |
| <span data-ttu-id="44f5d-456">Ledger</span><span class="sxs-lookup"><span data-stu-id="44f5d-456">Ledger</span></span>       | <span data-ttu-id="44f5d-457">1</span><span class="sxs-lookup"><span data-stu-id="44f5d-457">1</span></span>              | <span data-ttu-id="44f5d-458">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-458">Custom</span></span> | <span data-ttu-id="44f5d-459">Spesa di leasing</span><span class="sxs-lookup"><span data-stu-id="44f5d-459">Lease expense</span></span>       |          | <span data-ttu-id="44f5d-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-460">1,000.00</span></span> |

<span data-ttu-id="44f5d-461">Dopo aver eliminato le registrazioni contabili statutarie, registrerai tutte le scritture contabili richieste dall'IFRS 16 nel libro IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="44f5d-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="44f5d-462">Queste voci includono la rilevazione iniziale dell'Asset ROU e della passività e la registrazione di interessi e ammortamenti.</span><span class="sxs-lookup"><span data-stu-id="44f5d-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="44f5d-463">Rilevazione iniziale – 1/1/2020 – JE 140</span><span class="sxs-lookup"><span data-stu-id="44f5d-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="44f5d-464">Tipo di account</span><span class="sxs-lookup"><span data-stu-id="44f5d-464">Account type</span></span> | <span data-ttu-id="44f5d-465">Numero conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-465">Account number</span></span> | <span data-ttu-id="44f5d-466">Livello</span><span class="sxs-lookup"><span data-stu-id="44f5d-466">Layer</span></span>  | <span data-ttu-id="44f5d-467">Descrizione conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-467">Account description</span></span>      | <span data-ttu-id="44f5d-468">Dare</span><span class="sxs-lookup"><span data-stu-id="44f5d-468">Debit</span></span>     | <span data-ttu-id="44f5d-469">Avere</span><span class="sxs-lookup"><span data-stu-id="44f5d-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="44f5d-470">Ledger</span><span class="sxs-lookup"><span data-stu-id="44f5d-470">Ledger</span></span>       | <span data-ttu-id="44f5d-471">6</span><span class="sxs-lookup"><span data-stu-id="44f5d-471">6</span></span>              | <span data-ttu-id="44f5d-472">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-472">Custom</span></span> | <span data-ttu-id="44f5d-473">Asset ROU</span><span class="sxs-lookup"><span data-stu-id="44f5d-473">ROU Asset</span></span>                | <span data-ttu-id="44f5d-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="44f5d-474">22,793.90</span></span> |           |
| <span data-ttu-id="44f5d-475">Ledger</span><span class="sxs-lookup"><span data-stu-id="44f5d-475">Ledger</span></span>       | <span data-ttu-id="44f5d-476">7</span><span class="sxs-lookup"><span data-stu-id="44f5d-476">7</span></span>              | <span data-ttu-id="44f5d-477">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-477">Custom</span></span> | <span data-ttu-id="44f5d-478">Obbligo di leasing finanziario</span><span class="sxs-lookup"><span data-stu-id="44f5d-478">Finance lease obligation</span></span> |           | <span data-ttu-id="44f5d-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="44f5d-479">22,793.90</span></span> |

<span data-ttu-id="44f5d-480">Il canone di leasing viene registrato come gli altri canoni di leasing.</span><span class="sxs-lookup"><span data-stu-id="44f5d-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="44f5d-481">Il motivo per utilizzare il conto di compensazione è garantire che il contante venga accreditato solo una volta.</span><span class="sxs-lookup"><span data-stu-id="44f5d-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="44f5d-482">Canone di leasing - 31/01/2020 - JE 150</span><span class="sxs-lookup"><span data-stu-id="44f5d-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="44f5d-483">Tipo di account</span><span class="sxs-lookup"><span data-stu-id="44f5d-483">Account type</span></span> | <span data-ttu-id="44f5d-484">Numero conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-484">Account number</span></span> | <span data-ttu-id="44f5d-485">Livello</span><span class="sxs-lookup"><span data-stu-id="44f5d-485">Layer</span></span>  | <span data-ttu-id="44f5d-486">Descrizione conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-486">Account description</span></span>      | <span data-ttu-id="44f5d-487">Dare</span><span class="sxs-lookup"><span data-stu-id="44f5d-487">Debit</span></span>    | <span data-ttu-id="44f5d-488">Avere</span><span class="sxs-lookup"><span data-stu-id="44f5d-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="44f5d-489">Ledger</span><span class="sxs-lookup"><span data-stu-id="44f5d-489">Ledger</span></span>       | <span data-ttu-id="44f5d-490">7</span><span class="sxs-lookup"><span data-stu-id="44f5d-490">7</span></span>              | <span data-ttu-id="44f5d-491">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-491">Custom</span></span> | <span data-ttu-id="44f5d-492">Obbligo di leasing finanziario</span><span class="sxs-lookup"><span data-stu-id="44f5d-492">Finance lease obligation</span></span> | <span data-ttu-id="44f5d-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-493">1,000.00</span></span> |          |
| <span data-ttu-id="44f5d-494">Ledger</span><span class="sxs-lookup"><span data-stu-id="44f5d-494">Ledger</span></span>       | <span data-ttu-id="44f5d-495">4</span><span class="sxs-lookup"><span data-stu-id="44f5d-495">4</span></span>              | <span data-ttu-id="44f5d-496">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-496">Custom</span></span> | <span data-ttu-id="44f5d-497">Conto di compensazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-497">Clearing account</span></span>         |          | <span data-ttu-id="44f5d-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-498">1,000.00</span></span> |

<span data-ttu-id="44f5d-499">La scrittura contabile degli interessi passivi viene generata dal piano di ammortamento della passività.</span><span class="sxs-lookup"><span data-stu-id="44f5d-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="44f5d-500">Interessi passivi – 31/1/2020 – JE 160</span><span class="sxs-lookup"><span data-stu-id="44f5d-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="44f5d-501">Tipo di account</span><span class="sxs-lookup"><span data-stu-id="44f5d-501">Account type</span></span> | <span data-ttu-id="44f5d-502">Numero conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-502">Account number</span></span> | <span data-ttu-id="44f5d-503">Livello</span><span class="sxs-lookup"><span data-stu-id="44f5d-503">Layer</span></span>  | <span data-ttu-id="44f5d-504">Descrizione conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-504">Account description</span></span>      | <span data-ttu-id="44f5d-505">Dare</span><span class="sxs-lookup"><span data-stu-id="44f5d-505">Debit</span></span> | <span data-ttu-id="44f5d-506">Avere</span><span class="sxs-lookup"><span data-stu-id="44f5d-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="44f5d-507">Ledger</span><span class="sxs-lookup"><span data-stu-id="44f5d-507">Ledger</span></span>       | <span data-ttu-id="44f5d-508">8</span><span class="sxs-lookup"><span data-stu-id="44f5d-508">8</span></span>              | <span data-ttu-id="44f5d-509">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-509">Custom</span></span> | <span data-ttu-id="44f5d-510">Interessi passivi</span><span class="sxs-lookup"><span data-stu-id="44f5d-510">Interest expense</span></span>         | <span data-ttu-id="44f5d-511">94.97</span><span class="sxs-lookup"><span data-stu-id="44f5d-511">94.97</span></span> |        |
| <span data-ttu-id="44f5d-512">Ledger</span><span class="sxs-lookup"><span data-stu-id="44f5d-512">Ledger</span></span>       | <span data-ttu-id="44f5d-513">7</span><span class="sxs-lookup"><span data-stu-id="44f5d-513">7</span></span>              | <span data-ttu-id="44f5d-514">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-514">Custom</span></span> | <span data-ttu-id="44f5d-515">Obbligo di leasing finanziario</span><span class="sxs-lookup"><span data-stu-id="44f5d-515">Finance lease obligation</span></span> |       | <span data-ttu-id="44f5d-516">94.97</span><span class="sxs-lookup"><span data-stu-id="44f5d-516">94.97</span></span>  |

<span data-ttu-id="44f5d-517">La scrittura contabile della spesa di ammortamento viene generata dal piano di ammortamento dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="44f5d-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="44f5d-518">Spesa di ammortamento – 31/1/2020 – JE 170</span><span class="sxs-lookup"><span data-stu-id="44f5d-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="44f5d-519">Tipo di account</span><span class="sxs-lookup"><span data-stu-id="44f5d-519">Account type</span></span> | <span data-ttu-id="44f5d-520">Numero conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-520">Account number</span></span> | <span data-ttu-id="44f5d-521">Livello</span><span class="sxs-lookup"><span data-stu-id="44f5d-521">Layer</span></span>  | <span data-ttu-id="44f5d-522">Descrizione conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-522">Account description</span></span>      | <span data-ttu-id="44f5d-523">Dare</span><span class="sxs-lookup"><span data-stu-id="44f5d-523">Debit</span></span>  | <span data-ttu-id="44f5d-524">Avere</span><span class="sxs-lookup"><span data-stu-id="44f5d-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="44f5d-525">Ledger</span><span class="sxs-lookup"><span data-stu-id="44f5d-525">Ledger</span></span>       | <span data-ttu-id="44f5d-526">10</span><span class="sxs-lookup"><span data-stu-id="44f5d-526">10</span></span>             | <span data-ttu-id="44f5d-527">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-527">Custom</span></span> | <span data-ttu-id="44f5d-528">Spesa di ammortamento</span><span class="sxs-lookup"><span data-stu-id="44f5d-528">Depreciation expense</span></span>     | <span data-ttu-id="44f5d-529">949.75</span><span class="sxs-lookup"><span data-stu-id="44f5d-529">949.75</span></span> |        |
| <span data-ttu-id="44f5d-530">Ledger</span><span class="sxs-lookup"><span data-stu-id="44f5d-530">Ledger</span></span>       | <span data-ttu-id="44f5d-531">11</span><span class="sxs-lookup"><span data-stu-id="44f5d-531">11</span></span>             | <span data-ttu-id="44f5d-532">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-532">Custom</span></span> | <span data-ttu-id="44f5d-533">Fondo di ammortamento</span><span class="sxs-lookup"><span data-stu-id="44f5d-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="44f5d-534">949.75</span><span class="sxs-lookup"><span data-stu-id="44f5d-534">949.75</span></span> |

<span data-ttu-id="44f5d-535">Dopo che tutte queste registrazioni contabili sono state create e registrate, vedrai i seguenti valori di "livello personalizzato 1".</span><span class="sxs-lookup"><span data-stu-id="44f5d-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="44f5d-536">Nota che l'ultima colonna include la commissione bancaria, la spesa per l'imposta sul valore aggiunto (IVA) e la riduzione del contante dal livello precedente, ma non include le registrazioni contabili del reporting statutario.</span><span class="sxs-lookup"><span data-stu-id="44f5d-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="44f5d-537">Pertanto, si ottengono vere funzionalità di doppio reporting.</span><span class="sxs-lookup"><span data-stu-id="44f5d-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="44f5d-538">A questo punto, la società deve solo eseguire il bilancio di verifica e combinare il livello corrente e il livello personalizzato per creare un bilancio di verifica IFRS.</span><span class="sxs-lookup"><span data-stu-id="44f5d-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="44f5d-539">Numero di conto</span><span class="sxs-lookup"><span data-stu-id="44f5d-539">Account No</span></span> | <span data-ttu-id="44f5d-540">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44f5d-540">Description</span></span>              | <span data-ttu-id="44f5d-541">Libro statutario\-Livello corrente\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="44f5d-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="44f5d-542">Libro statutario\-Livello corrente\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="44f5d-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="44f5d-543">Libro statutario\-Livello corrente\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="44f5d-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="44f5d-544">Livello corrente \- Totali</span><span class="sxs-lookup"><span data-stu-id="44f5d-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="44f5d-545">Libro di storno\-Livello personalizzato\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="44f5d-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="44f5d-546">Libro IFRS 16\-Livello personalizzato\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="44f5d-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="44f5d-547">Libro IFRS 16\-Livello personalizzato\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="44f5d-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="44f5d-548">Libro IFRS 16\-Livello personalizzato\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="44f5d-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="44f5d-549">Libro IFRS 16\-Livello personalizzato\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="44f5d-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="44f5d-550">Livello personalizzato \+ Livello corrente \- Totali</span><span class="sxs-lookup"><span data-stu-id="44f5d-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="44f5d-551">1</span><span class="sxs-lookup"><span data-stu-id="44f5d-551">1</span></span>          | <span data-ttu-id="44f5d-552">Spesa di leasing</span><span class="sxs-lookup"><span data-stu-id="44f5d-552">Lease expense</span></span>            | <span data-ttu-id="44f5d-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="44f5d-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-554">1,000\.00</span></span>               |   | <span data-ttu-id="44f5d-555">\-1.000</span><span class="sxs-lookup"><span data-stu-id="44f5d-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="44f5d-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-556">0\.00</span></span>                                   |
| <span data-ttu-id="44f5d-557">2</span><span class="sxs-lookup"><span data-stu-id="44f5d-557">2</span></span>          | <span data-ttu-id="44f5d-558">Commissione bancaria</span><span class="sxs-lookup"><span data-stu-id="44f5d-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="44f5d-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="44f5d-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="44f5d-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-561">3\.00</span></span>                                   |
| <span data-ttu-id="44f5d-562">3</span><span class="sxs-lookup"><span data-stu-id="44f5d-562">3</span></span>          | <span data-ttu-id="44f5d-563">Spesa IVA</span><span class="sxs-lookup"><span data-stu-id="44f5d-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="44f5d-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="44f5d-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="44f5d-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-566">5\.00</span></span>                                   |
| <span data-ttu-id="44f5d-567">4</span><span class="sxs-lookup"><span data-stu-id="44f5d-567">4</span></span>          | <span data-ttu-id="44f5d-568">Conto di compensazione</span><span class="sxs-lookup"><span data-stu-id="44f5d-568">Clearing account</span></span>         | <span data-ttu-id="44f5d-569">\-1.000\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="44f5d-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="44f5d-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-571">0\.00</span></span>                   |   | <span data-ttu-id="44f5d-572">1.000</span><span class="sxs-lookup"><span data-stu-id="44f5d-572">1,000</span></span>                                           |                                                | <span data-ttu-id="44f5d-573">\-1.000</span><span class="sxs-lookup"><span data-stu-id="44f5d-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="44f5d-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-574">0\.00</span></span>                                   |
| <span data-ttu-id="44f5d-575">5</span><span class="sxs-lookup"><span data-stu-id="44f5d-575">5</span></span>          | <span data-ttu-id="44f5d-576">Contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="44f5d-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="44f5d-577">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="44f5d-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-578">1,008\.00</span></span>                                         | <span data-ttu-id="44f5d-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="44f5d-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-580">0\.00</span></span>                                   |
| <span data-ttu-id="44f5d-581">6</span><span class="sxs-lookup"><span data-stu-id="44f5d-581">6</span></span>          | <span data-ttu-id="44f5d-582">Asset ROU</span><span class="sxs-lookup"><span data-stu-id="44f5d-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="44f5d-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="44f5d-584">22,794</span><span class="sxs-lookup"><span data-stu-id="44f5d-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="44f5d-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="44f5d-585">22,793\.90</span></span>                              |
| <span data-ttu-id="44f5d-586">7</span><span class="sxs-lookup"><span data-stu-id="44f5d-586">7</span></span>          | <span data-ttu-id="44f5d-587">Obbligo di leasing finanziario</span><span class="sxs-lookup"><span data-stu-id="44f5d-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="44f5d-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="44f5d-589">\-22.794</span><span class="sxs-lookup"><span data-stu-id="44f5d-589">\-22,794</span></span>                                       | <span data-ttu-id="44f5d-590">1.000</span><span class="sxs-lookup"><span data-stu-id="44f5d-590">1,000</span></span>                                          | <span data-ttu-id="44f5d-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="44f5d-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="44f5d-592">\-21,888\.87</span><span class="sxs-lookup"><span data-stu-id="44f5d-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="44f5d-593">8</span><span class="sxs-lookup"><span data-stu-id="44f5d-593">8</span></span>          | <span data-ttu-id="44f5d-594">Interessi passivi</span><span class="sxs-lookup"><span data-stu-id="44f5d-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="44f5d-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="44f5d-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="44f5d-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="44f5d-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="44f5d-597">94\.97</span></span>                                  |
| <span data-ttu-id="44f5d-598">9</span><span class="sxs-lookup"><span data-stu-id="44f5d-598">9</span></span>          | <span data-ttu-id="44f5d-599">Cassa</span><span class="sxs-lookup"><span data-stu-id="44f5d-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="44f5d-600">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="44f5d-601">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="44f5d-602">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="44f5d-603">10</span><span class="sxs-lookup"><span data-stu-id="44f5d-603">10</span></span>         | <span data-ttu-id="44f5d-604">Spesa di ammortamento</span><span class="sxs-lookup"><span data-stu-id="44f5d-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="44f5d-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="44f5d-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="44f5d-606">949\.75</span></span>                                        | <span data-ttu-id="44f5d-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="44f5d-607">949\.75</span></span>                                 |
| <span data-ttu-id="44f5d-608">11</span><span class="sxs-lookup"><span data-stu-id="44f5d-608">11</span></span>         | <span data-ttu-id="44f5d-609">Fondo di ammortamento</span><span class="sxs-lookup"><span data-stu-id="44f5d-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="44f5d-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="44f5d-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="44f5d-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="44f5d-611">\-949\.75</span></span>                                      | <span data-ttu-id="44f5d-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="44f5d-612">\-949\.75</span></span>                               |




[!INCLUDE[footer-include](../../includes/footer-banner.md)]