---
title: Creare una distinta base per una rappresentazione generale prodotto basata su dimensioni
description: Per questa procedura è necessario completare le 4 guide precedenti di questa sequenza di otto registrazioni.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 677aacb72d1c3f33bed8bb6c9cd32e5dbca677cc
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844923"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a><span data-ttu-id="63b4c-103">Creare una distinta base per una rappresentazione generale prodotto basata su dimensioni</span><span class="sxs-lookup"><span data-stu-id="63b4c-103">Create a bill of materials for a dimension-based product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="63b4c-104">Per questa procedura è necessario completare le 4 guide precedenti di questa sequenza di otto registrazioni.</span><span class="sxs-lookup"><span data-stu-id="63b4c-104">For this procedure you should have completed the previous 4 guides in this sequence of eight recordings.</span></span> <span data-ttu-id="63b4c-105">Nelle prime 4 registrazioni vengono impostati i dati necessari per completare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="63b4c-105">The first 4 recordings set up data that is required to complete this procedure.</span></span> <span data-ttu-id="63b4c-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="63b4c-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="63b4c-107">Questa attività viene in genere gestita nella finestra di progettazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="63b4c-107">This task is typically handled by the product designer.</span></span>


## <a name="select-the-product"></a><span data-ttu-id="63b4c-108">Selezionare il prodotto</span><span class="sxs-lookup"><span data-stu-id="63b4c-108">Select the product</span></span>
1. <span data-ttu-id="63b4c-109">Fare clic su Gestione prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="63b4c-109">Click Released product maintenance.</span></span>
2. <span data-ttu-id="63b4c-110">Fare clic su Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="63b4c-110">Click Released products.</span></span>
3. <span data-ttu-id="63b4c-111">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="63b4c-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="63b4c-112">Individuare la rappresentazione generale prodotto rilasciata con la tecnologia di configurazione basata su dimensioni creata nella prima attività della guida di questa sequenza.</span><span class="sxs-lookup"><span data-stu-id="63b4c-112">Find the released product master with dimension-based configuration technology that you created in the first task guide in this sequence.</span></span>  
4. <span data-ttu-id="63b4c-113">Nel riquadro azioni fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="63b4c-113">On the Action Pane, click Engineer.</span></span>
5. <span data-ttu-id="63b4c-114">Fare clic su Versioni DBA.</span><span class="sxs-lookup"><span data-stu-id="63b4c-114">Click BOM versions.</span></span>

## <a name="create-new-bom-and-bom-version"></a><span data-ttu-id="63b4c-115">Creare una nuova DBA e una nuova versione DBA</span><span class="sxs-lookup"><span data-stu-id="63b4c-115">Create new BOM and BOM version</span></span>
1. <span data-ttu-id="63b4c-116">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="63b4c-116">Click New.</span></span>
2. <span data-ttu-id="63b4c-117">Fare clic su DBA e versione DBA.</span><span class="sxs-lookup"><span data-stu-id="63b4c-117">Click BOM and BOM version.</span></span>
3. <span data-ttu-id="63b4c-118">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="63b4c-118">In the Name field, type a value.</span></span>
    * <span data-ttu-id="63b4c-119">Impostazione di un sito</span><span class="sxs-lookup"><span data-stu-id="63b4c-119">Setting a site</span></span>  
    * <span data-ttu-id="63b4c-120">In questa procedura non impostiamo un sito specifico per la DBA.</span><span class="sxs-lookup"><span data-stu-id="63b4c-120">In this procedure we don't set a specific site for the BOM.</span></span>  
4. <span data-ttu-id="63b4c-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="63b4c-121">Click OK.</span></span>
5. <span data-ttu-id="63b4c-122">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="63b4c-122">Click New.</span></span>
    * <span data-ttu-id="63b4c-123">In questa procedura aggiungeremo quattro righe alla DBA.</span><span class="sxs-lookup"><span data-stu-id="63b4c-123">In this procedure we will add four lines to the BOM.</span></span> <span data-ttu-id="63b4c-124">Due righe rappresentano le opzioni di cavo e due righe rappresentano le opzioni di gabinetto.</span><span class="sxs-lookup"><span data-stu-id="63b4c-124">Two lines represent cable options and two lines represent cabinet options.</span></span>  
