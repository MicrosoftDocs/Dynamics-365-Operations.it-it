---
title: Impostare l'imballaggio manuale (febbraio 2016 e maggio 2016)
description: Il processo di imballaggio consente di convalidare e imballare i prodotti in contenitori.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2843c42474fcd4afbbc2cd7753c0d06cfe467dbe
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810368"
---
# <a name="set-up-manual-packing-february-2016--may-2016"></a><span data-ttu-id="81c06-103">Impostare l'imballaggio manuale (febbraio 2016 e maggio 2016)</span><span class="sxs-lookup"><span data-stu-id="81c06-103">Set up manual packing (February 2016 & May 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="81c06-104">Il processo di imballaggio consente di convalidare e imballare i prodotti in contenitori.</span><span class="sxs-lookup"><span data-stu-id="81c06-104">The packing process allows you to validate and pack products into containers.</span></span> <span data-ttu-id="81c06-105">In questo processo i magazzinieri prelevano i prodotti dai percorsi di immagazzinamento e li spostano in un centro d'imballaggio in cui le quantità e i tipi di articolo vengono controllati e assegnati ai contenitori appropriati.</span><span class="sxs-lookup"><span data-stu-id="81c06-105">In this process, warehouse workers pick products from the storage locations and move them to a packing station where they check the item quantities and types, and assign them to appropriate containers.</span></span> <span data-ttu-id="81c06-106">Quando un contenitore è completamente imballato, è possibile chiuderlo e spostarlo nelle banchine di uscita e i prodotti sono pronti per essere spediti.</span><span class="sxs-lookup"><span data-stu-id="81c06-106">When a container is fully packed, they can close it and move it to the outbound docks, and the products are ready to ship.</span></span> <span data-ttu-id="81c06-107">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="81c06-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="81c06-108">Questa procedura si riferisce solo alle versioni di febbraio 2016 e maggio 2016 di Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="81c06-108">This procedure is for the February 2016 & May 2016 versions of Dynamics 365 for Operations only.</span></span>


## <a name="set-up-location-profiles"></a><span data-ttu-id="81c06-109">Imposta profili ubicazione</span><span class="sxs-lookup"><span data-stu-id="81c06-109">Set up location profiles</span></span>
1. <span data-ttu-id="81c06-110">Andare a Gestione magazzino > Impostazioni > Magazzino > Profili ubicazione.</span><span class="sxs-lookup"><span data-stu-id="81c06-110">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>
2. <span data-ttu-id="81c06-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="81c06-111">Click New.</span></span>
    * <span data-ttu-id="81c06-112">Il profilo di ubicazione viene utilizzato per i centri di imballaggio e contiene le informazioni e le regole di un'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="81c06-112">The location profile is used for packing stations and contains information and rules for a location.</span></span>  
3. <span data-ttu-id="81c06-113">Nel campo ID profilo ubicazione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="81c06-113">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="81c06-114">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="81c06-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="81c06-115">Nel campo Formato ubicazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="81c06-115">In the Location format field, enter or select a value.</span></span>
6. <span data-ttu-id="81c06-116">Nel campo Tipo di ubicazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="81c06-116">In the Location type field, enter or select a value.</span></span>
7. <span data-ttu-id="81c06-117">Selezionare Sì nel campo Consenti articoli combinati.</span><span class="sxs-lookup"><span data-stu-id="81c06-117">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="81c06-118">Selezionare Sì nel campo Consenti stati inventario combinati.</span><span class="sxs-lookup"><span data-stu-id="81c06-118">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="81c06-119">Selezionare Sì nel campo Ignora regole per giorni di batch.</span><span class="sxs-lookup"><span data-stu-id="81c06-119">Select Yes in the Override rules for batch days field.</span></span>
10. <span data-ttu-id="81c06-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="81c06-120">Close the page.</span></span>

## <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="81c06-121">Impostare i parametri per Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="81c06-121">Set up warehouse management parameters</span></span> 
1. <span data-ttu-id="81c06-122">Andare a Gestione magazzino > Impostazioni > Parametri di gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="81c06-122">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="81c06-123">Fare clic sulla scheda Imballaggio.</span><span class="sxs-lookup"><span data-stu-id="81c06-123">Click the Packing tab.</span></span>
3. <span data-ttu-id="81c06-124">Nel campo ID profilo per l'ubicazione imballaggio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="81c06-124">In the Profile ID for packing location field, enter or select a value.</span></span>
    * <span data-ttu-id="81c06-125">Selezionare il profilo di ubicazione da utilizzare per l'imballaggio.</span><span class="sxs-lookup"><span data-stu-id="81c06-125">Select the location profile that you want to use for packing.</span></span>  
