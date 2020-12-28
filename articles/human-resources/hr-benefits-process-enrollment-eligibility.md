---
title: Elaborare l'idoneità di iscrizione
description: In questo articolo viene descritto come eseguire l'elaborazione dell'idoneità di iscrizione.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
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
ms.openlocfilehash: dfb7f13dce48f33c111af491918702763f7e3b8a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4419151"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="780a9-103">Elaborare l'idoneità di iscrizione</span><span class="sxs-lookup"><span data-stu-id="780a9-103">Process enrollment eligibility</span></span>

<span data-ttu-id="780a9-104">In questo articolo viene descritto come eseguire l'elaborazione dell'idoneità di iscrizione.</span><span class="sxs-lookup"><span data-stu-id="780a9-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="780a9-105">Nell'area di lavoro **Gestione benefit**, sotto **Elaborazione**, selezionare **Elaborazione idoneità iscrizione**.</span><span class="sxs-lookup"><span data-stu-id="780a9-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="780a9-106">Nella finestra di dialogo **Esegui elaborazione idoneità iscrizione a benefit**, specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="780a9-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="780a9-107">Campo</span><span class="sxs-lookup"><span data-stu-id="780a9-107">Field</span></span> | <span data-ttu-id="780a9-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="780a9-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="780a9-109">**Periodo di iscrizione**</span><span class="sxs-lookup"><span data-stu-id="780a9-109">**Enrollment period**</span></span> | <span data-ttu-id="780a9-110">Il periodo di iscrizione per il quale elaborare l'idoneità di iscrizione.</span><span class="sxs-lookup"><span data-stu-id="780a9-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="780a9-111">**Persona giuridica**</span><span class="sxs-lookup"><span data-stu-id="780a9-111">**Legal entity**</span></span> | <span data-ttu-id="780a9-112">La persona giuridica per la quale elaborare l'idoneità di iscrizione.</span><span class="sxs-lookup"><span data-stu-id="780a9-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="780a9-113">**Lavoro**</span><span class="sxs-lookup"><span data-stu-id="780a9-113">**Worker**</span></span> | <span data-ttu-id="780a9-114">Il lavoratore per il quale elaborare l'idoneità di iscrizione.</span><span class="sxs-lookup"><span data-stu-id="780a9-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="780a9-115">Se questo campo viene lasciato vuoto, l'idoneità di iscrizione verrà elaborata per tutti i lavoratori.</span><span class="sxs-lookup"><span data-stu-id="780a9-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="780a9-116">**Piano benefit**</span><span class="sxs-lookup"><span data-stu-id="780a9-116">**Benefit plan**</span></span> | <span data-ttu-id="780a9-117">Il piano di benefit per il quale elaborare l'idoneità di iscrizione.</span><span class="sxs-lookup"><span data-stu-id="780a9-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="780a9-118">Se si desidera eseguire l'elaborazione in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="780a9-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="780a9-119">Immettere le informazioni per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="780a9-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="780a9-120">Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="780a9-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="780a9-121">Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="780a9-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="780a9-122">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="780a9-122">Select **OK**.</span></span> <span data-ttu-id="780a9-123">l'elaborazione verrà eseguita con i parametri impostati.</span><span class="sxs-lookup"><span data-stu-id="780a9-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="780a9-124">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="780a9-124">Select **OK**.</span></span>

## <a name="view-process-results"></a><span data-ttu-id="780a9-125">Visualizzare i risultati del processo</span><span class="sxs-lookup"><span data-stu-id="780a9-125">View Process Results</span></span>

<span data-ttu-id="780a9-126">In questo articolo viene descritto come visualizzare i risultati del processo di idoneità.</span><span class="sxs-lookup"><span data-stu-id="780a9-126">This article explains how to view eligibility process results.</span></span>

1.  <span data-ttu-id="780a9-127">Nell'area di lavoro **Gestione benefit**, sotto **Elaborazione**, selezionare **Risultati processo**.</span><span class="sxs-lookup"><span data-stu-id="780a9-127">In the **Benefits management** workspace, under **Processing**, select **Process results**.</span></span>

