---
title: Concetti di congedo e assenza
description: In questo argomento vengono descritti i concetti di congedo e assenza e il modo in cui sono determinati i saldi permesso.
author: jcart
manager: AnnBe
ms.date: 01/03/2019
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: a388e0efe6c19a3aabe04e7fff039ce11ae023c4
ms.openlocfilehash: 563593d6c93b0488c681f5b43004f5c0d22cc004
ms.contentlocale: it-it
ms.lasthandoff: 01/07/2019

---

# <a name="leave-and-absence-concepts"></a><span data-ttu-id="2c2fe-103">Concetti di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="2c2fe-103">Leave and absence concepts</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2c2fe-104">I concetti e termini descritti in questo argomento consentono di determinare il modo in cui vengono concessi permessi a un dipendente e il modo in cui vengono calcolati i saldi permesso di quel dipendente.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-104">The concepts and terms that are described in this topic can help you determine how an employee is awarded time off, and how that employee's time balances are calculated.</span></span> <span data-ttu-id="2c2fe-105">Per ulteriori informazioni sulla gestione di congedi e assenze, vedere [Gestione di congedo e assenza](https://docs.microsoft.com/dynamics365/unified-operations/talent/leave-absence-overview).</span><span class="sxs-lookup"><span data-stu-id="2c2fe-105">For more information about leave and absence management, see [Leave and absence management](https://docs.microsoft.com/dynamics365/unified-operations/talent/leave-absence-overview).</span></span>

## <a name="leave-plan-details"></a><span data-ttu-id="2c2fe-106">Dettagli del piano di congedo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-106">Leave plan details</span></span>

### <a name="start-date"></a><span data-ttu-id="2c2fe-107">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="2c2fe-107">Start date</span></span>

<span data-ttu-id="2c2fe-108">La data di inizio è la data in cui ha inizio l'elaborazione degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-108">The start date is the date when accrual processing begins.</span></span> <span data-ttu-id="2c2fe-109">La data di inizio funge anche da data di ricorrenza utilizzata per calcolare gli importi riportabili in avanti.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-109">The start date also serves as the anniversary date that is used to calculate carry-forward amounts.</span></span>

## <a name="accruals"></a><span data-ttu-id="2c2fe-110">Ratei</span><span class="sxs-lookup"><span data-stu-id="2c2fe-110">Accruals</span></span>

<span data-ttu-id="2c2fe-111">Gli accumuli determinano quando e con quale frequenza vengono concessi permessi a un dipendente.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-111">Accruals determine when and how often an employee is awarded time off.</span></span> <span data-ttu-id="2c2fe-112">I criteri relativi a quando gli accumuli devono essere concessi e quelli relativi alla ripartizione sono definiti nella sezione **Accumuli** quando si configura il piano di congedo e assenza.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-112">Policies about when accruals should be awarded and policies about proration are defined in the **Accruals** section when setting up the leave and absence plan.</span></span>

### <a name="accrual-frequency"></a><span data-ttu-id="2c2fe-113">Frequenza dell'accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-113">Accrual frequency</span></span>

<span data-ttu-id="2c2fe-114">La frequenza dell'accumulo definisce la frequenza di accumulo o concessione di congedi.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-114">The accrual frequency defines how often leave is accrued or awarded.</span></span> <span data-ttu-id="2c2fe-115">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c2fe-115">The following options are available:</span></span>

- <span data-ttu-id="2c2fe-116">Giornaliera</span><span class="sxs-lookup"><span data-stu-id="2c2fe-116">Daily</span></span>
- <span data-ttu-id="2c2fe-117">Settimanale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-117">Weekly</span></span>
- <span data-ttu-id="2c2fe-118">Bisettimanale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-118">Biweekly</span></span>
- <span data-ttu-id="2c2fe-119">Quindicinale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-119">Semimonthly</span></span>
- <span data-ttu-id="2c2fe-120">Mensile</span><span class="sxs-lookup"><span data-stu-id="2c2fe-120">Monthly</span></span>
- <span data-ttu-id="2c2fe-121">Trimestrale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-121">Quarterly</span></span>
- <span data-ttu-id="2c2fe-122">Biennale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-122">Semiannually</span></span>
- <span data-ttu-id="2c2fe-123">Annualmente</span><span class="sxs-lookup"><span data-stu-id="2c2fe-123">Annually</span></span>
- <span data-ttu-id="2c2fe-124">Nessuna priorità</span><span class="sxs-lookup"><span data-stu-id="2c2fe-124">None</span></span>

### <a name="accrual-period-basis"></a><span data-ttu-id="2c2fe-125">Base del periodo di accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-125">Accrual period basis</span></span>

<span data-ttu-id="2c2fe-126">La base del periodo di accumulo determina la data che viene utilizzata per calcolare i periodi di accumulo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-126">The accrual period basis determines the date that is used to calculate accrual periods.</span></span> <span data-ttu-id="2c2fe-127">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c2fe-127">The following options are available:</span></span>

- <span data-ttu-id="2c2fe-128">**Data di inizio piano**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-128">**Plan start date**</span></span>
- <span data-ttu-id="2c2fe-129">**Data specifica dipendente** - Quando questa opzione è selezionata, il valore determina l'origine del valore di data iniziale utilizzato per calcolare i periodi di accumulo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-129">**Employee specific date** – When this option is selected, the value determines the source of the initial date value that is used to calculate accrual periods.</span></span> <span data-ttu-id="2c2fe-130">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c2fe-130">The following options are available:</span></span>

    - <span data-ttu-id="2c2fe-131">Personalizzata</span><span class="sxs-lookup"><span data-stu-id="2c2fe-131">Custom</span></span>
    - <span data-ttu-id="2c2fe-132">Data di ricorrenza annuale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-132">Anniversary date</span></span>
    - <span data-ttu-id="2c2fe-133">Data di assunzione originale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-133">Original hire date</span></span>
    - <span data-ttu-id="2c2fe-134">Data di anzianità</span><span class="sxs-lookup"><span data-stu-id="2c2fe-134">Seniority date</span></span>
    - <span data-ttu-id="2c2fe-135">Data di inizio rettificata del lavoratore</span><span class="sxs-lookup"><span data-stu-id="2c2fe-135">Worker's adjusted start date</span></span>
    - <span data-ttu-id="2c2fe-136">Data di inizio del lavoratore</span><span class="sxs-lookup"><span data-stu-id="2c2fe-136">Worker's start date</span></span>

