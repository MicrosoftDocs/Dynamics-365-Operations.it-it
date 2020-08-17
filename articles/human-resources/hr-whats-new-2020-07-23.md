---
title: Novità e modifiche in Dynamics 365 Human Resources (23 luglio 2020)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 07/23/2020
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
ms.search.validFrom: 2020-07-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dd71ab5c48be1bec5ce2272bbff37ab10a4aed67
ms.sourcegitcommit: 81296c49be9953aa01e15527c34d0ef13b4622a9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "3614412"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-23-2020"></a><span data-ttu-id="2ad30-103">Novità e modifiche in Dynamics 365 Human Resources (23 luglio 2020)</span><span class="sxs-lookup"><span data-stu-id="2ad30-103">What's new or changed in Dynamics 365 Human Resources (July 23, 2020)</span></span>

<span data-ttu-id="2ad30-104">Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2ad30-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="2ad30-105">Le modifiche si applicano alla build 8.1.3416.</span><span class="sxs-lookup"><span data-stu-id="2ad30-105">Changes apply to build number 8.1.3416.</span></span> <span data-ttu-id="2ad30-106">I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.</span><span class="sxs-lookup"><span data-stu-id="2ad30-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="deleting-financial-dimensions-on-a-position-doesnt-work-as-expected-445476"></a><span data-ttu-id="2ad30-107">L'eliminazione di dimensioni finanziarie in una posizione non funziona come previsto (445476)</span><span class="sxs-lookup"><span data-stu-id="2ad30-107">Deleting Financial Dimensions on a Position doesn't work as expected (445476)</span></span>

<span data-ttu-id="2ad30-108">La rimozione di dimensioni da una posizione ora rimuove quelle stesse posizioni da Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2ad30-108">Removing dimensions from a position now removes those same positions from Common Data Service.</span></span>

## <a name="positions-not-in-hierarchy-show-inactive-positions-397257"></a><span data-ttu-id="2ad30-109">Le posizioni non in gerarchia mostrano posizioni inattive (397257)</span><span class="sxs-lookup"><span data-stu-id="2ad30-109">Positions not in hierarchy show inactive positions (397257)</span></span>

<span data-ttu-id="2ad30-110">Le posizioni che sono inattive (hanno una durata scaduta) non vengono più visualizzate nella gerarchia delle posizioni come **Posizioni non in gerarchia**.</span><span class="sxs-lookup"><span data-stu-id="2ad30-110">Positions that are inactive (have an expired duration), no longer display in the position hierarchy as **Positions not in hierarchy**.</span></span> 

## <a name="validation-occurring-between-leaveenrollmententity-and-hcmworkerentity-on-data-management-framework-dmf-import-causes-slow-data-loads-442324"></a><span data-ttu-id="2ad30-111">La convalida che si verifica tra LeaveEnrollmentEntity e HcmWorkerEntity sull'importazione DMF (Data Management Framework) causa un caricamento dei dati lento (442324)</span><span class="sxs-lookup"><span data-stu-id="2ad30-111">Validation occurring between LeaveEnrollmentEntity and HcmWorkerEntity on Data Management Framework (DMF) import causes slow data loads (442324)</span></span>

<span data-ttu-id="2ad30-112">Le modifiche in questa versione aumentano le prestazioni di **LeaveEnrollmentEntity**.</span><span class="sxs-lookup"><span data-stu-id="2ad30-112">Changes in this release increase the performance of **LeaveEnrollmentEntity**.</span></span>

## <a name="unable-to-personalize-in-organization-administration-447490"></a><span data-ttu-id="2ad30-113">Impossibile personalizzare nell'amministrazione dell'organizzazione (447490)</span><span class="sxs-lookup"><span data-stu-id="2ad30-113">Unable to personalize in Organization administration (447490)</span></span>

<span data-ttu-id="2ad30-114">Con questa modifica, ora è possibile personalizzare i collegamenti in **Amministrazione organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="2ad30-114">With this change, you can now personalize the links in **Organization administration**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="2ad30-115">In anteprima</span><span class="sxs-lookup"><span data-stu-id="2ad30-115">In preview</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="2ad30-116">Campi obbligatori</span><span class="sxs-lookup"><span data-stu-id="2ad30-116">Mandatory fields</span></span> 

