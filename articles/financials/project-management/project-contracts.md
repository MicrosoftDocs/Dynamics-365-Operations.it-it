---
title: Contratti di progetto
description: "Vengono forniti esempi di contratti che è possibile creare per diversi tipi di progetto e fonti di finanziamento e viene illustrato il modo in cui è possibile gestire i contratti e le fatture dei clienti di progetto in Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectContractsListPage, ProjProjectsListPage
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23561
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 40f5f5e8c6a97cfa56e1c3e5aba2fc2d6629f6dd
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="project-contracts"></a><span data-ttu-id="270ac-103">Contratti di progetto</span><span class="sxs-lookup"><span data-stu-id="270ac-103">Project contracts</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="270ac-104">Vengono forniti esempi e descrizioni di contratti creabili per diversi tipi di progetto e fonti di finanziamento e viene illustrato il modo in cui è possibile gestire i contratti e fatturare i progetti ai clienti in Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="270ac-104">This article provides examples of the project contracts that you can create for various types of projects and funding sources, and how you can manage contracts and invoice project customers in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="270ac-105">Il tipo di progetto creato per un contratto di progetto determina il metodo utilizzato per rilasciare fatture ai clienti del progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-105">The type of project that you create for a project contract determines the method that is used to invoice project customers.</span></span> <span data-ttu-id="270ac-106">È possibile modificare un contratto di progetto e il relativo progetto, ma non è possibile modificare il tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-106">You can change a project contract and the related project, but you can't change the project type.</span></span> 

<span data-ttu-id="270ac-107">Un contratto di progetto consente di fatturare contemporaneamente uno o più progetti</span><span class="sxs-lookup"><span data-stu-id="270ac-107">By using a project contract, you can invoice one or more projects at the same time.</span></span> <span data-ttu-id="270ac-108">Il contratto di progetto consente inoltre di garantire che una procedura di fatturazione coerente venga utilizzata per ogni sottoprogetto in una struttura di progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-108">The project contract also helps guarantee a consistent invoicing procedure for every subproject in a project structure.</span></span> 

<span data-ttu-id="270ac-109">Ogni progetto fatturato deve essere associato a un contratto di progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-109">Every project that will be invoiced must be associated with a project contract.</span></span> <span data-ttu-id="270ac-110">Le impostazioni per un contratto di progetto vengono applicate a tutti i progetti e sottoprogetti associati al contratto di progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-110">The settings for a project contract apply to all projects and subprojects that are associated with that project contract.</span></span> 

<span data-ttu-id="270ac-111">Un contratto di progetto può specificare una o più fonti di finanziamento.</span><span class="sxs-lookup"><span data-stu-id="270ac-111">A project contract can specify one or more sources of funding.</span></span> <span data-ttu-id="270ac-112">È pertanto possibile suddividere la fatturazione tra più finanziatori, impostare limiti di finanziamento per impedire che alle fonti di finanziamento vengano fatturati importi superiori a quello specificato e configurare regole di finanziamento per il carico delle spese.</span><span class="sxs-lookup"><span data-stu-id="270ac-112">Therefore, you can split the billing among multiple funders, set up funding limits so that funding sources are not billed more than a specified amount, and configure funding rules for charging expenditures.</span></span>

## <a name="funding-for-project-contracts"></a><span data-ttu-id="270ac-113">Finanziamento dei contratti di progetto</span><span class="sxs-lookup"><span data-stu-id="270ac-113">Funding for project contracts</span></span>
<span data-ttu-id="270ac-114">In alcuni contratti di progetto viene specificato che più parti condividono la responsabilità del finanziamento dei costi di progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-114">Some project contracts specify that multiple parties share the responsibility for funding the project costs.</span></span> <span data-ttu-id="270ac-115">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="270ac-115">Here are some examples:</span></span>

-   <span data-ttu-id="270ac-116">Un cliente di grandi dimensioni con più divisioni richiede che il finanziamento di un progetto sia suddiviso per divisione.</span><span class="sxs-lookup"><span data-stu-id="270ac-116">A large customer that has multiple divisions requests that funding of a project be split by division.</span></span>
-   <span data-ttu-id="270ac-117">La società condivide i costi di un progetto di grandi dimensioni con un'organizzazione esterna.</span><span class="sxs-lookup"><span data-stu-id="270ac-117">Your company shares the costs of a large project with an external organization.</span></span>
-   <span data-ttu-id="270ac-118">Un progetto per una strada è cofinanziato da due comuni.</span><span class="sxs-lookup"><span data-stu-id="270ac-118">A  road project is co-funded by two municipalities.</span></span>
-   <span data-ttu-id="270ac-119">Un progetto per un ponte è finanziato da una sovvenzione di governo e da una società privata.</span><span class="sxs-lookup"><span data-stu-id="270ac-119">A bridge project is funded by a government grant and a private corporation.</span></span>

<span data-ttu-id="270ac-120">In Finance and Operations, è possibile suddividere la fatturazione per una singola transazione o un intero progetto tra più clienti, sovvenzioni o organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="270ac-120">In Finance and Operations, you can split the billing for a single transaction or an entire project among multiple customers, grants, or organizations.</span></span> 

<span data-ttu-id="270ac-121">In progetti con più finanziatori, tutte le parti che contribuiscono a un progetto di finanziamento avanzato sono denominate fonti di finanziamento.</span><span class="sxs-lookup"><span data-stu-id="270ac-121">In projects that have multiple funders, all parties that contribute to the funding of an advanced funding project are called funding sources.</span></span> <span data-ttu-id="270ac-122">Quando un cliente, organizzazione, o sovvenzione viene definito come fonte di finanziamento, potrà essere assegnato a una o più regole di finanziamento.</span><span class="sxs-lookup"><span data-stu-id="270ac-122">After a customer, organization, or grant is defined as a funding source, it can be assigned to one or more funding rules.</span></span> <span data-ttu-id="270ac-123">Le regole di finanziamento contengono i criteri che determinano come le spese sono allocate a diverse fonti di finanziamento per un progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-123">Funding rules contain the criteria that determines how charges are allocated to the various funding sources for a project.</span></span> 

<span data-ttu-id="270ac-124">Poiché gli articoli stoccati, ad esempio quelli visualizzati nelle richieste di acquisto e ordini fornitore, non possono essere suddivisi, l'importo costi non può essere suddiviso tra più fonti di finanziamento al momento della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="270ac-124">Because stocked items, such as those that appear on purchase requisitions and purchase orders, can't be split, the cost amount can't be split among multiple funding sources at the time of distribution.</span></span> <span data-ttu-id="270ac-125">Il valore relativo alla fonte di finanziamento rimane quindi pari a zero fino al momento della registrazione dell'uscita da magazzino.</span><span class="sxs-lookup"><span data-stu-id="270ac-125">Therefore, the funding source value remains 0 (zero) until the inventory issue is posted.</span></span> <span data-ttu-id="270ac-126">Quando l'uscita da magazzino viene registrata, l'importo dei costi viene distribuito in base alle regole di distribuzione contabile del progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-126">When the inventory issue is posted, the cost amount is distributed according to the account distribution rules for the project.</span></span>

<span data-ttu-id="270ac-127">Di seguito sono riportati alcuni passaggi che è possibile eseguire per rendere più facile suddividere la fatturazione tra più fonti di finanziamento:</span><span class="sxs-lookup"><span data-stu-id="270ac-127">Here are some steps that you can take to make it easier to split the billing among multiple funding sources:</span></span>