### <a name="accrual-award-date"></a><span data-ttu-id="2c2fe-137">Data concessione accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-137">Accrual award date</span></span>

<span data-ttu-id="2c2fe-138">La data di concessione accumulo determina quando a un dipendente viene concesso un permesso.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-138">The accrual award date determines when an employee is awarded time off.</span></span> <span data-ttu-id="2c2fe-139">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c2fe-139">The following options are available:</span></span>

- <span data-ttu-id="2c2fe-140">**Fine del periodo di accumulo** - Al dipendente verrà concesso un permesso l'ultimo giorno del periodo di premio.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-140">**Accrual period end date** – The employee will be awarded time off on the last day of the award period.</span></span>

    <span data-ttu-id="2c2fe-141">Per accumulare l'importo corretto, il processo di accumulo deve includere l'intero periodo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-141">To accrue the correct amount, the accrual process must include the whole period.</span></span> <span data-ttu-id="2c2fe-142">Ad esempio, il periodo di accumulo va dal 1° gennaio 2018 al 31 gennaio 2018.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-142">For example, the accrual period is January 1, 2018, through January 31, 2018.</span></span> <span data-ttu-id="2c2fe-143">In questo caso, affinché gennaio sia incluso, l'accumulo deve essere eseguito per il 1° febbraio 2018.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-143">In this case, for January to be included, the accrual must be run for February 1, 2018.</span></span>

- <span data-ttu-id="2c2fe-144">**Inizio del periodo di accumulo** - Al dipendente verrà concesso un permesso il primo giorno del periodo di premio.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-144">**Accrual period start date** – The employee will be awarded time off on the first day of the award period.</span></span>

### <a name="accrual-policy-on-enrollment"></a><span data-ttu-id="2c2fe-145">Criteri di accumulo all'iscrizione</span><span class="sxs-lookup"><span data-stu-id="2c2fe-145">Accrual policy on enrollment</span></span>

<span data-ttu-id="2c2fe-146">I criteri di accumulo all'iscrizione definiscono il modo di calcolo dell'accumulo quando un dipendente viene iscritto a metà di un periodo di accumulo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-146">The accrual policy on enrollment defines how accrual is calculated when an employee is enrolled in the middle of an accrual period.</span></span> <span data-ttu-id="2c2fe-147">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c2fe-147">The following options are available:</span></span>

- <span data-ttu-id="2c2fe-148">**Ripartito** - L'intervallo di date tra la data di iscrizione e la data di inizio viene utilizzato per determinare la differenza in giorni.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-148">**Prorated** – The date range between the enrollment date and the start date is used to determine the difference in days.</span></span> <span data-ttu-id="2c2fe-149">Tale differenza viene applicata quando si elaborano gli accumuli.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-149">That difference is applied when accruals are processed.</span></span>
- <span data-ttu-id="2c2fe-150">**Accumulo completo** - L'importo di accumulo completo, basato sul livello, viene concesso durante la prima elaborazione dell'accumulo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-150">**Full accrual** – The full accrual amount, based on the tier, is awarded during the first accrual processing.</span></span>
- <span data-ttu-id="2c2fe-151">**Nessun accumulo** - Non viene concesso alcun accumulo fino al periodo di accumulo successivo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-151">**No accrual** – No accrual is awarded until the next accrual period.</span></span>

### <a name="accrual-policy-on-unenrollment"></a><span data-ttu-id="2c2fe-152">Criteri di accumulo all'annullamento dell'iscrizione</span><span class="sxs-lookup"><span data-stu-id="2c2fe-152">Accrual policy on unenrollment</span></span>

<span data-ttu-id="2c2fe-153">I criteri di accumulo all'annullamento dell'iscrizione definiscono il modo di calcolo dell'accumulo quando l'iscrizione di un dipendente viene annullata a metà di un periodo di accumulo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-153">The accrual policy on unenrollment defines how accrual is calculated when an employee is unenrolled in the middle of an accrual period.</span></span> <span data-ttu-id="2c2fe-154">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c2fe-154">The following options are available:</span></span>

- <span data-ttu-id="2c2fe-155">**Ripartito** - L'intervallo di date tra la data di iscrizione e la data di inizio viene utilizzato per determinare la differenza in giorni.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-155">**Prorated** – The date range between the enrollment date and the start date is used to determine the difference in days.</span></span> <span data-ttu-id="2c2fe-156">Tale differenza viene applicata quando si elaborano gli accumuli.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-156">That difference is applied when accruals are processed.</span></span>
- <span data-ttu-id="2c2fe-157">**Accumulo completo** - L'importo di accumulo completo, basato sul livello, viene concesso durante la prima elaborazione dell'accumulo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-157">**Full accrual** – The full accrual amount, based on the tier, is awarded during the first accrual processing.</span></span>
- <span data-ttu-id="2c2fe-158">**Nessun accumulo** - Non viene concesso alcun accumulo fino al periodo di accumulo successivo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-158">**No accrual** – No accrual is awarded until the next accrual period.</span></span>

## <a name="accrual-schedule"></a><span data-ttu-id="2c2fe-159">Programmazione dell'accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-159">Accrual schedule</span></span>

<span data-ttu-id="2c2fe-160">La programmazione dell'accumulo determina il modo in cui un dipendente accumula permessi e gli importi che il dipendente accumulerà e riporterà.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-160">The accrual schedule determines how an employee will accrue time off, and what amounts that employee will accrue and carry forward.</span></span> <span data-ttu-id="2c2fe-161">È possibile creare livelli di modo che i permessi siano concessi in base a livelli differenti.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-161">Tiers can be created so that time off is awarded based on different levels.</span></span>

### <a name="months-of-service"></a><span data-ttu-id="2c2fe-162">Mesi di servizio</span><span class="sxs-lookup"><span data-stu-id="2c2fe-162">Months of service</span></span>

<span data-ttu-id="2c2fe-163">Il valore **Mesi di servizio** definisce il numero minimo di mesi che i dipendenti devono lavorare per avere diritto ad accumuli.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-163">The **Months of service** value defines the minimum number of months that employees must work to be entitled to accruals.</span></span> <span data-ttu-id="2c2fe-164">Se non è richiesto un minimo per i dipendenti, impostare il valore su **0**.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-164">If no minimum is required for employees, set the value to **0**.</span></span>

