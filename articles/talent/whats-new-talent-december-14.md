---
title: Novità o modifiche in Dynamics 365 for Talent Core HR (14 dicembre 2018)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 12/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-12-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7d2866923efd7f115ad5290f35ed4fcac5e47573
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "304926"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-december-14-2018"></a><span data-ttu-id="e223e-103">Novità o modifiche in Dynamics 365 for Talent Core HR (14 dicembre 2018)</span><span class="sxs-lookup"><span data-stu-id="e223e-103">What's new or changed in Dynamics 365 for Talent Core HR (December 14, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e223e-104">**Build 8.1.2085**</span><span class="sxs-lookup"><span data-stu-id="e223e-104">**Build 8.1.2085**</span></span>

<span data-ttu-id="e223e-105">Questo argomento descrive le funzionalità nuove o modificate di Core HR.</span><span class="sxs-lookup"><span data-stu-id="e223e-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="e223e-106">Modifiche</span><span class="sxs-lookup"><span data-stu-id="e223e-106">Changes</span></span>

### <a name="us---aca-affordable-care-act-support-for-tax-year-2018-1095-b-and-1095-c-forms"></a><span data-ttu-id="e223e-107">Supporto ACA (Affordable Care Act) per l'anno fiscale 2018 - Moduli 1095-B and 1095-C</span><span class="sxs-lookup"><span data-stu-id="e223e-107">US - ACA (Affordable Care Act) support for tax year 2018 1095-B and 1095-C forms</span></span>

<span data-ttu-id="e223e-108">Ogni anno, i datori di lavoro ALE (Applicable Large Employers) devono fornire a ogni dipendente a tempo pieno un modulo 1095-C.</span><span class="sxs-lookup"><span data-stu-id="e223e-108">Each year, Applicable Large Employers (ALEs) must provide each full-time employees with a 1095-C.</span></span> <span data-ttu-id="e223e-109">Inoltre, se il datore di lavoro fornisce una copertura autoassicurata, deve fornire il modulo 1095-C (se è un datore di lavoro ALE) e il modulo 1095-B (se ha pochi dipendenti) a qualsiasi dipendente, a tempo pieno o a tempo parziale, coperto da un piano di assistenza sanitaria.</span><span class="sxs-lookup"><span data-stu-id="e223e-109">In addition, if the employer provides self-insured coverage they must provide the 1095-C (if they are an ALE) and a 1095-B (if they are a small employer) to any employee, full-time or part-time, covered under one of their offered health plans.</span></span> <span data-ttu-id="e223e-110">Questa funzionalità fornisce moduli 1095-C e 1095-B stampabili.</span><span class="sxs-lookup"><span data-stu-id="e223e-110">This feature provides printable forms for both the 1095-C and 1095-B.</span></span>

### <a name="during-import-submittedbypersonid-field-on-hcmperfjournalentity-is-ignored"></a><span data-ttu-id="e223e-111">Durante l'importazione il campo SubmittedByPersonId in HcmPerfJournalEntity viene ignorato</span><span class="sxs-lookup"><span data-stu-id="e223e-111">During import SubmittedByPersonId field on HcmPerfJournalEntity is ignored</span></span>

<span data-ttu-id="e223e-112">Durante l'importazione/esportazione delle voci del giornale di registrazione delle prestazioni, il campo **Inviato da** viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="e223e-112">When importing/exporting performance journal entries, the **Submitted by** field is ignored.</span></span> <span data-ttu-id="e223e-113">Con questa modifica, il valore **importato/esportato** rifletterà il valore della tabella durante l'esportazione; durante l'importazione, il sistema verrà aggiornato con il valore fornito nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="e223e-113">With this change, the value **imported/exported** will reflect the value in the table during the export, when importing the system will be updated with the value supplied in the import file.</span></span>

