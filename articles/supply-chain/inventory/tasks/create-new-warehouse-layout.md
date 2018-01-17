---
title: Creare un nuovo layout di magazzino
description: Questa procedura consente di visualizzare come impostare le informazioni sulle ubicazioni in un magazzino.
author: perlynne
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
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 7374aec8e3033370453752b9f488d0838008d709
ms.contentlocale: it-it
ms.lasthandoff: 01/17/2018

---
# <a name="create-a-new-warehouse-layout"></a><span data-ttu-id="ff649-103">Creare un nuovo layout di magazzino</span><span class="sxs-lookup"><span data-stu-id="ff649-103">Create a new warehouse layout</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ff649-104">Questa procedura consente di visualizzare come impostare le informazioni sulle ubicazioni in un magazzino.</span><span class="sxs-lookup"><span data-stu-id="ff649-104">This procedure shows you how to set up information about the locations in a warehouse.</span></span> <span data-ttu-id="ff649-105">È applicabile solo ai magazzini creati utilizzando "Operazioni di magazzino di base" del modulo Gestione inventario, non ai magazzini creati nel modulo Gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="ff649-105">This applies only to warehouses created using "basic warehousing" in the Inventory management module, not to warehouses created in the Warehouse management module.</span></span> <span data-ttu-id="ff649-106">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="ff649-106">You can use this procedure in demo data company USMF, or on your own data.</span></span>


## <a name="set-the-default-location-capacity"></a><span data-ttu-id="ff649-107">Impostare la capacità dell'ubicazione predefinita</span><span class="sxs-lookup"><span data-stu-id="ff649-107">Set the default location capacity</span></span>
1. <span data-ttu-id="ff649-108">Fare clic su Gestione magazzino > Impostazioni > Parametri di gestione articoli e magazzino.</span><span class="sxs-lookup"><span data-stu-id="ff649-108">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="ff649-109">Fare clic sulla scheda Ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="ff649-109">Click the Locations tab.</span></span>
3. <span data-ttu-id="ff649-110">Nel campo Larghezza standard immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ff649-110">In the Standard width field, enter a number.</span></span>
4. <span data-ttu-id="ff649-111">Nel campo Profondità standard immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ff649-111">In the Standard depth field, enter a number.</span></span>
5. <span data-ttu-id="ff649-112">Nel campo Altezza standard immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ff649-112">In the Standard height field, enter a number.</span></span>
6. <span data-ttu-id="ff649-113">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ff649-113">Click Save.</span></span>
7. <span data-ttu-id="ff649-114">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ff649-114">Close the page.</span></span>

## <a name="define-the-location-name-format"></a><span data-ttu-id="ff649-115">Definire il formato del nome dell'ubicazione</span><span class="sxs-lookup"><span data-stu-id="ff649-115">Define the location name format</span></span>
1. <span data-ttu-id="ff649-116">Passare a Gestione inventario > Impostazioni > Suddivisione scorte > Magazzino.</span><span class="sxs-lookup"><span data-stu-id="ff649-116">Go to Inventory management > Setup > Inventory breakdown > Warehouses.</span></span>
2. <span data-ttu-id="ff649-117">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ff649-117">Click New.</span></span>
3. <span data-ttu-id="ff649-118">Digitare un valore nel campo Magazzino.</span><span class="sxs-lookup"><span data-stu-id="ff649-118">In the Warehouse field, type a value.</span></span>
4. <span data-ttu-id="ff649-119">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="ff649-119">In the Name field, type a value.</span></span>
5. <span data-ttu-id="ff649-120">Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff649-120">In the Site field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="ff649-121">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="ff649-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="ff649-122">Attiva/disattiva l'espansione della sezione Nomi ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="ff649-122">Toggle the expansion of the Location names section.</span></span>
    * <span data-ttu-id="ff649-123">Le opzioni di questa sezione definiscono il formato predefinito per i nomi delle ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="ff649-123">The options in this section define the default format for location names.</span></span> <span data-ttu-id="ff649-124">Nel nostro esempio, includeremo il numero di sezione, il numero di scaffale e il numero di ripiano.</span><span class="sxs-lookup"><span data-stu-id="ff649-124">In our example, we'll include the aisle number, rack number and shelf number.</span></span>  