-   <span data-ttu-id="270ac-128">Specificare che tutte le transazioni registrate per un progetto utilizzino la stessa valuta di vendita presente nel contratto del progetto stesso.</span><span class="sxs-lookup"><span data-stu-id="270ac-128">Specify that all transactions that are entered for a project use the same sales currency as the project contract.</span></span>
-   <span data-ttu-id="270ac-129">Impostare i limiti di finanziamento in modo che a una fonte di finanziamento non sia possibile fatturare per un progetto importi superiori a un limite specificato.</span><span class="sxs-lookup"><span data-stu-id="270ac-129">Set up funding limits, so that a funding source isn't invoiced more than a specified amount toward a project.</span></span>
-   <span data-ttu-id="270ac-130">Configurare le regole di finanziamento e i limiti di finanziamento per ciascun lavoratore, articolo, categoria, gruppo di categorie e tipo di transazione (o per tutti i tipi di transazione).</span><span class="sxs-lookup"><span data-stu-id="270ac-130">Configure funding rules and funding limits for each worker, item, category, category group, and transaction type (or for all transaction types).</span></span>
-   <span data-ttu-id="270ac-131">Selezionare facoltativamente le date di inizio e di fine per definire il periodo di validità di ciascuna regola di finanziamento.</span><span class="sxs-lookup"><span data-stu-id="270ac-131">Select optional start and end dates to define the period when each funding rule is valid.</span></span>
-   <span data-ttu-id="270ac-132">Specificare la percentuale di cui è responsabile ciascuna fonte di finanziamento.</span><span class="sxs-lookup"><span data-stu-id="270ac-132">Specify the percentage that each funding source is responsible for.</span></span>
-   <span data-ttu-id="270ac-133">Specificare la fonte di finanziamento responsabile delle differenze di arrotondamento derivanti dai calcoli per l'allocazione del finanziamento.</span><span class="sxs-lookup"><span data-stu-id="270ac-133">Specify which funding source is responsible for rounding differences that are caused by funding allocation calculations.</span></span>
-   <span data-ttu-id="270ac-134">Impostare le regole che determinano le modalità di fatturazione dei costi di progetto ai clienti esterni e per le modalità di addebito alle organizzazioni interne.</span><span class="sxs-lookup"><span data-stu-id="270ac-134">Set up rules that determine how project costs are invoiced to external customers and charged to internal organizations.</span></span>
-   <span data-ttu-id="270ac-135">Registrare le transazioni in un conto di finanziamento in sospeso fino all'ottenimento di un finanziamento aggiuntivo o fino alla decisione di farsi carico dei costi internamente.</span><span class="sxs-lookup"><span data-stu-id="270ac-135">Record transactions in an on-hold funding account until additional funding can be obtained, or until you decide to bear the costs internally.</span></span>

<span data-ttu-id="270ac-136">Per determinare la fascia IVA da associare a una transazione, viene effettuata la ricerca di un'assegnazione di fascia IVA all'interno del progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-136">To determine which tax group to associate with a transaction, the project is searched for a tax group assignment.</span></span> <span data-ttu-id="270ac-137">Se non è stata effettuata alcuna assegnazione di fascia IVA a livello di progetto, viene effettuata la ricerca nel contratto di progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-137">If no tax group assignment has been made at the project level, the project contract is searched.</span></span>

### <a name="example-multiple-funding-sources-simple"></a><span data-ttu-id="270ac-138">Esempi: più fonti di finanziamento (semplice)</span><span class="sxs-lookup"><span data-stu-id="270ac-138">Example: Multiple funding sources (simple)</span></span>

<span data-ttu-id="270ac-139">Nella tabella riportata di seguito vengono illustrati gli scenari per la gestione dell'allocazione del finanziamento tra più fonti di finanziamento.</span><span class="sxs-lookup"><span data-stu-id="270ac-139">The following table provides scenarios for managing funding allocation among multiple funding sources.</span></span> <span data-ttu-id="270ac-140">Questi scenari si basano sui seguenti presupposti:</span><span class="sxs-lookup"><span data-stu-id="270ac-140">These scenarios are based on the following assumptions:</span></span>

