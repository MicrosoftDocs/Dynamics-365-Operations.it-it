--- 
title: "Aggiungere criteri di calcolo di quantità kanban a una regola kanban"
description: "Questa procedura riguarda la creazione dei criteri di calcolo della quantità kanban e la relativa aggiunta a una regola kanban per ottimizzare la dimensione e le quantità kanban."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6a947d4a5302c6ed1848396d50cfbfcb78aabf97
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a><span data-ttu-id="ac15d-103">Aggiungere criteri di calcolo di quantità kanban a una regola kanban</span><span class="sxs-lookup"><span data-stu-id="ac15d-103">Add a kanban quantity calculation policy to a kanban rule</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ac15d-104">Questa procedura riguarda la creazione dei criteri di calcolo della quantità kanban e la relativa aggiunta a una regola kanban per ottimizzare la dimensione e le quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="ac15d-104">This procedure focuses on creating a kanban quantity calculation policy and adding it to a kanban rule to optimize the kanban size and quantities.</span></span> <span data-ttu-id="ac15d-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="ac15d-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="ac15d-106">Questa procedura è destinata al responsabile del flusso del valore.</span><span class="sxs-lookup"><span data-stu-id="ac15d-106">This procedure is intended for the value stream manager.</span></span> <span data-ttu-id="ac15d-107">Questa procedura è un prerequisito per creare la procedura Calcolare suggerimenti su quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="ac15d-107">This procedure is a prerequisite for creating the procedure Calculate kanban quantity suggestions.</span></span> 


## <a name="create-a-kanban-quantity-calculation-policy"></a><span data-ttu-id="ac15d-108">Creare criteri di calcolo delle quantità kanban</span><span class="sxs-lookup"><span data-stu-id="ac15d-108">Create a kanban quantity calculation policy</span></span>
1. <span data-ttu-id="ac15d-109">Andare a Controllo produzione > Attività periodiche > Calcolo quantità kanban > Criteri di calcolo quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="ac15d-109">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban quantity calculation policies.</span></span>
2. <span data-ttu-id="ac15d-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ac15d-110">Click New.</span></span>
3. <span data-ttu-id="ac15d-111">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="ac15d-111">In the Name field, type a value.</span></span>
    * <span data-ttu-id="ac15d-112">Ad esempio, digitare Speaker2016.</span><span class="sxs-lookup"><span data-stu-id="ac15d-112">For example, type Speaker2016.</span></span>  
4. <span data-ttu-id="ac15d-113">Nel campo Piano generale fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ac15d-113">In the Master plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="ac15d-114">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ac15d-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ac15d-115">Selezionare StaticPlan per calcolare la domanda.</span><span class="sxs-lookup"><span data-stu-id="ac15d-115">Select StaticPlan to calculate demand.</span></span>  
6. <span data-ttu-id="ac15d-116">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ac15d-116">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="ac15d-117">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ac15d-117">Click Save.</span></span>
8. <span data-ttu-id="ac15d-118">Nel campo Quantità kanban minima immettere "1".</span><span class="sxs-lookup"><span data-stu-id="ac15d-118">In the Minimum kanban quantity field, enter '1'.</span></span>
    * <span data-ttu-id="ac15d-119">Numero aggiuntivo di kanban incluso nel calcolo della quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="ac15d-119">This is the additional number of kanbans that is included in the kanban quantity calculation.</span></span>  
9. <span data-ttu-id="ac15d-120">Impostare il fattore di sicurezza su "1".</span><span class="sxs-lookup"><span data-stu-id="ac15d-120">Set Safety factor to '1'.</span></span>
    * <span data-ttu-id="ac15d-121">Fattore utilizzato per calcolare la quantità aggiuntiva di scorte di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ac15d-121">This is the factor that is used to calculate additional quantity of safety stock.</span></span>  
10. <span data-ttu-id="ac15d-122">Nel campo Giorni di anticipo immettere "30".</span><span class="sxs-lookup"><span data-stu-id="ac15d-122">In the Days ahead field, enter '30'.</span></span>
    * <span data-ttu-id="ac15d-123">Numero di giorni precedenti alla data di calcolo della quantità kanban inclusa nel calcolo della domanda.</span><span class="sxs-lookup"><span data-stu-id="ac15d-123">This is the number of days prior to the kanban quantity calculation date that is included in the demand calculation.</span></span>  
11. <span data-ttu-id="ac15d-124">Nel campo Giorni di ritardo immettere "30".</span><span class="sxs-lookup"><span data-stu-id="ac15d-124">In the Days behind field, enter '30'.</span></span>
    * <span data-ttu-id="ac15d-125">Numero di giorni successivi alla data di calcolo della quantità kanban inclusa nel calcolo della domanda.</span><span class="sxs-lookup"><span data-stu-id="ac15d-125">This is the number of days forward from the kanban quantity calculation date that is included in the demand calculation.</span></span>  <span data-ttu-id="ac15d-126">La formula utilizzata per il calcolo viene visualizzata con i valori effettivi.</span><span class="sxs-lookup"><span data-stu-id="ac15d-126">The formula used for the calculation is shown with the actual values.</span></span> <span data-ttu-id="ac15d-127">Ad esempio, quantità kanban = ((Domanda giornaliera media x lead time x 2)/Quantità prodotto per unità movimentazione) + 1</span><span class="sxs-lookup"><span data-stu-id="ac15d-127">For example,  Kanban quantity = ((Average daily demand x lead time x 2.00) / Product quantity per handling unit) + 1</span></span>  
12. <span data-ttu-id="ac15d-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ac15d-128">Close the page.</span></span>

## <a name="add-the-kanban-quantity-calculation-policy-to-a-kanban-rule"></a><span data-ttu-id="ac15d-129">Aggiungere i criteri di calcolo della quantità kanban a una regola kanban</span><span class="sxs-lookup"><span data-stu-id="ac15d-129">Add the kanban quantity calculation policy to a kanban rule</span></span>
1. <span data-ttu-id="ac15d-130">Andare a Gestione informazioni sul prodotto > Lean manufacturing > Regole kanban.</span><span class="sxs-lookup"><span data-stu-id="ac15d-130">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="ac15d-131">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ac15d-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ac15d-132">Selezionare la regola kanban 000020 per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="ac15d-132">Select kanban rule 000020 for this procedure.</span></span>  
3. <span data-ttu-id="ac15d-133">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ac15d-133">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="ac15d-134">Attivare/disattivare l'espansione della sezione Criteri di calcolo quantità kanban.</span><span class="sxs-lookup"><span data-stu-id="ac15d-134">Toggle the expansion of the Kanban quantity calculation policies section.</span></span>
5. <span data-ttu-id="ac15d-135">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="ac15d-135">Click Add.</span></span>
    * <span data-ttu-id="ac15d-136">Aggiungere i criteri di calcolo della quantità kanban creati nella sottoattività precedente.</span><span class="sxs-lookup"><span data-stu-id="ac15d-136">Add the kanban quantity calculation policy that you have just created in the previous sub-task.</span></span>  
6. <span data-ttu-id="ac15d-137">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ac15d-137">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="ac15d-138">Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ac15d-138">In the Name field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="ac15d-139">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ac15d-139">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ac15d-140">Selezionare il criterio Speaker2016 creato nella sottoattività precedente.</span><span class="sxs-lookup"><span data-stu-id="ac15d-140">Select the policy Speaker2016 that you have just created in the previous sub-task.</span></span>  

