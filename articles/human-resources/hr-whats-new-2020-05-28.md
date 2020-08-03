---
title: Novità o modifiche in Dynamics 365 Human Resources (28 maggio 2020)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 05/28/2020
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
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7664afbd0b1fd4e2c9686053fa102d85809c0411
ms.sourcegitcommit: bd9ff0d28718d535356ffbe1cffaaf60310dd430
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "3555317"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-28-2020"></a><span data-ttu-id="97c06-103">Novità o modifiche in Dynamics 365 Human Resources (28 maggio 2020)</span><span class="sxs-lookup"><span data-stu-id="97c06-103">What's new or changed in Dynamics 365 Human Resources (May 28, 2020)</span></span>

<span data-ttu-id="97c06-104">Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="97c06-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="97c06-105">Le modifiche si applicano alla build 8.1.3287.</span><span class="sxs-lookup"><span data-stu-id="97c06-105">Changes apply to build number 8.1.3287.</span></span> <span data-ttu-id="97c06-106">I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.</span><span class="sxs-lookup"><span data-stu-id="97c06-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="leaverequest-entity-doesnt-work-when-you-enable-multiple-types-per-leave-plan-447498"></a><span data-ttu-id="97c06-107">L'entità LeaveRequest non funziona quando si abilitano più tipi per piano di congedo (447498)</span><span class="sxs-lookup"><span data-stu-id="97c06-107">LeaveRequest entity doesn't work when you enable multiple types per leave plan (447498)</span></span>

<span data-ttu-id="97c06-108">Con questa modifica, **LeaveEnrollmentV2Entity** è ora disponibile per correggere l'errore che si verifica quando si abilitano più tipi di congedo.</span><span class="sxs-lookup"><span data-stu-id="97c06-108">With this change, the **LeaveEnrollmentV2Entity** is now available to correct the error that occurs when you enable multiple leave types.</span></span>

## <a name="batch-contention-reduction-feature-preview-446619"></a><span data-ttu-id="97c06-109">Funzionalità di riduzione di conflitti nei batch (anteprima) (446619)</span><span class="sxs-lookup"><span data-stu-id="97c06-109">Batch contention reduction feature (preview) (446619)</span></span>

<span data-ttu-id="97c06-110">Quando si abilita questa funzione, è possibile che si abbia una riduzione nel blocco delle tabelle di framework dei batch durante la selezione di attività e il completamento di processi.</span><span class="sxs-lookup"><span data-stu-id="97c06-110">When you enable this feature, you can expect a reduction in blocking on batch framework tables while selecting tasks and finishing jobs.</span></span>

## <a name="updateconflict-while-saving-worker-prevents-editing-a-record-in-people-427915"></a><span data-ttu-id="97c06-111">L'utilizzo di UpdateConflict durante il salvataggio del lavoratore impedisce la modifica di un record in Persone (427915)</span><span class="sxs-lookup"><span data-stu-id="97c06-111">UpdateConflict while saving worker prevents editing a record in People (427915)</span></span>

<span data-ttu-id="97c06-112">Questa modifica corregge un errore durante l'aggiunta di un nuovo lavoratore, l'aggiornamento delle informazioni relative all'indirizzo e la modifica della lingua preferita.</span><span class="sxs-lookup"><span data-stu-id="97c06-112">This change corrects an error when adding a new worker, updating address information, and changing language preference.</span></span> <span data-ttu-id="97c06-113">In questo scenario, viene visualizzato un errore indicante che il record non è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="97c06-113">In this unique scenario, an error displayed indicating the record couldn't be updated.</span></span> 

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-to-resubmit-425407"></a><span data-ttu-id="97c06-114">Impossibile aggiungere un allegato a una richiesta di congedo approvata (425407)</span><span class="sxs-lookup"><span data-stu-id="97c06-114">Unable to add an attachment to an approved leave request to resubmit (425407)</span></span>

