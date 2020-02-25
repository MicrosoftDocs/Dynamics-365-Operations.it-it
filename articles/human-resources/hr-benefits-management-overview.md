---
title: Panoramica di Gestione benefit
description: Panoramica della funzionalità di anteprima Gestione benefit in Dynamics 365 Human Resources. Offrire opzioni di benefit estese ai propri dipendenti con un'esperienza online di facile utilizzo.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63db1b55bae9150dd87d9981136b96d72ffd0c59
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029465"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="47896-104">Panoramica di Gestione benefit</span><span class="sxs-lookup"><span data-stu-id="47896-104">Benefits management overview</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="47896-105">Per rimanere competitivi, è necessario offrire una ricca gamma di benefit per attirare e trattenere i migliori dipendenti.</span><span class="sxs-lookup"><span data-stu-id="47896-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="47896-106">Oltre ai benefit standard come la copertura medica e dentale, è possibile che si voglia offrire anche servizi estesi come assistenza all'adozione, programmi ricreativi e indennità per l'abbigliamento.</span><span class="sxs-lookup"><span data-stu-id="47896-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="47896-107">La funzionalità di anteprima Gestione benefit in Microsoft Dynamics 365 Human Resources fornisce una soluzione flessibile che supporta una vasta gamma di opzioni di benefit.</span><span class="sxs-lookup"><span data-stu-id="47896-107">The Benefits management preview feature in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="47896-108">Human Resources include anche un'esperienza per i dipendenti di facile utilizzo che evidenzia le offerte proposte.</span><span class="sxs-lookup"><span data-stu-id="47896-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="47896-109">I piani di benefit avanzati consentono di creare e gestire piani di benefit unici e supportare tabelle di tassi di benefit complesse e livelli nidificati.</span><span class="sxs-lookup"><span data-stu-id="47896-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="47896-110">È possibile creare facilmente programmi di benefit, pacchetti e regole di iscrizione automatica per un'esperienza per i dipendenti più semplice.</span><span class="sxs-lookup"><span data-stu-id="47896-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="47896-111">I programmi di crediti flessibili consentono una ripartizione per supportare il pensionamento e altri eventi della vita.</span><span class="sxs-lookup"><span data-stu-id="47896-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="47896-112">Le regole di idoneità estese consentono di rendere disponibili i benefit appropriati per i dipendenti appropriati.</span><span class="sxs-lookup"><span data-stu-id="47896-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="47896-113">L'iscrizione online ai benefit fornisce un'esperienza semplice per i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="47896-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="47896-114">L'elaborazione di eventi reali qualificati si integra con Dipendente self-service e inoltre supporta eventi reali futuri.</span><span class="sxs-lookup"><span data-stu-id="47896-114">Qualified life event processing integrates with Employee self service, and also supports future life events.</span></span>

<span data-ttu-id="47896-115">Se si desidera accedere ai dati dimostrativi, sarà necessario ridistribuire l'ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="47896-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

<span data-ttu-id="47896-116">È possibile fornire un feedback diretto o segnalare problemi all'indirizzo e-mail: D365BenefitsPreview@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="47896-116">You can provide direct feedback or report issues to:  D365BenefitsPreview@microsoft.com.</span></span>

## <a name="benefits-management-known-issues"></a><span data-ttu-id="47896-117">Problemi noti di Gestione benefit</span><span class="sxs-lookup"><span data-stu-id="47896-117">Benefits management known issues</span></span>

### <a name="eligibility-processing"></a><span data-ttu-id="47896-118">Elaborazione dell'idoneità</span><span class="sxs-lookup"><span data-stu-id="47896-118">Eligibility processing</span></span>

