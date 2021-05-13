---
title: Creare una distinta base per una rappresentazione generale prodotto basata su dimensioni
description: Per questa procedura è necessario completare le 4 guide precedenti di questa sequenza di otto registrazioni.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13053dd87242963586678b46c64493feb3383c4c
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920707"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a><span data-ttu-id="8b458-103">Creare una distinta base per una rappresentazione generale prodotto basata su dimensioni</span><span class="sxs-lookup"><span data-stu-id="8b458-103">Create a bill of materials for a dimension-based product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8b458-104">Per questa procedura è necessario completare le 4 guide precedenti di questa sequenza di otto registrazioni.</span><span class="sxs-lookup"><span data-stu-id="8b458-104">For this procedure you should have completed the previous 4 guides in this sequence of eight recordings.</span></span> <span data-ttu-id="8b458-105">Nelle prime 4 registrazioni vengono impostati i dati necessari per completare questa procedura.</span><span class="sxs-lookup"><span data-stu-id="8b458-105">The first 4 recordings set up data that is required to complete this procedure.</span></span> <span data-ttu-id="8b458-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="8b458-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="8b458-107">Questa attività viene in genere gestita nella finestra di progettazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="8b458-107">This task is typically handled by the product designer.</span></span>

## <a name="select-the-product"></a><span data-ttu-id="8b458-108">Selezionare il prodotto</span><span class="sxs-lookup"><span data-stu-id="8b458-108">Select the product</span></span>

1. <span data-ttu-id="8b458-109">Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="8b458-109">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="8b458-110">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8b458-110">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="8b458-111">Individuare la rappresentazione generale prodotto rilasciata con la tecnologia di configurazione basata su dimensioni creata nella prima attività della guida di questa sequenza.</span><span class="sxs-lookup"><span data-stu-id="8b458-111">Find the released product master with dimension-based configuration technology that you created in the first task guide in this sequence.</span></span>  
1. <span data-ttu-id="8b458-112">Nel riquadro azioni selezionare **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="8b458-112">On the Action Pane, select **Engineer**.</span></span>
1. <span data-ttu-id="8b458-113">Seleziona **Versioni DBA**.</span><span class="sxs-lookup"><span data-stu-id="8b458-113">Select **BOM versions**.</span></span>

## <a name="create-new-bom-and-bom-version"></a><span data-ttu-id="8b458-114">Creare una nuova DBA e una nuova versione DBA</span><span class="sxs-lookup"><span data-stu-id="8b458-114">Create new BOM and BOM version</span></span>

1. <span data-ttu-id="8b458-115">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8b458-115">Select **New**.</span></span>
1. <span data-ttu-id="8b458-116">Selezionare **DBA e versione DBA**.</span><span class="sxs-lookup"><span data-stu-id="8b458-116">Select **BOM and BOM version**.</span></span>
1. <span data-ttu-id="8b458-117">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="8b458-117">In the **Name** field, type a value.</span></span>
    * <span data-ttu-id="8b458-118">Impostazione di un sito</span><span class="sxs-lookup"><span data-stu-id="8b458-118">Setting a site</span></span>  
    * <span data-ttu-id="8b458-119">In questa procedura non impostiamo un sito specifico per la DBA.</span><span class="sxs-lookup"><span data-stu-id="8b458-119">In this procedure we don't set a specific site for the BOM.</span></span>  
1. <span data-ttu-id="8b458-120">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b458-120">Select **OK**.</span></span>
1. <span data-ttu-id="8b458-121">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8b458-121">Select **New**.</span></span>
    * <span data-ttu-id="8b458-122">In questa procedura aggiungeremo quattro righe alla DBA.</span><span class="sxs-lookup"><span data-stu-id="8b458-122">In this procedure we will add four lines to the BOM.</span></span> <span data-ttu-id="8b458-123">Due righe rappresentano le opzioni di cavo e due righe rappresentano le opzioni di gabinetto.</span><span class="sxs-lookup"><span data-stu-id="8b458-123">Two lines represent cable options and two lines represent cabinet options.</span></span>  
