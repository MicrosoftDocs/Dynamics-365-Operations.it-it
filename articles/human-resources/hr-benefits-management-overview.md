---
title: Panoramica di gestione dei benefit
description: Panoramica della funzionalità di Gestione benefit in Dynamics 365 Human Resources. Offrire opzioni di benefit estese ai propri dipendenti con un'esperienza online di facile utilizzo.
author: andreabichsel
manager: tfehr
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4ae4270f3185f8795753ecdb209515ecd6e86486
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113155"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="e9227-104">Panoramica di Gestione benefit</span><span class="sxs-lookup"><span data-stu-id="e9227-104">Benefits management overview</span></span>

<span data-ttu-id="e9227-105">Per rimanere competitivi, è necessario offrire una ricca gamma di benefit per attirare e trattenere i migliori dipendenti.</span><span class="sxs-lookup"><span data-stu-id="e9227-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="e9227-106">Oltre ai benefit standard come la copertura medica e dentale, è possibile che si voglia offrire anche servizi estesi come assistenza all'adozione, programmi ricreativi e indennità per l'abbigliamento.</span><span class="sxs-lookup"><span data-stu-id="e9227-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="e9227-107">Gestione benefit in Microsoft Dynamics 365 Human Resources fornisce una soluzione flessibile che supporta una vasta gamma di opzioni di benefit.</span><span class="sxs-lookup"><span data-stu-id="e9227-107">Benefits management in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="e9227-108">Human Resources include anche un'esperienza per i dipendenti di facile utilizzo che evidenzia le offerte proposte.</span><span class="sxs-lookup"><span data-stu-id="e9227-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="e9227-109">I piani di benefit avanzati consentono di creare e gestire piani di benefit unici e supportare tabelle di tassi di benefit complesse e livelli nidificati.</span><span class="sxs-lookup"><span data-stu-id="e9227-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="e9227-110">È possibile creare facilmente programmi di benefit, pacchetti e regole di iscrizione automatica per un'esperienza per i dipendenti più semplice.</span><span class="sxs-lookup"><span data-stu-id="e9227-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="e9227-111">I programmi di crediti flessibili consentono una ripartizione per supportare il pensionamento e altri eventi della vita.</span><span class="sxs-lookup"><span data-stu-id="e9227-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="e9227-112">Le regole di idoneità estese consentono di rendere disponibili i benefit appropriati per i dipendenti appropriati.</span><span class="sxs-lookup"><span data-stu-id="e9227-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="e9227-113">L'iscrizione online ai benefit fornisce un'esperienza semplice per i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="e9227-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="e9227-114">L'elaborazione di eventi reali qualificati supporta eventi reali futuri.</span><span class="sxs-lookup"><span data-stu-id="e9227-114">Qualified life event processing supports future life events.</span></span>

<span data-ttu-id="e9227-115">Se si desidera accedere ai dati dimostrativi, sarà necessario ridistribuire l'ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="e9227-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="e9227-116">Abilitare Gestione benefit</span><span class="sxs-lookup"><span data-stu-id="e9227-116">Enable Benefits management</span></span>

<span data-ttu-id="e9227-117">In questo argomento viene descritto come attivare le funzionalità in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e9227-117">This topic describes how to turn on features in Human Resources.</span></span> <span data-ttu-id="e9227-118">Indica anche quali funzionalità esistenti in Human Resources sono sostituite da Gestione benefit o vengono disattivate in seguito all'attivazione di Gestione benefit.</span><span class="sxs-lookup"><span data-stu-id="e9227-118">It also tells which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9227-119">Dopo aver abilitato Gestione benefit in un ambiente di **Produzione** non è possibile disabilitarlo.</span><span class="sxs-lookup"><span data-stu-id="e9227-119">After you enable Benefits management in a **Production** environment, you can't disable it.</span></span> <span data-ttu-id="e9227-120">Si consiglia di abilitare e testare Gestione benefit in un ambiente **sandbox** prima di abilitarlo in un ambiente di **Produzione**.</span><span class="sxs-lookup"><span data-stu-id="e9227-120">We recommend enabling and testing Benefits management in a **Sandbox** environment before enabling it in a **Production** environment.</span></span> <span data-ttu-id="e9227-121">Sono presenti differenze significative tra la funzionalità dei benefit legacy e la nuova funzionalità di Gestione benefit che richiedono una configurazione aggiuntiva e devono essere testati prima di essere messi in produzione.</span><span class="sxs-lookup"><span data-stu-id="e9227-121">There are significant differences between the legacy Benefit functionality and new Benefits management functionality that require additional setup and should be tested prior to being placed into production.</span></span>

