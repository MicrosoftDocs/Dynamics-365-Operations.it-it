---
title: Novità o modifiche in Dynamics 365 Talent - Core HR (10 settembre 2018)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/12/2018
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
ms.search.validFrom: 2018-09-06
ms.dyn365.ops.version: Talent September 10, 2018 update
ms.openlocfilehash: ff5d21a8a71b068a276bedaf6e4b9964adcb4027
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896752"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-september-10-2018"></a><span data-ttu-id="94d22-103">Novità o modifiche in Dynamics 365 Talent - Core HR (10 settembre 2018)</span><span class="sxs-lookup"><span data-stu-id="94d22-103">What's new or changed in Dynamics 365 Talent - Core HR (September 10, 2018)</span></span>

<span data-ttu-id="94d22-104">**Build 8.1.138.0**</span><span class="sxs-lookup"><span data-stu-id="94d22-104">**Build 8.1.138.0**</span></span>

<span data-ttu-id="94d22-105">Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent: Core HR.</span><span class="sxs-lookup"><span data-stu-id="94d22-105">This topic describes features that are either new or changed in Microsoft Dynamics 365 Talent: Core HR.</span></span>

## <a name="allow-specific-time-of-day-on-time-off-requests-half-days"></a><span data-ttu-id="94d22-106">Consentire tempo specifico per le richieste di permessi (mezze giornate)</span><span class="sxs-lookup"><span data-stu-id="94d22-106">Allow specific time of day on time-off requests (half days)</span></span>

<span data-ttu-id="94d22-107">Se il Riquadri Dettaglio informazioni è impostato in modo che il permesso sia inviato per giorni, è ora possibile abilitare una definizione di mezza giornata.</span><span class="sxs-lookup"><span data-stu-id="94d22-107">If leave and absence is set up so that time off is submitted in days, you can now also enable a half-day definition.</span></span> <span data-ttu-id="94d22-108">In seguito, quando gli utenti inviano le richieste di permesso, possono specificare se richiedono un permesso per la prima parte o la seconda parte della giornata.</span><span class="sxs-lookup"><span data-stu-id="94d22-108">Then, when users submit time-off requests, they can specify whether they are requesting the first half or the second half of the day off.</span></span>

<span data-ttu-id="94d22-109">Per impostazione predefinita, questa opzione è disattivata.</span><span class="sxs-lookup"><span data-stu-id="94d22-109">By default, this option is turned off.</span></span> <span data-ttu-id="94d22-110">Per fare in modo che i dipendenti possano richiedere un permesso per la prima parte o la seconda parte della giornata, è necessario attivare questa opzione nell'area **Congedo e assenza** di Parametri Risorse umane.</span><span class="sxs-lookup"><span data-stu-id="94d22-110">For employees to request the first half or second half of the day off, you must turn on this option in the **Leave and absence** area of Human resources parameters.</span></span>

<span data-ttu-id="94d22-111">Il privilegio di sicurezza per questa funzionalità è Gestisci parametri Risorse umane.</span><span class="sxs-lookup"><span data-stu-id="94d22-111">The security privilege for this feature is Maintain Human Resources Parameters.</span></span>

## <a name="validation-of-leave-and-absence-entries"></a><span data-ttu-id="94d22-112">Convalida delle voci di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="94d22-112">Validation of leave and absence entries</span></span>

<span data-ttu-id="94d22-113">A seconda di come è configurato il permesso, i dipendenti che tentano di inviare una richiesta di permesso superiore alla giornata lavorativa ricevono un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="94d22-113">Depending on how leave is configured, employees who try to submit a time-off request that is longer than their work day receive a warning message.</span></span> <span data-ttu-id="94d22-114">In altre parole vengono avvisati se tentano di prendere più di un giorno di permesso in una data specifica.</span><span class="sxs-lookup"><span data-stu-id="94d22-114">In other words, they are warned if they try to take more than a full day off on any given date.</span></span>

<span data-ttu-id="94d22-115">Questa convalida è sempre attivata.</span><span class="sxs-lookup"><span data-stu-id="94d22-115">This validation is always turned on.</span></span> <span data-ttu-id="94d22-116">Ogni volta che i dipendenti superano la soglia della giornata definita, ricevono un messaggio di avviso nella richiesta di permesso.</span><span class="sxs-lookup"><span data-stu-id="94d22-116">Any time that employees exceed the day threshold that is defined, they receive a warning in their time-off request.</span></span>

