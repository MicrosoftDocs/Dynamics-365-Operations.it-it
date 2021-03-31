---
title: Creare uno stato predefinito del ciclo di vita del prodotto
description: In questa procedura viene illustrato come creare uno stato del ciclo di vita del prodotto predefinito nonché come associare lo stato predefinito con i prodotti rilasciati.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b65f34c1d7a0fd22201df5b48f8d42d452d6b8ef
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216083"
---
# <a name="create-a-default-product-lifecycle-state"></a><span data-ttu-id="53ce0-103">Creare uno stato predefinito del ciclo di vita del prodotto</span><span class="sxs-lookup"><span data-stu-id="53ce0-103">Create a default product lifecycle state</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="53ce0-104">In questa procedura viene illustrato come creare uno stato del ciclo di vita del prodotto predefinito nonché come associare lo stato predefinito con i prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="53ce0-104">This procedure shows how to create a default product lifecycle state as well as how to associate the default state with released products.</span></span>


## <a name="create-a-default-lifecycle-state"></a><span data-ttu-id="53ce0-105">Creare uno stato predefinito del ciclo di vita</span><span class="sxs-lookup"><span data-stu-id="53ce0-105">Create a default lifecycle state</span></span>
1. <span data-ttu-id="53ce0-106">Fare clic su Gestione informazioni sul prodotto > Impostazioni > Stato del ciclo di vita prodotto.</span><span class="sxs-lookup"><span data-stu-id="53ce0-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="53ce0-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="53ce0-107">Click New.</span></span>
3. <span data-ttu-id="53ce0-108">Nel campo Stato digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="53ce0-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="53ce0-109">Selezionare Sì nel campo Impostazione predefinita quando rilasciato a persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="53ce0-109">Select Yes in the Default when released to legal entity field.</span></span>
5. <span data-ttu-id="53ce0-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="53ce0-110">In the Description field, type a value.</span></span>
6. <span data-ttu-id="53ce0-111">Selezionare No nel campo Attivo per pianificazione.</span><span class="sxs-lookup"><span data-stu-id="53ce0-111">Select No in the Is active for planning field.</span></span>

> [!NOTE]
> <span data-ttu-id="53ce0-112">Se un nuovo prodotto rilasciato non deve essere incluso nella pianificazione generale, selezionare No.</span><span class="sxs-lookup"><span data-stu-id="53ce0-112">If a new released product should not be included in Master planning, select No.</span></span> <span data-ttu-id="53ce0-113">Se deve essere incluso nella pianificazione generale, lasciare il controllo sul valore predefinito Sì.</span><span class="sxs-lookup"><span data-stu-id="53ce0-113">If it should be included in Master planning, leave the control at its default value Yes.</span></span>  

## <a name="create-a-new-released-product"></a><span data-ttu-id="53ce0-114">Creare un nuovo prodotto rilasciato</span><span class="sxs-lookup"><span data-stu-id="53ce0-114">Create a new released product</span></span>
1. <span data-ttu-id="53ce0-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="53ce0-115">Close the page.</span></span>
2. <span data-ttu-id="53ce0-116">Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="53ce0-116">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="53ce0-117">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="53ce0-117">Click New.</span></span>
4. <span data-ttu-id="53ce0-118">Nel campo Numero prodotto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="53ce0-118">In the Product number field, type a value.</span></span>
5. <span data-ttu-id="53ce0-119">Digitare un valore nel campo Nome prodotto.</span><span class="sxs-lookup"><span data-stu-id="53ce0-119">In the Product name field, type a value.</span></span>
6. <span data-ttu-id="53ce0-120">Digitare un valore nel campo Nome di ricerca.</span><span class="sxs-lookup"><span data-stu-id="53ce0-120">In the Search name field, type a value.</span></span>
7. <span data-ttu-id="53ce0-121">Nel campo Gruppo modello articolo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="53ce0-121">In the Item model group field, enter or select a value.</span></span>
8. <span data-ttu-id="53ce0-122">Nel campo Gruppo di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="53ce0-122">In the Item group field, enter or select a value.</span></span>
9. <span data-ttu-id="53ce0-123">Nel campo Dimensione di immagazzinamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="53ce0-123">In the Storage dimension group field, enter or select a value.</span></span>
10. <span data-ttu-id="53ce0-124">Nel campo Dimensione di tracciabilità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="53ce0-124">In the Tracking dimension group field, enter or select a value.</span></span>
11. <span data-ttu-id="53ce0-125">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="53ce0-125">Click OK.</span></span>

> [!NOTE]
> <span data-ttu-id="53ce0-126">Lo stato del ciclo di vita del prodotto predefinito è una definizione globale.</span><span class="sxs-lookup"><span data-stu-id="53ce0-126">The default product lifecycle state is a global definition.</span></span>  

## <a name="change-the-product-to-an-active-state"></a><span data-ttu-id="53ce0-127">Modificare il prodotto su uno stato attivo</span><span class="sxs-lookup"><span data-stu-id="53ce0-127">Change the product to an active state</span></span>
1. <span data-ttu-id="53ce0-128">Nel campo Stato del ciclo di vita prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="53ce0-128">In the Product lifecycle state field, enter or select a value.</span></span>

> [!NOTE]
> <span data-ttu-id="53ce0-129">Si supponga di aver impostato uno stato attivo, è possibile ora selezionare lo stato attivo per consentire al prodotto di essere utilizzato nel calcolo del livello DBA e della pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="53ce0-129">Assume that you have set up an active state, you can now select the active state to allow the product to be used in Master planning and BOM-level calculation.</span></span> <span data-ttu-id="53ce0-130">Ovviamente, ciò è applicabile solo se tutti i dettagli prodotto necessari per una pianificazione coerente vengono specificati.</span><span class="sxs-lookup"><span data-stu-id="53ce0-130">Obviously, this only makes sense if all the product details that are required for consistent planning are specified.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]