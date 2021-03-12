---
title: Creare una gerarchia di classificazione del prodotto
description: Questa procedura mostra come creare una nuova gerarchia di categorie e assegnare un tipo di gerarchia di codici di voce doganale.
author: ShylaThompson
manager: tfehr
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyCreate, EcoResCategory, EcoResCategoryHierarchyRole, EcoResProductCategory, EcoResCategorySearchList, EcoResCategoryHierarchyFactbox, EcoResCategoryFriendlyName, EcoResCategoryAddProduct
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 74be72ac5787273e13692abdb9db18be4c5ccc08
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966957"
---
# <a name="create-a-hierarchy-of-product-classification"></a><span data-ttu-id="0101c-103">Creare una gerarchia di classificazione del prodotto</span><span class="sxs-lookup"><span data-stu-id="0101c-103">Create a hierarchy of product classification</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0101c-104">Questa procedura mostra come creare una nuova gerarchia di categorie e assegnare un tipo di gerarchia di codici di voce doganale.</span><span class="sxs-lookup"><span data-stu-id="0101c-104">This procedure shows how to create a new category hierarchy and assign a commodity code hierarchy type.</span></span> <span data-ttu-id="0101c-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="0101c-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0101c-106">Questa procedura è destinata al responsabile della categoria.</span><span class="sxs-lookup"><span data-stu-id="0101c-106">This procedure is intended for the category manager.</span></span>


## <a name="create-the-new-category-hierarchy"></a><span data-ttu-id="0101c-107">Creare la nuova gerarchia di categorie</span><span class="sxs-lookup"><span data-stu-id="0101c-107">Create the new category hierarchy</span></span>
1. <span data-ttu-id="0101c-108">Andare a **Pannello di navigazione > Moduli > Gestione informazioni sul prodotto > Impostazioni > Categorie e attributi > Gerarchie di categorie.**</span><span class="sxs-lookup"><span data-stu-id="0101c-108">Go to **Navigation pane > Modules > Product information management > Setup > Categories and attributes > Category hierarchies**.</span></span>
2. <span data-ttu-id="0101c-109">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="0101c-109">Click **New**.</span></span>
3. <span data-ttu-id="0101c-110">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="0101c-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="0101c-111">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0101c-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="0101c-112">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="0101c-112">Click **Create**.</span></span>

## <a name="build-the-hierarchy"></a><span data-ttu-id="0101c-113">Sviluppare la gerarchia</span><span class="sxs-lookup"><span data-stu-id="0101c-113">Build the hierarchy</span></span>
1. <span data-ttu-id="0101c-114">Fare clic su nodo **Nuova categoria**.</span><span class="sxs-lookup"><span data-stu-id="0101c-114">Click **New** category node.</span></span>
2. <span data-ttu-id="0101c-115">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="0101c-115">In the **Name** field, type a value.</span></span>
3. <span data-ttu-id="0101c-116">Digitare un valore nel campo **Codice**.</span><span class="sxs-lookup"><span data-stu-id="0101c-116">In the **Code** field, type a value.</span></span>
4. <span data-ttu-id="0101c-117">Digitare un valore nel campo **Nome descrittivo**.</span><span class="sxs-lookup"><span data-stu-id="0101c-117">In the **Friendly name** field, type a value.</span></span>
5. <span data-ttu-id="0101c-118">Fare clic su nodo **Nuova categoria**.</span><span class="sxs-lookup"><span data-stu-id="0101c-118">Click **New** category node.</span></span>
6. <span data-ttu-id="0101c-119">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="0101c-119">In the **Name** field, type a value.</span></span>
7. <span data-ttu-id="0101c-120">Digitare un valore nel campo **Codice**.</span><span class="sxs-lookup"><span data-stu-id="0101c-120">In the **Code** field, type a value.</span></span>
8. <span data-ttu-id="0101c-121">Digitare un valore nel campo **Nome descrittivo**.</span><span class="sxs-lookup"><span data-stu-id="0101c-121">In the **Friendly name** field, type a value.</span></span>
9. <span data-ttu-id="0101c-122">Fare clic su nodo **Nuova categoria**.</span><span class="sxs-lookup"><span data-stu-id="0101c-122">Click **New** category node.</span></span>
10. <span data-ttu-id="0101c-123">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="0101c-123">In the **Name** field, type a value.</span></span>
11. <span data-ttu-id="0101c-124">Digitare un valore nel campo **Codice**.</span><span class="sxs-lookup"><span data-stu-id="0101c-124">In the **Code** field, type a value.</span></span>
12. <span data-ttu-id="0101c-125">Digitare un valore nel campo **Nome descrittivo**.</span><span class="sxs-lookup"><span data-stu-id="0101c-125">In the **Friendly name** field, type a value.</span></span>
13. <span data-ttu-id="0101c-126">Fare clic su nodo **Nuova categoria**.</span><span class="sxs-lookup"><span data-stu-id="0101c-126">Click **New** category node.</span></span>
14. <span data-ttu-id="0101c-127">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="0101c-127">In the **Name** field, type a value.</span></span>
15. <span data-ttu-id="0101c-128">Digitare un valore nel campo **Codice**.</span><span class="sxs-lookup"><span data-stu-id="0101c-128">In the **Code** field, type a value.</span></span>
16. <span data-ttu-id="0101c-129">Digitare un valore nel campo **Nome descrittivo**.</span><span class="sxs-lookup"><span data-stu-id="0101c-129">In the **Friendly name** field, type a value.</span></span>
17. <span data-ttu-id="0101c-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0101c-130">Close the page.</span></span>

## <a name="classify-the-hierarchy"></a><span data-ttu-id="0101c-131">Classificare la gerarchia</span><span class="sxs-lookup"><span data-stu-id="0101c-131">Classify the hierarchy</span></span>
1. <span data-ttu-id="0101c-132">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="0101c-132">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="0101c-133">Nel **riquadro Azioni** fare clic su **Gerarchia di categorie**.</span><span class="sxs-lookup"><span data-stu-id="0101c-133">On the **Action Pane**, click **Category hierarchy**.</span></span>
3. <span data-ttu-id="0101c-134">Fare clic su **Associa tipo gerarchia**.</span><span class="sxs-lookup"><span data-stu-id="0101c-134">Click **Associate hierarchy type**.</span></span>
4. <span data-ttu-id="0101c-135">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="0101c-135">Click **New**.</span></span>
5. <span data-ttu-id="0101c-136">Selezionare un'opzione nel campo **Tipo di gerarchia di categorie**.</span><span class="sxs-lookup"><span data-stu-id="0101c-136">In the **Category hierarchy type** field, select an option.</span></span> <span data-ttu-id="0101c-137">Selezionare il **tipo Gerarchia di codici di voce doganale per la classificazione di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="0101c-137">Select the **Commodity code category hierarchy type for product classification**.</span></span>  
6. <span data-ttu-id="0101c-138">Nel campo **Gerarchia di categorie** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="0101c-138">In the **Category hierarchy** field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="0101c-139">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0101c-139">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="0101c-140">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0101c-140">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="0101c-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0101c-141">Close the page.</span></span>

