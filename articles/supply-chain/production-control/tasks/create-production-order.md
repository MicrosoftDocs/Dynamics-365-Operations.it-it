---
title: Creare un ordine di produzione
description: Questa procedura indica come creare un ordine di produzione.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdTable, ProdBOM, ProdRoute
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 67a15a5c52bd1032c8bee8652f1f13d1f1a4cb64
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838585"
---
# <a name="create-a-production-order"></a><span data-ttu-id="8295d-103">Creare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="8295d-103">Create a production order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8295d-104">Questa procedura indica come creare un ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="8295d-104">This procedure shows how to create a production order.</span></span> <span data-ttu-id="8295d-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="8295d-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="8295d-106">Si tratta della prima procedura su sette che spiega il ciclo di vita dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="8295d-106">This is the first procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="8295d-107">Creare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="8295d-107">Create a production order</span></span>
1. <span data-ttu-id="8295d-108">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="8295d-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="8295d-109">Fare clic su Nuovo ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="8295d-109">Click New production order.</span></span>
3. <span data-ttu-id="8295d-110">Nel campo Numero articolo digitare "D0001".</span><span class="sxs-lookup"><span data-stu-id="8295d-110">In the Item number field, type 'D0001'.</span></span>
4. <span data-ttu-id="8295d-111">Immettere una data nel campo Consegna.</span><span class="sxs-lookup"><span data-stu-id="8295d-111">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="8295d-112">La data di consegna indica se l'ordine di produzione deve terminare per consegnare in tempo.</span><span class="sxs-lookup"><span data-stu-id="8295d-112">The delivery date indicates when the production order should end in order to deliver on time.</span></span> <span data-ttu-id="8295d-113">Questa data può essere utilizzata nel processo di programmazione.</span><span class="sxs-lookup"><span data-stu-id="8295d-113">This date can be used in the scheduling process.</span></span> <span data-ttu-id="8295d-114">Ad esempio, è possibile programmare l'ordine a ritroso dalla data di consegna.</span><span class="sxs-lookup"><span data-stu-id="8295d-114">For example, you can schedule the order backward from the delivery date.</span></span>  
5. <span data-ttu-id="8295d-115">Impostare la quantità su "20".</span><span class="sxs-lookup"><span data-stu-id="8295d-115">Set Quantity to '20'.</span></span>
    * <span data-ttu-id="8295d-116">Nota: nel campo Numero DBA verrà visualizzato automaticamente il numero di qualsiasi DBA attiva per l'articolo corrente, ma è possibile modificare la DBA per l'ordine di produzione selezionando una DBA attiva dall'elenco delle versioni DBA approvate.</span><span class="sxs-lookup"><span data-stu-id="8295d-116">Note: The BOM number field automatically displays the number of any active BOM for the current item, but you can change the BOM for the production order by selecting an active BOM from the list of approved BOM versions.</span></span>    <span data-ttu-id="8295d-117">Nel campo Numero ciclo di lavorazione verrà visualizzato automaticamente il numero di qualsiasi ciclo di lavorazione attivo per l'articolo corrente, ma è possibile modificare il ciclo di lavorazione per l'ordine di produzione selezionando un ciclo di lavorazione attivo dall'elenco delle versioni cicli di lavorazione approvati.</span><span class="sxs-lookup"><span data-stu-id="8295d-117">The Route number field automatically displays the number of any active Route for the current item, but you can change the Route for the production order by selecting an active Route from the list of approved Route versions.</span></span>  
6. <span data-ttu-id="8295d-118">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="8295d-118">Click Create.</span></span>

