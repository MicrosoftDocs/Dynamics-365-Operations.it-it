---
title: Novità e modifiche in Dynamics 365 Human Resources (20 agosto 2020)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 20 agosto 2020.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f0e8e450a4c4fd515419c735f9307be80c8df098
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054478"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-20-2020"></a><span data-ttu-id="5b679-103">Novità e modifiche in Dynamics 365 Human Resources (20 agosto 2020)</span><span class="sxs-lookup"><span data-stu-id="5b679-103">What's new or changed in Dynamics 365 Human Resources (August 20, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="5b679-104">Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5b679-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="5b679-105">Le modifiche si applicano alla build 8.1.3478.</span><span class="sxs-lookup"><span data-stu-id="5b679-105">Changes apply to build number 8.1.3478.</span></span> <span data-ttu-id="5b679-106">I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Lifecycle Services (LCS) per riferimento.</span><span class="sxs-lookup"><span data-stu-id="5b679-106">The numbers in parentheses in some headings refer to Lifecycle Services (LCS) support numbers for reference.</span></span>

## <a name="show-upcoming-and-pending-leave-of-absence-information-to-cards-in-people-workspace"></a><span data-ttu-id="5b679-107">Mostrare le informazioni sui congedi imminenti e in sospeso nelle schede dell'area di lavoro Persone</span><span class="sxs-lookup"><span data-stu-id="5b679-107">Show upcoming and pending leave of absence information to cards in People workspace</span></span>

<span data-ttu-id="5b679-108">Le opzioni di richiesta di congedo in sospeso e imminente sono ora disponibili nelle schede Congedo e assenza nell'area di lavoro **Persone**.</span><span class="sxs-lookup"><span data-stu-id="5b679-108">Pending and upcoming leave request options are now available on the Leave and absence cards in the **People** workspace.</span></span>

## <a name="private-field-isnt-yes-by-default-for-employee-role-in-employee-self-service-477106"></a><span data-ttu-id="5b679-109">Il campo privato non è Sì per impostazione predefinita per il ruolo dipendente in Self-service dipendenti (477106)</span><span class="sxs-lookup"><span data-stu-id="5b679-109">Private field isn't Yes by default for Employee role in Employee self service (477106)</span></span>

<span data-ttu-id="5b679-110">Il campo **Privato** ora è impostato su **Sì** quando i dipendenti aggiungono nuovi record di indirizzi tramite la pagina **Informazione personale** in Self-service dipendenti.</span><span class="sxs-lookup"><span data-stu-id="5b679-110">The **Private** field now defaults to **Yes** when employees add new address records through the **Personal information** page in Employee self service.</span></span> 

## <a name="candidates-to-hire-fasttab-in-personnel-management-shows-an-incorrect-count-of-candidates-470110"></a><span data-ttu-id="5b679-111">La scheda dettaglio Candidati da assumere nella gestione del personale mostra un conteggio errato dei candidati (470110)</span><span class="sxs-lookup"><span data-stu-id="5b679-111">Candidates to hire FastTab in Personnel management shows an incorrect count of candidates (470110)</span></span>

<span data-ttu-id="5b679-112">La pagina **Gestione personale** ora mostra accuratamente il numero di candidati da assumere.</span><span class="sxs-lookup"><span data-stu-id="5b679-112">The **Personnel management** page now accurately displays the number of candidates to hire.</span></span> 

## <a name="cant-enter-sickness-for-terminated-employee-when-accrual-is-set-to-zero-446195"></a><span data-ttu-id="5b679-113">Impossibile inserire la malattia per il dipendente licenziato quando l'accumulo è impostato su zero (446195)</span><span class="sxs-lookup"><span data-stu-id="5b679-113">Can’t enter sickness for terminated employee when accrual is set to zero (446195)</span></span>

<span data-ttu-id="5b679-114">Le transazioni di congedo sono ora consentite per i dipendenti licenziati in futuro e l'accumulo è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="5b679-114">Leave transactions are now allowed for employees that have been terminated in the future and the accrual is set to zero.</span></span> <span data-ttu-id="5b679-115">Le transazioni di congedo possono essere inserite fino alla data di licenziamento del dipendente.</span><span class="sxs-lookup"><span data-stu-id="5b679-115">Leave transactions can be entered up to the termination date of the employee.</span></span> 

