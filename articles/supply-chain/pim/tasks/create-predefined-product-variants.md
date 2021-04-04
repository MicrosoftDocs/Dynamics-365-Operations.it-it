---
title: Creare varianti prodotto predefinite
description: Questa procedura guida nella creazione di varianti prodotto per una rappresentazione generale prodotto mediante le combinazioni di dimensioni prodotto.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c33bbc7fa0ef7c3ce9768dd3688f9d1d575a513e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259868"
---
# <a name="create-predefined-product-variants"></a><span data-ttu-id="e772f-103">Creare varianti prodotto predefinite</span><span class="sxs-lookup"><span data-stu-id="e772f-103">Create predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e772f-104">Questa procedura guida nella creazione di varianti prodotto per una rappresentazione generale prodotto mediante le combinazioni di dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="e772f-104">This procedure walks through creating product variants for a product master using the combinations of product dimensions.</span></span> <span data-ttu-id="e772f-105">La società dimostrativa utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="e772f-105">The demo company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-master"></a><span data-ttu-id="e772f-106">Creare una rappresentazione generale prodotto</span><span class="sxs-lookup"><span data-stu-id="e772f-106">Create a product master</span></span>
1. <span data-ttu-id="e772f-107">Andare a Gestione informazioni sul prodotto > Prodotti > Rappresentazioni generali prodotto.</span><span class="sxs-lookup"><span data-stu-id="e772f-107">Go to Product information management > Products > Product masters.</span></span>
2. <span data-ttu-id="e772f-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e772f-108">Click New.</span></span>
3. <span data-ttu-id="e772f-109">Nel campo Numero prodotto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="e772f-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="e772f-110">Immettere un numero prodotto manualmente è obbligatorio solo se nessuna sequenza numerica è stata impostata per il campo relativo al numero di prodotto.</span><span class="sxs-lookup"><span data-stu-id="e772f-110">Entering a product number manually is only required if no number sequence has been set for the product number field.</span></span> <span data-ttu-id="e772f-111">In altre parole, ignorare il passaggio se la sequenza numerica è stata impostata per il campo.</span><span class="sxs-lookup"><span data-stu-id="e772f-111">In other words, skip the step if number sequence has been set for the field.</span></span>  
4. <span data-ttu-id="e772f-112">Digitare un valore nel campo Nome prodotto.</span><span class="sxs-lookup"><span data-stu-id="e772f-112">In the Product name field, type a value.</span></span>
5. <span data-ttu-id="e772f-113">Nel campo Gruppo di dimensioni prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e772f-113">In the Product dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="e772f-114">Selezionare il gruppo di dimensioni prodotto SizeCol (dimensione e colore).</span><span class="sxs-lookup"><span data-stu-id="e772f-114">Select the product dimension group SizeCol (Size and Color).</span></span>  
6. <span data-ttu-id="e772f-115">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e772f-115">Click OK.</span></span>

## <a name="add-product-dimensions"></a><span data-ttu-id="e772f-116">Aggiungere dimensioni prodotto</span><span class="sxs-lookup"><span data-stu-id="e772f-116">Add product dimensions</span></span>
1. <span data-ttu-id="e772f-117">Fare clic su Dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="e772f-117">Click Product dimensions.</span></span>
    * <span data-ttu-id="e772f-118">In questo esempio viene illustrato come immettere manualmente le dimensioni prodotto.</span><span class="sxs-lookup"><span data-stu-id="e772f-118">This example shows how to manually enter product dimensions.</span></span> <span data-ttu-id="e772f-119">È inoltre possibile scegliere di selezionare un gruppo di dimensioni, colore o stile che include i valori della dimensione prodotto si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="e772f-119">You can also choose to select a size, color or style group that includes the product dimension values you want to use.</span></span>  
2. <span data-ttu-id="e772f-120">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e772f-120">Click New.</span></span>
3. <span data-ttu-id="e772f-121">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e772f-121">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="e772f-122">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e772f-122">In the Size field, enter or select a value.</span></span>
5. <span data-ttu-id="e772f-123">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="e772f-123">In the Name field, type a value.</span></span>
6. <span data-ttu-id="e772f-124">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e772f-124">Click New.</span></span>
7. <span data-ttu-id="e772f-125">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e772f-125">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="e772f-126">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e772f-126">In the Size field, enter or select a value.</span></span>
9. <span data-ttu-id="e772f-127">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="e772f-127">In the Name field, type a value.</span></span>
10. <span data-ttu-id="e772f-128">Fare clic sulla scheda Colori.</span><span class="sxs-lookup"><span data-stu-id="e772f-128">Click the Colors tab.</span></span>
11. <span data-ttu-id="e772f-129">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e772f-129">Click New.</span></span>
12. <span data-ttu-id="e772f-130">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e772f-130">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="e772f-131">Nel campo Colore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e772f-131">In the Color field, enter or select a value.</span></span>
14. <span data-ttu-id="e772f-132">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="e772f-132">In the Name field, type a value.</span></span>
15. <span data-ttu-id="e772f-133">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e772f-133">Click New.</span></span>
16. <span data-ttu-id="e772f-134">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e772f-134">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="e772f-135">Nel campo Colore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e772f-135">In the Color field, enter or select a value.</span></span>
18. <span data-ttu-id="e772f-136">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="e772f-136">In the Name field, type a value.</span></span>
19. <span data-ttu-id="e772f-137">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="e772f-137">Click Save.</span></span>
20. <span data-ttu-id="e772f-138">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="e772f-138">Close the page.</span></span>

## <a name="generate-product-variants"></a><span data-ttu-id="e772f-139">Generare varianti prodotto</span><span class="sxs-lookup"><span data-stu-id="e772f-139">Generate product variants</span></span>
1. <span data-ttu-id="e772f-140">Fare clic su Varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="e772f-140">Click Product variants.</span></span>
2. <span data-ttu-id="e772f-141">Fare clic su Suggerimenti variante.</span><span class="sxs-lookup"><span data-stu-id="e772f-141">Click Variant suggestions.</span></span>
3. <span data-ttu-id="e772f-142">Fare clic su Seleziona tutto.</span><span class="sxs-lookup"><span data-stu-id="e772f-142">Click Select all.</span></span>
    * <span data-ttu-id="e772f-143">In questo esempio sono selezionate tutte le possibili varianti.</span><span class="sxs-lookup"><span data-stu-id="e772f-143">In this example, all possible variants are selected.</span></span> <span data-ttu-id="e772f-144">Se solo un sottoinsieme delle possibili combinazioni di dimensione prodotto verrà utilizzato per creare le varianti, è possibile selezionare le singole voci.</span><span class="sxs-lookup"><span data-stu-id="e772f-144">If only a subset of the possible product dimension combinations will be used to create variants, you can select the individual entries.</span></span>  
4. <span data-ttu-id="e772f-145">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="e772f-145">Click Create.</span></span>
    * <span data-ttu-id="e772f-146">È possibile generare le descrizioni per tutte le varianti in base alla combinazione di valori di dimensione prodotto.</span><span class="sxs-lookup"><span data-stu-id="e772f-146">You can generate descriptions for all your variants based on the combination of product dimension values.</span></span> <span data-ttu-id="e772f-147">La descrizioni sono facoltativa.</span><span class="sxs-lookup"><span data-stu-id="e772f-147">The descriptions are optional.</span></span>  
5. <span data-ttu-id="e772f-148">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="e772f-148">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]