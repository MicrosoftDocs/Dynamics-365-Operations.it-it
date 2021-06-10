---
title: Novità e modifiche in Dynamics 365 Human Resources (11 giugno 2020)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources all'11 giugno 2020.
author: andreabichsel
ms.date: 06/16/2020
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
ms.search.validFrom: 2020-06-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6b0bb1c6d00cdd816534caddd83a71f2f0a3cc3
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054310"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-11-2020"></a><span data-ttu-id="97fd1-103">Novità e modifiche in Dynamics 365 Human Resources (11 giugno 2020)</span><span class="sxs-lookup"><span data-stu-id="97fd1-103">What's new or changed in Dynamics 365 Human Resources (June 11, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="97fd1-104">Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="97fd1-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="97fd1-105">Le modifiche si applicano alla build 8.1.3316.</span><span class="sxs-lookup"><span data-stu-id="97fd1-105">Changes apply to build number 8.1.3316.</span></span> <span data-ttu-id="97fd1-106">I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.</span><span class="sxs-lookup"><span data-stu-id="97fd1-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="streamlined-employee-form-sometimes-causes-child-form-close-x-buttons-to-stop-working-442369"></a><span data-ttu-id="97fd1-107">Il modulo semplificato per i dipendenti a volte interrompe il funzionamento dei pulsanti di chiusura (X) del modulo figlio (442369)</span><span class="sxs-lookup"><span data-stu-id="97fd1-107">Streamlined employee form sometimes causes child form close (X) buttons to stop working (442369)</span></span>

<span data-ttu-id="97fd1-108">Quando il nuovo modulo **Lavoratore** è stato abilitato, il pulsante di chiusura (**X**) occasionalmente non funzionava sui moduli figlio.</span><span class="sxs-lookup"><span data-stu-id="97fd1-108">When the new **Worker** form was enabled, the close (**X**) button occasionally didn't work on child forms.</span></span> <span data-ttu-id="97fd1-109">Questo problema era intermittente.</span><span class="sxs-lookup"><span data-stu-id="97fd1-109">This problem was intermittent.</span></span> <span data-ttu-id="97fd1-110">Puoi chiudere il modulo dopo essere uscito e tornare in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="97fd1-110">You could close the form after leaving and coming back to it.</span></span> <span data-ttu-id="97fd1-111">Ad esempio, puoi selezionare una voce di menu a sinistra e tornare indietro al modulo **Lavoratore**, quindi chiudilo.</span><span class="sxs-lookup"><span data-stu-id="97fd1-111">For example, you could select a menu item on the left, and navigate back to the **Worker** form, and then close it.</span></span> <span data-ttu-id="97fd1-112">Questa versione risolverà questo problema.</span><span class="sxs-lookup"><span data-stu-id="97fd1-112">This week's release fixes this problem.</span></span> 

## <a name="the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-a-parent-relationship-type"></a><span data-ttu-id="97fd1-113">L'entità del contatto personale del lavoratore non esporta i contatti personali con un tipo di relazione principale</span><span class="sxs-lookup"><span data-stu-id="97fd1-113">The Worker personal contact person entity doesn't export personal contacts with a parent relationship type</span></span>

<span data-ttu-id="97fd1-114">Con questa versione, l'entità **Contatto personale del lavoratore** esporta tutti i tipi di relazione.</span><span class="sxs-lookup"><span data-stu-id="97fd1-114">With this release, the **Worker personal contact person** entity exports all relationship types.</span></span>

## <a name="the-hcmpositionworkerassignmentv2entity-should-be-part-of-the-ceridian-payroll-integration-package-by-default-448506"></a><span data-ttu-id="97fd1-115">HcmPositionWorkerAssignmentV2Entity dovrebbe essere parte del pacchetto di integrazione delle buste paga di Ceridian per impostazione predefinita (448506)</span><span class="sxs-lookup"><span data-stu-id="97fd1-115">The HcmPositionWorkerAssignmentV2Entity should be part of the Ceridian payroll integration package by default (448506)</span></span>

<span data-ttu-id="97fd1-116">Con questa modifica, **HcmPositionWorkerAssignmentV2Entity** è incluso nel pacchetto di integrazione delle buste paga di Ceridian.</span><span class="sxs-lookup"><span data-stu-id="97fd1-116">With this change, the **HcmPositionWorkerAssignmentV2Entity** is included in the Ceridian payroll integration package.</span></span>

## <a name="in-preview"></a><span data-ttu-id="97fd1-117">In anteprima</span><span class="sxs-lookup"><span data-stu-id="97fd1-117">In preview</span></span>

