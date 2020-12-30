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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 96e1d4d460aef2f74422d5e4bd4fc68255466455
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444970"
---
# <a name="dual-reporting"></a><span data-ttu-id="2c643-103">Doppio reporting</span><span class="sxs-lookup"><span data-stu-id="2c643-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2c643-104">In questo argomento viene illustrato un esempio che mostra come soddisfare i requisiti sia per la creazione di report International Financial Reporting Standard (IFRS) sia per il reporting statutario nel leasing di cespiti.</span><span class="sxs-lookup"><span data-stu-id="2c643-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="2c643-105">La conoscenza dei livelli di registrazione in Microsoft Dynamics 365 Finance è obbligatoria e renderà l'esempio più facile da capire.</span><span class="sxs-lookup"><span data-stu-id="2c643-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="2c643-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c643-106">Example</span></span>

<span data-ttu-id="2c643-107">Il seguente esempio utilizza un leasing ai sensi del reporting statutario italiano utilizzando sia il metodo di cassa sia i metodi di reporting IFRS.</span><span class="sxs-lookup"><span data-stu-id="2c643-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="2c643-108">L'azienda deve stabilire tre libri contabili per tenere conto sia dei requisiti legali italiani che dei requisiti IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="2c643-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="2c643-109">Un libro è richiesto per l'IFRS 16, un libro è richiesto per i requisiti legali e un libro è richiesto per stornare automaticamente le registrazioni statutarie.</span><span class="sxs-lookup"><span data-stu-id="2c643-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="2c643-110">I libri sono configurati come mostrato nelle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="2c643-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="2c643-111">**Libro IFRS 16**</span><span class="sxs-lookup"><span data-stu-id="2c643-111">**IFRS 16 book**</span></span>

<span data-ttu-id="2c643-112">Il libro IFRS 16 è configurato in modo da essere conforme al principio contabile IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="2c643-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="2c643-113">Tutte le voci registrate in questo libro verranno registrate su un livello personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2c643-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="2c643-114">Nome</span><span class="sxs-lookup"><span data-stu-id="2c643-114">Name</span></span>                                    | <span data-ttu-id="2c643-115">descrizione</span><span class="sxs-lookup"><span data-stu-id="2c643-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="2c643-116">Tipo libro</span><span class="sxs-lookup"><span data-stu-id="2c643-116">Book type</span></span>                               | <span data-ttu-id="2c643-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="2c643-117">IFRS 16</span></span>        |
| <span data-ttu-id="2c643-118">Descrizione del libro</span><span class="sxs-lookup"><span data-stu-id="2c643-118">Book description</span></span>                        | <span data-ttu-id="2c643-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="2c643-119">IFRS 16</span></span>        |
| <span data-ttu-id="2c643-120">Livello di registrazione</span><span class="sxs-lookup"><span data-stu-id="2c643-120">Posting Layer</span></span>                           | <span data-ttu-id="2c643-121">Livello personalizzato 1</span><span class="sxs-lookup"><span data-stu-id="2c643-121">Custom layer 1</span></span> |
| <span data-ttu-id="2c643-122">Tipo di leasing</span><span class="sxs-lookup"><span data-stu-id="2c643-122">Lease Type</span></span>                              | <span data-ttu-id="2c643-123">Finance</span><span class="sxs-lookup"><span data-stu-id="2c643-123">Finance</span></span>        |
| <span data-ttu-id="2c643-124">Framework di contabilità</span><span class="sxs-lookup"><span data-stu-id="2c643-124">Accounting Framework</span></span>                    | <span data-ttu-id="2c643-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="2c643-125">IFRS 16</span></span>        |
| <span data-ttu-id="2c643-126">Configurazione termine del leasing/vita utile</span><span class="sxs-lookup"><span data-stu-id="2c643-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="2c643-127">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-127">0.00</span></span>           |
| <span data-ttu-id="2c643-128">Configurazione valore corrente/valore equo cespite</span><span class="sxs-lookup"><span data-stu-id="2c643-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="2c643-129">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-129">0.00</span></span>           |
| <span data-ttu-id="2c643-130">Soglia a breve termine</span><span class="sxs-lookup"><span data-stu-id="2c643-130">Short-term threshold</span></span>                    | <span data-ttu-id="2c643-131">12</span><span class="sxs-lookup"><span data-stu-id="2c643-131">12</span></span>             |
| <span data-ttu-id="2c643-132">Soglia valore basso</span><span class="sxs-lookup"><span data-stu-id="2c643-132">Low Value Threshold</span></span>                     | <span data-ttu-id="2c643-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="2c643-133">5,000.00</span></span>       |
| <span data-ttu-id="2c643-134">Pagamento al fornitore</span><span class="sxs-lookup"><span data-stu-id="2c643-134">Pay to Vendor</span></span>                           | <span data-ttu-id="2c643-135">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2c643-135">No</span></span>             |

<span data-ttu-id="2c643-136">**Libro statutario**</span><span class="sxs-lookup"><span data-stu-id="2c643-136">**Statutory book**</span></span>

<span data-ttu-id="2c643-137">Il libro statutario è un libro di cassa in cui la società contabilizzerà le spese di leasing come l'importo in contanti che viene pagato ogni mese per l'affitto.</span><span class="sxs-lookup"><span data-stu-id="2c643-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="2c643-138">Questo libro non produrrà un Asset Right of use un'obbligazione sul leasing.</span><span class="sxs-lookup"><span data-stu-id="2c643-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="2c643-139">Nome</span><span class="sxs-lookup"><span data-stu-id="2c643-139">Name</span></span>                                    | <span data-ttu-id="2c643-140">descrizione</span><span class="sxs-lookup"><span data-stu-id="2c643-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="2c643-141">Tipo libro</span><span class="sxs-lookup"><span data-stu-id="2c643-141">Book type</span></span>                               | <span data-ttu-id="2c643-142">Statutario</span><span class="sxs-lookup"><span data-stu-id="2c643-142">Statutory</span></span>   |
| <span data-ttu-id="2c643-143">Descrizione del libro</span><span class="sxs-lookup"><span data-stu-id="2c643-143">Book description</span></span>                        | <span data-ttu-id="2c643-144">GAAP locale</span><span class="sxs-lookup"><span data-stu-id="2c643-144">Local GAAP</span></span>  |
| <span data-ttu-id="2c643-145">Livello di registrazione</span><span class="sxs-lookup"><span data-stu-id="2c643-145">Posting Layer</span></span>                           | <span data-ttu-id="2c643-146">Correnti</span><span class="sxs-lookup"><span data-stu-id="2c643-146">Current</span></span>     |
| <span data-ttu-id="2c643-147">Tipo di leasing</span><span class="sxs-lookup"><span data-stu-id="2c643-147">Lease Type</span></span>                              | <span data-ttu-id="2c643-148">Automatica</span><span class="sxs-lookup"><span data-stu-id="2c643-148">Automatic</span></span>   |
| <span data-ttu-id="2c643-149">Framework di contabilità</span><span class="sxs-lookup"><span data-stu-id="2c643-149">Accounting Framework</span></span>                    | <span data-ttu-id="2c643-150">Cassa</span><span class="sxs-lookup"><span data-stu-id="2c643-150">Cash basis</span></span>  |
| <span data-ttu-id="2c643-151">Configurazione termine del leasing/vita utile</span><span class="sxs-lookup"><span data-stu-id="2c643-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="2c643-152">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-152">0.00</span></span>        |
| <span data-ttu-id="2c643-153">Configurazione valore corrente/valore equo cespite</span><span class="sxs-lookup"><span data-stu-id="2c643-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="2c643-154">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-154">0.00</span></span>        |
| <span data-ttu-id="2c643-155">Soglia a breve termine</span><span class="sxs-lookup"><span data-stu-id="2c643-155">Short-term threshold</span></span>                    | <span data-ttu-id="2c643-156">0</span><span class="sxs-lookup"><span data-stu-id="2c643-156">0</span></span>           |
| <span data-ttu-id="2c643-157">Soglia valore basso</span><span class="sxs-lookup"><span data-stu-id="2c643-157">Low Value Threshold</span></span>                     | <span data-ttu-id="2c643-158">0</span><span class="sxs-lookup"><span data-stu-id="2c643-158">0</span></span>           |
| <span data-ttu-id="2c643-159">Pagamento al fornitore</span><span class="sxs-lookup"><span data-stu-id="2c643-159">Pay to Vendor</span></span>                           | <span data-ttu-id="2c643-160">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2c643-160">No</span></span>          |