### <a name="hours-worked"></a><span data-ttu-id="2c2fe-165">Ore lavorate</span><span class="sxs-lookup"><span data-stu-id="2c2fe-165">Hours worked</span></span>

<span data-ttu-id="2c2fe-166">Il valore **Ore lavorate** definisce il numero minimo di ore che i dipendenti devono lavorare per periodo di accumulo per avere diritto ad accumuli.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-166">The **Hours worked** value defines the minimum number of hours that employees must work per accrual period to be entitled to accruals.</span></span> <span data-ttu-id="2c2fe-167">Se non è richiesto un minimo per i dipendenti, impostare il valore su **0**.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-167">If no minimum is required for employees, set the value to **0**.</span></span>

### <a name="accrual-amount"></a><span data-ttu-id="2c2fe-168">Importo accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-168">Accrual amount</span></span>

<span data-ttu-id="2c2fe-169">L'importo di accumulo è il numero di ore o giorni che i dipendenti accumuleranno per periodo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-169">The accrual amount is the number of hours or days that employees will accrue per period.</span></span> <span data-ttu-id="2c2fe-170">Il periodo è basato sulla frequenza dell'accumulo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-170">The period is based on the accrual frequency.</span></span>

### <a name="minimum-balance"></a><span data-ttu-id="2c2fe-171">Saldo minimo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-171">Minimum balance</span></span>

<span data-ttu-id="2c2fe-172">Un valore negativo può essere utilizzato per il saldo minimo se i dipendenti possono richiedere più congedi di quelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-172">A negative value can be used for the minimum balance if employees can request more leave than they have available.</span></span>

### <a name="maximum-carry-forward"></a><span data-ttu-id="2c2fe-173">Riporto massimo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-173">Maximum carry-forward</span></span>

<span data-ttu-id="2c2fe-174">Il processo di accumulo rettificherà i saldi congedo che superano il saldo riporto massimo alla ricorrenza della data di inizio.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-174">The accrual process will adjust leave balances that exceed the maximum carry-forward balance on the anniversary of the start date.</span></span>

### <a name="grant-amount"></a><span data-ttu-id="2c2fe-175">Importo concesso</span><span class="sxs-lookup"><span data-stu-id="2c2fe-175">Grant amount</span></span>

<span data-ttu-id="2c2fe-176">L'importo concesso è il numero iniziale di ore o giorni concessi ai dipendenti quando si iscrivono per la prima volta al piano di congedo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-176">The grant amount is the initial number of hours or days that employees are granted when they first enroll in the leave plan.</span></span> <span data-ttu-id="2c2fe-177">Non si ha accumulo dell'importo per ogni periodo di accumulo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-177">The amount doesn't accrue for each accrual period.</span></span>

## <a name="enrollments-and-balances"></a><span data-ttu-id="2c2fe-178">Iscrizioni e saldi</span><span class="sxs-lookup"><span data-stu-id="2c2fe-178">Enrollments and balances</span></span>

### <a name="enrollment-date"></a><span data-ttu-id="2c2fe-179">Data di iscrizione</span><span class="sxs-lookup"><span data-stu-id="2c2fe-179">Enrollment date</span></span>

<span data-ttu-id="2c2fe-180">La data di iscrizione determina quando un dipendente può iniziare ad accumulare permessi.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-180">The enrollment date determines when an employee can start to accrue time off.</span></span> <span data-ttu-id="2c2fe-181">Ad esempio, se un dipendente viene iscritto a un piano di ferie il 15 giugno 2018, non può accumulare permessi prima del 15 giugno 2018.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-181">For example, if an employee is enrolled in a vacation plan on June 15, 2018, she can't accrue any time off before June 15, 2018.</span></span>

### <a name="current-balance"></a><span data-ttu-id="2c2fe-182">Saldo corrente</span><span class="sxs-lookup"><span data-stu-id="2c2fe-182">Current balance</span></span>

<span data-ttu-id="2c2fe-183">Il saldo corrente è l'importo di congedo disponibile per le richieste di permesso.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-183">The current balance is the amount of leave that is available for time off requests.</span></span> <span data-ttu-id="2c2fe-184">Questo importo include accumuli, richieste approvate e rettifiche fino alla data corrente.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-184">This amount includes accruals, approved requests, and adjustments through the current date.</span></span>

### <a name="current-balance-examples"></a><span data-ttu-id="2c2fe-185">Esempi di saldo corrente</span><span class="sxs-lookup"><span data-stu-id="2c2fe-185">Current balance examples</span></span>

#### <a name="annual-plan"></a><span data-ttu-id="2c2fe-186">Piano annuale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-186">Annual plan</span></span>

<span data-ttu-id="2c2fe-187">**Configurazione piano**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-187">**Plan setup**</span></span>

| <span data-ttu-id="2c2fe-188">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-188">Plan start date</span></span> | <span data-ttu-id="2c2fe-189">Data di iscrizione</span><span class="sxs-lookup"><span data-stu-id="2c2fe-189">Enrollment date</span></span> | <span data-ttu-id="2c2fe-190">Frequenza accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-190">Accrual frequency</span></span> | <span data-ttu-id="2c2fe-191">Base periodo di accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-191">Accrual period basis</span></span> | <span data-ttu-id="2c2fe-192">Data concessione accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-192">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="2c2fe-193">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-193">1/1/2018</span></span>        | <span data-ttu-id="2c2fe-194">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-194">1/1/2018</span></span>        | <span data-ttu-id="2c2fe-195">Annuale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-195">Annual</span></span>            | <span data-ttu-id="2c2fe-196">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-196">Plan start date</span></span>      | <span data-ttu-id="2c2fe-197">Fine del periodo di accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-197">End of accrual period</span></span> |

<span data-ttu-id="2c2fe-198">Gli accumuli sono elaborati il 1° gennaio 2019 (1/1/2019), di modo che sia incluso l'intero periodo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-198">Accruals are processed on January 1, 2019 (1/1/2019), so that that whole period is included.</span></span>

