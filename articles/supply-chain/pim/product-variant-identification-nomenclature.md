---
title: Nomenclatura di nomi e numeri di varianti prodotto
description: "In questo argomento viene descritto come impostare la nomenclatura per il numero prodotto per sostituire il formato fisso [Numero rappresentazione generale prodotto - Configurazione - Dimensione - Colore - Stile]. La nuova nomenclatura ha un formato di destinazione che include il numero della rappresentazione generale prodotto, le dimensioni prodotto attive e i delimitatori di testo scelti. È inoltre possibile creare una nomenclatura per i nomi di prodotto. Infine, è anche possibile creare una nomenclatura per identificare le configurazioni create in base alla configurazione basata su vincoli del prodotto. Queste nomenclature possono includere gli attributi scelti."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 4ebebc1d287908dbe8ac7557c34fc6693c88bfae
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="nomenclature-of-product-variant-numbers-and-names"></a><span data-ttu-id="cf407-107">Nomenclatura di nomi e numeri di varianti prodotto</span><span class="sxs-lookup"><span data-stu-id="cf407-107">Nomenclature of product variant numbers and names</span></span>

<span data-ttu-id="cf407-108">In questo argomento viene descritto come impostare la nomenclatura per il numero prodotto per sostituire il formato fisso [Numero rappresentazione generale prodotto - Configurazione - Dimensione - Colore - Stile].</span><span class="sxs-lookup"><span data-stu-id="cf407-108">This topic describes how you can set up a product number nomenclature to replace the fixed [Product master number - Configuration - Size - Color - Style] format.</span></span> <span data-ttu-id="cf407-109">La nuova nomenclatura ha un formato di destinazione che include il numero della rappresentazione generale prodotto, le dimensioni prodotto attive e i delimitatori di testo scelti.</span><span class="sxs-lookup"><span data-stu-id="cf407-109">The new nomenclature has a targeted format that includes the product master number, active product dimensions, and text delimiters of your choice.</span></span> <span data-ttu-id="cf407-110">È inoltre possibile creare una nomenclatura per i nomi di prodotto.</span><span class="sxs-lookup"><span data-stu-id="cf407-110">You can also create a nomenclature for product names.</span></span> <span data-ttu-id="cf407-111">Infine, è anche possibile creare una nomenclatura per identificare le configurazioni create in base alla configurazione basata su vincoli del prodotto.</span><span class="sxs-lookup"><span data-stu-id="cf407-111">Finally, you can build a nomenclature to identify configurations that are created by the constraint-based product configurator.</span></span> <span data-ttu-id="cf407-112">Queste nomenclature possono includere gli attributi scelti.</span><span class="sxs-lookup"><span data-stu-id="cf407-112">These nomenclatures can contain attributes of your choice.</span></span>

<span data-ttu-id="cf407-113">Le nuove nomenclature per i numeri di varianti prodotto e i nomi di varianti prodotto consentono di includere segmenti negli identificatori per le varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="cf407-113">The new nomenclatures for product variant numbers and product variant names let you include segments in the identifiers for product variants.</span></span> <span data-ttu-id="cf407-114">I segmenti possono includere il nome e il numero della rappresentazione generale prodotto, i nomi e gli ID delle dimensioni prodotto, le sequenze numeriche, le costanti di testo e gli attributi.</span><span class="sxs-lookup"><span data-stu-id="cf407-114">These segments can include the product master number and name, product dimension IDs and names, number sequences, text constants, and attributes.</span></span> <span data-ttu-id="cf407-115">Questa funzionalità consente di trovare velocemente una variante prodotto specifica quando si crea un ordine cliente o un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="cf407-115">This functionality lets you quickly find a specific product variant when you create a sales order or a purchase order.</span></span> <span data-ttu-id="cf407-116">È possibile creare nomenclature per i numeri di varianti prodotto e i nomi di varianti prodotto utilizzando la pagina **Nomenclatura di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="cf407-116">You create nomenclatures for both product variant numbers and product variant names by using the **Product nomenclature** page.</span></span> <span data-ttu-id="cf407-117">Per aprire questa pagina, fare clic su **Gestione informazioni sul prodotto** &gt; **Impostazione**.</span><span class="sxs-lookup"><span data-stu-id="cf407-117">To open this page, click **Product information management** &gt; **Setup**.</span></span>