-   <span data-ttu-id="270ac-141">Le impostazioni di priorità vengono considerate fattori importanti per l'allocazione di fondi prima dell'applicazione di altri criteri della regola di finanziamento.</span><span class="sxs-lookup"><span data-stu-id="270ac-141">Priority settings are factored into the allocation of funds before other funding rule criteria are applied.</span></span>
-   <span data-ttu-id="270ac-142">Alcun intervallo di date è stato specificato per definire il periodo d in cui la regola di finanziamento è valida.</span><span class="sxs-lookup"><span data-stu-id="270ac-142">No date range has been specified to define the period d when the funding rule is valid.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="270ac-143"><strong>Scenario</strong></span><span class="sxs-lookup"><span data-stu-id="270ac-143"><strong>Scenario</strong></span></span></td>
<td><span data-ttu-id="270ac-144"><strong>Fonte di finanziamento</strong></span><span class="sxs-lookup"><span data-stu-id="270ac-144"><strong>Funding source</strong></span></span></td>
<td><span data-ttu-id="270ac-145"><strong>Percentuale di allocazione </strong></span><span class="sxs-lookup"><span data-stu-id="270ac-145"><strong>Allocation percentage</strong></span></span></td>
<td><span data-ttu-id="270ac-146"><strong>Priorità di allocazione</strong></span><span class="sxs-lookup"><span data-stu-id="270ac-146"><strong>Allocation priority</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="270ac-147">Si desidera allocare i costi a una fonte di finanziamento fino a esaurire i relativi fondi, allocare i costi a una seconda fonte di finanziamento fino a esaurire i fondi e infine allocare i costi rimanenti a una terza fonte di finanziamento.</span><span class="sxs-lookup"><span data-stu-id="270ac-147">You want to allocate costs to one funding source until its funds are exhausted, allocate costs to a second funding source until its funds are exhausted, and finally allocate the remaining costs to a third funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="270ac-148">Fonte di finanziamento 1</span><span class="sxs-lookup"><span data-stu-id="270ac-148">Funding　source　1</span></span></li>
<li><span data-ttu-id="270ac-149">Fonte di finanziamento 2</span><span class="sxs-lookup"><span data-stu-id="270ac-149">Funding　source　2</span></span></li>
<li><span data-ttu-id="270ac-150">Fonte di finanziamento 3</span><span class="sxs-lookup"><span data-stu-id="270ac-150">Funding　source　3</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="270ac-151">100%</span><span class="sxs-lookup"><span data-stu-id="270ac-151">100%</span></span></li>
<li><span data-ttu-id="270ac-152">100%</span><span class="sxs-lookup"><span data-stu-id="270ac-152">100%</span></span></li>
<li><span data-ttu-id="270ac-153">100%</span><span class="sxs-lookup"><span data-stu-id="270ac-153">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="270ac-154">1</span><span class="sxs-lookup"><span data-stu-id="270ac-154">1</span></span></li>
<li><span data-ttu-id="270ac-155">2</span><span class="sxs-lookup"><span data-stu-id="270ac-155">2</span></span></li>
<li><span data-ttu-id="270ac-156">3</span><span class="sxs-lookup"><span data-stu-id="270ac-156">3</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="270ac-157">Si desidera allocare il 75 percento dei costi a una fonte di finanziamento e il 25 percento a una seconda fonte.</span><span class="sxs-lookup"><span data-stu-id="270ac-157">You want to allocate 75 percent of costs to one funding source and 25 percent to a second funding source.</span></span> <span data-ttu-id="270ac-158">Quando una delle fonti di finanziamento è esaurita, si desidera pagare i costi rimanenti da una terza fonte di finanziamento.</span><span class="sxs-lookup"><span data-stu-id="270ac-158">When either of those funding sources is exhausted, you want to pay the remaining costs from a third funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="270ac-159">Fonte di finanziamento 1</span><span class="sxs-lookup"><span data-stu-id="270ac-159">Funding　source　1</span></span></li>
<li><span data-ttu-id="270ac-160">Fonte di finanziamento 2</span><span class="sxs-lookup"><span data-stu-id="270ac-160">Funding　source　2</span></span></li>
<li><span data-ttu-id="270ac-161">Fonte di finanziamento 3</span><span class="sxs-lookup"><span data-stu-id="270ac-161">Funding　source　3</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="270ac-162">75%</span><span class="sxs-lookup"><span data-stu-id="270ac-162">75%</span></span></li>
<li><span data-ttu-id="270ac-163">25%</span><span class="sxs-lookup"><span data-stu-id="270ac-163">25%</span></span></li>
<li><span data-ttu-id="270ac-164">100%</span><span class="sxs-lookup"><span data-stu-id="270ac-164">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="270ac-165">1</span><span class="sxs-lookup"><span data-stu-id="270ac-165">1</span></span></li>
<li><span data-ttu-id="270ac-166">1</span><span class="sxs-lookup"><span data-stu-id="270ac-166">1</span></span></li>
<li><span data-ttu-id="270ac-167">2</span><span class="sxs-lookup"><span data-stu-id="270ac-167">2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="270ac-168">Si desidera allocare il 75 percento dei costi a una fonte di finanziamento e il 25 percento a una seconda fonte.</span><span class="sxs-lookup"><span data-stu-id="270ac-168">You want to allocate 75 percent of costs to one funding source and 25 percent to a second funding source.</span></span> <span data-ttu-id="270ac-169">Quando una delle fonti di finanziamento è esaurita, si desidera dividere i costi rimanenti tra una terza e una quarta fonte di finanziamento.</span><span class="sxs-lookup"><span data-stu-id="270ac-169">When either of those funding sources is exhausted, you want to split the remaining costs between a third funding source and a fourth funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="270ac-170">Fonte di finanziamento 1</span><span class="sxs-lookup"><span data-stu-id="270ac-170">Funding　source　1</span></span></li>
<li><span data-ttu-id="270ac-171">Fonte di finanziamento 2</span><span class="sxs-lookup"><span data-stu-id="270ac-171">Funding　source　2</span></span></li>
<li><span data-ttu-id="270ac-172">Fonte di finanziamento 3</span><span class="sxs-lookup"><span data-stu-id="270ac-172">Funding　source　3</span></span></li>
<li><span data-ttu-id="270ac-173">Fonte di finanziamento 4</span><span class="sxs-lookup"><span data-stu-id="270ac-173">Funding　source　4</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="270ac-174">75%</span><span class="sxs-lookup"><span data-stu-id="270ac-174">75%</span></span></li>
<li><span data-ttu-id="270ac-175">25%</span><span class="sxs-lookup"><span data-stu-id="270ac-175">25%</span></span></li>
<li><span data-ttu-id="270ac-176">50%</span><span class="sxs-lookup"><span data-stu-id="270ac-176">50%</span></span></li>
<li><span data-ttu-id="270ac-177">50%</span><span class="sxs-lookup"><span data-stu-id="270ac-177">50%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="270ac-178">1</span><span class="sxs-lookup"><span data-stu-id="270ac-178">1</span></span></li>
<li><span data-ttu-id="270ac-179">1</span><span class="sxs-lookup"><span data-stu-id="270ac-179">1</span></span></li>
<li><span data-ttu-id="270ac-180">2</span><span class="sxs-lookup"><span data-stu-id="270ac-180">2</span></span></li>
<li><span data-ttu-id="270ac-181">2</span><span class="sxs-lookup"><span data-stu-id="270ac-181">2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="270ac-182">Si desidera allocare il primo 25 percento dei costi a una fonte di finanziamento e il resto a una seconda fonte di finanziamento.</span><span class="sxs-lookup"><span data-stu-id="270ac-182">You want to allocate the first 25 percent of costs to one funding source and the rest to a second funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="270ac-183">Fonte di finanziamento 1</span><span class="sxs-lookup"><span data-stu-id="270ac-183">Funding　source　1</span></span></li>
<li><span data-ttu-id="270ac-184">Fonte di finanziamento 2</span><span class="sxs-lookup"><span data-stu-id="270ac-184">Funding　source　2</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="270ac-185">25%</span><span class="sxs-lookup"><span data-stu-id="270ac-185">25%</span></span></li>
<li><span data-ttu-id="270ac-186">100%</span><span class="sxs-lookup"><span data-stu-id="270ac-186">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="270ac-187">1</span><span class="sxs-lookup"><span data-stu-id="270ac-187">1</span></span></li>
<li><span data-ttu-id="270ac-188">2</span><span class="sxs-lookup"><span data-stu-id="270ac-188">2</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="example-multiple-funding-sources-complex"></a><span data-ttu-id="270ac-189">Esempio: più fonti di finanziamento (complesso)</span><span class="sxs-lookup"><span data-stu-id="270ac-189">Example: Multiple funding sources (complex)</span></span>

<span data-ttu-id="270ac-190">Sono disponibili tre fonti di finanziamento che si desidera utilizzare nel seguente ordine:</span><span class="sxs-lookup"><span data-stu-id="270ac-190">You have three funding sources that you want to use in the following order:</span></span>

1.  <span data-ttu-id="270ac-191">Utilizzare equamente la fonte di finanziamento 2 e la fonte di finanziamento 3 fino a esaurire la fonte di finanziamento 2.</span><span class="sxs-lookup"><span data-stu-id="270ac-191">Use funding source 2 and funding source 3 equally until funding source 2 is exhausted.</span></span>
2.  <span data-ttu-id="270ac-192">Continuare a utilizzare la fonte di finanziamento 3 fino a esaurimento.</span><span class="sxs-lookup"><span data-stu-id="270ac-192">Continue to use funding source 3 until it is exhausted.</span></span>
3.  <span data-ttu-id="270ac-193">Utilizzare la fonte di finanziamento 1 quando la fonte di finanziamento 3 viene esaurita.</span><span class="sxs-lookup"><span data-stu-id="270ac-193">Use funding source 1 after funding source 3 is exhausted.</span></span>

<span data-ttu-id="270ac-194">Per realizzare l'obiettivo in questione, è necessario eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="270ac-194">To accomplish this goal, you must do the following:</span></span>

-   <span data-ttu-id="270ac-195">Impostare limiti di finanziamento per le fonti di finanziamento 2 e 3 per i rispettivi importi.</span><span class="sxs-lookup"><span data-stu-id="270ac-195">Set up funding limits for funding source 2 and funding source 3, for their respective amounts.</span></span>
-   <span data-ttu-id="270ac-196">Creare le seguenti regole di finanziamento:</span><span class="sxs-lookup"><span data-stu-id="270ac-196">Create the following funding rules:</span></span>
    -   <span data-ttu-id="270ac-197">Regola 1: (priorità 1) allocare il 50 percento delle transazioni alla fonte di finanziamento 2 e il 50 percento alla fonte di finanziamento 3.</span><span class="sxs-lookup"><span data-stu-id="270ac-197">Rule 1 (Priority 1): Allocate 50 percent of transactions to funding source 2 and 50 percent to funding source 3.</span></span>
    -   <span data-ttu-id="270ac-198">Regola 2: (priorità 2) allocare il 100 percento delle transazioni alla fonte di finanziamento 3.</span><span class="sxs-lookup"><span data-stu-id="270ac-198">Rule 2 (Priority 2): Allocate 100 percent of transactions to funding source 3.</span></span>
    -   <span data-ttu-id="270ac-199">Regola 3: (priorità 3) allocare il 100 percento delle transazioni alla fonte di finanziamento 1.</span><span class="sxs-lookup"><span data-stu-id="270ac-199">Rule 3 (Priority 3): Allocate 100 percent of transactions to funding source 1.</span></span>

