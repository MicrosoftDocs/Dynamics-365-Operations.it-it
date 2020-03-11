---
title: Organizzare la forza lavoro utilizzando i reparti, le mansioni e le posizioni
description: Reparti, mansioni e posizioni sono elementi organizzativi che vengono gestiti in Risorse umane. Questo articolo descrive le nozioni relative a questi elementi.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmJob, HcmPosition, OMOperatingUnit
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources, Retail
ms.custom: 87933
ms.assetid: eb5dcacb-a5fe-451d-b30a-7ef14da65d81
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 98b9ba7f45a3af38fdd24c09b9a3164d1547a0d5
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009518"
---
# <a name="organize-your-workforce-by-using-departments-jobs-and-positions"></a><span data-ttu-id="4951a-104">Organizzare la forza lavoro utilizzando i reparti, le mansioni e le posizioni</span><span class="sxs-lookup"><span data-stu-id="4951a-104">Organize your workforce by using departments, jobs, and positions</span></span>

<span data-ttu-id="4951a-105">Reparti, mansioni e posizioni sono elementi organizzativi che vengono gestiti in Risorse umane.</span><span class="sxs-lookup"><span data-stu-id="4951a-105">Departments, jobs, and positions are organizational elements that are maintained within Human resources.</span></span> <span data-ttu-id="4951a-106">Questo articolo descrive le nozioni relative a questi elementi.</span><span class="sxs-lookup"><span data-stu-id="4951a-106">This article describes conceptual information about these elements.</span></span> 

<span data-ttu-id="4951a-107">Il seguente esempio viene utilizzato per illustrare i concetti descritti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="4951a-107">The following example is used to illustrate the concepts described in this article.</span></span>

|<span data-ttu-id="4951a-108">**Reparto**</span><span class="sxs-lookup"><span data-stu-id="4951a-108">**Department**</span></span>|<span data-ttu-id="4951a-109">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="4951a-109">**Position**</span></span>|<span data-ttu-id="4951a-110">**Mansione**</span><span class="sxs-lookup"><span data-stu-id="4951a-110">**Job**</span></span>|
|---|---|---|
|<span data-ttu-id="4951a-111">**Vendite**</span><span class="sxs-lookup"><span data-stu-id="4951a-111">**Sales**</span></span>|<span data-ttu-id="4951a-112">Manager vendite (Est)</span><span class="sxs-lookup"><span data-stu-id="4951a-112">Sales manager (East)</span></span>|<span data-ttu-id="4951a-113">Manager vendite</span><span class="sxs-lookup"><span data-stu-id="4951a-113">Sales manager</span></span>|
|<span data-ttu-id="4951a-114">**Vendite**</span><span class="sxs-lookup"><span data-stu-id="4951a-114">**Sales**</span></span>|<span data-ttu-id="4951a-115">Manager vendite (Ovest)</span><span class="sxs-lookup"><span data-stu-id="4951a-115">Sales manager (West)</span></span>|<span data-ttu-id="4951a-116">Manager vendite</span><span class="sxs-lookup"><span data-stu-id="4951a-116">Sales manager</span></span>|
|<span data-ttu-id="4951a-117">**Vendite**</span><span class="sxs-lookup"><span data-stu-id="4951a-117">**Sales**</span></span>|<span data-ttu-id="4951a-118">Manager vendite (Centro)</span><span class="sxs-lookup"><span data-stu-id="4951a-118">Sales manager (Central)</span></span>|<span data-ttu-id="4951a-119">Manager vendite</span><span class="sxs-lookup"><span data-stu-id="4951a-119">Sales manager</span></span>|
|<span data-ttu-id="4951a-120">**Contabilità**</span><span class="sxs-lookup"><span data-stu-id="4951a-120">**Accounting**</span></span>|<span data-ttu-id="4951a-121">Supervisore contabile</span><span class="sxs-lookup"><span data-stu-id="4951a-121">Accounting supervisor</span></span>|<span data-ttu-id="4951a-122">Direttore amministrativo</span><span class="sxs-lookup"><span data-stu-id="4951a-122">Accounting manager</span></span>|
|<span data-ttu-id="4951a-123">**Contabilità**</span><span class="sxs-lookup"><span data-stu-id="4951a-123">**Accounting**</span></span>|<span data-ttu-id="4951a-124">Contabilità A</span><span class="sxs-lookup"><span data-stu-id="4951a-124">Accounting-A</span></span>|<span data-ttu-id="4951a-125">Ragioniere</span><span class="sxs-lookup"><span data-stu-id="4951a-125">Accountant</span></span>|
|<span data-ttu-id="4951a-126">**Risorse umane**</span><span class="sxs-lookup"><span data-stu-id="4951a-126">**Human resources**</span></span>|<span data-ttu-id="4951a-127">Responsabile risorse umane (Est)</span><span class="sxs-lookup"><span data-stu-id="4951a-127">HR manager (East)</span></span>|<span data-ttu-id="4951a-128">Responsabile risorse Umane</span><span class="sxs-lookup"><span data-stu-id="4951a-128">HR manager</span></span>|
|<span data-ttu-id="4951a-129">**Risorse umane**</span><span class="sxs-lookup"><span data-stu-id="4951a-129">**Human resources**</span></span>|<span data-ttu-id="4951a-130">Responsabile risorse umane (Ovest)</span><span class="sxs-lookup"><span data-stu-id="4951a-130">HR manager (West)</span></span>|<span data-ttu-id="4951a-131">Responsabile risorse Umane</span><span class="sxs-lookup"><span data-stu-id="4951a-131">HR manager</span></span>|
|<span data-ttu-id="4951a-132">**Risorse umane**</span><span class="sxs-lookup"><span data-stu-id="4951a-132">**Human resources**</span></span>|<span data-ttu-id="4951a-133">Responsabile risorse umane (Centro)</span><span class="sxs-lookup"><span data-stu-id="4951a-133">HR manager (Central)</span></span>|<span data-ttu-id="4951a-134">Responsabile risorse Umane</span><span class="sxs-lookup"><span data-stu-id="4951a-134">HR manager</span></span>|


 <a name="departments"></a><span data-ttu-id="4951a-135">Reparti</span><span class="sxs-lookup"><span data-stu-id="4951a-135">Departments</span></span>
