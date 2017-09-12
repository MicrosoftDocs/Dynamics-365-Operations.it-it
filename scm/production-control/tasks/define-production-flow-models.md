--- 
title: Definire i modelli di flusso di produzione
description: "I modelli di flusso di produzione descrivono come la capacità delle celle di lavoro di produzione snella viene calcolata e gestita."
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7850a121ca06f25f6c532e49e18c0b6811bd7455
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="define-production-flow-models"></a><span data-ttu-id="e58b8-103">Definire i modelli di flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="e58b8-103">Define production flow models</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e58b8-104">I modelli di flusso di produzione descrivono come la capacità delle celle di lavoro di produzione snella viene calcolata e gestita.</span><span class="sxs-lookup"><span data-stu-id="e58b8-104">Production flow models describe how the capacity of lean manufacturing work cells is calculated and maintained.</span></span> <span data-ttu-id="e58b8-105">Pertanto la definizione di un modello di flusso di produzione è un prerequisito della definizione delle celle di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e58b8-105">Therefore the definition of a production flow model is a prerequisite of the definition of work cells.</span></span> <span data-ttu-id="e58b8-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="e58b8-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="define-a-production-flow-model"></a><span data-ttu-id="e58b8-107">Definire un modello di flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="e58b8-107">Define a production flow model.</span></span> 
1. <span data-ttu-id="e58b8-108">Passare a Controllo produzione > Impostazione > Flusso di produzione snella > Modelli di flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="e58b8-108">Go to Production control > Setup > Lean production flow > Production flow models.</span></span>
2. <span data-ttu-id="e58b8-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e58b8-109">Click New.</span></span>
3. <span data-ttu-id="e58b8-110">Nel campo Modello di flusso di produzione, immettere un ID per il modello di flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="e58b8-110">In the Production flow model field, enter an ID for the production flow model.</span></span>
4. <span data-ttu-id="e58b8-111">Nel campo Tipo di modello selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="e58b8-111">In the Model type field, select an option.</span></span>
    * <span data-ttu-id="e58b8-112">Sono disponibili due tipi di modello: il tipo Produttività e il tipo Ore.</span><span class="sxs-lookup"><span data-stu-id="e58b8-112">There are two model types: Throughput type and Hours type.</span></span> <span data-ttu-id="e58b8-113">Per il tipo Produttività, la capacità delle celle di lavoro che utilizzano questo modello di flusso di produzione verrà calcolata e espressa in quantità di prodotto.</span><span class="sxs-lookup"><span data-stu-id="e58b8-113">For Throughput type, the capacity of work cells that use this production flow model will be expressed and calculated in product quantities.</span></span> <span data-ttu-id="e58b8-114">Per il tipo Ore, la capacità delle celle di lavoro che utilizzano questo modello di flusso di produzione verrà calcolata e espressa in ore.</span><span class="sxs-lookup"><span data-stu-id="e58b8-114">For Hours type, the capacity of work cells that uses this production flow model will be expressed and calculated in hours.</span></span> <span data-ttu-id="e58b8-115">Si noti che la proprietà non può essere modificata per un modello di flusso di produzione esistente.</span><span class="sxs-lookup"><span data-stu-id="e58b8-115">Note that this property can’t be changed for an existing production flow model.</span></span> <span data-ttu-id="e58b8-116">Dopo che una cella di lavoro dispone di prenotazioni di capacità, il tipo di modello di flusso di produzione non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="e58b8-116">After a work cell has capacity reservations, the production flow model type can’t be changed.</span></span>  
5. <span data-ttu-id="e58b8-117">Immettere il numero di giorni nel campo Ciclo EPE.</span><span class="sxs-lookup"><span data-stu-id="e58b8-117">Enter the number of days in the EPE Cycle.</span></span>
    * <span data-ttu-id="e58b8-118">L'intervallo descrive il periodo in cui ogni parte prodotta da un flusso di produzione o da una cella di lavoro verrà prodotta almeno una volta.</span><span class="sxs-lookup"><span data-stu-id="e58b8-118">The interval describes the period when every part produced by a production flow or work cell will be produced at least once.</span></span> <span data-ttu-id="e58b8-119">Più breve è il ciclo EPE, più flessibile è il processo di produzione.</span><span class="sxs-lookup"><span data-stu-id="e58b8-119">The shorter the EPE cycle, the more flexible the production process is.</span></span> <span data-ttu-id="e58b8-120">Se Ciclo EPE = 0, qualsiasi richiesta può essere prodotta nello stesso giorno.</span><span class="sxs-lookup"><span data-stu-id="e58b8-120">If EPE Cycle = 0, all demand can be produced in the same day.</span></span> <span data-ttu-id="e58b8-121">Il ciclo EPE viene utilizzato per la programmazione dei processi di lavorazione di produzione snella.</span><span class="sxs-lookup"><span data-stu-id="e58b8-121">The EPE Cycle is used to schedule lean process jobs.</span></span> <span data-ttu-id="e58b8-122">Nella programmazione di un processo per una cella di lavoro con il ciclo EPE = 5, il processo di programmazione cerca la capacità della cella di lavoro alla data di scadenza del ciclo EPE (5 giorni prima della data di scadenza) per verificare che il prodotto possa essere prodotto in quel ciclo.</span><span class="sxs-lookup"><span data-stu-id="e58b8-122">When scheduling a job on a work cell with EPE Cycle = 5, the scheduling process will look for capacity on the work cell at Due date - EPE Cycle (5 days ahead of the due date) to ensure that the product can be produced in that cycle.</span></span> <span data-ttu-id="e58b8-123">Il lead time di magazzino di un prodotto è in genere uguale o maggiore del ciclo EPE del processo di produzione correlato.</span><span class="sxs-lookup"><span data-stu-id="e58b8-123">The inventory lead time of a product is usually equal to or greater than the EPE Cycle of the related production process.</span></span>  