4. <span data-ttu-id="81c06-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="81c06-126">Close the page.</span></span>

## <a name="set-up-container-types"></a><span data-ttu-id="81c06-127">Impostare i tipi di contenitore</span><span class="sxs-lookup"><span data-stu-id="81c06-127">Set up container types</span></span>
1. <span data-ttu-id="81c06-128">Andare a Gestione magazzino > Impostazioni > Contenitori > Tipi di contenitore.</span><span class="sxs-lookup"><span data-stu-id="81c06-128">Go to Warehouse management > Setup > Containers > Container types.</span></span>
2. <span data-ttu-id="81c06-129">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="81c06-129">Click New.</span></span>
    * <span data-ttu-id="81c06-130">È possibile definire i tipi di contenitori da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="81c06-130">You can define the types of containers to use.</span></span> <span data-ttu-id="81c06-131">È possibile specificare le dimensioni fisiche del contenitore, inclusi tara, peso massimo, volume massimo, lunghezza, larghezza e peso.</span><span class="sxs-lookup"><span data-stu-id="81c06-131">You can specify the physical dimensions of the container, including tare weight, maximum weight, maximum volume, length, width, and weight.</span></span>  <span data-ttu-id="81c06-132">Gli attributi sono campi personalizzati che consentono di aggiungere dimensioni extra sul tipo di contenitore.</span><span class="sxs-lookup"><span data-stu-id="81c06-132">The Attributes are customized fields that allow you to add extra dimensions on the container type.</span></span>     
3. <span data-ttu-id="81c06-133">Nel campo Codice tipo di contenitore immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="81c06-133">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="81c06-134">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="81c06-134">In the Description field, type a value.</span></span>
5. <span data-ttu-id="81c06-135">Immettere un numero nel campo Tara.</span><span class="sxs-lookup"><span data-stu-id="81c06-135">In the Tare weight field, enter a number.</span></span>
6. <span data-ttu-id="81c06-136">Nel campo Peso massimo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="81c06-136">In the Maximum weight field, enter a number.</span></span>
7. <span data-ttu-id="81c06-137">Nel campo Volume immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="81c06-137">In the Volume field, enter a number.</span></span>
8. <span data-ttu-id="81c06-138">Immettere un numero nel campo Lunghezza.</span><span class="sxs-lookup"><span data-stu-id="81c06-138">In the Length field, enter a number.</span></span>
9. <span data-ttu-id="81c06-139">Nel campo Larghezza immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="81c06-139">In the Width field, enter a number.</span></span>
10. <span data-ttu-id="81c06-140">Nel campo Altezza immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="81c06-140">In the Height field, enter a number.</span></span>
11. <span data-ttu-id="81c06-141">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="81c06-141">Click Save.</span></span>
12. <span data-ttu-id="81c06-142">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="81c06-142">Close the page.</span></span>

## <a name="set-up-packing-profiles"></a><span data-ttu-id="81c06-143">Impostare i profili imballaggio</span><span class="sxs-lookup"><span data-stu-id="81c06-143">Set up packing profiles</span></span>
1. <span data-ttu-id="81c06-144">Andare a Gestione magazzino > Impostazioni > Imballaggio > Profili imballaggio.</span><span class="sxs-lookup"><span data-stu-id="81c06-144">Go to Warehouse management > Setup > Packing > Packing profiles.</span></span>
2. <span data-ttu-id="81c06-145">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="81c06-145">Click New.</span></span>
3. <span data-ttu-id="81c06-146">Nel campo ID profilo imballaggio digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="81c06-146">In the Packing profile ID field, type a value.</span></span>
4. <span data-ttu-id="81c06-147">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="81c06-147">In the Description field, type a value.</span></span>
5. <span data-ttu-id="81c06-148">Nel campo ID profilo chiusura contenitore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="81c06-148">In the Container closing profile ID field, enter or select a value.</span></span>
    * <span data-ttu-id="81c06-149">Un ID profilo di chiusura contenitore è facoltativo ed è il profilo contenitore predefinito di chiusura per questo profilo di imballaggio.</span><span class="sxs-lookup"><span data-stu-id="81c06-149">A container closing profile ID is optional and is the default close container profile for this packing profile.</span></span>  
