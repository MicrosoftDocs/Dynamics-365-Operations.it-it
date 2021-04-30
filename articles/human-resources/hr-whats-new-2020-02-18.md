---
title: Novità o modifiche in Dynamics 365 Human Resources (18 febbraio 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 18 febbraio 2020.
author: andreabichsel
ms.date: 02/18/2020
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
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8109826df93f9916914a2db3876ee0f9107985f9
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890960"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a><span data-ttu-id="c679d-103">Novità o modifiche in Dynamics 365 Human Resources (18 febbraio 2020)</span><span class="sxs-lookup"><span data-stu-id="c679d-103">What's new or changed in Dynamics 365 Human Resources (February 18, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="c679d-104">Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c679d-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="c679d-105">Le modifiche si applicano alla build 8.1.2903.</span><span class="sxs-lookup"><span data-stu-id="c679d-105">Changes apply to build number 8.1.2903.</span></span> <span data-ttu-id="c679d-106">I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.</span><span class="sxs-lookup"><span data-stu-id="c679d-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="platform-update-32"></a><span data-ttu-id="c679d-107">Update 32 della piattaforma</span><span class="sxs-lookup"><span data-stu-id="c679d-107">Platform update 32</span></span> 

<span data-ttu-id="c679d-108">L'update 32 della piattaforma è ora disponibile.</span><span class="sxs-lookup"><span data-stu-id="c679d-108">Platform update 32 is now available.</span></span> <span data-ttu-id="c679d-109">Per ulteriori informazioni, vedere [Novità o modifiche introdotte nell'update 32 della piattaforma per app Finance and Operations (febbraio 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32.md).</span><span class="sxs-lookup"><span data-stu-id="c679d-109">For more information, see [What's new or changed in Platform update 32 for Finance and Operations (February 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32.md).</span></span>

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a><span data-ttu-id="c679d-110">I valori di ricerca vengono memorizzati quando si modificano le opzioni di visualizzazione nel modulo dipendente semplificato (383833)</span><span class="sxs-lookup"><span data-stu-id="c679d-110">Search values are remembered when changing view options in streamlined employee form (383833)</span></span>

<span data-ttu-id="c679d-111">Il nuovo modulo **Lavoratore** ora memorizza i valori di ricerca quando si cambiano le opzioni di visualizzazione e si applicano le modifiche.</span><span class="sxs-lookup"><span data-stu-id="c679d-111">The new **Worker** form now remembers  search values when you change the view options and apply changes.</span></span>

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a><span data-ttu-id="c679d-112">I riquadri di riepilogo della gestione retribuzioni nella funzione di anteprima reindirizzano al modulo errato (401861)</span><span class="sxs-lookup"><span data-stu-id="c679d-112">Compensation management summary tiles in preview feature redirect to wrong form (401861)</span></span>

<span data-ttu-id="c679d-113">I riquadri della gestione retribuzioni fissa e variabile ora visualizzano i record corretti nel nuovo modulo **Lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="c679d-113">Fixed and variable compensation management tiles now display the correct records in the new **Worker** form.</span></span> <span data-ttu-id="c679d-114">Si applica solo alla funzione di anteprima del modulo dipendente semplificato.</span><span class="sxs-lookup"><span data-stu-id="c679d-114">Applies only to the streamlined employee form preview feature.</span></span> <span data-ttu-id="c679d-115">È possibile abilitare questa funzione di anteprima in **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="c679d-115">You can enable this preview feature in **Feature management**.</span></span> <span data-ttu-id="c679d-116">Per ulteriori informazioni, vedere [Gestire le funzionalità](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="c679d-116">For more information, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="empty-status-field-for-some-leave-request-records-in-dataverse-414915"></a><span data-ttu-id="c679d-117">Campo di stato vuoto per alcuni record di richiesta di congedo in Dataverse (414.915)</span><span class="sxs-lookup"><span data-stu-id="c679d-117">Empty Status field for some leave request records in Dataverse (414915)</span></span>

<span data-ttu-id="c679d-118">Questa modifica risolve un problema in Dataverse quando il campo **Stato** in una richiesta di congedo è impostato su **Revisione**.</span><span class="sxs-lookup"><span data-stu-id="c679d-118">This change corrects an issue in Dataverse when the **Status** field in a leave request is set to **Review**.</span></span> <span data-ttu-id="c679d-119">Dataverse ora riflette lo stato.</span><span class="sxs-lookup"><span data-stu-id="c679d-119">Dataverse now reflects the status.</span></span>

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a><span data-ttu-id="c679d-120">Analisi lacuna competenze possibile solo per il lavoro assegnato (411390)</span><span class="sxs-lookup"><span data-stu-id="c679d-120">Skill gap analysis only possible for assigned job (411390)</span></span>

<span data-ttu-id="c679d-121">È ora possibile eseguire un'analisi lacuna competenze su qualsiasi lavoro definito in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c679d-121">You can now do a skill gap analysis on any job defined in Human Resources.</span></span>

## <a name="system-currency-doesnt-sync-from-dataverse-to-human-resources-in-new-environments-418011"></a><span data-ttu-id="c679d-122">La valuta di sistema non si sincronizza da Dataverse in Human Resources in nuovi ambienti (418011)</span><span class="sxs-lookup"><span data-stu-id="c679d-122">System currency doesn't sync from Dataverse to Human Resources in new environments (418011)</span></span>

<span data-ttu-id="c679d-123">La valuta di sistema in Dataverse ora si sincronizza con Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c679d-123">The system currency in Dataverse can now sync to Human Resources.</span></span>

## <a name="in-preview"></a><span data-ttu-id="c679d-124">In anteprima</span><span class="sxs-lookup"><span data-stu-id="c679d-124">In preview</span></span>

- [<span data-ttu-id="c679d-125">Funzionalità di anteprima di Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="c679d-125">Leave and absence preview features</span></span>](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [<span data-ttu-id="c679d-126">Funzionalità di anteprima della gestione dei benefit</span><span class="sxs-lookup"><span data-stu-id="c679d-126">Benefits management preview features</span></span>](hr-benefits-management-overview.md)

## <a name="coming-soon"></a><span data-ttu-id="c679d-127">Presto disponibili</span><span class="sxs-lookup"><span data-stu-id="c679d-127">Coming soon</span></span>

### <a name="updated-dataverse-solution"></a><span data-ttu-id="c679d-128">Soluzione Dataverse aggiornata</span><span class="sxs-lookup"><span data-stu-id="c679d-128">Updated Dataverse solution</span></span>

<span data-ttu-id="c679d-129">Una nuova soluzione Dataverse sarà presto disponibile con le seguenti modifiche:</span><span class="sxs-lookup"><span data-stu-id="c679d-129">A new Dataverse solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="c679d-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c679d-130">Description</span></span> | <span data-ttu-id="c679d-131">Modifica</span><span class="sxs-lookup"><span data-stu-id="c679d-131">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="c679d-132">Modifiche all'entità **Posizione lavorativa**</span><span class="sxs-lookup"><span data-stu-id="c679d-132">**Job/Position** entity changes</span></span> | <span data-ttu-id="c679d-133">Aggiunta di **Paese di retribuzione**</span><span class="sxs-lookup"><span data-stu-id="c679d-133">**Compensation region** added</span></span></br><span data-ttu-id="c679d-134">Aggiunta di **Dimensioni finanziarie**</span><span class="sxs-lookup"><span data-stu-id="c679d-134">**Financial dimensions** added</span></span> |
| <span data-ttu-id="c679d-135">Modifiche all'entità **Lavoratore**</span><span class="sxs-lookup"><span data-stu-id="c679d-135">**Worker** entity changes</span></span> | <span data-ttu-id="c679d-136">Aggiunta di **Sequenza nome**</span><span class="sxs-lookup"><span data-stu-id="c679d-136">**Name sequence** added</span></span></br><span data-ttu-id="c679d-137">Aggiunta di **Lavora da casa**</span><span class="sxs-lookup"><span data-stu-id="c679d-137">**Works from home** added</span></span></br><span data-ttu-id="c679d-138">Aggiunta di **Lingua**</span><span class="sxs-lookup"><span data-stu-id="c679d-138">**Language** added</span></span></br><span data-ttu-id="c679d-139">Aggiunta di **Data di anzianità**</span><span class="sxs-lookup"><span data-stu-id="c679d-139">**Seniority date** added</span></span></br><span data-ttu-id="c679d-140">Aggiunta di **Data di ricorrenza annuale**</span><span class="sxs-lookup"><span data-stu-id="c679d-140">**Anniversary date** added</span></span></br><span data-ttu-id="c679d-141">Aggiunta di **Data di assunzione originale**</span><span class="sxs-lookup"><span data-stu-id="c679d-141">**Original hire date** added</span></span> |
| <span data-ttu-id="c679d-142">Modifiche all'entità **Impiego**</span><span class="sxs-lookup"><span data-stu-id="c679d-142">**Employment** entity changes</span></span> | <span data-ttu-id="c679d-143">Aggiunta di **Dimensioni finanziarie**</span><span class="sxs-lookup"><span data-stu-id="c679d-143">**Financial dimensions** added</span></span></br><span data-ttu-id="c679d-144">Aggiunta di **Motivo fine rapporto**</span><span class="sxs-lookup"><span data-stu-id="c679d-144">**Termination reason** added</span></span></br><span data-ttu-id="c679d-145">**Data di transizione** rinominata in **Data fine rapporto**</span><span class="sxs-lookup"><span data-stu-id="c679d-145">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="c679d-146">Aggiunta di **Date periodo di prova**</span><span class="sxs-lookup"><span data-stu-id="c679d-146">**Probation date** added</span></span> |
| <span data-ttu-id="c679d-147">Modifiche all'entità **Indirizzo lavoratore**</span><span class="sxs-lookup"><span data-stu-id="c679d-147">**Worker address** entity changes</span></span> | <span data-ttu-id="c679d-148">Aggiunta di **Nome della via**</span><span class="sxs-lookup"><span data-stu-id="c679d-148">**Street address** added</span></span></br><span data-ttu-id="c679d-149">**Riga indirizzo 1**, **Riga indirizzo 2** e **Riga indirizzo 3** contrassegnate per deprecamento</span><span class="sxs-lookup"><span data-stu-id="c679d-149">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="c679d-150">Nuove entità di impostazione della retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="c679d-150">New variable compensation setup entities</span></span> | <span data-ttu-id="c679d-151">**Tipo di piano di retribuzione variabile**</span><span class="sxs-lookup"><span data-stu-id="c679d-151">**Compensation variable plan type**</span></span></br><span data-ttu-id="c679d-152">**Piano di retribuzione variabile**</span><span class="sxs-lookup"><span data-stu-id="c679d-152">**Compensation variable plan**</span></span></br><span data-ttu-id="c679d-153">**Regole distribuzione incentivi**</span><span class="sxs-lookup"><span data-stu-id="c679d-153">**Vesting rules**</span></span></br><span data-ttu-id="c679d-154">**Livello del piano di retribuzione variabile**</span><span class="sxs-lookup"><span data-stu-id="c679d-154">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="c679d-155">Nuova entità **Impiego calendario lavoratore**</span><span class="sxs-lookup"><span data-stu-id="c679d-155">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="c679d-156">Aggiunta di **Entità calendario lavoro**</span><span class="sxs-lookup"><span data-stu-id="c679d-156">**Work calendar entity** added</span></span> |
| <span data-ttu-id="c679d-157">Nuova entità **Dettagli posizione di retribuzione**</span><span class="sxs-lookup"><span data-stu-id="c679d-157">New **Payroll position detail** entity</span></span> | <span data-ttu-id="c679d-158">Aggiunta di **Dettagli posizione di retribuzione**</span><span class="sxs-lookup"><span data-stu-id="c679d-158">**Payroll position detail** added</span></span> |
| <span data-ttu-id="c679d-159">Nuova entità **Titolo**</span><span class="sxs-lookup"><span data-stu-id="c679d-159">New **Title** entity</span></span> | <span data-ttu-id="c679d-160">Aggiunta di **Titolo**.</span><span class="sxs-lookup"><span data-stu-id="c679d-160">**Title** added.</span></span> <span data-ttu-id="c679d-161">La nuova entità **Titolo** sarà inclusa nel processo di sincronizzazione tra Human Resources e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c679d-161">The new **Title** entity will be included in the sync process between Human Resources and Dataverse.</span></span> <span data-ttu-id="c679d-162">Inizialmente non vi verrà fatto riferimento dalle entità **Posizione lavorativa** o **Posizione**.</span><span class="sxs-lookup"><span data-stu-id="c679d-162">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c679d-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c679d-163">See also</span></span>

[<span data-ttu-id="c679d-164">Novità o modifiche in Human Resources</span><span class="sxs-lookup"><span data-stu-id="c679d-164">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="c679d-165">Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019</span><span class="sxs-lookup"><span data-stu-id="c679d-165">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="c679d-166">Aggiornare un processo</span><span class="sxs-lookup"><span data-stu-id="c679d-166">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="c679d-167">Gestire le funzionalità</span><span class="sxs-lookup"><span data-stu-id="c679d-167">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]