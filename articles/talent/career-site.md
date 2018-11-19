---
title: "Funzionalità del sito di avanzamento professionale in Attract"
description: "Questo articolo fornisce una panoramica delle funzionalità del sito di avanzamento professionale rivolto ai candidati in Microsoft Dynamics 365 for Talent - Attract. Viene descritto inoltre come impostare le funzionalità."
author: josaw
manager: AnnBe
ms.date: 10/18/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 452e3e92ea32ab5f1e3720ab81ff2f7ea18b2a06
ms.contentlocale: it-it
ms.lasthandoff: 10/22/2018

---
# <a name="career-site-functionality-in-attract"></a><span data-ttu-id="351a0-104">Funzionalità del sito di avanzamento professionale in Attract</span><span class="sxs-lookup"><span data-stu-id="351a0-104">Career site functionality in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="351a0-105">Questo articolo fornisce una panoramica delle funzionalità del sito di avanzamento professionale rivolto ai candidati in Microsoft Dynamics 365 for Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="351a0-105">This article provides an overview of the candidate-facing career site functionality in Microsoft Dynamics 365 for Talent: Attract.</span></span> <span data-ttu-id="351a0-106">Viene descritto inoltre come impostare le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="351a0-106">It also explains how to set up this functionality.</span></span>

## <a name="overview"></a><span data-ttu-id="351a0-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="351a0-107">Overview</span></span>

<span data-ttu-id="351a0-108">Attract fornisce un sito di avanzamento professionale per ogni ambiente in un tenant.</span><span class="sxs-lookup"><span data-stu-id="351a0-108">Attract provides one career site for each environment in a tenant.</span></span> <span data-ttu-id="351a0-109">Ad esempio, se un'organizzazione ha un ambiente di sviluppo e un ambiente di test, un sito di avanzamento professionale viene fornito per l'ambiente di sviluppo e un altro sito di avanzamento professionale per l'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="351a0-109">For example, if an organization has a development environment and a test environment, one career site is provisioned for the development environment, and another career site is provisioned for the test environment.</span></span> <span data-ttu-id="351a0-110">Ogni sito di avanzamento professionale è **completamente isolato** e ha un proprio meccanismo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="351a0-110">Each career site is **completely isolated** and has its own authentication mechanism.</span></span> <span data-ttu-id="351a0-111">Le mansioni e i profili dei candidati non sono condivisi tra siti di avanzamento professionale.</span><span class="sxs-lookup"><span data-stu-id="351a0-111">Jobs and candidate profiles aren't shared between career sites.</span></span>

<span data-ttu-id="351a0-112">Per impostazione predefinita, il sito di avanzamento professionale è pubblico.</span><span class="sxs-lookup"><span data-stu-id="351a0-112">By default, the career site is public.</span></span> <span data-ttu-id="351a0-113">Di conseguenza, i candidati possono visualizzare tutte le mansioni contrassegnate come esterne senza dover accedere.</span><span class="sxs-lookup"><span data-stu-id="351a0-113">Therefore, candidates can view all jobs that are marked as external without having to sign in.</span></span> <span data-ttu-id="351a0-114">Tuttavia, tutte le altre azioni richiedono l'accesso dei candidati.</span><span class="sxs-lookup"><span data-stu-id="351a0-114">However, all other actions require that candidates sign in.</span></span>

## <a name="career-site-management"></a><span data-ttu-id="351a0-115">Gestione del sito per le possibilità di carriera</span><span class="sxs-lookup"><span data-stu-id="351a0-115">Career site management</span></span>

<span data-ttu-id="351a0-116">I seguenti elementi nel sito di avanzamento professionale sono controllati da impostazioni:</span><span class="sxs-lookup"><span data-stu-id="351a0-116">The following items on the career site are controlled by settings:</span></span>

- <span data-ttu-id="351a0-117">**Nome organizzazione:** Il nome dell'organizzazione appare sulla barra di spostamento nella parte superiore del sito di avanzamento professionale.</span><span class="sxs-lookup"><span data-stu-id="351a0-117">**Organization name:** The organization name appears on the navigation bar at the top of the career site.</span></span> <span data-ttu-id="351a0-118">Selezionando il nome di organizzazione, i candidati vanno a una pagina contenente tutte le posizioni aperte.</span><span class="sxs-lookup"><span data-stu-id="351a0-118">By selecting the organization name, candidates go to a page that lists all open jobs.</span></span>
- <span data-ttu-id="351a0-119">**Logo organizzazione:** Un'immagine del logo dell'organizzazione appare in alto a sinistra del sito di avanzamento professionale.</span><span class="sxs-lookup"><span data-stu-id="351a0-119">**Organization logo:** An image of the organization's logo appears in the upper left of the career site.</span></span> <span data-ttu-id="351a0-120">Selezionando l'immagine del logo, i candidati vanno a una pagina contenente tutte le posizioni aperte.</span><span class="sxs-lookup"><span data-stu-id="351a0-120">By selecting the logo image, candidates go to a page that lists all open jobs.</span></span>

