--- 
title: Creare una cella di lavoro in conto lavoro per la lean manufacturing
description: "Per modellare un'attività in conto lavoro per la lean manufacturing, è necessario creare una cella di lavoro associata al fornitore che esegue il lavoro."
author: cvocph
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3a42873cde84d67e1a4dd8c01f97b125b3a4f8cf
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a><span data-ttu-id="ac9e8-103">Creare una cella di lavoro in conto lavoro per la lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="ac9e8-103">Create a subcontracted work cell for lean manufacturing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ac9e8-104">Per modellare un'attività in conto lavoro per la lean manufacturing, è necessario creare una cella di lavoro associata al fornitore che esegue il lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-104">To model subcontracted work for lean manufacturing, you must create a work cell that is associated with the vendor that provides the work.</span></span> <span data-ttu-id="ac9e8-105">Una cella di lavoro in conto lavoro è collegata al fornitore tramite l'associazione di una risorsa di tipo fornitore.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-105">A subcontracted work cell is linked to the vendor through the association of a resource of the Vendor type.</span></span> <span data-ttu-id="ac9e8-106">Se si esegue questa registrazione nella società dimostrativa USMF, è possibile selezionare il conto fornitore con ID 1002 e il sito 1.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-106">If you play this recording in the USMF demo company, you can select vendor account ID 1002 and site 1.</span></span>


## <a name="create-a-vendor-resource"></a><span data-ttu-id="ac9e8-107">Creare una risorsa fornitore</span><span class="sxs-lookup"><span data-stu-id="ac9e8-107">Create a vendor resource</span></span>
1. <span data-ttu-id="ac9e8-108">Fare clic su Risorse.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-108">Go to Resources.</span></span>
2. <span data-ttu-id="ac9e8-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-109">Click New.</span></span>
3. <span data-ttu-id="ac9e8-110">Digitare un valore nel campo Risorsa.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-110">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="ac9e8-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ac9e8-112">Nel campo Tipo selezionare "Fornitore".</span><span class="sxs-lookup"><span data-stu-id="ac9e8-112">In the Type field, select 'Vendor'.</span></span>
6. <span data-ttu-id="ac9e8-113">Nel campo Fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-113">In the Vendor field, click the drop-down button to open the lookup.</span></span>