<span data-ttu-id="2c643-161">**Libro storno statutario**</span><span class="sxs-lookup"><span data-stu-id="2c643-161">**Statutory reversal book**</span></span>

<span data-ttu-id="2c643-162">Il libro di storno statutario è configurato allo stesso modo del libro statutario.</span><span class="sxs-lookup"><span data-stu-id="2c643-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="2c643-163">Nome</span><span class="sxs-lookup"><span data-stu-id="2c643-163">Name</span></span>                                    | <span data-ttu-id="2c643-164">descrizione</span><span class="sxs-lookup"><span data-stu-id="2c643-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="2c643-165">Tipo libro</span><span class="sxs-lookup"><span data-stu-id="2c643-165">Book type</span></span>                               | <span data-ttu-id="2c643-166">Statutario - Storno</span><span class="sxs-lookup"><span data-stu-id="2c643-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="2c643-167">Descrizione del libro</span><span class="sxs-lookup"><span data-stu-id="2c643-167">Book description</span></span>                        | <span data-ttu-id="2c643-168">Libro per stornare libro statutario</span><span class="sxs-lookup"><span data-stu-id="2c643-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="2c643-169">Livello di registrazione</span><span class="sxs-lookup"><span data-stu-id="2c643-169">Posting Layer</span></span>                           | <span data-ttu-id="2c643-170">Livello personalizzato 1</span><span class="sxs-lookup"><span data-stu-id="2c643-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="2c643-171">Tipo di leasing</span><span class="sxs-lookup"><span data-stu-id="2c643-171">Lease Type</span></span>                              | <span data-ttu-id="2c643-172">Automatica</span><span class="sxs-lookup"><span data-stu-id="2c643-172">Automatic</span></span>                      |
| <span data-ttu-id="2c643-173">Framework di contabilità</span><span class="sxs-lookup"><span data-stu-id="2c643-173">Accounting Framework</span></span>                    | <span data-ttu-id="2c643-174">Cassa</span><span class="sxs-lookup"><span data-stu-id="2c643-174">Cash basis</span></span>                     |
| <span data-ttu-id="2c643-175">Configurazione termine del leasing/vita utile</span><span class="sxs-lookup"><span data-stu-id="2c643-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="2c643-176">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-176">0.00</span></span>                           |
| <span data-ttu-id="2c643-177">Configurazione valore corrente/valore equo cespite</span><span class="sxs-lookup"><span data-stu-id="2c643-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="2c643-178">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-178">0.00</span></span>                           |
| <span data-ttu-id="2c643-179">Soglia a breve termine</span><span class="sxs-lookup"><span data-stu-id="2c643-179">Short-term threshold</span></span>                    | <span data-ttu-id="2c643-180">0</span><span class="sxs-lookup"><span data-stu-id="2c643-180">0</span></span>                              |
| <span data-ttu-id="2c643-181">Soglia valore basso</span><span class="sxs-lookup"><span data-stu-id="2c643-181">Low Value Threshold</span></span>                     | <span data-ttu-id="2c643-182">0</span><span class="sxs-lookup"><span data-stu-id="2c643-182">0</span></span>                              |
| <span data-ttu-id="2c643-183">Pagamento al fornitore</span><span class="sxs-lookup"><span data-stu-id="2c643-183">Pay to Vendor</span></span>                           | <span data-ttu-id="2c643-184">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2c643-184">No</span></span>                             |

<span data-ttu-id="2c643-185">Per questo esempio, è stato creato un contratto di leasing con le seguenti impostazioni nelle schede **Generale** e **Righe scadenzario pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="2c643-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="2c643-186">**Scheda Generale**</span><span class="sxs-lookup"><span data-stu-id="2c643-186">**General tab**</span></span>

| <span data-ttu-id="2c643-187">Campo</span><span class="sxs-lookup"><span data-stu-id="2c643-187">Field</span></span>                      | <span data-ttu-id="2c643-188">Valore</span><span class="sxs-lookup"><span data-stu-id="2c643-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="2c643-189">Tasso incrementale di prestito</span><span class="sxs-lookup"><span data-stu-id="2c643-189">Incremental borrowing rate</span></span> | <span data-ttu-id="2c643-190">5%</span><span class="sxs-lookup"><span data-stu-id="2c643-190">5%</span></span>               |
| <span data-ttu-id="2c643-191">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="2c643-191">Commencement date</span></span>          | <span data-ttu-id="2c643-192">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="2c643-192">1/1/2020</span></span>         |
| <span data-ttu-id="2c643-193">Gruppo di leasing</span><span class="sxs-lookup"><span data-stu-id="2c643-193">Lease group</span></span>                | <span data-ttu-id="2c643-194">Edifici</span><span class="sxs-lookup"><span data-stu-id="2c643-194">Buildings</span></span>        |
| <span data-ttu-id="2c643-195">Fornitore</span><span class="sxs-lookup"><span data-stu-id="2c643-195">Vendor</span></span>                     | <span data-ttu-id="2c643-196">1001</span><span class="sxs-lookup"><span data-stu-id="2c643-196">1001</span></span>             |
| <span data-ttu-id="2c643-197">Valore equo del cespite</span><span class="sxs-lookup"><span data-stu-id="2c643-197">Fair value of the asset</span></span>    | <span data-ttu-id="2c643-198">245,000</span><span class="sxs-lookup"><span data-stu-id="2c643-198">245,000</span></span>          |
| <span data-ttu-id="2c643-199">Vita utile del cespite</span><span class="sxs-lookup"><span data-stu-id="2c643-199">Asset useful life</span></span>          | <span data-ttu-id="2c643-200">120</span><span class="sxs-lookup"><span data-stu-id="2c643-200">120</span></span>              |
| <span data-ttu-id="2c643-201">Tipo di rendita finanziaria</span><span class="sxs-lookup"><span data-stu-id="2c643-201">Annuity type</span></span>               | <span data-ttu-id="2c643-202">Rendita finanziaria posticipata</span><span class="sxs-lookup"><span data-stu-id="2c643-202">Ordinary annuity</span></span> |
| <span data-ttu-id="2c643-203">Intervallo interessi composti</span><span class="sxs-lookup"><span data-stu-id="2c643-203">Compounding interval</span></span>       | <span data-ttu-id="2c643-204">Ogni mese</span><span class="sxs-lookup"><span data-stu-id="2c643-204">Monthly</span></span>          |

