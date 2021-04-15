---
title: Novità o modifiche in Dynamics 365 Human Resources (1 maggio 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 1 maggio 2020.
author: andreabichsel
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 52eb748fe8b3c62d6a5ebf46fd01afc291ec5572
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803419"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-1-2020"></a><span data-ttu-id="a44b4-103">Novità o modifiche in Dynamics 365 Human Resources (1 maggio 2020)</span><span class="sxs-lookup"><span data-stu-id="a44b4-103">What's new or changed in Dynamics 365 Human Resources (May 1, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a44b4-104">Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a44b4-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="a44b4-105">Le modifiche si applicano alla build 8.1.3196.</span><span class="sxs-lookup"><span data-stu-id="a44b4-105">Changes apply to build number 8.1.3196.</span></span> <span data-ttu-id="a44b4-106">I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.</span><span class="sxs-lookup"><span data-stu-id="a44b4-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="new-performance-management-entities-available-in-data-management-framework-dmf"></a><span data-ttu-id="a44b4-107">Nuove entità Gestione delle prestazioni disponibili nel framework di gestione dei dati (DMF)</span><span class="sxs-lookup"><span data-stu-id="a44b4-107">New Performance Management entities available in Data Management Framework (DMF)</span></span>

<span data-ttu-id="a44b4-108">Ora sono disponibili le seguenti entità.</span><span class="sxs-lookup"><span data-stu-id="a44b4-108">The following entities are now available.</span></span> <span data-ttu-id="a44b4-109">Se queste entità non sono elencate nell'elenco delle entità, usare l'opzione **Aggiorna entità** in **Parametri framework > Impostazioni entità > Aggiorna elenco entità**.</span><span class="sxs-lookup"><span data-stu-id="a44b4-109">If you don't see these entities listed in the entities list, use the **Refresh entities** option in **Framework Parameters > Entity settings > Refresh entity list**.</span></span>

- <span data-ttu-id="a44b4-110">**Competenza di discussione**</span><span class="sxs-lookup"><span data-stu-id="a44b4-110">**Discussion Competency**</span></span>
- <span data-ttu-id="a44b4-111">**Obiettivi di discussione**</span><span class="sxs-lookup"><span data-stu-id="a44b4-111">**Discussion Goals**</span></span>
- <span data-ttu-id="a44b4-112">**Misura di discussione**</span><span class="sxs-lookup"><span data-stu-id="a44b4-112">**Discussion Measurement**</span></span>
- <span data-ttu-id="a44b4-113">**Argomento di discussione**</span><span class="sxs-lookup"><span data-stu-id="a44b4-113">**Discussion Topic**</span></span>
- <span data-ttu-id="a44b4-114">**Giornale di registrazione prestazioni**</span><span class="sxs-lookup"><span data-stu-id="a44b4-114">**Performance Journal**</span></span>
- <span data-ttu-id="a44b4-115">**Misura**</span><span class="sxs-lookup"><span data-stu-id="a44b4-115">**Measurement**</span></span>
- <span data-ttu-id="a44b4-116">**Misura obiettivo**</span><span class="sxs-lookup"><span data-stu-id="a44b4-116">**Goal Measurement**</span></span>

<span data-ttu-id="a44b4-117">Inoltre, **Punteggio totale** e **Punteggio medio** sono stati aggiunti all'entità **Discussione**.</span><span class="sxs-lookup"><span data-stu-id="a44b4-117">In addition, **Total score** and **Average score** were added to the **Discussion** entity.</span></span>

## <a name="increase-length-of-leave-request-comments-275641"></a><span data-ttu-id="a44b4-118">Aumentare la lunghezza dei commenti nelle richieste di congedo (275641)</span><span class="sxs-lookup"><span data-stu-id="a44b4-118">Increase length of leave request comments (275641)</span></span>

<span data-ttu-id="a44b4-119">I commenti nelle richieste di congedo consentono ora l'uso di più di 100 caratteri.</span><span class="sxs-lookup"><span data-stu-id="a44b4-119">Comments on leave requests now allow more than 100 characters.</span></span>

## <a name="final-comments-on-reviews-dont-appear-when-the-manager-or-employee-is-signed-into-a-different-company-431688"></a><span data-ttu-id="a44b4-120">I commenti finali nelle revisioni non vengono visualizzati quando il responsabile o il dipendente ha effettuato l'accesso a un'altra società (431688)</span><span class="sxs-lookup"><span data-stu-id="a44b4-120">Final comments on reviews don't appear when the manager or employee is signed into a different company (431688)</span></span>

<span data-ttu-id="a44b4-121">Tutti i commenti verranno ora visualizzati alla visualizzazione delle revisioni.</span><span class="sxs-lookup"><span data-stu-id="a44b4-121">All comments will now appear when viewing reviews.</span></span>

## <a name="user-defined-links-arent-supported-on-new-worker-form-390374"></a><span data-ttu-id="a44b4-122">I collegamenti definiti dall'utente non sono supportati nel nuovo modulo Lavoratore (390374)</span><span class="sxs-lookup"><span data-stu-id="a44b4-122">User-defined links aren't supported on new Worker form (390374)</span></span>

<span data-ttu-id="a44b4-123">I collegamenti definiti dall'utente sono ora abilitati nel modulo **Lavoratore** semplificato.</span><span class="sxs-lookup"><span data-stu-id="a44b4-123">User-defined links are now enabled on the streamlined **Worker** form.</span></span>

## <a name="hcmratinglevelentity-causes-odata-api-crash-439476"></a><span data-ttu-id="a44b4-124">HcmRatingLevelEntity provoca l'arresto anomalo dell'API OData (439476)</span><span class="sxs-lookup"><span data-stu-id="a44b4-124">HcmRatingLevelEntity causes OData API crash (439476)</span></span>

<span data-ttu-id="a44b4-125">Questa modifica corregge l'arresto anomalo dell'API.</span><span class="sxs-lookup"><span data-stu-id="a44b4-125">This change corrects the API crash.</span></span> <span data-ttu-id="a44b4-126">Un nome duplicato ha generato questo errore.</span><span class="sxs-lookup"><span data-stu-id="a44b4-126">A duplicate name cased this error.</span></span>

## <a name="in-preview"></a><span data-ttu-id="a44b4-127">In anteprima</span><span class="sxs-lookup"><span data-stu-id="a44b4-127">In preview</span></span>

## <a name="leave-suspension"></a><span data-ttu-id="a44b4-128">Sospensione del congedo</span><span class="sxs-lookup"><span data-stu-id="a44b4-128">Leave suspension</span></span>

<span data-ttu-id="a44b4-129">È possibile sospendere le ferie e le assenze nelle risorse umane per un dipendente.</span><span class="sxs-lookup"><span data-stu-id="a44b4-129">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="a44b4-130">La sospensione del congedo e interrompe la maturazione delle ferie per i tipi di congedi selezionati.</span><span class="sxs-lookup"><span data-stu-id="a44b4-130">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="a44b4-131">Se la sospensione si verifica dopo l'elaborazione della maturazione, la sospensione delle ferie crea una rettifica proporzionale del saldo delle ferie del dipendente.</span><span class="sxs-lookup"><span data-stu-id="a44b4-131">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="a44b4-132">Per ulteriori informazioni, vedere [Sospendere il congedo](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="a44b4-132">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a><span data-ttu-id="a44b4-133">Aggiornamento dell'esperienza utente per indicare che l'accumulo è sospeso (429550)</span><span class="sxs-lookup"><span data-stu-id="a44b4-133">Update user experience to indicate that accrual is suspended (429550)</span></span>

<span data-ttu-id="a44b4-134">L'esperienza utente ora indica che l'accumulo è stato sospeso per un piano.</span><span class="sxs-lookup"><span data-stu-id="a44b4-134">The user experience now indicates that the accrual has been suspended for a plan.</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a><span data-ttu-id="a44b4-135">Sospendere l'accumulo dei congedi per determinati tipi di congedo (272447)</span><span class="sxs-lookup"><span data-stu-id="a44b4-135">Suspend leave accrual for specified leave types (272447)</span></span>

<span data-ttu-id="a44b4-136">In questa versione le risorse umane possono creare una regola per sospendere gli accumuli dei congedi per i dipendenti con richieste di congedo inserite per congedi non retribuiti.</span><span class="sxs-lookup"><span data-stu-id="a44b4-136">In this release, HR can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="a44b4-137">Il congedo non retribuito può essere un tipo, ma non è necessario che lo sia.</span><span class="sxs-lookup"><span data-stu-id="a44b4-137">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="a44b4-138">È possibile sospendere qualsiasi congedo in base a un altro tipo di congedo.</span><span class="sxs-lookup"><span data-stu-id="a44b4-138">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a><span data-ttu-id="a44b4-139">Entità DMF disponibile per le sospensioni degli accumuli (429549)</span><span class="sxs-lookup"><span data-stu-id="a44b4-139">DMF entity available for accrual suspensions (429549)</span></span>

<span data-ttu-id="a44b4-140">Un'entità DMF è ora disponibile per le sospensioni degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="a44b4-140">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="add-reason-code-to-accrual-suspensions-429547"></a><span data-ttu-id="a44b4-141">Aggiungere il codice motivo alle sospensioni degli accumuli (429547)</span><span class="sxs-lookup"><span data-stu-id="a44b4-141">Add reason code to accrual suspensions (429547)</span></span>

<span data-ttu-id="a44b4-142">Codici motivo sono stati aggiunti alla sospensione degli accumuli.</span><span class="sxs-lookup"><span data-stu-id="a44b4-142">Reason codes have been added to the accrual suspension.</span></span>

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a><span data-ttu-id="a44b4-143">Iniziare la transizione dai parametri delle risorse umane ai parametri di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="a44b4-143">Begin transitioning from Human Resources parameters to leave and absence parameters</span></span>

<span data-ttu-id="a44b4-144">Questa versione inizia a combinare i parametri delle risorse umane con i parametri di congedo e assenza.</span><span class="sxs-lookup"><span data-stu-id="a44b4-144">This release starts to combine Human Resources parameters with Leave and absence parameters.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="a44b4-145">Regole di riporto</span><span class="sxs-lookup"><span data-stu-id="a44b4-145">Carry forward rules</span></span>

<span data-ttu-id="a44b4-146">È possibile specificare un tipo di congedo riporto per i saldi del riporto in cui vengono trasferiti le rettifiche di riporto.</span><span class="sxs-lookup"><span data-stu-id="a44b4-146">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="a44b4-147">Ad esempio, se un dipendente riporta 10 giorni, è possibile scegliere un tipo di congedo diverso per quei 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="a44b4-147">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="a44b4-148">Per ulteriori informazioni, vedere [Configurare i tipi di congedo e assenza](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="a44b4-148">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="a44b4-149">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="a44b4-149">Known issues</span></span>

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a><span data-ttu-id="a44b4-150">L'anteprima di SharePoint non funziona in alcuni ambienti</span><span class="sxs-lookup"><span data-stu-id="a44b4-150">SharePoint preview doesn't work in some environments</span></span>

<span data-ttu-id="a44b4-151">Se l'anteprima del documento per i documenti memorizzati in SharePoint non funziona, provare la seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="a44b4-151">If document preview for documents stored in SharePoint doesn't work, try the following procedure:</span></span>

1. <span data-ttu-id="a44b4-152">Verificare che l'account utente amministratore abbia un'e-mail associata al record utente.</span><span class="sxs-lookup"><span data-stu-id="a44b4-152">Verify the Admin user account has an email associated with the user record.</span></span> <span data-ttu-id="a44b4-153">È possibile visualizzare tali informazioni nella pagina **Utente**.</span><span class="sxs-lookup"><span data-stu-id="a44b4-153">You can view this information in the **User** page.</span></span> <span data-ttu-id="a44b4-154">Se l'e-mail non è impostata, è necessario aggiungere l'e-mail e il provider con il componente aggiuntivo OData Excel.</span><span class="sxs-lookup"><span data-stu-id="a44b4-154">If email isn't set up, you need to add the email and provider with the OData Excel add-in.</span></span> <span data-ttu-id="a44b4-155">Per impostazione predefinita, l'indirizzo e-mail non è presente nella progettazione di Excel.</span><span class="sxs-lookup"><span data-stu-id="a44b4-155">By default, the email address isn't present in the Excel design.</span></span> <span data-ttu-id="a44b4-156">È necessario modificare la progettazione di Excel, aggiungere tutti i campi, applicare e aggiornare.</span><span class="sxs-lookup"><span data-stu-id="a44b4-156">You'll need to edit the Excel design, add all fields, apply, and refresh.</span></span> <span data-ttu-id="a44b4-157">Dopo aver completato questi passaggi, è possibile aggiornare l'account amministratore.</span><span class="sxs-lookup"><span data-stu-id="a44b4-157">Once you've completed those steps, you can update the admin account.</span></span>

2. <span data-ttu-id="a44b4-158">Una volta che l'account amministratore ha un account e-mail associato, accedere a Human Resources con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="a44b4-158">After the Admin account has an associated email account, sign in to Human Resources with Admin credentials.</span></span>

3. <span data-ttu-id="a44b4-159">Accedere a un allegato in SharePoint per avviare l'anteprima del documento.</span><span class="sxs-lookup"><span data-stu-id="a44b4-159">Access an attachment in SharePoint to start the document preview.</span></span>

4. <span data-ttu-id="a44b4-160">Accedere con un altro account utente che ha accesso agli allegati e verificare che l'anteprima funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="a44b4-160">Sign in with another user account that has access to attachments and verify that the preview works as expected.</span></span>

## <a name="see-also"></a><span data-ttu-id="a44b4-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a44b4-161">See also</span></span>

[<span data-ttu-id="a44b4-162">Novità o modifiche in Human Resources</span><span class="sxs-lookup"><span data-stu-id="a44b4-162">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="a44b4-163">Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019</span><span class="sxs-lookup"><span data-stu-id="a44b4-163">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="a44b4-164">Aggiornare un processo</span><span class="sxs-lookup"><span data-stu-id="a44b4-164">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="a44b4-165">Gestire le funzionalità</span><span class="sxs-lookup"><span data-stu-id="a44b4-165">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]