<span data-ttu-id="351a0-121">Per impostare i valori per il nome e il logo di organizzazione, accedere ad Attract come amministratore, selezionare **Interfaccia di amministrazione** dal menu **Impostazioni** (il simbolo di ingranaggio) e quindi fare clic sulla scheda **Informazioni società**.</span><span class="sxs-lookup"><span data-stu-id="351a0-121">To set the values for the organization name and logo, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu (the gear symbol), and then select the **Company information** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="351a0-122">Immagine di logo visualizzata nel sito di avanzamento professionale ha un'altezza fissa di 20 pixel.</span><span class="sxs-lookup"><span data-stu-id="351a0-122">The logo image that appears on the career site has a fixed height of 20 pixels (px).</span></span> <span data-ttu-id="351a0-123">L'immagine che si aggiunge nell'Interfaccia di amministrazione viene ridimensionata in base allo spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="351a0-123">The image that you add in the Admin center is scaled to fit.</span></span> <span data-ttu-id="351a0-124">Di conseguenza, a seconda dell'immagine, la larghezza può cambiare.</span><span class="sxs-lookup"><span data-stu-id="351a0-124">Therefore, depending on the image, the width might change.</span></span>

## <a name="career-site-url"></a><span data-ttu-id="351a0-125">URL del sito di avanzamento professionale</span><span class="sxs-lookup"><span data-stu-id="351a0-125">Career site URL</span></span>