## <a name="adding-custom-fields-to-the-new-worker-form-disables-the-fields-in-the-action-pane-for-manage-leave-473314"></a><span data-ttu-id="5b679-116">L'aggiunta di campi personalizzati al nuovo modulo Lavoratore disabilita i campi nel riquadro azioni per Gestisci congedo (473314)</span><span class="sxs-lookup"><span data-stu-id="5b679-116">Adding custom fields to the new Worker form disables the fields in the action pane for Manage leave (473314)</span></span>

<span data-ttu-id="5b679-117">Le opzioni del riquadro azioni sul nuovo modulo **Lavoratore** in **Gestisci congedo** non saranno più disabilitate se i campi personalizzati vengono aggiunti al nuovo modulo **Lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="5b679-117">Action pane options on the new **Worker** form in **Manage leave** will no longer be disabled if custom fields have been added to the new **Worker** form.</span></span>

## <a name="making-the-leave-comment-field-mandatory-allows-a-leave-request-to-be-submitted-when-no-comment-is-entered-473543"></a><span data-ttu-id="5b679-118">Rendere obbligatorio il campo per il commento consente di inviare una richiesta di congedo quando non viene inserito alcun commento (473543)</span><span class="sxs-lookup"><span data-stu-id="5b679-118">Making the Leave comment field mandatory allows a leave request to be submitted when no comment is entered (473543)</span></span>

<span data-ttu-id="5b679-119">I campi dei commenti ora possono essere obbligatori e le richieste di congedo rispettano questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="5b679-119">Comment fields can now be mandatory, and leave requests honor this setting.</span></span> <span data-ttu-id="5b679-120">I campi obbligatori sono una funzione di anteprima.</span><span class="sxs-lookup"><span data-stu-id="5b679-120">Mandatory fields is a preview feature.</span></span>

### <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="5b679-121">Entità DMF disponibile per le sospensioni degli accumuli</span><span class="sxs-lookup"><span data-stu-id="5b679-121">DMF entity available for accrual suspensions</span></span>

<span data-ttu-id="5b679-122">Un'entità DMF è ora disponibile per le sospensioni degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="5b679-122">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="in-preview"></a><span data-ttu-id="5b679-123">In anteprima</span><span class="sxs-lookup"><span data-stu-id="5b679-123">In preview</span></span>

### <a name="mandatory-fields"></a><span data-ttu-id="5b679-124">Campi obbligatori</span><span class="sxs-lookup"><span data-stu-id="5b679-124">Mandatory fields</span></span>

<span data-ttu-id="5b679-125">È ora possibile rendere obbligatori i campi utilizzando le funzionalità di personalizzazione di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5b679-125">You can make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="5b679-126">Questa funzionalità richiede **Visualizzazioni salvate**.</span><span class="sxs-lookup"><span data-stu-id="5b679-126">This feature requires **Saved views**.</span></span> <span data-ttu-id="5b679-127">Per ulteriori informazioni sulle visualizzazioni salvate, vedere:</span><span class="sxs-lookup"><span data-stu-id="5b679-127">For more information about saved views, see:</span></span>

- <span data-ttu-id="5b679-128">[Visualizzazioni salvate - disponibilità generale](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) nel piano della seconda ondata di rilascio di Dynamics 365 2020</span><span class="sxs-lookup"><span data-stu-id="5b679-128">[Saved views - general availability](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) in the Dynamics 365 2020 release wave 2 plan</span></span>
- [<span data-ttu-id="5b679-129">Creare moduli che utilizzano interamente visualizzazioni salvate</span><span class="sxs-lookup"><span data-stu-id="5b679-129">Build forms that fully utilize saved views</span></span>](../fin-ops-core/dev-itpro/user-interface/understanding-saved-views.md)

### <a name="human-resources-application-in-teams"></a><span data-ttu-id="5b679-130">Applicazione Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="5b679-130">Human Resources application in Teams</span></span>

<span data-ttu-id="5b679-131">I dipendenti possono visualizzare i congedi e richiederli in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5b679-131">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="5b679-132">Possono interagire con un bot per creare richieste di congedo.</span><span class="sxs-lookup"><span data-stu-id="5b679-132">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="5b679-133">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="5b679-133">For more information, see:</span></span>

- <span data-ttu-id="5b679-134">[Esperienza di congedo e assenza dei dipendenti in Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) nel piano della prima ondata di rilascio di Dynamics 365 2020</span><span class="sxs-lookup"><span data-stu-id="5b679-134">[Employee leave and absence experience in Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) in the Dynamics 365 2020 release wave 1 plan</span></span>
- [<span data-ttu-id="5b679-135">App Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="5b679-135">Human Resources app in Teams</span></span>](./hr-admin-teams-leave-app.md)

