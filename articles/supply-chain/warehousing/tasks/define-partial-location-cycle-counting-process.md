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
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dfea71459b80712c924912d909a0fdfa5fad09ad
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238944"
---
# <a name="define-partial-location-cycle-counting-process"></a><span data-ttu-id="692fa-103">Definire il processo di conteggio ciclo parziale di ubicazione </span><span class="sxs-lookup"><span data-stu-id="692fa-103">Define partial location cycle counting process</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="692fa-104">Quando si utilizzano i piani di conteggio ciclo per creare il lavoro di conteggio, è possibile definire le operazioni di conteggio effettive richiedendo che vengano conteggiati solo i prodotti specifici e le varianti prodotto anziché tutti le scorte disponibili nell'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="692fa-104">When you use cycle count plans to create counting work, you can guide the actual counting operations by requesting that only specific products and product variants be counted instead of all on-hand inventory at the location.</span></span> <span data-ttu-id="692fa-105">Applicando un filtro per prodotti specifici, il responsabile del magazzino può ridurre i costi generali di revisione, evitare errori di consolidamento e risparmiare tempo.</span><span class="sxs-lookup"><span data-stu-id="692fa-105">By filtering on specific products, the warehouse manager can reduce review overhead, help prevent consolidation mistakes, and save time.</span></span> <span data-ttu-id="692fa-106">In genere, un responsabile del magazzino esegue le attività di impostazione.</span><span class="sxs-lookup"><span data-stu-id="692fa-106">Typically, a warehouse manager performs the setup tasks.</span></span> <span data-ttu-id="692fa-107">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure con dati propri.</span><span class="sxs-lookup"><span data-stu-id="692fa-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="create-a-cycle-counting-work-template"></a><span data-ttu-id="692fa-108">Creare un modello di lavoro di conteggio ciclo</span><span class="sxs-lookup"><span data-stu-id="692fa-108">Create a cycle counting work template</span></span>
1. <span data-ttu-id="692fa-109">Andare a Gestione magazzino > Impostazioni > Lavoro > Modelli di lavoro.</span><span class="sxs-lookup"><span data-stu-id="692fa-109">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="692fa-110">Nel campo Tipo ordine di lavoro selezionare "Conteggio ciclo".</span><span class="sxs-lookup"><span data-stu-id="692fa-110">In the Work order type field, select 'Cycle counting'.</span></span>
3. <span data-ttu-id="692fa-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="692fa-111">Click New.</span></span>
4. <span data-ttu-id="692fa-112">Immettere un numero nel campo Numero progressivo.</span><span class="sxs-lookup"><span data-stu-id="692fa-112">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="692fa-113">L'ordinamento è crescente.</span><span class="sxs-lookup"><span data-stu-id="692fa-113">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="692fa-114">Il valore deve essere maggiore di 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="692fa-114">The value must be more than 0 (zero).</span></span>  
5. <span data-ttu-id="692fa-115">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="692fa-115">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="692fa-116">Digitare un valore nel campo Modello di lavoro.</span><span class="sxs-lookup"><span data-stu-id="692fa-116">In the Work template field, type a value.</span></span>
7. <span data-ttu-id="692fa-117">Nel campo Descrizione modello di lavoro, immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="692fa-117">In the Work template description field, type a value.</span></span>
8. <span data-ttu-id="692fa-118">Nel campo ID pool lavoro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="692fa-118">In the Work pool ID field, enter or select a value.</span></span>
9. <span data-ttu-id="692fa-119">Nel campo Priorità lavoro immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="692fa-119">In the Work priority field, enter a number.</span></span>
10. <span data-ttu-id="692fa-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="692fa-120">Click Save.</span></span>
11. <span data-ttu-id="692fa-121">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="692fa-121">Click New.</span></span>
12. <span data-ttu-id="692fa-122">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="692fa-122">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="692fa-123">Nel campo Tipo di lavoro selezionare "Conteggio".</span><span class="sxs-lookup"><span data-stu-id="692fa-123">In the Work type field, select 'Counting'.</span></span>
14. <span data-ttu-id="692fa-124">Nel campo ID classe lavoro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="692fa-124">In the Work class ID field, enter or select a value.</span></span>
15. <span data-ttu-id="692fa-125">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="692fa-125">Click Save.</span></span>
16. <span data-ttu-id="692fa-126">Fare clic su Interruzioni riga lavoro.</span><span class="sxs-lookup"><span data-stu-id="692fa-126">Click Work line breaks.</span></span>
17. <span data-ttu-id="692fa-127">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="692fa-127">Click New.</span></span>
18. <span data-ttu-id="692fa-128">Immettere un numero nel campo Numero progressivo.</span><span class="sxs-lookup"><span data-stu-id="692fa-128">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="692fa-129">L'ordinamento è crescente.</span><span class="sxs-lookup"><span data-stu-id="692fa-129">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="692fa-130">Il valore deve essere maggiore di 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="692fa-130">The value must be more than 0 (zero).</span></span>  
19. <span data-ttu-id="692fa-131">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="692fa-131">Click Save.</span></span>
20. <span data-ttu-id="692fa-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="692fa-132">Close the page.</span></span>
21. <span data-ttu-id="692fa-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="692fa-133">Close the page.</span></span>

