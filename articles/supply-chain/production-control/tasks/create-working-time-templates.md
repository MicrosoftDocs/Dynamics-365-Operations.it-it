---
title: Creare modelli di orario di lavoro
description: I modelli di orario di lavoro definiscono le ore lavorative di una settimana e vengono utilizzati per generare gli orari di lavoro per un periodo di tempo.
author: sorenva
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f41ae891625fea77eed6650a5bc1fb800a08ee8f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210711"
---
# <a name="create-working-time-templates"></a><span data-ttu-id="95d35-103">Creare modelli di orario di lavoro</span><span class="sxs-lookup"><span data-stu-id="95d35-103">Create working time templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="95d35-104">I modelli di orario di lavoro definiscono le ore lavorative di una settimana e vengono utilizzati per generare gli orari di lavoro per un periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="95d35-104">Working time templates define the working hours throughout a week and are used to generate working times for a period of time.</span></span> <span data-ttu-id="95d35-105">Questa procedura consente di definire un modello di orario di lavoro utilizzando le proprietà di programmazione dell'orario di lavoro per classificare gli intervalli di orario di lavoro.</span><span class="sxs-lookup"><span data-stu-id="95d35-105">This procedure shows you how to define a working time template using working time scheduling properties for categorizing working time intervals.</span></span> <span data-ttu-id="95d35-106">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati.</span><span class="sxs-lookup"><span data-stu-id="95d35-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="95d35-107">Andare a Tutte le aree di lavoro > Gestione ciclo di vita risorse.</span><span class="sxs-lookup"><span data-stu-id="95d35-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="95d35-108">Fare clic su Modelli di orario di lavoro.</span><span class="sxs-lookup"><span data-stu-id="95d35-108">Click Working time templates.</span></span>

## <a name="create-working-time-template"></a><span data-ttu-id="95d35-109">Creare un modello di orario di lavoro</span><span class="sxs-lookup"><span data-stu-id="95d35-109">Create working time template</span></span>
1. <span data-ttu-id="95d35-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="95d35-110">Click New.</span></span>
2. <span data-ttu-id="95d35-111">Nel campo Modello di orario di lavoro, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="95d35-111">In the Working time template field, type a value.</span></span>
3. <span data-ttu-id="95d35-112">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="95d35-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="95d35-113">Espandere la sezione Lunedì.</span><span class="sxs-lookup"><span data-stu-id="95d35-113">Expand the Monday section.</span></span>
5. <span data-ttu-id="95d35-114">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="95d35-114">Click Add.</span></span>
6. <span data-ttu-id="95d35-115">Nel campo Da immettere un'ora.</span><span class="sxs-lookup"><span data-stu-id="95d35-115">In the From field, enter a time.</span></span>
    * <span data-ttu-id="95d35-116">Specificare l'ora in cui inizia il lavoro di mattina.</span><span class="sxs-lookup"><span data-stu-id="95d35-116">Specify the time when work begins in the morning.</span></span>  
7. <span data-ttu-id="95d35-117">Nel campo A immettere un'ora.</span><span class="sxs-lookup"><span data-stu-id="95d35-117">In the To field, enter a time.</span></span>
    * <span data-ttu-id="95d35-118">Specificare l'ora in cui i lavoratori iniziano la pausa pranzo.</span><span class="sxs-lookup"><span data-stu-id="95d35-118">Specify the time when workers break for lunch.</span></span>  
8. <span data-ttu-id="95d35-119">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="95d35-119">Click Add.</span></span>
9. <span data-ttu-id="95d35-120">Nel campo Da immettere un'ora.</span><span class="sxs-lookup"><span data-stu-id="95d35-120">In the From field, enter a time.</span></span>
    * <span data-ttu-id="95d35-121">Specificare l'ora in cui il lavoro riprende dopo il pranzo.</span><span class="sxs-lookup"><span data-stu-id="95d35-121">Specify the time when work resumes after lunch.</span></span>  
10. <span data-ttu-id="95d35-122">Nel campo A immettere un'ora.</span><span class="sxs-lookup"><span data-stu-id="95d35-122">In the To field, enter a time.</span></span>
    * <span data-ttu-id="95d35-123">Specificare la fine della giornata lavorativa.</span><span class="sxs-lookup"><span data-stu-id="95d35-123">Specify the end of the work day.</span></span>  

