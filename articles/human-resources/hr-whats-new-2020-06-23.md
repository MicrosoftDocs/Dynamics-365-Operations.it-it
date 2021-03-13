---
title: Novità e modifiche in Dynamics 365 Human Resources (25 giugno 2020)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 23 giugno 2020.
author: andreabichsel
manager: tfehr
ms.date: 06/25/2020
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
ms.search.validFrom: 2020-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ad80e53c0a24d602ac446d3e0765f397dd0fc2d9
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127499"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-23-2020"></a><span data-ttu-id="f0353-103">Novità e modifiche in Dynamics 365 Human Resources (23 giugno 2020)</span><span class="sxs-lookup"><span data-stu-id="f0353-103">What's new or changed in Dynamics 365 Human Resources (June 23, 2020)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="f0353-104">Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f0353-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="f0353-105">Le modifiche si applicano alla build 8.1.3347.</span><span class="sxs-lookup"><span data-stu-id="f0353-105">Changes apply to build number 8.1.3347.</span></span> <span data-ttu-id="f0353-106">I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.</span><span class="sxs-lookup"><span data-stu-id="f0353-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="when-an-enrollment-is-expired-for-a-terminated-employee-the-leave-type-balance-and-amount-are-all-cleared-in-the-leave-enrollment-form-444867"></a><span data-ttu-id="f0353-107">Alla scadenza di un'iscrizione per un dipendente licenziato, il tipo di congedo, il saldo e l'importo vengono cancellati nel modulo di iscrizione congedo (444867)</span><span class="sxs-lookup"><span data-stu-id="f0353-107">When an enrollment is expired for a terminated employee, the leave type, balance, and amount are all cleared in the Leave enrollment form (444867)</span></span>

<span data-ttu-id="f0353-108">I valori in **Tipo di congedo**, **Saldo** e **Importo** vengono ora mantenuti anziché cancellati dopo aver effettuato questa selezione.</span><span class="sxs-lookup"><span data-stu-id="f0353-108">Values in the **Leave type**, **Balance**, and **Amount** are now maintained instead of cleared upon making this selection.</span></span>

## <a name="incorrect-forecasted-balance-when-new-feature-leave-accrual-for-a-single-company-or-a-single-plan-is-enabled-456553"></a><span data-ttu-id="f0353-109">Saldo previsto errato quando è abilitata la nuova funzionalità (accumulo congedo per una singola società o un singolo piano) (456553)</span><span class="sxs-lookup"><span data-stu-id="f0353-109">Incorrect forecasted balance when new feature (Leave accrual for a single company or a single plan) is enabled (456553)</span></span>

<span data-ttu-id="f0353-110">Il saldo previsto corretto viene ora visualizzato quanto l'accumulo congedo per una singola società o un singolo piano è stato abilitato.</span><span class="sxs-lookup"><span data-stu-id="f0353-110">The correct forecasted balance now displays when the leave accrual for a single company or single plan has been enabled.</span></span>

## <a name="entities-with-relations-that-result-in-duplicate-navigation-properties-456486"></a><span data-ttu-id="f0353-111">Entità con relazioni che generano proprietà di navigazione duplicate (456486)</span><span class="sxs-lookup"><span data-stu-id="f0353-111">Entities with relations that result in duplicate navigation properties (456486)</span></span>

<span data-ttu-id="f0353-112">Questa versione corregge un problema con le proprietà di navigazione (relazione) di più entità.</span><span class="sxs-lookup"><span data-stu-id="f0353-112">This release corrects an issue with the navigation properties (relation) of multiple entities.</span></span> <span data-ttu-id="f0353-113">Vengono rilevate relazioni duplicate.</span><span class="sxs-lookup"><span data-stu-id="f0353-113">Duplicate relations are detected.</span></span> <span data-ttu-id="f0353-114">Questi scenari sono stati tutti corretti.</span><span class="sxs-lookup"><span data-stu-id="f0353-114">These scenarios have all been corrected.</span></span>
 
## <a name="cross-company-comments-on-performance-review-455536"></a><span data-ttu-id="f0353-115">Commenti interaziendali sulla revisione delle prestazioni (455536)</span><span class="sxs-lookup"><span data-stu-id="f0353-115">Cross-company comments on Performance review (455536)</span></span>