## <a name="create-the-resource-group"></a><span data-ttu-id="ac9e8-114">Creare il gruppo di risorse</span><span class="sxs-lookup"><span data-stu-id="ac9e8-114">Create the resource group</span></span>
1. <span data-ttu-id="ac9e8-115">Fare clic su Gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-115">Go to Resource groups.</span></span>
2. <span data-ttu-id="ac9e8-116">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-116">Click New.</span></span>
3. <span data-ttu-id="ac9e8-117">Digitare un valore nel campo Gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-117">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="ac9e8-118">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-118">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ac9e8-119">Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-119">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ac9e8-120">Selezionare il sito a cui la cella di lavoro deve essere allocata.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-120">Select the site that the work cell should be allocated to.</span></span> <span data-ttu-id="ac9e8-121">In teoria, un sito può rappresentare un singolo sito in cui opera un fornitore.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-121">In theory, a site can represent a single site that is operated by a vendor.</span></span> <span data-ttu-id="ac9e8-122">Tuttavia, nella maggior parte dei casi, le risorse in conto lavoro vengono inserite solo nel sito che ordina il conto lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-122">However, in most cases, subcontracted resources are just allocated to the site that orders the subcontracted work.</span></span> <span data-ttu-id="ac9e8-123">Si noti che i magazzini in ingresso e in uscita delle celle di lavoro in conto lavoro devono essere nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-123">Note that the input and output warehouses of subcontracted work cells must be on the same site.</span></span>  
6. <span data-ttu-id="ac9e8-124">Digitare un valore nel campo Sito.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-124">In the Site field, type a value.</span></span>
7. @SysTaskRecorder:_RequestClose
8. <span data-ttu-id="ac9e8-125">Selezionare o deselezionare la casella di controllo Cella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-125">Select or clear the Work cell check box.</span></span>
9. <span data-ttu-id="ac9e8-126">Nel campo Magazzino di input fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-126">In the Input warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ac9e8-127">Selezionare il magazzino e l'ubicazione utilizzati per conservare il materiale per la cella di lavoro gestita dal fornitore.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-127">Select the warehouse and location that are used to stage the material for the vendor-managed work cell.</span></span> <span data-ttu-id="ac9e8-128">In molti casi, il magazzino e l'ubicazione sono modellati utilizzando un magazzino separato per il fornitore e un'ubicazione per la cella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-128">In many cases, the warehouse and location are modeled by using a separate warehouse per vendor and one location per work cell.</span></span>  
10. <span data-ttu-id="ac9e8-129">Nel campo Ubicazione di input fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-129">In the Input location field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="ac9e8-130">Nel campo Magazzino di output fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-130">In the Output warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ac9e8-131">Definire il magazzino e l'ubicazione in cui il materiale viene registrato quando le attività in conto lavoro della cella di lavoro vengono registrate.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-131">Define the warehouse and location where the material is posted when the subcontracted activities of the work cell are posted.</span></span> <span data-ttu-id="ac9e8-132">Il magazzino e l'ubicazione possono trovarsi nel sito del fornitore se quest'ultimo dichiara il processo kanban.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-132">The warehouse and location can be at the vendor site if the vendor reports the kanban jobs.</span></span> <span data-ttu-id="ac9e8-133">In alternativa, il magazzino e l'ubicazione possono essere l'ubicazione di ricevimento associata al passaggio successivo del flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-133">Alternatively, the warehouse and location can be the receiving location that is associated with the next step of the production flow.</span></span>  
12. <span data-ttu-id="ac9e8-134">Nel campo Ubicazione di output fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-134">In the Output location field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="ac9e8-135">Espandere o comprimere la sezione Calendari.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-135">Expand or collapse the Calendars section.</span></span>
14. <span data-ttu-id="ac9e8-136">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-136">Click Add.</span></span>
15. <span data-ttu-id="ac9e8-137">Nel campo Calendario fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-137">In the Calendar field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ac9e8-138">Associare il calendario lavorativo della cella di lavoro al gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-138">Associate the working time calendar of the work cell with the resource group.</span></span> <span data-ttu-id="ac9e8-139">Per le risorse importanti, si consiglia di definire calendari specifici che rappresentano gli orari di lavoro esatti e le funzioni correlate del sito del fornitore o della cella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-139">For critical resources, we recommend that you define specific calendars that represent the exact working times and related capacities of the work cell or vendor site.</span></span>  
16. <span data-ttu-id="ac9e8-140">Espandere o comprimere la sezione Risorse.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-140">Expand or collapse the Resources section.</span></span>
17. <span data-ttu-id="ac9e8-141">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-141">Click Add.</span></span>
    * <span data-ttu-id="ac9e8-142">Un gruppo di risorse in conto lavoro deve disporre di una risorsa associata di tipo fornitore che collega il gruppo di risorse al conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-142">A subcontracted resource group must have an associated resource of the Vendor type that links the resource group to the vendor account.</span></span>  
18. <span data-ttu-id="ac9e8-143">Nel campo Risorsa fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-143">In the Resource field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ac9e8-144">Selezionare o immettere la risorsa fornitore creata nella sottoattività precedente.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-144">Select or enter the vendor resource that you created in the previous sub-task.</span></span>  
19. <span data-ttu-id="ac9e8-145">Espandere o comprimere la sezione Capacità cella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-145">Expand or collapse the Work cell capacity section.</span></span>
20. <span data-ttu-id="ac9e8-146">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-146">Click Add.</span></span>
    * <span data-ttu-id="ac9e8-147">Una cella di lavoro deve avere una capacità definita.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-147">A work cell must have a defined capacity.</span></span> <span data-ttu-id="ac9e8-148">In questo esempio verrà creata una capacità di produttività di 100 pezzi per giorno lavorativo standard.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-148">In this example, we create a throughput capacity of 100 pieces per standard workday.</span></span>  
21. <span data-ttu-id="ac9e8-149">Nel campo Modello di flusso di produzione fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-149">In the Production flow model field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="ac9e8-150">Selezionare un'opzione nel campo Periodo di capacità.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-150">In the Capacity period field, select an option.</span></span>
23. <span data-ttu-id="ac9e8-151">Nel campo Quantità di produttività media, immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-151">In the Average throughput quantity field, enter a number.</span></span>
24. <span data-ttu-id="ac9e8-152">Nel campo Unità fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-152">In the Unit field, click the drop-down button to open the lookup.</span></span>
25. <span data-ttu-id="ac9e8-153">ResolveChanges per l'unità.</span><span class="sxs-lookup"><span data-stu-id="ac9e8-153">ResolveChanges the Unit.</span></span>