<span data-ttu-id="47896-119">Quando si esegue l'idoneità per benefit che utilizzano un importo di copertura 1-5X stipendio, % di stipendio e Importo forfettario, è necessario impostare la data di **Dettagli del benefit** su **Data di inizio del dipendente** in **Storico esperienze lavorative**.</span><span class="sxs-lookup"><span data-stu-id="47896-119">When running eligibility for benefits that use a 1-5X Salary, % of Salary, and Flat Amount coverage amount, you must set the **Benefit details** date to the **Employee start date** in **Employment history**.</span></span> <span data-ttu-id="47896-120">È anche necessario includere **Ore lavorate**, **Frequenza pagamenti** e **Importo retribuzione benefit annuale**.</span><span class="sxs-lookup"><span data-stu-id="47896-120">You must also include **Hours worked**, **Payment frequency**, and **Annual benefits salary amount**.</span></span> <span data-ttu-id="47896-121">Se il lavoratore ha una retribuzione fissa, immettere un valore in **Ore lavorate** e **Frequenza pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="47896-121">If the worker has fixed compensation, enter **Hours worked** and **Payment frequency**.</span></span> <span data-ttu-id="47896-122">L'importo della retribuzione annuale verrà calcolato.</span><span class="sxs-lookup"><span data-stu-id="47896-122">The annual salary amount will calculate.</span></span> <span data-ttu-id="47896-123">Se il dipendente è stipendiato, non è necessario specificare **Ore lavorate**.</span><span class="sxs-lookup"><span data-stu-id="47896-123">If the employee is salaried, you don't need to enter **Hours worked**.</span></span> <span data-ttu-id="47896-124">Quando si creano nuovi lavoratori, si consiglia di immettere prima la retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="47896-124">We recommend that when creating new workers, enter fixed compensation first.</span></span> <span data-ttu-id="47896-125">Per aggiornare il record dei dettagli del benefit, selezionare **Lavoratore > Storico lavoratore > Dettagli impiego**.</span><span class="sxs-lookup"><span data-stu-id="47896-125">To update the benefit details record, navigate to **Worker > Worker history > Employment details**.</span></span> <span data-ttu-id="47896-126">Modificare la data in base alla data di inizio del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="47896-126">Adjust the date to the worker's start date.</span></span>

### <a name="employee-self-service"></a><span data-ttu-id="47896-127">Dipendente self-service</span><span class="sxs-lookup"><span data-stu-id="47896-127">Employee self-service</span></span>

<span data-ttu-id="47896-128">L'importo del dipendente non viene calcolato durante l'aggiornamento dell'importo della copertura per l'assicurazione sulla vita.</span><span class="sxs-lookup"><span data-stu-id="47896-128">Employee amount doesn't calculate when updating the coverage amount for life insurance.</span></span> <span data-ttu-id="47896-129">Ad esempio, quando a un dipendente viene offerto un piano di assicurazione sulla vita, può selezionare fino a $50.000 in copertura al costo di $ 0,36 per $1.000 di copertura.</span><span class="sxs-lookup"><span data-stu-id="47896-129">For example, when an employee is offered a life insurance plan, they can select up to $50,000 in coverage at a cost of $.36 per $1,000 of coverage.</span></span>  <span data-ttu-id="47896-130">Quando il dipendente aggiorna l'importo della copertura, il costo associato del dipendente rimane a zero.</span><span class="sxs-lookup"><span data-stu-id="47896-130">When the employee updates the coverage amount, the employee’s associated cost remains at zero.</span></span>

<span data-ttu-id="47896-131">Per un piano di benefit che consente una sola selezione di quel tipo di piano, l'utente riceve un errore se tenta di rinunciare a un piano dopo aver selezionato un piano.</span><span class="sxs-lookup"><span data-stu-id="47896-131">For a benefit plan that only allows a single selection of that plan type, the user receives an error if they attempt to waive a plan after selecting a plan.</span></span> <span data-ttu-id="47896-132">Ad esempio, un utente seleziona un piano sanitario e lo inserisce nel carrello.</span><span class="sxs-lookup"><span data-stu-id="47896-132">For example, a user selects a medical plan and places it in their cart.</span></span> <span data-ttu-id="47896-133">L'utente quindi seleziona **Rinuncia** per un altro piano sanitario.</span><span class="sxs-lookup"><span data-stu-id="47896-133">The user then selects **Waive** for another medical plan.</span></span> <span data-ttu-id="47896-134">L'utente riceverà un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="47896-134">The user will receive an error.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="47896-135">Abilitare Gestione benefit</span><span class="sxs-lookup"><span data-stu-id="47896-135">Enable Benefits management</span></span>

<span data-ttu-id="47896-136">Gestione benefit è una funzionalità di anteprima ed è disponibile solo in ambienti **sandbox**.</span><span class="sxs-lookup"><span data-stu-id="47896-136">Benefits management is a preview feature, and is only available in **Sandbox** environments.</span></span> <span data-ttu-id="47896-137">Questi articoli descrivono come attivare le funzionalità di anteprima in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="47896-137">These articles describe how to turn on preview features in Human Resources.</span></span> <span data-ttu-id="47896-138">Indicano inoltre quali funzionalità esistenti in Human Resources sono sostituite da Gestione benefit o vengono disattivate in seguito all'attivazione di Gestione benefit.</span><span class="sxs-lookup"><span data-stu-id="47896-138">They also tell which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