<span data-ttu-id="f0353-116">I commenti interaziendali sono ora visibili sulle revisioni delle prestazioni con questa correzione.</span><span class="sxs-lookup"><span data-stu-id="f0353-116">Cross-company comments are now visible on performance reviews with this fix.</span></span> <span data-ttu-id="f0353-117">Questa modifica corregge la visualizzazione dei commenti dei revisori inseriti in diverse società per la stessa revisione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f0353-117">This change corrects the view of reviewer comments that were entered in different companies for the same performance review.</span></span>
 
## <a name="inconsistency-in-showing-compensation-management-data-432562"></a><span data-ttu-id="f0353-118">Incoerenza nella visualizzazione dei dati di gestione della retribuzione (432562)</span><span class="sxs-lookup"><span data-stu-id="f0353-118">Inconsistency in showing compensation management data (432562)</span></span>

<span data-ttu-id="f0353-119">Una visualizzazione coerente dei dati di retribuzione è ora mantenuta in Responsabile self-service.</span><span class="sxs-lookup"><span data-stu-id="f0353-119">A consistent view of compensation data is now maintained in Manager self service.</span></span> <span data-ttu-id="f0353-120">A seconda di come passi **Dettagli retribuzione** del lavoratore, i dati di retribuzione ora vengono visualizzati in modo coerente per i responsabili.</span><span class="sxs-lookup"><span data-stu-id="f0353-120">Depending on how you navigate to a worker's **Compensation details**, compensation data now consistently displays to managers.</span></span>
 
## <a name="fixed-compensation-plans-effective-date-defaults-to-todays-date-411994"></a><span data-ttu-id="f0353-121">La data effettiva del piano di retribuzione è impostata in modo predefinito sulla data odierna (411994)</span><span class="sxs-lookup"><span data-stu-id="f0353-121">Fixed compensation plan's effective date defaults to today's date (411994)</span></span>

<span data-ttu-id="f0353-122">La data di inizio della retribuzione è basata basa ora sulla data di inizio della posizione assegnata al dipendente.</span><span class="sxs-lookup"><span data-stu-id="f0353-122">The compensation start date is now based on the start date of the position being assigned to the employee.</span></span>

## <a name="leave-and-absence-form-enable-half-day-definition-is-disabled-when-form-opens-452607"></a><span data-ttu-id="f0353-123">L'opzione Abilita la definizione di mezza giornata del modulo di congedo e assenza è disabilitata all'apertura del modulo (452607)</span><span class="sxs-lookup"><span data-stu-id="f0353-123">Leave and absence form Enable half day definition is disabled when form opens (452607)</span></span>

<span data-ttu-id="f0353-124">Con questa modifica, **Abilita la definizione di mezza giornata** sarà abilitata fino a quando non saranno presenti nuove transazioni di congedo.</span><span class="sxs-lookup"><span data-stu-id="f0353-124">With this change, the **Enable half day definition** will be enabled until new leave transactions exist.</span></span> 

## <a name="unable-to-publish-to-hcmdiscussionentity-via-excel-totalratingscore-field-error-453899"></a><span data-ttu-id="f0353-125">Impossibile pubblicare su HcmDiscussionEntity tramite Excel; errore del campo TotalRatingScore (453899)</span><span class="sxs-lookup"><span data-stu-id="f0353-125">Unable to publish to HcmDiscussionEntity via Excel; TotalRatingScore field error (453899)</span></span>

<span data-ttu-id="f0353-126">Ora puoi aggiornare il campo **TotalRatingScore** utilizzando **HCMDiscussionEntity** nella finestra di progettazione delle cartelle di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="f0353-126">You can now update the **TotalRatingScore** field using **HCMDiscussionEntity** in the Excel workbook designer.</span></span>

## <a name="in-preview"></a><span data-ttu-id="f0353-127">In anteprima</span><span class="sxs-lookup"><span data-stu-id="f0353-127">In preview</span></span>

## <a name="database-logging"></a><span data-ttu-id="f0353-128">Registrazione database</span><span class="sxs-lookup"><span data-stu-id="f0353-128">Database logging</span></span>

