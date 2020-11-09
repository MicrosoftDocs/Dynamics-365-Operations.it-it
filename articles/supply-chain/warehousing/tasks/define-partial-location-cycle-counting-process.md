---
title: 'Definire il processo di conteggio ciclo parziale di ubicazione '
description: Quando si utilizzano i piani di conteggio ciclo per creare il lavoro di conteggio, è possibile definire le operazioni di conteggio effettive richiedendo che vengano conteggiati solo i prodotti specifici e le varianti prodotto anziché tutti le scorte disponibili nell'ubicazione.
author: ShylaThompson
manager: tfehr
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 39a256a5a88a6d70373d6e23f1f380da6791f418
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016080"
---
# <a name="define-partial-location-cycle-counting-process"></a><span data-ttu-id="59e71-103">Definire il processo di conteggio ciclo parziale di ubicazione </span><span class="sxs-lookup"><span data-stu-id="59e71-103">Define partial location cycle counting process</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="59e71-104">Quando si utilizzano i piani di conteggio ciclo per creare il lavoro di conteggio, è possibile definire le operazioni di conteggio effettive richiedendo che vengano conteggiati solo i prodotti specifici e le varianti prodotto anziché tutti le scorte disponibili nell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="59e71-104">When you use cycle count plans to create counting work, you can guide the actual counting operations by requesting that only specific products and product variants be counted instead of all on-hand inventory at the location.</span></span> <span data-ttu-id="59e71-105">Applicando un filtro per prodotti specifici, il responsabile del magazzino può ridurre i costi generali di revisione, evitare errori di consolidamento e risparmiare tempo.</span><span class="sxs-lookup"><span data-stu-id="59e71-105">By filtering on specific products, the warehouse manager can reduce review overhead, help prevent consolidation mistakes, and save time.</span></span> <span data-ttu-id="59e71-106">In genere, un responsabile del magazzino esegue le attività di impostazione.</span><span class="sxs-lookup"><span data-stu-id="59e71-106">Typically, a warehouse manager performs the setup tasks.</span></span> <span data-ttu-id="59e71-107">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure con dati propri.</span><span class="sxs-lookup"><span data-stu-id="59e71-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="create-a-cycle-counting-work-template"></a><span data-ttu-id="59e71-108">Creare un modello di lavoro di conteggio ciclo</span><span class="sxs-lookup"><span data-stu-id="59e71-108">Create a cycle counting work template</span></span>
1. <span data-ttu-id="59e71-109">Andare a Gestione magazzino > Impostazioni > Lavoro > Modelli di lavoro.</span><span class="sxs-lookup"><span data-stu-id="59e71-109">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="59e71-110">Nel campo Tipo ordine di lavoro selezionare "Conteggio ciclo".</span><span class="sxs-lookup"><span data-stu-id="59e71-110">In the Work order type field, select 'Cycle counting'.</span></span>
3. <span data-ttu-id="59e71-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="59e71-111">Click New.</span></span>
4. <span data-ttu-id="59e71-112">Immettere un numero nel campo Numero progressivo.</span><span class="sxs-lookup"><span data-stu-id="59e71-112">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="59e71-113">L'ordinamento è crescente.</span><span class="sxs-lookup"><span data-stu-id="59e71-113">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="59e71-114">Il valore deve essere maggiore di 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="59e71-114">The value must be more than 0 (zero).</span></span>  
5. <span data-ttu-id="59e71-115">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="59e71-115">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="59e71-116">Digitare un valore nel campo Modello di lavoro.</span><span class="sxs-lookup"><span data-stu-id="59e71-116">In the Work template field, type a value.</span></span>
7. <span data-ttu-id="59e71-117">Nel campo Descrizione modello di lavoro, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="59e71-117">In the Work template description field, type a value.</span></span>
8. <span data-ttu-id="59e71-118">Nel campo ID pool lavoro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="59e71-118">In the Work pool ID field, enter or select a value.</span></span>
9. <span data-ttu-id="59e71-119">Nel campo Priorità lavoro immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="59e71-119">In the Work priority field, enter a number.</span></span>
10. <span data-ttu-id="59e71-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="59e71-120">Click Save.</span></span>
11. <span data-ttu-id="59e71-121">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="59e71-121">Click New.</span></span>
12. <span data-ttu-id="59e71-122">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="59e71-122">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="59e71-123">Nel campo Tipo di lavoro selezionare "Conteggio".</span><span class="sxs-lookup"><span data-stu-id="59e71-123">In the Work type field, select 'Counting'.</span></span>
14. <span data-ttu-id="59e71-124">Nel campo ID classe lavoro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="59e71-124">In the Work class ID field, enter or select a value.</span></span>
15. <span data-ttu-id="59e71-125">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="59e71-125">Click Save.</span></span>
16. <span data-ttu-id="59e71-126">Fare clic su Interruzioni riga lavoro.</span><span class="sxs-lookup"><span data-stu-id="59e71-126">Click Work line breaks.</span></span>
17. <span data-ttu-id="59e71-127">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="59e71-127">Click New.</span></span>
18. <span data-ttu-id="59e71-128">Immettere un numero nel campo Numero progressivo.</span><span class="sxs-lookup"><span data-stu-id="59e71-128">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="59e71-129">L'ordinamento è crescente.</span><span class="sxs-lookup"><span data-stu-id="59e71-129">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="59e71-130">Il valore deve essere maggiore di 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="59e71-130">The value must be more than 0 (zero).</span></span>  
19. <span data-ttu-id="59e71-131">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="59e71-131">Click Save.</span></span>
20. <span data-ttu-id="59e71-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="59e71-132">Close the page.</span></span>
21. <span data-ttu-id="59e71-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="59e71-133">Close the page.</span></span>