------------

<span data-ttu-id="4951a-136">Un reparto è un'unità operativa che rappresenta una categoria o un'area funzionale di un'organizzazione, responsabile di un'area specifica dell'organizzazione, ad esempio vendita o contabilità.</span><span class="sxs-lookup"><span data-stu-id="4951a-136">A department is an operating unit that represents a category or functional area of an organization that is responsible for a specific area of the organization, such as sales or accounting.</span></span> <span data-ttu-id="4951a-137">Un reparto viene utilizzato per i report sulle aree funzionali e può avere responsabilità di profitti e perdite.</span><span class="sxs-lookup"><span data-stu-id="4951a-137">A department is used to report on functional areas and may have profit and loss responsibility.</span></span> <span data-ttu-id="4951a-138">Inoltre, un reparto può includere un gruppo di centri di costo.</span><span class="sxs-lookup"><span data-stu-id="4951a-138">Also, a department might include a group of cost centers.</span></span> <span data-ttu-id="4951a-139">Le vendite, la contabilità e le risorse umane sono alcuni esempi di reparti in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4951a-139">Sales, accounting, and human resources are some examples of departments in an organization.</span></span>

## <a name="jobs-and-positions"></a><span data-ttu-id="4951a-140">Mansioni e posizioni</span><span class="sxs-lookup"><span data-stu-id="4951a-140">Jobs and positions</span></span>
<span data-ttu-id="4951a-141">Una mansione è una raccolta di attività e responsabilità proprie della persona assegnata alla mansione.</span><span class="sxs-lookup"><span data-stu-id="4951a-141">A job is a collection of tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="4951a-142">Una posizione è una singola istanza di un processo.</span><span class="sxs-lookup"><span data-stu-id="4951a-142">A position is an individual instance of a job.</span></span> <span data-ttu-id="4951a-143">Le aree di responsabilità, le attività associate alla mansione, le funzioni lavorative, le competenze, le informazioni di formazione e i certificati necessari per una mansione vengono inoltre richiesti per le posizioni associate a una mansione.</span><span class="sxs-lookup"><span data-stu-id="4951a-143">Areas of responsibility, job tasks, job functions, skills, education information, and certificates that are required for a job are also required for positions that are associated with a job.</span></span>
### <a name="job-tasks"></a><span data-ttu-id="4951a-144">Mansioni di lavoro</span><span class="sxs-lookup"><span data-stu-id="4951a-144">Job tasks</span></span>

