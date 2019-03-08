---
title: Nomenclatura di nomi e numeri di varianti prodotto
description: In questo argomento viene descritto come impostare la nomenclatura per il numero prodotto per sostituire il formato fisso [Numero rappresentazione generale prodotto - Configurazione - Dimensione - Colore - Stile].
author: roxanadiaconu
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: f84b6982af8b81ff83086d163a77e1c2f58ca478
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "336683"
---
# <a name="nomenclature-of-product-variant-numbers-and-names"></a><span data-ttu-id="606aa-103">Nomenclatura di nomi e numeri di varianti prodotto</span><span class="sxs-lookup"><span data-stu-id="606aa-103">Nomenclature of product variant numbers and names</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="606aa-104">In questo argomento viene descritto come impostare la nomenclatura per il numero prodotto per sostituire il formato fisso [Numero rappresentazione generale prodotto - Configurazione - Dimensione - Colore - Stile].</span><span class="sxs-lookup"><span data-stu-id="606aa-104">This topic describes how you can set up a product number nomenclature to replace the fixed [Product master number - Configuration - Size - Color - Style] format.</span></span> <span data-ttu-id="606aa-105">La nuova nomenclatura ha un formato di destinazione che include il numero della rappresentazione generale prodotto, le dimensioni prodotto attive e i delimitatori di testo scelti.</span><span class="sxs-lookup"><span data-stu-id="606aa-105">The new nomenclature has a targeted format that includes the product master number, active product dimensions, and text delimiters of your choice.</span></span> <span data-ttu-id="606aa-106">È inoltre possibile creare una nomenclatura per i nomi di prodotto.</span><span class="sxs-lookup"><span data-stu-id="606aa-106">You can also create a nomenclature for product names.</span></span> <span data-ttu-id="606aa-107">Infine, è anche possibile creare una nomenclatura per identificare le configurazioni create in base alla configurazione basata su vincoli del prodotto.</span><span class="sxs-lookup"><span data-stu-id="606aa-107">Finally, you can build a nomenclature to identify configurations that are created by the constraint-based product configurator.</span></span> <span data-ttu-id="606aa-108">Queste nomenclature possono includere gli attributi scelti.</span><span class="sxs-lookup"><span data-stu-id="606aa-108">These nomenclatures can contain attributes of your choice.</span></span>

<span data-ttu-id="606aa-109">Le nuove nomenclature per i numeri di varianti prodotto e i nomi di varianti prodotto consentono di includere segmenti negli identificatori per le varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="606aa-109">The new nomenclatures for product variant numbers and product variant names let you include segments in the identifiers for product variants.</span></span> <span data-ttu-id="606aa-110">I segmenti possono includere il nome e il numero della rappresentazione generale prodotto, i nomi e gli ID delle dimensioni prodotto, le sequenze numeriche, le costanti di testo e gli attributi.</span><span class="sxs-lookup"><span data-stu-id="606aa-110">These segments can include the product master number and name, product dimension IDs and names, number sequences, text constants, and attributes.</span></span> <span data-ttu-id="606aa-111">Questa funzionalità consente di trovare velocemente una variante prodotto specifica quando si crea un ordine cliente o un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="606aa-111">This functionality lets you quickly find a specific product variant when you create a sales order or a purchase order.</span></span> <span data-ttu-id="606aa-112">È possibile creare nomenclature per i numeri di varianti prodotto e i nomi di varianti prodotto utilizzando la pagina **Nomenclatura di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="606aa-112">You create nomenclatures for both product variant numbers and product variant names by using the **Product nomenclature** page.</span></span> <span data-ttu-id="606aa-113">Per aprire questa pagina, fare clic su **Gestione informazioni sul prodotto** &gt; **Impostazione**.</span><span class="sxs-lookup"><span data-stu-id="606aa-113">To open this page, click **Product information management** &gt; **Setup**.</span></span>