- [<span data-ttu-id="e9227-122">Gestire le funzionalità</span><span class="sxs-lookup"><span data-stu-id="e9227-122">Manage features</span></span>](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a><span data-ttu-id="e9227-123">Configurare le informazioni sui dipendenti</span><span class="sxs-lookup"><span data-stu-id="e9227-123">Configure employee information</span></span>

<span data-ttu-id="e9227-124">Prima di poter iscrivere dipendenti nei benefit, è necessario fornire le informazioni richieste.</span><span class="sxs-lookup"><span data-stu-id="e9227-124">Before you can enroll employees in benefits, you must provide required information.</span></span> <span data-ttu-id="e9227-125">È necessario iscrivere un dipendente al **Piano di retribuzione fissa** alla data di inizio ed è necessario selezionare una **frequenza di pagamento dei benefit** nel campo **Dettagli impiego** del modulo **Lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="e9227-125">You must enroll an employee in a **Fixed compensation plan** on their start date, and you must select a **Benefit pay frequency** in **Employment details** on the **Worker** form.</span></span>

<span data-ttu-id="e9227-126">Se un dipendente riceve un compenso supplementare come le commissioni, è possibile aggiungere un importo **Retribuzione annuale benefit** dal record dipendente.</span><span class="sxs-lookup"><span data-stu-id="e9227-126">If you have an employee who receives supplemental compensation like commissions, you can add a **Benefits annual salary** amount from the employee record.</span></span> <span data-ttu-id="e9227-127">Le risorse umane useranno l'importo **Retribuzione annuale benefit** nel determinare gli importi di copertura, anziché l'importo annuale di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="e9227-127">Human Resources will use the **Benefits annual salary** amount when determining coverage amounts, instead of the fixed compensation annual amount.</span></span> <span data-ttu-id="e9227-128">La **Retribuzione annuale benefit** deve essere valida a partire dalla data di inizio dell'impiegato o di quella del periodo di benefit, a seconda di quale è più recente.</span><span class="sxs-lookup"><span data-stu-id="e9227-128">The **Benefits annual salary** must be valid as of the employee’s start date or the beginning of the benefit period, whichever is latest.</span></span> <span data-ttu-id="e9227-129">Se per un dipendente viene registrato sia una retribuzione fissa sia un importo di retribuzione annuale benefit, la retribuzione annuale benefit sarà utilizzata per determinare gli importi della copertura.</span><span class="sxs-lookup"><span data-stu-id="e9227-129">If both a fixed compensation and benefits annual salary amount is recorded for an employee, the benefits annual salary will be used in determining coverage amounts.</span></span>

<span data-ttu-id="e9227-130">Quando si crea un piano di benefit che utilizza tariffe basate sul genere o sull'età, è necessario immettere una data di nascita e un genere affinché il dipendente possa calcolare il costo del benefit.</span><span class="sxs-lookup"><span data-stu-id="e9227-130">When you create a benefit plan that uses rates that are based on gender or age, you must enter a birth date and gender for the employee to calculate the benefit cost.</span></span>

## <a name="configure-benefits-management"></a><span data-ttu-id="e9227-131">Configurare la gestione dei benefit</span><span class="sxs-lookup"><span data-stu-id="e9227-131">Configure Benefits management</span></span>

<span data-ttu-id="e9227-132">Prima di poter creare piani di benefit per i dipendenti, è necessario configurare le opzioni per i piani.</span><span class="sxs-lookup"><span data-stu-id="e9227-132">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="e9227-133">Impostare i parametri di Gestione benefit</span><span class="sxs-lookup"><span data-stu-id="e9227-133">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="e9227-134">Configurare le regole e le opzioni di idoneità</span><span class="sxs-lookup"><span data-stu-id="e9227-134">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="e9227-135">Configurare le opzioni di idoneità del contatto personale</span><span class="sxs-lookup"><span data-stu-id="e9227-135">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="e9227-136">Creare opzioni di copertura</span><span class="sxs-lookup"><span data-stu-id="e9227-136">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="e9227-137">Impostare le frequenze pagamenti</span><span class="sxs-lookup"><span data-stu-id="e9227-137">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="e9227-138">Configurare i tipi di eventi reali</span><span class="sxs-lookup"><span data-stu-id="e9227-138">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="e9227-139">Creare i tipi di piano</span><span class="sxs-lookup"><span data-stu-id="e9227-139">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="e9227-140">Impostare i codici causale</span><span class="sxs-lookup"><span data-stu-id="e9227-140">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="e9227-141">Impostare i codici livello</span><span class="sxs-lookup"><span data-stu-id="e9227-141">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="e9227-142">Configurare le tariffe</span><span class="sxs-lookup"><span data-stu-id="e9227-142">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="e9227-143">Configurare le detrazioni</span><span class="sxs-lookup"><span data-stu-id="e9227-143">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="e9227-144">Configurare i giorni di attesa</span><span class="sxs-lookup"><span data-stu-id="e9227-144">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="e9227-145">Configurare i periodi di attesa</span><span class="sxs-lookup"><span data-stu-id="e9227-145">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="e9227-146">Impostare le regole di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="e9227-146">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="e9227-147">Creare le categorie di impiego</span><span class="sxs-lookup"><span data-stu-id="e9227-147">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="e9227-148">Impostare i tipi di impieghi</span><span class="sxs-lookup"><span data-stu-id="e9227-148">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="e9227-149">Configurare Dipendente self-service</span><span class="sxs-lookup"><span data-stu-id="e9227-149">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="e9227-150">Creare piani di benefit</span><span class="sxs-lookup"><span data-stu-id="e9227-150">Create benefit plans</span></span>

<span data-ttu-id="e9227-151">Questi articoli mostrano come creare piani di benefit, inclusi pacchetti e programmi di crediti flessibili.</span><span class="sxs-lookup"><span data-stu-id="e9227-151">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="e9227-152">Impostare i piani di benefit</span><span class="sxs-lookup"><span data-stu-id="e9227-152">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="e9227-153">Impostare i programmi di credito flessibile</span><span class="sxs-lookup"><span data-stu-id="e9227-153">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="e9227-154">Elaborare i piani di benefit</span><span class="sxs-lookup"><span data-stu-id="e9227-154">Process benefit plans</span></span>

<span data-ttu-id="e9227-155">È necessario elaborare alcune delle modifiche per renderle attive.</span><span class="sxs-lookup"><span data-stu-id="e9227-155">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="e9227-156">Elaborare l'idoneità di iscrizione</span><span class="sxs-lookup"><span data-stu-id="e9227-156">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="e9227-157">Elaborare eventi reali</span><span class="sxs-lookup"><span data-stu-id="e9227-157">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="e9227-158">Elaborare le modifiche a eventi reali</span><span class="sxs-lookup"><span data-stu-id="e9227-158">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="e9227-159">Elaborare l'idoneità a eventi reali</span><span class="sxs-lookup"><span data-stu-id="e9227-159">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="e9227-160">Elaborare modifiche ai tassi</span><span class="sxs-lookup"><span data-stu-id="e9227-160">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