## <a name="nomenclature-of-predefined-product-variants"></a><span data-ttu-id="cf407-118">Nomenclatura di varianti prodotto predefinite</span><span class="sxs-lookup"><span data-stu-id="cf407-118">Nomenclature of predefined product variants</span></span>
<span data-ttu-id="cf407-119">Le varianti prodotto vengono generate per le rappresentazioni generali prodotto in base a una delle tre tecnologie di configurazione:</span><span class="sxs-lookup"><span data-stu-id="cf407-119">Product variants are generated for product masters according to one of three configuration technologies:</span></span>

-   <span data-ttu-id="cf407-120">Varianti predefinite</span><span class="sxs-lookup"><span data-stu-id="cf407-120">Predefined variants</span></span>
-   <span data-ttu-id="cf407-121">Basata su vincoli</span><span class="sxs-lookup"><span data-stu-id="cf407-121">Constraint-based</span></span>
-   <span data-ttu-id="cf407-122">Basata su dimensioni</span><span class="sxs-lookup"><span data-stu-id="cf407-122">Dimension-based</span></span>

<span data-ttu-id="cf407-123">A ogni variante prodotto è associato un numero e un nome e le nomenclature dell'identificazione variante prodotto consente di selezionare i segmenti che verranno inclusi in ciascun numero di variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="cf407-123">Each product variant has a number and a name, and the product variant identification nomenclatures let you select the segments that will be included in each product variant number or name.</span></span> <span data-ttu-id="cf407-124">È possibile selezionare i segmenti che seguono nella pagina **Nomenclatura di prodotto**:</span><span class="sxs-lookup"><span data-stu-id="cf407-124">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="cf407-125">Numero rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="cf407-125">Product master number</span></span>
-   <span data-ttu-id="cf407-126">Nome rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="cf407-126">Product master name</span></span>
-   <span data-ttu-id="cf407-127">Valore sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="cf407-127">Number sequence value</span></span>
-   <span data-ttu-id="cf407-128">Costante testo</span><span class="sxs-lookup"><span data-stu-id="cf407-128">Text constant</span></span>
-   <span data-ttu-id="cf407-129">Dimensioni prodotto</span><span class="sxs-lookup"><span data-stu-id="cf407-129">Product dimensions</span></span>
    -   <span data-ttu-id="cf407-130">Nome o ID configurazione</span><span class="sxs-lookup"><span data-stu-id="cf407-130">Configuration ID or name</span></span>
    -   <span data-ttu-id="cf407-131">Nome o ID colore</span><span class="sxs-lookup"><span data-stu-id="cf407-131">Color ID or name</span></span>
    -   <span data-ttu-id="cf407-132">Nome o ID dimensione</span><span class="sxs-lookup"><span data-stu-id="cf407-132">Size ID or name</span></span>
    -   <span data-ttu-id="cf407-133">Nome o ID stile</span><span class="sxs-lookup"><span data-stu-id="cf407-133">Style ID or name</span></span>

<span data-ttu-id="cf407-134">Una volta definita, la nomenclatura numero di identificazione variante prodotto può essere associata a un gruppo di dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="cf407-134">After you define a product variant identification number nomenclature, you can associate it with a product dimension group.</span></span> <span data-ttu-id="cf407-135">A tutte le rappresentazioni generali prodotto che fanno riferimento al gruppo di dimensioni prodotto verranno assegnati i numeri di varianti prodotto in base alla nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="cf407-135">All product masters that reference this product dimension group will then be assigned product variant numbers according to the nomenclature.</span></span> <span data-ttu-id="cf407-136">Tuttavia, le nomenclature nome di variante prodotto non possono essere associate ai gruppi di dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="cf407-136">However, product variant name nomenclatures can't be associated with product dimension groups.</span></span> <span data-ttu-id="cf407-137">È inoltre possibile assegnare una nomenclatura identificazione variante prodotto direttamente a una rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="cf407-137">You can also assign a product variant identification nomenclature directly to a product master.</span></span> <span data-ttu-id="cf407-138">In questo caso, alle varianti prodotto che appartengono alla rappresentazione generale prodotto verranno assegnati i numeri e i nomi di variante prodotto in base alle nomenclature.</span><span class="sxs-lookup"><span data-stu-id="cf407-138">In this case, the product variants that belong to the product master will be assigned product variant numbers and names according to the nomenclatures.</span></span>

