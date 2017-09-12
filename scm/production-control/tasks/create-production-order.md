--- 
title: Creare un ordine di produzione
description: Questa procedura indica come creare un ordine di produzione.
author: johanhoffmann
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
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: ac2ee418082aa6579424fc9480478587b7c22c6d
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-production-order"></a><span data-ttu-id="c0a7e-103">Creare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="c0a7e-103">Create a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c0a7e-104">Questa procedura indica come creare un ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-104">This procedure shows how to create a production order.</span></span> <span data-ttu-id="c0a7e-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c0a7e-106">Si tratta della prima procedura su sette che spiega il ciclo di vita dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-106">This is the first procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="c0a7e-107">Creare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="c0a7e-107">Create a production order</span></span>
1. <span data-ttu-id="c0a7e-108">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="c0a7e-109">Fare clic su Nuovo ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-109">Click New production order.</span></span>
3. <span data-ttu-id="c0a7e-110">Nel campo Numero articolo digitare "D0001".</span><span class="sxs-lookup"><span data-stu-id="c0a7e-110">In the Item number field, type 'D0001'.</span></span>
4. <span data-ttu-id="c0a7e-111">Immettere una data nel campo Consegna.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-111">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="c0a7e-112">La data di consegna indica se l'ordine di produzione deve terminare per consegnare in tempo.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-112">The delivery date indicates when the production order should end in order to deliver on time.</span></span> <span data-ttu-id="c0a7e-113">Questa data può essere utilizzata nel processo di programmazione.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-113">This date can be used in the scheduling process.</span></span> <span data-ttu-id="c0a7e-114">Ad esempio, è possibile programmare l'ordine a ritroso dalla data di consegna.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-114">For example, you can schedule the order backward from the delivery date.</span></span>  
5. <span data-ttu-id="c0a7e-115">Impostare la quantità su "20".</span><span class="sxs-lookup"><span data-stu-id="c0a7e-115">Set Quantity to '20'.</span></span>
    * <span data-ttu-id="c0a7e-116">Nota: nel campo Numero DBA verrà visualizzato automaticamente il numero di qualsiasi DBA attiva per l'articolo corrente, ma è possibile modificare la DBA per l'ordine di produzione selezionando una DBA attiva dall'elenco delle versioni DBA approvate.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-116">Note: The BOM number field automatically displays the number of any active BOM for the current item, but you can change the BOM for the production order by selecting an active BOM from the list of approved BOM versions.</span></span>    <span data-ttu-id="c0a7e-117">Nel campo Numero ciclo di lavorazione verrà visualizzato automaticamente il numero di qualsiasi ciclo di lavorazione attivo per l'articolo corrente, ma è possibile modificare il ciclo di lavorazione per l'ordine di produzione selezionando un ciclo di lavorazione attivo dall'elenco delle versioni cicli di lavorazione approvati.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-117">The Route number field automatically displays the number of any active Route for the current item, but you can change the Route for the production order by selecting an active Route from the list of approved Route versions.</span></span>  
6. <span data-ttu-id="c0a7e-118">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-118">Click Create.</span></span>

## <a name="validate-the-production-order"></a><span data-ttu-id="c0a7e-119">Convalida l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="c0a7e-119">Validate the production order</span></span>
1. <span data-ttu-id="c0a7e-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c0a7e-121">Fare clic sul collegamento relativo al numero dell'ordine di produzione appena creato.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-121">Click the link for the production order number that you have just created.</span></span> <span data-ttu-id="c0a7e-122">Verrà aperta la pagina dei dettagli dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-122">This will open the details page for the order.</span></span>  
2. <span data-ttu-id="c0a7e-123">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-123">Click Edit.</span></span>
3. <span data-ttu-id="c0a7e-124">Immettere una data nel campo Consegna.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-124">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="c0a7e-125">Ad esempio, è possibile modificare la data di consegna per l'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-125">For example, you can change the delivery date for the production order.</span></span>  
4. <span data-ttu-id="c0a7e-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-126">Click Save.</span></span>
5. <span data-ttu-id="c0a7e-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-127">Close the page.</span></span>

## <a name="update-the-bom"></a><span data-ttu-id="c0a7e-128">Aggiorna la DBA</span><span class="sxs-lookup"><span data-stu-id="c0a7e-128">Update the BOM</span></span>
1. <span data-ttu-id="c0a7e-129">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-129">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="c0a7e-130">Fare clic su DBA.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-130">Click BOM.</span></span>
    * <span data-ttu-id="c0a7e-131">Aprire la pagina DBA per convalidare i dati DBA che sono stati copiati dai dati predefiniti quando l'ordine di produzione è stato creato.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-131">Open the BOM page to validate the BOM data that was copied from the default data when the production order was created.</span></span> <span data-ttu-id="c0a7e-132">In questa procedura, è necessario aggiornare la quantità per una DBA.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-132">In this procedure, you need to update the quantity for a BOM.</span></span>  
3. <span data-ttu-id="c0a7e-133">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-133">Click Edit.</span></span>
4. <span data-ttu-id="c0a7e-134">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-134">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="c0a7e-135">La modifica della quantità nella riga DBA influisce sulla stima dei costi del consumo di materiali per l'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-135">Changing the quantity on the BOM line affects the cost estimate of material consumption for the production order.</span></span>  
5. <span data-ttu-id="c0a7e-136">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-136">Click Save.</span></span>
6. <span data-ttu-id="c0a7e-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-137">Close the page.</span></span>

## <a name="update-the-production-route"></a><span data-ttu-id="c0a7e-138">Aggiorna il ciclo di lavorazione produzione</span><span class="sxs-lookup"><span data-stu-id="c0a7e-138">Update the production route</span></span>
1. <span data-ttu-id="c0a7e-139">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-139">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="c0a7e-140">Fare clic su Ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-140">Click Route.</span></span>
    * <span data-ttu-id="c0a7e-141">Aprire la pagina Ciclo di lavorazione per convalidare i dati del ciclo di lavorazione produzione copiati dai dati predefiniti quando l'ordine è stato creato.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-141">Open the Route page to validate the data of the production route that was copied from the default data when the order was created.</span></span> <span data-ttu-id="c0a7e-142">In questa procedura, è necessario aggiornare la quantità per una delle operazioni nel ciclo di lavorazione produzione.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-142">In this procedure, you need to update the quantity for one of the operations in the production route.</span></span>  
3. <span data-ttu-id="c0a7e-143">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-143">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="c0a7e-144">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-144">Click Edit.</span></span>
5. <span data-ttu-id="c0a7e-145">Nel campo Qtà lavorazione</span><span class="sxs-lookup"><span data-stu-id="c0a7e-145">In the Process qty.</span></span> <span data-ttu-id="c0a7e-146">immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-146">field, enter a number.</span></span>
    * <span data-ttu-id="c0a7e-147">La modifica del tempo di elaborazione influisce sul consumo del ciclo di lavorazione stimato e sul costo dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-147">Changing the process time affects the estimated route consumption and the cost of the production order.</span></span>  
6. <span data-ttu-id="c0a7e-148">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-148">Click Save.</span></span>
7. <span data-ttu-id="c0a7e-149">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c0a7e-149">Close the page.</span></span>