## <a name="nomenclature-of-predefined-product-variants"></a><span data-ttu-id="606aa-114">Nomenclatura di varianti prodotto predefinite</span><span class="sxs-lookup"><span data-stu-id="606aa-114">Nomenclature of predefined product variants</span></span>
<span data-ttu-id="606aa-115">Le varianti prodotto vengono generate per le rappresentazioni generali prodotto in base a una delle tre tecnologie di configurazione:</span><span class="sxs-lookup"><span data-stu-id="606aa-115">Product variants are generated for product masters according to one of three configuration technologies:</span></span>

-   <span data-ttu-id="606aa-116">Varianti predefinite</span><span class="sxs-lookup"><span data-stu-id="606aa-116">Predefined variants</span></span>
-   <span data-ttu-id="606aa-117">Basata su vincoli</span><span class="sxs-lookup"><span data-stu-id="606aa-117">Constraint-based</span></span>
-   <span data-ttu-id="606aa-118">Basata su dimensioni</span><span class="sxs-lookup"><span data-stu-id="606aa-118">Dimension-based</span></span>

<span data-ttu-id="606aa-119">A ogni variante prodotto è associato un numero e un nome e le nomenclature dell'identificazione variante prodotto consente di selezionare i segmenti che verranno inclusi in ciascun numero di variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="606aa-119">Each product variant has a number and a name, and the product variant identification nomenclatures let you select the segments that will be included in each product variant number or name.</span></span> <span data-ttu-id="606aa-120">È possibile selezionare i segmenti che seguono nella pagina **Nomenclatura di prodotto**:</span><span class="sxs-lookup"><span data-stu-id="606aa-120">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="606aa-121">Numero rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="606aa-121">Product master number</span></span>
-   <span data-ttu-id="606aa-122">Nome rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="606aa-122">Product master name</span></span>
-   <span data-ttu-id="606aa-123">Valore sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="606aa-123">Number sequence value</span></span>
-   <span data-ttu-id="606aa-124">Costante testo</span><span class="sxs-lookup"><span data-stu-id="606aa-124">Text constant</span></span>
-   <span data-ttu-id="606aa-125">Dimensioni prodotto</span><span class="sxs-lookup"><span data-stu-id="606aa-125">Product dimensions</span></span>
    -   <span data-ttu-id="606aa-126">Nome o ID configurazione</span><span class="sxs-lookup"><span data-stu-id="606aa-126">Configuration ID or name</span></span>
    -   <span data-ttu-id="606aa-127">Nome o ID colore</span><span class="sxs-lookup"><span data-stu-id="606aa-127">Color ID or name</span></span>
    -   <span data-ttu-id="606aa-128">Nome o ID dimensione</span><span class="sxs-lookup"><span data-stu-id="606aa-128">Size ID or name</span></span>
    -   <span data-ttu-id="606aa-129">Nome o ID stile</span><span class="sxs-lookup"><span data-stu-id="606aa-129">Style ID or name</span></span>

<span data-ttu-id="606aa-130">Una volta definita, la nomenclatura numero di identificazione variante prodotto può essere associata a un gruppo di dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="606aa-130">After you define a product variant identification number nomenclature, you can associate it with a product dimension group.</span></span> <span data-ttu-id="606aa-131">A tutte le rappresentazioni generali prodotto che fanno riferimento al gruppo di dimensioni prodotto verranno assegnati i numeri di varianti prodotto in base alla nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="606aa-131">All product masters that reference this product dimension group will then be assigned product variant numbers according to the nomenclature.</span></span> <span data-ttu-id="606aa-132">Tuttavia, le nomenclature nome di variante prodotto non possono essere associate ai gruppi di dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="606aa-132">However, product variant name nomenclatures can't be associated with product dimension groups.</span></span> <span data-ttu-id="606aa-133">È inoltre possibile assegnare una nomenclatura identificazione variante prodotto direttamente a una rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="606aa-133">You can also assign a product variant identification nomenclature directly to a product master.</span></span> <span data-ttu-id="606aa-134">In questo caso, alle varianti prodotto che appartengono alla rappresentazione generale prodotto verranno assegnati i numeri e i nomi di variante prodotto in base alle nomenclature.</span><span class="sxs-lookup"><span data-stu-id="606aa-134">In this case, the product variants that belong to the product master will be assigned product variant numbers and names according to the nomenclatures.</span></span>

