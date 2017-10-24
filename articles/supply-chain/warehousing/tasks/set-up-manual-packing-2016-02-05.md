--- 
title: Impostare l'imballaggio manuale (solo febbraio e maggio 2016)
description: Il processo di imballaggio consente di convalidare e imballare i prodotti in contenitori.
author: BibiSp
manager: AnnBe
ms.date: 11/04/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7f992a6a1655cd868d79228c490d59b46bfae715
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-manual-packing-february--may-2016-only"></a><span data-ttu-id="33ec9-103">Impostare l'imballaggio manuale (solo febbraio e maggio 2016)</span><span class="sxs-lookup"><span data-stu-id="33ec9-103">Set up manual packing (February & May 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="33ec9-104">Il processo di imballaggio consente di convalidare e imballare i prodotti in contenitori.</span><span class="sxs-lookup"><span data-stu-id="33ec9-104">The packing process allows you to validate and pack products into containers.</span></span> <span data-ttu-id="33ec9-105">In questo processo i magazzinieri prelevano i prodotti dai percorsi di immagazzinamento e li spostano in un centro d'imballaggio in cui le quantità e i tipi di articolo vengono controllati e assegnati ai contenitori appropriati.</span><span class="sxs-lookup"><span data-stu-id="33ec9-105">In this process, warehouse workers pick products from the storage locations and move them to a packing station where they check the item quantities and types, and assign them to appropriate containers.</span></span> <span data-ttu-id="33ec9-106">Quando un contenitore è completamente imballato, è possibile chiuderlo e spostarlo nelle banchine di uscita e i prodotti sono pronti per essere spediti.</span><span class="sxs-lookup"><span data-stu-id="33ec9-106">When a container is fully packed, they can close it and move it to the outbound docks, and the products are ready to ship.</span></span> <span data-ttu-id="33ec9-107">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="33ec9-107">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-location-profiles"></a><span data-ttu-id="33ec9-108">Imposta profili ubicazione</span><span class="sxs-lookup"><span data-stu-id="33ec9-108">Set up location profiles</span></span>
1. <span data-ttu-id="33ec9-109">Andare a Gestione magazzino > Impostazioni > Magazzino > Profili ubicazione.</span><span class="sxs-lookup"><span data-stu-id="33ec9-109">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>
2. <span data-ttu-id="33ec9-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="33ec9-110">Click New.</span></span>
    * <span data-ttu-id="33ec9-111">Il profilo di ubicazione viene utilizzato per i centri di imballaggio e contiene le informazioni e le regole di un'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="33ec9-111">The location profile is used for packing stations and contains information and rules for a location.</span></span>  
3. <span data-ttu-id="33ec9-112">Nel campo ID profilo ubicazione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-112">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="33ec9-113">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="33ec9-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="33ec9-114">Nel campo Formato ubicazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-114">In the Location format field, enter or select a value.</span></span>
6. <span data-ttu-id="33ec9-115">Nel campo Tipo di ubicazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-115">In the Location type field, enter or select a value.</span></span>
7. <span data-ttu-id="33ec9-116">Selezionare Sì nel campo Consenti articoli combinati.</span><span class="sxs-lookup"><span data-stu-id="33ec9-116">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="33ec9-117">Selezionare Sì nel campo Consenti stati inventario combinati.</span><span class="sxs-lookup"><span data-stu-id="33ec9-117">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="33ec9-118">Selezionare Sì nel campo Ignora regole per giorni di batch.</span><span class="sxs-lookup"><span data-stu-id="33ec9-118">Select Yes in the Override rules for batch days field.</span></span>
10. <span data-ttu-id="33ec9-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="33ec9-119">Close the page.</span></span>

## <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="33ec9-120">Impostare i parametri per Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="33ec9-120">Set up warehouse management parameters</span></span> 
1. <span data-ttu-id="33ec9-121">Andare a Gestione magazzino > Impostazioni > Parametri di gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="33ec9-121">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="33ec9-122">Fare clic sulla scheda Imballaggio.</span><span class="sxs-lookup"><span data-stu-id="33ec9-122">Click the Packing tab.</span></span>
3. <span data-ttu-id="33ec9-123">Nel campo ID profilo per l'ubicazione imballaggio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-123">In the Profile ID for packing location field, enter or select a value.</span></span>
    * <span data-ttu-id="33ec9-124">Selezionare il profilo di ubicazione da utilizzare per l'imballaggio.</span><span class="sxs-lookup"><span data-stu-id="33ec9-124">Select the location profile that you want to use for packing.</span></span>  
