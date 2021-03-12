---
title: Creare un ordine di produzione
description: Questa procedura indica come creare un ordine di produzione.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdTable, ProdBOM, ProdRoute, ProdJournalCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 81caa6693d86c797d8565270094556ae4e103e6a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4998680"
---
# <a name="create-a-production-order"></a><span data-ttu-id="11046-103">Creare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="11046-103">Create a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="11046-104">Questa procedura indica come creare un ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="11046-104">This procedure shows how to create a production order.</span></span> <span data-ttu-id="11046-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="11046-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="11046-106">Si tratta della prima procedura su sette che spiega il ciclo di vita dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="11046-106">This is the first procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="11046-107">Creare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="11046-107">Create a production order</span></span>
1. <span data-ttu-id="11046-108">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="11046-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="11046-109">Fare clic su Nuovo ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="11046-109">Click New production order.</span></span>
3. <span data-ttu-id="11046-110">Nel campo Numero articolo digitare "D0001".</span><span class="sxs-lookup"><span data-stu-id="11046-110">In the Item number field, type 'D0001'.</span></span>
4. <span data-ttu-id="11046-111">Immettere una data nel campo Consegna.</span><span class="sxs-lookup"><span data-stu-id="11046-111">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="11046-112">La data di consegna indica se l'ordine di produzione deve terminare per consegnare in tempo.</span><span class="sxs-lookup"><span data-stu-id="11046-112">The delivery date indicates when the production order should end in order to deliver on time.</span></span> <span data-ttu-id="11046-113">Questa data può essere utilizzata nel processo di programmazione.</span><span class="sxs-lookup"><span data-stu-id="11046-113">This date can be used in the scheduling process.</span></span> <span data-ttu-id="11046-114">Ad esempio, è possibile programmare l'ordine a ritroso dalla data di consegna.</span><span class="sxs-lookup"><span data-stu-id="11046-114">For example, you can schedule the order backward from the delivery date.</span></span>  
5. <span data-ttu-id="11046-115">Impostare la quantità su "20".</span><span class="sxs-lookup"><span data-stu-id="11046-115">Set Quantity to '20'.</span></span>
    * <span data-ttu-id="11046-116">Nota: nel campo Numero DBA verrà visualizzato automaticamente il numero di qualsiasi DBA attiva per l'articolo corrente, ma è possibile modificare la DBA per l'ordine di produzione selezionando una DBA attiva dall'elenco delle versioni DBA approvate.</span><span class="sxs-lookup"><span data-stu-id="11046-116">Note: The BOM number field automatically displays the number of any active BOM for the current item, but you can change the BOM for the production order by selecting an active BOM from the list of approved BOM versions.</span></span>    <span data-ttu-id="11046-117">Nel campo Numero ciclo di lavorazione verrà visualizzato automaticamente il numero di qualsiasi ciclo di lavorazione attivo per l'articolo corrente, ma è possibile modificare il ciclo di lavorazione per l'ordine di produzione selezionando un ciclo di lavorazione attivo dall'elenco delle versioni cicli di lavorazione approvati.</span><span class="sxs-lookup"><span data-stu-id="11046-117">The Route number field automatically displays the number of any active Route for the current item, but you can change the Route for the production order by selecting an active Route from the list of approved Route versions.</span></span>  
6. <span data-ttu-id="11046-118">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="11046-118">Click Create.</span></span>

