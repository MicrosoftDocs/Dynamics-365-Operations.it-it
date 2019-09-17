---
title: Novità e modifiche in Dynamics 365 for Talent (11 giugno 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/11/2019
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
ms.search.validFrom: 2019-06-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a1413ea43e852c78ede227b69c0f49c07944a872
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741622"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-june-11-2019"></a><span data-ttu-id="aeeae-103">Novità e modifiche in Dynamics 365 for Talent (11 giugno 2019)</span><span class="sxs-lookup"><span data-stu-id="aeeae-103">What's new or changed in Dynamics 365 for Talent (June 11, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="aeeae-104">Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="aeeae-104">This topic describes features that are either new or changed in Microsoft Dynamics 365 for Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="aeeae-105">Modifiche in Attract</span><span class="sxs-lookup"><span data-stu-id="aeeae-105">Changes in Attract</span></span>

### <a name="search-engine-optimization-for-job-posts"></a><span data-ttu-id="aeeae-106">Ottimizzazione del motore di ricerca per annunci di lavoro</span><span class="sxs-lookup"><span data-stu-id="aeeae-106">Search engine optimization for job posts</span></span>

<span data-ttu-id="aeeae-107">Dopo l'attivazione di **Ottimizzazione del motore di ricerca** nell'interfaccia di amministrazione di Dynamics 365 for Talent: Attract, Attract indica all'API Google Indexing di effettuare la ricerca per indicizzazione della pagina Web ogni volta che si attiva e si pubblica un nuovo annuncio di lavoro o se ne aggiorna uno esistente.</span><span class="sxs-lookup"><span data-stu-id="aeeae-107">After you turn on **Search Engine Optimization** in the Dynamics 365 for Talent: Attract Admin center, Attract informs the Google Indexing application programming interface (API) to crawl the webpage whenever you activate and post a new job or update an existing job.</span></span> <span data-ttu-id="aeeae-108">In questo modo, l'annuncio di lavoro sarà visualizzato nei risultati delle ricerca per Google e altri motori di ricerca.</span><span class="sxs-lookup"><span data-stu-id="aeeae-108">In this way, the job will appear in the search results for Google and other search engines.</span></span>

<span data-ttu-id="aeeae-109">Analogamente, ogni volta che si annulla la pubblicazione di un annuncio di lavoro, Attract informa l'API di indicizzazione, di modo che tale annuncio non sia incluso nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="aeeae-109">Likewise, whenever you unpost a job, Attract informs the Indexing API, so that the unposted job will stop appearing in search results.</span></span>

> [!NOTE]
> <span data-ttu-id="aeeae-110">I crawler Web non dispongono di un periodo di tempo definito per la ricerca per indicizzazione delle pagine Web o l'aggiornamento dei risultati di ricerca.</span><span class="sxs-lookup"><span data-stu-id="aeeae-110">Web crawlers don't have a defined timeframe for crawling webpages or updating search results.</span></span>

## <a name="coming-soon-in-attract"></a><span data-ttu-id="aeeae-111">Funzionalità presto disponibili in Attract</span><span class="sxs-lookup"><span data-stu-id="aeeae-111">Coming soon in Attract</span></span>

### <a name="job-approvals-appear-on-the-home-page"></a><span data-ttu-id="aeeae-112">Approvazioni delle mansioni visualizzate nella home page</span><span class="sxs-lookup"><span data-stu-id="aeeae-112">Job approvals appear on the home page</span></span>

<span data-ttu-id="aeeae-113">Le approvazioni sono visualizzate nella sezione **Approvazioni** del dashboard.</span><span class="sxs-lookup"><span data-stu-id="aeeae-113">Approvals appear in an **Approvals** section on the dashboard.</span></span> <span data-ttu-id="aeeae-114">Gli approvatori possono esaminare le relative approvazioni in **Assegnate all'utente**, in cui è visualizzato l'ID mansione, il titolo della mansione, altri approvatori e la data in cui la mansione è stata assegnata.</span><span class="sxs-lookup"><span data-stu-id="aeeae-114">Approvers can review their approvals under **Assigned to you**, which shows the job ID, the job title, other approvers, and the date when the job was assigned.</span></span> <span data-ttu-id="aeeae-115">Gli utenti che inviano una mansione per l'approvazione possono esaminare le mansioni in **Richieste dall'utente** in cui sono visualizzati gli approvatori che devono ancora approvare la mansione inviata.</span><span class="sxs-lookup"><span data-stu-id="aeeae-115">Users who submit a job for approval can review their jobs under **Requested by you**, which shows the approvers who must still approve the submitted job.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="aeeae-116">Modifiche in Onboard</span><span class="sxs-lookup"><span data-stu-id="aeeae-116">Changes in Onboard</span></span>

<span data-ttu-id="aeeae-117">Questa versione include correzioni di bug minori per Dynamics 365 for Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="aeeae-117">This release includes minor bug fixes for Dynamics 365 for Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="aeeae-118">Modifiche di Core HR</span><span class="sxs-lookup"><span data-stu-id="aeeae-118">Changes in Core HR</span></span>

<span data-ttu-id="aeeae-119">Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2337.</span><span class="sxs-lookup"><span data-stu-id="aeeae-119">The changes that are described in this section apply to build number 8.1.2337.</span></span>

### <a name="platform-update-27"></a><span data-ttu-id="aeeae-120">Update 27 della piattaforma</span><span class="sxs-lookup"><span data-stu-id="aeeae-120">Platform update 27</span></span>

<span data-ttu-id="aeeae-121">Per ulteriori dettagli sull'aggiornamento 27 della piattaforma, vedere [Funzionalità di anteprima nell'aggiornamento 27 della piattaforma Dynamics 365 for Finance and Operations (giugno 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-27).</span><span class="sxs-lookup"><span data-stu-id="aeeae-121">For more details about Platform update 27, see [Preview features in Dynamics 365 for Finance and Operations platform update 27 (June 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-27).</span></span>

### <a name="feature-management-workspace-in-talent"></a><span data-ttu-id="aeeae-122">Area di lavoro Gestione funzionalità in Talent</span><span class="sxs-lookup"><span data-stu-id="aeeae-122">Feature management workspace in Talent</span></span>

<span data-ttu-id="aeeae-123">L'area di lavoro **Gestione funzionalità** in **Amministrazione sistema** consente di visualizzare, abilitare, disabilitare e programmare funzionalità fornite in ogni versione.</span><span class="sxs-lookup"><span data-stu-id="aeeae-123">The **Feature management** workspace in **System administration** lets you view, enable, disable, and schedule features that have been delivered in each release.</span></span> <span data-ttu-id="aeeae-124">Per impostazione predefinita, le nuove funzionalità sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="aeeae-124">By default, new features are turned off.</span></span> <span data-ttu-id="aeeae-125">È possibile utilizzare l'area di lavoro **Gestione funzionalità** per attivarle e visualizzare la documentazione correlata.</span><span class="sxs-lookup"><span data-stu-id="aeeae-125">You can use the **Feature management** workspace to turn them on and view the documentation for them.</span></span>

### <a name="common-data-service-entity-support-for-custom-fields"></a><span data-ttu-id="aeeae-126">Support dell'entità Common Data Service per i campi personalizzati</span><span class="sxs-lookup"><span data-stu-id="aeeae-126">Common Data Service entity support for custom fields</span></span>

<span data-ttu-id="aeeae-127">L'entità Agenzia emittente ora supporta i campi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="aeeae-127">The Issuing agency entity now supports custom fields.</span></span>

### <a name="new-common-data-service-entities"></a><span data-ttu-id="aeeae-128">Nuove entità di Common Data Service</span><span class="sxs-lookup"><span data-stu-id="aeeae-128">New Common Data Service entities</span></span>

<span data-ttu-id="aeeae-129">L'entità Gruppo di attività è stata aggiunta.</span><span class="sxs-lookup"><span data-stu-id="aeeae-129">The Task group entity has been added.</span></span>

## <a name="in-preview"></a><span data-ttu-id="aeeae-130">In anteprima</span><span class="sxs-lookup"><span data-stu-id="aeeae-130">In preview</span></span>

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a><span data-ttu-id="aeeae-131">Le funzionalità di anteprima verranno attivate solo negli ambienti sandbox</span><span class="sxs-lookup"><span data-stu-id="aeeae-131">Preview features will be enabled only in sandbox environments</span></span>

<span data-ttu-id="aeeae-132">Per ulteriori informazioni su come vengono pubblicate le modifiche, vedere [Eseguire il provisioning di Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="aeeae-132">For more information about how changes are published, see [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="aeeae-133">Quando si esegue il provisioning di una nuova istanza di Talent, è possibile indicare se il tipo di istanza è Produzione o Sandbox.</span><span class="sxs-lookup"><span data-stu-id="aeeae-133">When you provision a new instance of Talent, you can indicate whether the instance type is Production or Sandbox.</span></span> <span data-ttu-id="aeeae-134">Il tipo di istanza Sandbox consente di testare le nuove funzionalità prima dell'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="aeeae-134">The Sandbox instance type allows for early testing of new features.</span></span> <span data-ttu-id="aeeae-135">Tutte le istanze Talent esistenti verranno aggiornate al tipo di istanza di **produzione**.</span><span class="sxs-lookup"><span data-stu-id="aeeae-135">All existing Talent instances will be updated to the **Production** instance type.</span></span> <span data-ttu-id="aeeae-136">Se si desidera aggiornare una delle istanze esistenti al tipo di istanza **Sandbox**, contattare il [supporto tecnico](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) per avviare la richiesta di modifica.</span><span class="sxs-lookup"><span data-stu-id="aeeae-136">If you want one of your existing instances to be updated to the **Sandbox** instance type, contact [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) to initiate the change request.</span></span>

### <a name="restrict-the-leave-types-in-time-off-requests"></a><span data-ttu-id="aeeae-137">Limitare i tipi di congedo nelle richieste di permessi</span><span class="sxs-lookup"><span data-stu-id="aeeae-137">Restrict the leave types in time-off requests</span></span>

<span data-ttu-id="aeeae-138">Le organizzazioni possono offrire molti tipi di congedo ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="aeeae-138">Organizations can offer many types of leave to employees.</span></span> <span data-ttu-id="aeeae-139">Tuttavia, potrebbe non essere appropriato per i dipendenti inviare richieste di permesso per alcuni tipi di congedo.</span><span class="sxs-lookup"><span data-stu-id="aeeae-139">However, it might not be appropriate for employees to submit time-off requests for some leave types.</span></span> <span data-ttu-id="aeeae-140">Tali tipi di congedo possono invece essere gestiti dalle risorse umane.</span><span class="sxs-lookup"><span data-stu-id="aeeae-140">Those leave types might be managed by Human resources (HR) instead.</span></span> <span data-ttu-id="aeeae-141">In questa versione, è possibile configurare i tipi di congedo per i quali i dipendenti possono inviare richieste di permessi.</span><span class="sxs-lookup"><span data-stu-id="aeeae-141">In this release, you can configure which leave types employees can submit time-off requests for.</span></span> 

## <a name="coming-soon-in-core-hr"></a><span data-ttu-id="aeeae-142">Funzionalità presto disponibili in Core HR</span><span class="sxs-lookup"><span data-stu-id="aeeae-142">Coming soon in Core HR</span></span>

### <a name="view-extended-information-about-report-performance-in-manager-self-service"></a><span data-ttu-id="aeeae-143">Visualizzare informazioni estese sulle prestazioni dei report in Responsabile self-service</span><span class="sxs-lookup"><span data-stu-id="aeeae-143">View extended information about report performance in manager self-service</span></span>

<span data-ttu-id="aeeae-144">Una nuova opzione consentirà ai responsabili di visualizzare le prestazioni dei report diretti ed estesi.</span><span class="sxs-lookup"><span data-stu-id="aeeae-144">A new option will let managers view the performance of both their direct reports and their extended reports.</span></span> <span data-ttu-id="aeeae-145">Attualmente, i responsabili linea possono assegnare e aggiornare obiettivi prestazionali e pubblicare nuove revisioni.</span><span class="sxs-lookup"><span data-stu-id="aeeae-145">Currently, line managers can assign and update performance goals and issue new reviews.</span></span> <span data-ttu-id="aeeae-146">Inoltre, i responsabili diretti e i relativi dipendenti possono gestire e aggiornare giornali di registrazione prestazioni per garantire la corretta esecuzione del processo di valutazione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="aeeae-146">In addition, direct managers and their employees can maintain and update performance journals to help guarantee that the performance review process goes smoothly.</span></span> <span data-ttu-id="aeeae-147">Una volta questa modifica implementata, i responsabili potranno visualizzare e gestire informazioni relative alle prestazioni per i report estesi oltre che per quelli diretti.</span><span class="sxs-lookup"><span data-stu-id="aeeae-147">When this change is implemented, managers will be able to view and maintain performance-related information for their extended reports in addition to their direct reports.</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="aeeae-148">Stampare le valutazioni delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="aeeae-148">Print performance reviews</span></span>

<span data-ttu-id="aeeae-149">Dipendenti, responsabili e risorse umane potranno stampare la valutazione delle prestazioni di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="aeeae-149">Employees, managers, and HR will be able to print an employee's performance review.</span></span>