6. <span data-ttu-id="63b4c-125">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="63b4c-125">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="63b4c-126">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="63b4c-126">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="63b4c-127">Selezionare il numero di articolo A0001, cavi HDMI 6.</span><span class="sxs-lookup"><span data-stu-id="63b4c-127">Select item number A0001, HDMI 6' Cables.</span></span>  
8. <span data-ttu-id="63b4c-128">Nel campo Gruppo di configurazioni immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="63b4c-128">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="63b4c-129">Selezionare il gruppo di configurazione dei cavi creato nella guida 4 di questa sequenza.</span><span class="sxs-lookup"><span data-stu-id="63b4c-129">Select the Cable configuration group created in guide 4 in this sequence.</span></span>  
9. <span data-ttu-id="63b4c-130">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="63b4c-130">Click New.</span></span>
    * <span data-ttu-id="63b4c-131">Selezionare il numero di articolo A0002, cavi HDMI 12.</span><span class="sxs-lookup"><span data-stu-id="63b4c-131">Select item number A0002, HDMI 12' Cables.</span></span>  
10. <span data-ttu-id="63b4c-132">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="63b4c-132">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="63b4c-133">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="63b4c-133">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="63b4c-134">Nel campo Gruppo di configurazioni immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="63b4c-134">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="63b4c-135">Selezionare di nuovo il gruppo di configurazioni dei cavi.</span><span class="sxs-lookup"><span data-stu-id="63b4c-135">Select the Cable configuration group again.</span></span>  
13. <span data-ttu-id="63b4c-136">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="63b4c-136">Click New.</span></span>
14. <span data-ttu-id="63b4c-137">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="63b4c-137">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="63b4c-138">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="63b4c-138">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="63b4c-139">Selezionare il numero di articolo D0002, cabinet.</span><span class="sxs-lookup"><span data-stu-id="63b4c-139">Select item number D0002 Cabinet.</span></span>  
16. <span data-ttu-id="63b4c-140">Nel campo Gruppo di configurazioni immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="63b4c-140">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="63b4c-141">Selezionare il gruppo di configurazioni del cabinet per questa riga DBA.</span><span class="sxs-lookup"><span data-stu-id="63b4c-141">Select the Cabinet configuration group for this BOM line.</span></span>  
17. <span data-ttu-id="63b4c-142">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="63b4c-142">Click New.</span></span>
18. <span data-ttu-id="63b4c-143">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="63b4c-143">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="63b4c-144">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="63b4c-144">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="63b4c-145">Selezionare il numero di articolo M0007 StandardCabinet come ultima riga DBA.</span><span class="sxs-lookup"><span data-stu-id="63b4c-145">Select Item number M0007 StandardCabinet as the last BOM line.</span></span>  
20. <span data-ttu-id="63b4c-146">Nel campo Gruppo di configurazioni immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="63b4c-146">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="63b4c-147">Selezionare il gruppo di configurazioni del cabinet per l'ultima riga DBA.</span><span class="sxs-lookup"><span data-stu-id="63b4c-147">Select the Cabinet configuration group for the laste BOM line.</span></span>  

## <a name="approve-and-activate"></a><span data-ttu-id="63b4c-148">Approva e attiva</span><span class="sxs-lookup"><span data-stu-id="63b4c-148">Approve and activate</span></span>
1. <span data-ttu-id="63b4c-149">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="63b4c-149">Close the page.</span></span>
2. <span data-ttu-id="63b4c-150">Fare clic su Approva.</span><span class="sxs-lookup"><span data-stu-id="63b4c-150">Click Approve.</span></span>
3. <span data-ttu-id="63b4c-151">Nel campo Approvato da immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="63b4c-151">In the Approved by field, enter or select a value.</span></span>
4. <span data-ttu-id="63b4c-152">Selezionare Sì nel campo Approvare anche la distinta base? .</span><span class="sxs-lookup"><span data-stu-id="63b4c-152">Select Yes in the Do you also want to approve the bill of materials? field.</span></span>
5. <span data-ttu-id="63b4c-153">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="63b4c-153">Click OK.</span></span>
6. <span data-ttu-id="63b4c-154">Fare clic su Attiva.</span><span class="sxs-lookup"><span data-stu-id="63b4c-154">Click Activate.</span></span>