4. <span data-ttu-id="33ec9-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="33ec9-125">Close the page.</span></span>

## <a name="set-up-container-types"></a><span data-ttu-id="33ec9-126">Impostare i tipi di contenitore</span><span class="sxs-lookup"><span data-stu-id="33ec9-126">Set up container types</span></span>
1. <span data-ttu-id="33ec9-127">Andare a Gestione magazzino > Impostazioni > Contenitori > Tipi di contenitore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-127">Go to Warehouse management > Setup > Containers > Container types.</span></span>
2. <span data-ttu-id="33ec9-128">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="33ec9-128">Click New.</span></span>
    * <span data-ttu-id="33ec9-129">È possibile definire i tipi di contenitori da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="33ec9-129">You can define the types of containers to use.</span></span> <span data-ttu-id="33ec9-130">È possibile specificare le dimensioni fisiche del contenitore, inclusi tara, peso massimo, volume massimo, lunghezza, larghezza e peso.</span><span class="sxs-lookup"><span data-stu-id="33ec9-130">You can specify the physical dimensions of the container, including tare weight, maximum weight, maximum volume, length, width, and weight.</span></span>  <span data-ttu-id="33ec9-131">Gli attributi sono campi personalizzati che consentono di aggiungere dimensioni extra sul tipo di contenitore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-131">The Attributes are customized fields that allow you to add extra dimensions on the container type.</span></span>     
3. <span data-ttu-id="33ec9-132">Nel campo Codice tipo di contenitore immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-132">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="33ec9-133">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-133">In the Description field, type a value.</span></span>
5. <span data-ttu-id="33ec9-134">Immettere un numero nel campo Tara.</span><span class="sxs-lookup"><span data-stu-id="33ec9-134">In the Tare weight field, enter a number.</span></span>
6. <span data-ttu-id="33ec9-135">Nel campo Peso massimo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="33ec9-135">In the Maximum weight field, enter a number.</span></span>
7. <span data-ttu-id="33ec9-136">Nel campo Volume immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="33ec9-136">In the Volume field, enter a number.</span></span>
8. <span data-ttu-id="33ec9-137">Immettere un numero nel campo Lunghezza.</span><span class="sxs-lookup"><span data-stu-id="33ec9-137">In the Length field, enter a number.</span></span>
9. <span data-ttu-id="33ec9-138">Nel campo Larghezza immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="33ec9-138">In the Width field, enter a number.</span></span>
10. <span data-ttu-id="33ec9-139">Nel campo Altezza immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="33ec9-139">In the Height field, enter a number.</span></span>
11. <span data-ttu-id="33ec9-140">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="33ec9-140">Click Save.</span></span>
12. <span data-ttu-id="33ec9-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="33ec9-141">Close the page.</span></span>

## <a name="set-up-packing-profiles"></a><span data-ttu-id="33ec9-142">Impostare i profili imballaggio</span><span class="sxs-lookup"><span data-stu-id="33ec9-142">Set up packing profiles</span></span>
1. <span data-ttu-id="33ec9-143">Andare a Gestione magazzino > Impostazioni > Imballaggio > Profili imballaggio.</span><span class="sxs-lookup"><span data-stu-id="33ec9-143">Go to Warehouse management > Setup > Packing > Packing profiles.</span></span>
2. <span data-ttu-id="33ec9-144">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="33ec9-144">Click New.</span></span>
3. <span data-ttu-id="33ec9-145">Nel campo ID profilo imballaggio digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-145">In the Packing profile ID field, type a value.</span></span>
4. <span data-ttu-id="33ec9-146">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-146">In the Description field, type a value.</span></span>
5. <span data-ttu-id="33ec9-147">Nel campo ID profilo chiusura contenitore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-147">In the Container closing profile ID field, enter or select a value.</span></span>
    * <span data-ttu-id="33ec9-148">Un ID profilo di chiusura contenitore è facoltativo ed è il profilo contenitore predefinito di chiusura per questo profilo di imballaggio.</span><span class="sxs-lookup"><span data-stu-id="33ec9-148">A container closing profile ID is optional and is the default close container profile for this packing profile.</span></span>  