## <a name="database-logging"></a><span data-ttu-id="97fd1-118">Registrazione database</span><span class="sxs-lookup"><span data-stu-id="97fd1-118">Database logging</span></span>

<span data-ttu-id="97fd1-119">La funzione di registrazione del database consente di determinare quali tabelle e quali campi monitorare.</span><span class="sxs-lookup"><span data-stu-id="97fd1-119">The database logging feature allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="97fd1-120">Inoltre, consente di determinare gli eventi che dovrebbero attivare il rilevamento delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="97fd1-120">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="97fd1-121">Usare le funzionalità di registrazione del database per visualizzare tali modifiche nel tempo.</span><span class="sxs-lookup"><span data-stu-id="97fd1-121">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="97fd1-122">Per ulteriori informazioni, vedi [Configurare e gestire la registrazione del database](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="97fd1-122">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="97fd1-123">Applicazione Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="97fd1-123">Human Resources application in Teams</span></span>

<span data-ttu-id="97fd1-124">I dipendenti possono visualizzare i congedi e richiederli in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="97fd1-124">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="97fd1-125">Possono interagire con un bot per creare richieste di congedo.</span><span class="sxs-lookup"><span data-stu-id="97fd1-125">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="97fd1-126">Per ulteriori informazioni, vedere [App Human Resources in Teams](./hr-admin-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="97fd1-126">For more information, see [Human Resources app in Teams](./hr-admin-teams-leave-app.md).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="97fd1-127">Entità Data Management Framework per la gestione di benefit</span><span class="sxs-lookup"><span data-stu-id="97fd1-127">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="97fd1-128">Le entità di gestione di benefit sono in fase di rilascio.</span><span class="sxs-lookup"><span data-stu-id="97fd1-128">Benefits management entities are releasing.</span></span> <span data-ttu-id="97fd1-129">Le entità DMF consentono di importare ed esportare dati per configurare facilmente la gestione dei benefit.</span><span class="sxs-lookup"><span data-stu-id="97fd1-129">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="97fd1-130">Sarà disponibile un modello di gestione dei benefit per spostare i dati.</span><span class="sxs-lookup"><span data-stu-id="97fd1-130">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="97fd1-131">Il modello esporta e importa i dati in modo in modo sequenziale per rispettare le dipendenze dei dati.</span><span class="sxs-lookup"><span data-stu-id="97fd1-131">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="97fd1-132">Acquista e vendi congedo</span><span class="sxs-lookup"><span data-stu-id="97fd1-132">Buy and sell leave</span></span> 

<span data-ttu-id="97fd1-133">Alcune organizzazioni offrono un benefit che consente ai dipendenti di acquistare o vendere congedi.</span><span class="sxs-lookup"><span data-stu-id="97fd1-133">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="97fd1-134">Questo processo è spesso gestito manualmente.</span><span class="sxs-lookup"><span data-stu-id="97fd1-134">This process is often managed manually.</span></span> <span data-ttu-id="97fd1-135">Questa funzione automatizza la gestione dei criteri e delle richieste per il dipartimento Risorse umane.</span><span class="sxs-lookup"><span data-stu-id="97fd1-135">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="97fd1-136">Semplifica il processo di gestione delle ferie e aiuta a eliminare gli errori.</span><span class="sxs-lookup"><span data-stu-id="97fd1-136">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="97fd1-137">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="97fd1-137">For more information, see:</span></span>

- [<span data-ttu-id="97fd1-138">Gestire i criteri di acquisto e vendita congedo</span><span class="sxs-lookup"><span data-stu-id="97fd1-138">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="97fd1-139">Acquista e vendi congedo</span><span class="sxs-lookup"><span data-stu-id="97fd1-139">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="97fd1-140">Lascia l'attribuzione per una singola azienda o un singolo piano</span><span class="sxs-lookup"><span data-stu-id="97fd1-140">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="97fd1-141">I clienti possono elaborare attribuzioni per una singola azienda o un singolo piano di ferie e assenze.</span><span class="sxs-lookup"><span data-stu-id="97fd1-141">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="97fd1-142">Questa capacità fornisce chiarezza nel processo di maturazione per i clienti con diversi anni di ferie o politiche di maturazione delle ferie.</span><span class="sxs-lookup"><span data-stu-id="97fd1-142">This ability provides clarity into the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="97fd1-143">Per ulteriori informazioni, vedi [Accumulare congedi per società o per piano di congedo](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="97fd1-143">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="97fd1-144">Aggiungi allegati alle richieste di ferie</span><span class="sxs-lookup"><span data-stu-id="97fd1-144">Add attachments to time off requests</span></span>

<span data-ttu-id="97fd1-145">La possibilità di aggiungere allegati alle richieste di ferie approvate è fondamentale nell'attuale ambiente COVID-19.</span><span class="sxs-lookup"><span data-stu-id="97fd1-145">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="97fd1-146">I dipendenti possono ora aggiungere questi allegati.</span><span class="sxs-lookup"><span data-stu-id="97fd1-146">Employees can now add these attachments.</span></span> <span data-ttu-id="97fd1-147">Hanno anche maggiori informazioni dettagliate su come vengono effettuati gli aggiornamenti per lasciare le richieste.</span><span class="sxs-lookup"><span data-stu-id="97fd1-147">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="97fd1-148">Per ulteriori informazioni, vedi [Aggiungi un allegato a una richiesta esistente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="97fd1-148">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="97fd1-149">Aggiungi il codice motivo alle sospensioni degli accumuli</span><span class="sxs-lookup"><span data-stu-id="97fd1-149">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="97fd1-150">Codici motivo sono stati aggiunti alla sospensione degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="97fd1-150">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="97fd1-151">Regole di riporto</span><span class="sxs-lookup"><span data-stu-id="97fd1-151">Carry forward rules</span></span> 

<span data-ttu-id="97fd1-152">È possibile specificare un tipo di congedo riporto per i saldi del riporto in cui vengono trasferiti le rettifiche di riporto.</span><span class="sxs-lookup"><span data-stu-id="97fd1-152">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="97fd1-153">Ad esempio, se un dipendente riporta 10 giorni, è possibile scegliere un tipo di congedo diverso per quei 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="97fd1-153">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="97fd1-154">Per ulteriori informazioni, vedere [Configurare i tipi di congedo e assenza](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="97fd1-154">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="97fd1-155">Sospendi l'accumulo dei congedi per determinati tipi di congedo</span><span class="sxs-lookup"><span data-stu-id="97fd1-155">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="97fd1-156">Puoi creare una regola per sospendere gli accumuli dei congedi per i dipendenti con richieste di congedo inserite per congedi non retribuiti.</span><span class="sxs-lookup"><span data-stu-id="97fd1-156">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="97fd1-157">Il congedo non retribuito può essere un tipo, ma non è necessario che lo sia.</span><span class="sxs-lookup"><span data-stu-id="97fd1-157">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="97fd1-158">È possibile sospendere qualsiasi congedo in base a un altro tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="97fd1-158">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="97fd1-159">Entità DMF disponibile per le sospensioni degli accumuli</span><span class="sxs-lookup"><span data-stu-id="97fd1-159">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="97fd1-160">Un'entità DMF è ora disponibile per le sospensioni degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="97fd1-160">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="97fd1-161">Presto disponibili</span><span class="sxs-lookup"><span data-stu-id="97fd1-161">Coming soon</span></span>

## <a name="new-platform-capabilities"></a><span data-ttu-id="97fd1-162">Nuove funzionalità della piattaforma</span><span class="sxs-lookup"><span data-stu-id="97fd1-162">New platform capabilities</span></span> 

<span data-ttu-id="97fd1-163">Sarai in grado di rendere i campi obbligatori utilizzando la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="97fd1-163">You'll be able to make fields mandatory by using personalization.</span></span> <span data-ttu-id="97fd1-164">Questa funzione ti richiederà di abilitare **Visualizzazioni salvate**.</span><span class="sxs-lookup"><span data-stu-id="97fd1-164">This feature will require you to enable **Saved views**.</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="97fd1-165">Configurare il nome del self-service dipendenti</span><span class="sxs-lookup"><span data-stu-id="97fd1-165">Configure the name of Employee self-service</span></span>

<span data-ttu-id="97fd1-166">Una nuova opzione sarà disponibile nei parametri Risorse umane per aggiornare il nome dell'area di lavoro Self-service dipendenti in Self-service.</span><span class="sxs-lookup"><span data-stu-id="97fd1-166">A new option will be available in Human Resources parameters to update the name of the Employee self service workspace to Self service.</span></span> 

## <a name="see-also"></a><span data-ttu-id="97fd1-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97fd1-167">See also</span></span>

[<span data-ttu-id="97fd1-168">Novità o modifiche in Human Resources</span><span class="sxs-lookup"><span data-stu-id="97fd1-168">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="97fd1-169">Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019</span><span class="sxs-lookup"><span data-stu-id="97fd1-169">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="97fd1-170">Aggiornare un processo</span><span class="sxs-lookup"><span data-stu-id="97fd1-170">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="97fd1-171">Gestire le funzionalità</span><span class="sxs-lookup"><span data-stu-id="97fd1-171">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]