<span data-ttu-id="2c2fe-199">**Risultati**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-199">**Results**</span></span>

| <span data-ttu-id="2c2fe-200">Importo accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-200">Accrual amount</span></span> | <span data-ttu-id="2c2fe-201">Saldo minimo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-201">Minimum balance</span></span> | <span data-ttu-id="2c2fe-202">Riporto massimo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-202">Maximum carry-forward</span></span> | <span data-ttu-id="2c2fe-203">Importo richiesta</span><span class="sxs-lookup"><span data-stu-id="2c2fe-203">Request amount</span></span> | <span data-ttu-id="2c2fe-204">Saldo corrente (al 1/1/2019)</span><span class="sxs-lookup"><span data-stu-id="2c2fe-204">Current balance (as of 1/1/2019)</span></span> |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| <span data-ttu-id="2c2fe-205">200</span><span class="sxs-lookup"><span data-stu-id="2c2fe-205">200</span></span>            | <span data-ttu-id="2c2fe-206">0</span><span class="sxs-lookup"><span data-stu-id="2c2fe-206">0</span></span>               | <span data-ttu-id="2c2fe-207">120</span><span class="sxs-lookup"><span data-stu-id="2c2fe-207">120</span></span>                   | <span data-ttu-id="2c2fe-208">40</span><span class="sxs-lookup"><span data-stu-id="2c2fe-208">40</span></span>             | <span data-ttu-id="2c2fe-209">160</span><span class="sxs-lookup"><span data-stu-id="2c2fe-209">160</span></span>                              |

<span data-ttu-id="2c2fe-210">Saldo corrente (160) = Importo accumulo (200) – Importo richiesta (40)</span><span class="sxs-lookup"><span data-stu-id="2c2fe-210">Current balance (160) = Accrual amount (200) – Request amount (40)</span></span>

#### <a name="semimonthly-plan"></a><span data-ttu-id="2c2fe-211">Piano quindicinale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-211">Semimonthly plan</span></span>

<span data-ttu-id="2c2fe-212">**Configurazione piano**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-212">**Plan setup**</span></span>

| <span data-ttu-id="2c2fe-213">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-213">Plan start date</span></span> | <span data-ttu-id="2c2fe-214">Data di iscrizione</span><span class="sxs-lookup"><span data-stu-id="2c2fe-214">Enrollment date</span></span> | <span data-ttu-id="2c2fe-215">Frequenza accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-215">Accrual frequency</span></span> | <span data-ttu-id="2c2fe-216">Base periodo di accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-216">Accrual period basis</span></span> | <span data-ttu-id="2c2fe-217">Data concessione accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-217">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="2c2fe-218">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-218">1/1/2018</span></span>        | <span data-ttu-id="2c2fe-219">2/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-219">2/1/2018</span></span>        | <span data-ttu-id="2c2fe-220">Quindicinale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-220">Semimonthly</span></span>       | <span data-ttu-id="2c2fe-221">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-221">Plan start date</span></span>      | <span data-ttu-id="2c2fe-222">Fine del periodo di accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-222">End of accrual period</span></span> |

<span data-ttu-id="2c2fe-223">Gli accumuli sono elaborati il 1° maggio 2018 (1/5/2018), di modo che sia incluso l'intero periodo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-223">Accruals are processed on May 1, 2018 (5/1/2018), so that that whole period is included.</span></span>

<span data-ttu-id="2c2fe-224">**Risultati**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-224">**Results**</span></span>

| <span data-ttu-id="2c2fe-225">Importo accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-225">Accrual amount</span></span> | <span data-ttu-id="2c2fe-226">Saldo minimo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-226">Minimum balance</span></span> | <span data-ttu-id="2c2fe-227">Riporto massimo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-227">Maximum carry-forward</span></span> | <span data-ttu-id="2c2fe-228">Importo richiesta</span><span class="sxs-lookup"><span data-stu-id="2c2fe-228">Request amount</span></span> | <span data-ttu-id="2c2fe-229">Saldo corrente (al 1/1/2019)</span><span class="sxs-lookup"><span data-stu-id="2c2fe-229">Current balance (as of 1/1/2019)</span></span> |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| <span data-ttu-id="2c2fe-230">5</span><span class="sxs-lookup"><span data-stu-id="2c2fe-230">5</span></span>              | <span data-ttu-id="2c2fe-231">0</span><span class="sxs-lookup"><span data-stu-id="2c2fe-231">0</span></span>               | <span data-ttu-id="2c2fe-232">120</span><span class="sxs-lookup"><span data-stu-id="2c2fe-232">120</span></span>                   | <span data-ttu-id="2c2fe-233">8</span><span class="sxs-lookup"><span data-stu-id="2c2fe-233">8</span></span>              | <span data-ttu-id="2c2fe-234">22</span><span class="sxs-lookup"><span data-stu-id="2c2fe-234">22</span></span>                               |

<span data-ttu-id="2c2fe-235">Saldo corrente (22) = Importo accumulo (5 × 6) – Importo richiesta (8)</span><span class="sxs-lookup"><span data-stu-id="2c2fe-235">Current balance (22) = Accrual amount (5 × 6) – Request amount (8)</span></span>

#### <a name="monthly-plan"></a><span data-ttu-id="2c2fe-236">Piano mensile</span><span class="sxs-lookup"><span data-stu-id="2c2fe-236">Monthly plan</span></span>

<span data-ttu-id="2c2fe-237">**Configurazione piano**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-237">**Plan setup**</span></span>

| <span data-ttu-id="2c2fe-238">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-238">Plan start date</span></span> | <span data-ttu-id="2c2fe-239">Data di iscrizione</span><span class="sxs-lookup"><span data-stu-id="2c2fe-239">Enrollment date</span></span> | <span data-ttu-id="2c2fe-240">Frequenza accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-240">Accrual frequency</span></span> | <span data-ttu-id="2c2fe-241">Base periodo di accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-241">Accrual period basis</span></span> | <span data-ttu-id="2c2fe-242">Data concessione accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-242">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="2c2fe-243">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-243">1/1/2018</span></span>        | <span data-ttu-id="2c2fe-244">2/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-244">2/1/2018</span></span>        | <span data-ttu-id="2c2fe-245">Quindicinale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-245">Semimonthly</span></span>       | <span data-ttu-id="2c2fe-246">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-246">Plan start date</span></span>      | <span data-ttu-id="2c2fe-247">Fine del periodo di accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-247">End of accrual period</span></span> |