6. <span data-ttu-id="81c06-150">Selezionare un'opzione nel campo Modalità ID contenitore.</span><span class="sxs-lookup"><span data-stu-id="81c06-150">In the Container ID mode field, select an option.</span></span>
    * <span data-ttu-id="81c06-151">Questa opzione determina se un ID contenitore verrà generato automaticamente quando verrà creato un contenitore o se un ID contenitore verrà creato manualmente.</span><span class="sxs-lookup"><span data-stu-id="81c06-151">This option determines whether a container ID will be automatically generated when a container is created or if a container ID will be created manually.</span></span>  
7. <span data-ttu-id="81c06-152">Nel campo Tipo di contenitore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="81c06-152">In the Container type field, enter or select a value.</span></span>
    * <span data-ttu-id="81c06-153">Il tipo di contenitore verrà utilizzato per impostazione predefinita quando verrà creato un nuovo contenitore.</span><span class="sxs-lookup"><span data-stu-id="81c06-153">The container type will be used by default when a new container is created.</span></span>  
8. <span data-ttu-id="81c06-154">Selezionare la casella di controllo Crea automaticamente il contenitore alla chiusura.</span><span class="sxs-lookup"><span data-stu-id="81c06-154">Select the Autocreate container at container close check box.</span></span>
9. <span data-ttu-id="81c06-155">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="81c06-155">Click Save.</span></span>
10. <span data-ttu-id="81c06-156">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="81c06-156">Close the page.</span></span>

## <a name="set-up-container-closing-profiles"></a><span data-ttu-id="81c06-157">Impostare i profili chiusura contenitore</span><span class="sxs-lookup"><span data-stu-id="81c06-157">Set up container closing profiles</span></span>
1. <span data-ttu-id="81c06-158">Andare a Gestione magazzino > Impostazioni > Contenitori > Profili chiusura contenitore.</span><span class="sxs-lookup"><span data-stu-id="81c06-158">Go to Warehouse management > Setup > Containers > Container closing profiles.</span></span>
    * <span data-ttu-id="81c06-159">I profili di chiusura contenitore definiscono l'azione da eseguire quando viene chiuso un contenitore.</span><span class="sxs-lookup"><span data-stu-id="81c06-159">Container closing profiles define what happens when a container is closed.</span></span> <span data-ttu-id="81c06-160">È possibile impostare più profili contenitore chiuso.</span><span class="sxs-lookup"><span data-stu-id="81c06-160">You can set up multiple close container profiles.</span></span>       
2. <span data-ttu-id="81c06-161">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="81c06-161">Click New.</span></span>
3. <span data-ttu-id="81c06-162">Nel campo ID profilo chiusura contenitore digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="81c06-162">In the Container closing profile ID field, type a value.</span></span>
4. <span data-ttu-id="81c06-163">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="81c06-163">In the Description field, type a value.</span></span>
5. <span data-ttu-id="81c06-164">Selezionare un'opzione nel campo Manifesto alle.</span><span class="sxs-lookup"><span data-stu-id="81c06-164">In the Manifest at field, select an option.</span></span>
    * <span data-ttu-id="81c06-165">Specificare se l'esecuzione del manifesto si verificherà quando si chiudono i contenitori o quando si conferma la spedizione.</span><span class="sxs-lookup"><span data-stu-id="81c06-165">Specify whether manifesting will occur when closing containers or when confirming the shipment.</span></span> <span data-ttu-id="81c06-166">L'esecuzione del manifesto richiede la gestione del trasporto</span><span class="sxs-lookup"><span data-stu-id="81c06-166">Note that manifesting requires Transportation management.</span></span> <span data-ttu-id="81c06-167">e dovrà essere implementata nei motori di trasporto per funzionare.</span><span class="sxs-lookup"><span data-stu-id="81c06-167">Manifesting must be implemented in the transportation engines in order for it work.</span></span>  
6. <span data-ttu-id="81c06-168">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="81c06-168">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="81c06-169">Nel campo Ubicazione predefinita per spedizione finale immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="81c06-169">In the Default location for final shipment field, enter or select a value.</span></span>
    * <span data-ttu-id="81c06-170">Questa sarà l'ubicazione in cui i prodotti verranno spostati dopo la chiusura dei contenitori.</span><span class="sxs-lookup"><span data-stu-id="81c06-170">This will be location to which products will be moved after the containers are closed.</span></span> <span data-ttu-id="81c06-171">Questa ubicazione deve essere un profilo di ubicazione definito nei parametri di magazzino.</span><span class="sxs-lookup"><span data-stu-id="81c06-171">This location must have a location profile defined on Warehouse parameters.</span></span>  
8. <span data-ttu-id="81c06-172">Nel campo Unità peso immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="81c06-172">In the Weight unit field, enter or select a value.</span></span>
9. <span data-ttu-id="81c06-173">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="81c06-173">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]