<span data-ttu-id="270ac-200">Questa impostazione funziona poiché le transazioni vengono confrontate con le regole e i limiti per determinare se una qualsiasi si applica alla transazione.</span><span class="sxs-lookup"><span data-stu-id="270ac-200">This setup works because transactions are checked against rules and limits to determine whether any of them apply to the transaction.</span></span> <span data-ttu-id="270ac-201">Se alla transazione non si applica alcun limite o regola specifico, si applicherà la regola Tutte le transazioni.</span><span class="sxs-lookup"><span data-stu-id="270ac-201">If no specific rules or limits apply to the transaction, the All transactions rule applies.</span></span> <span data-ttu-id="270ac-202">La regola Tutte le transazioni corrisponde a tutte le transazioni.</span><span class="sxs-lookup"><span data-stu-id="270ac-202">The All transactions rule matches all transactions.</span></span> 

<span data-ttu-id="270ac-203">Se viene trovata una regola che corrisponde a una transazione, in primo luogo si applica la percentuale che è stata allocata nella regola, ma solo dopo che le corrispondenze vengono confrontate con tutti i limiti impostati.</span><span class="sxs-lookup"><span data-stu-id="270ac-203">If a rule is found that matches a transaction, the percentage that has been allocated in that rule is applied first, but only after the matches are checked against any limits that have been set up.</span></span> <span data-ttu-id="270ac-204">Se un limite è stato raggiunto e i fondi di una fonte di finanziamento vengono esauriti, la regola di finanziamento associata al limite di finanziamento viene ignorata e il programma verifica la presenta della regola successiva applicabile.</span><span class="sxs-lookup"><span data-stu-id="270ac-204">If a limit has been met, and a funding source’s funds are exhausted, the funding rule that is associated with the funding limit is disregarded, and the program checks for the next rule that applies.</span></span> 

<span data-ttu-id="270ac-205">In alcuni casi, solo parte di una transazione può essere allocata in base a una regola.</span><span class="sxs-lookup"><span data-stu-id="270ac-205">In some cases, only part of a transaction can be allocated under a rule.</span></span> <span data-ttu-id="270ac-206">Ciò potrebbe verificarsi poiché un limite viene raggiunto quando la transazione viene allocata.</span><span class="sxs-lookup"><span data-stu-id="270ac-206">This might happen because a limit is reached when the transaction is allocated.</span></span> <span data-ttu-id="270ac-207">In questo caso, solo un certo importo viene allocato in base alla regola, ad esempio il 50 percento a ciascuna fonte di finanziamento.</span><span class="sxs-lookup"><span data-stu-id="270ac-207">In this case, only a certain amount is allocated according to that rule, such as 50 percent to each funding source.</span></span> <span data-ttu-id="270ac-208">Questo si verifica nella regola 1, descritta in precedenza in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="270ac-208">This is the case in rule 1, which is described earlier in this section.</span></span> <span data-ttu-id="270ac-209">Il resto viene allocato in base alla regola successiva nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="270ac-209">The remainder is allocated according to the next rule in the sequence.</span></span> 

