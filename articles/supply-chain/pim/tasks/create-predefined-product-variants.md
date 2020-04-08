---
title: Creare varianti prodotto predefinite
description: Questa procedura guida nella creazione di varianti prodotto per una rappresentazione generale prodotto mediante le combinazioni di dimensioni prodotto.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 678e2d7207628529530dcf3decd094583d3dff22
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150117"
---
# <a name="create-predefined-product-variants"></a><span data-ttu-id="a3047-103">Creare varianti prodotto predefinite</span><span class="sxs-lookup"><span data-stu-id="a3047-103">Create predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a3047-104">Questa procedura guida nella creazione di varianti prodotto per una rappresentazione generale prodotto mediante le combinazioni di dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="a3047-104">This procedure walks through creating product variants for a product master using the combinations of product dimensions.</span></span> <span data-ttu-id="a3047-105">La società dimostrativa utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="a3047-105">The demo company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-master"></a><span data-ttu-id="a3047-106">Creare una rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="a3047-106">Create a product master</span></span>
1. <span data-ttu-id="a3047-107">Andare a Gestione informazioni sul prodotto > Prodotti > Rappresentazioni generali prodotto.</span><span class="sxs-lookup"><span data-stu-id="a3047-107">Go to Product information management > Products > Product masters.</span></span>
2. <span data-ttu-id="a3047-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a3047-108">Click New.</span></span>
3. <span data-ttu-id="a3047-109">Nel campo Numero prodotto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="a3047-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="a3047-110">Immettere un numero prodotto manualmente è obbligatorio solo se nessuna sequenza numerica è stata impostata per il campo relativo al numero di prodotto.</span><span class="sxs-lookup"><span data-stu-id="a3047-110">Entering a product number manually is only required if no number sequence has been set for the product number field.</span></span> <span data-ttu-id="a3047-111">In altre parole, ignorare il passaggio se la sequenza numerica è stata impostata per il campo.</span><span class="sxs-lookup"><span data-stu-id="a3047-111">In other words, skip the step if number sequence has been set for the field.</span></span>  
4. <span data-ttu-id="a3047-112">Digitare un valore nel campo Nome prodotto.</span><span class="sxs-lookup"><span data-stu-id="a3047-112">In the Product name field, type a value.</span></span>
5. <span data-ttu-id="a3047-113">Nel campo Gruppo di dimensioni prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a3047-113">In the Product dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="a3047-114">Selezionare il gruppo di dimensioni prodotto SizeCol (dimensione e colore).</span><span class="sxs-lookup"><span data-stu-id="a3047-114">Select the product dimension group SizeCol (Size and Color).</span></span>  
6. <span data-ttu-id="a3047-115">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a3047-115">Click OK.</span></span>

## <a name="add-product-dimensions"></a><span data-ttu-id="a3047-116">Aggiungere dimensioni prodotto</span><span class="sxs-lookup"><span data-stu-id="a3047-116">Add product dimensions</span></span>
1. <span data-ttu-id="a3047-117">Fare clic su Dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="a3047-117">Click Product dimensions.</span></span>
    * <span data-ttu-id="a3047-118">In questo esempio viene illustrato come immettere manualmente le dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="a3047-118">This example shows how to manually enter product dimensions.</span></span> <span data-ttu-id="a3047-119">È inoltre possibile scegliere di selezionare un gruppo di dimensioni, colore o stile che include i valori della dimensione prodotto si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="a3047-119">You can also choose to select a size, color or style group that includes the product dimension values you want to use.</span></span>  
2. <span data-ttu-id="a3047-120">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a3047-120">Click New.</span></span>
3. <span data-ttu-id="a3047-121">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a3047-121">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="a3047-122">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a3047-122">In the Size field, enter or select a value.</span></span>
5. <span data-ttu-id="a3047-123">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="a3047-123">In the Name field, type a value.</span></span>
6. <span data-ttu-id="a3047-124">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a3047-124">Click New.</span></span>
7. <span data-ttu-id="a3047-125">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a3047-125">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="a3047-126">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a3047-126">In the Size field, enter or select a value.</span></span>
9. <span data-ttu-id="a3047-127">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="a3047-127">In the Name field, type a value.</span></span>
10. <span data-ttu-id="a3047-128">Fare clic sulla scheda Colori.</span><span class="sxs-lookup"><span data-stu-id="a3047-128">Click the Colors tab.</span></span>
11. <span data-ttu-id="a3047-129">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a3047-129">Click New.</span></span>
12. <span data-ttu-id="a3047-130">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a3047-130">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="a3047-131">Nel campo Colore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a3047-131">In the Color field, enter or select a value.</span></span>
14. <span data-ttu-id="a3047-132">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="a3047-132">In the Name field, type a value.</span></span>
15. <span data-ttu-id="a3047-133">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="a3047-133">Click New.</span></span>
16. <span data-ttu-id="a3047-134">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="a3047-134">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="a3047-135">Nel campo Colore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a3047-135">In the Color field, enter or select a value.</span></span>
18. <span data-ttu-id="a3047-136">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="a3047-136">In the Name field, type a value.</span></span>
19. <span data-ttu-id="a3047-137">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a3047-137">Click Save.</span></span>
20. <span data-ttu-id="a3047-138">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a3047-138">Close the page.</span></span>

## <a name="generate-product-variants"></a><span data-ttu-id="a3047-139">Generare varianti prodotto</span><span class="sxs-lookup"><span data-stu-id="a3047-139">Generate product variants</span></span>
1. <span data-ttu-id="a3047-140">Fare clic su Varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="a3047-140">Click Product variants.</span></span>
2. <span data-ttu-id="a3047-141">Fare clic su Suggerimenti variante.</span><span class="sxs-lookup"><span data-stu-id="a3047-141">Click Variant suggestions.</span></span>
3. <span data-ttu-id="a3047-142">Fare clic su Seleziona tutto.</span><span class="sxs-lookup"><span data-stu-id="a3047-142">Click Select all.</span></span>
    * <span data-ttu-id="a3047-143">In questo esempio sono selezionate tutte le possibili varianti.</span><span class="sxs-lookup"><span data-stu-id="a3047-143">In this example, all possible variants are selected.</span></span> <span data-ttu-id="a3047-144">Se solo un sottoinsieme delle possibili combinazioni di dimensione prodotto verrà utilizzato per creare le varianti, è possibile selezionare le singole voci.</span><span class="sxs-lookup"><span data-stu-id="a3047-144">If only a subset of the possible product dimension combinations will be used to create variants, you can select the individual entries.</span></span>  
4. <span data-ttu-id="a3047-145">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="a3047-145">Click Create.</span></span>
    * <span data-ttu-id="a3047-146">È possibile generare le descrizioni per tutte le varianti in base alla combinazione di valori di dimensione prodotto.</span><span class="sxs-lookup"><span data-stu-id="a3047-146">You can generate descriptions for all your variants based on the combination of product dimension values.</span></span> <span data-ttu-id="a3047-147">La descrizioni sono facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a3047-147">The descriptions are optional.</span></span>  
5. <span data-ttu-id="a3047-148">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a3047-148">Click Save.</span></span>