## <a name="additional-fields-for-conditional-statements-in-workflows"></a><span data-ttu-id="94d22-117">Campi aggiuntivi per istruzioni condizionali nei flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="94d22-117">Additional fields for conditional statements in workflows</span></span>

<span data-ttu-id="94d22-118">Sono stati aggiunti altri campi alle istruzioni condizionali e ai segnaposto per vari flussi di lavoro in Core HR.</span><span class="sxs-lookup"><span data-stu-id="94d22-118">Additional fields have been added to conditional statements and placeholders for several workflows in Core HR.</span></span>

<span data-ttu-id="94d22-119">Sono stati aggiunti i campi seguenti ai flussi di lavoro di retribuzione, fine rapporto e trasferimento:</span><span class="sxs-lookup"><span data-stu-id="94d22-119">The following fields have been added to the compensation, termination, and transfer workflows:</span></span>

- <span data-ttu-id="94d22-120">EmploymentType</span><span class="sxs-lookup"><span data-stu-id="94d22-120">EmploymentType</span></span>
- <span data-ttu-id="94d22-121">LegalEntity</span><span class="sxs-lookup"><span data-stu-id="94d22-121">LegalEntity</span></span>
- <span data-ttu-id="94d22-122">AdjustedWorkerStartDate</span><span class="sxs-lookup"><span data-stu-id="94d22-122">AdjustedWorkerStartDate</span></span>
- <span data-ttu-id="94d22-123">EmployerNoticeAmount</span><span class="sxs-lookup"><span data-stu-id="94d22-123">EmployerNoticeAmount</span></span>
- <span data-ttu-id="94d22-124">EmployerUnitOfNotice</span><span class="sxs-lookup"><span data-stu-id="94d22-124">EmployerUnitOfNotice</span></span>
- <span data-ttu-id="94d22-125">TransitionDate</span><span class="sxs-lookup"><span data-stu-id="94d22-125">TransitionDate</span></span>
- <span data-ttu-id="94d22-126">WorkerNoticeAmount</span><span class="sxs-lookup"><span data-stu-id="94d22-126">WorkerNoticeAmount</span></span>
- <span data-ttu-id="94d22-127">WorkerStartDate</span><span class="sxs-lookup"><span data-stu-id="94d22-127">WorkerStartDate</span></span>
- <span data-ttu-id="94d22-128">WorkerUnitOfNotice</span><span class="sxs-lookup"><span data-stu-id="94d22-128">WorkerUnitOfNotice</span></span>
- <span data-ttu-id="94d22-129">ProbationEndDate</span><span class="sxs-lookup"><span data-stu-id="94d22-129">ProbationEndDate</span></span>
- <span data-ttu-id="94d22-130">Posizione</span><span class="sxs-lookup"><span data-stu-id="94d22-130">Position</span></span>
- <span data-ttu-id="94d22-131">Sindacato</span><span class="sxs-lookup"><span data-stu-id="94d22-131">Union</span></span>
- <span data-ttu-id="94d22-132">Reparto</span><span class="sxs-lookup"><span data-stu-id="94d22-132">Department</span></span>
- <span data-ttu-id="94d22-133">PositionType</span><span class="sxs-lookup"><span data-stu-id="94d22-133">PositionType</span></span>
- <span data-ttu-id="94d22-134">CompLocation</span><span class="sxs-lookup"><span data-stu-id="94d22-134">CompLocation</span></span>
- <span data-ttu-id="94d22-135">Funzione</span><span class="sxs-lookup"><span data-stu-id="94d22-135">Title</span></span>
- <span data-ttu-id="94d22-136">Mansione</span><span class="sxs-lookup"><span data-stu-id="94d22-136">Job</span></span>
- <span data-ttu-id="94d22-137">JobType</span><span class="sxs-lookup"><span data-stu-id="94d22-137">JobType</span></span>
- <span data-ttu-id="94d22-138">JobFamily</span><span class="sxs-lookup"><span data-stu-id="94d22-138">JobFamily</span></span>
- <span data-ttu-id="94d22-139">JobFunction</span><span class="sxs-lookup"><span data-stu-id="94d22-139">JobFunction</span></span>