<span data-ttu-id="270ac-210">Nella tabella seguente questo scenario viene esaminato in modo più dettagliato.</span><span class="sxs-lookup"><span data-stu-id="270ac-210">The following table examines this scenario in more detail.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="270ac-211"><strong>Elemento attivo</strong></span><span class="sxs-lookup"><span data-stu-id="270ac-211"><strong>Focus</strong></span></span></td>
<td><span data-ttu-id="270ac-212"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="270ac-212"><strong>Details</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="270ac-213">Regole di finanziamento</span><span class="sxs-lookup"><span data-stu-id="270ac-213">Funding rules</span></span></td>
<td><ul>
<li><span data-ttu-id="270ac-214">Regola 1 (priorità 1): tutte le transazioni.</span><span class="sxs-lookup"><span data-stu-id="270ac-214">Rule 1 (Priority 1): All transactions.</span></span> <span data-ttu-id="270ac-215">Allocare la fonte di finanziamento 2 per il 50% e la fonte di finanziamento 3 per il 50%.</span><span class="sxs-lookup"><span data-stu-id="270ac-215">Allocate funding source 2 at 50% and funding source 3 at 50%.</span></span></li>
<li><span data-ttu-id="270ac-216">Regola 2 (priorità 2): tutte le transazioni.</span><span class="sxs-lookup"><span data-stu-id="270ac-216">Rule 2 (Priority 2): All transactions.</span></span> <span data-ttu-id="270ac-217">Allocare la fonte di finanziamento 3 per il 100%.</span><span class="sxs-lookup"><span data-stu-id="270ac-217">Allocate funding source 3 at 100%.</span></span></li>
<li><span data-ttu-id="270ac-218">Regola 3 (priorità 2): tutte le transazioni.</span><span class="sxs-lookup"><span data-stu-id="270ac-218">Rule 3 (Priority 2): All transactions.</span></span> <span data-ttu-id="270ac-219">Allocare la fonte di finanziamento 1 per il 100%.</span><span class="sxs-lookup"><span data-stu-id="270ac-219">Allocate funding source 1 at 100%.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="270ac-220">Limiti di finanziamento</span><span class="sxs-lookup"><span data-stu-id="270ac-220">Funding limits</span></span></td>
<td><ul>
<li><span data-ttu-id="270ac-221">Limite della fonte di finanziamento 1 = 10.000,00</span><span class="sxs-lookup"><span data-stu-id="270ac-221">Funding source 1 limit = 10,000.00</span></span></li>
<li><span data-ttu-id="270ac-222">Limite della fonte di finanziamento 2 = 500,00</span><span class="sxs-lookup"><span data-stu-id="270ac-222">Funding source 2 limit = 500.00</span></span></li>
<li><span data-ttu-id="270ac-223">Limite della fonte di finanziamento 3 = 750,00</span><span class="sxs-lookup"><span data-stu-id="270ac-223">Funding source 3 limit = 750.00</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="270ac-224">Transazione 1</span><span class="sxs-lookup"><span data-stu-id="270ac-224">Transaction 1</span></span></td>
<td><span data-ttu-id="270ac-225"><strong>Importo della transazione:</strong> 100.00<strong>Finanziamento:</strong> La transazione viene pagata solo in base alla regola 1, poiché la transazione è interamente pagata dopo l'applicazione della regola 1.</span><span class="sxs-lookup"><span data-stu-id="270ac-225"><strong>Transaction amount:</strong> 100.00<strong>Funding:</strong> The transaction is paid according to rule 1 only, because the transaction is fully paid after rule 1 is applied.</span></span> <span data-ttu-id="270ac-226">La transazione è finanziata equamente tra la fonte di finanziamento 2 e la fonte di finanziamento 3.</span><span class="sxs-lookup"><span data-stu-id="270ac-226">The transaction is funded equally between funding source 2 and funding source 3.</span></span>
<ul>
<li><span data-ttu-id="270ac-227">Fonte di finanziamento 2: 50,00</span><span class="sxs-lookup"><span data-stu-id="270ac-227">Funding source 2: 50.00</span></span></li>
<li><span data-ttu-id="270ac-228">Fonte di finanziamento 3: 50,00</span><span class="sxs-lookup"><span data-stu-id="270ac-228">Funding source 3: 50.00</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="270ac-229">Transazione 2</span><span class="sxs-lookup"><span data-stu-id="270ac-229">Transaction 2</span></span></td>
<td><span data-ttu-id="270ac-230"><strong>Importo della transazione:</strong> 5.000,00<strong>Finanziamento:</strong> la transazione viene pagata in base a tutte e tre le regole.</span><span class="sxs-lookup"><span data-stu-id="270ac-230"><strong>Transaction amount:</strong> 5,000.00<strong>Funding:</strong> The transaction is paid according to all three rules.</span></span> <span data-ttu-id="270ac-231"><strong>Regola 1</strong>
</span><span class="sxs-lookup"><span data-stu-id="270ac-231"><strong>Rule 1</strong>
</span></span><ul>
<li><span data-ttu-id="270ac-232">Fonte di finanziamento 2: 450,00</span><span class="sxs-lookup"><span data-stu-id="270ac-232">Funding source 2: 450.00</span></span></li>
<li><span data-ttu-id="270ac-233">Fonte di finanziamento 3: 450,00</span><span class="sxs-lookup"><span data-stu-id="270ac-233">Funding source 3: 450.00</span></span></li>
</ul><span data-ttu-id="270ac-234">
<strong>Regola 2</strong>
</span><span class="sxs-lookup"><span data-stu-id="270ac-234">
<strong>Rule 2</strong>
</span></span><ul>
<li><span data-ttu-id="270ac-235">Fonte di finanziamento 3: 250,00 (= 750,00 – 50,00 – 450,00)</span><span class="sxs-lookup"><span data-stu-id="270ac-235">Funding source 3: 250.00 (= 750.00 – 50.00 – 450.00)</span></span></li>
</ul><span data-ttu-id="270ac-236">
<strong>Regola 3</strong>
</span><span class="sxs-lookup"><span data-stu-id="270ac-236">
<strong>Rule 3</strong>
</span></span><ul>
<li><span data-ttu-id="270ac-237">Fonte di finanziamento 1: 3.850,00 (= 5.000,00 – 450,00 – 450,00 – 250,00)</span><span class="sxs-lookup"><span data-stu-id="270ac-237">Funding source 1: 3,850.00 (= 5,000.00 – 450.00 – 450.00 – 250.00)</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="270ac-238">Fondi totali distribuiti per ciascuna fonte di finanziamento</span><span class="sxs-lookup"><span data-stu-id="270ac-238">Total funds that are distributed for each funding source</span></span></td>
<td><ul>
<li><span data-ttu-id="270ac-239">Fonte di finanziamento 1: 3.850,00</span><span class="sxs-lookup"><span data-stu-id="270ac-239">Funding source 1: 3,850.00</span></span></li>
<li><span data-ttu-id="270ac-240">Fonte di finanziamento 2: 500,00</span><span class="sxs-lookup"><span data-stu-id="270ac-240">Funding source 2: 500.00</span></span></li>
<li><span data-ttu-id="270ac-241">Fonte di finanziamento 3: 750,00</span><span class="sxs-lookup"><span data-stu-id="270ac-241">Funding source 3: 750.00</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="billing-rules"></a><span data-ttu-id="270ac-242">Regole di fatturazione</span><span class="sxs-lookup"><span data-stu-id="270ac-242">Billing rules</span></span>
<span data-ttu-id="270ac-243">Nel contratto di progetto negoziato con il cliente vengono definiti tempi e modalità per poter fatturare al cliente un lavoro nell'ambito di un progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-243">When you negotiate a project contract with a customer, you define how and when you can invoice the customer for work on a project.</span></span> <span data-ttu-id="270ac-244">Dopo aver impostato il progetto e il relativo contratto, è possibile stabilire le regole di fatturazione del progetto stesso.</span><span class="sxs-lookup"><span data-stu-id="270ac-244">After you set up the project contract and the project, you can set up billing rules for the project.</span></span> <span data-ttu-id="270ac-245">Tali regole si basano sui termini specificati nel contratto di progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-245">Billing rules are based on the project terms that are specified in the project contract.</span></span> <span data-ttu-id="270ac-246">Le regole di fatturazione che è possibile creare dipendono dai termini del contratto di progetto e dal tipo di progetto, ad esempio Tempistica e materiali o A prezzi fissi, associato alla regola di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="270ac-246">The billing rules that you can create depend on the terms of the project contract and the project type, such as Time and material or Fixed-price, that you associate with the billing rule.</span></span> <span data-ttu-id="270ac-247">È possibile creare più di una regola di fatturazione per un contratto di progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-247">You can create more than one billing rule for a project contract.</span></span> <span data-ttu-id="270ac-248">È inoltre possibile assegnare una regola di fatturazione a più progetti associati allo stesso contratto di progetto e applicare termini di fatturazione simili.</span><span class="sxs-lookup"><span data-stu-id="270ac-248">You can also assign a billing rule to multiple projects that are associated with the same project contract and have similar billing terms.</span></span> 

<span data-ttu-id="270ac-249">Si possono impostare i seguenti tipi di regole di fatturazione:</span><span class="sxs-lookup"><span data-stu-id="270ac-249">You can set up the following types of billing rules:</span></span>

-   <span data-ttu-id="270ac-250">**Unità di consegna** – Fatturazione al cliente dopo il completamento di un'unità di consegna.</span><span class="sxs-lookup"><span data-stu-id="270ac-250">**Unit of delivery** – Invoice a customer when you complete a unit of delivery.</span></span> <span data-ttu-id="270ac-251">L'utente definisce le unità di consegna all'interno del contratto.</span><span class="sxs-lookup"><span data-stu-id="270ac-251">You define the units of delivery in the contract.</span></span>
-   <span data-ttu-id="270ac-252">**Stato** – Fatturazione al cliente dopo il completamento di una percentuale di progetto specificata.</span><span class="sxs-lookup"><span data-stu-id="270ac-252">**Progress** – Invoice a customer when you complete a specified percentage of the project.</span></span> <span data-ttu-id="270ac-253">È possibile impostare una regola di fatturazione per calcolare automaticamente la percentuale di lavoro completato, oppure è possibile calcolare manualmente la percentuale di lavoro completato e l'importo da fatturare al cliente.</span><span class="sxs-lookup"><span data-stu-id="270ac-253">You can set up a billing rule to automatically calculate the percentage of work completed, or you can manually calculate the percentage of work completed and the amount to invoice the customer.</span></span>
-   <span data-ttu-id="270ac-254">**Punto cardine** – Fatturazione a un cliente per l'intero importo relativo a un punto cardine di un progetto quando viene raggiunto tale punto cardine.</span><span class="sxs-lookup"><span data-stu-id="270ac-254">**Milestone** – Invoice a customer for the full amount of a project milestone when the milestone is reached.</span></span>
-   <span data-ttu-id="270ac-255">**Commissioni** - Fatturazione a un cliente per i servizi forniti più una commissione di gestione, in genere costituita da una percentuale del costo dei servizi.</span><span class="sxs-lookup"><span data-stu-id="270ac-255">**Fee** – Invoice a customer for your services plus a management fee, which is typically a percentage of the cost of services.</span></span>
-   <span data-ttu-id="270ac-256">**Tempistica e materiali** - Fatturazione a un cliente per il valore di tempo e i materiali utilizzati per un progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-256">**Time and material** – Invoice a customer for the value of time and materials that are used on a project.</span></span>