<span data-ttu-id="4951a-145">È possibile creare attività per una mansione che descrivono le attività di base che un lavoratore in una posizione per tale mansione deve completare.</span><span class="sxs-lookup"><span data-stu-id="4951a-145">You can create job tasks that describe the basic tasks that a worker in a position for that job must complete.</span></span> <span data-ttu-id="4951a-146">La stessa attività associata a una mansione può essere aggiunta a più mansioni e le posizioni di tali mansioni erediteranno tali attività.</span><span class="sxs-lookup"><span data-stu-id="4951a-146">The same job task can be added to multiple jobs, and positions for those jobs will inherit those job tasks.</span></span> <span data-ttu-id="4951a-147">Esempi di attività di mansioni sono elencati nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="4951a-147">Examples of job tasks are listed in the following table.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="4951a-148">Processo</span><span class="sxs-lookup"><span data-stu-id="4951a-148">Job</span></span></th>
<th><span data-ttu-id="4951a-149">Mansione di lavoro</span><span class="sxs-lookup"><span data-stu-id="4951a-149">Job task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4951a-150">Manager vendite</span><span class="sxs-lookup"><span data-stu-id="4951a-150">Sales manager</span></span></td>
<td><ul>
<li><span data-ttu-id="4951a-151"><span class="input">Verifica-prestazioni</span>: verificare le prestazioni di ciascun venditore.</span><span class="sxs-lookup"><span data-stu-id="4951a-151"><span class="input">Perf-review</span> – Review each salesperson’s job performance.</span></span></li>
<li><span data-ttu-id="4951a-152"><span class="input">Verifica-assenze</span>: approvare o rifiutare le richieste o le registrazioni di assenza di ciascun venditore.</span><span class="sxs-lookup"><span data-stu-id="4951a-152"><span class="input">Abs-review</span> – Approve or reject each salesperson’s absence requests or registrations.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4951a-153">Ragioniere</span><span class="sxs-lookup"><span data-stu-id="4951a-153">Accountant</span></span></td>
<td><span data-ttu-id="4951a-154"><span class="input">Report-finanziario</span>: presentare report finanziari settimanali al responsabile finanziario.</span><span class="sxs-lookup"><span data-stu-id="4951a-154"><span class="input">FIN-Report</span> – Present weekly financial reports to chief financial officer.</span></span></td>
</tr>
</tbody>
</table>

### <a name="job-functions"></a><span data-ttu-id="4951a-155">Funzioni lavorative</span><span class="sxs-lookup"><span data-stu-id="4951a-155">Job functions</span></span>

<span data-ttu-id="4951a-156">Le funzioni lavorative sono simili alle attività associate alle mansioni.</span><span class="sxs-lookup"><span data-stu-id="4951a-156">Job functions are like job tasks.</span></span> <span data-ttu-id="4951a-157">Una funzione lavorativa descrive una o più attività, compiti o responsabilità assegnati a una mansione.</span><span class="sxs-lookup"><span data-stu-id="4951a-157">A job function describes one or more tasks, duties or responsibilities that are assigned to a job.</span></span> <span data-ttu-id="4951a-158">Le funzioni lavorative possono essere assegnate alle mansioni e utilizzate per impostare e implementare le regole di idoneità per i piani di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="4951a-158">Job functions can be assigned to jobs and used to set up and implement eligibility rules for compensation plans.</span></span> <span data-ttu-id="4951a-159">Esempi di funzioni di mansioni sono elencati nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="4951a-159">Examples of job functions are listed in the following table.</span></span>

| <span data-ttu-id="4951a-160">Processo</span><span class="sxs-lookup"><span data-stu-id="4951a-160">Job</span></span>           | <span data-ttu-id="4951a-161">Funzione lavorativa</span><span class="sxs-lookup"><span data-stu-id="4951a-161">Job function</span></span>                                                |
|---------------|-------------------------------------------------------------|
| <span data-ttu-id="4951a-162">Manager vendite</span><span class="sxs-lookup"><span data-stu-id="4951a-162">Sales manager</span></span> | <span data-ttu-id="4951a-163">Gestione-persone: gestire le persone di cui si è superiori.</span><span class="sxs-lookup"><span data-stu-id="4951a-163">Mng-people – Manage people who report to you.</span></span>               |
| <span data-ttu-id="4951a-164">Ragioniere</span><span class="sxs-lookup"><span data-stu-id="4951a-164">Accountant</span></span>    | <span data-ttu-id="4951a-165">Revisione-finanziaria: gestire i dati finanziari per un insieme di conti.</span><span class="sxs-lookup"><span data-stu-id="4951a-165">FIN-Review – Maintain financial data for a set of accounts.</span></span> |

