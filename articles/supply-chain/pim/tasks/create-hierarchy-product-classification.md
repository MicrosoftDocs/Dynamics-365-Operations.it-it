--- 
title: Creare una gerarchia di classificazione del prodotto
description: Questa procedura mostra come creare una nuova gerarchia di categorie e assegnare un tipo di gerarchia di codici di voce doganale.
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyCreate, EcoResCategory, EcoResCategoryHierarchyRole
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: ee65e4ff990c14942432af48a6a7d451460c7b15
ms.contentlocale: it-it
ms.lasthandoff: 09/11/2018

---
# <a name="create-a-hierarchy-of-product-classification"></a><span data-ttu-id="53f4b-103">Creare una gerarchia di classificazione del prodotto</span><span class="sxs-lookup"><span data-stu-id="53f4b-103">Create a hierarchy of product classification</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="53f4b-104">Questa procedura mostra come creare una nuova gerarchia di categorie e assegnare un tipo di gerarchia di codici di voce doganale.</span><span class="sxs-lookup"><span data-stu-id="53f4b-104">This procedure shows how to create a new category hierarchy and assign a commodity code hierarchy type.</span></span> <span data-ttu-id="53f4b-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="53f4b-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="53f4b-106">Questa procedura è destinata al responsabile della categoria.</span><span class="sxs-lookup"><span data-stu-id="53f4b-106">This procedure is intended for the category manager.</span></span>


## <a name="create-the-new-category-hierarchy"></a><span data-ttu-id="53f4b-107">Creare la nuova gerarchia di categorie</span><span class="sxs-lookup"><span data-stu-id="53f4b-107">Create the new category hierarchy</span></span>
1. <span data-ttu-id="53f4b-108">Scegliere Gestione informazioni sul prodotto > Impostazioni > Categorie e attributi > Gerarchie di categorie.</span><span class="sxs-lookup"><span data-stu-id="53f4b-108">Go to Product information management > Setup > Categories and attributes > Category hierarchies.</span></span>
2. <span data-ttu-id="53f4b-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="53f4b-109">Click New.</span></span>
3. <span data-ttu-id="53f4b-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="53f4b-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="53f4b-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="53f4b-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="53f4b-112">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="53f4b-112">Click Create.</span></span>

## <a name="build-the-hierarchy"></a><span data-ttu-id="53f4b-113">Sviluppare la gerarchia</span><span class="sxs-lookup"><span data-stu-id="53f4b-113">Build the hierarchy</span></span>
1. <span data-ttu-id="53f4b-114">Fare clic su nodo Nuova categoria.</span><span class="sxs-lookup"><span data-stu-id="53f4b-114">Click New category node.</span></span>
2. <span data-ttu-id="53f4b-115">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="53f4b-115">In the Name field, type a value.</span></span>
3. <span data-ttu-id="53f4b-116">Digitare un valore nel campo Codice.</span><span class="sxs-lookup"><span data-stu-id="53f4b-116">In the Code field, type a value.</span></span>
4. <span data-ttu-id="53f4b-117">Digitare un valore nel campo Nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="53f4b-117">In the Friendly name field, type a value.</span></span>
5. <span data-ttu-id="53f4b-118">Fare clic su nodo Nuova categoria.</span><span class="sxs-lookup"><span data-stu-id="53f4b-118">Click New category node.</span></span>
6. <span data-ttu-id="53f4b-119">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="53f4b-119">In the Name field, type a value.</span></span>
7. <span data-ttu-id="53f4b-120">Digitare un valore nel campo Codice.</span><span class="sxs-lookup"><span data-stu-id="53f4b-120">In the Code field, type a value.</span></span>
8. <span data-ttu-id="53f4b-121">Digitare un valore nel campo Nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="53f4b-121">In the Friendly name field, type a value.</span></span>
9. <span data-ttu-id="53f4b-122">Fare clic su nodo Nuova categoria.</span><span class="sxs-lookup"><span data-stu-id="53f4b-122">Click New category node.</span></span>
10. <span data-ttu-id="53f4b-123">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="53f4b-123">In the Name field, type a value.</span></span>
11. <span data-ttu-id="53f4b-124">Digitare un valore nel campo Codice.</span><span class="sxs-lookup"><span data-stu-id="53f4b-124">In the Code field, type a value.</span></span>
12. <span data-ttu-id="53f4b-125">Digitare un valore nel campo Nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="53f4b-125">In the Friendly name field, type a value.</span></span>
13. <span data-ttu-id="53f4b-126">Fare clic su nodo Nuova categoria.</span><span class="sxs-lookup"><span data-stu-id="53f4b-126">Click New category node.</span></span>
14. <span data-ttu-id="53f4b-127">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="53f4b-127">In the Name field, type a value.</span></span>
15. <span data-ttu-id="53f4b-128">Digitare un valore nel campo Codice.</span><span class="sxs-lookup"><span data-stu-id="53f4b-128">In the Code field, type a value.</span></span>
16. <span data-ttu-id="53f4b-129">Digitare un valore nel campo Nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="53f4b-129">In the Friendly name field, type a value.</span></span>
17. <span data-ttu-id="53f4b-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="53f4b-130">Close the page.</span></span>

## <a name="classify-the-hierarchy"></a><span data-ttu-id="53f4b-131">Classificare la gerarchia</span><span class="sxs-lookup"><span data-stu-id="53f4b-131">Classify the hierarchy</span></span>
1. <span data-ttu-id="53f4b-132">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="53f4b-132">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="53f4b-133">Nel riquadro Azioni fare clic su Gerarchia di categorie.</span><span class="sxs-lookup"><span data-stu-id="53f4b-133">On the Action Pane, click Category hierarchy.</span></span>
3. <span data-ttu-id="53f4b-134">Fare clic su Associa tipo gerarchia.</span><span class="sxs-lookup"><span data-stu-id="53f4b-134">Click Associate hierarchy type.</span></span>
4. <span data-ttu-id="53f4b-135">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="53f4b-135">Click New.</span></span>
5. <span data-ttu-id="53f4b-136">Selezionare un'opzione nel campo Tipo di gerarchia di categorie.</span><span class="sxs-lookup"><span data-stu-id="53f4b-136">In the Category hierarchy type field, select an option.</span></span>
    * <span data-ttu-id="53f4b-137">Selezionare il tipo Gerarchia di codici di voce doganale per la classificazione di prodotto.</span><span class="sxs-lookup"><span data-stu-id="53f4b-137">Select the Commodity code category hierarchy type for product classification.</span></span>  
6. <span data-ttu-id="53f4b-138">Nel campo Gerarchia di categorie fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="53f4b-138">In the Category hierarchy field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="53f4b-139">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="53f4b-139">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="53f4b-140">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="53f4b-140">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="53f4b-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="53f4b-141">Close the page.</span></span>