## <a name="validate-the-production-order"></a><span data-ttu-id="11046-119">Convalida l'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="11046-119">Validate the production order</span></span>
1. <span data-ttu-id="11046-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="11046-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="11046-121">Fare clic sul collegamento relativo al numero dell'ordine di produzione appena creato.</span><span class="sxs-lookup"><span data-stu-id="11046-121">Click the link for the production order number that you have just created.</span></span> <span data-ttu-id="11046-122">Verrà aperta la pagina dei dettagli dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="11046-122">This will open the details page for the order.</span></span>  
2. <span data-ttu-id="11046-123">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="11046-123">Click Edit.</span></span>
3. <span data-ttu-id="11046-124">Immettere una data nel campo Consegna.</span><span class="sxs-lookup"><span data-stu-id="11046-124">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="11046-125">Ad esempio, è possibile modificare la data di consegna per l'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="11046-125">For example, you can change the delivery date for the production order.</span></span>  
4. <span data-ttu-id="11046-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="11046-126">Click Save.</span></span>
5. <span data-ttu-id="11046-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="11046-127">Close the page.</span></span>

## <a name="update-the-bom"></a><span data-ttu-id="11046-128">Aggiorna la DBA</span><span class="sxs-lookup"><span data-stu-id="11046-128">Update the BOM</span></span>
1. <span data-ttu-id="11046-129">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="11046-129">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="11046-130">Fare clic su DBA.</span><span class="sxs-lookup"><span data-stu-id="11046-130">Click BOM.</span></span>
    * <span data-ttu-id="11046-131">Aprire la pagina DBA per convalidare i dati DBA che sono stati copiati dai dati predefiniti quando l'ordine di produzione è stato creato.</span><span class="sxs-lookup"><span data-stu-id="11046-131">Open the BOM page to validate the BOM data that was copied from the default data when the production order was created.</span></span> <span data-ttu-id="11046-132">In questa procedura, è necessario aggiornare la quantità per una DBA.</span><span class="sxs-lookup"><span data-stu-id="11046-132">In this procedure, you need to update the quantity for a BOM.</span></span>  
3. <span data-ttu-id="11046-133">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="11046-133">Click Edit.</span></span>
4. <span data-ttu-id="11046-134">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="11046-134">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="11046-135">La modifica della quantità nella riga DBA influisce sulla stima dei costi del consumo di materiali per l'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="11046-135">Changing the quantity on the BOM line affects the cost estimate of material consumption for the production order.</span></span>  
5. <span data-ttu-id="11046-136">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="11046-136">Click Save.</span></span>
6. <span data-ttu-id="11046-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="11046-137">Close the page.</span></span>

## <a name="update-the-production-route"></a><span data-ttu-id="11046-138">Aggiorna il ciclo di lavorazione produzione</span><span class="sxs-lookup"><span data-stu-id="11046-138">Update the production route</span></span>
1. <span data-ttu-id="11046-139">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="11046-139">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="11046-140">Fare clic su Ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="11046-140">Click Route.</span></span>
    * <span data-ttu-id="11046-141">Aprire la pagina Ciclo di lavorazione per convalidare i dati del ciclo di lavorazione produzione copiati dai dati predefiniti quando l'ordine è stato creato.</span><span class="sxs-lookup"><span data-stu-id="11046-141">Open the Route page to validate the data of the production route that was copied from the default data when the order was created.</span></span> <span data-ttu-id="11046-142">In questa procedura, è necessario aggiornare la quantità per una delle operazioni nel ciclo di lavorazione produzione.</span><span class="sxs-lookup"><span data-stu-id="11046-142">In this procedure, you need to update the quantity for one of the operations in the production route.</span></span>  
3. <span data-ttu-id="11046-143">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="11046-143">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="11046-144">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="11046-144">Click Edit.</span></span>
5. <span data-ttu-id="11046-145">Nel campo Qtà lavorazione immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="11046-145">In the Process qty. field, enter a number.</span></span>
    * <span data-ttu-id="11046-146">La modifica del tempo di elaborazione influisce sul consumo del ciclo di lavorazione stimato e sul costo dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="11046-146">Changing the process time affects the estimated route consumption and the cost of the production order.</span></span>  
6. <span data-ttu-id="11046-147">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="11046-147">Click Save.</span></span>
7. <span data-ttu-id="11046-148">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="11046-148">Close the page.</span></span>

