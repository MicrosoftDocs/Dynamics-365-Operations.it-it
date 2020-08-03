---
title: Novità o modifiche in Dynamics 365 Human Resources (14 maggio 2020)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 05/14/2020
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
ms.author: dkrame
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3ce1aca9cebc5b330f054a11e38b5dfc4fc9109d
ms.sourcegitcommit: bd9ff0d28718d535356ffbe1cffaaf60310dd430
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "3555173"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-14-2020"></a><span data-ttu-id="a524b-103">Novità o modifiche in Dynamics 365 Human Resources (14 maggio 2020)</span><span class="sxs-lookup"><span data-stu-id="a524b-103">What's new or changed in Dynamics 365 Human Resources (May 14, 2020)</span></span>

<span data-ttu-id="a524b-104">Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a524b-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="a524b-105">Le modifiche si applicano alla build 8.1.3244.</span><span class="sxs-lookup"><span data-stu-id="a524b-105">Changes apply to build number 8.1.3244.</span></span> <span data-ttu-id="a524b-106">I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Lifecycle Services (LCS) per riferimento.</span><span class="sxs-lookup"><span data-stu-id="a524b-106">The numbers in parentheses in some headings refer to Lifecycle Services (LCS) support numbers for reference.</span></span>

## <a name="platform-changes"></a><span data-ttu-id="a524b-107">Modifiche della piattaforma</span><span class="sxs-lookup"><span data-stu-id="a524b-107">Platform changes</span></span>

<span data-ttu-id="a524b-108">Le modifiche alla piattaforma sono incluse nella versione di questa settimana.</span><span class="sxs-lookup"><span data-stu-id="a524b-108">Platform changes are included in this week's release.</span></span> <span data-ttu-id="a524b-109">Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.10 delle app Finance and Operations (maggio 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34).</span><span class="sxs-lookup"><span data-stu-id="a524b-109">For more information, see [Platform updates for version 10.0.10 of Finance and Operations apps (May 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34).</span></span> <span data-ttu-id="a524b-110">Questa versione include correzioni di bug e modifiche alle viste salvate.</span><span class="sxs-lookup"><span data-stu-id="a524b-110">This release includes bug fixes and changes to saved views.</span></span>
 
## <a name="ensure-common-data-service-picklists-are-consistent-with-leave-enums-436343"></a><span data-ttu-id="a524b-111">Verificare che le distinte di prelievo Common Data Service siano coerenti con le enumerazioni Leave (436343)</span><span class="sxs-lookup"><span data-stu-id="a524b-111">Ensure Common Data Service picklists are consistent with Leave enums (436343)</span></span>

<span data-ttu-id="a524b-112">Le distinte di prelievo Common Data Service sono ora coerenti con le enumerazioni Leave.</span><span class="sxs-lookup"><span data-stu-id="a524b-112">Common Data Service picklists are now consistent with Leave enums.</span></span>

## <a name="allow-users-to-configure-leave-request-workflow-based-on-the-request-amount-300044"></a><span data-ttu-id="a524b-113">Consenti agli utenti di configurare il flusso di lavoro della richiesta di congedo in base all'importo della richiesta (300044)</span><span class="sxs-lookup"><span data-stu-id="a524b-113">Allow users to configure leave request workflow based on the request amount (300044)</span></span>

<span data-ttu-id="a524b-114">Gli utenti possono configurare i flussi di lavoro delle richieste di congedo in base alla quantità delle richieste.</span><span class="sxs-lookup"><span data-stu-id="a524b-114">Users can configure leave requests workflows based on request amounts.</span></span>
 
## <a name="new-worker-form-exposes-data-through-the-view-menu-when-advanced-security-is-enabled-403185"></a><span data-ttu-id="a524b-115">Il nuovo modulo del lavoratore espone i dati attraverso il menu Visualizza quando è abilitata la sicurezza avanzata (403185)</span><span class="sxs-lookup"><span data-stu-id="a524b-115">New worker form exposes data through the View menu when advanced security is enabled (403185)</span></span>

<span data-ttu-id="a524b-116">Questa versione corregge le modalità di visualizzazione dei lavoratori attraverso le persone giuridiche quando è abilitato l'accesso avanzato e sono accessibili i lavoratori di altre società.</span><span class="sxs-lookup"><span data-stu-id="a524b-116">This release corrects how viewing workers across legal entities functions when advanced access is enabled and workers in other companies are accessible.</span></span>

