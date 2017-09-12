--- 
title: Creare una regola kanban di prelievo
description: Questa procedura illustra l'impostazione necessaria per creare una regola kanban di prelievo per il trasferimento di materiale in un ambiente lean manufacturing.
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 02c7133d2e02b27fb428874deeda21e2bab28fb6
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-withdrawal-kanban-rule"></a><span data-ttu-id="dc8e9-103">Creare una regola kanban di prelievo</span><span class="sxs-lookup"><span data-stu-id="dc8e9-103">Create a withdrawal kanban rule</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dc8e9-104">Questa procedura illustra l'impostazione necessaria per creare una regola kanban di prelievo per il trasferimento di materiale in un ambiente lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-104">This procedure shows the setup that is needed to create a withdrawal kanban rule for transferring material in a lean environment.</span></span> <span data-ttu-id="dc8e9-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="dc8e9-106">Questa procedura è destinata all'addetto procedure tecniche o al responsabile flusso del valore che prepara il rifornimento di un materiale nuovo o modificato.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-106">This procedure is intended for the Process Engineer or the Value Stream Manager, as they prepare replenishment of new or modified material.</span></span>


## <a name="create-new-kanban-rule"></a><span data-ttu-id="dc8e9-107">Creare una nuova regola kanban</span><span class="sxs-lookup"><span data-stu-id="dc8e9-107">Create new kanban rule</span></span>
1. <span data-ttu-id="dc8e9-108">Passare a Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-108">Go to Kanban rules.</span></span>
2. <span data-ttu-id="dc8e9-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-109">Click New.</span></span>
3. <span data-ttu-id="dc8e9-110">Selezionare "Prelievo" nel campo Tipo.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="dc8e9-111">Il tipo Prelievo viene utilizzato per le regole kanban per trasferire materiale o merci.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-111">The Withdrawal type is used for kanban rules to transfer material or goods.</span></span>  
4. <span data-ttu-id="dc8e9-112">Nel campo Prima attività piano immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-112">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="dc8e9-113">Selezionare ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-113">Select ReplenishSpeakerComponents.</span></span>   <span data-ttu-id="dc8e9-114">Questa attività viene impostata per spostare i componenti dal magazzino 11, ubicazione 11 al magazzino 12 e ubicazione 12.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-114">This activity is set up to move components from warehouse 11, location 11 to warehouse 12, and location 12.</span></span>  
5. <span data-ttu-id="dc8e9-115">Nel campo Prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-115">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="dc8e9-116">Selezionare M0007.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-116">Select M0007.</span></span>  
6. <span data-ttu-id="dc8e9-117">Nel campo Lead time immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-117">In the Lead time field, enter a number.</span></span>
    * <span data-ttu-id="dc8e9-118">Ad esempio, 60.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-118">For example, 60.</span></span>  
7. <span data-ttu-id="dc8e9-119">Nel campo Unità di misura immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-119">In the Unit of measure field, enter or select a value.</span></span>
    * <span data-ttu-id="dc8e9-120">Ad esempio, Minuti.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-120">For example, Minutes.</span></span>  

## <a name="set-quantities-for-kanban"></a><span data-ttu-id="dc8e9-121">Impostare le quantità per il kanban</span><span class="sxs-lookup"><span data-stu-id="dc8e9-121">Set quantities for kanban</span></span>
1. <span data-ttu-id="dc8e9-122">Impostare Quantità predefinita su '5'.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-122">Set Default quantity to '5'.</span></span>
    * <span data-ttu-id="dc8e9-123">Si tratta della quantità che verrà trasferita per ogni kanban.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-123">This is the quantity that will be transferred for each kanban.</span></span>  
2. <span data-ttu-id="dc8e9-124">Nel campo Kanban a quantità fissa immettere "2".</span><span class="sxs-lookup"><span data-stu-id="dc8e9-124">In the Fixed kanban quantity field, enter '2'.</span></span>
    * <span data-ttu-id="dc8e9-125">Si tratta della quantità di kanban che devono essere attivi.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-125">This is the amount of kanbans that should be active.</span></span> <span data-ttu-id="dc8e9-126">In questo caso, 2 kanban che ne trasferiscono 5 ognuno.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-126">In this case, 2 kanbans transferring 5 each.</span></span>  
3. <span data-ttu-id="dc8e9-127">Nel campo Avviso per limite minimo immettere '1'.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-127">In the Alert boundary minimum field, enter '1'.</span></span>
    * <span data-ttu-id="dc8e9-128">Utilizzato per tenere traccia dell'importo minimo di kanban completi che devono essere nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-128">Used to keep track of the minimum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="dc8e9-129">Ad esempio, questo viene utilizzato nella panoramica della quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-129">For example, this is used on the kanban quantity overview.</span></span>  
4. <span data-ttu-id="dc8e9-130">Nel campo Avviso per limite massimo immettere '2'.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-130">In the Alert boundary maximum field, enter '2'.</span></span>
    * <span data-ttu-id="dc8e9-131">Utilizzato per tenere traccia dell'importo massimo di kanban completi che devono essere nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-131">Used to keep track of the maximum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="dc8e9-132">Ad esempio, questo viene utilizzato nella panoramica della quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-132">For example, this is used on the kanban quantity overview.</span></span>  

## <a name="create-kanbans"></a><span data-ttu-id="dc8e9-133">Crea kanban</span><span class="sxs-lookup"><span data-stu-id="dc8e9-133">Create kanbans</span></span>
1. <span data-ttu-id="dc8e9-134">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-134">Click Save.</span></span>
    * <span data-ttu-id="dc8e9-135">La regola kanban deve essere salvata prima di poter creare i kanban.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-135">The kanban rule needs to be saved before kanbans can be created.</span></span>  
2. <span data-ttu-id="dc8e9-136">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-136">Click Add.</span></span>
    * <span data-ttu-id="dc8e9-137">Non sono presenti kanban attivi, in quanto il "Numero di nuovi kanban" suggerito è 2, che corrisponde a "Kanban a quantità fissa".</span><span class="sxs-lookup"><span data-stu-id="dc8e9-137">Note that there are no active kanbans because the suggested 'Number of new kanbans' is 2, which is equal to the 'Fixed kanban quantity'.</span></span>  
3. <span data-ttu-id="dc8e9-138">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-138">Click Create.</span></span>
    * <span data-ttu-id="dc8e9-139">Ciò creerà due kanban.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-139">This will create two kanbans.</span></span>  
    * <span data-ttu-id="dc8e9-140">2 kanban, ciascuno per 5, sono stati creati per questa regola kanban di prelievo.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-140">Note that 2 kanbans, for 5 each, was created for this withdrawal kanban rule.</span></span>  <span data-ttu-id="dc8e9-141">Si tratta dell'ultimo passaggio di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="dc8e9-141">This is the last step in this procedure.</span></span>  