2.  <span data-ttu-id="780a9-128">Nel modulo **Risultati processo** sono specificati i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="780a9-128">In the **Process results** form, the following fields are specified:</span></span>

   | <span data-ttu-id="780a9-129">Campo</span><span class="sxs-lookup"><span data-stu-id="780a9-129">Field</span></span> | <span data-ttu-id="780a9-130">descrizione</span><span class="sxs-lookup"><span data-stu-id="780a9-130">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="780a9-131">**ID processo**</span><span class="sxs-lookup"><span data-stu-id="780a9-131">**Process ID**</span></span> | <span data-ttu-id="780a9-132">L'ID univoco per la combinazione di lavoratore, persona giuridica ed esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="780a9-132">The unique ID for the combination of Worker, Legal entity, and process run.</span></span> |
   | <span data-ttu-id="780a9-133">**Tipo di processo**</span><span class="sxs-lookup"><span data-stu-id="780a9-133">**Process type**</span></span> | <span data-ttu-id="780a9-134">Identifica il processo che è stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="780a9-134">This identifies the process that was run.</span></span> <span data-ttu-id="780a9-135">Ad esempio: Iscrizione.</span><span class="sxs-lookup"><span data-stu-id="780a9-135">For example:  Enrollment.</span></span> |
   | <span data-ttu-id="780a9-136">**Timbro data/ora**</span><span class="sxs-lookup"><span data-stu-id="780a9-136">**Time stamp**</span></span> | <span data-ttu-id="780a9-137">L'ora in cui è stato eseguito il processo di idoneità.</span><span class="sxs-lookup"><span data-stu-id="780a9-137">The time that the eligibility process was run.</span></span> |
   | <span data-ttu-id="780a9-138">**Persona giuridica**</span><span class="sxs-lookup"><span data-stu-id="780a9-138">**Legal entity**</span></span> | <span data-ttu-id="780a9-139">La persona giuridica specificata durante il processo di iscrizione.</span><span class="sxs-lookup"><span data-stu-id="780a9-139">The legal entity specified during the enrollment process.</span></span> |
   | <span data-ttu-id="780a9-140">**Lavoro**</span><span class="sxs-lookup"><span data-stu-id="780a9-140">**Worker**</span></span> | <span data-ttu-id="780a9-141">Lavoratore elaborato.</span><span class="sxs-lookup"><span data-stu-id="780a9-141">The worker who was processed.</span></span> |
   | <span data-ttu-id="780a9-142">\*\*Piano</span><span class="sxs-lookup"><span data-stu-id="780a9-142">\*\*Plan</span></span> | <span data-ttu-id="780a9-143">Il piano di benefit per cui è stata tentata l'iscrizione.</span><span class="sxs-lookup"><span data-stu-id="780a9-143">The Benefit plan that enrollment was attempted for.</span></span> |
   | <span data-ttu-id="780a9-144">**Regola di idoneità**</span><span class="sxs-lookup"><span data-stu-id="780a9-144">**Eligibility rule**</span></span> | <span data-ttu-id="780a9-145">La regola di idoneità che è stata elaborata.</span><span class="sxs-lookup"><span data-stu-id="780a9-145">The eligibility rule that was processed.</span></span> <span data-ttu-id="780a9-146">Se si è verificato un errore prima dell'esecuzione dell'idoneità, questo campo sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="780a9-146">If an error was encountered before eligibility was run, this will be blank.</span></span> <span data-ttu-id="780a9-147">Ad esempio: se non è stato definito un compenso per un lavoratore, il processo di idoneità non verrà eseguito e questo campo verrà lasciato vuoto.</span><span class="sxs-lookup"><span data-stu-id="780a9-147">For example: If compensation hasn't been defined for a worker, the eligibility process won't run, and this field will be left blank.</span></span> |
   | <span data-ttu-id="780a9-148">**Stato risultati**</span><span class="sxs-lookup"><span data-stu-id="780a9-148">**Result status**</span></span> | <span data-ttu-id="780a9-149">Questo sarà Idoneo o Non idoneo.</span><span class="sxs-lookup"><span data-stu-id="780a9-149">This will be Eligible or Ineligible.</span></span> <span data-ttu-id="780a9-150">Lo stato del risultato sarà Non idoneo se il lavoratore non ha soddisfatto i criteri della regola di idoneità, se al lavoratore mancano informazioni richieste come una frequenza di retribuzione o un compenso fisso o se nel piano di benefit mancano informazioni che impediscono ai lavoratori di essere iscritti.</span><span class="sxs-lookup"><span data-stu-id="780a9-150">The result status will be Ineligible if the worker didn’t meet the eligibility rule criteria, if the worker is missing required information such as a pay frequency or fixed compensation, or if there is information missing on the benefit plan that prevents workers from being enrolled.</span></span> |
   | <span data-ttu-id="780a9-151">**Messaggio risultati**</span><span class="sxs-lookup"><span data-stu-id="780a9-151">**Result message**</span></span> | <span data-ttu-id="780a9-152">Indica perché un lavoratore non è idoneo per un piano di benefit o se è stata approvata la regola di idoneità.</span><span class="sxs-lookup"><span data-stu-id="780a9-152">Indicates why a worker is ineligible for a benefit plan or if the eligibility rule passed.</span></span> |