<span data-ttu-id="2c643-205">**Scheda Righe scadenzario pagamenti**</span><span class="sxs-lookup"><span data-stu-id="2c643-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="2c643-206">Campo</span><span class="sxs-lookup"><span data-stu-id="2c643-206">Field</span></span>             | <span data-ttu-id="2c643-207">Valore</span><span class="sxs-lookup"><span data-stu-id="2c643-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="2c643-208">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="2c643-208">Start date</span></span>        | <span data-ttu-id="2c643-209">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="2c643-209">1/1/2020</span></span>   |
| <span data-ttu-id="2c643-210">Intervallo periodico</span><span class="sxs-lookup"><span data-stu-id="2c643-210">Period interval</span></span>   | <span data-ttu-id="2c643-211">Mesi</span><span class="sxs-lookup"><span data-stu-id="2c643-211">Months</span></span>     |
| <span data-ttu-id="2c643-212">Periodi</span><span class="sxs-lookup"><span data-stu-id="2c643-212">Periods</span></span>           | <span data-ttu-id="2c643-213">24</span><span class="sxs-lookup"><span data-stu-id="2c643-213">24</span></span>         |
| <span data-ttu-id="2c643-214">Data di fine</span><span class="sxs-lookup"><span data-stu-id="2c643-214">End date</span></span>          | <span data-ttu-id="2c643-215">31/12/2020</span><span class="sxs-lookup"><span data-stu-id="2c643-215">12/31/2020</span></span> |
| <span data-ttu-id="2c643-216">Frequenza pagamenti</span><span class="sxs-lookup"><span data-stu-id="2c643-216">Payment frequency</span></span> | <span data-ttu-id="2c643-217">Ogni mese</span><span class="sxs-lookup"><span data-stu-id="2c643-217">Monthly</span></span>    |
| <span data-ttu-id="2c643-218">Importo pagamento</span><span class="sxs-lookup"><span data-stu-id="2c643-218">Payment amount</span></span>    | <span data-ttu-id="2c643-219">1.000</span><span class="sxs-lookup"><span data-stu-id="2c643-219">1,000</span></span>      |

<span data-ttu-id="2c643-220">Per contabilizzare questo leasing in due framework, utilizza un livello di registrazione corrente e un livello di registrazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2c643-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="2c643-221">La tabella seguente mostra un esempio di ogni registrazione a giornale il cui obbligo era di rappresentare equamente i dati finanziari in ogni standard di reporting.</span><span class="sxs-lookup"><span data-stu-id="2c643-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="2c643-222">Successivamente viene fornita una descrizione dettagliata di ciascuna registrazione a giornale per il primo mese del contratto di leasing.</span><span class="sxs-lookup"><span data-stu-id="2c643-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="2c643-223">Numero conto</span><span class="sxs-lookup"><span data-stu-id="2c643-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="2c643-224">descrizione</span><span class="sxs-lookup"><span data-stu-id="2c643-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="2c643-225">Libro statutario (livello attuale)</span><span class="sxs-lookup"><span data-stu-id="2c643-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="2c643-226">Totale livello corrente</span><span class="sxs-lookup"><span data-stu-id="2c643-226">Current layer total</span></span></th>
<th><span data-ttu-id="2c643-227">Libro di storno (livello personalizzato)</span><span class="sxs-lookup"><span data-stu-id="2c643-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="2c643-228">Libro IFRS 16 (livello personalizzato)</span><span class="sxs-lookup"><span data-stu-id="2c643-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="2c643-229">Totale livello corrente + livello personalizzato</span><span class="sxs-lookup"><span data-stu-id="2c643-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="2c643-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="2c643-230">JE-100</span></span></th>
<th><span data-ttu-id="2c643-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="2c643-231">JE-110</span></span></th>
<th><span data-ttu-id="2c643-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="2c643-232">JE-120</span></span></th>
<th><span data-ttu-id="2c643-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="2c643-233">JE-130</span></span></th>
<th><span data-ttu-id="2c643-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="2c643-234">JE-140</span></span></th>
<th><span data-ttu-id="2c643-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="2c643-235">JE-150</span></span></th>
<th><span data-ttu-id="2c643-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="2c643-236">JE-160</span></span></th>
<th><span data-ttu-id="2c643-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="2c643-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="2c643-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="2c643-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="2c643-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="2c643-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="2c643-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="2c643-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="2c643-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="2c643-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="2c643-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="2c643-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="2c643-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="2c643-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="2c643-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="2c643-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="2c643-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="2c643-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2c643-246">1</span><span class="sxs-lookup"><span data-stu-id="2c643-246">1</span></span></td>
<td><span data-ttu-id="2c643-247">Spesa di leasing</span><span class="sxs-lookup"><span data-stu-id="2c643-247">Lease expense</span></span></td>
<td><span data-ttu-id="2c643-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="2c643-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="2c643-249">1,000.00</span></span></td>
<td><span data-ttu-id="2c643-250">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="2c643-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-251">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-252">2</span><span class="sxs-lookup"><span data-stu-id="2c643-252">2</span></span></td>
<td><span data-ttu-id="2c643-253">Commissione bancaria</span><span class="sxs-lookup"><span data-stu-id="2c643-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-254">3.00</span><span class="sxs-lookup"><span data-stu-id="2c643-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-255">3.00</span><span class="sxs-lookup"><span data-stu-id="2c643-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-256">3.00</span><span class="sxs-lookup"><span data-stu-id="2c643-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-257">3</span><span class="sxs-lookup"><span data-stu-id="2c643-257">3</span></span></td>
<td><span data-ttu-id="2c643-258">Spesa IVA</span><span class="sxs-lookup"><span data-stu-id="2c643-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-259">5.00</span><span class="sxs-lookup"><span data-stu-id="2c643-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-260">5.00</span><span class="sxs-lookup"><span data-stu-id="2c643-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-261">5.00</span><span class="sxs-lookup"><span data-stu-id="2c643-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-262">4</span><span class="sxs-lookup"><span data-stu-id="2c643-262">4</span></span></td>
<td><span data-ttu-id="2c643-263">Conto di compensazione</span><span class="sxs-lookup"><span data-stu-id="2c643-263">Clearing account</span></span></td>
<td><span data-ttu-id="2c643-264">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="2c643-264">-1,000.00</span></span></td>
<td><span data-ttu-id="2c643-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="2c643-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-266">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-266">0.00</span></span></td>
<td><span data-ttu-id="2c643-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="2c643-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-268">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="2c643-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-269">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-270">5</span><span class="sxs-lookup"><span data-stu-id="2c643-270">5</span></span></td>
<td><span data-ttu-id="2c643-271">Contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="2c643-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-272">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="2c643-272">-1,008.00</span></span></td>
<td><span data-ttu-id="2c643-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="2c643-273">1,008.00</span></span></td>
<td><span data-ttu-id="2c643-274">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-275">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-276">6</span><span class="sxs-lookup"><span data-stu-id="2c643-276">6</span></span></td>
<td><span data-ttu-id="2c643-277">Asset ROU</span><span class="sxs-lookup"><span data-stu-id="2c643-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-278">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="2c643-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="2c643-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-281">7</span><span class="sxs-lookup"><span data-stu-id="2c643-281">7</span></span></td>
<td><span data-ttu-id="2c643-282">Obbligo di leasing finanziario</span><span class="sxs-lookup"><span data-stu-id="2c643-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-283">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-284">-22.794,00</span><span class="sxs-lookup"><span data-stu-id="2c643-284">-22,794.00</span></span></td>
<td><span data-ttu-id="2c643-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="2c643-285">1,000.00</span></span></td>
<td><span data-ttu-id="2c643-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="2c643-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-287">-21.888,87</span><span class="sxs-lookup"><span data-stu-id="2c643-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-288">8</span><span class="sxs-lookup"><span data-stu-id="2c643-288">8</span></span></td>
<td><span data-ttu-id="2c643-289">Interessi passivi</span><span class="sxs-lookup"><span data-stu-id="2c643-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-290">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-291">94.97</span><span class="sxs-lookup"><span data-stu-id="2c643-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-292">94.97</span><span class="sxs-lookup"><span data-stu-id="2c643-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-293">9</span><span class="sxs-lookup"><span data-stu-id="2c643-293">9</span></span></td>
<td><span data-ttu-id="2c643-294">Cassa</span><span class="sxs-lookup"><span data-stu-id="2c643-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-295">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="2c643-295">-1,008.00</span></span></td>
<td><span data-ttu-id="2c643-296">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="2c643-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-297">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="2c643-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-298">10</span><span class="sxs-lookup"><span data-stu-id="2c643-298">10</span></span></td>
<td><span data-ttu-id="2c643-299">Spesa di ammortamento</span><span class="sxs-lookup"><span data-stu-id="2c643-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-300">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-301">949.75</span><span class="sxs-lookup"><span data-stu-id="2c643-301">949.75</span></span></td>
<td><span data-ttu-id="2c643-302">949.75</span><span class="sxs-lookup"><span data-stu-id="2c643-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-303">11</span><span class="sxs-lookup"><span data-stu-id="2c643-303">11</span></span></td>
<td><span data-ttu-id="2c643-304">Fondo di ammortamento</span><span class="sxs-lookup"><span data-stu-id="2c643-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-305">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="2c643-306">-949.75</span></span></td>
<td><span data-ttu-id="2c643-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="2c643-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2c643-308">Come mostra la tabella precedente, sono obbligatori tre libri per la rendicontazione ai sensi sia del reporting statutario che del reporting IFRS.</span><span class="sxs-lookup"><span data-stu-id="2c643-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="2c643-309">Il libro legale registra il canone di leasing secondo le regole per la contabilità di cassa nel livello corrente.</span><span class="sxs-lookup"><span data-stu-id="2c643-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="2c643-310">Il libro di storno statutario storna le registrazioni di scrittura contabile.</span><span class="sxs-lookup"><span data-stu-id="2c643-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="2c643-311">Il libro IFRS 16 crea le registrazioni di scrittura contabile obbligatorie ai sensi di IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="2c643-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="2c643-312">Devi inserire un leasing solo una volta.</span><span class="sxs-lookup"><span data-stu-id="2c643-312">You must enter a lease only one time.</span></span> <span data-ttu-id="2c643-313">È quindi possibile aprire la pagina **Libri** per vedere tutti i libri associati al leasing.</span><span class="sxs-lookup"><span data-stu-id="2c643-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="2c643-314">Quando crei i libri, tutti e tre devono essere associati allo stesso record di leasing.</span><span class="sxs-lookup"><span data-stu-id="2c643-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="2c643-315">La prima registrazione a giornale registra le spese di leasing nel libro statutario.</span><span class="sxs-lookup"><span data-stu-id="2c643-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="2c643-316">È possibile creare i pagamenti in batch o selezionando lo scadenzario pagamenti nel libro statutario.</span><span class="sxs-lookup"><span data-stu-id="2c643-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="2c643-317">Per questo esempio, la seguente scrittura contabile viene prodotta per il libro legale dallo scadenzario pagamenti.</span><span class="sxs-lookup"><span data-stu-id="2c643-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="2c643-318">Canone di leasing - 31/01/2020 - JE 100</span><span class="sxs-lookup"><span data-stu-id="2c643-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="2c643-319">Tipo di account</span><span class="sxs-lookup"><span data-stu-id="2c643-319">Account type</span></span> | <span data-ttu-id="2c643-320">Numero conto</span><span class="sxs-lookup"><span data-stu-id="2c643-320">Account number</span></span> | <span data-ttu-id="2c643-321">Livello</span><span class="sxs-lookup"><span data-stu-id="2c643-321">Layer</span></span>   | <span data-ttu-id="2c643-322">Descrizione conto</span><span class="sxs-lookup"><span data-stu-id="2c643-322">Account description</span></span> | <span data-ttu-id="2c643-323">Dare</span><span class="sxs-lookup"><span data-stu-id="2c643-323">Debit</span></span>    | <span data-ttu-id="2c643-324">Avere</span><span class="sxs-lookup"><span data-stu-id="2c643-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="2c643-325">Ledger</span><span class="sxs-lookup"><span data-stu-id="2c643-325">Ledger</span></span>       | <span data-ttu-id="2c643-326">1</span><span class="sxs-lookup"><span data-stu-id="2c643-326">1</span></span>              | <span data-ttu-id="2c643-327">Correnti</span><span class="sxs-lookup"><span data-stu-id="2c643-327">Current</span></span> | <span data-ttu-id="2c643-328">Spesa di leasing</span><span class="sxs-lookup"><span data-stu-id="2c643-328">Lease expense</span></span>       | <span data-ttu-id="2c643-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="2c643-329">1,000.00</span></span> |          |
| <span data-ttu-id="2c643-330">Ledger</span><span class="sxs-lookup"><span data-stu-id="2c643-330">Ledger</span></span>       | <span data-ttu-id="2c643-331">4</span><span class="sxs-lookup"><span data-stu-id="2c643-331">4</span></span>              | <span data-ttu-id="2c643-332">Correnti</span><span class="sxs-lookup"><span data-stu-id="2c643-332">Current</span></span> | <span data-ttu-id="2c643-333">Conto di compensazione</span><span class="sxs-lookup"><span data-stu-id="2c643-333">Clearing account</span></span>    |          | <span data-ttu-id="2c643-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="2c643-334">1,000.00</span></span> |