<span data-ttu-id="2c2fe-248">Gli accumuli sono elaborati il 1° maggio 2018 (1/5/2018), di modo che sia incluso l'intero periodo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-248">Accruals are processed on May 1, 2018 (5/1/2018), so that that whole period is included.</span></span>

<span data-ttu-id="2c2fe-249">**Risultati**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-249">**Results**</span></span>

| <span data-ttu-id="2c2fe-250">Importo accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-250">Accrual amount</span></span> | <span data-ttu-id="2c2fe-251">Saldo minimo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-251">Minimum balance</span></span> | <span data-ttu-id="2c2fe-252">Riporto massimo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-252">Maximum carry-forward</span></span> | <span data-ttu-id="2c2fe-253">Importo richiesta</span><span class="sxs-lookup"><span data-stu-id="2c2fe-253">Request amount</span></span> | <span data-ttu-id="2c2fe-254">Saldo corrente (al 1/1/2019)</span><span class="sxs-lookup"><span data-stu-id="2c2fe-254">Current balance (as of 1/1/2019)</span></span> |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| <span data-ttu-id="2c2fe-255">5</span><span class="sxs-lookup"><span data-stu-id="2c2fe-255">5</span></span>              | <span data-ttu-id="2c2fe-256">0</span><span class="sxs-lookup"><span data-stu-id="2c2fe-256">0</span></span>               | <span data-ttu-id="2c2fe-257">120</span><span class="sxs-lookup"><span data-stu-id="2c2fe-257">120</span></span>                   | <span data-ttu-id="2c2fe-258">8</span><span class="sxs-lookup"><span data-stu-id="2c2fe-258">8</span></span>              | <span data-ttu-id="2c2fe-259">7</span><span class="sxs-lookup"><span data-stu-id="2c2fe-259">7</span></span>                                |

<span data-ttu-id="2c2fe-260">Saldo corrente (7) = Importo accumulo (5 × 3) – Importo richiesta (8)</span><span class="sxs-lookup"><span data-stu-id="2c2fe-260">Current balance (7) = Accrual amount (5 × 3) – Request amount (8)</span></span>

### <a name="forecasted-balance"></a><span data-ttu-id="2c2fe-261">Saldo previsto</span><span class="sxs-lookup"><span data-stu-id="2c2fe-261">Forecasted balance</span></span>

<span data-ttu-id="2c2fe-262">Il *saldo previsto* è l'importo di congedo disponibile in una data futura.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-262">The *forecasted balance* is the amount of leave that is available on a future date.</span></span> <span data-ttu-id="2c2fe-263">Gli accumuli e le rettifiche di riporto sono previste fino a tale data.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-263">Accruals and carry-forward adjustments are forecasted up to that date.</span></span>

<span data-ttu-id="2c2fe-264">Viene utilizzata la seguente formula:</span><span class="sxs-lookup"><span data-stu-id="2c2fe-264">The following formula is used:</span></span>

<span data-ttu-id="2c2fe-265">Saldo previsto lunedì = Saldo corrente – Richieste + Accumuli – Rettifica di riporto</span><span class="sxs-lookup"><span data-stu-id="2c2fe-265">Monday forecasted balance = Current balance – Requests + Accruals – Carry-forward adjustment</span></span>

### <a name="forecasted-balance-examples"></a><span data-ttu-id="2c2fe-266">Esempi di saldo previsto</span><span class="sxs-lookup"><span data-stu-id="2c2fe-266">Forecasted balance examples</span></span>

#### <a name="annual-plan"></a><span data-ttu-id="2c2fe-267">Piano annuale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-267">Annual plan</span></span>

<span data-ttu-id="2c2fe-268">**Configurazione piano**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-268">**Plan setup**</span></span>

| <span data-ttu-id="2c2fe-269">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-269">Plan start date</span></span> | <span data-ttu-id="2c2fe-270">Data di iscrizione</span><span class="sxs-lookup"><span data-stu-id="2c2fe-270">Enrollment date</span></span> | <span data-ttu-id="2c2fe-271">Frequenza accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-271">Accrual frequency</span></span> | <span data-ttu-id="2c2fe-272">Base periodo di accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-272">Accrual period basis</span></span> | <span data-ttu-id="2c2fe-273">Data concessione accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-273">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="2c2fe-274">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-274">1/1/2018</span></span>        | <span data-ttu-id="2c2fe-275">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-275">1/1/2018</span></span>        | <span data-ttu-id="2c2fe-276">Annuale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-276">Annual</span></span>            | <span data-ttu-id="2c2fe-277">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-277">Plan start date</span></span>      | <span data-ttu-id="2c2fe-278">Fine del periodo di accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-278">End of accrual period</span></span> |

<span data-ttu-id="2c2fe-279">Gli accumuli sono elaborati il 15 febbraio 2019 (15/2/2019), di modo che sia incluso l'intero periodo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-279">Accruals are processed on February 15, 2019 (2/15/2019), so that that whole period is included.</span></span>

<span data-ttu-id="2c2fe-280">**Risultati**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-280">**Results**</span></span>

| <span data-ttu-id="2c2fe-281">Importo accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-281">Accrual amount</span></span> | <span data-ttu-id="2c2fe-282">Saldo minimo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-282">Minimum balance</span></span> | <span data-ttu-id="2c2fe-283">Riporto massimo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-283">Maximum carry-forward</span></span> | <span data-ttu-id="2c2fe-284">Saldo corrente</span><span class="sxs-lookup"><span data-stu-id="2c2fe-284">Current balance</span></span> | <span data-ttu-id="2c2fe-285">Saldo previsto (al 15/2/2019)</span><span class="sxs-lookup"><span data-stu-id="2c2fe-285">Forecasted balance (as of 2/15/2019)</span></span> |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| <span data-ttu-id="2c2fe-286">20</span><span class="sxs-lookup"><span data-stu-id="2c2fe-286">20</span></span>             | <span data-ttu-id="2c2fe-287">0</span><span class="sxs-lookup"><span data-stu-id="2c2fe-287">0</span></span>               | <span data-ttu-id="2c2fe-288">20</span><span class="sxs-lookup"><span data-stu-id="2c2fe-288">20</span></span>                    | <span data-ttu-id="2c2fe-289">40</span><span class="sxs-lookup"><span data-stu-id="2c2fe-289">40</span></span>              | <span data-ttu-id="2c2fe-290">40</span><span class="sxs-lookup"><span data-stu-id="2c2fe-290">40</span></span>                                   |

