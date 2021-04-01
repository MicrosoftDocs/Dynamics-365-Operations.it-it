---
title: Creare una nuova versione del flusso di produzione
description: Questa procedura è incentrata sulla creazione di una nuova versione del flusso di produzione.
author: cvocph
manager: tfehr
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b57dbd2516a25b414193ca76367bd8d5c4a1b298
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255063"
---
# <a name="create-a-production-flow-version"></a><span data-ttu-id="b5f41-103">Creare una nuova versione del flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="b5f41-103">Create a production flow version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b5f41-104">Questa procedura è incentrata sulla creazione di una nuova versione del flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="b5f41-104">This procedure focuses on creating a new production flow version.</span></span> <span data-ttu-id="b5f41-105">Per questa procedura, i parametri di produzione di lean manufacturing e le unità di misura della classe Time devono essere definiti.</span><span class="sxs-lookup"><span data-stu-id="b5f41-105">For this procedure, the production parameters for lean manufacturing and the units of measurement for class time must be defined.</span></span> <span data-ttu-id="b5f41-106">È inoltre necessario definire un flusso del valore e un gruppo di produzione.</span><span class="sxs-lookup"><span data-stu-id="b5f41-106">You also need to define a value stream and a production group.</span></span> <span data-ttu-id="b5f41-107">Per ulteriori informazioni sui flussi e attività di produzione nel lean manufacturing, vedere i white paper sul lean manufacturing per Microsoft Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="b5f41-107">To learn more about production flows and activities in lean manufacturing, see the white papers on Lean manufacturing for Microsoft Dynamics AX.</span></span> <span data-ttu-id="b5f41-108">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="b5f41-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-production-flow"></a><span data-ttu-id="b5f41-109">Creare un flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="b5f41-109">Create a production flow</span></span>
1. <span data-ttu-id="b5f41-110">Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.</span><span class="sxs-lookup"><span data-stu-id="b5f41-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="b5f41-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b5f41-111">Click New.</span></span>
3. <span data-ttu-id="b5f41-112">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="b5f41-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="b5f41-113">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="b5f41-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="b5f41-114">Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="b5f41-114">In the Name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="b5f41-115">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b5f41-115">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b5f41-116">Selezionare un'unità operativa del flusso del valore di tipo.</span><span class="sxs-lookup"><span data-stu-id="b5f41-116">Select an operating unit of type value stream.</span></span> <span data-ttu-id="b5f41-117">Un flusso del valore è un'unità operativa che comprende tutte le attività e i flussi del flusso del valore.</span><span class="sxs-lookup"><span data-stu-id="b5f41-117">A value stream is an operating unit that spans all activities and flows of the value stream.</span></span> <span data-ttu-id="b5f41-118">In questa fase, le unità operative sono limitate a una persona giuridica e non hanno ulteriori funzionalità.</span><span class="sxs-lookup"><span data-stu-id="b5f41-118">At this stage, operating units are limited to a legal entity and have no further functionality.</span></span>  
7. <span data-ttu-id="b5f41-119">Nel campo Gruppo di produzioni fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="b5f41-119">In the Production group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="b5f41-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b5f41-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b5f41-121">Selezionare un gruppo di produzione per il flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="b5f41-121">Select a production group for the production flow.</span></span> <span data-ttu-id="b5f41-122">I gruppi di produzione consentono la definizione dei conti materiale, manodopera e WIP per un processo di produzione.</span><span class="sxs-lookup"><span data-stu-id="b5f41-122">Production groups allow the definition of material, labor, and WIP accounts for a production process.</span></span> <span data-ttu-id="b5f41-123">Per associare il contesto di contabilità a un flusso di produzione, un gruppo di produzione deve essere selezionato.</span><span class="sxs-lookup"><span data-stu-id="b5f41-123">To associate the accounting context to a production flow, a production group must be selected.</span></span>  
9. <span data-ttu-id="b5f41-124">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="b5f41-124">Click Save.</span></span>

