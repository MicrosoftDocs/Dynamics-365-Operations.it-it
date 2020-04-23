---
title: Novità o modifiche in Dynamics 365 Human Resources (13 aprile 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 4/13/2020
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
ms.search.validFrom: 2020-04-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 711cc4491024e647429b108438ce1d88483ea63c
ms.sourcegitcommit: dbff1c6bb371a443a0cd2a310f5a48d5c21b08ca
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "3259819"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-13-2020"></a><span data-ttu-id="457df-103">Novità o modifiche in Dynamics 365 Human Resources (13 aprile 2020)</span><span class="sxs-lookup"><span data-stu-id="457df-103">What's new or changed in Dynamics 365 Human Resources (April 13, 2020)</span></span>

<span data-ttu-id="457df-104">Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="457df-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="457df-105">Le modifiche si applicano alla build 8.1.3136.</span><span class="sxs-lookup"><span data-stu-id="457df-105">Changes apply to build number 8.1.3136.</span></span> <span data-ttu-id="457df-106">I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.</span><span class="sxs-lookup"><span data-stu-id="457df-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="new-production-release-cadence"></a><span data-ttu-id="457df-107">Nuova cadenza di rilascio di produzione</span><span class="sxs-lookup"><span data-stu-id="457df-107">New production release cadence</span></span>

<span data-ttu-id="457df-108">A partire da questo rilascio settimanale, la cadenza di rilascio di Human Resources passa da un aggiornamento settimanale a un aggiornamento bisettimanale.</span><span class="sxs-lookup"><span data-stu-id="457df-108">With this week's release, the release cadence for Human Resources shifts from a weekly update to a biweekly update.</span></span> <span data-ttu-id="457df-109">Per garantire l'allineamento con procedure di distribuzione sicure e mantenere elevati gli standard di stabilità e affidabilità nel servizio, il processo di distribuzione degli aggiornamenti del servizio in tutte le regioni è ora un'implementazione ogni due settimane.</span><span class="sxs-lookup"><span data-stu-id="457df-109">To ensure alignment with safe deployment practices, and maintain high standards of stability and reliability in the service, the process of deploying service updates to all regions is now a two-week rollout.</span></span> <span data-ttu-id="457df-110">Ulteriori test e controlli sono applicati per verificare la corretta implementazione in ogni fase del processo.</span><span class="sxs-lookup"><span data-stu-id="457df-110">Additional testing and monitors are in place to verify successful deployment at each stage of the process.</span></span> <span data-ttu-id="457df-111">Per ulteriori informazioni sulla cadenza di rilascio, consultare [Processo di aggiornamento](hr-admin-setup-update-process.md).</span><span class="sxs-lookup"><span data-stu-id="457df-111">For more information on the release cadence, see [Update process](hr-admin-setup-update-process.md).</span></span>

## <a name="rounding-precision-field-isnt-editable-after-specifying-a-rounding-type-435616"></a><span data-ttu-id="457df-112">Il campo della precisione di arrotondamento non è modificabile dopo aver specificato un tipo di arrotondamento (435616)</span><span class="sxs-lookup"><span data-stu-id="457df-112">Rounding precision field isn't editable after specifying a Rounding type (435616)</span></span>

<span data-ttu-id="457df-113">Con questa modifica, il campo **Precisione di arrotondamento** è ora disponibile dopo aver aggiornato il campo **Tipo di arrotondamento**.</span><span class="sxs-lookup"><span data-stu-id="457df-113">With this change, the **Rounding precision** field is now available after you update the **Rounding type** field.</span></span>

## <a name="cant-edit-leave-enrollment-end-date-when-the-leave-plan-doesnt-have-accrual-periods-413628"></a><span data-ttu-id="457df-114">Impossibile modificare la data di fine iscrizione congedo quando il piano di congedo non ha periodi di attribuzione per competenza (413628)</span><span class="sxs-lookup"><span data-stu-id="457df-114">Can't edit leave enrollment end date when the leave plan doesn't have accrual periods (413628)</span></span>

<span data-ttu-id="457df-115">Ora è possibile modificare la data di fine iscrizione senza ricevere l'errore indicante che il campo Base data di accumulo deve essere compilato.</span><span class="sxs-lookup"><span data-stu-id="457df-115">You can now edit the enrollment end date without getting the error "Field Accrual date basis must be filled in."</span></span>

## <a name="employment-entity-doesnt-sync-to-common-data-service-430834"></a><span data-ttu-id="457df-116">L'entità di impiego non si sincronizza con Common Data Service (430834)</span><span class="sxs-lookup"><span data-stu-id="457df-116">Employment entity doesn't sync to Common Data Service (430834)</span></span>

<span data-ttu-id="457df-117">Questa modifica corregge un problema a causa del quale i dati sull'impiego non erano sincronizzati in Common Data Service dopo aver aggiunto le dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="457df-117">This change corrects an issue where the employment data wasn't syncing to Common Data Service after adding financial dimensions.</span></span> 

## <a name="remove-multi-parenting-for-work-calendar-time-interval-entity-431775"></a><span data-ttu-id="457df-118">Rimuovere l'associazione di più elementi padre per l'entità Intervallo orario del calendario di lavoro (431775)</span><span class="sxs-lookup"><span data-stu-id="457df-118">Remove multi-parenting for Work Calendar Time Interval entity (431775)</span></span>

<span data-ttu-id="457df-119">Questa modifica rimuove l'associazione di più elementi padre per l'entità **Intervallo orario del calendario di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="457df-119">This change removes multi-parenting for the **Work Calendar Time Interval** entity.</span></span>

## <a name="filter-with-cast-function-doesnt-work-on-odata-call-position-worker-assignment-entity-431699"></a><span data-ttu-id="457df-120">Il filtro con la funzione CAST non funziona sull'entità Assegnazione lavoratore posizione della chiamata OData (431699)</span><span class="sxs-lookup"><span data-stu-id="457df-120">Filter with CAST function doesn't work on OData call Position Worker Assignment entity (431699)</span></span>

<span data-ttu-id="457df-121">Questo aggiornamento include una modifica per consentire il filtro con la funzione CAST in OData per l'entità **Assegnazione lavoratore posizione**.</span><span class="sxs-lookup"><span data-stu-id="457df-121">This update includes a change to allow  filter with CAST function within OData for the **Position Worker Assignment** entity.</span></span>

## <a name="in-preview"></a><span data-ttu-id="457df-122">In anteprima</span><span class="sxs-lookup"><span data-stu-id="457df-122">In Preview</span></span>

## <a name="leave-suspension"></a><span data-ttu-id="457df-123">Sospensione del congedo</span><span class="sxs-lookup"><span data-stu-id="457df-123">Leave suspension</span></span>

<span data-ttu-id="457df-124">È possibile sospendere le ferie e le assenze nelle risorse umane per un dipendente.</span><span class="sxs-lookup"><span data-stu-id="457df-124">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="457df-125">La sospensione del congedo e interrompe la maturazione delle ferie per i tipi di congedi selezionati.</span><span class="sxs-lookup"><span data-stu-id="457df-125">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="457df-126">Se la sospensione si verifica dopo l'elaborazione della maturazione, la sospensione delle ferie crea una rettifica proporzionale del saldo delle ferie del dipendente.</span><span class="sxs-lookup"><span data-stu-id="457df-126">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="457df-127">Per ulteriori informazioni, vedere [Sospendere il congedo](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="457df-127">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="457df-128">Regole di riporto</span><span class="sxs-lookup"><span data-stu-id="457df-128">Carry forward rules</span></span>

<span data-ttu-id="457df-129">È possibile specificare un tipo di congedo riporto per i saldi del riporto in cui vengono trasferiti le rettifiche di riporto.</span><span class="sxs-lookup"><span data-stu-id="457df-129">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="457df-130">Ad esempio, se un dipendente riporta 10 giorni, è possibile scegliere un tipo di congedo diverso per quei 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="457df-130">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="457df-131">Per ulteriori informazioni, vedere [Configurare i tipi di congedo e assenza](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="457df-131">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="457df-132">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="457df-132">Known issues</span></span>

## <a name="employment-details-entity"></a><span data-ttu-id="457df-133">Entità Dettagli impiego</span><span class="sxs-lookup"><span data-stu-id="457df-133">Employment Details entity</span></span>

<span data-ttu-id="457df-134">L'entità **Dettagli impiego** è stata aggiornata con i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="457df-134">The **Employment Detail** entity has been updated with the following fields:</span></span>

- <span data-ttu-id="457df-135">**PayFrequency**</span><span class="sxs-lookup"><span data-stu-id="457df-135">**PayFrequency**</span></span>
- <span data-ttu-id="457df-136">**ID categoria impiego**</span><span class="sxs-lookup"><span data-stu-id="457df-136">**Employment Category ID**</span></span>
- <span data-ttu-id="457df-137">**Tipo di impiego**</span><span class="sxs-lookup"><span data-stu-id="457df-137">**Employment Type**</span></span>
- <span data-ttu-id="457df-138">**ID EmploymentType**</span><span class="sxs-lookup"><span data-stu-id="457df-138">**EmploymentType ID**</span></span>
- <span data-ttu-id="457df-139">**Stato impiego benefit**</span><span class="sxs-lookup"><span data-stu-id="457df-139">**Benefit Employment Status**</span></span>

<span data-ttu-id="457df-140">I dati di configurazione per questi campi si basano sulla gestione dei benefit abilitata nell'area di lavoro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="457df-140">The setup data for these fields rely on benefits management being enabled in the **Feature management** workspace.</span></span> <span data-ttu-id="457df-141">Non popolare o aggiornare questi campi nell'entità **Dettagli impiego** perché vengono restituiti errori durante l'importazione.</span><span class="sxs-lookup"><span data-stu-id="457df-141">Don't populate or update these fields in the **Employment Detail** entity, because it will result in errors during import.</span></span>

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a><span data-ttu-id="457df-142">L'anteprima di SharePoint non funziona in alcuni ambienti</span><span class="sxs-lookup"><span data-stu-id="457df-142">SharePoint preview doesn't work in some environments</span></span>

<span data-ttu-id="457df-143">Se l'anteprima del documento per i documenti memorizzati in SharePoint non funziona, provare la seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="457df-143">If document preview for documents stored in SharePoint doesn't work, try the following procedure:</span></span>

1. <span data-ttu-id="457df-144">Verificare che l'account utente amministratore abbia un'e-mail associata al record utente.</span><span class="sxs-lookup"><span data-stu-id="457df-144">Verify the Admin user account has an email associated with the user record.</span></span> <span data-ttu-id="457df-145">È possibile visualizzare tali informazioni nella pagina **Utente**.</span><span class="sxs-lookup"><span data-stu-id="457df-145">You can view this information in the **User** page.</span></span> <span data-ttu-id="457df-146">Se l'e-mail non è impostata, è necessario aggiungere l'e-mail e il provider con il componente aggiuntivo OData Excel.</span><span class="sxs-lookup"><span data-stu-id="457df-146">If email isn't set up, you need to add the email and provider with the OData Excel add-in.</span></span> <span data-ttu-id="457df-147">Per impostazione predefinita, l'indirizzo e-mail non è presente nella progettazione di Excel.</span><span class="sxs-lookup"><span data-stu-id="457df-147">By default, the email address isn't present in the Excel design.</span></span> <span data-ttu-id="457df-148">È necessario modificare la progettazione di Excel, aggiungere tutti i campi, applicare e aggiornare.</span><span class="sxs-lookup"><span data-stu-id="457df-148">You'll need to edit the Excel design, add all fields, apply, and refresh.</span></span> <span data-ttu-id="457df-149">Dopo aver completato questi passaggi, è possibile aggiornare l'account amministratore.</span><span class="sxs-lookup"><span data-stu-id="457df-149">Once you've completed those steps, you can update the admin account.</span></span>

2. <span data-ttu-id="457df-150">Una volta che l'account amministratore ha un account e-mail associato, accedere a Human Resources con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="457df-150">After the Admin account has an associated email account, sign in to Human Resources with Admin credentials.</span></span>

3. <span data-ttu-id="457df-151">Accedere a un allegato in SharePoint per avviare l'anteprima del documento.</span><span class="sxs-lookup"><span data-stu-id="457df-151">Access an attachment in SharePoint to start the document preview.</span></span>

4. <span data-ttu-id="457df-152">Accedere con un altro account utente che ha accesso agli allegati e verificare che l'anteprima funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="457df-152">Sign in with another user account that has access to attachments and verify that the preview works as expected.</span></span>
