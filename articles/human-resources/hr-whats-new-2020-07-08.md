---
title: Novità e modifiche in Dynamics 365 Human Resources (08 luglio 2020)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources all'8 luglio 2020.
author: andreabichsel
manager: tfehr
ms.date: 07/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9715f332088b7b5340f4252af5f789d226d90ff2
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463600"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-8-2020"></a><span data-ttu-id="df62c-103">Novità e modifiche in Dynamics 365 Human Resources (8 luglio 2020)</span><span class="sxs-lookup"><span data-stu-id="df62c-103">What's new or changed in Dynamics 365 Human Resources (July 8, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="df62c-104">Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="df62c-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="df62c-105">Le modifiche si applicano alla build 8.1.3382.</span><span class="sxs-lookup"><span data-stu-id="df62c-105">Changes apply to build number 8.1.3382.</span></span> <span data-ttu-id="df62c-106">I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.</span><span class="sxs-lookup"><span data-stu-id="df62c-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="database-logging"></a><span data-ttu-id="df62c-107">Registrazione database</span><span class="sxs-lookup"><span data-stu-id="df62c-107">Database logging</span></span>

<span data-ttu-id="df62c-108">La registrazione del database consente di determinare quali tabelle e quali campi monitorare.</span><span class="sxs-lookup"><span data-stu-id="df62c-108">Database logging allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="df62c-109">Inoltre, consente di determinare gli eventi che dovrebbero attivare il rilevamento delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="df62c-109">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="df62c-110">Usare le funzionalità di registrazione del database per visualizzare tali modifiche nel tempo.</span><span class="sxs-lookup"><span data-stu-id="df62c-110">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="df62c-111">Per ulteriori informazioni, vedi [Configurare e gestire la registrazione del database](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="df62c-111">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="df62c-112">Configurare il nome dell'area di lavoro Self-service dipendenti</span><span class="sxs-lookup"><span data-stu-id="df62c-112">Configure the name of Employee self service</span></span>

<span data-ttu-id="df62c-113">In **Parametri Risorse umane**, è ora possibile cambiare il nome dell'area di lavoro **Self-service dipendenti** in **Self-service**.</span><span class="sxs-lookup"><span data-stu-id="df62c-113">In **Human Resources parameters**, you can now change the name of the **Employee self service** workspace to **Self service**.</span></span> <span data-ttu-id="df62c-114">Per ulteriori informazioni, vedere [Cambiare il nome dell'area di lavoro Self-service dipendenti](hr-employee-self-service-workspace-name.md)</span><span class="sxs-lookup"><span data-stu-id="df62c-114">For more information, see [Change Employee self service workspace name](hr-employee-self-service-workspace-name.md)</span></span>

## <a name="benefits-management-open-enrollment-access-outside-of-period"></a><span data-ttu-id="df62c-115">Accesso all'iscrizione aperta in Gestione benefit al di fuori del periodo di iscrizione</span><span class="sxs-lookup"><span data-stu-id="df62c-115">Benefits management open enrollment access outside of period</span></span>

<span data-ttu-id="df62c-116">Questa versione corregge un bug che consentiva ai dipendenti di accedere all'iscrizione aperta dei benefit al di fuori del periodo di iscrizione o senza un evento reale.</span><span class="sxs-lookup"><span data-stu-id="df62c-116">This release fixes a bug where employees could access benefits open enrollment outside of the enrollment period or without a life event.</span></span> <span data-ttu-id="df62c-117">Di conseguenza, se è necessario eseguire una demo dell'iscrizione aperta in Self-service dipendenti, è necessario impostare le date di iscrizione aperta sulla data odierna o una data precedente per renderla accessibile.</span><span class="sxs-lookup"><span data-stu-id="df62c-117">As a result, if you need to demo open enrollment in Employee self service, you must adjust the open enrollment dates to today (or earlier) to make it accessible.</span></span> <span data-ttu-id="df62c-118">È possibile modificare questa impostazione in **Gestione benefit > Periodi di regole e opzioni**.</span><span class="sxs-lookup"><span data-stu-id="df62c-118">You can change this setting under **Benefits management > Rules and options periods**.</span></span>

