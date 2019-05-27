---
title: Creare una nomenclatura del numero di prodotto per le varianti prodotto configurate
description: In questa procedura viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto configurate e come può essere collegata a una rappresentazione generale prodotto configurabile.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 800afdf075f0675185514158f3b712a0fe7675e3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567150"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="cec6d-103">Creare una nomenclatura del numero di prodotto per le varianti prodotto configurate</span><span class="sxs-lookup"><span data-stu-id="cec6d-103">Create a product number nomenclature for configured product variants</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cec6d-104">In questa procedura viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto configurate e come può essere collegata a una rappresentazione generale prodotto configurabile.</span><span class="sxs-lookup"><span data-stu-id="cec6d-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="cec6d-105">Questa procedura dimostra anche come è possibile creare una nomenclatura di configurazione per un componente del modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="cec6d-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="cec6d-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="cec6d-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="cec6d-107">La nuova nomenclatura di numero prodotto è assegnata alla rappresentazione generale prodotto D0004.</span><span class="sxs-lookup"><span data-stu-id="cec6d-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="cec6d-108">Questa attività viene in genere effettuata da un responsabile del design del prodotto.</span><span class="sxs-lookup"><span data-stu-id="cec6d-108">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="cec6d-109">Creare una nomenclatura di numero prodotto</span><span class="sxs-lookup"><span data-stu-id="cec6d-109">Create a product number nomenclature</span></span>
1. <span data-ttu-id="cec6d-110">Fare clic su Definizione modello di variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="cec6d-110">Click Product variant model definition.</span></span>
2. <span data-ttu-id="cec6d-111">Fare clic su Nomenclatura di prodotto.</span><span class="sxs-lookup"><span data-stu-id="cec6d-111">Click Product nomenclature.</span></span>
3. <span data-ttu-id="cec6d-112">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="cec6d-112">Click New.</span></span>
4. <span data-ttu-id="cec6d-113">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="cec6d-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="cec6d-114">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="cec6d-114">In the Description field, type a value.</span></span>
6. <span data-ttu-id="cec6d-115">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="cec6d-115">Click Add.</span></span>
7. <span data-ttu-id="cec6d-116">Fare clic su Numero rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="cec6d-116">Click Product master number.</span></span>
8. <span data-ttu-id="cec6d-117">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="cec6d-117">Click Add.</span></span>
9. <span data-ttu-id="cec6d-118">Fare clic su Costante testo.</span><span class="sxs-lookup"><span data-stu-id="cec6d-118">Click Text constant.</span></span>
10. <span data-ttu-id="cec6d-119">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cec6d-119">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="cec6d-120">Digitare un valore nel campo Testo.</span><span class="sxs-lookup"><span data-stu-id="cec6d-120">In the Text field, type a value.</span></span>
12. <span data-ttu-id="cec6d-121">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="cec6d-121">Click Add.</span></span>
13. <span data-ttu-id="cec6d-122">Fare clic su Configurazione.</span><span class="sxs-lookup"><span data-stu-id="cec6d-122">Click Configuration.</span></span>
14. <span data-ttu-id="cec6d-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cec6d-123">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="cec6d-124">Assegnare la nomenclatura di un numero prodotto a una rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="cec6d-124">Assign the product number nomenclature to a product master</span></span>
1. <span data-ttu-id="cec6d-125">Fare clic su Rappresentazioni generali prodotto.</span><span class="sxs-lookup"><span data-stu-id="cec6d-125">Click Product masters.</span></span>
2. <span data-ttu-id="cec6d-126">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="cec6d-126">Use the Quick Filter to find records.</span></span> <span data-ttu-id="cec6d-127">Ad esempio, filtrare in base al campo Numero prodotto con un valore di 'D'.</span><span class="sxs-lookup"><span data-stu-id="cec6d-127">For example, filter on the Product number field with a value of 'D'.</span></span>
3. <span data-ttu-id="cec6d-128">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cec6d-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="cec6d-129">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="cec6d-129">Click Edit.</span></span>
5. <span data-ttu-id="cec6d-130">Selezionare Sì nel campo Utilizza nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="cec6d-130">Select Yes in the Use nomenclature field.</span></span>
6. <span data-ttu-id="cec6d-131">Nel campo Nomenclatura di numero di variante prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="cec6d-131">In the Product variant number nomenclature field, enter or select a value.</span></span>
7. <span data-ttu-id="cec6d-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cec6d-132">Close the page.</span></span>
8. <span data-ttu-id="cec6d-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cec6d-133">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="cec6d-134">Creare una nomenclatura per un componente di modello di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="cec6d-134">Create nomenclature for a product configuration model component</span></span>
1. <span data-ttu-id="cec6d-135">Fare clic su Modelli di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="cec6d-135">Click Product configuration models.</span></span>
2. <span data-ttu-id="cec6d-136">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="cec6d-136">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="cec6d-137">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cec6d-137">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="cec6d-138">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="cec6d-138">Click Edit.</span></span>
5. <span data-ttu-id="cec6d-139">Selezionare Sì nel campo Utilizza nomenclatura di configurazione.</span><span class="sxs-lookup"><span data-stu-id="cec6d-139">Select Yes in the Use configuration nomenclature field.</span></span>
6. <span data-ttu-id="cec6d-140">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="cec6d-140">Click Add.</span></span>
7. <span data-ttu-id="cec6d-141">Fare clic su Valore attributo.</span><span class="sxs-lookup"><span data-stu-id="cec6d-141">Click Attribute value.</span></span>
8. <span data-ttu-id="cec6d-142">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cec6d-142">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="cec6d-143">Nel campo Attributo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="cec6d-143">In the Attribute field, enter or select a value.</span></span>
10. <span data-ttu-id="cec6d-144">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="cec6d-144">Click Add.</span></span>
11. <span data-ttu-id="cec6d-145">Fare clic su Costante testo.</span><span class="sxs-lookup"><span data-stu-id="cec6d-145">Click Text constant.</span></span>
12. <span data-ttu-id="cec6d-146">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cec6d-146">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="cec6d-147">Digitare un valore nel campo Testo.</span><span class="sxs-lookup"><span data-stu-id="cec6d-147">In the Text field, type a value.</span></span>
14. <span data-ttu-id="cec6d-148">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="cec6d-148">Click Add.</span></span>
15. <span data-ttu-id="cec6d-149">Fare clic su Valore attributo.</span><span class="sxs-lookup"><span data-stu-id="cec6d-149">Click Attribute value.</span></span>
16. <span data-ttu-id="cec6d-150">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cec6d-150">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="cec6d-151">Nel campo Attributo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="cec6d-151">In the Attribute field, enter or select a value.</span></span>
18. <span data-ttu-id="cec6d-152">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="cec6d-152">Click Add.</span></span>
19. <span data-ttu-id="cec6d-153">Fare clic su Costante testo.</span><span class="sxs-lookup"><span data-stu-id="cec6d-153">Click Text constant.</span></span>
20. <span data-ttu-id="cec6d-154">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cec6d-154">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="cec6d-155">Digitare un valore nel campo Testo.</span><span class="sxs-lookup"><span data-stu-id="cec6d-155">In the Text field, type a value.</span></span>
22. <span data-ttu-id="cec6d-156">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="cec6d-156">Click Add.</span></span>
23. <span data-ttu-id="cec6d-157">Fare clic su Valore attributo.</span><span class="sxs-lookup"><span data-stu-id="cec6d-157">Click Attribute value.</span></span>
24. <span data-ttu-id="cec6d-158">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cec6d-158">In the list, mark the selected row.</span></span>
25. <span data-ttu-id="cec6d-159">Nel campo Attributo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="cec6d-159">In the Attribute field, enter or select a value.</span></span>
26. <span data-ttu-id="cec6d-160">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="cec6d-160">Click Add.</span></span>
27. <span data-ttu-id="cec6d-161">Fare clic su Costante testo.</span><span class="sxs-lookup"><span data-stu-id="cec6d-161">Click Text constant.</span></span>
28. <span data-ttu-id="cec6d-162">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cec6d-162">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="cec6d-163">Digitare un valore nel campo Testo.</span><span class="sxs-lookup"><span data-stu-id="cec6d-163">In the Text field, type a value.</span></span>
30. <span data-ttu-id="cec6d-164">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="cec6d-164">Click Add.</span></span>
31. <span data-ttu-id="cec6d-165">Fare clic su Valore attributo.</span><span class="sxs-lookup"><span data-stu-id="cec6d-165">Click Attribute value.</span></span>
32. <span data-ttu-id="cec6d-166">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cec6d-166">In the list, mark the selected row.</span></span>
33. <span data-ttu-id="cec6d-167">Nel campo Attributo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="cec6d-167">In the Attribute field, enter or select a value.</span></span>
34. <span data-ttu-id="cec6d-168">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="cec6d-168">Click Add.</span></span>
35. <span data-ttu-id="cec6d-169">Fare clic su Costante testo.</span><span class="sxs-lookup"><span data-stu-id="cec6d-169">Click Text constant.</span></span>
36. <span data-ttu-id="cec6d-170">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cec6d-170">In the list, mark the selected row.</span></span>
37. <span data-ttu-id="cec6d-171">Digitare un valore nel campo Testo.</span><span class="sxs-lookup"><span data-stu-id="cec6d-171">In the Text field, type a value.</span></span>
38. <span data-ttu-id="cec6d-172">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="cec6d-172">Click Add.</span></span>
39. <span data-ttu-id="cec6d-173">Fare clic su Valore sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="cec6d-173">Click Number sequence value.</span></span>
40. <span data-ttu-id="cec6d-174">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cec6d-174">In the list, mark the selected row.</span></span>
41. <span data-ttu-id="cec6d-175">Nel campo Sequenza numerica immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="cec6d-175">In the Number sequence field, enter or select a value.</span></span>
42. <span data-ttu-id="cec6d-176">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cec6d-176">Close the page.</span></span>
43. <span data-ttu-id="cec6d-177">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cec6d-177">Close the page.</span></span>
44. <span data-ttu-id="cec6d-178">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cec6d-178">Close the page.</span></span>