## <a name="create-a-cycle-counting-plan"></a><span data-ttu-id="59e71-134">Crea un piano di conteggio ciclo</span><span class="sxs-lookup"><span data-stu-id="59e71-134">Create a cycle counting plan</span></span>
1. <span data-ttu-id="59e71-135">Andare a Gestione magazzino > Impostazioni > Conteggio ciclo > Piani di conteggio ciclo.</span><span class="sxs-lookup"><span data-stu-id="59e71-135">Go to Warehouse management > Setup > Cycle counting > Cycle count plans.</span></span>
2. <span data-ttu-id="59e71-136">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="59e71-136">Click New.</span></span>
3. <span data-ttu-id="59e71-137">Nel campo ID piano di conteggio ciclo immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="59e71-137">In the Cycle counting plan ID field, type a value.</span></span>
4. <span data-ttu-id="59e71-138">Digitare un valore nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="59e71-138">In the Description field, type a value.</span></span>
5. <span data-ttu-id="59e71-139">Nel campo Numero massimo di conteggi ciclo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="59e71-139">In the Maximum number of cycle counts field, enter a number.</span></span>
6. <span data-ttu-id="59e71-140">Nel campo Modello di lavoro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="59e71-140">In the Work template field, enter or select a value.</span></span>
7. <span data-ttu-id="59e71-141">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="59e71-141">Click New.</span></span>
8. <span data-ttu-id="59e71-142">Immettere un numero nel campo Numero progressivo.</span><span class="sxs-lookup"><span data-stu-id="59e71-142">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="59e71-143">L'ordinamento è crescente.</span><span class="sxs-lookup"><span data-stu-id="59e71-143">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="59e71-144">Il valore deve essere maggiore di 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="59e71-144">The value must be more than 0 (zero).</span></span>  
9. <span data-ttu-id="59e71-145">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="59e71-145">In the Description field, type a value.</span></span>
10. <span data-ttu-id="59e71-146">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="59e71-146">Click Save.</span></span>
11. <span data-ttu-id="59e71-147">Fare clic su Definisci query prodotto.</span><span class="sxs-lookup"><span data-stu-id="59e71-147">Click Define product query.</span></span>
12. <span data-ttu-id="59e71-148">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="59e71-148">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="59e71-149">Nel campo Criteri immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="59e71-149">In the Criteria field, enter or select a value.</span></span>
14. <span data-ttu-id="59e71-150">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="59e71-150">Click OK.</span></span>
15. <span data-ttu-id="59e71-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="59e71-151">Close the page.</span></span>

