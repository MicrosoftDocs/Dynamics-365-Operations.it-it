---
title: Novità o modifiche in Dynamics 365 Human Resources (25 febbraio 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 25 febbraio 2020.
author: Darinkramer
manager: AnnBe
ms.date: 02/25/2020
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
ms.search.validFrom: 2020-02-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1302686aeba52de484ad520efe292fafefc39ebf
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4526812"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a><span data-ttu-id="53337-103">Novità o modifiche in Dynamics 365 Human Resources (25 febbraio 2020)</span><span class="sxs-lookup"><span data-stu-id="53337-103">What's new or changed in Dynamics 365 Human Resources (February 25, 2020)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="53337-104">Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="53337-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="53337-105">Le modifiche si applicano alla build 8.1.2927.</span><span class="sxs-lookup"><span data-stu-id="53337-105">Changes apply to build number 8.1.2927.</span></span> <span data-ttu-id="53337-106">I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.</span><span class="sxs-lookup"><span data-stu-id="53337-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a><span data-ttu-id="53337-107">Abilitare l'entità framework di gestione dei dati e navigazione di gestione dei casi (DMF) (414754)</span><span class="sxs-lookup"><span data-stu-id="53337-107">Enable Case Management navigation and data management framework (DMF) entity (414754)</span></span>

<span data-ttu-id="53337-108">Questa funzione di anteprima consente una navigazione aggiuntiva ai casi di gestione dei casi.</span><span class="sxs-lookup"><span data-stu-id="53337-108">This preview feature enables additional navigation to case management cases.</span></span> <span data-ttu-id="53337-109">È possibile abilitare questa funzione di anteprima nell'area di lavoro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="53337-109">You can enable this preview feature in the **Feature Management** workspace.</span></span> <span data-ttu-id="53337-110">Queste voci di menu appaiono nell'area di lavoro **Conformità** di Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="53337-110">These menu items appear in the **Compliance** workspace of Dynamics 365 Human Resources.</span></span> <span data-ttu-id="53337-111">Con questa modifica, Human Resources può accedere a:</span><span class="sxs-lookup"><span data-stu-id="53337-111">With this change, Human Resources can access:</span></span>

- <span data-ttu-id="53337-112">Tutti i casi</span><span class="sxs-lookup"><span data-stu-id="53337-112">All cases</span></span>
- <span data-ttu-id="53337-113">Casi personali</span><span class="sxs-lookup"><span data-stu-id="53337-113">My cases</span></span>
- <span data-ttu-id="53337-114">Casi personali aperti</span><span class="sxs-lookup"><span data-stu-id="53337-114">My open cases</span></span>
- <span data-ttu-id="53337-115">Casi personali scaduti</span><span class="sxs-lookup"><span data-stu-id="53337-115">My overdue cases</span></span>
- <span data-ttu-id="53337-116">Casi assegnati all'utente tramite un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="53337-116">Cases assigned to me through workflow</span></span>

<span data-ttu-id="53337-117">Insieme a queste nuove visualizzazioni dei casi, è disponibile l'entità DMF **Dettaglio caso**.</span><span class="sxs-lookup"><span data-stu-id="53337-117">Along with these new views into cases, the **Case detail** DMF entity is also available.</span></span>

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a><span data-ttu-id="53337-118">Abilitare le definizioni di relazione nel rubrica globale (414762)</span><span class="sxs-lookup"><span data-stu-id="53337-118">Enable Relationship definitions in global address bBook (414762)</span></span>

<span data-ttu-id="53337-119">Le relazioni sono ora abilitate nella rubrica globale.</span><span class="sxs-lookup"><span data-stu-id="53337-119">Relationships are now enabled in the global address book.</span></span> <span data-ttu-id="53337-120">Prima dell'uscita di questa settimana, il riquadro Dettaglio informazioni **Relazioni** mostrava eventuali relazioni definite dal sistema.</span><span class="sxs-lookup"><span data-stu-id="53337-120">Prior to this week's release, the **Relationship** fact box displayed any system-defined relationships.</span></span> <span data-ttu-id="53337-121">Ora è possibile definire quelle relazioni all'interno della pagina della rubrica globale.</span><span class="sxs-lookup"><span data-stu-id="53337-121">Now you can define those relationships within the global address book page.</span></span>

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a><span data-ttu-id="53337-122">Una posizione può essere rimossa quando esistono record di compensazione attivi per la posizione (414568)</span><span class="sxs-lookup"><span data-stu-id="53337-122">A position can be removed when active compensation records exist for the position (414568)</span></span>

<span data-ttu-id="53337-123">Con questa modifica, viene visualizzato un avviso quando si tenta di eliminare una posizione e un lavoratore ha un record di compensazione attivo per quella stessa posizione.</span><span class="sxs-lookup"><span data-stu-id="53337-123">With this change, a warning appears when you attempt to delete a position and a worker has an active compensation record for that same position.</span></span> <span data-ttu-id="53337-124">In questo caso, è necessario aggiornare il record di retribuzione fissa del dipendente prima di rimuovere la posizione.</span><span class="sxs-lookup"><span data-stu-id="53337-124">When this happens, you must update the employee fixed compensation record before removing the position.</span></span>

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a><span data-ttu-id="53337-125">Il flusso di lavoro di revisione delle prestazioni aggiunge occasionalmente le approvazioni da parte di persone che non fanno parte del processo (414171)</span><span class="sxs-lookup"><span data-stu-id="53337-125">Performance review workflow occasionally adds sign-offs from people who are not part of the process (414171)</span></span>

<span data-ttu-id="53337-126">Questa modifica risolve un problema in cui i partecipanti di conferma aggiuntivi venivano aggiunti alla revisione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="53337-126">This change corrects an issue where additional sign-off participants are added to the performance review.</span></span>

## <a name="worker-position-assignment-not-created-in-common-data-service-when-selected-on-the-new-worker-dialog-413479"></a><span data-ttu-id="53337-127">Assegnazione della posizione del lavoratore non creata in Common Data Service quando selezionata nella finestra di dialogo Nuovo lavoratore (413479)</span><span class="sxs-lookup"><span data-stu-id="53337-127">Worker position assignment not created in Common Data Service when selected on the New Worker dialog (413479)</span></span>

<span data-ttu-id="53337-128">Questa modifica corregge un problema durante l'assunzione di un nuovo lavoratore e l'assegnazione della nuova assunzione a una posizione nella finestra di dialogo **Nuovo lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="53337-128">This change corrects an issue when hiring a new worker and assigning the new hire to a position through the **New worker** dialog.</span></span> <span data-ttu-id="53337-129">Ora l'assegnazione della posizione si riflette in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="53337-129">Now the position assignment is reflected in Common Data Service.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="53337-130">Presto disponibili</span><span class="sxs-lookup"><span data-stu-id="53337-130">Coming soon</span></span>

### <a name="updated-common-data-service-solution"></a><span data-ttu-id="53337-131">Soluzione Common Data Service aggiornata</span><span class="sxs-lookup"><span data-stu-id="53337-131">Updated Common Data Service solution</span></span>

<span data-ttu-id="53337-132">Una nuova soluzione Common Data Service sarà presto disponibile con le seguenti modifiche:</span><span class="sxs-lookup"><span data-stu-id="53337-132">A new Common Data Service solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="53337-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53337-133">Description</span></span> | <span data-ttu-id="53337-134">Modifica</span><span class="sxs-lookup"><span data-stu-id="53337-134">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="53337-135">Modifiche all'entità **Posizione lavorativa**</span><span class="sxs-lookup"><span data-stu-id="53337-135">**Job/Position** entity changes</span></span> | <span data-ttu-id="53337-136">Aggiunta di **Paese di retribuzione**</span><span class="sxs-lookup"><span data-stu-id="53337-136">**Compensation region** added</span></span></br><span data-ttu-id="53337-137">Aggiunta di **Dimensioni finanziarie**</span><span class="sxs-lookup"><span data-stu-id="53337-137">**Financial dimensions** added</span></span> |
| <span data-ttu-id="53337-138">Modifiche all'entità **Lavoratore**</span><span class="sxs-lookup"><span data-stu-id="53337-138">**Worker** entity changes</span></span> | <span data-ttu-id="53337-139">Aggiunta di **Sequenza nome**</span><span class="sxs-lookup"><span data-stu-id="53337-139">**Name sequence** added</span></span></br><span data-ttu-id="53337-140">Aggiunta di **Lavora da casa**</span><span class="sxs-lookup"><span data-stu-id="53337-140">**Works from home** added</span></span></br><span data-ttu-id="53337-141">Aggiunta di **Lingua**</span><span class="sxs-lookup"><span data-stu-id="53337-141">**Language** added</span></span></br><span data-ttu-id="53337-142">Aggiunta di **Data di anzianità**</span><span class="sxs-lookup"><span data-stu-id="53337-142">**Seniority date** added</span></span></br><span data-ttu-id="53337-143">Aggiunta di **Data di ricorrenza annuale**</span><span class="sxs-lookup"><span data-stu-id="53337-143">**Anniversary date** added</span></span></br><span data-ttu-id="53337-144">Aggiunta di **Data di assunzione originale**</span><span class="sxs-lookup"><span data-stu-id="53337-144">**Original hire date** added</span></span> |
| <span data-ttu-id="53337-145">Modifiche all'entità **Impiego**</span><span class="sxs-lookup"><span data-stu-id="53337-145">**Employment** entity changes</span></span> | <span data-ttu-id="53337-146">Aggiunta di **Dimensioni finanziarie**</span><span class="sxs-lookup"><span data-stu-id="53337-146">**Financial dimensions** added</span></span></br><span data-ttu-id="53337-147">Aggiunta di **Motivo fine rapporto**</span><span class="sxs-lookup"><span data-stu-id="53337-147">**Termination reason** added</span></span></br><span data-ttu-id="53337-148">**Data di transizione** rinominata in **Data fine rapporto**</span><span class="sxs-lookup"><span data-stu-id="53337-148">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="53337-149">Aggiunta di **Date periodo di prova**</span><span class="sxs-lookup"><span data-stu-id="53337-149">**Probation date** added</span></span> |
| <span data-ttu-id="53337-150">Modifiche all'entità **Indirizzo lavoratore**</span><span class="sxs-lookup"><span data-stu-id="53337-150">**Worker address** entity changes</span></span> | <span data-ttu-id="53337-151">Aggiunta di **Nome della via**</span><span class="sxs-lookup"><span data-stu-id="53337-151">**Street address** added</span></span></br><span data-ttu-id="53337-152">**Riga indirizzo 1**, **Riga indirizzo 2** e **Riga indirizzo 3** contrassegnate per deprecamento</span><span class="sxs-lookup"><span data-stu-id="53337-152">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="53337-153">Nuove entità di impostazione della retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="53337-153">New variable compensation setup entities</span></span> | <span data-ttu-id="53337-154">**Tipo di piano di retribuzione variabile**</span><span class="sxs-lookup"><span data-stu-id="53337-154">**Compensation variable plan type**</span></span></br><span data-ttu-id="53337-155">**Piano di retribuzione variabile**</span><span class="sxs-lookup"><span data-stu-id="53337-155">**Compensation variable plan**</span></span></br><span data-ttu-id="53337-156">**Regole distribuzione incentivi**</span><span class="sxs-lookup"><span data-stu-id="53337-156">**Vesting rules**</span></span></br><span data-ttu-id="53337-157">**Livello del piano di retribuzione variabile**</span><span class="sxs-lookup"><span data-stu-id="53337-157">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="53337-158">Nuova entità **Impiego calendario lavoratore**</span><span class="sxs-lookup"><span data-stu-id="53337-158">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="53337-159">Aggiunta di **Entità calendario lavoro**</span><span class="sxs-lookup"><span data-stu-id="53337-159">**Work calendar entity** added</span></span> |
| <span data-ttu-id="53337-160">Nuova entità **Dettagli posizione di retribuzione**</span><span class="sxs-lookup"><span data-stu-id="53337-160">New **Payroll position detail** entity</span></span> | <span data-ttu-id="53337-161">Aggiunta di **Dettagli posizione di retribuzione**</span><span class="sxs-lookup"><span data-stu-id="53337-161">**Payroll position detail** added</span></span> |
| <span data-ttu-id="53337-162">Nuova entità **Titolo**</span><span class="sxs-lookup"><span data-stu-id="53337-162">New **Title** entity</span></span> | <span data-ttu-id="53337-163">Aggiunta di **Titolo**.</span><span class="sxs-lookup"><span data-stu-id="53337-163">**Title** added.</span></span> <span data-ttu-id="53337-164">La nuova entità **Titolo** sarà inclusa nel processo di sincronizzazione tra Human Resources e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="53337-164">The new **Title** entity will be included in the sync process between Human Resources and Common Data Service.</span></span> <span data-ttu-id="53337-165">Inizialmente non vi verrà fatto riferimento dalle entità **Posizione lavorativa** o **Posizione**.</span><span class="sxs-lookup"><span data-stu-id="53337-165">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

<span data-ttu-id="53337-166">Nelle prossime settimane, questi cambiamenti di entità saranno disponibili in tutti gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="53337-166">Over the next few weeks, these entity changes will be available in all environments.</span></span> <span data-ttu-id="53337-167">Per installare manualmente l'ultima soluzione Common Data Service per Human Resources:</span><span class="sxs-lookup"><span data-stu-id="53337-167">To manually install the latest Common Data Service solution for Human Resources:</span></span>

1.  <span data-ttu-id="53337-168">Accedere all'[Interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="53337-168">Go to the [Power Platform Admin Center](https://admin.powerplatform.microsoft.com).</span></span>

2.  <span data-ttu-id="53337-169">Selezionare **Ambienti**.</span><span class="sxs-lookup"><span data-stu-id="53337-169">Select **Environments**.</span></span>

3.  <span data-ttu-id="53337-170">Trovare l'ambiente da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="53337-170">Find the environment you want to upgrade.</span></span> <span data-ttu-id="53337-171">L'ambiente deve corrispondere al **nome dell'ambiente** nella sezione **informazioni Common Data Service** del modulo **Informazioni su** in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="53337-171">This should correspond to **Environment name** in the **Common Data Service information** section in the **About** form in Human Resources.</span></span>

4.  <span data-ttu-id="53337-172">Selezionare l'ambiente per visualizzare i dettagli dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="53337-172">Select the environment to view the environment details.</span></span>

5.  <span data-ttu-id="53337-173">Selezionare **Gestisci soluzioni** nella barra di azione superiore.</span><span class="sxs-lookup"><span data-stu-id="53337-173">In the action bar at the top, select **Manage Solutions**.</span></span> <span data-ttu-id="53337-174">Una nuova finestra del browser viene visualizzata con l'**interfaccia di amministrazione di Dynamics 365** nel contesto dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="53337-174">A new browser window will open and navigate to **Dynamics 365 Administration Center** in the context of your environment.</span></span>

6.  <span data-ttu-id="53337-175">Nell'elenco **Soluzione** selezionare **Ancora Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="53337-175">In the **Solution** list, select **Dynamics 365 Human Resources Anchor**.</span></span>

7.  <span data-ttu-id="53337-176">Selezionare **Aggiorna** per applicare l'ultima soluzione.</span><span class="sxs-lookup"><span data-stu-id="53337-176">Select **Upgrade** to apply the latest solution.</span></span>

## <a name="in-preview"></a><span data-ttu-id="53337-177">In anteprima</span><span class="sxs-lookup"><span data-stu-id="53337-177">In preview</span></span>

<span data-ttu-id="53337-178">Le seguenti funzionalità di anteprima diventano disponibili a partire dal 3 febbraio 2020:</span><span class="sxs-lookup"><span data-stu-id="53337-178">The following preview features became available on February 3, 2020:</span></span>

- <span data-ttu-id="53337-179">**Funzionalità di anteprima di Congedi e assenza** - Per ulteriori informazioni, vedere [Funzionalità di anteprima di Congedo e assenza](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span><span class="sxs-lookup"><span data-stu-id="53337-179">**Leave and absence preview features** - For more information, see [Leave and absence preview features](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span></span>

- <span data-ttu-id="53337-180">**Funzionalità di anteprima di Gestione benefit** - Per ulteriori informazioni, inclusi problemi noti, vedere [Panoramica di Gestione benefit](hr-benefits-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="53337-180">**Benefits management preview feature** - For more information, including known issues, see [Benefits management overview](hr-benefits-management-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="53337-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53337-181">See also</span></span>

[<span data-ttu-id="53337-182">Novità o modifiche in Human Resources</span><span class="sxs-lookup"><span data-stu-id="53337-182">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="53337-183">Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019</span><span class="sxs-lookup"><span data-stu-id="53337-183">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="53337-184">Aggiornare un processo</span><span class="sxs-lookup"><span data-stu-id="53337-184">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="53337-185">Gestire le funzionalità</span><span class="sxs-lookup"><span data-stu-id="53337-185">Manage features</span></span>](hr-admin-manage-features.md)