<span data-ttu-id="351a0-126">Quando si [pubblica l'annuncio di una mansione esterna](./Creating-jobs-Attract.md#postings) per la prima volta, è possibile copiare il collegamento **Domanda di lavoro** nell'applicazione Attract.</span><span class="sxs-lookup"><span data-stu-id="351a0-126">When you [post an external job](./Creating-jobs-Attract.md#postings) for the first time, you can copy the **Apply** link from the Attract application.</span></span> <span data-ttu-id="351a0-127">L'URL per il collegamento avrà il formato seguente: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`</span><span class="sxs-lookup"><span data-stu-id="351a0-127">The URL for this link will be in the following format: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`</span></span>

<span data-ttu-id="351a0-128">L'URL del sito di avanzamento professionale è una sottostringa dell'URL **Domanda di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="351a0-128">The URL of the career site is a substring of the **Apply** URL.</span></span> <span data-ttu-id="351a0-129">È formata da tutte le parti fino al nome della società.</span><span class="sxs-lookup"><span data-stu-id="351a0-129">It consists of everything up through the company name.</span></span> <span data-ttu-id="351a0-130">Di conseguenza, per l'URL **Domanda di lavoro** precedente, l'URL del sito di avanzamento professionale è `https://jobs.talent.dynamics.com/jobs/<company_name>/`.</span><span class="sxs-lookup"><span data-stu-id="351a0-130">Therefore, for the preceding **Apply** URL, the career site URL is `https://jobs.talent.dynamics.com/jobs/<company_name>/`.</span></span>

## <a name="authentication-options"></a><span data-ttu-id="351a0-131">Opzioni di autenticazione</span><span class="sxs-lookup"><span data-stu-id="351a0-131">Authentication options</span></span>

<span data-ttu-id="351a0-132">I candidati hanno le seguenti opzioni di accesso per un sito di avanzamento professionale Attract:</span><span class="sxs-lookup"><span data-stu-id="351a0-132">Candidates have the following sign-in options for an Attract career site:</span></span>

- <span data-ttu-id="351a0-133">Account personale:</span><span class="sxs-lookup"><span data-stu-id="351a0-133">Personal account:</span></span>

    - <span data-ttu-id="351a0-134">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="351a0-134">LinkedIn</span></span>
    - <span data-ttu-id="351a0-135">Microsoft</span><span class="sxs-lookup"><span data-stu-id="351a0-135">Microsoft</span></span>
    - <span data-ttu-id="351a0-136">Google</span><span class="sxs-lookup"><span data-stu-id="351a0-136">Google</span></span>
    - <span data-ttu-id="351a0-137">Facebook</span><span class="sxs-lookup"><span data-stu-id="351a0-137">Facebook</span></span>

- <span data-ttu-id="351a0-138">Account di lavoro o dell'istituto di istruzione:</span><span class="sxs-lookup"><span data-stu-id="351a0-138">Work or school account:</span></span>

    - <span data-ttu-id="351a0-139">Microsoft Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="351a0-139">Microsoft Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="351a0-140">L'accesso tramite Azure AD è destinato solo ai candidati interni.</span><span class="sxs-lookup"><span data-stu-id="351a0-140">Azure AD sign-in is intended only for internal candidates.</span></span> <span data-ttu-id="351a0-141">Di conseguenza, funziona solo per i candidati interni che utilizzano le proprie credenziali Azure AD aziendali.</span><span class="sxs-lookup"><span data-stu-id="351a0-141">Therefore, it works only for internal candidates who use their company Azure AD credentials.</span></span> <span data-ttu-id="351a0-142">Ad esempio, un candidato che è attualmente un dipendente di Contoso Ltd desidera inviare una candidatura per una mansione in una società non correlata, Alpine Ski House.</span><span class="sxs-lookup"><span data-stu-id="351a0-142">For example, a candidate who is currently an employee of Contoso Ltd wants to apply for a job in an unrelated company, Alpine Ski House.</span></span> <span data-ttu-id="351a0-143">In questo caso, l'accesso non riuscirà se il dipendente tenta di utilizzare le credenziali Azure AD di Contoso Ltd.</span><span class="sxs-lookup"><span data-stu-id="351a0-143">In this case, the sign-in will be unsuccessful if the employee tries to use his or her Azure AD credentials from Contoso Ltd.</span></span>

## <a name="create-and-maintain-a-profile"></a><span data-ttu-id="351a0-144">Creazione e gestione di un profilo</span><span class="sxs-lookup"><span data-stu-id="351a0-144">Create and maintain a profile</span></span>

<span data-ttu-id="351a0-145">Dopo che i candidati accedono al sito di avanzamento professionale, possono selezionare **Profilo personale** sulla barra di spostamento nella parte superiore della pagina per creare e gestire il proprio profilo.</span><span class="sxs-lookup"><span data-stu-id="351a0-145">After candidates sign in to the career site, they can select **My profile** on the navigation bar at the top of the page to create and maintain their profile.</span></span> <span data-ttu-id="351a0-146">Il profilo include le informazioni personali, le informazioni sull'esperienza di lavoro, i dettagli del percorso formativo, i documenti, i collegamenti e le informazioni sugli insiemi delle competenze.</span><span class="sxs-lookup"><span data-stu-id="351a0-146">The profile includes personal information, information about work experience, education details, documents, links, and information about skill sets.</span></span> <span data-ttu-id="351a0-147">Dopo che un profilo viene creato, può essere utilizzato per fare domanda per le mansioni a cui il candidato è interessato.</span><span class="sxs-lookup"><span data-stu-id="351a0-147">After a profile is created, it can be used to apply for jobs that the candidate is interested in.</span></span> <span data-ttu-id="351a0-148">I profili consentono anche ad Attract di consigliare le mansioni giuste ai candidati.</span><span class="sxs-lookup"><span data-stu-id="351a0-148">Profiles also help Attract recommend the right jobs to candidates.</span></span>

## <a name="find-the-right-job"></a><span data-ttu-id="351a0-149">Individuare la giusta mansione</span><span class="sxs-lookup"><span data-stu-id="351a0-149">Find the right job</span></span>

<span data-ttu-id="351a0-150">Nella pagina con l'elenco delle mansioni, i candidati possono cercare una mansione specifica immettendo i termini di ricerca.</span><span class="sxs-lookup"><span data-stu-id="351a0-150">On the job list page, candidates can search for a specific job by entering search terms.</span></span> <span data-ttu-id="351a0-151">La funzionalità di ricerca cerca i termini di ricerca nei titoli e nelle le descrizioni delle mansioni e visualizza le mansioni rilevanti come risultati.</span><span class="sxs-lookup"><span data-stu-id="351a0-151">The search functionality looks for the search terms in job titles and job descriptions, and shows relevant jobs as results.</span></span> <span data-ttu-id="351a0-152">I candidati possono filtrare in qualsiasi momento i risultati, in base alla posizione della mansione o alla funzione lavorativa.</span><span class="sxs-lookup"><span data-stu-id="351a0-152">Candidates can filter the results at any time, based on the job location or job function.</span></span>

<span data-ttu-id="351a0-153">I candidati possono inoltre visualizzare un insieme di mansioni consigliate nel sito di avanzamento professionale.</span><span class="sxs-lookup"><span data-stu-id="351a0-153">Candidates can also view a set of recommended jobs on the career site.</span></span> <span data-ttu-id="351a0-154">Le mansioni consigliate a un candidato si basano sulle passate domande di lavoro, profilo e curriculum del candidato.</span><span class="sxs-lookup"><span data-stu-id="351a0-154">The jobs that are recommended to a candidate are based on the candidate's past applications, profile, and resumes.</span></span>

> [!NOTE]
> <span data-ttu-id="351a0-155">I suggerimenti di mansioni vengono visualizzati solo se almeno 10 posizioni lavorative sono pubblicate nel sito di avanzamento professionale e se il candidato ha completato il proprio profilo.</span><span class="sxs-lookup"><span data-stu-id="351a0-155">Job recommendations are shown only if at least 10 jobs are posted on the career site, and if the candidate has completed his or her profile.</span></span>

## <a name="apply-for-jobs"></a><span data-ttu-id="351a0-156">Inviare candidature per posizioni lavorative</span><span class="sxs-lookup"><span data-stu-id="351a0-156">Apply for jobs</span></span>

<span data-ttu-id="351a0-157">Dopo che i candidati individuano la giusta mansione, possono inviare la candidatura tramite il pulsante **Applica** nella pagina dei dettagli della mansione.</span><span class="sxs-lookup"><span data-stu-id="351a0-157">After candidates find the right job, they can apply by using the **Apply** button on the job details page.</span></span> <span data-ttu-id="351a0-158">A questo punto, i candidati possono creare un profilo nuovo di zecca oppure modificare le informazioni nel profilo esistente.</span><span class="sxs-lookup"><span data-stu-id="351a0-158">At this point, candidates can either create a brand-new profile or review the information in their existing profile.</span></span> <span data-ttu-id="351a0-159">I candidati possono inoltre possibile caricare un curriculum, secondo le esigenze, e quindi inviare la domanda di lavoro.</span><span class="sxs-lookup"><span data-stu-id="351a0-159">Candidates can also upload a resume, as required, and then submit the job application.</span></span>

## <a name="check-application-status"></a><span data-ttu-id="351a0-160">Verificare lo stato della domanda di lavoro</span><span class="sxs-lookup"><span data-stu-id="351a0-160">Check application status</span></span>

<span data-ttu-id="351a0-161">Dopo che i candidati fanno domanda per una o più mansioni, possono selezionare **Domande di lavoro** sulla barra di spostamento nella parte superiore della pagina per visualizzare le domande aperte e chiuse.</span><span class="sxs-lookup"><span data-stu-id="351a0-161">After candidates apply for one or more jobs, they can select **Applications** on the navigation bar at the top of the page to view their open and closed applications.</span></span> <span data-ttu-id="351a0-162">Quando i candidati aprono una delle domande, vedono la fase corrente e le eventuali azioni in sospeso da completare.</span><span class="sxs-lookup"><span data-stu-id="351a0-162">When candidates open one of their applications, they see the current stage and any pending action items that they must complete.</span></span> <span data-ttu-id="351a0-163">Ad esempio, se un candidato deve fornire date potenziali per un colloquio di persona, la pagina mostra le relative opzioni.</span><span class="sxs-lookup"><span data-stu-id="351a0-163">For example, if a candidate must provide potential dates for an in-person interview, the page shows his or her options.</span></span>

## <a name="internal-jobs"></a><span data-ttu-id="351a0-164">Mansioni interne</span><span class="sxs-lookup"><span data-stu-id="351a0-164">Internal jobs</span></span>

<span data-ttu-id="351a0-165">Attualmente, le mansioni contrassegnate come interne e pubblicate nel sito di avanzamento professionale Attract non vengono visualizzate nel sito di avanzamento professionale.</span><span class="sxs-lookup"><span data-stu-id="351a0-165">Currently, jobs that are marked as internal and posted to the Attract career site don't appear on the career site.</span></span> <span data-ttu-id="351a0-166">Sono accessibili solo tramite l'URL diretto di **Domanda di lavoro** che può essere copiato dall'applicazione Attract.</span><span class="sxs-lookup"><span data-stu-id="351a0-166">They are accessible only via the direct **Apply** URL that can be copied from the Attract application.</span></span>

