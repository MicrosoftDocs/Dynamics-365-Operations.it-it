--- 
title: Impostare l'imballaggio manuale (febbraio 2016 e maggio 2016)
description: Il processo di imballaggio consente di convalidare e imballare i prodotti in contenitori.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: b90b4a71e2447e942dbb4a9645ef93064da630d3
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="set-up-manual-packing-february-2016--may-2016"></a><span data-ttu-id="c46bf-103">Impostare l'imballaggio manuale (febbraio 2016 e maggio 2016)</span><span class="sxs-lookup"><span data-stu-id="c46bf-103">Set up manual packing (February 2016 & May 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c46bf-104">Il processo di imballaggio consente di convalidare e imballare i prodotti in contenitori.</span><span class="sxs-lookup"><span data-stu-id="c46bf-104">The packing process allows you to validate and pack products into containers.</span></span> <span data-ttu-id="c46bf-105">In questo processo i magazzinieri prelevano i prodotti dai percorsi di immagazzinamento e li spostano in un centro d'imballaggio in cui le quantità e i tipi di articolo vengono controllati e assegnati ai contenitori appropriati.</span><span class="sxs-lookup"><span data-stu-id="c46bf-105">In this process, warehouse workers pick products from the storage locations and move them to a packing station where they check the item quantities and types, and assign them to appropriate containers.</span></span> <span data-ttu-id="c46bf-106">Quando un contenitore è completamente imballato, è possibile chiuderlo e spostarlo nelle banchine di uscita e i prodotti sono pronti per essere spediti.</span><span class="sxs-lookup"><span data-stu-id="c46bf-106">When a container is fully packed, they can close it and move it to the outbound docks, and the products are ready to ship.</span></span> <span data-ttu-id="c46bf-107">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="c46bf-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="c46bf-108">Questa procedura si riferisce solo alle versioni di febbraio 2016 e maggio 2016 di Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="c46bf-108">This procedure is for the February 2016 & May 2016 versions of Dynamics 365 for Operations only.</span></span>


## <a name="set-up-location-profiles"></a><span data-ttu-id="c46bf-109">Imposta profili ubicazione</span><span class="sxs-lookup"><span data-stu-id="c46bf-109">Set up location profiles</span></span>
1. <span data-ttu-id="c46bf-110">Andare a Gestione magazzino > Impostazioni > Magazzino > Profili ubicazione.</span><span class="sxs-lookup"><span data-stu-id="c46bf-110">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>
2. <span data-ttu-id="c46bf-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="c46bf-111">Click New.</span></span>
    * <span data-ttu-id="c46bf-112">Il profilo di ubicazione viene utilizzato per i centri di imballaggio e contiene le informazioni e le regole di un'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="c46bf-112">The location profile is used for packing stations and contains information and rules for a location.</span></span>  
3. <span data-ttu-id="c46bf-113">Nel campo ID profilo ubicazione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-113">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="c46bf-114">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="c46bf-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="c46bf-115">Nel campo Formato ubicazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-115">In the Location format field, enter or select a value.</span></span>
6. <span data-ttu-id="c46bf-116">Nel campo Tipo di ubicazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-116">In the Location type field, enter or select a value.</span></span>
7. <span data-ttu-id="c46bf-117">Selezionare Sì nel campo Consenti articoli combinati.</span><span class="sxs-lookup"><span data-stu-id="c46bf-117">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="c46bf-118">Selezionare Sì nel campo Consenti stati inventario combinati.</span><span class="sxs-lookup"><span data-stu-id="c46bf-118">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="c46bf-119">Selezionare Sì nel campo Ignora regole per giorni di batch.</span><span class="sxs-lookup"><span data-stu-id="c46bf-119">Select Yes in the Override rules for batch days field.</span></span>
10. <span data-ttu-id="c46bf-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c46bf-120">Close the page.</span></span>

## <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="c46bf-121">Impostare i parametri per Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="c46bf-121">Set up warehouse management parameters</span></span> 
1. <span data-ttu-id="c46bf-122">Andare a Gestione magazzino > Impostazioni > Parametri di gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="c46bf-122">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="c46bf-123">Fare clic sulla scheda Imballaggio.</span><span class="sxs-lookup"><span data-stu-id="c46bf-123">Click the Packing tab.</span></span>
3. <span data-ttu-id="c46bf-124">Nel campo ID profilo per l'ubicazione imballaggio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-124">In the Profile ID for packing location field, enter or select a value.</span></span>
    * <span data-ttu-id="c46bf-125">Selezionare il profilo di ubicazione da utilizzare per l'imballaggio.</span><span class="sxs-lookup"><span data-stu-id="c46bf-125">Select the location profile that you want to use for packing.</span></span>  
