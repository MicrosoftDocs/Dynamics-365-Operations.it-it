--- 
title: Creare un piano materiali per co-prodotti
description: Il pianificatore della produzione pianifica i fabbisogni di materiali per gli articoli che sono co-prodotti della formula.
author: YuyuScheller
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c8805ca02525ae001fbd5e10ad9405fe60c7473e
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="24984-103">Creare un piano materiali per co-prodotti</span><span class="sxs-lookup"><span data-stu-id="24984-103">Create a material plan for co-products</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="24984-104">Il pianificatore della produzione pianifica i fabbisogni di materiali per gli articoli che sono co-prodotti della formula.</span><span class="sxs-lookup"><span data-stu-id="24984-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="24984-105">La società di dati dimostrativi utilizzata per creare questa procedura è USP2.</span><span class="sxs-lookup"><span data-stu-id="24984-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="24984-106">Creare il fabbisogno per un co-prodotto</span><span class="sxs-lookup"><span data-stu-id="24984-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="24984-107">Fare clic su Dashboard predefinito.</span><span class="sxs-lookup"><span data-stu-id="24984-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="24984-108">Fare clic su Elaborazione e richiesta di informazioni ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="24984-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="24984-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="24984-109">Click New.</span></span>
4. <span data-ttu-id="24984-110">Fare clic su Ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="24984-110">Click Sales order.</span></span>
5. <span data-ttu-id="24984-111">Digitare un valore nel campo Conto cliente.</span><span class="sxs-lookup"><span data-stu-id="24984-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="24984-112">Esempio: US-001</span><span class="sxs-lookup"><span data-stu-id="24984-112">Example: US-001</span></span>  
6. <span data-ttu-id="24984-113">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="24984-113">Click OK.</span></span>
7. <span data-ttu-id="24984-114">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="24984-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="24984-115">Esempio: P6003</span><span class="sxs-lookup"><span data-stu-id="24984-115">Example: P6003</span></span>  
8. <span data-ttu-id="24984-116">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="24984-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="24984-117">Esempio: 50000</span><span class="sxs-lookup"><span data-stu-id="24984-117">Example: 50000</span></span>  
9. <span data-ttu-id="24984-118">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="24984-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="24984-119">Creare un piano materiali per co-prodotti</span><span class="sxs-lookup"><span data-stu-id="24984-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="24984-120">Fare clic su Pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="24984-120">Click Master planning.</span></span>
2. <span data-ttu-id="24984-121">Nel campo Piano fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="24984-121">In the Plan field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="24984-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="24984-122">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="24984-123">Esempio: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="24984-123">Example: MasterPlan</span></span>  
4. <span data-ttu-id="24984-124">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="24984-124">Click Run.</span></span>
5. <span data-ttu-id="24984-125">Espandere o comprimere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="24984-125">Expand or collapse the Records to include section.</span></span>
6. <span data-ttu-id="24984-126">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="24984-126">Click Filter.</span></span>
7. <span data-ttu-id="24984-127">Nell'elenco selezionare la riga per Campo = Numero articolo.</span><span class="sxs-lookup"><span data-stu-id="24984-127">In the list, select the row for Field = Item number.</span></span>
8. <span data-ttu-id="24984-128">Digitare un valore nel campo Criteri.</span><span class="sxs-lookup"><span data-stu-id="24984-128">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="24984-129">Esempio: P6003</span><span class="sxs-lookup"><span data-stu-id="24984-129">Example: P6003</span></span>  
9. <span data-ttu-id="24984-130">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="24984-130">Click OK.</span></span>
10. <span data-ttu-id="24984-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="24984-131">Click OK.</span></span>
11. <span data-ttu-id="24984-132">Fare clic su Ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="24984-132">Click Planned orders.</span></span>
12. <span data-ttu-id="24984-133">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="24984-133">Use the Quick Filter to find records.</span></span> <span data-ttu-id="24984-134">Ad esempio, filtrare il campo Numero articolo con un valore "P6000".</span><span class="sxs-lookup"><span data-stu-id="24984-134">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="24984-135">Applicare un filtro in base all'articolo formula con co-prodotto dell'articolo per cui è stato creato un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="24984-135">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
13. <span data-ttu-id="24984-136">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="24984-136">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="24984-137">Selezionare una delle righe restituite dal filtro.</span><span class="sxs-lookup"><span data-stu-id="24984-137">Select any of the rows returned by the filter.</span></span>  
14. <span data-ttu-id="24984-138">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="24984-138">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="24984-139">Espandere o comprimere la sezione Pegging.</span><span class="sxs-lookup"><span data-stu-id="24984-139">Expand or collapse the Pegging section.</span></span>
16. <span data-ttu-id="24984-140">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="24984-140">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="24984-141">L'ordine pianificato viene sottoposto all'ordine cliente per il co-prodotto.</span><span class="sxs-lookup"><span data-stu-id="24984-141">The planned order is pegged to the sales order for the co-product.</span></span>  
17. <span data-ttu-id="24984-142">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="24984-142">Close the page.</span></span>