<span data-ttu-id="2c643-335">Un addetto alla contabilità fornitori utilizza la funzionalità standard di Dynamics 365 per creare una fattura per pagare il leasing al di fuori del leasing di cespiti.</span><span class="sxs-lookup"><span data-stu-id="2c643-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="2c643-336">Tuttavia, invece di selezionare **Spese di leasing** come conto in Dare, l'addetto alla contabilità fornitori seleziona un conto di compensazione per generare la seguente voce.</span><span class="sxs-lookup"><span data-stu-id="2c643-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="2c643-337">Processo contabilità fornitori - 31/1/2020 - JE 110</span><span class="sxs-lookup"><span data-stu-id="2c643-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="2c643-338">Tipo di account</span><span class="sxs-lookup"><span data-stu-id="2c643-338">Account type</span></span> | <span data-ttu-id="2c643-339">Numero conto</span><span class="sxs-lookup"><span data-stu-id="2c643-339">Account number</span></span> | <span data-ttu-id="2c643-340">Livello</span><span class="sxs-lookup"><span data-stu-id="2c643-340">Layer</span></span>   | <span data-ttu-id="2c643-341">Descrizione conto</span><span class="sxs-lookup"><span data-stu-id="2c643-341">Account description</span></span> | <span data-ttu-id="2c643-342">Dare</span><span class="sxs-lookup"><span data-stu-id="2c643-342">Debit</span></span>    | <span data-ttu-id="2c643-343">Avere</span><span class="sxs-lookup"><span data-stu-id="2c643-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="2c643-344">Ledger</span><span class="sxs-lookup"><span data-stu-id="2c643-344">Ledger</span></span>       | <span data-ttu-id="2c643-345">4</span><span class="sxs-lookup"><span data-stu-id="2c643-345">4</span></span>              | <span data-ttu-id="2c643-346">Correnti</span><span class="sxs-lookup"><span data-stu-id="2c643-346">Current</span></span> | <span data-ttu-id="2c643-347">Conto di compensazione</span><span class="sxs-lookup"><span data-stu-id="2c643-347">Clearing account</span></span>    | <span data-ttu-id="2c643-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="2c643-348">1,000.00</span></span> |          |
| <span data-ttu-id="2c643-349">Ledger</span><span class="sxs-lookup"><span data-stu-id="2c643-349">Ledger</span></span>       | <span data-ttu-id="2c643-350">2</span><span class="sxs-lookup"><span data-stu-id="2c643-350">2</span></span>              | <span data-ttu-id="2c643-351">Correnti</span><span class="sxs-lookup"><span data-stu-id="2c643-351">Current</span></span> | <span data-ttu-id="2c643-352">Commissione bancaria</span><span class="sxs-lookup"><span data-stu-id="2c643-352">Bank fee</span></span>            | <span data-ttu-id="2c643-353">3.00</span><span class="sxs-lookup"><span data-stu-id="2c643-353">3.00</span></span>     |          |
| <span data-ttu-id="2c643-354">Ledger</span><span class="sxs-lookup"><span data-stu-id="2c643-354">Ledger</span></span>       | <span data-ttu-id="2c643-355">3</span><span class="sxs-lookup"><span data-stu-id="2c643-355">3</span></span>              | <span data-ttu-id="2c643-356">Correnti</span><span class="sxs-lookup"><span data-stu-id="2c643-356">Current</span></span> | <span data-ttu-id="2c643-357">Spesa IVA</span><span class="sxs-lookup"><span data-stu-id="2c643-357">VAT expense</span></span>         | <span data-ttu-id="2c643-358">5.00</span><span class="sxs-lookup"><span data-stu-id="2c643-358">5.00</span></span>     |          |
| <span data-ttu-id="2c643-359">Fornitore</span><span class="sxs-lookup"><span data-stu-id="2c643-359">Vendor</span></span>       | <span data-ttu-id="2c643-360">5</span><span class="sxs-lookup"><span data-stu-id="2c643-360">5</span></span>              | <span data-ttu-id="2c643-361">Correnti</span><span class="sxs-lookup"><span data-stu-id="2c643-361">Current</span></span> | <span data-ttu-id="2c643-362">Contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="2c643-362">Accounts payable</span></span>    |          | <span data-ttu-id="2c643-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="2c643-363">1,008.00</span></span> |