## <a name="allow-running-leave-accruals-for-a-single-plan-or-a-single-company-318844"></a><span data-ttu-id="a524b-117">Consenti l'esecuzione della maturazione delle ferie per un singolo piano o una singola azienda (318844)</span><span class="sxs-lookup"><span data-stu-id="a524b-117">Allow running leave accruals for a single plan or a single company (318844)</span></span>

<span data-ttu-id="a524b-118">Con questa modifica, puoi eseguire la maturazione per un'azienda o un piano.</span><span class="sxs-lookup"><span data-stu-id="a524b-118">With this change, you can run accruals for a company or a plan.</span></span>
 
## <a name="show-the-positions-full-time-equivalent-fte-in-the-enrolled-workers-form-414658"></a><span data-ttu-id="a524b-119">Mostra l'equivalente al tempo pieno della posizione (ETP) nel modulo dei lavoratori iscritti (414658)</span><span class="sxs-lookup"><span data-stu-id="a524b-119">Show the position's full-time equivalent (FTE) in the Enrolled workers form (414658)</span></span>

<span data-ttu-id="a524b-120">Il valore FTE dalla posizione di un lavoratore determina il tasso di maturazione di un lavoratore quando l'opzione FTE è abilitata sul tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="a524b-120">The FTE value from a worker's position determines a worker's accrual rate when the FTE option is enabled on the leave type.</span></span> <span data-ttu-id="a524b-121">Questo campo è ora incluso nel modulo **Lavoratori iscritti** e nella finestra **Iscrizione collettiva**.</span><span class="sxs-lookup"><span data-stu-id="a524b-121">This field is now included in **Enrolled workers** form and the **Mass enrollment** dialog.</span></span>

## <a name="add-leave-balance-expiration-batch-job-431266"></a><span data-ttu-id="a524b-122">Aggiungi processo batch con scadenza saldo congedi (431266)</span><span class="sxs-lookup"><span data-stu-id="a524b-122">Add leave balance expiration batch job (431266)</span></span>

<span data-ttu-id="a524b-123">È ora disponibile un nuovo processo batch che viene eseguito quotidianamente.</span><span class="sxs-lookup"><span data-stu-id="a524b-123">A new batch job is now available that runs daily.</span></span> <span data-ttu-id="a524b-124">Diminuisce il saldo residuo delle ferie quando le date di scadenza diventano correnti.</span><span class="sxs-lookup"><span data-stu-id="a524b-124">It decreases the remaining leave balance when expiration dates become current.</span></span>

## <a name="exporting-personal-contacts-for-an-employee-using-the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-the-parent-relationship-type-345893"></a><span data-ttu-id="a524b-125">L'esportazione di contatti personali per un dipendente che utilizza l'entità persona di contatto personale del lavoratore non esporta i contatti personali con il tipo di relazione padre (345893)</span><span class="sxs-lookup"><span data-stu-id="a524b-125">Exporting personal contacts for an employee using the Worker personal contact person entity doesn't export personal contacts with the Parent relationship type (345893)</span></span>

<span data-ttu-id="a524b-126">L'entità dati **Persona di contatto personale del lavoratore** (**HcmPersonalContactPersonEntity** in DMF e **PersonalContactPerson** in OData) non è stata in grado di esportare i contatti personali che hanno un tipo di relazione **Padre**.</span><span class="sxs-lookup"><span data-stu-id="a524b-126">The **Worker personal contact person** data entity (**HcmPersonalContactPersonEntity** in DMF and **PersonalContactPerson** in OData) couldn't export personal contacts that have a relationship type of **Parent**.</span></span> <span data-ttu-id="a524b-127">Questo problema è stato risolto per i contatti personali creati dopo questa modifica.</span><span class="sxs-lookup"><span data-stu-id="a524b-127">This issue is fixed for personal contacts that are created after this change.</span></span> <span data-ttu-id="a524b-128">Contatti personali esistenti di tipo **Padre** verranno risolti in una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="a524b-128">Existing personal contacts of type **Parent** will be fixed in a later release.</span></span>

