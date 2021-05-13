---
title: Creare modelli di orario di lavoro
description: I modelli di orario di lavoro definiscono le ore lavorative di una settimana e vengono utilizzati per generare gli orari di lavoro per un periodo di tempo.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed1981b7c1427c902f237f0aa95f63e89bc345ab
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920931"
---
# <a name="create-working-time-templates"></a><span data-ttu-id="46002-103">Creare modelli di orario di lavoro</span><span class="sxs-lookup"><span data-stu-id="46002-103">Create working time templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="46002-104">I modelli di orario di lavoro definiscono le ore lavorative di una settimana e vengono utilizzati per generare gli orari di lavoro per un periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="46002-104">Working time templates define the working hours throughout a week and are used to generate working times for a period of time.</span></span> <span data-ttu-id="46002-105">Questa procedura consente di definire un modello di orario di lavoro utilizzando le proprietà di programmazione dell'orario di lavoro per classificare gli intervalli di orario di lavoro.</span><span class="sxs-lookup"><span data-stu-id="46002-105">This procedure shows you how to define a working time template using working time scheduling properties for categorizing working time intervals.</span></span> <span data-ttu-id="46002-106">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati.</span><span class="sxs-lookup"><span data-stu-id="46002-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="46002-107">Andare a **Aree di lavoro > Gestione ciclo di vita risorse**.</span><span class="sxs-lookup"><span data-stu-id="46002-107">Go to **Workspaces > Resource lifecycle management**.</span></span>
1. <span data-ttu-id="46002-108">Selezionare **Modelli di orario di lavoro**</span><span class="sxs-lookup"><span data-stu-id="46002-108">Select **Working time templates**.</span></span>

## <a name="create-working-time-template"></a><span data-ttu-id="46002-109">Creare un modello di orario di lavoro</span><span class="sxs-lookup"><span data-stu-id="46002-109">Create working time template</span></span>

1. <span data-ttu-id="46002-110">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="46002-110">Select **New**.</span></span>
1. <span data-ttu-id="46002-111">Nel campo **Modello di orario di lavoro**, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="46002-111">In the **Working time template** field, type a value.</span></span>
1. <span data-ttu-id="46002-112">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="46002-112">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="46002-113">Espandere la sezione **Lunedì**.</span><span class="sxs-lookup"><span data-stu-id="46002-113">Expand the **Monday** section.</span></span>
1. <span data-ttu-id="46002-114">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="46002-114">Select **Add**.</span></span>
1. <span data-ttu-id="46002-115">Nel campo **Da** immettere un'ora.</span><span class="sxs-lookup"><span data-stu-id="46002-115">In the **From** field, enter a time.</span></span>
    * <span data-ttu-id="46002-116">Specificare l'ora in cui inizia il lavoro di mattina.</span><span class="sxs-lookup"><span data-stu-id="46002-116">Specify the time when work begins in the morning.</span></span>  
1. <span data-ttu-id="46002-117">Nel campo **A** immettere un'ora.</span><span class="sxs-lookup"><span data-stu-id="46002-117">In the **To** field, enter a time.</span></span>
    * <span data-ttu-id="46002-118">Specificare l'ora in cui i lavoratori iniziano la pausa pranzo.</span><span class="sxs-lookup"><span data-stu-id="46002-118">Specify the time when workers break for lunch.</span></span>  
1. <span data-ttu-id="46002-119">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="46002-119">Select **Add**.</span></span>
1. <span data-ttu-id="46002-120">Nel campo **Da** immettere un'ora.</span><span class="sxs-lookup"><span data-stu-id="46002-120">In the **From** field, enter a time.</span></span>
    * <span data-ttu-id="46002-121">Specificare l'ora in cui il lavoro riprende dopo il pranzo.</span><span class="sxs-lookup"><span data-stu-id="46002-121">Specify the time when work resumes after lunch.</span></span>  
1. <span data-ttu-id="46002-122">Nel campo **A** immettere un'ora.</span><span class="sxs-lookup"><span data-stu-id="46002-122">In the **To** field, enter a time.</span></span>
    * <span data-ttu-id="46002-123">Specificare la fine della giornata lavorativa.</span><span class="sxs-lookup"><span data-stu-id="46002-123">Specify the end of the work day.</span></span>  

## <a name="replicate-working-times-to-all-week-days"></a><span data-ttu-id="46002-124">Replicare gli orari di lavoro per tutti i giorni della settimana</span><span class="sxs-lookup"><span data-stu-id="46002-124">Replicate working times to all week days</span></span>

