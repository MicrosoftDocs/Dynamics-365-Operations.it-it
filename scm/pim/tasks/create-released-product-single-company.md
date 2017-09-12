--- 
title: "Creare un prodotto rilasciato per una singola società"
description: "Questa procedura descrive come creare un unico prodotto rilasciato nel contesto di un'unica unità legale."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 042eafc29e377e0ad6fb8dc1499daf8eb105b7ed
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-released-product-for-a-single-company"></a><span data-ttu-id="ee7c8-103">Creare un prodotto rilasciato per una singola società</span><span class="sxs-lookup"><span data-stu-id="ee7c8-103">Create a released product for a single company</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ee7c8-104">Questa procedura descrive come creare un unico prodotto rilasciato nel contesto di un'unica unità legale.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-104">This procedure walks through how to create a single released product in the context of a single legal unit.</span></span> <span data-ttu-id="ee7c8-105">Dopo la creazione, il prodotto rilasciato viene immediatamente reso disponibile solo in questa unità.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-105">After the released product is created,  it's immediately available in this unit only.</span></span> <span data-ttu-id="ee7c8-106">È possibile eseguire questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-106">You can walk through this procedure in demo data company USMF.</span></span> <span data-ttu-id="ee7c8-107">Questa attività viene in genere eseguita da un responsabile di design prodotto.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-107">This task is usually performed by a product designer.</span></span>


## <a name="create-a-released-product"></a><span data-ttu-id="ee7c8-108">Creare un prodotto rilasciato</span><span class="sxs-lookup"><span data-stu-id="ee7c8-108">Create a released product</span></span>
1. <span data-ttu-id="ee7c8-109">Fare clic su Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-109">Go to Released products.</span></span>
2. <span data-ttu-id="ee7c8-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-110">Click New.</span></span>
3. <span data-ttu-id="ee7c8-111">Nel campo Numero prodotto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-111">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="ee7c8-112">Se un numero prodotto non è immesso automaticamente nel campo relativo al numero prodotto, immettere un numero prodotto univoco.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-112">If a product number is not automatically entered in the Product number field, type a unique product number.</span></span> <span data-ttu-id="ee7c8-113">Questo passaggio è obbligatorio solo se nessuna sequenza numerica è stata impostata per i numeri prodotto.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-113">This step is only  required if no number sequence has been set up for product numbers.</span></span>  
4. <span data-ttu-id="ee7c8-114">Digitare un valore nel campo Nome prodotto.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-114">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="ee7c8-115">Il nome prodotto è impostato come valore predefinito sul nome di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-115">The Product name is defaulted to the search name.</span></span> <span data-ttu-id="ee7c8-116">Se necessario, è possibile scegliere di modificare il nome di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-116">If needed, you can select to change the search name.</span></span>  
5. <span data-ttu-id="ee7c8-117">Nel campo Gruppo di modelli di articoli fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-117">In the Item model group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ee7c8-118">I gruppi di modelli articolo contengono impostazioni che determinano la modalità in cui gli articoli vengono controllati e gestiti all'entrata e all'uscita.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-118">The item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="ee7c8-119">Le impostazioni determinano anche la modalità di calcolo del consumo di articoli.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-119">The settings also determine how the consumption of items are calculated.</span></span>  
6. <span data-ttu-id="ee7c8-120">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="ee7c8-121">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-121">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="ee7c8-122">Nel campo Gruppo di articoli fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-122">In the Item group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ee7c8-123">I gruppi di articoli vengono utilizzati per la gestione delle scorte mediante la divisione degli articoli di magazzino in gruppi basati sulle relative caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-123">Item groups are used to manage inventory by dividing inventory items into groups based on item characteristics.</span></span> <span data-ttu-id="ee7c8-124">Ad esempio, per gestire la modalità con cui le informazioni vengono registrate nei conti principali, è possibile creare una serie di gruppi di articoli diversi associati a conti principali specifici.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-124">For example, to manage how information is posted to main accounts, you can create a series of different item groups that are associated with specific main accounts.</span></span> <span data-ttu-id="ee7c8-125">In questo modo è possibile tenere traccia del valore di inventario degli articoli nelle diverse fasi.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-125">This lets you track the inventory value of items at different stages.</span></span>  
9. <span data-ttu-id="ee7c8-126">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-126">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="ee7c8-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-127">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="ee7c8-128">Nel campo Gruppo di dimensioni di immagazzinamento fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-128">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ee7c8-129">Le dimensioni di immagazzinamento consentono di controllare il modo in cui gli articoli vengono immagazzinati e prelevati dal magazzino.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-129">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="ee7c8-130">Ad esempio, una dimensione di immagazzinamento può essere il sito e il magazzino.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-130">For example, a storage dimension can be Site and Warehouse.</span></span>  
12. <span data-ttu-id="ee7c8-131">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-131">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="ee7c8-132">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-132">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="ee7c8-133">Nel campo Gruppo di dimensioni di tracciabilità fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-133">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ee7c8-134">Il gruppo di dimensioni di tracciabilità determina quali dimensioni di tracciabilità è possibile aggiungere a un prodotto.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-134">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="ee7c8-135">Ad esempio, numero batch e numero di serie vengono utilizzati per tenere traccia degli articoli di magazzino.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-135">For example, the batch number and serial number are used to track inventory items.</span></span>  
15. <span data-ttu-id="ee7c8-136">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-136">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="ee7c8-137">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-137">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="ee7c8-138">Nel campo Unità di magazzino fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-138">In the Inventory unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ee7c8-139">L'unità di magazzino determina la modalità in cui il prodotto viene quantificato quando è archiviato in magazzino.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-139">The inventory unit determines how the product is quantified when it's stored in inventory.</span></span>  
18. <span data-ttu-id="ee7c8-140">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-140">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="ee7c8-141">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-141">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="ee7c8-142">Nel campo Unità di acquisto fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-142">In the Purchase unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ee7c8-143">L'unità di acquisto determina la modalità in cui prodotto viene quantificato quando viene acquistato da un fornitore.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-143">The purchase unit determines how the product is quantified when it’s purchased from a vendor.</span></span>  
21. <span data-ttu-id="ee7c8-144">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-144">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="ee7c8-145">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-145">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="ee7c8-146">Nel campo Unità di vendita fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-146">In the Sales unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ee7c8-147">L'unità di vendita determina la modalità in cui il prodotto viene quantificato quando è venduto a un cliente.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-147">The sales unit determines how the product is quantified when it’s sold to a customer.</span></span>  
24. <span data-ttu-id="ee7c8-148">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-148">In the list, find and select the desired record.</span></span>
25. <span data-ttu-id="ee7c8-149">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-149">In the list, click the link in the selected row.</span></span>
26. <span data-ttu-id="ee7c8-150">Nel campo Unità DBA fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-150">In the BOM unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ee7c8-151">L'unità DBA determina la modalità in cui il prodotto viene quantificato quando viene incluso in una distinta base (BOM).</span><span class="sxs-lookup"><span data-stu-id="ee7c8-151">The BOM unit determines how the product is quantified when including it in a bill of materials (BOM).</span></span>  
27. <span data-ttu-id="ee7c8-152">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-152">In the list, find and select the desired record.</span></span>
28. <span data-ttu-id="ee7c8-153">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-153">In the list, click the link in the selected row.</span></span>
29. <span data-ttu-id="ee7c8-154">Nel campo Fascia IVA fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-154">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ee7c8-155">La fascia IVA articoli nel gruppo di commissioni di vendita determina come viene calcolata l'IVA per ogni articolo.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-155">The item sales tax group in the Sales taxation group determines how sales tax is calculated for each item.</span></span>  
30. <span data-ttu-id="ee7c8-156">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-156">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="ee7c8-157">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-157">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="ee7c8-158">Nel campo Fascia IVA fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-158">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ee7c8-159">La fascia IVA articoli nel gruppo di commissioni di acquisto determina come viene calcolata la tassa sull'acquisto per ogni articolo.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-159">The item sales tax group in the Purchase taxation group determines how purchase tax is calculated for each item.</span></span>  
33. <span data-ttu-id="ee7c8-160">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-160">In the list, find and select the desired record.</span></span>
34. <span data-ttu-id="ee7c8-161">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-161">In the list, click the link in the selected row.</span></span>
35. <span data-ttu-id="ee7c8-162">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-162">Click OK.</span></span>