<span data-ttu-id="2c643-364">Quando la dichiarazione viene rilasciata al fornitore, segui il normale processo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="2c643-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="2c643-365">Durante questo processo, viene generata la seguente scrittura contabile.</span><span class="sxs-lookup"><span data-stu-id="2c643-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="2c643-366">Pagamento in contanti - 31/01/2020 - JE 120</span><span class="sxs-lookup"><span data-stu-id="2c643-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="2c643-367">Tipo di account</span><span class="sxs-lookup"><span data-stu-id="2c643-367">Account type</span></span> | <span data-ttu-id="2c643-368">Numero conto</span><span class="sxs-lookup"><span data-stu-id="2c643-368">Account number</span></span> | <span data-ttu-id="2c643-369">Livello</span><span class="sxs-lookup"><span data-stu-id="2c643-369">Layer</span></span>   | <span data-ttu-id="2c643-370">Descrizione conto</span><span class="sxs-lookup"><span data-stu-id="2c643-370">Account description</span></span> | <span data-ttu-id="2c643-371">Dare</span><span class="sxs-lookup"><span data-stu-id="2c643-371">Debit</span></span>    | <span data-ttu-id="2c643-372">Avere</span><span class="sxs-lookup"><span data-stu-id="2c643-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="2c643-373">Fornitore</span><span class="sxs-lookup"><span data-stu-id="2c643-373">Vendor</span></span>       | <span data-ttu-id="2c643-374">5</span><span class="sxs-lookup"><span data-stu-id="2c643-374">5</span></span>              | <span data-ttu-id="2c643-375">Correnti</span><span class="sxs-lookup"><span data-stu-id="2c643-375">Current</span></span> | <span data-ttu-id="2c643-376">Contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="2c643-376">Accounts Payable</span></span>    | <span data-ttu-id="2c643-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="2c643-377">1,008.00</span></span> |          |
| <span data-ttu-id="2c643-378">Banca</span><span class="sxs-lookup"><span data-stu-id="2c643-378">Bank</span></span>         | <span data-ttu-id="2c643-379">9</span><span class="sxs-lookup"><span data-stu-id="2c643-379">9</span></span>              | <span data-ttu-id="2c643-380">Correnti</span><span class="sxs-lookup"><span data-stu-id="2c643-380">Current</span></span> | <span data-ttu-id="2c643-381">Cassa</span><span class="sxs-lookup"><span data-stu-id="2c643-381">Cash</span></span>                |          | <span data-ttu-id="2c643-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="2c643-382">1,008.00</span></span> |