6. <span data-ttu-id="e58b8-124">Nel campo Tipo di pianificazione del periodo selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="e58b8-124">In the Planning period type field, select an option.</span></span>
    * <span data-ttu-id="e58b8-125">Dopo che una cella di lavoro dispone di prenotazioni di capacità, il tipo di periodo di pianificazione non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="e58b8-125">After a work cell has capacity reservations, the planning period type cannot by changed.</span></span> <span data-ttu-id="e58b8-126">È possibile selezionare solo i modelli di flusso di produzione con lo stesso tipo di periodo di questa cella di lavoro specifica.</span><span class="sxs-lookup"><span data-stu-id="e58b8-126">You can only select production flow models with the same period type for this given work cell.</span></span>  
7. <span data-ttu-id="e58b8-127">Nel campo Intervallo temporale pianificazione immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="e58b8-127">In the Planning time fence field, enter a number.</span></span>
    * <span data-ttu-id="e58b8-128">L'intervallo temporale di pianificazione descrive il numero di giorni in cui le prenotazioni di capacità possono essere effettuate per le celle di lavoro correlate.</span><span class="sxs-lookup"><span data-stu-id="e58b8-128">The planning time fence describes the number of days where capacity reservations can be made for the related work cells.</span></span> <span data-ttu-id="e58b8-129">Nell'intervallo temporale di pianificazione, immettere il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="e58b8-129">In the Planning time fence, enter the number of days.</span></span>   <span data-ttu-id="e58b8-130">I processi di lavorazione kanban che non rientrano in questo periodo non vengono pianificati con la pianificazione automatica.</span><span class="sxs-lookup"><span data-stu-id="e58b8-130">Kanban process jobs that fall outside of this period are not planned with automatic planning.</span></span> <span data-ttu-id="e58b8-131">L'intervallo temporale di pianificazione è in genere il doppio del lead time di magazzino medio dei prodotti creati in un flusso di produzione o una cella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e58b8-131">The planning time fence is typically two times the average inventory lead time of the products produced in a production flow or work cell.</span></span> <span data-ttu-id="e58b8-132">Il ciclo EPE non deve essere maggiore della metà dell'intervallo temporale di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="e58b8-132">The EPE Cycle should not be more than half the planning time fence.</span></span>     
8. <span data-ttu-id="e58b8-133">Selezionare un'opzione nel campo Reazione alla carenza di capacità.</span><span class="sxs-lookup"><span data-stu-id="e58b8-133">In the Capacity shortage reaction field, select an option.</span></span>
    * <span data-ttu-id="e58b8-134">Le opzioni sono: Posticipa, per posticipare la domanda completa dell'evento di programmazione al successivo giorno di produzione disponibile con produttività disponibile.</span><span class="sxs-lookup"><span data-stu-id="e58b8-134">The options include:   Postpone - Postponing the full demand of the scheduling event on the next available production day, with available throughput.</span></span> <span data-ttu-id="e58b8-135">Annulla, per terminare la pianificazione automatica per l'evento di programmazione e lascia i processi correlati non pianificati.</span><span class="sxs-lookup"><span data-stu-id="e58b8-135">Cancel - End the automatic planning for the scheduling event and leave the related jobs unplanned.</span></span>   <span data-ttu-id="e58b8-136">Aggiungi al giorno richiesto, per pianificare i processi necessari per il periodo richiesto.</span><span class="sxs-lookup"><span data-stu-id="e58b8-136">Add to requested day - Plan the requested jobs for the requested period.</span></span> <span data-ttu-id="e58b8-137">Ciò determina un overload della cella per questo giorno e richiede al responsabile della pianificazione di rivedere e interagire manualmente.</span><span class="sxs-lookup"><span data-stu-id="e58b8-137">This overloads the cell for this day and requires the planner to review and to a manual interaction .</span></span>   <span data-ttu-id="e58b8-138">Distribuire i diversi processi di evento di programmazione a tutti i giorni di produzione disponibili, a partire dal primo giorno disponibile.</span><span class="sxs-lookup"><span data-stu-id="e58b8-138">Distribute to available periods - Distribute the different jobs of the scheduling event to all available production days, beginning from the first available day.</span></span> <span data-ttu-id="e58b8-139">La quantità di distribuzione minima è la quantità del processo kanban.</span><span class="sxs-lookup"><span data-stu-id="e58b8-139">The minimum distribution quantity is the kanban job quantity.</span></span> <span data-ttu-id="e58b8-140">La distribuzione assegna la quantità di pianificazione minima (quantità kanban) per ogni giorno con sufficiente produttività disponibile.</span><span class="sxs-lookup"><span data-stu-id="e58b8-140">The distribution assigns the minimum planning quantity (kanban quantity) to every day with enough available throughput.</span></span>  