1. <span data-ttu-id="8b458-124">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8b458-124">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="8b458-125">Nel campo **Numero articolo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8b458-125">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="8b458-126">Selezionare il numero di articolo A0001, cavi HDMI 6.</span><span class="sxs-lookup"><span data-stu-id="8b458-126">Select item number A0001, HDMI 6' Cables.</span></span>  
1. <span data-ttu-id="8b458-127">Nel campo **Gruppo di configurazioni** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8b458-127">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="8b458-128">Selezionare il gruppo di configurazione dei cavi creato nella guida 4 di questa sequenza.</span><span class="sxs-lookup"><span data-stu-id="8b458-128">Select the cable configuration group created in guide 4 in this sequence.</span></span>  
1. <span data-ttu-id="8b458-129">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8b458-129">Select **New**.</span></span>
    * <span data-ttu-id="8b458-130">Selezionare il numero di articolo A0002, cavi HDMI 12.</span><span class="sxs-lookup"><span data-stu-id="8b458-130">Select item number A0002, HDMI 12' Cables.</span></span>  
1. <span data-ttu-id="8b458-131">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8b458-131">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="8b458-132">Nel campo **Numero articolo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8b458-132">In the **Item number** field, enter or select a value.</span></span>
1. <span data-ttu-id="8b458-133">Nel campo **Gruppo di configurazioni** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8b458-133">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="8b458-134">Selezionare di nuovo il gruppo di configurazioni dei cavi.</span><span class="sxs-lookup"><span data-stu-id="8b458-134">Select the cable configuration group again.</span></span>  
1. <span data-ttu-id="8b458-135">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8b458-135">Select **New**.</span></span>
1. <span data-ttu-id="8b458-136">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8b458-136">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="8b458-137">Nel campo **Numero articolo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8b458-137">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="8b458-138">Selezionare il numero di articolo D0002, cabinet.</span><span class="sxs-lookup"><span data-stu-id="8b458-138">Select item number D0002 Cabinet.</span></span>  
1. <span data-ttu-id="8b458-139">Nel campo **Gruppo di configurazioni** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8b458-139">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="8b458-140">Selezionare il gruppo di configurazioni del cabinet per questa riga DBA.</span><span class="sxs-lookup"><span data-stu-id="8b458-140">Select the cabinet configuration group for this BOM line.</span></span>  
1. <span data-ttu-id="8b458-141">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8b458-141">Select **New**.</span></span>
1. <span data-ttu-id="8b458-142">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8b458-142">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="8b458-143">Nel campo **Numero articolo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8b458-143">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="8b458-144">Selezionare il numero di articolo M0007 StandardCabinet come ultima riga DBA.</span><span class="sxs-lookup"><span data-stu-id="8b458-144">Select Item number M0007 StandardCabinet as the last BOM line.</span></span>  
1. <span data-ttu-id="8b458-145">Nel campo **Gruppo di configurazioni** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8b458-145">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="8b458-146">Selezionare il gruppo di configurazioni del cabinet per l'ultima riga DBA.</span><span class="sxs-lookup"><span data-stu-id="8b458-146">Select the Cabinet configuration group for the last BOM line.</span></span>  

## <a name="approve-and-activate"></a><span data-ttu-id="8b458-147">Approva e attiva</span><span class="sxs-lookup"><span data-stu-id="8b458-147">Approve and activate</span></span>

1. <span data-ttu-id="8b458-148">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b458-148">Close the page.</span></span>
1. <span data-ttu-id="8b458-149">Selezionare **Approva**.</span><span class="sxs-lookup"><span data-stu-id="8b458-149">Select **Approve**.</span></span>
1. <span data-ttu-id="8b458-150">Nel campo **Approvato da** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="8b458-150">In the **Approved by** field, enter or select a value.</span></span>
1. <span data-ttu-id="8b458-151">Selezionare *Sì* nel campo **Approvare anche la distinta base?**.</span><span class="sxs-lookup"><span data-stu-id="8b458-151">Select *Yes* in the **Do you also want to approve the bill of materials?** field.</span></span>
1. <span data-ttu-id="8b458-152">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b458-152">Select **OK**.</span></span>
1. <span data-ttu-id="8b458-153">Selezionare **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="8b458-153">Select **Activate**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]