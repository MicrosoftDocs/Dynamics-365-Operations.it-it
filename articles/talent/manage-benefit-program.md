---
title: Definire e gestire un programma di benefit
description: Le risorse umane forniscono un set di strumenti che possono essere utilizzati per impostare e gestire i benefit, le detrazioni e i piani di retribuzione dei lavoratori che un'organizzazione offre o elabora per i propri lavoratori. Questo articolo fornisce le informazioni su come impostare e gestire i benefit.
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6de99fc6aea808fddbec047cc74e533c4e5f9ee9
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="define-and-manage-a-benefits-program"></a><span data-ttu-id="d2032-104">Definire e gestire un programma di benefit</span><span class="sxs-lookup"><span data-stu-id="d2032-104">Define and manage a benefits program</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="d2032-105">Le risorse umane forniscono un set di strumenti che possono essere utilizzati per impostare e gestire i benefit, le detrazioni e i piani di retribuzione dei lavoratori che un'organizzazione offre o elabora per i propri lavoratori.</span><span class="sxs-lookup"><span data-stu-id="d2032-105">Human resources provides a set of tools that can be used to set up and maintain benefits, deductions, and workers' compensation plans that an organization offers or processes for its workers.</span></span> <span data-ttu-id="d2032-106">Questo argomento fornisce le informazioni su come impostare e gestire i benefit.</span><span class="sxs-lookup"><span data-stu-id="d2032-106">This topic provides information about how to set up an manage benefits.</span></span>

<a name="benefit-setup"></a><span data-ttu-id="d2032-107">Impostazione dei benefit</span><span class="sxs-lookup"><span data-stu-id="d2032-107">Benefit setup</span></span>
-------------

<span data-ttu-id="d2032-108">Prima che i lavoratori possano essere iscritti al benefit, è necessario creare gli elementi di ogni benefit.</span><span class="sxs-lookup"><span data-stu-id="d2032-108">Before workers can be enrolled in benefits, you must create the elements of each benefit.</span></span> <span data-ttu-id="d2032-109">Questi elementi combinano piani di benefit simili e definiscono le impostazioni predefinite, ad esempio le percentuali di detrazione e i dettagli di contabilità.</span><span class="sxs-lookup"><span data-stu-id="d2032-109">These elements combine similar benefit plans and define default settings, such as deduction rates and accounting details.</span></span> <span data-ttu-id="d2032-110">Molte di queste impostazioni possono essere modificate una volta che i lavoratori sono iscritti al benefit.</span><span class="sxs-lookup"><span data-stu-id="d2032-110">Many of these settings can be adjusted when workers are later enrolled in the benefit.</span></span> <span data-ttu-id="d2032-111">Per ciascun piano di benefit, un'organizzazione può offrire più opzioni di iscrizione oppure un lavoratore può rinunciare all'iscrizione nel piano.</span><span class="sxs-lookup"><span data-stu-id="d2032-111">For each benefit plan, an organization can offer several enrollment options, or a worker can waive enrollment in the plan.</span></span> 