4. <span data-ttu-id="c46bf-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c46bf-126">Close the page.</span></span>

## <a name="set-up-container-types"></a><span data-ttu-id="c46bf-127">Impostare i tipi di contenitore</span><span class="sxs-lookup"><span data-stu-id="c46bf-127">Set up container types</span></span>
1. <span data-ttu-id="c46bf-128">Andare a Gestione magazzino > Impostazioni > Contenitori > Tipi di contenitore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-128">Go to Warehouse management > Setup > Containers > Container types.</span></span>
2. <span data-ttu-id="c46bf-129">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="c46bf-129">Click New.</span></span>
    * <span data-ttu-id="c46bf-130">È possibile definire i tipi di contenitori da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="c46bf-130">You can define the types of containers to use.</span></span> <span data-ttu-id="c46bf-131">È possibile specificare le dimensioni fisiche del contenitore, inclusi tara, peso massimo, volume massimo, lunghezza, larghezza e peso.</span><span class="sxs-lookup"><span data-stu-id="c46bf-131">You can specify the physical dimensions of the container, including tare weight, maximum weight, maximum volume, length, width, and weight.</span></span>  <span data-ttu-id="c46bf-132">Gli attributi sono campi personalizzati che consentono di aggiungere dimensioni extra sul tipo di contenitore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-132">The Attributes are customized fields that allow you to add extra dimensions on the container type.</span></span>     
3. <span data-ttu-id="c46bf-133">Nel campo Codice tipo di contenitore immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-133">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="c46bf-134">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-134">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c46bf-135">Immettere un numero nel campo Tara.</span><span class="sxs-lookup"><span data-stu-id="c46bf-135">In the Tare weight field, enter a number.</span></span>
6. <span data-ttu-id="c46bf-136">Nel campo Peso massimo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c46bf-136">In the Maximum weight field, enter a number.</span></span>
7. <span data-ttu-id="c46bf-137">Nel campo Volume immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c46bf-137">In the Volume field, enter a number.</span></span>
8. <span data-ttu-id="c46bf-138">Immettere un numero nel campo Lunghezza.</span><span class="sxs-lookup"><span data-stu-id="c46bf-138">In the Length field, enter a number.</span></span>
9. <span data-ttu-id="c46bf-139">Nel campo Larghezza immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c46bf-139">In the Width field, enter a number.</span></span>
10. <span data-ttu-id="c46bf-140">Nel campo Altezza immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c46bf-140">In the Height field, enter a number.</span></span>
11. <span data-ttu-id="c46bf-141">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c46bf-141">Click Save.</span></span>
12. <span data-ttu-id="c46bf-142">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c46bf-142">Close the page.</span></span>

## <a name="set-up-packing-profiles"></a><span data-ttu-id="c46bf-143">Impostare i profili imballaggio</span><span class="sxs-lookup"><span data-stu-id="c46bf-143">Set up packing profiles</span></span>
1. <span data-ttu-id="c46bf-144">Andare a Gestione magazzino > Impostazioni > Imballaggio > Profili imballaggio.</span><span class="sxs-lookup"><span data-stu-id="c46bf-144">Go to Warehouse management > Setup > Packing > Packing profiles.</span></span>
2. <span data-ttu-id="c46bf-145">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="c46bf-145">Click New.</span></span>
3. <span data-ttu-id="c46bf-146">Nel campo ID profilo imballaggio digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-146">In the Packing profile ID field, type a value.</span></span>
4. <span data-ttu-id="c46bf-147">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-147">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c46bf-148">Nel campo ID profilo chiusura contenitore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-148">In the Container closing profile ID field, enter or select a value.</span></span>
    * <span data-ttu-id="c46bf-149">Un ID profilo di chiusura contenitore è facoltativo ed è il profilo contenitore predefinito di chiusura per questo profilo di imballaggio.</span><span class="sxs-lookup"><span data-stu-id="c46bf-149">A container closing profile ID is optional and is the default close container profile for this packing profile.</span></span>  