<span data-ttu-id="2c2fe-291">Saldo previsto (40) = Saldo accumulo (20) + Saldo corrente (40) – Rettifica di riporto (20)</span><span class="sxs-lookup"><span data-stu-id="2c2fe-291">Forecasted balance (40) = Accrual amount (20) + Current balance (40) – Carry-forward adjustment (20)</span></span>

#### <a name="semimonthly-plan"></a><span data-ttu-id="2c2fe-292">Piano quindicinale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-292">Semimonthly plan</span></span>

<span data-ttu-id="2c2fe-293">**Configurazione piano**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-293">**Plan setup**</span></span>

| <span data-ttu-id="2c2fe-294">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-294">Plan start date</span></span> | <span data-ttu-id="2c2fe-295">Data di iscrizione</span><span class="sxs-lookup"><span data-stu-id="2c2fe-295">Enrollment date</span></span> | <span data-ttu-id="2c2fe-296">Frequenza accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-296">Accrual frequency</span></span> | <span data-ttu-id="2c2fe-297">Base periodo di accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-297">Accrual period basis</span></span> | <span data-ttu-id="2c2fe-298">Data concessione accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-298">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="2c2fe-299">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-299">1/1/2018</span></span>        | <span data-ttu-id="2c2fe-300">2/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-300">2/1/2018</span></span>        | <span data-ttu-id="2c2fe-301">Quindicinale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-301">Semimonthly</span></span>       | <span data-ttu-id="2c2fe-302">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-302">Plan start date</span></span>      | <span data-ttu-id="2c2fe-303">Fine del periodo di accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-303">End of accrual period</span></span> |

<span data-ttu-id="2c2fe-304">Gli accumuli sono elaborati il 15 febbraio 2019 (15/2/2019), di modo che sia incluso l'intero periodo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-304">Accruals are processed on February 15, 2019 (2/15/2019), so that that whole period is included.</span></span>

<span data-ttu-id="2c2fe-305">**Risultati**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-305">**Results**</span></span>

| <span data-ttu-id="2c2fe-306">Importo accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-306">Accrual amount</span></span> | <span data-ttu-id="2c2fe-307">Saldo minimo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-307">Minimum balance</span></span> | <span data-ttu-id="2c2fe-308">Riporto massimo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-308">Maximum carry-forward</span></span> | <span data-ttu-id="2c2fe-309">Saldo corrente</span><span class="sxs-lookup"><span data-stu-id="2c2fe-309">Current balance</span></span> | <span data-ttu-id="2c2fe-310">Saldo previsto (al 15/2/2019)</span><span class="sxs-lookup"><span data-stu-id="2c2fe-310">Forecasted balance (as of 2/15/2019)</span></span> |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| <span data-ttu-id="2c2fe-311">5</span><span class="sxs-lookup"><span data-stu-id="2c2fe-311">5</span></span>              | <span data-ttu-id="2c2fe-312">0</span><span class="sxs-lookup"><span data-stu-id="2c2fe-312">0</span></span>               | <span data-ttu-id="2c2fe-313">20</span><span class="sxs-lookup"><span data-stu-id="2c2fe-313">20</span></span>                    | <span data-ttu-id="2c2fe-314">40</span><span class="sxs-lookup"><span data-stu-id="2c2fe-314">40</span></span>              | <span data-ttu-id="2c2fe-315">35</span><span class="sxs-lookup"><span data-stu-id="2c2fe-315">35</span></span>                                   |

<span data-ttu-id="2c2fe-316">Saldo previsto (35) = Saldo accumulo (5 × 3) + Saldo corrente (40) – Rettifica di riporto (20)</span><span class="sxs-lookup"><span data-stu-id="2c2fe-316">Forecasted balance (35) = Accrual amount (5 × 3) + Current balance (40) – Carry-forward adjustment (20)</span></span>

#### <a name="monthly-plan"></a><span data-ttu-id="2c2fe-317">Piano mensile</span><span class="sxs-lookup"><span data-stu-id="2c2fe-317">Monthly plan</span></span>

<span data-ttu-id="2c2fe-318">**Configurazione piano**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-318">**Plan setup**</span></span>

| <span data-ttu-id="2c2fe-319">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-319">Plan start date</span></span> | <span data-ttu-id="2c2fe-320">Data di iscrizione</span><span class="sxs-lookup"><span data-stu-id="2c2fe-320">Enrollment date</span></span> | <span data-ttu-id="2c2fe-321">Frequenza accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-321">Accrual frequency</span></span> | <span data-ttu-id="2c2fe-322">Base periodo di accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-322">Accrual period basis</span></span> | <span data-ttu-id="2c2fe-323">Data concessione accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-323">Accrual award date</span></span>    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| <span data-ttu-id="2c2fe-324">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-324">1/1/2018</span></span>        | <span data-ttu-id="2c2fe-325">2/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-325">2/1/2018</span></span>        | <span data-ttu-id="2c2fe-326">Quindicinale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-326">Semimonthly</span></span>       | <span data-ttu-id="2c2fe-327">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-327">Plan start date</span></span>      | <span data-ttu-id="2c2fe-328">Fine del periodo di accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-328">End of accrual period</span></span> |

<span data-ttu-id="2c2fe-329">Gli accumuli sono elaborati il 15 febbraio 2019 (15/2/2019), di modo che sia incluso l'intero periodo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-329">Accruals are processed on February 15, 2019 (2/15/2019), so that that whole period is included.</span></span>

<span data-ttu-id="2c2fe-330">**Risultati**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-330">**Results**</span></span>