### <a name="analytics-tab-on-leave-and-absence-workspace-displays-openconnectionerror-error-for-non-system-admin-roles"></a><span data-ttu-id="e223e-114">La scheda Analisi nell'area di lavoro "Congedo e assenza" visualizza l'errore "OpenConnectionError" per i ruoli di amministratore non di sistema</span><span class="sxs-lookup"><span data-stu-id="e223e-114">Analytics tab on 'Leave and absence' workspace displays "OpenConnectionError" error for non-system Admin roles</span></span>

<span data-ttu-id="e223e-115">Con questo aggiornamento, non verrà generato alcun errore quando si apre la scheda **Analisi** nell'area di lavoro **Congedo e assenza**.</span><span class="sxs-lookup"><span data-stu-id="e223e-115">With this update, no errors will be issued when opening the **Analytics** tab on the **Leave and Absence** workspace.</span></span>

### <a name="employee-self-service-position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a><span data-ttu-id="e223e-116">In Dipendente self-service il drill-down della gerarchia delle posizioni non riesce a richiamare il nodo padre</span><span class="sxs-lookup"><span data-stu-id="e223e-116">Employee self-service, Position Hierarchy drill-down from tile fails to get parent node</span></span>

<span data-ttu-id="e223e-117">È stata apportata una modifica per correggere l'errore "Richiamo del nodo padre non riuscito" quando la gerarchia delle posizioni viene personalizzata per essere visualizzata in un'area di lavoro esistente e una posizione è selezionata nella gerarchia.</span><span class="sxs-lookup"><span data-stu-id="e223e-117">A change has been made to correct the error "Getting the parent node failed" when the position hierarchy has been personalized to appear on an existing workspace and a position is selected in the hierarchy.</span></span>  

### <a name="must-be-system-admin-to-see-the-payroll-tab-in-the-position-page"></a><span data-ttu-id="e223e-118">È necessario essere un amministratore di sistema per visualizzare la scheda Retribuzioni nella pagina Posizione</span><span class="sxs-lookup"><span data-stu-id="e223e-118">Must be System Admin to see the Payroll tab in the Position page</span></span>

<span data-ttu-id="e223e-119">È stata apportata una modifica per includere gli elementi di protezione corretti nel privilegio esistente: "Gestisci i dettagli di lavoratori e posizioni per la retribuzione".</span><span class="sxs-lookup"><span data-stu-id="e223e-119">A change has been made to include the correct security elements in the existing privilege: "Maintain payroll worker and position detail".</span></span> <span data-ttu-id="e223e-120">Con questa modifica, per impostazione predefinita, l'amministratore delle retribuzioni potrà accedere ai campi Retribuzioni nella pagina Posizione.</span><span class="sxs-lookup"><span data-stu-id="e223e-120">With this change, by default, the Payroll Administrator will have access to the Payroll fields on the Position page.</span></span>

### <a name="error-when-submitting-performance-review-to-manager-and-the-reviewsperfperiod-placeholder-is-used-in-the-submission-instructions"></a><span data-ttu-id="e223e-121">Errore durante l'invio della revisione delle prestazioni al responsabile e il segnaposto %Reviews.PerfPeriod% è utilizzato nelle istruzioni di invio</span><span class="sxs-lookup"><span data-stu-id="e223e-121">Error when submitting performance review to manager and the %Reviews.PerfPeriod% placeholder is used in the Submission instructions</span></span>

<span data-ttu-id="e223e-122">È stata apportata una modifica che corregge l'errore "Riferimento null" quando si utilizza il segnaposto %Reviews.PerfPeriod% nelle istruzioni di invio.</span><span class="sxs-lookup"><span data-stu-id="e223e-122">A change has been made that corrects the "Null Reference" error when using the %Reviews.PerfPeriod% placeholder in the Submission instructions.</span></span>

### <a name="workforce-power-bi-report-shows-error-when-worker-seniority-date-is-a-leap-day"></a><span data-ttu-id="e223e-123">Il report Power BI sulla forza lavoro presenta un errore quando la data di anzianità del lavoratore è un giorno bisesto</span><span class="sxs-lookup"><span data-stu-id="e223e-123">Workforce Power BI report shows error when worker seniority date is a leap day</span></span>

