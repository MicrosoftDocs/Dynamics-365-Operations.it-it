---
title: Panoramica di gestione dei benefit
description: Panoramica della funzionalità di Gestione benefit in Dynamics 365 Human Resources. Offrire opzioni di benefit estese ai propri dipendenti con un'esperienza online di facile utilizzo.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
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
ms.openlocfilehash: 91a4425b4f020f90843bb3b0b280b7ee28463670
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2020
ms.locfileid: "3230156"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="caf97-104">Panoramica di Gestione benefit</span><span class="sxs-lookup"><span data-stu-id="caf97-104">Benefits management overview</span></span>

<span data-ttu-id="caf97-105">Per rimanere competitivi, è necessario offrire una ricca gamma di benefit per attirare e trattenere i migliori dipendenti.</span><span class="sxs-lookup"><span data-stu-id="caf97-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="caf97-106">Oltre ai benefit standard come la copertura medica e dentale, è possibile che si voglia offrire anche servizi estesi come assistenza all'adozione, programmi ricreativi e indennità per l'abbigliamento.</span><span class="sxs-lookup"><span data-stu-id="caf97-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="caf97-107">Gestione benefit in Microsoft Dynamics 365 Human Resources fornisce una soluzione flessibile che supporta una vasta gamma di opzioni di benefit.</span><span class="sxs-lookup"><span data-stu-id="caf97-107">Benefits management in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="caf97-108">Human Resources include anche un'esperienza per i dipendenti di facile utilizzo che evidenzia le offerte proposte.</span><span class="sxs-lookup"><span data-stu-id="caf97-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="caf97-109">I piani di benefit avanzati consentono di creare e gestire piani di benefit unici e supportare tabelle di tassi di benefit complesse e livelli nidificati.</span><span class="sxs-lookup"><span data-stu-id="caf97-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="caf97-110">È possibile creare facilmente programmi di benefit, pacchetti e regole di iscrizione automatica per un'esperienza per i dipendenti più semplice.</span><span class="sxs-lookup"><span data-stu-id="caf97-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="caf97-111">I programmi di crediti flessibili consentono una ripartizione per supportare il pensionamento e altri eventi della vita.</span><span class="sxs-lookup"><span data-stu-id="caf97-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="caf97-112">Le regole di idoneità estese consentono di rendere disponibili i benefit appropriati per i dipendenti appropriati.</span><span class="sxs-lookup"><span data-stu-id="caf97-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="caf97-113">L'iscrizione online ai benefit fornisce un'esperienza semplice per i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="caf97-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="caf97-114">L'elaborazione di eventi reali qualificati supporta eventi reali futuri.</span><span class="sxs-lookup"><span data-stu-id="caf97-114">Qualified life event processing supports future life events.</span></span>

<span data-ttu-id="caf97-115">Se si desidera accedere ai dati dimostrativi, sarà necessario ridistribuire l'ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="caf97-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

## <a name="benefits-management-known-issues"></a><span data-ttu-id="caf97-116">Problemi noti di Gestione benefit</span><span class="sxs-lookup"><span data-stu-id="caf97-116">Benefits management known issues</span></span>

### <a name="flex-credit-programs"></a><span data-ttu-id="caf97-117">Programmi di crediti flessibili</span><span class="sxs-lookup"><span data-stu-id="caf97-117">Flex credit programs</span></span>

<span data-ttu-id="caf97-118">Il valore di credito totale definito per un programma di credito flessibile non viene visualizzato nel modulo **Piani di benefit lavoratori**.</span><span class="sxs-lookup"><span data-stu-id="caf97-118">The total credit value defined for a flex credit program doesn't display in the **Worker benefit plans** form.</span></span> <span data-ttu-id="caf97-119">Inoltre, se si imposta un programma di credito flessibile con la regola di proroga impostata su **Nessuna**, viene visualizzato un errore nel modulo **Piano di benefit lavoratori** durante la selezione e la conferma dei piani.</span><span class="sxs-lookup"><span data-stu-id="caf97-119">Also, if you set a flex credit program to have a proration rule of **None**, you get an error in the **Worker benefit plan** form when selecting and confirming plans.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="caf97-120">Abilitare Gestione benefit</span><span class="sxs-lookup"><span data-stu-id="caf97-120">Enable Benefits management</span></span>

<span data-ttu-id="caf97-121">In questo articolo viene descritto come attivare le funzionalità in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="caf97-121">This article describes how to turn on features in Human Resources.</span></span> <span data-ttu-id="caf97-122">Indica anche quali funzionalità esistenti in Human Resources sono sostituite da Gestione benefit o vengono disattivate in seguito all'attivazione di Gestione benefit.</span><span class="sxs-lookup"><span data-stu-id="caf97-122">It also tells which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="caf97-123">Dopo aver abilitato Gestione benefit in un ambiente di **Produzione** non è possibile disabilitarlo.</span><span class="sxs-lookup"><span data-stu-id="caf97-123">After you enable Benefits management in a **Production** environment, you can't disable it.</span></span> <span data-ttu-id="caf97-124">Si consiglia di abilitare e testare Gestione benefit in un ambiente **sandbox** prima di abilitarlo in un ambiente di **Produzione**.</span><span class="sxs-lookup"><span data-stu-id="caf97-124">We recommend enabling and testing Benefits management in a **Sandbox** environment before enabling it in a **Production** environment.</span></span> <span data-ttu-id="caf97-125">Sono presenti differenze significative tra la funzionalità dei benefit legacy e la nuova funzionalità di Gestione benefit che richiedono una configurazione aggiuntiva e devono essere testati prima di essere messi in produzione.</span><span class="sxs-lookup"><span data-stu-id="caf97-125">There are significant differences between the legacy Benefit functionality and new Benefits management functionality that require additional setup and should be tested prior to being placed into production.</span></span>