### <a name="example"></a><span data-ttu-id="cf407-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf407-139">Example</span></span>

<span data-ttu-id="cf407-140">Una maglietta (TS1234) viene prodotta in tre dimensioni (S, M, L), quattro colori (rosso, verde, blu, giallo) e due stili (polo, a V).</span><span class="sxs-lookup"><span data-stu-id="cf407-140">A T-shirt (TS1234) is produced in three sizes (S, M, L), four colors (Red, Green, Blue, Yellow), and two styles (Polo, V).</span></span> <span data-ttu-id="cf407-141">Di conseguenza, 24 varianti prodotto sono possibili = (3 × 4 × 2).</span><span class="sxs-lookup"><span data-stu-id="cf407-141">Therefore, 24 product variants are possible (= 3 × 4 × 2).</span></span> <span data-ttu-id="cf407-142">Creare una nomenclatura numero di varianti prodotto contenente i segmenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf407-142">You create a product variant number nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="cf407-143">Numero rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="cf407-143">Product master number</span></span>
2.  <span data-ttu-id="cf407-144">Costante testo: "-"</span><span class="sxs-lookup"><span data-stu-id="cf407-144">Text constant: "-"</span></span>
3.  <span data-ttu-id="cf407-145">Colore</span><span class="sxs-lookup"><span data-stu-id="cf407-145">Color</span></span>
4.  <span data-ttu-id="cf407-146">Costante testo: "-"</span><span class="sxs-lookup"><span data-stu-id="cf407-146">Text constant: "-"</span></span>
5.  <span data-ttu-id="cf407-147">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="cf407-147">Size</span></span>
6.  <span data-ttu-id="cf407-148">Costante testo: "-"</span><span class="sxs-lookup"><span data-stu-id="cf407-148">Text constant: "-"</span></span>
7.  <span data-ttu-id="cf407-149">Stile</span><span class="sxs-lookup"><span data-stu-id="cf407-149">Style</span></span>

<span data-ttu-id="cf407-150">In questo caso, il numero di variante prodotto per la polo piccola e rossa sarà TS1234-Red-Small-Polo.</span><span class="sxs-lookup"><span data-stu-id="cf407-150">In this case, the product variant number for a red, small, polo T-shirt will be TS1234-Red-Small-Polo.</span></span>

## <a name="nomenclature-of-constraintbased-configurations"></a><span data-ttu-id="cf407-151">Nomenclatura delle configurazioni basate su vincoli</span><span class="sxs-lookup"><span data-stu-id="cf407-151">Nomenclature of constraintbased configurations</span></span>
<span data-ttu-id="cf407-152">Per le configurazioni basate su vincoli, è possibile creare una nomenclatura dedicata per la dimensione prodotto della configurazione.</span><span class="sxs-lookup"><span data-stu-id="cf407-152">For constraint-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="cf407-153">È possibile selezionare i segmenti che seguono nella pagina **Nomenclatura di prodotto**:</span><span class="sxs-lookup"><span data-stu-id="cf407-153">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="cf407-154">Valore sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="cf407-154">Number sequence value</span></span>
-   <span data-ttu-id="cf407-155">Costante testo</span><span class="sxs-lookup"><span data-stu-id="cf407-155">Text constant</span></span>
-   <span data-ttu-id="cf407-156">Valore attributo</span><span class="sxs-lookup"><span data-stu-id="cf407-156">Attribute value</span></span>