## <a name="add-product-characteristics"></a><span data-ttu-id="ee7c8-163">Aggiungere le caratteristiche del prodotto</span><span class="sxs-lookup"><span data-stu-id="ee7c8-163">Add product characteristics</span></span>
1. <span data-ttu-id="ee7c8-164">Espandere o comprimere la sezione Gestione articoli.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-164">Expand or collapse the Manage inventory section.</span></span>
2. <span data-ttu-id="ee7c8-165">Immettere un numero nel campo Peso netto.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-165">In the Net weight field, enter a number.</span></span>
3. <span data-ttu-id="ee7c8-166">Immettere un numero nel campo Tara.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-166">In the Tare weight field, enter a number.</span></span>
4. <span data-ttu-id="ee7c8-167">Nel campo Profondità lorda immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-167">In the Gross depth field, enter a number.</span></span>
5. <span data-ttu-id="ee7c8-168">Nel campo Larghezza lorda immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-168">In the Gross width field, enter a number.</span></span>
6. <span data-ttu-id="ee7c8-169">Nel campo Altezza lorda immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-169">In the Gross height field, enter a number.</span></span>
7. <span data-ttu-id="ee7c8-170">Nel campo Volume immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-170">In the Volume field, enter a number.</span></span>

## <a name="add-financial-dimensions"></a><span data-ttu-id="ee7c8-171">Aggiungere dimensioni finanziarie</span><span class="sxs-lookup"><span data-stu-id="ee7c8-171">Add financial dimensions</span></span>
1. <span data-ttu-id="ee7c8-172">Espandere o comprimere la sezione Dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-172">Expand or collapse the Financial dimensions section.</span></span>
2. <span data-ttu-id="ee7c8-173">Nel campo Business Unit fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-173">In the BusinessUnit field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="ee7c8-174">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-174">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="ee7c8-175">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-175">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="ee7c8-176">Nel campo Centro di costo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-176">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="ee7c8-177">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-177">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="ee7c8-178">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-178">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="ee7c8-179">Nel campo Reparto fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-179">In the Department field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="ee7c8-180">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-180">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="ee7c8-181">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-181">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="ee7c8-182">Nel campo Gruppo di articoli fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-182">In the ItemGroup field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="ee7c8-183">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-183">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="ee7c8-184">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee7c8-184">In the list, click the link in the selected row.</span></span>

