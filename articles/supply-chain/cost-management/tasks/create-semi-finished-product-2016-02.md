--- 
title: Creare un prodotto semi-lavorato (solo febbraio 2016)
description: "Questa attività consente di creare un prodotto semilavorato."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 4d06f291036c656731a00fcf312e229ed9e9f3d0
ms.openlocfilehash: 038d8cd9333635d3269bb4f62a5402c2309bfd3c
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-semi-finished-product-february-2016-only"></a><span data-ttu-id="25c69-103">Creare un prodotto semi-lavorato (solo febbraio 2016)</span><span class="sxs-lookup"><span data-stu-id="25c69-103">Create a semi-finished product (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="25c69-104">Questa attività consente di creare un prodotto semilavorato.</span><span class="sxs-lookup"><span data-stu-id="25c69-104">This task focuses on creating a semi-finished product.</span></span> <span data-ttu-id="25c69-105">Corrisponde alla seconda attività della serie di calcoli DBA.</span><span class="sxs-lookup"><span data-stu-id="25c69-105">It is the second task in the BOM calculation series.</span></span> <span data-ttu-id="25c69-106">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="25c69-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="25c69-107">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="25c69-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="25c69-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="25c69-108">Click New.</span></span>
3. <span data-ttu-id="25c69-109">Nel campo Numero prodotto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="25c69-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="25c69-110">Per questo esempio, digitare BOM_2.</span><span class="sxs-lookup"><span data-stu-id="25c69-110">For this example, type BOM_2.</span></span>  
4. <span data-ttu-id="25c69-111">Nel campo Gruppo modello articolo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25c69-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="25c69-112">Selezionare STD.</span><span class="sxs-lookup"><span data-stu-id="25c69-112">Select STD.</span></span> <span data-ttu-id="25c69-113">STD sta per costo standard ed è il modello più utilizzato quando si lavora con i calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="25c69-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="25c69-114">Nel campo Gruppo di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25c69-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="25c69-115">Selezionare, ad esempio Audio.</span><span class="sxs-lookup"><span data-stu-id="25c69-115">For example, select Audio.</span></span> <span data-ttu-id="25c69-116">Ciò non ha effetto sui calcoli dei costi.</span><span class="sxs-lookup"><span data-stu-id="25c69-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="25c69-117">Nel campo Dimensione di immagazzinamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25c69-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="25c69-118">Selezionare SiteWH.</span><span class="sxs-lookup"><span data-stu-id="25c69-118">Select SiteWH.</span></span> <span data-ttu-id="25c69-119">Solo sito e magazzino verranno utilizzati per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="25c69-119">Only Site and Warehouse will be used for this example.</span></span>  
7. <span data-ttu-id="25c69-120">Nel campo Dimensione di tracciabilità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25c69-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="25c69-121">Le dimensioni di tracciabilità non verranno utilizzate in questo esempio, selezionare Nessuno.</span><span class="sxs-lookup"><span data-stu-id="25c69-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="25c69-122">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="25c69-122">Click OK.</span></span>
9. <span data-ttu-id="25c69-123">Nel riquadro azioni, fare clic su Gestione articoli.</span><span class="sxs-lookup"><span data-stu-id="25c69-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="25c69-124">Fare clic su Impostazioni ordine predefinite.</span><span class="sxs-lookup"><span data-stu-id="25c69-124">Click Default order settings.</span></span>
11. <span data-ttu-id="25c69-125">Nel campo Tipo di ordine predefinito selezionare 'Production'.</span><span class="sxs-lookup"><span data-stu-id="25c69-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="25c69-126">Poiché si sta producendo un prodotto semilavorato, selezionare Produzione.</span><span class="sxs-lookup"><span data-stu-id="25c69-126">Because this is a semi-finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="25c69-127">Nel campo Sito acquisto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25c69-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="25c69-128">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="25c69-128">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="25c69-129">Nel campo Sito magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25c69-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="25c69-130">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="25c69-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="25c69-131">Nel campo Sito vendite immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25c69-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="25c69-132">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="25c69-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="25c69-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25c69-133">Close the page.</span></span>
16. <span data-ttu-id="25c69-134">Nel riquadro azioni, fare clic su Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="25c69-134">On the Action Pane, click Manage costs.</span></span>
17. <span data-ttu-id="25c69-135">Fare clic su Prezzo articolo.</span><span class="sxs-lookup"><span data-stu-id="25c69-135">Click Item price.</span></span>
18. <span data-ttu-id="25c69-136">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="25c69-136">Click New.</span></span>
19. <span data-ttu-id="25c69-137">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="25c69-137">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="25c69-138">Nel campo Versione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25c69-138">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="25c69-139">Per questo esempio, selezionare Version 10.</span><span class="sxs-lookup"><span data-stu-id="25c69-139">For this example, select Version 10.</span></span>  
21. <span data-ttu-id="25c69-140">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25c69-140">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="25c69-141">Per questo esempio, selezionare Site 1.</span><span class="sxs-lookup"><span data-stu-id="25c69-141">For this example, select Site 1.</span></span>  
22. <span data-ttu-id="25c69-142">Impostare il prezzo su '10'.</span><span class="sxs-lookup"><span data-stu-id="25c69-142">Set Price to '10'.</span></span>
    * <span data-ttu-id="25c69-143">Per questo esempio, digitare un prezzo di costo di 10.</span><span class="sxs-lookup"><span data-stu-id="25c69-143">For this example, type a cost price of 10.</span></span>  
23. <span data-ttu-id="25c69-144">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="25c69-144">Click Save.</span></span>
24. <span data-ttu-id="25c69-145">Fare clic su Attiva prezzo/i in sospeso.</span><span class="sxs-lookup"><span data-stu-id="25c69-145">Click Activate pending price(s).</span></span>
25. <span data-ttu-id="25c69-146">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25c69-146">Close the page.</span></span>
26. <span data-ttu-id="25c69-147">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25c69-147">Close the page.</span></span>
27. <span data-ttu-id="25c69-148">Fare clic su BOM_2 per aprire.</span><span class="sxs-lookup"><span data-stu-id="25c69-148">Click BOM_2 to open it.</span></span>
28. <span data-ttu-id="25c69-149">Espandere la sezione Gestisci costi.</span><span class="sxs-lookup"><span data-stu-id="25c69-149">Expand the Manage costs section.</span></span>
29. <span data-ttu-id="25c69-150">Nel campo Gruppo di costi, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="25c69-150">In the Cost group field, enter or select a value.</span></span>
    * <span data-ttu-id="25c69-151">Per questo esempio, selezionare Gruppo di costi M1.</span><span class="sxs-lookup"><span data-stu-id="25c69-151">For this example, select Cost group M1.</span></span>  
30. <span data-ttu-id="25c69-152">Utilizzare il collegamento per salvare un record.</span><span class="sxs-lookup"><span data-stu-id="25c69-152">Use the shortcut for saving a record.</span></span>
31. <span data-ttu-id="25c69-153">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="25c69-153">Close the page.</span></span>