## <a name="create-a-production-flow-version"></a><span data-ttu-id="b5f41-125">Creare una nuova versione del flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="b5f41-125">Create a production flow version</span></span>
1. <span data-ttu-id="b5f41-126">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="b5f41-126">Click Add.</span></span>
2. <span data-ttu-id="b5f41-127">Nel campo Data di scadenza immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="b5f41-127">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="b5f41-128">Se necessario, definire una data di scadenza della versione.</span><span class="sxs-lookup"><span data-stu-id="b5f41-128">If required, define an Expiration date for the version.</span></span> <span data-ttu-id="b5f41-129">È possibile aggiornarla in ogni dato momento, anche per le versioni attive.</span><span class="sxs-lookup"><span data-stu-id="b5f41-129">You can update it at any given time, even for active versions.</span></span> <span data-ttu-id="b5f41-130">È possibile utilizzarla per pianificare di eliminare una versione.</span><span class="sxs-lookup"><span data-stu-id="b5f41-130">You can use it to plan to phase out a version.</span></span>  
3. <span data-ttu-id="b5f41-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b5f41-131">Click OK.</span></span>
4. <span data-ttu-id="b5f41-132">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b5f41-132">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="b5f41-133">Digitare un valore nel campo Unità.</span><span class="sxs-lookup"><span data-stu-id="b5f41-133">In the Unit field, type a value.</span></span>
6. <span data-ttu-id="b5f41-134">ResolveChanges per l'unità di tempo di produzione di un'unità.</span><span class="sxs-lookup"><span data-stu-id="b5f41-134">ResolveChanges the Takt unit.</span></span>
7. <span data-ttu-id="b5f41-135">Nel campo Tempo di produzione di un'unità medio immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="b5f41-135">In the Average takt time field, enter a number.</span></span>
    * <span data-ttu-id="b5f41-136">Definire il tempo medio di produzione di un'unità della versione.</span><span class="sxs-lookup"><span data-stu-id="b5f41-136">Define the Average takt time of the version.</span></span> <span data-ttu-id="b5f41-137">Per il controllo della produzione di un'unità della versione del flusso di produzione, definire un tempo medio di destinazione per la produzione di un'unità.</span><span class="sxs-lookup"><span data-stu-id="b5f41-137">For the takt control of the production flow version, define a targeted average takt time.</span></span> <span data-ttu-id="b5f41-138">La produzione di un'unità viene definita come quantità per periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="b5f41-138">The takt is defined as quantity per time period.</span></span> <span data-ttu-id="b5f41-139">Nell'esempio, il tempo di produzione di un'unità è di 0,2 ore per 10 pezzi.</span><span class="sxs-lookup"><span data-stu-id="b5f41-139">In the example, the takt time is 0.2 hours per 10 pieces.</span></span> <span data-ttu-id="b5f41-140">Per un orario di lavoro di 8 ore, corrisponde a una capacità di produttività giornaliera di 400 pezzi.</span><span class="sxs-lookup"><span data-stu-id="b5f41-140">For a working time of 8 hours, this corresponds to a daily throughput capacity of 400 pieces.</span></span>  
8. <span data-ttu-id="b5f41-141">Nel campo Quantità per ciclo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="b5f41-141">In the Quantity per cycle field, enter a number.</span></span>
    * <span data-ttu-id="b5f41-142">Definire la quantità per ciclo correlata al tempo medio di produzione di un'unità.</span><span class="sxs-lookup"><span data-stu-id="b5f41-142">Define the quantity per cycle related to the Average takt time.</span></span>  
9. <span data-ttu-id="b5f41-143">Attivare/disattivare l'espansione della sezione Dettagli versione.</span><span class="sxs-lookup"><span data-stu-id="b5f41-143">Toggle the expansion of the Version details section.</span></span>
10. <span data-ttu-id="b5f41-144">Nel campo Tempo di produzione di un'unità minimo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="b5f41-144">In the Minimum takt time field, enter a number.</span></span>
    * <span data-ttu-id="b5f41-145">Definire il tempo minimo di produzione di un'unità.</span><span class="sxs-lookup"><span data-stu-id="b5f41-145">Define the minimum takt time.</span></span> <span data-ttu-id="b5f41-146">Il tempo minimo di produzione di un'unità deve essere minore o uguale al tempo medio di produzione di un'unità.</span><span class="sxs-lookup"><span data-stu-id="b5f41-146">The minimum takt time must be less than or equal to the average takt time.</span></span>  
11. <span data-ttu-id="b5f41-147">Nel campo Tempo di produzione di un'unità massimo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="b5f41-147">In the Maximum takt time field, enter a number.</span></span>
    * <span data-ttu-id="b5f41-148">Il tempo massimo di produzione di un'unità deve essere maggiore o uguale al tempo medio di produzione di un'unità.</span><span class="sxs-lookup"><span data-stu-id="b5f41-148">The maximum takt time must be higher than or equal to the Average takt time.</span></span>  
12. <span data-ttu-id="b5f41-149">Nel campo Periodo per durata ciclo effettiva (giorni) immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="b5f41-149">In the Period for actual cycle time (days) field, enter a number.</span></span>
    * <span data-ttu-id="b5f41-150">Immettere il numero di giorni nel periodo per la durata ciclo effettiva.</span><span class="sxs-lookup"><span data-stu-id="b5f41-150">Enter the number of days in the Period for actual cycle time.</span></span> <span data-ttu-id="b5f41-151">Il periodo di durata ciclo effettiva è il numero di giorni che i processi verranno aggregati dal minuto effettivo a ritroso per calcolare la durata ciclo effettiva.</span><span class="sxs-lookup"><span data-stu-id="b5f41-151">The period for actual cycle time is the number of days that jobs are aggregated from the actual minute backwards to calculate the actual cycle time.</span></span> <span data-ttu-id="b5f41-152">Il valore può essere modificato in qualsiasi momento ed è solo utilizzato per il calcolo delle durate ciclo effettive.</span><span class="sxs-lookup"><span data-stu-id="b5f41-152">The value can be changed at any time and is only used for the calculation of the actual cycle times.</span></span>  
13. <span data-ttu-id="b5f41-153">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="b5f41-153">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]