<span data-ttu-id="cf407-157">Ciascun componente in un modello di configurazione prodotto può avere la propria nomenclatura di configurazione.</span><span class="sxs-lookup"><span data-stu-id="cf407-157">Each component in a product configuration model can have its own configuration nomenclature.</span></span> <span data-ttu-id="cf407-158">Solo gli attributi che appartengono al componente possono essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="cf407-158">Only attributes that belong to the component can be used.</span></span> <span data-ttu-id="cf407-159">Gli attributi di componenti secondari o dei requisiti dell'utente non possono essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="cf407-159">Attributes from subcomponents or user requirements can't be used.</span></span>

### <a name="example"></a><span data-ttu-id="cf407-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf407-160">Example</span></span>

<span data-ttu-id="cf407-161">Un modello di configurazione prodotto ha un componente principale con due attributi:</span><span class="sxs-lookup"><span data-stu-id="cf407-161">A product configuration model has a root component that has two attributes:</span></span>

-   <span data-ttu-id="cf407-162">Materiale (plastica, legno, acciaio)</span><span class="sxs-lookup"><span data-stu-id="cf407-162">Material (Plastic, Wood, Steel)</span></span>
-   <span data-ttu-id="cf407-163">Lunghezza (10...100)</span><span class="sxs-lookup"><span data-stu-id="cf407-163">Length (10...100)</span></span>

<span data-ttu-id="cf407-164">Creare una nomenclatura configurazione contenente i segmenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf407-164">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="cf407-165">Valore attributo: materiale</span><span class="sxs-lookup"><span data-stu-id="cf407-165">Attribute value: Material</span></span>
2.  <span data-ttu-id="cf407-166">Costante testo: "AAA"</span><span class="sxs-lookup"><span data-stu-id="cf407-166">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="cf407-167">Valore attributo: lunghezza</span><span class="sxs-lookup"><span data-stu-id="cf407-167">Attribute value: Length</span></span>

<span data-ttu-id="cf407-168">In questo caso, l'ID configurazione per il materiale legno con una lunghezza di 78 sarà WoodAAA78.</span><span class="sxs-lookup"><span data-stu-id="cf407-168">In this case, the configuration ID for wood material that has a length of 78 will be WoodAAA78.</span></span>

## <a name="nomenclature-of-dimensionbased-configurations"></a><span data-ttu-id="cf407-169">Nomenclatura di configurazioni basate su dimensioni</span><span class="sxs-lookup"><span data-stu-id="cf407-169">Nomenclature of dimensionbased configurations</span></span>
<span data-ttu-id="cf407-170">Per le configurazioni basate su dimensioni, è possibile creare una nomenclatura dedicata per la dimensione prodotto della configurazione.</span><span class="sxs-lookup"><span data-stu-id="cf407-170">For dimension-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="cf407-171">È possibile selezionare i segmenti che seguono nella pagina **Nomenclatura di prodotto**:</span><span class="sxs-lookup"><span data-stu-id="cf407-171">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="cf407-172">Valore sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="cf407-172">Number sequence value</span></span>
-   <span data-ttu-id="cf407-173">Costante testo</span><span class="sxs-lookup"><span data-stu-id="cf407-173">Text constant</span></span>
-   <span data-ttu-id="cf407-174">Articolo gruppo di configurazioni</span><span class="sxs-lookup"><span data-stu-id="cf407-174">Configuration group item</span></span>

<span data-ttu-id="cf407-175">È possibile definire una nomenclatura di configurazione per una distinta base (DBA).</span><span class="sxs-lookup"><span data-stu-id="cf407-175">You can define a configuration nomenclature for a bill of materials (BOM).</span></span>

### <a name="example"></a><span data-ttu-id="cf407-176">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf407-176">Example</span></span>

<span data-ttu-id="cf407-177">La DBA è composta da quattro righe DBA divise in due gruppi di configurazioni:</span><span class="sxs-lookup"><span data-stu-id="cf407-177">A BOM has four BOM lines that are divided into two configuration groups:</span></span>