<span data-ttu-id="e223e-124">Con questa modifica, i giorni bisesti sono ora supportati in Power BI.</span><span class="sxs-lookup"><span data-stu-id="e223e-124">With this change, leap days are now supported in Power BI.</span></span>

### <a name="integration-between-core-hr-and-attract"></a><span data-ttu-id="e223e-125">Integrazione tra Core HR e Attract</span><span class="sxs-lookup"><span data-stu-id="e223e-125">Integration between Core HR and Attract</span></span>

<span data-ttu-id="e223e-126">È stata apportata una modifica per aggiornare l'integrazione tra Core HR e Attract in relazione ai candidati da assumere.</span><span class="sxs-lookup"><span data-stu-id="e223e-126">A change has been made to update the integration between Core HR and Attract related to candidates to hire.</span></span> <span data-ttu-id="e223e-127">Affinché i candidati da assumere siano visibili nell'area di lavoro **Gestione personale**, vengono utilizzate le seguenti entità CDS per Apps (CDS 2.0):</span><span class="sxs-lookup"><span data-stu-id="e223e-127">For candidates to hire to be visible in the **Personnel Management** workspace, the following CDS for Apps (CDS 2.0) entities are used:</span></span>

<span data-ttu-id="e223e-128">Domanda di lavoro</span><span class="sxs-lookup"><span data-stu-id="e223e-128">Job Application</span></span>
- <span data-ttu-id="e223e-129">Motivo dello stato deve essere impostato su Offerta accettata</span><span class="sxs-lookup"><span data-stu-id="e223e-129">Status Reason needs to be set to Offer Accepted</span></span>
-   <span data-ttu-id="e223e-130">Fornisce Candidato e Posizione aperta</span><span class="sxs-lookup"><span data-stu-id="e223e-130">Provides Candidate and Job Opening</span></span>

<span data-ttu-id="e223e-131">Candidato</span><span class="sxs-lookup"><span data-stu-id="e223e-131">Candidate</span></span>
-   <span data-ttu-id="e223e-132">Fornisce Informazioni sul candidato</span><span class="sxs-lookup"><span data-stu-id="e223e-132">Provides Candidate information</span></span>

<span data-ttu-id="e223e-133">Posizione aperta</span><span class="sxs-lookup"><span data-stu-id="e223e-133">Job Opening</span></span>
-   <span data-ttu-id="e223e-134">Fornisce ID posizione aperta e Partecipanti posizione aperta</span><span class="sxs-lookup"><span data-stu-id="e223e-134">Provides Job Opening ID and Job Opening Participants</span></span>

<span data-ttu-id="e223e-135">Partecipanti posizione aperta</span><span class="sxs-lookup"><span data-stu-id="e223e-135">Job Opening Participants</span></span>
-   <span data-ttu-id="e223e-136">Fornisce Responsabile assunzioni</span><span class="sxs-lookup"><span data-stu-id="e223e-136">Provides Hiring Manager</span></span>

<span data-ttu-id="e223e-137">Quando un candidato è aggiunto a Gestione personale, può anche essere chiuso utilizzando una nuova opzione disponibile nella scheda del candidato.</span><span class="sxs-lookup"><span data-stu-id="e223e-137">When a candidate is added to Personnel Management, the candidate can now also be dismissed using a new option available on the candidate card.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="e223e-138">Presto disponibili</span><span class="sxs-lookup"><span data-stu-id="e223e-138">Coming soon</span></span>

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a><span data-ttu-id="e223e-139">Congedo e assenza: saldi congedo futuri e previsione di saldi congedo</span><span class="sxs-lookup"><span data-stu-id="e223e-139">Leave and absence: Future leave and forecasting leave balances</span></span>