## <a name="email-employee-enrollment-confirmation"></a><span data-ttu-id="df62c-119">Email di conferma dell'iscrizione dei dipendenti</span><span class="sxs-lookup"><span data-stu-id="df62c-119">Email employee enrollment confirmation</span></span>

<span data-ttu-id="df62c-120">Ora è possibile inviare e-mail ai dipendenti dopo che questi hanno completato la selezione dei benefit.</span><span class="sxs-lookup"><span data-stu-id="df62c-120">You can now send emails to employees after they complete their benefits selection.</span></span> <span data-ttu-id="df62c-121">È possibile inviare un messaggio predefinito o utilizzare un modello di posta elettronica dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="df62c-121">You can either send a default message or use an organization email template.</span></span> <span data-ttu-id="df62c-122">Queste impostazioni sono in **Parametri Risorse umane > Gestione benefit**.</span><span class="sxs-lookup"><span data-stu-id="df62c-122">These settings are under **Human resource parameters > Benefits management**.</span></span>

## <a name="canceled-leave-still-appears-in-upcoming-time-off-on-people-workspace-441358"></a><span data-ttu-id="df62c-123">Il congedo annullato appare ancora in Tempo libero imminente nell'area di lavoro Persone (441358)</span><span class="sxs-lookup"><span data-stu-id="df62c-123">Canceled leave still appears in upcoming time off on People workspace (441358)</span></span>

<span data-ttu-id="df62c-124">Il congedo annullato non è più visualizzato come tempo libero imminente nelle schede di congedo nell'area di lavoro **Persone**.</span><span class="sxs-lookup"><span data-stu-id="df62c-124">Canceled leave no longer displays as upcoming time off on the leave cards in the **People** workspace.</span></span>

## <a name="unable-to-use-the-department-entity-property-in-the-positionv2-entity-456486"></a><span data-ttu-id="df62c-125">Impossibile utilizzare la proprietà dell'entità reparto nell'entità PositionV2 (456486)</span><span class="sxs-lookup"><span data-stu-id="df62c-125">Unable to use the department entity property in the PositionV2 entity (456486)</span></span>

<span data-ttu-id="df62c-126">Ora è possibile aggiungere un reparto senza creare una relazione duplicata.</span><span class="sxs-lookup"><span data-stu-id="df62c-126">You can now add a department without creating a duplicate relation.</span></span>

## <a name="payrollworkerenrolledbenefitdetailentity-should-only-use-calculated-field-for-retirement-plans-459779"></a><span data-ttu-id="df62c-127">PayrollWorkerEnrolledBenefitDetailEntity deve utilizzare il campo calcolato solo per i piani pensionistici (459779)</span><span class="sxs-lookup"><span data-stu-id="df62c-127">PayrollWorkerEnrolledBenefitDetailEntity should only use calculated field for retirement plans (459779)</span></span>

<span data-ttu-id="df62c-128">Quando si esporta l'entità **PayrollWorkerEnrolledBenefitDetailEntity**, l'esportazione determina se deve utilizzare un campo calcolato in base a una tabella di tariffe o utilizzare il campo **ContributionAmountCur** nella tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="df62c-128">When exporting the **PayrollWorkerEnrolledBenefitDetailEntity** entity, the export determines whether it should use a calculated field based on a rate table or use the **ContributionAmountCur** field on the backing table.</span></span> <span data-ttu-id="df62c-129">La logica utilizzata dall'entità data utilizza la tabella delle tariffe in situazioni in cui l'applicazione normalmente non l'utilizza.</span><span class="sxs-lookup"><span data-stu-id="df62c-129">The logic used by the data entity uses the rate table in situations where the application normally doesn't.</span></span> <span data-ttu-id="df62c-130">Questa logica fa sì che le esportazioni delle entità restituiscano un valore zero per questa colonna, poiché non esiste una tabella delle tariffe di calcolo e il prodotto non consente al cliente di specificarne una.</span><span class="sxs-lookup"><span data-stu-id="df62c-130">This logic causes the entity exports to return a zero value for this column, because there's no calculation rate table and the product doesn't allow the customer to specify one.</span></span>
 