### <a name="example"></a><span data-ttu-id="606aa-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="606aa-135">Example</span></span>

<span data-ttu-id="606aa-136">Una maglietta (TS1234) viene prodotta in tre dimensioni (S, M, L), quattro colori (rosso, verde, blu, giallo) e due stili (polo, a V).</span><span class="sxs-lookup"><span data-stu-id="606aa-136">A T-shirt (TS1234) is produced in three sizes (S, M, L), four colors (Red, Green, Blue, Yellow), and two styles (Polo, V).</span></span> <span data-ttu-id="606aa-137">Di conseguenza, 24 varianti prodotto sono possibili = (3 × 4 × 2).</span><span class="sxs-lookup"><span data-stu-id="606aa-137">Therefore, 24 product variants are possible (= 3 × 4 × 2).</span></span> <span data-ttu-id="606aa-138">Creare una nomenclatura numero di varianti prodotto contenente i segmenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="606aa-138">You create a product variant number nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="606aa-139">Numero rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="606aa-139">Product master number</span></span>
2.  <span data-ttu-id="606aa-140">Costante testo: "-"</span><span class="sxs-lookup"><span data-stu-id="606aa-140">Text constant: "-"</span></span>
3.  <span data-ttu-id="606aa-141">Colore</span><span class="sxs-lookup"><span data-stu-id="606aa-141">Color</span></span>
4.  <span data-ttu-id="606aa-142">Costante testo: "-"</span><span class="sxs-lookup"><span data-stu-id="606aa-142">Text constant: "-"</span></span>
5.  <span data-ttu-id="606aa-143">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="606aa-143">Size</span></span>
6.  <span data-ttu-id="606aa-144">Costante testo: "-"</span><span class="sxs-lookup"><span data-stu-id="606aa-144">Text constant: "-"</span></span>
7.  <span data-ttu-id="606aa-145">Stile</span><span class="sxs-lookup"><span data-stu-id="606aa-145">Style</span></span>

<span data-ttu-id="606aa-146">In questo caso, il numero di variante prodotto per la polo piccola e rossa sarà TS1234-Red-Small-Polo.</span><span class="sxs-lookup"><span data-stu-id="606aa-146">In this case, the product variant number for a red, small, polo T-shirt will be TS1234-Red-Small-Polo.</span></span>

## <a name="nomenclature-of-constraint-based-configurations"></a><span data-ttu-id="606aa-147">Nomenclatura delle configurazioni basate su vincoli</span><span class="sxs-lookup"><span data-stu-id="606aa-147">Nomenclature of constraint-based configurations</span></span>
<span data-ttu-id="606aa-148">Per le configurazioni basate su vincoli, è possibile creare una nomenclatura dedicata per la dimensione prodotto della configurazione.</span><span class="sxs-lookup"><span data-stu-id="606aa-148">For constraint-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="606aa-149">È possibile selezionare i segmenti che seguono nella pagina **Nomenclatura di prodotto**:</span><span class="sxs-lookup"><span data-stu-id="606aa-149">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="606aa-150">Valore sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="606aa-150">Number sequence value</span></span>
-   <span data-ttu-id="606aa-151">Costante testo</span><span class="sxs-lookup"><span data-stu-id="606aa-151">Text constant</span></span>
-   <span data-ttu-id="606aa-152">Valore attributo</span><span class="sxs-lookup"><span data-stu-id="606aa-152">Attribute value</span></span>