<span data-ttu-id="2c643-383">A questo punto, hai contabilizzato completamente questo leasing in base ai requisiti di reporting legali e puoi generare un bilancio di verifica utilizzando il livello corrente.</span><span class="sxs-lookup"><span data-stu-id="2c643-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="2c643-384">Il sistema restituisce un bilancio di verifica con le seguenti cifre.</span><span class="sxs-lookup"><span data-stu-id="2c643-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="2c643-385">Numero conto</span><span class="sxs-lookup"><span data-stu-id="2c643-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="2c643-386">descrizione</span><span class="sxs-lookup"><span data-stu-id="2c643-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="2c643-387">Libro statutario (livello attuale)</span><span class="sxs-lookup"><span data-stu-id="2c643-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="2c643-388">Totale livello corrente</span><span class="sxs-lookup"><span data-stu-id="2c643-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="2c643-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="2c643-389">JE-100</span></span></th>
<th><span data-ttu-id="2c643-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="2c643-390">JE-110</span></span></th>
<th><span data-ttu-id="2c643-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="2c643-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="2c643-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="2c643-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="2c643-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="2c643-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="2c643-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="2c643-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2c643-395">1</span><span class="sxs-lookup"><span data-stu-id="2c643-395">1</span></span></td>
<td><span data-ttu-id="2c643-396">Spesa di leasing</span><span class="sxs-lookup"><span data-stu-id="2c643-396">Lease expense</span></span></td>
<td><span data-ttu-id="2c643-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="2c643-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="2c643-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-399">2</span><span class="sxs-lookup"><span data-stu-id="2c643-399">2</span></span></td>
<td><span data-ttu-id="2c643-400">Commissione bancaria</span><span class="sxs-lookup"><span data-stu-id="2c643-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-401">3.00</span><span class="sxs-lookup"><span data-stu-id="2c643-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-402">3.00</span><span class="sxs-lookup"><span data-stu-id="2c643-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-403">3</span><span class="sxs-lookup"><span data-stu-id="2c643-403">3</span></span></td>
<td><span data-ttu-id="2c643-404">Spesa IVA</span><span class="sxs-lookup"><span data-stu-id="2c643-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-405">5.00</span><span class="sxs-lookup"><span data-stu-id="2c643-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-406">5.00</span><span class="sxs-lookup"><span data-stu-id="2c643-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-407">4</span><span class="sxs-lookup"><span data-stu-id="2c643-407">4</span></span></td>
<td><span data-ttu-id="2c643-408">Conto di compensazione</span><span class="sxs-lookup"><span data-stu-id="2c643-408">Clearing account</span></span></td>
<td><span data-ttu-id="2c643-409">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="2c643-409">-1,000.00</span></span></td>
<td><span data-ttu-id="2c643-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="2c643-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-411">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-412">5</span><span class="sxs-lookup"><span data-stu-id="2c643-412">5</span></span></td>
<td><span data-ttu-id="2c643-413">Contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="2c643-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="2c643-414">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="2c643-414">-1,008.00</span></span></td>
<td><span data-ttu-id="2c643-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="2c643-415">1,008.00</span></span></td>
<td><span data-ttu-id="2c643-416">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-417">6</span><span class="sxs-lookup"><span data-stu-id="2c643-417">6</span></span></td>
<td><span data-ttu-id="2c643-418">Asset ROU</span><span class="sxs-lookup"><span data-stu-id="2c643-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-419">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-420">7</span><span class="sxs-lookup"><span data-stu-id="2c643-420">7</span></span></td>
<td><span data-ttu-id="2c643-421">Obbligo di leasing finanziario</span><span class="sxs-lookup"><span data-stu-id="2c643-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-422">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-423">8</span><span class="sxs-lookup"><span data-stu-id="2c643-423">8</span></span></td>
<td><span data-ttu-id="2c643-424">Interessi passivi</span><span class="sxs-lookup"><span data-stu-id="2c643-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-425">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-426">9</span><span class="sxs-lookup"><span data-stu-id="2c643-426">9</span></span></td>
<td><span data-ttu-id="2c643-427">Cassa</span><span class="sxs-lookup"><span data-stu-id="2c643-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-428">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="2c643-428">-1,008.00</span></span></td>
<td><span data-ttu-id="2c643-429">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="2c643-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-430">10</span><span class="sxs-lookup"><span data-stu-id="2c643-430">10</span></span></td>
<td><span data-ttu-id="2c643-431">Spesa di ammortamento</span><span class="sxs-lookup"><span data-stu-id="2c643-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-432">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2c643-433">11</span><span class="sxs-lookup"><span data-stu-id="2c643-433">11</span></span></td>
<td><span data-ttu-id="2c643-434">Fondo di ammortamento</span><span class="sxs-lookup"><span data-stu-id="2c643-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="2c643-435">0,00</span><span class="sxs-lookup"><span data-stu-id="2c643-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2c643-436">Se vuoi utilizzare i dati IFRS 16 per eseguire lo stesso bilancio di verifica, le registrazioni a giornale contabili legali devono essere stornate e le registrazioni contabili IFRS 16 devono essere registrate.</span><span class="sxs-lookup"><span data-stu-id="2c643-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="2c643-437">Per stornare le registrazioni a giornale legali, questo esempio include un libro di storno legale che ha la stessa configurazione del libro legale ma un profilo di registrazione opposto.</span><span class="sxs-lookup"><span data-stu-id="2c643-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="2c643-438">Ad esempio, il libro statutario ha *addebitato* un conto spese di leasing, ma il libro di storno *accredita* questo account.</span><span class="sxs-lookup"><span data-stu-id="2c643-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="2c643-439">Queste relazioni sono facilmente definibili nei conti di registrazione del leasing di asset nella pagina **Parametri del leasing di cespiti** (**Leasing di cespiti\> Imposta \> Parametri del leasing di cespiti**).</span><span class="sxs-lookup"><span data-stu-id="2c643-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="2c643-440">Quando lo stesso processo utilizzato per il libro legale viene utilizzato per il libro di storno, viene prodotta la seguente registrazione a giornale.</span><span class="sxs-lookup"><span data-stu-id="2c643-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="2c643-441">La differenza è che il libro di storno registra le registrazioni di storno dal libro statutario.</span><span class="sxs-lookup"><span data-stu-id="2c643-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="2c643-442">Le voci di storno vengono apportate anche al livello personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2c643-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="2c643-443">Quando un bilancio di verifica viene eseguito al livello corrente, le registrazioni a giornale di storno non vengono incluse.</span><span class="sxs-lookup"><span data-stu-id="2c643-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="2c643-444">Canone di leasing - 31/01/2020 - JE 130</span><span class="sxs-lookup"><span data-stu-id="2c643-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="2c643-445">Tipo di account</span><span class="sxs-lookup"><span data-stu-id="2c643-445">Account type</span></span> | <span data-ttu-id="2c643-446">Numero conto</span><span class="sxs-lookup"><span data-stu-id="2c643-446">Account number</span></span> | <span data-ttu-id="2c643-447">Livello</span><span class="sxs-lookup"><span data-stu-id="2c643-447">Layer</span></span>  | <span data-ttu-id="2c643-448">Descrizione conto</span><span class="sxs-lookup"><span data-stu-id="2c643-448">Account description</span></span> | <span data-ttu-id="2c643-449">Dare</span><span class="sxs-lookup"><span data-stu-id="2c643-449">Debit</span></span>    | <span data-ttu-id="2c643-450">Avere</span><span class="sxs-lookup"><span data-stu-id="2c643-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="2c643-451">Ledger</span><span class="sxs-lookup"><span data-stu-id="2c643-451">Ledger</span></span>       | <span data-ttu-id="2c643-452">4</span><span class="sxs-lookup"><span data-stu-id="2c643-452">4</span></span>              | <span data-ttu-id="2c643-453">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="2c643-453">Custom</span></span> | <span data-ttu-id="2c643-454">Conto di compensazione</span><span class="sxs-lookup"><span data-stu-id="2c643-454">Clearing account</span></span>    | <span data-ttu-id="2c643-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="2c643-455">1,000.00</span></span> |          |
| <span data-ttu-id="2c643-456">Ledger</span><span class="sxs-lookup"><span data-stu-id="2c643-456">Ledger</span></span>       | <span data-ttu-id="2c643-457">1</span><span class="sxs-lookup"><span data-stu-id="2c643-457">1</span></span>              | <span data-ttu-id="2c643-458">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="2c643-458">Custom</span></span> | <span data-ttu-id="2c643-459">Spesa di leasing</span><span class="sxs-lookup"><span data-stu-id="2c643-459">Lease expense</span></span>       |          | <span data-ttu-id="2c643-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="2c643-460">1,000.00</span></span> |

<span data-ttu-id="2c643-461">Dopo aver eliminato le registrazioni contabili statutarie, registrerai tutte le scritture contabili richieste dall'IFRS 16 nel libro IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="2c643-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="2c643-462">Queste voci includono la rilevazione iniziale dell'Asset ROU e della passività e la registrazione di interessi e ammortamenti.</span><span class="sxs-lookup"><span data-stu-id="2c643-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="2c643-463">Rilevazione iniziale – 1/1/2020 – JE 140</span><span class="sxs-lookup"><span data-stu-id="2c643-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="2c643-464">Tipo di account</span><span class="sxs-lookup"><span data-stu-id="2c643-464">Account type</span></span> | <span data-ttu-id="2c643-465">Numero conto</span><span class="sxs-lookup"><span data-stu-id="2c643-465">Account number</span></span> | <span data-ttu-id="2c643-466">Livello</span><span class="sxs-lookup"><span data-stu-id="2c643-466">Layer</span></span>  | <span data-ttu-id="2c643-467">Descrizione conto</span><span class="sxs-lookup"><span data-stu-id="2c643-467">Account description</span></span>      | <span data-ttu-id="2c643-468">Dare</span><span class="sxs-lookup"><span data-stu-id="2c643-468">Debit</span></span>     | <span data-ttu-id="2c643-469">Avere</span><span class="sxs-lookup"><span data-stu-id="2c643-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="2c643-470">Ledger</span><span class="sxs-lookup"><span data-stu-id="2c643-470">Ledger</span></span>       | <span data-ttu-id="2c643-471">6</span><span class="sxs-lookup"><span data-stu-id="2c643-471">6</span></span>              | <span data-ttu-id="2c643-472">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="2c643-472">Custom</span></span> | <span data-ttu-id="2c643-473">Asset ROU</span><span class="sxs-lookup"><span data-stu-id="2c643-473">ROU Asset</span></span>                | <span data-ttu-id="2c643-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="2c643-474">22,793.90</span></span> |           |
| <span data-ttu-id="2c643-475">Ledger</span><span class="sxs-lookup"><span data-stu-id="2c643-475">Ledger</span></span>       | <span data-ttu-id="2c643-476">7</span><span class="sxs-lookup"><span data-stu-id="2c643-476">7</span></span>              | <span data-ttu-id="2c643-477">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="2c643-477">Custom</span></span> | <span data-ttu-id="2c643-478">Obbligo di leasing finanziario</span><span class="sxs-lookup"><span data-stu-id="2c643-478">Finance lease obligation</span></span> |           | <span data-ttu-id="2c643-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="2c643-479">22,793.90</span></span> |