<span data-ttu-id="d2032-112">[![Flusso di elaborazione benefit](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)</span><span class="sxs-lookup"><span data-stu-id="d2032-112">[![Benefit process flow](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)</span></span>

## <a name="benefit-elements"></a><span data-ttu-id="d2032-113">Elementi benefit</span><span class="sxs-lookup"><span data-stu-id="d2032-113">Benefit elements</span></span>
<span data-ttu-id="d2032-114">Prima di iniziare a creare i benefit e iscrivere i lavoratori, è necessario definire gli elementi che costituiscono un benefit: il tipo, il piano e le opzioni.</span><span class="sxs-lookup"><span data-stu-id="d2032-114">Before you begin to create to create benefits and enroll workers in them, you must define the elements that make up a benefit: the type, plan, and options.</span></span>

-   <span data-ttu-id="d2032-115">**Tipo**: una raccolta di piani relativi a un benefit specifico, ad esempio assistenza sanitaria o parcheggio.</span><span class="sxs-lookup"><span data-stu-id="d2032-115">**Type** – A collection of plans for a specific benefit, such as medical or parking.</span></span>
-   <span data-ttu-id="d2032-116">**Piano**: un benefit specifico che un fornitore offre in base a un contratto.</span><span class="sxs-lookup"><span data-stu-id="d2032-116">**Plan** – A specific benefit that is contracted from a provider.</span></span>
-   <span data-ttu-id="d2032-117">**Opzione**: il livello di copertura, ad esempio per il singolo dipendente o per il dipendente e il coniuge/partner.</span><span class="sxs-lookup"><span data-stu-id="d2032-117">**Option** – The coverage level, such as employee only, or employee and spouse/partner.</span></span>

<span data-ttu-id="d2032-118">Per ogni tipo di benefit, ad esempio visivo o dentistico, un'organizzazione può offrire uno o più piani ai lavoratori.</span><span class="sxs-lookup"><span data-stu-id="d2032-118">For each type of benefit, such as vision or dental, an organization can offer one or more plans to its workers.</span></span> <span data-ttu-id="d2032-119">Per ciascun piano, l'organizzazione può offrire opzioni diverse.</span><span class="sxs-lookup"><span data-stu-id="d2032-119">For each plan, the organization can offer different options.</span></span> <span data-ttu-id="d2032-120">Ad esempio, i lavoratori possono acquistare la copertura aggiuntiva dell'assicurazione vitalizia in una, due o tre volte la retribuzione annuale.</span><span class="sxs-lookup"><span data-stu-id="d2032-120">For example, workers can buy additional term life insurance coverage at one, two, or three times their yearly salary.</span></span> <span data-ttu-id="d2032-121">Ogni combinazione di piano e di opzioni diventa un benefit a cui i lavoratori possono iscriversi.</span><span class="sxs-lookup"><span data-stu-id="d2032-121">Each combination of a plan and options becomes a benefit that workers can enroll in.</span></span> 

<span data-ttu-id="d2032-122">[![immagine benefit](./media/benefit-pic.png)](./media/benefit-pic.png)</span><span class="sxs-lookup"><span data-stu-id="d2032-122">[![benefit pic](./media/benefit-pic.png)](./media/benefit-pic.png)</span></span>

## <a name="eligibility"></a><span data-ttu-id="d2032-123">Idoneità</span><span class="sxs-lookup"><span data-stu-id="d2032-123">Eligibility</span></span>
<span data-ttu-id="d2032-124">Molti fattori determinano l'idoneità del lavoratore per diversi tipi di benefit che un datore di lavoro offre.</span><span class="sxs-lookup"><span data-stu-id="d2032-124">Many factors determine worker eligibility for the various types of benefits that an employer offers.</span></span> <span data-ttu-id="d2032-125">Quando si crea un benefit in Microsoft Talent, è possibile impostare il tipo di idoneità applicabile al benefit.</span><span class="sxs-lookup"><span data-stu-id="d2032-125">When you create a benefit in Microsoft Talent, you can set the type of eligibility that applies to that benefit.</span></span> 

<span data-ttu-id="d2032-126">È possibile mettere un benefit a disposizione di tutti i lavoratori.</span><span class="sxs-lookup"><span data-stu-id="d2032-126">You can make a benefit available to all workers.</span></span> <span data-ttu-id="d2032-127">Ad esempio, alcune aziende offrono a tutti i dipendenti il pass per il parcheggio come benefit extrasalariale.</span><span class="sxs-lookup"><span data-stu-id="d2032-127">For example, some companies offer parking passes to all employees as a fringe benefit.</span></span> <span data-ttu-id="d2032-128">Quando si crea il benefit, impostare l'idoneità su **Tutti i lavoratori sono idonei**.</span><span class="sxs-lookup"><span data-stu-id="d2032-128">When you create this benefit, you set the eligibility to **All workers are eligible**.</span></span> 

<span data-ttu-id="d2032-129">Per altri benefit, ad esempio i pignoramenti e i gettiti di un'imposta, l'idoneità non è applicabile.</span><span class="sxs-lookup"><span data-stu-id="d2032-129">For other benefits, such as garnishments and tax levies, eligibility doesn't apply.</span></span> <span data-ttu-id="d2032-130">Quando si creano questi tipi di benefit, si imposta l'idoneità su **Ignora elaborazione idoneità**.</span><span class="sxs-lookup"><span data-stu-id="d2032-130">Whey you create these types of benefits, you set the eligibility to **Bypass eligibility process**.</span></span> 

<span data-ttu-id="d2032-131">Infine, l'idoneità al benefit può essere basata su regole.</span><span class="sxs-lookup"><span data-stu-id="d2032-131">Finally, benefit eligibility can be rule-based.</span></span> <span data-ttu-id="d2032-132">Ad esempio, un'azienda offe due tipi di premio assicurativo sulla vita ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="d2032-132">For example, a company offers two types of life insurance benefit to employees.</span></span> <span data-ttu-id="d2032-133">I dipendenti esecutivi sono idonei a un piano di assicurazione sulla vita, mentre gli altri dipendenti a tempo pieno sono idonei a un altro piano di assicurazione sulla vita.</span><span class="sxs-lookup"><span data-stu-id="d2032-133">Executive employees are eligible for one life insurance plan, whereas all other full-time employees are eligible for the other life insurance plan.</span></span> <span data-ttu-id="d2032-134">In Talent, è possibile creare una regola di idoneità al benefit per individuare tutti i dipendenti esecutivi e un'altra regola per individuare tutti gli altri dipendenti a tempo pieno, quindi applicare tali regole al benefit appropriato.</span><span class="sxs-lookup"><span data-stu-id="d2032-134">In Talent, you can create a benefit eligibility rule to find all executive employees and another rule to find all other full-time employees, and then apply those rules to the appropriate benefit.</span></span>

## <a name="enrollment"></a><span data-ttu-id="d2032-135">Iscrizione</span><span class="sxs-lookup"><span data-stu-id="d2032-135">Enrollment</span></span>
<span data-ttu-id="d2032-136">Dopo aver creato i benefit che l'organizzazione offre e l'idoneità determinata, è possibile iscrivere i lavoratori al benefit.</span><span class="sxs-lookup"><span data-stu-id="d2032-136">After you've created the benefits that your organization offers and determined eligibility, you can enroll your workers in benefits.</span></span> <span data-ttu-id="d2032-137">È possibile iscrivere un singolo lavoratore ai benefit oppure è possibile iscrivere più lavoratori a uno o più benefit durante il singolo processo.</span><span class="sxs-lookup"><span data-stu-id="d2032-137">You can enroll a single worker in benefits, or you can enroll many workers in one or more benefits during a single process.</span></span> 

<span data-ttu-id="d2032-138">Talvolta, un'organizzazione smette di offrire determinati benefit.</span><span class="sxs-lookup"><span data-stu-id="d2032-138">Sometimes, an organization stops offering certain benefits.</span></span> <span data-ttu-id="d2032-139">In questo caso, è necessario aggiornare il benefit e i lavoratori che ne hanno titolo.</span><span class="sxs-lookup"><span data-stu-id="d2032-139">In this case, you must update the benefit and the workers who are enrolled in.</span></span> <span data-ttu-id="d2032-140">La scadenza dei benefit di massa consente di modificare contemporaneamente la data di scadenza sia di un benefit sia delle iscrizioni dei lavoratori al benefit.</span><span class="sxs-lookup"><span data-stu-id="d2032-140">Mass benefit expiration lets you change the expiration date of both a benefit and the worker enrollments for that benefit at the same time.</span></span> <span data-ttu-id="d2032-141">È inoltre possibile selezionare più lavoratori iscritti a un benefit e modificare la data di fine delle copertura.</span><span class="sxs-lookup"><span data-stu-id="d2032-141">You can also select multiple workers who are enrolled in a benefit and change the ending date of their coverage.</span></span> 

<span data-ttu-id="d2032-142">In modo analogo, la proroga di benefit collettiva consente di estendere la data di scadenza sia di un benefit che delle iscrizioni del lavoratore per il benefit, se si decide di offrire un benefit più lungo di quanto originariamente pianificato.</span><span class="sxs-lookup"><span data-stu-id="d2032-142">Similarly, mass benefit extension lets you extend the expiration date of both a benefit and the worker enrollments for that benefit if you decide to offer a benefit longer than you originally planned.</span></span>

<a name="see-also"></a><span data-ttu-id="d2032-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2032-143">See also</span></span>
--------

[<span data-ttu-id="d2032-144">Criteri di idoneità benefit</span><span class="sxs-lookup"><span data-stu-id="d2032-144">Benefit eligibility policies</span></span>](benefit-eligibility-policies.md)




