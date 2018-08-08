--- 
title: Individuare le varianti prodotto obsolete
description: Questa procedura mostra come trovare prodotti o varianti di prodotto obsoleti e come associare uno stato del ciclo di vita del prodotto ai prodotti obsoleti.
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 4641d24cfa24722f5411da8943bfe4095a9546a4
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---
# <a name="find-obsolete-product-variants"></a><span data-ttu-id="f12fb-103">Individuare le varianti prodotto obsolete</span><span class="sxs-lookup"><span data-stu-id="f12fb-103">Find obsolete product variants</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f12fb-104">Questa procedura mostra come trovare prodotti o varianti di prodotto obsoleti e come associare uno stato del ciclo di vita del prodotto ai prodotti obsoleti.</span><span class="sxs-lookup"><span data-stu-id="f12fb-104">This procedure shows how to find obsolete released products or product variants and how to associate a product lifecycle state to the obsolete products.</span></span> <span data-ttu-id="f12fb-105">Prerequisito: è necessario definire almeno uno stato del ciclo di vita di un prodotto che è inattivo per la progettazione prima di poter eseguire la guida attività.</span><span class="sxs-lookup"><span data-stu-id="f12fb-105">Prerequisite: You need to define at least one product lifecycle state that is inactive for planning before you can play this task guide.</span></span>


## <a name="run-a-simulation"></a><span data-ttu-id="f12fb-106">Eseguire una simulazione</span><span class="sxs-lookup"><span data-stu-id="f12fb-106">Run a simulation</span></span>
1. <span data-ttu-id="f12fb-107">Passare a Gestione delle informazioni sul prodotto > Attività periodiche > Cambia stato del ciclo di vita per prodotti obsoleti.</span><span class="sxs-lookup"><span data-stu-id="f12fb-107">Go to Product information management > Periodic tasks > Change lifecycle state for obsolete products.</span></span>
2. <span data-ttu-id="f12fb-108">Nel campo Nuovo stato del ciclo di vita prodotto immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f12fb-108">In the New product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="f12fb-109">Selezionare Sì nel campo Esegui simulazione senza aggiornare i dati del prodotto.</span><span class="sxs-lookup"><span data-stu-id="f12fb-109">Select Yes in the Run simulation without updating product data field.</span></span>
4. <span data-ttu-id="f12fb-110">Nel campo Escludi prodotti creati in questo numero di giorni, immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="f12fb-110">In the Exclude products created within this number of days field, enter a number.</span></span>
5. <span data-ttu-id="f12fb-111">Nel campo Escludi prodotti utilizzati nelle transazioni (in numero di giorni), immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="f12fb-111">In the Exclude products used in transactions (in number of days) field, enter a number.</span></span>
6. <span data-ttu-id="f12fb-112">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="f12fb-112">Expand the Records to include section.</span></span>
7. <span data-ttu-id="f12fb-113">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="f12fb-113">Click Filter.</span></span>
8. <span data-ttu-id="f12fb-114">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f12fb-114">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="f12fb-115">Digitare un valore nel campo Criteri.</span><span class="sxs-lookup"><span data-stu-id="f12fb-115">In the Criteria field, type a value.</span></span>
10. <span data-ttu-id="f12fb-116">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f12fb-116">Click OK.</span></span>
11. <span data-ttu-id="f12fb-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f12fb-117">Click OK.</span></span>

> [!NOTE]
> <span data-ttu-id="f12fb-118">Si consiglia di eseguire la simulazione nel batch se si prevede di cercare un numero elevato di prodotti.</span><span class="sxs-lookup"><span data-stu-id="f12fb-118">It is recommended to run the simulation in batch if you expect to search a large number of products.</span></span> <span data-ttu-id="f12fb-119">Inoltre, verificare che la simulazione non venga eseguita durante l'orario di lavoro più attivo della società.</span><span class="sxs-lookup"><span data-stu-id="f12fb-119">Also, make sure that the simulation is not run during the most active working time of the company.</span></span>  

