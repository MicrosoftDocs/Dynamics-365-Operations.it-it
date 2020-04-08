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
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a837721db5281b0626f37b7a793349b91afa6f85
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147758"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="a24c3-103">Creare una nomenclatura del numero di prodotto per le varianti prodotto configurate</span><span class="sxs-lookup"><span data-stu-id="a24c3-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a24c3-104">In questa procedura viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto configurate e come può essere collegata a una rappresentazione generale prodotto configurabile.</span><span class="sxs-lookup"><span data-stu-id="a24c3-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="a24c3-105">Questa procedura dimostra anche come è possibile creare una nomenclatura di configurazione per un componente del modello di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="a24c3-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="a24c3-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="a24c3-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a24c3-107">La nuova nomenclatura di numero prodotto è assegnata alla rappresentazione generale prodotto D0004.</span><span class="sxs-lookup"><span data-stu-id="a24c3-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="a24c3-108">Questa attività viene in genere effettuata da un responsabile del design del prodotto.</span><span class="sxs-lookup"><span data-stu-id="a24c3-108">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="a24c3-109">Creare una nomenclatura di numero prodotto</span><span class="sxs-lookup"><span data-stu-id="a24c3-109">Create a product number nomenclature</span></span>
1. <span data-ttu-id="a24c3-110">Fare clic su Definizione modello di variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="a24c3-110">Click Product variant model definition.</span></span>
2. <span data-ttu-id="a24c3-111">Fare clic su Nomenclatura di prodotto.</span><span class="sxs-lookup"><span data-stu-id="a24c3-111">Click Product nomenclature.</span></span>
3. <span data-ttu-id="a24c3-112">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a24c3-112">Click New.</span></span>
4. <span data-ttu-id="a24c3-113">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="a24c3-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="a24c3-114">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="a24c3-114">In the Description field, type a value.</span></span>
6. <span data-ttu-id="a24c3-115">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a24c3-115">Click Add.</span></span>
7. <span data-ttu-id="a24c3-116">Fare clic su Numero rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="a24c3-116">Click Product master number.</span></span>
8. <span data-ttu-id="a24c3-117">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a24c3-117">Click Add.</span></span>
9. <span data-ttu-id="a24c3-118">Fare clic su Costante testo.</span><span class="sxs-lookup"><span data-stu-id="a24c3-118">Click Text constant.</span></span>
10. <span data-ttu-id="a24c3-119">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a24c3-119">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="a24c3-120">Digitare un valore nel campo Testo.</span><span class="sxs-lookup"><span data-stu-id="a24c3-120">In the Text field, type a value.</span></span>
12. <span data-ttu-id="a24c3-121">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a24c3-121">Click Add.</span></span>
13. <span data-ttu-id="a24c3-122">Fare clic su Configurazione.</span><span class="sxs-lookup"><span data-stu-id="a24c3-122">Click Configuration.</span></span>
14. <span data-ttu-id="a24c3-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a24c3-123">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="a24c3-124">Assegnare la nomenclatura di un numero prodotto a una rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="a24c3-124">Assign the product number nomenclature to a product master</span></span>
1. <span data-ttu-id="a24c3-125">Fare clic su Rappresentazioni generali prodotto.</span><span class="sxs-lookup"><span data-stu-id="a24c3-125">Click Product masters.</span></span>
2. <span data-ttu-id="a24c3-126">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="a24c3-126">Use the Quick Filter to find records.</span></span> <span data-ttu-id="a24c3-127">Ad esempio, filtrare in base al campo Numero prodotto con un valore di 'D'.</span><span class="sxs-lookup"><span data-stu-id="a24c3-127">For example, filter on the Product number field with a value of 'D'.</span></span>
3. <span data-ttu-id="a24c3-128">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a24c3-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a24c3-129">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="a24c3-129">Click Edit.</span></span>
5. <span data-ttu-id="a24c3-130">Selezionare Sì nel campo Utilizza nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="a24c3-130">Select Yes in the Use nomenclature field.</span></span>
6. <span data-ttu-id="a24c3-131">Nel campo Nomenclatura di numero di variante prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a24c3-131">In the Product variant number nomenclature field, enter or select a value.</span></span>
7. <span data-ttu-id="a24c3-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a24c3-132">Close the page.</span></span>
8. <span data-ttu-id="a24c3-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a24c3-133">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="a24c3-134">Creare una nomenclatura per un componente di modello di configurazione prodotto</span><span class="sxs-lookup"><span data-stu-id="a24c3-134">Create nomenclature for a product configuration model component</span></span>
1. <span data-ttu-id="a24c3-135">Fare clic su Modelli di configurazione prodotto.</span><span class="sxs-lookup"><span data-stu-id="a24c3-135">Click Product configuration models.</span></span>
2. <span data-ttu-id="a24c3-136">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="a24c3-136">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="a24c3-137">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a24c3-137">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a24c3-138">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="a24c3-138">Click Edit.</span></span>
5. <span data-ttu-id="a24c3-139">Selezionare Sì nel campo Utilizza nomenclatura di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a24c3-139">Select Yes in the Use configuration nomenclature field.</span></span>
6. <span data-ttu-id="a24c3-140">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a24c3-140">Click Add.</span></span>
7. <span data-ttu-id="a24c3-141">Fare clic su Valore attributo.</span><span class="sxs-lookup"><span data-stu-id="a24c3-141">Click Attribute value.</span></span>
8. <span data-ttu-id="a24c3-142">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a24c3-142">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="a24c3-143">Nel campo Attributo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a24c3-143">In the Attribute field, enter or select a value.</span></span>
10. <span data-ttu-id="a24c3-144">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a24c3-144">Click Add.</span></span>
11. <span data-ttu-id="a24c3-145">Fare clic su Costante testo.</span><span class="sxs-lookup"><span data-stu-id="a24c3-145">Click Text constant.</span></span>
12. <span data-ttu-id="a24c3-146">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a24c3-146">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="a24c3-147">Digitare un valore nel campo Testo.</span><span class="sxs-lookup"><span data-stu-id="a24c3-147">In the Text field, type a value.</span></span>
14. <span data-ttu-id="a24c3-148">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a24c3-148">Click Add.</span></span>
15. <span data-ttu-id="a24c3-149">Fare clic su Valore attributo.</span><span class="sxs-lookup"><span data-stu-id="a24c3-149">Click Attribute value.</span></span>
16. <span data-ttu-id="a24c3-150">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a24c3-150">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="a24c3-151">Nel campo Attributo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a24c3-151">In the Attribute field, enter or select a value.</span></span>
18. <span data-ttu-id="a24c3-152">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a24c3-152">Click Add.</span></span>
19. <span data-ttu-id="a24c3-153">Fare clic su Costante testo.</span><span class="sxs-lookup"><span data-stu-id="a24c3-153">Click Text constant.</span></span>
20. <span data-ttu-id="a24c3-154">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a24c3-154">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="a24c3-155">Digitare un valore nel campo Testo.</span><span class="sxs-lookup"><span data-stu-id="a24c3-155">In the Text field, type a value.</span></span>
22. <span data-ttu-id="a24c3-156">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a24c3-156">Click Add.</span></span>
23. <span data-ttu-id="a24c3-157">Fare clic su Valore attributo.</span><span class="sxs-lookup"><span data-stu-id="a24c3-157">Click Attribute value.</span></span>
24. <span data-ttu-id="a24c3-158">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a24c3-158">In the list, mark the selected row.</span></span>
25. <span data-ttu-id="a24c3-159">Nel campo Attributo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a24c3-159">In the Attribute field, enter or select a value.</span></span>
26. <span data-ttu-id="a24c3-160">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a24c3-160">Click Add.</span></span>
27. <span data-ttu-id="a24c3-161">Fare clic su Costante testo.</span><span class="sxs-lookup"><span data-stu-id="a24c3-161">Click Text constant.</span></span>
28. <span data-ttu-id="a24c3-162">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a24c3-162">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="a24c3-163">Digitare un valore nel campo Testo.</span><span class="sxs-lookup"><span data-stu-id="a24c3-163">In the Text field, type a value.</span></span>
30. <span data-ttu-id="a24c3-164">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a24c3-164">Click Add.</span></span>
31. <span data-ttu-id="a24c3-165">Fare clic su Valore attributo.</span><span class="sxs-lookup"><span data-stu-id="a24c3-165">Click Attribute value.</span></span>
32. <span data-ttu-id="a24c3-166">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a24c3-166">In the list, mark the selected row.</span></span>
33. <span data-ttu-id="a24c3-167">Nel campo Attributo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a24c3-167">In the Attribute field, enter or select a value.</span></span>
34. <span data-ttu-id="a24c3-168">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a24c3-168">Click Add.</span></span>
35. <span data-ttu-id="a24c3-169">Fare clic su Costante testo.</span><span class="sxs-lookup"><span data-stu-id="a24c3-169">Click Text constant.</span></span>
36. <span data-ttu-id="a24c3-170">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a24c3-170">In the list, mark the selected row.</span></span>
37. <span data-ttu-id="a24c3-171">Digitare un valore nel campo Testo.</span><span class="sxs-lookup"><span data-stu-id="a24c3-171">In the Text field, type a value.</span></span>
38. <span data-ttu-id="a24c3-172">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a24c3-172">Click Add.</span></span>
39. <span data-ttu-id="a24c3-173">Fare clic su Valore sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="a24c3-173">Click Number sequence value.</span></span>
40. <span data-ttu-id="a24c3-174">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a24c3-174">In the list, mark the selected row.</span></span>
41. <span data-ttu-id="a24c3-175">Nel campo Sequenza numerica immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a24c3-175">In the Number sequence field, enter or select a value.</span></span>
42. <span data-ttu-id="a24c3-176">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a24c3-176">Close the page.</span></span>
43. <span data-ttu-id="a24c3-177">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a24c3-177">Close the page.</span></span>
44. <span data-ttu-id="a24c3-178">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a24c3-178">Close the page.</span></span>