<span data-ttu-id="e223e-140">A seguito delle modifiche apportate per consentire ai dipendenti di prevedere i permessi e richiedere richieste di permessi futuri senza alterare i relativi saldi permesso correnti, anche la modalità di visualizzazione dei saldi permesso risulterà modificata.</span><span class="sxs-lookup"><span data-stu-id="e223e-140">With the changes being made to allow for employees to forecast time off and request future time off requests without impacting their current time off balances, the way the time off balances are displayed is also changing.</span></span> 

<span data-ttu-id="e223e-141">Il saldo disponibile attualmente visualizzato è la quantità di permessi disponibile per le richieste inclusi gli accumuli fino alla data odierna e tutte le richieste di congedo approvate.</span><span class="sxs-lookup"><span data-stu-id="e223e-141">The available balance currently displayed is the amount of time off available for requests including accruals through today and all approved leave requests to the end of time.</span></span> 

<span data-ttu-id="e223e-142">Al rilascio della funzionalità di previsione, il saldo visualizzato sarà il saldo permessi corrente inclusi gli accumuli e le richieste fino alla data odierna.</span><span class="sxs-lookup"><span data-stu-id="e223e-142">When the ability to forecast is released, the balance displayed changes to  be the current balance of time off including accruals through today and requests through today.</span></span> <span data-ttu-id="e223e-143">Dipendenti e responsabili vedranno questi saldi aggiornati in responsabile e dipendente self service nella scheda **Tempo libero** e nella finestra **Saldi permessi**.</span><span class="sxs-lookup"><span data-stu-id="e223e-143">Employees and managers will see these updated balances in employee and manager self-service on the **Time off** card and in the **Time off balances** window.</span></span> <span data-ttu-id="e223e-144">I responsabili risorse umane vedranno questi saldi aggiornati nell'area di lavoro **Persone** e nella finestra **Piani di congedo assegnati del dipendente**.</span><span class="sxs-lookup"><span data-stu-id="e223e-144">HR managers will see these updated balances in the **People** workspace and in the employee’s **Assigned leave plans** window.</span></span>

## <a name="known-issue"></a><span data-ttu-id="e223e-145">Problema noto</span><span class="sxs-lookup"><span data-stu-id="e223e-145">Known issue</span></span>

### <a name="mapping-errors-in-the-integration-with-finance-and-operations"></a><span data-ttu-id="e223e-146">Errori di mapping nell'integrazione con Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e223e-146">Mapping errors in the integration with Finance and Operations</span></span>

<span data-ttu-id="e223e-147">I seguenti problemi sono stati identificati nel modello corrente per l'integrazione di Talent con Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e223e-147">The following issues have been identified in the current template for integrating Talent with Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="e223e-148">Un nuovo modello verrà pubblicato a breve e applicato a tutti i nuovi progetti di integrazione creati.</span><span class="sxs-lookup"><span data-stu-id="e223e-148">A new template will be published soon and will be applied to all new integration projects that are created.</span></span> <span data-ttu-id="e223e-149">Per i progetti di integrazione esistenti, i mapping di attività possono essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="e223e-149">For existing integration projects, the task mappings can be updated.</span></span> <span data-ttu-id="e223e-150">Consultare la tabella seguente per i mapping aggiornati.</span><span class="sxs-lookup"><span data-stu-id="e223e-150">Refer to the following table for updated mappings.</span></span> 

>[!NOTE]
> <span data-ttu-id="e223e-151">L'attività di assegnazione del processo padre Posizioni lavorative a Posizioni non integra dati.</span><span class="sxs-lookup"><span data-stu-id="e223e-151">The Job Positions to Positions Parent Job Assignment task does not integrate data.</span></span> <span data-ttu-id="e223e-152">Questo problema è attualmente in fase di risoluzione.</span><span class="sxs-lookup"><span data-stu-id="e223e-152">This is an issue that is currently being researched.</span></span> <span data-ttu-id="e223e-153">Non esiste alcuna soluzione alternativa nel mapping corrente.</span><span class="sxs-lookup"><span data-stu-id="e223e-153">There is no workaround in the current mapping.</span></span> 