## <a name="reason-codes-display-across-different-scenarios-when-theyre-marked-as-leave-and-absence-and-the-streamlined-employee-form-is-enabled-434163"></a><span data-ttu-id="a524b-129">I codici motivo vengono visualizzati in diversi scenari quando sono contrassegnati come Congedo e assenza e il modulo dipendente semplificato è abilitato (434163)</span><span class="sxs-lookup"><span data-stu-id="a524b-129">Reason codes display across different scenarios when they're marked as Leave and absence and the streamlined employee form is enabled (434163)</span></span>

<span data-ttu-id="a524b-130">Questa modifica limita i codici motivo solo ai codici Permesso e Assenza quando si abilita l'inserimento semplificato dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="a524b-130">This change restricts the reason codes to only Leave and absence codes when you enable streamlined employee entry.</span></span>

## <a name="the-preview-feature-assign-a-leave-plan-to-employees-in-the-future-displays-error-433555"></a><span data-ttu-id="a524b-131">La funzionalità di anteprima Assegna un piano di ferie ai dipendenti in futuro visualizza l'errore (433555)</span><span class="sxs-lookup"><span data-stu-id="a524b-131">The preview feature Assign a leave plan to employees in the future displays error (433555)</span></span>

<span data-ttu-id="a524b-132">Questa modifica corregge un errore quando un piano ferie ha due tipi di ferie assegnati e si tenta di assegnare un dipendente.</span><span class="sxs-lookup"><span data-stu-id="a524b-132">This change corrects an error when a leave plan has two leave types assigned and you attempt to assign an employee.</span></span>

## <a name="getting-started-banner-appears-for-all-users-441731"></a><span data-ttu-id="a524b-133">Il banner Introduzione appare per tutti gli utenti (441731)</span><span class="sxs-lookup"><span data-stu-id="a524b-133">Getting started banner appears for all users (441731)</span></span>

<span data-ttu-id="a524b-134">Con questa modifica, il banner Introduzione viene nascosto per gli utenti che non sono amministratori di sistema o amministratori della gestione dei dati.</span><span class="sxs-lookup"><span data-stu-id="a524b-134">With this change, the Getting started banner is hidden for users that aren't System administrators or Data management administrators.</span></span> 

## <a name="the-common-data-service-worker-address-entity-works-differently-in-terms-of-date-time-effective-dates-in-human-resources-425071"></a><span data-ttu-id="a524b-135">L'entità Indirizzo lavoratore Common Data Service funziona in modo diverso in termini di date effettive di data e ora in Human Resources (425071)</span><span class="sxs-lookup"><span data-stu-id="a524b-135">The Common Data Service Worker Address entity works differently in terms of date time effective dates in Human Resources (425071)</span></span>

<span data-ttu-id="a524b-136">Questa modifica mantiene le informazioni sull'indirizzo allineate in determinati scenari, in base alle date dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="a524b-136">This change keeps address information aligned in certain scenarios, based on the dates of the address.</span></span>

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-425407"></a><span data-ttu-id="a524b-137">Impossibile aggiungere un allegato a una richiesta di congedo approvata (425407)</span><span class="sxs-lookup"><span data-stu-id="a524b-137">Unable to add an attachment to an approved leave request (425407)</span></span>

<span data-ttu-id="a524b-138">Con la versione di questa settimana, puoi aggiungere allegati alle richieste di ferie approvate senza modificare la richiesta di ferie.</span><span class="sxs-lookup"><span data-stu-id="a524b-138">With this week's release, you can add attachments to approved leave requests without changing the leave request.</span></span>

## <a name="in-preview"></a><span data-ttu-id="a524b-139">In anteprima</span><span class="sxs-lookup"><span data-stu-id="a524b-139">In preview</span></span>

## <a name="leave-suspension"></a><span data-ttu-id="a524b-140">Sospensione del congedo</span><span class="sxs-lookup"><span data-stu-id="a524b-140">Leave suspension</span></span>