<span data-ttu-id="2c643-480">Il canone di leasing viene registrato come gli altri canoni di leasing.</span><span class="sxs-lookup"><span data-stu-id="2c643-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="2c643-481">Il motivo per utilizzare il conto di compensazione è garantire che il contante venga accreditato solo una volta.</span><span class="sxs-lookup"><span data-stu-id="2c643-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="2c643-482">Canone di leasing - 31/01/2020 - JE 150</span><span class="sxs-lookup"><span data-stu-id="2c643-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="2c643-483">Tipo di account</span><span class="sxs-lookup"><span data-stu-id="2c643-483">Account type</span></span> | <span data-ttu-id="2c643-484">Numero conto</span><span class="sxs-lookup"><span data-stu-id="2c643-484">Account number</span></span> | <span data-ttu-id="2c643-485">Livello</span><span class="sxs-lookup"><span data-stu-id="2c643-485">Layer</span></span>  | <span data-ttu-id="2c643-486">Descrizione conto</span><span class="sxs-lookup"><span data-stu-id="2c643-486">Account description</span></span>      | <span data-ttu-id="2c643-487">Dare</span><span class="sxs-lookup"><span data-stu-id="2c643-487">Debit</span></span>    | <span data-ttu-id="2c643-488">Avere</span><span class="sxs-lookup"><span data-stu-id="2c643-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="2c643-489">Ledger</span><span class="sxs-lookup"><span data-stu-id="2c643-489">Ledger</span></span>       | <span data-ttu-id="2c643-490">7</span><span class="sxs-lookup"><span data-stu-id="2c643-490">7</span></span>              | <span data-ttu-id="2c643-491">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="2c643-491">Custom</span></span> | <span data-ttu-id="2c643-492">Obbligo di leasing finanziario</span><span class="sxs-lookup"><span data-stu-id="2c643-492">Finance lease obligation</span></span> | <span data-ttu-id="2c643-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="2c643-493">1,000.00</span></span> |          |
| <span data-ttu-id="2c643-494">Ledger</span><span class="sxs-lookup"><span data-stu-id="2c643-494">Ledger</span></span>       | <span data-ttu-id="2c643-495">4</span><span class="sxs-lookup"><span data-stu-id="2c643-495">4</span></span>              | <span data-ttu-id="2c643-496">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="2c643-496">Custom</span></span> | <span data-ttu-id="2c643-497">Conto di compensazione</span><span class="sxs-lookup"><span data-stu-id="2c643-497">Clearing account</span></span>         |          | <span data-ttu-id="2c643-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="2c643-498">1,000.00</span></span> |

<span data-ttu-id="2c643-499">La scrittura contabile degli interessi passivi viene generata dal piano di ammortamento della passività.</span><span class="sxs-lookup"><span data-stu-id="2c643-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="2c643-500">Interessi passivi – 31/1/2020 – JE 160</span><span class="sxs-lookup"><span data-stu-id="2c643-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="2c643-501">Tipo di account</span><span class="sxs-lookup"><span data-stu-id="2c643-501">Account type</span></span> | <span data-ttu-id="2c643-502">Numero conto</span><span class="sxs-lookup"><span data-stu-id="2c643-502">Account number</span></span> | <span data-ttu-id="2c643-503">Livello</span><span class="sxs-lookup"><span data-stu-id="2c643-503">Layer</span></span>  | <span data-ttu-id="2c643-504">Descrizione conto</span><span class="sxs-lookup"><span data-stu-id="2c643-504">Account description</span></span>      | <span data-ttu-id="2c643-505">Dare</span><span class="sxs-lookup"><span data-stu-id="2c643-505">Debit</span></span> | <span data-ttu-id="2c643-506">Avere</span><span class="sxs-lookup"><span data-stu-id="2c643-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="2c643-507">Ledger</span><span class="sxs-lookup"><span data-stu-id="2c643-507">Ledger</span></span>       | <span data-ttu-id="2c643-508">8</span><span class="sxs-lookup"><span data-stu-id="2c643-508">8</span></span>              | <span data-ttu-id="2c643-509">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="2c643-509">Custom</span></span> | <span data-ttu-id="2c643-510">Interessi passivi</span><span class="sxs-lookup"><span data-stu-id="2c643-510">Interest expense</span></span>         | <span data-ttu-id="2c643-511">94.97</span><span class="sxs-lookup"><span data-stu-id="2c643-511">94.97</span></span> |        |
| <span data-ttu-id="2c643-512">Ledger</span><span class="sxs-lookup"><span data-stu-id="2c643-512">Ledger</span></span>       | <span data-ttu-id="2c643-513">7</span><span class="sxs-lookup"><span data-stu-id="2c643-513">7</span></span>              | <span data-ttu-id="2c643-514">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="2c643-514">Custom</span></span> | <span data-ttu-id="2c643-515">Obbligo di leasing finanziario</span><span class="sxs-lookup"><span data-stu-id="2c643-515">Finance lease obligation</span></span> |       | <span data-ttu-id="2c643-516">94.97</span><span class="sxs-lookup"><span data-stu-id="2c643-516">94.97</span></span>  |

<span data-ttu-id="2c643-517">La scrittura contabile della spesa di ammortamento viene generata dal piano di ammortamento dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="2c643-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="2c643-518">Spesa di ammortamento – 31/1/2020 – JE 170</span><span class="sxs-lookup"><span data-stu-id="2c643-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="2c643-519">Tipo di account</span><span class="sxs-lookup"><span data-stu-id="2c643-519">Account type</span></span> | <span data-ttu-id="2c643-520">Numero conto</span><span class="sxs-lookup"><span data-stu-id="2c643-520">Account number</span></span> | <span data-ttu-id="2c643-521">Livello</span><span class="sxs-lookup"><span data-stu-id="2c643-521">Layer</span></span>  | <span data-ttu-id="2c643-522">Descrizione conto</span><span class="sxs-lookup"><span data-stu-id="2c643-522">Account description</span></span>      | <span data-ttu-id="2c643-523">Dare</span><span class="sxs-lookup"><span data-stu-id="2c643-523">Debit</span></span>  | <span data-ttu-id="2c643-524">Avere</span><span class="sxs-lookup"><span data-stu-id="2c643-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="2c643-525">Ledger</span><span class="sxs-lookup"><span data-stu-id="2c643-525">Ledger</span></span>       | <span data-ttu-id="2c643-526">10</span><span class="sxs-lookup"><span data-stu-id="2c643-526">10</span></span>             | <span data-ttu-id="2c643-527">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="2c643-527">Custom</span></span> | <span data-ttu-id="2c643-528">Spesa di ammortamento</span><span class="sxs-lookup"><span data-stu-id="2c643-528">Depreciation expense</span></span>     | <span data-ttu-id="2c643-529">949.75</span><span class="sxs-lookup"><span data-stu-id="2c643-529">949.75</span></span> |        |
| <span data-ttu-id="2c643-530">Ledger</span><span class="sxs-lookup"><span data-stu-id="2c643-530">Ledger</span></span>       | <span data-ttu-id="2c643-531">11</span><span class="sxs-lookup"><span data-stu-id="2c643-531">11</span></span>             | <span data-ttu-id="2c643-532">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="2c643-532">Custom</span></span> | <span data-ttu-id="2c643-533">Fondo di ammortamento</span><span class="sxs-lookup"><span data-stu-id="2c643-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="2c643-534">949.75</span><span class="sxs-lookup"><span data-stu-id="2c643-534">949.75</span></span> |

