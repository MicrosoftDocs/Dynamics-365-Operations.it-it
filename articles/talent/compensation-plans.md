---
title: Piani di retribuzione
description: I responsabili di benefit e retribuzione possono utilizzare la gestione della retribuzione per gestire ed elaborare i piani di retribuzione fissa e variabile per i dipendenti dell'organizzazione.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCompensationLevel, HRCCompGrid, HRMCompFixedAction, HRMCompFixedBudget, HRMCompFixedPlanTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 8e7e41756c3be73937ef62523ff6bf41536405b0
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898852"
---
# <a name="compensation-plans"></a><span data-ttu-id="b0d0d-103">Piani di retribuzione</span><span class="sxs-lookup"><span data-stu-id="b0d0d-103">Compensation plans</span></span>

<span data-ttu-id="b0d0d-104">I responsabili di benefit e retribuzione possono utilizzare la gestione della retribuzione per gestire ed elaborare i piani di retribuzione fissa e variabile per i dipendenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-104">Compensation and Benefits Managers can use Compensation management to maintain and process fixed and variable compensation plans for the organization's employees.</span></span>

### <a name="introduction"></a><span data-ttu-id="b0d0d-105">Introduzione</span><span class="sxs-lookup"><span data-stu-id="b0d0d-105">Introduction</span></span>

<span data-ttu-id="b0d0d-106">La gestione delle retribuzioni consente di controllare la liquidazione dei premi e della retribuzione base.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-106">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="b0d0d-107">La retribuzione di base fissa di un dipendente e gli aumenti per merito sono controllati mediante piani di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-107">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="b0d0d-108">È possibile controllare il pagamento degli incentivi, ad esempio il pagamento dei bonus, dei premi produttività, dei diritti di opzione, delle sovvenzioni, oltre che dei premi una tantum, tramite i piani di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-108">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span> 

<span data-ttu-id="b0d0d-109">I dipendenti possono essere iscritti a uno o più piani di entrambi i tipi.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-109">Employees can be enrolled in one or more plans of both types.</span></span> <span data-ttu-id="b0d0d-110">Un dipendente deve soddisfare i seguenti requisiti per poter essere iscritto a un piano di retribuzione:</span><span class="sxs-lookup"><span data-stu-id="b0d0d-110">An employee must meet the following requirements in order to be eligible for enrollment in a compensation plan:</span></span>
-   <span data-ttu-id="b0d0d-111">L'assegnazione di posizione del dipendente deve essere attiva.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-111">The employee must have an active position assignment.</span></span>
-   <span data-ttu-id="b0d0d-112">Il dipendente deve soddisfare i criteri definiti dai criteri di idoneità per un determinato piano di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-112">The employee must meet the criteria that are defined by eligibility rules for a compensation plan.</span></span>

