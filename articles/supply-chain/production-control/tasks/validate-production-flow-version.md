--- 
title: Convalidare un flusso e una versione di produzione
description: Questa procedura mostra come creare un nuovo flusso di produzione e una prima versione per il lean manufacturing.
author: ChristianRytt
manager: AnnBe
ms.date: 02/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 9087b0865dd7d22bcb9040631207f4fef2c82c06
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---
# <a name="validate-a-production-flow-and-version"></a><span data-ttu-id="ee96a-103">Convalidare un flusso e una versione di produzione</span><span class="sxs-lookup"><span data-stu-id="ee96a-103">Validate a production flow and version</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ee96a-104">Questa procedura mostra come creare un nuovo flusso di produzione e una prima versione per il lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="ee96a-104">This procedure shows how to create a new production flow and a first version for lean manufacturing.</span></span> <span data-ttu-id="ee96a-105">Prerequisiti: i parametri di produzione di lean manufacturing e le unità di misura della classe Time devono essere definiti.</span><span class="sxs-lookup"><span data-stu-id="ee96a-105">Prerequisites: The production parameters for Lean manufacturing and the units of measure for class time must be defined.</span></span> <span data-ttu-id="ee96a-106">È necessario definire un flusso del valore e un gruppo di produzione.</span><span class="sxs-lookup"><span data-stu-id="ee96a-106">You need to define a Value stream and a Production group.</span></span> <span data-ttu-id="ee96a-107">Fare riferimento ai white paper sul lean manufacturing per familiarizzare con i concetti di flussi di produzione e attività.</span><span class="sxs-lookup"><span data-stu-id="ee96a-107">Refer to the white papers on Lean manufacturing to familiarize yourself with the concepts of production flows and activities.</span></span> <span data-ttu-id="ee96a-108">Questa procedura si riferisce alla persona giuridica USMF in dati dimostrativi.</span><span class="sxs-lookup"><span data-stu-id="ee96a-108">This procedure refers to the legal entity USMF in demo data.</span></span> <span data-ttu-id="ee96a-109">Tuttavia, presupponendo che la persona giuridica sia configurata per il lean manufacturing, altre persone giuridiche possono essere utilizzate.</span><span class="sxs-lookup"><span data-stu-id="ee96a-109">However, assuming that the legal entity is configured for Lean manufacturing, other legal entities can be used.</span></span>


## <a name="create-a-production-flow"></a><span data-ttu-id="ee96a-110">Creare un flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="ee96a-110">Create a production flow</span></span>
1. <span data-ttu-id="ee96a-111">Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.</span><span class="sxs-lookup"><span data-stu-id="ee96a-111">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="ee96a-112">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ee96a-112">Click New.</span></span>
3. <span data-ttu-id="ee96a-113">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="ee96a-113">In the Name field, type a value.</span></span>
4. <span data-ttu-id="ee96a-114">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee96a-114">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ee96a-115">Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee96a-115">In the Name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="ee96a-116">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee96a-116">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ee96a-117">Un flusso del valore è un'unità operativa che comprende tutte le attività e i flussi del flusso del valore.</span><span class="sxs-lookup"><span data-stu-id="ee96a-117">A value stream is an operating unit that spans over all activities and flows of the value stream.</span></span>   <span data-ttu-id="ee96a-118">In questa fase, le unità operative sono limitate a una persona giuridica e non hanno ulteriori funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ee96a-118">At this stage, operating units are limited to a legal entity and have no further functionality.</span></span>  
7. <span data-ttu-id="ee96a-119">Nel campo Gruppo di produzioni fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee96a-119">In the Production group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="ee96a-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee96a-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ee96a-121">I gruppi di produzione consentono la definizione dei conti materiale, manodopera e WIP per un processo di produzione.</span><span class="sxs-lookup"><span data-stu-id="ee96a-121">Production groups allow the definition of material, labor, and WIP accounts for a production process.</span></span> <span data-ttu-id="ee96a-122">Per associare il contesto di contabilità a un flusso di produzione, un gruppo di produzione deve essere selezionato.</span><span class="sxs-lookup"><span data-stu-id="ee96a-122">To associate the accounting context to a production flow, a production group must be selected.</span></span>  
9. <span data-ttu-id="ee96a-123">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ee96a-123">Click Save.</span></span>