-   <span data-ttu-id="cf407-178">Riga DBA: M0007, cabinet predefinito</span><span class="sxs-lookup"><span data-stu-id="cf407-178">BOM line: M0007, Standard cabinet</span></span>
    -   <span data-ttu-id="cf407-179">Gruppo di configurazioni: cabinet</span><span class="sxs-lookup"><span data-stu-id="cf407-179">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="cf407-180">Riga DBA: M0008, cabinet di fascia alta</span><span class="sxs-lookup"><span data-stu-id="cf407-180">BOM line: M0008, High end cabinet</span></span>
    -   <span data-ttu-id="cf407-181">Gruppo di configurazioni: cabinet</span><span class="sxs-lookup"><span data-stu-id="cf407-181">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="cf407-182">Riga DBA: M0021, panno della griglia anteriore</span><span class="sxs-lookup"><span data-stu-id="cf407-182">BOM line: M0021, Front grill cloth</span></span>
    -   <span data-ttu-id="cf407-183">Gruppo di configurazioni: griglia anteriore</span><span class="sxs-lookup"><span data-stu-id="cf407-183">Configuration group: Front grill</span></span>
-   <span data-ttu-id="cf407-184">Riga DBA: M0022, metallo della griglia anteriore</span><span class="sxs-lookup"><span data-stu-id="cf407-184">BOM line: M0022, Front grill metal</span></span>
    -   <span data-ttu-id="cf407-185">Gruppo di configurazioni: griglia anteriore</span><span class="sxs-lookup"><span data-stu-id="cf407-185">Configuration group: Front grill</span></span>

<span data-ttu-id="cf407-186">Creare una nomenclatura configurazione contenente i segmenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf407-186">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="cf407-187">Gruppo di configurazioni: cabinet</span><span class="sxs-lookup"><span data-stu-id="cf407-187">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="cf407-188">Costante testo: "&"</span><span class="sxs-lookup"><span data-stu-id="cf407-188">Text constant: "&"</span></span>
3.  <span data-ttu-id="cf407-189">Gruppo di configurazioni: griglia anteriore</span><span class="sxs-lookup"><span data-stu-id="cf407-189">Configuration group: Front grill</span></span>

<span data-ttu-id="cf407-190">In questo caso, l'ID di configurazione per un cabinet standard con panno della griglia anteriore sarà M0007&M0021.</span><span class="sxs-lookup"><span data-stu-id="cf407-190">In this case, the configuration ID for a standard cabinet that has a cloth front grill will be M0007&M0021.</span></span>

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a><span data-ttu-id="cf407-191">Nomenclatura per una combinazione di varianti prodotto e configurazioni</span><span class="sxs-lookup"><span data-stu-id="cf407-191">Nomenclature for a combination of product variants and configurations</span></span>
<span data-ttu-id="cf407-192">Quando si utilizza la tecnologia di configurazione basata su vincoli o su dimensioni per configurare le varianti prodotto per una rappresentazione generale prodotto, i numeri delle varianti prodotto possono includere la nomenclatura dalla dimensione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="cf407-192">When you use either the constraint-based configuration technology or the dimension-based configuration technology to configure product variants for a product master, the product variant numbers of the product variants can include the nomenclature from the configuration dimension.</span></span> <span data-ttu-id="cf407-193">Attenersi a questa procedura per configurare le varianti.</span><span class="sxs-lookup"><span data-stu-id="cf407-193">Follow these steps to configure variants.</span></span>

1.  <span data-ttu-id="cf407-194">Definire una nomenclatura del numero di varianti prodotto che includa la dimensione di configurazione nella pagina **Nomenclatura di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="cf407-194">On the **Product nomenclature** page, define a product variant number nomenclature that includes the configuration dimension.</span></span>
2.  <span data-ttu-id="cf407-195">Assegnare questa nomenclatura a un gruppo di dimensioni prodotto con la dimensione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="cf407-195">Assign the nomenclature to a product dimension group that has the configuration dimension.</span></span>
3.  <span data-ttu-id="cf407-196">Definire una nomenclatura di configurazione per i componenti o le DBA che verranno utilizzate per la configurazione di varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="cf407-196">Define a configuration nomenclature for the components or BOMs that will be used to configure the product variants.</span></span>