## <a name="coming-soon"></a><span data-ttu-id="5b679-136">Presto disponibili</span><span class="sxs-lookup"><span data-stu-id="5b679-136">Coming soon</span></span>

### <a name="human-resources-app-in-teams-preview-features"></a><span data-ttu-id="5b679-137">Funzioni di anteprima dell'app Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="5b679-137">Human Resources app in Teams preview features</span></span>
 
-  <span data-ttu-id="5b679-138">**Notifiche**: i mittenti e gli approvatori delle richieste di permesso verranno informati nell'app Human Resources in Teams.</span><span class="sxs-lookup"><span data-stu-id="5b679-138">**Notifications**: Submitters and approvers of time-off requests will be notified in the Human Resources app in Teams.</span></span> <span data-ttu-id="5b679-139">Gli approvatori potranno approvare o rifiutare le richieste di permesso e i mittenti riceveranno una notifica se la richiesta è stata approvata o rifiutata.</span><span class="sxs-lookup"><span data-stu-id="5b679-139">Approvers will be able to approve or deny time-off requests, and submitters will be notified if the request was approved or denied.</span></span>
 
- <span data-ttu-id="5b679-140">**Calendario permessi del responsabile**: i responsabili potranno vedere i permessi approvati e in sospeso per i loro diretti subalterni in una visualizzazione calendario.</span><span class="sxs-lookup"><span data-stu-id="5b679-140">**Manager time-off calendar**: Managers will be able to see approved and pending time off for their direct reports in a calendar view.</span></span> <span data-ttu-id="5b679-141">Questa visualizzazione fornisce una facile comprensione di quando i membri del team non sono al lavoro.</span><span class="sxs-lookup"><span data-stu-id="5b679-141">This view provides an easy understanding of when their team members are away from work.</span></span>

### <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="5b679-142">Elenco di controllo entità incluso in Dataverse</span><span class="sxs-lookup"><span data-stu-id="5b679-142">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="5b679-143">Le entità dell'elenco di controllo per i processi di onboarding, offboarding, trasferimenti e aziendali saranno presto disponibili in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5b679-143">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Dataverse.</span></span>

## <a name="known-issues"></a><span data-ttu-id="5b679-144">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="5b679-144">Known issues</span></span>

<span data-ttu-id="5b679-145">L'area di lavoro **Gestione funzionalità** potrebbe visualizzare funzioni disabilitate come funzioni di anteprima quando sono generalmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="5b679-145">The **Feature management** workspace may be displaying features that are disabled as preview features when they are generally available.</span></span> <span data-ttu-id="5b679-146">Di seguito è riportato un elenco di funzionalità generalmente disponibili che mostrano uno stato errato.</span><span class="sxs-lookup"><span data-stu-id="5b679-146">Below is a list of generally available features that show an incorrect status.</span></span> 