## <a name="compensation-setup"></a><span data-ttu-id="b0d0d-113">Configurazione della retribuzione</span><span class="sxs-lookup"><span data-stu-id="b0d0d-113">Compensation setup</span></span>
<span data-ttu-id="b0d0d-114">La seguente tabella elenca le componenti del processo di retribuzione che possono essere chiamate in causa durante la configurazione dei piani di retribuzione aziendali.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-114">The following table lists components of the compensation process that can be integral in setting up your company's compensation plans.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="b0d0d-115">Componente</span><span class="sxs-lookup"><span data-stu-id="b0d0d-115">Component</span></span></th>
<th><span data-ttu-id="b0d0d-116">Ulteriori informazioni...</span><span class="sxs-lookup"><span data-stu-id="b0d0d-116">More information…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b0d0d-117">Azioni retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="b0d0d-117">Fixed compensation actions</span></span></td>
<td><span data-ttu-id="b0d0d-118">Le azioni di retribuzione fissa hanno due scopi:</span><span class="sxs-lookup"><span data-stu-id="b0d0d-118">Fixed compensation actions accomplish two purposes:</span></span>
<ul>
<li><span data-ttu-id="b0d0d-119">Le azioni possono specificare il tipo di informazioni che deve essere registrato quando una retribuzione dipendente cambia.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-119">Actions can specify the kind of information that must be recorded when an employee’s compensation changes.</span></span> <span data-ttu-id="b0d0d-120">Ad esempio, è possibile richiedere che il motivo una modifica, ad esempio una promozione o una retrocessione, venga registrato.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-120">For example, you can require that the reason a change, such as a promotion or a demotion be recorded.</span></span></li>
<li><span data-ttu-id="b0d0d-121">Le azioni possono assicurare che un calcolo venga applicato durante l'elaborazione dei piani di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-121">Actions can ensure that a calculation is applied when fixed compensation plans are processed.</span></span>  <span data-ttu-id="b0d0d-122">Ad esempio, le azioni di tipo capitale netto confrontano la retribuzione dei dipendenti con il punto di riferimento minimo per il livello del dipendente e garantiscono al dipendente almeno la retribuzione minima.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-122">For example, actions of type Equity will compare the employees pay to the minimum reference point for the level on the employee&#39;s and ensure the employee is getting paid at least the minimum.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b0d0d-123">Livelli</span><span class="sxs-lookup"><span data-stu-id="b0d0d-123">Levels</span></span></td>
<td><span data-ttu-id="b0d0d-124">I livelli sono associati alle mansioni e a qualsiasi posizione correlata a una mansione.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-124">Levels are associated with jobs and any positions that are related to a job reference.</span></span> <span data-ttu-id="b0d0d-125">È possibile creare livelli distinti per i tre tipi di piani di retribuzione: Grado, Fascia e Passaggio.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-125">You can create discrete levels for the three types of compensation plans: Grade, Band, and Step.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b0d0d-126">Matrice utilizzo range retributivo</span><span class="sxs-lookup"><span data-stu-id="b0d0d-126">Range utilization matrix</span></span></td>
<td><span data-ttu-id="b0d0d-127">Le matrici utilizzo range retributivo consentono di trasferire i dipendenti nel punto di controllo per le rispettive mansioni.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-127">A range utilization matrix helps you transition employees to the control point for their jobs.</span></span> <span data-ttu-id="b0d0d-128">Si può ricorrere all'utilizzo del range retributivo anche per verificare l'omogeneità delle tariffe all'interno della società, indipendentemente dal rendimento di un singolo dipendente o dalle prestazioni complessive della società.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-128">You can also use range utilization to control pay rate equity in the company without regard to an individual employee&#39;s performance or the overall performance of the company.</span></span> <span data-ttu-id="b0d0d-129">Ad esempio, i dipendenti che ricevono basse retribuzioni nell'ambito del proprio range retributivo potrebbero ottenere aumenti percentuali maggiori rispetto ai dipendenti che ricevono retribuzioni più elevate nell'ambito del range retributivo stesso.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-129">For example, employees who are paid lower in their range get higher percentage increases than employees who are paid higher in the range.</span></span> <span data-ttu-id="b0d0d-130">In questo modo, è possibile compensare sistematicamente le differenze.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-130">In this manner, you can systematically offset equity differences.</span></span> <span data-ttu-id="b0d0d-131">L'utilizzo del range retributivo viene calcolato nel modo seguente: (frequenza di retribuzione fissa - range retributivo minimo) ÷ (range retributivo massimo - range retributivo minimo).</span><span class="sxs-lookup"><span data-stu-id="b0d0d-131">The range utilization is calculated as follows: (Fixed Pay Rate - Range Minimum) ÷ (Range Maximum - Range Minimum).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b0d0d-132">Impostazioni punti di riferimento</span><span class="sxs-lookup"><span data-stu-id="b0d0d-132">Reference point setups</span></span></td>
<td><span data-ttu-id="b0d0d-133">La configurazione dei punti di riferimento comprende un insieme di punti di riferimento che rappresentano i range retributivi all'interno di una matrice.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-133">A reference point setup includes a set of reference points that represent ranges in a matrix.</span></span> <span data-ttu-id="b0d0d-134">Ciascun range retributivo può essere associato a una tariffa retributiva.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-134">Each range can be associated with a pay rate.</span></span> <span data-ttu-id="b0d0d-135">Ad esempio, i piani del grado avranno spesso punti di riferimento di minimo, punto intermedio e massimo.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-135">For example, grade plans will often have reference points of Minimum, Midpoint, and Maximum.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b0d0d-136">Matrice di retribuzione</span><span class="sxs-lookup"><span data-stu-id="b0d0d-136">Compensation matrix</span></span></td>
<td><span data-ttu-id="b0d0d-137">Una matrice di retribuzione è un insieme di punti di riferimento e di livelli utilizzato per creare una struttura retributiva.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-137">A compensation matrix is the set of reference points and levels that you use to create a compensation structure.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b0d0d-138">Struttura retributiva</span><span class="sxs-lookup"><span data-stu-id="b0d0d-138">Compensation structure</span></span></td>
<td><span data-ttu-id="b0d0d-139">Una struttura retributiva è una matrice di incremento retributivo che presenta range retributivi associati alle tariffe retributive.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-139">A compensation structure is a compensation matrix that has pay rates associated with the reference points for each level.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b0d0d-140">Regole di idoneità</span><span class="sxs-lookup"><span data-stu-id="b0d0d-140">Eligibility rules</span></span></td>
<td><span data-ttu-id="b0d0d-141">Le regole di idoneità vengono utilizzate per identificare i dipendenti nell'ambito di specifici processi, funzioni lavorative, tipi di processo, reparti, sindacati o Paesi di retribuzione coperte da piani di retribuzione specifici.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-141">Eligibility rules are used to identify employees in specific jobs, job functions, job types, departments, labor unions, or compensation regions that are covered by specific compensation plans.</span></span> <span data-ttu-id="b0d0d-142">È necessario creare le regole di idoneità sia per la variabile che i piani di retribuzione fissa per iscrivere i dipendenti al piano.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-142">You must create eligibility rules for both variable and fixed compensation plans in order to enroll employees in the plan.</span></span> <span data-ttu-id="b0d0d-143">Dopo avere specificato le regole di idoneità per un piano di retribuzione, sarà possibile definire i livelli del piano che dovranno essere applicati alle mansioni coperte dal piano.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-143">After eligibility rules are specified for a compensation plan, you can define the levels that should apply to the jobs that are covered by the plan.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b0d0d-144">Frequenze retribuzione</span><span class="sxs-lookup"><span data-stu-id="b0d0d-144">Pay frequencies</span></span></td>
<td><span data-ttu-id="b0d0d-145">Le frequenze di retribuzione vengono utilizzate per definire il periodo per il quale è specificata la retribuzione.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-145">Pay frequencies are used to define the time period for which the compensation is specified.</span></span>  <span data-ttu-id="b0d0d-146">Ad esempio, la frequenza di retribuzione aiuta a comprendere se l'importo della retribuzione viene specificato come retribuzione annuale anziché come tariffa di retribuzione oraria.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-146">For example, the pay frequency helps you understand if the compensation amount is specified as an annual salary versus an hourly pay rate.</span></span> <span data-ttu-id="b0d0d-147">Le frequenze di retribuzione sono inoltre utilizzate per impostare i fattori di conversione che consentono di convertire gli importi retributivi da frequenze di retribuzione mensile, settimanale, bisettimanale e oraria in una frequenza di retribuzione annua.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-147">Pay frequencies are also used to set up conversion factors to convert compensation amounts from monthly, weekly, biweekly and hourly pay frequencies to an annual pay frequency.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b0d0d-148">Paesi di retribuzione</span><span class="sxs-lookup"><span data-stu-id="b0d0d-148">Compensation regions</span></span></td>
<td><span data-ttu-id="b0d0d-149">I Paesi di retribuzione vengono utilizzati per specificare la retribuzione dipendente in base all'ubicazione del luogo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-149">Compensation regions are used to specify employee compensation based on the location of the workplace.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b0d0d-150">Punto di controllo</span><span class="sxs-lookup"><span data-stu-id="b0d0d-150">Control point</span></span></td>
<td><span data-ttu-id="b0d0d-151">Il punto di controllo definisce ciò che si considera essere la tariffa ideale per tutti i dipendenti inclusi in un livello retributivo.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-151">The control point defines what you consider to be the ideal pay rate for all employees at a compensation level.</span></span> <span data-ttu-id="b0d0d-152">Nelle strutture retributive scalari, i punti di controllo corrispondono in genere al punto medio dei singoli range.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-152">For grade plan structures, control points are typically the midpoint of the ranges.</span></span> <span data-ttu-id="b0d0d-153">Le strutture "a fascia" utilizzano raramente i punti di controllo.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-153">Band structures rarely use control points.</span></span> <span data-ttu-id="b0d0d-154">È possibile specificare il punto di controllo di un piano di retribuzione fissa nel modulo Piani di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-154">You can specify the control point for a fixed compensation plan in the Fixed compensation plans form.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b0d0d-155">Funzioni lavorative</span><span class="sxs-lookup"><span data-stu-id="b0d0d-155">Job functions</span></span></td>
<td><span data-ttu-id="b0d0d-156">Le funzioni lavorative vengono utilizzate per classificare e filtrare i piani di retribuzione nei processi specifici.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-156">Job functions are used to classify and filter compensation plans to specific jobs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b0d0d-157">Tipi di processo</span><span class="sxs-lookup"><span data-stu-id="b0d0d-157">Job types</span></span></td>
<td><span data-ttu-id="b0d0d-158">I tipi di processo vengono utilizzati per classificare e filtrare i piani di retribuzione nei processi specifici.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-158">Job types are used to classify and filter compensation plans to specific jobs.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b0d0d-159">Tipi di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="b0d0d-159">Variable compensation types</span></span></td>
<td><span data-ttu-id="b0d0d-160">I tipi di retribuzione variabile, ad esempio un premio in azioni o una gratifica in contanti, vengono impostati nei piani di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-160">Variable compensation types, such as stock awards or cash award bonuses, are set up in variable compensation plans.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b0d0d-161">Griglie retributive</span><span class="sxs-lookup"><span data-stu-id="b0d0d-161">Compensation grids</span></span></td>
<td><span data-ttu-id="b0d0d-162">Le griglie retributive contengono la struttura retributiva.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-162">Compensation grids contain the compensation structure.</span></span>  <span data-ttu-id="b0d0d-163">Le griglie retributive possono essere utilizzate da uno o più piani di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-163">Compensation grids can be used by one or more compensation plans.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b0d0d-164">Piani prestazioni</span><span class="sxs-lookup"><span data-stu-id="b0d0d-164">Performance plans</span></span></td>
<td><span data-ttu-id="b0d0d-165">I piani prestazioni sono utilizzati per associare le prestazioni a una matrice di allocazione, in modo tale da poter utilizzare il piano in una strategia di retribuzione basata sulla produttività.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-165">Performance plans are used to associate performance with an allocation matrix, so that you can use the plan in a pay-for-performance strategy.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b0d0d-166">Valutazioni delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="b0d0d-166">Performance ratings</span></span></td>
<td><span data-ttu-id="b0d0d-167">Le valutazioni delle prestazioni sono utilizzate nei piani prestazioni per stabilire l'importo di un premio di merito o di un premio produttività.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-167">Performance ratings are used in performance plans to determine the amount of a merit award or performance award.</span></span></td>
</tr>
</tbody>
</table>