<span data-ttu-id="606aa-153">Ciascun componente in un modello di configurazione prodotto può avere la propria nomenclatura di configurazione.</span><span class="sxs-lookup"><span data-stu-id="606aa-153">Each component in a product configuration model can have its own configuration nomenclature.</span></span> <span data-ttu-id="606aa-154">Solo gli attributi che appartengono al componente possono essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="606aa-154">Only attributes that belong to the component can be used.</span></span> <span data-ttu-id="606aa-155">Gli attributi di componenti secondari o dei requisiti dell'utente non possono essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="606aa-155">Attributes from subcomponents or user requirements can't be used.</span></span>

### <a name="example"></a><span data-ttu-id="606aa-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="606aa-156">Example</span></span>

<span data-ttu-id="606aa-157">Un modello di configurazione prodotto ha un componente principale con due attributi:</span><span class="sxs-lookup"><span data-stu-id="606aa-157">A product configuration model has a root component that has two attributes:</span></span>

-   <span data-ttu-id="606aa-158">Materiale (plastica, legno, acciaio)</span><span class="sxs-lookup"><span data-stu-id="606aa-158">Material (Plastic, Wood, Steel)</span></span>
-   <span data-ttu-id="606aa-159">Lunghezza (10...100)</span><span class="sxs-lookup"><span data-stu-id="606aa-159">Length (10...100)</span></span>

<span data-ttu-id="606aa-160">Creare una nomenclatura configurazione contenente i segmenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="606aa-160">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="606aa-161">Valore attributo: materiale</span><span class="sxs-lookup"><span data-stu-id="606aa-161">Attribute value: Material</span></span>
2.  <span data-ttu-id="606aa-162">Costante testo: "AAA"</span><span class="sxs-lookup"><span data-stu-id="606aa-162">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="606aa-163">Valore attributo: lunghezza</span><span class="sxs-lookup"><span data-stu-id="606aa-163">Attribute value: Length</span></span>

<span data-ttu-id="606aa-164">In questo caso, l'ID configurazione per il materiale legno con una lunghezza di 78 sarà WoodAAA78.</span><span class="sxs-lookup"><span data-stu-id="606aa-164">In this case, the configuration ID for wood material that has a length of 78 will be WoodAAA78.</span></span>

## <a name="nomenclature-of-dimension-based-configurations"></a><span data-ttu-id="606aa-165">Nomenclatura di configurazioni basate su dimensioni</span><span class="sxs-lookup"><span data-stu-id="606aa-165">Nomenclature of dimension-based configurations</span></span>
<span data-ttu-id="606aa-166">Per le configurazioni basate su dimensioni, è possibile creare una nomenclatura dedicata per la dimensione prodotto della configurazione.</span><span class="sxs-lookup"><span data-stu-id="606aa-166">For dimension-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="606aa-167">È possibile selezionare i segmenti che seguono nella pagina **Nomenclatura di prodotto**:</span><span class="sxs-lookup"><span data-stu-id="606aa-167">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="606aa-168">Valore sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="606aa-168">Number sequence value</span></span>
-   <span data-ttu-id="606aa-169">Costante testo</span><span class="sxs-lookup"><span data-stu-id="606aa-169">Text constant</span></span>
-   <span data-ttu-id="606aa-170">Articolo gruppo di configurazioni</span><span class="sxs-lookup"><span data-stu-id="606aa-170">Configuration group item</span></span>

<span data-ttu-id="606aa-171">È possibile definire una nomenclatura di configurazione per una distinta base (DBA).</span><span class="sxs-lookup"><span data-stu-id="606aa-171">You can define a configuration nomenclature for a bill of materials (BOM).</span></span>

### <a name="example"></a><span data-ttu-id="606aa-172">Esempio</span><span class="sxs-lookup"><span data-stu-id="606aa-172">Example</span></span>

<span data-ttu-id="606aa-173">La DBA è composta da quattro righe DBA divise in due gruppi di configurazioni:</span><span class="sxs-lookup"><span data-stu-id="606aa-173">A BOM has four BOM lines that are divided into two configuration groups:</span></span>

