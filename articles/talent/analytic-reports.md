---
title: Utilizzare report analitici in Attract
description: In questo argomento vengono descritti i report analitici per il processo di assunzione in Microsoft Dynamics 365 Talent - Attract
author: fewatson
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: fewatson
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent April 2019 update
ms.openlocfilehash: 081988e8b8cfe1e2ddb533247b678ba38a07f5f1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461668"
---
# <a name="use-analytic-reports-in-attract"></a><span data-ttu-id="528ec-103">Utilizzare report analitici in Attract</span><span class="sxs-lookup"><span data-stu-id="528ec-103">Use analytic reports in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="528ec-104">I report analitici in Microsoft Dynamics 365 Talent: Attract offrono una soluzione pronta all'uso per informazioni sul processo di assunzione.</span><span class="sxs-lookup"><span data-stu-id="528ec-104">Analytic reports in Microsoft Dynamics 365 Talent: Attract provide an out-of-the-box (OOTB) solution for hiring process insights.</span></span> <span data-ttu-id="528ec-105">Le funzionalità disponibili includono:</span><span class="sxs-lookup"><span data-stu-id="528ec-105">Availabe features include:</span></span>

- <span data-ttu-id="528ec-106">**Analisi posizione**: fare clic sulla scheda **Analisi** in una mansione per visualizzare le metriche su un candidato per la mansione.</span><span class="sxs-lookup"><span data-stu-id="528ec-106">**Job analytics:** Click the **Analytics** tab within a job for metrics on the job's applicants.</span></span>
- <span data-ttu-id="528ec-107">**Hub analisi**: fare clic su **Analisi** nel riquadro di spostamento sinistro per visualizzare le metriche aggregate di tutte le posizioni lavorative.</span><span class="sxs-lookup"><span data-stu-id="528ec-107">**Analytics hub:** Click **Analytics** on the left navigation for aggregated metrics across jobs.</span></span>
- <span data-ttu-id="528ec-108">**Sicurezza specifica per l'utente**: l'accesso ai report è controllato dal [ruolo](security-attract.md) di Attract e dal ruolo di partecipante alla posizione lavorativa.</span><span class="sxs-lookup"><span data-stu-id="528ec-108">**User-specific security:** Access to reports is controlled by Attract [role](security-attract.md) and job participant role.</span></span>
- <span data-ttu-id="528ec-109">**Filtro incrociato**: fare clic sugli oggetti visivi in un report per visualizzare altre metriche filtrate in base ai dati selezionati.</span><span class="sxs-lookup"><span data-stu-id="528ec-109">**Cross-filtering:** Click visuals within a report to view other metrics filtered by selected data.</span></span>

