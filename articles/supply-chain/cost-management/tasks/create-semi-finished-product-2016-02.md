---
title: Creare un prodotto semi-lavorato (solo febbraio 2016)
description: Questa attività consente di creare un prodotto semilavorato.
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76fcba3732879f85c9bf0faa6d2481b9c5313a17
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563183"
---
# <a name="create-a-semi-finished-product-february-2016-only"></a><span data-ttu-id="12e70-103">Creare un prodotto semi-lavorato (solo febbraio 2016)</span><span class="sxs-lookup"><span data-stu-id="12e70-103">Create a semi-finished product (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="12e70-104">Questa attività consente di creare un prodotto semilavorato.</span><span class="sxs-lookup"><span data-stu-id="12e70-104">This task focuses on creating a semi-finished product.</span></span> <span data-ttu-id="12e70-105">Corrisponde alla seconda attività della serie di calcoli DBA.</span><span class="sxs-lookup"><span data-stu-id="12e70-105">It is the second task in the BOM calculation series.</span></span> <span data-ttu-id="12e70-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="12e70-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="12e70-107">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="12e70-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="12e70-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="12e70-108">Click New.</span></span>
3. <span data-ttu-id="12e70-109">Nel campo Numero prodotto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="12e70-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="12e70-110">Per questo esempio, digitare BOM_2.</span><span class="sxs-lookup"><span data-stu-id="12e70-110">For this example, type BOM_2.</span></span>  
4. <span data-ttu-id="12e70-111">Nel campo Gruppo modello articolo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="12e70-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="12e70-112">Selezionare STD.</span><span class="sxs-lookup"><span data-stu-id="12e70-112">Select STD.</span></span> <span data-ttu-id="12e70-113">STD sta per costo standard ed è il modello più utilizzato quando si lavora con i calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="12e70-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="12e70-114">Nel campo Gruppo di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="12e70-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="12e70-115">Selezionare, ad esempio Audio.</span><span class="sxs-lookup"><span data-stu-id="12e70-115">For example, select Audio.</span></span> <span data-ttu-id="12e70-116">Ciò non ha effetto sui calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="12e70-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="12e70-117">Nel campo Dimensione di immagazzinamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="12e70-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="12e70-118">Selezionare SiteWH.</span><span class="sxs-lookup"><span data-stu-id="12e70-118">Select SiteWH.</span></span> <span data-ttu-id="12e70-119">Solo sito e magazzino verranno utilizzati per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="12e70-119">Only Site and Warehouse will be used for this example.</span></span>  
7. <span data-ttu-id="12e70-120">Nel campo Dimensione di tracciabilità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="12e70-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="12e70-121">Le dimensioni di tracciabilità non verranno utilizzate in questo esempio, selezionare Nessuno.</span><span class="sxs-lookup"><span data-stu-id="12e70-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="12e70-122">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="12e70-122">Click OK.</span></span>
9. <span data-ttu-id="12e70-123">Nel riquadro azioni, fare clic su Gestione articoli.</span><span class="sxs-lookup"><span data-stu-id="12e70-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="12e70-124">Fare clic su Impostazioni ordine predefinite.</span><span class="sxs-lookup"><span data-stu-id="12e70-124">Click Default order settings.</span></span>
11. <span data-ttu-id="12e70-125">Nel campo Tipo di ordine predefinito selezionare 'Production'.</span><span class="sxs-lookup"><span data-stu-id="12e70-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="12e70-126">Poiché si sta producendo un prodotto semilavorato, selezionare Produzione.</span><span class="sxs-lookup"><span data-stu-id="12e70-126">Because this is a semi-finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="12e70-127">Nel campo Sito acquisto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="12e70-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="12e70-128">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="12e70-128">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="12e70-129">Nel campo Sito magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="12e70-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="12e70-130">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="12e70-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="12e70-131">Nel campo Sito vendite immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="12e70-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="12e70-132">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="12e70-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="12e70-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="12e70-133">Close the page.</span></span>
16. <span data-ttu-id="12e70-134">Nel riquadro azioni, fare clic su Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="12e70-134">On the Action Pane, click Manage costs.</span></span>
17. <span data-ttu-id="12e70-135">Fare clic su Prezzo articolo.</span><span class="sxs-lookup"><span data-stu-id="12e70-135">Click Item price.</span></span>
18. <span data-ttu-id="12e70-136">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="12e70-136">Click New.</span></span>
19. <span data-ttu-id="12e70-137">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="12e70-137">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="12e70-138">Nel campo Versione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="12e70-138">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="12e70-139">Per questo esempio, selezionare Version 10.</span><span class="sxs-lookup"><span data-stu-id="12e70-139">For this example, select Version 10.</span></span>  
21. <span data-ttu-id="12e70-140">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="12e70-140">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="12e70-141">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="12e70-141">For this example, select Site 1.</span></span>  
22. <span data-ttu-id="12e70-142">Impostare il prezzo su '10'.</span><span class="sxs-lookup"><span data-stu-id="12e70-142">Set Price to '10'.</span></span>
    * <span data-ttu-id="12e70-143">Per questo esempio, digitare un prezzo di costo di 10.</span><span class="sxs-lookup"><span data-stu-id="12e70-143">For this example, type a cost price of 10.</span></span>  
23. <span data-ttu-id="12e70-144">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="12e70-144">Click Save.</span></span>
24. <span data-ttu-id="12e70-145">Fare clic su Attiva prezzo/i in sospeso.</span><span class="sxs-lookup"><span data-stu-id="12e70-145">Click Activate pending price(s).</span></span>
25. <span data-ttu-id="12e70-146">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="12e70-146">Close the page.</span></span>
26. <span data-ttu-id="12e70-147">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="12e70-147">Close the page.</span></span>
27. <span data-ttu-id="12e70-148">Fare clic su BOM_2 per aprire.</span><span class="sxs-lookup"><span data-stu-id="12e70-148">Click BOM_2 to open it.</span></span>
28. <span data-ttu-id="12e70-149">Espandere la sezione Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="12e70-149">Expand the Manage costs section.</span></span>
29. <span data-ttu-id="12e70-150">Nel campo Gruppo di costi, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="12e70-150">In the Cost group field, enter or select a value.</span></span>
    * <span data-ttu-id="12e70-151">Per questo esempio, selezionare Gruppo di costi M1.</span><span class="sxs-lookup"><span data-stu-id="12e70-151">For this example, select Cost group M1.</span></span>  
30. <span data-ttu-id="12e70-152">Utilizzare il collegamento per salvare un record.</span><span class="sxs-lookup"><span data-stu-id="12e70-152">Use the shortcut for saving a record.</span></span>
31. <span data-ttu-id="12e70-153">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="12e70-153">Close the page.</span></span>