<span data-ttu-id="cf407-197">È inoltre possibile creare le nomenclature per i nomi di varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="cf407-197">You can also create nomenclatures for the product variant names.</span></span> <span data-ttu-id="cf407-198">I nomi di varianti prodotto possono essere configurati per includere il nome o l'ID configurazione.</span><span class="sxs-lookup"><span data-stu-id="cf407-198">The product variant names can be configured to include the configuration ID or name.</span></span>

### <a name="example-for-constraint-based-configurations"></a><span data-ttu-id="cf407-199">Esempio per le configurazioni basate su vincoli</span><span class="sxs-lookup"><span data-stu-id="cf407-199">Example for constraint-based configurations</span></span>

<span data-ttu-id="cf407-200">In questo esempio è possibile utilizzare una nomenclatura del numero di varianti prodotto costituita dai seguenti segmenti:</span><span class="sxs-lookup"><span data-stu-id="cf407-200">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="cf407-201">Numero rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="cf407-201">Product master number</span></span>
2.  <span data-ttu-id="cf407-202">Costante testo "\_"</span><span class="sxs-lookup"><span data-stu-id="cf407-202">Text constant "\_"</span></span>
3.  <span data-ttu-id="cf407-203">Configurazione</span><span class="sxs-lookup"><span data-stu-id="cf407-203">Configuration</span></span>

<span data-ttu-id="cf407-204">La nomenclatura di configurazione consiste nei seguenti segmenti:</span><span class="sxs-lookup"><span data-stu-id="cf407-204">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="cf407-205">Valore attributo: materiale</span><span class="sxs-lookup"><span data-stu-id="cf407-205">Attribute value: Material</span></span>
2.  <span data-ttu-id="cf407-206">Costante testo: "AAA"</span><span class="sxs-lookup"><span data-stu-id="cf407-206">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="cf407-207">Valore attributo: lunghezza</span><span class="sxs-lookup"><span data-stu-id="cf407-207">Attribute value: Length</span></span>

<span data-ttu-id="cf407-208">Immettere i seguenti valori per segmenti:</span><span class="sxs-lookup"><span data-stu-id="cf407-208">You enter the following values for segments:</span></span>

-   <span data-ttu-id="cf407-209">Numero rappresentazione generale prodotto = **M0099**</span><span class="sxs-lookup"><span data-stu-id="cf407-209">Product master number = **M0099**</span></span>
-   <span data-ttu-id="cf407-210">Materiale = **Plastic**</span><span class="sxs-lookup"><span data-stu-id="cf407-210">Material = **Plastic**</span></span>
-   <span data-ttu-id="cf407-211">Lunghezza = **12**</span><span class="sxs-lookup"><span data-stu-id="cf407-211">Length = **12**</span></span>

<span data-ttu-id="cf407-212">In questo caso, il numero di varianti prodotto diventerà M0099\_PlasticAAA12.</span><span class="sxs-lookup"><span data-stu-id="cf407-212">In this case, the product variant number will be M0099\_PlasticAAA12.</span></span>

### <a name="example-for-dimension-based-configurations"></a><span data-ttu-id="cf407-213">Esempio per le configurazioni basate su dimensioni</span><span class="sxs-lookup"><span data-stu-id="cf407-213">Example for dimension-based configurations</span></span>

<span data-ttu-id="cf407-214">In questo esempio è possibile utilizzare una nomenclatura del numero di varianti prodotto costituita dai seguenti segmenti:</span><span class="sxs-lookup"><span data-stu-id="cf407-214">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="cf407-215">Numero rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="cf407-215">Product master number</span></span>
2.  <span data-ttu-id="cf407-216">Costante testo "//"</span><span class="sxs-lookup"><span data-stu-id="cf407-216">Text constant "//"</span></span>
3.  <span data-ttu-id="cf407-217">Configurazione</span><span class="sxs-lookup"><span data-stu-id="cf407-217">Configuration</span></span>