<span data-ttu-id="270ac-257">Per tutti i tipi di regole di fatturazione, è possibile specificare una percentuale di ritenuta detratta dalle fatture cliente finché un progetto non raggiunge una fase concordata.</span><span class="sxs-lookup"><span data-stu-id="270ac-257">For all types of billing rules, you can specify a retention percentage that is deducted from customer invoices until a project reaches an agreed-upon stage.</span></span> <span data-ttu-id="270ac-258">La percentuale di ritenuta pagamento è specificata nel contratto di progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-258">The payment retention percentage is specified in the project contract.</span></span> <span data-ttu-id="270ac-259">L'importo viene calcolato in base al, e sottratto dal, valore totale delle righe di una fattura cliente.</span><span class="sxs-lookup"><span data-stu-id="270ac-259">The amount is calculated based on, and subtracted from, the total value of the lines in a customer invoice.</span></span> 

<span data-ttu-id="270ac-260">Per le regole di fatturazione **Tempistica e materiali** e **Progressiva** è possibile assegnare le categorie addebitabili.</span><span class="sxs-lookup"><span data-stu-id="270ac-260">For **Time and material** and **Progress** billing rules, you can assign chargeable categories.</span></span> <span data-ttu-id="270ac-261">Tali categorie indicano le transazioni da includere nelle fatture cliente.</span><span class="sxs-lookup"><span data-stu-id="270ac-261">Chargeable categories indicate the transactions that should be included in customer invoices.</span></span> 

<span data-ttu-id="270ac-262">Quando si desidera fatturare al cliente, l'importo da fatturare per il progetto viene calcolato in base alle regole di fatturazione e viene generata una proposta di fattura di progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-262">When you are ready to invoice the customer, the amount to invoice for the project is calculated based on the billing rules, and a project invoice proposal is generated.</span></span> 

<span data-ttu-id="270ac-263">Nelle sezioni seguenti vengono forniti alcuni esempi che illustrano come impostare e gestire le regole di fatturazione per un progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-263">The following sections provide examples that show how to set up and manage billing rules for a project.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-the-number-of-units-delivered"></a><span data-ttu-id="270ac-264">Esempio: Creare una regola di fatturazione in base al numero di unità consegnate</span><span class="sxs-lookup"><span data-stu-id="270ac-264">Example: Create a billing rule that is based on the number of units delivered</span></span>

<span data-ttu-id="270ac-265">L'organizzazione stipula un contratto fornire a un totale di cinque sessioni di formazione ai dipendenti di un cliente al costo di 10.000 per sessione.</span><span class="sxs-lookup"><span data-stu-id="270ac-265">Your organization enters into an agreement to provide a total of five training sessions to a customer’s employees at a cost of 10,000 per training session.</span></span> <span data-ttu-id="270ac-266">La fatturazione al cliente verrà eseguita dopo ogni sessione di formazione.</span><span class="sxs-lookup"><span data-stu-id="270ac-266">You invoice the customer after each training session.</span></span> 

<span data-ttu-id="270ac-267">Quando si impostano le regole di fatturazione per il contratto, si utilizzano i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="270ac-267">When you set up the billing rules for the contract, you use the following values:</span></span>

-   <span data-ttu-id="270ac-268">L'unità di consegna è la singola sessione di formazione.</span><span class="sxs-lookup"><span data-stu-id="270ac-268">The unit of delivery is one training session.</span></span>
-   <span data-ttu-id="270ac-269">Il prezzo unitario è di 10.000 per sessione di formazione.</span><span class="sxs-lookup"><span data-stu-id="270ac-269">The unit price is 10,000 per training session.</span></span>
-   <span data-ttu-id="270ac-270">Il numero totale di unità è di cinque sessioni di formazione.</span><span class="sxs-lookup"><span data-stu-id="270ac-270">The total number of units is five training sessions.</span></span>

<span data-ttu-id="270ac-271">Dopo aver completato una sessione di formazione, è possibile creare una fattura per l'importo di 10.000 per la prima unità consegnata e inviare la fattura al cliente.</span><span class="sxs-lookup"><span data-stu-id="270ac-271">When you have completed one training session, you can create an invoice for 10,000, for the first unit that was delivered, and send the invoice to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-manual-calculation"></a><span data-ttu-id="270ac-272">Esempio: Creare una regola di fatturazione basata su una percentuale di completamento del progetto specificata (calcolo manuale)</span><span class="sxs-lookup"><span data-stu-id="270ac-272">Example: Create a billing rule that is based on a specified percentage of project completion (manual calculation)</span></span>

<span data-ttu-id="270ac-273">L'organizzazione dell'utente (una società di consulenza software) stipula un contratto con un cliente per sviluppare una parte di un prodotto che il cliente sta realizzando.</span><span class="sxs-lookup"><span data-stu-id="270ac-273">Your organization, a software consulting firm, enters into an agreement with a customer to develop part of a product that the customer is developing.</span></span> <span data-ttu-id="270ac-274">L'organizzazione accetta di consegnare il codice software in un periodo di sei mesi,</span><span class="sxs-lookup"><span data-stu-id="270ac-274">Your organization agrees to deliver the software code over a period of six months.</span></span> <span data-ttu-id="270ac-275">mentre il cliente accetta di corrispondere all'organizzazione un totale di 100.000 per questo lavoro.</span><span class="sxs-lookup"><span data-stu-id="270ac-275">The customer agrees to pay your organization a total of 100,000 for the work.</span></span> <span data-ttu-id="270ac-276">Viene creata una regola di fatturazione per fatturare al cliente in base alla percentuale di lavoro completata nel progetto come specificato nel contratto.</span><span class="sxs-lookup"><span data-stu-id="270ac-276">You create a billing rule to invoice the customer based on the percentage of work that is completed on the project, as specified in the contract.</span></span>

-   <span data-ttu-id="270ac-277">Al termine del primo mese, l'utente incontra il cliente per stabilire la percentuale di lavoro completata</span><span class="sxs-lookup"><span data-stu-id="270ac-277">At the end of the first month, you meet with the customer to determine the percentage of work completed.</span></span> <span data-ttu-id="270ac-278">e in seguito alla revisione del progetto, insieme al cliente, decide che la percentuale di completamento è pari al 15%.</span><span class="sxs-lookup"><span data-stu-id="270ac-278">After you and the customer review the project, you decide that the project is 15 percent completed.</span></span>
-   <span data-ttu-id="270ac-279">Viene pertanto creata una fattura per l'importo di 15.000 (15% di $100.000), successivamente inviata al cliente.</span><span class="sxs-lookup"><span data-stu-id="270ac-279">You create an invoice for 15,000 (15 percent of 100,000) and send it to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-automatic-calculation"></a><span data-ttu-id="270ac-280">Esempio: Creare una regola di fatturazione basata su una percentuale di completamento del progetto specificata (calcolo automatico)</span><span class="sxs-lookup"><span data-stu-id="270ac-280">Example: Create a billing rule that is based on a specified percentage of project completion (automatic calculation)</span></span>