### <a name="job-types"></a><span data-ttu-id="4951a-166">Tipi di processo</span><span class="sxs-lookup"><span data-stu-id="4951a-166">Job types</span></span>

<span data-ttu-id="4951a-167">Utilizzare i tipi di mansione per classificare mansioni simili in categorie.</span><span class="sxs-lookup"><span data-stu-id="4951a-167">Use job types to classify similar jobs into categories.</span></span> <span data-ttu-id="4951a-168">I tipi di mansione, proprio come le funzioni lavorative, possono essere assegnati alle mansioni e utilizzati per impostare e implementare le regole di idoneità per i piani di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="4951a-168">Job types, just like job functions, can be assigned to jobs and used to set up and implement eligibility rules for compensation plans.</span></span> <span data-ttu-id="4951a-169">Nel seguente elenco sono inclusi alcuni esempi di tipi di mansione:</span><span class="sxs-lookup"><span data-stu-id="4951a-169">Some examples of job types are included in the following list:</span></span>
-   <span data-ttu-id="4951a-170">A tempo pieno</span><span class="sxs-lookup"><span data-stu-id="4951a-170">Full-time</span></span>
-   <span data-ttu-id="4951a-171">A tempo parziale</span><span class="sxs-lookup"><span data-stu-id="4951a-171">Part-time</span></span>
-   <span data-ttu-id="4951a-172">Stipendio</span><span class="sxs-lookup"><span data-stu-id="4951a-172">Salary</span></span>
-   <span data-ttu-id="4951a-173">Retribuzione oraria</span><span class="sxs-lookup"><span data-stu-id="4951a-173">Hourly pay</span></span>

### <a name="areas-of-responsibility"></a><span data-ttu-id="4951a-174">Aree di responsabilità</span><span class="sxs-lookup"><span data-stu-id="4951a-174">Areas of responsibility</span></span>

<span data-ttu-id="4951a-175">Utilizzare le aree di responsabilità per indicare i ruoli di lavoro, i processi e i prodotti di cui un lavoratore in una posizione di tale mansione è responsabile.</span><span class="sxs-lookup"><span data-stu-id="4951a-175">Use areas of responsibility to indicate the work roles, processes, and products that a worker in a position for that job would be responsible for.</span></span> <span data-ttu-id="4951a-176">Un esempio di un'area di responsabilità per una mansione denominata "Ragioniere" potrebbe essere "Reporting finanziario per il prodotto A".</span><span class="sxs-lookup"><span data-stu-id="4951a-176">An example of an area of responsibility for a job titled “Accountant” might be “Financial reporting for Product A”.</span></span>

<a name="positions"></a><span data-ttu-id="4951a-177">Posizioni</span><span class="sxs-lookup"><span data-stu-id="4951a-177">Positions</span></span>
----------

<span data-ttu-id="4951a-178">Le posizioni sono un elemento importante del livello inferiore di una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="4951a-178">Positions are an important element of the lower level of an organization hierarchy.</span></span> <span data-ttu-id="4951a-179">Una posizione è una singola istanza di un processo.</span><span class="sxs-lookup"><span data-stu-id="4951a-179">A position is an individual instance of a job.</span></span> <span data-ttu-id="4951a-180">Ad esempio, la posizione "Manager vendite (Est") è solo una delle posizioni associate alla mansione "Manager vendite".</span><span class="sxs-lookup"><span data-stu-id="4951a-180">For example, the position, “Sales manager (East),” is just one of the positions that is associated with the job, “Sales manager.”</span></span> <span data-ttu-id="4951a-181">Le posizioni esistono in un reparto e vengono assegnate ai lavoratori.</span><span class="sxs-lookup"><span data-stu-id="4951a-181">Positions exist in a department and are assigned to workers.</span></span>
### <a name="position-creation-and-maintenance"></a><span data-ttu-id="4951a-182">Creazione e gestione di posizioni</span><span class="sxs-lookup"><span data-stu-id="4951a-182">Position creation and maintenance</span></span>