<span data-ttu-id="2c643-535">Dopo che tutte queste registrazioni contabili sono state create e registrate, vedrai i seguenti valori di "livello personalizzato 1".</span><span class="sxs-lookup"><span data-stu-id="2c643-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="2c643-536">Nota che l'ultima colonna include la commissione bancaria, la spesa per l'imposta sul valore aggiunto (IVA) e la riduzione del contante dal livello precedente, ma non include le registrazioni contabili del reporting statutario.</span><span class="sxs-lookup"><span data-stu-id="2c643-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="2c643-537">Pertanto, si ottengono vere funzionalità di doppio reporting.</span><span class="sxs-lookup"><span data-stu-id="2c643-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="2c643-538">A questo punto, la società deve solo eseguire il bilancio di verifica e combinare il livello corrente e il livello personalizzato per creare un bilancio di verifica IFRS.</span><span class="sxs-lookup"><span data-stu-id="2c643-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="2c643-539">Numero di conto</span><span class="sxs-lookup"><span data-stu-id="2c643-539">Account No</span></span> | <span data-ttu-id="2c643-540">descrizione</span><span class="sxs-lookup"><span data-stu-id="2c643-540">Description</span></span>              | <span data-ttu-id="2c643-541">Libro statutario\-Livello corrente\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="2c643-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="2c643-542">Libro statutario\-Livello corrente\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="2c643-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="2c643-543">Libro statutario\-Livello corrente\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="2c643-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="2c643-544">Livello corrente \- Totali</span><span class="sxs-lookup"><span data-stu-id="2c643-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="2c643-545">Libro di storno\-Livello personalizzato\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="2c643-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="2c643-546">Libro IFRS 16\-Livello personalizzato\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="2c643-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="2c643-547">Libro IFRS 16\-Livello personalizzato\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="2c643-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="2c643-548">Libro IFRS 16\-Livello personalizzato\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="2c643-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="2c643-549">Libro IFRS 16\-Livello personalizzato\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="2c643-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="2c643-550">Livello personalizzato \+ Livello corrente \- Totali</span><span class="sxs-lookup"><span data-stu-id="2c643-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="2c643-551">1</span><span class="sxs-lookup"><span data-stu-id="2c643-551">1</span></span>          | <span data-ttu-id="2c643-552">Spesa di leasing</span><span class="sxs-lookup"><span data-stu-id="2c643-552">Lease expense</span></span>            | <span data-ttu-id="2c643-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="2c643-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-554">1,000\.00</span></span>               |   | <span data-ttu-id="2c643-555">\-1.000</span><span class="sxs-lookup"><span data-stu-id="2c643-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="2c643-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-556">0\.00</span></span>                                   |
| <span data-ttu-id="2c643-557">2</span><span class="sxs-lookup"><span data-stu-id="2c643-557">2</span></span>          | <span data-ttu-id="2c643-558">Commissione bancaria</span><span class="sxs-lookup"><span data-stu-id="2c643-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="2c643-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="2c643-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="2c643-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-561">3\.00</span></span>                                   |
| <span data-ttu-id="2c643-562">3</span><span class="sxs-lookup"><span data-stu-id="2c643-562">3</span></span>          | <span data-ttu-id="2c643-563">Spesa IVA</span><span class="sxs-lookup"><span data-stu-id="2c643-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="2c643-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="2c643-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="2c643-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-566">5\.00</span></span>                                   |
| <span data-ttu-id="2c643-567">4</span><span class="sxs-lookup"><span data-stu-id="2c643-567">4</span></span>          | <span data-ttu-id="2c643-568">Conto di compensazione</span><span class="sxs-lookup"><span data-stu-id="2c643-568">Clearing account</span></span>         | <span data-ttu-id="2c643-569">\-1.000\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="2c643-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="2c643-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-571">0\.00</span></span>                   |   | <span data-ttu-id="2c643-572">1.000</span><span class="sxs-lookup"><span data-stu-id="2c643-572">1,000</span></span>                                           |                                                | <span data-ttu-id="2c643-573">\-1.000</span><span class="sxs-lookup"><span data-stu-id="2c643-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="2c643-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-574">0\.00</span></span>                                   |
| <span data-ttu-id="2c643-575">5</span><span class="sxs-lookup"><span data-stu-id="2c643-575">5</span></span>          | <span data-ttu-id="2c643-576">Contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="2c643-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="2c643-577">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="2c643-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-578">1,008\.00</span></span>                                         | <span data-ttu-id="2c643-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="2c643-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-580">0\.00</span></span>                                   |
| <span data-ttu-id="2c643-581">6</span><span class="sxs-lookup"><span data-stu-id="2c643-581">6</span></span>          | <span data-ttu-id="2c643-582">Asset ROU</span><span class="sxs-lookup"><span data-stu-id="2c643-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="2c643-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="2c643-584">22,794</span><span class="sxs-lookup"><span data-stu-id="2c643-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="2c643-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="2c643-585">22,793\.90</span></span>                              |
| <span data-ttu-id="2c643-586">7</span><span class="sxs-lookup"><span data-stu-id="2c643-586">7</span></span>          | <span data-ttu-id="2c643-587">Obbligo di leasing finanziario</span><span class="sxs-lookup"><span data-stu-id="2c643-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="2c643-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="2c643-589">\-22.794</span><span class="sxs-lookup"><span data-stu-id="2c643-589">\-22,794</span></span>                                       | <span data-ttu-id="2c643-590">1.000</span><span class="sxs-lookup"><span data-stu-id="2c643-590">1,000</span></span>                                          | <span data-ttu-id="2c643-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="2c643-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="2c643-592">\-21,888\.87</span><span class="sxs-lookup"><span data-stu-id="2c643-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="2c643-593">8</span><span class="sxs-lookup"><span data-stu-id="2c643-593">8</span></span>          | <span data-ttu-id="2c643-594">Interessi passivi</span><span class="sxs-lookup"><span data-stu-id="2c643-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="2c643-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="2c643-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="2c643-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="2c643-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="2c643-597">94\.97</span></span>                                  |
| <span data-ttu-id="2c643-598">9</span><span class="sxs-lookup"><span data-stu-id="2c643-598">9</span></span>          | <span data-ttu-id="2c643-599">Cassa</span><span class="sxs-lookup"><span data-stu-id="2c643-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="2c643-600">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="2c643-601">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="2c643-602">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="2c643-603">10</span><span class="sxs-lookup"><span data-stu-id="2c643-603">10</span></span>         | <span data-ttu-id="2c643-604">Spesa di ammortamento</span><span class="sxs-lookup"><span data-stu-id="2c643-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="2c643-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="2c643-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="2c643-606">949\.75</span></span>                                        | <span data-ttu-id="2c643-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="2c643-607">949\.75</span></span>                                 |
| <span data-ttu-id="2c643-608">11</span><span class="sxs-lookup"><span data-stu-id="2c643-608">11</span></span>         | <span data-ttu-id="2c643-609">Fondo di ammortamento</span><span class="sxs-lookup"><span data-stu-id="2c643-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="2c643-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="2c643-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="2c643-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="2c643-611">\-949\.75</span></span>                                      | <span data-ttu-id="2c643-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="2c643-612">\-949\.75</span></span>                               |