<span data-ttu-id="cf407-218">La nomenclatura di configurazione consiste nei seguenti segmenti:</span><span class="sxs-lookup"><span data-stu-id="cf407-218">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="cf407-219">Gruppo di configurazioni: cabinet</span><span class="sxs-lookup"><span data-stu-id="cf407-219">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="cf407-220">Costante testo: "&"</span><span class="sxs-lookup"><span data-stu-id="cf407-220">Text constant: "&"</span></span>
3.  <span data-ttu-id="cf407-221">Gruppo di configurazioni: griglia anteriore</span><span class="sxs-lookup"><span data-stu-id="cf407-221">Configuration group: Front grill</span></span>

<span data-ttu-id="cf407-222">Immettere i seguenti valori per segmenti:</span><span class="sxs-lookup"><span data-stu-id="cf407-222">You enter the following values for segments:</span></span>

-   <span data-ttu-id="cf407-223">Numero rappresentazione generale prodotto = **D0123**</span><span class="sxs-lookup"><span data-stu-id="cf407-223">Product master number = **D0123**</span></span>
-   <span data-ttu-id="cf407-224">Cabinet = **M0008**</span><span class="sxs-lookup"><span data-stu-id="cf407-224">Cabinet = **M0008**</span></span>
-   <span data-ttu-id="cf407-225">Griglia anteriore = **M0022**</span><span class="sxs-lookup"><span data-stu-id="cf407-225">Front grill = **M0022**</span></span>

<span data-ttu-id="cf407-226">In questo caso, il numero di varianti prodotto diventerà D0123//M0008&M0022.</span><span class="sxs-lookup"><span data-stu-id="cf407-226">In this case, the product variant number will be D0123//M0008&M0022.</span></span>

## <a name="numbering-conflicts"></a><span data-ttu-id="cf407-227">Conflitti di numerazione</span><span class="sxs-lookup"><span data-stu-id="cf407-227">Numbering conflicts</span></span>
<span data-ttu-id="cf407-228">In alcuni casi, è possibile impostare una nomenclatura del numero di varianti prodotto che non generi numeri univoci di varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="cf407-228">In some cases, a product variant number nomenclature that you set up might not produce unique product variant numbers.</span></span> <span data-ttu-id="cf407-229">Ad esempio, i numeri di varianti prodotto non sarebbero univoci se una dimensione prodotto attiva non è inclusa nella nomenclatura per una rappresentazione generale prodotto che utilizzi la tecnologia di configurazione varianti predefinita.</span><span class="sxs-lookup"><span data-stu-id="cf407-229">For example, the product variant numbers won't be unique if one active product dimension isn't included in the nomenclature for a product master that uses the predefined variant configuration technology.</span></span> <span data-ttu-id="cf407-230">Il modo in cui si gestiscono i conflitti varia in base alla tecnologia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="cf407-230">The way that you handle conflicts varies, depending on the configuration technology.</span></span>

### <a name="predefined-variants"></a><span data-ttu-id="cf407-231">Varianti predefinite</span><span class="sxs-lookup"><span data-stu-id="cf407-231">Predefined variants</span></span>

<span data-ttu-id="cf407-232">Si verifica un errore se si tenta di creare manualmente o generare automaticamente varianti prodotto in cui più varianti prodotto finiscono con lo stesso numero.</span><span class="sxs-lookup"><span data-stu-id="cf407-232">An error occurs if you try to manually create or automatically generate product variants, and more than one product variant ends up with the same product variant number.</span></span> <span data-ttu-id="cf407-233">Per evitare questo scenario, è necessario utilizzare tutte le dimensioni prodotto attive nel gruppo di dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="cf407-233">To avoid this scenario, you should use all active product dimensions in the product dimension group.</span></span> <span data-ttu-id="cf407-234">In alternativa, includere una sequenza numerica per garantire che i numeri di varianti prodotto siano univoci.</span><span class="sxs-lookup"><span data-stu-id="cf407-234">Alternatively, include a number sequence to help guarantee that the product variant numbers are unique.</span></span>