1. <span data-ttu-id="46002-125">Seleziona **Copia giorno**.</span><span class="sxs-lookup"><span data-stu-id="46002-125">Select **Copy day**.</span></span>
    * <span data-ttu-id="46002-126">Copiare le definizioni di orario di lavoro da lunedì a martedì.</span><span class="sxs-lookup"><span data-stu-id="46002-126">Copy the working times definitions from Monday to Tuesday.</span></span>  
1. <span data-ttu-id="46002-127">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="46002-127">Select **OK**.</span></span>
1. <span data-ttu-id="46002-128">Seleziona **Copia giorno**.</span><span class="sxs-lookup"><span data-stu-id="46002-128">Select **Copy day**.</span></span>
    * <span data-ttu-id="46002-129">Copiare le definizioni di orario di lavoro da lunedì a mercoledì.</span><span class="sxs-lookup"><span data-stu-id="46002-129">Copy the working times definitions from Monday to Wednesday.</span></span>  
1. <span data-ttu-id="46002-130">Selezionare un'opzione nel campo **Al giorno feriale**.</span><span class="sxs-lookup"><span data-stu-id="46002-130">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="46002-131">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="46002-131">Select **OK**.</span></span>
1. <span data-ttu-id="46002-132">Seleziona **Copia giorno**.</span><span class="sxs-lookup"><span data-stu-id="46002-132">Select **Copy day**.</span></span>
    * <span data-ttu-id="46002-133">Copiare le definizioni di orario di lavoro da lunedì a giovedì.</span><span class="sxs-lookup"><span data-stu-id="46002-133">Copy the working times definitions from Monday to Thursday.</span></span>  
1. <span data-ttu-id="46002-134">Selezionare un'opzione nel campo **Al giorno feriale**.</span><span class="sxs-lookup"><span data-stu-id="46002-134">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="46002-135">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="46002-135">Select **OK**.</span></span>
1. <span data-ttu-id="46002-136">Seleziona **Copia giorno**.</span><span class="sxs-lookup"><span data-stu-id="46002-136">Select **Copy day**.</span></span>
    * <span data-ttu-id="46002-137">Copiare le definizioni di orario di lavoro da lunedì a venerdì.</span><span class="sxs-lookup"><span data-stu-id="46002-137">Copy the working times definitions from Monday to Friday.</span></span>  
1. <span data-ttu-id="46002-138">Selezionare un'opzione nel campo **Al giorno feriale**.</span><span class="sxs-lookup"><span data-stu-id="46002-138">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="46002-139">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="46002-139">Select **OK**.</span></span>

## <a name="define-time-slots-for-special-operations"></a><span data-ttu-id="46002-140">Definire le fasce orarie per le operazioni speciali</span><span class="sxs-lookup"><span data-stu-id="46002-140">Define time slots for special operations</span></span>

1. <span data-ttu-id="46002-141">Espandere la sezione **Venerdì**.</span><span class="sxs-lookup"><span data-stu-id="46002-141">Expand the **Friday** section.</span></span>
1. <span data-ttu-id="46002-142">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="46002-142">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="46002-143">Nel campo **Proprietà** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="46002-143">In the **Property** field, enter or select a value.</span></span>
1. <span data-ttu-id="46002-144">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="46002-144">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="46002-145">Nel campo **Proprietà** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="46002-145">In the **Property** field, enter or select a value.</span></span>

## <a name="mark-weekend-days-as-closed-for-pickup"></a><span data-ttu-id="46002-146">Contrassegnare i giorni del fine settimana come chiusi per prelievo</span><span class="sxs-lookup"><span data-stu-id="46002-146">Mark weekend days as closed for pickup</span></span>

1. <span data-ttu-id="46002-147">Espandere la sezione **Sabato**.</span><span class="sxs-lookup"><span data-stu-id="46002-147">Expand the **Saturday** section.</span></span>
1. <span data-ttu-id="46002-148">Selezionare *Sì* nel campo **Chiuso per prelievo**.</span><span class="sxs-lookup"><span data-stu-id="46002-148">Select *Yes* in the **Closed for pickup** field.</span></span>
1. <span data-ttu-id="46002-149">Espandere la sezione **Domenica**.</span><span class="sxs-lookup"><span data-stu-id="46002-149">Expand the **Sunday** section.</span></span>
1. <span data-ttu-id="46002-150">Selezionare *Sì* nel campo **Chiuso per prelievo**.</span><span class="sxs-lookup"><span data-stu-id="46002-150">Select *Yes* in the **Closed for pickup** field.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]