<span data-ttu-id="e223e-154">L'attività Reparti a Unità operativa necessita l'aggiornamento dei mapping seguenti.</span><span class="sxs-lookup"><span data-stu-id="e223e-154">The Departments to Operating unit task needs the following mappings updated.</span></span>

| <span data-ttu-id="e223e-155">Campo origine esistente</span><span class="sxs-lookup"><span data-stu-id="e223e-155">Existing source field</span></span>          | <span data-ttu-id="e223e-156">Campo nuova origine</span><span class="sxs-lookup"><span data-stu-id="e223e-156">New source field</span></span> |
| -------------------------------|------------------|
| <span data-ttu-id="e223e-157">cdm_description (Descrizione)</span><span class="sxs-lookup"><span data-stu-id="e223e-157">cdm_description (Description)</span></span>  | <span data-ttu-id="e223e-158">cdm_name (Nome)</span><span class="sxs-lookup"><span data-stu-id="e223e-158">cdm_name (Name)</span></span>  |

<span data-ttu-id="e223e-159">È necessario aggiungere anche un ulteriore mapping.</span><span class="sxs-lookup"><span data-stu-id="e223e-159">An additional mapping also needs to be added.</span></span> <span data-ttu-id="e223e-160">Selezionare l'ultimo campo **Nessuno** per aggiungere il mapping successivo.</span><span class="sxs-lookup"><span data-stu-id="e223e-160">Select the last **None** field to add the following mapping.</span></span>

| <span data-ttu-id="e223e-161">Campo di origine</span><span class="sxs-lookup"><span data-stu-id="e223e-161">Source field</span></span>                   | <span data-ttu-id="e223e-162">Campo di destinazione</span><span class="sxs-lookup"><span data-stu-id="e223e-162">Destination field</span></span>    |
| -------------------------------|----------------------|
| <span data-ttu-id="e223e-163">cdm_description (Descrizione)</span><span class="sxs-lookup"><span data-stu-id="e223e-163">cdm_description (Description)</span></span>  | <span data-ttu-id="e223e-164">NAMEALIAS (NAMEALIAS)</span><span class="sxs-lookup"><span data-stu-id="e223e-164">NAMEALIAS (NAMEALIAS)</span></span>|

<span data-ttu-id="e223e-165">I mapping aggiornati devono essere simili all'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="e223e-165">The updated mappings should look like the following image.</span></span>

![Attività Reparti a Unità operative](./media/DepartmentMapping.png)


<span data-ttu-id="e223e-167">L'attività Mansioni a Dettagli mansione necessita l'aggiornamento dei mapping seguenti.</span><span class="sxs-lookup"><span data-stu-id="e223e-167">The Jobs to Job Detail task needs the following mappings updated.</span></span>

| <span data-ttu-id="e223e-168">Campo origine esistente</span><span class="sxs-lookup"><span data-stu-id="e223e-168">Existing source field</span></span>          | <span data-ttu-id="e223e-169">Campo nuova origine</span><span class="sxs-lookup"><span data-stu-id="e223e-169">New source field</span></span>                   |
| -------------------------------|------------------------------------|
| <span data-ttu-id="e223e-170">cdm_name (Nome)</span><span class="sxs-lookup"><span data-stu-id="e223e-170">cdm_name (Name)</span></span>                | <span data-ttu-id="e223e-171">cdm_description (Descrizione)</span><span class="sxs-lookup"><span data-stu-id="e223e-171">cdm_description (Description)</span></span>      |
| <span data-ttu-id="e223e-172">cdm_name (Descrizione)</span><span class="sxs-lookup"><span data-stu-id="e223e-172">cdm_name (Description)</span></span>         | <span data-ttu-id="e223e-173">cdm_jobdescription(Descrizione mansione)</span><span class="sxs-lookup"><span data-stu-id="e223e-173">cdm_jobdescription(Job Description)</span></span>|


<span data-ttu-id="e223e-174">I mapping aggiornati devono essere simili all'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="e223e-174">The updated mappings should look like the image below.</span></span>