- [<span data-ttu-id="caf97-126">Gestire le funzionalità</span><span class="sxs-lookup"><span data-stu-id="caf97-126">Manage features</span></span>](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a><span data-ttu-id="caf97-127">Configurare le informazioni sui dipendenti</span><span class="sxs-lookup"><span data-stu-id="caf97-127">Configure employee information</span></span>

<span data-ttu-id="caf97-128">Prima di poter iscrivere dipendenti nei benefit, è necessario fornire le informazioni richieste.</span><span class="sxs-lookup"><span data-stu-id="caf97-128">Before you can enroll employees in benefits, you must provide required information.</span></span> <span data-ttu-id="caf97-129">È necessario iscrivere un dipendente al **Piano di retribuzione fissa** alla data di inizio ed è necessario selezionare una **frequenza di pagamento dei benefit** nel campo **Dettagli impiego** del modulo **Lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="caf97-129">You must enroll an employee in a **Fixed compensation plan** on their start date, and you must select a **Benefit pay frequency** in **Employment details** on the **Worker** form.</span></span>

<span data-ttu-id="caf97-130">Quando si crea un piano di benefit che utilizza tariffe basate sul genere o sull'età, è necessario immettere una data di nascita e un genere affinché il dipendente possa calcolare il costo del benefit.</span><span class="sxs-lookup"><span data-stu-id="caf97-130">When you create a benefit plan that uses rates that are based on gender or age, you must enter a birth date and gender for the employee to calculate the benefit cost.</span></span>

## <a name="configure-benefits-management"></a><span data-ttu-id="caf97-131">Configurare la gestione dei benefit</span><span class="sxs-lookup"><span data-stu-id="caf97-131">Configure Benefits management</span></span>

<span data-ttu-id="caf97-132">Prima di poter creare piani di benefit per i dipendenti, è necessario configurare le opzioni per i piani.</span><span class="sxs-lookup"><span data-stu-id="caf97-132">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="caf97-133">Impostare i parametri di Gestione benefit</span><span class="sxs-lookup"><span data-stu-id="caf97-133">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="caf97-134">Configurare le regole e le opzioni di idoneità</span><span class="sxs-lookup"><span data-stu-id="caf97-134">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="caf97-135">Configurare le opzioni di idoneità del contatto personale</span><span class="sxs-lookup"><span data-stu-id="caf97-135">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="caf97-136">Creare opzioni di copertura</span><span class="sxs-lookup"><span data-stu-id="caf97-136">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="caf97-137">Impostare le frequenze pagamenti</span><span class="sxs-lookup"><span data-stu-id="caf97-137">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="caf97-138">Configurare i tipi di eventi reali</span><span class="sxs-lookup"><span data-stu-id="caf97-138">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="caf97-139">Creare i tipi di piano</span><span class="sxs-lookup"><span data-stu-id="caf97-139">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="caf97-140">Impostare i codici causale</span><span class="sxs-lookup"><span data-stu-id="caf97-140">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="caf97-141">Impostare i codici livello</span><span class="sxs-lookup"><span data-stu-id="caf97-141">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="caf97-142">Configurare le tariffe</span><span class="sxs-lookup"><span data-stu-id="caf97-142">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="caf97-143">Configurare le detrazioni</span><span class="sxs-lookup"><span data-stu-id="caf97-143">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="caf97-144">Configurare i giorni di attesa</span><span class="sxs-lookup"><span data-stu-id="caf97-144">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="caf97-145">Configurare i periodi di attesa</span><span class="sxs-lookup"><span data-stu-id="caf97-145">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="caf97-146">Impostare le regole di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="caf97-146">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="caf97-147">Creare le categorie di impiego</span><span class="sxs-lookup"><span data-stu-id="caf97-147">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="caf97-148">Impostare i tipi di impieghi</span><span class="sxs-lookup"><span data-stu-id="caf97-148">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="caf97-149">Configurare Dipendente self-service</span><span class="sxs-lookup"><span data-stu-id="caf97-149">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="caf97-150">Creare piani di benefit</span><span class="sxs-lookup"><span data-stu-id="caf97-150">Create benefit plans</span></span>

<span data-ttu-id="caf97-151">Questi articoli mostrano come creare piani di benefit, inclusi pacchetti e programmi di crediti flessibili.</span><span class="sxs-lookup"><span data-stu-id="caf97-151">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="caf97-152">Impostare i piani di benefit</span><span class="sxs-lookup"><span data-stu-id="caf97-152">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="caf97-153">Impostare i programmi di credito flessibile</span><span class="sxs-lookup"><span data-stu-id="caf97-153">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="caf97-154">Elaborare i piani di benefit</span><span class="sxs-lookup"><span data-stu-id="caf97-154">Process benefit plans</span></span>

<span data-ttu-id="caf97-155">È necessario elaborare alcune delle modifiche per renderle attive.</span><span class="sxs-lookup"><span data-stu-id="caf97-155">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="caf97-156">Elaborare l'idoneità di iscrizione</span><span class="sxs-lookup"><span data-stu-id="caf97-156">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="caf97-157">Elaborare eventi reali</span><span class="sxs-lookup"><span data-stu-id="caf97-157">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="caf97-158">Elaborare le modifiche a eventi reali</span><span class="sxs-lookup"><span data-stu-id="caf97-158">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="caf97-159">Elaborare l'idoneità a eventi reali</span><span class="sxs-lookup"><span data-stu-id="caf97-159">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="caf97-160">Elaborare modifiche ai tassi</span><span class="sxs-lookup"><span data-stu-id="caf97-160">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