<span data-ttu-id="2ad30-117">Ora puoi rendere obbligatori i campi utilizzando le funzionalità di personalizzazione di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2ad30-117">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="2ad30-118">Questa funzionalità richiede **Visualizzazioni salvate**.</span><span class="sxs-lookup"><span data-stu-id="2ad30-118">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="2ad30-119">Applicazione Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="2ad30-119">Human Resources application in Teams</span></span>

<span data-ttu-id="2ad30-120">I dipendenti possono visualizzare i congedi e richiederli in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ad30-120">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="2ad30-121">Possono interagire con un bot per creare richieste di congedo.</span><span class="sxs-lookup"><span data-stu-id="2ad30-121">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="2ad30-122">Per ulteriori informazioni, vedere [App Human Resources in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="2ad30-122">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="2ad30-123">Entità Data Management Framework per la gestione di benefit</span><span class="sxs-lookup"><span data-stu-id="2ad30-123">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="2ad30-124">Le entità di gestione di benefit sono in fase di rilascio.</span><span class="sxs-lookup"><span data-stu-id="2ad30-124">Benefits management entities are releasing.</span></span> <span data-ttu-id="2ad30-125">Le entità DMF consentono di importare ed esportare dati per configurare facilmente la gestione dei benefit.</span><span class="sxs-lookup"><span data-stu-id="2ad30-125">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="2ad30-126">Sarà disponibile un modello di gestione dei benefit per spostare i dati.</span><span class="sxs-lookup"><span data-stu-id="2ad30-126">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="2ad30-127">Il modello esporta e importa i dati in modo in modo sequenziale per rispettare le dipendenze dei dati.</span><span class="sxs-lookup"><span data-stu-id="2ad30-127">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="2ad30-128">Acquista e vendi congedo</span><span class="sxs-lookup"><span data-stu-id="2ad30-128">Buy and sell leave</span></span> 

<span data-ttu-id="2ad30-129">Alcune organizzazioni offrono un benefit che consente ai dipendenti di acquistare o vendere congedi.</span><span class="sxs-lookup"><span data-stu-id="2ad30-129">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="2ad30-130">Questo processo è spesso gestito manualmente.</span><span class="sxs-lookup"><span data-stu-id="2ad30-130">This process is often managed manually.</span></span> <span data-ttu-id="2ad30-131">Questa funzione automatizza la gestione dei criteri e delle richieste per il dipartimento Risorse umane.</span><span class="sxs-lookup"><span data-stu-id="2ad30-131">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="2ad30-132">Semplifica il processo di gestione delle ferie e aiuta a eliminare gli errori.</span><span class="sxs-lookup"><span data-stu-id="2ad30-132">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="2ad30-133">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="2ad30-133">For more information, see:</span></span>

