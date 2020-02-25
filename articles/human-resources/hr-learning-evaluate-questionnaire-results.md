---
title: Visualizzare e valutare i risultati dei questionari
description: In questo articolo viene illustrato come è possibile visualizzare e valutare i risultati dei questionari che gli intervistati completano.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: b597421a79d5038d9d2f55ace250c13db185d120
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009528"
---
# <a name="view-and-evaluate-the-results-of-questionnaires"></a><span data-ttu-id="5aa7c-103">Visualizzare e valutare i risultati dei questionari</span><span class="sxs-lookup"><span data-stu-id="5aa7c-103">View and evaluate the results of questionnaires</span></span>

<span data-ttu-id="5aa7c-104">In questo articolo viene illustrato come è possibile visualizzare e valutare i risultati dei questionari che gli intervistati completano.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-104">This article explains how you can view and evaluate the results of questionnaires that respondents complete.</span></span> 

<span data-ttu-id="5aa7c-105">Dopo che gli intervistati avranno compilato un questionario, sarà possibile vedere e valutare i risultati del questionario nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5aa7c-105">After respondents complete a questionnaire, you can view and evaluate the questionnaire results in the following ways:</span></span>

-   <span data-ttu-id="5aa7c-106">**Sessioni di risposte completate**: visualizzare i dettagli sui questionari completati degli intervistati e generare i report per riepilogare le risposte e anche tutti i punti che sono stati ottenuti.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-106">**Completed answer sessions** – View details about the questionnaires that respondents have completed, and generate reports to summarize answers and any points that were earned.</span></span>
-   <span data-ttu-id="5aa7c-107">**Gruppi di risultati**: visualizzare i dettagli e le statistiche del gruppo di risultati per i questionari.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-107">**Result groups** – View result group details and statistics for questionnaires.</span></span> <span data-ttu-id="5aa7c-108">Le statistiche del gruppo di risultati possono essere generate per una singola sessione di risposte di un questionario o per tutte le sessioni di risposte di un questionario.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-108">Result group statistics can be generated for either a single answer session  of a questionnaire or all answer sessions.</span></span>
-   <span data-ttu-id="5aa7c-109">**Statistiche del questionario**: specificare i criteri per calcolare le statistiche per un gruppo specifico di intervistati.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-109">**Questionnaire statistics** – Specify criteria to calculate statistics for a specific group of respondents.</span></span>

<span data-ttu-id="5aa7c-110">È anche possibile generare i vari report per visualizzare i risultati ordinati per persona, sessione di risposte o gruppo di risultati.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-110">You can also generate various reports to view results that are sorted by person, answer session, or result group.</span></span> <span data-ttu-id="5aa7c-111">Sono disponibili i report seguenti relativi ai questionari completati:</span><span class="sxs-lookup"><span data-stu-id="5aa7c-111">The following reports that are related to completed questionnaires are available:</span></span>

-   <span data-ttu-id="5aa7c-112">Risposte</span><span class="sxs-lookup"><span data-stu-id="5aa7c-112">Answers</span></span>
-   <span data-ttu-id="5aa7c-113">Risposte per questionario</span><span class="sxs-lookup"><span data-stu-id="5aa7c-113">Answers per questionnaire</span></span>
-   <span data-ttu-id="5aa7c-114">Risposte per persona</span><span class="sxs-lookup"><span data-stu-id="5aa7c-114">Answers per person</span></span>
-   <span data-ttu-id="5aa7c-115">Analisi riscontro</span><span class="sxs-lookup"><span data-stu-id="5aa7c-115">Feedback analysis</span></span>

## <a name="answer-session-results"></a><span data-ttu-id="5aa7c-116">Risultati della sessione di risposte</span><span class="sxs-lookup"><span data-stu-id="5aa7c-116">Answer session results</span></span>

<span data-ttu-id="5aa7c-117">Dopo che gli intervistati hanno compilato un questionario, è possibile visualizzare i risultati delle sessioni di risposte completate.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-117">After respondents complete a questionnaire, you can view the results of the completed answer sessions.</span></span> <span data-ttu-id="5aa7c-118">Una sessione di risposte corrisponde alla risposta di un utente a un questionario.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-118">An answer session is one user’s response to a questionnaire.</span></span> <span data-ttu-id="5aa7c-119">È possibile visualizzare i dettagli sulle sessioni di risposte completate nella pagina **Risposte**.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-119">You can view details about completed answer sessions on the **Answers** page.</span></span> <span data-ttu-id="5aa7c-120">Le sessioni di risposte incluse nella pagina **Risposte** vengono filtrate in vari modi, in base alla modalità di apertura la pagina:</span><span class="sxs-lookup"><span data-stu-id="5aa7c-120">The answer sessions that are included on the **Answers** page are filtered in various ways, depending on how you open the page:</span></span>

-   <span data-ttu-id="5aa7c-121">Tutti i questionari</span><span class="sxs-lookup"><span data-stu-id="5aa7c-121">All questionnaires</span></span>
-   <span data-ttu-id="5aa7c-122">Un questionario specifico</span><span class="sxs-lookup"><span data-stu-id="5aa7c-122">A specific questionnaire</span></span>
-   <span data-ttu-id="5aa7c-123">Una persona specifica</span><span class="sxs-lookup"><span data-stu-id="5aa7c-123">A specific person</span></span>