- [<span data-ttu-id="47896-139">Gestire le funzionalità</span><span class="sxs-lookup"><span data-stu-id="47896-139">Manage features</span></span>](hr-admin-manage-features.md)
- [<span data-ttu-id="47896-140">Funzionalità di anteprima: Gestione benefit</span><span class="sxs-lookup"><span data-stu-id="47896-140">Preview feature: Benefits management</span></span>](hr-admin-manage-features.md?preview-feature-benefits-management)

## <a name="configure-benefits-management"></a><span data-ttu-id="47896-141">Configurare Gestione benefit</span><span class="sxs-lookup"><span data-stu-id="47896-141">Configure Benefits management</span></span>

<span data-ttu-id="47896-142">Prima di poter creare piani di benefit per i dipendenti, è necessario configurare le opzioni per i piani.</span><span class="sxs-lookup"><span data-stu-id="47896-142">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="47896-143">Impostare i parametri di Gestione benefit</span><span class="sxs-lookup"><span data-stu-id="47896-143">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="47896-144">Configurare le regole e le opzioni di idoneità</span><span class="sxs-lookup"><span data-stu-id="47896-144">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="47896-145">Configurare opzioni di idoneità per contatti personali</span><span class="sxs-lookup"><span data-stu-id="47896-145">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="47896-146">Creare opzioni di copertura</span><span class="sxs-lookup"><span data-stu-id="47896-146">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="47896-147">Impostare frequenze di pagamento</span><span class="sxs-lookup"><span data-stu-id="47896-147">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="47896-148">Configurare tipi di eventi reali</span><span class="sxs-lookup"><span data-stu-id="47896-148">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="47896-149">Creare tipi di piani</span><span class="sxs-lookup"><span data-stu-id="47896-149">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="47896-150">Imposta i codici causale</span><span class="sxs-lookup"><span data-stu-id="47896-150">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="47896-151">Impostare codici di livello</span><span class="sxs-lookup"><span data-stu-id="47896-151">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="47896-152">Configurare i tassi</span><span class="sxs-lookup"><span data-stu-id="47896-152">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="47896-153">Configurare le detrazioni</span><span class="sxs-lookup"><span data-stu-id="47896-153">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="47896-154">Configurare giorni di attesa</span><span class="sxs-lookup"><span data-stu-id="47896-154">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="47896-155">Configurare periodi di attesa</span><span class="sxs-lookup"><span data-stu-id="47896-155">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="47896-156">Impostare regole di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="47896-156">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="47896-157">Crea categorie di impieghi</span><span class="sxs-lookup"><span data-stu-id="47896-157">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="47896-158">Impostare i tipi di impieghi</span><span class="sxs-lookup"><span data-stu-id="47896-158">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="47896-159">Configurare Dipendente self-service</span><span class="sxs-lookup"><span data-stu-id="47896-159">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="47896-160">Creare piani di benefit</span><span class="sxs-lookup"><span data-stu-id="47896-160">Create benefit plans</span></span>

<span data-ttu-id="47896-161">Questi articoli mostrano come creare piani di benefit, inclusi pacchetti e programmi di crediti flessibili.</span><span class="sxs-lookup"><span data-stu-id="47896-161">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="47896-162">Impostare piani di benefit</span><span class="sxs-lookup"><span data-stu-id="47896-162">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="47896-163">Creare piani di benefit per i lavoratori</span><span class="sxs-lookup"><span data-stu-id="47896-163">Create worker benefit plans</span></span>](hr-benefits-plans-worker.md)
- [<span data-ttu-id="47896-164">Impostare programmi di crediti flessibili</span><span class="sxs-lookup"><span data-stu-id="47896-164">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)
- [<span data-ttu-id="47896-165">Configurare eventi reali futuri</span><span class="sxs-lookup"><span data-stu-id="47896-165">Configure future life events</span></span>](hr-benefits-plans-future-life-events.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="47896-166">Elaborare piani di benefit</span><span class="sxs-lookup"><span data-stu-id="47896-166">Process benefit plans</span></span>

<span data-ttu-id="47896-167">È necessario elaborare alcune delle modifiche per renderle attive.</span><span class="sxs-lookup"><span data-stu-id="47896-167">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="47896-168">Elaborare l'idoneità di iscrizione</span><span class="sxs-lookup"><span data-stu-id="47896-168">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="47896-169">Elaborare eventi reali</span><span class="sxs-lookup"><span data-stu-id="47896-169">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="47896-170">Elaborare le modifiche a eventi reali</span><span class="sxs-lookup"><span data-stu-id="47896-170">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="47896-171">Elaborare l'idoneità a eventi reali</span><span class="sxs-lookup"><span data-stu-id="47896-171">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="47896-172">Elaborare modifiche ai tassi</span><span class="sxs-lookup"><span data-stu-id="47896-172">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