<span data-ttu-id="a524b-141">È possibile sospendere le ferie e le assenze nelle risorse umane per un dipendente.</span><span class="sxs-lookup"><span data-stu-id="a524b-141">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="a524b-142">La sospensione del congedo e interrompe la maturazione delle ferie per i tipi di congedi selezionati.</span><span class="sxs-lookup"><span data-stu-id="a524b-142">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="a524b-143">Se la sospensione si verifica dopo l'elaborazione della maturazione, la sospensione delle ferie crea una rettifica proporzionale del saldo delle ferie del dipendente.</span><span class="sxs-lookup"><span data-stu-id="a524b-143">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="a524b-144">Per ulteriori informazioni, vedere [Sospendere il congedo](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="a524b-144">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a><span data-ttu-id="a524b-145">Aggiornamento dell'esperienza utente per indicare che l'accumulo è sospeso (429550)</span><span class="sxs-lookup"><span data-stu-id="a524b-145">Update user experience to indicate that accrual is suspended (429550)</span></span>

<span data-ttu-id="a524b-146">L'esperienza utente ora indica che l'accumulo è stato sospeso per un piano.</span><span class="sxs-lookup"><span data-stu-id="a524b-146">The user experience now indicates that the accrual has been suspended for a plan.</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a><span data-ttu-id="a524b-147">Sospendere l'accumulo dei congedi per determinati tipi di congedo (272447)</span><span class="sxs-lookup"><span data-stu-id="a524b-147">Suspend leave accrual for specified leave types (272447)</span></span>

<span data-ttu-id="a524b-148">In questa versione le risorse umane possono creare una regola per sospendere gli accumuli dei congedi per i dipendenti con richieste di congedo inserite per congedi non retribuiti.</span><span class="sxs-lookup"><span data-stu-id="a524b-148">In this release, HR can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="a524b-149">Il congedo non retribuito può essere un tipo, ma non è necessario che lo sia.</span><span class="sxs-lookup"><span data-stu-id="a524b-149">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="a524b-150">È possibile sospendere qualsiasi congedo in base a un altro tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="a524b-150">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a><span data-ttu-id="a524b-151">Entità DMF disponibile per le sospensioni degli accumuli (429549)</span><span class="sxs-lookup"><span data-stu-id="a524b-151">DMF entity available for accrual suspensions (429549)</span></span>

<span data-ttu-id="a524b-152">Un'entità DMF è ora disponibile per le sospensioni degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="a524b-152">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="add-reason-code-to-accrual-suspensions-429547"></a><span data-ttu-id="a524b-153">Aggiungere il codice motivo alle sospensioni degli accumuli (429547)</span><span class="sxs-lookup"><span data-stu-id="a524b-153">Add reason code to accrual suspensions (429547)</span></span>

<span data-ttu-id="a524b-154">Codici motivo sono stati aggiunti alla sospensione degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="a524b-154">Reason codes have been added to the accrual suspension.</span></span>

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a><span data-ttu-id="a524b-155">Iniziare la transizione dai parametri delle risorse umane ai parametri di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="a524b-155">Begin transitioning from Human Resources parameters to leave and absence parameters</span></span>

<span data-ttu-id="a524b-156">Questa versione inizia a combinare i parametri delle risorse umane con i parametri di congedo e assenza.</span><span class="sxs-lookup"><span data-stu-id="a524b-156">This release starts to combine Human Resources parameters with Leave and absence parameters.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="a524b-157">Regole di riporto</span><span class="sxs-lookup"><span data-stu-id="a524b-157">Carry forward rules</span></span>

<span data-ttu-id="a524b-158">È possibile specificare un tipo di congedo riporto per i saldi del riporto in cui vengono trasferiti le rettifiche di riporto.</span><span class="sxs-lookup"><span data-stu-id="a524b-158">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="a524b-159">Ad esempio, se un dipendente riporta 10 giorni, è possibile scegliere un tipo di congedo diverso per quei 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="a524b-159">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="a524b-160">Per ulteriori informazioni, vedere [Configurare i tipi di congedo e assenza](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="a524b-160">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a524b-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a524b-161">See also</span></span>

[<span data-ttu-id="a524b-162">Novità o modifiche in Human Resources</span><span class="sxs-lookup"><span data-stu-id="a524b-162">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="a524b-163">Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019</span><span class="sxs-lookup"><span data-stu-id="a524b-163">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="a524b-164">Aggiornare un processo</span><span class="sxs-lookup"><span data-stu-id="a524b-164">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="a524b-165">Gestire le funzionalità</span><span class="sxs-lookup"><span data-stu-id="a524b-165">Manage features</span></span>](hr-admin-manage-features.md)