![Attività Mansioni a Dettagli mansione](./media/JobMapping.png)

<span data-ttu-id="e223e-176">L'attività Lavoratori a Lavoro necessita l'aggiornamento dei mapping seguenti.</span><span class="sxs-lookup"><span data-stu-id="e223e-176">The Workers to Work task needs the following mappings updated.</span></span>

| <span data-ttu-id="e223e-177">Campo origine esistente</span><span class="sxs-lookup"><span data-stu-id="e223e-177">Existing source field</span></span>                 | <span data-ttu-id="e223e-178">Campo nuova origine</span><span class="sxs-lookup"><span data-stu-id="e223e-178">New source field</span></span>                               |
| --------------------------------------|------------------------------------------------|
| <span data-ttu-id="e223e-179">cdm_emailaddress1 (Indirizzo di posta elettronica 1)</span><span class="sxs-lookup"><span data-stu-id="e223e-179">cdm_emailaddress1 (Email Address 1)</span></span>   | <span data-ttu-id="e223e-180">cdm_primaryemailaddress (Indirizzo di posta elettronica principale)</span><span class="sxs-lookup"><span data-stu-id="e223e-180">cdm_primaryemailaddress (Primary Email Address</span></span> |
| <span data-ttu-id="e223e-181">cdm_telephone1 (Telefono 1)</span><span class="sxs-lookup"><span data-stu-id="e223e-181">cdm_telephone1 (Telephone 1)</span></span>          | <span data-ttu-id="e223e-182">cdm_primarytelephone (Telefono principale)</span><span class="sxs-lookup"><span data-stu-id="e223e-182">cdm_primarytelephone (Primary Telephone)</span></span>       |

<span data-ttu-id="e223e-183">Anche la trasformazione del campo Sesso deve essere aggiornata.</span><span class="sxs-lookup"><span data-stu-id="e223e-183">The Gender field transform also needs to be updated.</span></span> <span data-ttu-id="e223e-184">Selezionare il tipo di mappa **fn** (funzione) per Sesso e aggiornare i mapping dei valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="e223e-184">Select the **fn** (function) map type for Gender and update the following value mappings.</span></span>

| <span data-ttu-id="e223e-185">Valore CDS</span><span class="sxs-lookup"><span data-stu-id="e223e-185">CDS value</span></span>                   | <span data-ttu-id="e223e-186">Valore Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e223e-186">Finance and Operations value</span></span>                     |
| ----------------------------|--------------------------------------------------|
| <span data-ttu-id="e223e-187">75440000</span><span class="sxs-lookup"><span data-stu-id="e223e-187">75440000</span></span>                    | <span data-ttu-id="e223e-188">Maschio</span><span class="sxs-lookup"><span data-stu-id="e223e-188">Male</span></span>                                             |
| <span data-ttu-id="e223e-189">75440001</span><span class="sxs-lookup"><span data-stu-id="e223e-189">75440001</span></span>                    | <span data-ttu-id="e223e-190">Femmina</span><span class="sxs-lookup"><span data-stu-id="e223e-190">Female</span></span>                                           |
| <span data-ttu-id="e223e-191">75440002</span><span class="sxs-lookup"><span data-stu-id="e223e-191">75440002</span></span>                    | <span data-ttu-id="e223e-192">Nessuna priorità</span><span class="sxs-lookup"><span data-stu-id="e223e-192">None</span></span>                                             | 
| <span data-ttu-id="e223e-193">75440003</span><span class="sxs-lookup"><span data-stu-id="e223e-193">75440003</span></span>                    | <span data-ttu-id="e223e-194">NonSpecific</span><span class="sxs-lookup"><span data-stu-id="e223e-194">NonSpecific</span></span>                                      |

<span data-ttu-id="e223e-195">I mapping aggiornati devono essere simili all'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="e223e-195">The updated mappings should look like the following images.</span></span>

![Attività Lavoratori a Lavoratore.](./media/WorkerMapping.png)

![Trasformazione del campo Sesso](./media/WorkerTransform.png)