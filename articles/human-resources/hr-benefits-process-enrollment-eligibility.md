---
title: Elaborare l'idoneità di iscrizione
description: In questo articolo viene descritto come eseguire l'elaborazione dell'idoneità di iscrizione.
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
ms.openlocfilehash: 0344c48460a7d1540481e09ba106526e119de72b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009489"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="19e00-103">Elaborare l'idoneità di iscrizione</span><span class="sxs-lookup"><span data-stu-id="19e00-103">Process enrollment eligibility</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="19e00-104">In questo articolo viene descritto come eseguire l'elaborazione dell'idoneità di iscrizione.</span><span class="sxs-lookup"><span data-stu-id="19e00-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="19e00-105">Nell'area di lavoro **Gestione benefit**, sotto **Elaborazione**, selezionare **Elaborazione idoneità iscrizione**.</span><span class="sxs-lookup"><span data-stu-id="19e00-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="19e00-106">Nella finestra di dialogo **Esegui elaborazione idoneità iscrizione a benefit**, specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="19e00-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="19e00-107">Campo</span><span class="sxs-lookup"><span data-stu-id="19e00-107">Field</span></span> | <span data-ttu-id="19e00-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19e00-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="19e00-109">Periodo di iscrizione</span><span class="sxs-lookup"><span data-stu-id="19e00-109">Enrollment period</span></span> | <span data-ttu-id="19e00-110">Il periodo di iscrizione per il quale elaborare l'idoneità di iscrizione.</span><span class="sxs-lookup"><span data-stu-id="19e00-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="19e00-111">Persona giuridica</span><span class="sxs-lookup"><span data-stu-id="19e00-111">Legal entity</span></span> | <span data-ttu-id="19e00-112">La persona giuridica per la quale elaborare l'idoneità di iscrizione.</span><span class="sxs-lookup"><span data-stu-id="19e00-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="19e00-113">Lavoro</span><span class="sxs-lookup"><span data-stu-id="19e00-113">Worker</span></span> | <span data-ttu-id="19e00-114">Il lavoratore per il quale elaborare l'idoneità di iscrizione.</span><span class="sxs-lookup"><span data-stu-id="19e00-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="19e00-115">Se questo campo viene lasciato vuoto, l'idoneità di iscrizione verrà elaborata per tutti i lavoratori.</span><span class="sxs-lookup"><span data-stu-id="19e00-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="19e00-116">Piano di benefit</span><span class="sxs-lookup"><span data-stu-id="19e00-116">Benefit plan</span></span> | <span data-ttu-id="19e00-117">Il piano di benefit per il quale elaborare l'idoneità di iscrizione.</span><span class="sxs-lookup"><span data-stu-id="19e00-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="19e00-118">Se si desidera eseguire l'elaborazione in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="19e00-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="19e00-119">Immettere le informazioni per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="19e00-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="19e00-120">Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="19e00-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="19e00-121">Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="19e00-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="19e00-122">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="19e00-122">Select **OK**.</span></span> <span data-ttu-id="19e00-123">l'elaborazione verrà eseguita con i parametri impostati.</span><span class="sxs-lookup"><span data-stu-id="19e00-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="19e00-124">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="19e00-124">Select **OK**.</span></span>
