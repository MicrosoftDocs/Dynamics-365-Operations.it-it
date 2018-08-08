--- 
title: "Creare una regola kanban a quantità fissa per la produzione"
description: "Questa procedura è incentrata sull'impostazione necessaria per creare una regola kanban di produzione fissa per attivare le attività di trasformazione, in una cella di lavoro, in un ambiente lean manufacturing."
author: ChristianRytt
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 555d79e8bacbae0287472e68701a04a3c1d635aa
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---
# <a name="create-a-fixed-quantity-kanban-rule-for-manufacturing"></a><span data-ttu-id="1fd13-103">Creare una regola kanban a quantità fissa per la produzione</span><span class="sxs-lookup"><span data-stu-id="1fd13-103">Create a fixed quantity kanban rule for manufacturing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1fd13-104">Questa procedura è incentrata sull'impostazione necessaria per creare una regola kanban di produzione fissa per attivare le attività di trasformazione, in una cella di lavoro, in un ambiente lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="1fd13-104">This procedure focuses on the setup needed to create a fixed manufacturing kanban rule for triggering transforming activities, at a work cell, in a lean environment.</span></span> <span data-ttu-id="1fd13-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="1fd13-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="1fd13-106">Questa procedura è destinata all'addetto procedure tecniche o al responsabile flusso del valore che prepara la produzione di un prodotto nuovo o modificato.</span><span class="sxs-lookup"><span data-stu-id="1fd13-106">This procedure is intended for the Process Engineer or the Value Stream Manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-new-kanban-rule"></a><span data-ttu-id="1fd13-107">Creare una nuova regola kanban</span><span class="sxs-lookup"><span data-stu-id="1fd13-107">Create new kanban rule</span></span>
1. <span data-ttu-id="1fd13-108">Passare a Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="1fd13-108">Go to Kanban rules.</span></span>
2. <span data-ttu-id="1fd13-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="1fd13-109">Click New.</span></span>
    * <span data-ttu-id="1fd13-110">Si noti che il tipo predefinito è Produzione e la Strategia di rifornimento è Fisso.</span><span class="sxs-lookup"><span data-stu-id="1fd13-110">Notice that the default Type is Manufacturing and Replenishment strategy is Fixed.</span></span> <span data-ttu-id="1fd13-111">Non è necessario modificare questi parametri.</span><span class="sxs-lookup"><span data-stu-id="1fd13-111">You do not have to change these parameters.</span></span>  
3. <span data-ttu-id="1fd13-112">Nel campo Prima attività piano immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1fd13-112">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="1fd13-113">Si tratta dell'attività che verrà eseguita per i kanban creati in base alla regola kanban.</span><span class="sxs-lookup"><span data-stu-id="1fd13-113">This is the activity that will be performed for kanbans created based on this kanban rule.</span></span>  <span data-ttu-id="1fd13-114">Selezionare 'SpeakerTestAndPackaging'.</span><span class="sxs-lookup"><span data-stu-id="1fd13-114">Select 'SpeakerTestAndPackaging'.</span></span>  
4. <span data-ttu-id="1fd13-115">Espandere la sezione Dettagli.</span><span class="sxs-lookup"><span data-stu-id="1fd13-115">Expand the Details section.</span></span>
5. <span data-ttu-id="1fd13-116">Nel campo Prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1fd13-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="1fd13-117">Selezionare L0050.</span><span class="sxs-lookup"><span data-stu-id="1fd13-117">Select L0050.</span></span>  
6. <span data-ttu-id="1fd13-118">Nel campo Unità di misura immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1fd13-118">In the Unit of measure field, enter or select a value.</span></span>
    * <span data-ttu-id="1fd13-119">Selezionare i minuti.</span><span class="sxs-lookup"><span data-stu-id="1fd13-119">Select minutes.</span></span>  