-   <span data-ttu-id="606aa-174">Riga DBA: M0007, cabinet predefinito</span><span class="sxs-lookup"><span data-stu-id="606aa-174">BOM line: M0007, Standard cabinet</span></span>
    -   <span data-ttu-id="606aa-175">Gruppo di configurazioni: cabinet</span><span class="sxs-lookup"><span data-stu-id="606aa-175">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="606aa-176">Riga DBA: M0008, cabinet di fascia alta</span><span class="sxs-lookup"><span data-stu-id="606aa-176">BOM line: M0008, High end cabinet</span></span>
    -   <span data-ttu-id="606aa-177">Gruppo di configurazioni: cabinet</span><span class="sxs-lookup"><span data-stu-id="606aa-177">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="606aa-178">Riga DBA: M0021, panno della griglia anteriore</span><span class="sxs-lookup"><span data-stu-id="606aa-178">BOM line: M0021, Front grill cloth</span></span>
    -   <span data-ttu-id="606aa-179">Gruppo di configurazioni: griglia anteriore</span><span class="sxs-lookup"><span data-stu-id="606aa-179">Configuration group: Front grill</span></span>
-   <span data-ttu-id="606aa-180">Riga DBA: M0022, metallo della griglia anteriore</span><span class="sxs-lookup"><span data-stu-id="606aa-180">BOM line: M0022, Front grill metal</span></span>
    -   <span data-ttu-id="606aa-181">Gruppo di configurazioni: griglia anteriore</span><span class="sxs-lookup"><span data-stu-id="606aa-181">Configuration group: Front grill</span></span>

<span data-ttu-id="606aa-182">Creare una nomenclatura configurazione contenente i segmenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="606aa-182">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="606aa-183">Gruppo di configurazioni: cabinet</span><span class="sxs-lookup"><span data-stu-id="606aa-183">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="606aa-184">Costante testo: "&"</span><span class="sxs-lookup"><span data-stu-id="606aa-184">Text constant: "&"</span></span>
3.  <span data-ttu-id="606aa-185">Gruppo di configurazioni: griglia anteriore</span><span class="sxs-lookup"><span data-stu-id="606aa-185">Configuration group: Front grill</span></span>

<span data-ttu-id="606aa-186">In questo caso, l'ID di configurazione per un cabinet standard con panno della griglia anteriore sarà M0007&M0021.</span><span class="sxs-lookup"><span data-stu-id="606aa-186">In this case, the configuration ID for a standard cabinet that has a cloth front grill will be M0007&M0021.</span></span>

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a><span data-ttu-id="606aa-187">Nomenclatura per una combinazione di varianti prodotto e configurazioni</span><span class="sxs-lookup"><span data-stu-id="606aa-187">Nomenclature for a combination of product variants and configurations</span></span>
<span data-ttu-id="606aa-188">Quando si utilizza la tecnologia di configurazione basata su vincoli o su dimensioni per configurare le varianti prodotto per una rappresentazione generale prodotto, i numeri delle varianti prodotto possono includere la nomenclatura dalla dimensione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="606aa-188">When you use either the constraint-based configuration technology or the dimension-based configuration technology to configure product variants for a product master, the product variant numbers of the product variants can include the nomenclature from the configuration dimension.</span></span> <span data-ttu-id="606aa-189">Attenersi a questa procedura per configurare le varianti.</span><span class="sxs-lookup"><span data-stu-id="606aa-189">Follow these steps to configure variants.</span></span>

1.  <span data-ttu-id="606aa-190">Definire una nomenclatura del numero di varianti prodotto che includa la dimensione di configurazione nella pagina **Nomenclatura di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="606aa-190">On the **Product nomenclature** page, define a product variant number nomenclature that includes the configuration dimension.</span></span>
2.  <span data-ttu-id="606aa-191">Assegnare questa nomenclatura a un gruppo di dimensioni prodotto con la dimensione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="606aa-191">Assign the nomenclature to a product dimension group that has the configuration dimension.</span></span>
3.  <span data-ttu-id="606aa-192">Definire una nomenclatura di configurazione per i componenti o le DBA che verranno utilizzate per la configurazione di varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="606aa-192">Define a configuration nomenclature for the components or BOMs that will be used to configure the product variants.</span></span>

