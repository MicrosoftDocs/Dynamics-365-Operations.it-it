---
title: Novità o modifiche in Dynamics 365 Talent (16 aprile 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-04-16
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 0781a479ebf37334d8eba18ea6d69d7cfb9db9ea
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024139"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-16-2019"></a><span data-ttu-id="20f3a-103">Novità o modifiche in Dynamics 365 Talent (16 aprile 2019)</span><span class="sxs-lookup"><span data-stu-id="20f3a-103">What's new or changed in Dynamics 365 Talent (April 16, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="20f3a-104">Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="20f3a-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="20f3a-105">Modifiche in Attract</span><span class="sxs-lookup"><span data-stu-id="20f3a-105">Changes in Attract</span></span>

### <a name="process-auditing"></a><span data-ttu-id="20f3a-106">Controllo dei processi</span><span class="sxs-lookup"><span data-stu-id="20f3a-106">Process auditing</span></span>

<span data-ttu-id="20f3a-107">Ora è possibile tenere traccia delle modifiche apportate ai candidati, alle posizioni di lavoro o alle domande di lavoro.</span><span class="sxs-lookup"><span data-stu-id="20f3a-107">You can now track the changes made to candidates, job openings, and job applications.</span></span> <span data-ttu-id="20f3a-108">Per ulteriori informazioni, vedere [Utilizzare le modifiche ai dati del personale](process-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="20f3a-108">For more information, see [Track changes in recruiting data](process-auditing.md).</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="20f3a-109">Modifiche in Onboard</span><span class="sxs-lookup"><span data-stu-id="20f3a-109">Changes in Onboard</span></span>

<span data-ttu-id="20f3a-110">Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="20f3a-110">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="20f3a-111">Modifiche di Core HR</span><span class="sxs-lookup"><span data-stu-id="20f3a-111">Changes in Core HR</span></span>

<span data-ttu-id="20f3a-112">Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2239.</span><span class="sxs-lookup"><span data-stu-id="20f3a-112">Changes described in this section apply to build number 8.1.2239.</span></span> <span data-ttu-id="20f3a-113">I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="20f3a-113">Numbers in parentheses refer to support numbers in Lifecycle Services (LCS).</span></span>

### <a name="compensation-region-compensation-level-benefit-option-and-skill-type-entities-in-common-data-service-updated-to-include-customer-field-support"></a><span data-ttu-id="20f3a-114">Le entità di paese di retribuzione, livello retributivo, opzione di benefit e tipo di competenza di Common Data Service sono state aggiornate per includere il supporto del campo del cliente</span><span class="sxs-lookup"><span data-stu-id="20f3a-114">Compensation region, Compensation level, Benefit option and Skill type entities in Common Data Service updated to include customer field support</span></span>

<span data-ttu-id="20f3a-115">In questa versione, queste entità di Common Data Service sono state aggiornate con la possibilità di includere il campo personalizzato aggiunto tramite Talent: Core HR.</span><span class="sxs-lookup"><span data-stu-id="20f3a-115">With this release, these Common Data Service entities have been updated to include the ability to include custom field added through Talent: Core HR.</span></span>

### <a name="new-common-data-service-entity-support-for-compensation-vesting-rules-compensation-variable-plan-variable-compensation"></a><span data-ttu-id="20f3a-116">Nuovo supporto di entità Common Data Service : Regole di distribuzione incentivi retribuzione, Piano di retribuzione variabile, Retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="20f3a-116">New Common Data Service entity support for: Compensation vesting rules, Compensation variable plan, Variable compensation</span></span>

<span data-ttu-id="20f3a-117">In questa versione, le entità Regole di distribuzione incentivi retribuzione, Piano di retribuzione variabile, Retribuzione variabile sono state aggiunte a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="20f3a-117">With this release, Compensation vesting rules, Compensation variable plan, and Variable compensation entities have been added to Common Data Service.</span></span> <span data-ttu-id="20f3a-118">Queste entità supportano anche i campi personalizzati aggiunti tramite Talent: Core HR.</span><span class="sxs-lookup"><span data-stu-id="20f3a-118">These entities also support custom fields added through Talent: Core HR.</span></span>

### <a name="powerbi-refresh-issues-314342"></a><span data-ttu-id="20f3a-119">Problemi di aggiornamento di PowerBI (314342)</span><span class="sxs-lookup"><span data-stu-id="20f3a-119">PowerBI refresh issues (314342)</span></span>

<span data-ttu-id="20f3a-120">Questa modifica corregge un problema con i report PowerBI che si aggiornano correttamente.</span><span class="sxs-lookup"><span data-stu-id="20f3a-120">This change corrects an issue with PowerBI reports refreshing correctly.</span></span>

### <a name="unable-to-click-directly-through-on-transition-tasks-in-employee-self-service-303309"></a><span data-ttu-id="20f3a-121">Impossibile fare clic direttamente sulle attività di transizione nel Self Service dipendenti (303309)</span><span class="sxs-lookup"><span data-stu-id="20f3a-121">Unable to click directly through on transition tasks in employee self-service (303309)</span></span>

<span data-ttu-id="20f3a-122">Questa modifica consente agli utenti con il ruolo di dipendente di selezionare e aggiornare le attività di transizione dall'elenco di cose da fare di Talent.</span><span class="sxs-lookup"><span data-stu-id="20f3a-122">This change enables users with the employee role to select and update transition tasks from the Talent to-do list.</span></span>

### <a name="performance-feedback-email-message-updated-309615"></a><span data-ttu-id="20f3a-123">Messaggio email di feedback sulle prestazioni aggiornato (309615)</span><span class="sxs-lookup"><span data-stu-id="20f3a-123">Performance feedback email message updated (309615)</span></span>

<span data-ttu-id="20f3a-124">Con questa modifica, viene visualizzato un messaggio di conferma quando il feedback viene inviato correttamente.</span><span class="sxs-lookup"><span data-stu-id="20f3a-124">With this change, a confirmation message displays when feedback is successfully submitted.</span></span>

### <a name="missing-tables-in-word-template-308048"></a><span data-ttu-id="20f3a-125">Tabelle mancanti nel modello di Word (308048)</span><span class="sxs-lookup"><span data-stu-id="20f3a-125">Missing tables in Word template (308048)</span></span>

<span data-ttu-id="20f3a-126">Con questa modifica, quando si crea un modello di Word con informazioni su dipendenti e competenze, nel documento di Word vengono visualizzate solo le competenze per il dipendente selezionato.</span><span class="sxs-lookup"><span data-stu-id="20f3a-126">With this change, when creating a Word template with employee and skill information, only the skills for the selected employee appear in the Word document.</span></span>

### <a name="when-applying-an-offboarding-checklist-an-error-is-displayed-299877"></a><span data-ttu-id="20f3a-127">Quando si applica un elenco di controllo di offboarding viene visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="20f3a-127">When applying an offboarding checklist an error is displayed.</span></span> <span data-ttu-id="20f3a-128">(299877)</span><span class="sxs-lookup"><span data-stu-id="20f3a-128">(299877)</span></span>

<span data-ttu-id="20f3a-129">Questa modifica corregge un problema quando si applicano un elenco di controllo di offboarding direttamente dal modulo del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="20f3a-129">This change corrects an issue when applying an offboarding checklist directly from the worker form.</span></span>

## <a name="in-preview"></a><span data-ttu-id="20f3a-130">In anteprima</span><span class="sxs-lookup"><span data-stu-id="20f3a-130">In preview</span></span>

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a><span data-ttu-id="20f3a-131">Consentire la specifica dei codici motivo nei tipi di congedo</span><span class="sxs-lookup"><span data-stu-id="20f3a-131">Allow reason codes to be specified on leave types</span></span>

<span data-ttu-id="20f3a-132">Le organizzazioni potrebbero necessitare di informazioni aggiuntive sulle richieste di permesso.</span><span class="sxs-lookup"><span data-stu-id="20f3a-132">Organizations might need additional information about time-off requests.</span></span> <span data-ttu-id="20f3a-133">Ora è possibile specificare i codici motivo per i tipi di congedo e consentire ai dipendenti di selezionare un codice motivo nelle relative richieste di permesso.</span><span class="sxs-lookup"><span data-stu-id="20f3a-133">You can now specify reason codes for leave types and enable employees to select a reason code on their time-off requests.</span></span>

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a><span data-ttu-id="20f3a-134">Richiedere codici motivo per alcuni tipi di congedo nelle richieste di permesso</span><span class="sxs-lookup"><span data-stu-id="20f3a-134">Require reason codes for certain leave types on time-off requests</span></span>

<span data-ttu-id="20f3a-135">Le organizzazioni potrebbero richiedere codici motivo per determinati tipi di congedo quando i dipendenti inviano richieste di permesso.</span><span class="sxs-lookup"><span data-stu-id="20f3a-135">Organizations might require reason codes for specific leave types when employees submit time off.</span></span> <span data-ttu-id="20f3a-136">Ciò potrebbe essere dovuto ai criteri o ai requisiti normativi della società.</span><span class="sxs-lookup"><span data-stu-id="20f3a-136">This might be due to company policy or regulatory requirements.</span></span> <span data-ttu-id="20f3a-137">Ora è possibile specificare quali tipi di congedo richiedono un codice motivo ed è possibile richiedere ai dipendenti di fornire un codice motivo per il tipo di congedo nelle relative richieste di permesso.</span><span class="sxs-lookup"><span data-stu-id="20f3a-137">You can now specify which leave types require a reason code, and you can require employees to provide a reason code for the leave type on their time-off requests.</span></span>

### <a name="provide-leave-and-absence-transaction-list-for-hr"></a><span data-ttu-id="20f3a-138">Fornire un elenco di transazioni assenze e congedo per le Risorse umane</span><span class="sxs-lookup"><span data-stu-id="20f3a-138">Provide leave and absence transaction list for HR</span></span>

<span data-ttu-id="20f3a-139">La tracciabilità del tempo libero dei dipendenti e la comprensione di come tale tempo viene calcolato non solo consente alle Risorse umane di rispondere alle domande dei dipendenti, ma anche di garantire premi appropriati per il tempo libero dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="20f3a-139">Tracking employee time off and understanding how time off is calculated not only helps HR answer employee questions, but also ensures accurate time-off awards for employees.</span></span> <span data-ttu-id="20f3a-140">Ora le Risorse umane hanno una nuova visibilità sulle transazioni (concessioni, accumuli, rettifiche e richieste) per determinare i motivi dei saldi.</span><span class="sxs-lookup"><span data-stu-id="20f3a-140">HR now has a new view into the transactions (grants, accruals, adjustments, and requests) to see the reasons behind balances.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="20f3a-141">Presto disponibili</span><span class="sxs-lookup"><span data-stu-id="20f3a-141">Coming soon</span></span>

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a><span data-ttu-id="20f3a-142">Miglioramenti all'interfaccia utente per la verifica di dipendenti duplicati</span><span class="sxs-lookup"><span data-stu-id="20f3a-142">Improvements to the user interface for duplicate employee check</span></span>

<span data-ttu-id="20f3a-143">Con questa modifica, i duplicati vengono rilevati durante l'immissione nei campi Nome e uno stato indica il numero di duplicati trovati.</span><span class="sxs-lookup"><span data-stu-id="20f3a-143">With this change, duplicates are detected as you enter name fields, and a status displays the number of duplicates found.</span></span> <span data-ttu-id="20f3a-144">È possibile selezionare il collegamento fornito per aprire una nuova pagina e valutare se utilizzare la corrispondenza rilevata.</span><span class="sxs-lookup"><span data-stu-id="20f3a-144">You can select the provided link to open a new page to evaluate whether to use the detected match.</span></span> <span data-ttu-id="20f3a-145">Per evitare di interrompere l'immissione di dati, il modulo Duplicati non viene aperto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="20f3a-145">To avoid interrupting data entry, the duplicates form doesn't automatically open.</span></span>

### <a name="email-support-for-alerts"></a><span data-ttu-id="20f3a-146">Supporto di messaggi di posta elettronica per avvisi</span><span class="sxs-lookup"><span data-stu-id="20f3a-146">Email support for alerts</span></span>

<span data-ttu-id="20f3a-147">Con l'aggiornamento 25 della piattaforma per Finance and Operations, gli utenti possono creare regole di avviso che inviano automaticamente notifiche di posta elettronica ai contatti quando le notifiche sono attivate da un evento.</span><span class="sxs-lookup"><span data-stu-id="20f3a-147">With Platform update 25 for Finance and Operations, users can create alert rules that automatically send email notifications to contacts when triggered by an event.</span></span>