## <a name="confusing-translations-in-czech-language-in-personnel-management-and-employee-self-service-400276"></a><span data-ttu-id="df62c-131">Traduzioni confuse in lingua ceca in Gestione dipendente e Self-service dipendenti (400276)</span><span class="sxs-lookup"><span data-stu-id="df62c-131">Confusing translations in Czech language in Personnel management and Employee self service (400276)</span></span>

<span data-ttu-id="df62c-132">Questa versione corregge le traduzioni di **Directory società**, **Prossimo corso registrato**, **Processo** e **Posizione**.</span><span class="sxs-lookup"><span data-stu-id="df62c-132">This release corrects the translations for **Company directory**, **Next registered course**, **Job**, and **Position**.</span></span>
 
## <a name="the-workcalendaremployment-table-doesnt-have-the-created-and-modified-system-fields-enabled-460171"></a><span data-ttu-id="df62c-133">La tabella WorkCalendarEmployment non ha i campi di sistema creati e modificati abilitati (460171)</span><span class="sxs-lookup"><span data-stu-id="df62c-133">The WorkCalendarEmployment table doesn't have the created and modified system fields enabled (460171)</span></span>

<span data-ttu-id="df62c-134">I campi di sistema creati e modificati sono ora abilitati nella tabella **WorkCalendarEmployment** in Risorse umane.</span><span class="sxs-lookup"><span data-stu-id="df62c-134">Created and modified system fields are now enabled on the **WorkCalendarEmployment** table in Human Resources.</span></span>
 
## <a name="null-reference-exception-for-hire-and-add-details-for-future-employee-455475"></a><span data-ttu-id="df62c-135">Eccezione di riferimento null per Assumi e aggiungi dettagli per un futuro dipendente (455475)</span><span class="sxs-lookup"><span data-stu-id="df62c-135">Null reference exception for Hire and add details for future employee (455475)</span></span>

<span data-ttu-id="df62c-136">Questa versione corregge un errore (riferimento null) nella voce di dipendente semplificata quando si assume un dipendente utilizzando l'opzione **Assumi e aggiungi dettagli**.</span><span class="sxs-lookup"><span data-stu-id="df62c-136">This release corrects an error (null reference) in streamlined employee entry when you hire an employee using the option to **Hire and add details**.</span></span>

## <a name="changes-made-in-the-dataverse-worker-entity-dont-reflect-in-human-resources-455652"></a><span data-ttu-id="df62c-137">Le modifiche apportate all'entità Lavoratore di Dataverse non sono riflesse in Risorse umane (455652)</span><span class="sxs-lookup"><span data-stu-id="df62c-137">Changes made in the Dataverse Worker entity don't reflect in Human Resources (455652)</span></span>

<span data-ttu-id="df62c-138">Le modifiche apportate ai seguenti campi nell'entità **Lavoratore** in Dataverse ora saranno visualizzate in Risorse umane:</span><span class="sxs-lookup"><span data-stu-id="df62c-138">Changes made to the following fields in the **Worker** entity in Dataverse will now show up in Human Resources:</span></span>

- <span data-ttu-id="df62c-139">**Lavora da casa**</span><span class="sxs-lookup"><span data-stu-id="df62c-139">**Works from home**</span></span>
- <span data-ttu-id="df62c-140">**Data di anzianità**</span><span class="sxs-lookup"><span data-stu-id="df62c-140">**Seniority date**</span></span>
- <span data-ttu-id="df62c-141">**Data di ricorrenza annuale**</span><span class="sxs-lookup"><span data-stu-id="df62c-141">**Anniversary date**</span></span>
- <span data-ttu-id="df62c-142">**Data di assunzione originale**</span><span class="sxs-lookup"><span data-stu-id="df62c-142">**Original hire date**</span></span>

## <a name="correct-compensation-level-doesnt-default-based-on-the-job-assigned-to-the-position-394136"></a><span data-ttu-id="df62c-143">L'impostazione predefinita del livello di compensazione corretto non viene selezionata in base al lavoro assegnato alla posizione (394136)</span><span class="sxs-lookup"><span data-stu-id="df62c-143">Correct compensation level doesn't default based on the job assigned to the position (394136)</span></span>