| <span data-ttu-id="2c2fe-331">Importo accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-331">Accrual amount</span></span> | <span data-ttu-id="2c2fe-332">Saldo minimo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-332">Minimum balance</span></span> | <span data-ttu-id="2c2fe-333">Riporto massimo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-333">Maximum carry-forward</span></span> | <span data-ttu-id="2c2fe-334">Saldo corrente</span><span class="sxs-lookup"><span data-stu-id="2c2fe-334">Current balance</span></span> | <span data-ttu-id="2c2fe-335">Saldo previsto (al 15/2/2019)</span><span class="sxs-lookup"><span data-stu-id="2c2fe-335">Forecasted balance (as of 2/15/2019)</span></span> |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| <span data-ttu-id="2c2fe-336">10</span><span class="sxs-lookup"><span data-stu-id="2c2fe-336">10</span></span>             | <span data-ttu-id="2c2fe-337">0</span><span class="sxs-lookup"><span data-stu-id="2c2fe-337">0</span></span>               | <span data-ttu-id="2c2fe-338">20</span><span class="sxs-lookup"><span data-stu-id="2c2fe-338">20</span></span>                    | <span data-ttu-id="2c2fe-339">40</span><span class="sxs-lookup"><span data-stu-id="2c2fe-339">40</span></span>              | <span data-ttu-id="2c2fe-340">30</span><span class="sxs-lookup"><span data-stu-id="2c2fe-340">30</span></span>                                   |

<span data-ttu-id="2c2fe-341">Saldo previsto (30) = Saldo accumulo (10 × 1) + Saldo corrente (40) – Rettifica di riporto (20)</span><span class="sxs-lookup"><span data-stu-id="2c2fe-341">Forecasted balance (30) = Accrual amount (10 × 1) + Current balance (40) – Carry-forward adjustment (20)</span></span>

### <a name="proration-balance-examples"></a><span data-ttu-id="2c2fe-342">Esempi di saldo ripartizione</span><span class="sxs-lookup"><span data-stu-id="2c2fe-342">Proration balance examples</span></span>

#### <a name="prorated-monthly-plan"></a><span data-ttu-id="2c2fe-343">Piano mensile ripartito</span><span class="sxs-lookup"><span data-stu-id="2c2fe-343">Prorated monthly plan</span></span>

<span data-ttu-id="2c2fe-344">**Configurazione piano**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-344">**Plan setup**</span></span>

| <span data-ttu-id="2c2fe-345">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-345">Plan start date</span></span> | <span data-ttu-id="2c2fe-346">Frequenza accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-346">Accrual frequency</span></span> | <span data-ttu-id="2c2fe-347">Base periodo di accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-347">Accrual period basis</span></span> |
|-----------------|-------------------|----------------------|
| <span data-ttu-id="2c2fe-348">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-348">1/1/2018</span></span>        | <span data-ttu-id="2c2fe-349">Mensile</span><span class="sxs-lookup"><span data-stu-id="2c2fe-349">Monthly</span></span>           | <span data-ttu-id="2c2fe-350">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-350">Plan start date</span></span>      |

<span data-ttu-id="2c2fe-351">**Risultati**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-351">**Results**</span></span>

| <span data-ttu-id="2c2fe-352">Dipendente</span><span class="sxs-lookup"><span data-stu-id="2c2fe-352">Employee</span></span>            | <span data-ttu-id="2c2fe-353">Mesi di servizio</span><span class="sxs-lookup"><span data-stu-id="2c2fe-353">Months of service</span></span> | <span data-ttu-id="2c2fe-354">Data di iscrizione</span><span class="sxs-lookup"><span data-stu-id="2c2fe-354">Enrollment date</span></span> | <span data-ttu-id="2c2fe-355">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="2c2fe-355">Start date</span></span> | <span data-ttu-id="2c2fe-356">Importo accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-356">Accrual amount</span></span> | <span data-ttu-id="2c2fe-357">Accumulo processo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-357">Process accrual</span></span> | <span data-ttu-id="2c2fe-358">Stato patrimoniale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-358">Balance</span></span> |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| <span data-ttu-id="2c2fe-359">Jeannette Nicholson</span><span class="sxs-lookup"><span data-stu-id="2c2fe-359">Jeannette Nicholson</span></span> | <span data-ttu-id="2c2fe-360">0,00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-360">0.00</span></span>              | <span data-ttu-id="2c2fe-361">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-361">6/1/2018</span></span>        | <span data-ttu-id="2c2fe-362">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-362">6/1/2018</span></span>   | <span data-ttu-id="2c2fe-363">1,00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-363">1.00</span></span>           | <span data-ttu-id="2c2fe-364">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-364">9/1/2018</span></span>        | <span data-ttu-id="2c2fe-365">3,00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-365">3.00</span></span>    |
| <span data-ttu-id="2c2fe-366">Jay Norman</span><span class="sxs-lookup"><span data-stu-id="2c2fe-366">Jay Norman</span></span>          | <span data-ttu-id="2c2fe-367">0,00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-367">0.00</span></span>              | <span data-ttu-id="2c2fe-368">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-368">6/15/2018</span></span>       | <span data-ttu-id="2c2fe-369">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-369">6/15/2018</span></span>  | <span data-ttu-id="2c2fe-370">1,00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-370">1.00</span></span>           | <span data-ttu-id="2c2fe-371">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-371">9/1/2018</span></span>        | <span data-ttu-id="2c2fe-372">2.53</span><span class="sxs-lookup"><span data-stu-id="2c2fe-372">2.53</span></span>    |

#### <a name="full-accrual-monthly-plan"></a><span data-ttu-id="2c2fe-373">Piano mensile accumulo completo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-373">Full accrual monthly plan</span></span>

<span data-ttu-id="2c2fe-374">**Configurazione piano**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-374">**Plan setup**</span></span>

| <span data-ttu-id="2c2fe-375">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-375">Plan start date</span></span> | <span data-ttu-id="2c2fe-376">Frequenza accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-376">Accrual frequency</span></span> | <span data-ttu-id="2c2fe-377">Base periodo di accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-377">Accrual period basis</span></span> |
|-----------------|-------------------|----------------------|
| <span data-ttu-id="2c2fe-378">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-378">1/1/2018</span></span>        | <span data-ttu-id="2c2fe-379">Mensile</span><span class="sxs-lookup"><span data-stu-id="2c2fe-379">Monthly</span></span>           | <span data-ttu-id="2c2fe-380">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-380">Plan start date</span></span>      |