## <a name="replicate-working-times-to-all-week-days"></a><span data-ttu-id="95d35-124">Replicare gli orari di lavoro per tutti i giorni della settimana</span><span class="sxs-lookup"><span data-stu-id="95d35-124">Replicate working times to all week days</span></span>
1. <span data-ttu-id="95d35-125">Fare clic su Copia giorno.</span><span class="sxs-lookup"><span data-stu-id="95d35-125">Click Copy day.</span></span>
    * <span data-ttu-id="95d35-126">Copiare le definizioni di orario di lavoro da lunedì a martedì.</span><span class="sxs-lookup"><span data-stu-id="95d35-126">Copy the working times definitions from Monday to Tuesday.</span></span>  
2. <span data-ttu-id="95d35-127">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="95d35-127">Click OK.</span></span>
3. <span data-ttu-id="95d35-128">Fare clic su Copia giorno.</span><span class="sxs-lookup"><span data-stu-id="95d35-128">Click Copy day.</span></span>
    * <span data-ttu-id="95d35-129">Copiare le definizioni di orario di lavoro da lunedì a mercoledì.</span><span class="sxs-lookup"><span data-stu-id="95d35-129">Copy the working times definitions from Monday to Wednesday.</span></span>  
4. <span data-ttu-id="95d35-130">Selezionare un'opzione nel campo Al giorno feriale.</span><span class="sxs-lookup"><span data-stu-id="95d35-130">In the To weekday field, select an option.</span></span>
5. <span data-ttu-id="95d35-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="95d35-131">Click OK.</span></span>
6. <span data-ttu-id="95d35-132">Fare clic su Copia giorno.</span><span class="sxs-lookup"><span data-stu-id="95d35-132">Click Copy day.</span></span>
    * <span data-ttu-id="95d35-133">Copiare le definizioni di orario di lavoro da lunedì a giovedì.</span><span class="sxs-lookup"><span data-stu-id="95d35-133">Copy the working times definitions from Monday to Thursday.</span></span>  
7. <span data-ttu-id="95d35-134">Selezionare un'opzione nel campo Al giorno feriale.</span><span class="sxs-lookup"><span data-stu-id="95d35-134">In the To weekday field, select an option.</span></span>
8. <span data-ttu-id="95d35-135">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="95d35-135">Click OK.</span></span>
9. <span data-ttu-id="95d35-136">Fare clic su Copia giorno.</span><span class="sxs-lookup"><span data-stu-id="95d35-136">Click Copy day.</span></span>
    * <span data-ttu-id="95d35-137">Copiare le definizioni di orario di lavoro da lunedì a venerdì.</span><span class="sxs-lookup"><span data-stu-id="95d35-137">Copy the working times definitions from Monday to Friday.</span></span>  
10. <span data-ttu-id="95d35-138">Selezionare un'opzione nel campo Al giorno feriale.</span><span class="sxs-lookup"><span data-stu-id="95d35-138">In the To weekday field, select an option.</span></span>
11. <span data-ttu-id="95d35-139">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="95d35-139">Click OK.</span></span>

## <a name="define-time-slots-for-special-operations"></a><span data-ttu-id="95d35-140">Definire le fasce orarie per le operazioni speciali</span><span class="sxs-lookup"><span data-stu-id="95d35-140">Define time slots for special operations</span></span>
1. <span data-ttu-id="95d35-141">Espandere la sezione Venerdì.</span><span class="sxs-lookup"><span data-stu-id="95d35-141">Expand the Friday section.</span></span>
2. <span data-ttu-id="95d35-142">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="95d35-142">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="95d35-143">Nel campo Proprietà immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="95d35-143">In the Property field, enter or select a value.</span></span>
4. <span data-ttu-id="95d35-144">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="95d35-144">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="95d35-145">Nel campo Proprietà immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="95d35-145">In the Property field, enter or select a value.</span></span>

## <a name="mark-weekend-days-as-closed-for-pickup"></a><span data-ttu-id="95d35-146">Contrassegnare i giorni del fine settimana come chiusi per prelievo</span><span class="sxs-lookup"><span data-stu-id="95d35-146">Mark weekend days as closed for pickup</span></span>
1. <span data-ttu-id="95d35-147">Espandere la sezione Sabato.</span><span class="sxs-lookup"><span data-stu-id="95d35-147">Expand the Saturday section.</span></span>
2. <span data-ttu-id="95d35-148">Selezionare Sì nel campo Chiuso per prelievo.</span><span class="sxs-lookup"><span data-stu-id="95d35-148">Select Yes in the Closed for pickup field.</span></span>
3. <span data-ttu-id="95d35-149">Espandere la sezione Domenica.</span><span class="sxs-lookup"><span data-stu-id="95d35-149">Expand the Sunday section.</span></span>
4. <span data-ttu-id="95d35-150">Selezionare Sì nel campo Chiuso per prelievo.</span><span class="sxs-lookup"><span data-stu-id="95d35-150">Select Yes in the Closed for pickup field.</span></span>