<span data-ttu-id="df62c-144">Con questa modifica, il livello di compensazione corretto viene impostato automaticamente in base ai record **Data valida** per **Dettagli posizioni** e **Data d'inizio** dell'**Assegnazione del piano di compensazione**.</span><span class="sxs-lookup"><span data-stu-id="df62c-144">With this change, the correct compensation level defaults based on the **Date effective** records for the **Position details** and the **Start date** of the **Compensation plan assignment**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="df62c-145">In anteprima</span><span class="sxs-lookup"><span data-stu-id="df62c-145">In preview</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="df62c-146">Campi obbligatori</span><span class="sxs-lookup"><span data-stu-id="df62c-146">Mandatory fields</span></span> 

<span data-ttu-id="df62c-147">Ora puoi rendere obbligatori i campi utilizzando le funzionalità di personalizzazione di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="df62c-147">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="df62c-148">Questa funzionalità richiede **Visualizzazioni salvate**.</span><span class="sxs-lookup"><span data-stu-id="df62c-148">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="df62c-149">Applicazione Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="df62c-149">Human Resources application in Teams</span></span>

<span data-ttu-id="df62c-150">I dipendenti possono visualizzare i congedi e richiederli in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="df62c-150">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="df62c-151">Possono interagire con un bot per creare richieste di congedo.</span><span class="sxs-lookup"><span data-stu-id="df62c-151">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="df62c-152">Per ulteriori informazioni, vedere [App Human Resources in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="df62c-152">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="df62c-153">Entità Data Management Framework per la gestione di benefit</span><span class="sxs-lookup"><span data-stu-id="df62c-153">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="df62c-154">Le entità di gestione di benefit sono in fase di rilascio.</span><span class="sxs-lookup"><span data-stu-id="df62c-154">Benefits management entities are releasing.</span></span> <span data-ttu-id="df62c-155">Le entità DMF consentono di importare ed esportare dati per configurare facilmente la gestione dei benefit.</span><span class="sxs-lookup"><span data-stu-id="df62c-155">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="df62c-156">Sarà disponibile un modello di gestione dei benefit per spostare i dati.</span><span class="sxs-lookup"><span data-stu-id="df62c-156">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="df62c-157">Il modello esporta e importa i dati in modo in modo sequenziale per rispettare le dipendenze dei dati.</span><span class="sxs-lookup"><span data-stu-id="df62c-157">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="df62c-158">Acquista e vendi congedo</span><span class="sxs-lookup"><span data-stu-id="df62c-158">Buy and sell leave</span></span> 

<span data-ttu-id="df62c-159">Alcune organizzazioni offrono un benefit che consente ai dipendenti di acquistare o vendere congedi.</span><span class="sxs-lookup"><span data-stu-id="df62c-159">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="df62c-160">Questo processo è spesso gestito manualmente.</span><span class="sxs-lookup"><span data-stu-id="df62c-160">This process is often managed manually.</span></span> <span data-ttu-id="df62c-161">Questa funzione automatizza la gestione dei criteri e delle richieste per il dipartimento Risorse umane.</span><span class="sxs-lookup"><span data-stu-id="df62c-161">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="df62c-162">Semplifica il processo di gestione delle ferie e aiuta a eliminare gli errori.</span><span class="sxs-lookup"><span data-stu-id="df62c-162">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="df62c-163">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="df62c-163">For more information, see:</span></span>

- [<span data-ttu-id="df62c-164">Gestire i criteri di acquisto e vendita congedo</span><span class="sxs-lookup"><span data-stu-id="df62c-164">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="df62c-165">Acquista e vendi congedo</span><span class="sxs-lookup"><span data-stu-id="df62c-165">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="df62c-166">Lascia l'attribuzione per una singola azienda o un singolo piano</span><span class="sxs-lookup"><span data-stu-id="df62c-166">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="df62c-167">I clienti possono elaborare attribuzioni per una singola azienda o un singolo piano di ferie e assenze.</span><span class="sxs-lookup"><span data-stu-id="df62c-167">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="df62c-168">Questa capacità fornisce chiarezza per il processo di maturazione per i clienti con diversi anni di ferie o politiche di maturazione delle ferie.</span><span class="sxs-lookup"><span data-stu-id="df62c-168">This ability provides clarity for the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="df62c-169">Per ulteriori informazioni, vedi [Accumulare congedi per società o per piano di congedo](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="df62c-169">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="df62c-170">Aggiungi allegati alle richieste di ferie</span><span class="sxs-lookup"><span data-stu-id="df62c-170">Add attachments to time-off requests</span></span>

<span data-ttu-id="df62c-171">La possibilità di aggiungere allegati alle richieste di ferie approvate è fondamentale nell'attuale ambiente COVID-19.</span><span class="sxs-lookup"><span data-stu-id="df62c-171">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="df62c-172">I dipendenti possono ora aggiungere questi allegati.</span><span class="sxs-lookup"><span data-stu-id="df62c-172">Employees can now add these attachments.</span></span> <span data-ttu-id="df62c-173">Hanno anche maggiori informazioni dettagliate su come vengono effettuati gli aggiornamenti per lasciare le richieste.</span><span class="sxs-lookup"><span data-stu-id="df62c-173">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="df62c-174">Per ulteriori informazioni, vedi [Aggiungi un allegato a una richiesta esistente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="df62c-174">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="df62c-175">Aggiungi il codice motivo alle sospensioni degli accumuli</span><span class="sxs-lookup"><span data-stu-id="df62c-175">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="df62c-176">Codici motivo sono stati aggiunti alla sospensione degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="df62c-176">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="df62c-177">Regole di riporto</span><span class="sxs-lookup"><span data-stu-id="df62c-177">Carry forward rules</span></span> 

<span data-ttu-id="df62c-178">È possibile specificare un tipo di congedo riporto per i saldi del riporto in cui vengono trasferiti le rettifiche di riporto.</span><span class="sxs-lookup"><span data-stu-id="df62c-178">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="df62c-179">Ad esempio, se un dipendente riporta 10 giorni, è possibile scegliere un tipo di congedo diverso per quei 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="df62c-179">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="df62c-180">Per ulteriori informazioni, vedere [Configurare i tipi di congedo e assenza](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="df62c-180">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="df62c-181">Sospendi l'accumulo dei congedi per determinati tipi di congedo</span><span class="sxs-lookup"><span data-stu-id="df62c-181">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="df62c-182">Puoi creare una regola per sospendere gli accumuli dei congedi per i dipendenti con richieste di congedo inserite per congedi non retribuiti.</span><span class="sxs-lookup"><span data-stu-id="df62c-182">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="df62c-183">Il congedo non retribuito può essere un tipo, ma non è necessario che lo sia.</span><span class="sxs-lookup"><span data-stu-id="df62c-183">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="df62c-184">È possibile sospendere qualsiasi congedo in base a un altro tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="df62c-184">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="df62c-185">Entità DMF disponibile per le sospensioni degli accumuli</span><span class="sxs-lookup"><span data-stu-id="df62c-185">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="df62c-186">Un'entità DMF è ora disponibile per le sospensioni degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="df62c-186">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="df62c-187">Presto disponibili</span><span class="sxs-lookup"><span data-stu-id="df62c-187">Coming soon</span></span>

## <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="df62c-188">Elenco di controllo entità incluso in Dataverse</span><span class="sxs-lookup"><span data-stu-id="df62c-188">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="df62c-189">Le entità dell'elenco di controllo per i processi di onboarding, offboarding, trasferimenti e aziendali saranno presto disponibili in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="df62c-189">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="df62c-190">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df62c-190">See also</span></span>

[<span data-ttu-id="df62c-191">Novità o modifiche in Human Resources</span><span class="sxs-lookup"><span data-stu-id="df62c-191">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="df62c-192">Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019</span><span class="sxs-lookup"><span data-stu-id="df62c-192">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="df62c-193">Aggiornare un processo</span><span class="sxs-lookup"><span data-stu-id="df62c-193">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="df62c-194">Gestire le funzionalità</span><span class="sxs-lookup"><span data-stu-id="df62c-194">Manage features</span></span>](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]