<span data-ttu-id="270ac-281">L'organizzazione, una società di sviluppo software, accetta di sviluppare un pacchetto per la contabilità delle retribuzioni per un cliente al costo di 30.000.</span><span class="sxs-lookup"><span data-stu-id="270ac-281">Your organization, a software development firm, agrees to develop a payroll accounting package for a customer for 30,000.</span></span> <span data-ttu-id="270ac-282">Il cliente accetta di effettuare i pagamenti all'organizzazione in base alla percentuale di lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="270ac-282">The customer agrees to pay your organization based on the percentage of work completed.</span></span> <span data-ttu-id="270ac-283">L'utente stima che i costi di progetto ammontano a 20.000.</span><span class="sxs-lookup"><span data-stu-id="270ac-283">You estimate that the project costs are 20,000.</span></span> <span data-ttu-id="270ac-284">Nel contratto di progetto vengono specificate le categorie di lavoro da utilizzare nel processo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="270ac-284">The project contract specifies the categories of work that you use in the billing process.</span></span> <span data-ttu-id="270ac-285">Vengono quindi impostate le regole di fatturazione che calcolano automaticamente gli importi della fattura per la percentuale di lavoro completato per ogni categoria.</span><span class="sxs-lookup"><span data-stu-id="270ac-285">You set up billing rules that automatically calculate the invoice amounts for the percentage of work that is completed for each category.</span></span> <span data-ttu-id="270ac-286">e viene impostato un budget per ogni categoria:</span><span class="sxs-lookup"><span data-stu-id="270ac-286">You set up a budget for each category:</span></span>

-   <span data-ttu-id="270ac-287">**Sviluppo**: costo di 15.000 e ricavi per 20.000</span><span class="sxs-lookup"><span data-stu-id="270ac-287">**Development** – Cost of 15,000 and revenue of 20,000</span></span>
-   <span data-ttu-id="270ac-288">**Installazione**: costo di 5.000 e ricavi per 10.000</span><span class="sxs-lookup"><span data-stu-id="270ac-288">**Installation** – Cost of 5,000 and revenue of 10,000</span></span>

<span data-ttu-id="270ac-289">Quando si crea una fattura cliente per la prima volta, l'importo della fattura viene calcolato automaticamente in base alle informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="270ac-289">When you create a customer invoice for the first time, the invoice amount is automatically calculated based on the following information:</span></span>

-   <span data-ttu-id="270ac-290">Dopo un mese, il dipendente impegnato nel progetto invia una scheda attività relativa al progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-290">After a month, the worker on the project submits a timesheet for the project.</span></span> <span data-ttu-id="270ac-291">Il costo per le ore di lavoro è di 5.000 per lo sviluppo e di 1.000 per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="270ac-291">The cost of the worker’s hours is 5,000 for development and 1,000 for installation.</span></span> <span data-ttu-id="270ac-292">Il lavoro di sviluppo è completo al 33% (5.000 in costi effettivi /15.000 in costi di budget), mentre il lavoro di installazione è completo al 20% (1.000 in costi effettivi /5.000 in costi di budget).</span><span class="sxs-lookup"><span data-stu-id="270ac-292">The development work is 33 percent completed (5,000 actual cost/15,000 budget cost), and the installation work is 20 percent completed (1,000 actual cost/5,000 budget cost).</span></span>
-   <span data-ttu-id="270ac-293">L'importo della fattura, pari a 8.667, verrà calcolato automaticamente (il 33% di 20.000 + il 20% di 10.000).</span><span class="sxs-lookup"><span data-stu-id="270ac-293">The invoice amount of 8,667 is automatically calculated (33 percent of 20,000 + 20 percent of 10,000).</span></span>
-   <span data-ttu-id="270ac-294">Viene pertanto creata una fattura per l'importo di 8.667 successivamente inviata al cliente.</span><span class="sxs-lookup"><span data-stu-id="270ac-294">You create an invoice for 8,667 and send it to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-agreed-upon-milestones"></a><span data-ttu-id="270ac-295">Esempio: Creare una regola di fatturazione basata su punti cardine stabiliti</span><span class="sxs-lookup"><span data-stu-id="270ac-295">Example: Create a billing rule that is based on agreed-upon milestones</span></span>

<span data-ttu-id="270ac-296">L'organizzazione dell'utente, una società di consulenza gestionale, acconsente di condurre una ricerca di mercato su un prodotto consumer che il cliente prevede di vendere.</span><span class="sxs-lookup"><span data-stu-id="270ac-296">Your organization, a management consulting firm, agrees to conduct market research for a consumer product that the customer plans to sell.</span></span> <span data-ttu-id="270ac-297">Il cliente accetta di utilizzare i servizi dell'utente per un periodo di tre mesi, a partire da marzo, e acconsente al pagamento di 50.000 all'organizzazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="270ac-297">The customer agrees to use your services for a period of three months, starting in March, and agrees to pay your organization 50,000.</span></span> <span data-ttu-id="270ac-298">Il progetto è costituito da tre punti cardine:</span><span class="sxs-lookup"><span data-stu-id="270ac-298">The project has three milestones:</span></span>

-   <span data-ttu-id="270ac-299">Punto cardine 1: raccolta dei dati sui consumatori (31 marzo)</span><span class="sxs-lookup"><span data-stu-id="270ac-299">Milestone 1: Collect consumer data – March 31</span></span>
-   <span data-ttu-id="270ac-300">Punto cardine 2: analisi dei dati sui consumatori (30 aprile)</span><span class="sxs-lookup"><span data-stu-id="270ac-300">Milestone 2: Analyze consumer data – April 30</span></span>
-   <span data-ttu-id="270ac-301">Punto cardine 3: presentazione di una proposta di fattibilità per il prodotto (31 maggio).</span><span class="sxs-lookup"><span data-stu-id="270ac-301">Milestone 3: Present a product viability proposal – May 31</span></span>

<span data-ttu-id="270ac-302">Il cliente accetta di pagare all'organizzazione 10.000 per il primo punto cardine, 20.000 per il secondo punto cardine e 20.000 per il terzo punto cardine.</span><span class="sxs-lookup"><span data-stu-id="270ac-302">The customer agrees to pay your organization 10,000 for the first milestone, 20,000 for the second milestone, and 20,000 for the third milestone.</span></span> 

<span data-ttu-id="270ac-303">Quando imposta il contratto di progetto, l'organizzazione accetta di fatturare al cliente in base al punto cardine completato.</span><span class="sxs-lookup"><span data-stu-id="270ac-303">When you set up the project contract, you agree to bill the customer based on the milestone that has been completed.</span></span> <span data-ttu-id="270ac-304">L'impostazione delle regole di fatturazione è costituita dai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="270ac-304">The billing rule setup includes the following steps:</span></span>

-   <span data-ttu-id="270ac-305">Definizione delle fasi di progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-305">Define the project milestones.</span></span>
-   <span data-ttu-id="270ac-306">Definire l'importo da fatturare al cliente quando viene ogni punto cardine è completato.</span><span class="sxs-lookup"><span data-stu-id="270ac-306">Define the amount to invoice the customer when each milestone is completed.</span></span>

<span data-ttu-id="270ac-307">Quando si completa il primo punto cardine, il 31 marzo, si contrassegna il punto cardine come completato, quindi si crea una fattura per l'importo di 10.000 e si invia al cliente.</span><span class="sxs-lookup"><span data-stu-id="270ac-307">When the first milestone is completed on March 31, you mark the milestone as completed, and then create an invoice for 10,000 and send it to the customer.</span></span> <span data-ttu-id="270ac-308">Non è possibile creare una fattura per un punto cardine finché il punto cardine non è contrassegnato come completo.</span><span class="sxs-lookup"><span data-stu-id="270ac-308">You can’t create an invoice for a milestone until you have marked the milestone as completed.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-services-plus-a-management-fee"></a><span data-ttu-id="270ac-309">Esempio: Creare una regola di fatturazione basata sui servizi forniti più una commissione di gestione</span><span class="sxs-lookup"><span data-stu-id="270ac-309">Example: Create a billing rule that is based on services plus a management fee</span></span>