<span data-ttu-id="606aa-193">È inoltre possibile creare le nomenclature per i nomi di varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="606aa-193">You can also create nomenclatures for the product variant names.</span></span> <span data-ttu-id="606aa-194">I nomi di varianti prodotto possono essere configurati per includere il nome o l'ID configurazione.</span><span class="sxs-lookup"><span data-stu-id="606aa-194">The product variant names can be configured to include the configuration ID or name.</span></span>

### <a name="example-for-constraint-based-configurations"></a><span data-ttu-id="606aa-195">Esempio per le configurazioni basate su vincoli</span><span class="sxs-lookup"><span data-stu-id="606aa-195">Example for constraint-based configurations</span></span>

<span data-ttu-id="606aa-196">In questo esempio è possibile utilizzare una nomenclatura del numero di varianti prodotto costituita dai seguenti segmenti:</span><span class="sxs-lookup"><span data-stu-id="606aa-196">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="606aa-197">Numero rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="606aa-197">Product master number</span></span>
2.  <span data-ttu-id="606aa-198">Costante testo "\_"</span><span class="sxs-lookup"><span data-stu-id="606aa-198">Text constant "\_"</span></span>
3.  <span data-ttu-id="606aa-199">Configurazione</span><span class="sxs-lookup"><span data-stu-id="606aa-199">Configuration</span></span>

<span data-ttu-id="606aa-200">La nomenclatura di configurazione consiste nei seguenti segmenti:</span><span class="sxs-lookup"><span data-stu-id="606aa-200">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="606aa-201">Valore attributo: materiale</span><span class="sxs-lookup"><span data-stu-id="606aa-201">Attribute value: Material</span></span>
2.  <span data-ttu-id="606aa-202">Costante testo: "AAA"</span><span class="sxs-lookup"><span data-stu-id="606aa-202">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="606aa-203">Valore attributo: lunghezza</span><span class="sxs-lookup"><span data-stu-id="606aa-203">Attribute value: Length</span></span>

<span data-ttu-id="606aa-204">Immettere i seguenti valori per segmenti:</span><span class="sxs-lookup"><span data-stu-id="606aa-204">You enter the following values for segments:</span></span>

-   <span data-ttu-id="606aa-205">Numero rappresentazione generale prodotto = **M0099**</span><span class="sxs-lookup"><span data-stu-id="606aa-205">Product master number = **M0099**</span></span>
-   <span data-ttu-id="606aa-206">Materiale = **Plastic**</span><span class="sxs-lookup"><span data-stu-id="606aa-206">Material = **Plastic**</span></span>
-   <span data-ttu-id="606aa-207">Lunghezza = **12**</span><span class="sxs-lookup"><span data-stu-id="606aa-207">Length = **12**</span></span>

<span data-ttu-id="606aa-208">In questo caso, il numero di varianti prodotto diventerà M0099\_PlasticAAA12.</span><span class="sxs-lookup"><span data-stu-id="606aa-208">In this case, the product variant number will be M0099\_PlasticAAA12.</span></span>

### <a name="example-for-dimension-based-configurations"></a><span data-ttu-id="606aa-209">Esempio per le configurazioni basate su dimensioni</span><span class="sxs-lookup"><span data-stu-id="606aa-209">Example for dimension-based configurations</span></span>

<span data-ttu-id="606aa-210">In questo esempio è possibile utilizzare una nomenclatura del numero di varianti prodotto costituita dai seguenti segmenti:</span><span class="sxs-lookup"><span data-stu-id="606aa-210">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="606aa-211">Numero rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="606aa-211">Product master number</span></span>
2.  <span data-ttu-id="606aa-212">Costante testo "//"</span><span class="sxs-lookup"><span data-stu-id="606aa-212">Text constant "//"</span></span>
3.  <span data-ttu-id="606aa-213">Configurazione</span><span class="sxs-lookup"><span data-stu-id="606aa-213">Configuration</span></span>