6. <span data-ttu-id="c46bf-150">Selezionare un'opzione nel campo Modalità ID contenitore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-150">In the Container ID mode field, select an option.</span></span>
    * <span data-ttu-id="c46bf-151">Questa opzione determina se un ID contenitore verrà generato automaticamente quando verrà creato un contenitore o se un ID contenitore verrà creato manualmente.</span><span class="sxs-lookup"><span data-stu-id="c46bf-151">This option determines whether a container ID will be automatically generated when a container is created or if a container ID will be created manually.</span></span>  
7. <span data-ttu-id="c46bf-152">Nel campo Tipo di contenitore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-152">In the Container type field, enter or select a value.</span></span>
    * <span data-ttu-id="c46bf-153">Il tipo di contenitore verrà utilizzato per impostazione predefinita quando verrà creato un nuovo contenitore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-153">The container type will be used by default when a new container is created.</span></span>  
8. <span data-ttu-id="c46bf-154">Selezionare la casella di controllo Crea automaticamente il contenitore alla chiusura.</span><span class="sxs-lookup"><span data-stu-id="c46bf-154">Select the Autocreate container at container close check box.</span></span>
9. <span data-ttu-id="c46bf-155">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c46bf-155">Click Save.</span></span>
10. <span data-ttu-id="c46bf-156">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c46bf-156">Close the page.</span></span>

## <a name="set-up-container-closing-profiles"></a><span data-ttu-id="c46bf-157">Impostare i profili chiusura contenitore</span><span class="sxs-lookup"><span data-stu-id="c46bf-157">Set up container closing profiles</span></span>
1. <span data-ttu-id="c46bf-158">Andare a Gestione magazzino > Impostazioni > Contenitori > Profili chiusura contenitore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-158">Go to Warehouse management > Setup > Containers > Container closing profiles.</span></span>
    * <span data-ttu-id="c46bf-159">I profili di chiusura contenitore definiscono l'azione da eseguire quando viene chiuso un contenitore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-159">Container closing profiles define what happens when a container is closed.</span></span> <span data-ttu-id="c46bf-160">È possibile impostare più profili contenitore chiuso.</span><span class="sxs-lookup"><span data-stu-id="c46bf-160">You can set up multiple close container profiles.</span></span>       
2. <span data-ttu-id="c46bf-161">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="c46bf-161">Click New.</span></span>
3. <span data-ttu-id="c46bf-162">Nel campo ID profilo chiusura contenitore digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-162">In the Container closing profile ID field, type a value.</span></span>
4. <span data-ttu-id="c46bf-163">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-163">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c46bf-164">Selezionare un'opzione nel campo Manifesto alle.</span><span class="sxs-lookup"><span data-stu-id="c46bf-164">In the Manifest at field, select an option.</span></span>
    * <span data-ttu-id="c46bf-165">Specificare se l'esecuzione del manifesto si verificherà quando si chiudono i contenitori o quando si conferma la spedizione.</span><span class="sxs-lookup"><span data-stu-id="c46bf-165">Specify whether manifesting will occur when closing containers or when confirming the shipment.</span></span> <span data-ttu-id="c46bf-166">L'esecuzione del manifesto richiede la gestione del trasporto</span><span class="sxs-lookup"><span data-stu-id="c46bf-166">Note that manifesting requires Transportation management.</span></span> <span data-ttu-id="c46bf-167">e dovrà essere implementata nei motori di trasporto per funzionare.</span><span class="sxs-lookup"><span data-stu-id="c46bf-167">Manifesting must be implemented in the transportation engines in order for it work.</span></span>  
6. <span data-ttu-id="c46bf-168">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-168">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="c46bf-169">Nel campo Ubicazione predefinita per spedizione finale immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-169">In the Default location for final shipment field, enter or select a value.</span></span>
    * <span data-ttu-id="c46bf-170">Questa sarà l'ubicazione in cui i prodotti verranno spostati dopo la chiusura dei contenitori.</span><span class="sxs-lookup"><span data-stu-id="c46bf-170">This will be location to which products will be moved after the containers are closed.</span></span> <span data-ttu-id="c46bf-171">Questa ubicazione deve essere un profilo di ubicazione definito nei parametri di magazzino.</span><span class="sxs-lookup"><span data-stu-id="c46bf-171">This location must have a location profile defined on Warehouse parameters.</span></span>  
8. <span data-ttu-id="c46bf-172">Nel campo Unità peso immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c46bf-172">In the Weight unit field, enter or select a value.</span></span>
9. <span data-ttu-id="c46bf-173">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c46bf-173">Click Save.</span></span>