7. <span data-ttu-id="1fd13-120">Nel campo Lead time immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1fd13-120">In the Lead time field, enter a number.</span></span>
    * <span data-ttu-id="1fd13-121">Immettere 5.</span><span class="sxs-lookup"><span data-stu-id="1fd13-121">Enter 5.</span></span>  

## <a name="set-quantities"></a><span data-ttu-id="1fd13-122">Impostare le quantità</span><span class="sxs-lookup"><span data-stu-id="1fd13-122">Set quantities</span></span>
1. <span data-ttu-id="1fd13-123">Espandere la sezione Quantità.</span><span class="sxs-lookup"><span data-stu-id="1fd13-123">Expand the Quantities section.</span></span>
2. <span data-ttu-id="1fd13-124">Impostare Quantità predefinita su '10'.</span><span class="sxs-lookup"><span data-stu-id="1fd13-124">Set Default quantity to '10'.</span></span>
    * <span data-ttu-id="1fd13-125">Si tratta della quantità che verrà trasferita per ogni kanban.</span><span class="sxs-lookup"><span data-stu-id="1fd13-125">This is the quantity that will be transferred for each kanban.</span></span>  
3. <span data-ttu-id="1fd13-126">Selezionare la casella di controllo Scostamento quantità prodotto.</span><span class="sxs-lookup"><span data-stu-id="1fd13-126">Select the Product quantity variance check box.</span></span>
    * <span data-ttu-id="1fd13-127">Con questo, i kanban selezionati possono essere completati con uno scostamento dalla quantità predefinita.</span><span class="sxs-lookup"><span data-stu-id="1fd13-127">With this, selected kanbans can be completed with a variance from the default quantity.</span></span>  <span data-ttu-id="1fd13-128">Per consentire il completamento dei kanban con una quantità da 8 a 12, impostare entrambi gli scostamenti su 2.</span><span class="sxs-lookup"><span data-stu-id="1fd13-128">To allow kanbans to be completed with a quantity from 8 to 12, set both variances to 2.</span></span>  
4. <span data-ttu-id="1fd13-129">Impostare Scostamento al di sotto su '2'.</span><span class="sxs-lookup"><span data-stu-id="1fd13-129">Set Variance below to '2'.</span></span>
    * <span data-ttu-id="1fd13-130">Questo permetterà il completamento sul valore inferiore 10 - 2 = 8</span><span class="sxs-lookup"><span data-stu-id="1fd13-130">This will allow completing down to 10 - 2 = 8</span></span>  
5. <span data-ttu-id="1fd13-131">Impostare Scostamento al di sopra su '2'.</span><span class="sxs-lookup"><span data-stu-id="1fd13-131">Set Variance above to '2'.</span></span>
    * <span data-ttu-id="1fd13-132">Questo permetterà il completamento sul valore superiore 10 + 2 = 12</span><span class="sxs-lookup"><span data-stu-id="1fd13-132">This will allow completing up to 10 + 2 = 12</span></span>  
6. <span data-ttu-id="1fd13-133">Nel campo Kanban a quantità fissa immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1fd13-133">In the Fixed kanban quantity field, enter a number.</span></span>
    * <span data-ttu-id="1fd13-134">Si tratta della quantità di kanban che devono essere attivi.</span><span class="sxs-lookup"><span data-stu-id="1fd13-134">This is the amount of kanbans that should be active.</span></span> <span data-ttu-id="1fd13-135">In questo caso, 5 kanban che elaborano 10 ognuno.</span><span class="sxs-lookup"><span data-stu-id="1fd13-135">In this case, 5 kanbans processing 10 each.</span></span>  
7. <span data-ttu-id="1fd13-136">Nel campo Avviso per limite minimo immettere '2'.</span><span class="sxs-lookup"><span data-stu-id="1fd13-136">In the Alert boundary minimum field, enter '2'.</span></span>
    * <span data-ttu-id="1fd13-137">Utilizzato per tenere traccia dell'importo minimo di kanban completi che devono essere nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="1fd13-137">Used to keep track of the minimum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="1fd13-138">Ad esempio, questo viene utilizzato nella panoramica della quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="1fd13-138">For example, this is used on the kanban quantity overview.</span></span>  