<span data-ttu-id="606aa-214">La nomenclatura di configurazione consiste nei seguenti segmenti:</span><span class="sxs-lookup"><span data-stu-id="606aa-214">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="606aa-215">Gruppo di configurazioni: cabinet</span><span class="sxs-lookup"><span data-stu-id="606aa-215">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="606aa-216">Costante testo: "&"</span><span class="sxs-lookup"><span data-stu-id="606aa-216">Text constant: "&"</span></span>
3.  <span data-ttu-id="606aa-217">Gruppo di configurazioni: griglia anteriore</span><span class="sxs-lookup"><span data-stu-id="606aa-217">Configuration group: Front grill</span></span>

<span data-ttu-id="606aa-218">Immettere i seguenti valori per segmenti:</span><span class="sxs-lookup"><span data-stu-id="606aa-218">You enter the following values for segments:</span></span>

-   <span data-ttu-id="606aa-219">Numero rappresentazione generale prodotto = **D0123**</span><span class="sxs-lookup"><span data-stu-id="606aa-219">Product master number = **D0123**</span></span>
-   <span data-ttu-id="606aa-220">Cabinet = **M0008**</span><span class="sxs-lookup"><span data-stu-id="606aa-220">Cabinet = **M0008**</span></span>
-   <span data-ttu-id="606aa-221">Griglia anteriore = **M0022**</span><span class="sxs-lookup"><span data-stu-id="606aa-221">Front grill = **M0022**</span></span>

<span data-ttu-id="606aa-222">In questo caso, il numero di varianti prodotto diventerà D0123//M0008&M0022.</span><span class="sxs-lookup"><span data-stu-id="606aa-222">In this case, the product variant number will be D0123//M0008&M0022.</span></span>

## <a name="numbering-conflicts"></a><span data-ttu-id="606aa-223">Conflitti di numerazione</span><span class="sxs-lookup"><span data-stu-id="606aa-223">Numbering conflicts</span></span>
<span data-ttu-id="606aa-224">In alcuni casi, è possibile impostare una nomenclatura del numero di varianti prodotto che non generi numeri univoci di varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="606aa-224">In some cases, a product variant number nomenclature that you set up might not produce unique product variant numbers.</span></span> <span data-ttu-id="606aa-225">Ad esempio, i numeri di varianti prodotto non sarebbero univoci se una dimensione prodotto attiva non è inclusa nella nomenclatura per una rappresentazione generale prodotto che utilizzi la tecnologia di configurazione varianti predefinita.</span><span class="sxs-lookup"><span data-stu-id="606aa-225">For example, the product variant numbers won't be unique if one active product dimension isn't included in the nomenclature for a product master that uses the predefined variant configuration technology.</span></span> <span data-ttu-id="606aa-226">Il modo in cui si gestiscono i conflitti varia in base alla tecnologia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="606aa-226">The way that you handle conflicts varies, depending on the configuration technology.</span></span>

### <a name="predefined-variants"></a><span data-ttu-id="606aa-227">Varianti predefinite</span><span class="sxs-lookup"><span data-stu-id="606aa-227">Predefined variants</span></span>

<span data-ttu-id="606aa-228">Si verifica un errore se si tenta di creare manualmente o generare automaticamente varianti prodotto in cui più varianti prodotto finiscono con lo stesso numero.</span><span class="sxs-lookup"><span data-stu-id="606aa-228">An error occurs if you try to manually create or automatically generate product variants, and more than one product variant ends up with the same product variant number.</span></span> <span data-ttu-id="606aa-229">Per evitare questo scenario, è necessario utilizzare tutte le dimensioni prodotto attive nel gruppo di dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="606aa-229">To avoid this scenario, you should use all active product dimensions in the product dimension group.</span></span> <span data-ttu-id="606aa-230">In alternativa, includere una sequenza numerica per garantire che i numeri di varianti prodotto siano univoci.</span><span class="sxs-lookup"><span data-stu-id="606aa-230">Alternatively, include a number sequence to help guarantee that the product variant numbers are unique.</span></span>