<span data-ttu-id="f0353-129">La registrazione del database consente di determinare quali tabelle e quali campi monitorare.</span><span class="sxs-lookup"><span data-stu-id="f0353-129">Database logging allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="f0353-130">Inoltre, consente di determinare gli eventi che dovrebbero attivare il rilevamento delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="f0353-130">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="f0353-131">Usare le funzionalità di registrazione del database per visualizzare tali modifiche nel tempo.</span><span class="sxs-lookup"><span data-stu-id="f0353-131">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="f0353-132">Per ulteriori informazioni, vedi [Configurare e gestire la registrazione del database](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="f0353-132">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="f0353-133">Campi obbligatori</span><span class="sxs-lookup"><span data-stu-id="f0353-133">Mandatory fields</span></span> 

<span data-ttu-id="f0353-134">Ora puoi rendere obbligatori i campi utilizzando le funzionalità di personalizzazione di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f0353-134">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="f0353-135">Questa funzionalità richiede **Visualizzazioni salvate**.</span><span class="sxs-lookup"><span data-stu-id="f0353-135">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="f0353-136">Applicazione Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="f0353-136">Human Resources application in Teams</span></span>

<span data-ttu-id="f0353-137">I dipendenti possono visualizzare i congedi e richiederli in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f0353-137">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="f0353-138">Possono interagire con un bot per creare richieste di congedo.</span><span class="sxs-lookup"><span data-stu-id="f0353-138">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="f0353-139">Per ulteriori informazioni, vedere [App Human Resources in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="f0353-139">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="f0353-140">Entità Data Management Framework per la gestione di benefit</span><span class="sxs-lookup"><span data-stu-id="f0353-140">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="f0353-141">Le entità di gestione di benefit sono in fase di rilascio.</span><span class="sxs-lookup"><span data-stu-id="f0353-141">Benefits management entities are releasing.</span></span> <span data-ttu-id="f0353-142">Le entità DMF consentono di importare ed esportare dati per configurare facilmente la gestione dei benefit.</span><span class="sxs-lookup"><span data-stu-id="f0353-142">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="f0353-143">Sarà disponibile un modello di gestione dei benefit per spostare i dati.</span><span class="sxs-lookup"><span data-stu-id="f0353-143">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="f0353-144">Il modello esporta e importa i dati in modo in modo sequenziale per rispettare le dipendenze dei dati.</span><span class="sxs-lookup"><span data-stu-id="f0353-144">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="f0353-145">Acquista e vendi congedo</span><span class="sxs-lookup"><span data-stu-id="f0353-145">Buy and sell leave</span></span> 

<span data-ttu-id="f0353-146">Alcune organizzazioni offrono un benefit che consente ai dipendenti di acquistare o vendere congedi.</span><span class="sxs-lookup"><span data-stu-id="f0353-146">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="f0353-147">Questo processo è spesso gestito manualmente.</span><span class="sxs-lookup"><span data-stu-id="f0353-147">This process is often managed manually.</span></span> <span data-ttu-id="f0353-148">Questa funzione automatizza la gestione dei criteri e delle richieste per il dipartimento Risorse umane.</span><span class="sxs-lookup"><span data-stu-id="f0353-148">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="f0353-149">Semplifica il processo di gestione delle ferie e aiuta a eliminare gli errori.</span><span class="sxs-lookup"><span data-stu-id="f0353-149">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="f0353-150">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="f0353-150">For more information, see:</span></span>

- [<span data-ttu-id="f0353-151">Gestire i criteri di acquisto e vendita congedo</span><span class="sxs-lookup"><span data-stu-id="f0353-151">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="f0353-152">Acquista e vendi congedo</span><span class="sxs-lookup"><span data-stu-id="f0353-152">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="f0353-153">Lascia l'attribuzione per una singola azienda o un singolo piano</span><span class="sxs-lookup"><span data-stu-id="f0353-153">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="f0353-154">I clienti possono elaborare attribuzioni per una singola azienda o un singolo piano di ferie e assenze.</span><span class="sxs-lookup"><span data-stu-id="f0353-154">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="f0353-155">Questa capacità fornisce chiarezza nel processo di maturazione per i clienti con diversi anni di ferie o politiche di maturazione delle ferie.</span><span class="sxs-lookup"><span data-stu-id="f0353-155">This ability provides clarity into the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="f0353-156">Per ulteriori informazioni, vedi [Accumulare congedi per società o per piano di congedo](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="f0353-156">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="f0353-157">Aggiungi allegati alle richieste di ferie</span><span class="sxs-lookup"><span data-stu-id="f0353-157">Add attachments to time off requests</span></span>

<span data-ttu-id="f0353-158">La possibilità di aggiungere allegati alle richieste di ferie approvate è fondamentale nell'attuale ambiente COVID-19.</span><span class="sxs-lookup"><span data-stu-id="f0353-158">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="f0353-159">I dipendenti possono ora aggiungere questi allegati.</span><span class="sxs-lookup"><span data-stu-id="f0353-159">Employees can now add these attachments.</span></span> <span data-ttu-id="f0353-160">Hanno anche maggiori informazioni dettagliate su come vengono effettuati gli aggiornamenti per lasciare le richieste.</span><span class="sxs-lookup"><span data-stu-id="f0353-160">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="f0353-161">Per ulteriori informazioni, vedi [Aggiungi un allegato a una richiesta esistente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="f0353-161">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="f0353-162">Aggiungi il codice motivo alle sospensioni degli accumuli</span><span class="sxs-lookup"><span data-stu-id="f0353-162">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="f0353-163">Codici motivo sono stati aggiunti alla sospensione degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="f0353-163">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="f0353-164">Regole di riporto</span><span class="sxs-lookup"><span data-stu-id="f0353-164">Carry forward rules</span></span> 

<span data-ttu-id="f0353-165">È possibile specificare un tipo di congedo riporto per i saldi del riporto in cui vengono trasferiti le rettifiche di riporto.</span><span class="sxs-lookup"><span data-stu-id="f0353-165">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="f0353-166">Ad esempio, se un dipendente riporta 10 giorni, è possibile scegliere un tipo di congedo diverso per quei 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="f0353-166">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="f0353-167">Per ulteriori informazioni, vedere [Configurare i tipi di congedo e assenza](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="f0353-167">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="f0353-168">Sospendi l'accumulo dei congedi per determinati tipi di congedo</span><span class="sxs-lookup"><span data-stu-id="f0353-168">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="f0353-169">Puoi creare una regola per sospendere gli accumuli dei congedi per i dipendenti con richieste di congedo inserite per congedi non retribuiti.</span><span class="sxs-lookup"><span data-stu-id="f0353-169">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="f0353-170">Il congedo non retribuito può essere un tipo, ma non è necessario che lo sia.</span><span class="sxs-lookup"><span data-stu-id="f0353-170">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="f0353-171">È possibile sospendere qualsiasi congedo in base a un altro tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="f0353-171">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="f0353-172">Entità DMF disponibile per le sospensioni degli accumuli</span><span class="sxs-lookup"><span data-stu-id="f0353-172">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="f0353-173">Un'entità DMF è ora disponibile per le sospensioni degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="f0353-173">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="f0353-174">Presto disponibili</span><span class="sxs-lookup"><span data-stu-id="f0353-174">Coming soon</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="f0353-175">Configurare il nome del self-service dipendenti</span><span class="sxs-lookup"><span data-stu-id="f0353-175">Configure the name of Employee self-service</span></span>

<span data-ttu-id="f0353-176">Una nuova opzione sarà disponibile nei **parametri Risorse umane** per aggiornare il nome dell'area di lavoro Self-service dipendenti in Self-service.</span><span class="sxs-lookup"><span data-stu-id="f0353-176">A new option will be available in **Human Resources parameters** to update the name of the Employee self service workspace to Self service.</span></span>

## <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="f0353-177">Elenco di controllo entità incluso in Dataverse</span><span class="sxs-lookup"><span data-stu-id="f0353-177">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="f0353-178">Le entità dell'elenco di controllo per i processi di onboarding, offboarding, trasferimenti e aziendali saranno presto disponibili in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="f0353-178">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon within Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0353-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0353-179">See also</span></span>

[<span data-ttu-id="f0353-180">Novità o modifiche in Human Resources</span><span class="sxs-lookup"><span data-stu-id="f0353-180">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="f0353-181">Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019</span><span class="sxs-lookup"><span data-stu-id="f0353-181">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="f0353-182">Aggiornare un processo</span><span class="sxs-lookup"><span data-stu-id="f0353-182">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="f0353-183">Gestire le funzionalità</span><span class="sxs-lookup"><span data-stu-id="f0353-183">Manage features</span></span>](hr-admin-manage-features.md)