<span data-ttu-id="97c06-115">Questa modifica ora consente di aggiungere allegati alle richieste di congedo approvate.</span><span class="sxs-lookup"><span data-stu-id="97c06-115">This change now allows attachments to approved leave requests.</span></span>

## <a name="user-can-enter-compensation-for-an-employee-in-a-different-legal-entity-form-409529"></a><span data-ttu-id="97c06-116">L'utente può inserire una retribuzione per un dipendente in un modulo persona giuridica differente (409529)</span><span class="sxs-lookup"><span data-stu-id="97c06-116">User can enter compensation for an employee in a different legal entity form (409529)</span></span>

<span data-ttu-id="97c06-117">Questa modifica disabilita le opzioni di retribuzione per impedire l'immissione accidentale di record di retribuzione per la persona giuridica errata.</span><span class="sxs-lookup"><span data-stu-id="97c06-117">This change disables compensation options to prevent inadvertent entry of compensation records for the wrong legal entity.</span></span>

## <a name="error-when-you-transfer-an-employee-and-the-worker-position-assignment-date-is-before-the-position-duration-429402"></a><span data-ttu-id="97c06-118">Errore durante il trasferimento di un dipendente e la data di assegnazione della posizione del lavoratore è precedente alla durata della posizione (429402)</span><span class="sxs-lookup"><span data-stu-id="97c06-118">Error when you transfer an employee and the Worker position assignment date is before the position duration (429402)</span></span>

<span data-ttu-id="97c06-119">I messaggi di errore durante il trasferimento di un dipendente in questo scenario sono stati aggiornati per descrivere meglio le modifiche necessarie per correggere il problema.</span><span class="sxs-lookup"><span data-stu-id="97c06-119">Error messages when transferring an employee in this scenario have been updated to better describe the changes needed to correct the problem.</span></span>

## <a name="attachments-capabilities-in-employee-self-service-benefits-enrollment"></a><span data-ttu-id="97c06-120">Funzionalità relative agli allegati nell'iscrizione ai benefit in Dipendente self-service</span><span class="sxs-lookup"><span data-stu-id="97c06-120">Attachments capabilities in Employee self service benefits enrollment</span></span>
 
<span data-ttu-id="97c06-121">Ora è possibile aggiungere allegati durante il processo di iscrizione ai benefit per ciascun piano a cui si iscrive il dipendente.</span><span class="sxs-lookup"><span data-stu-id="97c06-121">Now you can add attachments during the benefits enrollment process for each plan that the employee's enrolling in.</span></span> <span data-ttu-id="97c06-122">È quindi possibile visualizzare gli allegati nel modulo **Benefit a cui è iscritto il lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="97c06-122">You can then view the attachments within the **Worker enrolled benefit** form.</span></span>

## <a name="in-preview"></a><span data-ttu-id="97c06-123">In anteprima</span><span class="sxs-lookup"><span data-stu-id="97c06-123">In preview</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="97c06-124">Applicazione Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="97c06-124">Human Resources application in Teams</span></span>