<span data-ttu-id="2c2fe-381">**Risultati**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-381">**Results**</span></span>

| <span data-ttu-id="2c2fe-382">Dipendente</span><span class="sxs-lookup"><span data-stu-id="2c2fe-382">Employee</span></span>            | <span data-ttu-id="2c2fe-383">Mesi di servizio</span><span class="sxs-lookup"><span data-stu-id="2c2fe-383">Months of service</span></span> | <span data-ttu-id="2c2fe-384">Data di iscrizione</span><span class="sxs-lookup"><span data-stu-id="2c2fe-384">Enrollment date</span></span> | <span data-ttu-id="2c2fe-385">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="2c2fe-385">Start date</span></span> | <span data-ttu-id="2c2fe-386">Importo accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-386">Accrual amount</span></span> | <span data-ttu-id="2c2fe-387">Accumulo processo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-387">Process accrual</span></span> | <span data-ttu-id="2c2fe-388">Stato patrimoniale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-388">Balance</span></span> |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| <span data-ttu-id="2c2fe-389">Jeannette Nicholson</span><span class="sxs-lookup"><span data-stu-id="2c2fe-389">Jeannette Nicholson</span></span> | <span data-ttu-id="2c2fe-390">0,00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-390">0.00</span></span>              | <span data-ttu-id="2c2fe-391">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-391">6/1/2018</span></span>        | <span data-ttu-id="2c2fe-392">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-392">6/1/2018</span></span>   | <span data-ttu-id="2c2fe-393">1,00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-393">1.00</span></span>           | <span data-ttu-id="2c2fe-394">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-394">9/1/2018</span></span>        | <span data-ttu-id="2c2fe-395">3,00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-395">3.00</span></span>    |
| <span data-ttu-id="2c2fe-396">Jay Norman</span><span class="sxs-lookup"><span data-stu-id="2c2fe-396">Jay Norman</span></span>          | <span data-ttu-id="2c2fe-397">0,00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-397">0.00</span></span>              | <span data-ttu-id="2c2fe-398">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-398">6/15/2018</span></span>       | <span data-ttu-id="2c2fe-399">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-399">6/15/2018</span></span>  | <span data-ttu-id="2c2fe-400">1,00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-400">1.00</span></span>           | <span data-ttu-id="2c2fe-401">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-401">9/1/2018</span></span>        | <span data-ttu-id="2c2fe-402">3,00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-402">3.00</span></span>    |

#### <a name="no-accrual-monthly-plan"></a><span data-ttu-id="2c2fe-403">Piano mensile senza accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-403">No accrual monthly plan</span></span>

<span data-ttu-id="2c2fe-404">**Configurazione piano**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-404">**Plan setup**</span></span>

| <span data-ttu-id="2c2fe-405">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-405">Plan start date</span></span> | <span data-ttu-id="2c2fe-406">Frequenza accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-406">Accrual frequency</span></span> | <span data-ttu-id="2c2fe-407">Base periodo di accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-407">Accrual period basis</span></span> |
|-----------------|-------------------|----------------------|
| <span data-ttu-id="2c2fe-408">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-408">1/1/2018</span></span>        | <span data-ttu-id="2c2fe-409">Mensile</span><span class="sxs-lookup"><span data-stu-id="2c2fe-409">Monthly</span></span>           | <span data-ttu-id="2c2fe-410">Data di inizio piano</span><span class="sxs-lookup"><span data-stu-id="2c2fe-410">Plan start date</span></span>      |

<span data-ttu-id="2c2fe-411">**Risultati**</span><span class="sxs-lookup"><span data-stu-id="2c2fe-411">**Results**</span></span>

| <span data-ttu-id="2c2fe-412">Dipendente</span><span class="sxs-lookup"><span data-stu-id="2c2fe-412">Employee</span></span>            | <span data-ttu-id="2c2fe-413">Mesi di servizio</span><span class="sxs-lookup"><span data-stu-id="2c2fe-413">Months of service</span></span> | <span data-ttu-id="2c2fe-414">Data di iscrizione</span><span class="sxs-lookup"><span data-stu-id="2c2fe-414">Enrollment date</span></span> | <span data-ttu-id="2c2fe-415">Data di inizio</span><span class="sxs-lookup"><span data-stu-id="2c2fe-415">Start date</span></span> | <span data-ttu-id="2c2fe-416">Importo accumulo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-416">Accrual amount</span></span> | <span data-ttu-id="2c2fe-417">Accumulo processo</span><span class="sxs-lookup"><span data-stu-id="2c2fe-417">Process accrual</span></span> | <span data-ttu-id="2c2fe-418">Stato patrimoniale</span><span class="sxs-lookup"><span data-stu-id="2c2fe-418">Balance</span></span> |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| <span data-ttu-id="2c2fe-419">Jeannette Nicholson</span><span class="sxs-lookup"><span data-stu-id="2c2fe-419">Jeannette Nicholson</span></span> | <span data-ttu-id="2c2fe-420">0,00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-420">0.00</span></span>              | <span data-ttu-id="2c2fe-421">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-421">6/1/2018</span></span>        | <span data-ttu-id="2c2fe-422">6/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-422">6/1/2018</span></span>   | <span data-ttu-id="2c2fe-423">1,00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-423">1.00</span></span>           | <span data-ttu-id="2c2fe-424">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-424">9/1/2018</span></span>        | <span data-ttu-id="2c2fe-425">3,00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-425">3.00</span></span>    |
| <span data-ttu-id="2c2fe-426">Jay Norman</span><span class="sxs-lookup"><span data-stu-id="2c2fe-426">Jay Norman</span></span>          | <span data-ttu-id="2c2fe-427">0,00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-427">0.00</span></span>              | <span data-ttu-id="2c2fe-428">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-428">6/15/2018</span></span>       | <span data-ttu-id="2c2fe-429">6/15/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-429">6/15/2018</span></span>  | <span data-ttu-id="2c2fe-430">1,00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-430">1.00</span></span>           | <span data-ttu-id="2c2fe-431">9/1/2018</span><span class="sxs-lookup"><span data-stu-id="2c2fe-431">9/1/2018</span></span>        | <span data-ttu-id="2c2fe-432">2.00</span><span class="sxs-lookup"><span data-stu-id="2c2fe-432">2.00</span></span>    |

