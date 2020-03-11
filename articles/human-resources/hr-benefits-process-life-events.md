---
title: Elaborare eventi reali
description: Durante il ciclo di vita dei dipendenti in Microsoft Dynamics 365 Human Resources, per ogni dipendente possono verificarsi varie modifiche agli eventi reali.
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
ms.openlocfilehash: 91812432ead4b0afccfba30f8023f014e216236a
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009554"
---
# <a name="process-life-events"></a><span data-ttu-id="15a4b-103">Elaborare eventi reali</span><span class="sxs-lookup"><span data-stu-id="15a4b-103">Process life events</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="15a4b-104">Durante il ciclo di vita dei dipendenti in Microsoft Dynamics 365 Human Resources, per ogni dipendente possono verificarsi varie modifiche agli eventi reali.</span><span class="sxs-lookup"><span data-stu-id="15a4b-104">During the employee lifecycle in Microsoft Dynamics 365 Human Resources, each employee may encounter various life event changes.</span></span> <span data-ttu-id="15a4b-105">Ad esempio, un matrimonio, un cambio di lavoro o un modifica relativa a una persona a carico/beneficiario.</span><span class="sxs-lookup"><span data-stu-id="15a4b-105">For example, marriage, change in employment, or dependent/beneficiary change.</span></span> <span data-ttu-id="15a4b-106">Per utilizzare gli eventi reali, è necessario abilitarli nel modulo dei parametri dei benefit, impostare i tipi di eventi reali nonché le opzioni degli eventi reali per i tipi di piano.</span><span class="sxs-lookup"><span data-stu-id="15a4b-106">To use life events, you must enable life events in the benefits parameters form, set up life event types, and set up life event options for plan types.</span></span>

<span data-ttu-id="15a4b-107">Prima di poter elaborare gli eventi reali, è necessario aver già eseguito l'iscrizione aperta almeno una volta durante un periodo di assunzione.</span><span class="sxs-lookup"><span data-stu-id="15a4b-107">Before you can process life events, you must have already run open enrollment at least once during a hiring time frame.</span></span> <span data-ttu-id="15a4b-108">Negli Stati Uniti, l'iscrizione aperta è in genere una volta all'anno.</span><span class="sxs-lookup"><span data-stu-id="15a4b-108">In the United States, open enrollment is typically once per year.</span></span> <span data-ttu-id="15a4b-109">Al di fuori degli Stati Uniti, l'iscrizione aperta può essere effettuata al momento dell'assunzione.</span><span class="sxs-lookup"><span data-stu-id="15a4b-109">Outside the United States, open enrollment may be run at the time of hire.</span></span> <span data-ttu-id="15a4b-110">Un lavoratore non deve selezionare un piano di benefit per poter elaborare eventi reali, ma deve essere stato incluso nell'elaborazione dell'iscrizione aperta.</span><span class="sxs-lookup"><span data-stu-id="15a4b-110">A worker does not need to select a benefit plan in order for life events to be processed, but they need to have been included in open enrollment processing.</span></span> 

<span data-ttu-id="15a4b-111">Utilizzare l'elaborazione di eventi reali quando vi sono lavoratori con eventi reali che avvengono in una data futura.</span><span class="sxs-lookup"><span data-stu-id="15a4b-111">Use life event processing when you have workers who have life events that take place on a future date.</span></span> <span data-ttu-id="15a4b-112">Questo evento elaborerà tutti gli eventi reali che non sono stati elaborati (come eventi reali futuri o eventi reali che sono stati aggiunti e che non sono specifici a un lavoratore - un esempio è un nuovo benefit).</span><span class="sxs-lookup"><span data-stu-id="15a4b-112">This event will process all life events that have not been processed (like future life events, or life events that have been added that are not specific to any one worker – one example is a new benefit).</span></span> <span data-ttu-id="15a4b-113">Gli eventi reali in tempo reale sono nascosti.</span><span class="sxs-lookup"><span data-stu-id="15a4b-113">Real time life events are hidden.</span></span>

<span data-ttu-id="15a4b-114">Ad esempio, se oggi è il 1° febbraio e il 14 febbraio il lavoratore Joe Smith è programmato per cambiare le persone giuridiche, se si esegue l'elaborazione degli eventi reali per il 15 febbraio, il sistema elabora tutti gli eventi fino al 15 febbraio.</span><span class="sxs-lookup"><span data-stu-id="15a4b-114">For example, if today is February 1, and on February 14 worker Joe Smith is scheduled to change legal entities, if you run life event processing for February 15, the system processes all events up until February 15.</span></span> 

1. <span data-ttu-id="15a4b-115">Nell'area di lavoro **Gestione benefit**, sotto **Elaborazione**, selezionare **Elaborazione eventi reali**.</span><span class="sxs-lookup"><span data-stu-id="15a4b-115">In the **Benefits management** workspace, under **Processing**, select **Life event processing**.</span></span>

2. <span data-ttu-id="15a4b-116">Nella finestra di dialogo **Esegui elaborazione eventi reali**, specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="15a4b-116">In the **Run life event process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="15a4b-117">Campo</span><span class="sxs-lookup"><span data-stu-id="15a4b-117">Field</span></span> | <span data-ttu-id="15a4b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15a4b-118">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="15a4b-119">Periodo di iscrizione</span><span class="sxs-lookup"><span data-stu-id="15a4b-119">Enrollment period</span></span> | <span data-ttu-id="15a4b-120">Il periodo di iscrizione per il quale elaborare gli eventi reali.</span><span class="sxs-lookup"><span data-stu-id="15a4b-120">The enrollment period to process life events for.</span></span> |
   | <span data-ttu-id="15a4b-121">Persona giuridica</span><span class="sxs-lookup"><span data-stu-id="15a4b-121">Legal entity</span></span> | <span data-ttu-id="15a4b-122">La persona giuridica per la quale elaborare gli eventi reali.</span><span class="sxs-lookup"><span data-stu-id="15a4b-122">The legal entity to process life events for.</span></span> |
   | <span data-ttu-id="15a4b-123">Data evento reale</span><span class="sxs-lookup"><span data-stu-id="15a4b-123">Life event date</span></span> | <span data-ttu-id="15a4b-124">Il sistema elabora tutti gli eventi durante il periodo di iscrizione che si verificano fino a questa data.</span><span class="sxs-lookup"><span data-stu-id="15a4b-124">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="15a4b-125">Lavoro</span><span class="sxs-lookup"><span data-stu-id="15a4b-125">Worker</span></span> | <span data-ttu-id="15a4b-126">Il lavoratore per il quale elaborare gli eventi reali.</span><span class="sxs-lookup"><span data-stu-id="15a4b-126">The worker to process life events for.</span></span> <span data-ttu-id="15a4b-127">Se questo campo viene lasciato vuoto, gli eventi reali saranno elaborati per tutti i lavoratori.</span><span class="sxs-lookup"><span data-stu-id="15a4b-127">If you leave this field blank, life events will be processed for all workers.</span></span> |

3. <span data-ttu-id="15a4b-128">Se si desidera eseguire l'elaborazione in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="15a4b-128">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="15a4b-129">Immettere le informazioni per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="15a4b-129">Enter information for the process.</span></span>

   2. <span data-ttu-id="15a4b-130">Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="15a4b-130">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="15a4b-131">Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="15a4b-131">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="15a4b-132">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="15a4b-132">Select **OK**.</span></span> <span data-ttu-id="15a4b-133">l'elaborazione verrà eseguita con i parametri impostati.</span><span class="sxs-lookup"><span data-stu-id="15a4b-133">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="15a4b-134">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="15a4b-134">Select **OK**.</span></span>