<span data-ttu-id="5aa7c-124">Dalla pagina **Risposte**, è possibile visualizzare i dettagli sulle risposte, i punti ottenuti, le risposte di un intervistato in ciascun gruppo di risultati e la gerarchia delle domande utilizzata nel questionario selezionato, se un gerarchia di domante è stata usata.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-124">From the **Answers** page, you can view details about answers, points that were earned, a respondent’s responses in each result group, and the question hierarchy that was used on the selected questionnaire, if a question hierarchy was used.</span></span> <span data-ttu-id="5aa7c-125">È inoltre possibile generare e stampare i report seguenti:</span><span class="sxs-lookup"><span data-stu-id="5aa7c-125">You can also generate and print the following reports:</span></span>

-   <span data-ttu-id="5aa7c-126">**Report di risultati**: questo report mostra una rappresentazione grafica di punti che sono stati ottenuti per gruppo di risultati della sessione di risposte selezionata.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-126">**Results report** – This report shows a graphical representation of the points that were earned per result group for the selected answer session.</span></span>
-   <span data-ttu-id="5aa7c-127">**Report risposte**: il report mostra le risposte che l'intervistato ha selezionato per ciascuna domanda del questionario.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-127">**Answer report** – This report shows the answers that the respondent selected for each question on the questionnaire.</span></span>
-   <span data-ttu-id="5aa7c-128">**Risposte errate**: questo report mostra le informazioni correlate alle risposte errate selezionate dall'intervistato.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-128">**Incorrect answers** – This report shows information that is related to the incorrect answers that the respondent selected.</span></span>

> [!NOTE]
> <span data-ttu-id="5aa7c-129">Il report **Risultati** è disponibile solo se si utilizzano i gruppi di risultati del questionario e se è stato selezionato **Pagina risultati** nella pagina **Questionari**.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-129">The **Results** report is available only if you use results groups on the questionnaire, and if you selected **Results page** on the **Questionnaires** page.</span></span> <span data-ttu-id="5aa7c-130">Il report **Risposta** e il report **Risposte errate** sono disponibili solo se **Report risposte** è stato selezionato nella pagina **Questionari**.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-130">The **Answer** report and the **Incorrect answers** report are available only if you selected **Answer report** on the **Questionnaires** page.</span></span>

## <a name="questionnaire-statistics"></a><span data-ttu-id="5aa7c-131">Statistiche questionario</span><span class="sxs-lookup"><span data-stu-id="5aa7c-131">Questionnaire statistics</span></span>

<span data-ttu-id="5aa7c-132">È possibile utilizzare le statistiche del questionario per analizzare i risultati di un questionario completato, basato sui calcoli definiti.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-132">You can use questionnaire statistics to analyze the results of a completed questionnaire, based on calculations that you define.</span></span> <span data-ttu-id="5aa7c-133">Per definire i calcoli, è necessario completare le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="5aa7c-133">To define calculations, you must complete the following tasks:</span></span>

-   <span data-ttu-id="5aa7c-134">Selezionare i criteri per calcolare e visualizzare le statistiche.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-134">Select criteria to calculate and display the statistics.</span></span>
    -   <span data-ttu-id="5aa7c-135">È possibile visualizzare le statistiche per questionario, domande, righe delle domande o gruppi di risultati.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-135">You can show statistics by questionnaire, questions, question rows, or results groups.</span></span>
    -   <span data-ttu-id="5aa7c-136">Selezionare il tipo di grafico da utilizzare quando si visualizzano i risultati.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-136">Select the type of chart that will be used when you view results.</span></span>
    -   <span data-ttu-id="5aa7c-137">Selezionare i tipi di persone presenti in rete, ad esempio dipendenti, contatti o candidati, di cui includere le risposte.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-137">Select the types of people from the network, such as employees, contact persons, or applicants, to include answers for.</span></span> <span data-ttu-id="5aa7c-138">È inoltre possibile includere le risposte dei questionari completati in modo anonimo.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-138">You can also include answers from questionnaires that were completed anonymously.</span></span>
    -   <span data-ttu-id="5aa7c-139">Impostare intervalli basati sull'età o l'anzianità per analizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-139">Set up intervals that are based on age or seniority to analyze results.</span></span>
-   <span data-ttu-id="5aa7c-140">Selezionare o verificare le impostazioni disponibili per definire più dettagliatamente il soggetto delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-140">Select or verify settings that refine the subject of the statistics.</span></span> <span data-ttu-id="5aa7c-141">Se ad esempio si seleziona un codice postale (CAP), sarà possibile analizzare i risultati per tutti gli intervistati all'interno dell'area geografica specifica corrispondente a tale codice.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-141">For example, by selecting a ZIP Code or postal code, you can analyze results for all respondents within a specific geographic area.</span></span>
-   <span data-ttu-id="5aa7c-142">Selezionare o verificare i criteri per analizzare i risultati per caratteristiche del questionario o dell'intervistato.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-142">Select or verify criteria to analyze results by respondent or questionnaire characteristics.</span></span> <span data-ttu-id="5aa7c-143">Ad esempio, selezionando **Codice postale (CAP)**, è possibile analizzare la correlazione tra l'ubicazione di un intervistato e le risposte corrette.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-143">For example, by selecting **ZIP/postal code**, you can analyze the correlation between a respondent’s location and correct answers.</span></span>

<span data-ttu-id="5aa7c-144">Le impostazioni definite vengono salvate e possono essere utilizzate per ricalcolare periodicamente i risultati.</span><span class="sxs-lookup"><span data-stu-id="5aa7c-144">The settings that you define are saved and can be used to periodically recalculate results.</span></span>