### <a name="constraint-based-configurations"></a><span data-ttu-id="cf407-235">Configurazioni basata su vincoli</span><span class="sxs-lookup"><span data-stu-id="cf407-235">Constraint-based configurations</span></span>

<span data-ttu-id="cf407-236">A seconda della nomenclatura, il sistema può tentare di assegnare un numero di variante prodotto non univoco a una configurazione.</span><span class="sxs-lookup"><span data-stu-id="cf407-236">Depending on the nomenclature, the system might try to assign a non-unique product variant number to a configuration.</span></span> <span data-ttu-id="cf407-237">In questo caso viene utilizzata la sequenza numerica per la dimensione di configurazione come numero di variante prodotto e viene visualizzato un avviso.</span><span class="sxs-lookup"><span data-stu-id="cf407-237">In this case, the system uses the number sequence for the configuration dimension as the product variant number instead, and you receive a warning.</span></span> <span data-ttu-id="cf407-238">Per evitare questo scenario, includere sufficienti attributi nella nomenclature per garantire che i numeri di varianti prodotto siano univoci.</span><span class="sxs-lookup"><span data-stu-id="cf407-238">To avoid this scenario, you should include enough attributes in the nomenclature to help guarantee unique product variant numbers.</span></span> <span data-ttu-id="cf407-239">È inoltre necessario assicurarsi che l'opzione **Riutilizza** sia attivata per il componente.</span><span class="sxs-lookup"><span data-stu-id="cf407-239">You should also make sure that the **Reuse** option is turned on for the component.</span></span>

### <a name="dimension-based-configurations"></a><span data-ttu-id="cf407-240">Configurazioni basate su dimensioni</span><span class="sxs-lookup"><span data-stu-id="cf407-240">Dimension-based configurations</span></span>

<span data-ttu-id="cf407-241">Durante un passaggio del processo di configurazione viene suggerito automaticamente un valore di configurazione in base alla nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="cf407-241">During one step of the configuration process, the system suggests a configuration value according to the nomenclature.</span></span> <span data-ttu-id="cf407-242">In questa fase è possibile modificare manualmente il valore di configurazione.</span><span class="sxs-lookup"><span data-stu-id="cf407-242">In this step, you can manually change the configuration value.</span></span> <span data-ttu-id="cf407-243">Quando si salva la configurazione, il sistema verifica che il valore di configurazione sia univoco.</span><span class="sxs-lookup"><span data-stu-id="cf407-243">When you save the configuration, the system verifies that the configuration value is unique.</span></span> <span data-ttu-id="cf407-244">Se il valore immesso non è univoco, verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="cf407-244">If the value that you entered isn't unique, you receive an error message.</span></span> <span data-ttu-id="cf407-245">Per salvare la configurazione è necessario immettere un valore univoco di configurazione.</span><span class="sxs-lookup"><span data-stu-id="cf407-245">To save the configuration, you must enter a unique configuration value.</span></span>

<a name="see-also"></a><span data-ttu-id="cf407-246">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf407-246">See also</span></span>
--------

[<span data-ttu-id="cf407-247">Creare una nomenclatura di numero prodotto per le varianti prodotto predefinite</span><span class="sxs-lookup"><span data-stu-id="cf407-247">Create a product number nomenclature for predefined product variants</span></span>](tasks/create-product-number-nomenclature-predefined-variants-2016-11.md)

[<span data-ttu-id="cf407-248">Creare una nomenclatura di numero prodotto per le varianti prodotto configurate</span><span class="sxs-lookup"><span data-stu-id="cf407-248">Create a product number nomenclature for configured product variants</span></span>](tasks/create-product-number-nomenclature-product-variants_2016_11.md)