## <a name="create-a-cycle-counting-plan"></a><span data-ttu-id="692fa-134">Crea un piano di conteggio ciclo</span><span class="sxs-lookup"><span data-stu-id="692fa-134">Create a cycle counting plan</span></span>
1. <span data-ttu-id="692fa-135">Andare a Gestione magazzino > Impostazioni > Conteggio ciclo > Piani di conteggio ciclo.</span><span class="sxs-lookup"><span data-stu-id="692fa-135">Go to Warehouse management > Setup > Cycle counting > Cycle count plans.</span></span>
2. <span data-ttu-id="692fa-136">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="692fa-136">Click New.</span></span>
3. <span data-ttu-id="692fa-137">Nel campo ID piano di conteggio ciclo immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="692fa-137">In the Cycle counting plan ID field, type a value.</span></span>
4. <span data-ttu-id="692fa-138">Digitare un valore nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="692fa-138">In the Description field, type a value.</span></span>
5. <span data-ttu-id="692fa-139">Nel campo Numero massimo di conteggi ciclo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="692fa-139">In the Maximum number of cycle counts field, enter a number.</span></span>
6. <span data-ttu-id="692fa-140">Nel campo Modello di lavoro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="692fa-140">In the Work template field, enter or select a value.</span></span>
7. <span data-ttu-id="692fa-141">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="692fa-141">Click New.</span></span>
8. <span data-ttu-id="692fa-142">Immettere un numero nel campo Numero progressivo.</span><span class="sxs-lookup"><span data-stu-id="692fa-142">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="692fa-143">L'ordinamento è crescente.</span><span class="sxs-lookup"><span data-stu-id="692fa-143">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="692fa-144">Il valore deve essere maggiore di 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="692fa-144">The value must be more than 0 (zero).</span></span>  
9. <span data-ttu-id="692fa-145">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="692fa-145">In the Description field, type a value.</span></span>
10. <span data-ttu-id="692fa-146">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="692fa-146">Click Save.</span></span>
11. <span data-ttu-id="692fa-147">Fare clic su Definisci query prodotto.</span><span class="sxs-lookup"><span data-stu-id="692fa-147">Click Define product query.</span></span>
12. <span data-ttu-id="692fa-148">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="692fa-148">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="692fa-149">Nel campo Criteri immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="692fa-149">In the Criteria field, enter or select a value.</span></span>
14. <span data-ttu-id="692fa-150">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="692fa-150">Click OK.</span></span>
15. <span data-ttu-id="692fa-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="692fa-151">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]