## <a name="process-events"></a><span data-ttu-id="b0d0d-168">Eventi processo</span><span class="sxs-lookup"><span data-stu-id="b0d0d-168">Process events</span></span>
<span data-ttu-id="b0d0d-169">Gli eventi processo consentono di calcolare le informazioni sulle retribuzioni in un periodo specifico per tutti i dipendenti iscritti a uno o più piani di retribuzione fissa o variabile.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-169">A process event calculates compensation information for a specific period for all employees who are enrolled in one or more fixed or variable compensation plans.</span></span> <span data-ttu-id="b0d0d-170">È possibile eseguire ripetutamente un evento processo per effettuare il test o l'aggiornamento dei risultati retributivi calcolati.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-170">You can run a process event repeatedly to test or update calculated compensation results.</span></span>

<a name="compensation-events"></a><span data-ttu-id="b0d0d-171">Eventi retributivi</span><span class="sxs-lookup"><span data-stu-id="b0d0d-171">Compensation events</span></span>
-------------------

<span data-ttu-id="b0d0d-172">Ogni volta che viene eseguito un evento processo, viene creato un evento retribuzione.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-172">Each time a process event is run, a compensation event is created.</span></span>  <span data-ttu-id="b0d0d-173">Gli eventi retribuzione contengono i risultati del processo retributivo per ciascun dipendente incluso nell'evento processo.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-173">Compensation events contain the results of the compensation process for each employee included in that process event.</span></span>  <span data-ttu-id="b0d0d-174">Quando i calcoli sono corretti, è possibile caricare l'evento retribuzione per aggiornare le voci relative alla retribuzione per i dipendenti interessati dall'evento processo.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-174">When the calculations are correct, you can load the compensation event to update the compensation records for the employees who are affected by the process event.</span></span>

## <a name="recommendations"></a><span data-ttu-id="b0d0d-175">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="b0d0d-175">Recommendations</span></span>
<span data-ttu-id="b0d0d-176">Dopo aver eseguito un evento processo, è possibile suggerire correzioni dell'aumento per merito o dell'importo del premio di un dipendente, in base alle linee guida calcolate per l'evento processo.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-176">After you run a process event, you can recommend adjustments to an employee’s merit increase or award amount, based on the calculated guidelines of the process event.</span></span> <span data-ttu-id="b0d0d-177">Per proporre suggerimenti relativi ai dipendenti, è necessario abilitare i suggerimenti quando si impostano i piani di retribuzione o l'evento processo.</span><span class="sxs-lookup"><span data-stu-id="b0d0d-177">To make recommendations for employees, you must enable recommendations when you set up compensation plans or when you set up the process event.</span></span>