<span data-ttu-id="97c06-125">I dipendenti possono visualizzare i congedi e richiederli in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="97c06-125">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="97c06-126">Possono interagire con un bot per creare richieste di congedo.</span><span class="sxs-lookup"><span data-stu-id="97c06-126">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="97c06-127">Per ulteriori informazioni, vedere [App Human Resources in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="97c06-127">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="leave-suspension"></a><span data-ttu-id="97c06-128">Sospensione del congedo</span><span class="sxs-lookup"><span data-stu-id="97c06-128">Leave suspension</span></span>

<span data-ttu-id="97c06-129">In Human Resources è possibile sospendere le ferie e le assenze per un dipendente.</span><span class="sxs-lookup"><span data-stu-id="97c06-129">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="97c06-130">La sospensione del congedo e interrompe la maturazione delle ferie per i tipi di congedi selezionati.</span><span class="sxs-lookup"><span data-stu-id="97c06-130">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="97c06-131">Se la sospensione si verifica dopo l'elaborazione della maturazione, la sospensione delle ferie crea una rettifica proporzionale del saldo delle ferie del dipendente.</span><span class="sxs-lookup"><span data-stu-id="97c06-131">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="97c06-132">Per ulteriori informazioni, vedere [Sospendere il congedo](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="97c06-132">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a><span data-ttu-id="97c06-133">Aggiornamento dell'esperienza utente per indicare che l'accumulo è sospeso (429550)</span><span class="sxs-lookup"><span data-stu-id="97c06-133">Update user experience to indicate that accrual is suspended (429550)</span></span>

<span data-ttu-id="97c06-134">L'esperienza utente ora indica che l'accumulo è stato sospeso per un piano.</span><span class="sxs-lookup"><span data-stu-id="97c06-134">The user experience now indicates that the accrual has been suspended for a plan.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="97c06-135">Presto disponibili</span><span class="sxs-lookup"><span data-stu-id="97c06-135">Coming soon</span></span>

## <a name="database-logging-in-preview-in-june"></a><span data-ttu-id="97c06-136">Registrazione di database (in anteprima a giugno)</span><span class="sxs-lookup"><span data-stu-id="97c06-136">Database logging (in preview in June)</span></span>

<span data-ttu-id="97c06-137">La funzione di registrazione di database consente di determinare quale tabella e quali campi devono essere monitorati.</span><span class="sxs-lookup"><span data-stu-id="97c06-137">The database logging feature allows you to determine which table and fields should be monitored.</span></span> <span data-ttu-id="97c06-138">Inoltre, consente di determinare gli eventi che dovrebbero attivare il rilevamento delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="97c06-138">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="97c06-139">Sono disponibili funzionalità di richiesta di informazioni per vedere queste modifiche nel tempo.</span><span class="sxs-lookup"><span data-stu-id="97c06-139">Inquiry capabilities are available to see these changes over time.</span></span>

## <a name="buy-and-sell-leave-in-preview-june-1"></a><span data-ttu-id="97c06-140">Acquisto e vendita di congedi (in anteprima il 1 giugno)</span><span class="sxs-lookup"><span data-stu-id="97c06-140">Buy and sell leave (in preview June 1)</span></span>

<span data-ttu-id="97c06-141">Alcune organizzazioni offrono un benefit che consente ai dipendenti di acquistare o vendere congedi.</span><span class="sxs-lookup"><span data-stu-id="97c06-141">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="97c06-142">Questo processo è spesso gestito manualmente.</span><span class="sxs-lookup"><span data-stu-id="97c06-142">This process is often managed manually.</span></span> <span data-ttu-id="97c06-143">Questa funzionalità offre un modo più automatizzato di gestire i criteri e le richieste per il dipartimento Risorse umane e semplifica il processo di gestione dei congedi eliminando gli errori.</span><span class="sxs-lookup"><span data-stu-id="97c06-143">This feature provides a more automated way to manage policies and requests for the HR department, and it helps eliminate mistakes while streamlining the leave management process.</span></span> <span data-ttu-id="97c06-144">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="97c06-144">For more information, see:</span></span>

- [<span data-ttu-id="97c06-145">Gestire i criteri di acquisto e vendita congedo</span><span class="sxs-lookup"><span data-stu-id="97c06-145">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="97c06-146">Acquista e vendi congedo</span><span class="sxs-lookup"><span data-stu-id="97c06-146">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="97c06-147">Entità Data Management Framework per la gestione di benefit</span><span class="sxs-lookup"><span data-stu-id="97c06-147">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="97c06-148">Le entità di gestione di benefit sono in fase di rilascio.</span><span class="sxs-lookup"><span data-stu-id="97c06-148">Benefits management entities are releasing.</span></span> <span data-ttu-id="97c06-149">Le entità Data Management Framework consentono di importare ed esportare dati per configurare facilmente la gestione dei benefit.</span><span class="sxs-lookup"><span data-stu-id="97c06-149">DMF entities allow importing and exporting data to easily configure benefits management.</span></span> <span data-ttu-id="97c06-150">Sarà inoltre disponibile un modello di gestione dei benefit per spostare i dati.</span><span class="sxs-lookup"><span data-stu-id="97c06-150">A Benefits management template will also be available to move data.</span></span> <span data-ttu-id="97c06-151">Il modello esporta e importa i dati in modo sequenziale per rispettare le dipendenze dei dati.</span><span class="sxs-lookup"><span data-stu-id="97c06-151">The template exports and imports the data in a sequential manner to respect data dependencies.</span></span>

## <a name="add-reason-code-to-accrual-suspensions-june-1"></a><span data-ttu-id="97c06-152">Aggiunta di codici motivo alle sospensioni degli accumuli (1 giugno)</span><span class="sxs-lookup"><span data-stu-id="97c06-152">Add reason code to accrual suspensions (June 1)</span></span>

<span data-ttu-id="97c06-153">Codici motivo sono stati aggiunti alla sospensione degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="97c06-153">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules-june-1"></a><span data-ttu-id="97c06-154">Regole di riporto (1 giugno)</span><span class="sxs-lookup"><span data-stu-id="97c06-154">Carry forward rules (June 1)</span></span>

<span data-ttu-id="97c06-155">È possibile specificare un tipo di congedo riporto per i saldi del riporto in cui vengono trasferiti le rettifiche di riporto.</span><span class="sxs-lookup"><span data-stu-id="97c06-155">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="97c06-156">Ad esempio, se un dipendente riporta 10 giorni, è possibile scegliere un tipo di congedo diverso per quei 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="97c06-156">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="97c06-157">Per ulteriori informazioni, vedere [Configurare i tipi di congedo e assenza](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="97c06-157">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types-june-1"></a><span data-ttu-id="97c06-158">Sospensione dell'accumulo dei congedi per determinati tipi di congedo (1 giugno)</span><span class="sxs-lookup"><span data-stu-id="97c06-158">Suspend leave accrual for specified leave types (June 1)</span></span>

<span data-ttu-id="97c06-159">In questa versione le risorse umane possono creare una regola per sospendere gli accumuli dei congedi per i dipendenti con richieste di congedo inserite per congedi non retribuiti.</span><span class="sxs-lookup"><span data-stu-id="97c06-159">In this release, HR can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="97c06-160">Il congedo non retribuito può essere un tipo, ma non è necessario che lo sia.</span><span class="sxs-lookup"><span data-stu-id="97c06-160">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="97c06-161">È possibile sospendere qualsiasi congedo in base a un altro tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="97c06-161">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions-june-1"></a><span data-ttu-id="97c06-162">Entità DMF disponibile per le sospensioni degli accumuli (1 giugno)</span><span class="sxs-lookup"><span data-stu-id="97c06-162">DMF entity available for accrual suspensions (June 1)</span></span>

<span data-ttu-id="97c06-163">Un'entità DMF è ora disponibile per le sospensioni degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="97c06-163">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="see-also"></a><span data-ttu-id="97c06-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97c06-164">See also</span></span>

[<span data-ttu-id="97c06-165">Novità o modifiche in Human Resources</span><span class="sxs-lookup"><span data-stu-id="97c06-165">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="97c06-166">Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019</span><span class="sxs-lookup"><span data-stu-id="97c06-166">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="97c06-167">Aggiornare un processo</span><span class="sxs-lookup"><span data-stu-id="97c06-167">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="97c06-168">Gestire le funzionalità</span><span class="sxs-lookup"><span data-stu-id="97c06-168">Manage features</span></span>](hr-admin-manage-features.md)