## <a name="create-a-production-flow-version"></a><span data-ttu-id="ee96a-124">Creare una nuova versione del flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="ee96a-124">Create a production flow version</span></span>
1. <span data-ttu-id="ee96a-125">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="ee96a-125">Click Add.</span></span>
2. <span data-ttu-id="ee96a-126">Nel campo Data di scadenza immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="ee96a-126">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="ee96a-127">È possibile aggiornare la data di scadenza della versione in ogni dato momento, anche per le versioni attive.</span><span class="sxs-lookup"><span data-stu-id="ee96a-127">You can update the Expiration date of the version at any given time, even for active versions.</span></span> <span data-ttu-id="ee96a-128">Utilizzare la scadenza della versione per pianificare l'eliminazione di una versione.</span><span class="sxs-lookup"><span data-stu-id="ee96a-128">Use the expiration of the version to plan for a phase out of a version.</span></span>  
3. <span data-ttu-id="ee96a-129">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ee96a-129">Click OK.</span></span>
4. <span data-ttu-id="ee96a-130">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ee96a-130">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="ee96a-131">Digitare un valore nel campo Unità.</span><span class="sxs-lookup"><span data-stu-id="ee96a-131">In the Unit field, type a value.</span></span>
6. <span data-ttu-id="ee96a-132">Selezionare l'unità del tempo di produzione di un'unità.</span><span class="sxs-lookup"><span data-stu-id="ee96a-132">Select the Takt unit.</span></span>
7. <span data-ttu-id="ee96a-133">Nel campo Tempo di produzione di un'unità medio immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ee96a-133">In the Average takt time field, enter a number.</span></span>
    * <span data-ttu-id="ee96a-134">Per il controllo della produzione di un'unità della versione del flusso di produzione, definire un tempo medio di destinazione per la produzione di un'unità.</span><span class="sxs-lookup"><span data-stu-id="ee96a-134">For the takt control of the production flow version, define a targeted average takt time.</span></span>   <span data-ttu-id="ee96a-135">La produzione di un'unità viene definita come quantità per periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="ee96a-135">The takt is defined as quantity  per time period.</span></span>  <span data-ttu-id="ee96a-136">Nell'esempio dato, il tempo di produzione di un'unità è di 0,2 ore per 10 pezzi.</span><span class="sxs-lookup"><span data-stu-id="ee96a-136">In the given example, the takt time is 0.2 hours per 10 pieces.</span></span> <span data-ttu-id="ee96a-137">Per un orario di lavoro di 8 ore, corrisponde a una capacità di produttività giornaliera di 400 pezzi.</span><span class="sxs-lookup"><span data-stu-id="ee96a-137">For a working time of 8 hours, this corresponds to a daily throughput capacity of 400 pieces.</span></span>  
8. <span data-ttu-id="ee96a-138">Nel campo Quantità per ciclo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ee96a-138">In the Quantity per cycle field, enter a number.</span></span>
9. <span data-ttu-id="ee96a-139">Espandere o comprimere la sezione Dettagli versione.</span><span class="sxs-lookup"><span data-stu-id="ee96a-139">Expand or collapse the Version details section.</span></span>
10. <span data-ttu-id="ee96a-140">Nel campo Tempo di produzione di un'unità minimo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ee96a-140">In the Minimum takt time field, enter a number.</span></span>
    * <span data-ttu-id="ee96a-141">Il tempo minimo di produzione di un'unità deve essere minore o uguale al tempo medio di produzione di un'unità.</span><span class="sxs-lookup"><span data-stu-id="ee96a-141">The minimum takt time must be less than or equal to the average takt time.</span></span>  
11. <span data-ttu-id="ee96a-142">Nel campo Tempo di produzione di un'unità massimo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ee96a-142">In the Maximum takt time field, enter a number.</span></span>
    * <span data-ttu-id="ee96a-143">Il tempo massimo di produzione di un'unità deve essere maggiore o uguale al tempo medio di produzione di un'unità.</span><span class="sxs-lookup"><span data-stu-id="ee96a-143">The maximum takt time must be higher than or equal to the Average takt time.</span></span>  
12. <span data-ttu-id="ee96a-144">Immettere il numero di giorni nel periodo per la durata ciclo effettiva.</span><span class="sxs-lookup"><span data-stu-id="ee96a-144">Enter a number of days in the Period for actual cycle time</span></span>
    * <span data-ttu-id="ee96a-145">Il periodo di durata ciclo effettiva è il numero di giorni che i processi verranno aggregati dal minuto effettivo a ritroso per calcolare la durata ciclo effettiva.</span><span class="sxs-lookup"><span data-stu-id="ee96a-145">The period for actual cycle time is the number of days that jobs are aggregated from the actual minute backwards to calculate the actual cycle time.</span></span> <span data-ttu-id="ee96a-146">Il valore può essere modificato in qualsiasi momento ed è solo utilizzato per il calcolo delle durate ciclo effettive.</span><span class="sxs-lookup"><span data-stu-id="ee96a-146">The value can be changed at any time and is only used for the calculation of the actual cycle times.</span></span>  
13. <span data-ttu-id="ee96a-147">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ee96a-147">Click Save.</span></span>