<span data-ttu-id="94d22-140">Sono stati aggiunti i campi seguenti al flusso di lavoro posizione:</span><span class="sxs-lookup"><span data-stu-id="94d22-140">The following fields have been added to the position workflow:</span></span>

- <span data-ttu-id="94d22-141">Posizione</span><span class="sxs-lookup"><span data-stu-id="94d22-141">Position</span></span>
- <span data-ttu-id="94d22-142">Sindacato</span><span class="sxs-lookup"><span data-stu-id="94d22-142">Union</span></span>
- <span data-ttu-id="94d22-143">Reparto</span><span class="sxs-lookup"><span data-stu-id="94d22-143">Department</span></span>
- <span data-ttu-id="94d22-144">PositionType</span><span class="sxs-lookup"><span data-stu-id="94d22-144">PositionType</span></span>
- <span data-ttu-id="94d22-145">CompLocation</span><span class="sxs-lookup"><span data-stu-id="94d22-145">CompLocation</span></span>
- <span data-ttu-id="94d22-146">Funzione</span><span class="sxs-lookup"><span data-stu-id="94d22-146">Title</span></span>
- <span data-ttu-id="94d22-147">Mansione</span><span class="sxs-lookup"><span data-stu-id="94d22-147">Job</span></span>
- <span data-ttu-id="94d22-148">JobType</span><span class="sxs-lookup"><span data-stu-id="94d22-148">JobType</span></span>
- <span data-ttu-id="94d22-149">JobFamily</span><span class="sxs-lookup"><span data-stu-id="94d22-149">JobFamily</span></span>
- <span data-ttu-id="94d22-150">JobFunction</span><span class="sxs-lookup"><span data-stu-id="94d22-150">JobFunction</span></span>

<span data-ttu-id="94d22-151">I campi nelle istruzioni condizionali e nei segnaposto sono disponibili a tutti gli utenti che hanno accesso per configurare i flussi di lavoro sopra menzionati.</span><span class="sxs-lookup"><span data-stu-id="94d22-151">Fields in conditional statements and placeholders are available to all users who have access to configure the previously mentioned workflows.</span></span>

## <a name="navigation-to-attract-from-personnel-management"></a><span data-ttu-id="94d22-152">Passaggio ad Attract dalla gestione del personale</span><span class="sxs-lookup"><span data-stu-id="94d22-152">Navigation to Attract from personnel management</span></span>

<span data-ttu-id="94d22-153">Nella gestione del personale, se Attract non è stato installato, la sezione **Candidati da assumere** indirizza gli utenti a un'introduzione di Attract invece di visualizzare il messaggio "Nessun elemento da visualizzare."</span><span class="sxs-lookup"><span data-stu-id="94d22-153">In personnel management, if Attract hasn't been set up, the **Candidates to hire** section directs users to get started with Attract instead of showing the message, "We didn't find anything to show here."</span></span>

## <a name="other-changes"></a><span data-ttu-id="94d22-154">Altre modifiche</span><span class="sxs-lookup"><span data-stu-id="94d22-154">Other changes</span></span>

<span data-ttu-id="94d22-155">In questa versione sono incluse altre correzioni di bug:</span><span class="sxs-lookup"><span data-stu-id="94d22-155">This release includes several additional bug fixes:</span></span>

- <span data-ttu-id="94d22-156">Quando viene assunto un terzista, la scheda **Retribuzione** non deve essere disponibile nella pagina azione di richiesta.</span><span class="sxs-lookup"><span data-stu-id="94d22-156">When a contractor is hired, the **Compensation** tab should not be available on the request/action page.</span></span>
- <span data-ttu-id="94d22-157">Durante il processo di richiesta di fine rapporto, non è possibile continuare fino a quanto non sono stati completati tutti i campi obbligatori.</span><span class="sxs-lookup"><span data-stu-id="94d22-157">During the request termination process, you can't continue until all required fields contain data.</span></span>
- <span data-ttu-id="94d22-158">Sono stati risolti i problemi relativi all'ordinamento e alla visualizzazione delle date nell'analisi della gestione del personale.</span><span class="sxs-lookup"><span data-stu-id="94d22-158">Sort order and date display issues on the Personnel management analytics have been addressed.</span></span>