8. <span data-ttu-id="ff649-125">Impostare l'opzione Includi sezione su Sì.</span><span class="sxs-lookup"><span data-stu-id="ff649-125">Set the Include aisle option to Yes.</span></span>
9. <span data-ttu-id="ff649-126">Impostare l'opzione Includi scaffale su Sì.</span><span class="sxs-lookup"><span data-stu-id="ff649-126">Set the Include rack option to Yes.</span></span>
10. <span data-ttu-id="ff649-127">Nel campo Formato digitare un valore per lo scaffale.</span><span class="sxs-lookup"><span data-stu-id="ff649-127">In the Format field, for the rack, type a value.</span></span>
    * <span data-ttu-id="ff649-128">Ad esempio: -N</span><span class="sxs-lookup"><span data-stu-id="ff649-128">For example: -##</span></span>  
11. <span data-ttu-id="ff649-129">Impostare l'opzione Includi ripiano su Sì.</span><span class="sxs-lookup"><span data-stu-id="ff649-129">Set the Include shelf option to Yes.</span></span>
12. <span data-ttu-id="ff649-130">Nel campo Formato digitare un valore per il ripiano.</span><span class="sxs-lookup"><span data-stu-id="ff649-130">In the Format field, for the shelf, type a value.</span></span>
    * <span data-ttu-id="ff649-131">Ad esempio: -N</span><span class="sxs-lookup"><span data-stu-id="ff649-131">For example: -##</span></span>  

## <a name="define-warehouse-locations"></a><span data-ttu-id="ff649-132">Definire le ubicazioni di magazzino</span><span class="sxs-lookup"><span data-stu-id="ff649-132">Define warehouse locations</span></span>
1. <span data-ttu-id="ff649-133">Nel riquadro azioni fare clic su Magazzino.</span><span class="sxs-lookup"><span data-stu-id="ff649-133">On the Action Pane, click Warehouse.</span></span>
2. <span data-ttu-id="ff649-134">Fare clic su Creazione guidata ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ff649-134">Click Location Wizard.</span></span>
3. <span data-ttu-id="ff649-135">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="ff649-135">Click Next.</span></span>
4. <span data-ttu-id="ff649-136">Deselezionare l'opzione Banchine di uscita</span><span class="sxs-lookup"><span data-stu-id="ff649-136">De-select the Outbound docks option</span></span>
5. <span data-ttu-id="ff649-137">Deselezionare l'opzione Ubicazioni di stoccaggio</span><span class="sxs-lookup"><span data-stu-id="ff649-137">De-select the Bulk locations option</span></span>
6. <span data-ttu-id="ff649-138">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="ff649-138">Click Next.</span></span>
7. <span data-ttu-id="ff649-139">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="ff649-139">Click Next.</span></span>
8. <span data-ttu-id="ff649-140">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="ff649-140">Click Next.</span></span>
9. <span data-ttu-id="ff649-141">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="ff649-141">Click Next.</span></span>
10. <span data-ttu-id="ff649-142">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="ff649-142">Click Next.</span></span>
11. <span data-ttu-id="ff649-143">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="ff649-143">Click Next.</span></span>
12. <span data-ttu-id="ff649-144">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="ff649-144">Click Next.</span></span>
    * <span data-ttu-id="ff649-145">Si noti che le dimensioni fisiche visualizzate in questa pagina sono quelle impostate all'inizio di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="ff649-145">Note that the physical dimensions shown on this page are the ones that you set at the start of this procedure.</span></span>  
13. <span data-ttu-id="ff649-146">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="ff649-146">Click Next.</span></span>
14. <span data-ttu-id="ff649-147">Scegliere Fine.</span><span class="sxs-lookup"><span data-stu-id="ff649-147">Click Finish.</span></span>
15. <span data-ttu-id="ff649-148">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ff649-148">Close the page.</span></span>
16. <span data-ttu-id="ff649-149">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="ff649-149">Refresh the page.</span></span>