- [<span data-ttu-id="2ad30-134">Gestire i criteri di acquisto e vendita congedo</span><span class="sxs-lookup"><span data-stu-id="2ad30-134">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="2ad30-135">Acquista e vendi congedo</span><span class="sxs-lookup"><span data-stu-id="2ad30-135">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="2ad30-136">Lascia l'attribuzione per una singola azienda o un singolo piano</span><span class="sxs-lookup"><span data-stu-id="2ad30-136">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="2ad30-137">I clienti possono elaborare attribuzioni per una singola azienda o un singolo piano di ferie e assenze.</span><span class="sxs-lookup"><span data-stu-id="2ad30-137">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="2ad30-138">Questa capacità fornisce chiarezza per il processo di maturazione per i clienti con diversi anni di ferie o politiche di maturazione delle ferie.</span><span class="sxs-lookup"><span data-stu-id="2ad30-138">This ability provides clarity for the accrual process for customers with different leave years or leaves accrual policies.</span></span> <span data-ttu-id="2ad30-139">Per ulteriori informazioni, vedi [Accumulare congedi per società o per piano di congedo](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span><span class="sxs-lookup"><span data-stu-id="2ad30-139">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="2ad30-140">Aggiungi allegati alle richieste di ferie</span><span class="sxs-lookup"><span data-stu-id="2ad30-140">Add attachments to time-off requests</span></span>

<span data-ttu-id="2ad30-141">La possibilità di aggiungere allegati alle richieste di ferie approvate è fondamentale nell'attuale ambiente COVID-19.</span><span class="sxs-lookup"><span data-stu-id="2ad30-141">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="2ad30-142">I dipendenti possono ora aggiungere questi allegati.</span><span class="sxs-lookup"><span data-stu-id="2ad30-142">Employees can now add these attachments.</span></span> <span data-ttu-id="2ad30-143">Hanno anche maggiori informazioni dettagliate su come vengono effettuati gli aggiornamenti per lasciare le richieste.</span><span class="sxs-lookup"><span data-stu-id="2ad30-143">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="2ad30-144">Per ulteriori informazioni, vedi [Aggiungi un allegato a una richiesta esistente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="2ad30-144">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="2ad30-145">Aggiungi il codice motivo alle sospensioni degli accumuli</span><span class="sxs-lookup"><span data-stu-id="2ad30-145">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="2ad30-146">Codici motivo sono stati aggiunti alla sospensione degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="2ad30-146">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="2ad30-147">Regole di riporto</span><span class="sxs-lookup"><span data-stu-id="2ad30-147">Carry forward rules</span></span> 

<span data-ttu-id="2ad30-148">È possibile specificare un tipo di congedo riporto per i saldi del riporto in cui vengono trasferiti le rettifiche di riporto.</span><span class="sxs-lookup"><span data-stu-id="2ad30-148">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="2ad30-149">Ad esempio, se un dipendente riporta 10 giorni, è possibile scegliere un tipo di congedo diverso per quei 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="2ad30-149">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="2ad30-150">Per ulteriori informazioni, vedere [Configurare i tipi di congedo e assenza](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="2ad30-150">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="2ad30-151">Sospendi l'accumulo dei congedi per determinati tipi di congedo</span><span class="sxs-lookup"><span data-stu-id="2ad30-151">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="2ad30-152">Puoi creare una regola per sospendere gli accumuli dei congedi per i dipendenti con richieste di congedo inserite per congedi non retribuiti.</span><span class="sxs-lookup"><span data-stu-id="2ad30-152">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="2ad30-153">Il congedo non retribuito può essere un tipo, ma non è necessario che lo sia.</span><span class="sxs-lookup"><span data-stu-id="2ad30-153">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="2ad30-154">È possibile sospendere qualsiasi congedo in base a un altro tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="2ad30-154">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="2ad30-155">Entità DMF disponibile per le sospensioni degli accumuli</span><span class="sxs-lookup"><span data-stu-id="2ad30-155">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="2ad30-156">Un'entità DMF è ora disponibile per le sospensioni degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="2ad30-156">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="2ad30-157">Presto disponibili</span><span class="sxs-lookup"><span data-stu-id="2ad30-157">Coming soon</span></span>

## <a name="checklist-entities-included-in-common-data-service"></a><span data-ttu-id="2ad30-158">Elenco di controllo entità incluso in Common Data Service</span><span class="sxs-lookup"><span data-stu-id="2ad30-158">Checklist entities included in Common Data Service</span></span>

<span data-ttu-id="2ad30-159">Le entità dell'elenco di controllo per i processi di onboarding, offboarding, trasferimenti e aziendali saranno presto disponibili in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2ad30-159">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Common Data Service.</span></span>

## <a name="platform-changes"></a><span data-ttu-id="2ad30-160">Modifiche della piattaforma</span><span class="sxs-lookup"><span data-stu-id="2ad30-160">Platform changes</span></span>

<span data-ttu-id="2ad30-161">Platform Update 10.0.12 (36)</span><span class="sxs-lookup"><span data-stu-id="2ad30-161">Platform update 10.0.12 (36)</span></span>

## <a name="see-also"></a><span data-ttu-id="2ad30-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ad30-162">See also</span></span>

[<span data-ttu-id="2ad30-163">Novità o modifiche in Human Resources</span><span class="sxs-lookup"><span data-stu-id="2ad30-163">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="2ad30-164">Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019</span><span class="sxs-lookup"><span data-stu-id="2ad30-164">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="2ad30-165">Aggiornare un processo</span><span class="sxs-lookup"><span data-stu-id="2ad30-165">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="2ad30-166">Gestire le funzionalità</span><span class="sxs-lookup"><span data-stu-id="2ad30-166">Manage features</span></span>](hr-admin-manage-features.md)