## <a name="review-the-simulation-results"></a><span data-ttu-id="f12fb-120">Esaminare i risultati della simulazione</span><span class="sxs-lookup"><span data-stu-id="f12fb-120">Review the simulation results</span></span>
1. <span data-ttu-id="f12fb-121">Passare a Gestione delle informazioni sul prodotto > Richieste di informazioni e report > Storico di gestione dello stato del ciclo di vita prodotto.</span><span class="sxs-lookup"><span data-stu-id="f12fb-121">Go to Product information management > Inquiries and reports > Product lifecycle state maintenance history.</span></span>
   
> [!NOTE]
> <span data-ttu-id="f12fb-122">In questa pagina è possibile esaminare i risultati della simulazione e valutare quanti prodotti e varianti di prodotto saranno associati a un nuovo stato del ciclo di vita del prodotto quando si esegue l'aggiornamento senza simulazione.</span><span class="sxs-lookup"><span data-stu-id="f12fb-122">On this page, you can review the simulation results and make an assessment of how many products and product variants will be associated with a new product lifecycle state when running the update without simulation.</span></span>  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a><span data-ttu-id="f12fb-123">Eseguire l'aggiornamento dello stato del ciclo di vita per prodotti obsoleti</span><span class="sxs-lookup"><span data-stu-id="f12fb-123">Run the update of the Product lifecycle state for obsolete products</span></span>
1. <span data-ttu-id="f12fb-124">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f12fb-124">Close the page.</span></span>
2. <span data-ttu-id="f12fb-125">Passare a Gestione delle informazioni sul prodotto > Attività periodiche > Cambia stato del ciclo di vita per prodotti obsoleti.</span><span class="sxs-lookup"><span data-stu-id="f12fb-125">Go to Product information management > Periodic tasks > Change lifecycle state for obsolete products.</span></span>
3. <span data-ttu-id="f12fb-126">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="f12fb-126">Expand the Records to include section.</span></span>

> [!NOTE]
> <span data-ttu-id="f12fb-127">Tenere presente che l'ultima selezione è stata salvata.</span><span class="sxs-lookup"><span data-stu-id="f12fb-127">Note that the last selection has been saved.</span></span>  

4. <span data-ttu-id="f12fb-128">Selezionare No nel campo Esegui simulazione senza aggiornare i dati del prodotto.</span><span class="sxs-lookup"><span data-stu-id="f12fb-128">Select No in the Run simulation without updating product data field.</span></span>
5. <span data-ttu-id="f12fb-129">Espandere la sezione Esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="f12fb-129">Expand the Run in the background section.</span></span>

> [!NOTE]
> <span data-ttu-id="f12fb-130">A seconda del numero di prodotti e delle varianti prodotto che vengono modificati, valutare l'opportunità di eseguire il processo in batch.</span><span class="sxs-lookup"><span data-stu-id="f12fb-130">Depending on how many products and product variants are affected, consider running this job in batch.</span></span> <span data-ttu-id="f12fb-131">Verificare che non si sta eseguendo un processo di aggiornamento di grandi dimensioni durante le ore lavorative più attive della società.</span><span class="sxs-lookup"><span data-stu-id="f12fb-131">Make sure that you are not running a large update job during the most active working hours in the company.</span></span>  

6. <span data-ttu-id="f12fb-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f12fb-132">Click OK.</span></span>
7. <span data-ttu-id="f12fb-133">Passare a Gestione delle informazioni sul prodotto > Richieste di informazioni e report > Storico di gestione dello stato del ciclo di vita prodotto.</span><span class="sxs-lookup"><span data-stu-id="f12fb-133">Go to Product information management > Inquiries and reports > Product lifecycle state maintenance history.</span></span>

> [!NOTE]
> <span data-ttu-id="f12fb-134">Esaminare i prodotti e le varianti prodotto rilasciati modificati.</span><span class="sxs-lookup"><span data-stu-id="f12fb-134">Review the changed released products and product variants.</span></span>  

8. <span data-ttu-id="f12fb-135">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="f12fb-135">In the list, find and select the desired record.</span></span>