6. <span data-ttu-id="33ec9-149">Selezionare un'opzione nel campo Modalità ID contenitore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-149">In the Container ID mode field, select an option.</span></span>
    * <span data-ttu-id="33ec9-150">Questa opzione determina se un ID contenitore verrà generato automaticamente quando verrà creato un contenitore o se un ID contenitore verrà creato manualmente.</span><span class="sxs-lookup"><span data-stu-id="33ec9-150">This option determines whether a container ID will be automatically generated when a container is created or if a container ID will be created manually.</span></span>  
7. <span data-ttu-id="33ec9-151">Nel campo Tipo di contenitore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-151">In the Container type field, enter or select a value.</span></span>
    * <span data-ttu-id="33ec9-152">Il tipo di contenitore verrà utilizzato per impostazione predefinita quando verrà creato un nuovo contenitore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-152">The container type will be used by default when a new container is created.</span></span>  
8. <span data-ttu-id="33ec9-153">Selezionare la casella di controllo Crea automaticamente il contenitore alla chiusura.</span><span class="sxs-lookup"><span data-stu-id="33ec9-153">Select the Autocreate container at container close check box.</span></span>
9. <span data-ttu-id="33ec9-154">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="33ec9-154">Click Save.</span></span>
10. <span data-ttu-id="33ec9-155">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="33ec9-155">Close the page.</span></span>

## <a name="set-up-container-closing-profiles"></a><span data-ttu-id="33ec9-156">Impostare i profili chiusura contenitore</span><span class="sxs-lookup"><span data-stu-id="33ec9-156">Set up container closing profiles</span></span>
1. <span data-ttu-id="33ec9-157">Andare a Gestione magazzino > Impostazioni > Contenitori > Profili chiusura contenitore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-157">Go to Warehouse management > Setup > Containers > Container closing profiles.</span></span>
    * <span data-ttu-id="33ec9-158">I profili di chiusura contenitore definiscono l'azione da eseguire quando viene chiuso un contenitore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-158">Container closing profiles define what happens when a container is closed.</span></span> <span data-ttu-id="33ec9-159">È possibile impostare più profili contenitore chiuso.</span><span class="sxs-lookup"><span data-stu-id="33ec9-159">You can set up multiple close container profiles.</span></span>       
2. <span data-ttu-id="33ec9-160">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="33ec9-160">Click New.</span></span>
3. <span data-ttu-id="33ec9-161">Nel campo ID profilo chiusura contenitore digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-161">In the Container closing profile ID field, type a value.</span></span>
4. <span data-ttu-id="33ec9-162">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-162">In the Description field, type a value.</span></span>
5. <span data-ttu-id="33ec9-163">Selezionare un'opzione nel campo Manifesto alle.</span><span class="sxs-lookup"><span data-stu-id="33ec9-163">In the Manifest at field, select an option.</span></span>
    * <span data-ttu-id="33ec9-164">Specificare se l'esecuzione del manifesto si verificherà quando si chiudono i contenitori o quando si conferma la spedizione.</span><span class="sxs-lookup"><span data-stu-id="33ec9-164">Specify whether manifesting will occur when closing containers or when confirming the shipment.</span></span> <span data-ttu-id="33ec9-165">L'esecuzione del manifesto richiede la gestione del trasporto</span><span class="sxs-lookup"><span data-stu-id="33ec9-165">Note that manifesting requires Transportation management.</span></span> <span data-ttu-id="33ec9-166">e dovrà essere implementata nei motori di trasporto per funzionare.</span><span class="sxs-lookup"><span data-stu-id="33ec9-166">Manifesting must be implemented in the transportation engines in order for it work.</span></span>  
6. <span data-ttu-id="33ec9-167">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-167">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="33ec9-168">Nel campo Ubicazione predefinita per spedizione finale immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-168">In the Default location for final shipment field, enter or select a value.</span></span>
    * <span data-ttu-id="33ec9-169">Questa sarà l'ubicazione in cui i prodotti verranno spostati dopo la chiusura dei contenitori.</span><span class="sxs-lookup"><span data-stu-id="33ec9-169">This will be location to which products will be moved after the containers are closed.</span></span> <span data-ttu-id="33ec9-170">Questa ubicazione deve essere un profilo di ubicazione definito nei parametri di magazzino.</span><span class="sxs-lookup"><span data-stu-id="33ec9-170">This location must have a location profile defined on Warehouse parameters.</span></span>  
8. <span data-ttu-id="33ec9-171">Nel campo Unità peso immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="33ec9-171">In the Weight unit field, enter or select a value.</span></span>
9. <span data-ttu-id="33ec9-172">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="33ec9-172">Click Save.</span></span>