>[!NOTE] 
>- <span data-ttu-id="528ec-110">Questa funzionalità è attualmente in [anteprima](access-preview-feature.md).</span><span class="sxs-lookup"><span data-stu-id="528ec-110">This feature is currently in [preview](access-preview-feature.md).</span></span> <span data-ttu-id="528ec-111">Per provarla, è necessario il [**Componente aggiuntivo per l'assunzione a livello globale**](attract-comprehensive-hiring.md).</span><span class="sxs-lookup"><span data-stu-id="528ec-111">To try it, you must have the [**Comprehensive Hiring Add-On**](attract-comprehensive-hiring.md).</span></span>
>- <span data-ttu-id="528ec-112">Tutti i report pubblici in anteprima vengono visualizzati in inglese.</span><span class="sxs-lookup"><span data-stu-id="528ec-112">All public preview reports are displayed in English.</span></span>
>- <span data-ttu-id="528ec-113">Segnala l'aggiornamento ogni 3 ore.</span><span class="sxs-lookup"><span data-stu-id="528ec-113">Reports refresh every 3 hours.</span></span> <span data-ttu-id="528ec-114">Ultimo aggiornamento (ora in base al fuso orario locale) si trova nella parte superiore del report.</span><span class="sxs-lookup"><span data-stu-id="528ec-114">The last refresh time (in the local timezone) is located at the top of the report.</span></span> <span data-ttu-id="528ec-115">I tempi di aggiornamento sono un'approssimazione e variano in base al volume di dati e al carico di risorse nell'area.</span><span class="sxs-lookup"><span data-stu-id="528ec-115">Refresh times are an approximation and vary based on data volume and resource load in your region.</span></span>

## <a name="job-analytics"></a><span data-ttu-id="528ec-116">Analisi posizione</span><span class="sxs-lookup"><span data-stu-id="528ec-116">Job Analytics</span></span>

<span data-ttu-id="528ec-117">I report Analisi posizione sono uno snapshot del processo di assunzione per una posizione lavorativa.</span><span class="sxs-lookup"><span data-stu-id="528ec-117">Job Analytics reports are a snapshot of the hiring process for a job.</span></span>  <span data-ttu-id="528ec-118">Le metriche chiave includono:</span><span class="sxs-lookup"><span data-stu-id="528ec-118">Key metrics include:</span></span>

- <span data-ttu-id="528ec-119">Candidati attivi per fase</span><span class="sxs-lookup"><span data-stu-id="528ec-119">Active applicants by stage</span></span>
- <span data-ttu-id="528ec-120">Origine del candidato</span><span class="sxs-lookup"><span data-stu-id="528ec-120">Applicant source</span></span>
- <span data-ttu-id="528ec-121">Tipo di candidato (interno o esterno)</span><span class="sxs-lookup"><span data-stu-id="528ec-121">Applicant type (internal or external)</span></span>

## <a name="analytics-hub"></a><span data-ttu-id="528ec-122">Hub analisi</span><span class="sxs-lookup"><span data-stu-id="528ec-122">Analytics Hub</span></span>

<span data-ttu-id="528ec-123">Report dell'Hub analisi aggregano i dati relativi alle posizioni lavorative per individuare le tendenze nel processo di assunzione.</span><span class="sxs-lookup"><span data-stu-id="528ec-123">Analytics Hub reports aggregate data across jobs to surface trends in the hiring process.</span></span> <span data-ttu-id="528ec-124">Attract include due report pronti all'uso: Riepilogo pipeline e Analisi del flusso di conversione.</span><span class="sxs-lookup"><span data-stu-id="528ec-124">Attract includes two OOTB reports: Pipeline Summary and Funnel Analysis.</span></span>

### <a name="pipeline-summary"></a><span data-ttu-id="528ec-125">Riepilogo pipeline</span><span class="sxs-lookup"><span data-stu-id="528ec-125">Pipeline Summary</span></span>

<span data-ttu-id="528ec-126">Il report di riepilogo della pipeline raggruppa i dati per le posizioni aperte.</span><span class="sxs-lookup"><span data-stu-id="528ec-126">The Pipeline Summary report aggregates data for open jobs.</span></span> <span data-ttu-id="528ec-127">Le metriche chiave includono:</span><span class="sxs-lookup"><span data-stu-id="528ec-127">Key metrics include:</span></span>

- <span data-ttu-id="528ec-128">Candidati per tutte le posizioni lavorative in base alla fase</span><span class="sxs-lookup"><span data-stu-id="528ec-128">Applicants across all jobs by stage</span></span>
- <span data-ttu-id="528ec-129">Origine del candidato</span><span class="sxs-lookup"><span data-stu-id="528ec-129">Applicant source</span></span>
- <span data-ttu-id="528ec-130">Posizioni lavorative aperte in base al livello di anzianità</span><span class="sxs-lookup"><span data-stu-id="528ec-130">Open jobs by seniority level</span></span>

### <a name="funnel-analysis"></a><span data-ttu-id="528ec-131">Analisi del flusso di conversione</span><span class="sxs-lookup"><span data-stu-id="528ec-131">Funnel Analysis</span></span>

<span data-ttu-id="528ec-132">Il report di Analisi del flusso di conversione raggruppa i dati per le posizioni lavorative che sono stati chiuse come completate.</span><span class="sxs-lookup"><span data-stu-id="528ec-132">The Funnel Analysis report aggregates data for jobs that have been closed as filled.</span></span> <span data-ttu-id="528ec-133">Le metriche chiave includono:</span><span class="sxs-lookup"><span data-stu-id="528ec-133">Key metrics include:</span></span>

- <span data-ttu-id="528ec-134">Tempi di assunzione</span><span class="sxs-lookup"><span data-stu-id="528ec-134">Time to hire</span></span>
- <span data-ttu-id="528ec-135">Metriche di conversione (al passaggio del mouse)</span><span class="sxs-lookup"><span data-stu-id="528ec-135">Conversion metrics (on hover)</span></span>
- <span data-ttu-id="528ec-136">Tasso di accettazione dell'offerta</span><span class="sxs-lookup"><span data-stu-id="528ec-136">Offer acceptance rate</span></span>

<span data-ttu-id="528ec-137">Nota: per report più precisi sui tempi di assunzione, si consiglia di utilizzare [Gestione offerte](offer-setup.md), una funzionalità disponibile come parte del Componente aggiuntivo per l'assunzione a livello globale.</span><span class="sxs-lookup"><span data-stu-id="528ec-137">Note: For the most accurate time to hire reporting, it is recommended that you use [Offer management](offer-setup.md), a feature available as part of the Comprehensive Hiring Add-On.</span></span>

>[!TIP] 
><span data-ttu-id="528ec-138">Provare a passare il mouse sopra le immagini per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="528ec-138">Try hovering over visuals for additional information.</span></span> <span data-ttu-id="528ec-139">Ad esempio, passando il mouse su **Candidati attivi** verranno visualizzata la media in giorni per la fase.</span><span class="sxs-lookup"><span data-stu-id="528ec-139">For example, hovering over **Active applicants** visuals will display the average days in stage.</span></span> <span data-ttu-id="528ec-140">L'analisi di queste informazioni può fornire informazioni fondamentali per ridurre i tempi di assunzione e consentire ai selezionatori di concentrarsi su come ridurre il tempo dedicato per ciascuna fase.</span><span class="sxs-lookup"><span data-stu-id="528ec-140">Analyzing this information can provide insights critical to reducing time to hire and enable recruiters to focus on ways to reduce the time spent in each stage.</span></span>

## <a name="user-specific-security"></a><span data-ttu-id="528ec-141">Sicurezza specifica dell'utente</span><span class="sxs-lookup"><span data-stu-id="528ec-141">User-specific security</span></span>

<span data-ttu-id="528ec-142">I report Attract sono accessibili per i [ruoli](security-attract.md) di Amministratore, Leggi tutto, Selezionatore e Responsabile assunzioni.</span><span class="sxs-lookup"><span data-stu-id="528ec-142">Attract reports are accessible for Admin, Read All, Recruiter, and Hiring Manager [roles](security-attract.md).</span></span> <span data-ttu-id="528ec-143">Gli utenti senza ruolo non possono accedere alle pagine dei report analitici Analisi posizione o Hub analisi.</span><span class="sxs-lookup"><span data-stu-id="528ec-143">Unassigned users do not have access to either of the analytic report pages (Job Analytics or Analytics Hub).</span></span>

<span data-ttu-id="528ec-144">Nei report Analisi posizione vengono visualizzati i dati relativi alla posizione lavorativa selezionata.</span><span class="sxs-lookup"><span data-stu-id="528ec-144">Job Analytics reports display data for the selected job.</span></span> <span data-ttu-id="528ec-145">L'hub analisi riporta i dati aggregati per tutte le posizioni che un utente può visualizzare.</span><span class="sxs-lookup"><span data-stu-id="528ec-145">Analytics Hub reports aggregate data across all jobs a user can view.</span></span> <span data-ttu-id="528ec-146">Gli utenti che possono visualizzare sia Mansioni personali che Tutti le mansioni nella pagina Posizioni possono accedere alle stesse visualizzazioni disponibili nell'Hub analisi.</span><span class="sxs-lookup"><span data-stu-id="528ec-146">Users that can view both My jobs and All jobs on the Jobs page have the same views available in the Analytics Hub.</span></span>

## <a name="cross-filter"></a><span data-ttu-id="528ec-147">Filtro incrociato</span><span class="sxs-lookup"><span data-stu-id="528ec-147">Cross-filter</span></span>

<span data-ttu-id="528ec-148">Una delle interessanti caratteristiche di Power BI è il modo in cui tutte le immagini in una pagina di report sono interconnesse.</span><span class="sxs-lookup"><span data-stu-id="528ec-148">One of the great features of Power BI is the way all visuals on a report page are interconnected.</span></span> <span data-ttu-id="528ec-149">Se si seleziona un punto dati su una delle immagini, tutte le altre immagini della pagina che contengono tali dati cambiano, in base a tale selezione.</span><span class="sxs-lookup"><span data-stu-id="528ec-149">If you select a data point on one of the visuals, all the other visuals on the page that contain that data change, based on that selection.</span></span> <span data-ttu-id="528ec-150">Ulteriori informazioni e un esempio sono disponibili qui: [In che modo le immagini si filtrano a vicenda in un report di Power BI](https://docs.microsoft.com/power-bi/consumer/end-user-interactions).</span><span class="sxs-lookup"><span data-stu-id="528ec-150">Find out more and see an example in [How visuals cross-filter each other in a Power BI report](https://docs.microsoft.com/power-bi/consumer/end-user-interactions).</span></span>

## <a name="export-to-excel"></a><span data-ttu-id="528ec-151">Esporta in Excel</span><span class="sxs-lookup"><span data-stu-id="528ec-151">Export to Excel</span></span>

<span data-ttu-id="528ec-152">Per visualizzare i dati del report in Excel, è possibile fare clic sul menu di opzioni (tre punti) su un'immagine e selezionare **Esporta i dati sottostanti**.</span><span class="sxs-lookup"><span data-stu-id="528ec-152">To view report data in Excel, you can click the options menu (three dots) on a visual and select **Export underlying data**.</span></span> <span data-ttu-id="528ec-153">I dati esportati verranno esportati come filtrati, rispettando le autorizzazioni degli utenti in Attract.</span><span class="sxs-lookup"><span data-stu-id="528ec-153">Exported data will export as filtered, respecting user permissions in Attract.</span></span> <span data-ttu-id="528ec-154">Per ulteriori informazioni, vedere [Esportare dati dalle visualizzazioni](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).</span><span class="sxs-lookup"><span data-stu-id="528ec-154">For more information, see [Export data from visualizations](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).</span></span>