### <a name="constraint-based-configurations"></a><span data-ttu-id="606aa-231">Configurazioni basata su vincoli</span><span class="sxs-lookup"><span data-stu-id="606aa-231">Constraint-based configurations</span></span>

<span data-ttu-id="606aa-232">A seconda della nomenclatura, il sistema può tentare di assegnare un numero di variante prodotto non univoco a una configurazione.</span><span class="sxs-lookup"><span data-stu-id="606aa-232">Depending on the nomenclature, the system might try to assign a non-unique product variant number to a configuration.</span></span> <span data-ttu-id="606aa-233">In questo caso viene utilizzata la sequenza numerica per la dimensione di configurazione come numero di variante prodotto e viene visualizzato un avviso.</span><span class="sxs-lookup"><span data-stu-id="606aa-233">In this case, the system uses the number sequence for the configuration dimension as the product variant number instead, and you receive a warning.</span></span> <span data-ttu-id="606aa-234">Per evitare questo scenario, includere sufficienti attributi nella nomenclature per garantire che i numeri di varianti prodotto siano univoci.</span><span class="sxs-lookup"><span data-stu-id="606aa-234">To avoid this scenario, you should include enough attributes in the nomenclature to help guarantee unique product variant numbers.</span></span> <span data-ttu-id="606aa-235">È inoltre necessario assicurarsi che l'opzione **Riutilizza** sia attivata per il componente.</span><span class="sxs-lookup"><span data-stu-id="606aa-235">You should also make sure that the **Reuse** option is turned on for the component.</span></span>

### <a name="dimension-based-configurations"></a><span data-ttu-id="606aa-236">Configurazioni basate su dimensioni</span><span class="sxs-lookup"><span data-stu-id="606aa-236">Dimension-based configurations</span></span>

<span data-ttu-id="606aa-237">Durante un passaggio del processo di configurazione viene suggerito automaticamente un valore di configurazione in base alla nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="606aa-237">During one step of the configuration process, the system suggests a configuration value according to the nomenclature.</span></span> <span data-ttu-id="606aa-238">In questa fase è possibile modificare manualmente il valore di configurazione.</span><span class="sxs-lookup"><span data-stu-id="606aa-238">In this step, you can manually change the configuration value.</span></span> <span data-ttu-id="606aa-239">Quando si salva la configurazione, il sistema verifica che il valore di configurazione sia univoco.</span><span class="sxs-lookup"><span data-stu-id="606aa-239">When you save the configuration, the system verifies that the configuration value is unique.</span></span> <span data-ttu-id="606aa-240">Se il valore immesso non è univoco, verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="606aa-240">If the value that you entered isn't unique, you receive an error message.</span></span> <span data-ttu-id="606aa-241">Per salvare la configurazione è necessario immettere un valore univoco di configurazione.</span><span class="sxs-lookup"><span data-stu-id="606aa-241">To save the configuration, you must enter a unique configuration value.</span></span>

<a name="additional-resources"></a><span data-ttu-id="606aa-242">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="606aa-242">Additional resources</span></span>
--------

[<span data-ttu-id="606aa-243">Creare una nomenclatura del numero di prodotto per le varianti prodotto predefinite</span><span class="sxs-lookup"><span data-stu-id="606aa-243">Create a product number nomenclature for predefined product variants</span></span>](tasks/create-product-number-nomenclature-predefined-variants-2016-11.md)

[<span data-ttu-id="606aa-244">Creare una nomenclatura di numero prodotto per le varianti prodotto configurate</span><span class="sxs-lookup"><span data-stu-id="606aa-244">Create a product number nomenclature for configured product variants</span></span>](tasks/create-product-number-nomenclature-product-variants_2016_11.md)