8. <span data-ttu-id="1fd13-139">Nel campo Avviso per limite massimo immettere '4'.</span><span class="sxs-lookup"><span data-stu-id="1fd13-139">In the Alert boundary maximum field, enter '4'.</span></span>
    * <span data-ttu-id="1fd13-140">Utilizzato per tenere traccia dell'importo massimo di kanban completi che devono essere nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="1fd13-140">Used to keep track of the maximum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="1fd13-141">Ad esempio, questo viene utilizzato nella panoramica della quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="1fd13-141">For example, this is used on the kanban quantity overview.</span></span>  
9. <span data-ttu-id="1fd13-142">Nel campo Quantità di pianificazione automatica immettere '1'.</span><span class="sxs-lookup"><span data-stu-id="1fd13-142">In the Automatic planning quantity field, enter '1'.</span></span>
    * <span data-ttu-id="1fd13-143">Impostare questo su 1 indica che ogni kanban verrà automaticamente pianificato.</span><span class="sxs-lookup"><span data-stu-id="1fd13-143">Setting this to 1 means that every kanban will be automatically planned.</span></span>   <span data-ttu-id="1fd13-144">Se fosse specificato 3, i kanban non verrebbero pianificati fino a che 3 kanban vuoti sono pronti per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1fd13-144">If we entered 3, the kanbans would not be planned until 3 empty kanbans are ready for planning.</span></span> <span data-ttu-id="1fd13-145">Questa opzione è utile per raggruppare il lavoro ed evitare troppe impostazioni.</span><span class="sxs-lookup"><span data-stu-id="1fd13-145">This is useful for grouping work and avoiding too much setup.</span></span>  

## <a name="create-kanbans"></a><span data-ttu-id="1fd13-146">Creare kanban</span><span class="sxs-lookup"><span data-stu-id="1fd13-146">Create Kanbans</span></span>
1. <span data-ttu-id="1fd13-147">Espandere la sezione Kanban.</span><span class="sxs-lookup"><span data-stu-id="1fd13-147">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="1fd13-148">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="1fd13-148">Click Save.</span></span>
    * <span data-ttu-id="1fd13-149">La regola kanban deve essere salvata prima di poter creare i kanban.</span><span class="sxs-lookup"><span data-stu-id="1fd13-149">The kanban rule needs to be saved before kanbans can be created.</span></span>  
3. <span data-ttu-id="1fd13-150">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="1fd13-150">Click Add.</span></span>
    * <span data-ttu-id="1fd13-151">Si noti che non sono presenti kanban attivi, in quanto il 'Numero di nuovi kanban' suggerito è 5.</span><span class="sxs-lookup"><span data-stu-id="1fd13-151">Note that there are no active kanbans, due to this the suggested 'Number of new kanbans' are 5.</span></span> <span data-ttu-id="1fd13-152">Questo corrisponde a 'Kanban a quantità fissa'.</span><span class="sxs-lookup"><span data-stu-id="1fd13-152">This is equal to the 'Fixed kanban quantity'.</span></span>  
4. <span data-ttu-id="1fd13-153">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="1fd13-153">Click Create.</span></span>
    * <span data-ttu-id="1fd13-154">Ciò creerà 5 kanban.</span><span class="sxs-lookup"><span data-stu-id="1fd13-154">This will create 5 kanbans.</span></span>  
    * <span data-ttu-id="1fd13-155">Si noti che 5 kanban, ciascuno per 10, sono stati creati per questa regola kanban di produzione.</span><span class="sxs-lookup"><span data-stu-id="1fd13-155">Note that 5 kanbans, for 10 each, was created for this manufacturing kanban rule.</span></span> <span data-ttu-id="1fd13-156">Si tratta dell'ultimo passaggio di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="1fd13-156">This is the last step in this procedure.</span></span>  