- <span data-ttu-id="5b679-147">Gestione benefit</span><span class="sxs-lookup"><span data-stu-id="5b679-147">Benefits management</span></span>
- <span data-ttu-id="5b679-148">Gestione casi</span><span class="sxs-lookup"><span data-stu-id="5b679-148">Case management</span></span>
- <span data-ttu-id="5b679-149">Registrazione database (controllo)</span><span class="sxs-lookup"><span data-stu-id="5b679-149">Database logging (Auditing)</span></span>
- <span data-ttu-id="5b679-150">Accumulo per congedo di una singola società o un singolo piano</span><span class="sxs-lookup"><span data-stu-id="5b679-150">Leave accrual for a single company or a single plan</span></span>
- <span data-ttu-id="5b679-151">Sospensione accumuli per congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="5b679-151">Leave and absence accrual suspension</span></span>
- <span data-ttu-id="5b679-152">Codice motivo rettifica saldo e commento</span><span class="sxs-lookup"><span data-stu-id="5b679-152">Balance adjustment reason code and comment</span></span>
- <span data-ttu-id="5b679-153">Acquista e vendi congedo</span><span class="sxs-lookup"><span data-stu-id="5b679-153">Buy and sell leave</span></span>
- <span data-ttu-id="5b679-154">Calendario di congedi e assenze</span><span class="sxs-lookup"><span data-stu-id="5b679-154">Leave and absence calendar</span></span>
- <span data-ttu-id="5b679-155">Regole di riporto per congedo</span><span class="sxs-lookup"><span data-stu-id="5b679-155">Leave carry-forward rules</span></span>
- <span data-ttu-id="5b679-156">Controllo accumulo per congedo</span><span class="sxs-lookup"><span data-stu-id="5b679-156">Leave accrual auditing</span></span>
- <span data-ttu-id="5b679-157">Eliminazione accumuli per congedo</span><span class="sxs-lookup"><span data-stu-id="5b679-157">Leave accrual deletion</span></span>
- <span data-ttu-id="5b679-158">Arrotondamento accumulo per congedo</span><span class="sxs-lookup"><span data-stu-id="5b679-158">Leave accrual rounding</span></span>
- <span data-ttu-id="5b679-159">Configura più tipi di congedo in un piano di congedo singolo</span><span class="sxs-lookup"><span data-stu-id="5b679-159">Configure multiple leave types on a single leave plan</span></span>
- <span data-ttu-id="5b679-160">Aggiornamento del permesso migliorato</span><span class="sxs-lookup"><span data-stu-id="5b679-160">Update time-off enhancements</span></span>
- <span data-ttu-id="5b679-161">Utilizza l'equivalenza a tempo pieno del dipendente per gli accumuli</span><span class="sxs-lookup"><span data-stu-id="5b679-161">Use an employee's FTE for accruals</span></span>
- <span data-ttu-id="5b679-162">Visualizzazione retribuzione interaziendale</span><span class="sxs-lookup"><span data-stu-id="5b679-162">Cross company compensation view</span></span>
- <span data-ttu-id="5b679-163">Stampare le valutazioni delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="5b679-163">Print performance reviews</span></span>
- <span data-ttu-id="5b679-164">Correzioni giorni festivi accumulo per congedo</span><span class="sxs-lookup"><span data-stu-id="5b679-164">Leave accrual holiday corrections</span></span>

### <a name="benefit-plan-employee-entity"></a><span data-ttu-id="5b679-165">Entità dipendente del piano di benefit</span><span class="sxs-lookup"><span data-stu-id="5b679-165">Benefit plan employee entity</span></span> 

<span data-ttu-id="5b679-166">Abbiamo recentemente scoperto due problemi riguardanti l'entità **BenefitsPlanEmployee**.</span><span class="sxs-lookup"><span data-stu-id="5b679-166">We have recently discovered two issues regarding the **BenefitsPlanEmployee** entity.</span></span> <span data-ttu-id="5b679-167">Quando si importano le iscrizioni dei lavoratori, il **Codice di copertura** e il **Codice tipo piano** vengono impostati in modo errato.</span><span class="sxs-lookup"><span data-stu-id="5b679-167">When importing worker enrollments, the **Coverage code** and the **Plan type code** are being set incorrectly.</span></span> <span data-ttu-id="5b679-168">Questo problema causa la visualizzazione errata dei piani di benefit per i dipendenti nel modulo **Piano di benefit del lavoratore** e nel modulo **Iscrizione aperta** in Self-service dipendente.</span><span class="sxs-lookup"><span data-stu-id="5b679-168">This issue causes employee benefit plans to display incorrectly in the **Worker benefits plan** form and in the **Open enrollment** form in Employee self service.</span></span> <span data-ttu-id="5b679-169">Questo problema può anche influire sulla capacità del dipendente di selezionare i piani in Self-service dipendente.</span><span class="sxs-lookup"><span data-stu-id="5b679-169">This issue can also impact the employee's ability to select plans in Employee self service.</span></span> <span data-ttu-id="5b679-170">Al momento non c'è una soluzione alternativa.</span><span class="sxs-lookup"><span data-stu-id="5b679-170">Currently there isn't a workaround.</span></span> <span data-ttu-id="5b679-171">Consideriamo questo come una soluzione ad alta priorità e implementeremo la correzione nella prossima versione.</span><span class="sxs-lookup"><span data-stu-id="5b679-171">We're treating this as a high-priority fix and will roll out the fix with our next release.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b679-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b679-172">See also</span></span>

[<span data-ttu-id="5b679-173">Novità o modifiche in Human Resources</span><span class="sxs-lookup"><span data-stu-id="5b679-173">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="5b679-174">Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019</span><span class="sxs-lookup"><span data-stu-id="5b679-174">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="5b679-175">Aggiornare un processo</span><span class="sxs-lookup"><span data-stu-id="5b679-175">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="5b679-176">Gestire le funzionalità</span><span class="sxs-lookup"><span data-stu-id="5b679-176">Manage features</span></span>](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]