## <a name="validate-the-production-order"></a><span data-ttu-id="8295d-119">Convalida l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="8295d-119">Validate the production order</span></span>
1. <span data-ttu-id="8295d-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8295d-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="8295d-121">Fare clic sul collegamento relativo al numero dell'ordine di produzione appena creato.</span><span class="sxs-lookup"><span data-stu-id="8295d-121">Click the link for the production order number that you have just created.</span></span> <span data-ttu-id="8295d-122">Verrà aperta la pagina dei dettagli dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="8295d-122">This will open the details page for the order.</span></span>  
2. <span data-ttu-id="8295d-123">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="8295d-123">Click Edit.</span></span>
3. <span data-ttu-id="8295d-124">Immettere una data nel campo Consegna.</span><span class="sxs-lookup"><span data-stu-id="8295d-124">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="8295d-125">Ad esempio, è possibile modificare la data di consegna per l'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="8295d-125">For example, you can change the delivery date for the production order.</span></span>  
4. <span data-ttu-id="8295d-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8295d-126">Click Save.</span></span>
5. <span data-ttu-id="8295d-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8295d-127">Close the page.</span></span>

## <a name="update-the-bom"></a><span data-ttu-id="8295d-128">Aggiorna la DBA</span><span class="sxs-lookup"><span data-stu-id="8295d-128">Update the BOM</span></span>
1. <span data-ttu-id="8295d-129">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="8295d-129">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="8295d-130">Fare clic su DBA.</span><span class="sxs-lookup"><span data-stu-id="8295d-130">Click BOM.</span></span>
    * <span data-ttu-id="8295d-131">Aprire la pagina DBA per convalidare i dati DBA che sono stati copiati dai dati predefiniti quando l'ordine di produzione è stato creato.</span><span class="sxs-lookup"><span data-stu-id="8295d-131">Open the BOM page to validate the BOM data that was copied from the default data when the production order was created.</span></span> <span data-ttu-id="8295d-132">In questa procedura, è necessario aggiornare la quantità per una DBA.</span><span class="sxs-lookup"><span data-stu-id="8295d-132">In this procedure, you need to update the quantity for a BOM.</span></span>  
3. <span data-ttu-id="8295d-133">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="8295d-133">Click Edit.</span></span>
4. <span data-ttu-id="8295d-134">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="8295d-134">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="8295d-135">La modifica della quantità nella riga DBA influisce sulla stima dei costi del consumo di materiali per l'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="8295d-135">Changing the quantity on the BOM line affects the cost estimate of material consumption for the production order.</span></span>  
5. <span data-ttu-id="8295d-136">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8295d-136">Click Save.</span></span>
6. <span data-ttu-id="8295d-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8295d-137">Close the page.</span></span>

## <a name="update-the-production-route"></a><span data-ttu-id="8295d-138">Aggiorna il ciclo di lavorazione produzione</span><span class="sxs-lookup"><span data-stu-id="8295d-138">Update the production route</span></span>
1. <span data-ttu-id="8295d-139">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="8295d-139">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="8295d-140">Fare clic su Ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="8295d-140">Click Route.</span></span>
    * <span data-ttu-id="8295d-141">Aprire la pagina Ciclo di lavorazione per convalidare i dati del ciclo di lavorazione produzione copiati dai dati predefiniti quando l'ordine è stato creato.</span><span class="sxs-lookup"><span data-stu-id="8295d-141">Open the Route page to validate the data of the production route that was copied from the default data when the order was created.</span></span> <span data-ttu-id="8295d-142">In questa procedura, è necessario aggiornare la quantità per una delle operazioni nel ciclo di lavorazione produzione.</span><span class="sxs-lookup"><span data-stu-id="8295d-142">In this procedure, you need to update the quantity for one of the operations in the production route.</span></span>  
3. <span data-ttu-id="8295d-143">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8295d-143">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="8295d-144">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="8295d-144">Click Edit.</span></span>
5. <span data-ttu-id="8295d-145">Nel campo Qtà lavorazione immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="8295d-145">In the Process qty. field, enter a number.</span></span>
    * <span data-ttu-id="8295d-146">La modifica del tempo di elaborazione influisce sul consumo del ciclo di lavorazione stimato e sul costo dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="8295d-146">Changing the process time affects the estimated route consumption and the cost of the production order.</span></span>  
6. <span data-ttu-id="8295d-147">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8295d-147">Click Save.</span></span>
7. <span data-ttu-id="8295d-148">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8295d-148">Close the page.</span></span>