<span data-ttu-id="270ac-310">L'organizzazione dell'utente, una società di consulenza gestionale, accetta di condurre una ricerca di mercato per valutare la fattibilità di un prodotto che il cliente, un società di vendita al dettaglio, sta sviluppando.</span><span class="sxs-lookup"><span data-stu-id="270ac-310">Your organization, a management consulting firm, agrees to conduct market research to evaluate the viability of a product that the customer, a retail company, is developing.</span></span> <span data-ttu-id="270ac-311">Le condizioni del contratto indicano che l'organizzazione dovrà fornire i servizi di tre consulenti gestionali principali che condurranno la ricerca su basi di tempistica e di materiali.</span><span class="sxs-lookup"><span data-stu-id="270ac-311">The terms of the agreement specify that you will provide the services of your top three management consultants, who will conduct the research on a time-and-materials basis.</span></span> <span data-ttu-id="270ac-312">Il cliente accetta di corrispondere 100 per ciascuna ora, oltre a una commissione di gestione pari al 10% per le ore di consulenza attribuite al progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-312">The customer agrees to pay 100 per hour, plus a 10 percent management fee for the consulting hours that are charged to the project.</span></span> 

<span data-ttu-id="270ac-313">Durante l'impostazione del contratto di progetto viene creata una regola di fatturazione che consente di aggiungere una commissione di gestione del 10% alle ore di consulenza attribuite al progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-313">When you set up the project contract, create a billing rule to add a 10 percent management fee to the consulting hours that are charged to the project.</span></span> 

<span data-ttu-id="270ac-314">Quando si crea una fattura per il cliente, a quest'ultimo vengono addebitati una commissione di gestione del 10% insieme al costo delle ore di consulenza.</span><span class="sxs-lookup"><span data-stu-id="270ac-314">When you create an invoice for the customer, the customer is billed a 10 percent management fee plus the cost of the consulting hours.</span></span> <span data-ttu-id="270ac-315">Se ad esempio il totale delle ore di lavoro sul progetto dei tre consulenti è di 200 ore, viene creata una fattura per l'importo di 22.000 in base al calcolo seguente:</span><span class="sxs-lookup"><span data-stu-id="270ac-315">For example, if the three consultants worked a total of 200 hours on the project, an invoice for 22,000 is created based on the following calculation:</span></span>

-   <span data-ttu-id="270ac-316">200 ore al costo di 100 all'ora = 20.000</span><span class="sxs-lookup"><span data-stu-id="270ac-316">200 hours at 100 per hour = 20,000</span></span>
-   <span data-ttu-id="270ac-317">commissione di gestione del 10% = 2.000</span><span class="sxs-lookup"><span data-stu-id="270ac-317">10 percent management fee = 2,000</span></span>
-   <span data-ttu-id="270ac-318">Importo totale fattura = 22.000</span><span class="sxs-lookup"><span data-stu-id="270ac-318">Total invoice amount = 22,000</span></span>

<span data-ttu-id="270ac-319">Se le commissioni sono tassabili per un cliente e si seleziona una fascia IVA nel contratto di progetto, la fascia IVA verrà immessa automaticamente in una regola di fatturazione per le commissioni.</span><span class="sxs-lookup"><span data-stu-id="270ac-319">If fees are taxable to a customer, and you select a sales tax group in the project contract, the sales tax group is automatically entered in a billing rule for fees.</span></span>

### <a name="example-create-a-billing-rule-for-the-value-of-time-and-materials"></a><span data-ttu-id="270ac-320">Esempio: Creazione di una regola di fatturazione per il valore delle ore di lavoro e dei materiali</span><span class="sxs-lookup"><span data-stu-id="270ac-320">Example: Create a billing rule for the value of time and materials</span></span>

<span data-ttu-id="270ac-321">L'organizzazione, una società di consulenza software, ha stipulato un contratto in base al quale cinque consulenti tecnici lavoreranno su un progetto di sviluppo software per un cliente per i sei mesi successivi.</span><span class="sxs-lookup"><span data-stu-id="270ac-321">Your organization, a software consulting firm, agrees to provide five technical consultants to work on a software development project for a customer for the next six months.</span></span> <span data-ttu-id="270ac-322">Il cliente accetta di pagare 150 per ogni ora di consulenza, più il costo della cancelleria.</span><span class="sxs-lookup"><span data-stu-id="270ac-322">The customer agrees to pay 150 for each consulting hour, plus the cost of office supplies.</span></span> <span data-ttu-id="270ac-323">L'organizzazione invierà una fattura al cliente alla fine di ogni mese.</span><span class="sxs-lookup"><span data-stu-id="270ac-323">Your organization sends an invoice to the customer at the end of each month.</span></span> 

<span data-ttu-id="270ac-324">Al momento di impostare il contratto di progetto, l'utente accetta di fatturare ogni mese al cliente le ore di lavoro e i materiali per il progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-324">When you set up the project contract, you agree to bill the customer each month for time and materials on the project.</span></span> <span data-ttu-id="270ac-325">L'utente crea una regola di fatturazione che include le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="270ac-325">You create a billing rule that includes the following information:</span></span>

-   <span data-ttu-id="270ac-326">Il periodo del contratto è di sei mesi.</span><span class="sxs-lookup"><span data-stu-id="270ac-326">The contract period is six months.</span></span>
-   <span data-ttu-id="270ac-327">Il tempo di consulenza viene calcolato alla tariffa di 150 all'ora.</span><span class="sxs-lookup"><span data-stu-id="270ac-327">Consulting time is calculated at a rate of 150 per hour.</span></span>
-   <span data-ttu-id="270ac-328">La cancelleria viene fatturata in base al costo e il costo totale del progetto non deve superare 10.000.</span><span class="sxs-lookup"><span data-stu-id="270ac-328">Office supplies are invoiced at cost, and the total cost for the project must not exceed 10,000.</span></span>
-   <span data-ttu-id="270ac-329">L'utente crea una fattura cliente alla fine di ogni mese di calendario per tutta la durata del progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-329">You create a customer invoice at the end of each calendar month during the project.</span></span>

<span data-ttu-id="270ac-330">Durante il primo mese, i consulenti registrano 800 ore di lavoro totali nell'ambito del progetto.</span><span class="sxs-lookup"><span data-stu-id="270ac-330">During the first month, a total of 800 hours are recorded by the consultants on the project.</span></span> <span data-ttu-id="270ac-331">Il costo della cancelleria addebitato al progetto è di 2.000.</span><span class="sxs-lookup"><span data-stu-id="270ac-331">The cost of office supplies that are charged to the project is 2,000.</span></span> <span data-ttu-id="270ac-332">Alla fine del mese, l'utente crea quindi una fattura per un importo di 122.000, calcolato nel modo seguente: 800 ore al costo di 150 all'ora più 2.000 per gli articoli di cancelleria.</span><span class="sxs-lookup"><span data-stu-id="270ac-332">Therefore, at the end of the month, you create an invoice for 122,000, which is calculated as 800 hours at 150 per hour, plus 2,000 for office supplies.</span></span>