-   <span data-ttu-id="4951a-183">È possibile visualizzare lo storico delle modifiche al sistema relative alle posizioni in una pagina elenco di semplice accesso.</span><span class="sxs-lookup"><span data-stu-id="4951a-183">You can view a history of position-related system changes in an easy-to-access list page.</span></span>
-   <span data-ttu-id="4951a-184">È possibile creare codici motivo che gli utenti possono selezionare quando creano o modificano posizioni.</span><span class="sxs-lookup"><span data-stu-id="4951a-184">You can create reason codes that your users can select when they create or modify positions.</span></span>
-   <span data-ttu-id="4951a-185">È possibile creare tipi di azione dipendente e assegnare una sequenza numerica alle azioni dipendente.</span><span class="sxs-lookup"><span data-stu-id="4951a-185">You can create personnel action types and assign a number sequence to personnel actions.</span></span>
-   <span data-ttu-id="4951a-186">È possibile impostare il flusso di lavoro in modo da poter richiedere l'approvazione per le aggiunte e le modifiche alle posizioni.</span><span class="sxs-lookup"><span data-stu-id="4951a-186">You can set up workflow so that position additions and changes can require approval.</span></span>

### <a name="position-duration"></a><span data-ttu-id="4951a-187">Durata posizione</span><span class="sxs-lookup"><span data-stu-id="4951a-187">Position duration</span></span>

<span data-ttu-id="4951a-188">Ogni posizione è valida per un periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="4951a-188">Every position has a length of time that the position is effective.</span></span> <span data-ttu-id="4951a-189">Tale periodo di tempo viene definito durata.</span><span class="sxs-lookup"><span data-stu-id="4951a-189">This length of time is referred to as duration.</span></span> <span data-ttu-id="4951a-190">Ad esempio, le posizioni estive possono avere una durata compresa tra il 1° maggio 2015 e il 31 agosto 2015.</span><span class="sxs-lookup"><span data-stu-id="4951a-190">For example, summer positions might have duration of May 1, 2015 until August 31, 2015.</span></span>

### <a name="worker-assignments"></a><span data-ttu-id="4951a-191">Assegnazioni lavoratori</span><span class="sxs-lookup"><span data-stu-id="4951a-191">Worker assignments</span></span>

<span data-ttu-id="4951a-192">Quando si assegna un lavoratore a una posizione, tale posizione viene coperta.</span><span class="sxs-lookup"><span data-stu-id="4951a-192">When you assign a worker to a position, you fill that position.</span></span> <span data-ttu-id="4951a-193">È possibile assegnare i lavoratori a più posizioni, ma solo un lavoratore può essere assegnato a una posizione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="4951a-193">You can assign workers to multiple positions, but only one worker can be assigned to a position at the same time.</span></span>

### <a name="reporting-relationships"></a><span data-ttu-id="4951a-194">Relazioni gerarchiche</span><span class="sxs-lookup"><span data-stu-id="4951a-194">Reporting relationships</span></span>

<span data-ttu-id="4951a-195">Le posizioni sono elementi importanti del livello inferiore di una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="4951a-195">Positions are important elements of the lower level of an organization hierarchy.</span></span> <span data-ttu-id="4951a-196">Nel modulo Posizione è possibile specificare la posizione gerarchicamente superiore a una posizione.</span><span class="sxs-lookup"><span data-stu-id="4951a-196">In the Position form, you can specify the position that a position reports to.</span></span> <span data-ttu-id="4951a-197">Quando si assegna un lavoratore a una posizione che ha una posizione superiore, viene creata una relazione gerarchica tra i lavoratori assegnati alle due posizioni.</span><span class="sxs-lookup"><span data-stu-id="4951a-197">When you assign a worker to a position that reports to another position, you create a reporting relationship between the workers who are assigned to the two positions.</span></span> <span data-ttu-id="4951a-198">Ad esempio, la posizione “Ragioniere-A" risponde alla posizione superiore "Supervisore contabile".</span><span class="sxs-lookup"><span data-stu-id="4951a-198">For example, position “Accountant-A” reports to position “Accounting Supervisor”.</span></span> <span data-ttu-id="4951a-199">Kim Akers viene assegnata alla posizione “Supervisore contabile" e Sanjay Patel alla posizione “Ragioniere-A”.</span><span class="sxs-lookup"><span data-stu-id="4951a-199">Kim Akers is assigned to position “Accounting Supervisor” and Sanjay Patel is assigned to position “Accountant-A”.</span></span> <span data-ttu-id="4951a-200">Ciò significa che Kim Akers è il superiore gerarchico di Sanjay Patel.</span><span class="sxs-lookup"><span data-stu-id="4951a-200">This means that Sanjay Patel reports to Kim Akers.</span></span> 

<span data-ttu-id="4951a-201">Se l'organizzazione utilizza una gerarchia a matrice o un'altra gerarchia personalizzata, è possibile impostare i tipi di gerarchia delle posizioni e aggiungere le relazioni gerarchiche alle posizioni per ogni tipo di gerarchia impostata.</span><span class="sxs-lookup"><span data-stu-id="4951a-201">If your organization uses a matrix hierarchy or another custom hierarchy, you can set up position hierarchy types and then add reporting relationships to positions for each hierarchy type that you set up.</span></span> <span data-ttu-id="4951a-202">Ad esempio, Lori Penor è una responsabile generale in Adventure Works e viene assegnata alla posizione "Responsabile generale".</span><span class="sxs-lookup"><span data-stu-id="4951a-202">For example, Lori Penor is a general manager at Adventure Works and is assigned to the “General Manager” position.</span></span> <span data-ttu-id="4951a-203">Lori gestisce lo sviluppo di un prodotto che viene utilizzato per eseguire la pulitura dei congegni meccanici.</span><span class="sxs-lookup"><span data-stu-id="4951a-203">Lori manages the development of a product that is used to clean widgets.</span></span> <span data-ttu-id="4951a-204">Lori ha bisogno dell'assistenza di un ragioniere per gli aspetti finanziari dello sviluppo del prodotto.</span><span class="sxs-lookup"><span data-stu-id="4951a-204">Lori requires an accountant to help her with the finances for developing the product.</span></span> <span data-ttu-id="4951a-205">Di conseguenza, ha assunto Sanjay Patel come proprio ragioniere.</span><span class="sxs-lookup"><span data-stu-id="4951a-205">Therefore, she has recruited Sanjay Patel to be her accountant.</span></span> <span data-ttu-id="4951a-206">Sanjay risponde direttamente a Kim Akers, ma lavora anche con Lori Penor relativamente agli aspetti finanziari dello sviluppo del prodotto per la pulitura dei congegni.</span><span class="sxs-lookup"><span data-stu-id="4951a-206">Sanjay reports directly to Kim Akers, but also works with Lori Penor on his work related to the finances for developing the widget cleaner.</span></span> 

<span data-ttu-id="4951a-207">Per l'esempio precedente, vanno completate le seguenti attività per impostare la relazione di lavoro tra Sanjay Patel e Lori Penor:</span><span class="sxs-lookup"><span data-stu-id="4951a-207">For the previous example, you would complete the following tasks to set up the working relationship between Sanjay Patel and Lori Penor:</span></span>
1.  <span data-ttu-id="4951a-208">Creare un tipo di gerarchia di posizioni personalizzato, denominato "Congegni", per creare una gerarchia che include le posizioni responsabili per le attività sul prodotto per la pulitura dei congegni.</span><span class="sxs-lookup"><span data-stu-id="4951a-208">Create a custom position hierarchy type called “Widget” to create a hierarchy that includes positions responsible for working on the widget cleaner product.</span></span>
2.  <span data-ttu-id="4951a-209">Assegnare la posizione Responsabile generale come posizione superiore della posizione Ragioniere-A nella gerarchia Congegni.</span><span class="sxs-lookup"><span data-stu-id="4951a-209">Assign the General Manager position to be the position that the Accountant-A position reports to in the Widget hierarchy.</span></span>

<span data-ttu-id="4951a-210">Utilizzare la gerarchia di posizioni per visualizzare la struttura gerarchica delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="4951a-210">Use the position hierarchy to view the reporting structure of positions.</span></span> <span data-ttu-id="4951a-211">Se sono presenti più gerarchie di posizioni, è possibile visualizzare la gerarchia di ogni tipo nella gerarchia di posizioni.</span><span class="sxs-lookup"><span data-stu-id="4951a-211">If you have multiple position hierarchies, you can view the hierarchy for each hierarchy type in the position hierarchy.</span></span> <span data-ttu-id="4951a-212">Inoltre, è possibile cercare una posizione in base all'ID posizione o al nome del lavoratore assegnato alla posizione.</span><span class="sxs-lookup"><span data-stu-id="4951a-212">Also, you can search for a position by position ID or by the name of the worker who is assigned to the position.</span></span> <span data-ttu-id="4951a-213">La gerarchia di posizioni è una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="4951a-213">The position hierarchy is an organizational hierarchy.</span></span>

## <a name="date-effective-records"></a><span data-ttu-id="4951a-214">Record con date valide</span><span class="sxs-lookup"><span data-stu-id="4951a-214">Date effective records</span></span>
<span data-ttu-id="4951a-215">Per alcuni record, è possibile specificare le modifiche future al record.</span><span class="sxs-lookup"><span data-stu-id="4951a-215">For some records, you can specify future changes to the record.</span></span> <span data-ttu-id="4951a-216">Le seguenti informazioni sono correlate a una data di validità.</span><span class="sxs-lookup"><span data-stu-id="4951a-216">The following information is date effective.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="4951a-217">Record</span><span class="sxs-lookup"><span data-stu-id="4951a-217">Records</span></span></th>
<th><span data-ttu-id="4951a-218">Informazioni correlate a una data di validità</span><span class="sxs-lookup"><span data-stu-id="4951a-218">Date effective information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4951a-219">Processi</span><span class="sxs-lookup"><span data-stu-id="4951a-219">Jobs</span></span></td>
<td><ul>
<li><span data-ttu-id="4951a-220">Alcune informazioni dettagliate sulla mansione</span><span class="sxs-lookup"><span data-stu-id="4951a-220">Some detailed job information</span></span></li>
<li><span data-ttu-id="4951a-221">Informazioni sulla classificazione della mansione</span><span class="sxs-lookup"><span data-stu-id="4951a-221">Job classification information</span></span></li>
<li><span data-ttu-id="4951a-222">Informazioni sulla retribuzione</span><span class="sxs-lookup"><span data-stu-id="4951a-222">Compensation information</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4951a-223">Posizioni</span><span class="sxs-lookup"><span data-stu-id="4951a-223">Positions</span></span></td>
<td><ul>
<li><span data-ttu-id="4951a-224">Alcune informazioni dettagliate sulla posizione</span><span class="sxs-lookup"><span data-stu-id="4951a-224">Some detailed position information</span></span></li>
<li><span data-ttu-id="4951a-225">Assegnazioni dei lavoratori</span><span class="sxs-lookup"><span data-stu-id="4951a-225">Worker assignments</span></span></li>
<li><span data-ttu-id="4951a-226">Durate posizione</span><span class="sxs-lookup"><span data-stu-id="4951a-226">Position durations</span></span></li>
<li><span data-ttu-id="4951a-227">Gerarchie posizioni</span><span class="sxs-lookup"><span data-stu-id="4951a-227">Position hierarchies</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4951a-228">È possibile modificare le informazioni citate nella tabella precedente per una posizione o una mansione e specificare una data in cui le modifiche alla posizione o alla mansione devono essere rese effettive.</span><span class="sxs-lookup"><span data-stu-id="4951a-228">You can modify the information mentioned in the previous table for a position or a job and specify a date when the modifications to the position or job should take effect.</span></span> <span data-ttu-id="4951a-229">Ad esempio, una posizione può essere assegnata solo a un lavoratore, ma Sanjay Patel, assegnato alla posizione Ragioniere-A, lascerà la società tra due settimane.</span><span class="sxs-lookup"><span data-stu-id="4951a-229">For example, a position can only be assigned to one worker, but Sanjay Patel, who is assigned to the position Accountant-A, will be leaving in two weeks.</span></span> <span data-ttu-id="4951a-230">Joe Healy sostituirà Sanjay Patel.</span><span class="sxs-lookup"><span data-stu-id="4951a-230">Joe Healy will replace Sanjay Patel when he leaves.</span></span> <span data-ttu-id="4951a-231">Anche se Sanjay è ancora assegnato alla posizione, è possibile assegnare Joe Healy alla stessa posizione in modo che l'assegnazione sia valida solo dopo l'ultimo giorno di Sanjay.</span><span class="sxs-lookup"><span data-stu-id="4951a-231">Even though Sanjay is still assigned to his position, you can assign Joe Healy to the same position so that the assignment is effective only after Sanjay’s last day.</span></span>




